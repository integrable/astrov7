---
title: "Spin Structures"
description: "Explains spin structures as lifts of orthonormal frame bundles, including the obstruction by the second Stiefel–Whitney class, spinor bundles, vielbeins, spin connections, and QFT boundary-condition consequences."
sidebar:
  label: "Spin Structures"
  order: 10
level: Advanced
status: "Polished draft"
source: "Standard references on spin geometry and QFT, including Lawson–Michelsohn, Nakahara, Frankel, Freed–Uhlenbeck, Eguchi–Gilkey–Hanson, Friedrich, Weinberg, and QFT treatments of fermions on curved backgrounds."
topics:
  - spin structures
  - spinor bundles
  - frame bundles
  - Spin groups
  - Stiefel-Whitney classes
  - spin connection
  - vielbeins
  - Clifford action
  - fermion boundary conditions
  - spin-c structures
canonicalTopics:
  - spin-structure
  - spinor-bundle
  - orthonormal-frame-bundle
  - spin-group
  - second-stiefel-whitney-class
  - spin-connection
  - vielbein
  - clifford-action
  - spin-c-structure
researchStatus:
  established:
    - "For an oriented Riemannian manifold, and similarly for oriented time-oriented Lorentzian manifolds, spin structures are lifts of the orthonormal frame bundle to a Spin principal bundle; existence is obstructed by $w_2(TM)$."
  active:
    - "Modern QFT uses refinements such as Spin-c, Pin, twisted, relative, and generalized spin structures, especially in anomalies, topological phases, defects, nonorientable backgrounds, and fermionic TQFT."
---

## Summary

A spin structure is the global geometric datum that allows spinor fields to exist on a manifold. Gamma matrices are local algebra. A spin structure is global topology.

On a flat patch, a spinor field looks like a column vector acted on by gamma matrices. On a curved or topologically nontrivial manifold, that local picture is not enough. One must ask whether the orthonormal frame bundle can be lifted from the rotation or Lorentz group to its double cover, the Spin group.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Commutative diagram showing a spin bundle lifting the oriented orthonormal frame bundle, the obstruction w2(TM), choices classified by H1(M,Z2), and the associated spinor bundle with spin connection.](/figures/math-toolkit/spin-structure-lift.svg)

<figcaption>

A spin structure is a lift of the oriented orthonormal frame bundle $F_{SO}(M)$ to a principal $\,\operatorname{Spin}(p,q)$ bundle. Once the lift exists, spinor fields are sections of an associated spinor bundle $S=P_{\operatorname{Spin}}\times_\rho\Sigma$.

</figcaption>
</figure>

For an oriented Riemannian manifold, the basic existence criterion is

$$
w_2(TM)=0,
$$

where $w_2(TM)$ is the second Stiefel–Whitney class of the tangent bundle. If spin structures exist, their isomorphism classes form a torsor over

$$
H^1(M,\mathbb Z_2).
$$

This means there may be more than one spin structure. In QFT, different spin structures can mean different fermion boundary conditions, different fermion spectra, and different signs in the path integral.

## Prerequisites

Read [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/), [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), and [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/) first.

For the local algebra, see [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/) and [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/). This page explains the global bundle layer that must be added before spinors can be placed consistently on a curved or topologically nontrivial manifold.

## Core idea

A tensor field can be built from the frame bundle because tensor representations descend to representations of the orthogonal group. Spinors do not. Spinors transform under representations of

$$
\operatorname{Spin}(p,q),
$$

not directly under

$$
SO(p,q).
$$

The Spin group is a double cover:

$$
\lambda:\operatorname{Spin}(p,q)\to SO(p,q),
\qquad
\ker\lambda=\{\pm1\}.
$$

Locally, every rotation or proper Lorentz transformation can be lifted to a spin transformation. Globally, the lifts on overlaps may fail to satisfy the required cocycle condition. The obstruction is $w_2(TM)$.

So the core statement is:

$$
\text{spinors require a lift of the orthonormal frame bundle, not just a metric.}
$$

This is why a local gamma-matrix calculation can be perfectly correct and still fail to define a global fermion theory. The goblin has upgraded from sign errors to topology. Naturally.

## Orthonormal frame bundles

