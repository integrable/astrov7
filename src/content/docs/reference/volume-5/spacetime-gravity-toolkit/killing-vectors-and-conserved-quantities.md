---
title: "Killing Vectors and Conserved Quantities"
description: "A QFT-oriented guide to spacetime symmetries, Killing vectors, conserved currents, charges, horizon generators, and the limits of energy conservation in curved spacetime."
sidebar:
  label: "Killing Vectors and Conserved Quantities"
  order: 30
level: Graduate
status: "Polished draft"
source: "Wald 1984, chs. 3–4 and 11–12; Carroll 2004, chs. 3–5; Poisson 2004, chs. 3–4; Birrell and Davies 1982, ch. 3; Wald 1994"
topics:
  - Killing vectors
  - conserved currents
  - stress tensor
  - stationary spacetimes
  - Noether charges
canonicalTopics:
  - killing-vector
  - conserved-current
  - stress-tensor-current
  - stationary-spacetime
  - surface-gravity
researchStatus:
  established:
    - "Killing vectors encode exact spacetime symmetries and turn covariantly conserved stress tensors into conserved currents and charges."
  active:
    - "In nonstationary spacetimes, asymptotic regions, quantum anomalies, and gravitational theories, the definition of energy and symmetry charges requires additional structure."
---

## Summary

A Killing vector is the infinitesimal generator of an isometry: a flow that leaves the metric unchanged. In tensor language, a vector field $\xi^\mu$ is Killing when

$$
\nabla_{(\mu}\xi_{\nu)}=0.
$$

If the stress tensor is symmetric and covariantly conserved,

$$
\nabla_\mu T^{\mu\nu}=0,
$$

then every Killing vector gives a conserved current

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu,
\qquad
\nabla_\mu J^\mu=0.
$$

This is the curved-spacetime version of Noether's theorem for spacetime symmetries. The flat-space energy, momentum, and angular momentum currents are all special cases. The important difference is that a generic curved spacetime has no global translation symmetry, so there may be no globally conserved energy.

For QFT in curved spacetime, Killing vectors are the bridge between geometry and dynamics. A timelike Killing vector can define a preferred frequency, a Hamiltonian, a thermal equilibrium state, and a notion of positive energy. A horizon-generating Killing vector defines surface gravity and, in stationary black-hole spacetimes, the temperature of the Hawking state.

## Prerequisites

Read [Conventions and Notation](/spacetime-gravity-holography/conventions/), [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/), and [Causal Structure](/spacetime-gravity-holography/spacetime-gravity-toolkit/causal-structure/) first. You should know covariant derivatives, stress tensors, hypersurface integrals, and the basic idea that symmetries generate conserved currents.

The next page, [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/), uses Killing vectors to define Killing horizons and surface gravity.

## Core idea

In flat spacetime, Poincare symmetry gives energy, momentum, angular momentum, and boosts. In curved spacetime, these symmetries are usually absent. A conserved quantity exists only when the geometry supplies the corresponding symmetry or when an asymptotic region supplies an approximate or boundary symmetry.

The key mechanism is:

$$
\text{metric symmetry} + \text{stress-tensor conservation}
\Longrightarrow
\text{ordinary conserved current}.
$$

The metric symmetry is encoded by a Killing vector. Stress-tensor conservation is local and covariant. The resulting current has an ordinary divergence-free meaning, so it can be integrated over a hypersurface to define a charge.

This is why curved spacetime forces a conceptual upgrade. Local conservation,

$$
\nabla_\mu T^{\mu\nu}=0,
$$

does not by itself mean there is a conserved total energy. Energy conservation is tied to time-translation symmetry, and a generic spacetime has no such symmetry.

## Setup and conventions

We use mostly-minus signature and the curvature conventions of this volume. A vector field $\xi^\mu$ generates an infinitesimal diffeomorphism along its flow. The Lie derivative of the metric is

$$
(\mathcal L_\xi g)_{\mu\nu}
=\nabla_\mu\xi_\nu+\nabla_\nu\xi_\mu.
$$

A Killing vector satisfies

$$
\mathcal L_\xi g_{\mu\nu}=0,
$$

or equivalently

$$
\nabla_\mu\xi_\nu+\nabla_\nu\xi_\mu=0.
$$

The antisymmetric derivative

$$
\nabla_\mu\xi_\nu=-\nabla_\nu\xi_\mu
$$

