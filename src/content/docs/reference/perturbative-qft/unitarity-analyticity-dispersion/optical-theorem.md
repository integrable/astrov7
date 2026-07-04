---
title: "Optical Theorem"
description: "The optical theorem from S-matrix unitarity: forward amplitudes, total rates, total cross sections, cuts, and the link between imaginary parts and physical intermediate states."
sidebar:
  label: "Optical Theorem"
  order: 1
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I ch. 3; Coleman ch. 12; Srednicki §§10–11 and 20; Schwartz ch. 24; Zee ch. III.8"
topics:
  - unitarity
  - optical theorem
  - forward scattering
  - total cross sections
  - cuts
  - imaginary parts
canonicalTopics:
  - optical-theorem
  - s-matrix-unitarity
  - forward-amplitude
  - cutkosky-preview
researchStatus:
  established:
    - "The optical theorem is a direct consequence of S-matrix unitarity and is a standard bridge between imaginary parts of forward amplitudes and total inclusive probabilities."
  active:
    - "Modern uses include high-order collider calculations, finite-density and thermal rates, positivity bounds, nonperturbative spectral constraints, and amplitudes-based reconstruction methods."
---

## Summary

The **optical theorem** is the forward-scattering form of unitarity. If

$$
S=1+iT,
$$

then $S^\dagger S=1$ implies

$$
-i(T-T^\dagger)=T^\dagger T.
$$

Taking a matrix element between the same initial state $|i\rangle$ gives

$$
2\operatorname{Im}T_{ii}
=\sum_X T_{Xi}^*T_{Xi},
$$

with the sum understood as a sum over all physical intermediate states and their Lorentz-invariant phase space.

In scattering-amplitude language, the same statement says that the imaginary part of the forward amplitude equals the total inclusive transition probability. For a two-particle initial state,

$$
\sigma_{\rm tot}
=\frac{1}{\mathcal F}
2\operatorname{Im}\mathcal M_{i\to i},
$$

where $\mathcal F$ is the invariant flux factor, with the same spin, color, and averaging conventions on both sides.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![The optical theorem equates the imaginary part of a forward amplitude with a sum over cut physical intermediate states](/figures/perturbative-qft/optical-theorem.svg)

<figcaption>

The optical theorem is unitarity in forward kinematics. The imaginary part of the forward amplitude equals a sum over on-shell physical intermediate states. In perturbation theory this becomes the logic of cutting rules: cut lines are put on shell and integrated over phase space.

</figcaption>
</figure>

The theorem is simple; using it correctly is not always simple. One must keep track of connected versus disconnected pieces, normalization conventions, initial-state averages, identical-particle factors, and which states are included in the inclusive sum.

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Connected Correlators and Scattering](/perturbative-qft/from-correlators-to-s-matrix/connected-correlators-and-scattering/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), and [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/).

For loop-level applications, review [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/).

## Core idea

Quantum mechanics says probabilities add to one. In scattering theory, this becomes unitarity of the S-matrix. The optical theorem is what unitarity looks like after inserting a complete set of possible final states.

The name comes from optics, where absorption is related to the imaginary part of the forward scattering amplitude. In QFT the same structure is much more general:

```txt
forward elastic amplitude
        ↓ imaginary part
sum over all possible on-shell final states
        ↓ phase-space integral
total rate or total cross section.
```

The theorem is inclusive. It does not say that one exclusive process equals an imaginary part. It says that the sum over all final states accessible from the initial state is controlled by the forward amplitude.

## Setup and conventions

We use the qft.org S-matrix convention

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}
$$

for connected scattering amplitudes. State normalization and phase-space measures are those of the scattering conventions page.

The invariant phase space for a final state $X$ is denoted $d\Pi_X$. For a multiparticle final state,

$$
d\Pi_X
=
\prod_{a\in X}\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a},
$$

with an accompanying momentum-conservation delta function when inserted into a rate or cross section.

For a two-particle initial state, the invariant flux factor is

$$
\mathcal F
=4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}.
$$

If initial spin or color states are averaged in the cross section, the same average must be applied to the forward amplitude side.

## Derivation from unitarity

Start from

$$
S=1+iT.
$$

Unitarity gives

$$
S^\dagger S=1.
$$

Substitute $S=1+iT$:

$$
(1-iT^\dagger)(1+iT)=1.
$$

Expanding gives

$$
1+iT-iT^\dagger+T^\dagger T=1,
$$

so

$$
-i(T-T^\dagger)=T^\dagger T.
$$

