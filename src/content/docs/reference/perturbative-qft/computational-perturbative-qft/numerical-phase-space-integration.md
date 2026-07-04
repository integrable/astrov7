---
title: "Numerical Phase-Space Integration"
description: "A reproducible workflow for integrating scattering and decay observables over phase space with Monte Carlo methods, adaptive maps, cuts, and validation checks."
sidebar:
  label: "Numerical Phase Space"
  order: 4
level: Advanced
status: "Polished draft"
source: "Lepage VEGAS; Byckling–Kajantie; Kleiss–Pittau; Catani–Seymour; Frixione–Kunszt–Signer; Weinzierl; Ellis–Stirling–Webber; Schwartz."
topics:
  - computational perturbative QFT
  - phase-space integration
  - Monte Carlo integration
  - collider observables
  - numerical validation
canonicalTopics:
  - numerical-phase-space-integration
  - monte-carlo-phase-space
  - multi-channel-integration
  - phase-space-workflows
researchStatus:
  established:
    - "Monte Carlo phase-space integration, adaptive importance sampling, and multi-channel mappings are standard tools for decay rates, cross sections, and differential distributions."
  active:
    - "High-multiplicity final states, subtraction at higher orders, negative weights, GPU-aware event generation, and uncertainty propagation remain active computational areas."
---

## Summary

Numerical phase-space integration is the bridge between an amplitude and a prediction for an observable. Once an amplitude has been squared, summed or averaged over unobserved quantum numbers, and combined with flux factors, PDFs when needed, measurement functions, and cuts, the remaining problem is usually an integral over the allowed final-state momenta.

For an $n$-particle final state, a schematic scattering observable is

$$
\sigma[F]
=
\frac{1}{\mathcal F}
\int d\Phi_n(P;p_1,\ldots,p_n)\,
\overline{|\mathcal M(p_1,\ldots,p_n)|^2}\,
F_n(p_1,\ldots,p_n),
$$

where $\mathcal F$ is the incoming flux factor, $d\Phi_n$ is Lorentz-invariant phase space, and $F_n$ is the measurement function implementing cuts, bins, event shapes, or acceptance criteria. Decay rates use the same logic with $\mathcal F=2M$ for a parent particle of mass $M$.

The stable computational problem is not merely “sample random points.” It is to design a map from simple variables to physical momenta so that the singular, peaked, constrained, and cut-dependent structure of the integrand is visible to the integrator.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 58rem;">

![Numerical phase-space integration workflow from observable definition to phase-space map, weighted integrand, Monte Carlo estimate, and validated result](/figures/perturbative-qft/numerical-phase-space-integration.svg)

<figcaption>

Numerical phase-space integration is a map-design problem before it is a sampling problem. The amplitude, measurement function, singular channels, random seeds, grids, and logs are part of the calculation, not optional bookkeeping.

</figcaption>
</figure>

This page explains how to set up numerical phase-space integration so that the result is normalized, stable, reproducible, and physically checkable.

## Prerequisites

You should know [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/), [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/), [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/), [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/), [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), and [Symbolic Amplitude Tools](/perturbative-qft/computational-perturbative-qft/symbolic-amplitude-tools/).

## Core idea

A phase-space integral combines three objects that should be kept logically separate:

| Object | What it does | Typical failure mode |
|---|---|---|
| phase-space measure | enforces on-shell constraints and momentum conservation | wrong factors of $2\pi$, $2E$, symmetry factors, or Jacobians |
| squared matrix element | supplies the dynamics | missing spin/color averages, gauge artifacts, unstable algebra |
| measurement function | defines the observable | non-IR-safe cuts, binning mistakes, hidden units, discontinuities |

The numerical task is to rewrite the physical integral as an integral over a unit hypercube,

$$
I=\int_{[0,1]^D} d^Dx\,w(x),
$$

where $x$ are sampling variables and $w(x)$ includes the matrix element, measurement function, Jacobian, PDFs when present, and any symmetry factors. The art is choosing the map $x\mapsto \Phi_n$ so that $w(x)$ is not impossible for the integrator to learn.

Monte Carlo methods converge slowly in the number of samples, roughly like $N^{-1/2}$, but their scaling with dimension is mild compared with deterministic grids. That is why they dominate high-dimensional phase-space integration. The price is that every quoted numerical answer needs a meaningful statistical error and enough metadata to reproduce it.

## Setup and conventions

Use the scattering and state conventions fixed in the Perturbative QFT volume. The $n$-body Lorentz-invariant phase space is

