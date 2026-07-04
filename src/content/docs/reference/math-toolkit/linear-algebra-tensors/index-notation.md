---
title: "Index Notation"
description: "Explains Einstein notation as a type system for tensor algebra, including free and dummy indices, variance, contractions, Kronecker deltas, raising and lowering, matrix translation, and QFT index hygiene."
sidebar:
  label: "Index Notation"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard references on tensor notation, multilinear algebra, differential geometry, representation theory, and QFT convention practice, including Frankel, Nakahara, Weinberg, Srednicki, Schwartz, Zee, and common mathematical physics usage."
topics:
  - index notation
  - Einstein summation
  - tensor components
  - free index
  - dummy index
  - contraction
  - Kronecker delta
  - raising and lowering indices
  - abstract index notation
  - QFT notation
canonicalTopics:
  - index-notation
  - einstein-summation
  - tensor-components
  - free-index
  - dummy-index
  - contraction
  - kronecker-delta
  - raising-lowering-indices
  - abstract-index-notation
  - qft-notation
researchStatus:
  established:
    - "Einstein summation, tensor component notation, free and dummy indices, contractions, and basis-change rules are standard tools in multilinear algebra and differential geometry."
    - "Reliable index notation requires tracking which vector space each index belongs to and which pairing, metric, or invariant tensor is being used."
  active:
    - "Modern QFT uses many overlapping index systems — spacetime, spinor, gauge, flavor, form, replica, Keldysh, super, and categorical labels — so notation choices remain an active source of practical convention work."
---

## Summary

Index notation is compressed tensor algebra. A formula such as

$$
A^\mu B_\mu
$$

means: take a vector with components $A^\mu$, take a covector with components $B_\mu$, and apply the canonical pairing. A formula such as

$$
\eta_{\mu\nu}A^\mu B^\nu
$$

means: use the metric $\eta$ to turn one vector index into a dual index, then contract.

Index notation is powerful because it shows tensor type, basis transformation, and contraction pattern at a glance. It is dangerous because it can make illegal operations look legal. The cure is to read every index as a type label.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing index notation as a type system: free indices determine tensor type, repeated upper-lower indices contract, metrics raise and lower, and different index alphabets belong to different vector spaces.](/figures/math-toolkit/index-notation-type-system.svg)

<figcaption>

Index notation is a type system. Free indices tell you the type of the output. Repeated upper-lower indices are summed only when they refer to the same vector space and pairing. Metrics, symplectic forms, spinor epsilons, and group invariant tensors are the legal bridges between different variance conventions.

</figcaption>
</figure>

The best mental model is this: an equation with indices is not an equation for symbols; it is an equation between tensor components in every basis. Each free index must appear on both sides with the same type. Each repeated dummy index is a contracted internal wire. If that wire connects incompatible spaces, the formula is nonsense no matter how elegant it looks.

## Prerequisites

You should know [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), and [Bilinear Forms and Metrics](/math-toolkit/linear-algebra-tensors/bilinear-forms-and-metrics/). You should also know the site’s [Mathematical Conventions](/math-toolkit/conventions/), especially the mostly-minus Lorentz signature and Fourier convention.

This page focuses on finite-dimensional tensor notation and its QFT use. Functional derivatives, distributions, differential forms, spinors, and gauge theory each add refinements, but the basic index hygiene is the same.

## The Einstein convention

Einstein summation says that a repeated index appearing once up and once down is summed over:

$$
\alpha_i v^i=\sum_{i=1}^n \alpha_i v^i.
$$

The upper index labels components of a vector in $V$. The lower index labels components of a covector in $V^*$. Their repetition indicates the canonical evaluation pairing

$$
V^*\otimes V\to\mathbb F.
$$

In this notation,

$$
A^i{}_j v^j
$$

means the $i$th component of the vector $Av$. The index $j$ is summed. The index $i$ is free.

A useful rule:

:::note[Free indices determine the type]
The free indices in a tensor expression determine the tensor type of the result. Dummy indices are internal contractions and may be renamed. Every term in a sum must have exactly the same free indices with the same variance and meaning.
:::

For example,

$$
T^i{}_{jk}v^j w^k
$$

