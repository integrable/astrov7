---
title: "Vector Spaces and Duals"
description: "Explains vector spaces, dual vector spaces, bases, dual bases, pairings, linear maps, pullbacks, double duals, complex-linear versus Hermitian duals, and why covectors are indispensable in QFT notation."
sidebar:
  label: "Vector Spaces and Duals"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard references on finite-dimensional linear algebra, tensor notation, differential geometry, functional analysis prerequisites, and QFT convention practice, including Axler, Hoffman–Kunze, Roman, Frankel, Nakahara, Weinberg, Srednicki, Schwartz, and Zee."
topics:
  - vector space
  - dual vector space
  - basis
  - dual basis
  - covector
  - linear map
  - pullback
  - double dual
  - complex vector space
  - QFT notation
canonicalTopics:
  - vector-space
  - dual-vector-space
  - basis
  - dual-basis
  - covector
  - linear-map
  - pullback
  - double-dual
  - complex-vector-space
  - qft-notation
researchStatus:
  established:
    - "Finite-dimensional vector spaces, dual spaces, bases, dual bases, linear maps, pullbacks, and double duals are standard linear algebra."
    - "The distinction between a vector and a covector is convention-independent; identifying them requires extra structure such as a metric or Hermitian inner product."
  active:
    - "In QFT the finite-dimensional ideas reappear in infinite-dimensional test-function spaces, Hilbert spaces, operator algebras, distribution spaces, and derived or categorical settings, where topology and domains become essential."
---

## Summary

A vector space is a place where addition and scalar multiplication make sense. A dual vector space is the space of linear measurements on that vector space. If $V$ is a vector space over $\mathbb F$, where $\mathbb F=\mathbb R$ or $\mathbb C$, then

$$
V^*=\operatorname{Hom}_{\mathbb F}(V,\mathbb F)
$$

is the space of linear maps $V\to\mathbb F$. Elements of $V$ are vectors. Elements of $V^*$ are covectors, one-forms, or linear functionals, depending on context.

The basic pairing is

$$
\langle \alpha,v\rangle = \alpha(v),
\qquad \alpha\in V^*,\quad v\in V.
$$

It is not a metric. It is not an inner product. It is the canonical evaluation of a linear functional on a vector. This distinction is one of the cheapest ways to avoid expensive sign errors.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing a vector space, its dual, the evaluation pairing, components in a basis, and the pullback of a linear map.](/figures/math-toolkit/vector-dual-pairing.svg)

<figcaption>

A vector space $V$ and its dual $V^*$ come with a canonical pairing $\alpha(v)$. A basis $e_i$ gives vector components $v^i$, while the dual basis $\varepsilon^i$ gives covector components $\alpha_i$. A linear map $A:V\to W$ pushes vectors forward and pulls covectors back by $A^*:W^*\to V^*$.

</figcaption>
</figure>

In QFT, this is the type system behind momenta, gradients, sources, bras, test-function smearings, tensor indices, spinor duals, and representation duals. The algebra is simple. The damage begins when we silently identify $V$ with $V^*$ without saying which metric, inner product, symplectic form, charge-conjugation matrix, or invariant tensor did the identifying.

## Prerequisites

You should know matrix multiplication, bases, determinants, and elementary linear algebra. You should also know the site’s [Mathematical Conventions](/math-toolkit/conventions/) and the chapter overview [Linear Algebra, Tensors, and Index Notation](/math-toolkit/linear-algebra-tensors/).

No functional analysis is needed here. Infinite-dimensional Hilbert spaces, distributions, rigged Hilbert spaces, unbounded operators, and trace-class questions are handled elsewhere. This page keeps the finite-dimensional algebra clean.

## Vector spaces without coordinates

A vector space $V$ over $\mathbb F$ is a set with addition and scalar multiplication satisfying the usual linearity axioms. The elements of $\mathbb F$ are scalars. In QFT the relevant finite-dimensional vector spaces include:

| Space | Typical elements | Where it appears |
|---|---|---|
| Minkowski vector space | $x^\mu$, $p^\mu$ | spacetime vectors and momenta |
| Internal representation space | $\phi^i$, $\psi^a$ | flavor, gauge, and global symmetry multiplets |
| Spinor representation space | $\psi_\alpha$, $\bar\psi_{\dot\alpha}$ | Lorentz spinors and Clifford modules |
| Tangent space $T_pM$ | $X=X^\mu\partial_\mu$ | vector fields on spacetime |
| Cotangent space $T_p^*M$ | $\omega=\omega_\mu dx^\mu$ | one-forms, gradients, connections |

A coordinate column is not a vector. It is a representation of a vector after a basis has been chosen. If $e_1,\dots,e_n$ is a basis of $V$, then every $v\in V$ has a unique expansion

$$
v=v^i e_i.
$$

The numbers $v^i$ are the components of $v$ in that basis. The vector is the basis-independent object. The components are bookkeeping.

This distinction sounds fussy until the first Lorentz transformation, gauge transformation, or coordinate change. Then it is not fussy at all; it is the whole game.

## Dual spaces and covectors

The dual space $V^*$ consists of linear maps $\alpha:V\to\mathbb F$. Linearity means

$$
\alpha(av+bw)=a\alpha(v)+b\alpha(w)
$$

for $a,b\in\mathbb F$ and $v,w\in V$. Given a basis $e_i$ of $V$, the dual basis $\varepsilon^i$ of $V^*$ is defined by

$$
\varepsilon^i(e_j)=\delta^i{}_j.
$$

Every covector $\alpha\in V^*$ can be written as

$$
\alpha=\alpha_i\varepsilon^i.
$$

Evaluating on $v=v^i e_i$ gives

$$
\alpha(v)=\alpha_i v^i.
$$

The repeated upper-lower index indicates the canonical pairing between $V^*$ and $V$. Nothing has been raised or lowered. No metric has appeared.

:::note[Why covectors matter]
A covector is a linear measurement. Momentum measures displacement by $p_\mu dx^\mu$. A source measures a field by $\int d^dx\,J(x)\phi(x)$. A test function measures a distribution by $T[f]$. A bra measures a ket by $\langle \psi|\phi\rangle$. These are all versions of the same idea: dual objects act on primal objects.
:::

## How components transform

Let $e_i$ be a basis of $V$, and choose a new basis

$$
e'_i=e_j A^j{}_i,
$$

where $A$ is an invertible matrix. The same vector $v$ can be written as

$$
v=v^i e_i=v'^i e'_i.
$$

Substituting the new basis gives

$$
v^j=A^j{}_i v'^i,
\qquad
v'^i=(A^{-1})^i{}_j v^j.
$$

So vector components transform with the inverse matrix. That is why one sometimes calls them contravariant components.

The dual basis transforms as

$$
\varepsilon'^i=(A^{-1})^i{}_j\varepsilon^j.
$$

A covector $\alpha=\alpha_i\varepsilon^i=\alpha'_i\varepsilon'^i$ therefore has components

$$
\alpha'_i=\alpha_j A^j{}_i.
$$

Covector components transform with the same matrix as the basis vectors. That is why one sometimes calls them covariant components.

The pairing is invariant:

$$
\alpha'_i v'^i
=\alpha_j A^j{}_i (A^{-1})^i{}_k v^k
=\alpha_j v^j.
$$

This is the cleanest way to remember which object transforms how: the number $\alpha(v)$ cannot depend on the basis used to compute it.

## Linear maps and pullbacks

A linear map $A:V\to W$ sends vectors in $V$ to vectors in $W$. Choose bases $e_i$ of $V$ and $f_a$ of $W$. We write

$$
A e_i = f_a A^a{}_i.
$$

Then

$$
Av=f_a A^a{}_i v^i.
$$

The same map also acts on dual spaces in the reverse direction. The pullback

$$
A^*:W^*\to V^*
$$

is defined by

$$
(A^*\beta)(v)=\beta(Av),
\qquad \beta\in W^*,\quad v\in V.
$$

In components,

$$
(A^*\beta)_i=\beta_a A^a{}_i.
$$

The direction reversal is not a nuisance; it is the point. Vectors are pushed forward. Covectors are pulled back. Differential geometry, gauge theory, and Ward identities use this distinction constantly.

## The double dual

The double dual $V^{**}$ is the dual of the dual. There is a canonical linear map

