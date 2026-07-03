---
title: "Gauge Fields as Connections"
description: "A geometric explanation of gauge fields as connection one-forms that define parallel transport, Wilson lines, and covariant differentiation in internal space."
sidebar:
  label: "Gauge Fields as Connections"
  order: 3
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II §15.1; Srednicki §69; Schwartz Ch. 25; Zee Part IV.5; Polyakov Ch. 1."
topics:
  - gauge fields
  - connections
  - parallel transport
  - Wilson lines
canonicalTopics:
  - gauge-connection
  - parallel-transport
  - wilson-line
researchStatus:
  established:
    - "The interpretation of gauge potentials as connections and field strengths as curvature is a standard local formulation of classical gauge theory."
  active:
    - "Global bundle topology, boundary conditions, higher-form symmetries, and the spectrum of allowed line operators add physical data beyond the local connection form."
---

## Summary

A gauge field is more than a vector field with an internal index. Locally, it is a **connection**: a rule for comparing internal vectors at neighboring spacetime points.

In this volume's convention, the covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
$$

and the connection one-form is

$$
A=A_\mu dx^\mu.
$$

A field $\psi(x)$ is not just a list of functions; it is a section of an internal vector bundle. A gauge transformation is a change of local frame in that bundle. The connection tells us how to move a vector from one fiber to another so that derivatives and finite transports are meaningful.

The finite version of this comparison along a path $C:x\to y$ is the Wilson line or parallel transporter

$$
U_C(y,x)=\mathcal P\exp\left(-ig\int_C A_\mu dz^\mu\right),
$$

which transforms as

$$
U_C(y,x)\mapsto G^{-1}(y)U_C(y,x)G(x).
$$

For a closed curve, the endpoint factors coincide, so $\operatorname{tr}_R U_C(x,x)$ is gauge invariant. This is the first appearance of Wilson loops, one of the central observables of gauge theory.

## Prerequisites

You should know [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/) and the convention $D_\mu=\partial_\mu+igA_\mu^aT^a$. The page uses basic matrix multiplication, path-ordered exponentials, and the idea that a local gauge transformation is a change of internal frame.

Differential geometry is helpful but not assumed. The page introduces the geometric words “fiber,” “section,” “connection,” “parallel transport,” and “curvature” in the narrow sense needed for gauge theory.

## Core idea

The value of a charged field at $x$ and the value of the same field at $y$ live in different internal vector spaces attached to different spacetime points. To subtract them, differentiate them, or ask whether they point in the “same internal direction,” we need a rule for comparison.

A connection is precisely such a rule.

In a chosen local frame, the rule is encoded by $A_\mu$. For an infinitesimal displacement $dx^\mu$,

$$
\psi(x)\quad\text{parallel transported to }x+dx
\quad\longmapsto\quad
\bigl(1-igA_\mu(x)dx^\mu\bigr)\psi(x).
$$

Therefore

$$
\psi(x+dx)-\bigl(1-igA_\mu dx^\mu\bigr)\psi(x)
=dx^\mu(\partial_\mu+igA_\mu)\psi(x)+O(dx^2).
$$

The covariant derivative is the infinitesimal failure of a field to be parallel transported:

$$
D_\mu\psi=0
\qquad\Longleftrightarrow\qquad
\psi\text{ is locally parallel in the }\mu\text{ direction}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![A gauge connection assigns parallel transport between internal fibers over spacetime points.](/figures/gauge-theories-standard-model/connection-parallel-transport.svg)

<figcaption>

A matter field is a section of an internal vector bundle over spacetime. The connection $A_\mu$ defines parallel transport between neighboring fibers, and the path-ordered exponential gives finite transport along a curve $C$.

</figcaption>
</figure>

## Setup and conventions

Let $M$ be spacetime, and let each point $x\in M$ carry an internal vector space $V_x$ on which the gauge group acts. A matter field is a choice of vector

$$
\psi(x)\in V_x
$$

for each $x$. In a local frame, this becomes a column vector of functions.

A gauge transformation is a change of local frame:

$$
\psi(x)\mapsto G^{-1}(x)\psi(x).
$$

The gauge field is a matrix-valued one-form

$$
A=A_\mu dx^\mu,
\qquad
A_\mu=A_\mu^aT^a.
$$

The covariant exterior derivative is

$$
D=d+igA,
$$

