---
title: "Riemannian and Lorentzian Geometry"
description: "Introduces metrics, signatures, Levi–Civita connections, curvature conventions, Hodge stars, causal structure, vielbeins, and the geometric ingredients used by QFT on curved backgrounds."
sidebar:
  label: "Riemannian and Lorentzian Geometry"
  order: 9
level: Graduate
status: "Polished draft"
source: "Standard geometry and QFT references, including Nakahara, Frankel, Kobayashi–Nomizu, Eguchi–Gilkey–Hanson, Wald, Weinberg, Birrell–Davies, Parker–Toms, and Freedman–Van Proeyen."
topics:
  - Riemannian geometry
  - Lorentzian geometry
  - metric tensor
  - Levi-Civita connection
  - curvature conventions
  - Hodge star
  - vielbeins
  - causal structure
  - QFT in curved spacetime
canonicalTopics:
  - riemannian-geometry
  - lorentzian-geometry
  - metric-tensor
  - levi-civita-connection
  - riemann-curvature-tensor
  - ricci-tensor
  - scalar-curvature
  - hodge-star
  - vielbein
  - causal-structure
researchStatus:
  established:
    - "The metric, Levi–Civita connection, curvature tensor, Hodge star, and causal structure are standard geometric objects; the only serious ambiguity for QFT notation is convention choice."
  active:
    - "Active QFT questions involve quantum fields on singular spaces, null boundaries, non-smooth backgrounds, generalized spin structures, gravitational anomalies, semiclassical gravity, and path integrals over metrics."
---

## Summary

A metric turns a smooth manifold into a geometric spacetime or Euclidean background. It lets us measure lengths and angles, raise and lower indices, define volume, build Laplacians, identify kinetic terms, and distinguish timelike, null, and spacelike directions in Lorentzian signature.

A **Riemannian metric** is positive definite. A **Lorentzian metric** has one time direction. In the default flat-space convention used throughout this volume,

$$
\eta_{ab}=\operatorname{diag}(+1,-1,-1,-1),
$$

so flat Lorentzian spacetime has signature $(1,3)$: one positive time direction and three negative spatial directions.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing metric tensor, signature, Levi-Civita connection, curvature, Hodge star, causal structure, operators, and QFT data.](/figures/math-toolkit/metric-geometry-dictionary.svg)

<figcaption>

A metric supplies much of the geometric background data used by QFT on manifolds. It determines volume, the Hodge star, the Levi–Civita connection, curvature, causal structure in Lorentzian signature, and the standard differential operators used in kinetic terms.

</figcaption>
</figure>

The central convention on this page is the curvature sign. For a vector field $V^\rho$, we use

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

Equivalently,

$$
R^\rho{}_{\sigma\mu\nu}
=\partial_\mu\Gamma^\rho{}_{\nu\sigma}
-\partial_\nu\Gamma^\rho{}_{\mu\sigma}
+\Gamma^\rho{}_{\mu\lambda}\Gamma^\lambda{}_{\nu\sigma}
-\Gamma^\rho{}_{\nu\lambda}\Gamma^\lambda{}_{\mu\sigma}.
$$

Some books use the opposite sign. Nothing physical changes, but formulas for $R_{\mu\nu}$, heat-kernel coefficients, gravitational actions, and anomaly polynomials must be translated consistently. Curvature-sign confusion is one of those tiny doors through which a whole herd of wrong signs can escape.

## Prerequisites

Read [Manifolds](/math-toolkit/geometry-of-fields/manifolds/), [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/), [Lie Derivatives](/math-toolkit/geometry-of-fields/lie-derivatives/), and [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) first.

You should know what tangent vectors, cotangent vectors, differential forms, pullbacks, and vector-bundle connections are. This page specializes those ideas to the tangent bundle and to the metric structures used in QFT.

For local spinor algebra, see [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) and [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/). For the global existence of spinor fields, continue to [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/).

## Core idea

A smooth manifold $M$ has enough structure to define differentiable fields and differential forms, but not enough structure to measure their sizes. A metric adds a nondegenerate symmetric bilinear form

$$
g_x:T_xM\times T_xM\to\mathbb R
$$

at every point $x\in M$, varying smoothly with $x$.

In coordinates,

$$
g=g_{\mu\nu}(x)\,dx^\mu\otimes dx^\nu,
$$

with

$$
g_{\mu\nu}=g_{\nu\mu},
\qquad
\det(g_{\mu\nu})\ne 0.
$$

The metric does four basic jobs.

First, it pairs tangent vectors:

$$
g(V,W)=g_{\mu\nu}V^\mu W^\nu.
$$

