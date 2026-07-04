---
title: "Fixed-Order Predictions"
description: "How precision observables are computed as truncated perturbative predictions with amplitudes, phase space, infrared-safe measurement functions, scales, PDFs, and input parameters."
sidebar:
  label: "Fixed-Order Predictions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11, 20, 26; Weinberg 1995, Vol. I, ch. 3 and ch. 13; Schwartz 2014, chs. 5, 20, 31–32; Ellis, Stirling, and Webber; Catani–Seymour 1997."
topics:
  - precision observables
  - fixed-order perturbation theory
  - infrared safety
  - collider predictions
canonicalTopics:
  - fixed-order-predictions
  - precision-observables
  - infrared-safe-observables
researchStatus:
  established:
    - "The construction of fixed-order predictions from renormalized amplitudes, phase space, subtraction or slicing, PDFs, and infrared-safe measurement functions is standard perturbative QFT technology."
  active:
    - "The frontier is not the definition of fixed order itself, but pushing predictions to higher orders, matching them to resummation and parton showers, controlling correlations among theory uncertainties, and defining observables that are both experimentally robust and theoretically clean."
---

## Summary

A **fixed-order prediction** is a perturbative prediction truncated after a finite power of the coupling. It is the workhorse behind precision tests of QFT: one defines an observable, computes the relevant renormalized amplitudes to a specified loop order, combines real and virtual radiation so infrared singularities cancel, folds in parton distributions when the initial state contains hadrons, and integrates over the measured phase-space region.

For a hadronic observable defined by a measurement function $F$, the schematic prediction is

$$
\sigma[F]
=
\sum_{i,j}\int_0^1 dx_1\,dx_2\,
 f_{i/h_1}(x_1,\mu_F)
 f_{j/h_2}(x_2,\mu_F)
 \widehat\sigma_{ij}[F](x_1P_1,x_2P_2;\mu_R,\mu_F),
$$

where $\mu_R$ is the renormalization scale and $\mu_F$ is the factorization scale. The partonic quantity is expanded as

$$
\widehat\sigma_{ij}[F]
=
\alpha_s^p(\mu_R)
\sum_{n=0}^{N}
\left(\frac{\alpha_s(\mu_R)}{2\pi}\right)^n
\widehat\sigma_{ij}^{(n)}[F](\mu_R,\mu_F)
+
O(\alpha_s^{p+N+1}).
$$

The labels LO, NLO, NNLO, and N³LO mean $N=0,1,2,3$ relative to the first nonzero contribution for the chosen process and observable. They do **not** by themselves guarantee accuracy. Accuracy also depends on the observable, scale choice, PDFs, electroweak corrections, nonperturbative effects, cuts, resummation needs, and experimental definition.

Fixed-order perturbation theory is powerful because it is local in final-state kinematics and systematically improvable. It is dangerous when the observable is not infrared safe, when a veto or endpoint creates large logarithms, or when the first nonzero contribution appears only at an unusually high order. Precision is a chain; the weakest link gets a vote.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![A fixed-order prediction combines an observable definition, renormalized amplitudes, infrared subtraction, phase-space integration, input parameters, and PDFs into a number or distribution.](/figures/perturbative-qft/fixed-order-predictions-flow.svg)

<figcaption>

A fixed-order prediction is not just a Feynman diagram. It is a controlled assembly of observable definition, renormalized amplitudes, real–virtual infrared cancellation, phase-space integration, input parameters, scale choices, and, for hadron collisions, PDFs and factorization.

</figcaption>
</figure>

## Prerequisites

You should know [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/), and the infrared-safety ideas in [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/).

For hadron-collider applications, you should also know what PDFs are and why collinear factorization is needed. Those topics are developed more fully in the Gauge Theories and the Standard Model and Renormalization, RG, and EFT volumes.

## Core idea

A prediction becomes a **precision observable** only after four questions have been answered.

| Question | What it fixes |
|---|---|
| What is measured? | The observable, cuts, bins, jet algorithm, fiducial region, and measurement function $F$. |
| What is computed? | The partonic amplitudes, perturbative order, renormalization scheme, and included channels. |
| How are singularities treated? | UV renormalization, IR cancellation, subtraction or slicing, and factorization into PDFs or fragmentation functions. |
| What is compared? | A number, distribution, likelihood input, unfolded quantity, or fiducial cross section with theory and experimental uncertainties. |

The mathematical object that connects these questions is the **measurement function**. For a final state with momenta $p_1,\ldots,p_n$, write $F_n(p_1,\ldots,p_n)$ for the weight assigned by the observable. A differential bin has a measurement function that is one inside the bin and zero outside, or a smooth version of the same idea.

