---
title: "Manifolds"
description: "Introduces smooth manifolds as coordinate-independent spaces for QFT, including charts, atlases, tangent spaces, maps, submanifolds, boundaries, and the difference between geometric objects and their components."
sidebar:
  label: "Manifolds"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard differential-geometry references for physicists, including Nakahara, Frankel, Lee, Bott–Tu, and geometry sections of modern QFT texts."
topics:
  - manifolds
  - charts and atlases
  - tangent spaces
  - cotangent spaces
  - smooth maps
  - submanifolds
  - boundaries
  - coordinate invariance
canonicalTopics:
  - smooth-manifolds
  - charts-and-atlases
  - tangent-space
  - cotangent-space
  - smooth-maps
  - submanifolds
  - manifolds-with-boundary
researchStatus:
  established:
    - "Smooth manifolds, tangent and cotangent spaces, smooth maps, submanifolds, and manifolds with boundary are standard foundational objects in differential geometry and field theory."
  active:
    - "Many modern QFT applications use refinements such as orbifolds, stratified spaces, stacks, supermanifolds, derived spaces, and infinite-dimensional spaces of fields; this page stays with the finite-dimensional smooth setting."
---

## Summary

A smooth manifold is a space that can be described locally by coordinates, with smooth coordinate changes on overlaps. The object is the space $M$ itself; coordinates are temporary measuring devices. A point $p\in M$ does not come with preferred numbers attached to it. A chart assigns numbers near $p$, another chart assigns different numbers, and the transition map tells us how to translate.

For field theory this distinction is not cosmetic. A scalar field can be a function on spacetime, but the statement that an action, equation of motion, current, or charge is meaningful should not depend on a particular coordinate system. Gauge fields, spinors, forms, stress tensors, and defects all need this basic geometric stage before the later bundle and curvature language can even begin.

The key definition is an atlas of charts

$$
\varphi_U:U\to \varphi_U(U)\subset \mathbb R^d,
$$

such that whenever two charts overlap, the transition map

$$
\varphi_V\circ \varphi_U^{-1}:\varphi_U(U\cap V)\to \varphi_V(U\cap V)
$$

is smooth. The point of the definition is not to worship coordinates; it is to make clear when a calculation written in coordinates represents a coordinate-independent statement.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Diagram of a manifold with overlapping coordinate charts, chart maps to open subsets of Euclidean space, a smooth transition map, and tangent data at a point.](/figures/math-toolkit/manifold-atlas-transition.svg)

<figcaption>

A smooth manifold is described by compatible local charts. Coordinates $x=\varphi_U(p)$ and $y=\varphi_V(p)$ are two descriptions of the same point $p\in M$, related on overlaps by the smooth transition map $\varphi_V\circ\varphi_U^{-1}$. Tangent vectors may be defined using curves through $p$ or as derivations acting on smooth functions.

</figcaption>
</figure>

The rest of the geometry chapter builds on this page. Differential forms live in exterior powers of the cotangent spaces. Bundles assign vector spaces or other fibers to each point of $M$. Connections say how to compare nearby fibers. Curvature measures the failure of parallel transport to be path independent. None of that works cleanly if $M$ itself is still being mistaken for one coordinate chart.

## Prerequisites

You should know multivariable calculus, linear algebra, and the notation fixed in [Mathematical Conventions](/math-toolkit/conventions/). The chapter overview [Geometry of Fields](/math-toolkit/geometry-of-fields/) explains why this material sits in the Mathematical Toolkit volume.

No prior differential geometry is assumed. The page uses examples from classical mechanics and QFT, but it treats them as motivation rather than prerequisites.

## Core idea

The core idea is local Euclidean structure with globally flexible gluing:

$$
\text{near every point, }M\text{ looks like }\mathbb R^d,
\qquad
\text{globally, }M\text{ need not be }\mathbb R^d.
$$

This solves a recurring problem. Physics likes local formulas; topology and geometry often live in the way local formulas are glued. A sphere is locally a plane, but not globally a plane. A thermal Euclidean time circle is locally a line, but globally periodic. A gauge field can be written in local patches, but the patching can carry physical information such as magnetic flux or instanton number.

A coordinate formula is trustworthy only if it transforms correctly under changes of chart. For example, a scalar field $\phi$ is coordinate-independent data if its chart descriptions satisfy

$$
\phi_U(x)=\phi_V(y),
\qquad
x=\varphi_U(p),\quad y=\varphi_V(p),
$$