Second, it identifies tangent and cotangent spaces by raising and lowering indices:

$$
V_\mu=g_{\mu\nu}V^\nu,
\qquad
\alpha^\mu=g^{\mu\nu}\alpha_\nu.
$$

Third, it defines a natural volume density:

$$
\sqrt{|g|}\,d^nx,
\qquad
|g|=|\det(g_{\mu\nu})|.
$$

Fourth, together with the requirement of zero torsion, it determines a preferred connection: the Levi–Civita connection.

The important philosophy is this:

$$
\text{a metric is not just a way to measure length; it is a machine for building QFT operators.}
$$

It enters scalar kinetic terms, Maxwell theory through the Hodge star, fermion kinetic terms through vielbeins and spin connections, stress tensors through metric variation, and Euclidean path integrals through the measure and action.

## Metrics and signatures

Let $M$ have dimension $n$. A pseudo-Riemannian metric has constant signature $(p,q)$, meaning that at each point it can be diagonalized to

$$
\underbrace{+1,\ldots,+1}_{p\text{ times}},
\underbrace{-1,\ldots,-1}_{q\text{ times}}.
$$

The two most important cases are:

| Geometry | Signature | Typical use |
|---|---:|---|
| Riemannian | $(n,0)$ | Euclidean QFT, statistical mechanics, instantons, heat kernels, spectral theory |
| Lorentzian, mostly-minus | $(1,n-1)$ | Real-time relativistic QFT and classical spacetime |

In four-dimensional Lorentzian signature, our default local flat metric is

$$
\eta_{ab}=\operatorname{diag}(+1,-1,-1,-1).
$$

Here $a,b$ are local orthonormal-frame indices. Curved coordinate indices are written $\mu,\nu$. A local orthonormal frame relates the two by a vielbein, discussed below.

The line element is

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu.
$$

In mostly-minus Lorentzian signature, a tangent vector $V$ is called

$$
\begin{array}{lll}
\text{timelike} & \text{if} & g(V,V)>0,\\
\text{null} & \text{if} & g(V,V)=0\text{ and }V\ne0,\\
\text{spacelike} & \text{if} & g(V,V)<0.
\end{array}
$$

In Riemannian signature, every nonzero vector has positive norm. There is no light cone, no causal future, and no real-time unitarity notion built into the metric.

## Raising, lowering, and musical maps

The metric inverse $g^{\mu\nu}$ is defined by

$$
g^{\mu\rho}g_{\rho\nu}=\delta^\mu{}_{\nu}.
$$

It lets us turn vectors into one-forms and one-forms into vectors:

$$
V^\mu\mapsto V_\mu=g_{\mu\nu}V^\nu,
\qquad
\alpha_\mu\mapsto \alpha^\mu=g^{\mu\nu}\alpha_\nu.
$$

In geometric language these are the musical maps

$$
\flat:TM\to T^*M,
\qquad
\sharp:T^*M\to TM.
$$

Thus

$$
V^\flat=g(V,\cdot),
\qquad
\alpha^\sharp\text{ is defined by }g(\alpha^\sharp,V)=\alpha(V).
$$

Physics notation often suppresses this operation. For example, the gradient of a scalar field is naturally the one-form

$$
d\phi=(\partial_\mu\phi)dx^\mu.
$$

The vector field called the gradient is

$$
\nabla\phi=(d\phi)^\sharp,
\qquad
(\nabla\phi)^\mu=g^{\mu\nu}\partial_\nu\phi.
$$

This distinction matters in curved space and in Lorentzian signature. The one-form $d\phi$ is metric-independent. The vector field $g^{\mu\nu}\partial_\nu\phi$ is metric-dependent.

## Volume forms and integration

On an oriented pseudo-Riemannian manifold, the metric determines a volume form

$$
\operatorname{vol}_g
=\sqrt{|g|}\,dx^1\wedge\cdots\wedge dx^n
$$

in an oriented coordinate chart. In Lorentzian spacetime with coordinates $x^0,x^1,\ldots,x^{n-1}$, we usually write

$$
\operatorname{vol}_g
=\sqrt{|g|}\,d^nx.
$$

The absolute value in $|g|$ is essential in indefinite signature. For flat mostly-minus Minkowski space in four dimensions,

$$
\det(\eta)=-1,
\qquad
\sqrt{|\det\eta|}=1.
$$

The scalar action on a curved Lorentzian background is written

$$
S[\phi;g]
=\int_M d^nx\sqrt{|g|}\,
\left[
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-\frac12 m^2\phi^2
\right]
$$

for the mostly-minus convention. In Riemannian signature, the standard positive Euclidean action is instead

