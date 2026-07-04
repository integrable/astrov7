---
title: "Scalar Fields in Curved Spacetime"
description: "A careful introduction to real scalar fields on curved backgrounds, including curvature coupling, the covariant Klein–Gordon equation, conserved inner products, modes, Green functions, and stress tensors."
sidebar:
  label: "Scalar Fields in Curved Spacetime"
  order: 10
level: Graduate
status: "Polished draft"
source: "Birrell and Davies 1982, chs. 3–4; Wald 1994, chs. 2–4; Parker and Toms 2009; Fulling 1989; Carroll 2004, chs. 3–4"
topics:
  - scalar fields
  - curved spacetime
  - Klein–Gordon equation
  - curvature coupling
  - Green functions
canonicalTopics:
  - scalar-field-curved-spacetime
  - covariant-klein-gordon-equation
  - conformal-coupling
  - klein-gordon-inner-product
  - curved-spacetime-green-functions
researchStatus:
  established:
    - "Free scalar fields on globally hyperbolic curved spacetimes are the basic model for QFT in curved spacetime, particle creation, and stress-tensor renormalization."
  active:
    - "The local theory is standard, while state selection, renormalized stress tensors, backreaction, and interacting fields on general backgrounds require additional structure."
---

## Summary

A real scalar field is the simplest quantum field one can place on a curved spacetime. In the conventions of this volume, its local action is

$$
S_\phi
=\frac{1}{2}\int_M d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\nabla_\mu\phi\nabla_\nu\phi
-(m^2+\xi R)\phi^2
\right).
$$

The equation of motion is the curved-spacetime Klein–Gordon equation

$$
(\Box_g+m^2+\xi R)\phi=0,
\qquad
\Box_g\phi=\nabla_\mu\nabla^\mu\phi.
$$

For scalars,

$$
\Box_g\phi
=\frac{1}{\sqrt{|g|}}\partial_\mu
\left(\sqrt{|g|}\,g^{\mu\nu}\partial_\nu\phi\right).
$$

The new feature, compared with flat spacetime, is not merely replacing $\eta_{\mu\nu}$ by $g_{\mu\nu}$. Curvature allows the local coupling $\xi R\phi^2$, global time translations may be absent, and a preferred particle basis may not exist. The field remains local; the vacuum and particles become state- and geometry-dependent.

This page builds the scalar-field template used later for Bogoliubov transformations, particle creation, the Unruh effect, Hawking radiation, de Sitter fluctuations, heat kernels, and stress-tensor renormalization.

## Prerequisites

Read [Conventions and Notation](/spacetime-gravity-holography/conventions/), [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/), [Causal Structure](/spacetime-gravity-holography/spacetime-gravity-toolkit/causal-structure/), and [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/).

You should also know the flat-space real scalar field: action, mode expansion, canonical commutators, Feynman propagator, and stress tensor.

## Core idea

A scalar field on curved spacetime is governed by three principles:

| Principle | Consequence |
|---|---|
| Locality | The equation of motion is a local differential equation. |
| Diffeomorphism covariance | The action is built from tensors and $\sqrt{|g|}d^Dx$. |
| Hyperbolic evolution | On globally hyperbolic spacetimes, Cauchy data determine the field. |

These principles determine the minimal kinetic term and permit curvature couplings. They do not determine a unique vacuum state. That extra choice depends on symmetry, boundary conditions, asymptotic regions, regularity, or physical preparation.

The practical slogan is

$$
\text{curved spacetime changes the mode basis before it changes the local field algebra.}
$$

## Setup and conventions

We use mostly-minus signature. The scalar action is

$$
S_\phi
=\frac{1}{2}\int d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-(m^2+\xi R)\phi^2
\right).
$$

For a scalar, $\nabla_\mu\phi=\partial_\mu\phi$. We still write covariant derivatives when doing integration by parts or constructing invariant expressions.

The operator acting on the field is

$$
P=\Box_g+m^2+\xi R.
$$

With our signature, the flat-space limit is

$$
P\to \partial_t^2-\nabla^2+m^2.
$$

The curvature coupling $\xi$ is dimensionless in any spacetime dimension. Two common choices are:

| Coupling | Value | Meaning |
|---|---:|---|
| Minimal coupling | $\xi=0$ | No explicit $R\phi^2$ term. |
| Conformal coupling | $\xi_c=(D-2)/[4(D-1)]$ | Classically Weyl invariant for $m=0$. |

Minimal coupling is not more fundamental than other values. It is a choice of local operator coefficient. Renormalization in curved spacetime generally forces curvature terms into the effective action.

