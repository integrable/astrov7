---
title: "Partial-Wave Unitarity"
description: "How S-matrix unitarity constrains angular-momentum partial waves, phase shifts, inelasticity, tree amplitudes, and EFT validity."
sidebar:
  label: "Partial-Wave Unitarity"
  order: 5
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I; Coleman ch. 12; Schwartz ch. 24; Peskin and Schroeder"
topics:
  - partial waves
  - unitarity
  - phase shifts
  - scattering amplitudes
  - perturbative unitarity
  - effective field theory
canonicalTopics:
  - partial-wave-unitarity
  - partial-wave-expansion
  - perturbative-unitarity-bound
  - phase-shift-unitarity
researchStatus:
  established:
    - "Partial-wave unitarity is a standard consequence of S-matrix unitarity and angular-momentum decomposition for two-body scattering."
  active:
    - "Modern applications include EFT validity estimates, positivity programs, coupled-channel amplitude analyses, collider unitarity checks, and nonperturbative S-matrix bootstrap methods."
---

## Summary

**Partial-wave unitarity** is S-matrix unitarity resolved into angular-momentum channels. It turns the abstract equation

$$
S^\dagger S=1
$$

into concrete bounds on the coefficients in a partial-wave expansion.

For spinless $2\to2$ scattering in the center-of-mass frame, write

$$
\mathcal M(s,z)=16\pi\sum_{\ell=0}^\infty(2\ell+1)a_\ell(s)P_\ell(z),
\qquad z=\cos\theta.
$$

For a single elastic two-particle channel, define

$$
\widehat a_\ell(s)\equiv \rho(s)a_\ell(s),
\qquad
\rho(s)=\frac{2p_{\rm cm}}{\sqrt s}.
$$

Then unitarity implies

$$
\operatorname{Im}\widehat a_\ell(s)\ge |\widehat a_\ell(s)|^2.
$$

In the purely elastic case,

$$
\widehat a_\ell(s)=e^{i\delta_\ell(s)}\sin\delta_\ell(s),
$$

so each partial wave lies on the **unitarity circle**

$$
\left|\widehat a_\ell-\frac{i}{2}\right|=\frac{1}{2}.
$$

With inelastic channels open, the equality becomes an inequality and the partial wave moves inside the circle.

<figure class="doc-figure" style="--figure-width: 36rem; --caption-width: 52rem;">

![Partial-wave unitarity constrains each angular-momentum amplitude to an Argand circle](/figures/perturbative-qft/partial-wave-unitarity.svg)

<figcaption>

In the elastic region, each normalized partial wave $\widehat a_\ell=\rho a_\ell$ lies on the unitarity circle centered at $i/2$. Inelastic channels move it inside the disk. A tree-level real partial wave must remain in the interval $|\operatorname{Re}\widehat a_\ell|\le 1/2$ if perturbation theory is to remain trustworthy.

</figcaption>
</figure>

Partial-wave unitarity is not just a formal nicety. It diagnoses when a tree amplitude has grown too large, when an EFT is being pushed beyond its range, when a resonance is forming, and when a perturbative description must be replaced by loops, new states, strong dynamics, or a different expansion.

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/), and [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/).

For analytic applications, [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/) and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) are the natural next companions.

## Core idea

Two-body scattering in a rotationally invariant center-of-mass frame decomposes into angular-momentum channels. Different $\ell$ values do not mix if the particles are spinless and the interaction respects rotations. The full unitarity condition becomes an independent constraint for each $\ell$.

This is the angular-momentum version of the optical theorem. Probability conservation gives the optical theorem for the full forward amplitude; after angular-momentum decomposition, the same probability conservation gives a separate unitarity constraint for each $\ell$.

The reason partial waves are useful is that a complicated angular function becomes a list of numbers $a_\ell(s)$ at each energy. Unitarity bounds each number sharply.

## Setup and conventions

Consider spinless $1+2\to3+4$ scattering in the center-of-mass frame. Let

$$
z=\cos\theta,
$$

where $\theta$ is the angle between the incoming and outgoing relative momenta. For the simplest elastic case with equal incoming and outgoing masses, the two-body phase-space factor is

$$
\rho(s)=\frac{2p_{\rm cm}}{\sqrt s}.
$$

For equal masses $m$,

$$
\rho(s)=\sqrt{1-\frac{4m^2}{s}}.
$$

The spinless partial-wave expansion is

$$
\mathcal M(s,z)
=16\pi\sum_{\ell=0}^\infty(2\ell+1)a_\ell(s)P_\ell(z).
$$

The inverse formula is

$$
a_\ell(s)=\frac{1}{32\pi}\int_{-1}^{1}dz\,P_\ell(z)\mathcal M(s,z).
$$

The phase-space-normalized partial wave is