or in components,

$$
D_\mu=\partial_\mu+igA_\mu.
$$

Under a gauge transformation,

$$
A\mapsto A^G=G^{-1}AG-\frac{i}{g}G^{-1}dG,
$$

which is the one-form version of

$$
A_\mu\mapsto A_\mu^G=G^{-1}A_\mu G-\frac{i}{g}G^{-1}\partial_\mu G.
$$

Mathematicians often use the anti-Hermitian connection

$$
\mathcal A=igA.
$$

Then the same transformation law becomes the standard frame-change formula

$$
\mathcal A\mapsto \mathcal A^G=G^{-1}\mathcal A G+G^{-1}dG.
$$

Both notations describe the same connection. The physics convention keeps the coupling $g$ and Hermitian generators visible.

## Fields as sections and gauges as frames

The geometric viewpoint separates three ideas that are easily blurred.

First, the internal vector space is physical bookkeeping: it records charges, color, weak isospin, or another representation label. A quark color triplet, for example, has values in a three-dimensional complex vector space at each spacetime point.

Second, a gauge choice is a local frame choice in those internal spaces. Saying “red, green, blue” at one point and “red, green, blue” at a neighboring point requires a convention for identifying the two color bases. Gauge transformations change that convention.

Third, the connection tells us how to compare vectors in nearby fibers without pretending that the frame convention is absolute.

This is why the gauge potential transforms inhomogeneously. The term

$$
-\frac{i}{g}G^{-1}dG
$$

is not a strange add-on; it is exactly the term that compensates for a position-dependent change of frame. A tensorial object would transform simply as $G^{-1}(\text{object})G$. A connection is not tensorial because it defines how frames change.

## Parallel transport along a curve

Let $C$ be a path parameterized by $z^\mu(s)$, with $z(s_i)=x$ and $z(s_f)=y$. Parallel transport of an internal vector $\chi(s)$ along $C$ is defined by

$$
\frac{d\chi}{ds}+ig\dot z^\mu(s)A_\mu(z(s))\chi(s)=0.
$$

The solution is

$$
\chi(s_f)=U_C(y,x)\chi(s_i),
$$

where

$$
U_C(y,x)=\mathcal P\exp\left(-ig\int_{s_i}^{s_f}ds\,\dot z^\mu(s)A_\mu(z(s))\right).
$$

Equivalently,

$$
U_C(y,x)=\mathcal P\exp\left(-ig\int_C A_\mu dz^\mu\right).
$$

The symbol $\mathcal P$ means path ordering. It is necessary because matrices $A_\mu(z(s_1))$ and $A_\nu(z(s_2))$ at different points along the path need not commute.

For an infinitesimal path from $x$ to $x+dx$,

$$
U_C(x+dx,x)=1-igA_\mu(x)dx^\mu+O(dx^2).
$$

This is the infinitesimal transporter used in the previous page to derive the covariant derivative.

## Endpoint covariance of Wilson lines

Under a gauge transformation $G(x)$, the Wilson line transforms as

$$
U_C(y,x)\mapsto G^{-1}(y)U_C(y,x)G(x).
$$

This transformation rule has a clear meaning. The Wilson line maps a vector in $V_x$ to a vector in $V_y$. If we change the frame at the starting point and the ending point, the matrix representing the map must change by one factor at each endpoint.

For an open Wilson line, the endpoint factors do not cancel. Therefore an open Wilson line is not gauge invariant by itself. It becomes gauge invariant when attached to charged fields transforming at the endpoints, for example schematically

$$
\psi^\dagger(y)U_C(y,x)\psi(x),
$$

with representation indices contracted appropriately.

For a closed curve $C$ based at $x$,

$$
U_C(x,x)\mapsto G^{-1}(x)U_C(x,x)G(x).
$$

The trace in a representation $R$ is invariant:

$$
W_R(C)=\operatorname{tr}_R U_C(x,x)
$$

because traces are invariant under conjugation. This is the Wilson loop. It will later become a diagnostic of confinement, center symmetry, screening, and the global form of the gauge group.

## Curvature preview

A connection can have curvature. In gauge theory, curvature is the field strength.

With the anti-Hermitian connection $\mathcal A=igA$, the curvature is

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

In physics variables,

$$
\mathcal F=igF,
\qquad
F=dA+igA\wedge A.
$$

In components,

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
$$

