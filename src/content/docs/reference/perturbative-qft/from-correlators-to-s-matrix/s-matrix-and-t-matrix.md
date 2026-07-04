---
title: "S-Matrix and T-Matrix"
description: "The normalization of the S-matrix, the transition operator T, and the invariant amplitude used in perturbative scattering calculations."
sidebar:
  label: "S-Matrix and T-Matrix"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, ch. 3; Coleman 2019, chs. 7 and 11–12; Srednicki 2007, §§10–11; Schwartz 2014, chs. 5–7 and 24"
topics:
  - S-matrix
  - T-matrix
  - invariant amplitude
  - scattering amplitudes
  - unitarity
canonicalTopics:
  - s-matrix
  - t-matrix
  - invariant-amplitude
  - scattering-normalization
researchStatus:
  established:
    - "The split S = 1 + iT, the momentum-conserving delta function, and the invariant amplitude normalization are textbook-standard once state conventions are fixed."
  active:
    - "Infrared-safe S-matrix definitions in massless gauge theories, unstable-particle treatments, and nonperturbative S-matrix constructions require additional machinery beyond this page."
---

## Summary

The **S-matrix** is the overlap between outgoing and incoming asymptotic states:

$$
S_{\beta\alpha}
=
\langle\beta,\mathrm{out}|\alpha,\mathrm{in}\rangle.
$$

In this volume we write

$$
S=\mathbf 1+iT,
$$

and define the invariant amplitude $\mathcal M_{\beta\alpha}$ by

$$
\langle\beta|iT|\alpha\rangle
=
i(2\pi)^4\delta^{(4)}(P_\beta-P_\alpha)\mathcal M_{\beta\alpha}.
$$

Equivalently,

$$
\langle\beta|T|\alpha\rangle
=
(2\pi)^4\delta^{(4)}(P_\beta-P_\alpha)\mathcal M_{\beta\alpha}.
$$

This page explains what each layer means: $S$ is the full overlap, $\mathbf 1$ is the no-scattering identity piece, $T$ is the transition operator, the delta function is forced by translation invariance, and $\mathcal M$ is the stripped amplitude inserted into phase-space formulas for decay rates and cross sections.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![The full S-matrix element splits into an identity part and a transition part, whose momentum delta function is stripped to define the invariant amplitude](/figures/perturbative-qft/s-matrix-t-matrix-split.svg)

<figcaption>

The full S-matrix contains an identity contribution and a transition contribution. Perturbative diagrams compute the connected scattering kernel, usually reported as $i\mathcal M$ after external-state rules and after stripping the total momentum-conservation delta function.

</figcaption>
</figure>

## Prerequisites

You should know [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/) and [Conventions and Notation](/perturbative-qft/conventions/). The pages [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) and [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) explain the diagrammatic side of the same normalization.

## Core idea

The S-matrix is the complete scattering map. It includes the possibility that nothing happens. The T-matrix removes the trivial identity part and keeps the transition part. The invariant amplitude $\mathcal M$ removes the universal delta function imposed by spacetime translation invariance.

The hierarchy is:

| Object | Meaning | Typical use |
|---|---|---|
| $S_{\beta\alpha}$ | full in–out overlap | abstract scattering map and unitarity |
| $\delta_{\beta\alpha}$ | identity/no-scattering piece | forward scattering, normalization, disconnected pieces |
| $T_{\beta\alpha}$ | transition matrix element | unitarity relations and optical theorem |
| $\mathcal M_{\beta\alpha}$ | invariant amplitude with total delta function stripped | Feynman-rule output, rates, cross sections |

The page is mostly about normalization. That sounds small until the first time one loses a factor of $2E_{\mathbf p}$, $(2\pi)^4$, or $i$ and spends a week hunting it. Scattering theory is where convention mistakes become numerically expensive.

## Setup and conventions

We use the qft.org mostly-minus convention and covariantly normalized external states. For one-particle states,

