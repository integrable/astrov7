---
title: "Bilinear Forms and Metrics"
description: "Explains bilinear forms, metrics, nondegeneracy, signature, raising and lowering indices, orthogonality, invariant tensors, quadratic actions, and the QFT meaning of contractions."
sidebar:
  label: "Bilinear Forms and Metrics"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard references on multilinear algebra, differential geometry, representation theory, and QFT conventions, including Axler, Hoffman–Kunze, Roman, Frankel, Nakahara, Weinberg, Srednicki, Schwartz, and Zee."
topics:
  - bilinear form
  - metric
  - nondegenerate pairing
  - signature
  - raising and lowering indices
  - orthogonality
  - quadratic form
  - invariant tensor
  - Lorentz metric
  - QFT notation
canonicalTopics:
  - bilinear-form
  - metric
  - nondegenerate-pairing
  - signature
  - raising-lowering-indices
  - orthogonality
  - quadratic-form
  - invariant-tensor
  - lorentz-metric
  - qft-notation
researchStatus:
  established:
    - "Finite-dimensional bilinear forms, symmetric and antisymmetric forms, nondegeneracy, signature, inverse metrics, and raising and lowering indices are standard multilinear algebra."
    - "Lorentzian metrics, symplectic forms, invariant tensors, and Hermitian inner products are distinct structures that identify spaces with duals in different ways."
  active:
    - "In QFT the same finite-dimensional language appears inside indefinite inner-product spaces, constrained systems, gauge theories, spinor modules, anomalies, and infinite-dimensional functional spaces where domains and topology matter."
---

## Summary

A bilinear form on a vector space $V$ over a field $\mathbb F$ is a map

$$
b:V\times V\to\mathbb F
$$

that is linear in each argument separately. After choosing a basis $e_i$, it has components

$$
b_{ij}=b(e_i,e_j),
$$

and for $v=v^i e_i$, $w=w^j e_j$,

$$
b(v,w)=b_{ij}v^i w^j.
$$

A metric is a special kind of bilinear form. In finite-dimensional linear algebra, one often reserves the word metric for a symmetric nondegenerate bilinear form. It may be positive definite, as in Euclidean geometry, or indefinite, as in Lorentzian spacetime. In this site’s default convention,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing a bilinear form, the induced flat map from a vector space to its dual, the inverse sharp map, signatures, and QFT uses such as kinetic terms and invariant contractions.](/figures/math-toolkit/bilinear-metric-identification.svg)

<figcaption>

A nondegenerate bilinear form $b$ identifies $V$ with $V^*$ by $v\mapsto b(v,-)$. This is the algebraic meaning of lowering an index. The inverse map raises indices. Different pairings — Euclidean metrics, Lorentz metrics, symplectic forms, Hermitian products, invariant tensors — are different pieces of structure and must not be silently exchanged.

</figcaption>
</figure>

The central warning is simple: an upper index and a lower index are not two fonts for the same thing. They live in dual vector spaces. Moving an index requires an explicit nondegenerate pairing. In QFT, the choice of pairing is physical bookkeeping: it controls signs in propagators, kinetic terms, canonical brackets, spinor bilinears, invariant couplings, gauge traces, and quadratic fluctuations.

## Prerequisites

You should know [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/) and [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/). You should also know the site’s [Mathematical Conventions](/math-toolkit/conventions/), especially the mostly-minus Lorentz metric.

This page stays mostly finite-dimensional. Metrics on manifolds, spin structures, Dirac operators, symplectic phase spaces, and functional determinants appear elsewhere. Here the goal is to make the linear-algebra type system completely explicit.

## Bilinear forms as tensors

A bilinear form is an element of

$$
V^*\otimes V^*.
$$

Equivalently, it is a linear map

$$
\widetilde b:V\otimes V\to\mathbb F
$$

with

$$
\widetilde b(v\otimes w)=b(v,w).
$$

Choosing a basis $e_i$ and dual basis $\varepsilon^i$, we write

$$
b=b_{ij}\varepsilon^i\otimes\varepsilon^j.
$$

The components $b_{ij}$ are not the bilinear form itself. They are its coordinates in a chosen basis. If the basis changes by

$$
e'_i=e_j A^j{}_i,
$$

then

$$
b'_{ij}=A^k{}_i A^\ell{}_j b_{k\ell}.
$$

