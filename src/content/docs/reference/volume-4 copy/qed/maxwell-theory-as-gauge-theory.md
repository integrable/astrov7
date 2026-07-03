---
title: "Maxwell Theory as Gauge Theory"
description: "Explains Maxwell electrodynamics as the classical U(1) gauge theory of a massless Abelian connection, including field strength, equations of motion, gauge redundancy, currents, and physical polarizations."
sidebar:
  label: "Maxwell as Gauge Theory"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§54–57; Schwartz §8; Coleman lectures on electromagnetic interactions and Faddeev–Popov; Weinberg Vol. I, QED chapters; Zee Parts II–III."
topics:
  - Maxwell theory
  - Abelian gauge theory
  - electromagnetic field strength
  - gauge redundancy
  - photon polarizations
canonicalTopics:
  - maxwell-theory
  - abelian-gauge-theory
  - electromagnetic-field-strength
researchStatus:
  established:
    - "Classical Maxwell theory is the canonical free U(1) gauge theory and the starting point for quantum electrodynamics."
  active:
    - "The infrared, boundary, and asymptotic-symmetry structure of Maxwell theory continues to be an active interface between gauge theory, scattering theory, and gravity."
---

## Summary

Maxwell theory is the free Abelian gauge theory of a one-form potential $A_\mu$. Its gauge-invariant local field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

and its Lorentzian action in the conventions of this volume is

$$
S_{\mathrm{Maxwell}}[A]
=
-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

The key point is that $A_\mu$ contains more variables than the photon has physical degrees of freedom. The transformation

$$
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\lambda(x)
$$

changes the potential but leaves $F_{\mu\nu}$ unchanged. Gauge symmetry is therefore a redundancy in the description, not an ordinary physical symmetry acting faithfully on distinct states.

Maxwell theory matters because every later gauge theory is a deformation of this prototype. Scalar QED and spinor QED add charged matter. Yang–Mills theory makes the gauge group non-Abelian, so the field strength itself becomes nonlinear. Electroweak theory mixes several Abelian and non-Abelian gauge fields through spontaneous symmetry breaking. Tiny seed, very large tree.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Maxwell theory organizes gauge potentials, gauge redundancy, field strength, equations of motion, and physical photon data.](/figures/gauge-theories-standard-model/maxwell-gauge-structure.svg)

<figcaption>

Maxwell theory separates gauge-dependent potential data from gauge-invariant field-strength data. The potential $A_\mu$ is the variable used for locality and coupling to charged matter; $F_{\mu\nu}$ contains the local electromagnetic fields; gauge fixing chooses representatives without changing physical observables.

</figcaption>
</figure>

## Prerequisites

You should know the Gauge Principle chapter through [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/), especially the distinction between gauge redundancy and physical symmetry. You should also know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), including the mostly-minus metric, Fourier phase, and Abelian convention

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

This page is mostly classical. Quantization, path-integral gauge fixing, photon propagators, and Ward identities enter later in the QED chapter.

## Core idea

The electromagnetic field can be described locally by a potential $A_\mu$, but the potential is not itself unique. If

$$
A_\mu' = A_\mu+\partial_\mu\lambda,
$$

then

$$
F'_{\mu\nu}
=
\partial_\mu A'_\nu-\partial_\nu A'_\mu
=
F_{\mu\nu}
+\partial_\mu\partial_\nu\lambda
-\partial_\nu\partial_\mu\lambda
=
F_{\mu\nu}.
$$

The equality of mixed partial derivatives is the Abelian miracle. It is the reason the field strength is gauge invariant and why Maxwell theory has no photon self-interaction in its classical free action.

The potential $A_\mu$ is still indispensable. It is the object that couples locally to charged matter through $D_\mu$, it makes Lorentz invariance and locality manifest, and it is the natural connection one-form in the geometric view of gauge theory. The field strength $F_{\mu\nu}$ is the local curvature of that connection.