## Deriving the equation of motion

Vary the action with respect to $\phi$ while holding the metric fixed:

$$
\delta S_\phi
=\int d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\nabla_\mu\phi\nabla_\nu\delta\phi
-(m^2+\xi R)\phi\delta\phi
\right).
$$

Using covariant integration by parts,

$$
\int d^Dx\sqrt{|g|}\,
\nabla_\mu\phi\nabla^\mu\delta\phi
=-\int d^Dx\sqrt{|g|}\,
(\Box_g\phi)\delta\phi
+\text{boundary term}.
$$

With boundary conditions that remove the boundary term,

$$
\delta S_\phi
=-\int d^Dx\sqrt{|g|}\,
(P\phi)\delta\phi.
$$

Since $\delta\phi$ is arbitrary,

$$
(\Box_g+m^2+\xi R)\phi=0.
$$

This sign is a useful convention check: in flat spacetime, plane waves $e^{-iEt+i\mathbf p\cdot\mathbf x}$ obey $E^2=\mathbf p^2+m^2$.

## Cauchy data and symplectic structure

On a globally hyperbolic spacetime, choose a spacelike Cauchy surface $\Sigma$ with future-directed unit normal $n^\mu$. Classical initial data are

$$
\phi|_\Sigma,
\qquad
\pi_\Sigma=n^\mu\nabla_\mu\phi|_\Sigma.
$$

The conserved Klein–Gordon current for two complex solutions $u$ and $v$ is

$$
j^\mu[u,v]
=i\left(u^*\nabla^\mu v-v\nabla^\mu u^*\right).
$$

If $Pu=Pv=0$, then

$$
\nabla_\mu j^\mu[u,v]=0.
$$

This gives the Klein–Gordon inner product

$$
(u,v)_{\mathrm{KG}}
=i\int_\Sigma d\Sigma\,n_\mu
\left(u^*\nabla^\mu v-v\nabla^\mu u^*\right).
$$

By current conservation, this inner product is independent of the Cauchy surface, assuming no boundary flux. It is not positive definite on the space of all complex solutions. A quantization requires choosing a positive-frequency subspace on which it becomes positive.

## Mode expansion and quantization

Suppose a complete set of complex solutions $u_i$ has been chosen so that

$$
(u_i,u_j)_{\mathrm{KG}}=\delta_{ij},
\qquad
(u_i^*,u_j^*)_{\mathrm{KG}}=-\delta_{ij},
\qquad
(u_i,u_j^*)_{\mathrm{KG}}=0.
$$

Then the real quantum field can be expanded as

$$
\widehat\phi(x)
=\sum_i\left(a_i u_i(x)+a_i^\dagger u_i^*(x)\right),
$$

with

$$
[a_i,a_j^\dagger]=\delta_{ij},
\qquad
[a_i,a_j]=[a_i^\dagger,a_j^\dagger]=0.
$$

The vacuum associated with this choice is defined by

$$
a_i|0_u\rangle=0
\qquad
\text{for all }i.
$$

The notation $|0_u\rangle$ is a warning label. A different complete positive-frequency basis may define a different vacuum. In flat spacetime, Poincare symmetry selects the usual basis. In a general curved spacetime, no symmetry may exist to make one basis canonical.

## Positive frequency and Killing time

If the spacetime has a timelike Killing vector $\xi^\mu$, a mode can be assigned Killing frequency by

$$
\mathcal L_\xi u=-i\omega u.
$$

When $\xi^\mu$ is timelike in the region of interest and the boundary conditions are compatible with it, positive-frequency modes are those with $\omega>0$. This is the closest curved-spacetime analogue of the flat-space mode basis.

When the geometry is time dependent, this clean split can fail. In cosmology, a natural early-time positive-frequency basis may evolve into a mixture of positive and negative frequencies at late times. That mixing is the origin of particle creation.

Near horizons, different time flows lead to different positive-frequency notions. This is the seed of the Unruh and Hawking effects.

## Green functions

A Green function for the scalar operator satisfies

$$
P_xG(x,x')=\delta^{(D)}(x,x')/\sqrt{|g|}.
$$

On a globally hyperbolic spacetime, the retarded and advanced Green functions are uniquely characterized by support conditions:

$$
\operatorname{supp}G_R(\cdot,x')\subseteq J^+(x'),
\qquad
\operatorname{supp}G_A(\cdot,x')\subseteq J^-(x').
$$

Their difference is the causal propagator,