$$
S_E[\phi;g]
=\int_M d^nx\sqrt{g}\,
\left[
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
+\frac12 m^2\phi^2
\right].
$$

Notice the sign of the mass term. Lorentzian actions enter path integrals as $e^{iS}$, while Euclidean actions enter as $e^{-S_E}$.

## Hodge star

The Hodge star is the metric-dependent map

$$
\star:\Omega^k(M)\to\Omega^{n-k}(M).
$$

It is defined by the requirement that, for $k$-forms $\alpha$ and $\beta$,

$$
\alpha\wedge\star\beta
=\langle \alpha,\beta\rangle_g\operatorname{vol}_g.
$$

In coordinates, if

$$
\alpha=\frac1{k!}\alpha_{\mu_1\cdots\mu_k}
 dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_k},
$$

then

$$
(\star\alpha)_{\nu_1\cdots\nu_{n-k}}
=\frac{\sqrt{|g|}}{k!}\,
\epsilon_{\nu_1\cdots\nu_{n-k}\mu_1\cdots\mu_k}
\alpha^{\mu_1\cdots\mu_k},
$$

where indices on $\alpha$ are raised with $g^{\mu\nu}$ and $\epsilon$ is the coordinate Levi-Civita symbol in the chosen orientation.

For a metric with $q$ negative directions,

$$
\star\star\alpha=(-1)^{k(n-k)+q}\alpha
$$

on $k$-forms. In four-dimensional Lorentzian signature, $q$ is odd for either mostly-minus or mostly-plus conventions, so on two-forms

$$
\star\star F=-F.
$$

This is why real self-dual two-forms are natural in Euclidean four-dimensional geometry but need complexification in Lorentzian four-dimensional geometry.

The Hodge star is the quiet engine behind many compact QFT formulas. Maxwell theory can be written

$$
S[A]=-\frac1{2g^2}\int F\wedge\star F
$$

in Lorentzian signature with mostly-minus convention, up to trace normalization for non-Abelian gauge theory. The Yang–Mills equation without sources is

$$
D\star F=0,
$$

while the Bianchi identity is

$$
DF=0.
$$

The two equations look almost identical in differential-form notation, but only the first uses the metric.

## The Levi–Civita connection

A connection on $TM$ has Christoffel symbols $\Gamma^\rho{}_{\mu\nu}$ defined by

$$
\nabla_\mu V^\rho
=\partial_\mu V^\rho+\Gamma^\rho{}_{\mu\sigma}V^\sigma.
$$

The torsion tensor is

$$
T^\rho{}_{\mu\nu}
=\Gamma^\rho{}_{\mu\nu}-\Gamma^\rho{}_{\nu\mu}.
$$

A metric $g$ determines a unique connection satisfying

$$
\nabla_\rho g_{\mu\nu}=0,
\qquad
T^\rho{}_{\mu\nu}=0.
$$

This is the **Levi–Civita connection**. Its Christoffel symbols are

$$
\Gamma^\rho{}_{\mu\nu}
=\frac12 g^{\rho\sigma}
\left(
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\mu\sigma}
-\partial_\sigma g_{\mu\nu}
\right).
$$

Two warnings are worth making early.

First, $\Gamma^\rho{}_{\mu\nu}$ is not a tensor. It can vanish at a point in a suitable coordinate system, but curvature cannot be transformed away if it is nonzero.

Second, the symbol $\nabla$ is overloaded in physics. It may mean a spatial gradient, a covariant derivative, a gauge-covariant derivative, or the Levi–Civita connection. Here $\nabla$ means the Levi–Civita covariant derivative unless another bundle connection is explicitly included.

For a one-form $\alpha_\nu$,

$$
\nabla_\mu\alpha_\nu
=\partial_\mu\alpha_\nu-\Gamma^\rho{}_{\mu\nu}\alpha_\rho.
$$

For a general tensor, $\nabla_\mu$ adds a $+\Gamma$ term for every upper index and a $-\Gamma$ term for every lower index.

## Curvature convention

Our curvature convention is

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

With this convention,

$$
R^\rho{}_{\sigma\mu\nu}
=\partial_\mu\Gamma^\rho{}_{\nu\sigma}
-\partial_\nu\Gamma^\rho{}_{\mu\sigma}
+\Gamma^\rho{}_{\mu\lambda}\Gamma^\lambda{}_{\nu\sigma}
-\Gamma^\rho{}_{\nu\lambda}\Gamma^\lambda{}_{\mu\sigma}.
$$

Lowering the first index gives

$$
R_{\rho\sigma\mu\nu}=g_{\rho\lambda}R^\lambda{}_{\sigma\mu\nu}.
$$

