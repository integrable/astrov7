---
title: "Conformal Killing Equation"
description: "Derives and solves the conformal Killing equation in flat space, explaining how infinitesimal conformal transformations lead to translations, rotations, dilatations, and special conformal transformations."
sidebar:
  label: "Conformal Killing Equation"
  order: 5
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Nakahara 2018; Frankel 2011"
topics:
  - conformal Killing equation
  - infinitesimal conformal transformations
  - conformal vector fields
  - stress tensor
  - scale invariance
  - conformal algebra
canonicalTopics:
  - conformal-killing-equation
  - conformal-vector-fields
  - infinitesimal-conformal-transformations
  - stress-tensor-trace
researchStatus:
  established:
    - 'In flat dimension $d>2$, the conformal Killing equation has only the finite-dimensional solutions corresponding to translations, rotations, dilatations, and special conformal transformations.'
    - 'In two Euclidean dimensions, the local conformal Killing equation becomes the Cauchy–Riemann equation, giving infinitely many local conformal transformations.'
  active:
    - "The flat-space equation is standard; active uses include curved conformal manifolds, conformal Killing spinors, defects, boundaries, supersymmetric backgrounds, and Lorentzian conformal geometry."
---

## Summary

The conformal Killing equation is the infinitesimal condition that a coordinate transformation preserves angles. For a small transformation

$$
x^\mu\mapsto x'^\mu=x^\mu+\xi^\mu(x),
$$

the flat Euclidean metric changes by

$$
\delta_{\mu\nu}\,dx'^\mu dx'^\nu
=
\left(\delta_{\mu\nu}+\partial_\mu\xi_\nu+\partial_\nu\xi_\mu\right)dx^\mu dx^\nu+O(\xi^2).
$$

The transformation is conformal if this change is a local Weyl rescaling of the metric. Therefore

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
\frac{2}{d}(\partial\cdot \xi)\delta_{\mu\nu}.
$$

For $d>2$, the general flat-space solution is

$$
\xi^\mu(x)
=
a^\mu+
\omega^\mu{}_{\nu}x^\nu+
\lambda x^\mu+
2(b\cdot x)x^\mu-b^\mu x^2,
$$

where $a^\mu$ generates translations, $\omega_{\mu\nu}=-\omega_{\nu\mu}$ generates rotations, $\lambda$ generates dilatations, and $b^\mu$ generates special conformal transformations.

This one equation explains why higher-dimensional conformal symmetry is powerful but finite-dimensional. It also explains why two-dimensional CFT is exceptional: in two dimensions, the local equation becomes the Cauchy–Riemann equation and admits infinitely many local solutions.

:::note[The equation behind the algebra]
The conformal algebra is not a guess. It is the algebra of vector fields solving the conformal Killing equation on flat space, with global and signature-dependent qualifications.
:::

## Prerequisites

You should know the finite transformations in [Finite Conformal Transformations](/cft-bootstrap/conformal-symmetry/finite-conformal-transformations/) and the generator language in [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/). It is also useful to know the stress-tensor interpretation of scale versus conformal invariance from [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/).

This page uses flat Euclidean notation. In Lorentzian signature, replace $\delta_{\mu\nu}$ by $\eta_{\mu\nu}$. The algebraic form of the equation is the same, but causal and global questions require more care.

## Core idea

An ordinary Killing vector preserves the metric:

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=0.
$$

A conformal Killing vector preserves the metric up to a local scale:

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=2\sigma(x)\delta_{\mu\nu}.
$$

Taking the trace fixes the scale function:

$$
\sigma(x)=\frac{1}{d}\partial_\mu\xi^\mu.
$$

So the conformal Killing equation is

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
2\sigma(x)\delta_{\mu\nu},
\qquad
\sigma(x)=\frac{1}{d}\partial\cdot\xi.
$$

The symmetric traceless part of $\partial_\mu\xi_\nu$ must vanish. Rotations are allowed because they are antisymmetric. Dilatations are allowed because they are pure trace. Special conformal transformations are allowed because their derivative is carefully arranged so that the symmetric traceless part cancels.

## Setup and conventions

We work in $d$-dimensional Euclidean space with

$$
ds^2=\delta_{\mu\nu}dx^\mu dx^\nu.
$$

A small coordinate transformation is

$$
x'^\mu=x^\mu+\xi^\mu(x),
$$

where $\xi^\mu$ is kept only to first order. Indices are raised and lowered with $\delta_{\mu\nu}$, so there is no distinction between upper and lower spatial Euclidean indices except notational clarity.

The local scale function is

$$
\sigma(x)=\frac{1}{d}\partial\cdot \xi,
\qquad
\partial\cdot \xi=\partial_\mu\xi^\mu.
$$

With this convention, a dilatation vector field

$$
\xi^\mu=\lambda x^\mu
$$

has