where both sides describe the same value $\phi(p)$. A vector field, one-form, tensor, density, spinor, or connection has a different transformation law. Much of geometry is disciplined bookkeeping of what kind of object is being written down.

A useful QFT translation is:

| Geometric object | Local notation | Field-theory role |
|---|---|---|
| Point of spacetime | $p\in M$ or coordinates $x^\mu$ | event or insertion point |
| Smooth function | $f(x)$ | scalar background or scalar field |
| Tangent vector | $X=X^\mu\partial_\mu$ | infinitesimal displacement, flow, symmetry generator |
| Cotangent vector | $\alpha=\alpha_\mu dx^\mu$ | gradient, momentum covector, one-form field |
| Tensor field | $T^{\mu\cdots}{}_{\nu\cdots}(x)$ | stress tensor, metric, response tensor |
| Submanifold | $\Sigma\subset M$ | worldline, worldsheet, boundary, defect support |
| Manifold with boundary | $\partial M\neq\varnothing$ | boundary QFT, variational boundary terms |

The table is deliberately local. The later pages on differential forms and bundles explain which objects integrate naturally, which require a metric, and which are globally sections rather than functions.

## Topological and smooth manifolds

A **topological manifold** of dimension $d$ is a topological space $M$ such that every point has an open neighborhood homeomorphic to an open subset of $\mathbb R^d$. In most physics applications one also assumes that $M$ is Hausdorff and second countable. These technical conditions remove pathological spaces where limits and coordinate patches behave badly.

A **smooth manifold** is a topological manifold equipped with a maximal smooth atlas. This means that the allowed coordinate charts have smooth transition maps on overlaps, and all charts compatible with the atlas are considered part of the same smooth structure.

A chart is a pair $(U,\varphi_U)$, where $U\subset M$ is open and

$$
\varphi_U:U\to \varphi_U(U)\subset\mathbb R^d
$$

is a homeomorphism onto an open subset of Euclidean space. The chart coordinates are often written

$$
\varphi_U(p)=(x^1(p),\ldots,x^d(p)).
$$

If $(U,\varphi_U)$ and $(V,\varphi_V)$ overlap, then the coordinate change is

$$
\varphi_V\circ\varphi_U^{-1}:\varphi_U(U\cap V)\to \varphi_V(U\cap V).
$$

For a smooth atlas, every such transition map is $C^\infty$, and its inverse is also smooth. In physics we usually say simply “manifold” when we mean a smooth manifold.

The local dimension $d$ is fixed. A two-dimensional surface and a four-dimensional spacetime are both manifolds, but not manifolds of the same dimension. Dimension is an intrinsic property: it does not depend on how you draw or embed the space.

## Examples

The easiest example is $\mathbb R^d$ with its global coordinate chart. Most perturbative flat-space QFT takes spacetime to be $\mathbb R^{1,3}$ or its Euclidean continuation $\mathbb R^4$, but the underlying smooth manifold is just $\mathbb R^4$; the Lorentzian or Euclidean metric is additional structure.

The circle $S^1$ is a one-dimensional manifold. It cannot be covered by one periodic angle chart without a seam, because a chart must map to an open subset of $\mathbb R$. Instead one uses at least two overlapping charts. The familiar coordinate $\theta$ is useful, but the point $\theta=0$ and the point $\theta=2\pi$ are the same point of $S^1$, not two distinct endpoints.

The sphere $S^2$ is a two-dimensional manifold. Stereographic charts from the north and south poles give two coordinate patches. The transition map on the overlap is smooth. No single smooth coordinate chart covers the whole sphere without coordinate singularities. That is not a flaw of $S^2$; it is the whole point of charts.

The torus $T^d$ can be described as

$$
T^d=\mathbb R^d/(2\pi\mathbb Z)^d.
$$

It appears constantly in finite-temperature field theory, compactification, lattice momentum spaces, theta angles, and periodic boundary conditions. Locally it looks like $\mathbb R^d$; globally it has noncontractible cycles.

Lie groups are manifolds with compatible multiplication and inverse maps. The groups $U(1)$, $SU(2)$, $SU(N)$, $SO(N)$, and $Spin(N)$ are all smooth manifolds, and the compatibility with group multiplication is what makes them Lie groups. This is why group theory and geometry meet so early in gauge theory.

