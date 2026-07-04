---
title: "Degree of a Map"
description: "Defines the degree of a smooth map between oriented manifolds and explains its local, homological, and differential-form descriptions in QFT applications."
sidebar:
  label: "Degree of a Map"
  order: 4
level: Advanced
status: "Polished draft"
source: "Standard topology and geometry references for physicists, including Nakahara, Frankel, Bott–Tu, Milnor, Coleman, Polyakov, and QFT treatments of sigma-model and gauge-theory topological charge."
topics:
  - degree of a map
  - local degree
  - orientation
  - topological charge
  - winding number
  - sigma models
  - instantons
  - homology
  - de Rham cohomology
canonicalTopics:
  - degree-of-a-map
  - local-degree
  - topological-charge
  - winding-number
  - sigma-model-sector
  - instanton-number
  - homology-class
  - de-rham-period
researchStatus:
  established:
    - "The degree of a smooth map between closed oriented manifolds of the same dimension is a standard integer-valued homotopy invariant, computable by signed preimages, fundamental classes, or integration of pulled-back volume forms."
  active:
    - "In quantum field theory, degree-like labels are often refined by gauge equivalence, global form of the symmetry group, torsion data, defects, anomalies, differential cohomology, and cobordism."
---

## Summary

The degree of a map is the integer that measures how many times one oriented space covers another, with signs. For a smooth map between closed oriented connected $n$-manifolds,

$$
f:M^n\to N^n,
$$

the degree is the integer $\deg f$ defined by

$$
f_\ast[M]=(\deg f)[N]
$$

on top homology. Equivalently, for every top-degree form $\omega$ on $N$,

$$
\int_M f^\ast\omega=(\deg f)\int_N\omega.
$$

When $y\in N$ is a regular value, the same integer is obtained by adding signs over its preimages:

$$
\deg f=\sum_{x\in f^{-1}(y)}\operatorname{sgn}\det df_x.
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![Diagram showing a map between oriented manifolds, a regular value, signed preimages, and the equivalent regular-value and cohomological formulas for the degree.](/figures/math-toolkit/degree-map-local-signs.svg)

<figcaption>

The degree of $f:M^n\to N^n$ can be computed locally by signed preimages of a regular value, or globally by pulling back a normalized volume form. In field theory, finite-action boundary conditions often turn a configuration into such a map, and $\deg f$ becomes a topological charge.

</figcaption>
</figure>

This page explains the three equivalent definitions, why the degree is invariant under homotopy, and why this single integer keeps reappearing as vortex number, monopole charge, Skyrmion number, instanton number, and the winding number of large gauge transformations.

The main warning is that degree is not “the number of solutions” unless those solutions are counted with orientation signs and the dimensions match. It is also not automatically a physical superselection label: gauge equivalence, singular configurations, boundary conditions, and quantum effects can identify or change what the classical integer seemed to label.

## Prerequisites

Read [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) for the map-based view of topological sectors, [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) for fundamental classes and period pairings, and [Winding Numbers](/math-toolkit/topology-cohomology-characteristic-classes/winding-numbers/) for the circle-valued prototype.

For the differential-form formula, read [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/). For field-theory examples involving compactification of space and target manifolds, it helps to have seen [Manifolds](/math-toolkit/geometry-of-fields/manifolds/) and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/).

Unless stated otherwise, $M$ and $N$ are smooth, closed, oriented, connected manifolds of the same dimension $n$. “Closed” here means compact without boundary, not a closed subset of another space. Boundaries are discussed separately below.

## Core idea

Degree is the oriented count of how many times $M$ maps over $N$.

If $f:M\to N$ is a map between finite sets, the phrase “how many times” would simply mean the number of preimages of a point. For manifolds, the same idea survives after two improvements.

First, choose a point $y\in N$ whose preimages are nondegenerate. This means that for each $x\in f^{-1}(y)$, the derivative

$$
df_x:T_xM\to T_yN
$$

