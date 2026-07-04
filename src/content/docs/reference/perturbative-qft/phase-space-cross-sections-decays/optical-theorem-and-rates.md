---
title: "Optical Theorem and Rates"
description: "A derivation of total cross sections and total decay rates from unitarity, forward amplitudes, and cut phase space."
sidebar:
  label: "Optical Theorem and Rates"
  order: 8
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, ch. 3; Srednicki 2007, §§10–11 and §20; Coleman 2019, ch. 12; Schwartz 2014, chs. 5 and 24"
topics:
  - optical theorem
  - total cross sections
  - total decay rates
  - unitarity
  - cut diagrams
canonicalTopics:
  - optical-theorem
  - total-cross-section
  - total-decay-rate
  - forward-amplitude
  - cutkosky-preview
researchStatus:
  established:
    - "The optical theorem follows directly from S-matrix unitarity and gives total inclusive rates from imaginary parts of forward amplitudes."
  active:
    - "Precision applications require renormalization, infrared-safe definitions, unstable-particle schemes, factorization, and sometimes finite-density or non-vacuum generalizations."
---

## Summary

The **optical theorem** is the rate formula hidden inside unitarity. If

$$
S=1+iT,
\qquad
S^\dagger S=1,
$$

then

$$
-i(T-T^\dagger)=T^\dagger T.
$$

Taking the matrix element between the same initial state and inserting a complete set of final states gives

$$
2\operatorname{Im}\mathcal M_{i\to i}^{\rm forward}
=
\sum_X\frac{1}{S_X}\int d\Pi_X(P_i)\,
|\mathcal M_{i\to X}|^2.
$$

The right-hand side is exactly the inclusive sum that appears in total rates. Therefore, for a two-particle scattering initial state $I$, qft.org conventions give

$$
\sigma_{\rm tot}(I)
=
\frac{1}{F_I}\,2\operatorname{Im}\mathcal M_{I\to I}^{\rm forward},
$$

and for a one-particle decay $A$ at rest,

$$
\Gamma_{\rm tot}(A)
=
\frac{1}{2M_A}\,2\operatorname{Im}\mathcal M_{A\to A}^{\rm forward}.
$$

This page derives these formulas, explains the normalization, and connects the optical theorem to cut diagrams and total inclusive rates. For genuinely unstable particles, the exact $S$-matrix is defined between stable asymptotic states, so the forward-amplitude width formula should be understood perturbatively or through the pole and self-energy language discussed below.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![The imaginary part of a forward amplitude equals a sum over cut on-shell intermediate states, which becomes a total cross section or total decay rate after dividing by the initial normalization](/figures/perturbative-qft/optical-theorem-and-rates.svg)

<figcaption>

Unitarity converts the imaginary part of a forward amplitude into a sum over on-shell intermediate states. Dividing that inclusive sum by the initial flux gives a total cross section; dividing by $2M_A$ for a one-particle initial state gives a total decay rate.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/), and [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/).

## Core idea

Probabilities add to one. In scattering language, that statement is $S^\dagger S=1$. When one isolates the nontrivial part of $S$, unitarity says that the discontinuity or imaginary part of a forward process is equal to a sum over all ways the initial state can turn into real on-shell final states.

That is why the optical theorem is powerful. It replaces a sum over many final states by a forward amplitude:

$$
\text{sum over all final states}
\quad\longleftrightarrow\quad
\operatorname{Im}(\text{forward amplitude}).
$$

The theorem does not give arbitrary differential distributions for free. It gives **fully inclusive** total rates. More differential observables require inserting a measurement function on the cut final-state phase space.

## Setup and conventions

We use

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

Equivalently,

$$
\langle f|T|i\rangle
=(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The completeness relation over multiparticle final states is written schematically as

$$
\mathbf 1
=
\sum_X\frac{1}{S_X}
\int
\prod_{a\in X}\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}
\,|X\rangle\langle X|,
$$

where $S_X$ divides by identical final-state permutations. After the momentum-conserving delta function from $T$ is included, this becomes the usual invariant phase-space measure

$$
d\Pi_X(P_i)
=(2\pi)^4\delta^{(4)}\!\left(P_i-\sum_{a\in X}p_a\right)
\prod_{a\in X}\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

We first write formulas for fixed initial spin, color, and polarization labels. For unpolarized rates, average the final result over initial labels and sum over unresolved final labels.

## Derivation from unitarity

Start with

$$
S=1+iT.
$$

Then

$$
S^\dagger S
=(1-iT^\dagger)(1+iT)
=1+iT-iT^\dagger+T^\dagger T.
$$

Unitarity, $S^\dagger S=1$, gives

$$
iT-iT^\dagger+T^\dagger T=0.
$$

Therefore

