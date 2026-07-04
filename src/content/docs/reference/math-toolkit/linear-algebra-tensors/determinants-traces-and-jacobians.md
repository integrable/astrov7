---
title: "Determinants, Traces, and Jacobians"
description: "Explains determinants, traces, logarithmic determinant identities, Jacobians, Schur complements, finite-dimensional change of variables, and their role in Gaussian integrals, functional determinants, and QFT measures."
sidebar:
  label: "Determinants, Traces, and Jacobians"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard references on multilinear algebra, matrix analysis, differential geometry, Gaussian integration, path integrals, and QFT applications, including Frankel, Nakahara, Srednicki, Schwartz, Zee, Weinberg, Zinn-Justin, and common mathematical physics conventions."
topics:
  - determinant
  - trace
  - Jacobian
  - logarithmic determinant
  - matrix determinant lemma
  - Schur complement
  - change of variables
  - Gaussian integral
  - functional determinant
  - QFT measure
canonicalTopics:
  - determinant
  - trace
  - jacobian
  - logarithmic-determinant
  - matrix-determinant-lemma
  - schur-complement
  - change-of-variables
  - gaussian-integral
  - functional-determinant
  - qft-measure
researchStatus:
  established:
    - "The determinant is the scalar by which a linear endomorphism acts on the top exterior power."
    - "The trace is the contraction of one upper and one lower index and gives the infinitesimal variation of the determinant."
    - "Jacobians are determinants of derivative maps and control finite-dimensional changes of variables."
    - "Finite-dimensional determinant identities are standard inputs to Gaussian integration, effective actions, Faddeev–Popov factors, and functional determinants."
  active:
    - "In infinite-dimensional field spaces, determinants, traces, and Jacobians require regularization; their regulator dependence encodes anomalies, counterterms, eta invariants, and measure choices."
---

## Summary

The determinant, trace, and Jacobian are three faces of the same idea: how a linear map changes volume.

For a linear map $A:V\to V$ on an $n$-dimensional vector space, the determinant is the scalar by which $A$ acts on the top exterior power:

$$
\Lambda^n A=(\det A)\,\operatorname{id}_{\Lambda^n V}.
$$

The trace is the infinitesimal version of this statement. If $A=I+\epsilon X$, then

$$
\det(I+\epsilon X)=1+\epsilon\operatorname{tr}X+O(\epsilon^2).
$$

More generally,

$$
\delta\log\det A=\operatorname{tr}(A^{-1}\delta A),
$$

whenever $A$ is invertible. A Jacobian is the same determinant applied to the derivative of a change of variables:

$$
x=f(y),
\qquad
 d^nx=\left|\det\frac{\partial x}{\partial y}\right|d^ny.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a linear map acting on top exterior power to define the determinant, the trace as infinitesimal determinant, the logarithmic determinant variation, and the Jacobian as determinant of a derivative map, with QFT applications to Gaussian integrals, functional determinants, and path-integral measures.](/figures/math-toolkit/determinants-traces-jacobians-flow.svg)

<figcaption>

Determinants measure finite volume scaling, traces measure infinitesimal volume scaling, and Jacobians apply determinants to coordinate changes. In QFT the same identities become Gaussian normalization factors, one-loop effective actions, Faddeev–Popov determinants, and measure Jacobians.

</figcaption>
</figure>

For QFT, this page is not optional bookkeeping. The Gaussian integral gives powers of determinants. The one-loop effective action contains traces of logarithms. A change of field variables can produce a Jacobian. Gauge fixing inserts a determinant. An anomaly is often the regulated failure of a seemingly harmless infinite-dimensional Jacobian to equal $1$.

## Prerequisites

You should know [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), [Index Notation](/math-toolkit/linear-algebra-tensors/index-notation/), and [Exterior Algebra](/math-toolkit/linear-algebra-tensors/exterior-algebra/). For the Gaussian and functional-integral applications, see [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/), [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), and [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/).