has one free upper index $i$, so the result is a vector component. The repeated indices $j,k$ are summed.

## Free indices and dummy indices

An index is free if it appears exactly once in a monomial term. It is dummy if it is repeated and summed over.

The expression

$$
A^i{}_jB^j{}_k
$$

has free indices $i,k$ and dummy index $j$. It is the component expression for matrix composition $AB$:

$$
(AB)^i{}_k=A^i{}_jB^j{}_k.
$$

Dummy indices have no identity. They are placeholders. Thus

$$
A^i{}_jB^j{}_k=A^i{}_\ell B^\ell{}_k.
$$

Free indices cannot be renamed in only one term or one side of an equation. The equation

$$
C^i{}_k=A^i{}_jB^j{}_k
$$

is equivalent to

$$
C^a{}_b=A^a{}_cB^c{}_b
$$

if every free and dummy index is renamed consistently. But writing

$$
C^i{}_k=A^a{}_jB^j{}_k
$$

changes the free-index pattern and is generally meaningless.

## Tensor type from indices

A tensor of type $(r,s)$ has $r$ upper and $s$ lower indices:

$$
T^{i_1\dots i_r}{}_{j_1\dots j_s}.
$$

In finite dimensions this is a component expression for an element of

$$
V^{\otimes r}\otimes(V^*)^{\otimes s}.
$$

Examples:

| Components | Tensor type | Typical interpretation |
|---|---:|---|
| $v^i$ | $(1,0)$ | vector |
| $\alpha_i$ | $(0,1)$ | covector |
| $A^i{}_j$ | $(1,1)$ | linear map $V\to V$ |
| $g_{ij}$ | $(0,2)$ | bilinear form or metric |
| $g^{ij}$ | $(2,0)$ | inverse metric |
| $T^{ij}{}_k$ | $(2,1)$ | multilinear tensor |

This table assumes all indices refer to the same vector space $V$. In QFT, they often do not. A Lorentz index $\mu$, a spinor index $\alpha$, an adjoint index $a$, a flavor index $i$, and a spacetime-coordinate index $m$ may appear in the same formula, but they belong to different spaces.

## Different alphabets, different spaces

A clean convention uses different index alphabets for different vector spaces. A typical relativistic QFT formula may contain:

| Index | Space | Example |
|---|---|---|
| $\mu,\nu,\rho$ | spacetime tangent or cotangent space | $A_\mu$, $p^\mu$ |
| $i,j,k$ | flavor or field-space index | $\phi^i$ |
| $a,b,c$ | Lie algebra or adjoint index | $F^a_{\mu\nu}$ |
| $\alpha,\beta$ | left-handed spinor index | $\psi_\alpha$ |
| $\dot\alpha,\dot\beta$ | right-handed spinor index | $\bar\psi_{\dot\alpha}$ |
| $m,n$ | coordinate index on a general manifold | $g_{mn}$ |

These labels are not cosmetic. They prevent illegal contractions. The expression

$$
A_\mu B^\mu
$$

can be meaningful as a spacetime contraction. The expression

$$
A_a B^\mu
$$

has one gauge index and one spacetime index; there is no canonical contraction between them. If a formula sums such indices, some additional tensor must be present.

For example,

$$
F^a_{\mu\nu}F^{a\mu\nu}
$$

contains two independent contractions: one over spacetime indices using $\eta^{\mu\nu}$ or $g^{\mu\nu}$, and one over Lie-algebra indices using an invariant bilinear form such as $\delta^{ab}$ in an orthonormal adjoint basis.

## The Kronecker delta

The Kronecker delta

$$
\delta^i{}_j
$$

is the component expression for the identity map $V\to V$. It satisfies

$$
\delta^i{}_j v^j=v^i,
\qquad
\alpha_i\delta^i{}_j=\alpha_j.
$$

It has one upper and one lower index because it maps vectors to vectors or covectors to covectors. In a basis,

$$
1_V=e_i\otimes\varepsilon^i.
$$

The trace of the identity is

$$
\delta^i{}_i=\dim V.
$$

Do not confuse $\delta^i{}_j$ with a metric $g_{ij}$ or inverse metric $g^{ij}$. The metric changes variance. The Kronecker delta preserves it. In Euclidean orthonormal coordinates, they may have the same numerical array, but they are not the same tensor.

