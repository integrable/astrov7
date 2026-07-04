---
title: "Chern Classes"
description: "Defines Chern classes of complex vector bundles, derives their curvature representatives, and explains their use in flux quantization, instanton number, index theory, and anomaly formulas."
sidebar:
  label: "Chern Classes"
  order: 8
level: Advanced
status: "Polished draft"
source: "Standard references on Chern classes and Chern–Weil theory, including Milnor–Stasheff, Bott–Tu, Nakahara, Frankel, Eguchi–Gilkey–Hanson, and QFT treatments of monopoles, instantons, anomalies, and index theory."
topics:
  - Chern classes
  - Chern character
  - complex vector bundles
  - Chern-Weil theory
  - first Chern class
  - second Chern class
  - flux quantization
  - instanton number
  - index theorem
  - anomaly polynomials
canonicalTopics:
  - chern-class
  - chern-character
  - complex-vector-bundle
  - chern-weil-theory
  - first-chern-class
  - second-chern-class
  - flux-quantization
  - instanton-number
  - index-theorem
  - anomaly-polynomial
researchStatus:
  established:
    - "Chern classes are standard integral characteristic classes of complex vector bundles and are the basic topological invariants behind line-bundle flux, nonabelian instanton number, Chern characters, and many index-theoretic formulas."
  active:
    - "Modern QFT often uses refinements of Chern data in differential cohomology, equivariant cohomology, K-theory, higher gauge fields, and anomaly inflow with singular or background-field configurations."
---

## Summary

Chern classes are characteristic classes of complex vector bundles. For a rank-$r$ complex bundle

$$
E\to M,
$$

they are cohomology classes

$$
c_k(E)\in H^{2k}(M;\mathbb Z),\qquad k=0,1,\ldots,r,
$$

assembled into the total Chern class

$$
c(E)=1+c_1(E)+c_2(E)+\cdots+c_r(E).
$$

They measure the global twisting of complex vector spaces over $M$. In QFT, this is not ornamental mathematics. The first Chern class is quantized $U(1)$ flux. The second Chern class is the invariant behind many four-dimensional instanton numbers. The Chern character enters index theorems and anomaly polynomials. If you have ever seen

$$
\int_\Sigma \frac{F}{2\pi}\in\mathbb Z,
\qquad
\int_M \operatorname{tr}(F\wedge F),
\qquad
\operatorname{index}(D_E)=\int_M \widehat A(TM)\operatorname{ch}(E),
$$

then Chern classes are already in the room, quietly moving furniture.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram showing a complex vector bundle, patching data, a connection, curvature, a Chern-Weil representative, Chern roots, Chern classes, characteristic numbers, and QFT uses such as flux sectors, instanton number, index theorem, and anomaly polynomials.](/figures/math-toolkit/chern-class-dictionary.svg)

<figcaption>

Chern classes can be read from patching data or represented by curvature polynomials after choosing a connection. The curvature form is not itself the topology; the cohomology class of the normalized invariant polynomial is.

</figcaption>
</figure>

The basic dictionary is

$$
\text{complex bundle}\quad\longrightarrow\quad
\text{Chern classes}\quad\longrightarrow\quad
\text{quantized topological data}.
$$

The subtle point is that a connection gives differential-form representatives, while the Chern classes themselves are integral cohomology classes. Different connections give different forms, but the same class.

## Prerequisites

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) for transition functions, [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) for the curvature convention

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A,
$$

and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) for the translation between mathematical connections and physics gauge fields.

Read [Čech Cohomology Preview](/math-toolkit/topology-cohomology-characteristic-classes/cech-cohomology-preview/) for patching cocycles, [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) for closed forms modulo exact forms, and [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/) for the general Chern–Weil philosophy.

For later applications, [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) explains where Chern characters enter index formulas, and [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/) explains the real-bundle obstruction data that Chern classes do not replace.

## Core idea

A complex vector bundle is locally trivial:

$$
E|_{U_i}\simeq U_i\times \mathbb C^r.
$$

On overlaps $U_i\cap U_j$, local trivializations are related by transition functions

$$
g_{ij}:U_i\cap U_j\to GL(r,\mathbb C),
$$

or, after choosing a Hermitian metric, by transition functions valued in $U(r)$. The Chern classes are natural cohomology classes built from this patching data.

Naturality means that for any smooth map $f:N\to M$,

$$
c_k(f^*E)=f^*c_k(E).
$$