So Maxwell theory is not merely a theory of two vector fields $\mathbf E$ and $\mathbf B$. It is the first example of the pattern

$$
\text{connection }A
\quad\longrightarrow\quad
\text{curvature }F=dA
\quad\longrightarrow\quad
\text{gauge-invariant dynamics}.
$$

## Setup and conventions

We use

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
\epsilon^{0123}=+1.
$$

The Abelian field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The electric and magnetic fields are defined by

$$
E^i=F^{i0},
\qquad
F^{ij}=-\epsilon^{ijk}B^k.
$$

With these definitions,

$$
-\frac14F_{\mu\nu}F^{\mu\nu}
=
\frac12(\mathbf E^2-\mathbf B^2).
$$

If $A^\mu=(\Phi,\mathbf A)$, then $A_\mu=(\Phi,-\mathbf A)$ and

$$
\mathbf E=-\nabla\Phi-\partial_t\mathbf A,
\qquad
\mathbf B=\nabla\times\mathbf A.
$$

The gauge transformation may be written either as

$$
A_\mu\mapsto A_\mu+\partial_\mu\lambda
$$

or, when the coupling is kept in the transformation parameter,

$$
A_\mu\mapsto A_\mu+e^{-1}\partial_\mu\alpha.
$$

The first form is used on this page. The second is useful when a charge-$Q$ matter field transforms as $\psi\mapsto e^{-iQ\alpha}\psi$ and $D_\mu=\partial_\mu+ieQ A_\mu$.

## The Maxwell action and equations of motion

The free Maxwell action is

$$
S[A]=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

Varying the potential gives

$$
\delta F_{\mu\nu}
=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu.
$$

Using antisymmetry of $F^{\mu\nu}$,

$$
\delta S
=
-\int d^4x\,F^{\mu\nu}\partial_\mu\delta A_\nu
=
\int d^4x\,(\partial_\mu F^{\mu\nu})\delta A_\nu,
$$

up to a boundary term. The Euler–Lagrange equation is therefore

$$
\partial_\mu F^{\mu\nu}=0.
$$

With an external conserved current $J^\mu$, the source-coupled action is

$$
S[A;J]
=
\int d^4x\left[-\frac14F_{\mu\nu}F^{\mu\nu}-J^\mu A_\mu\right],
$$

and the equation of motion becomes

$$
\partial_\mu F^{\mu\nu}=J^\nu.
$$

In three-vector language this contains the two inhomogeneous Maxwell equations,

$$
\nabla\cdot\mathbf E=\rho,
\qquad
\nabla\times\mathbf B-\partial_t\mathbf E=\mathbf J,
$$

where $J^\mu=(\rho,\mathbf J)$.

## The Bianchi identity

The remaining two Maxwell equations do not come from varying the action. They follow from the definition $F=dA$. In components,

$$
\partial_\rho F_{\mu\nu}
+\partial_\mu F_{\nu\rho}
+\partial_\nu F_{\rho\mu}=0.
$$

Equivalently,

$$
\partial_\mu \widetilde F^{\mu\nu}=0,
\qquad
\widetilde F^{\mu\nu}
=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

In three-vector notation these are

$$
\nabla\cdot\mathbf B=0,
\qquad
\nabla\times\mathbf E+\partial_t\mathbf B=0.
$$

The conceptual split is important:

| Equation | Origin | Meaning |
|---|---|---|
| $\partial_\mu F^{\mu\nu}=J^\nu$ | Euler–Lagrange equation | Dynamics and sources |
| $\partial_\mu\widetilde F^{\mu\nu}=0$ | Definition $F=dA$ | No magnetic monopoles in the globally defined potential description |

Magnetic monopoles, compact gauge fields, and nontrivial bundles modify the global interpretation of the Bianchi identity. Locally the equation still says that $F$ is closed away from magnetic sources.

## Current conservation from gauge invariance

The source term is gauge invariant only if the external current is conserved. Under

$$
A_\mu\mapsto A_\mu+\partial_\mu\lambda,
$$