$$
\langle \mathbf p',s'|\mathbf p,s\rangle
=
(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'}.
$$

Incoming and outgoing multiparticle labels are written as $\alpha$ and $\beta$, with total four-momenta

$$
P_\alpha^\mu=\sum_{a\in\alpha}p_a^\mu,
\qquad
P_\beta^\mu=\sum_{b\in\beta}p_b^\mu.
$$

After defining the S-matrix using in and out states, we usually write matrix elements between free labels:

$$
S_{\beta\alpha}
={}_0\langle\beta|S|\alpha\rangle_0.
$$

The subscript $0$ is usually dropped once the convention is clear. All external physical momenta are positive-energy momenta unless a page explicitly switches to all-incoming analytic notation.

## Definition of the S-matrix

The S-matrix element is

$$
S_{\beta\alpha}
=
\langle\beta,\mathrm{out}|\alpha,\mathrm{in}\rangle.
$$

Using Møller operators, one may write

$$
S=\Omega_+^\dagger\Omega_-,
$$

where $\Omega_-$ maps free labels to incoming exact states and $\Omega_+$ maps free labels to outgoing exact states.

For stable asymptotic states, $S$ is unitary on the scattering-state Hilbert space:

$$
S^\dagger S=\mathbf 1.
$$

This is just conservation of total probability, but it becomes powerful. Written in terms of $T$, it leads to the optical theorem, unitarity cuts, and eventually dispersion relations.

The identity term in $S$ is not optional. It means that the final labels can be the same as the initial labels without an interaction. For continuous momentum states this identity is a product of delta functions and Kronecker deltas matching momenta, species, spin labels, and identical-particle symmetrization.

## Definition of the T-matrix

We define the transition operator by

$$
S=\mathbf 1+iT.
$$

Therefore,

$$
S_{\beta\alpha}
=\delta_{\beta\alpha}+iT_{\beta\alpha}.
$$

Here $\delta_{\beta\alpha}$ is a compact notation for the identity matrix element in the continuum-normalized multiparticle basis. For a one-particle scalar state it reduces to

$$
\langle \mathbf q|\mathbf p\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

For many particles it includes a sum over the allowed permutations of identical particles. In a process where $\beta$ and $\alpha$ have different particle content or different total momenta, the identity part vanishes.

The factor of $i$ in $S=1+iT$ is a convention, but it is a very common and useful one. With the usual Lorentzian Feynman rules, diagrams naturally produce factors called $i\mathcal M$. This convention makes that phrase literal.

:::caution[Not the time-ordering symbol]
The $T$ in $S=1+iT$ is the transition operator. It is not the time-ordering symbol $T\{\cdots\}$. The notation is traditional and mildly cursed; context has to do the work.
:::

## Translation invariance and the invariant amplitude

If the theory is translationally invariant, the S-matrix commutes with the total four-momentum:

$$
[P^\mu,S]=0.
$$

Therefore transition matrix elements vanish unless total four-momentum is conserved. In continuum normalization, this statement becomes a delta function:

$$
\langle\beta|iT|\alpha\rangle
=
i(2\pi)^4\delta^{(4)}(P_\beta-P_\alpha)\mathcal M_{\beta\alpha}.
$$

The quantity $\mathcal M_{\beta\alpha}$ is the **invariant amplitude**. It is the object that appears in phase-space formulas. For example, decay rates and cross sections are built from

$$
\overline{|\mathcal M|^2}
$$

together with the Lorentz-invariant final-state phase-space measure and the appropriate flux or initial-state normalization.

The word "invariant" means that, after external spin or polarization labels are treated correctly, the stripped amplitude transforms covariantly under Lorentz transformations and has no leftover total momentum delta function. It does not mean that every intermediate expression in a gauge theory is gauge independent or that every off-shell continuation is physical.

## Example: scalar four-point contact amplitude

Consider real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4.
$$

The quartic vertex factor is

$$
-i\lambda.
$$

For tree-level $2\to2$ scattering, the single contact diagram gives

$$
i\mathcal M_{2\to2}^{\mathrm{tree}}=-i\lambda,
$$

so in this convention

$$
\mathcal M_{2\to2}^{\mathrm{tree}}=-\lambda.
$$

The corresponding S-matrix contribution is

$$
\langle p_3p_4|iT|p_1p_2\rangle
=
i(2\pi)^4\delta^{(4)}(p_3+p_4-p_1-p_2)(-\lambda),
$$

for distinguishable external labels or for a fixed labeled contribution. Identical-particle symmetrization and final-state factors enter when constructing physical rates or cross sections.

The sign of $\mathcal M$ is less directly observable than the relative signs between diagrams. For this contact example, $|\mathcal M|^2=\lambda^2$ in tree-level scalar observables, but in a theory with multiple diagrams interference signs matter immediately.

## Connected and disconnected pieces

The full S-matrix contains disconnected pieces. Some are pure identity contributions. Others describe spectators passing through while a smaller subset of particles interacts.

For example, in a three-particle state, one particle might be a spectator while the other two scatter. The full matrix element then contains a spectator delta function multiplying a connected two-particle scattering amplitude.

The connected scattering amplitude is the part that cannot be factorized into independent scattering events after separating the external labels. Cluster decomposition is the physical principle behind this organization: widely separated experiments should have independent probabilities.

In practical perturbative calculations, when someone says "the amplitude for $a+b\to c+d$," they usually mean the connected, amputated amplitude $\mathcal M$ for that process, not the full many-body S-matrix including every possible spectator identity factor.

## Unitarity in T-matrix form

Unitarity is

$$
S^\dagger S=\mathbf 1.
$$

With $S=\mathbf 1+iT$, this becomes

$$
-i(T-T^\dagger)=T^\dagger T.
$$

Equivalently,

$$
i(T^\dagger-T)=T^\dagger T.
$$

Taking a matrix element between states $|\beta\rangle$ and $|\alpha\rangle$ gives

$$
-i\left(T_{\beta\alpha}-T_{\alpha\beta}^*\right)
=
\sum_X T_{X\beta}^*T_{X\alpha},
$$

where the sum over $X$ includes integrals over all allowed intermediate on-shell multiparticle states with the qft.org phase-space normalization.

For forward scattering, $\beta=\alpha$, this gives the schematic optical-theorem form

$$
2\operatorname{Im}T_{\alpha\alpha}
=
\sum_X |T_{X\alpha}|^2.
$$

After stripping the common momentum delta functions carefully, this becomes a relation between the imaginary part of the forward invariant amplitude and a sum over physical intermediate-state phase space. Later pages turn this into the optical theorem and Cutkosky cutting rules.

:::tip[What unitarity knows]
Unitarity is not a diagrammatic trick. It is probability conservation. Diagrammatic cutting rules are perturbative ways of implementing the same operator equation.
:::

## From amplitude to observables

The invariant amplitude is not yet a probability. Its square must be combined with phase space and the appropriate initial-state normalization.

For a decay of one particle with four-momentum $P$ and mass $M$,

$$
d\Gamma
=
\frac{1}{2M}\,
\overline{|\mathcal M|^2}\,d\Phi_n(P),
$$

up to final-state identical-particle factors if they are not already included in the phase-space convention.

For a two-body initial state, the differential cross section has the schematic form

$$
d\sigma
=
\frac{1}{\text{flux}}\,
\overline{|\mathcal M|^2}\,d\Phi_n(P_i),
$$

with the exact flux factor fixed in the phase-space and cross-section pages. This page stops at the amplitude normalization; the next layer is the observable normalization.

## Common pitfalls

**Dropping the identity term.** For non-forward transitions the identity often vanishes, so it is tempting to forget it exists. That is dangerous in forward scattering, unitarity, disconnected diagrams, and cluster-decomposition arguments.

**Confusing $T$ with $\mathcal M$.** The T-matrix still contains the total momentum-conserving delta function. The invariant amplitude $\mathcal M$ is what remains after that universal delta function is stripped according to the convention on this page.

**Comparing amplitudes without checking the factor of $i$.** Some authors define diagrams to equal $\mathcal M$, others $i\mathcal M$, and others use $\mathcal A$ or $\mathcal T$. Always identify the definition of $S$ and the stripped delta function before comparing signs.

**Using $|\mathcal M|^2$ before summing and averaging correctly.** For spin, helicity, color, flavor, or polarization labels, observables require the relevant sums over final labels and averages over initial ensembles. A definite polarized amplitude and an unpolarized cross section are not the same object.

**Treating off-shell amplitudes as observables.** The S-matrix relates on-shell asymptotic states. Off-shell Green functions are useful computational objects but depend on field choices and, in gauge theories, on gauge fixing.

## Relations to other pages

- [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/) defines the in and out states whose overlap is the S-matrix.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) explains how diagrams produce factors that assemble into $i\mathcal M$.
- [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) explains why the connected amplitude is separated from spectator and vacuum factors.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) gives the irreducible kernels that build connected amplitudes.
- [Conventions and Notation](/perturbative-qft/conventions/) is the normalization reference for phase space, spin sums, polarization sums, and unitarity signs.

