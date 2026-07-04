---
title: "Lorentzian Geometry for QFT"
description: "A QFT-oriented introduction to Lorentzian manifolds, covariant derivatives, curvature, causal structure, invariant actions, and the geometric data seen by quantum fields."
sidebar:
  label: "Lorentzian Geometry for QFT"
  order: 10
level: Graduate
status: "Polished draft"
source: "Wald 1984, chs. 2–4; Hawking and Ellis 1973, chs. 2–6; Carroll 2004, chs. 2–4; Poisson 2004, chs. 2–3; Nakahara 2018, chs. 5 and 7; Frankel 2011, chs. 2–3 and 9–11; Birrell and Davies 1982, ch. 3"
topics:
  - Lorentzian geometry
  - curved spacetime
  - covariant derivatives
  - causal structure
  - curvature
canonicalTopics:
  - lorentzian-manifold
  - curved-spacetime-qft
  - levi-civita-connection
  - causal-structure
  - curvature-tensor
researchStatus:
  established:
    - "Lorentzian geometry is the standard geometric language for classical spacetime backgrounds and for QFT coupled to a background metric."
  active:
    - "The geometric framework is settled, but the quantum meaning of observables, states, and locality becomes subtler on nonstationary spacetimes, near horizons, and when gravity is dynamical."
---

## Summary

Lorentzian geometry is the language of spacetime backgrounds. A QFT on a fixed curved spacetime is not merely a flat-space QFT written in fancy coordinates: the metric determines causal cones, invariant volumes, covariant derivatives, curvature couplings, conserved currents, and the distinction between local fields and global particles.

A Lorentzian spacetime is a smooth manifold $M$ equipped with a metric $g_{\mu\nu}$ of signature

$$
(+,-,\ldots,-).
$$

At each point, the metric classifies tangent vectors as

$$
\begin{array}{ccl}
\text{timelike} &:& g_{\mu\nu}v^\mu v^\nu>0,\\
\text{null} &:& g_{\mu\nu}v^\mu v^\nu=0,\\
\text{spacelike} &:& g_{\mu\nu}v^\mu v^\nu<0.
\end{array}
$$

Those light cones are physical. They determine which operator commutators vanish, which hypersurfaces can carry initial data, when a Hamiltonian description exists, and why particle number is usually not a coordinate-independent concept in curved spacetime.

The basic differential operators are built from the Levi-Civita connection,

$$
\Gamma^\rho{}_{\mu\nu}
=
\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\mu\sigma}
-\partial_\sigma g_{\mu\nu}
\right),
$$

and curvature is fixed by

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

The most important moral is that QFT is local, while particles are usually global. Local field equations and short-distance singularities only need the geometry near a point. A unique vacuum or particle basis usually needs more: a timelike symmetry, an asymptotic region, or a preferred state prescription.

## Prerequisites

You should know the volume [Conventions and Notation](/spacetime-gravity-holography/conventions/) and the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/). You should be comfortable with special relativity, tensors, the action principle, Noether currents, and the flat-space Klein–Gordon field.

Differential forms, fiber bundles, and spin geometry are helpful but not required for a first pass. This page introduces only the geometry needed to begin QFT in curved spacetime.

## Core idea

A QFT asks spacetime for several pieces of data:

| Geometric data | QFT use |
|---|---|
| Smooth manifold $M$ | The arena on which fields are defined. |
| Lorentzian metric $g_{\mu\nu}$ | Causal cones, distances, volume measure, wave operator. |
| Time orientation | Distinguishes future from past. |
| Connection $\nabla$ | Differentiates tensors and spinors covariantly. |
| Curvature tensors | Allow local curvature couplings and enter anomalies. |
| Boundary or asymptotic structure | Defines charges, fluxes, boundary conditions, and holographic sources. |
| Choice of state | Replaces the flat-space vacuum when no global Poincare symmetry exists. |

The first five items are local geometric structure. The last two are where many physics subtleties enter. You can write a local scalar field equation on almost any smooth Lorentzian manifold. You cannot always define a unique vacuum, a preferred particle number, or an S-matrix.

## Setup and conventions

