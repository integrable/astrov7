---
title: "Tensor Products"
description: "Explains tensor products as the universal home of bilinear maps, including bases, components, simple and non-simple tensors, tensor products of maps, duals, contractions, tensor types, direct sums versus tensor products, and QFT applications."
sidebar:
  label: "Tensor Products"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard references on tensor products, multilinear algebra, tensor notation, representation theory prerequisites, differential geometry, and QFT applications, including Axler, Hoffman–Kunze, Roman, Frankel, Nakahara, Fulton–Harris, Weinberg, Srednicki, Schwartz, and Zee."
topics:
  - tensor product
  - multilinear algebra
  - bilinear map
  - universal property
  - simple tensor
  - tensor rank
  - contraction
  - tensor type
  - product Hilbert space
  - QFT notation
canonicalTopics:
  - tensor-product
  - multilinear-algebra
  - bilinear-map
  - universal-property
  - simple-tensor
  - tensor-rank
  - contraction
  - tensor-type
  - product-hilbert-space
  - qft-notation
researchStatus:
  established:
    - "Tensor products of finite-dimensional vector spaces are standard and are characterized by a universal property for bilinear maps."
    - "Finite-dimensional tensor products organize multilinear maps, tensor components, contractions, product representations, and composite systems."
  active:
    - "In QFT and mathematical physics, tensor products acquire analytic, topological, categorical, and operator-algebraic refinements; infinite-dimensional tensor products and local operator products require additional structure."
---

## Summary

The tensor product $V\otimes W$ is the vector space whose linear maps are the same thing as bilinear maps out of $V\times W$. It is defined by the rule

$$
\operatorname{Linear}(V\otimes W,X)
\cong
\operatorname{Bilinear}(V\times W,X).
$$

Equivalently, every bilinear map $b:V\times W\to X$ factors uniquely through a linear map $\widetilde b:V\otimes W\to X$:

$$
\widetilde b(v\otimes w)=b(v,w).
$$

This is the universal property. It is more important than any component formula. Component formulas are what the universal property looks like after choosing bases.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing the universal property of the tensor product, a basis of simple tensors, and QFT examples such as product states, multiplets, and multilinear couplings.](/figures/math-toolkit/tensor-product-universal-property.svg)

<figcaption>

The tensor product linearizes bilinear dependence. A bilinear map $b(v,w)$ is equivalent to a linear map out of $V\otimes W$. In QFT this language organizes product Hilbert spaces, tensor product representations, multi-index fields, multilinear couplings, local composite operators, and contractions.

</figcaption>
</figure>

For QFT, tensor products are everywhere: multiparticle state spaces, tensor product representations, spinor-vector fields, products of local operators, gauge-invariant contractions, Feynman-rule index factors, and the algebraic backbone of identical-particle symmetrization. If vector spaces and duals tell you what one index means, tensor products tell you what a string of indices means.

## Prerequisites

You should know [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/). You should be comfortable with bases, dual bases, linear maps, and the evaluation pairing $\alpha(v)$.

This page discusses algebraic tensor products in finite dimensions. Infinite-dimensional Hilbert-space completions, operator tensor products, nuclear spaces, and local operator algebras require extra topology and are handled in the functional-analysis and rigorous-QFT parts of the site.

## Why tensor products exist

Suppose $V,W,X$ are vector spaces over $\mathbb F$. A map

$$
B:V\times W\to X
$$

is bilinear if it is linear in each slot separately:

$$
B(cv_1+dv_2,w)=cB(v_1,w)+dB(v_2,w),
$$

and

$$
B(v,cw_1+dw_2)=cB(v,w_1)+dB(v,w_2).
$$

A bilinear map is not usually linear as a map from $V\times W$ to $X$, because $V\times W$ has componentwise addition. The tensor product $V\otimes W$ is built so that bilinear maps become honest linear maps.

The construction starts with formal symbols $v\otimes w$ and imposes bilinearity relations:

$$
(cv_1+dv_2)\otimes w
=c(v_1\otimes w)+d(v_2\otimes w),
$$

$$
v\otimes(cw_1+dw_2)
=c(v\otimes w_1)+d(v\otimes w_2).
$$