This page is finite-dimensional unless explicitly stated otherwise. In infinite-dimensional settings, traces and determinants are not automatically defined. The notation $\operatorname{Tr}\log D$ is a slogan until a regulator, domain, boundary condition, and zero-mode prescription have been specified.

## Determinant as volume scaling

Let $V$ be an $n$-dimensional vector space over $\mathbb R$ or $\mathbb C$. Choose a basis $e_1,\dots,e_n$. The top exterior power $\Lambda^nV$ is one-dimensional, with basis

$$
e_1\wedge\cdots\wedge e_n.
$$

A linear map $A:V\to V$ induces a map on $\Lambda^nV$ by

$$
(\Lambda^n A)(v_1\wedge\cdots\wedge v_n)
=Av_1\wedge\cdots\wedge Av_n.
$$

Since $\Lambda^nV$ is one-dimensional, this induced map must be multiplication by a scalar. That scalar is $\det A$:

$$
Ae_1\wedge\cdots\wedge Ae_n
=(\det A)e_1\wedge\cdots\wedge e_n.
$$

This definition is the least mysterious one. The determinant is not primarily a formula with permutations; it is the oriented volume scaling factor of a linear map.

If $A$ has components $A^i{}_j$ defined by

$$
Ae_j=e_iA^i{}_j,
$$

then expanding the wedge product gives

$$
\det A
=\sum_{\sigma\in S_n}\operatorname{sgn}(\sigma)
A^1{}_{\sigma(1)}A^2{}_{\sigma(2)}\cdots A^n{}_{\sigma(n)}.
$$

Equivalently, using the Levi-Civita symbol,

$$
\det A
=\frac{1}{n!}\epsilon_{i_1\cdots i_n}\epsilon^{j_1\cdots j_n}
A^{i_1}{}_{j_1}\cdots A^{i_n}{}_{j_n}.
$$

This formula is useful, but it can obscure the invariant meaning: $\det A$ is the induced action on oriented top-degree volume.

## First properties

The determinant is multiplicative because induced maps on exterior powers compose:

$$
\Lambda^n(AB)=(\Lambda^n A)(\Lambda^n B).
$$

Therefore

$$
\det(AB)=\det A\,\det B.
$$

The identity has determinant $1$, so if $A$ is invertible,

$$
\det A^{-1}=(\det A)^{-1}.
$$

For a block diagonal matrix,

$$
A=\begin{pmatrix}
B&0\\
0&C
\end{pmatrix},
$$

one has

$$
\det A=(\det B)(\det C).
$$

For triangular matrices, the determinant is the product of diagonal entries:

$$
A^i{}_j=0\quad \text{for }i>j
\qquad\Longrightarrow\qquad
\det A=\prod_i A^i{}_i.
$$

This last formula is often the quickest way to evaluate determinants after Gaussian elimination.

## Trace as contraction

The trace of an endomorphism $A:V\to V$ is the contraction of its input and output index:

$$
\operatorname{tr}A=A^i{}_i.
$$

This definition is basis-independent. Under a change of basis, $A$ transforms by similarity,

$$
A\mapsto S^{-1}AS,
$$

and cyclicity gives

$$
\operatorname{tr}(S^{-1}AS)=\operatorname{tr}(ASS^{-1})=\operatorname{tr}A.
$$

The trace is linear:

$$
\operatorname{tr}(aA+bB)=a\operatorname{tr}A+b\operatorname{tr}B.
$$

For finite matrices it is cyclic:

$$
\operatorname{tr}(AB)=\operatorname{tr}(BA),
$$

and more generally

$$
\operatorname{tr}(A_1A_2\cdots A_k)
=\operatorname{tr}(A_kA_1\cdots A_{k-1}).
$$

Cyclicity is the humble reason why traces produce conjugation-invariant quantities such as $\operatorname{tr}F_{\mu\nu}F^{\mu\nu}$ in gauge theory.