This distinction matters in Lorentzian signature. The identity has components

$$
\delta^\mu{}_{\nu}=\operatorname{diag}(1,1,1,1),
$$

whereas the mostly-minus metric has components

$$
\eta_{\mu\nu}=\operatorname{diag}(1,-1,-1,-1).
$$

Confusing these two is a reliable way to make a sign error and then blame the universe.

## Raising and lowering indices

A nondegenerate bilinear form $g$ gives maps

$$
\flat_g:V\to V^*,
\qquad
\sharp_g:V^*\to V.
$$

In components,

$$
v_i=g_{ij}v^j,
\qquad
\alpha^i=g^{ij}\alpha_j,
$$

where

$$
g^{ik}g_{kj}=\delta^i{}_j.
$$

For spacetime vectors in the default mostly-minus convention,

$$
A_0=A^0,
\qquad
A_i=-A^i
$$

for spatial $i=1,2,3$ in inertial Cartesian coordinates.

Thus

$$
A_\mu B^\mu=A^0B^0-\mathbf A\cdot\mathbf B.
$$

The notation $A_\mu$ is not merely $A^\mu$ written lower. It is the covector obtained from $A^\mu$ using the metric.

## Matrix notation versus index notation

Index notation and matrix notation often describe the same operation from different angles. For a linear map $A:V\to V$,

$$
(Av)^i=A^i{}_jv^j.
$$

For composition,

$$
(AB)^i{}_k=A^i{}_jB^j{}_k.
$$

For a bilinear form $g$ acting on two vectors,

$$
g(v,w)=g_{ij}v^i w^j.
$$

In matrix notation this is often written

$$
v^{\mathsf T}g w.
$$

But the transpose notation hides variance. The object $v^{\mathsf T}$ is not intrinsically a covector unless a basis and the usual coordinate pairing have been chosen. Tensor notation keeps the type visible:

$$
g_{ij}v^i w^j.
$$

For QFT, the tensor notation is often safer because there are many different vector spaces in play at once.

## Contractions and traces

A contraction pairs one upper and one lower index of the same type. For an endomorphism,

$$
A^i{}_i=\operatorname{tr}A.
$$

For a type $(2,1)$ tensor,

$$
T^{ij}{}_j
$$

is a vector component with free index $i$. The contraction is between the second upper index and the lower index.

Different contraction choices are different maps. For

$$
T^{ij}{}_k,
$$

one may form

$$
T^{ij}{}_j
$$

or

$$
T^{ij}{}_i.
$$

These are generally different vectors. Index notation does not choose for you.

The same issue appears in QFT loop calculations. A trace over spinor indices,

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu),
$$

is not a trace over color indices,

$$
\operatorname{tr}_R(T^aT^b),
$$

and neither is a spacetime contraction. The word “trace” always needs its vector space.

## Derivative indices

For a scalar function $f$, the derivative $\partial_\mu f$ is naturally a covector component:

$$
df=(\partial_\mu f)dx^\mu.
$$

A vector derivative is obtained only after raising the index:

$$
\partial^\mu f=\eta^{\mu\nu}\partial_\nu f
$$

in flat spacetime.

With mostly-minus signature,

$$
\partial_\mu=\frac{\partial}{\partial x^\mu}
=(\partial_t,\nabla),
$$

while

$$
\partial^\mu=\eta^{\mu\nu}\partial_\nu
=(\partial_t,-\nabla).
$$

Thus the d’Alembertian is

$$
\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

This is why raising the index on a derivative is not harmless. It inserts the metric.

## Abstract indices and component indices

There are two related but distinct uses of indices.

In component index notation, $v^i$ is a number depending on a chosen basis. The equation

$$
w^i=A^i{}_jv^j
$$

means an equality of components in that basis.

In abstract index notation, an index labels tensor type rather than a component slot. One writes $v^a$, $\omega_a$, $T^a{}_b$ to indicate tensor character without choosing a basis. The repeated abstract index still indicates a contraction, but the letters are not numerical labels.