is an isomorphism. Such a point is called a **regular value**. The inverse function theorem then says that near each preimage, $f$ is a local diffeomorphism.

Second, orientations decide whether each local diffeomorphism preserves or reverses orientation. Define

$$
\operatorname{sgn}_x(f)=
\begin{cases}
+1, & df_x\text{ preserves orientation},\\
-1, & df_x\text{ reverses orientation}.
\end{cases}
$$

Then

$$
\deg f=\sum_{x\in f^{-1}(y)}\operatorname{sgn}_x(f).
$$

The miracle is that this sum does not depend on the regular value $y$. As $y$ moves, pairs of preimages can be created or annihilated at critical values, but they appear with opposite signs. The signed total stays fixed.

That integer is the degree.

## Definition by fundamental classes

The cleanest invariant definition uses homology. If $M$ and $N$ are closed oriented connected $n$-manifolds, their top homology groups are

$$
H_n(M;\mathbb Z)\simeq\mathbb Z,
\qquad
H_n(N;\mathbb Z)\simeq\mathbb Z.
$$

An orientation chooses fundamental classes

$$
[M]\in H_n(M;\mathbb Z),
\qquad
[N]\in H_n(N;\mathbb Z).
$$

The map $f$ induces a homomorphism on homology,

$$
f_\ast:H_n(M;\mathbb Z)\to H_n(N;\mathbb Z).
$$

Since both groups are copies of $\mathbb Z$, the image of $[M]$ must be an integer multiple of $[N]$:

$$
f_\ast[M]=(\deg f)[N].
$$

This integer is the degree of $f$.

This definition is compact and powerful. It immediately shows that $\deg f$ is a homotopy invariant, because homotopic maps induce the same map on homology. It also makes clear why orientation matters. Reverse the orientation of $M$ or $N$, and $\deg f$ changes sign. Reverse both, and it does not.

## Definition by signed preimages

The local formula is the one most useful in calculations and pictures. Suppose $y\in N$ is a regular value of $f$. Because $M$ is compact and $df_x$ is invertible at each preimage, the set $f^{-1}(y)$ is finite. Then

$$
\deg f=\sum_{x\in f^{-1}(y)}\operatorname{sgn}\det df_x,
$$

where the determinant is computed in any positively oriented local coordinates on $M$ and $N$.

Changing positively oriented coordinates multiplies the coordinate determinant by positive Jacobians, so the sign is well-defined. If one of the coordinate charts is orientation-reversing, the sign would flip, which is exactly why the orientation of both manifolds is part of the data.

This formula is sometimes the easiest way to compute degree. It also gives a good mental model:

$$
\deg f=(\text{number of orientation-preserving sheets})
-(\text{number of orientation-reversing sheets}).
$$

A nonzero degree forces $f$ to be onto. Indeed, if $y$ were outside the image of $f$, then $f^{-1}(y)$ would be empty and the regular-value formula would give $\deg f=0$.

## Definition by integration

Let $\omega_N$ be any smooth top-degree form on $N$. Then $f^\ast\omega_N$ is a top-degree form on $M$. The degree is characterized by

$$
\int_M f^\ast\omega_N=(\deg f)\int_N\omega_N.
$$

If $\omega_N$ is normalized so that

$$
\int_N\omega_N=1,
$$

then

$$
\deg f=\int_M f^\ast\omega_N.
$$

This is the formula that most directly turns into topological charge densities in field theory.

Why is it true? Near a regular value, choose a small coordinate ball $B\subset N$ around $y$. Its inverse image is a disjoint union of small balls $B_x\subset M$, one around each preimage. On each $B_x$, the change-of-variables formula gives either

$$
\int_{B_x}f^\ast\omega_N=+\int_B\omega_N
$$

or

$$
\int_{B_x}f^\ast\omega_N=-\int_B\omega_N,
$$

depending on whether $f$ preserves or reverses orientation at $x$. Adding the local sheets produces the signed preimage count.

More globally, the integration formula is just the pairing between top cohomology and top homology:

$$
\int_M f^\ast\omega_N
=
\langle f^\ast[\omega_N],[M]\rangle
=
\langle [\omega_N],f_\ast[M]\rangle
=
(\deg f)\langle [\omega_N],[N]\rangle.
$$

That line is worth digesting. It says the local Jacobian signs, the homology fundamental class, and the pulled-back volume form are not three separate concepts. They are three windows onto the same integer.

## Homotopy invariance

If $f_0,f_1:M\to N$ are smoothly homotopic, then

$$
\deg f_0=\deg f_1.
$$

Using homology, this is immediate: homotopic maps induce the same map on homology, so

$$
(f_0)_\ast[M]=(f_1)_\ast[M].
$$

Using forms, let $F:M\times[0,1]\to N$ be a homotopy from $f_0$ to $f_1$. For a closed top form $\omega_N$ on $N$, the difference of pulled-back integrals is

$$
\int_M f_1^\ast\omega_N-\int_M f_0^\ast\omega_N
=
\int_{\partial(M\times[0,1])}F^\ast\omega_N.
$$

By Stokes’ theorem,

$$
\int_{\partial(M\times[0,1])}F^\ast\omega_N
=
\int_{M\times[0,1]}dF^\ast\omega_N
=
\int_{M\times[0,1]}F^\ast d\omega_N
=0.
$$

Since top-degree forms on $N$ are closed, the integral formula for degree is unchanged.

In physics language, a topological charge cannot change under smooth time evolution unless the field configuration leaves the allowed configuration space. It must pass through a singularity, violate a boundary condition, change the topology of space, or couple to an object that carries away the charge.

## Basic examples

### Maps from the circle to itself

For

$$
f:S^1\to S^1,
\qquad
f(e^{i\theta})=e^{ik\theta},
$$

the degree is

$$
\deg f=k.
$$

The normalized volume form on the target circle is $d\phi/(2\pi)$, so

$$
\deg f=rac{1}{2\pi}\int_0^{2\pi}d(k\theta)=k.
$$

This is the winding number. Degree generalizes winding from maps $S^1\to S^1$ to maps $M^n\to N^n$.

### The identity and constant maps

The identity map has degree

$$
\deg(\operatorname{id}_M)=1.
$$

A constant map from a positive-dimensional closed manifold has degree

$$
\deg f=0,
$$

because its image is a point and therefore cannot cover the target fundamental class.

### Antipodal maps on spheres

The antipodal map

$$
A:S^n\to S^n,
\qquad
A(x)=-x,
$$

has degree

$$
\deg A=(-1)^{n+1}.
$$

A quick way to see this is to extend $A$ to the linear map $-I$ on $\mathbb R^{n+1}$. Its determinant is $(-1)^{n+1}$. The induced sign on the boundary sphere agrees with that determinant. Thus the antipodal map reverses orientation on $S^2$, but preserves orientation on $S^1$ and $S^3$.

### Composition

If

$$
M\xrightarrow{f}N\xrightarrow{g}P
$$

are maps between closed oriented connected $n$-manifolds, then

$$
\deg(g\circ f)=(\deg g)(\deg f).
$$

This follows immediately from fundamental classes:

$$
(g\circ f)_\ast[M]
=g_\ast(f_\ast[M])
=g_\ast((\deg f)[N])
=(\deg f)(\deg g)[P].
$$

## Degree of sphere-valued fields

A common QFT situation is a field

$$
\mathbf n:M^d\to S^d
$$

where $\mathbf n=(n^1,\dots,n^{d+1})$ is a unit vector field,

$$
\sum_{a=1}^{d+1}(n^a)^2=1.
$$

The degree is

$$
Q[\mathbf n]
=rac{1}{\operatorname{Vol}(S^d)}\int_M \mathbf n^\ast\operatorname{vol}_{S^d}.
$$

Using the standard embedded volume form on the unit sphere,