:::caution[Finite versus infinite trace]
Cyclicity of the trace is automatic for finite matrices, but not for arbitrary infinite-dimensional operators. In field theory one must check trace-class conditions or regulate the trace. Anomalies often arise precisely because a formal cyclic rearrangement fails after regularization.
:::

## Trace as infinitesimal determinant

The determinant is nonlinear. The trace is its first derivative at the identity.

Let

$$
A(\epsilon)=I+\epsilon X.
$$

To first order in $\epsilon$,

$$
A(\epsilon)e_1\wedge\cdots\wedge A(\epsilon)e_n
=\prod_{k=1}^n(e_k+\epsilon Xe_k)+O(\epsilon^2).
$$

The first-order terms are

$$
\epsilon\sum_{r=1}^n e_1\wedge\cdots\wedge Xe_r\wedge\cdots\wedge e_n.
$$

Only the component of $Xe_r$ along $e_r$ survives, because any component along $e_s$ with $s\ne r$ repeats a basis vector in the wedge. Thus

$$
\det(I+\epsilon X)=1+\epsilon\sum_r X^r{}_r+O(\epsilon^2)
=1+\epsilon\operatorname{tr}X+O(\epsilon^2).
$$

This is the infinitesimal form of volume scaling. It is also why the Lie algebra of $SL(n)$ consists of traceless matrices:

$$
A\in SL(n)\quad\Longrightarrow\quad \det A=1,
$$

so infinitesimally $A=I+\epsilon X$ gives

$$
\operatorname{tr}X=0.
$$

Likewise, physicists often take generators of $SU(N)$ to be traceless Hermitian matrices $T^a$, or traceless anti-Hermitian matrices depending on convention.

## Logarithmic determinant identities

The most important determinant identity in QFT is

$$
\delta\log\det A=\operatorname{tr}(A^{-1}\delta A).
$$

Here $A$ must be invertible. One derivation uses multiplicativity. Write

$$
A+\delta A=A(I+A^{-1}\delta A).
$$

Then

$$
\det(A+\delta A)
=\det A\,\det(I+A^{-1}\delta A).
$$

Using $\det(I+\epsilon X)=1+\epsilon\operatorname{tr}X+O(\epsilon^2)$ gives

$$
\det(A+\delta A)
=\det A\left(1+\operatorname{tr}(A^{-1}\delta A)+O(\delta A^2)\right),
$$

so

$$
\delta\det A=(\det A)\operatorname{tr}(A^{-1}\delta A),
$$

and therefore

$$
\delta\log\det A=\frac{\delta\det A}{\det A}
=\operatorname{tr}(A^{-1}\delta A).
$$

A closely related formula is

$$
\det e^X=e^{\operatorname{tr}X}.
$$

One way to see it is to define $f(t)=\log\det e^{tX}$. Then

$$
\frac{df}{dt}=\operatorname{tr}\left(e^{-tX}Xe^{tX}\right)=\operatorname{tr}X,
$$

so $f(1)-f(0)=\operatorname{tr}X$.

For invertible matrices one also formally writes

$$
\log\det A=\operatorname{tr}\log A.
$$

In finite dimensions, this is safe once a branch of $\log$ is chosen and eigenvalues are kept away from the branch cut. In infinite-dimensional QFT, it is a definition only after regularization. That tiny phrase “after regularization” is where one-loop physics lives.

## Characteristic polynomial and elementary invariants

The determinant and trace are the first two universal spectral invariants. The characteristic polynomial is

$$
p_A(\lambda)=\det(\lambda I-A).
$$

For an $n\times n$ matrix it has the form

$$
p_A(\lambda)=\lambda^n-(\operatorname{tr}A)\lambda^{n-1}+\cdots+(-1)^n\det A.
$$

Thus

$$
\operatorname{tr}A=\sum_i\lambda_i,
\qquad
\det A=\prod_i\lambda_i,
$$

counting eigenvalues with algebraic multiplicity over $\mathbb C$.

The intermediate coefficients are elementary symmetric polynomials in the eigenvalues. They can be expressed in terms of traces $\operatorname{tr}(A^k)$ by Newton identities. For example,