is therefore the only nonzero first derivative of a Killing vector.

A spacetime with a timelike Killing vector is stationary. If the timelike Killing vector is also hypersurface-orthogonal, the spacetime is static. The distinction matters: a rotating black hole is stationary but not static outside the horizon.

## From Killing vectors to conserved currents

Let $T^{\mu\nu}$ be symmetric and covariantly conserved. Given a Killing vector $\xi^\mu$, define

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu.
$$

Then

$$
\nabla_\mu J^\mu
=(\nabla_\mu T^\mu{}_{\nu})\xi^\nu
+T^{\mu\nu}\nabla_\mu\xi_\nu.
$$

The first term vanishes by stress-tensor conservation. The second term vanishes because $T^{\mu\nu}$ is symmetric while $\nabla_\mu\xi_\nu$ is antisymmetric:

$$
T^{\mu\nu}\nabla_\mu\xi_\nu
=T^{\mu\nu}\nabla_{(\mu}\xi_{\nu)}=0.
$$

Therefore

$$
\nabla_\mu J^\mu=0.
$$

This proof is tiny but mighty. It is the reason stationary spacetimes have conserved energy currents and axisymmetric spacetimes have conserved angular-momentum currents.

## Charges on hypersurfaces

Let $\Sigma$ be a spacelike hypersurface with future-directed unit normal $n^\mu$. The charge associated with $J^\mu$ is

$$
Q_\xi[\Sigma]
=\int_\Sigma d\Sigma\,n_\mu J^\mu
=\int_\Sigma d\Sigma\,n_\mu T^\mu{}_{\nu}\xi^\nu.
$$

If $\nabla_\mu J^\mu=0$ and no flux escapes through the boundary of the spacetime region between two hypersurfaces, then

$$
Q_\xi[\Sigma_2]=Q_\xi[\Sigma_1].
$$

This is the covariant form of charge conservation. The phrase “no flux escapes” is not optional. If the region has a timelike boundary, null infinity, a horizon, or an AdS conformal boundary, the boundary flux must be included.

For a timelike Killing vector $\xi=\partial_t$, $Q_\xi$ is the energy associated with that time translation. For a rotational Killing vector $\psi=\partial_\phi$, $Q_\psi$ is an angular momentum, up to sign conventions fixed by how the stress tensor and normal are oriented.

## Flat-space examples

Minkowski spacetime has ten Killing vectors in four dimensions: four translations, three rotations, and three boosts. In Cartesian coordinates,

$$
ds^2=dt^2-dx^2-dy^2-dz^2.
$$

The time translation

$$
\xi=\partial_t
$$

gives energy. Spatial translations

$$
\xi=\partial_i
$$

give momentum. Rotations such as

$$
\psi=x\partial_y-y\partial_x
$$

give angular momentum. Boosts such as

$$
\beta=x\partial_t+t\partial_x
$$

give the conserved boost charges associated with Lorentz symmetry.

Curved-spacetime notation reduces to the familiar Noether currents in this limit. What changes in curved spacetime is not the logic of Noether's theorem; what changes is the availability of global symmetries.

## Stationary spacetimes and positive frequency

A stationary spacetime has a timelike Killing vector $\xi^\mu$ in the region of interest. For a field mode $u(x)$, one can define frequency by

$$
\mathcal L_\xi u=-i\omega u.
$$

When $\xi^\mu$ is globally timelike and the state is compatible with the symmetry, positive frequency can be tied to $\omega>0$. This is the curved-spacetime substitute for the flat-space split into creation and annihilation operators.

But the phrase “globally timelike” matters. In rotating spacetimes, the natural stationary Killing vector may become spacelike in an ergoregion. Then the energy associated with that Killing field can be negative for some classical modes. This is the geometric seed of superradiance.

In nonstationary spacetimes, there may be no preferred positive-frequency split at all. This is why particle creation in cosmology is not a paradox: the local field equation remains well-defined, but the global particle basis changes.

## Killing horizons and horizon generators

A Killing horizon is a null hypersurface whose null generators are orbits of a Killing vector $\chi^\mu$. On the horizon,

$$
\chi^2=g_{\mu\nu}\chi^\mu\chi^\nu=0.
$$

The surface gravity $\kappa$ is defined by