This is the same rule one learns for metric components in differential geometry. It is not arbitrary. It is forced by the requirement that the scalar $b(v,w)$ be basis-independent.

## Symmetric, antisymmetric, and Hermitian pairings

A bilinear form is symmetric if

$$
b(v,w)=b(w,v),
$$

and antisymmetric if

$$
b(v,w)=-b(w,v).
$$

In components,

$$
b_{ij}=b_{ji}
$$

for a symmetric form, and

$$
b_{ij}=-b_{ji}
$$

for an antisymmetric form.

The most common QFT pairings are:

| Structure | Algebraic type | Main use |
|---|---|---|
| Euclidean metric | symmetric, positive definite | rotations, Gaussian integrals, Euclidean kinetic terms |
| Lorentz metric | symmetric, nondegenerate, indefinite | spacetime contractions $p^2=\eta_{\mu\nu}p^\mu p^\nu$ |
| Symplectic form | antisymmetric, nondegenerate | phase space, Poisson brackets, canonical commutators |
| Hermitian inner product | sesquilinear, positive definite | Hilbert spaces, unitarity, probabilities |
| Invariant group tensor | representation-dependent | gauge traces, Clebsch–Gordan maps, invariant couplings |

The Hermitian case deserves its own warning. A Hermitian inner product on a complex vector space is not bilinear; it is linear in one argument and antilinear in the other. In physics convention,

$$
\langle \psi|a\phi+b\chi\rangle
=a\langle\psi|\phi\rangle+b\langle\psi|\chi\rangle,
$$

while

$$
\langle a\psi+b\chi|\phi\rangle
=\overline a\langle\psi|\phi\rangle+
\overline b\langle\chi|\phi\rangle.
$$

So a Hilbert-space bra is related to a ket by an antilinear operation, not by the same kind of bilinear metric used to lower a Lorentz index. It is a cousin, not a clone.

## Nondegeneracy and the flat map

A bilinear form $b$ defines a linear map

$$
\flat_b:V\to V^*,
\qquad
\flat_b(v)(w)=b(v,w).
$$

In components,

$$
(\flat_b(v))_i=b_{ij}v^j.
$$

The form is nondegenerate if

$$
b(v,w)=0\quad\text{for all }w\in V
$$

implies

$$
v=0.
$$

Equivalently, $\flat_b$ is an isomorphism. In a finite-dimensional basis, this means

$$
\det(b_{ij})\neq0.
$$

If $b$ is nondegenerate, its inverse is a map

$$
\sharp_b:V^*\to V.
$$

In components the inverse matrix $b^{ij}$ satisfies

$$
b^{ik}b_{kj}=\delta^i{}_j.
$$

Then

$$
v_i=b_{ij}v^j,
\qquad
\alpha^i=b^{ij}\alpha_j.
$$

These are lowering and raising operations. They are not syntactic tricks. They are applications of $\flat_b$ and $\sharp_b$.

:::caution[Index motion uses structure]
Never move an index unless you know which nondegenerate pairing is being used. A spacetime Lorentz index, an $SU(N)$ fundamental index, an adjoint index, a spinor index, and a phase-space index can all be raised or lowered only by their own appropriate tensors.
:::

## Quadratic forms

A bilinear form gives a quadratic form

$$
Q(v)=b(v,v).
$$

If $b$ is antisymmetric, then

$$
Q(v)=b(v,v)=0
$$

for every $v$. Thus symplectic forms do not measure lengths. They measure oriented phase-space area.

If $b$ is symmetric, the quadratic form contains the same information as $b$ when the characteristic is not two. The polarization identity gives

$$
b(v,w)=\frac{1}{2}\bigl(Q(v+w)-Q(v)-Q(w)\bigr)
$$

for symmetric bilinear forms over $\mathbb R$ or $\mathbb C$.

In QFT, quadratic forms appear as the free part of an action. Schematically,

$$
S_2[\phi]=\frac12\int d^dx\,\phi(x)K\phi(x).
$$

The operator $K$ is the infinite-dimensional analogue of a matrix representing a bilinear form. Its inverse, when defined with a boundary condition or $i\epsilon$ prescription, is the propagator. This is the same algebra as finite-dimensional Gaussian integration, with analytic and distributional complications added.