$$
-i(T-T^\dagger)=T^\dagger T.
$$

Now take a matrix element between the same initial state $|i\rangle$:

$$
-i\langle i|T-T^\dagger|i\rangle
=
\langle i|T^\dagger T|i\rangle.
$$

The left side is

$$
-i(T_{ii}-T_{ii}^*)=2\operatorname{Im}T_{ii}.
$$

On the right, insert a complete set of states:

$$
\langle i|T^\dagger T|i\rangle
=
\sum_X\frac{1}{S_X}\int d\Phi_X\,
\langle i|T^\dagger|X\rangle\langle X|T|i\rangle,
$$

where

$$
d\Phi_X
=\prod_{a\in X}\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}
$$

is the product of on-shell measures before imposing total momentum conservation.

Using the invariant-amplitude definition and stripping the common overall spacetime-volume factor gives

$$
2\operatorname{Im}\mathcal M_{i\to i}^{\rm forward}
=
\sum_X\frac{1}{S_X}\int d\Pi_X(P_i)\,
|\mathcal M_{i\to X}|^2.
$$

This is the optical theorem in the normalization used throughout this chapter.

:::note[The identity part is already removed]
The forward amplitude in the optical theorem is the nontrivial connected part of the $S$-matrix. The identity piece $\delta_{fi}$ represents no scattering and is not the forward amplitude whose imaginary part gives the total rate.
:::

## Total cross sections

For a two-particle initial state

$$
I=1(p_1)+2(p_2),
$$

the total cross section is

$$
\sigma_{\rm tot}(I)
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}\int d\Pi_X(P_I)\,
\overline{|\mathcal M_{I\to X}|^2}.
$$

Using the optical theorem gives

$$
\sigma_{\rm tot}(I)
=
\frac{1}{F_I}\,
2\operatorname{Im}\overline{\mathcal M_{I\to I}^{\rm forward}}.
$$

Here

$$
F_I=4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}
$$

is the invariant flux factor. The bar on the forward amplitude means the same initial-state average used in the cross-section definition. More explicitly, if the incoming particles have $g_I$ unresolved spin, polarization, or color configurations, then

$$
\overline{\mathcal M_{I\to I}^{\rm forward}}
=
\frac{1}{g_I}\sum_{\alpha=1}^{g_I}
\mathcal M_{I_\alpha\to I_\alpha}^{\rm forward},
$$

with the same external momenta on the two sides of the forward matrix element.

For massless $2\to X$ scattering in the center-of-momentum frame, $F_I=2s$, so

$$
\sigma_{\rm tot}
=
\frac{1}{s}\operatorname{Im}\overline{\mathcal M_{I\to I}^{\rm forward}}
\qquad\text{for massless two-particle initial states.}
$$

This form is common in high-energy scattering, but the invariant flux version is safer because it also covers massive initial particles.

## Total decay rates

For a one-particle initial state $A(P)$, the total width is

$$
\Gamma_{\rm tot}(A)
=
\frac{1}{2M_A}
\sum_X\frac{1}{S_X}\int d\Pi_X(P)\,
\overline{|\mathcal M_{A\to X}|^2}
$$

in the rest frame $P=(M_A,\mathbf 0)$. The same optical-theorem identity gives

$$
\Gamma_{\rm tot}(A)
=
\frac{1}{2M_A}\,
2\operatorname{Im}\overline{\mathcal M_{A\to A}^{\rm forward}}.
$$

This is the cleanest conceptual relation between widths and imaginary parts for a perturbative one-particle channel. A fully unstable particle is not an exact asymptotic state of the full theory, so practical propagator calculations usually phrase the same statement in terms of the imaginary part of a pole or self-energy. The exact sign and normalization of that self-energy relation depend on how the inverse propagator and the amputated two-point amplitude are defined, so the safest route is always to check it against the positive rate formula above.

For example, if a particle $A$ can decay into two particles $b,c$, then the optical theorem says

$$
2\operatorname{Im}\mathcal M_{A\to A}^{\rm forward}(P)
=
\int d\Pi_2(P;p_b,p_c)\,|\mathcal M_{A\to bc}|^2
+\cdots,
$$

where the ellipsis denotes all other allowed final states. Dividing by $2M_A$ gives the contribution to the total width.

## Cut diagrams

The perturbative version of the optical theorem is the cutting idea. A cut through a forward diagram places the cut internal lines on shell and interprets them as real final-state particles. Schematically, a cut scalar propagator is replaced by

$$
\frac{i}{k^2-m^2+i\epsilon}
\quad\longrightarrow\quad
2\pi\,\theta(k^0)\delta(k^2-m^2),
$$

with the rest of the diagram split into an amplitude and its complex conjugate.