$$
d\Phi_n(P;p_1,\ldots,p_n)
=
(2\pi)^4\delta^{(4)}\!\left(P-\sum_{i=1}^n p_i\right)
\prod_{i=1}^n \frac{d^3\mathbf p_i}{(2\pi)^3 2E_i}.
$$

For a decay of a particle of mass $M$,

$$
d\Gamma
=
\frac{1}{2M}\overline{|\mathcal M|^2}\,d\Phi_n.
$$

For a two-particle scattering process,

$$
d\sigma
=
\frac{1}{4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}}
\overline{|\mathcal M|^2}\,d\Phi_n.
$$

If the final state contains identical particles, include the appropriate factor $1/S$ in the observable definition or in the event weight, but not both. If hadronic initial states are present, the partonic integral is folded with PDFs and summed over parton species. In that case, the sampling variables include parton momentum fractions and the factorization scale belongs in the metadata.

## Monte Carlo estimators

The simplest Monte Carlo estimator starts from an integral

$$
I=\int_\Omega dx\,f(x).
$$

If points are sampled with probability density $p(x)$, normalized by $\int_\Omega dx\,p(x)=1$, then

$$
I=\int_\Omega dx\,p(x)\frac{f(x)}{p(x)},
$$

and the estimator is

$$
\widehat I_N
=
\frac{1}{N}\sum_{a=1}^N \frac{f(x_a)}{p(x_a)},
\qquad x_a\sim p.
$$

Its variance is

$$
\operatorname{Var}(\widehat I_N)
=
\frac{1}{N}\left[\int_\Omega dx\,p(x)\left(\frac{f(x)}{p(x)}\right)^2-I^2\right].
$$

This formula is the entire reason for importance sampling. The ideal choice would have $p(x)\propto |f(x)|$, which makes the sampled weights nearly constant. We rarely know that density in advance, so adaptive algorithms try to approximate useful sampling densities from previous evaluations.

For a phase-space integral, the integrand may contain resonant denominators, soft singularities, collinear enhancements, threshold square roots, PDFs with strong endpoint behavior, and discontinuities from cuts. A flat random scan is usually a heroic way to waste electricity.

## Phase-space maps

A phase-space map is a parametrization

$$
x\in [0,1]^D
\quad\longmapsto\quad
\{p_1(x),\ldots,p_n(x)\}
$$

such that the output momenta are on shell and conserve total momentum. The weight is

$$
w(x)=J(x)\,\frac{1}{\mathcal F}\,
\overline{|\mathcal M(\{p_i(x)\})|^2}\,
F_n(\{p_i(x)\}),
$$

where $J(x)$ is the Jacobian for the chosen parametrization.

The most useful identity for building maps recursively is phase-space factorization. If $q=p_1+\cdots+p_k$ and $s_q=q^2$, then

$$
d\Phi_n(P;p_1,\ldots,p_n)
=
\frac{ds_q}{2\pi}\,
 d\Phi_{n-k+1}(P;q,p_{k+1},\ldots,p_n)\,
 d\Phi_k(q;p_1,\ldots,p_k).
$$

This identity lets an $n$-body final state be generated as a sequence of two-body decays and invariant-mass integrations. It is also how one builds channels adapted to resonances: if an amplitude has a propagator enhanced near $q^2=M^2$, use $s_q$ as a sampling variable and map it with a density resembling the resonance shape.

A good map does four things.

| Goal | Practical meaning |
|---|---|
| exact constraints | on-shell conditions and momentum conservation are built in, not imposed approximately |
| transparent Jacobian | the normalization is auditable |
| singular alignment | soft, collinear, threshold, and resonant regions are controlled by explicit variables |
| cut stability | small changes in random variables do not produce pathological bin jumping more than necessary |

No single map is best for every diagram or kinematic region. That is why multi-channel integration exists.

## Importance sampling and adaptive grids

Suppose an integrand is large near $x=0$, for example $f(x)\sim x^{-a}$ with $0<a<1$. Sampling uniformly gives a finite integral but large variance when $a$ is close to $1$. A change of variables can flatten the endpoint:

$$
x=y^{1/(1-a)},
\qquad
 dx=\frac{1}{1-a}y^{a/(1-a)}dy.
$$

Then

$$
x^{-a}dx
=\frac{1}{1-a}dy,
$$

so the singular factor has been absorbed into the Jacobian. This toy example is the local logic behind soft, collinear, and resonance mappings.

Adaptive algorithms such as VEGAS-style integration learn one-dimensional projections of $|w(x)|$ and concentrate samples where those projections are large. This works well when the dominant structure factorizes approximately by coordinate. It works less well when the integrand has curved ridges, competing resonances, sector-dependent peaks, or cancellations between positive and negative contributions.

