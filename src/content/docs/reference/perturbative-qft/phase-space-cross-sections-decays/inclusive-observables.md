---
title: "Inclusive Observables"
description: "A practical guide to defining inclusive and infrared-safe observables by summing over final states with measurement weights."
sidebar:
  label: "Inclusive Observables"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11 and §26; Weinberg 1995, Vol. I, ch. 3; Coleman 2019, ch. 12; Schwartz 2014, chs. 5, 20, and 24"
topics:
  - inclusive observables
  - infrared safety
  - phase space
  - total rates
  - measurement functions
canonicalTopics:
  - inclusive-observable
  - infrared-safe-observable
  - measurement-function
  - real-virtual-cancellation
  - kln-theorem
researchStatus:
  established:
    - "Inclusive sums over experimentally indistinguishable final states are the standard way to define finite rates and cross sections in theories with massless radiation."
  active:
    - "Precision collider and decay predictions require refined measurement functions, jet algorithms, factorization, resummation, nonperturbative corrections, and detector-level definitions beyond the idealized formulas on this page."
---

## Summary

An **inclusive observable** is a rate or cross section that sums over a class of final states rather than demanding one exact particle list. Instead of asking for precisely

$$
I\to p_1+\cdots+p_n
$$

and nothing else, one assigns a weight $w(X)$ to every allowed final state $X$ and computes

$$
\sigma[w]
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}
\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2}\,w(X).
$$

For a decay of one particle $A$ of mass $M_A$, the corresponding weighted rate is

$$
\Gamma[w]
=
\frac{1}{2M_A}
\sum_X\frac{1}{S_X}
\int d\Pi_X(P_A)\,
\overline{|\mathcal M_{A\to X}|^2}\,w(X).
$$

Here $F_I$ is the appropriate initial flux factor for scattering, $d\Pi_X$ is Lorentz-invariant phase space, $S_X$ is the final-state identical-particle counting factor, and the bar denotes spin, polarization, color, or flavor sums and averages appropriate to the observable.

The point is not just experimental realism, though that is already reason enough. In theories with massless particles, exclusive probabilities for “exactly this final state and no arbitrarily soft radiation” can be infrared divergent or experimentally meaningless. Inclusive, infrared-safe observables are the quantities for which real emission and virtual corrections combine into finite physical predictions.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Inclusive observables combine amplitudes, phase space, and measurement weights before summing over final states](/figures/perturbative-qft/inclusive-observables-flow.svg)

<figcaption>

An inclusive observable is a weighted sum over final states. The amplitude supplies dynamics, phase space supplies kinematics, and the measurement function $w(X)$ tells the calculation which final states are counted, binned, or weighted. Infrared safety means that experimentally degenerate soft and collinear final states receive compatible weights.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/), and [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/).

## Core idea

Real detectors do not ask whether the final state is a mathematical Fock state with exactly $n$ particles and no additional radiation down to zero energy. They ask coarser questions: did the event pass a cut, which bin did it land in, how much energy entered a region, how many jets were reconstructed, or which inclusive decay channel was tagged?

The theory-side object that captures this is a **measurement weight**. A final state $X$ contributes with weight $w(X)$. The choices include:

| Choice of $w(X)$ | Observable |
|---|---|
| $w(X)=1$ for all allowed $X$ | fully inclusive total rate or total cross section |
| $w(X)=1$ if $X$ passes cuts, $0$ otherwise | cut cross section or fiducial rate |
| $w(X)=\delta(\mathcal O-\mathcal O(X))$ | differential distribution in an event variable $\mathcal O$ |
| $w(X)=\mathcal O(X)$ | weighted expectation value |

The amplitude tells us how likely each final state is. The measurement function tells us what question we asked.

## Setup and conventions

We use the qft.org scattering convention

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

with relativistically normalized asymptotic states. For a final state $X$ with total momentum $P_I$, the phase-space measure is

$$
d\Pi_X(P_I)
=(2\pi)^4\delta^{(4)}
\!\left(P_I-\sum_{a\in X}p_a\right)
\prod_{a\in X}\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