Now sandwich this equation between the same initial state $|i\rangle$:

$$
-i\langle i|T-T^\dagger|i\rangle
=
\langle i|T^\dagger T|i\rangle.
$$

The left-hand side is

$$
-i(T_{ii}-T_{ii}^*)=2\operatorname{Im}T_{ii}.
$$

On the right-hand side, insert a complete set of physical states:

$$
\mathbf 1=\sum_X\int d\Pi_X\,|X\rangle\langle X|.
$$

Then

$$
\langle i|T^\dagger T|i\rangle
=
\sum_X\int d\Pi_X\,
\langle i|T^\dagger|X\rangle\langle X|T|i\rangle
=
\sum_X\int d\Pi_X\,|T_{Xi}|^2.
$$

Therefore

$$
2\operatorname{Im}T_{ii}
=
\sum_X\int d\Pi_X\,|T_{Xi}|^2.
$$

This is the optical theorem before stripping off momentum-conservation delta functions.

## Amplitude form

After removing the common spacetime volume factors and using the standard amplitude definition, the optical theorem becomes

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X
\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
|\mathcal M_{i\to X}|^2.
$$

This formula is one of the most useful equations in perturbative QFT. The left side is a forward amplitude. The right side is a sum over real physical states.

For a two-particle initial state, the total cross section is

$$
\sigma_{\rm tot}
=
\frac{1}{\mathcal F}
\sum_X
\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
|\mathcal M_{i\to X}|^2.
$$

Combining the previous two equations gives

$$
\sigma_{\rm tot}
=
\frac{2\operatorname{Im}\mathcal M_{i\to i}}{\mathcal F}.
$$

This is the common forward-amplitude version of the optical theorem. It is not a separate dynamical assumption. It is just unitarity plus phase-space normalization.

## Decays and self-energies

The same logic applies to unstable particles. For a one-particle initial state of mass $M$, the total decay rate is

$$
\Gamma_{\rm tot}
=
\frac{1}{2M}
\sum_X
\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(p-P_X)
|\mathcal M_{p\to X}|^2.
$$

The optical theorem relates this inclusive rate to the imaginary part of a forward matrix element or, equivalently, to the imaginary part of the self-energy near the pole.

For a scalar propagator written near the pole as

$$
\frac{i}{p^2-M^2-\Pi_{\rm ren}(p^2)+i\epsilon},
$$

a positive decay width corresponds to

$$
\Gamma
=
-\frac{1}{M}\operatorname{Im}\Pi_{\rm ren}(M^2),
$$

with this self-energy sign convention. The minus sign is a convention check, not deep metaphysics. Change the definition of $\Pi$, and the displayed sign changes.

Physically, the imaginary part appears only when intermediate states can go on shell. Below threshold, the same loop correction may be real. Above threshold, the loop knows that the particle can decay.

## Diagrammatic meaning: cuts

In perturbation theory, the optical theorem becomes a statement about cuts of diagrams. The right-hand side sums over on-shell intermediate states. A cut through a diagram is a graphical way to represent exactly that sum.

For a scalar cut line carrying momentum $k$, the Feynman propagator is replaced by an on-shell phase-space factor of the form

$$
\frac{i}{k^2-m^2+i\epsilon}
\quad\longrightarrow\quad
2\pi\theta(k^0)\delta(k^2-m^2),
$$

up to the sign and $i$ conventions appropriate to the full cutting rule being used.

Thus a one-loop bubble has an imaginary part when the two cut internal lines can both be on shell while conserving external momentum. This is the analytic origin of thresholds and branch cuts.

The full Cutkosky rules are a precise diagrammatic implementation of this idea. The optical theorem is the conceptual parent; cutting rules are the perturbative offspring.

## Forward does not mean trivial

The forward amplitude has the same initial and final quantum numbers:

$$
i\to i.
$$

This does not mean no scattering happened. It means the amplitude is evaluated at zero momentum transfer between the external state labels. Internal virtual states still explore the dynamics, and their imaginary parts encode all possible real final states.

For example, in $2\to2$ scattering, the forward amplitude has $t=0$. The total cross section includes elastic and inelastic contributions. The elastic process is only one term in the sum over $X$.

This is why the optical theorem is powerful: a single forward amplitude knows about a total inclusive probability.

## Partial-wave form

For identical spinless elastic scattering in a simple normalization, write the amplitude as

$$
\mathcal M(s,\cos\theta)
=16\pi\sum_{\ell=0}^{\infty}(2\ell+1)a_\ell(s)P_\ell(\cos\theta).
$$