$$
\operatorname{vol}_{S^d}
=\frac{1}{d!}\epsilon_{a_0a_1\cdots a_d}
 n^{a_0}dn^{a_1}\wedge\cdots\wedge dn^{a_d},
$$

one obtains

$$
Q[\mathbf n]
=rac{1}{d!\operatorname{Vol}(S^d)}
\int_M
\epsilon_{a_0a_1\cdots a_d}
 n^{a_0}dn^{a_1}\wedge\cdots\wedge dn^{a_d}.
$$

For $d=2$, this becomes the familiar sigma-model charge

$$
Q[\mathbf n]
=rac{1}{4\pi}\int_M
\mathbf n\cdot(\partial_1\mathbf n\times\partial_2\mathbf n)
\,d^2x,
$$

assuming the orientation $d^2x=dx^1dx^2$.

The formula says that the topological charge density is the Jacobian of the map into the target sphere, normalized by the target volume. It is a local density whose integral is globally quantized.

## Finite-action compactification

Field theory often starts on noncompact space, such as $\mathbb R^d$. Degree enters after imposing finite-energy or finite-action boundary conditions.

For example, suppose a field $\mathbf n:\mathbb R^d\to S^d$ obeys

$$
\mathbf n(x)\to \mathbf n_\infty
\qquad \text{as } |x|\to\infty,
$$

with the limit independent of direction. Then all points at spatial infinity can be identified, giving the one-point compactification

$$
\mathbb R^d\cup\{\infty\}\simeq S^d.
$$

The field becomes a map

$$
\mathbf n:S^d\to S^d,
$$

and the degree is an integer.

This is the common mechanism behind many classical topological sectors. The spatial boundary condition turns field configurations into maps from a compactified domain to a target space. Homotopy classes of those maps are then candidates for conserved topological sectors.

Candidates, not guarantees. A classical finite-action sector may be destroyed or refined by gauge identifications, defects, anomalies, or allowed singular events. The degree calculation tells you what the smooth classical configuration space says; the full quantum theory gets a vote.

## Relation to defects

Degree also detects defects. Suppose a field is undefined or forced to vanish on a locus $D$. Around $D$, take a small sphere $S^r$ linking the defect. If the normalized field defines a map

$$
S^r\to S^r,
$$

then the defect has local degree

$$
Q_D=\deg(\text{linking sphere}\to\text{target sphere}).
$$

Examples include:

- a vortex in two spatial dimensions, where a small circle around the core maps to the phase circle;
- a monopole in three spatial dimensions, where a large sphere maps to an internal sphere;
- a point defect in a sigma model, where the field wraps a target sphere around the defect;
- a zero of a vector field, whose index is the local degree of the normalized vector field on a small surrounding sphere.

This local degree is stable as long as the defect core cannot disappear or leave through the boundary. Defects of opposite degree can annihilate because the total degree on a surface enclosing both can be zero.

## Gauge transformations and degree

The same mathematics appears for maps into compact Lie groups. A gauge transformation on a spatial slice can be a map

$$
g:M\to G.
$$

For $M=S^3$ and $G=SU(N)$ with $N\ge2$,

$$
\pi_3(SU(N))\simeq\mathbb Z.
$$

The integer is often called the winding number or degree of the gauge transformation. With a common matrix normalization, one writes

$$
\nu(g)=-\frac{1}{24\pi^2}\int_{S^3}\operatorname{tr}(g^{-1}dg)^3,
$$

where the sign depends on conventions for Hermitian versus anti-Hermitian generators and orientation. The important invariant statement is that the normalized Maurer–Cartan 3-form represents the generator of $H^3(SU(N);\mathbb Z)$, and its pullback integrates to an integer.

This integer controls the shift of Chern–Simons functionals under large gauge transformations and appears in the classification of instanton sectors after relating four-dimensional gauge fields to transition functions on spheres at infinity.

The phrase “large gauge transformation” means a gauge transformation not homotopic to the identity within the allowed class. The word “large” is topological, not metric. A large transformation can be pointwise tiny-looking in places; what matters is that it cannot be continuously unwound.