$$
\iota:V\to V^{**},
\qquad
\iota(v)(\alpha)=\alpha(v).
$$

For finite-dimensional vector spaces, $\iota$ is an isomorphism. Thus one may identify $V$ with $V^{**}$ without choosing a basis or metric.

This is different from identifying $V$ with $V^*$. There is no canonical isomorphism $V\cong V^*$ for a general vector space. To identify vectors and covectors, one must add structure.

For example, a nondegenerate bilinear form $g:V\times V\to\mathbb F$ defines a map

$$
\flat_g:V\to V^*,
\qquad
\flat_g(v)(w)=g(v,w).
$$

If $g$ is nondegenerate, this map is an isomorphism. Its inverse is often denoted $\sharp_g:V^*\to V$. In components,

$$
v_i=g_{ij}v^j,
\qquad
\alpha^i=g^{ij}\alpha_j.
$$

The symbols $\flat$ and $\sharp$ are a nice antidote to one of the most common QFT mistakes: raising or lowering an index without knowing which bilinear form is being used.

## Metrics, symplectic forms, and other pairings

Different pairings have different meanings. They are not interchangeable.

A Euclidean inner product is symmetric and positive definite:

$$
\langle v,w\rangle=\langle w,v\rangle,
\qquad
\langle v,v\rangle>0\quad v\neq0.
$$

A Lorentzian metric is symmetric and nondegenerate but indefinite. In the site convention,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

A symplectic form is antisymmetric and nondegenerate:

$$
\omega(v,w)=-\omega(w,v).
$$

A Hermitian inner product on a complex vector space is sesquilinear rather than bilinear: it is linear in one argument and antilinear in the other. In physics bra-ket notation, $\langle \psi|\phi\rangle$ is linear in $|\phi\rangle$ and antilinear in $|\psi\rangle$.

These structures all define pairings, but they do not define the same pairing. A Lorentzian metric cannot be used like a Hilbert-space inner product. A symplectic form cannot be used like a Riemannian metric. A charge-conjugation matrix on spinors is not the spacetime metric wearing a trench coat.

## Complex vector spaces and Hermitian duals

For a complex vector space $V$, the algebraic dual $V^*$ is the space of complex-linear maps $V\to\mathbb C$:

$$
\alpha(av+bw)=a\alpha(v)+b\alpha(w).
$$

This is not the same as the conjugate vector space $\overline V$, whose scalar multiplication is conjugated. It is also not the same as the Hilbert-space bra associated to a ket by a Hermitian inner product.

If $\mathcal H$ is a Hilbert space, the map

$$
|\psi\rangle\mapsto \langle\psi|
$$

is antilinear in physics convention:

$$
|a\psi+b\chi\rangle
\mapsto
\overline a\langle\psi|+\overline b\langle\chi|.
$$

This is exactly why complex conjugation appears in probabilities, unitarity, and adjoints. In finite-dimensional unitary representation theory, an invariant Hermitian product lets us identify a representation with a conjugate dual in a controlled way. Without that structure, $V$, $V^*$, and $\overline V$ should be kept separate.

## Dual representations

Let a group $G$ act linearly on $V$ by $\rho(g):V\to V$. The dual representation on $V^*$ is defined so that the pairing remains invariant:

$$
\langle \rho^*(g)\alpha,\rho(g)v\rangle=\langle\alpha,v\rangle.
$$

Therefore

$$
\rho^*(g)\alpha=\alpha\circ \rho(g)^{-1}.
$$

The inverse is essential. It is why dual indices transform contragrediently. In gauge theory, if a field transforms in a representation $R$, then a source or conjugate field that pairs with it transforms in the dual representation $R^*$, or in the conjugate representation when a Hermitian structure is involved.

For infinitesimal transformations, if $X$ acts on $V$ as a matrix $T_X$, then the induced action on covectors is

$$
T_X^*=-T_X^{\mathsf T}
$$

in the dual basis. The minus sign comes from differentiating the inverse group element. In unitary physics conventions one often inserts factors of $i$ and Hermitian generators; those are convention choices layered on top of this algebraic fact.

## Gradients and differentials

For a smooth function $f:M\to\mathbb R$, its differential at $p\in M$ is a covector