Physicists often use a hybrid notation: concrete enough to compute, abstract enough to hide the basis. This is fine when done carefully. The safety rule is: every formula should be meaningful as a coordinate-independent tensor statement.

## Symmetrization and antisymmetrization notation

Symmetrization and antisymmetrization are often written with parentheses and brackets:

$$
T_{(ij)}=\frac12(T_{ij}+T_{ji}),
$$

$$
T_{[ij]}=\frac12(T_{ij}-T_{ji}).
$$

For more indices, the convention used in this volume includes the factorial normalization:

$$
T_{[i_1\dots i_p]}
=\frac{1}{p!}\sum_{\sigma\in S_p}\operatorname{sgn}(\sigma)
T_{i_{\sigma(1)}\dots i_{\sigma(p)}}.
$$

This is the convention that makes exterior forms clean:

$$
\omega=\frac{1}{p!}\omega_{\mu_1\dots\mu_p}
 dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p}.
$$

Always check whether a source includes the $1/p!$ in bracket notation. Both conventions exist. Naturally. Because apparently one convention would have been too merciful.

## Index placement in common QFT formulas

A few examples show how much structure is packed into ordinary notation.

### Scalar kinetic term

$$
\frac12\partial_\mu\phi\,\partial^\mu\phi
=\frac12\eta^{\mu\nu}\partial_\mu\phi\,\partial_\nu\phi.
$$

The metric is hidden in $\partial^\mu$.

### Gauge kinetic term

$$
-\frac14 F^a_{\mu\nu}F^{a\mu\nu}.
$$

This contracts antisymmetric spacetime indices with $\eta^{\mu\nu}$ and adjoint gauge indices with an invariant form. The minus sign is adapted to mostly-minus Lorentz signature.

### Yukawa coupling

$$
y\phi\bar\psi\psi.
$$

This suppresses spinor indices, possible flavor indices, representation duals, and Hermitian conjugation conventions. A more explicit expression might contain an invariant tensor $y_{ij}$, a spinor pairing, and a gauge-singlet projection.

### Covariant derivative

$$
(D_\mu\phi)^i=\partial_\mu\phi^i+(A_\mu)^a(T_a)^i{}_j\phi^j.
$$

Here $\mu$ is a spacetime covector index, $a$ is a Lie algebra index, and $i,j$ are representation indices. The repeated $a$ and $j$ are summed, but they live in different spaces and use different contractions.

## Common pitfalls

**Mismatched free indices.** An equation such as $A^i=B_j$ is not a tensor equation unless an identification between $V$ and $V^*$ has been specified.

**Using a dummy index more than twice.** Expressions like $A_iB_iC_i$ are ambiguous or illegal in standard Einstein notation. Use explicit sums or introduce invariant tensors.

**Contracting indices from different spaces.** A Lorentz index cannot be summed with a gauge index. Same letter, different job? Rename it before it bites.

**Confusing $\delta^i{}_j$ with $g_{ij}$.** The identity preserves variance. The metric changes variance.

**Raising a derivative without inserting the metric.** $\partial^\mu$ means $\eta^{\mu\nu}\partial_\nu$ in flat spacetime, not merely a relabeled derivative.

**Treating matrix transpose as coordinate-free.** Transpose depends on a pairing. The adjoint depends on an inner product. In indefinite signature and complex spaces, the differences matter.

**Suppressing too many indices too early.** Compact notation is good after the tensor structure is understood. Before that, it can hide the only part of the formula that mattered.

## Exercises

### Exercise 1: Free-index consistency

Which of the following can be a valid tensor equation without adding extra structure?

$$
A^i=B^i,
\qquad
A^i=B_i,
\qquad
C^i{}_j=A^iB_j,
\qquad
D_i=A^jB_{ij}.
$$

<details><summary><strong>Solution</strong></summary>

The equation

$$
A^i=B^i
$$

can be valid because both sides have one free upper index of the same type.

The equation

$$
A^i=B_i
$$

is not valid without extra structure, because the left side is a vector component and the right side is a covector component.

The expression

$$
C^i{}_j=A^iB_j
$$

can be valid: both sides have one free upper index $i$ and one free lower index $j$.

The expression

$$
D_i=A^jB_{ij}
$$