## Signature and Lorentzian signs

A real symmetric nondegenerate bilinear form can be diagonalized over $\mathbb R$ to

$$
\operatorname{diag}(\underbrace{+1,\dots,+1}_{p},
\underbrace{-1,\dots,-1}_{q}).
$$

The pair $(p,q)$ is its signature. Sylvester’s law of inertia says that $(p,q)$ is invariant under real changes of basis.

For Euclidean space, the signature is $(n,0)$. For the site’s default Minkowski convention in four spacetime dimensions, the signature is $(1,3)$:

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

Thus

$$
p^2=\eta_{\mu\nu}p^\mu p^\nu=(p^0)^2-\mathbf p^2.
$$

A massive on-shell momentum satisfies

$$
p^2=m^2.
$$

This convention affects the Klein–Gordon operator, propagator denominators, gamma-matrix anticommutators, and Wick rotation. It is harmless only when everyone remembers it.

## Orthogonality without positivity

Given a bilinear form $b$, two vectors are orthogonal if

$$
b(v,w)=0.
$$

For a positive-definite inner product, $b(v,v)=0$ implies $v=0$. For an indefinite metric, this is false. A nonzero vector can be null:

$$
b(v,v)=0,
\qquad
v\neq0.
$$

In Minkowski space, lightlike momenta satisfy

$$
p^2=0.
$$

That does not mean the momentum vanishes. It means the vector lies on the null cone. Many false arguments in relativistic QFT come from importing Euclidean geometric intuition into Lorentzian signature without checking positivity.

The orthogonal complement of a subspace $W\subset V$ is

$$
W^\perp=\{v\in V\mid b(v,w)=0\text{ for all }w\in W\}.
$$

In positive-definite geometry, $V=W\oplus W^\perp$. In indefinite geometry, this can fail when $W$ contains null vectors. Gauge theory and constrained Hamiltonian systems love this failure. They will invite it over for tea.

## Metrics on manifolds

On a manifold $M$, a metric is a smoothly varying nondegenerate bilinear form on each tangent space:

$$
g_p:T_pM\times T_pM\to\mathbb R.
$$

In local coordinates,

$$
g=g_{\mu\nu}(x)dx^\mu\otimes dx^\nu.
$$

The inverse metric has components $g^{\mu\nu}$ satisfying

$$
g^{\mu\rho}g_{\rho\nu}=\delta^\mu{}_{\nu}.
$$

The metric identifies tangent and cotangent spaces pointwise:

$$
X_\mu=g_{\mu\nu}X^\nu,
\qquad
\omega^\mu=g^{\mu\nu}\omega_\nu.
$$

In flat spacetime, $g_{\mu\nu}=\eta_{\mu\nu}$ in inertial Cartesian coordinates. In curved spacetime, the same formulas hold locally, but $g_{\mu\nu}(x)$ varies and the derivative compatible with $g$ is the Levi-Civita connection.

## Invariant bilinear forms

If a group $G$ acts on $V$ by a representation $\rho$, a bilinear form $b$ is $G$-invariant if

$$
b(\rho(g)v,\rho(g)w)=b(v,w)
$$

for all $g\in G$. Infinitesimally, if $T_a$ are the representation matrices, this becomes

$$
b(T_a v,w)+b(v,T_a w)=0.
$$

In a basis,

$$
(T_a)^k{}_i b_{kj}+(T_a)^k{}_j b_{ik}=0.
$$

This equation is the algebraic heart of many QFT contractions. A Lagrangian term is invariant only if its indices are contracted using invariant tensors. Examples include:

$$
\delta_{ij}\phi^i\phi^j
$$

for an orthogonal representation,

$$
\epsilon_{ij}\psi^i\chi^j
$$

for a two-dimensional symplectic-like invariant, and

$$
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab}
$$

for a compact simple gauge algebra in a representation $R$.

The last formula is a convention-sensitive invariant bilinear form on the Lie algebra. Its normalization affects beta functions, anomaly coefficients, Casimirs, and Feynman-rule color factors.

## Mass matrices and kinetic terms

A quadratic Lagrangian often contains several bilinear forms at once. For real scalar fields $\phi^i$,

$$
\mathcal L
=\frac12 G_{ij}\partial_\mu\phi^i\partial^\mu\phi^j
-\frac12 M_{ij}\phi^i\phi^j.
$$