$$
df_p\in T_p^*M.
$$

It acts on a tangent vector $X_p\in T_pM$ by directional differentiation:

$$
df_p(X_p)=X_p(f).
$$

The gradient $\nabla f$ is a vector field only after a metric has been chosen. With metric $g$,

$$
g(\nabla f,X)=df(X)
$$

for all vector fields $X$. In components,

$$
(\nabla f)^\mu=g^{\mu\nu}\partial_\nu f.
$$

Thus $\partial_\mu f$ is naturally a covector component, not a vector component. In flat Euclidean coordinates this distinction is easy to miss. In Lorentzian QFT, curved spacetime, and gauge theory, it is not optional.

## Distributions as dual vectors

The dual-space idea becomes genuinely powerful in distribution theory. A distribution is not usually a function. It is a continuous linear functional on a space of test functions. Schematically,

$$
T:\mathcal D\to\mathbb C,
\qquad
f\mapsto T[f].
$$

The delta distribution at $a$ is defined by

$$
\delta_a[f]=f(a).
$$

This is the infinite-dimensional analogue of a covector evaluating a vector. It explains why QFT fields are often smeared:

$$
\phi(f)=\int d^dx\,f(x)\phi(x).
$$

The local symbol $\phi(x)$ behaves like an operator-valued distribution. Its safe meaning is through its action on test functions.

## What QFT notation is hiding

Many standard QFT expressions are compact dual-pairing statements:

$$
p\cdot x=p_\mu x^\mu,
$$

$$
\int d^dx\,J(x)\phi(x),
$$

$$
\bar\psi_\alpha\psi^\alpha,
$$

$$
\operatorname{tr}_R(T^aT^b),
$$

$$
\omega(X,Y).
$$

Each formula pairs an object with a dual object, or uses extra structure to create such a pairing. The notation becomes trustworthy only when the spaces and pairings are explicit enough to be checked.

## Common pitfalls

**Treating vectors as columns.** A column is a coordinate representation. The vector is basis-independent.

**Treating covectors as row vectors.** A row is a coordinate representation of a covector after a basis has been chosen. The covector is the linear functional.

**Raising and lowering without naming the metric.** Index motion is not typography. It uses a nondegenerate bilinear form, and different spaces may carry different forms.

**Confusing the algebraic dual with the Hermitian adjoint.** For complex vector spaces, $V^*$, $\overline V$, and the Hilbert-space bra construction are related but distinct.

**Forgetting the inverse in the dual representation.** Dual actions use $g^{-1}$ so that $\alpha(v)$ stays invariant.

**Thinking $V\cong V^*$ canonically because dimensions match.** Equal dimensions are not enough. A canonical identification requires structure; otherwise it is basis-dependent.

**Ignoring topology in infinite dimensions.** In finite dimensions, all linear maps are continuous and $V\cong V^{**}$. In infinite dimensions, topological duals, algebraic duals, and double duals differ dramatically.

## Exercises

### Exercise 1: Dual-basis transformation

Let $e'_i=e_jA^j{}_i$ be a change of basis. Show that the dual basis transforms as

$$
\varepsilon'^i=(A^{-1})^i{}_j\varepsilon^j.
$$

Then derive the covector component transformation $\alpha'_i=\alpha_jA^j{}_i$.

<details><summary><strong>Solution</strong></summary>

The dual basis must satisfy $\varepsilon'^i(e'_j)=\delta^i{}_j$. Write $\varepsilon'^i=B^i{}_k\varepsilon^k$. Then

$$
\varepsilon'^i(e'_j)
=B^i{}_k\varepsilon^k(e_\ell A^\ell{}_j)
=B^i{}_kA^k{}_j.
$$

Thus $B^i{}_kA^k{}_j=\delta^i{}_j$, so $B=A^{-1}$ and

$$
\varepsilon'^i=(A^{-1})^i{}_j\varepsilon^j.
$$

Now use $\alpha=\alpha_i\varepsilon^i=\alpha'_i\varepsilon'^i$:

$$
\alpha_j\varepsilon^j
=\alpha'_i(A^{-1})^i{}_j\varepsilon^j.
$$