For the Levi–Civita connection, the Riemann tensor obeys

$$
R_{\rho\sigma\mu\nu}=-R_{\sigma\rho\mu\nu},
\qquad
R_{\rho\sigma\mu\nu}=-R_{\rho\sigma\nu\mu},
$$

and

$$
R_{\rho\sigma\mu\nu}=R_{\mu\nu\rho\sigma}.
$$

It also obeys the first Bianchi identity

$$
R^\rho{}_{[\sigma\mu\nu]}=0,
$$

and the differential Bianchi identity

$$
\nabla_{[\lambda}R^\rho{}_{|\sigma|\mu\nu]}=0.
$$

In form language, the curvature two-form of the Levi–Civita connection is

$$
\mathcal R^a{}_b
=d\omega^a{}_b+\omega^a{}_c\wedge\omega^c{}_b,
$$

where $\omega^a{}_b$ is the connection one-form in an orthonormal frame. The local frame and coordinate conventions must be matched carefully; this is exactly where sign conventions in gravity and QFT like to stage tiny coups.

## Curvature contractions

The Ricci tensor is the contraction

$$
R_{\mu\nu}=R^\rho{}_{\mu\rho\nu}.
$$

The scalar curvature is

$$
R=g^{\mu\nu}R_{\mu\nu}.
$$

The Einstein tensor is

$$
G_{\mu\nu}=R_{\mu\nu}-\frac12 g_{\mu\nu}R.
$$

With the curvature convention above, changing to the opposite Riemann convention flips the signs of $R^\rho{}_{\sigma\mu\nu}$, $R_{\mu\nu}$, $R$, and $G_{\mu\nu}$, provided the Ricci contraction convention is held fixed. Some authors also change the Ricci contraction, so always check the definitions, not just the words “Riemann tensor.”

For QFT, these contractions enter in several recurring places:

$$
\int d^nx\sqrt{|g|}\,R
$$

is the Einstein–Hilbert term;

$$
\int d^nx\sqrt{|g|}\,\xi R\phi^2
$$

is the nonminimal scalar curvature coupling; and curvature invariants such as

$$
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma},
\qquad
R_{\mu\nu}R^{\mu\nu},
\qquad
R^2
$$

appear in heat-kernel coefficients, counterterms in curved backgrounds, trace anomalies, and effective gravitational actions.

## Laplacians and wave operators

For a scalar function $f$, the metric Laplacian is

$$
\Delta_g f
=\nabla_\mu\nabla^\mu f
=\frac1{\sqrt{|g|}}\partial_\mu
\left(\sqrt{|g|}g^{\mu\nu}\partial_\nu f\right).
$$

In Lorentzian signature, this operator is usually called the d’Alembertian or wave operator and is written

$$
\Box_g f=\nabla_\mu\nabla^\mu f.
$$

In flat mostly-minus spacetime,

$$
\Box=\partial_t^2-\nabla^2.
$$

In Riemannian signature, mathematicians often define a positive Laplacian with an additional minus sign, depending on convention. In QFT, one must check whether the kinetic operator is written as $-\Delta_g+m^2$, $\Delta_g+m^2$, or another sign-normalized version. The operator that appears in the Gaussian path integral is the thing that matters.

On differential forms, the codifferential is

$$
d^\dagger=(-1)^{n(k+1)+q+1}\star d\star
$$

on $k$-forms for a metric with $q$ negative directions, up to convention choices for the inner product in indefinite signature. The Hodge Laplacian is

$$
\Delta_H=dd^\dagger+d^\dagger d.
$$

On Riemannian manifolds this is elliptic. On Lorentzian manifolds the corresponding wave operators are hyperbolic. That analytic distinction is enormous: elliptic problems behave like boundary-value problems; hyperbolic problems behave like initial-value problems.

## Causal structure in Lorentzian geometry

A Lorentzian metric does not merely assign lengths. It assigns light cones. At each point $x$, the null vectors satisfying

$$
g(V,V)=0
$$

form a cone in $T_xM$. Timelike vectors lie inside the cone; spacelike vectors lie outside.

A Lorentzian manifold is **time-orientable** if one can choose a continuous notion of future timelike direction. This is often silently assumed in QFT on curved backgrounds because positive frequency, canonical time evolution, retarded and advanced propagators, and causal support all require some causal structure.

Common causal notions include:

| Term | Meaning |
|---|---|
| Timelike curve | Tangent vector is timelike everywhere. |
| Null curve | Tangent vector is null everywhere. |
| Causal curve | Tangent vector is timelike or null. |
| Chronological future $I^+(p)$ | Points reachable from $p$ by future-directed timelike curves. |
| Causal future $J^+(p)$ | Points reachable from $p$ by future-directed causal curves. |
| Globally hyperbolic spacetime | A Lorentzian spacetime with well-behaved Cauchy surfaces and causal propagation. |