or

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

The commutator of covariant derivatives is

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

The next page derives these formulas carefully. For now, the geometric meaning is enough: curvature measures the failure of parallel transport around a tiny loop to return a vector to itself.

Infinitesimally, around a small parallelogram with area element $\Sigma^{\mu\nu}$,

$$
U_{\partial\Sigma}
=1-igF_{\mu\nu}\Sigma^{\mu\nu}+O(\Sigma^{3/2}).
$$

Flat connection means $F_{\mu\nu}=0$ locally. Curved connection means the transport remembers the path even for arbitrarily small loops.

## Flat is not always trivial

The statement $F=0$ implies that the connection is locally pure gauge on a simply connected patch. In this volume's convention, a pure gauge connection can be written locally as

$$
A=-\frac{i}{g}G^{-1}dG,
$$

which is what one obtains by gauge-transforming $A=0$.

But local flatness does not always mean global triviality. If spacetime or space has noncontractible loops, a flat connection can have nontrivial holonomy. For a closed curve $C$,

$$
U_C=\mathcal P\exp\left(-ig\oint_C A\right)
$$

can be nontrivial even when $F=0$ everywhere along the region being probed.

The Abelian Aharonov–Bohm setup is the standard intuition: outside an idealized solenoid the magnetic field can vanish, but the vector potential can still produce a measurable phase around a loop encircling the excluded region. In non-Abelian theories, flat connections and holonomies become part of the global data of the gauge theory, especially on compact spaces or in finite-temperature settings.

This is one reason the local formula $A_\mu^aT^a$ does not fully define a gauge theory. The global form of the gauge group, the topology of the bundle, allowed line operators, and boundary conditions can all matter.

## Abelian connection

For $U(1)$, the matrices commute and path ordering is unnecessary. A charge-$q$ field has

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

and parallel transport along $C$ gives the phase

$$
U_C(y,x)=\exp\left(-iq\int_C A_\mu dz^\mu\right).
$$

A gauge transformation $A\mapsto A+d\alpha$ changes the open transporter by

$$
U_C(y,x)\mapsto e^{-iq\alpha(y)}U_C(y,x)e^{iq\alpha(x)}.
$$

For a closed loop,

$$
U_C(x,x)=\exp\left(-iq\oint_C A\right)
$$

is gauge invariant under ordinary single-valued gauge transformations. By Stokes' theorem on a surface $\Sigma$ with boundary $C$,

$$
\oint_C A=\int_\Sigma F
$$

when such a surface is available without singularities or excluded regions. The caveat is important: global topology is exactly where holonomy can contain information not visible from a single smooth surface patch.

## Non-Abelian connection

For a non-Abelian group, $A_\mu$ is matrix-valued and the order of matrices matters. The Wilson line expansion is

$$
\begin{aligned}
U_C(y,x)
&=1-ig\int_C dz^\mu A_\mu(z) \\
&\quad +(-ig)^2\int_{s_i<s_2<s_f}ds_2\int_{s_i<s_1<s_2}ds_1\,
\dot z^{\mu_2}(s_2)\dot z^{\mu_1}(s_1)
A_{\mu_2}(z(s_2))A_{\mu_1}(z(s_1))+
\cdots.
\end{aligned}
$$

The ordering convention here places later points along the path to the left. This is the convention compatible with

$$
\frac{d}{ds}U(s,s_i)=-ig\dot z^\mu(s)A_\mu(z(s))U(s,s_i).
$$

Non-Abelian parallel transport is why Wilson lines are natural observables even before quantization. They encode the finite effect of the connection, not just its infinitesimal components.

## What the connection viewpoint buys you

The connection language is not ornamental. It compresses several essential facts.

| Gauge-theory object | Connection-language meaning |
|---|---|
| $A_\mu$ | Local coefficients of a connection in a chosen frame. |
| Gauge transformation | Change of local frame. |
| $D_\mu$ | Covariant derivative defined by the connection. |
| Wilson line | Finite parallel transport along a path. |
| Wilson loop | Gauge-invariant trace of holonomy around a closed path. |
| $F_{\mu\nu}$ | Curvature of the connection. |
| Pure gauge field | Connection obtained by frame-changing the zero connection. |
| Bianchi identity | Geometric identity obeyed by curvature. |