The result is a vector space $V\otimes W$ together with a bilinear map

$$
q:V\times W\to V\otimes W,
\qquad
q(v,w)=v\otimes w,
$$

such that every bilinear $B:V\times W\to X$ factors uniquely through $q$.

That sentence is the definition worth remembering.

## Bases and components

If $e_i$ is a basis of $V$ and $f_a$ is a basis of $W$, then

$$
e_i\otimes f_a
$$

is a basis of $V\otimes W$. Therefore

$$
\dim(V\otimes W)=\dim V\,\dim W.
$$

A general element $T\in V\otimes W$ can be written as

$$
T=T^{ia}e_i\otimes f_a.
$$

A simple tensor, also called a decomposable tensor, is one of the form

$$
v\otimes w.
$$

Its components factor:

$$
(v\otimes w)^{ia}=v^i w^a.
$$

Not every tensor is simple. A general $T^{ia}$ is a matrix of components, and it factors as $v^i w^a$ only when that matrix has rank one. The tensor product is made of finite sums of simple tensors:

$$
T=\sum_{r=1}^k v_r\otimes w_r.
$$

The smallest such $k$ is the tensor rank in this two-factor case. For more factors, tensor rank becomes subtle quickly; happily, most QFT calculations need the tensor product itself, not a theory of tensor rank.

## The universal property in practice

Let $\alpha\in V^*$ and $\beta\in W^*$. The rule

$$
(v,w)\mapsto \alpha(v)\beta(w)
$$

is bilinear. Therefore it defines a unique linear functional on $V\otimes W$, denoted $\alpha\otimes\beta$, with

$$
(\alpha\otimes\beta)(v\otimes w)=\alpha(v)\beta(w).
$$

In finite dimensions, every linear functional on $V\otimes W$ is a sum of such simple dual tensors, and there is a canonical isomorphism

$$
(V\otimes W)^*\cong V^*\otimes W^*.
$$

This identity is finite-dimensional. In infinite dimensions, the correct statement depends on which topology and which completed tensor product are being used.

Similarly, a bilinear form $g:V\times V\to\mathbb F$ is equivalent to a linear functional

$$
\widetilde g:V\otimes V\to\mathbb F,
\qquad
\widetilde g(v\otimes w)=g(v,w).
$$

This is why bilinear forms are tensors of type $(0,2)$.

## Tensor products of linear maps

If $A:V\to V'$ and $B:W\to W'$ are linear maps, their tensor product is the linear map

$$
A\otimes B:V\otimes W\to V'\otimes W'
$$

specified on simple tensors by

$$
(A\otimes B)(v\otimes w)=Av\otimes Bw.
$$

In components, if

$$
A e_i=e'_{i'}A^{i'}{}_i,
\qquad
B f_a=f'_{a'}B^{a'}{}_a,
$$

then

$$
(A\otimes B)(e_i\otimes f_a)
=e'_{i'}\otimes f'_{a'}\,A^{i'}{}_iB^{a'}{}_a.
$$

This formula is the algebra behind product representations. If $G$ acts on $V$ by $\rho$ and on $W$ by $\sigma$, then $G$ acts on $V\otimes W$ by

$$
(\rho\otimes\sigma)(g)=\rho(g)\otimes\sigma(g).
$$

This is how spin, flavor, color, and spacetime representation indices combine.

## Tensor type

A tensor of type $(r,s)$ on $V$ is an element of

$$
V^{\otimes r}\otimes (V^*)^{\otimes s}.
$$

In a basis, its components look like

$$
T^{i_1\dots i_r}{}_{j_1\dots j_s}.
$$

The upper indices correspond to $V$ factors. The lower indices correspond to $V^*$ factors. This is bookkeeping, not decoration.

Equivalently, a type $(r,s)$ tensor can be regarded as a multilinear map after using the canonical finite-dimensional identifications. For example,

$$
T\in V\otimes V^*
$$

can be identified with a linear map $V\to V$, because

$$
V\otimes V^*\cong \operatorname{End}(V)
$$

in finite dimensions. In components,

$$
T=T^i{}_j e_i\otimes\varepsilon^j
$$

acts as