Let $(M,g)$ be an oriented pseudo-Riemannian manifold of signature $(p,q)$. At each point $x\in M$, an oriented orthonormal frame is a basis

$$
(e_1,\ldots,e_n)
$$

of $T_xM$ satisfying

$$
g(e_a,e_b)=\eta_{ab},
$$

where

$$
\eta_{ab}=\operatorname{diag}(\underbrace{+1,\ldots,+1}_{p},
\underbrace{-1,\ldots,-1}_{q}).
$$

The collection of all oriented orthonormal frames forms a principal $SO(p,q)$-bundle

$$
F_{SO}(M)\to M.
$$

For Riemannian signature this is $SO(n)$. For Lorentzian signature one often assumes both orientation and time orientation, reducing the structure group to the identity component

$$
SO^+(1,n-1).
$$

In a local trivialization, the frame bundle is described by transition functions

$$
g_{ij}:U_i\cap U_j\to SO(p,q)
$$

on overlaps. These functions obey the cocycle condition

$$
g_{ij}g_{jk}g_{ki}=1
$$

on triple overlaps $U_i\cap U_j\cap U_k$.

Tensor fields are easy to define from this data. Given a representation $\rho$ of $SO(p,q)$ on a vector space $V$, one forms the associated bundle

$$
E=F_{SO}(M)\times_\rho V.
$$

Spinors are not obtained this way from a representation of $SO(p,q)$. Their natural representation lives upstairs on $\operatorname{Spin}(p,q)$.

## The double cover

The Spin group is built inside the Clifford algebra of the tangent-space metric. Locally, Clifford generators satisfy

$$
\{\gamma^a,\gamma^b\}=2\eta^{ab}.
$$

The group $\operatorname{Spin}(p,q)$ maps onto $SO(p,q)$ by conjugation on vectors. The map

$$
\lambda:\operatorname{Spin}(p,q)\to SO(p,q)
$$

is two-to-one. The two elements $s$ and $-s$ in the Spin group define the same orthogonal transformation:

$$
\lambda(s)=\lambda(-s).
$$

This double cover is the geometric origin of the familiar fact that a $2\pi$ rotation acts as $-1$ on spinors, while a $4\pi$ rotation acts as $+1$.

For ordinary three-dimensional rotations,

$$
\operatorname{Spin}(3)\simeq SU(2),
\qquad
SO(3)\simeq SU(2)/\mathbb Z_2.
$$

For four-dimensional Lorentzian geometry in mostly-minus convention, the identity component is covered by

$$
\operatorname{Spin}^+(1,3)\simeq SL(2,\mathbb C).
$$

This is the group behind Weyl spinors and the Lorentz transformation law used in flat-space QFT.

## Definition of a spin structure

A spin structure on an oriented pseudo-Riemannian manifold is a principal $\operatorname{Spin}(p,q)$-bundle

$$
P_{\operatorname{Spin}}\to M
$$

together with a bundle map

$$
\Lambda:P_{\operatorname{Spin}}\to F_{SO}(M)
$$

covering the identity on $M$, such that

$$
\Lambda(p\cdot s)=\Lambda(p)\cdot\lambda(s)
$$

for all $s\in\operatorname{Spin}(p,q)$.

In words: $P_{\operatorname{Spin}}$ is a lift of the orthonormal frame bundle through the double cover

$$
\operatorname{Spin}(p,q)\to SO(p,q).
$$

In local transition functions, a spin structure amounts to choosing lifts

$$
\widetilde g_{ij}:U_i\cap U_j\to\operatorname{Spin}(p,q)
$$

such that

$$
\lambda(\widetilde g_{ij})=g_{ij}
$$

and

$$
\widetilde g_{ij}\widetilde g_{jk}\widetilde g_{ki}=1
$$

on triple overlaps.

The catch is that lifts always exist locally, but the triple-overlap product may be $-1$ rather than $+1$. The collection of these signs defines the obstruction class.

## Existence and classification

For an oriented Riemannian manifold, a spin structure exists if and only if

$$
w_2(TM)=0.
$$

The same criterion applies to the oriented time-oriented Lorentzian frame bundle after the appropriate reduction of structure group.

Here

$$
w_2(TM)\in H^2(M,\mathbb Z_2)
$$

is the second Stiefel–Whitney class of the tangent bundle. It measures the failure of the $SO$ transition functions to admit compatible $\operatorname{Spin}$ lifts.