Elastic unitarity below the first inelastic threshold implies

$$
\operatorname{Im}a_\ell(s)=\rho(s)|a_\ell(s)|^2,
$$

where $\rho(s)$ is the relevant two-body phase-space factor in the chosen normalization.

A common parametrization is

$$
a_\ell(s)=\frac{e^{2i\delta_\ell(s)}-1}{2i\rho(s)},
$$

where $\delta_\ell$ is the phase shift. When inelastic channels open, unitarity becomes an inequality or a matrix equation in channel space.

This partial-wave form is often the cleanest route from unitarity to bounds. It is the ancestor of perturbative unitarity constraints and modern positivity logic.

## Inclusive sums and infrared safety

The optical theorem naturally asks for an inclusive sum over final states. This is exactly the structure that appears in infrared physics.

If soft photons or gluons can be emitted with arbitrarily low energy, an exclusive final state with exactly no soft radiation is often not an infrared-safe observable. The physically measurable probability includes unresolved radiation below detector resolution. The optical theorem is compatible with this: it sums over all states included in the definition of the inclusive observable.

This is one way unitarity and infrared physics talk to each other. Virtual corrections produce imaginary and divergent pieces; real emissions supply the corresponding physical intermediate states; inclusive observables combine them into finite predictions when the KLN conditions are met.

## Common pitfalls

**Using $S$ instead of the connected $T$ amplitude.** The identity part of $S$ contains disconnected no-scattering contributions. The optical theorem for cross sections uses the connected transition operator after the standard delta functions are handled.

**Forgetting initial-state averages.** If a cross section averages over initial spins or colors, the forward amplitude side must be averaged in the same way.

**Confusing total and exclusive probabilities.** The theorem relates the forward amplitude to an inclusive sum over final states. It does not equate an imaginary part with one chosen exclusive channel unless that channel is the only available final state.

**Dropping identical-particle factors.** The phase-space side must include the same symmetry factors used in the definition of the rate or cross section.

**Ignoring thresholds.** Imaginary parts appear when intermediate states can go on shell. Below threshold, a loop may contribute to the real part without contributing to the total rate for that channel.

**Treating gauge-dependent cuts as physical.** In gauge theories, the physical state sum must be handled consistently. Gauge-dependent intermediate pieces can cancel in the final gauge-invariant result.

## Relations to other pages

- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the basic decomposition used here.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) introduces the idea before the dedicated unitarity chapter.
- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) defines the final-state measures on the right-hand side.
- [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/) explains the denominator in the total cross section.
- [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/) gives the one-particle version of the phase-space formula.
- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) explains how cut loop integrals expose the same on-shell intermediate states.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) and [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) explain why inclusive sums are essential in infrared-sensitive theories.

## Research status

- **Established:** The optical theorem follows from unitarity and is part of standard scattering theory. It is exact when the S-matrix exists and the relevant state sums are complete.
- **Active:** Modern work uses optical-theorem and cutting ideas in high-order collider calculations, finite-temperature rates, inclusive decay calculations, amplitude reconstruction, positivity bounds, and nonperturbative spectral constraints.
- **Speculative:** The theorem itself is not speculative. Its application can become subtle in theories without ordinary asymptotic states, in confining theories formulated in terms of partons, in cosmological spacetimes, and in gauge/gravity settings where the correct observables must be identified carefully.

## Exercises

### Exercise 1: Derive the operator identity

Starting from $S=1+iT$ and $S^\dagger S=1$, derive

$$
-i(T-T^\dagger)=T^\dagger T.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute $S=1+iT$ into unitarity:

$$
(1-iT^\dagger)(1+iT)=1.
$$

Multiplying out gives

$$
1+iT-iT^\dagger+T^\dagger T=1.
$$

Cancel the identity operator on both sides:

$$
iT-iT^\dagger+T^\dagger T=0.
$$

Move the first two terms to the other side or multiply by $-1$:

$$
-i(T-T^\dagger)=T^\dagger T.
$$

</details>

### Exercise 2: Insert a complete set of states

Use the identity from Exercise 1 to show that

$$
2\operatorname{Im}T_{ii}
=\sum_X\int d\Pi_X\,|T_{Xi}|^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Take the $|i\rangle$ matrix element of

$$
-i(T-T^\dagger)=T^\dagger T.
$$

The left-hand side is