$$
\det(I+tA)=1+t\operatorname{tr}A+\frac{t^2}{2}\left((\operatorname{tr}A)^2-\operatorname{tr}A^2\right)+O(t^3).
$$

This expansion is common in perturbative determinants. If $K$ is small, then

$$
\log\det(I+K)=\operatorname{tr}\log(I+K)
=\sum_{m=1}^{\infty}\frac{(-1)^{m+1}}{m}\operatorname{tr}K^m,
$$

whenever the series makes sense. In perturbative QFT, this is the algebraic skeleton of loop expansions: the $m$th trace is a closed chain of $m$ insertions.

## Schur complements and block determinants

Block matrices appear whenever fields are split into light and heavy modes, bosons and fermions, constraints and gauge directions, or sources and dynamical variables.

Suppose

$$
M=\begin{pmatrix}
A&B\\
C&D
\end{pmatrix},
$$

where $A$ is invertible. Then

$$
\det M=\det A\,\det(D-CA^{-1}B).
$$

The matrix

$$
D-CA^{-1}B
$$

is the Schur complement of $A$ in $M$. A quick derivation uses block Gaussian elimination:

$$
\begin{pmatrix}
I&0\\
-CA^{-1}&I
\end{pmatrix}
\begin{pmatrix}
A&B\\
C&D
\end{pmatrix}
=
\begin{pmatrix}
A&B\\
0&D-CA^{-1}B
\end{pmatrix}.
$$

The left multiplier has determinant $1$, and the right side is block triangular.

Similarly, if $D$ is invertible,

$$
\det M=\det D\,\det(A-BD^{-1}C).
$$

These formulas are more than algebra tricks. Integrating out a subset of Gaussian variables produces precisely Schur complements. In field theory, the same operation becomes “integrating out heavy fields,” “completing the square,” or “computing a constrained determinant.”

## Matrix determinant lemma

A rank-one update has a simple determinant:

$$
\det(A+uv^T)=\det A\,(1+v^TA^{-1}u),
$$

provided $A$ is invertible. More generally, for compatible rectangular matrices $U$ and $V$,

$$
\det(A+UV)=\det A\,\det(I+VA^{-1}U).
$$

The useful point is that $I+VA^{-1}U$ may be much smaller than $A+UV$. This identity is a finite-dimensional ancestor of many formulas in scattering theory and determinant-ratio computations, where a localized perturbation changes a large operator by a finite-rank or trace-class amount.

A related identity is Sylvester’s determinant theorem:

$$
\det(I_m+AB)=\det(I_n+BA),
$$

for $A:m\leftarrow n$ and $B:n\leftarrow m$. This is often the clean way to move determinants from a big space to a smaller auxiliary space.

## Jacobians in finite dimensions

Let $x=f(y)$ be a smooth change of variables between open regions of $\mathbb R^n$. Its derivative at a point is the matrix

$$
J^i{}_a(y)=\frac{\partial x^i}{\partial y^a}.
$$

Infinitesimally,

$$
dx^1\wedge\cdots\wedge dx^n
=\det J\,dy^1\wedge\cdots\wedge dy^n.
$$

Thus oriented integrals transform as

$$
\int_{f(U)}\omega=\int_U f^*\omega.
$$

For positive measures on $\mathbb R^n$, one usually writes the absolute value:

$$
\int_{f(U)}g(x)\,d^nx
=\int_U g(f(y))\left|\det\frac{\partial x}{\partial y}\right|d^ny.
$$

The absolute value is not a random extra. It appears because $d^nx$ as a positive measure forgets orientation, while $dx^1\wedge\cdots\wedge dx^n$ is an oriented volume form.

In complex variables, if $z=f(w)$ is holomorphic in one complex dimension, then

$$
d^2z=|f'(w)|^2d^2w,
$$

because one complex variable is two real variables. In $n$ complex dimensions,

