---
title: "Mass Renormalization"
description: "How self-energy counterterms, pole conditions, running masses, and symmetry protection determine the mass parameter in renormalized perturbation theory."
sidebar:
  label: "Mass Renormalization"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§13–16, 18–20, and 27–28; Coleman 2019, chs. 10, 15–16, 23, and 25; Weinberg 1995, Vol. I, chs. 10 and 12; Schwartz 2014, chs. 18–23; Zinn-Justin 2021, chs. 8–10"
topics:
  - mass renormalization
  - self-energy
  - pole mass
  - running mass
  - naturalness
canonicalTopics:
  - mass-renormalization
  - pole-mass
  - running-mass
  - mass-counterterm
  - scalar-mass-naturalness
researchStatus:
  established:
    - "Mass renormalization is the standard counterterm and scheme-dependent procedure that relates Lagrangian mass parameters to propagator poles, running masses, and measured particle masses."
  active:
    - "Precision gauge theories, unstable-particle masses, threshold masses, infrared-sensitive mass definitions, and scalar-naturalness questions require more refined treatments than the elementary scalar examples on this page."
---

## Summary

**Mass renormalization** is the part of renormalized perturbation theory that fixes the mass parameter appearing in propagators. Loop self-energies move propagator poles; mass counterterms are chosen so that the chosen mass definition remains finite and matches the selected renormalization condition.

For a scalar field with counterterms

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2,
$$

the renormalized self-energy is

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Z\,p^2.
$$

The exact stable-particle pole mass $M$ is determined by

$$
M^2-m^2-\operatorname{Re}\Sigma_{\rm ren}(M^2)=0.
$$

An on-shell scheme chooses the renormalized mass to be the pole mass. A minimal-subtraction scheme instead removes ultraviolet poles and leaves a running mass $m(\mu)$. Both descriptions can encode the same physics after conversion to observables.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Mass renormalization relates the bare mass, mass counterterm, self-energy, pole mass, and running mass](/figures/perturbative-qft/mass-renormalization-map.svg)

<figcaption>

Mass renormalization is the two-point part of parameter renormalization. The bare quadratic term is rewritten using renormalized parameters and counterterms. Loop self-energies plus counterterms define a finite inverse propagator. Different schemes turn that finite object into either a pole mass $M$ or a running mass $m(\mu)$.

</figcaption>
</figure>

The conceptual trap is to call every symbol named “mass” the same thing. A bare mass, a Lagrangian renormalized mass, a pole mass, a running mass, a screening mass, and a resonance mass are related, but they are not interchangeable.

## Prerequisites

You should know [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/), [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/), [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/), and [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/).

For scattering applications, review [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) and [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/).

## Core idea

Masses are read from poles, not from typography.

At tree level, the scalar propagator

$$
G_0(p)=\frac{i}{p^2-m^2+i\epsilon}
$$

has a pole at $p^2=m^2$. Once interactions are included, the propagator is corrected by self-energy insertions:

$$
G(p)=\frac{i}{p^2-m^2-\Sigma_{\rm ren}(p^2)+i\epsilon}.
$$

The mass parameter $m$ in the renormalized Lagrangian is now only one coordinate in a chosen scheme. The physical stable-particle mass is the position of the propagator pole. A renormalization condition is the rule that tells us how to choose $m$ and $\delta m^2$ so that the pole, or some other chosen reference quantity, has the desired value.

The practical slogan is

$$
\text{mass renormalization fixes the local two-point part of the inverse propagator.}
$$

The word “local” matters. A mass counterterm can cancel a momentum-independent ultraviolet divergence. It cannot remove a branch cut, a threshold logarithm, or the imaginary part associated with a physical decay channel. Those are not mistakes; they are physics.

## Setup and conventions

We use qft.org mostly-minus conventions. For scalar examples,

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
+\mathcal L_{\rm int},
$$

and

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2.
$$

The two-point counterterm vertex is

$$
 i(p^2\delta Z-\delta m^2).