Then a non-hadronic cross section has the schematic structure

$$
\sigma[F]
=
\frac{1}{\text{flux}}
\sum_X
\int d\Pi_X\,
|\mathcal M_X|^2 F_X,
$$

where $X$ runs over final states included at the chosen perturbative order. For a decay rate, replace the scattering flux by $2M$ for a parent particle of mass $M$.

This notation is deliberately compact. In real calculations, $|\mathcal M_X|^2$ includes spin and color sums or averages, counterterm contributions, loop integrals, regularization, renormalization, and possible subtraction terms. But the conceptual structure remains the same: amplitudes times phase space times the observable definition.

## Setup and conventions

This page uses the qft.org scattering conventions: covariantly normalized asymptotic states, invariant phase space, and

$$
S_{fi}
=
\delta_{fi}
+
i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

Renormalized couplings and masses are used unless stated otherwise. In QCD examples, $\alpha_s$ usually means the $\overline{\rm MS}$ coupling evaluated at a renormalization scale $\mu_R$. Hadronic predictions also use a factorization scale $\mu_F$ and PDFs in a specified PDF scheme.

A page about a particular observable should state at least:

| Item | Typical examples |
|---|---|
| Perturbative accuracy | LO, NLO, NNLO, N³LO; fixed order, resummed, matched, or showered. |
| Coupling expansion | QCD order, electroweak order, mixed QCD–EW order. |
| Inputs | $\alpha_s$, electroweak scheme, masses, widths, CKM parameters, PDFs. |
| Scales | Central $\mu_R$, $\mu_F$, and any resummation or matching scales. |
| Observable definition | Fiducial cuts, jet algorithm, binning, isolation, recombination, flavor scheme. |
| Uncertainties | Missing higher orders, PDFs, parametric inputs, nonperturbative corrections, matching, numerical integration. |

The more precise the observable, the less forgiving this bookkeeping becomes. This is where the glamour of Feynman diagrams meets the DMV of definitions. Both matter.

## Infrared-safe observables

Fixed-order predictions in gauge theories require infrared safety. An observable is infrared safe if adding an unresolved soft particle or splitting one particle into two collinear particles does not change the measured value.

For a final-state observable, the limiting conditions are schematically

$$
F_{n+1}(p_1,\ldots,p_n,k)
\longrightarrow
F_n(p_1,\ldots,p_n)
\qquad (k\to0),
$$

and

$$
F_{n+1}(p_1,\ldots,p_i,p_j,\ldots)
\longrightarrow
F_n(p_1,\ldots,p_i+p_j,\ldots)
\qquad (p_i\parallel p_j).
$$

These conditions are not aesthetic. They are what allow real-emission singularities to cancel virtual singularities in inclusive enough quantities. If an observable changes when an arbitrarily soft gluon is emitted, perturbation theory will try to assign a finite answer to an experimentally unresolvable distinction. It will fail, loudly and logarithmically.

Common infrared-safe quantities include sufficiently inclusive total cross sections, many jet observables defined with infrared-safe jet algorithms, and event shapes such as thrust. Common danger zones include exclusive parton multiplicities, strict vetoes, endpoint bins, isolation criteria that are not collinear safe, and observables sensitive to hadron species or detector thresholds.

## Anatomy of a fixed-order calculation

Suppose the Born process has $m$ final-state partons. At LO, the prediction has the form

$$
\sigma_{\rm LO}[F]
=
\int d\Pi_m\,d\sigma_m^{\rm B}\,F_m.
$$

At NLO, there are virtual corrections with the same resolved multiplicity and real-emission corrections with one extra parton:

$$
\sigma_{\rm NLO}[F]
=
\int d\Pi_m\,
\left(d\sigma_m^{\rm B}+d\sigma_m^{\rm V}\right)F_m
+
\int d\Pi_{m+1}\,d\sigma_{m+1}^{\rm R}F_{m+1}.
$$

This expression is morally correct but not yet a numerical formula. In dimensional regularization, $d\sigma_m^{\rm V}$ and $d\sigma_{m+1}^{\rm R}$ are separately singular. A subtraction method rewrites the same result as

$$
\sigma_{\rm NLO}[F]
=
\int d\Pi_{m+1}\,
\left(d\sigma_{m+1}^{\rm R}F_{m+1}-d\sigma_{m+1}^{\rm A}F_m\right)
+
\int d\Pi_m\,
\left(d\sigma_m^{\rm B}+d\sigma_m^{\rm V}+\int_1 d\sigma_{m+1}^{\rm A}\right)F_m.
$$