Configuration spaces are often manifolds after removing singular or coincident configurations. For $n$ distinct particles moving on a manifold $X$, the ordered configuration space is

$$
\operatorname{Conf}_n(X)=\{(x_1,\ldots,x_n)\in X^n\mid x_i\neq x_j\text{ for }i\neq j\}.
$$

Taking quotients by particle exchange leads to configuration spaces relevant for identical particles, braid groups, and anyonic statistics.

Spacetimes with boundaries, such as a half-space or a cylinder with initial and final time slices, are modeled by manifolds with boundary. Defects and branes are often represented by embedded submanifolds inside spacetime.

## Non-examples and generalizations

The tip of a cone is not a smooth manifold point in the ordinary sense. Away from the tip, the cone is locally smooth, but at the tip there is no neighborhood smoothly equivalent to an open subset of $\mathbb R^2$. Physics often uses such spaces anyway, for example in orbifolds, conical defects, replica geometries, and cosmic strings. Then one must say what generalized category of spaces is being allowed.

The union of two coordinate axes crossing in the plane is not a one-dimensional manifold at the crossing. A neighborhood of the crossing has four branches, unlike an interval. Such singular spaces appear naturally as nodal varieties or stratified spaces, but they are not smooth manifolds.

An interval $[0,1]$ is not a manifold without boundary, because neighborhoods of endpoints look like half-lines, not open intervals. It is a one-dimensional manifold with boundary. Boundary points are not defects; they are part of a slightly enlarged definition.

Infinite-dimensional spaces of fields are not finite-dimensional manifolds of the kind defined here. A field space may carry manifold-like, functional-analytic, or derived structure, but it requires more care. In this volume, finite-dimensional spacetime manifolds come first; field spaces are treated through functional derivatives, path integrals, and later geometric refinements.

## Smooth functions and coordinate descriptions

A smooth function on $M$ is a map

$$
f:M\to\mathbb R
$$

such that in every chart the coordinate representative

$$
f_U=f\circ\varphi_U^{-1}:\varphi_U(U)\to\mathbb R
$$

is an ordinary smooth function of $d$ real variables.

This definition is coordinate-independent because smoothness is preserved under smooth chart changes. On an overlap,

$$
f_V=f_U\circ \varphi_U\circ\varphi_V^{-1}.
$$

If $f_U$ is smooth and the transition maps are smooth, then $f_V$ is smooth. The calculation is mundane, but the lesson is not: a property is geometrically meaningful only if it survives changes of chart.

A scalar field on a fixed spacetime manifold is, at this level, just a smooth function or a generalized function on $M$:

$$
\phi:M\to\mathbb R
$$

or $\phi:M\to\mathbb C$, depending on the theory. Local coordinates let us write $\phi(x)$, but the geometric field is not the coordinate expression; it is the function whose coordinate expression is $\phi_U(x)=\phi(\varphi_U^{-1}(x))$.

For quantum fields, smooth functions are often too naive: fields become operator-valued distributions, and path integrals sum over rough configurations. Still, the underlying geometric typing remains the same. A scalar quantum field is distributional scalar data on $M$; it is not a vector or form merely because it has an $x$ in its argument.

## Smooth maps and diffeomorphisms

A map $F:M\to N$ between smooth manifolds is smooth if its coordinate representatives are smooth:

$$
\psi\circ F\circ\varphi^{-1}:\varphi(U)\to\psi(V),
$$

where $\varphi$ is a chart on $M$ and $\psi$ is a chart on $N$.

A diffeomorphism is a bijective smooth map whose inverse is also smooth. If $M$ and $N$ are diffeomorphic, they are the same as smooth manifolds. They may still carry different metrics, connections, bundles, boundary conditions, or field configurations.

This distinction is central in generally covariant theories. A bare smooth manifold does not know distances, angles, light cones, or volume. A Lorentzian spacetime is more data:

$$
(M,g,\text{orientation, time orientation, possibly spin structure, fields}).
$$

A diffeomorphism of $M$ can be passive, as a change of coordinates, or active, as a map moving geometric fields on the manifold. Both views use the same mathematics, but their physical interpretations differ. Mixing them is a reliable way to grow sign errors and philosophical weeds.

## Tangent spaces

The tangent space $T_pM$ is the vector space of infinitesimal directions at $p$. There are several equivalent definitions. Two are especially useful in field theory.

First, a tangent vector can be defined by a curve. Let