$$
\widehat a_\ell(s)=\rho(s)a_\ell(s).
$$

This normalization is chosen so that the elastic unitarity circle has radius $1/2$. Other books absorb $\rho(s)$ into the definition of the partial wave. That is fine; it just moves the phase-space factor.

## Elastic unitarity and phase shifts

For a single elastic channel, the partial-wave S-matrix can be written

$$
S_\ell=e^{2i\delta_\ell(s)},
$$

where $\delta_\ell(s)$ is the phase shift. Define $\widehat a_\ell$ by

$$
S_\ell=1+2i\widehat a_\ell.
$$

Then

$$
\widehat a_\ell
=\frac{e^{2i\delta_\ell}-1}{2i}
=e^{i\delta_\ell}\sin\delta_\ell.
$$

Therefore

$$
\operatorname{Im}\widehat a_\ell
=\sin^2\delta_\ell,
\qquad
|\widehat a_\ell|^2
=\sin^2\delta_\ell.
$$

So elastic unitarity gives

$$
\operatorname{Im}\widehat a_\ell=|\widehat a_\ell|^2.
$$

Geometrically,

$$
\left(\operatorname{Re}\widehat a_\ell\right)^2
+
\left(\operatorname{Im}\widehat a_\ell-\frac12\right)^2
=\frac14.
$$

This circle is the Argand-diagram form of elastic probability conservation.

## Inelasticity

Once additional final states are available, the elastic two-body channel is no longer a closed system. The elastic partial-wave S-matrix is commonly written

$$
S_\ell=\eta_\ell(s)e^{2i\delta_\ell(s)},
\qquad 0\le\eta_\ell\le1.
$$

Here $\eta_\ell=1$ means purely elastic scattering. Values $\eta_\ell<1$ mean probability has leaked into inelastic channels.

The corresponding partial wave is

$$
\widehat a_\ell
=\frac{\eta_\ell e^{2i\delta_\ell}-1}{2i}.
$$

One finds

$$
\operatorname{Im}\widehat a_\ell-|\widehat a_\ell|^2
=\frac{1-\eta_\ell^2}{4}\ge0.
$$

Thus the general single-channel elastic amplitude satisfies

$$
\operatorname{Im}\widehat a_\ell\ge |\widehat a_\ell|^2,
$$

and lies inside the same unitarity disk:

$$
\left|\widehat a_\ell-\frac{i}{2}\right|\le\frac{1}{2}.
$$

The missing distance to the elastic circle measures inelastic probability in that partial wave.

## Tree-level perturbative unitarity

At tree level, amplitudes in a real theory are often real away from poles and thresholds. But exact unitarity requires an imaginary part:

$$
\operatorname{Im}\widehat a_\ell=|\widehat a_\ell|^2+\cdots.
$$

This is not a contradiction. The imaginary part appears at the next order in perturbation theory. If

$$
\widehat a_\ell
=\widehat a_\ell^{(0)}+\widehat a_\ell^{(1)}+\cdots,
$$

with $\widehat a_\ell^{(0)}$ real, then perturbative unitarity begins as

$$
\operatorname{Im}\widehat a_\ell^{(1)}
=|\widehat a_\ell^{(0)}|^2.
$$

The tree amplitude is trustworthy only if it is small enough that the loop correction required by unitarity is genuinely a correction. A common diagnostic is

$$
|\operatorname{Re}\widehat a_\ell^{(0)}|\le\frac12.
$$

This is not a sacred cliff edge. It is a conservative warning sign: once a tree-level partial wave approaches the edge of the disk, fixed-order perturbation theory is no longer parametrically reliable.

## Example: contact interaction in scalar theory

Take a constant tree amplitude

$$
\mathcal M_{\rm tree}(s,z)=-\lambda.
$$

Only the $\ell=0$ partial wave is nonzero:

$$
a_0^{\rm tree}
=\frac{1}{32\pi}\int_{-1}^{1}dz\,(-\lambda)
=-\frac{\lambda}{16\pi}.
$$

Thus

$$
\widehat a_0^{\rm tree}
=-\rho(s)\frac{\lambda}{16\pi}.
$$

The perturbative unitarity estimate gives

$$
\rho(s)|\lambda|\lesssim 8\pi.
$$

At high energy for massive particles, $\rho(s)\to1$, so this becomes $|\lambda|\lesssim 8\pi$ in this simple normalization. The exact numerical coefficient can change with identical-particle conventions or coupled-channel eigenvalues, but the lesson survives: a large constant quartic coupling is not perturbative merely because it is dimensionless.

## Example: growing EFT amplitude

Suppose a higher-dimension operator generates a high-energy amplitude of the rough form

$$
\mathcal M_{\rm tree}(s,z)=c\frac{s}{\Lambda^2},
$$

with weak angular dependence ignored for clarity. Then