## Relation to instanton number

Instanton number in four-dimensional Yang–Mills theory is not literally the degree of a map $M^4\to N^4$ in the simplest presentation. It is a characteristic number of a principal bundle and connection, often written schematically as

$$
k=\frac{1}{8\pi^2}\int_M \operatorname{tr}(F\wedge F)
$$

with normalization depending on the trace convention. But on $\mathbb R^4$ with suitable finite-action boundary conditions, the gauge field at infinity becomes pure gauge,

$$
A\sim g^{-1}dg
\qquad \text{on } S^3_\infty,
$$

and the instanton number can be related to the winding of

$$
g:S^3_\infty\to G.
$$

So degree is the boundary-map shadow of a characteristic class in the bulk. This is a recurring pattern: a bulk topological charge can often be detected by transition functions or asymptotic maps on overlaps and boundaries.

## Degree versus homotopy class

For maps

$$
S^n\to S^n,
$$

the degree completely classifies homotopy classes:

$$
[S^n,S^n]\simeq\pi_n(S^n)\simeq\mathbb Z.
$$

For general manifolds, degree is usually not a complete invariant. Two maps can have the same degree but not be homotopic. Degree only records what the map does to the top-dimensional fundamental class. It forgets lower-dimensional information, torsion information, and more refined structure.

This is why degree is powerful but not omniscient. It is the first invariant to compute, not the last possible invariant.

## Manifolds with boundary

If $M$ has a boundary, the simplest degree formula must be modified. The identity

$$
\int_M f^\ast\omega_N=(\deg f)\int_N\omega_N
$$

is no longer homotopy invariant under arbitrary homotopies, because Stokes’ theorem produces boundary terms.

There are several standard fixes.

First, impose boundary conditions that allow $M$ to be compactified to a closed manifold. This is the finite-action compactification used above.

Second, use maps of pairs,

$$
f:(M,\partial M)\to (N,A),
$$

and define relative degree using relative homology. This is the natural setting when the boundary is constrained to lie in a subspace $A\subset N$.

Third, if $f$ is proper between noncompact oriented manifolds, one can define degree using compactly supported cohomology. Properness means inverse images of compact sets are compact, so the preimage of a regular value remains finite.

The physics translation is direct. Boundary conditions are not decorative; they are part of the topological problem. Changing them can change the charge.

## Common pitfalls

**Counting preimages without signs.** The degree is an oriented count. A map can have many preimages of a regular value and still have degree zero.

**Ignoring compactness or properness.** If the domain is noncompact and no boundary condition is imposed, preimages can escape to infinity and degree may not be defined.

**Forgetting that dimensions must match.** Degree in this sense is for maps $M^n\to N^n$. Maps between spaces of different dimensions have other invariants, but not this degree.

**Treating degree as a complete invariant.** For $S^n\to S^n$, degree classifies homotopy classes. For general targets and domains, it usually does not.

**Confusing local density with local conservation.** The degree density is locally written using derivatives of fields, but the integer quantization is global. Locally the density can move around continuously.

**Forgetting gauge equivalence.** A degree computed from a representative field can be changed or identified by allowed gauge transformations. Always ask whether the object whose degree you computed is gauge-invariant.

## Exercises

### Exercise 1: Circle maps

Let

$$
f:S^1\to S^1,
\qquad
f(e^{i\theta})=e^{ik\theta}.
$$

Compute $\deg f$ using the normalized angular form $d\phi/(2\pi)$.

<details><summary><strong>Solution</strong></summary>

The pullback of the target angle is

$$
f^\ast d\phi=d(k\theta)=k\,d\theta.
$$

Therefore

$$
\deg f=\int_{S^1}f^\ast\left(\frac{d\phi}{2\pi}\right)
=\frac{1}{2\pi}\int_0^{2\pi}k\,d\theta
=k.
$$

This is the usual winding number.

</details>

### Exercise 2: Degree of the antipodal map

