---
title: "Single-Particle States"
description: "Momentum eigenstates, mass shell, spin, helicity, little groups, wave packets, and the Poincaré-representation viewpoint on relativistic one-particle states."
sidebar:
  label: "Single-Particle States"
  order: 2
level: Graduate
status: "Polished draft"
topics:
  - one-particle states
  - Poincaré group
  - mass shell
  - little group
  - spin
  - helicity
canonicalTopics:
  - one-particle-state
  - mass-shell
  - little-group
  - helicity
---

## Summary

A stable relativistic particle is first a state in Hilbert space. Kinematically, an elementary particle species is described by an irreducible unitary representation of the Poincaré group. Translations measure its four-momentum. Lorentz transformations move it along the mass shell. The little group supplies the spin or helicity labels.

For a massive particle in qft.org conventions,

$$
P^\mu\lvert \boldsymbol p,\sigma,a\rangle
=p^\mu\lvert \boldsymbol p,\sigma,a\rangle,
\qquad
p^\mu=(E_{\boldsymbol p},\boldsymbol p),
\qquad
E_{\boldsymbol p}=\sqrt{\boldsymbol p^2+m^2}.
$$

The momentum lies on the positive-energy mass shell,

$$
p^2=m^2,
\qquad
p^0>0.
$$

The label $\sigma$ is a spin projection for massive particles and a helicity label for massless particles. The label $a$ collects internal quantum numbers such as charge, flavor, color representation, or species.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Mass shells and little groups for massive and massless one-particle states](/figures/foundations/mass-shell-little-groups.svg)

<figcaption>

Massive particles have a rest frame, so their little group is the rotation group. Massless particles have no rest frame; their ordinary finite-polarization representations are labeled by helicity.

</figcaption>
</figure>

## Prerequisites

You should know [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/) and the conventions from [Conventions and Normalizations](/foundations/conventions-and-normalizations/). The page assumes special relativity, angular momentum in quantum mechanics, and Dirac notation.

## The core idea

The one-particle story is kinematics. It does not yet require a Lagrangian, path integral, or field equation.

The Poincaré group contains translations and Lorentz transformations. Momentum eigenstates diagonalize translations. Lorentz transformations preserve $p^2$, so they move a state around a fixed orbit in momentum space. The transformations that leave a chosen standard momentum fixed form the little group, and the little group labels the remaining internal spacetime degrees of freedom.

:::note[What this page is not saying]
A one-particle representation is a good object. The point of QFT is not to abolish it. The point is that a local interacting relativistic theory also needs multiparticle states, antiparticles, and local fields.
:::

## Momentum eigenstates

Let $P^\mu$ be the generators of spacetime translations. A momentum eigenstate satisfies

$$
P^\mu\lvert p,\sigma,a\rangle
=p^\mu\lvert p,\sigma,a\rangle.
$$

For a massive particle,

$$
p^2=m^2,
\qquad
p^0=E_{\boldsymbol p}=\sqrt{\boldsymbol p^2+m^2}>0.
$$

For a massless particle,

$$
p^2=0,
\qquad
p^0=|\boldsymbol p|>0.
$$

Because $p^0$ is fixed by $\boldsymbol p$ and the mass, one often writes

$$
\lvert p,\sigma,a\rangle
\equiv
\lvert \boldsymbol p,
\sigma,a\rangle.
$$

These are delta-normalized generalized eigenstates, not finite-norm localized states. Physical one-particle states are wave packets built from them.

## Translations

Under a spacetime translation by $b^\mu$,

$$
U(b)\lvert p,\sigma,a\rangle
=e^{ip\cdot b}\lvert p,\sigma,a\rangle.
$$

Translations therefore do not mix different momenta. They only multiply a momentum eigenstate by a phase. The interesting structure comes from Lorentz transformations.

## Lorentz transformations and Wigner rotations

A Lorentz transformation sends $p$ to $\Lambda p$. Spin labels can rotate among themselves. With covariant state normalization, a massive spin-$j$ state transforms schematically as

$$
U(\Lambda)\lvert p,\sigma,a\rangle
=
\sum_{\sigma'}D^{(j)}_{\sigma'\sigma}\!\left(W(\Lambda,p)\right)
\lvert \Lambda p,\sigma',a\rangle.
$$

Here

$$
W(\Lambda,p)=L^{-1}(\Lambda p)\Lambda L(p)
$$

is the Wigner rotation. The standard boost $L(p)$ carries a chosen standard momentum $k$ to $p$.

The formula has a simple meaning. To compare spin labels at different momenta, choose a standard way to boost from $k$ to $p$. A general Lorentz transformation moves the momentum. Boosting back to the standard momentum leaves a transformation that fixes $k$. That leftover transformation acts on spin labels.

## Massive particles: spin

For $m>0$, choose the rest momentum

$$
k^\mu=(m,0,0,0).
$$

The little group preserving $k$ is the rotation group $SO(3)$, or its double cover $SU(2)$ when spinors are included. Its irreducible representations are labeled by

$$
j=0,\frac12,1,\frac32,\ldots,
$$