If $X$ contains $n_r$ identical particles of species $r$, the final-state counting factor is

$$
S_X=\prod_r n_r!.
$$

The symbol $\sum_X$ means a sum over particle species and discrete quantum numbers, together with the phase-space integral over momenta. In practice, $X$ may also include a bin label, a jet assignment, a flavor tag, or an energy resolution prescription.

:::caution[What is included in $X$?]
The same symbol $X$ can mean different levels of detail. In a partonic tree-level exercise, $X$ might be two named particles. In a physical QED or QCD observable, $X$ usually includes unresolved radiation, and the observable is defined only after specifying cuts, bins, or a jet algorithm.
:::

## Inclusive, exclusive, and semi-inclusive

The word “inclusive” is relative to a question.

A **fully inclusive** observable sums over all final states allowed by the conserved quantum numbers. For a fixed initial state, the total cross section is

$$
\sigma_{\rm tot}
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2}.
$$

A **semi-inclusive** observable fixes some macroscopic feature while summing over the rest. Examples include “one charged lepton with energy in this bin,” “at least two jets above this transverse momentum,” or “a hadronic final state with invariant mass in this window.” The theory expression is the same master formula with a nontrivial $w(X)$.

An **exclusive** observable attempts to isolate one exact final particle content. In a massive scalar toy model, this can be perfectly sensible. In QED or QCD, exact exclusivity with no soft photons or gluons is usually not a physical observable. The sharper the demand, the more it tends to probe unresolved infrared structure rather than a stable measurable number.

The useful slogan is:

$$
\text{exclusive amplitude} \quad\longrightarrow\quad
\text{inclusive observable by summing final states with a weight}.
$$

## Measurement functions

Let $\Phi_X$ denote a point in the phase space of the final state $X$. A measurement function is a map

$$
W_X:\Phi_X\mapsto \text{number}.
$$

Then the scattering observable is

$$
\sigma[W]
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}
\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2}\,W_X(\Phi_X).
$$

For a differential distribution in an observable $\mathcal O$, choose

$$
W_X(\Phi_X)=\delta\!\left(\mathcal O-\mathcal O_X(\Phi_X)\right),
$$

so that

$$
\frac{d\sigma}{d\mathcal O}
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}
\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2}\,
\delta\!\left(\mathcal O-\mathcal O_X(\Phi_X)\right).
$$

For an event selection, choose $W_X=1$ if the event passes the selection and $W_X=0$ otherwise. For an expectation value normalized by the total rate, use

$$
\langle \mathcal O\rangle
=
\frac{\sigma[\mathcal O]}{\sigma[1]}.
$$

The notation may look formal, but it is exactly how real predictions are organized: dynamics, phase space, and measurement definition are separate inputs.

## Infrared safety

The most important use of inclusive observables is the cancellation of infrared singularities. In a theory with massless radiation, loop diagrams can be singular when a virtual photon or gluon becomes soft or collinear. Real-emission diagrams can be singular in the corresponding regions of final-state phase space. Physical predictions become finite only when the observable treats degenerate final states consistently.

A final-state observable is **soft safe** if adding an unresolved soft particle does not change the measured value:

$$
W_{n+1}(\Phi_n,k)\longrightarrow W_n(\Phi_n)
\qquad\text{as }k^0\to0.
$$

For massless particles, it is **collinear safe** if replacing a collinear pair by its total momentum does not change the measured value:

$$
W_{n+1}(\ldots,zp,(1-z)p,\ldots)
\longrightarrow
W_n(\ldots,p,\ldots).
$$

These two limits are the operational content of infrared safety. They say that the observable cannot resolve distinctions that the long-distance physics makes arbitrarily cheap.

At next-to-leading order, the structure is schematically