This dictionary also clarifies the analogy with general relativity. The Christoffel connection defines parallel transport of tangent vectors and has Riemann curvature. The gauge connection defines parallel transport of internal vectors and has Yang–Mills curvature. The analogy is deep, but not identity: in gauge theory the connection is an independent dynamical field, while in ordinary general relativity the Levi-Civita connection is built from the metric.

## Common pitfalls

**Thinking the connection is gauge invariant.** A connection is not a tensor. It transforms with an inhomogeneous term. Curvature transforms covariantly, and traces or closed-loop holonomies can be gauge invariant.

**Forgetting the representation.** The same abstract connection acts through different matrices in different representations. A Wilson loop in the fundamental representation and a Wilson loop in the adjoint representation are different operators.

**Dropping path ordering in non-Abelian theory.** Path ordering is unnecessary in $U(1)$ but essential when the gauge group is non-Abelian.

**Equating flat with zero.** If $F=0$, then locally the connection is pure gauge on a simply connected patch. Global holonomy can still be nontrivial on spaces with noncontractible loops or excluded regions.

**Treating the bundle as automatically trivial.** On a small patch, one can usually write $A_\mu^a$ as ordinary functions. Globally, nontrivial bundles, transition functions, and topological sectors can be physical.

**Confusing gauge parallel transport with spacetime transport.** The Wilson line transports internal gauge indices along a spacetime path. It does not move the spacetime point by itself, and it is distinct from parallel transport by the spacetime spin connection or Christoffel connection.

## Relations to other pages

- [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/) derives the same $A_\mu$ from local covariance of derivatives.
- [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) explains why changing the local frame is redundancy when the transformation is proper gauge.
- The next page on field strength and curvature derives $F=dA+igA\wedge A$, the commutator formula $[D_\mu,D_\nu]=igF_{\mu\nu}$, and the Bianchi identity.
- Later pages on Wilson loops, center symmetry, confinement, global form, and Standard Model gauge structure use the finite parallel transport introduced here.

## Research status

The local connection interpretation of gauge fields is settled and foundational. It underlies classical Yang–Mills theory, gauge-invariant matter couplings, Wilson lines, lattice gauge theory link variables, and the geometric treatment of anomalies and instantons.

The active refinements are global and categorical rather than local: which bundles are summed over, which line operators are genuine, what the global form of the gauge group is, how boundary conditions create edge modes, and how generalized symmetries organize Wilson and 't Hooft operators. Those questions do not replace the connection viewpoint; they complete it.

## Exercises

### Exercise 1: Infinitesimal parallel transport gives the covariant derivative

Assume parallel transport from $x$ to $x+dx$ is

$$
\psi(x)\mapsto \bigl(1-igA_\mu(x)dx^\mu\bigr)\psi(x).
$$

Show that the covariant difference

$$
\psi(x+dx)-\bigl(1-igA_\mu dx^\mu\bigr)\psi(x)
$$

is $dx^\mu D_\mu\psi(x)+O(dx^2)$.

<details>
<summary><strong>Solution</strong></summary>

Expand

$$
\psi(x+dx)=\psi(x)+dx^\mu\partial_\mu\psi(x)+O(dx^2).
$$

Then

$$
\begin{aligned}
\psi(x+dx)-\bigl(1-igA_\mu dx^\mu\bigr)\psi(x)
&=\psi+dx^\mu\partial_\mu\psi-\psi+igA_\mu dx^\mu\psi+O(dx^2)\\
&=dx^\mu(\partial_\mu+igA_\mu)\psi+O(dx^2)\\
&=dx^\mu D_\mu\psi+O(dx^2).
\end{aligned}
$$

</details>

### Exercise 2: Endpoint transformation of a Wilson line

Let $U_C(y,x)$ solve

$$
\frac{d}{ds}U(s,s_i)=-ig\dot z^\mu A_\mu(z(s))U(s,s_i),
\qquad
U(s_i,s_i)=1.
$$

Use the gauge transformation of $A_\mu$ to check that