Throughout this page, $D$ denotes spacetime dimension. Curved spacetime indices are Greek,

$$
\mu,\nu,\rho,\sigma=0,1,\ldots,D-1,
$$

and local Lorentz indices are Latin,

$$
a,b,c,d=0,1,\ldots,D-1.
$$

The signature is mostly-minus:

$$
\eta_{ab}=\operatorname{diag}(+,-,\ldots,-).
$$

The invariant volume is

$$
d\mathrm{vol}_g=d^Dx\sqrt{|g|},
\qquad
|g|=|\det g_{\mu\nu}|.
$$

Curvature follows the convention

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma,
\qquad
R_{\mu\nu}=R^\rho{}_{\mu\rho\nu}.
$$

These conventions match the volume conventions page. If you learned general relativity with mostly-plus signature or the opposite Riemann sign, translate before comparing formulas.

## Coordinates and tensors

A spacetime manifold $M$ is a space that locally looks like $\mathbb R^D$. A coordinate chart assigns labels $x^\mu$ to points in some patch, but the labels are not physical observables by themselves.

A scalar field is a coordinate-independent function

$$
\phi:M\to\mathbb R.
$$

In coordinates, it is represented by $\phi(x)$. Under a coordinate change $x^\mu\to x'^\mu(x)$, the same scalar is described by

$$
\phi'(x')=\phi(x).
$$

A vector field is a section of the tangent bundle. Its components transform as

$$
V'^{\mu}(x')
=
\frac{\partial x'^\mu}{\partial x^\nu}V^\nu(x).
$$

A covector transforms oppositely:

$$
\omega'_\mu(x')
=
\frac{\partial x^\nu}{\partial x'^\mu}\omega_\nu(x).
$$

The QFT lesson is simple: coordinates are bookkeeping. Local fields and operator equations should be stated tensorially if they are meant to survive arbitrary coordinate changes.

## The metric and light cones

The Lorentzian metric assigns an inner product to tangent vectors:

$$
v\cdot w=g_{\mu\nu}v^\mu w^\nu.
$$

At each point, the equation

$$
g_{\mu\nu}v^\mu v^\nu=0
$$

defines the local light cone. This cone is the curved-spacetime replacement of the flat-space condition $t^2-\mathbf x^2=0$.

For timelike curves, the proper time is

$$
d\tau=\sqrt{g_{\mu\nu}dx^\mu dx^\nu}.
$$

For spacelike curves, the proper length is

$$
d\ell=\sqrt{-g_{\mu\nu}dx^\mu dx^\nu}.
$$

A time orientation is a continuous choice of future light cone. Without it, the words future and past are not globally meaningful.

In local QFT, causality is expressed by microcausality: bosonic local observables commute at spacelike separation, and fermionic fields anticommute at spacelike separation after accounting for spin-statistics. In curved spacetime, “spacelike separation” is determined by the causal structure of $g_{\mu\nu}$, not by coordinate distance.

## Covariant differentiation

Partial derivatives of scalars are tensors:

$$
\nabla_\mu\phi=\partial_\mu\phi.
$$

Partial derivatives of vector components are not tensors. The covariant derivative fixes this by adding the connection:

$$
\nabla_\mu V^\nu
=\partial_\mu V^\nu+\Gamma^\nu{}_{\mu\rho}V^\rho.
$$

For a covector,

$$
\nabla_\mu\omega_\nu
=\partial_\mu\omega_\nu-\Gamma^\rho{}_{\mu\nu}\omega_\rho.
$$

The Levi-Civita connection is the unique connection satisfying

$$
\nabla_\rho g_{\mu\nu}=0,
\qquad
\Gamma^\rho{}_{\mu\nu}=\Gamma^\rho{}_{\nu\mu}.
$$

The divergence of a vector has the useful form

$$
\nabla_\mu V^\mu
=
\frac{1}{\sqrt{|g|}}
\partial_\mu\left(\sqrt{|g|}V^\mu\right).
$$

This identity is what makes integration by parts look familiar:

$$
\int_M d^Dx\sqrt{|g|}\,\nabla_\mu V^\mu
=
\int_{\partial M} d^{D-1}y\sqrt{|h|}\,n_\mu V^\mu,
$$

up to the orientation and causal character of the boundary normal.

## Curvature

Curvature measures the failure of covariant derivatives to commute. For a vector,

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

For a covector,

$$
[\nabla_\mu,\nabla_\nu]\omega_\rho
=-R^\sigma{}_{\rho\mu\nu}\omega_\sigma.
$$

The Riemann tensor is

$$
R^\rho{}_{\sigma\mu\nu}
=
\partial_\mu\Gamma^\rho{}_{\nu\sigma}
-\partial_\nu\Gamma^\rho{}_{\mu\sigma}
+\Gamma^\rho{}_{\mu\lambda}\Gamma^\lambda{}_{\nu\sigma}
-\Gamma^\rho{}_{\nu\lambda}\Gamma^\lambda{}_{\mu\sigma}.
$$

The contractions most often used in QFT and gravity are

$$
R_{\mu\nu}=R^\rho{}_{\mu\rho\nu},
\qquad
R=g^{\mu\nu}R_{\mu\nu},
\qquad
G_{\mu\nu}=R_{\mu\nu}-\frac12Rg_{\mu\nu}.
$$

The scalar curvature $R$ is a local scalar of mass dimension two. Therefore it can appear in local effective actions. For a scalar field, the term $\xi R\phi^2$ is just as local as $m^2\phi^2$; it is not an exotic quantum-gravity correction.

At any point $p$, one can choose local inertial coordinates such that

$$
g_{\mu\nu}(p)=\eta_{\mu\nu},
\qquad
\partial_\rho g_{\mu\nu}(p)=0.
$$

Equivalently, $\Gamma^\rho{}_{\mu\nu}(p)=0$. But curvature cannot generally be transformed away:

$$
R^\rho{}_{\sigma\mu\nu}(p)\neq0.
$$

Local inertial frames remove the connection at one point, not tidal effects over a finite region.

## Actions and the curved-space scalar field

The minimal scalar action is

$$
S_\phi
=\frac12\int_M d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-m^2\phi^2
\right).
$$