$$
\begin{aligned}
\sigma^{\rm NLO}[W]
&=\frac{1}{F_I}
\int d\Pi_n\,
\left(
|\mathcal M_n^{(0)}|^2
+2\operatorname{Re}\{\mathcal M_n^{(0)*}\mathcal M_n^{(1)}\}
\right)W_n\\
&\quad+
\frac{1}{F_I}
\int d\Pi_{n+1}\,
|\mathcal M_{n+1}^{(0)}|^2W_{n+1}.
\end{aligned}
$$

The first line contains virtual corrections. The second line contains real emission. Neither line needs to be finite by itself. The observable is designed so that their singular parts cancel in the sum.

:::note[KLN logic]
The Kinoshita–Lee–Nauenberg theorem is often summarized as “sum over degenerate states.” The precise theorem is more careful, especially about initial-state degeneracies. For ordinary final-state measurements, the practical lesson is that infrared-safe weights are the correct objects to compute.
:::

## Total rates and the optical theorem

The simplest inclusive observable is the total rate, $W_X=1$. Total rates are special because unitarity relates them directly to forward scattering amplitudes. For a two-particle initial state,

$$
\sigma_{\rm tot}
=
\frac{1}{F_I}\,2\operatorname{Im}\mathcal M_{I\to I}^{\rm forward}.
$$

For a one-particle decay,

$$
\Gamma_{\rm tot}
=
\frac{1}{2M_A}\,2\operatorname{Im}\mathcal M_{A\to A}^{\rm forward}.
$$

These formulas are the rate-level form of the optical theorem. They work because a fully inclusive sum over final states is exactly what appears when one inserts a complete set of states into $S^\dagger S=1$.

For a nontrivial measurement weight $W_X$, the ordinary optical theorem is not enough by itself. One has inserted a measurement operator between the amplitude and its conjugate. Diagrammatically, this leads to cut diagrams with a measurement function acting on the cut phase space. That is the beginning of the technology used in infrared subtraction, jet physics, and factorization.

## Common pitfalls

**Calling an exact Fock-state count an observable.** In a theory with massless radiation, “exactly two charged particles and no photons” is not a robust physical question. A finite-energy detector cannot exclude photons of arbitrarily small energy.

**Forgetting the measurement function.** An inclusive prediction is not defined by saying “sum over radiation” in words. One must specify what is summed, what is vetoed, what is binned, and which quantum numbers are observed.

**Expecting real and virtual terms to be finite separately.** Infrared cancellation usually occurs only after adding all degenerate real and virtual contributions. Splitting the answer into real and virtual parts is a calculational device, not a physical separation.

**Confusing fully inclusive with experimentally inclusive.** A fully inclusive theoretical rate may sum over more states than an experiment accepts. Fiducial cuts and reconstruction efficiencies are part of the observable definition.

**Assuming final-state inclusivity solves every collinear problem.** Initial-state collinear singularities in high-energy hadron scattering are absorbed into parton distribution functions. That is factorization, not merely final-state inclusivity.

## Relations to other pages

- [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/) gives the unweighted and partially weighted rate formula that this page generalizes.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) treats fixed two-body kinematics before extra radiation is included.
- [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/) explains why fully inclusive rates are imaginary parts of forward amplitudes.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) introduces the unitarity idea before the rate formulas are applied.
- [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) explains the counting factor $S_X$ used in the phase-space sums.
- Later pages on infrared physics turn the soft and collinear safety conditions into factorization and resummation tools.

## Research status

The master formulas on this page are textbook-standard for stable asymptotic states in flat spacetime. The conceptual lesson is also settled: physical predictions in massless gauge theories are inclusive over experimentally unresolved radiation.

The active work is in the precision frontier. Modern applications require carefully designed jet algorithms, fiducial cuts, subtraction schemes, resummation, parton distributions, nonperturbative corrections, unstable-particle effects, and detector definitions. Those refinements preserve the same basic structure: amplitudes are integrated over phase space with a precisely defined measurement weight.

## Exercises

### Exercise 1: Recover the total cross section

Show that the weighted formula for $\sigma[W]$ reduces to the total cross section when $W_X=1$ for every allowed final state.