$$

We define the scalar 1PI two-point insertion by

$$
\text{1PI two-point insertion}=-i\Sigma(p^2),
$$

so that

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Z\,p^2.
$$

The resummed scalar propagator is

$$
G(p)
=
\frac{i}{p^2-m^2-\Sigma_{\rm ren}(p^2)+i\epsilon}.
$$

When dimensional regularization is used, we write

$$
d=4-2\epsilon,
\qquad
\frac{1}{\overline\epsilon}
=
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

For a dimensionless quartic scalar coupling near four dimensions, the interaction is written

$$
\mathcal L_{\rm int}
=
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4.
$$

## Bare mass, renormalized mass, and counterterm

Start from a bare scalar quadratic Lagrangian,

$$
\mathcal L_0^{(2)}
=
\frac12\partial_\mu\phi_0\,\partial^\mu\phi_0
-
\frac12m_0^2\phi_0^2.
$$

Introduce

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z.
$$

The bare quadratic terms become

$$
\mathcal L_0^{(2)}
=
\frac12Z_\phi\partial_\mu\phi\,\partial^\mu\phi
-
\frac12Z_\phi m_0^2\phi^2.
$$

A convenient counterterm split is

$$
Z_\phi m_0^2=m^2+\delta m^2,
$$

so

$$
\mathcal L_0^{(2)}
=
\left[
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
\right]
+
\left[
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
\right].
$$

This is only a split of the same bare theory. It becomes predictive after a renormalization prescription specifies $m^2$, $\delta m^2$, and $\delta Z$ order by order.

Many books use instead

$$
m_0^2=Z_{m^2}m^2,
$$

or

$$
m_0^2=m^2+\Delta m^2.
$$

These notations are equivalent after translating how $Z_\phi$ is distributed. The safe object is the quadratic Lagrangian itself, not the name chosen for the mass counterterm.

## Pole mass

For a stable scalar particle, the pole mass $M$ is defined by the zero of the real part of the inverse propagator:

$$
M^2-m^2-\operatorname{Re}\Sigma_{\rm ren}(M^2)=0.
$$

Perturbatively, if $\Sigma_{\rm ren}$ is first order in the loop expansion, then

$$
M^2=m^2+\operatorname{Re}\Sigma_{\rm ren}(m^2)+O(\Sigma^2).
$$

This formula is useful, but it also reveals why the Lagrangian mass and the pole mass are not automatically the same. The loop self-energy shifts the pole unless the counterterm has been chosen to prevent that shift.

Near a stable pole,

$$
G(p)
\sim
\frac{iZ_{\rm pole}}{p^2-M^2+i\epsilon}
+
\text{regular terms},
$$

where

$$
Z_{\rm pole}^{-1}
=
1-\operatorname{Re}\Sigma_{\rm ren}'(M^2).
$$

Mass renormalization fixes the pole position. Wavefunction renormalization fixes, or at least tracks, the pole residue. They are coupled through the same two-point function but impose different conditions.

## On-shell mass renormalization

In an on-shell scheme for a stable scalar particle, one chooses the renormalized parameter to equal the physical pole mass:

$$
m^2=M^2.
$$

Then the mass-renormalization condition is

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0.
$$

If the residue is also normalized to one, one imposes

$$
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

Using

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2,
$$

the residue condition fixes

$$
\delta Z
=
\operatorname{Re}\Sigma_{\rm loop}'(M^2),
$$

and the pole condition fixes

$$
\delta m^2
=
M^2\delta Z
-
\operatorname{Re}\Sigma_{\rm loop}(M^2).
$$

If no residue condition is imposed, the mass condition alone fixes only the combination

$$
\delta m^2-M^2\delta Z.
$$

This is one reason mass and field-strength renormalization should be discussed together.

:::note[Unstable particles]
For an unstable particle, the pole is not on the real $p^2$ axis. A gauge-invariant pole definition uses the complex pole,