A more general local action includes curvature coupling:

$$
S_\phi
=\frac12\int_M d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-(m^2+\xi R)\phi^2
\right).
$$

The equation of motion is

$$
(\Box_g+m^2+\xi R)\phi=0,
$$

where

$$
\Box_g\phi
=
\nabla_\mu\nabla^\mu\phi
=
\frac{1}{\sqrt{|g|}}\partial_\mu
\left(\sqrt{|g|}\,g^{\mu\nu}\partial_\nu\phi\right).
$$

In flat spacetime this reduces to

$$
(\partial_t^2-\nabla^2+m^2)\phi=0.
$$

The conformal coupling is

$$
\xi_c=\frac{D-2}{4(D-1)}.
$$

For $m=0$ and $\xi=\xi_c$, the classical scalar action is invariant under local Weyl rescalings when the scalar transforms with the appropriate conformal weight. Quantum mechanically, renormalization can still generate trace anomalies.

## Conserved currents from Killing fields

A vector field $\xi^\mu$ is Killing if

$$
\nabla_{(\mu}\xi_{\nu)}=0.
$$

This is the infinitesimal statement that the metric is invariant under the flow generated by $\xi^\mu$.

If the stress tensor is symmetric and conserved,

$$
\nabla_\mu T^{\mu\nu}=0,
$$

then a Killing vector gives a conserved current

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu,
\qquad
\nabla_\mu J^\mu=0.
$$

This is how energy conservation survives in a stationary spacetime. If there is no timelike Killing vector, there is generally no conserved global energy associated with time translations. Local stress-tensor conservation still holds, but “energy of particles” becomes more delicate and observer-dependent.

## Global hyperbolicity and initial data

A spacetime is globally hyperbolic if it has a Cauchy surface $\Sigma$: a hypersurface intersected exactly once by every inextendible causal curve.

For hyperbolic field equations, global hyperbolicity is the geometric condition that makes the initial-value problem well behaved. For a scalar field, one specifies

$$
\phi|_\Sigma,
\qquad
n^\mu\nabla_\mu\phi|_\Sigma,
$$