the source action changes by

$$
\delta S_J
=
-\int d^4x\,J^\mu\partial_\mu\lambda
=
\int d^4x\,\lambda\,\partial_\mu J^\mu,
$$

again up to a boundary term. Thus gauge invariance for arbitrary $\lambda(x)$ requires

$$
\partial_\mu J^\mu=0.
$$

The same condition follows from the equation of motion because

$$
\partial_\nu\partial_\mu F^{\mu\nu}=0
$$

identically: the derivatives are symmetric in $(\mu,\nu)$ while $F^{\mu\nu}$ is antisymmetric. If the left-hand side of the Maxwell equation is identically conserved, the source on the right-hand side must be conserved too.

When the current comes from dynamical charged matter, this conservation law is not an optional add-on. It is the classical ancestor of the Ward identities of QED.

## Gauge redundancy and degrees of freedom

A four-vector $A_\mu$ has four components. A massless photon has two physical polarizations. Maxwell theory gets from four to two by constraints and gauge redundancy.

In the source-free theory, the equation of motion can be written as

$$
\Box A^\nu-\partial^\nu(\partial_\mu A^\mu)=0.
$$

A plane-wave potential

$$
A_\mu(x)=\varepsilon_\mu(k)e^{-ik\cdot x}
$$

obeys

$$
k^2\varepsilon^\nu-k^\nu(k\cdot\varepsilon)=0.
$$

For radiation modes, $k^2=0$. Gauge transformations shift the polarization by

$$
\varepsilon_\mu\mapsto \varepsilon_\mu+i k_\mu \lambda(k),
$$

up to the Fourier convention for $\lambda$. A polarization proportional to $k_\mu$ is pure gauge and produces $F_{\mu\nu}=0$.

After imposing a gauge condition and quotienting by residual gauge transformations, only two transverse photon polarizations remain. This is the classical counterpart of the quantum statement that a photon has helicity $+1$ or $-1$, not four independent Lorentz-vector polarizations.

## Useful gauge choices

Gauge fixing chooses one representative from each gauge orbit, at least locally. It is a choice of coordinates on redundant configuration space, not a physical restriction on nature.

Common choices include:

| Gauge choice | Condition | Typical use |
|---|---|---|
| Lorenz gauge | $\partial_\mu A^\mu=0$ | Relativistic classical theory and covariant quantization. |
| Feynman gauge | covariant gauge with $\xi=1$ after adding $-\frac{1}{2\xi}(\partial\cdot A)^2$ | Simplest photon propagator in perturbation theory. |
| Landau gauge | covariant gauge with $\xi=0$ | Transverse propagator and some renormalization arguments. |
| Coulomb gauge | $\nabla\cdot\mathbf A=0$ | Separating instantaneous Coulomb fields from transverse radiation. |
| Temporal gauge | $A_0=0$ | Hamiltonian and classical radiation problems, with residual constraints. |

The Lorenz condition is named after Ludvig Lorenz, not Hendrik Lorentz. Yes, the universe chose violence.

## Why a photon mass is not allowed here

The Proca mass term

$$
\frac12m^2A_\mu A^\mu
$$

is not invariant under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$. Adding it changes the theory from Maxwell gauge theory to a massive vector theory with three physical polarizations.

This does not mean vector bosons can never be massive. The electroweak $W^\pm$ and $Z$ bosons become massive through the Higgs mechanism, where gauge redundancy remains present but is realized in a less transparent set of variables. That story is different from simply adding $m^2A^2/2$ to Maxwell theory.

For the photon in ordinary QED, the masslessness of the gauge boson is protected by gauge invariance. Quantum corrections cannot generate a local photon mass term without violating the Ward identity.

## Stress tensor and energy density

The symmetric gauge-invariant stress tensor of Maxwell theory is

$$
T^{\mu\nu}
=
-F^{\mu\rho}F^{\nu}{}_{\rho}
+\frac14\eta^{\mu\nu}F_{\rho\sigma}F^{\rho\sigma}.
$$