can be valid: $j$ is a dummy index and $i$ is the free lower index.

</details>

### Exercise 2: Rename dummy indices

Show that

$$
A^i{}_jB^j{}_k=A^i{}_\ell B^\ell{}_k.
$$

Why is it wrong to write $A^m{}_jB^j{}_k$ for the same expression while leaving the left side as $C^i{}_k$?

<details><summary><strong>Solution</strong></summary>

The index $j$ is dummy: it is summed over. A dummy index can be renamed consistently, so

$$
A^i{}_jB^j{}_k=A^i{}_\ell B^\ell{}_k.
$$

The index $i$ is free. If one changes $A^i{}_j$ to $A^m{}_j$ without also changing the free index on the left side, the expression now has free indices $m,k$ rather than $i,k$. It is a different tensor component expression.

</details>

### Exercise 3: Identity versus metric

In four-dimensional mostly-minus Minkowski space, compute $\delta^\mu{}_{\mu}$ and $\eta_{\mu\nu}\eta^{\mu\nu}$.

<details><summary><strong>Solution</strong></summary>

The trace of the identity is

$$
\delta^\mu{}_{\mu}=4.
$$

For the metric contraction,

$$
\eta_{\mu\nu}\eta^{\mu\nu}
=\delta_\mu{}^\mu=4,
$$

because $\eta^{\mu\nu}$ is the inverse metric. This result is not the same as summing only diagonal entries of $\eta_{\mu\nu}$. The expression contracts the metric with its inverse, not the trace of the metric matrix by itself.

</details>

### Exercise 4: Raising a derivative

Using mostly-minus signature, show that

$$
\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

<details><summary><strong>Solution</strong></summary>

In inertial coordinates,

$$
\partial_\mu=(\partial_t,\partial_1,\partial_2,\partial_3).
$$

Raising with $\eta^{\mu\nu}=\operatorname{diag}(1,-1,-1,-1)$ gives

$$
\partial^\mu=(\partial_t,-\partial_1,-\partial_2,-\partial_3).
$$

Therefore

$$
\partial_\mu\partial^\mu
=\partial_t^2-
\partial_1^2-
\partial_2^2-
\partial_3^2
=\partial_t^2-\nabla^2.
$$

</details>

### Exercise 5: Matrix multiplication as contraction

Let $A:V\to V$ and $B:V\to V$ have components $A^i{}_j$ and $B^i{}_j$. Show that the component expression for $AB$ is

$$
(AB)^i{}_k=A^i{}_jB^j{}_k.
$$

<details><summary><strong>Solution</strong></summary>

Act on a vector $v$:

$$
(Bv)^j=B^j{}_k v^k.
$$

Then

$$
(A(Bv))^i=A^i{}_j(Bv)^j
=A^i{}_jB^j{}_k v^k.
$$

Since this holds for every $v^k$, the matrix components of $AB$ are

$$
(AB)^i{}_k=A^i{}_jB^j{}_k.
$$

</details>

## Connections

The previous page is [Bilinear Forms and Metrics](/math-toolkit/linear-algebra-tensors/bilinear-forms-and-metrics/). Earlier pages in this chapter introduced [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/) and [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/). Later pages in this chapter develop symmetrization, antisymmetrization, exterior algebra, determinants, traces, Jacobians, eigenvalues, and normal forms.

For index notation in geometry, see [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), and [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/). For spinor indices, see [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/), [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/), and [Fierz Identities](/math-toolkit/clifford-spinors/fierz-identities/).

## References

For index notation in geometry and physics, see Frankel, *The Geometry of Physics* and Nakahara, *Geometry, Topology and Physics*. For QFT usage, compare Weinberg, Srednicki, Schwartz, and Zee, especially their conventions for Lorentz indices, spinor indices, gamma matrices, and gauge traces. For the underlying multilinear algebra, see standard linear-algebra references such as Axler, Hoffman–Kunze, and Roman.

## Version history

- **2026-06-26:** Initial polished draft. Added Einstein summation, free and dummy indices, tensor types, index alphabets, Kronecker deltas, raising and lowering, matrix translation, contractions, derivative indices, abstract-index warnings, QFT examples, pitfalls, exercises, and cross-links.