Here $d\sigma_{m+1}^{\rm A}$ is a local approximation to the real-emission singular limits. It is subtracted from the real phase space and added back after analytic integration over the unresolved one-particle phase space. The two bracketed terms are finite for an infrared-safe $F$.

At NNLO and beyond, the same idea persists but the taxonomy expands: double-real radiation, real–virtual terms, two-loop virtual terms, nested unresolved limits, and more elaborate subtraction or slicing methods. The physics is still cancellation of unobservable soft and collinear distinctions. The algebra just grows teeth.

## Hadron-collider predictions

For hadron collisions, the perturbative prediction is a convolution of partonic cross sections with PDFs:

$$
\sigma_{h_1h_2\to X}[F]
=
\sum_{i,j}\int_0^1 dx_1\,dx_2\,
 f_{i/h_1}(x_1,\mu_F)
 f_{j/h_2}(x_2,\mu_F)
 \widehat\sigma_{ij\to X}[F].
$$

The partonic cross section contains the short-distance process. The PDFs absorb long-distance collinear physics associated with the incoming hadrons. The separation scale $\mu_F$ is unphysical: all-order predictions are independent of it, but fixed-order predictions retain residual dependence.

Several consequences follow.

First, a hadronic fixed-order prediction is not determined by matrix elements alone. It also requires a PDF set, the value of $\alpha_s$ used with that PDF set, flavor-number conventions, heavy-quark mass treatment, and factorization scheme.

Second, changing the observable can change the relevant partonic channels. A total Drell–Yan prediction and a high-$p_T$ Drell–Yan prediction are not the same calculation with different numbers in the last line. The resolved radiation pattern matters.

Third, fiducial predictions are often more robust than extrapolated total predictions because they stay closer to what the detector actually measures. But fiducial cuts can introduce new scales, jet vetoes, or endpoint sensitivities that fixed order may not describe well without resummation.

## Perturbative orders and K factors

A process with Born scaling $\alpha_s^p\alpha^q$ has a fixed-order expansion of the form

$$
\sigma
=
\alpha_s^p\alpha^q
\left[
\sigma^{(0)}
+
\frac{\alpha_s}{2\pi}\sigma^{(1)}_{\rm QCD}
+
\frac{\alpha}{2\pi}\sigma^{(1)}_{\rm EW}
+
\left(\frac{\alpha_s}{2\pi}\right)^2\sigma^{(2)}_{\rm QCD}
+\cdots
\right].
$$

The **K factor** is the ratio of a higher-order prediction to a lower-order one, often

$$
K_{\rm NLO}
=
\frac{\sigma_{\rm NLO}}{\sigma_{\rm LO}}.
$$

K factors are useful diagnostics, not universal correction multipliers. A K factor for an inclusive rate need not apply to a differential distribution. A K factor in one fiducial region need not apply in another. A large K factor may signal a new channel, a poor scale choice, a large logarithm, a threshold enhancement, or simply that LO was a bad first approximation.

A good fixed-order page should therefore say not only “the result is NNLO,” but also what quantity is NNLO, in which expansion, with which cuts, and relative to which leading process.

## Example: a clean fixed-order observable

The classic clean example is the ratio

$$
R(Q)
=
\frac{\sigma(e^+e^-\to \text{hadrons})}
{\sigma(e^+e^-\to \mu^+\mu^-)}.
$$

Away from quark thresholds and narrow resonances, this observable is inclusive enough that perturbative QCD applies. Schematically,

$$
R(Q)
=
N_c\sum_q e_q^2
\left[
1+c_1\frac{\alpha_s(Q)}{\pi}
+c_2\left(\frac{\alpha_s(Q)}{\pi}\right)^2
+\cdots
\right]
+
\text{mass and power corrections}.
$$

This example illustrates why fixed-order predictions are so valuable. The observable is inclusive, the hard scale is clear, the leading term has a direct parton interpretation, and higher-order QCD corrections systematically improve the comparison.

It also illustrates why precision is never just “add one loop.” Near thresholds, quark masses and resonances matter. At lower energies, power corrections and nonperturbative physics matter. At very high precision, electroweak effects, input parameters, and correlations matter. The same formula can be a beautiful prediction or a trap, depending on where it is used.

## Inputs and uncertainty budget

A fixed-order prediction usually has several distinct uncertainty sources:

| Source | What it estimates |
|---|---|
| Scale variation | Missing higher perturbative orders. |
| PDFs | Uncertainty in fitted parton distributions. |
| $\alpha_s$ | Parametric uncertainty in the strong coupling. |
| Masses and widths | Parametric dependence on particle masses and unstable-particle treatment. |
| Electroweak scheme | Dependence on how electroweak inputs are chosen and converted. |
| Nonperturbative corrections | Hadronization, underlying event, intrinsic transverse momentum, power corrections. |
| Numerical integration | Monte Carlo integration error and convergence diagnostics. |
| Matching or merging | Dependence on how fixed-order predictions are combined with resummation or showers. |

These categories should not be mixed casually. A PDF error and a missing-higher-order error have different meanings. A numerical integration error is not a theory error. A shower tune variation is not the same as a fixed-order scale variation. Combining them responsibly requires knowing which are correlated across bins, processes, and experiments.

## Fixed order versus resummation and showers

Fixed order is strongest when all relevant scales are comparable. It becomes strained when the observable contains ratios of scales that generate large logarithms such as

$$
\alpha_s^n\log^m\!\frac{Q}{q},
\qquad m\le 2n.
$$

Examples include jet vetoes, transverse-momentum spectra at small $p_T$, threshold regions, event-shape endpoints, and observables sensitive to soft or collinear radiation. In such regions, fixed order may be formally correct but numerically badly organized. Resummation reorganizes the expansion by summing towers of logarithms to all orders.

Parton showers approximate soft and collinear radiation probabilistically and are essential for realistic event simulation. But a shower is not automatically a substitute for a fixed-order calculation. Modern precision predictions often combine fixed order with resummation or parton showers through matching and merging. The matched result inherits assumptions from both sides.

## Common pitfalls

**Calling a partonic quantity an observable.** A parton-level expression is not an experimental observable unless it is tied to an infrared-safe measurement definition and, for hadrons, to factorization.

**Using K factors as paint.** Multiplying every bin by an inclusive K factor can hide shape corrections and new channels.

**Confusing perturbative order with accuracy.** NNLO for the wrong observable definition can be less useful than NLO for the right fiducial observable.

**Forgetting new channels.** A formally higher-order channel can dominate a region of phase space if it opens a new topology or parton luminosity.

**Ignoring correlations.** Theory uncertainties are often correlated across bins and processes. Treating every bin as independent can make fits look more precise than they are.

**Trusting fixed order near endpoints.** If a distribution contains large logarithms or plus distributions, a fixed-order curve may be a poor description even when the total rate is well behaved.

## Relations to other pages

- [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/) explains the most common estimate of missing higher orders.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) introduces the observable-level logic behind real–virtual cancellation.
- [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) explains why sufficiently inclusive sums over degenerate states are finite.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explains how jet definitions make perturbative final states comparable to detector objects.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) introduces hard, collinear, and soft factorization.
- [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/) explains how large logarithms are reorganized beyond fixed order.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how UV-finite amplitudes enter predictions.

## Research status

- **Established:** The fixed-order framework, including UV renormalization, real–virtual IR cancellation, collinear factorization, and subtraction methods, is a standard part of perturbative QFT.
- **Active:** Many phenomenologically important processes are still being pushed to higher fixed orders, mixed QCD–electroweak accuracy, improved heavy-mass dependence, and better matching to resummation and parton showers.
- **Subtle:** Theory-uncertainty estimates are not themselves observables. Scale variation is useful but not a theorem, and correlations among theory errors remain a major issue in precision fits.
- **Speculative:** None of the basic fixed-order framework is speculative. Some advanced uncertainty models and automation strategies are active methodological proposals rather than universal standards.

## Exercises

### Exercise 1: Infrared safety of a total rate

Let $F_n=1$ for every allowed final-state multiplicity $n$. Show that this measurement function is soft and collinear safe.

<details>
<summary><strong>Solution</strong></summary>

Soft safety requires

$$
F_{n+1}(p_1,\ldots,p_n,k)\to F_n(p_1,\ldots,p_n)
\qquad (k\to0).
$$

Both sides are equal to $1$. Collinear safety requires

$$
F_{n+1}(p_1,\ldots,p_i,p_j,\ldots)
\to
F_n(p_1,\ldots,p_i+p_j,\ldots)
\qquad (p_i\parallel p_j).
$$

Again both sides are equal to $1$. Therefore a fully inclusive total rate does not change when an unresolved soft particle is emitted or when a particle splits into collinear daughters. This is the simplest infrared-safe measurement function.

</details>

### Exercise 2: Why “exactly two partons” is not infrared safe