With the conventions above,

$$
T^{00}=\frac12(\mathbf E^2+\mathbf B^2),
$$

which is positive. This is a useful sign check: if a convention gives the Maxwell Lagrangian density $\frac12(\mathbf E^2-\mathbf B^2)$ but energy density $\frac12(\mathbf E^2+\mathbf B^2)$, the signs are behaving.

The classical stress tensor is traceless in four spacetime dimensions:

$$
T^\mu{}_\mu=0.
$$

Quantum mechanically, QED with charged matter develops a scale anomaly tied to charge renormalization. Pure free Maxwell theory remains conformal in four dimensions.

## Quantization preview

The free Maxwell action has a degenerate kinetic operator. In momentum space, the quadratic action contains the operator

$$
K^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}+k^\mu k^\nu.
$$

It has a null direction:

$$
K^{\mu\nu}(k)k_\nu=0.
$$

That null direction is the infinitesimal gauge redundancy. Because of it, $K^{\mu\nu}$ cannot be inverted until we fix gauge. Adding the covariant gauge-fixing term

$$
\mathcal L_{\mathrm{gf}}
=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2
$$

makes the kinetic operator invertible and leads to the photon propagator developed later in the chapter.

In Abelian QED, Faddeev–Popov ghosts decouple in ordinary covariant gauges because the gauge transformation is linear and field-independent. In non-Abelian Yang–Mills theory, the corresponding ghosts interact and become essential.

## Common pitfalls

**Thinking $A_\mu$ is directly observable.** The local potential is gauge-dependent. The local gauge-invariant field strength $F_{\mu\nu}$ and suitable line operators are physical; $A_\mu$ is a redundant but useful coordinate.

**Forgetting the Bianchi identity.** Half of Maxwell's equations are identities once $F=dA$. They do not follow from varying the Maxwell action.

**Calling Lorenz gauge Lorentz gauge.** The condition $\partial_\mu A^\mu=0$ is Lorentz covariant, but the historical name is Lorenz gauge. Both spellings appear in the wild; know the distinction and then move on with your life.

**Adding a photon mass casually.** A term $m^2A_\mu A^\mu/2$ breaks the $U(1)$ gauge redundancy. Massive vector fields and Higgsed gauge fields are related but not identical presentations.

**Counting four photon polarizations.** Covariant quantization uses four components plus gauge fixing and constraints. Physical photons have two transverse polarizations.

**Assuming gauge fixing changes physics.** Proper gauge fixing changes the description and propagators, not gauge-invariant observables.

## Relations to other pages

- [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) explains $F=dA$ as the Abelian curvature of a connection.
- [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/) explains why $F_{\mu\nu}$, fluxes, and Wilson lines are better observables than $A_\mu$ itself.
- [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/) adds the simplest dynamical charged matter and shows how the covariant derivative generates both current and seagull couplings.
- Later pages on Gauge Fixing in QED and Photon Propagator turn the classical redundancy into the practical machinery of perturbative QED.
- The Yang–Mills chapter generalizes $F=dA$ to a non-Abelian curvature with an $A\wedge A$ term and gauge-boson self-interactions.

## Research status

Classical Maxwell theory and perturbative free-photon quantization are established. The subtle parts are not about the local equations themselves but about global and infrared structure: large gauge transformations, boundary charges, soft photons, memory effects, charged-sector dressings, and the correct definition of asymptotic charged states.

Those issues do not invalidate textbook QED. They clarify what its physical observables really are when massless gauge bosons and long-range fields are present.

## Exercises

### Exercise 1: Gauge invariance of the field strength

Show that $F_{\mu\nu}$ is invariant under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\begin{aligned}
F'_{\mu\nu}
&=\partial_\mu(A_\nu+\partial_\nu\lambda)
-\partial_\nu(A_\mu+\partial_\mu\lambda)\\
&=F_{\mu\nu}
+\partial_\mu\partial_\nu\lambda
-\partial_\nu\partial_\mu\lambda
=F_{\mu\nu}.
\end{aligned}
$$

