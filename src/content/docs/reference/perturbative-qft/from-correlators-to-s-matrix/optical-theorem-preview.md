---
title: "Optical Theorem Preview"
description: "A first derivation of the optical theorem from S-matrix unitarity and its relation to total rates, forward amplitudes, and unitarity cuts."
sidebar:
  label: "Optical Theorem Preview"
  order: 8
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, ch. 3; Coleman 2019, ch. 12; Srednicki 2007, §§10–11 and 20; Schwartz 2014, ch. 24; Zee 2010, ch. III.8"
topics:
  - optical theorem
  - S-matrix unitarity
  - forward scattering
  - total cross section
  - unitarity cuts
canonicalTopics:
  - optical-theorem
  - s-matrix-unitarity
  - forward-amplitude
  - total-cross-section
researchStatus:
  established:
    - "The optical theorem is a standard consequence of S-matrix unitarity and is the basic bridge between forward amplitudes, total rates, and sums over physical intermediate states."
  active:
    - "Infrared-safe observables, gauge-theory factorization, finite-volume extraction of amplitudes, unstable particles, and nonperturbative real-time dynamics require refined versions beyond this preview."
---

## Summary

The **optical theorem** is the forward-scattering form of probability conservation. With

$$
S=\mathbf 1+iT,
$$

unitarity gives

$$
S^\dagger S=\mathbf 1
\qquad\Longrightarrow\qquad
-i(T-T^\dagger)=T^\dagger T.
$$

Taking a matrix element between the same initial state $|i\rangle$ gives

$$
2\operatorname{Im}\langle i|T|i\rangle
=
\sum_X\int d\Pi_X\,
\left|\langle X|T|i\rangle\right|^2,
$$

where the sum and integral run over allowed on-shell final states.

After stripping the total momentum-conservation delta function, the same statement becomes

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
\left|\mathcal M_{i\to X}\right|^2.
$$

Thus the imaginary part of the **forward** transition amplitude is the total probability flow from the initial state into every allowed final state. This page is a normalization-first preview; the later unitarity and analyticity pages develop cuts, discontinuities, dispersion relations, and partial-wave unitarity in more detail.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![The imaginary part of the forward amplitude equals a phase-space sum over on-shell intermediate states](/figures/perturbative-qft/optical-theorem-preview.svg)

<figcaption>

The optical theorem is unitarity written in forward kinematics. The imaginary part of the forward amplitude is equal to a sum over physical on-shell intermediate states, represented diagrammatically by cutting through the transition probability.

</figcaption>
</figure>

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), and [Connected Correlators and Scattering](/perturbative-qft/from-correlators-to-s-matrix/connected-correlators-and-scattering/). The page also uses the Lorentz-invariant phase-space measure fixed in [Conventions and Notation](/perturbative-qft/conventions/).

## Core idea

Quantum mechanics says probabilities add to one. In scattering language, that statement is

$$
S^\dagger S=\mathbf 1.
$$

The optical theorem is what this statement becomes after separating the identity part of $S$ from the transition part and then focusing on the forward matrix element. The left-hand side is an interference term involving the forward amplitude. The right-hand side is a positive sum over actual intermediate states.

The theorem is important because it turns a complex analytic property of amplitudes into an observable statement about total rates:

| Object | Meaning in the optical theorem |
|---|---|
| $\operatorname{Im}\mathcal M_{i\to i}$ | absorptive part of the forward amplitude |
| $\sum_X\int d\Pi_X$ | sum over all physical on-shell final states |
| $|\mathcal M_{i\to X}|^2$ | transition probability density into each final state |
| total cross section or decay rate | normalized version of the right-hand side |

This is why imaginary parts in loop amplitudes are not optional decorations. They know about real particles that can be produced.

## Setup and conventions

We use covariantly normalized states and

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The Lorentz-invariant final-state phase space for an $n$-particle state $X$ is

$$
d\Pi_X
=
\prod_{a\in X}\frac{d^3\mathbf k_a}{(2\pi)^3 2E_a},
$$

with an additional total momentum-conservation delta function written explicitly in the optical-theorem formula. Sums over species, spin, polarization, color, and identical-particle symmetry factors are included in the symbol

$$
\sum_X\int d\Pi_X.
$$

For a two-particle initial state, the invariant flux factor is

$$
\mathcal F_{12}
=4E_1E_2|\mathbf v_1-\mathbf v_2|
=2\sqrt{\lambda(s,m_1^2,m_2^2)},
$$

where