This property is the reason Chern classes are so useful in physics. You can restrict a gauge bundle to a two-sphere surrounding a monopole, pull a Berry bundle back to a parameter subspace, or evaluate a bundle on a compactified spacetime, and the Chern class follows the pullback.

The total Chern class obeys the Whitney product formula:

$$
c(E\oplus F)=c(E)c(F).
$$

This formula is one of the main computational engines. It says that Chern classes behave like elementary symmetric functions of hidden degree-two variables, the Chern roots.

## Line bundles and the first Chern class

For a complex line bundle $L\to M$, the only potentially nonzero Chern class is

$$
c_1(L)\in H^2(M;\mathbb Z).
$$

Line bundles are classified, on a sufficiently nice space such as a smooth manifold, by their first Chern class:

$$
\{
\text{complex line bundles on }M
\}/\cong
\simeq H^2(M;\mathbb Z).
$$

This is already the Dirac-monopole story. A $U(1)$ gauge field is a connection on a complex line bundle. If its curvature is normalized as $F_{\mathrm{geom}}$, then

$$
c_1(L)_\mathbb R=\left[\frac{F_{\mathrm{geom}}}{2\pi}\right],
$$

so for every closed oriented two-cycle $\Sigma$,

$$
\int_\Sigma \frac{F_{\mathrm{geom}}}{2\pi}\in\mathbb Z.
$$

This integer is not a perturbative statement. It is the period of an integral cohomology class.

### Transition functions

Let $L$ be described by nonzero complex transition functions

$$
g_{ij}:U_i\cap U_j\to \mathbb C^*.
$$

On triple overlaps,

$$
g_{ij}g_{jk}g_{ki}=1.
$$

If $g_{ij}=e^{i\lambda_{ij}}$ locally, then on triple overlaps the sum

$$
\lambda_{ij}+\lambda_{jk}+\lambda_{ki}
$$

is an integer multiple of $2\pi$. These integers form a Čech two-cocycle, and its cohomology class is $c_1(L)$. This is the patching-data definition of the same object represented by curvature as $F_{\mathrm{geom}}/(2\pi)$.

So there are two complementary pictures:

$$
\text{transition functions}\quad\leadsto\quad c_1(L)\in H^2(M;\mathbb Z),
$$

and, after choosing a connection,

$$
\text{curvature}\quad\leadsto\quad \frac{F_{\mathrm{geom}}}{2\pi}\in \Omega^2_{\mathrm{closed}}(M).
$$

They agree after mapping integral cohomology to de Rham cohomology.

### Tensor products and duals

The first Chern class is additive under tensor products:

$$
c_1(L\otimes L')=c_1(L)+c_1(L').
$$

For the dual line bundle,

$$
c_1(L^*)=-c_1(L).
$$

For an $n$th tensor power,

$$
c_1(L^{\otimes n})=n c_1(L).
$$

This is why charge-$q$ matter coupled to a $U(1)$ connection effectively sees $q$ times the basic line-bundle curvature. It is also why flux quantization and charge quantization cannot be cleanly separated once global bundle data is taken seriously.

## Chern–Weil representatives

Let $E\to M$ be a rank-$r$ complex vector bundle with connection

$$
\nabla=d+\mathcal A,
$$

where $\mathcal A$ is a matrix-valued one-form. Its curvature is

$$
\mathcal F=\nabla^2=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

Define the matrix-valued two-form

$$
X=\frac{i\mathcal F}{2\pi}.
$$

The total Chern class has the de Rham representative

$$
c(E)_\mathbb R=\big[\det(1+X)\big].
$$

Expanding the determinant gives

$$
c_1(E)_\mathbb R=[\operatorname{tr}X],
$$

and

$$
c_2(E)_\mathbb R=
\left[\frac12\left((\operatorname{tr}X)^2-\operatorname{tr}(X^2)\right)\right].
$$

Here $X^2$ means wedge product of forms together with matrix multiplication.

The Chern character is

$$
\operatorname{ch}(E)=\left[\operatorname{tr}\exp X\right].
$$

It begins as

$$
\operatorname{ch}(E)
=r+c_1(E)+\frac12\left(c_1(E)^2-2c_2(E)\right)
+\frac16\left(c_1(E)^3-3c_1(E)c_2(E)+3c_3(E)\right)+\cdots.
$$

Unlike the total Chern class, the Chern character is additive under direct sums and multiplicative under tensor products:

$$
\operatorname{ch}(E\oplus F)=\operatorname{ch}(E)+\operatorname{ch}(F),
$$

$$
\operatorname{ch}(E\otimes F)=\operatorname{ch}(E)\operatorname{ch}(F).
$$

That is why it is the natural characteristic class for K-theory and index formulas.

## Chern roots and the splitting principle

The splitting principle says that, for purposes of computing universal characteristic-class identities, one may pretend that a rank-$r$ complex bundle splits into line bundles:

$$
E\sim L_1\oplus\cdots\oplus L_r.
$$

This need not be literally true on $M$. The point is that there is a pullback space on which it becomes true and where no universal identity is lost.

Write

$$
x_a=c_1(L_a),\qquad a=1,\ldots,r.
$$

The $x_a$ are the Chern roots. Then

$$
c(E)=\prod_{a=1}^r(1+x_a),
$$

so

$$
c_1(E)=\sum_a x_a,
$$

$$
c_2(E)=\sum_{a<b}x_a x_b,
$$

and, more generally, $c_k(E)$ is the $k$th elementary symmetric polynomial in the Chern roots.

The Chern character becomes especially simple:

$$
\operatorname{ch}(E)=\sum_{a=1}^r e^{x_a}.
$$

This notation is wildly efficient. It is also a source of confusion: the Chern roots are computational devices, not necessarily honest globally defined two-classes on the original base manifold.

## Standard identities

For complex vector bundles $E$ and $F$,

$$
c(E\oplus F)=c(E)c(F).
$$

For the dual bundle,

$$
c_k(E^*)=(-1)^k c_k(E).
$$

For the determinant line bundle,

$$
\det E=\Lambda^r E,
$$

one has

$$
c_1(\det E)=c_1(E).
$$

For a short exact sequence of complex vector bundles

$$
0\to E'\to E\to E''\to 0,
$$

one has