$$
\gamma:(-\epsilon,\epsilon)\to M,
\qquad
\gamma(0)=p.
$$

In a chart $x^\mu$, the curve has coordinate functions $x^\mu(\gamma(t))$. Its velocity at $p$ has components

$$
\left.\frac{d}{dt}x^\mu(\gamma(t))\right|_{t=0}.
$$

Two curves represent the same tangent vector if these derivatives agree in one chart, and therefore in all compatible charts.

Second, a tangent vector can be defined as a derivation at $p$. This is a linear map

$$
X_p:C^\infty(M)\to\mathbb R
$$

obeying the Leibniz rule

$$
X_p(fg)=X_p(f)g(p)+f(p)X_p(g).
$$

The curve definition and the derivation definition agree because a curve differentiates functions by

$$
X_p(f)=\left.\frac{d}{dt}f(\gamma(t))\right|_{t=0}.
$$

In local coordinates, a tangent vector is written

$$
X_p=X^\mu\left.\frac{\partial}{\partial x^\mu}\right|_p.
$$

Here $\partial/\partial x^\mu|_p$ is the coordinate basis of $T_pM$. The components $X^\mu$ depend on the chart; the vector $X_p$ does not.

Under a coordinate change $y^a=y^a(x)$,

$$
\frac{\partial}{\partial x^\mu}
=
\frac{\partial y^a}{\partial x^\mu}\frac{\partial}{\partial y^a},
$$

so the components transform as

$$
Y^a=\frac{\partial y^a}{\partial x^\mu}X^\mu.
$$

This transformation law is what makes a vector field different from a list of $d$ scalar fields.

## Cotangent spaces and one-forms

The cotangent space $T_p^*M$ is the dual vector space to $T_pM$. Its elements are covectors or one-forms at $p$. A covector eats a tangent vector and returns a number:

$$
\alpha_p:T_pM\to\mathbb R.
$$

In coordinates, the dual basis is written $dx^\mu|_p$, with

$$
dx^\mu\left(\frac{\partial}{\partial x^\nu}\right)=\delta^\mu_\nu.
$$

A covector has local expression

$$
\alpha_p=\alpha_\mu dx^\mu|_p.
$$

Under $y^a=y^a(x)$,

$$
dy^a=\frac{\partial y^a}{\partial x^\mu}dx^\mu,
$$

and the components transform oppositely to vector components. This is why upper and lower indices matter before a metric is introduced.

For any smooth function $f$, its differential is a one-form

$$
df=\frac{\partial f}{\partial x^\mu}dx^\mu.
$$

It acts on a vector $X$ by directional differentiation:

$$
df(X)=X(f).
$$

This formula is more fundamental than the coordinate gradient. The gradient vector $\nabla f$ requires a metric to identify $df$ with a vector. The differential $df$ does not.

## Tangent and cotangent bundles

The tangent bundle is the disjoint union of all tangent spaces:

$$
TM=\bigsqcup_{p\in M}T_pM.
$$

The cotangent bundle is

$$
T^*M=\bigsqcup_{p\in M}T_p^*M.
$$

A vector field is a smooth section of the tangent bundle:

$$
X\in\Gamma(TM).
$$

A one-form field is a smooth section of the cotangent bundle:

$$
\alpha\in\Gamma(T^*M).
$$

This is the first appearance of a general pattern: a field assigns something to each point of spacetime, and the assignment should vary smoothly. Later, a charged matter field will be a section of an associated vector bundle, and a spinor field will be a section of a spinor bundle.

The tangent and cotangent bundles are themselves manifolds of dimension $2d$. The cotangent bundle $T^*Q$ of a configuration manifold $Q$ is the natural phase space of classical mechanics. It carries a canonical one-form and symplectic form, which is why Hamiltonian mechanics is secretly geometry all the way down.

## Pushforward and pullback

A smooth map $F:M\to N$ sends curves in $M$ to curves in $N$. Therefore it sends tangent vectors at $p$ to tangent vectors at $F(p)$. This linear map is the pushforward:

$$
F_*:T_pM\to T_{F(p)}N.
$$

In coordinates, if $y^a=F^a(x)$, then

$$
(F_*X)^a=\frac{\partial F^a}{\partial x^\mu}X^\mu.
$$

Covectors go the other way. If $\beta\in T^*_{F(p)}N$, then its pullback is a covector $F^*\beta\in T_p^*M$ defined by

$$
(F^*\beta)(X)=\beta(F_*X).
$$