If spin structures exist, the set of their isomorphism classes is not naturally a group, but it is acted on freely and transitively by

$$
H^1(M,\mathbb Z_2).
$$

That is, it is a torsor over $H^1(M,\mathbb Z_2)$.

This matters in examples.

A simply connected spin manifold has a unique spin structure, because

$$
H^1(M,\mathbb Z_2)=0.
$$

The circle has

$$
H^1(S^1,\mathbb Z_2)=\mathbb Z_2,
$$

so it has two spin structures. These correspond to periodic and antiperiodic fermions around the circle.

The $d$-torus has

$$
H^1(T^d,\mathbb Z_2)\simeq(\mathbb Z_2)^d,
$$

so it has

$$
2^d
$$

spin structures.

The complex projective plane $\mathbb{CP}^2$ is oriented but not spin:

$$
w_2(T\mathbb{CP}^2)\ne0.
$$

It does admit a Spin-c structure, which is why charged fermions can still be discussed there with suitable gauge-field data.

## Spinor bundles

Once a spin structure $P_{\operatorname{Spin}}$ is chosen, a spinor representation

$$
\rho:\operatorname{Spin}(p,q)\to GL(\Sigma)
$$

produces the spinor bundle

$$
S=P_{\operatorname{Spin}}\times_\rho\Sigma.
$$

A spinor field is a section

$$
\psi\in\Gamma(S).
$$

This statement replaces the flat-space phrase “a spinor-valued function.” On a general manifold, spinors are not functions

$$
M\to\Sigma
$$

unless a global trivialization has been chosen and exists. They are sections of a bundle glued together using spin transition functions.

If $M$ is even-dimensional in Riemannian signature, the spinor representation splits into chiral pieces:

$$
S=S^+\oplus S^-.
$$

In four-dimensional Lorentzian signature, this local algebra is related to left-handed and right-handed Weyl spinors. The global existence of these chiral bundles still depends on the spin structure.

A spinor bundle can also be tensored with an internal gauge bundle. For a representation $R$ of a gauge group $G$, a charged spinor field is a section of

$$
S\otimes E_R,
$$

where $E_R=P_G\times_R V_R$ is the associated gauge vector bundle.

## Vielbeins and Clifford multiplication

A vielbein is a local orthonormal coframe

$$
e^a=e^a{}_{\mu}dx^\mu
$$

satisfying

$$
g_{\mu\nu}=e^a{}_{\mu}e^b{}_{\nu}\eta_{ab}.
$$

It converts coordinate indices into local orthonormal-frame indices. Given constant tangent-space gamma matrices obeying

$$
\{\gamma^a,\gamma^b\}=2\eta^{ab},
$$

one defines curved gamma matrices

$$
\gamma^\mu(x)=e_a{}^\mu(x)\gamma^a.
$$

Then

$$
\{\gamma^\mu(x),\gamma^\nu(x)\}=2g^{\mu\nu}(x).
$$

This is Clifford multiplication by cotangent vectors. More invariantly, there is a bundle map

$$
T^*M\otimes S\to S,
\qquad
\alpha\otimes\psi\mapsto c(\alpha)\psi,
$$

such that

$$
c(\alpha)c(\beta)+c(\beta)c(\alpha)=2g^{-1}(\alpha,\beta).
$$

The vielbein is local. The Clifford action is global once the spinor bundle exists.

## Spin connection

The Levi–Civita connection on the tangent bundle induces a connection on the orthonormal frame bundle. A spin structure lifts this to a connection on the spin bundle, hence to a covariant derivative on spinor fields.

In a local orthonormal frame, the spin connection is a Lie-algebra-valued one-form

$$
\omega^a{}_b=\omega_\mu{}^a{}_b dx^\mu
$$

with

$$
\omega_{ab}=-\omega_{ba}.
$$

For the torsion-free Levi–Civita connection, it is determined by Cartan’s first structure equation:

$$
de^a+\omega^a{}_b\wedge e^b=0.
$$

Define

$$
\gamma^{ab}\equiv\frac12[\gamma^a,\gamma^b].
$$

With this convention, the spinor covariant derivative is

$$
\nabla_\mu\psi
=\partial_\mu\psi
+\frac14\omega_{\mu ab}\gamma^{ab}\psi.
$$