$$
\chi^\nu\nabla_\nu\chi^\mu=\kappa\chi^\mu
\qquad
\text{on the horizon}.
$$

For a static black hole, $\chi=\partial_t$ with normalization fixed at infinity. For a rotating stationary black hole,

$$
\chi=\partial_t+\Omega_H\partial_\phi,
$$

where $\Omega_H$ is the angular velocity of the horizon. The corresponding thermodynamic combination in the first law is built from the charge generated by $\chi$, not by $\partial_t$ alone.

This is the geometric reason that black-hole thermodynamics involves

$$
dM=T_HdS+\Omega_HdJ+\Phi_HdQ.
$$

The horizon generator combines time translation with rotations and gauge transformations in precisely the way that remains null on the horizon.

## Conformal Killing vectors

A conformal Killing vector preserves the metric only up to a local Weyl rescaling:

$$
\mathcal L_\xi g_{\mu\nu}=2\sigma(x)g_{\mu\nu}.
$$

Equivalently,

$$
\nabla_\mu\xi_\nu+\nabla_\nu\xi_\mu
=2\sigma g_{\mu\nu}.
$$

If the stress tensor is conserved and traceless, then

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu
$$

is also conserved:

$$
\nabla_\mu J^\mu
=\sigma T^\mu{}_{\mu}=0.
$$

This is the curved-geometric version of the statement that CFTs have currents associated with conformal transformations. Quantum mechanically, trace anomalies can spoil the tracelessness of $T^\mu{}_{\mu}$ on curved backgrounds, so conformal symmetry must be discussed with the anomaly included.

## Approximate and asymptotic symmetries

Many important spacetimes do not have exact Killing vectors everywhere but have approximate or asymptotic symmetries. Asymptotically flat spacetimes have Poincare-like charges at spatial or null infinity under suitable falloff conditions. Asymptotically AdS spacetimes have boundary charges associated with symmetries of the boundary metric.

These charges are not obtained by simply integrating the matter stress tensor over a finite hypersurface. In gravity, the metric itself carries energy and momentum. Defining gravitational charges requires boundary terms, constraints, and careful falloff conditions.

For this volume, the practical rule is:

$$
\text{matter on fixed background: use }T_{\mu\nu}\xi^\nu;
\qquad
\text{dynamical gravity: include boundary gravitational charges.}
$$

The second half of this rule becomes central in gravitational EFT, black-hole thermodynamics, and holographic stress tensors.

## Common pitfalls

**Mistaking local stress-tensor conservation for global energy conservation.** The equation $\nabla_\mu T^{\mu\nu}=0$ is always local. A conserved energy needs a timelike symmetry or an appropriate asymptotic structure.

**Ignoring boundary flux.** A current can be divergence-free while charge in a region changes because flux crosses its boundary.

**Forgetting normalization of a Killing vector.** Surface gravity and energy depend on the normalization of the time-translation generator. In asymptotically flat spacetimes, the usual normalization is fixed at infinity.

**Assuming stationary means static.** Stationary means time-translation symmetry. Static also requires no rotation in the sense of hypersurface orthogonality.

**Using positive frequency without asking: positive with respect to what?** Frequency is defined relative to a time flow. Different time flows can define different particles.

**Treating conformal Killing vectors like ordinary Killing vectors when the trace anomaly matters.** Quantum trace anomalies turn classical conformal conservation laws into anomalous Ward identities.

## Relations to other pages

This page sits between [Causal Structure](/spacetime-gravity-holography/spacetime-gravity-toolkit/causal-structure/) and [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/). Causal structure explains what can influence what; Killing vectors explain when the geometry has symmetry; horizons use special Killing vectors to define surface gravity and temperature.

The first QFT page, [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/), uses Killing time to discuss modes and positive frequency. Later black-hole pages use horizon generators and conserved charges to formulate the first law and Hawking temperature.

## Research status

The material on exact Killing vectors and stress-tensor currents is standard. The subtleties are not in the local proof; they are in the global and quantum interpretation.

Active issues include gravitational charge definitions at boundaries, asymptotic symmetry algebras, soft charges, horizon charges, quantum anomalies, and the role of modular flow as a generalized symmetry-like time evolution for subregion algebras. These are refinements of the same basic lesson: a conserved quantity is only as well-defined as the symmetry and boundary conditions that support it.

## Exercises

### Exercise 1: Prove current conservation