When the integrand has several different singular structures, use a multi-channel decomposition. Write the same integral as a sum over channels,

$$
I=\sum_{c=1}^{N_{\rm ch}}\alpha_c
\int_{[0,1]^D} d^Dx\,w_c(x),
\qquad
\sum_c\alpha_c=1,
$$

where each channel has its own map and sampling density. The weights $\alpha_c$ can be optimized during warm-up. In practice, channels often correspond to different resonant histories, soft/collinear pairings, or diagram topologies.

## Measurement functions and cuts

A measurement function turns momenta into the observable being reported. It may be a cut,

$$
F_n(\Phi_n)=\Theta(p_{T,j}>p_T^{\rm min})\,
\Theta(|\eta_j|<\eta_{\rm max}),
$$

or a histogram bin,

$$
F_n(\Phi_n)=\Theta(O(\Phi_n)-O_a)\Theta(O_b-O(\Phi_n)),
$$

or an event-shape weight. The notation $F_n$ is intentionally broad: it includes analysis cuts, reconstruction definitions, jet algorithms, binning, and acceptance.

For infrared-sensitive calculations, the measurement function must be infrared safe. Adding a soft particle or splitting a massless particle into collinear fragments should not change the measured value discontinuously in the singular limit. More formally, for a final-state observable,

$$
F_{n+1}(p_1,\ldots,p_n,k)\to F_n(p_1,\ldots,p_n)
\quad\text{as } k\to 0,
$$

and analogous limits should hold for collinear splittings. Without this property, real and virtual infrared singularities cannot cancel in the observable.

A good numerical implementation treats the measurement function as a first-class part of the calculation. Keep the cuts and bin edges in a configuration file or manifest, not buried in handwritten code branches. Unit tests for cuts are not glamorous, but neither is discovering that an entire distribution is shifted because rapidity and pseudorapidity were silently mixed.

## Singular regions and subtraction

At fixed order beyond leading order, phase-space integration is entangled with infrared subtraction. A typical NLO observable is organized schematically as

$$
\sigma^{\rm NLO}[F]
=
\int_{\Phi_{n+1}}\left[d\sigma_R F_{n+1}-d\sigma_A F_A\right]
+
\int_{\Phi_n}\left[d\sigma_V+\int_1 d\sigma_A\right]F_n.
$$

Here $d\sigma_R$ is the real-emission contribution, $d\sigma_V$ is the virtual contribution, and $d\sigma_A$ is a local approximation that matches the singular behavior of the real term. The symbol $F_A$ indicates the measurement evaluated on the mapped lower-multiplicity kinematics associated with the subtraction term.

The point is local finiteness. The first integral should be numerically integrable in four dimensions because $d\sigma_R F_{n+1}-d\sigma_A F_A$ is finite in unresolved limits. The second integral should be finite after the integrated subtraction term cancels the explicit poles in $d\sigma_V$.

For numerical work, this means the integrator is not only sampling phase space. It is sampling differences of terms that can be individually huge. Stability near subtraction boundaries is a major validation target.

## Error estimates and convergence

A Monte Carlo error bar is a statistical estimate conditional on the integrand, map, random sequence, and implementation. It is not automatically the total theoretical uncertainty. Keep the following uncertainties conceptually distinct:

| Uncertainty | Source | How it is tested |
|---|---|---|
| Monte Carlo error | finite sampling | independent runs, error scaling with $N$ |
| integration-systematic error | bad maps, missed peaks, adaptation bias | map comparisons, channel scans, bin-by-bin stability |
| numerical precision error | floating-point cancellation, unstable algebra | higher precision, phase-space stress tests |
| perturbative uncertainty | missing higher orders | scale variation, order comparison, resummation tests |
| parametric uncertainty | masses, couplings, PDFs, inputs | input variations and covariance propagation |

For independent Monte Carlo runs with estimates $I_r$ and statistical errors $\Delta_r$, a useful consistency diagnostic is the pull

$$
\chi_r=\frac{I_r-\overline I}{\Delta_r},
$$

where $\overline I$ is the weighted average. Pulls much larger than expected may indicate underestimated errors, missed regions, or correlated random streams.

A second basic diagnostic is error scaling. If the integrand is well behaved and samples are effectively independent, the estimated error should scale approximately as

$$
\Delta_N\propto \frac{1}{\sqrt N}.
$$

Failure of this scaling does not automatically mean the result is wrong, but it means the quoted error is not yet trustworthy.