Some authors define $\gamma^{ab}$ without the factor $1/2$. Then the coefficient in this formula changes. Always check both the definition of $\gamma^{ab}$ and the coefficient in the spinor connection.

For a charged spinor in a gauge representation $R$, the full covariant derivative is

$$
D_\mu\psi
=\nabla_\mu\psi+igA_\mu^aT_R^a\psi
$$

in the gauge convention used in this volume.

## Dirac operator preview

The Dirac operator is the first-order operator obtained by composing the spinor covariant derivative with Clifford multiplication:

$$
\mathcal D\psi=\gamma^\mu\nabla_\mu\psi
=e_a{}^\mu\gamma^a\nabla_\mu\psi.
$$

In Lorentzian QFT, the kinetic operator is usually written with an $i$:

$$
i\gamma^\mu\nabla_\mu-m.
$$

For a charged spinor,

$$
i\gamma^\mu D_\mu-m
$$

includes both the spin connection and the gauge connection.

The Dirac operator is where many parts of QFT meet:

$$
\text{spin structure}+\text{metric}+\text{gauge bundle}+\text{connection}
\longrightarrow
\text{fermion dynamics}.
$$

Its kernel gives fermion zero modes. Its determinant enters fermion path integrals. Its index is tied to topology and anomalies. Those topics require separate pages; this page is the global setup.

## Examples

### The circle

The circle $S^1$ has two spin structures because

$$
H^1(S^1,\mathbb Z_2)=\mathbb Z_2.
$$

They correspond to

$$
\psi(\theta+2\pi)=+\psi(\theta)
$$

and

$$
\psi(\theta+2\pi)=-\psi(\theta).
$$

In two-dimensional CFT language these are often called Ramond and Neveu–Schwarz boundary conditions along that cycle. In finite-temperature QFT, antiperiodic fermion boundary conditions around the Euclidean thermal circle implement the thermal trace for fermions.

### The torus

For $T^d$,

$$
H^1(T^d,\mathbb Z_2)\simeq(\mathbb Z_2)^d.
$$

Therefore there are $2^d$ spin structures. Each cycle can independently have periodic or antiperiodic fermion boundary condition.

On a two-torus, the four spin structures are usually labeled by choices around the $a$ and $b$ cycles:

$$
(P,P),\quad(P,A),\quad(A,P),\quad(A,A).
$$

These choices matter in fermion determinants, theta functions, modular transformations, and partition functions.

### Spheres

The sphere $S^n$ is spin for all $n\ge1$. For $n\ge2$, it is simply connected, so the spin structure is unique.

The two-sphere $S^2$ is therefore spin, despite the hairy-ball theorem saying that it has no nowhere-vanishing tangent vector field. Being spin is not the same as having a global frame. This distinction saves an absurd amount of confusion.

### Complex projective plane

The manifold $\mathbb{CP}^2$ is oriented but not spin. Its second Stiefel–Whitney class is nonzero:

$$
w_2(T\mathbb{CP}^2)\ne0.
$$

A neutral spinor field cannot be globally defined on $\mathbb{CP}^2$ using an ordinary spin structure. However, $\mathbb{CP}^2$ admits Spin-c structures, so charged fermions can exist when the $U(1)$ gauge field supplies the missing topological data.

This example appears often in discussions of global anomalies and the global form of fermionic theories.

## Spin, Spin-c, and Pin structures

Spin structures are not the end of the story. QFT often needs variants.

A **Spin-c structure** combines a spin lift with a $U(1)$ bundle. It exists when there is a complex line bundle $L$ such that

$$
c_1(L)\equiv w_2(TM)\pmod 2.
$$

Spin-c structures allow charged fermions on manifolds that are not spin. In physics terms, a background $U(1)$ gauge field can compensate for the obstruction to defining a neutral spinor.

A **Pin structure** is the analog for unoriented manifolds, where the frame group is $O(p,q)$ rather than $SO(p,q)$. There are different Pin groups, usually denoted

$$
\operatorname{Pin}^+,
\qquad
\operatorname{Pin}^-.
$$

They differ by how reflections square in the Clifford algebra. In QFT this distinction is tied to parity, time reversal, and fermionic theories on nonorientable backgrounds.