For many field-theory constructions, global hyperbolicity is the clean condition. It ensures that wave equations have well-posed initial-value problems and that advanced and retarded Green functions behave properly.

Euclidean QFT has no causal cones. It can encode Lorentzian QFT through analytic continuation when reflection positivity and other reconstruction conditions hold, but the Euclidean metric itself does not know what is timelike.

## Vielbeins and local orthonormal frames

A vielbein is a local orthonormal coframe

$$
e^a=e^a{}_{\mu}dx^\mu
$$

satisfying

$$
g_{\mu\nu}=e^a{}_{\mu}e^b{}_{\nu}\eta_{ab}.
$$

Here $\eta_{ab}$ is the flat metric in the chosen signature. In four-dimensional mostly-minus Lorentzian signature,

$$
\eta_{ab}=\operatorname{diag}(+1,-1,-1,-1).
$$

The inverse vielbein $e_a{}^\mu$ satisfies

$$
e_a{}^\mu e^a{}_{\nu}=\delta^\mu{}_{\nu},
\qquad
 e_a{}^\mu e^b{}_{\mu}=\delta_a{}^b.
$$

Coordinate and local-frame gamma matrices are related by

$$
\gamma^\mu(x)=e_a{}^\mu(x)\gamma^a,
$$

so that

$$
\{\gamma^\mu(x),\gamma^\nu(x)\}=2g^{\mu\nu}(x).
$$

This is the bridge from metric geometry to spinor fields. A vielbein exists locally on any pseudo-Riemannian manifold, but global spinor fields require additional topology: a spin structure.

The Levi–Civita connection can be expressed in the orthonormal frame by the spin connection one-forms $\omega^a{}_b$, determined by the torsion-free Cartan equation

$$
de^a+\omega^a{}_b\wedge e^b=0.
$$

Metric compatibility gives

$$
\omega_{ab}=-\omega_{ba}.
$$

The curvature two-form is

$$
\mathcal R^a{}_b=d\omega^a{}_b+\omega^a{}_c\wedge\omega^c{}_b.
$$

Spinors use this connection through the spin representation. That is the next page’s job.

## Metrics in QFT

The metric appears in QFT in at least six distinct roles.

**Kinetic terms.** For a scalar field, the kinetic term is

$$
\frac12\sqrt{|g|}\,g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi.
$$

For a gauge field, the kinetic term uses the Hodge star:

$$
-\frac1{2g_{\text{YM}}^2}\operatorname{tr}(F\wedge\star F)
$$

in Lorentzian signature. For fermions, the metric enters through vielbeins and the spin connection.

**Propagators.** Free propagators are inverses of differential operators built from the metric. In flat space this gives momentum denominators such as

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

On curved backgrounds, the inverse operator is a Green function of an operator such as $\Box_g+m^2+\xi R$.

**Stress tensors.** The stress tensor is defined by varying the action with respect to the metric. With the mostly-minus Lorentzian scalar-action convention used on this site, a convenient convention is

$$
T_{\mu\nu}=\frac{2}{\sqrt{|g|}}\frac{\delta S}{\delta g^{\mu\nu}}.
$$

Equivalently, $\delta S=\frac12\int\sqrt{|g|}\,T_{\mu\nu}\delta g^{\mu\nu}$. Some authors use the opposite sign, especially with mostly-plus signature or different action conventions. Always check the variational definition, not only the displayed formula.

**Curved-background counterterms.** Even if gravity is treated as nondynamical, renormalization in curved backgrounds generates curvature-dependent counterterms. For scalar fields this includes $R\phi^2$; for vacuum terms it includes curvature-squared invariants.

**Anomalies.** Trace anomalies and gravitational anomalies are expressed in terms of curvature invariants and characteristic classes. The signs depend on curvature conventions.

**Euclidean methods.** Instantons, heat kernels, zeta regularization, thermal field theory, and statistical mechanics often use Riemannian metrics. Analytic continuation from Lorentzian signature is powerful, but not automatic.

## Example: scalar field on a curved background

Consider a real scalar field with Lorentzian action

$$
S[\phi;g]
=\int d^nx\sqrt{|g|}\,
\left[
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-\frac12 m^2\phi^2
-\frac12\xi R\phi^2
\right].
$$

Varying with respect to $\phi$ and integrating by parts gives

$$
\delta S
=-\int d^nx\sqrt{|g|}\,
\delta\phi
\left(
\Box_g+m^2+\xi R
\right)\phi
+\text{boundary terms}.
$$