$$
v^j e_j\mapsto T^i{}_jv^j e_i.
$$

This identification is canonical in finite dimensions, but one should still remember what spaces are being paired.

## Contractions

A contraction uses the canonical pairing between a dual factor and a vector factor. For example,

$$
C:V\otimes V^*\to\mathbb F,
\qquad
C(v\otimes\alpha)=\alpha(v).
$$

For a type $(1,1)$ tensor $T=T^i{}_j e_i\otimes\varepsilon^j$, the contraction is

$$
C(T)=T^i{}_i,
$$

which is the trace of the corresponding endomorphism.

For a type $(2,1)$ tensor

$$
T=T^{ij}{}_k e_i\otimes e_j\otimes\varepsilon^k,
$$

one possible contraction pairs the second vector factor with the covector factor:

$$
T^{ij}{}_j e_i.
$$

Another contraction pairs the first vector factor with the covector factor:

$$
T^{ij}{}_i e_j.
$$

These are different operations. Index notation hides the maps, but it does not make them disappear.

## Tensor products versus direct sums

Direct sums and tensor products answer different questions.

| Construction | Dimension | Meaning | Typical QFT use |
|---|---:|---|---|
| $V\oplus W$ | $\dim V+\dim W$ | a $V$ component and a $W$ component side by side | multiplets with independent sectors, block matrices |
| $V\otimes W$ | $\dim V\dim W$ | bilinear combination of $V$ and $W$ data | product states, product representations, multi-index tensors |

A Dirac spinor written as a pair of Weyl spinors is naturally a direct-sum statement:

$$
S_D\cong S_L\oplus S_R.
$$

A vector-spinor, such as the field content behind a Rarita–Schwinger-type object, is naturally a tensor-product statement:

$$
V_{\text{spacetime}}\otimes S.
$$

A field carrying both color and flavor indices lives in a tensor product of representation spaces, not in a direct sum unless the theory says so.

## Tensor products and composite systems

In ordinary quantum mechanics, if two finite-dimensional systems have state spaces $\mathcal H_1$ and $\mathcal H_2$, the combined system has state space

$$
\mathcal H_1\otimes\mathcal H_2.
$$

A simple tensor

$$
|\psi\rangle\otimes|\chi\rangle
$$

is an unentangled product state. A general vector

$$
|\Psi\rangle=\sum_{ia}C_{ia}|i\rangle\otimes|a\rangle
$$

need not factor. Entanglement is precisely the failure of a state to be a simple tensor.

In QFT, product Hilbert spaces are more subtle. Local algebras, gauge constraints, Gauss-law edge modes, and continuum limits can obstruct naive factorization. The algebraic tensor product remains the local model, but the physical Hilbert-space factorization question requires more than finite-dimensional multilinear algebra.

## Tensor products of representations

If $V$ and $W$ are representation spaces of a group $G$, then $V\otimes W$ is again a representation space. The representation may decompose into irreducibles:

$$
V\otimes W\cong \bigoplus_\lambda N_\lambda R_\lambda.
$$

This is the algebra behind angular-momentum addition, Clebsch–Gordan coefficients, color decompositions, flavor multiplets, and operator product selection rules.

For $SU(2)$, for example,

$$
\frac12\otimes\frac12=0\oplus1.
$$

The left side is the tensor product of two spin-$1/2$ representation spaces. The right side is its decomposition into irreducible spin-$0$ and spin-$1$ pieces. The tensor product creates the space; representation theory decomposes it.

## Tensor products and local operators

Local QFT notation often suppresses tensor products. A scalar Yukawa coupling schematically written as

$$
y\phi\bar\psi\psi
$$

contains several hidden tensor operations:

- multiplication of local operator-valued distributions,
- contraction of spinor indices,
- contraction or projection of internal representation indices,
- possible Hermitian or charge-conjugation pairings,
- renormalization of the composite operator.

At the algebraic level, the coupling coefficient is an invariant tensor. If fields transform in representations $R_1,R_2,R_3$, then a cubic invariant is equivalently an element of

$$
\operatorname{Hom}_G(R_1\otimes R_2\otimes R_3,\mathbb F),
$$

or a $G$-invariant multilinear map