These refinements are essential in modern anomaly theory, topological phases, and fermionic topological quantum field theory. The basic spin structure is the first rung of the ladder.

## Boundary conditions and QFT path integrals

A spin structure is often experienced by physicists as a fermion boundary condition. That is true, but it is only the surface symptom.

On a manifold with nontrivial one-cycles, a spinor transported around a closed loop may return with a sign. These signs are the holonomies of the $\mathbb Z_2$ difference between spin structures.

For a Euclidean thermal circle of circumference $\beta$, finite-temperature fermions obey

$$
\psi(\tau+\beta)=-\psi(\tau).
$$

This antiperiodicity is what makes the fermionic thermal trace work:

$$
Z(\beta)=\operatorname{Tr}\,e^{-\beta H}.
$$

Periodic fermions around the Euclidean time circle compute a different quantity, often a graded trace such as

$$
\operatorname{Tr}\,(-1)^F e^{-\beta H}
$$

when the theory has the required fermion parity structure.

In path integrals, changing the spin structure changes the spectrum of the Dirac operator and therefore the fermion determinant. For a free fermion,

$$
Z_{\text{fermion}}[g,\text{spin structure}]
\sim \det(i\gamma^\mu\nabla_\mu-m)
$$

with the determinant regularized appropriately. The dependence on spin structure is physical, especially in low-dimensional CFT, topological phases, and anomaly calculations.

## Local Lorentz transformations

A vielbein has a local redundancy. If

$$
e^a{}_{\mu}\mapsto \Lambda^a{}_b(x)e^b{}_{\mu}
$$

with

$$
\Lambda(x)\in SO(p,q),
$$

then the metric is unchanged:

$$
g_{\mu\nu}=e^a{}_{\mu}e^b{}_{\nu}\eta_{ab}.
$$

Spinors transform under a lift

$$
S(\Lambda(x))\in\operatorname{Spin}(p,q).
$$

The spin connection transforms as a gauge field for local Lorentz transformations:

$$
\omega_\mu\mapsto S\omega_\mu S^{-1}-(\partial_\mu S)S^{-1}
$$

in the spinor representation, with sign depending on whether the derivative is written as $\partial+\omega$ or $\partial-\omega$.

The covariant derivative is constructed precisely so that

$$
\nabla_\mu\psi
$$

transforms like a spinor whenever $\psi$ does.

This is why the spin connection is not optional decoration in curved-space fermion theory. Without it, the derivative of a spinor would not transform covariantly under local frame rotations.

## Spinors are not tensors

A rank-$(r,s)$ tensor representation of $SO(p,q)$ descends from the vector representation. If you rotate an orthonormal frame by $2\pi$, tensor components return to themselves.

A spinor representation does not descend to $SO(p,q)$. A $2\pi$ rotation acts as

$$
\psi\mapsto -\psi.
$$

This is not a problem; it is the point. But it means spinors require the lifted structure group.

That is why one should resist phrases like “spinor tensor” unless a specific construction is meant. Spinors can carry tensor indices, and tensors can be built as spinor bilinears, but spinors themselves are not ordinary tensors on $M$.

## Common pitfalls

**Gamma matrices are not a spin structure.** Gamma matrices define the local Clifford algebra. A spin structure is global bundle data.

**A vielbein is not the same as a spin structure.** Vielbeins are local orthonormal frames or coframes. A spin structure is a global lift of the frame bundle. You can write local vielbeins even when no global spin structure exists.

**Being orientable is not enough.** Orientation reduces the structure group from $O(n)$ to $SO(n)$. Spin requires a further lift to $\operatorname{Spin}(n)$, obstructed by $w_2(TM)$.

**Being spin is not being parallelizable.** A parallelizable manifold has a global frame. A spin manifold only has a lifted orthonormal frame bundle. For example, $S^2$ is spin but not parallelizable.

**Different spin structures can define different QFTs.** On a torus or thermal circle, changing the spin structure changes the fermion spectrum and partition function.

**Spin-c is not merely “spin plus electromagnetism.”** It is a specific topological structure in which a $U(1)$ line bundle compensates for $w_2(TM)$.

**The spin connection coefficient depends on the gamma-bivector convention.** If $\gamma^{ab}$ means $\frac12[\gamma^a,\gamma^b]$, the coefficient differs from the convention where $\gamma^{ab}$ means $[\gamma^a,\gamma^b]$.