Therefore the equation of motion is

$$
(\Box_g+m^2+\xi R)\phi=0
$$

with the mostly-minus convention and the action sign chosen above.

In flat space with $R=0$, this becomes

$$
(\partial_t^2-\nabla^2+m^2)\phi=0,
$$

the Klein–Gordon equation in the default convention.

The coefficient $\xi$ is not decorative. In $n$ dimensions, the conformal scalar coupling is

$$
\xi=\frac{n-2}{4(n-1)}.
$$

In four dimensions this gives $\xi=1/6$.

## Example: Maxwell theory and the Hodge star

Let $A$ be a $U(1)$ gauge potential and

$$
F=dA.
$$

In four-dimensional Lorentzian signature, Maxwell theory can be written

$$
S[A]=-\frac1{2e^2}\int F\wedge\star F.
$$

The Bianchi identity is metric-independent:

$$
dF=0.
$$

The equation of motion is metric-dependent:

$$
d\star F=0.
$$

This split is conceptually useful. The statement $F=dA$ and the identity $dF=0$ know about differential forms, but not distances. The Hodge star knows the metric and turns the two-form $F$ into another two-form $\star F$ in four dimensions.

In components, the action is proportional to

$$
-\frac1{4e^2}\int d^4x\sqrt{|g|}\,F_{\mu\nu}F^{\mu\nu}.
$$

The sign is chosen so that the Hamiltonian density is positive in mostly-minus Lorentzian signature. In Euclidean signature the standard action is positive:

$$
S_E[A]=\frac1{2e^2}\int F\wedge\star F.
$$

## Example: stress tensor from metric variation

Let $S[\Phi;g]$ be an action for fields $\Phi$ on a background metric $g$. The stress tensor measures the response to a metric variation.

With the mostly-minus Lorentzian convention used here,

$$
\delta S
=\frac12\int d^nx\sqrt{|g|}\,T_{\mu\nu}\delta g^{\mu\nu},
$$

so

$$
T_{\mu\nu}
=\frac2{\sqrt{|g|}}\frac{\delta S}{\delta g^{\mu\nu}}.
$$

For the minimally coupled scalar action

$$
S=\int d^nx\sqrt{|g|}\,
\left[
\frac12 g^{\rho\sigma}\partial_\rho\phi\partial_\sigma\phi
-V(\phi)
\right],
$$

this gives

$$
T_{\mu\nu}
=\partial_\mu\phi\partial_\nu\phi
-g_{\mu\nu}\left(
\frac12 g^{\rho\sigma}\partial_\rho\phi\partial_\sigma\phi
-V(\phi)
\right),
$$

up to the overall convention for the action and stress-tensor definition. In flat mostly-minus spacetime, the energy density is positive for the usual scalar potential.

The stress tensor is therefore not just “Noether’s translation current.” On curved backgrounds, it is the operator coupled to the metric.

## Euclidean continuation and signature warnings

Many QFT calculations move between Lorentzian and Euclidean signature. In flat space, one often writes

$$
t=-i\tau
$$

or equivalently rotates the energy contour. Under this continuation, the phase $e^{iS}$ becomes the damping factor $e^{-S_E}$ when the theory is well behaved.

But several things can go wrong if one rotates formulas by eye.

The Hodge star changes its square. In four dimensions,

$$
\star^2=-1
$$

on Lorentzian two-forms, while

$$
\star^2=+1
$$

on Euclidean two-forms. Thus self-dual instantons are naturally Euclidean objects.

Gamma matrices change their Hermiticity properties. The Lorentzian Clifford algebra

$$
\{\gamma^a,\gamma^b\}=2\eta^{ab}
$$

is not the same real algebra as the Euclidean one with positive definite metric.

Causal propagators do not exist in Euclidean signature. Euclidean Green functions can reconstruct Lorentzian Wightman functions only under analytic and positivity assumptions.

Finally, not every Lorentzian spacetime has a useful global Euclidean section, and not every Euclidean manifold has a physically meaningful Lorentzian continuation. Wick rotation is a method, not a magic passport.

## Common pitfalls

**A metric is not a coordinate system.** Coordinates label points locally. A metric is a tensor field. You can use terrible coordinates on flat space or elegant coordinates on curved space.

**Christoffel symbols are not tensors.** They can vanish at a point in normal coordinates. Curvature cannot be transformed away if it is nonzero.

**The Hodge star is metric-dependent.** Differential forms and the exterior derivative do not need a metric. The Hodge star does.