<details>
<summary><strong>Solution</strong></summary>

Substitute $W_X=1$ into

$$
\sigma[W]
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}
\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2}\,W_X.
$$

This gives

$$
\sigma[1]
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}
\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2},
$$

which is exactly the total cross section for the initial state $I$.

</details>

### Exercise 2: Differential distributions integrate back

For

$$
W_X(\Phi_X)=\delta(\mathcal O-\mathcal O_X(\Phi_X)),
$$

show that integrating $d\sigma/d\mathcal O$ over $\mathcal O$ gives $\sigma[1]$, assuming each final state receives exactly one value of $\mathcal O_X$.

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
\frac{d\sigma}{d\mathcal O}
=
\frac{1}{F_I}\sum_X\frac{1}{S_X}
\int d\Pi_X\,
\overline{|\mathcal M_{I\to X}|^2}
\delta(\mathcal O-\mathcal O_X).
$$

Integrating over $\mathcal O$ gives

$$
\int d\mathcal O\,\delta(\mathcal O-\mathcal O_X)=1.
$$

Therefore

$$
\int d\mathcal O\,\frac{d\sigma}{d\mathcal O}
=
\frac{1}{F_I}\sum_X\frac{1}{S_X}
\int d\Pi_X\,\overline{|\mathcal M_{I\to X}|^2}
=\sigma[1].
$$

</details>

### Exercise 3: Spot the infrared-unsafe observable

Consider two proposed QED observables for $e^+e^-$ annihilation:

1. events with exactly no photons in the final state;
2. events in which the total energy carried by photons below detector threshold $E_{\rm res}$ is ignored.

Which one is compatible with soft safety?

<details>
<summary><strong>Solution</strong></summary>

The first observable is not soft safe. Adding an arbitrarily soft photon changes the final state from “no photons” to “one photon,” so the weight jumps even as the photon energy tends to zero.

The second observable is soft safe in the intended sense. If an emitted photon is below the resolution threshold and is ignored by the measurement, then taking its energy to zero does not change the observed event. A complete precision calculation still needs a fully specified measurement, but the soft-safety logic is correct.

</details>

### Exercise 4: Real–virtual cancellation in one line

Suppose a regulated NLO calculation gives a virtual contribution

$$
\sigma_V=\sigma_0\left(1+\frac{a}{\epsilon}+b_V\right)
$$

and a real-emission contribution

$$
\sigma_R=\sigma_0\left(-\frac{a}{\epsilon}+b_R\right)
$$

for the same infrared-safe observable. What is the finite NLO result?

<details>
<summary><strong>Solution</strong></summary>

Add the two contributions:

$$
\sigma_{\rm NLO}=\sigma_V+\sigma_R
=\sigma_0\left(1+\frac{a}{\epsilon}+b_V-\frac{a}{\epsilon}+b_R\right).
$$

The singular terms cancel, leaving

$$
\sigma_{\rm NLO}=\sigma_0(1+b_V+b_R).
$$

The separate constants $b_V$ and $b_R$ can depend on the regulator and on the definition of the observable, but their physical combination is finite for an infrared-safe observable.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§10–11 and §26, for cross sections, decay rates, and the first discussion of infrared divergences.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering theory, rates, phase space, and unitarity.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5, 20, and 24, for rates, infrared divergences, and unitarity-based inclusive reasoning.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 12, for phase space, scattering applications, and the optical theorem in a pedagogical setting.

### Classic infrared references

- F. Bloch and A. Nordsieck, “Note on the Radiation Field of the Electron,” *Physical Review* **52** (1937), for the classic soft-photon cancellation mechanism.
- T. Kinoshita, “Mass Singularities of Feynman Amplitudes,” *Journal of Mathematical Physics* **3** (1962), and T. D. Lee and M. Nauenberg, “Degenerate Systems and Mass Singularities,” *Physical Review* **133** (1964), for the KLN theorem.

## Version history

- **2026-06-12:** Initial standardized page.