$$
p^2_{\rm pole}=M_{\rm pole}^2-iM_{\rm pole}\Gamma_{\rm pole},
$$

not the real zero of a gauge-dependent resummed denominator. The elementary on-shell scalar formulas on this page assume a stable particle unless explicitly stated otherwise.
:::

## Minimal-subtraction mass renormalization

Minimal subtraction does not define the mass by the propagator pole. It defines the mass by removing ultraviolet poles from two-point functions.

In scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

the one-loop tadpole self-energy is

$$
\Sigma_{\rm tad}^{(1)}
=
\frac{\lambda}{2}A(m^2),
$$

with

$$
A(m^2)
=
\frac{m^2}{16\pi^2}
\left[
-\frac{1}{\overline\epsilon}
+
\ln\frac{m^2}{\mu^2}
-1
\right]
+O(\epsilon).
$$

Thus the divergent part is

$$
\Sigma_{{\rm tad},\,\rm div}^{(1)}
=
-
\frac{\lambda m^2}{32\pi^2}
\frac{1}{\overline\epsilon}.
$$

At this order $\delta Z=0$ in four-dimensional $\phi^4$ theory, so minimal subtraction chooses

$$
\delta m^2_{\overline{\mathrm{MS}}}
=
\frac{\lambda m^2}{32\pi^2}
\frac{1}{\overline\epsilon}
+O(\lambda^2).
$$

The finite renormalized self-energy is then

$$
\Sigma_{\rm ren}^{(1)}
=
\frac{\lambda m^2}{32\pi^2}
\left[
\ln\frac{m^2}{\mu^2}-1
\right].
$$

The pole mass differs from the MS mass by a finite, scheme-dependent relation. To first order,

$$
M^2
=
m^2(\mu)
+
\frac{\lambda(\mu)m^2(\mu)}{32\pi^2}
\left[
\ln\frac{m^2(\mu)}{\mu^2}-1
\right]
+O(\lambda^2).
$$

The left-hand side is a physical pole location for a stable particle. The right-hand side contains running parameters. The equality is the matching relation between two descriptions.

## Running masses

A running mass is a scheme-dependent parameter that changes with $\mu$ so that bare quantities and physical predictions do not.

In an MS-like scheme, the bare mass is independent of $\mu$:

$$
\mu\frac{d m_0^2}{d\mu}=0.
$$

For the one-loop scalar example above, this gives the leading running

$$
\mu\frac{d m^2}{d\mu}
=
\gamma_{m^2}\,m^2,
\qquad
\gamma_{m^2}
=
\frac{\lambda}{16\pi^2}+O(\lambda^2).
$$

Here $\gamma_{m^2}$ is the anomalous dimension of the mass-squared parameter in this convention. Other normalizations of $\lambda$, or the choice $d=4-\epsilon$ instead of $d=4-2\epsilon$, move factors around.

Running masses are extremely useful because they absorb logarithms. If an observable contains powers of

$$
\ln\frac{Q^2}{m^2},
$$

choosing $\mu$ near $Q$ and using $m(\mu)$ often improves perturbation theory. But $m(\mu)$ itself is not directly what a detector measures. It is a scheme-defined coordinate.

## Fermion masses and chiral protection

For a Dirac fermion, write the inverse propagator conventionally as

$$
S^{-1}(p)
=
p\!\!\!/-m-\Sigma_F(p).
$$

The self-energy can be decomposed as

$$
\Sigma_F(p)
=
p\!\!\!/\,\Sigma_V(p^2)+m\Sigma_S(p^2)
$$

in a parity-invariant theory with one fermion species. The pole condition is the fermionic analogue of the scalar pole equation.

The important structural difference is symmetry. A fermion mass term

$$
-m\overline\psi\psi
$$

breaks chiral symmetry. If the theory and regulator preserve chiral symmetry at $m=0$, perturbation theory cannot generate an additive fermion mass from zero. Fermion mass renormalization is then multiplicative:

$$
m_0=Z_m m.
$$