with spin projection

$$
\sigma=-j,-j+1,\ldots,j.
$$

A massive spin-$j$ particle has

$$
2j+1
$$

spin states.

Examples:

| Particle type | Mass | Spacetime label |
|---|---:|---|
| massive scalar | $m>0$ | $j=0$ |
| massive Dirac particle | $m>0$ | $j=1/2$, two spin states |
| massive vector particle | $m>0$ | $j=1$, three spin states |

## Massless particles: helicity

For a massless particle, choose a standard null momentum such as

$$
k^\mu=(\kappa,0,0,\kappa),
\qquad
\kappa>0.
$$

There is no rest frame. The little group is $ISO(2)$, the Euclidean group of the plane. The ordinary finite-polarization particles used in local QFT have representations in which the translation-like part acts trivially. The remaining label is helicity,

$$
\lambda=\frac{\boldsymbol J\cdot\boldsymbol p}{|\boldsymbol p|}.
$$

For proper orthochronous Lorentz transformations, helicity is invariant. If parity is a symmetry and both helicities occur, parity flips helicity:

$$
\lambda\mapsto -\lambda.
$$

Examples:

| Particle type | Mass | Physical helicities |
|---|---:|---|
| massless scalar | $0$ | $0$ |
| photon | $0$ | $\pm1$ |
| graviton in perturbative gravity | $0$ | $\pm2$ |

Gauge redundancy in massless spin-one and spin-two fields is closely tied to this representation theory. That story continues in the gauge-field pages.

## Casimirs

The Poincaré algebra has two standard invariant operators. The first is

$$
P^2=P_\mu P^\mu.
$$

On a one-particle state,

$$
P^2\lvert p,\sigma,a\rangle
=m^2\lvert p,\sigma,a\rangle.
$$

The second uses the Pauli–Lubanski vector,

$$
W^\mu=\frac12\epsilon^{\mu\nu\rho\sigma}P_\nu J_{\rho\sigma}.
$$

For a massive spin-$j$ particle,

$$
W^2=-m^2j(j+1).
$$

For a finite-helicity massless particle,

$$
W^\mu=\lambda P^\mu,
\qquad
W^2=0.
$$

Thus mass and spin are not decorative labels. They are symmetry data of the state.

## Field components are not particle degrees of freedom

A common beginner mistake is to identify the number of field components with the number of particle degrees of freedom.

A scalar field creates spin-zero particles. A Dirac spinor field has four complex components in a common notation, but its particle states have spin one-half and come with particle and antiparticle sectors. A four-vector potential $A_\mu$ has four spacetime components, but the photon has two physical helicities.

The particle is classified by the representation carried by one-particle states. The field is a local operator chosen to transform covariantly and to create, annihilate, or interpolate those states.

## Wave packets

A normalizable one-particle state is a wave packet,

$$
\lvert\Psi\rangle
=\sum_a\int d\Pi_p\,f_a(\boldsymbol p)\lvert \boldsymbol p,a\rangle,
$$

where

$$
d\Pi_p=\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}}.
$$

With the qft.org normalization,

$$
\langle\Psi\mid\Psi\rangle
=\sum_a\int d\Pi_p\,|f_a(\boldsymbol p)|^2.
$$

Plane waves make formulas compact. Wave packets are the physical way to talk about normalizable incoming and outgoing particles.

## Common pitfalls

**Treating the Klein–Gordon equation as the definition of a scalar particle.** A stable scalar particle is a one-particle state with fixed mass and spin zero. The Klein–Gordon equation is the field equation for the simplest scalar field.

**Forgetting the positive-energy condition.** The mass shell has positive- and negative-energy sheets. The one-particle Hilbert space of ordinary stable particles uses $p^0>0$.

**Calling helicity just “spin.”** Massive spin is defined in the rest frame. Massless particles have no rest frame, and helicity is the invariant label for ordinary finite-polarization representations.

**Confusing field indices with physical polarization states.** Covariant fields often contain auxiliary, constrained, or gauge-redundant components.

## Relation to other topics

- [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/) explains why one-particle kinematics is not enough for interacting local QFT.
- [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/) fixes the state normalization and invariant measure used here.
- [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/) builds tensor-product sectors and identical-particle state spaces.
- [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/) states the full algebra.
- [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/) explains spinor representations.
- [Polarizations](/foundations/free-fields/polarizations/) connects one-particle helicity and spin labels to field polarizations.

## Research status

- **Established:** Wigner’s classification of stable one-particle states by Poincaré representations is textbook-standard.
- **Active:** Particle definitions require care in curved spacetime, gauge theory, confinement, infraparticle physics, and theories without isolated one-particle poles.

## References

- E. Wigner, “On unitary representations of the inhomogeneous Lorentz group,” *Annals of Mathematics* 40 (1939).
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2 and 5.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 1–3.
- M. Srednicki, *Quantum Field Theory*, §§1–2.

## Version history

- **2026-06-08:** Revised for chapter flow, cleaner particle-versus-field distinctions, shorter exposition, and reader-facing caveats.