$$
\lambda(s,m_1^2,m_2^2)
=
\big[s-(m_1+m_2)^2\big]\big[s-(m_1-m_2)^2\big].
$$

## Derivation from unitarity

Start from

$$
S=\mathbf 1+iT,
\qquad
S^\dagger=\mathbf 1-iT^\dagger.
$$

Then

$$
S^\dagger S
=
(\mathbf 1-iT^\dagger)(\mathbf 1+iT)
=
\mathbf 1+iT-iT^\dagger+T^\dagger T.
$$

Imposing $S^\dagger S=\mathbf 1$ gives

$$
i(T-T^\dagger)+T^\dagger T=0,
$$

or

$$
-i(T-T^\dagger)=T^\dagger T.
$$

Now insert the same initial state $|i\rangle$ on both sides:

$$
-i\langle i|(T-T^\dagger)|i\rangle
=
\langle i|T^\dagger T|i\rangle.
$$

The left-hand side is

$$
-i\left(\langle i|T|i\rangle-\langle i|T^\dagger|i\rangle\right)
=
2\operatorname{Im}\langle i|T|i\rangle.
$$

On the right-hand side, insert a complete set of physical final states:

$$
\mathbf 1
=
\sum_X\int d\Pi_X\,|X\rangle\langle X|.
$$

This gives

$$
\langle i|T^\dagger T|i\rangle
=
\sum_X\int d\Pi_X\,
\langle i|T^\dagger|X\rangle\langle X|T|i\rangle
=
\sum_X\int d\Pi_X\,
\left|\langle X|T|i\rangle\right|^2.
$$

Therefore

$$
2\operatorname{Im}\langle i|T|i\rangle
=
\sum_X\int d\Pi_X\,
\left|\langle X|T|i\rangle\right|^2.
$$

This is already the optical theorem, written before stripping delta functions.

## Stripping the delta function

For translation-invariant scattering,

$$
\langle X|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_X-P_i)\mathcal M_{X i}.
$$

When squaring a continuum-normalized matrix element, one encounters the square of a delta function. The clean interpretation is to regulate the system in a large spacetime box, use

$$
(2\pi)^4\delta^{(4)}(0)
$$

as the total spacetime volume factor, and divide it out when converting transition probabilities into rates or cross sections. After this standard stripping, the unitarity relation becomes

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
\left|\mathcal M_{i\to X}\right|^2.
$$

The amplitude on the left is the **forward** amplitude: the final external labels are the same as the initial labels. For a two-particle initial state, this means

$$
1(p_1)+2(p_2)\to1(p_1)+2(p_2)
$$

with zero momentum transfer.

## From optical theorem to total cross section

For a two-particle initial state, the total cross section is

$$
\sigma_{\rm tot}
=
\frac{1}{\mathcal F_{12}}
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
\left|\mathcal M_{i\to X}\right|^2,
$$

where

$$
\mathcal F_{12}=4E_1E_2|\mathbf v_1-\mathbf v_2|.
$$

Using the optical theorem gives

$$
\sigma_{\rm tot}
=
\frac{2\operatorname{Im}\mathcal M_{i\to i}^{\rm forward}}{\mathcal F_{12}}.
$$

Equivalently,

$$
\sigma_{\rm tot}
=
\frac{\operatorname{Im}\mathcal M_{i\to i}^{\rm forward}}{\sqrt{\lambda(s,m_1^2,m_2^2)}}.
$$

These formulas are for fixed initial quantum numbers. For unpolarized cross sections one averages over initial spin, polarization, and color labels and sums over the corresponding final labels. The optical theorem itself is an operator statement; the averaging is part of the experimental observable.

## Decay version

For a one-particle initial state of mass $M$, the total decay rate is

$$
\Gamma_{\rm tot}
=
\frac{1}{2M}
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(p-P_X)
\left|\mathcal M_{i\to X}\right|^2.
$$

The optical theorem relates this to the imaginary part of the forward self-energy or forward transition amplitude. In practice, unstable-particle widths are often extracted from the imaginary part of the pole position or the self-energy near the pole. That is a close cousin of the optical theorem, but the fully consistent treatment of unstable particles requires care because unstable particles are not exact asymptotic states.

## Diagrammatic preview: cuts

Perturbatively, the right-hand side of the optical theorem is represented by cutting diagrams. The cut places intermediate lines on shell and turns the loop integration into phase-space integration.

For scalar lines, the schematic replacement is