This does not mean fermion masses are unrenormalized. It means that the massless point is protected: if $m=0$, then $m_0=0$ in a chiral-symmetry-preserving scheme. This is the seed of technical naturalness.

## Scalar masses and quadratic sensitivity

Scalar masses are different. The operator

$$
\phi^2
$$

is compatible with the ordinary $\phi\mapsto-\phi$ symmetry. Unless an additional symmetry forbids it, loop corrections can generate additive contributions to $m^2$.

With a hard Euclidean cutoff, the one-loop scalar tadpole contains

$$
\int^{\Lambda}\frac{d^4\ell_E}{(2\pi)^4}
\frac{1}{\ell_E^2+m^2}
=
\frac{1}{16\pi^2}
\left[
\Lambda^2
-
m^2\ln\frac{\Lambda^2}{m^2}
+\cdots
\right].
$$

The scalar mass shift in $\phi^4$ theory therefore includes the schematic sensitivity

$$
\Delta m^2
\sim
\frac{\lambda}{32\pi^2}\Lambda^2
+
\text{logarithmic and finite terms}.
$$

Dimensional regularization hides explicit power divergences, but it does not by itself solve the physical question of why a scalar mass is small compared with heavy thresholds. If a heavy particle of mass $M_H$ couples to $\phi$, integrating it out can generate finite threshold corrections of order

$$
\Delta m^2\sim \frac{g^2}{16\pi^2}M_H^2,
$$

unless a symmetry or dynamical mechanism prevents it.

This issue belongs conceptually to naturalness and EFT. The perturbative lesson here is narrower: scalar mass counterterms are additive and local, so scalar masses are sensitive to all allowed local two-point operators.

## Massless gauge bosons

Gauge boson masses are also symmetry-sensitive. A photon mass term,

$$
\frac12m_A^2 A_\mu A^\mu,
$$

is not gauge invariant in ordinary unbroken QED. Gauge invariance therefore forbids it. The vacuum polarization tensor has the transverse form

$$
\Pi^{\mu\nu}(p)
=
\left(p^2\eta^{\mu\nu}-p^\mu p^\nu\right)\Pi(p^2),
$$

so it does not generate a gauge-invariant photon mass term.

For non-Abelian gauge bosons, the same statement is enforced by Slavnov–Taylor identities and BRST symmetry. In a Higgs phase, gauge bosons can become massive, but the mass then comes from spontaneous symmetry breaking and the gauge-invariant structure of the Higgs sector, not from an arbitrary Proca counterterm added to an unbroken gauge theory.

## A quick dictionary of mass definitions

| Name | Definition | Typical use | Caveat |
|---|---|---|---|
| Bare mass | Regulator-dependent parameter in the bare Lagrangian | Formal starting point | Not directly measured |
| Renormalized mass | Parameter after a scheme choice | Perturbative calculations | Scheme and scale dependent |
| Pole mass | Position of a stable one-particle pole | Physical stable-particle mass | Subtle for confined or unstable particles |
| Running mass | Renormalized mass $m(\mu)$ in an RG scheme | Resumming logarithms | Not itself an observable |
| Screening mass | Exponential decay scale in spatial correlators | Thermal and statistical systems | Not generally the same as a pole mass |
| Complex pole mass | Pole of an unstable propagator | Resonances | Requires careful analytic continuation |

The table is deliberately not a list of synonyms. It is a list of related but distinct objects.

## Common pitfalls

**Calling the bare mass physical.** The bare mass depends on the regulator. It is adjusted so that chosen renormalized quantities stay finite.

**Confusing the Lagrangian mass with the pole mass.** They agree in an on-shell scheme by construction. They do not agree in MS without a finite conversion formula.

**Forgetting the field-strength term in a mass condition.** The on-shell mass condition involves $\delta m^2-M^2\delta Z$, not only $\delta m^2$, when the kinetic counterterm is present.

**Treating unstable particles like stable particles.** Resonance masses require complex-pole or process-dependent definitions. A real-axis self-energy condition can be gauge dependent.