$$
R_1\times R_2\times R_3\to\mathbb F.
$$

This is a good way to read interaction terms: they are invariant multilinear maps dressed with spacetime dependence and dynamics.

## Symmetric and antisymmetric tensors

Given $V\otimes V$, there are two important subspaces when the characteristic is not two:

$$
\operatorname{Sym}^2 V
$$

and

$$
\Lambda^2 V.
$$

They are obtained by projecting onto tensors symmetric or antisymmetric under exchange of the two factors:

$$
v\otimes w+w\otimes v,
\qquad
v\otimes w-w\otimes v.
$$

Bosonic and fermionic many-particle states use symmetrized and antisymmetrized tensor powers. Differential forms use exterior powers of cotangent spaces. Curvature two-forms, field strengths, volume forms, and characteristic classes all depend on this specialization of tensor products.

This chapter treats symmetrization, antisymmetrization, and exterior algebra in later pages. Here the key point is that those constructions start from tensor powers.

## Tensor products are not products of components

The notation $v\otimes w$ is not the same as the scalar product $v\cdot w$, the matrix product $vw$, or the Cartesian product $(v,w)$.

The tensor product keeps both inputs. A pairing consumes one vector and one covector to produce a scalar. A direct product keeps an ordered pair but does not impose bilinearity. A matrix product contracts an index. These are distinct operations:

$$
v\otimes w \in V\otimes W,
$$

$$
\alpha(v)\in\mathbb F,
$$

$$
(v,w)\in V\times W,
$$

$$
A^i{}_jB^j{}_k\in \operatorname{End}(V).
$$

When a calculation feels like indices are “multiplying,” ask which of these operations is really being used. This tiny pause saves lives, or at least afternoons.

## Common pitfalls

**Thinking every tensor is a product.** Every tensor is a sum of simple tensors, but not every tensor is one simple tensor.

**Confusing $V\oplus W$ with $V\otimes W$.** Direct sums describe side-by-side components. Tensor products describe bilinear combination and composite structure.

**Forgetting the universal property.** Tensor products are not defined by arrays. Arrays are basis-dependent shadows of the universal bilinear construction.

**Contracting two vector indices without a pairing.** The canonical contraction is between $V^*$ and $V$. Contracting two $V$ indices requires a bilinear form or invariant tensor.

**Assuming finite-dimensional identities survive unchanged in field theory.** In infinite dimensions, tensor products need completions; products of distributions may be singular; Hilbert-space factorization can fail in gauge theories.

**Using the same symbol for different tensor factors.** A spacetime vector index, spinor index, color index, flavor index, and form degree live in different vector spaces. Their tensor products are real; their indices should not be casually interchanged.

## Exercises

### Exercise 1: Bilinear maps become linear maps

Let $B:V\times W\to X$ be bilinear. Assuming the universal property of $V\otimes W$, show that the linear map $\widetilde B:V\otimes W\to X$ is uniquely determined by its values on simple tensors.

<details><summary><strong>Solution</strong></summary>

The universal property states that there is a unique linear map $\widetilde B$ such that

$$
\widetilde B(v\otimes w)=B(v,w)
$$

for all $v\in V$ and $w\in W$. Since every tensor in $V\otimes W$ is a finite sum of simple tensors,

$$
T=\sum_r v_r\otimes w_r,
$$

linearity forces

$$
\widetilde B(T)=\sum_r\widetilde B(v_r\otimes w_r)
=\sum_r B(v_r,w_r).
$$

Thus the values on simple tensors determine $\widetilde B$ on all tensors. The universal property guarantees this assignment is well-defined, meaning it does not depend on the chosen decomposition of $T$ into simple tensors.

</details>

### Exercise 2: Not every tensor is simple

Let $V=W=\mathbb R^2$ with bases $e_1,e_2$ and $f_1,f_2$. Show that

$$
T=e_1\otimes f_1+e_2\otimes f_2
$$

is not a simple tensor.

<details><summary><strong>Solution</strong></summary>

If $T=v\otimes w$, with $v=v^1e_1+v^2e_2$ and $w=w^1f_1+w^2f_2$, then its component matrix is

$$
T^{ia}=v^i w^a.
$$