$$
\sigma=\lambda.
$$

A special-conformal vector field

$$
\xi^\mu=2(b\cdot x)x^\mu-b^\mu x^2
$$

has

$$
\sigma=2b\cdot x.
$$

## Deriving the equation

The transformed differential is

$$
dx'^\mu
=
\frac{\partial x'^\mu}{\partial x^\rho}dx^\rho
=
\left(\delta^\mu{}_{\rho}+\partial_\rho\xi^\mu\right)dx^\rho.
$$

Therefore

$$
\begin{aligned}
ds'^2
&=\delta_{\mu\nu}dx'^\mu dx'^\nu\\
&=\delta_{\rho\sigma}dx^\rho dx^\sigma
+
\left(\partial_\rho\xi_\sigma+\partial_\sigma\xi_\rho\right)dx^\rho dx^\sigma
+O(\xi^2).
\end{aligned}
$$

A conformal transformation may change the metric only by a local scale:

$$
ds'^2=(1+2\sigma(x))ds^2+O(\xi^2).
$$

Thus

$$
\partial_\rho\xi_\sigma+\partial_\sigma\xi_\rho
=
2\sigma(x)\delta_{\rho\sigma}.
$$

Taking the trace gives

$$
2\partial\cdot\xi=2d\sigma,
$$

so

$$
\sigma=\frac{1}{d}\partial\cdot\xi.
$$

Substituting this back gives the standard conformal Killing equation:

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
\frac{2}{d}(\partial\cdot \xi)\delta_{\mu\nu}.
$$

### Comparison with ordinary Killing vectors

If $\sigma=0$, the conformal Killing equation becomes the ordinary Killing equation. In flat Euclidean space, its solutions are translations and rotations:

$$
\xi^\mu=a^\mu+\omega^\mu{}_{\nu}x^\nu,
\qquad
\omega_{\mu\nu}=-\omega_{\nu\mu}.
$$

The conformal equation allows two more possibilities: a constant trace part, giving dilatations, and a trace part linear in $x$, giving special conformal transformations.

## Solving the equation in dimensions greater than two

For $d>2$, the conformal Killing equation is overdetermined. This is why the solution space is finite-dimensional.

Start from

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=2\sigma\delta_{\mu\nu}.
$$

By differentiating and combining cyclic permutations, one obtains

$$
\partial_\mu\partial_\nu\xi_\rho
=
\delta_{\mu\rho}\partial_\nu\sigma
+
\delta_{\nu\rho}\partial_\mu\sigma
-
\delta_{\mu\nu}\partial_\rho\sigma.
$$

Taking another derivative and using the commutativity of partial derivatives implies, for $d>2$,

$$
\partial_\mu\partial_\nu\sigma=0.
$$

Therefore $\sigma(x)$ is at most linear:

$$
\sigma(x)=\lambda+2b\cdot x.
$$

Integrating the equation gives

$$
\xi^\mu(x)
=
a^\mu+
\omega^\mu{}_{\nu}x^\nu+
\lambda x^\mu+
2(b\cdot x)x^\mu-b^\mu x^2,
$$

with

$$
\omega_{\mu\nu}=-\omega_{\nu\mu}.
$$

The four terms are easy to identify:

| Term | Vector field | Meaning |
|---|---|---|
| $a^\mu$ | constant | translation |
| $\omega^\mu{}_{\nu}x^\nu$ | antisymmetric linear | rotation |
| $\lambda x^\mu$ | trace linear | dilatation |
| $2(b\cdot x)x^\mu-b^\mu x^2$ | quadratic | special conformal transformation |

The number of independent parameters is

$$
d+\frac{d(d-1)}{2}+1+d
=
\frac{(d+1)(d+2)}{2}.
$$

This equals the dimension of $SO(d+1,1)$, the Euclidean conformal group in $d$ dimensions.

### Direct checks

For a translation,

$$
\xi^\mu=a^\mu,
$$

all derivatives vanish, so the equation is satisfied with $\sigma=0$.

For a rotation,

$$
\xi^\mu=\omega^\mu{}_{\nu}x^\nu,
\qquad
\omega_{\mu\nu}=-\omega_{\nu\mu},
$$

we have

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=\omega_{\nu\mu}+\omega_{\mu\nu}=0.
$$

For a dilatation,

$$
\xi^\mu=\lambda x^\mu,
$$

we have

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=2\lambda\delta_{\mu\nu},
\qquad
\partial\cdot\xi=d\lambda.
$$

For a special conformal transformation,

$$
\xi^\mu=2(b\cdot x)x^\mu-b^\mu x^2,
$$

one finds

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=4(b\cdot x)\delta_{\mu\nu},
\qquad
\partial\cdot\xi=2d(b\cdot x).
$$

Thus

$$
\frac{2}{d}\partial\cdot\xi=4b\cdot x,
$$

as required.

## The two-dimensional exception

In two Euclidean dimensions, introduce complex coordinates

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2.
$$

A local vector field can be written as

$$
\xi=\xi^z(z,\bar z)\partial_z+\xi^{\bar z}(z,\bar z)\partial_{\bar z}.
$$

The conformal Killing equation becomes

$$
\partial_{\bar z}\xi^z=0,
\qquad
\partial_z\xi^{\bar z}=0.
$$

Thus

$$
\xi^z=f(z),
\qquad
\xi^{\bar z}=\bar f(\bar z)
$$

for holomorphic and antiholomorphic functions. Locally, this gives infinitely many conformal vector fields.

For global transformations of the Riemann sphere, regularity restricts $f(z)$ to a quadratic polynomial:

$$
f(z)=a+bz+cz^2.
$$

These generate the global transformations

$$
z\mapsto \frac{Az+B}{Cz+D},
\qquad
AD-BC\neq 0.
$$

The infinite-dimensional enhancement reappears quantum mechanically as the Virasoro algebra. This is why the chapter [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) are not just special cases of the higher-dimensional story. They are structurally richer.

## Stress tensor interpretation

The conformal Killing equation also explains why a traceless stress tensor produces conformal charges.

Let $T_{\mu\nu}$ be a conserved symmetric stress tensor:

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
T_{\mu\nu}=T_{\nu\mu}.
$$

Given a vector field $\xi^\nu$, define the current

$$
j^\mu_\xi=T^{\mu}{}_{\nu}\xi^\nu.
$$

Its divergence is

$$
\begin{aligned}
\partial_\mu j^\mu_\xi
&=(\partial_\mu T^{\mu}{}_{\nu})\xi^\nu+T^{\mu}{}_{\nu}\partial_\mu\xi^\nu\\
&=T^{\mu\nu}\partial_\mu\xi_\nu.
\end{aligned}
$$

Since $T^{\mu\nu}$ is symmetric,

$$
T^{\mu\nu}\partial_\mu\xi_\nu
=
\frac12T^{\mu\nu}(\partial_\mu\xi_\nu+\partial_\nu\xi_\mu).
$$

If $\xi$ is conformal Killing, then

$$
\partial_\mu j^\mu_\xi
=
\sigma(x)T^\mu{}_{\mu}.
$$

Therefore, if the stress tensor is traceless,

$$
T^\mu{}_{\mu}=0,
$$

then every conformal Killing vector gives a conserved current:

$$
\partial_\mu j^\mu_\xi=0.
$$

This is the stress-tensor version of conformal symmetry.

### Why the trace matters

For a scale-invariant theory, the dilatation current has the form

$$
j_D^\mu=x_\nu T^{\mu\nu}-V^\mu,
$$

where $V^\mu$ is a possible virial current. If $V^\mu$ can be removed by improving the stress tensor, then one can arrange

$$
T^\mu{}_{\mu}=0,
$$

and the theory is conformal. If not, scale invariance may fail to enhance to conformal invariance. This is why the conformal Killing equation is tied to the subtle page [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/).

## From local vector fields to global transformations

The conformal Killing equation is local. It tells us which infinitesimal vector fields preserve the metric up to scale near a point. Turning these vector fields into globally well-defined transformations requires more information.

In $d>2$, local rigidity is strong enough that the global flat-space transformations are generated by translations, rotations, dilatations, and special conformal transformations, with singular points handled by conformal compactification.

In two dimensions, the local equation allows arbitrary holomorphic functions, but only a small subset are globally well-defined on the Riemann sphere. On other Riemann surfaces, the global conformal vector fields depend strongly on topology.

In Lorentzian signature, global questions are even more delicate because conformal maps interact with causal structure. The infinitesimal equation remains simple; the global analytic domain is not.

## Common pitfalls

**Thinking conformal means distance-preserving.** Killing vectors preserve the metric. Conformal Killing vectors preserve the metric only up to a local factor. Angles survive; lengths need not.

**Forgetting the trace subtraction.** The equation is not

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=0.
$$

That is the ordinary Killing equation. The conformal equation allows a pure trace symmetric part.

**Assuming two-dimensional and higher-dimensional CFT have the same local symmetry.** They do not. The local conformal group is infinite-dimensional in two Euclidean dimensions and finite-dimensional for $d>2$.

**Confusing local and global conformal transformations.** A holomorphic function is locally conformal where its derivative is nonzero. It need not define a globally allowed symmetry of the CFT background.

**Ignoring stress-tensor improvements.** Whether scale invariance becomes conformal invariance can depend on whether the stress tensor can be improved to become traceless. The conformal Killing equation tells you what currents would be conserved if the trace vanished.

## Relations to other pages

This page supplies the infinitesimal geometry behind [Finite Conformal Transformations](/cft-bootstrap/conformal-symmetry/finite-conformal-transformations/) and [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/). The general solution of the conformal Killing equation produces the vector fields whose commutators form the conformal algebra.

The stress-tensor discussion connects to [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/), [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/), and [Stress Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/). The two-dimensional exception leads to [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/) and [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/).

## Research status

The flat-space conformal Killing equation and its solutions are standard. The important caveats are not about the local equation; they are about assumptions, signature, topology, boundaries, defects, and quantum anomalies.

Current research often uses generalizations: conformal Killing vectors on curved backgrounds, conformal Killing spinors in supersymmetric theories, conformal isometries preserving defects or boundaries, and Lorentzian conformal geometry in collider bounds, light-ray operators, and celestial descriptions. These developments build on the same simple equation but impose additional global or representation-theoretic structure.

## Exercises

### Exercise 1: Derive the conformal Killing equation

Starting from

$$
x'^\mu=x^\mu+\xi^\mu(x),
$$

and requiring

$$
ds'^2=(1+2\sigma(x))ds^2+O(\xi^2),
$$

derive

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
\frac{2}{d}(\partial\cdot\xi)\delta_{\mu\nu}.
$$

<details><summary><strong>Solution</strong></summary>

The differential transforms as

$$
dx'^\mu=(\delta^\mu{}_{\rho}+\partial_\rho\xi^\mu)dx^\rho.
$$

Thus

$$
ds'^2
=
\delta_{\rho\sigma}dx^\rho dx^\sigma
+
(\partial_\rho\xi_\sigma+\partial_\sigma\xi_\rho)dx^\rho dx^\sigma
+O(\xi^2).
$$

The conformal condition says that the first-order correction must be pure trace:

$$
\partial_\rho\xi_\sigma+\partial_\sigma\xi_\rho=2\sigma\delta_{\rho\sigma}.
$$

Tracing gives

$$
2\partial\cdot\xi=2d\sigma,
$$

so

$$
\sigma=\frac{1}{d}\partial\cdot\xi.
$$

Substitution gives the conformal Killing equation.

</details>

### Exercise 2: Check the special-conformal vector field

Let

$$
\xi^\mu=2(b\cdot x)x^\mu-b^\mu x^2.
$$

Show that it satisfies the conformal Killing equation and find $\sigma(x)$.

<details><summary><strong>Solution</strong></summary>

Lowering indices with $\delta_{\mu\nu}$,

$$
\xi_\nu=2(b\cdot x)x_\nu-b_\nu x^2.
$$

Differentiate:

$$
\partial_\mu\xi_\nu
=2b_\mu x_\nu+2(b\cdot x)\delta_{\mu\nu}-2b_\nu x_\mu.
$$

Symmetrizing gives

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=4(b\cdot x)\delta_{\mu\nu}.
$$

The divergence is

$$
\partial\cdot\xi=2d(b\cdot x),
$$

so

$$
\frac{2}{d}\partial\cdot\xi=4b\cdot x.
$$

Therefore the conformal Killing equation is satisfied with

$$
\sigma(x)=2b\cdot x.
$$

</details>

### Exercise 3: Derive current conservation from tracelessness

Let $T_{\mu\nu}$ be conserved, symmetric, and traceless. Show that

$$
j^\mu_\xi=T^\mu{}_{\nu}\xi^\nu
$$

is conserved for every conformal Killing vector $\xi$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j^\mu_\xi
=(\partial_\mu T^\mu{}_{\nu})\xi^\nu+T^\mu{}_{\nu}\partial_\mu\xi^\nu.
$$

The first term vanishes by stress-tensor conservation. Since $T^{\mu\nu}$ is symmetric,

$$
T^\mu{}_{\nu}\partial_\mu\xi^\nu
=
\frac12T^{\mu\nu}(\partial_\mu\xi_\nu+\partial_\nu\xi_\mu).
$$

Using the conformal Killing equation,

$$
\partial_\mu j^\mu_\xi
=
\frac12T^{\mu\nu}\,2\sigma\delta_{\mu\nu}
=
\sigma T^\mu{}_{\mu}.
$$

If $T^\mu{}_{\mu}=0$, then

$$
\partial_\mu j^\mu_\xi=0.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Chapters 4–6 give the standard conformal-transformation and Ward-identity background.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, 2017. Especially useful for the higher-dimensional conformal Killing equation and its role in CFT kinematics.
- D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, 2016. Connects conformal Killing vectors, stress tensors, radial quantization, and bootstrap constraints.
- M. Nakahara, *Geometry, Topology and Physics*, 2nd ed., 2018. Useful background on Killing and conformal Killing vector fields.
- T. Frankel, *The Geometry of Physics*, 3rd ed., 2011. Useful for the geometric language of metrics, Lie derivatives, and infinitesimal transformations.

## Version history

- 2026-06-27: First polished draft.