Here $G_{ij}$ is a metric on field space, while $M_{ij}$ is a symmetric mass-squared bilinear form. If $G_{ij}=\delta_{ij}$, diagonalizing $M_{ij}$ is ordinary orthogonal diagonalization. If $G_{ij}$ is not the identity, the physical mass eigenvalue problem is generalized:

$$
M v=m^2 G v.
$$

For fermions, the bilinear structure is subtler because spinor duals, charge conjugation, chirality, and Grassmann parity enter. A symbol like $\bar\psi\psi$ hides a Lorentz-invariant spinor pairing. A Majorana mass term hides a charge-conjugation structure. The moral is the same: every quadratic term is a pairing.

## Raising, lowering, and contractions in QFT

The canonical contraction is between a vector space and its dual:

$$
V^*\otimes V\to\mathbb F.
$$

A metric creates additional contractions by converting one vector into a covector. For spacetime vectors,

$$
A\cdot B=\eta_{\mu\nu}A^\mu B^\nu=A_\mu B^\mu.
$$

For differential forms, the Hodge star uses a metric and orientation. For spinors, raising and lowering may use an antisymmetric tensor such as $\epsilon_{\alpha\beta}$ rather than the spacetime metric. For adjoint gauge indices, one often uses $\delta^{ab}$ or the Killing form, depending on convention and normalization.

A compact formula is often a stack of pairings:

$$
\frac14 F^a_{\mu\nu}F^{a\mu\nu}
$$

uses a spacetime metric to raise $\mu,\nu$ and an invariant gauge-algebra metric to contract $a$. These are different metrics. Writing them with the same visual index style is convenient, but slightly treacherous. The notation is a power tool; keep fingers clear.

## Common pitfalls

**Calling every bilinear form a dot product.** A dot product usually suggests positive definiteness. Lorentzian and symplectic pairings are not dot products in that sense.

**Using the Lorentz metric as a Hilbert-space inner product.** The Lorentz metric contracts spacetime indices. The Hilbert-space inner product defines probabilities. Mixing them breaks unitarity before breakfast.

**Forgetting that nondegenerate does not mean positive.** Lorentzian metrics are nondegenerate but indefinite. Null nonzero vectors exist.

**Raising a spinor index with the spacetime metric.** Spinor indices are raised and lowered by spinor invariant tensors, not by $\eta_{\mu\nu}$.

**Contracting two upper indices without a metric.** The canonical contraction is upper-lower for matching dual spaces. Upper-upper contraction needs a bilinear form or invariant tensor.

**Assuming diagonalization is always orthogonal.** Orthogonal diagonalization belongs to positive-definite settings. Generalized eigenvalue problems and indefinite metrics require more care.

**Dropping normalization data for gauge traces.** $\operatorname{tr}_R(T^aT^b)$ carries representation and normalization information. It is not automatically $\delta^{ab}$.

## Exercises

### Exercise 1: Basis transformation of a bilinear form

Let $e'_i=e_jA^j{}_i$. Show that the components of a bilinear form transform as

$$
b'_{ij}=A^k{}_iA^\ell{}_j b_{k\ell}.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
b'_{ij}=b(e'_i,e'_j).
$$

Using $e'_i=e_kA^k{}_i$ and bilinearity,

$$
b(e'_i,e'_j)
=b(e_kA^k{}_i,e_\ell A^\ell{}_j)
=A^k{}_iA^\ell{}_j b(e_k,e_\ell).
$$

Therefore

$$
b'_{ij}=A^k{}_iA^\ell{}_j b_{k\ell}.
$$

</details>

### Exercise 2: Nondegeneracy and the flat map

Show that a finite-dimensional bilinear form $b$ is nondegenerate if and only if the map $\flat_b:V\to V^*$ defined by $\flat_b(v)(w)=b(v,w)$ is an isomorphism.

<details><summary><strong>Solution</strong></summary>

The kernel of $\flat_b$ consists of vectors $v$ such that

$$
\flat_b(v)(w)=0
$$

for every $w\in V$. This is exactly the set of $v$ satisfying $b(v,w)=0$ for all $w$.