$$
d^{2n}z=\left|\det\frac{\partial z^i}{\partial w^a}\right|^2d^{2n}w,
$$

for a holomorphic change of coordinates.

## Jacobians and path-integral measures

In a formal path integral, a field redefinition

$$
\phi\mapsto \phi'=F[\phi]
$$

has a Jacobian

$$
\mathcal D\phi'=J[\phi]\,\mathcal D\phi,
\qquad
J[\phi]=\det\frac{\delta F}{\delta\phi}.
$$

This is a direct infinite-dimensional analog of the finite-dimensional formula. The dangerous word is “analog.” The expression

$$
\det\frac{\delta F}{\delta\phi}
$$

is usually divergent. One must define it by a regulator compatible with the symmetries one wants to preserve.

This is the source of several important phenomena:

- A linear field rescaling gives a determinant that may be an infinite constant; it is often absorbed into normalization.
- A local field redefinition can generate local Jacobian terms in the action.
- A chiral rotation of fermions can have a nontrivial regulated Jacobian, producing an anomaly.
- Gauge fixing produces a determinant measuring how the gauge condition changes along gauge orbits; this is the Faddeev–Popov determinant.

The finite-dimensional lesson remains valid: a Jacobian is a determinant of a derivative map. The field-theoretic lesson is harsher: infinite-dimensional determinants are not innocent.

## Bosonic and fermionic Gaussian determinants

For a positive-definite real symmetric $n\times n$ matrix $A$,

$$
\int_{\mathbb R^n}d^nx\,\exp\left(-\frac12 x^TAx\right)
=(2\pi)^{n/2}(\det A)^{-1/2}.
$$

The inverse square root appears because the change of variables $x=A^{-1/2}y$ has Jacobian $(\det A)^{-1/2}$.

For complex Grassmann variables,

$$
\int \prod_i d\bar\psi_i d\psi_i\,
\exp(-\bar\psi_i A^i{}_j\psi^j)=\det A,
$$

up to the sign convention fixed by the ordering of the Berezin measure. Fermionic Gaussian integrals produce determinants rather than inverse square roots because Berezin integration transforms oppositely to ordinary integration.

For a real antisymmetric matrix $B$, the fermionic integral gives a Pfaffian,

$$
\int d\theta_N\cdots d\theta_1\,
\exp\left(\frac12\theta_iB_{ij}\theta_j\right)=\operatorname{pf}(B),
$$

with

$$
\operatorname{pf}(B)^2=\det B.
$$

These finite-dimensional formulas are the templates for functional determinants in QFT.

## Determinants with metrics and densities

A determinant depends on which volume is being measured. In coordinates on a Riemannian or Lorentzian manifold, the metric determinant appears because the invariant volume density is

$$
\sqrt{|g|}\,d^dx,
\qquad
 g=\det(g_{\mu\nu}).
$$

The absolute value is used because Lorentzian metrics have negative determinant in mostly-minus convention for one time and $d-1$ space directions. The volume form on an oriented pseudo-Riemannian manifold is

$$
\operatorname{vol}_g=\sqrt{|g|}\,dx^0\wedge\cdots\wedge dx^{d-1}.
$$

Under a coordinate change $x=x(y)$,

$$
g'_{ab}(y)=\frac{\partial x^\mu}{\partial y^a}\frac{\partial x^\nu}{\partial y^b}g_{\mu\nu}(x(y)),
$$

so

$$
\det g'=\left(\det\frac{\partial x}{\partial y}\right)^2\det g.
$$

Therefore