**Lorentzian and Euclidean signatures are not interchangeable.** Signs in the action, Hodge star, gamma matrices, self-duality equations, positivity conditions, and propagator prescriptions all change.

**Curvature signs are convention-dependent.** Always check whether a source defines $R$ through $[\nabla_\mu,\nabla_\nu]$ or $[\nabla_\nu,\nabla_\mu]$.

**Vielbeins introduce local Lorentz redundancy.** The metric $g_{\mu\nu}$ is invariant under local rotations or boosts of the frame index $a$. A vielbein has more components than the metric because it includes this gauge redundancy.

**Flat connection is not flat metric.** A connection with zero curvature is locally pure gauge. A metric with zero Riemann curvature is locally isometric to flat space. These are parallel ideas, not the same object.

**The scalar curvature $R$ is not the curvature two-form.** The symbol $R$ is abused mercilessly. It may denote a scalar curvature, a Riemann tensor, a curvature two-form, a representation, or a radial coordinate. Be kind to your future self and specify it.

## Exercises

### Exercise 1: Derive the Christoffel formula

Assume a connection is torsion-free and metric-compatible:

$$
\Gamma^\rho{}_{\mu\nu}=\Gamma^\rho{}_{\nu\mu},
\qquad
\nabla_\rho g_{\mu\nu}=0.
$$

Derive

$$
\Gamma^\rho{}_{\mu\nu}
=\frac12 g^{\rho\sigma}
\left(
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\mu\sigma}
-\partial_\sigma g_{\mu\nu}
\right).
$$

<details><summary><strong>Solution</strong></summary>

Metric compatibility gives

$$
\partial_\rho g_{\mu\nu}
=\Gamma^\lambda{}_{\rho\mu}g_{\lambda\nu}
+\Gamma^\lambda{}_{\rho\nu}g_{\mu\lambda}.
$$

Lower the first Christoffel index:

$$
\Gamma_{\alpha\mu\nu}=g_{\alpha\rho}\Gamma^\rho{}_{\mu\nu}.
$$

Then

$$
\partial_\rho g_{\mu\nu}
=\Gamma_{\nu\rho\mu}+\Gamma_{\mu\rho\nu}.
$$

Write the three equations obtained by cyclically permuting $\rho,\mu,\nu$:

$$
\partial_\mu g_{\nu\sigma}=\Gamma_{\sigma\mu\nu}+\Gamma_{\nu\mu\sigma},
$$

$$
\partial_\nu g_{\mu\sigma}=\Gamma_{\sigma\nu\mu}+\Gamma_{\mu\nu\sigma},
$$

$$
\partial_\sigma g_{\mu\nu}=\Gamma_{\nu\sigma\mu}+\Gamma_{\mu\sigma\nu}.
$$

Using torsion-freeness in the last two indices,

$$
\Gamma_{\sigma\mu\nu}=\Gamma_{\sigma\nu\mu},
$$

we combine the first two equations and subtract the third:

$$
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\mu\sigma}
-\partial_\sigma g_{\mu\nu}
=2\Gamma_{\sigma\mu\nu}.
$$

Raising $\sigma$ gives the formula.

</details>

### Exercise 2: Flat-space wave operator

Using the mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

show that

$$
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

<details><summary><strong>Solution</strong></summary>

We have

$$
\partial_\mu=(\partial_t,\partial_i),
\qquad
\partial^\mu=\eta^{\mu\nu}\partial_\nu=(\partial_t,-\partial_i).
$$

Therefore

$$
\partial_\mu\partial^\mu
=\partial_t^2-\sum_{i=1}^3\partial_i^2
=\partial_t^2-\nabla^2.
$$

</details>

### Exercise 3: Hodge star square in four dimensions

Use

$$
\star\star\alpha=(-1)^{k(n-k)+q}\alpha
$$

on $k$-forms for a metric with $q$ negative directions. Compute $\star^2$ on two-forms in four-dimensional Euclidean and Lorentzian signature.

<details><summary><strong>Solution</strong></summary>

For Euclidean signature, $n=4$, $k=2$, and $q=0$. Thus

$$
(-1)^{k(n-k)+q}=(-1)^{2\cdot2}=+1.
$$

So

$$
\star^2=+1
$$

on two-forms.

For four-dimensional Lorentzian signature, $q$ is odd: $q=3$ in mostly-minus convention and $q=1$ in mostly-plus convention. Therefore

$$
(-1)^{2\cdot2+q}=-1.
$$

So

$$
\star^2=-1
$$

on two-forms.

</details>

### Exercise 4: Scalar equation of motion

Starting from

$$
S[\phi;g]
=\int d^nx\sqrt{|g|}\,
\left[
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-\frac12 m^2\phi^2
\right],
$$