For functions,

$$
F^*f=f\circ F.
$$

The pullback will become essential in the next page, because differential forms are integrated by pulling them back to parameter spaces or submanifolds. In physics notation this is the clean version of “substitute the embedding $X^\mu(\sigma)$ into the form.”

## Submanifolds and embeddings

A submanifold $\Sigma\subset M$ is a subset that is itself a manifold in a way compatible with the inclusion map

$$
i:\Sigma\hookrightarrow M.
$$

An embedded curve, surface, hypersurface, boundary, defect worldvolume, and brane worldvolume are all modeled this way in ordinary differential geometry.

For example, a particle worldline in spacetime is a one-dimensional submanifold, at least away from intersections or singular events. A Wilson line is supported on a curve. A surface operator is supported on a two-dimensional submanifold. A codimension-one interface or domain wall is supported on a hypersurface.

Local coordinates adapted to a $k$-dimensional submanifold can often be chosen so that $\Sigma$ is described by

$$
x^{k+1}=\cdots=x^d=0.
$$

The tangent space $T_p\Sigma$ then sits naturally inside $T_pM$. The normal directions require extra structure if one wants an orthogonal normal bundle; “orthogonal” needs a metric.

Submanifolds are also where integration starts to become geometric. A line integral integrates a one-form over a curve; a surface integral integrates a two-form over a surface; a spacetime action integrates a top-degree density or form over $M$.

## Manifolds with boundary

A manifold with boundary is locally modeled not only on open subsets of $\mathbb R^d$, but also on open subsets of the half-space

$$
\mathbb H^d=\{(x^1,\ldots,x^d)\in\mathbb R^d\mid x^d\geq 0\}.
$$

The boundary $\partial M$ consists of points mapped to $x^d=0$ in boundary charts. It is itself a $(d-1)$-dimensional manifold without boundary, assuming ordinary smoothness conditions.

Boundary terms in variational calculus are not bookkeeping accidents. They are the geometric trace left after integration by parts on a manifold with boundary. For an action $S[\phi]$, the variation often has the schematic form

$$
\delta S
=
\int_M \text{equations of motion}\cdot\delta\phi
+
\int_{\partial M}\text{boundary term}.
$$

The page [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) studies this from the variational side. The geometry pages explain the manifold and integration structures behind it.

Boundaries are also where QFT becomes richer. One can impose boundary conditions, add boundary degrees of freedom, study boundary conformal field theory, define edge modes in gauge theory, or examine anomaly inflow. All of these require knowing what is meant by $M$ and $\partial M$ before quantization begins.

## Metrics are extra structure

A smooth manifold by itself does not define lengths, angles, volumes, causal cones, Hodge stars, Laplacians, or kinetic energies. These require a metric.

A Riemannian metric is a smoothly varying positive-definite inner product on tangent spaces. A Lorentzian metric is a smoothly varying nondegenerate bilinear form with one time direction and $d-1$ space directions, or the opposite convention depending on signature. In the site convention for flat spacetime,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

But the underlying smooth manifold could be the same even if the metric changes. The data $(M,g)$ is richer than $M$.

This matters for index placement. Without a metric, vectors and covectors are different kinds of objects:

$$
X\in T_pM,
\qquad
\alpha\in T_p^*M.
$$

A metric gives a map between them, sometimes called musical isomorphisms:

$$
X^\flat=g_{\mu\nu}X^\nu dx^\mu,
\qquad
\alpha^\sharp=g^{\mu\nu}\alpha_\nu\frac{\partial}{\partial x^\mu}.
$$

In flat-space QFT we often identify them silently. In curved backgrounds, gauge theory, hydrodynamics, and topological field theory, silent identifications become expensive.

## Orientation and volume

Orientation is also extra structure. An orientable $d$-manifold admits a consistent choice of positive coordinate frames. If $M$ is oriented, one can integrate top-degree differential forms over $M$.

A metric on an oriented manifold gives a volume form, often written in coordinates as

$$
\operatorname{vol}_g=\sqrt{|g|}\,d^dx,
$$

where $g=\det(g_{\mu\nu})$. The expression $d^dx$ by itself is coordinate notation. The invariant object is a volume form or density.

This is the geometric reason that relativistic actions on curved spacetime use

$$
S=\int_M d^dx\,\sqrt{|g|}\,\mathcal L.
$$

In differential-form language one instead writes a top-form Lagrangian and integrates it directly. The next page develops that language.