Show that the antipodal map $A:S^n\to S^n$, $A(x)=-x$, has degree $(-1)^{n+1}$.

<details><summary><strong>Solution</strong></summary>

The antipodal map is the restriction to the unit sphere of the linear map $-I$ on $\mathbb R^{n+1}$. This linear map has determinant

$$
\det(-I)=(-1)^{n+1}.
$$

The induced orientation sign on the boundary sphere agrees with this determinant. Hence

$$
\deg A=(-1)^{n+1}.
$$

For example, the antipodal map on $S^1$ has degree $+1$, while on $S^2$ it has degree $-1$.

</details>

### Exercise 3: Degree by signed preimages

Let $f:S^1\to S^1$ be $f(e^{i\theta})=e^{i2\theta}$. Pick a regular value $y=1$. Compute $\deg f$ by signed preimages.

<details><summary><strong>Solution</strong></summary>

The equation $e^{i2\theta}=1$ has two solutions on $[0,2\pi)$:

$$
\theta=0,
\qquad \theta=\pi.
$$

In angular coordinates, the derivative is

$$
\frac{d(2\theta)}{d\theta}=2>0.
$$

Both local maps preserve orientation, so each preimage contributes $+1$. Therefore

$$
\deg f=1+1=2.
$$

</details>

### Exercise 4: A sphere-valued texture

Consider the map $\mathbf n:S^2\to S^2$ given by

$$
\mathbf n(\theta,\phi)=
(\sin\theta\cos k\phi,\sin\theta\sin k\phi,\cos\theta),
$$

where $k\in\mathbb Z$. Compute its degree.

<details><summary><strong>Solution</strong></summary>

The standard area form on the target sphere is

$$
\operatorname{vol}_{S^2}=\sin\Theta\,d\Theta\wedge d\Phi.
$$

Here the map sends

$$
\Theta=\theta,
\qquad
\Phi=k\phi.
$$

Thus

$$
\mathbf n^\ast\operatorname{vol}_{S^2}
=\sin\theta\,d\theta\wedge d(k\phi)
=k\sin\theta\,d\theta\wedge d\phi.
$$

Therefore

$$
\deg\mathbf n
=\frac{1}{4\pi}\int_0^{2\pi}\int_0^\pi
k\sin\theta\,d\theta\,d\phi
=k.
$$

</details>

### Exercise 5: Why exact changes do not affect the integral formula

Let $M$ be closed and $\omega_N$ be a normalized top form on $N$. Suppose $\omega_N$ is replaced by

$$
\omega_N' = \omega_N+d\alpha.
$$

Show that $\int_M f^\ast\omega_N'=\int_M f^\ast\omega_N$.

<details><summary><strong>Solution</strong></summary>

Using functoriality of pullback and Stokes’ theorem,

$$
\int_M f^\ast\omega_N'
=\int_M f^\ast\omega_N+\int_M f^\ast d\alpha
=\int_M f^\ast\omega_N+\int_M d(f^\ast\alpha).
$$

Since $M$ is closed,

$$
\int_M d(f^\ast\alpha)=\int_{\partial M}f^\ast\alpha=0.
$$

Hence the integral depends only on the cohomology class of $\omega_N$.

</details>

## References

- M. Nakahara, *Geometry, Topology and Physics*, chapters on homotopy, homology, de Rham cohomology, characteristic classes, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*, chapters on differential forms, integration, degree-related orientation ideas, vector bundles, and gauge fields.
- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*, for de Rham cohomology, degree, Thom classes, and Poincaré duality.
- J. Milnor, *Topology from the Differentiable Viewpoint*, for degree, regular values, transversality, and the local-sign definition.
- S. Coleman, *Aspects of Symmetry*, lectures on topology, solitons, monopoles, and instantons.
- A. Polyakov, *Gauge Fields and Strings*, for topological sectors, gauge fields, instantons, and sigma-model examples.

## Version history

- 2026-06-25: Initial polished draft for the Mathematical Toolkit topology chapter.