$$
\Delta(x,x')=G_R(x,x')-G_A(x,x').
$$

The field commutator is fixed by this causal propagator:

$$
[\widehat\phi(x),\widehat\phi(x')]=i\Delta(x,x').
$$

The Feynman two-point function is state-dependent:

$$
G_F(x,x')=\langle T\widehat\phi(x)\widehat\phi(x')\rangle.
$$

In curved spacetime, confusing $G_F$ with a purely geometric Green function is a common error. The retarded and advanced propagators are fixed by the operator and causal structure; the Feynman propagator also knows the state.

## Stress tensor

The stress tensor is defined by metric variation:

$$
T_{\mu\nu}
=-\frac{2}{\sqrt{|g|}}\frac{\delta S_\phi}{\delta g^{\mu\nu}}.
$$

For minimal coupling, $\xi=0$,

$$
T_{\mu\nu}^{\mathrm{min}}
=\nabla_\mu\phi\nabla_\nu\phi
-\frac{1}{2}g_{\mu\nu}
\left(\nabla_\rho\phi\nabla^\rho\phi-m^2\phi^2\right).
$$

For nonminimal coupling, the additional curvature-dependent contribution is

$$
T_{\mu\nu}^{(\xi)}
=\xi\left(
G_{\mu\nu}\phi^2
+g_{\mu\nu}\Box_g\phi^2
-\nabla_\mu\nabla_\nu\phi^2
\right).
$$

Thus

$$
T_{\mu\nu}=T_{\mu\nu}^{\mathrm{min}}+T_{\mu\nu}^{(\xi)}.
$$

On shell, the classical stress tensor is covariantly conserved:

$$
\nabla^\mu T_{\mu\nu}=0.
$$

Quantum mechanically, products such as $\widehat\phi(x)^2$ and $\widehat T_{\mu\nu}(x)$ require renormalization. This is where point-splitting, Hadamard subtraction, heat kernels, trace anomalies, and curvature counterterms enter.

## Examples

### Flat spacetime

In Minkowski spacetime,

$$
ds^2=dt^2-d\mathbf x^2,
$$

the equation is

$$
(\partial_t^2-\nabla^2+m^2)\phi=0.
$$

Plane-wave modes are

$$
u_{\mathbf p}(x)
=\frac{e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf x}}
{\sqrt{2E_{\mathbf p}}},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

with the usual continuum normalization after including the measure factors. Time-translation symmetry selects the positive-frequency modes.

### Spatially flat cosmology

For

$$
ds^2=dt^2-a(t)^2d\mathbf x^2,
$$

a homogeneous scalar obeys

$$
\ddot\phi+(D-1)H\dot\phi+(m^2+\xi R)\phi=0,
\qquad
H=\dot a/a.
$$

For inhomogeneous modes in $D=4$,

$$
\ddot\phi_{\mathbf k}+3H\dot\phi_{\mathbf k}
+\left(k^2/a^2+m^2+\xi R\right)\phi_{\mathbf k}=0.
$$

The time-dependent frequency is the reason that early-time and late-time particle notions can differ.

### Static spacetime

For a static metric, one can often separate variables as

$$
\phi(t,\mathbf x)=e^{-i\omega t}f_\omega(\mathbf x).
$$

The mode problem becomes a spatial eigenvalue problem. When the timelike Killing field remains well behaved and boundary conditions are fixed, this provides a natural quantization. Static black-hole exteriors require more care because the Killing field becomes null at the horizon.

## Common pitfalls

**Thinking minimal coupling is forced.** The term $\xi R\phi^2$ is allowed by locality and covariance. Setting $\xi=0$ is a model choice.

**Forgetting the sign convention.** With mostly-minus signature and this action, the equation is $(\Box_g+m^2+\xi R)\phi=0$.

**Treating the vacuum as part of the local Lagrangian.** The action defines the operator. The state is additional information.

**Confusing the Feynman propagator with the retarded propagator.** Retarded propagation is causal and state-independent. The Feynman two-point function depends on the state.

**Ignoring boundary conditions.** In spacetimes with timelike boundaries, such as AdS, the differential operator is not fully specified until a domain or boundary condition is chosen.

**Assuming the stress tensor is automatically finite.** The quantum stress tensor is composite and needs renormalization. Curvature counterterms are not optional bookkeeping.

## Relations to other pages

This is the first ordinary page in the QFT in Curved Spacetime chapter. It uses the geometric tools from [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/), [Causal Structure](/spacetime-gravity-holography/spacetime-gravity-toolkit/causal-structure/), and [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/).

The next natural pages are spinor fields in curved spacetime, vector fields in curved spacetime, mode expansions, Bogoliubov transformations, particle creation, the Unruh effect, and Hawking radiation. The stress tensor formula here is developed further in the Stress Tensor and Curved-Space Renormalization chapter.

## Research status

The free scalar field on globally hyperbolic curved spacetimes is a mature subject. The local equation, causal propagator, symplectic structure, and algebraic quantization are standard.

The subtleties are state selection and renormalization. In realistic curved backgrounds, one must decide which states are physically admissible, how to impose boundary conditions, how to renormalize composite operators, and when the expectation value $\langle T_{\mu\nu}\rangle$ can consistently backreact on the geometry.

## Exercises

### Exercise 1: Derive the covariant Klein–Gordon equation

Vary the scalar action

$$
S_\phi
=\frac{1}{2}\int d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-(m^2+\xi R)\phi^2
\right)
$$