## What QFT needs from manifolds

The minimal geometric stage for ordinary flat-space QFT is simple, but the general pattern is the same in much richer settings.

A field theory begins with a spacetime or Euclidean space $M$. Local operators are inserted at points $p\in M$. Extended operators are supported on submanifolds $\Sigma\subset M$. Correlation functions depend on the configuration of these insertions. Background fields may be functions, forms, metrics, or connections on bundles over $M$.

The action should be coordinate-independent. In local coordinates it may look like

$$
S[\phi]=\int d^dx\,\mathcal L(\phi,\partial_\mu\phi),
$$

but this expression only makes invariant sense after specifying whether $d^dx\,\mathcal L$ is a density, a top-form, or shorthand valid in a preferred flat chart.

The equations of motion should be geometric. For a scalar field, the statement $\Box\phi+m^2\phi=0$ on Minkowski space uses the flat metric. On a curved manifold it becomes a statement involving the metric Laplacian or d'Alembertian. On a gauge bundle, ordinary derivatives become covariant derivatives. On spinors, one also needs a spin connection.

The path integral also depends on global structure. A schematic expression

$$
Z=\int\mathcal D\phi\,e^{iS[\phi]}
$$

hides the choice of field space, boundary conditions, topological sectors, gauge quotient, and background structure on $M$. The manifold is not the whole story, but it is the first line of the story.

## Common pitfalls

**A manifold is not one coordinate system.** A chart is a local description. The manifold is the object described by all compatible charts. Coordinate singularities are often artifacts of a chart, not singularities of the manifold.

**A manifold is not automatically embedded in Euclidean space.** Many manifolds can be embedded in some $\mathbb R^N$, but an embedding is not part of the definition. Intrinsic geometry should not depend on how you drew the space.

**The metric is not part of the smooth manifold.** A smooth manifold defines smoothness and tangent spaces. A metric defines lengths, angles, volumes, causal cones, and the Hodge star.

**Tangent spaces at different points are different vector spaces.** In $\mathbb R^d$ we identify them by translation without thinking. On a general manifold, comparing tangent vectors at different points requires extra structure, such as a connection or a chosen path.

**Upper and lower indices are not decoration.** Before introducing a metric, vectors and covectors transform differently. Writing all objects as arrays of components hides their geometric type.

**A scalar field and a scalar density are different.** A scalar function transforms by composition. A density acquires a Jacobian factor and can be integrated in coordinates. Confusing them is a classic way to lose factors of $\sqrt{|g|}$.

**A boundary is not just a place where coordinates stop.** A manifold with boundary has a precise local model. Boundary terms, boundary conditions, and boundary degrees of freedom are geometric data.

## Worked example: the circle needs more than one chart

Let $S^1\subset\mathbb R^2$ be the unit circle. The angle $\theta$ is tempting, but the map

$$
\theta\mapsto (\cos\theta,\sin\theta)
$$

from $[0,2\pi)$ to $S^1$ is not a chart because $[0,2\pi)$ is not open in $\mathbb R$, and the seam at $0\sim2\pi$ creates a discontinuity in the inverse.

A clean atlas uses two charts. Remove the north pole for one stereographic coordinate and remove the south pole for the other. On the overlap, the transition map is smooth. Thus $S^1$ is locally one-dimensional even though it cannot be covered globally by a single smooth angle coordinate.

This is the baby version of a general lesson. Gauge potentials, spinors, and angular variables are often easy in a patch and subtle globally.

## Exercises

### Exercise 1: Coordinate change for a vector

Let $X=X^\mu\partial/\partial x^\mu$ be a tangent vector, and let $y^a=y^a(x)$ be a coordinate change. Show that the components in the $y$ coordinates are

$$
Y^a=\frac{\partial y^a}{\partial x^\mu}X^\mu.
$$

<details><summary><strong>Solution</strong></summary>

A tangent vector acts on smooth functions by directional differentiation. In the $x$ chart,

$$
X=X^\mu\frac{\partial}{\partial x^\mu}.
$$

Using the chain rule,

$$
\frac{\partial}{\partial x^\mu}
=
\frac{\partial y^a}{\partial x^\mu}\frac{\partial}{\partial y^a}.
$$

Therefore

$$
X
=
X^\mu\frac{\partial y^a}{\partial x^\mu}\frac{\partial}{\partial y^a}.
$$