**Using dimensional regularization to declare scalar naturalness gone.** Dimensional regularization removes explicit power divergences from the algebra, but finite heavy-threshold sensitivity remains a physical issue.

**Adding a photon mass counterterm in unbroken QED.** Gauge invariance forbids it. If a calculation seems to require one, the regulator or Ward identity bookkeeping has probably gone sideways.

## Relations to other pages

- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) defines the two-point insertion and Dyson-resummed denominator.
- [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/) explains the residue and kinetic counterterm that accompany mass renormalization.
- [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/) uses pole conditions to define physical masses for stable particles.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) defines running masses by ultraviolet pole subtraction rather than pole matching.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how the mass counterterm appears as a two-point vertex.
- [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/) explains how finite and divergent parts of counterterms are fixed.
- [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) uses resonance masses and widths in scattering and decay calculations.

## Research status

- **Established:** Mass renormalization, pole-mass conditions, MS running masses, and scalar/fermion/gauge-boson counterterm structures are textbook-standard in perturbative QFT.
- **Active:** High-precision mass definitions for quarks, unstable electroweak particles, threshold observables, finite-temperature systems, gauge-dependent intermediate quantities, and naturalness-sensitive scalar sectors remain technically and conceptually important.
- **Speculative:** Claims that one regulator or scheme alone solves scalar naturalness should be treated carefully; naturalness is about sensitivity to physical heavy thresholds and EFT structure, not merely the appearance of a cutoff symbol.

## Exercises

### Exercise 1: First-order pole shift

Starting from

$$
G(p)=\frac{i}{p^2-m^2-\Sigma(p^2)+i\epsilon},
$$

show that, to first order in $\Sigma$,

$$
M^2=m^2+\operatorname{Re}\Sigma(m^2)+O(\Sigma^2).
$$

<details>
<summary><strong>Solution</strong></summary>

The pole condition is

$$
M^2-m^2-\operatorname{Re}\Sigma(M^2)=0.
$$

Since $\Sigma$ is already first order in perturbation theory, $M^2-m^2$ is also first order. Expand

$$
\Sigma(M^2)=\Sigma(m^2)+(M^2-m^2)\Sigma'(m^2)+\cdots.
$$

The second term is second order because it is a product of $M^2-m^2$ and $\Sigma'$. Keeping only first order gives

$$
M^2-m^2-\operatorname{Re}\Sigma(m^2)=0,
$$

so

$$
M^2=m^2+\operatorname{Re}\Sigma(m^2)+O(\Sigma^2).
$$

</details>

### Exercise 2: On-shell counterterms

Assume

$$
\Sigma_{\rm ren}(p^2)=\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2.
$$

Impose

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

Solve for $\delta Z$ and $\delta m^2$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\Sigma_{\rm ren}'(p^2)=\Sigma_{\rm loop}'(p^2)-\delta Z.
$$

The residue condition gives

$$
0=\operatorname{Re}\Sigma_{\rm loop}'(M^2)-\delta Z,
$$

so

$$
\delta Z=\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

The mass condition gives

$$
0=\operatorname{Re}\Sigma_{\rm loop}(M^2)+\delta m^2-\delta ZM^2.
$$

Therefore

$$
\delta m^2=M^2\delta Z-\operatorname{Re}\Sigma_{\rm loop}(M^2).
$$

</details>

### Exercise 3: MS mass counterterm in φ⁴ theory

Use

$$
\Sigma_{\rm tad}^{(1)}=\frac{\lambda}{2}A(m^2),
$$

and

$$
A(m^2)
=
\frac{m^2}{16\pi^2}
\left[
-\frac{1}{\overline\epsilon}+\text{finite}
\right]
$$

to find the one-loop $\overline{\mathrm{MS}}$ mass counterterm in four-dimensional $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The divergent part of the tadpole self-energy is