## Unweighting and event generation

An integrator produces weighted estimates. An event generator may also need unweighted events. If events are sampled with weights $w_i$, one common accept–reject procedure accepts event $i$ with probability

$$
P_i=\frac{w_i}{w_{\max}},
$$

where $w_{\max}$ is an upper bound on the event weight. The unweighting efficiency is roughly

$$
\epsilon_{\rm unw}
=\frac{\langle w\rangle}{w_{\max}}.
$$

Large weight tails kill efficiency. They also warn that the sampling map is poorly adapted or that rare regions have large physical contributions. In precision work, weight distributions are diagnostic data. Save them.

Negative weights require special care. They appear naturally in subtraction-based fixed-order calculations and in some matching schemes. Negative weights are not “bad events”; they are signed contributions to an estimator. But they increase variance and complicate downstream analysis, so their fraction and distribution should be reported.

## Validation checklist

A serious numerical phase-space result should pass several checks.

| Check | Question |
|---|---|
| normalization check | Does the code reproduce known analytic phase-space volumes or two-body formulas? |
| soft/collinear check | Does the integrand approach the expected factorized behavior? |
| cut check | Are cuts and bins implemented with known test events? |
| symmetry check | Does the result respect exchange symmetries and charge/color sums? |
| gauge check | Do gauge-variant pieces cancel in physical observables? |
| convergence check | Does the estimate stabilize under increased samples and independent seeds? |
| channel check | Do alternative maps agree within errors? |
| benchmark check | Does the code reproduce published or internally archived benchmark points? |

For a new calculation, start with overkill checks on a small problem. Then scale up. Debugging a high-multiplicity calculation without a two-body or three-body normalization test is how one invites gremlins into the lab and hands them a keyboard.

## Common pitfalls

**Treating the Monte Carlo error as the full theory error.** A tiny statistical error does not estimate missing higher orders, PDF uncertainty, parametric uncertainty, or scheme dependence.

**Using a flat map for a sharply structured integrand.** The result may converge eventually, in the same sense that a glacier eventually makes landscaping choices.

**Losing normalization factors.** The phase-space measure, flux factor, spin/color averages, identical-particle factors, PDF Jacobians, and histogram bin widths are separate objects. Record where each one enters.

**Forgetting IR safety.** If the observable is not infrared safe, adding more samples will not make real–virtual cancellation appear.

**Trusting one seed.** One random stream can look calmer than it deserves. Use independent runs and compare pulls.

**Ignoring negative weights.** Signed weights are legitimate, but the variance and effective sample size must be reported honestly.

**Not saving adaptation data.** Adaptive grids, channel weights, warm-up choices, and failed trial runs are part of the computational history.

## Relations to other pages

- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) defines the invariant measure used here.
- [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) gives the simplest analytic benchmark for phase-space normalization.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) explains why observable definitions matter for cancellation of unresolved radiation.
- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) explains how phase-space integration enters perturbative predictions.
- [Parton-Shower Matching](/perturbative-qft/precision-observables/parton-shower-matching/) uses weighted and unweighted event samples in matched predictions.
- [Reproducibility and Benchmarks](/perturbative-qft/computational-perturbative-qft/reproducibility-and-benchmarks/) explains how to package numerical results so that they can be checked later.

## Research status

- **Established:** Lorentz-invariant phase-space measures, recursive phase-space factorization, Monte Carlo estimators, adaptive importance sampling, and multi-channel integration are standard tools of perturbative phenomenology.
- **Active:** Efficient handling of high-multiplicity final states, local subtraction at high orders, negative-weight reduction, variance reduction, differentiable event generation, GPU acceleration, and reproducible long-running integrations remain active computational problems.
- **Speculative:** Machine-learned phase-space maps and normalizing-flow methods are promising in some settings, but they do not replace analytic control of singular limits and normalization checks.

## Exercises

### Exercise 1: Monte Carlo variance with importance sampling

Let

$$
I=\int_0^1 dx\,x^{-a},
\qquad 0<a<1.
$$

Use the probability density

$$
p_b(x)=(1-b)x^{-b},
\qquad 0<b<1.
$$

For which value of $b$ is the Monte Carlo weight constant?

<details>
<summary><strong>Solution</strong></summary>

The sampled weight is

$$
\frac{f(x)}{p_b(x)}
=
\frac{x^{-a}}{(1-b)x^{-b}}
=
\frac{1}{1-b}x^{b-a}.
$$

This is constant when

$$
b=a.
$$

Then