$$
\sqrt{|g'|}\,d^dy=\sqrt{|g|}\,\left|\det\frac{\partial x}{\partial y}\right|d^dy,
$$

which is the invariant volume density. This is why actions such as

$$
S=\int d^dx\,\sqrt{|g|}\,\mathcal L
$$

are coordinate invariant when $\mathcal L$ is a scalar.

## Trace versus matrix trace in physics notation

Physics uses several traces at once. It is worth naming them explicitly.

A finite internal trace might be

$$
\operatorname{tr}_{\mathrm{fund}}(T^aT^b)=T_R\delta^{ab},
$$

where $T^a$ are gauge generators in a representation $R$. A spinor trace might be

$$
\operatorname{tr}_{\gamma}(\gamma^\mu\gamma^\nu)=4\eta^{\mu\nu}.
$$

A functional trace includes both discrete indices and integration over spacetime:

$$
\operatorname{Tr}K
=\int d^dx\,K^i{}_i(x,x),
$$

for an operator kernel $K^i{}_j(x,y)$, with whatever density and boundary conditions are appropriate.

A common convention is to use $\operatorname{tr}$ for finite matrix traces and $\operatorname{Tr}$ for functional traces. The distinction is not universal, but the idea is important. For example,

$$
\operatorname{Tr}\log D
$$

usually includes spacetime, spin, gauge, flavor, and possibly ghost indices. Missing one of these traces is a classic one-loop mistake.

## Variation formulas in field theory

The identity

$$
\delta\log\det A=\operatorname{tr}(A^{-1}\delta A)
$$

becomes, formally,

$$
\delta\operatorname{Tr}\log D
=\operatorname{Tr}(D^{-1}\delta D).
$$

This formula is everywhere in one-loop physics. If the quadratic fluctuation operator is $D$, then a bosonic one-loop contribution often has the schematic form

$$
\Gamma_{1,\mathrm{bos}}=\frac12\operatorname{Tr}\log D,
$$

while a fermionic one-loop contribution often has the schematic form

$$
\Gamma_{1,\mathrm{ferm}}=-\operatorname{Tr}\log D_{\mathrm{ferm}},
$$

with signs and factors depending on whether the variables are real, complex, constrained, or gauge-fixed.

Taking a variation avoids computing the determinant directly:

$$
\delta\Gamma_1
=\frac12\operatorname{Tr}(D^{-1}\delta D).
$$

The inverse operator $D^{-1}$ is a Green function. Thus many determinant calculations reduce to understanding Green functions and then integrating the variation back up, modulo local counterterms and zero-mode choices.

## Determinants and zero modes

If $A$ has a zero eigenvalue, then

$$
\det A=0,
$$

and $\log\det A$ is singular. In Gaussian integrals, this means the quadratic form has a flat direction. In QFT, zero modes may reflect:

- a symmetry of the saddle,
- a collective coordinate,
- a gauge redundancy not fully fixed,
- a physical massless mode,
- an instability or boundary-condition issue.

One often writes $\det' A$ to mean the determinant over nonzero modes only. The prime is not decoration. It means: remove zero modes, treat them separately, and include the correct measure on the zero-mode moduli if needed.

For a finite matrix with eigenvalues $\lambda_1,\dots,\lambda_n$, if $r$ eigenvalues vanish and the rest are nonzero, then

$$
\det{}'A=\prod_{\lambda_i\ne0}\lambda_i.
$$

In infinite dimensions, even this reduced product needs regularization.

## Common pitfalls

**Treating determinants as basis-dependent.** The determinant of an endomorphism is invariant. The determinant of a rectangular matrix is not defined. The determinant of a matrix representing a map $V\to W$ between different spaces requires volume choices on both spaces.

**Forgetting the absolute value in ordinary measures.** An oriented volume form transforms by $\det J$. A positive measure transforms by $|\det J|$.

**Using cyclic trace identities too freely.** In finite dimensions, $\operatorname{tr}(AB)=\operatorname{tr}(BA)$. For differential operators, regulators and domains matter.

**Writing $\operatorname{Tr}\log D$ without specifying zero modes.** Zero eigenvalues make $\log D$ singular. Gauge symmetries and collective coordinates must be handled before determinants are meaningful.

**Confusing bosonic and fermionic Jacobians.** Ordinary variables and Grassmann variables transform oppositely. Bosonic Gaussian integrals give inverse square roots of determinants; complex fermionic Gaussian integrals give determinants.

**Suppressing which trace is being taken.** Gauge, flavor, spinor, spacetime, Matsubara, replica, and Keldysh indices are different. A one-loop formula with an unspecified trace is an invitation to lose factors.

## Exercises

### Exercise 1: Variation of the determinant

Let $A$ be an invertible finite matrix. Prove

$$
\delta\det A=(\det A)\operatorname{tr}(A^{-1}\delta A).
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
A+\delta A=A(I+A^{-1}\delta A).
$$

Then

$$
\det(A+\delta A)=\det A\,\det(I+A^{-1}\delta A).
$$

Using

$$
\det(I+\epsilon X)=1+\epsilon\operatorname{tr}X+O(\epsilon^2)
$$

with $X=A^{-1}\delta A$ gives

$$
\det(A+\delta A)=\det A\left(1+\operatorname{tr}(A^{-1}\delta A)+O(\delta A^2)\right).
$$

Therefore

$$
\delta\det A=(\det A)\operatorname{tr}(A^{-1}\delta A).
$$

</details>

### Exercise 2: Determinant of a block matrix

Assume $A$ is invertible. Prove

$$
\det\begin{pmatrix}
A&B\\
C&D
\end{pmatrix}
=\det A\,\det(D-CA^{-1}B).
$$

<details><summary><strong>Solution</strong></summary>

Multiply on the left by a block lower-triangular matrix with determinant $1$:

$$
\begin{pmatrix}
I&0\\
-CA^{-1}&I
\end{pmatrix}
\begin{pmatrix}
A&B\\
C&D
\end{pmatrix}
=
\begin{pmatrix}
A&B\\
0&D-CA^{-1}B
\end{pmatrix}.
$$

The determinant of the left multiplier is $1$. The determinant of the resulting block triangular matrix is the product of the diagonal block determinants. Hence

$$
\det M=\det A\,\det(D-CA^{-1}B).
$$

</details>

### Exercise 3: Trace of a commutator

Show that for finite matrices

$$
\operatorname{tr}[A,B]=0.
$$

Why should you be careful with the same statement for differential operators?

<details><summary><strong>Solution</strong></summary>

In finite dimensions,

$$
\operatorname{tr}[A,B]=\operatorname{tr}(AB)-\operatorname{tr}(BA)=0
$$

by cyclicity. For infinite-dimensional operators, $AB$ and $BA$ may not be trace class, may not have the same domain, or may require a regulator that breaks naive cyclicity. This is one way anomalies and boundary terms can enter formal trace manipulations.

</details>

### Exercise 4: Small field redefinition

Consider a finite-dimensional change of variables

$$
x^i=y^i+\epsilon v^i(y).
$$

Find the Jacobian to first order in $\epsilon$.

<details><summary><strong>Solution</strong></summary>

The Jacobian matrix is

$$
J^i{}_j=\frac{\partial x^i}{\partial y^j}
=\delta^i{}_j+\epsilon\frac{\partial v^i}{\partial y^j}.
$$

Therefore

$$
\det J
=1+\epsilon\operatorname{tr}\left(\frac{\partial v^i}{\partial y^j}\right)+O(\epsilon^2)
=1+\epsilon\partial_i v^i+O(\epsilon^2).
$$

The divergence $\partial_i v^i$ is the infinitesimal volume change generated by the vector field $v$.

</details>

## References

For linear algebra and exterior powers, see standard treatments of multilinear algebra and the geometry-oriented introductions by Frankel and Nakahara. For QFT uses, compare the determinant technology in Gaussian path integrals, fermionic path integrals, functional determinants, and gauge fixing in Srednicki, Schwartz, Zee, Weinberg, Zinn-Justin, and related mathematical physics references. For the infinite-dimensional cautions, the relevant surrounding topics are trace-class operators, zeta regularization, heat kernels, eta invariants, and anomaly computations.

## Version history

- 2026-06-26: First polished draft for the Mathematical Toolkit.