with respect to $\phi$ and derive

$$
(\Box_g+m^2+\xi R)\phi=0.
$$

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta S_\phi
=\int d^Dx\sqrt{|g|}\,
\left(
\nabla_\mu\phi\nabla^\mu\delta\phi
-(m^2+\xi R)\phi\delta\phi
\right).
$$

Integrating by parts,

$$
\int d^Dx\sqrt{|g|}\,\nabla_\mu\phi\nabla^\mu\delta\phi
=-\int d^Dx\sqrt{|g|}\,(\Box_g\phi)\delta\phi,
$$

up to a boundary term. Therefore

$$
\delta S_\phi
=-\int d^Dx\sqrt{|g|}\,
(\Box_g+m^2+\xi R)\phi\,\delta\phi.
$$

Since $\delta\phi$ is arbitrary, the equation follows.

</details>

### Exercise 2: Conservation of the Klein–Gordon current

Let $u$ and $v$ satisfy $Pu=Pv=0$, where $P=\Box_g+m^2+\xi R$. Show that

$$
j^\mu=i(u^*\nabla^\mu v-v\nabla^\mu u^*)
$$

is conserved.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\nabla_\mu j^\mu
=i\left(u^*\Box_g v-v\Box_g u^*\right),
$$

because the cross terms cancel. Since $Pv=0$ and $Pu=0$,

$$
\Box_g v=-(m^2+\xi R)v,
\qquad
\Box_g u^*=-(m^2+\xi R)u^*.
$$

Substitution gives

$$
\nabla_\mu j^\mu
=i\left[-u^*(m^2+\xi R)v+v(m^2+\xi R)u^*\right]=0.
$$

</details>

### Exercise 3: Conformal coupling in four dimensions

Evaluate

$$
\xi_c=\frac{D-2}{4(D-1)}
$$

for $D=4$.

<details><summary><strong>Solution</strong></summary>

Substitute $D=4$:

$$
\xi_c=\frac{4-2}{4(4-1)}=\frac{2}{12}=\frac{1}{6}.
$$

</details>

### Exercise 4: Scalar modes in an expanding universe

For

$$
ds^2=dt^2-a(t)^2d\mathbf x^2
$$

in four spacetime dimensions, show that a Fourier mode obeys

$$
\ddot\phi_{\mathbf k}+3H\dot\phi_{\mathbf k}
+\left(k^2/a^2+m^2+\xi R\right)\phi_{\mathbf k}=0.
$$

<details><summary><strong>Solution</strong></summary>

The metric determinant gives $\sqrt{|g|}=a^3$, and

$$
g^{00}=1,
\qquad
g^{ij}=-a^{-2}\delta^{ij}.
$$

Thus

$$
\Box_g\phi
=\frac{1}{a^3}\partial_t(a^3\dot\phi)
-a^{-2}\nabla^2\phi.
$$

For $\phi(t,\mathbf x)=\phi_{\mathbf k}(t)e^{i\mathbf k\cdot\mathbf x}$, $\nabla^2\phi=-k^2\phi$. Therefore

$$
\Box_g\phi
=\left(\ddot\phi_{\mathbf k}+3H\dot\phi_{\mathbf k}+k^2a^{-2}\phi_{\mathbf k}\right)e^{i\mathbf k\cdot\mathbf x}.
$$

Adding $(m^2+\xi R)\phi$ gives the stated mode equation.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 2009.
- S. M. Carroll, *Spacetime and Geometry*, Addison-Wesley, 2004.
- B. S. DeWitt, *The Global Approach to Quantum Field Theory*, Oxford University Press, 2003.
- C. J. Fewster and K. Rejzner, “Algebraic quantum field theory: an introduction,” in *Progress and Visions in Quantum Theory in View of Gravity*, Birkhäuser, 2020.

## Version history

- 2026-07-01: Added a polished first page on scalar fields in curved spacetime.