## Research status

The definitions on this page are standard perturbative scattering theory. The unsettled or delicate issues are not the algebraic split $S=1+iT$ itself; they concern the existence and physical interpretation of the states to which it is applied. Massive stable particles in weakly coupled theories fit the elementary framework well. Massless gauge theories require infrared-safe observables or dressed states; confining theories have a physical asymptotic spectrum that is not the same as the Lagrangian's colored fields; unstable particles require resonance methods; and nonperturbative S-matrix constructions remain subtle in many QFTs.

## Exercises

### Exercise 1: Derive the T-matrix unitarity relation

Starting from $S^\dagger S=\mathbf 1$ and $S=\mathbf 1+iT$, derive

$$
-i(T-T^\dagger)=T^\dagger T.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute $S=1+iT$:

$$
S^\dagger S
=(1-iT^\dagger)(1+iT)
=1+iT-iT^\dagger+T^\dagger T.
$$

Unitarity requires this to equal $1$, so

$$
iT-iT^\dagger+T^\dagger T=0.
$$

Rearranging gives

$$
-i(T-T^\dagger)=T^\dagger T.
$$

</details>

### Exercise 2: Momentum conservation from translations

Assume $[P^\mu,T]=0$ and that $|\alpha\rangle$ and $|\beta\rangle$ are total-momentum eigenstates. Show that $T_{\beta\alpha}$ is proportional to $\delta^{(4)}(P_\beta-P_\alpha)$.