$$
-i\left(\langle i|T|i\rangle-\langle i|T^\dagger|i\rangle\right)
=-i(T_{ii}-T_{ii}^*)
=2\operatorname{Im}T_{ii}.
$$

For the right-hand side, insert the complete set

$$
\mathbf 1=\sum_X\int d\Pi_X\,|X\rangle\langle X|.
$$

Then

$$
\langle i|T^\dagger T|i\rangle
=\sum_X\int d\Pi_X\,
\langle i|T^\dagger|X\rangle\langle X|T|i\rangle
=\sum_X\int d\Pi_X\,T_{Xi}^*T_{Xi}.
$$

Thus

$$
2\operatorname{Im}T_{ii}
=\sum_X\int d\Pi_X\,|T_{Xi}|^2.
$$

</details>

### Exercise 3: Total cross section from the forward amplitude

Assume a two-particle initial state and the standard definition

$$
d\sigma_{i\to X}
=\frac{1}{\mathcal F}
(2\pi)^4\delta^{(4)}(P_i-P_X)
|\mathcal M_{i\to X}|^2d\Pi_X.
$$

Use the optical theorem to show that

$$
\sigma_{\rm tot}
=\frac{2\operatorname{Im}\mathcal M_{i\to i}}{\mathcal F}.
$$

<details>
<summary><strong>Solution</strong></summary>

Sum the differential cross section over all final states:

$$
\sigma_{\rm tot}
=\frac{1}{\mathcal F}
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
|\mathcal M_{i\to X}|^2.
$$

The amplitude form of the optical theorem gives

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,
(2\pi)^4\delta^{(4)}(P_i-P_X)
|\mathcal M_{i\to X}|^2.
$$

Substituting this into the total cross section gives

$$
\sigma_{\rm tot}
=\frac{2\operatorname{Im}\mathcal M_{i\to i}}{\mathcal F}.
$$

</details>

### Exercise 4: Threshold for a scalar bubble

Consider a one-loop bubble with two identical internal scalar masses $m$ and external momentum $P$. Explain why the bubble can develop an imaginary part only when $P^2\ge4m^2$.

<details>
<summary><strong>Solution</strong></summary>

A cut through the two internal lines places both internal particles on shell:

$$
k^2=m^2,
\qquad
(P-k)^2=m^2,
$$

with positive energies. This is possible only if the total invariant mass available satisfies

$$
P^2\ge(2m)^2=4m^2.
$$

Below this threshold, no physical two-particle intermediate state with masses $m$ and $m$ can carry total momentum $P$. Therefore the corresponding two-particle cut has no support, and that channel does not contribute an imaginary part.

</details>

### Exercise 5: Self-energy sign check

Suppose a scalar propagator is written as

$$
\frac{i}{p^2-M^2-\Pi(p^2)}.
$$

Near the resonance pole, compare this with

$$
\frac{i}{p^2-M^2+iM\Gamma}
$$

and derive $\Gamma=-\operatorname{Im}\Pi(M^2)/M$.

<details>
<summary><strong>Solution</strong></summary>

At $p^2=M^2$, the imaginary part of the denominator in the self-energy convention is

$$
-\Pi(M^2)\supset -i\operatorname{Im}\Pi(M^2).
$$

The Breit–Wigner form has imaginary denominator

$$
iM\Gamma.
$$

Equating the imaginary parts gives

$$
-i\operatorname{Im}\Pi(M^2)=iM\Gamma.
$$

Therefore

$$
\Gamma=-\frac{1}{M}\operatorname{Im}\Pi(M^2).
$$

For a positive width, this convention has $\operatorname{Im}\Pi(M^2)<0$.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for S-matrix unitarity, transition rates, the optical theorem, partial waves, and resonances.
- S. Coleman, *Lectures on Quantum Field Theory*, ch. 12, for scattering applications and the optical theorem.
- M. Srednicki, *Quantum Field Theory*, §§10–11 and §20, for scattering amplitudes, cross sections, and loop-level elastic scattering.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for unitarity, the optical theorem, spectral decomposition, and analytic structure.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. III.8, for the optical theorem and probability-conservation viewpoint.
- R. E. Cutkosky, “Singularities and discontinuities of Feynman amplitudes,” *Journal of Mathematical Physics* **1** (1960), for the perturbative cutting rules.

## Version history

- **2026-06-13:** Initial QFT.org page. Added derivation from $S^\dagger S=1$, amplitude and cross-section forms, decay/self-energy version, diagrammatic cut interpretation, partial-wave remarks, infrared-inclusive context, and solved exercises.