**Nonorientable manifolds need Pin-type structures, not ordinary spin structures.** This matters for time reversal, parity, unoriented worldsheets, and fermionic phases.

## Exercises

### Exercise 1: Spin structures on a torus

Use the fact that spin structures, when they exist, form a torsor over $H^1(M,\mathbb Z_2)$. Show that the $d$-torus has $2^d$ spin structures.

<details><summary><strong>Solution</strong></summary>

The cohomology of the $d$-torus is

$$
H^1(T^d,\mathbb Z)\simeq\mathbb Z^d.
$$

With $\mathbb Z_2$ coefficients,

$$
H^1(T^d,\mathbb Z_2)\simeq(\mathbb Z_2)^d.
$$

The torus is spin. Therefore its spin structures are acted on freely and transitively by $(\mathbb Z_2)^d$. The number of spin structures is

$$
|(\mathbb Z_2)^d|=2^d.
$$

Physically, each independent one-cycle can carry periodic or antiperiodic fermion boundary condition.

</details>

### Exercise 2: Periodic and antiperiodic spinors on a circle

Explain why the two spin structures on $S^1$ can be represented by

$$
\psi(\theta+2\pi)=\psi(\theta)
$$

and

$$
\psi(\theta+2\pi)=-\psi(\theta).
$$

<details><summary><strong>Solution</strong></summary>

The circle has

$$
H^1(S^1,\mathbb Z_2)=\mathbb Z_2,
$$

so it has two spin structures. Since $S^1$ can be covered by one interval with endpoints identified, the spinor may glue back to itself with either the trivial element $+1$ or the nontrivial central element $-1$ of the spin group.

Thus the two possible identifications are

$$
\psi(\theta+2\pi)=+\psi(\theta)
$$

and

$$
\psi(\theta+2\pi)=-\psi(\theta).
$$

These are usually called periodic and antiperiodic boundary conditions.

</details>

### Exercise 3: Spin connection in polar coordinates

On the Euclidean plane with polar coordinates,

$$
ds^2=dr^2+r^2d\theta^2,
$$

choose the orthonormal coframe

$$
e^1=dr,
\qquad
 e^2=rd\theta.
$$

Solve the torsion-free equations

$$
de^a+\omega^a{}_b\wedge e^b=0
$$

for $\omega^1{}_2$ and $\omega^2{}_1$.

<details><summary><strong>Solution</strong></summary>

First compute

$$
de^1=0,
\qquad
 de^2=d(r d\theta)=dr\wedge d\theta.
$$

Since

$$
e^1=dr,
\qquad
 e^2=rd\theta,
$$

we have

$$
d\theta=\frac1r e^2,
$$

so

$$
de^2=\frac1r e^1\wedge e^2.
$$

The torsion-free equation for $a=2$ is

$$
de^2+\omega^2{}_1\wedge e^1=0.
$$

Taking

$$
\omega^2{}_1=d\theta
$$

gives

$$
\omega^2{}_1\wedge e^1=d\theta\wedge dr=-dr\wedge d\theta=-de^2.
$$

Thus

$$
\omega^2{}_1=d\theta.
$$

Metric compatibility gives antisymmetry,

$$
\omega^1{}_2=-\omega^2{}_1=-d\theta.
$$

The plane is flat, but the spin connection in this rotating polar frame is not zero. Connection coefficients depend on the frame; curvature is the invariant test.

</details>

### Exercise 4: Spin-c compensation

Suppose an oriented manifold has

$$
w_2(TM)\ne0.
$$

Explain how a Spin-c structure can still allow charged fermions if there is a line bundle $L$ with

$$
c_1(L)\equiv w_2(TM)\pmod2.
$$

<details><summary><strong>Solution</strong></summary>

An ordinary spin structure requires the obstruction $w_2(TM)$ to vanish. If it does not vanish, the orthonormal frame bundle cannot be lifted to a Spin bundle by itself.

A Spin-c structure enlarges the lift by including a $U(1)$ factor. The relevant structure group is

$$
\operatorname{Spin}^c(n)=\frac{\operatorname{Spin}(n)\times U(1)}{\mathbb Z_2}.
$$