$$
c(E)=c(E')c(E'').
$$

For a trivial bundle $\underline{\mathbb C}^r$,

$$
c(\underline{\mathbb C}^r)=1.
$$

These formulas are the characteristic-class version of bookkeeping. They let you compute Chern classes from exact sequences, direct sums, tensor products, duals, and determinant line bundles without writing a connection explicitly.

## Gauge theory examples

### Abelian flux

For a $U(1)$ gauge bundle over a closed two-cycle $\Sigma$,

$$
\int_\Sigma c_1(L)=\int_\Sigma \frac{F_{\mathrm{geom}}}{2\pi}\in\mathbb Z.
$$

This integer is magnetic flux in the geometric normalization. In physics normalizations, the gauge coupling and the minimal electric charge may be absorbed into the definition of $F$. The invariant content is that the connection lives on a line bundle and $c_1(L)$ has integral periods.

For a Dirac monopole, restrict the line bundle to a surrounding $S^2$. The monopole charge is

$$
\int_{S^2}c_1(L).
$$

If the surrounding sphere is deformed without crossing sources, this integer does not change.

### Nonabelian instanton number

For an $SU(N)$ bundle, the determinant line bundle is trivial, so

$$
c_1(E)=0.
$$

The first interesting Chern class is $c_2(E)\in H^4(M;\mathbb Z)$. On a compact oriented four-manifold $M$, its integral

$$
\int_M c_2(E)
$$

is an integer characteristic number.

This is the topological quantity behind the instanton number of many four-dimensional gauge fields. Depending on whether one uses Hermitian or anti-Hermitian generators, and depending on the orientation convention, the physics quantity often written as

$$
\frac{1}{8\pi^2}\int_M \operatorname{tr}(F\wedge F)
$$

may equal $\int_M c_2(E)$ or its negative. The convention-dependent sign is less important than the invariant statement: a normalized degree-four characteristic class has integer periods.

### Chern–Simons transgression

Chern classes are closed-form representatives in even degree, but their changes are related to odd-dimensional Chern–Simons forms. Schematically,

$$
d\operatorname{CS}_{2k-1}(\mathcal A)=\operatorname{tr}(\mathcal F^k)
$$

with normalization and trace convention chosen appropriately. This is why Chern–Simons actions in odd dimensions know about Chern classes in one higher dimension. It is also why large gauge transformations can quantize Chern–Simons levels.

## Index and anomaly formulas

The Chern character is the form of Chern data that appears most naturally in the Atiyah–Singer index theorem. For a Dirac operator twisted by a complex vector bundle $E$,

$$
\operatorname{index}(D_E)
=
\int_M \widehat A(TM)\operatorname{ch}(E),
$$

on a compact spin manifold, with the degree-$\dim M$ component understood.

This formula has two lives in QFT.

First, it counts chiral zero modes in background gauge and gravitational fields. Instanton backgrounds can force fermion zero modes because the index is nonzero.

Second, the same characteristic classes organize anomaly polynomials. In even-dimensional chiral theories, anomaly data is often packaged in a closed form in two dimensions higher, built from factors such as

$$
\operatorname{ch}(E),\qquad \widehat A(TM),\qquad L(TM),
$$

and then related to anomalous variations by descent.

For this page, the important lesson is not the full descent machinery. It is this: Chern classes convert the topology of complex gauge bundles into the polynomial data that appears in indices and anomalies.

## Chern classes and complex geometry

If $X$ is a complex manifold, its holomorphic tangent bundle $TX$ is a complex vector bundle, so one can form

$$
c_k(TX).
$$

The first Chern class controls the determinant of the tangent bundle, equivalently the inverse of the canonical bundle:

$$
K_X=\Lambda^{\dim_\mathbb C X}T^*X.
$$

Thus

$$
c_1(TX)=-c_1(K_X).
$$

In geometry and string theory, the condition

$$
c_1(TX)=0
$$

is the topological part of the Calabi–Yau condition. It is not by itself the full Ricci-flat metric statement, but it is the characteristic-class obstruction that must vanish.

For ordinary QFT applications, the main reason to remember this section is simpler: once the tangent bundle has a complex structure, Chern classes can measure spacetime or target-space topology, not only gauge-bundle topology.

## Relation to real characteristic classes

Every complex vector bundle $E$ has an underlying real vector bundle $E_\mathbb R$, obtained by forgetting multiplication by $i$. Its Stiefel–Whitney classes satisfy

$$
w(E_\mathbb R)=c(E)\bmod 2.
$$

Equivalently,

$$
w_{2k}(E_\mathbb R)=c_k(E)\bmod 2,
\qquad
w_{2k+1}(E_\mathbb R)=0.
$$

This relation is one of the main bridges between Chern classes and spin obstructions. For example, if $X$ is a complex manifold, then

$$
w_2(TX_\mathbb R)=c_1(TX)\bmod 2.
$$

So a complex manifold with even $c_1(TX)$ is spin, while a complex manifold with odd $c_1(TX)$ is not. The next page develops this mod-$2$ obstruction viewpoint systematically.

## Common pitfalls

**A curvature formula is not the class itself.** The expression $\det(1+i\mathcal F/2\pi)$ is a differential-form representative after choosing a connection. The Chern class is the integral cohomology class represented by this form in de Rham cohomology.

**The normalization matters.** The factors of $2\pi$ and $i$ are not decoration. Without them, periods need not be integral. Physics conventions for Hermitian generators often move signs and couplings around, so always identify the geometric connection before reading off a Chern class.

**Chern roots are not always actual classes on the original manifold.** They are a computational device justified by the splitting principle. Symmetric polynomials in them are honest characteristic classes.

**Chern classes do not classify every complex vector bundle in every dimension.** They are powerful invariants, but not a complete classification in full generality. Torsion and unstable phenomena can require finer tools.

**$c_1=0$ does not mean the bundle is trivial.** An $SU(N)$ bundle has $c_1=0$ by construction, but it may still have nonzero $c_2$ or higher Chern classes.

**The instanton number sign is convention-sensitive.** The integer is topological. Whether a local formula is written with a plus or minus sign depends on generator, trace, and orientation conventions.

## Exercises

### Exercise 1: Tensor products of line bundles

Let $L$ and $M$ be complex line bundles. Show that

$$
c_1(L\otimes M)=c_1(L)+c_1(M).
$$

<details><summary><strong>Solution</strong></summary>

Choose transition functions $g_{ij}$ for $L$ and $h_{ij}$ for $M$. The tensor product $L\otimes M$ has transition functions

$$
g_{ij}h_{ij}.
$$

If locally

$$
g_{ij}=e^{i\lambda_{ij}},\qquad h_{ij}=e^{i\mu_{ij}},
$$

then

$$
g_{ij}h_{ij}=e^{i(\lambda_{ij}+\mu_{ij})}.
$$

The integer Čech two-cocycle on triple overlaps is therefore the sum of the two cocycles. Hence

$$
c_1(L\otimes M)=c_1(L)+c_1(M).
$$

The same result follows from curvature: tensoring line bundles adds connection one-forms, so it adds curvature two-forms.

</details>

### Exercise 2: Direct sum of two line bundles

Suppose

$$
E=L_1\oplus L_2,
\qquad
x_1=c_1(L_1),
\qquad
x_2=c_1(L_2).
$$

Compute $c_1(E)$, $c_2(E)$, and the degree-four part of $\operatorname{ch}(E)$.

<details><summary><strong>Solution</strong></summary>

By the Whitney product formula,

$$
c(E)=c(L_1)c(L_2)=(1+x_1)(1+x_2).
$$

Therefore

$$
c_1(E)=x_1+x_2,
$$

and

$$
c_2(E)=x_1x_2.
$$

The Chern character is

$$
\operatorname{ch}(E)=e^{x_1}+e^{x_2}.
$$

Its degree-four part is

$$
\operatorname{ch}_2(E)=\frac12(x_1^2+x_2^2).
$$

In terms of Chern classes,

$$
\operatorname{ch}_2(E)=\frac12\left(c_1(E)^2-2c_2(E)\right),
$$

because

$$
\frac12\left((x_1+x_2)^2-2x_1x_2\right)=\frac12(x_1^2+x_2^2).
$$

</details>

### Exercise 3: Why an SU bundle has vanishing first Chern class

Let $E\to M$ be a complex rank-$N$ vector bundle with structure group reduced to $SU(N)$. Explain why $c_1(E)=0$.

<details><summary><strong>Solution</strong></summary>

There are two standard arguments.

First, the determinant line bundle is

$$
\det E=\Lambda^N E.
$$

If the transition functions of $E$ lie in $SU(N)$, their determinants are $1$. Therefore the determinant line bundle has trivial transition functions and is trivial. Since

$$
c_1(E)=c_1(\det E),
$$

we get

$$
c_1(E)=0.
$$

Second, using a unitary connection with curvature $\mathcal F$ valued in $\mathfrak{su}(N)$,

$$
\operatorname{tr}\mathcal F=0.
$$

The Chern–Weil representative

$$
c_1(E)_\mathbb R=\left[\frac{i}{2\pi}\operatorname{tr}\mathcal F\right]
$$

therefore vanishes in de Rham cohomology. The determinant-bundle argument gives the stronger integral statement.

</details>

### Exercise 4: Flux quantization from the first Chern class

Let $L\to S^2$ be a complex line bundle with connection curvature $F_{\mathrm{geom}}$. Explain why

$$
\int_{S^2}\frac{F_{\mathrm{geom}}}{2\pi}
$$

is an integer.

<details><summary><strong>Solution</strong></summary>

The normalized curvature form represents the real image of the first Chern class:

$$
\left[\frac{F_{\mathrm{geom}}}{2\pi}\right]=c_1(L)_\mathbb R.
$$

Since

$$
c_1(L)\in H^2(S^2;\mathbb Z),
$$

its pairing with the fundamental class $[S^2]$ is an integer:

$$
\langle c_1(L),[S^2]\rangle\in\mathbb Z.
$$

Under the de Rham map, this pairing is computed by the integral

$$
\int_{S^2}\frac{F_{\mathrm{geom}}}{2\pi}.
$$

Therefore the integral is an integer.

</details>

## References

- J. Milnor and J. Stasheff, *Characteristic Classes*. Standard mathematical reference for Chern classes, Stiefel–Whitney classes, Pontryagin classes, and characteristic numbers.
- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*. Excellent for the relation between forms, cohomology, and characteristic classes.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented source for Chern classes, monopoles, instantons, and index-theorem applications.
- T. Frankel, *The Geometry of Physics*. Geometric source for bundles, connections, Chern forms, gauge fields, and applications to physics.
- T. Eguchi, P. Gilkey, and A. Hanson, “Gravitation, gauge theories and differential geometry.” Classic physics review of characteristic classes and index theory.
- A. S. Schwarz, *Topology for Physicists*. Useful for physical examples of characteristic classes and topological charges.
- M. F. Atiyah and I. M. Singer, papers on the index theorem. Foundational source for the index formula involving $\widehat A(TM)\operatorname{ch}(E)$.

## Version history

- **2026-06-25:** Initial polished draft. Added the line-bundle picture, Chern–Weil representatives, Chern roots, QFT applications to flux and instanton number, index/anomaly context, common pitfalls, exercises, and the Chern-class dictionary figure.