show that the equation of motion is

$$
(\Box_g+m^2)\phi=0.
$$

<details><summary><strong>Solution</strong></summary>

Vary the action:

$$
\delta S
=\int d^nx\sqrt{|g|}\,
\left[
 g^{\mu\nu}\partial_\mu\phi\partial_\nu\delta\phi
-m^2\phi\delta\phi
\right].
$$

Integrate the first term by parts:

$$
\int d^nx\sqrt{|g|}\,g^{\mu\nu}\partial_\mu\phi\partial_\nu\delta\phi
=
-\int d^nx\,\delta\phi\,
\partial_\nu\left(\sqrt{|g|}g^{\mu\nu}\partial_\mu\phi\right)
$$

up to boundary terms. Relabeling indices and using

$$
\Box_g\phi
=\frac1{\sqrt{|g|}}\partial_\mu
\left(\sqrt{|g|}g^{\mu\nu}\partial_\nu\phi\right),
$$

we obtain

$$
\delta S
=-\int d^nx\sqrt{|g|}\,\delta\phi(\Box_g+m^2)\phi
$$

up to boundary terms. Requiring $\delta S=0$ for arbitrary $\delta\phi$ gives

$$
(\Box_g+m^2)\phi=0.
$$

</details>

### Exercise 5: Maxwell equations in form language

Let $F=dA$ on a four-dimensional oriented Lorentzian manifold. Show that the source-free Maxwell equations are

$$
dF=0,
\qquad
 d\star F=0.
$$

Which equation uses the metric?

<details><summary><strong>Solution</strong></summary>

The first equation follows from $F=dA$ and $d^2=0$:

$$
dF=d^2A=0.
$$

This identity uses only the exterior derivative and therefore does not require a metric.

The Maxwell action is

$$
S[A]=-\frac1{2e^2}\int F\wedge\star F.
$$

Varying $A$ gives $\delta F=d\delta A$, so

$$
\delta S=-\frac1{e^2}\int d\delta A\wedge\star F.
$$

Integrating by parts gives

$$
\delta S=\frac1{e^2}\int \delta A\wedge d\star F
$$

up to a sign depending on degree conventions and boundary terms. The Euler–Lagrange equation is

$$
d\star F=0.
$$

This equation uses the metric because $\star$ is metric-dependent.

</details>

## Relations to other pages

[Manifolds](/math-toolkit/geometry-of-fields/manifolds/) supplies the smooth background. [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/) explain the form and integral notation used here. [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) gives the general connection theory; this page specializes it to the Levi–Civita connection. [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) uses the same curvature language for internal gauge bundles.

[Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/) explains when spinor fields can be globally defined. [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) explains the local Clifford algebra used with vielbeins. [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explains how curvature enters short-time expansions of determinants.

Later pages on Dirac operators, characteristic classes, index theorems, anomalies, instantons, and QFT in curved spacetime should link back here for metric and curvature conventions.

## Research status

The differential geometry on this page is standard. The research-sensitive issues begin when the background geometry becomes singular, dynamical, asymptotic, null, nonorientable, non-spin, or summed over in a gravitational path integral. In those settings, boundary terms, spin structures, self-adjoint extensions, anomalies, and global choices become part of the physical definition of the theory.

For ordinary smooth background-field QFT, the main practical risk is not conceptual uncertainty but convention mismatch.

## References

- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented reference for manifolds, metrics, curvature, vielbeins, spin connections, characteristic classes, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*. Geometric reference with strong intuition for forms, metrics, Hodge stars, integration, gauge fields, and physical applications.
- S. Kobayashi and K. Nomizu, *Foundations of Differential Geometry*, Vol. I. Mathematical reference for connections, curvature, frame bundles, and structure equations.
- T. Eguchi, P. B. Gilkey, and A. J. Hanson, “Gravitation, Gauge Theories and Differential Geometry.” Classic bridge between curvature conventions, gauge theory, gravity, and topology.
- R. M. Wald, *General Relativity*. Standard relativity reference for Lorentzian geometry, curvature conventions, causal structure, and stress tensors.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*. Classic reference for QFT on curved backgrounds.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*. Useful for stress tensors, effective actions, curvature couplings, and renormalization in curved backgrounds.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II. Useful for conventions, Lorentzian field theory, and the bridge from flat-space QFT to geometric backgrounds.

## Version history

- **2026-06-25:** Initial polished draft. Added metric signatures, raising and lowering, volume forms, Hodge star, Levi–Civita connection, curvature convention, curvature contractions, Laplacians, causal structure, vielbeins, QFT applications, examples, exercises, and figure.