where $n^\mu$ is the future-directed unit normal to the spacelike Cauchy surface. The field equation then determines the field in the domain of dependence.

Spacetimes with timelike boundaries or asymptotic boundaries require boundary conditions. In QFT, those boundary conditions affect modes, Green functions, conserved charges, and the Hilbert space.

## Particles, modes, and the role of symmetry

In flat spacetime, Poincare symmetry selects positive-frequency plane waves,

$$
e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf x},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

That positive-frequency split is what underwrites the usual particle interpretation.

On a generic curved spacetime, there may be no preferred time coordinate and no preferred positive-frequency decomposition. A field can still be expanded in a complete set of solutions, but the split into creation and annihilation operators may depend on the observer, the time slicing, or the asymptotic region.

This is why curved spacetime permits effects such as cosmological particle creation, the Unruh effect, and Hawking radiation. The local field algebra can be perfectly well defined while the global particle interpretation changes between observers.

The slogan worth keeping is

$$
\text{fields are local; particles are state- and symmetry-dependent.}
$$

## What QFT sees locally

At short distances, a physically acceptable state of a free field should have the same leading singularity structure as the Minkowski vacuum. This is the idea behind the Hadamard condition. Very roughly, in four dimensions the two-point function near coincidence has the local form

$$
G(x,x')
\sim
\frac{U(x,x')}{\sigma(x,x')+i\epsilon}
+V(x,x')\log(\sigma(x,x')+i\epsilon)
+\text{less singular},
$$