Thus $b$ is nondegenerate precisely when $\ker\flat_b=0$. In finite dimensions, $\dim V=\dim V^*$, so an injective linear map $V\to V^*$ is automatically an isomorphism. Conversely, if $\flat_b$ is an isomorphism, its kernel is zero, so $b$ is nondegenerate.

</details>

### Exercise 3: Null vectors in mostly-minus signature

With

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

show that $p^\mu=(E,E,0,0)$ is nonzero and null.

<details><summary><strong>Solution</strong></summary>

The vector is nonzero if $E\neq0$. Its squared norm is

$$
p^2=\eta_{\mu\nu}p^\mu p^\nu
=E^2-E^2-0-0=0.
$$

Thus $p$ is a nonzero null vector. This cannot happen for a positive-definite inner product, but it is central in Lorentzian geometry and massless relativistic kinematics.

</details>

### Exercise 4: Invariance condition

Let $\rho(e^{tX})=1+tT+O(t^2)$ preserve a bilinear form $b$. Derive the infinitesimal condition

$$
b(Tv,w)+b(v,Tw)=0.
$$

<details><summary><strong>Solution</strong></summary>

Invariance says

$$
b(\rho(e^{tX})v,\rho(e^{tX})w)=b(v,w).
$$

Expanding to first order in $t$ gives

$$
b(v+tTv,w+tTw)+O(t^2)=b(v,w).
$$

By bilinearity,

$$
b(v,w)+t\,b(Tv,w)+t\,b(v,Tw)+O(t^2)=b(v,w).
$$

The coefficient of $t$ must vanish, so

$$
b(Tv,w)+b(v,Tw)=0.
$$

</details>

### Exercise 5: Generalized mass eigenvalue problem

For real scalar fields with quadratic Lagrangian

$$
\mathcal L
=\frac12 G_{ij}\partial_\mu\phi^i\partial^\mu\phi^j
-\frac12 M_{ij}\phi^i\phi^j,
$$

where $G$ is positive definite, explain why the normal-mode equation is $M v=m^2Gv$ rather than simply $Mv=m^2v$.

<details><summary><strong>Solution</strong></summary>

A normal mode $\phi^i(x)=v^i\varphi(x)$ should reduce the equations of motion to

$$
(\partial^2+m^2)\varphi=0.
$$

The Euler–Lagrange equations are

$$
G_{ij}\partial_\mu\partial^\mu\phi^j+M_{ij}\phi^j=0.
$$

A normal-mode spacetime wave satisfies

$$
(\partial_\mu\partial^\mu+m^2)\varphi=0,
$$

so substituting $\phi^j=v^j\varphi$ gives

$$
-m^2G_{ij}v^j+M_{ij}v^j=0.
$$

Therefore

$$
M_{ij}v^j=m^2G_{ij}v^j.
$$

More invariantly, $M$ is a bilinear form and $G$ is the metric used to identify field space with its dual. Physical eigenvalues are eigenvalues of the endomorphism $G^{-1}M$.

When $G=1$, this reduces to the ordinary eigenvalue equation.

</details>

## Connections

The previous pages are [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/) and [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/). The next page in this batch is [Index Notation](/math-toolkit/linear-algebra-tensors/index-notation/), which turns the type system of vectors, covectors, tensor products, and metrics into reliable component notation.

For Lorentzian geometry, see [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/). For symplectic pairings, see [Symplectic Forms](/math-toolkit/calculus-of-variations-and-phase-space/symplectic-forms/). For spinor pairings, see [Spinor Bilinears](/math-toolkit/clifford-spinors/spinor-bilinears/). For gauge trace normalizations, see [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/).

## References

For bilinear forms and finite-dimensional multilinear algebra, see Axler, *Linear Algebra Done Right*; Hoffman and Kunze, *Linear Algebra*; and Roman, *Advanced Linear Algebra*. For metrics, forms, and physics applications, see Frankel, *The Geometry of Physics* and Nakahara, *Geometry, Topology and Physics*. For Lorentzian, spinor, and gauge-theory convention practice, compare standard QFT texts by Weinberg, Srednicki, Schwartz, and Zee.

## Version history

- **2026-06-26:** Initial polished draft. Added bilinear forms as tensors, symmetric and antisymmetric forms, nondegeneracy, flat and sharp maps, signature, orthogonality, metrics on manifolds, invariant tensors, QFT quadratic forms, pitfalls, exercises, and cross-links.