This matrix has rank at most one. But the tensor in the problem has component matrix

$$
\begin{pmatrix}
1&0\\
0&1
\end{pmatrix},
$$

which has rank two. Therefore $T$ cannot be written as a single simple tensor.

</details>

### Exercise 3: Tensor product of dual bases

Let $e_i$ be a basis of $V$ with dual $\varepsilon^i$, and let $f_a$ be a basis of $W$ with dual $\varphi^a$. Show that $\varepsilon^i\otimes\varphi^a$ is dual to $e_j\otimes f_b$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
(\varepsilon^i\otimes\varphi^a)(e_j\otimes f_b)
=\varepsilon^i(e_j)\varphi^a(f_b).
$$

Using the dual-basis relations gives

$$
\varepsilon^i(e_j)\varphi^a(f_b)
=\delta^i{}_j\delta^a{}_b.
$$

Thus $\varepsilon^i\otimes\varphi^a$ is the dual basis to $e_j\otimes f_b$.

</details>

### Exercise 4: Tensor product representation

Let $G$ act on $V$ and $W$ by $\rho$ and $\sigma$. Show that

$$
(\rho\otimes\sigma)(g)=\rho(g)\otimes\sigma(g)
$$

defines a representation of $G$ on $V\otimes W$.

<details><summary><strong>Solution</strong></summary>

First,

$$
(\rho\otimes\sigma)(e)=\rho(e)\otimes\sigma(e)=1_V\otimes1_W=1_{V\otimes W}.
$$

Second, for $g,h\in G$,

$$
(\rho\otimes\sigma)(g)(\rho\otimes\sigma)(h)
=(\rho(g)\otimes\sigma(g))(\rho(h)\otimes\sigma(h)).
$$

On simple tensors this acts as

$$
v\otimes w
\mapsto
\rho(g)\rho(h)v\otimes\sigma(g)\sigma(h)w
=\rho(gh)v\otimes\sigma(gh)w.
$$

Therefore

$$
(\rho\otimes\sigma)(g)(\rho\otimes\sigma)(h)
=(\rho\otimes\sigma)(gh).
$$

Since simple tensors span $V\otimes W$, the equality holds on the whole tensor product.

</details>

### Exercise 5: A contraction is a trace

Use the identification $V\otimes V^*\cong\operatorname{End}(V)$ to show that the contraction $T^i{}_i$ is the trace of the corresponding linear map.

<details><summary><strong>Solution</strong></summary>

Write

$$
T=T^i{}_j e_i\otimes\varepsilon^j.
$$

The corresponding endomorphism sends

$$
e_k\mapsto T^i{}_j\varepsilon^j(e_k)e_i=T^i{}_k e_i.
$$

Thus its matrix components are $T^i{}_k$. The trace of this matrix is

$$
\operatorname{tr}T=T^i{}_i,
$$

which is exactly the contraction of the $V$ and $V^*$ factors.

</details>

## Connections

The previous page is [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/). Later pages in this chapter develop bilinear forms, metrics, index notation, symmetrization, exterior algebra, determinants, traces, Jacobians, and normal forms.

For tensor products in representation theory, see [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/), [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/), [Characters](/math-toolkit/groups-representations/characters/), and [Young Tableaux](/math-toolkit/groups-representations/young-tableaux/). For tensor products in differential geometry, see [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/). For Hilbert-space subtleties, see [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/) and [Rigged Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/rigged-hilbert-spaces/).

## References

For tensor products and multilinear algebra, see Axler, *Linear Algebra Done Right*; Hoffman and Kunze, *Linear Algebra*; Roman, *Advanced Linear Algebra*; and Greub, *Multilinear Algebra*. For representation-theoretic uses, see Fulton and Harris, *Representation Theory*. For geometry and physics applications, see Frankel, *The Geometry of Physics*; Nakahara, *Geometry, Topology and Physics*; and standard QFT texts by Weinberg, Srednicki, Schwartz, and Zee.

## Version history

- **2026-06-26:** Initial polished draft. Added the universal property, bases and components, simple and non-simple tensors, tensor products of maps, tensor type, contractions, direct sums versus tensor products, QFT applications, pitfalls, exercises, and cross-links.