$$
U_C(y,x)\mapsto G^{-1}(y)U_C(y,x)G(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Define

$$
U^G(s,s_i)=G^{-1}(z(s))U(s,s_i)G(z(s_i)).
$$

Differentiate:

$$
\frac{dU^G}{ds}
=\frac{dG^{-1}}{ds}UG_i+G^{-1}\frac{dU}{ds}G_i,
$$

where $G_i=G(z(s_i))$. Using

$$
\frac{dU}{ds}=-ig\dot z^\mu A_\mu U
$$

and

$$
\frac{dG^{-1}}{ds}=-G^{-1}\frac{dG}{ds}G^{-1},
$$

one finds

$$
\frac{dU^G}{ds}
=-ig\dot z^\mu A_\mu^G(z(s))U^G(s,s_i)
$$

with

$$
A_\mu^G=G^{-1}A_\mu G-\frac{i}{g}G^{-1}\partial_\mu G.
$$

The initial condition is $U^G(s_i,s_i)=1$. Therefore $U^G$ is the Wilson line built from the transformed connection, and at the endpoint it is

$$
U_C^G(y,x)=G^{-1}(y)U_C(y,x)G(x).
$$

</details>

### Exercise 3: Pure gauge connections are flat

Let

$$
A=-\frac{i}{g}G^{-1}dG.
$$

Show that $F=dA+igA\wedge A=0$.

<details>
<summary><strong>Solution</strong></summary>

Let $\mathcal A=igA$. Then

$$
\mathcal A=G^{-1}dG.
$$

The curvature is

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

Using the Maurer–Cartan identity,

$$
d(G^{-1}dG)+(G^{-1}dG)\wedge(G^{-1}dG)=0,
$$

we get $\mathcal F=0$. Since $\mathcal F=igF$, this implies $F=0$.

Equivalently, $A$ is obtained by gauge-transforming the zero connection, and curvature transforms covariantly, so it remains zero.

</details>

### Exercise 4: Flat Abelian connection on a circle

Consider a $U(1)$ connection on a circle coordinate $\varphi\sim\varphi+2\pi$:

$$
A=a\,d\varphi,
$$

with constant $a$. Show that $F=0$ but that a charge-$q$ Wilson loop around the circle is

$$
\exp(-i2\pi q a).
$$

<details>
<summary><strong>Solution</strong></summary>

Since $a$ is constant,

$$
F=dA=d(a\,d\varphi)=0.
$$

The Wilson loop is

$$
\exp\left(-iq\oint A\right)
=\exp\left(-iq\int_0^{2\pi}a\,d\varphi\right)
=\exp(-i2\pi q a).
$$

Thus a flat connection can have nontrivial holonomy around a noncontractible loop.

</details>

### Exercise 5: Why path ordering matters

Expand the Wilson line to second order for a non-Abelian connection along a path $z(s)$, and identify where matrix ordering enters.

<details>
<summary><strong>Solution</strong></summary>

The solution to

$$
\frac{dU}{ds}=-ig\dot z^\mu(s)A_\mu(z(s))U(s)
$$

is obtained iteratively:

$$
U(s_f,s_i)=1-ig\int_{s_i}^{s_f}ds_1\,\dot z^{\mu_1}(s_1)A_{\mu_1}(z(s_1))
$$

plus the second-order term

$$
(-ig)^2\int_{s_i}^{s_f}ds_2\int_{s_i}^{s_2}ds_1\,
\dot z^{\mu_2}(s_2)\dot z^{\mu_1}(s_1)
A_{\mu_2}(z(s_2))A_{\mu_1}(z(s_1)).
$$

The matrix at the later parameter value $s_2$ appears to the left of the matrix at the earlier value $s_1$. If the matrices at different points do not commute, changing this order changes the answer. Path ordering records this order systematically.

</details>

## References

### Standard first pass

- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Yang–Mills theory, Wilson lines, and gauge-invariant structures.
- M. Srednicki, *Quantum Field Theory*, §69, for non-Abelian gauge theory in matrix notation and the field strength from covariant derivatives.
- A. Zee, *Quantum Field Theory in a Nutshell*, Part IV.5, for a compact physical route to non-Abelian gauge theory.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §15.1, for the analogy between gauge-covariant derivatives and spacetime covariant derivatives.
- A. M. Polyakov, *Gauge Fields and Strings*, Ch. 1, for the broad gauge-system viewpoint that later leads naturally to Wilson loops and nonperturbative gauge dynamics.
- M. Nakahara, *Geometry, Topology and Physics*, for the mathematical language of bundles, connections, curvature, and characteristic classes.

## Version history

- **2026-06-17:** Initial polished draft for the Gauge Principle and Classical Gauge Theory chapter.