$$
\frac{f(x)}{p_a(x)}=\frac{1}{1-a},
$$

which equals the exact integral. The variance vanishes in this idealized case. Real phase-space integrals are not this kind, sadly, but the lesson survives: sample like the singularity.

</details>

### Exercise 2: Recursive phase-space factorization

Use the insertion

$$
1=\int \frac{ds_q}{2\pi}\,(2\pi)\delta(q^2-s_q)
$$

and an integral over $q$ to explain why an $n$-body phase space can be factorized into a lower-body phase space times a decay phase space.

<details>
<summary><strong>Solution</strong></summary>

Let $q=p_1+\cdots+p_k$. Insert

$$
1=\int d^4q\,\delta^{(4)}\!\left(q-\sum_{i=1}^k p_i\right)
$$

into the $n$-body phase-space measure, and then insert an invariant-mass integral for $q^2=s_q$. The delta function enforcing total momentum conservation becomes a delta function for the process

$$
P\to q+p_{k+1}+\cdots+p_n,
$$

while the remaining delta function enforces

$$
q\to p_1+\cdots+p_k.
$$

The result is

$$
d\Phi_n(P;p_1,\ldots,p_n)
=
\frac{ds_q}{2\pi}\,
 d\Phi_{n-k+1}(P;q,p_{k+1},\ldots,p_n)\,
 d\Phi_k(q;p_1,\ldots,p_k).
$$

This is the basis for sequential-decay phase-space generators.

</details>

### Exercise 3: Pull test for two runs

Two independent integrations give

$$
I_1=1.003\pm0.004,
\qquad
I_2=0.991\pm0.005.
$$

Compute the difference in units of the combined statistical error.

<details>
<summary><strong>Solution</strong></summary>

For independent errors, the uncertainty on the difference is

$$
\Delta_{12}=\sqrt{0.004^2+0.005^2}=\sqrt{41}\times10^{-3}\simeq0.0064.
$$

The difference is

$$
I_1-I_2=0.012.
$$

Thus the pull is

$$
\frac{I_1-I_2}{\Delta_{12}}
\simeq
\frac{0.012}{0.0064}
\simeq1.9.
$$

A $1.9\sigma$ difference is not conclusive by itself, but it is large enough to motivate more samples or additional independent runs if this is a benchmark quantity.

</details>

### Exercise 4: Bin-width normalization

A Monte Carlo program fills a histogram with bin weights approximating

$$
\sigma_a=\int_{O_a}^{O_{a+1}} dO\,\frac{d\sigma}{dO}.
$$

What must be done to plot $d\sigma/dO$ rather than the bin-integrated cross section?

<details>
<summary><strong>Solution</strong></summary>

The bin content $\sigma_a$ approximates the integral over the bin. To estimate the differential distribution, divide by the bin width:

$$
\left.\frac{d\sigma}{dO}\right|_{a}
\simeq
\frac{\sigma_a}{O_{a+1}-O_a}.
$$

This is a common normalization trap. The distinction matters especially when bins have unequal widths.

</details>

## References

- G. P. Lepage, “A New Algorithm for Adaptive Multidimensional Integration,” *Journal of Computational Physics* **27** (1978), 192–203, for the VEGAS adaptive-integration idea.
- E. Byckling and K. Kajantie, *Particle Kinematics*, for invariant phase space and kinematic parametrizations.
- R. Kleiss and R. Pittau, “Weight Optimization in Multichannel Monte Carlo,” *Computer Physics Communications* **83** (1994), 141–146, for multi-channel integration.
- S. Catani and M. H. Seymour, “A General Algorithm for Calculating Jet Cross Sections in NLO QCD,” *Nuclear Physics B* **485** (1997), 291–419, for dipole subtraction and local real-emission counterterms.
- S. Frixione, Z. Kunszt, and A. Signer, “Three-Jet Cross Sections to Next-to-Leading Order,” *Nuclear Physics B* **467** (1996), 399–442, for subtraction methods in numerical NLO calculations.
- S. Weinzierl, “Introduction to Monte Carlo Methods,” arXiv:hep-ph/0006269, for a practical overview of Monte Carlo integration in particle physics.
- R. K. Ellis, W. J. Stirling, and B. R. Webber, *QCD and Collider Physics*, for phase space, jets, and perturbative collider observables.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20 and 32, for infrared-safe observables, jets, and parton-level calculations.

## Version history

- **2026-06-13:** Initial polished draft. Added workflow figure, Monte Carlo estimator formulas, phase-space factorization, subtraction overview, validation checklist, and solved exercises.