Let $T^{\mu\nu}=T^{\nu\mu}$, $\nabla_\mu T^{\mu\nu}=0$, and $\xi^\mu$ obey $\nabla_{(\mu}\xi_{\nu)}=0$. Show that $J^\mu=T^\mu{}_{\nu}\xi^\nu$ is conserved.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\nabla_\mu J^\mu
=(\nabla_\mu T^\mu{}_{\nu})\xi^\nu
+T^\mu{}_{\nu}\nabla_\mu\xi^\nu.
$$

The first term vanishes. The second term is

$$
T^{\mu\nu}\nabla_\mu\xi_\nu
=T^{\mu\nu}\nabla_{(\mu}\xi_{\nu)}=0,
$$

because $T^{\mu\nu}$ is symmetric and $\xi^\mu$ is Killing. Thus $\nabla_\mu J^\mu=0$.

</details>

### Exercise 2: Rotational Killing vector in flat space

In flat space with coordinates $(t,x,y,z)$, show that

$$
\psi=x\partial_y-y\partial_x
$$

is a Killing vector.

<details><summary><strong>Solution</strong></summary>

The metric components are constant, so the Killing equation reduces to

$$
\partial_\mu\psi_\nu+\partial_\nu\psi_\mu=0.
$$

The nonzero components are $\psi^x=-y$ and $\psi^y=x$. Lowering spatial indices with the mostly-minus metric gives $\psi_x=y$ and $\psi_y=-x$. Then

$$
\partial_x\psi_y=-1,
\qquad
\partial_y\psi_x=1,
$$

so $\partial_x\psi_y+\partial_y\psi_x=0$. All other symmetric derivatives vanish. Hence $\psi$ is Killing.

</details>

### Exercise 3: Conformal Killing current

Let $\xi^\mu$ obey

$$
\nabla_\mu\xi_\nu+\nabla_\nu\xi_\mu=2\sigma g_{\mu\nu}.
$$

Show that $J^\mu=T^\mu{}_{\nu}\xi^\nu$ is conserved if $T^{\mu\nu}$ is symmetric, conserved, and traceless.

<details><summary><strong>Solution</strong></summary>

As before,

$$
\nabla_\mu J^\mu=T^{\mu\nu}\nabla_\mu\xi_\nu.
$$

Only the symmetric part contributes:

$$
T^{\mu\nu}\nabla_\mu\xi_\nu
=T^{\mu\nu}\nabla_{(\mu}\xi_{\nu)}.
$$

The conformal Killing equation gives $\nabla_{(\mu}\xi_{\nu)}=\sigma g_{\mu\nu}$, hence

$$
\nabla_\mu J^\mu=\sigma T^\mu{}_{\mu}=0.
$$

</details>

### Exercise 4: Why expanding universes do not conserve particle energy

A spatially flat expanding universe has metric

$$
ds^2=dt^2-a(t)^2d\mathbf x^2.
$$

Explain why there is generally no conserved energy associated with $\partial_t$.

<details><summary><strong>Solution</strong></summary>

The vector $\partial_t$ is Killing only if the metric is independent of $t$. Here the spatial metric components are $g_{ij}=-a(t)^2\delta_{ij}$, so

$$
\partial_t g_{ij}=-2a\dot a\,\delta_{ij}.
$$

Unless $\dot a=0$, the Lie derivative $\mathcal L_{\partial_t}g_{\mu\nu}$ is nonzero. Therefore $\partial_t$ is not a time-translation symmetry and does not generate a conserved energy. Local stress-tensor conservation still holds, but there is no global time-translation charge of the flat-space kind.

</details>

## References

- R. M. Wald, *General Relativity*, University of Chicago Press, 1984.
- S. M. Carroll, *Spacetime and Geometry*, Addison-Wesley, 2004.
- E. Poisson, *A Relativist's Toolkit*, Cambridge University Press, 2004.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- V. Iyer and R. M. Wald, “Some properties of the Noether charge and a proposal for dynamical black hole entropy,” *Physical Review D* **50** (1994) 846.
- A. Ashtekar and B. Krishnan, “Isolated and dynamical horizons and their applications,” *Living Reviews in Relativity* **7** (2004) 10.

## Version history

- 2026-07-01: Added a polished toolkit page on Killing vectors, conserved currents, charges, and their QFT uses.