The cutting picture is not a new postulate. It is a diagrammatic representation of

$$
T-T^\dagger
\quad\text{versus}\quad
T^\dagger T.
$$

At a given perturbative order, it is also a powerful check: the imaginary part of a loop amplitude must match the phase-space integral of the corresponding lower-order real processes.

A useful mental model is:

$$
\text{imaginary part of loop}
\quad = \quad
\text{sum over allowed on-shell cuts}.
$$

The fully systematic version belongs to later pages on Cutkosky rules and unitarity cuts. Here the point is the rate normalization.

## Inclusive meaning

The optical theorem computes total inclusive rates. It does not ask how the final-state energy is distributed, how many jets were reconstructed, or which angular bin was selected. Those questions require measurement weights.

With no measurement weight, the complete set of states in

$$
\mathbf 1=\sum_X |X\rangle\langle X|
$$

is exactly the sum over all final states. With a measurement, the identity is replaced by a weighted insertion such as

$$
\sum_X |X\rangle w(X)\langle X|.
$$

That weighted insertion is the starting point for differential distributions, event shapes, fiducial cross sections, and jet observables. The optical theorem is the special case $w(X)=1$.

## Checks

**Positivity.** The right side of

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\frac{1}{S_X}\int d\Pi_X\,|\mathcal M_{i\to X}|^2
$$

is nonnegative. Therefore the imaginary part of the forward amplitude has the sign needed to give a nonnegative total rate in these conventions.

**Dimensions.** In four spacetime dimensions, a $2\to2$ amplitude in a renormalizable theory is often dimensionless. The flux factor has mass dimension $2$, so $2\operatorname{Im}\mathcal M/F_I$ has mass dimension $-2$, as a cross section should.

**Tree-level elastic amplitudes.** A purely real tree-level forward amplitude gives no total cross section through the optical theorem at the same order. The corresponding total cross section is of order $|\mathcal M^{(0)}|^2$, which appears in the imaginary part of the forward amplitude at the next perturbative order. Unitarity relates perturbative orders, not just single diagrams in isolation.

## Common pitfalls

**Forgetting that the theorem is inclusive.** The optical theorem gives a total rate because the right side contains a complete sum over final states. It does not directly give an angular distribution or a cut cross section without adding a measurement insertion.

**Dropping disconnected identity pieces carelessly.** The $S$-matrix contains the identity process. The optical theorem concerns the nontrivial transition operator $T$ and the connected forward amplitude after the identity contribution has been separated.

**Using the wrong flux denominator.** For scattering, the forward imaginary part must be divided by the invariant initial flux $F_I$. For a one-particle decay, it is divided by $2M_A$, not by a two-body flux factor.

**Reading self-energy signs without checking definitions.** The width is positive and is fixed by the phase-space sum. If a self-energy formula appears to give the opposite sign, the issue is almost always the convention for the inverse propagator or amputated two-point amplitude.

**Applying vacuum formulas blindly in media.** At finite temperature or density, rates involve thermal occupation factors, spectral functions, and real-time correlators. The unitarity logic survives, but the vacuum phase-space formula is not the whole story.

## Relations to other pages

- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) explains the weighted final-state sums of which the optical theorem is the fully inclusive case.
- [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/) derives the phase-space formula for $\Gamma$ that becomes the imaginary-part formula here.
- [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/) derives the denominator $F_I$ in the total cross-section formula.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the normalization of $S=1+iT$ and $\mathcal M$.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) introduces the unitarity idea before the rate-level applications.
- Later pages on unitarity cuts and Cutkosky rules turn the cut-diagram picture into a loop-integral method.

## Research status

The optical theorem is a direct consequence of unitarity and is textbook-standard. The rate formulas on this page are exact statements for stable asymptotic states in infinite-volume vacuum scattering, with the usual assumptions behind the $S$-matrix.

The active subtleties arise in realistic applications: unstable particles, gauge-dependent intermediate quantities, infrared-safe definitions, finite-volume spectra, factorization in hadronic collisions, finite-temperature media, and real-time nonequilibrium systems. In each case, the basic unitarity idea remains central, but the simple vacuum formula may need a more refined implementation.

## Exercises

### Exercise 1: Derive the T-matrix identity

Starting from $S=1+iT$ and $S^\dagger S=1$, derive

$$
-i(T-T^\dagger)=T^\dagger T.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
S^\dagger S=(1-iT^\dagger)(1+iT)
=1+iT-iT^\dagger+T^\dagger T.
$$

Setting this equal to $1$ gives

$$
iT-iT^\dagger+T^\dagger T=0.
$$

Moving the first two terms to the other side gives

$$
-i(T-T^\dagger)=T^\dagger T.
$$

</details>