Therefore $\alpha_j=\alpha'_i(A^{-1})^i{}_j$. Multiplying by $A^j{}_k$ gives

$$
\alpha'_k=\alpha_jA^j{}_k.
$$

</details>

### Exercise 2: Pullback of a covector

Let $A:V\to W$ be linear and let $\beta\in W^*$. Prove that $A^*\beta\in V^*$ is linear and that

$$
(A^*\beta)_i=\beta_a A^a{}_i.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
(A^*\beta)(v)=\beta(Av).
$$

For $v,w\in V$ and $a,b\in\mathbb F$,

$$
(A^*\beta)(av+bw)
=\beta(A(av+bw))
=\beta(aAv+bAw)
=a\beta(Av)+b\beta(Aw),
$$

so $A^*\beta$ is linear.

Choose bases $e_i$ of $V$ and $f_a$ of $W$, with $Ae_i=f_aA^a{}_i$. If $\beta=\beta_a\varphi^a$ in the dual basis of $W^*$, then

$$
(A^*\beta)(e_i)=\beta(Ae_i)
=\beta(f_aA^a{}_i)
=\beta_aA^a{}_i.
$$

These are precisely the components of $A^*\beta$.

</details>

### Exercise 3: The differential is a covector

Let $f:\mathbb R^n\to\mathbb R$ be smooth. Show that at a point $x$, the map

$$
v\mapsto v^i\partial_i f(x)
$$

is a covector. Explain why turning it into a gradient vector requires a metric.

<details><summary><strong>Solution</strong></summary>

For fixed $x$, the expression

$$
df_x(v)=v^i\partial_i f(x)
$$

is linear in $v$, so $df_x\in T_x^*\mathbb R^n$. It assigns to a tangent vector the directional derivative of $f$ along that vector.

A gradient vector $\nabla f$ must satisfy

$$
g(\nabla f,v)=df(v)
$$

for all vectors $v$. Without $g$, there is no canonical way to convert the covector $df$ into a vector. With components, the conversion is

$$
(\nabla f)^i=g^{ij}\partial_j f.
$$

</details>

### Exercise 4: Dual representation sign

Let $\rho(e^{tX})=1+tT_X+O(t^2)$ act on $V$. Show that the induced infinitesimal action on $V^*$ is $-T_X^{\mathsf T}$ in the dual basis.

<details><summary><strong>Solution</strong></summary>

The dual action is

$$
\rho^*(g)\alpha=\alpha\circ\rho(g)^{-1}.
$$

For $g=e^{tX}$,

$$
\rho(g)^{-1}=1-tT_X+O(t^2).
$$

Thus

$$
(\rho^*(e^{tX})\alpha)(v)
=\alpha((1-tT_X)v)+O(t^2)
=\alpha(v)-t\alpha(T_Xv)+O(t^2).
$$

In components, $\alpha(T_Xv)=\alpha_i(T_X)^i{}_jv^j$, so

$$
\alpha'_j=\alpha_j-t\alpha_i(T_X)^i{}_j+O(t^2).
$$

Therefore the generator on covector components is $-(T_X)^{\mathsf T}$.

</details>

## Connections

The next page is [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), where pairings and products are extended to multi-index objects. Later pages in this chapter explain bilinear forms, index notation, exterior algebra, determinants, traces, and normal forms.

For tangent and cotangent spaces on manifolds, see [Manifolds](/math-toolkit/geometry-of-fields/manifolds/) and [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/). For infinite-dimensional duals, see [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/) and [Rigged Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/rigged-hilbert-spaces/). For dual representations in symmetry theory, see [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/) and [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/).

## References

Good linear-algebra references include Axler, *Linear Algebra Done Right*; Hoffman and Kunze, *Linear Algebra*; and Roman, *Advanced Linear Algebra*. For the same objects as they appear in geometry and physics, see Frankel, *The Geometry of Physics*, Nakahara, *Geometry, Topology and Physics*, and standard QFT texts by Weinberg, Srednicki, Schwartz, and Zee.

## Version history

- **2026-06-26:** Initial polished draft. Added vector spaces, dual spaces, basis transformations, pullbacks, double duals, complex-dual subtleties, dual representations, distributional examples, pitfalls, exercises, and cross-links.