The last equality uses commuting partial derivatives.

</details>

### Exercise 2: Derive the sourced Maxwell equation

Starting from

$$
S=\int d^4x\left[-\frac14F_{\mu\nu}F^{\mu\nu}-J^\mu A_\mu\right],
$$

vary $A_\mu$ and derive the equation of motion.

<details>
<summary><strong>Solution</strong></summary>

The gauge-field variation is

$$
\delta S_{\mathrm{gauge}}
=
-\int d^4x\,F^{\mu\nu}\partial_\mu\delta A_\nu
=
\int d^4x\,(\partial_\mu F^{\mu\nu})\delta A_\nu,
$$

up to a boundary term. The source variation is

$$
\delta S_J=-\int d^4x\,J^\nu\delta A_\nu.
$$

Thus

$$
\delta S=\int d^4x\,(\partial_\mu F^{\mu\nu}-J^\nu)\delta A_\nu,
$$

and the Euler–Lagrange equation is

$$
\partial_\mu F^{\mu\nu}=J^\nu.
$$

</details>

### Exercise 3: Conservation of the source

Use gauge invariance of the source term to show that $\partial_\mu J^\mu=0$.

<details>
<summary><strong>Solution</strong></summary>

Under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$,

$$
\delta S_J
=
-\int d^4x\,J^\mu\partial_\mu\lambda
=
\int d^4x\,\lambda\,\partial_\mu J^\mu,
$$

up to a boundary term. Gauge invariance for arbitrary $\lambda(x)$ requires

$$
\partial_\mu J^\mu=0.
$$

</details>

### Exercise 4: Physical polarizations

For a source-free plane wave with $k^2=0$, explain why a polarization proportional to $k_\mu$ is pure gauge.

<details>
<summary><strong>Solution</strong></summary>

Take

$$
A_\mu(x)=\varepsilon_\mu e^{-ik\cdot x}.
$$

A gauge transformation with $\lambda(x)=c e^{-ik\cdot x}$ shifts

$$
A_\mu\mapsto A_\mu-ic k_\mu e^{-ik\cdot x},
$$

so the polarization shifts by a multiple of $k_\mu$. If $\varepsilon_\mu\propto k_\mu$, then

$$
F_{\mu\nu}\propto k_\mu k_\nu-k_\nu k_\mu=0.
$$

Such a mode carries no electromagnetic field strength and is pure gauge.

</details>

### Exercise 5: The Maxwell kinetic operator has a zero mode

Show that the quadratic Maxwell operator in momentum space,

$$
K^{\mu\nu}(k)=-k^2\eta^{\mu\nu}+k^\mu k^\nu,
$$

satisfies $K^{\mu\nu}k_\nu=0$.

<details>
<summary><strong>Solution</strong></summary>

Contract with $k_\nu$:

$$
K^{\mu\nu}k_\nu
=
-k^2 k^\mu+k^\mu(k^\nu k_\nu)
=
-k^2k^\mu+k^\mu k^2=0.
$$

This zero mode is the momentum-space imprint of gauge redundancy. It is why the free photon kinetic operator cannot be inverted before gauge fixing.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§54–57, for Maxwell equations, Coulomb gauge, LSZ for photons, and the path integral for photons.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §8, for spin-1 fields, gauge invariance, covariant derivatives, quantization, and the photon propagator.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the gauge-invariance and QED chapters, for a compact physical explanation of why the photon is described by a gauge field.

### Deeper references

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on electromagnetic interactions, massless electrodynamics, and the Faddeev–Popov prescription.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for the particle-theoretic construction of massless spin-one fields and QED.
- J. D. Jackson, *Classical Electrodynamics*, for the classical Maxwell theory and gauge choices from the electromagnetic side.

## Version history

- **2026-06-17:** Initial polished draft for the Abelian Gauge Theory and QED chapter.