### Exercise 2: Insert a complete set of states

Use the identity in Exercise 1 to show that

$$
2\operatorname{Im}T_{ii}
=\sum_X |T_{Xi}|^2
$$

in a discrete normalization where the sum over $X$ is an ordinary sum.

<details>
<summary><strong>Solution</strong></summary>

Take the $i,i$ matrix element:

$$
-i(T_{ii}-T_{ii}^*)=(T^\dagger T)_{ii}.
$$

The left side is $2\operatorname{Im}T_{ii}$. Insert a complete discrete basis on the right:

$$
(T^\dagger T)_{ii}
=\sum_X (T^\dagger)_{iX}T_{Xi}
=\sum_X T_{Xi}^*T_{Xi}
=\sum_X |T_{Xi}|^2.
$$

Therefore

$$
2\operatorname{Im}T_{ii}
=\sum_X |T_{Xi}|^2.
$$

The continuum QFT formula replaces the ordinary sum by invariant phase-space integrals and momentum-conserving delta functions.

</details>

### Exercise 3: Total cross section from the optical theorem

For a two-particle initial state with invariant flux $F_I$, show that the optical theorem implies

$$
\sigma_{\rm tot}(I)
=\frac{2\operatorname{Im}\mathcal M_{I\to I}^{\rm forward}}{F_I}.
$$

<details>
<summary><strong>Solution</strong></summary>

The total cross section is

$$
\sigma_{\rm tot}(I)
=
\frac{1}{F_I}
\sum_X\frac{1}{S_X}\int d\Pi_X(P_I)|\mathcal M_{I\to X}|^2.
$$

The optical theorem states that

$$
\sum_X\frac{1}{S_X}\int d\Pi_X(P_I)|\mathcal M_{I\to X}|^2
=
2\operatorname{Im}\mathcal M_{I\to I}^{\rm forward}.
$$

Substituting this into the cross-section formula gives

$$
\sigma_{\rm tot}(I)
=\frac{2\operatorname{Im}\mathcal M_{I\to I}^{\rm forward}}{F_I}.
$$

</details>

### Exercise 4: Width from a forward amplitude

For a scalar particle $A$ of mass $M_A$, use the decay-rate formula and the optical theorem to derive

$$
\Gamma_{\rm tot}(A)
=\frac{1}{2M_A}2\operatorname{Im}\mathcal M_{A\to A}^{\rm forward}.
$$

<details>
<summary><strong>Solution</strong></summary>

The total decay width is

$$
\Gamma_{\rm tot}(A)
=
\frac{1}{2M_A}
\sum_X\frac{1}{S_X}\int d\Pi_X(P_A)|\mathcal M_{A\to X}|^2.
$$

The optical theorem gives

$$
\sum_X\frac{1}{S_X}\int d\Pi_X(P_A)|\mathcal M_{A\to X}|^2
=
2\operatorname{Im}\mathcal M_{A\to A}^{\rm forward}.
$$

Therefore

$$
\Gamma_{\rm tot}(A)
=
\frac{1}{2M_A}2\operatorname{Im}\mathcal M_{A\to A}^{\rm forward}.
$$

</details>

### Exercise 5: Cut propagator identity

Use

$$
\frac{1}{x+i\epsilon}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x)
$$

to explain why the imaginary part of a scalar propagator knows about the on-shell condition $k^2=m^2$.

<details>
<summary><strong>Solution</strong></summary>

For the scalar propagator denominator,

$$
\frac{i}{k^2-m^2+i\epsilon}
=i\operatorname{PV}\frac{1}{k^2-m^2}+\pi\delta(k^2-m^2).
$$

The delta function is supported on

$$
k^2=m^2.
$$

Thus the discontinuity or cut of a propagator localizes the internal momentum on the mass shell. In a full cutting rule, the positive-energy condition $\theta(k^0)$ and the rest of the diagram supply the physical phase-space interpretation.

</details>

## References

### Standard first pass

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering theory, $S$-matrix unitarity, rates, and the optical theorem.
- M. Srednicki, *Quantum Field Theory*, §§10–11 and §20, for scattering amplitudes, rates, and perturbative unitarity checks.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 12, for phase space, applications, and the optical theorem.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5 and 24, for cross sections, decay rates, and implications of unitarity.

### Deeper references

- R. E. Cutkosky, “Singularities and Discontinuities of Feynman Amplitudes,” *Journal of Mathematical Physics* **1** (1960), for cutting rules.
- G. ’t Hooft and M. Veltman, “Diagrammar,” in *Particle Interactions at Very High Energies*, NATO Advanced Study Institute Series B **4** (1974), for a classic diagrammatic treatment of perturbative unitarity.

## Version history

- **2026-06-12:** Initial standardized page.