$$
a_0^{\rm tree}(s)=\frac{c}{16\pi}\frac{s}{\Lambda^2},
\qquad
\widehat a_0^{\rm tree}(s)=\rho(s)\frac{c}{16\pi}\frac{s}{\Lambda^2}.
$$

The tree-level unitarity estimate gives

$$
s\lesssim \frac{8\pi}{|c|\rho(s)}\Lambda^2.
$$

This does not mean the EFT mathematically self-destructs at exactly that energy. It means the truncated tree EFT cannot be trusted there without additional terms, loops, new degrees of freedom, or a UV completion.

This is one of the most useful practical roles of partial-wave unitarity: it turns “the amplitude grows with energy” into a channel-by-channel diagnostic.

## Coupled channels

If several two-body channels share the same quantum numbers, partial waves become matrices. Schematically,

$$
S_\ell=1+2i\widehat A_\ell,
$$

where $\widehat A_\ell$ is a matrix in channel space. Unitarity gives

$$
\operatorname{Im}\widehat A_\ell
=\widehat A_\ell^\dagger\widehat A_\ell
+\text{positive inelastic contribution}.
$$

Tree-level perturbative unitarity is then applied to eigenvalues of the real symmetric tree-level partial-wave matrix. This is why multi-field scalar sectors, electroweak gauge-boson scattering, and coupled EFT amplitudes are usually analyzed by diagonalizing a partial-wave matrix, not by bounding a single diagram.

## Spin and helicity

For spinning particles, Legendre polynomials are replaced by Wigner $d$-functions or helicity partial waves. The logic is unchanged: expand in angular-momentum channels, normalize by the two-body phase space, and apply unitarity channel by channel.

The details matter. Spin labels, helicity flips, identical-particle symmetrization, color, and coupled channels all affect the partial-wave matrix. The scalar formula on this page is the cleanest version, not the most general one.

## Common pitfalls

**Bounding the full amplitude instead of partial waves.** Unitarity constrains angular-momentum components, not $\mathcal M(s,z)$ pointwise at every angle.

**Dropping the phase-space factor.** Whether $\rho(s)$ appears in the expansion or in the unitarity equation is convention-dependent, but it must appear somewhere.

**Treating the tree bound as exact.** The tree-level criterion is a perturbative reliability estimate. Exact unitarity is a statement about the full amplitude.

**Ignoring coupled channels.** The strongest bound often comes from an eigenvalue of a channel matrix, not from a single process.

**Using the formula across massless forward singularities.** Long-range forces and $t$-channel massless poles can make the naive partial-wave expansion subtle or divergent.

**Forgetting identical-particle projections.** Identical bosons and fermions restrict allowed angular momenta and add symmetry factors in observables.

## Relations to other pages

- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) is the forward-amplitude version of probability conservation.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) fixes the cross-section normalization used with $\mathcal M$.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) defines the kinematic variables used in partial-wave expansions.
- [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/) combine analyticity with unitarity data.
- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) gives examples where partial-wave bounds can be applied directly.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how loop amplitudes restore perturbative unitarity order by order.

## Research status

- **Established:** Partial-wave decomposition, phase shifts, inelasticity parameters, unitarity circles, and tree-level perturbative unitarity bounds are standard S-matrix tools.
- **Active:** Modern applications include coupled-channel amplitude analysis, lattice finite-volume scattering, positivity bounds, EFT cutoff diagnostics, strongly coupled electroweak sectors, and numerical S-matrix bootstrap.
- **Approximate:** Tree-level unitarity bounds are estimates of perturbative breakdown, not exact thresholds for new physics.

## Exercises

### Exercise 1: Inverse partial-wave formula

Starting from

$$
\mathcal M(s,z)=16\pi\sum_{\ell=0}^\infty(2\ell+1)a_\ell(s)P_\ell(z),
$$

show that

$$
a_\ell(s)=\frac{1}{32\pi}\int_{-1}^{1}dz\,P_\ell(z)\mathcal M(s,z).
$$

<details>
<summary><strong>Solution</strong></summary>

Use Legendre orthogonality:

$$
\int_{-1}^{1}dz\,P_\ell(z)P_{\ell'}(z)
=\frac{2}{2\ell+1}\delta_{\ell\ell'}.
$$

Multiplying the expansion by $P_L(z)$ and integrating gives

$$
\int_{-1}^{1}dz\,P_L(z)\mathcal M(s,z)
=16\pi\sum_\ell(2\ell+1)a_\ell
\frac{2}{2\ell+1}\delta_{\ell L}
=32\pi a_L.
$$

Therefore

$$
a_L(s)=\frac{1}{32\pi}\int_{-1}^{1}dz\,P_L(z)\mathcal M(s,z).
$$

</details>

### Exercise 2: Elastic unitarity circle

Let

$$
\widehat a=e^{i\delta}\sin\delta.
$$

Show that

$$
\left|\widehat a-\frac{i}{2}\right|=\frac12.
$$

<details>
<summary><strong>Solution</strong></summary>

Write

$$
\widehat a=\sin\delta\cos\delta+i\sin^2\delta.
$$

Then

$$
\operatorname{Re}\widehat a=\sin\delta\cos\delta,
\qquad
\operatorname{Im}\widehat a=\sin^2\delta.
$$

Thus

$$
\left|\widehat a-\frac{i}{2}\right|^2
=\sin^2\delta\cos^2\delta+
\left(\sin^2\delta-\frac12\right)^2.
$$

Using $\sin^2\delta\cos^2\delta=\sin^2\delta(1-\sin^2\delta)$, this becomes

$$
\sin^2\delta-\sin^4\delta+
\sin^4\delta-\sin^2\delta+\frac14
=\frac14.
$$

Taking the square root gives the result.

</details>

### Exercise 3: Contact interaction bound

For $\mathcal M=-\lambda$, compute the $s$-wave partial wave and the tree-level unitarity estimate.

<details>
<summary><strong>Solution</strong></summary>

Only $P_0=1$ contributes:

$$
a_0=\frac{1}{32\pi}\int_{-1}^{1}dz\,(-\lambda)
=-\frac{\lambda}{16\pi}.
$$

The normalized partial wave is

$$
\widehat a_0=-\rho\frac{\lambda}{16\pi}.
$$

The tree-level criterion $|\operatorname{Re}\widehat a_0|\le1/2$ gives

$$
\rho|\lambda|\le8\pi.
$$

For high-energy equal-mass scattering, $\rho\to1$, so $|\lambda|\lesssim8\pi$.

</details>

### Exercise 4: Inelastic inequality

Given

$$
S=\eta e^{2i\delta},
\qquad
\widehat a=\frac{S-1}{2i},
$$

show that

$$
\operatorname{Im}\widehat a-|\widehat a|^2=\frac{1-\eta^2}{4}.
$$

<details>
<summary><strong>Solution</strong></summary>

Write

$$
\widehat a
=\frac{\eta\cos2\delta+i\eta\sin2\delta-1}{2i}
=\frac{\eta\sin2\delta}{2}
+i\frac{1-\eta\cos2\delta}{2}.
$$

Therefore

$$
\operatorname{Im}\widehat a=\frac{1-\eta\cos2\delta}{2}
$$

and

$$
|\widehat a|^2
=\frac{\eta^2\sin^2 2\delta+(1-\eta\cos2\delta)^2}{4}
=\frac{1-2\eta\cos2\delta+\eta^2}{4}.
$$

Subtracting gives

$$
\operatorname{Im}\widehat a-|\widehat a|^2
=\frac{2-2\eta\cos2\delta-1+2\eta\cos2\delta-\eta^2}{4}
=\frac{1-\eta^2}{4}.
$$

</details>

### Exercise 5: Growing EFT amplitude

Let

$$
\mathcal M(s,z)=c\frac{s}{\Lambda^2}
$$

with no angular dependence. Estimate the energy where tree-level $s$-wave unitarity becomes questionable for $\rho\approx1$.

<details>
<summary><strong>Solution</strong></summary>

The $s$-wave coefficient is

$$
a_0=\frac{1}{32\pi}\int_{-1}^{1}dz\,c\frac{s}{\Lambda^2}
=\frac{c}{16\pi}\frac{s}{\Lambda^2}.
$$

With $\rho\approx1$,

$$
\widehat a_0\approx \frac{c}{16\pi}\frac{s}{\Lambda^2}.
$$

The criterion $|\operatorname{Re}\widehat a_0|\le1/2$ gives

$$
\frac{|c|}{16\pi}\frac{s}{\Lambda^2}\lesssim\frac12,
$$

or

$$
\sqrt s\lesssim \sqrt{\frac{8\pi}{|c|}}\,\Lambda.
$$

This is an estimate of the breakdown of the truncated tree-level EFT description.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for S-matrix unitarity, partial waves, phase shifts, and cross-section relations.
- S. Coleman, *Lectures on Quantum Field Theory*, ch. 12, for scattering, phase space, and the optical theorem in a physically transparent normalization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for unitarity, partial-wave reasoning, and modern implications.
- M. E. Peskin and D. V. Schroeder, *An Introduction to Quantum Field Theory*, for perturbative unitarity examples in scalar and electroweak settings.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for classic S-matrix and partial-wave analytic structure.

## Version history

- **2026-06-13:** Initial polished draft. Added spinless partial-wave normalization, elastic and inelastic unitarity, Argand-circle figure, perturbative unitarity estimates, scalar and EFT examples, common pitfalls, and solved exercises.