$$
\text{internal propagators across a cut}
\quad\leadsto\quad
\text{on-shell phase-space measure}.
$$

More explicitly, the on-shell delta function

$$
\theta(k^0)\delta(k^2-m^2)
$$

is the same object that appears in

$$
\frac{d^3\mathbf k}{(2\pi)^3 2E_{\mathbf k}}
=
\frac{d^4k}{(2\pi)^3}\theta(k^0)\delta(k^2-m^2).
$$

The full Cutkosky rules refine this schematic statement by specifying factors of $i$, signs, particle types, and multiple cuts. This preview only needs the idea: imaginary parts of loop diagrams arise when internal states can go on shell, and unitarity says those imaginary parts equal sums over physical intermediate states.

## Example: order counting in scalar theory

In real scalar $\phi^4$ theory,

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the tree-level $2\to2$ amplitude is

$$
\mathcal M_{\rm tree}=-\lambda.
$$

This is real. Therefore it does not contribute to

$$
\operatorname{Im}\mathcal M_{2\to2}^{\rm forward}
$$

at order $\lambda$. The optical theorem predicts that the first nonzero contribution to the right-hand side is of order $\lambda^2$, since it contains

$$
|\mathcal M_{\rm tree}|^2=\lambda^2.
$$

So the imaginary part of the forward amplitude must first appear at one loop. Indeed, the one-loop bubble diagram has a two-particle cut. This is the first place where the forward amplitude can know about the real two-particle intermediate state.

For identical scalar intermediate particles, the two-particle contribution has a symmetry factor:

$$
2\operatorname{Im}\mathcal M_{2\to2}^{(2),\rm forward}
\supset
\frac{1}{2!}
\int d\Pi_2\,
(2\pi)^4\delta^{(4)}(P_i-k_1-k_2)
\left|\mathcal M_{2\to2}^{(1)}\right|^2.
$$

The factor $1/2!$ is not optional; it prevents double-counting identical final states.

## Common pitfalls

**Forgetting the word forward.** The optical theorem uses the amplitude $i\to i$, with the same initial and final external labels. A generic nonforward elastic amplitude is constrained by unitarity, but not by the simple total-cross-section formula above.

**Dropping the phase-space sum.** The right-hand side is a sum over all allowed on-shell states. Keeping only one final state gives a partial contribution, not the full optical theorem.

**Confusing diagram-by-diagram positivity with unitarity.** The total right-hand side is positive for physical states, but individual gauge-dependent diagrams or unphysical intermediate states need not look positive. Gauge theories require the sum over physical states or a BRST-consistent formulation.

**Ignoring identical-particle factors.** If the final state contains identical particles, phase space includes the appropriate symmetry factor. Missing this factor changes total rates.

**Applying the stable-particle formula to unstable particles blindly.** Unstable particles are resonances, not exact asymptotic states. Their widths are related to imaginary parts, but the pole prescription and gauge-invariant definition require extra care.

**Forgetting infrared issues.** In massless gauge theories, exclusive amplitudes can be infrared divergent. The physical statement is about infrared-safe inclusive observables or appropriately dressed states.

## Relations to other pages

- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the $S=1+iT$ and invariant-amplitude conventions used here.
- [Connected Correlators and Scattering](/perturbative-qft/from-correlators-to-s-matrix/connected-correlators-and-scattering/) explains why disconnected spectator pieces are separated before extracting physical scattering amplitudes.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) fixes the state normalization, phase-space measure, and flux conventions needed for the cross-section formula.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains a different analytic consequence of the same local relativistic S-matrix framework.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) gives the self-energy and vertex language behind loop imaginary parts and widths.

## Research status

The optical theorem is textbook-standard for stable asymptotic states in relativistic quantum mechanics and QFT. In perturbative QFT, it is the entry point to cutting rules, discontinuities, dispersion relations, and partial-wave unitarity.

The active and delicate issues appear when the simple S-matrix assumptions fail or need refinement: massless gauge-theory infrared structure, finite-volume extraction of scattering amplitudes, unstable particles, nonperturbative real-time dynamics, confinement, and cosmological or curved-spacetime settings. Those cases do not invalidate unitarity; they change how the unitary statement is represented in physical observables.

## Exercises

### Exercise 1: Derive the operator unitarity equation

Starting from

$$
S=\mathbf 1+iT,
\qquad
S^\dagger S=\mathbf 1,
$$

show that

$$
-i(T-T^\dagger)=T^\dagger T.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
S^\dagger S=(\mathbf 1-iT^\dagger)(\mathbf 1+iT)
=\mathbf 1+iT-iT^\dagger+T^\dagger T.
$$