<details>
<summary><strong>Solution</strong></summary>

The commutator gives

$$
0=\langle\beta|[P^\mu,T]|\alpha\rangle
=(P_\beta^\mu-P_\alpha^\mu)T_{\beta\alpha}.
$$

For ordinary numbers this would force $T_{\beta\alpha}=0$ unless $P_\beta=P_\alpha$. For continuum-normalized states, the corresponding distributional statement is that $T_{\beta\alpha}$ has support on $P_\beta=P_\alpha$, so it contains

$$
\delta^{(4)}(P_\beta-P_\alpha).
$$

With the qft.org convention, the coefficient of this delta function is $(2\pi)^4\mathcal M_{\beta\alpha}$.

</details>

### Exercise 3: Contact amplitude in φ⁴ theory

Using the quartic vertex $-i\lambda$, compute the tree-level invariant amplitude for scalar $2\to2$ scattering in real $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

At tree level there is one contact diagram. The diagram contributes

$$
i\mathcal M=-i\lambda.
$$

Therefore

$$
\mathcal M=-\lambda.
$$

The corresponding transition matrix element is

$$
\langle p_3p_4|iT|p_1p_2\rangle
=
i(2\pi)^4\delta^{(4)}(p_3+p_4-p_1-p_2)(-\lambda).
$$

</details>

### Exercise 4: Forward unitarity

Use

$$
-i(T-T^\dagger)=T^\dagger T
$$

to show schematically that

$$
2\operatorname{Im}T_{\alpha\alpha}=\sum_X |T_{X\alpha}|^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Take the matrix element between $|\alpha\rangle$ on both sides:

$$
-i(T_{\alpha\alpha}-T_{\alpha\alpha}^*)
=\sum_X T_{X\alpha}^*T_{X\alpha}.
$$

The left side is

$$
-i(T_{\alpha\alpha}-T_{\alpha\alpha}^*)
=2\operatorname{Im}T_{\alpha\alpha}.
$$

Thus

$$
2\operatorname{Im}T_{\alpha\alpha}
=\sum_X |T_{X\alpha}|^2,
$$

where the sum over $X$ includes the appropriate phase-space integrals and discrete quantum-number sums.

</details>

### Exercise 5: Identify the convention mismatch

A book defines

$$
\langle f|S|i\rangle
=\langle f|i\rangle+(2\pi)^4\delta^{(4)}(P_f-P_i)i\mathcal A_{fi}.
$$

What is the relation between $\mathcal A_{fi}$ and the qft.org $\mathcal M_{fi}$?

<details>
<summary><strong>Solution</strong></summary>

The qft.org convention is

$$
\langle f|S|i\rangle
=\langle f|i\rangle+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

This is identical to the book's definition with

$$
\mathcal A_{fi}=\mathcal M_{fi}.
$$

The book has placed the factor of $i$ outside $\mathcal A$, just as qft.org places it outside $\mathcal M$. If instead the book had written the transition part as $(2\pi)^4\delta^{(4)}\mathcal A_{fi}$ with no explicit $i$, then $\mathcal A_{fi}=i\mathcal M_{fi}$.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§10–11, for scattering amplitudes, Feynman rules, cross sections, and decay rates in the same broad normalization family.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 7 and 11–12, for scattering, the S-matrix, phase space, applications, and the optical theorem.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5–7, for cross sections, decay rates, the S-matrix, LSZ, and Feynman rules.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for a detailed construction of scattering theory, symmetries of the S-matrix, rates, cross sections, and unitarity.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for consequences of unitarity and the optical theorem.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for the classic analytic S-matrix perspective.

## Version history

- **2026-06-12:** Initial standardized page.