$$
\Sigma_{{\rm tad},\,\rm div}^{(1)}
=
\frac{\lambda}{2}
\frac{m^2}{16\pi^2}
\left(-\frac{1}{\overline\epsilon}\right)
=
-
\frac{\lambda m^2}{32\pi^2}
\frac{1}{\overline\epsilon}.
$$

At this order $\delta Z=0$, so

$$
\Sigma_{\rm ren}^{(1)}=
\Sigma_{\rm tad}^{(1)}+\delta m^2.
$$

Minimal subtraction cancels the pole, hence

$$
\delta m^2_{\overline{\mathrm{MS}}}
=
\frac{\lambda m^2}{32\pi^2}
\frac{1}{\overline\epsilon}.
$$

</details>

### Exercise 4: Quadratic cutoff sensitivity

Evaluate the leading large-$\Lambda$ behavior of

$$
I_\Lambda(m^2)
=
\int^{\Lambda}\frac{d^4\ell_E}{(2\pi)^4}
\frac{1}{\ell_E^2+m^2}
$$

using spherical coordinates in four-dimensional Euclidean momentum space.

<details>
<summary><strong>Solution</strong></summary>

The angular volume of the unit three-sphere is

$$
\Omega_3=2\pi^2.
$$

Thus

$$
I_\Lambda(m^2)
=
\frac{2\pi^2}{(2\pi)^4}
\int_0^\Lambda d\ell\,
\frac{\ell^3}{\ell^2+m^2}
=
\frac{1}{8\pi^2}
\int_0^\Lambda d\ell\,
\frac{\ell^3}{\ell^2+m^2}.
$$

Use

$$
\frac{\ell^3}{\ell^2+m^2}=\ell-
\frac{m^2\ell}{\ell^2+m^2}.
$$

Then

$$
I_\Lambda(m^2)
=
\frac{1}{8\pi^2}
\left[
\frac{\Lambda^2}{2}
-
\frac{m^2}{2}\ln\frac{\Lambda^2+m^2}{m^2}
\right].
$$

For $\Lambda\gg m$,

$$
I_\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\Lambda^2
-
m^2\ln\frac{\Lambda^2}{m^2}
+\cdots
\right].
$$

</details>

### Exercise 5: Chiral protection of a fermion mass

Suppose a massless Dirac theory has the chiral symmetry

$$
\psi\mapsto e^{i\alpha\gamma^5}\psi.
$$

Explain why a counterterm proportional to $\overline\psi\psi$ is forbidden if the regulator preserves the symmetry.

<details>
<summary><strong>Solution</strong></summary>

The fermion mass operator is

$$
\overline\psi\psi
=
\overline\psi_L\psi_R+
\overline\psi_R\psi_L.
$$

Under an axial rotation, the left- and right-handed fields transform with opposite phases. Therefore $\overline\psi_L\psi_R$ and $\overline\psi_R\psi_L$ acquire nontrivial phases unless the rotation angle is special. The operator $\overline\psi\psi$ is not invariant under the continuous chiral symmetry.

A counterterm must respect the symmetries preserved by the regulator and by the renormalization prescription. Therefore, when $m=0$ and chiral symmetry is preserved, an additive mass counterterm is forbidden. Mass renormalization is multiplicative:

$$
m_0=Z_m m,
$$

so $m=0$ remains $m_0=0$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§13–16 and §§27–28, for propagator poles, self-energies, and scheme dependence of renormalized masses.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 10, 15–16, 23, and 25, for mass renormalization, spectral interpretation, fermion masses, and general renormalization logic.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 10 and 12, for renormalized perturbation theory, mass parameters, and the general structure of counterterms.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–23, for pole masses, counterterms, minimal subtraction, and running parameters in practical calculations.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for mass renormalization, RG equations, and scalar-theory power counting.

## Version history

- **2026-06-12:** Initial polished draft. Added scalar mass counterterm conventions, pole-mass and on-shell formulas, MS mass counterterm example, running-mass discussion, scalar naturalness preview, symmetry-protection comparisons, solved exercises, and a compact mass-renormalization map figure.