Setting this equal to $\mathbf 1$ gives

$$
iT-iT^\dagger+T^\dagger T=0.
$$

Move the first two terms to the other side:

$$
T^\dagger T=-i(T-T^\dagger).
$$

Therefore

$$
-i(T-T^\dagger)=T^\dagger T.
$$

</details>

### Exercise 2: Positivity of the absorptive part

Use the optical theorem to show that

$$
\operatorname{Im}\mathcal M_{i\to i}^{\rm forward}\ge0
$$

for a fixed physical initial state, assuming the standard normalization used on this page.

<details>
<summary><strong>Solution</strong></summary>

The stripped optical theorem is

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
\left|\mathcal M_{i\to X}\right|^2.
$$

The phase-space measure is nonnegative, the delta function restricts to allowed kinematics, and each squared amplitude is nonnegative after summing over physical final quantum numbers. Therefore the right-hand side is nonnegative, so

$$
\operatorname{Im}\mathcal M_{i\to i}^{\rm forward}\ge0.
$$

If no final state is kinematically available other than the identity contribution already separated from $T$, the absorptive part vanishes.

</details>

### Exercise 3: Tree amplitude and one-loop imaginary part

In $\phi^4$ theory, the tree-level amplitude is

$$
\mathcal M^{(1)}=-\lambda.
$$

Use order counting in the optical theorem to explain why the first imaginary part of the forward $2\to2$ amplitude appears at order $\lambda^2$.

<details>
<summary><strong>Solution</strong></summary>

The optical theorem relates the imaginary part of the forward amplitude to squared transition amplitudes:

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
|\mathcal M_{i\to X}|^2.
$$

The leading $2\to2$ transition amplitude is order $\lambda$:

$$
\mathcal M^{(1)}=-\lambda.
$$

The square of this amplitude is order $\lambda^2$:

$$
|\mathcal M^{(1)}|^2=\lambda^2.
$$

Therefore the right-hand side begins at order $\lambda^2$. The left-hand side must also begin at order $\lambda^2$, so the first imaginary part appears in the one-loop forward amplitude, not in the tree amplitude.

</details>

### Exercise 4: Flux factor in the center-of-mass frame

Show that for two incoming particles in the center-of-mass frame,

$$
4E_1E_2|\mathbf v_1-\mathbf v_2|
=4|\mathbf p|\sqrt s
=2\sqrt{\lambda(s,m_1^2,m_2^2)}.
$$

<details>
<summary><strong>Solution</strong></summary>

In the center-of-mass frame,

$$
p_1=(E_1,\mathbf p),
\qquad
p_2=(E_2,-\mathbf p),
\qquad
\sqrt s=E_1+E_2.
$$

The velocities are

$$
\mathbf v_1=\frac{\mathbf p}{E_1},
\qquad
\mathbf v_2=-\frac{\mathbf p}{E_2}.
$$

Therefore

$$
|\mathbf v_1-\mathbf v_2|
=|\mathbf p|\left(\frac{1}{E_1}+\frac{1}{E_2}\right)
=\frac{|\mathbf p|(E_1+E_2)}{E_1E_2}.
$$

Multiplying by $4E_1E_2$ gives

$$
4E_1E_2|\mathbf v_1-\mathbf v_2|
=4|\mathbf p|(E_1+E_2)
=4|\mathbf p|\sqrt s.
$$

The center-of-mass momentum satisfies

$$
|\mathbf p|
=\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt s}.
$$

Substituting gives

$$
4|\mathbf p|\sqrt s
=2\sqrt{\lambda(s,m_1^2,m_2^2)}.
$$

</details>

## References

### Standard first pass

- Sidney Coleman, *Lectures on Quantum Field Theory*, ch. 12, for phase space and the optical theorem in scattering applications.
- Mark Srednicki, *Quantum Field Theory*, §§10–11 and §20, for scattering amplitudes, cross sections, decay rates, and loop-level unitarity checks.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for the optical theorem, spectral decomposition, and implications of unitarity.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for S-matrix unitarity, rates, cross sections, and partial-wave consequences.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. III.8, for a physics-first discussion of imaginary parts and probability conservation.
- R. E. Cutkosky, "Singularities and discontinuities of Feynman amplitudes," *Journal of Mathematical Physics* **1** (1960), for the classic cutting rules.

## Version history

- **2026-06-12:** Initial standardized page.