Comparing with $X=Y^a\partial/\partial y^a$ gives

$$
Y^a=\frac{\partial y^a}{\partial x^\mu}X^\mu.
$$

</details>

### Exercise 2: Coordinate change for a one-form

Let $\alpha=\alpha_\mu dx^\mu=\alpha'_a dy^a$. Show that

$$
\alpha'_a=\frac{\partial x^\mu}{\partial y^a}\alpha_\mu.
$$

<details><summary><strong>Solution</strong></summary>

The differentials transform as

$$
dx^\mu=\frac{\partial x^\mu}{\partial y^a}dy^a.
$$

Substituting this into $\alpha=\alpha_\mu dx^\mu$ gives

$$
\alpha
=
\alpha_\mu\frac{\partial x^\mu}{\partial y^a}dy^a.
$$

Comparing with $\alpha=\alpha'_a dy^a$ yields

$$
\alpha'_a=\frac{\partial x^\mu}{\partial y^a}\alpha_\mu.
$$

This is the inverse Jacobian transformation, as expected for covectors.

</details>

### Exercise 3: Derivations obey the product rule

Let $\gamma(t)$ be a curve with $\gamma(0)=p$, and define

$$
X_p(f)=\left.\frac{d}{dt}f(\gamma(t))\right|_{t=0}.
$$

Show that $X_p$ obeys the Leibniz rule.

<details><summary><strong>Solution</strong></summary>

For two smooth functions $f$ and $g$,

$$
X_p(fg)
=
\left.\frac{d}{dt}\big(f(\gamma(t))g(\gamma(t))\big)\right|_{t=0}.
$$

Using the ordinary product rule in one variable,

$$
X_p(fg)
=
\left.\frac{d}{dt}f(\gamma(t))\right|_{t=0}g(\gamma(0))
+
f(\gamma(0))\left.\frac{d}{dt}g(\gamma(t))\right|_{t=0}.
$$

Since $\gamma(0)=p$, this is

$$
X_p(fg)=X_p(f)g(p)+f(p)X_p(g).
$$

Thus curve velocities define derivations.

</details>

### Exercise 4: Why $d^dx$ is not invariant by itself

Let $y=y(x)$ be an orientation-preserving coordinate change on a $d$-dimensional manifold. Show that

$$
d^dy=\det\left(\frac{\partial y}{\partial x}\right)d^dx.
$$

What must happen to a coordinate Lagrangian density if $d^dx\,\mathcal L(x)$ is to define an invariant integral?

<details><summary><strong>Solution</strong></summary>

The ordinary multivariable change-of-variables theorem gives

$$
d^dy=\det\left(\frac{\partial y}{\partial x}\right)d^dx
$$

for an orientation-preserving coordinate change. Therefore $d^dx$ is not invariant by itself. To make

$$
\int d^dx\,\mathcal L_x(x)
$$

equal to

$$
\int d^dy\,\mathcal L_y(y),
$$

the coordinate representative of the Lagrangian density must transform as

$$
\mathcal L_y(y)
=
\det\left(\frac{\partial x}{\partial y}\right)\mathcal L_x(x(y)).
$$

Equivalently, $\mathcal L_x(x)d^dx$ is a density or top-form representative. The product is the invariant object, not $d^dx$ or $\mathcal L$ separately.

</details>

## References

- M. Nakahara, *Geometry, Topology and Physics*. Useful for manifolds, tangent spaces, forms, bundles, homotopy, cohomology, gauge fields, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*. Useful for the geometric meaning of vectors, covectors, forms, integration, phase space, gauge fields, and spinors.
- J. M. Lee, *Introduction to Smooth Manifolds*. A standard mathematics reference for smooth manifolds, tangent spaces, maps, submanifolds, and manifolds with boundary.
- R. Bott and L. W. Tu, *Differential Forms in Algebraic Topology*. Useful for the manifold, form, integration, and cohomological background used later.
- B. Schutz, *Geometrical Methods of Mathematical Physics*. A compact physics-friendly reference for manifolds, vectors, forms, and integration.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for seeing how classical field theory, Green functions, spinors, gauge fields, and curved-background ideas enter QFT.

## Version history

- **2026-06-25:** Initial polished draft. Introduced smooth manifolds, charts, atlases, smooth maps, tangent and cotangent spaces, pushforwards, pullbacks, submanifolds, boundaries, metrics as extra structure, and QFT-facing pitfalls.