where $\sigma(x,x')$ is Synge's world function, equal to one half the squared geodesic distance when the points are close enough to be connected by a unique geodesic.

The important point is not the exact formula yet. The ultraviolet behavior is local and geometric. This is why renormalized stress tensors in curved spacetime require local curvature counterterms, and why trace anomalies are built from curvature invariants.

## Common pitfalls

**Thinking coordinates are physics.** A singular coordinate system is not necessarily a singular spacetime. Always ask whether a scalar invariant or a physical observable is singular.

**Assuming every spacetime has a preferred vacuum.** Generic curved spacetimes do not have enough symmetry to define a unique positive-frequency split.

**Forgetting curvature couplings.** The term $\xi R\phi^2$ is allowed by locality and covariance. Minimal coupling $\xi=0$ is a choice, not a theorem.

**Calling $\nabla_\mu T^{\mu\nu}=0$ ordinary energy conservation.** It is local covariant conservation. A globally conserved energy requires additional structure, usually a timelike Killing vector and suitable boundary behavior.

**Ignoring boundary conditions.** Differential operators need domains. In QFT, the domain of the wave operator affects modes, commutators, spectra, and the path integral.

**Using local inertial frames too aggressively.** You can set $\Gamma^\rho{}_{\mu\nu}=0$ at one point, not in a finite region with curvature. Tidal effects and curvature counterterms are real.

## Relations to other pages

This page supplies the geometric language for the rest of the volume. The conventions are fixed in [Conventions and Notation](/spacetime-gravity-holography/conventions/). The next natural pages are causal structure, horizons, Killing vectors and conserved quantities, and scalar fields in curved spacetime.

Later chapters use this material in three different ways. QFT in curved spacetime treats $g_{\mu\nu}$ as a fixed external background. Semiclassical gravity lets $\langle T_{\mu\nu}\rangle$ source the metric. Holography treats a higher-dimensional gravitational geometry as a dual representation of strongly coupled QFT data.

## Research status

The differential geometry in this page is standard. The subtle questions begin when it is used in quantum theory: which states are physically admissible, how local algebras encode causal structure, how renormalized stress tensors backreact, and how spacetime geometry itself may emerge from quantum degrees of freedom.

This page deliberately stops before algebraic QFT in curved spacetime, Hadamard renormalization, quantum energy inequalities, and dynamical quantum gravity. Those topics need the vocabulary here, but they are not just vocabulary.

## Exercises

### Exercise 1: Derive the divergence formula

Show that

$$
\nabla_\mu V^\mu
=
\frac{1}{\sqrt{|g|}}\partial_\mu(\sqrt{|g|}V^\mu).
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
\nabla_\mu V^\mu=\partial_\mu V^\mu+\Gamma^\mu{}_{\mu\nu}V^\nu.
$$

For the Levi-Civita connection,

$$
\Gamma^\mu{}_{\mu\nu}=\partial_\nu\log\sqrt{|g|}.
$$

Therefore

$$
\nabla_\mu V^\mu
=\partial_\mu V^\mu+V^\mu\partial_\mu\log\sqrt{|g|}
=\frac{1}{\sqrt{|g|}}\partial_\mu(\sqrt{|g|}V^\mu).
$$

</details>

### Exercise 2: Killing vector current

Let $T^{\mu\nu}$ be symmetric and covariantly conserved. Let $\xi^\mu$ obey the Killing equation. Show that

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu
$$

is covariantly conserved.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\nabla_\mu J^\mu
=\nabla_\mu(T^\mu{}_{\nu}\xi^\nu)
=(\nabla_\mu T^\mu{}_{\nu})\xi^\nu
+T^\mu{}_{\nu}\nabla_\mu\xi^\nu.
$$

The first term vanishes by stress-tensor conservation. Lowering the index on the Killing field,

$$
T^\mu{}_{\nu}\nabla_\mu\xi^\nu
=T^{\mu\nu}\nabla_\mu\xi_\nu.
$$

Since $T^{\mu\nu}$ is symmetric, only the symmetric part of $\nabla_\mu\xi_\nu$ contributes:

$$
T^{\mu\nu}\nabla_\mu\xi_\nu
=T^{\mu\nu}\nabla_{(\mu}\xi_{\nu)}=0.
$$

Thus $\nabla_\mu J^\mu=0$.

</details>

### Exercise 3: Scalar wave operator in a spatially flat cosmology

Consider

$$
ds^2=dt^2-a(t)^2d\mathbf x^2
$$

in $D=4$. Show that for a homogeneous scalar $\phi(t)$,

$$
\Box_g\phi=\ddot\phi+3H\dot\phi,
\qquad
H=\frac{\dot a}{a}.
$$

<details><summary><strong>Solution</strong></summary>

For this metric,

$$
\sqrt{|g|}=a(t)^3,
\qquad
 g^{00}=1.
$$

Since $\phi$ is homogeneous, spatial derivatives vanish. Therefore

$$
\Box_g\phi
=\frac{1}{a^3}\partial_t(a^3\dot\phi)
=\ddot\phi+3\frac{\dot a}{a}\dot\phi.
$$

Thus $\Box_g\phi=\ddot\phi+3H\dot\phi$.

</details>

### Exercise 4: Local inertial coordinates do not remove curvature

Explain why setting $\Gamma^\rho{}_{\mu\nu}(p)=0$ at a point does not imply $R^\rho{}_{\sigma\mu\nu}(p)=0$.

<details><summary><strong>Solution</strong></summary>

The connection is not a tensor, so its value at a point can be changed by a coordinate transformation. The Riemann tensor is a tensor, so if it is nonzero in one coordinate system at $p$, it is nonzero in every coordinate system at $p$.

In local inertial coordinates, $\Gamma^\rho{}_{\mu\nu}(p)=0$, but derivatives of the connection need not vanish. The curvature contains terms schematically of the form

$$
R\sim \partial\Gamma+\Gamma\Gamma.
$$

At $p$, the $\Gamma\Gamma$ terms vanish in local inertial coordinates, but the $\partial\Gamma$ terms remain. These are the tidal effects.

</details>

## References

- R. M. Wald, *General Relativity*, University of Chicago Press, 1984.
- S. W. Hawking and G. F. R. Ellis, *The Large Scale Structure of Space-Time*, Cambridge University Press, 1973.
- S. M. Carroll, *Spacetime and Geometry*, Addison-Wesley, 2004.
- E. Poisson, *A Relativist's Toolkit*, Cambridge University Press, 2004.
- M. Nakahara, *Geometry, Topology and Physics*, 2nd ed., CRC Press, 2018.
- T. Frankel, *The Geometry of Physics*, 3rd ed., Cambridge University Press, 2011.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.

## Version history

- 2026-07-01: Added a polished QFT-oriented introduction to Lorentzian geometry.