The $U(1)$ line bundle contributes a mod-two class

$$
c_1(L)\pmod2.
$$

If

$$
c_1(L)\equiv w_2(TM)\pmod2,
$$

then the $U(1)$ twisting cancels the obstruction to defining charged spinors. The fermion is not a neutral section of an ordinary spinor bundle; it is a section of a Spin-c spinor bundle twisted by the appropriate gauge data.

</details>

### Exercise 5: Why the spin connection is needed

Let a spinor transform locally as

$$
\psi\mapsto S(x)\psi
$$

under a lifted local Lorentz transformation. Explain why the ordinary derivative $\partial_\mu\psi$ does not transform covariantly.

<details><summary><strong>Solution</strong></summary>

Differentiate the transformed spinor:

$$
\partial_\mu(S\psi)=(\partial_\mu S)\psi+S\partial_\mu\psi.
$$

The extra term

$$
(\partial_\mu S)\psi
$$

prevents $\partial_\mu\psi$ from transforming simply as $S\partial_\mu\psi$.

A spin connection supplies an additional term so that

$$
\nabla_\mu\psi=\partial_\mu\psi+\Omega_\mu\psi
$$

transforms covariantly:

$$
\nabla_\mu\psi\mapsto S\nabla_\mu\psi.
$$

This requires the connection to transform as

$$
\Omega_\mu\mapsto S\Omega_\mu S^{-1}-(\partial_\mu S)S^{-1}
$$

for the convention $\nabla=\partial+\Omega$. The inhomogeneous term cancels the derivative of the local Lorentz transformation.

</details>

## Relations to other pages

[Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/) defines the metric, vielbein, Levi–Civita connection, curvature convention, and Hodge star used here. [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) explains principal and associated bundles. [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) explains how local connection forms transform. [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/) explains the local double cover $\operatorname{Spin}(p,q)\to SO(p,q)$.

[Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) fixes local Clifford conventions. [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/) explains local spinor types in flat spacetime. [Spinor Bilinears](/math-toolkit/clifford-spinors/spinor-bilinears/) explains how spinors build tensors locally.

Later pages on Dirac operators, index theorems, characteristic classes, anomalies, fermion determinants, supersymmetric backgrounds, and QFT on nonorientable manifolds should link back here.

## Research status

The definition, obstruction theory, and classification of ordinary spin structures are standard. The active QFT frontier concerns the refinements: Spin-c and Pin structures, fermionic symmetry-protected phases, anomalies on non-spin or nonorientable manifolds, defects that change spin structure, higher-form symmetry backgrounds intertwined with fermion parity, and global definitions of fermion path integrals.

For most perturbative flat-space QFT, the spin structure is hidden because Minkowski space has the trivial one. It reappears the moment spacetime has nontrivial topology, finite temperature, curved backgrounds, boundaries, defects, or gravitational anomalies.

## References

- H. B. Lawson and M.-L. Michelsohn, *Spin Geometry*. Standard mathematical reference for spin structures, spinor bundles, Clifford modules, and Dirac operators.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented introduction to spinors, spin structures, characteristic classes, monopoles, instantons, and gauge theory.
- T. Frankel, *The Geometry of Physics*. Useful for the geometric intuition behind frame bundles, forms, spinors, and gauge fields.
- D. S. Freed and K. K. Uhlenbeck, *Instantons and Four-Manifolds*. Useful for spin and Spin-c structures in four-dimensional gauge theory.
- T. Eguchi, P. B. Gilkey, and A. J. Hanson, “Gravitation, Gauge Theories and Differential Geometry.” Classic physics bridge between spin connections, Dirac operators, curvature, and topology.
- T. Friedrich, *Dirac Operators in Riemannian Geometry*. Compact reference for spin geometry and Dirac operators.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for Lorentz representations and spinors in flat spacetime.
- D. Z. Freed and M. J. Hopkins, papers and lectures on reflection positivity and invertible phases. Useful for advanced fermionic QFT, Pin structures, and modern anomaly language.

## Version history

- **2026-06-25:** Initial polished draft. Added spin-structure definition, frame-bundle lift, obstruction and classification, spinor bundles, vielbeins, spin connection, Dirac operator preview, examples, Spin-c and Pin variants, QFT boundary-condition discussion, exercises, and figure.