Consider a measurement function that equals $1$ only if the final state contains exactly two partons and equals $0$ otherwise. Explain why this is not infrared safe.

<details>
<summary><strong>Solution</strong></summary>

At two-parton Born level, the measurement gives $F_2=1$. Now add a gluon with momentum $k$. If the observable literally counts partons, the three-parton final state has $F_3=0$, even when $k\to0$.

Thus

$$
F_3(p_1,p_2,k)\not\to F_2(p_1,p_2)
\qquad (k\to0).
$$

The observable distinguishes a two-parton state from a two-parton state plus an arbitrarily soft gluon. Such a distinction cannot be made physically at finite resolution and prevents the real-emission singularity from canceling the virtual singularity.

A jet algorithm can repair this by defining jets rather than bare partons, provided the algorithm is infrared and collinear safe.

</details>

### Exercise 3: NLO real–virtual bookkeeping

For a Born process with $m$ final-state partons, identify the final-state multiplicities appearing in the virtual and real NLO terms.

<details>
<summary><strong>Solution</strong></summary>

The virtual NLO correction has the same resolved external multiplicity as the Born process: it contributes on $m$-body phase space. It contains one-loop corrections to the $m$-parton amplitude and counterterm contributions.

The real NLO correction has one additional parton: it contributes on $(m+1)$-body phase space. Its singular regions occur when the additional parton becomes soft or collinear with another parton. A subtraction method maps these unresolved regions back onto $m$-body kinematics so that the singularities cancel against the virtual terms.

</details>

### Exercise 4: K factors are not universal

Suppose an inclusive cross section has $K_{\rm NLO}=1.3$. Give two reasons why multiplying every bin of a differential distribution by $1.3$ may be wrong.

<details>
<summary><strong>Solution</strong></summary>

First, radiative corrections can change shapes. Real emission may populate high transverse-momentum bins more strongly than low transverse-momentum bins, so the local ratio

$$
K(x)=\frac{d\sigma_{\rm NLO}/dx}{d\sigma_{\rm LO}/dx}
$$

may vary across the distribution.

Second, a new partonic channel can enter at NLO. Its contribution may be negligible in the inclusive average but important in a specific region because of parton luminosities or kinematic cuts.

The inclusive K factor is therefore a diagnostic of the total rate, not a universal bin-by-bin correction.

</details>

### Exercise 5: Fixed order and a large logarithm

Consider a dimensionless observable with perturbative form

$$
O(Q,q)
=
1+\alpha_s c_1\log^2\!\frac{Q}{q}+O(\alpha_s^2).
$$

Why might fixed order become unreliable when $q\ll Q$?

<details>
<summary><strong>Solution</strong></summary>

If $q\ll Q$, the logarithm $L=\log(Q/q)$ can be large. The nominal expansion parameter is no longer just $\alpha_s$ but combinations such as $\alpha_s L^2$.

Even when $\alpha_s\ll1$, the product $\alpha_s L^2$ may be order one. Higher orders can then contain terms like

$$
\alpha_s^n L^{2n},
$$

which are not suppressed relative to the first correction. The fixed-order expansion is badly organized, and resummation is needed to sum the enhanced logarithmic terms.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§10–11, 20, and 26, for scattering amplitudes, cross sections, loop corrections, and infrared divergences.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3 and ch. 13, for scattering theory, perturbation theory, and infrared issues.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5, 20, 31, and 32, for cross sections, infrared divergences, precision Standard Model tests, and QCD factorization.
- R. K. Ellis, W. J. Stirling, and B. R. Webber, *QCD and Collider Physics*, for the classic collider-QCD fixed-order framework.
- S. Catani and M. H. Seymour, “A General Algorithm for Calculating Jet Cross Sections in NLO QCD,” *Nuclear Physics B* **485** (1997), for dipole subtraction.
- S. Frixione, Z. Kunszt, and A. Signer, “Three-Jet Cross Sections to Next-to-Leading Order,” *Nuclear Physics B* **467** (1996), for another standard NLO subtraction framework.
- G. P. Salam, “Towards Jetography,” *European Physical Journal C* **67** (2010), for jet definitions and infrared safety.
- LHC Higgs Cross Section Working Group reports and the Particle Data Group reviews for phenomenological conventions, input parameters, and precision-observable practice.

## Version history

- **2026-06-13:** Initial polished draft for the Precision Observables chapter, emphasizing the anatomy of fixed-order predictions, infrared safety, hadronic factorization, uncertainty bookkeeping, and the handoff to scale variation and resummation.
