---
title: "Index Theorems"
description: "Explains the Atiyah–Singer index theorem for elliptic operators, derives the Dirac index formula used in QFT, and connects zero modes, characteristic classes, anomalies, and topological terms."
sidebar:
  label: "Index Theorems"
  order: 11
level: Advanced
status: "Polished draft"
source: "Standard references on elliptic operators and index theory, including Atiyah–Singer, Gilkey, Nakahara, Frankel, Berline–Getzler–Vergne, Eguchi–Gilkey–Hanson, and QFT treatments of instantons, anomalies, and fermion determinants."
topics:
  - Atiyah-Singer index theorem
  - elliptic operators
  - Dirac operator
  - zero modes
  - A-hat genus
  - Chern character
  - Hirzebruch signature theorem
  - Gauss-Bonnet theorem
  - anomaly polynomials
  - heat kernel proof
canonicalTopics:
  - atiyah-singer-index-theorem
  - elliptic-operator
  - dirac-operator
  - zero-mode
  - a-hat-genus
  - chern-character
  - signature-theorem
  - gauss-bonnet-theorem
  - anomaly-polynomial
  - heat-kernel-index
researchStatus:
  established:
    - "The Atiyah–Singer index theorem equates the analytic index of an elliptic operator on a compact manifold with a topological expression built from the operator symbol and characteristic classes."
  active:
    - "Modern QFT uses refinements of index theory with boundaries, defects, noncompact spaces, families, equivariance, differential cohomology, determinant lines, and global anomaly phases."
---

## Summary

Index theorems are bridges between analysis and topology. They say that a signed count of zero modes of a differential operator equals a characteristic-class integral.

The prototype is the Atiyah–Singer index theorem. For a suitable elliptic operator

$$
D:\Gamma(E)\to\Gamma(F)
$$

on a compact manifold,

$$
\operatorname{index}(D)
=\dim\ker D-\dim\operatorname{coker}D
$$

is determined by topological data. For the chiral Dirac operator $D_E^+$ on a closed spin manifold $M$ twisted by a complex bundle $E$, the formula is

$$
\operatorname{index}(D_E^+)
=\int_M \widehat A(TM)\operatorname{ch}(E).
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram showing elliptic operator data leading to analytic index, characteristic classes leading to topological index, heat kernel connecting both, and QFT uses including instanton zero modes, anomalies, determinant phases, and anomaly inflow.](/figures/math-toolkit/index-theorem-bridge.svg)

<figcaption>

The index theorem equates two ways of computing the same integer. The analytic side counts zero modes with signs. The topological side integrates characteristic classes. The heat-kernel proof explains why a local curvature density can know about a global zero-mode count.

</figcaption>
</figure>

This formula is everywhere in QFT, sometimes visibly and sometimes in disguise. It counts fermion zero modes in instanton backgrounds, determines selection rules for anomalous processes, supplies anomaly polynomials, controls determinant-line phases, and explains why local curvature terms such as $\widehat A(TM)\operatorname{ch}(E)$ have integer global consequences.

The slogan is

$$
\text{zero modes} \quad = \quad \text{topology, counted with the right signs}.
$$

That slogan is a little too short to be safe. The real statement requires ellipticity, compactness or boundary conditions, a precise operator, and the correct characteristic classes. This page keeps those hypotheses visible.

## Prerequisites

Read [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) for the geometric Dirac operator and [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/) for the topological condition needed to define ordinary spinors. Read [Chern Classes](/math-toolkit/topology-cohomology-characteristic-classes/chern-classes/) for the Chern character and [Pontryagin Classes](/math-toolkit/topology-cohomology-characteristic-classes/pontryagin-classes/) for the $\widehat A$ genus.

For the topology side, read [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/), [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/), and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/). For the analytic intuition, [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explains the short-time expansion that turns index formulas into local curvature densities.

## What an index counts

Let $D:V\to W$ be a linear map between finite-dimensional vector spaces. Its index is

$$
\operatorname{index}(D)=\dim\ker D-\dim\operatorname{coker}D.
$$

Since

$$
\operatorname{coker}D=W/\operatorname{im}D,
$$

the rank-nullity theorem gives

$$
\operatorname{index}(D)=\dim V-\dim W.
$$

In finite dimensions this is not very exciting. The index becomes powerful for infinite-dimensional spaces, where $D$ is a differential operator. The kernels can be finite-dimensional even though the ambient spaces are infinite-dimensional, and the index becomes stable under continuous deformations.

For a Fredholm operator, both $\ker D$ and $\operatorname{coker}D$ are finite-dimensional, and the index is well-defined. Elliptic differential operators on compact manifolds are Fredholm after choosing suitable Sobolev completions. This is why ellipticity is the analytic hypothesis that makes index theory work.

A self-adjoint operator $D$ has no coker mystery: $\operatorname{coker}D$ is naturally related to $\ker D^*$. But many physically important operators are chiral:

$$
D^+:\Gamma(S^+\otimes E)\to\Gamma(S^-\otimes E).
$$

Then

$$
\operatorname{index}(D^+)=\dim\ker D^+-\dim\ker D^-.
$$

This is a signed count of zero modes of positive and negative chirality. It is not the total number of zero modes.

## Elliptic operators and symbols

A differential operator $D$ of order $m$ has a principal symbol

$$
\sigma_D(x,\xi):E_x\to F_x,
$$

where $x\in M$ and $\xi\in T_x^*M$. The symbol keeps only the highest-derivative part of the operator, replacing

$$
\partial_\mu\quad\text{by}\quad i\xi_\mu.
$$

The operator is elliptic if

$$
\sigma_D(x,\xi)
$$

is an isomorphism for every nonzero covector $\xi\ne 0$.

For the Dirac operator

$$
D=\gamma^\mu\nabla_\mu,
$$

the principal symbol is

$$
\sigma_D(x,\xi)=i\gamma^\mu\xi_\mu.
$$

Using the Clifford relation in Euclidean signature,

$$
\{\gamma^\mu,\gamma^\nu\}=2g^{\mu\nu},
$$

we get

$$
\sigma_D(x,\xi)^2=-|\xi|^2.
$$

For $\xi\ne 0$, this is invertible. Hence the Euclidean Dirac operator is elliptic.

This is why index theorems are naturally Euclidean. Lorentzian Dirac operators are hyperbolic, not elliptic. In Lorentzian QFT the index-theoretic information usually enters after Wick rotation, through Euclidean backgrounds, or through spectral flow in a Hamiltonian formulation.

## The Atiyah–Singer theorem in one line

The general Atiyah–Singer theorem says

$$
\operatorname{index}_{\mathrm{an}}(D)=\operatorname{index}_{\mathrm{top}}(\sigma_D).
$$

The left side is analytic:

$$
\operatorname{index}_{\mathrm{an}}(D)
=\dim\ker D-\dim\operatorname{coker}D.
$$

The right side is topological: it is built from the $K$-theory class of the principal symbol and characteristic classes of the manifold.

For QFT, the most useful special cases are more concrete than the full $K$-theoretic statement:

$$
\operatorname{index}(D_E^+)=\int_M\widehat A(TM)\operatorname{ch}(E),
$$

for spin Dirac operators;

$$
\chi(M)=\int_M e(TM),
$$

for the de Rham operator and Gauss–Bonnet;

$$
\sigma(M)=\int_M L(TM),
$$

for the signature operator;

and

$$
\chi(M,E)=\int_M \operatorname{Td}(T^{1,0}M)\operatorname{ch}(E),
$$

for the Dolbeault operator on a compact complex manifold.

## The Dirac index formula

Let $M$ be a closed oriented spin manifold of dimension $2n$. The spinor bundle decomposes into chiral pieces:

$$
S=S^+\oplus S^-.
$$

Let $E\to M$ be a complex vector bundle with connection. The twisted Dirac operator is

$$
D_E:\Gamma(S\otimes E)\to\Gamma(S\otimes E).
$$

It anticommutes with chirality, so it has off-diagonal form

$$
D_E=\begin{pmatrix}
0&D_E^-\\
D_E^+&0
\end{pmatrix},
$$

where

$$
D_E^+:\Gamma(S^+\otimes E)\to\Gamma(S^-\otimes E).
$$

The Atiyah–Singer formula is

$$
\operatorname{index}(D_E^+)
=\dim\ker D_E^+-\dim\ker D_E^-
=\int_M \widehat A(TM)\operatorname{ch}(E).
$$

Here

$$
\operatorname{ch}(E)=\operatorname{tr}\exp\!\left(\frac{iF}{2\pi}\right)
$$

for a unitary connection with curvature $F$, and

$$
\widehat A(TM)=1-\frac{p_1(TM)}{24}+\frac{7p_1(TM)^2-4p_2(TM)}{5760}+\cdots .
$$

The product is expanded and only the top-degree part is integrated.

:::note[Physics convention warning]
Gauge theorists often take the connection to be Hermitian or anti-Hermitian depending on convention. The expression $\operatorname{tr}\exp(iF/2\pi)$ assumes the usual Chern–Weil normalization for a unitary connection. If $F$ is anti-Hermitian, the same formula is often written as $\operatorname{tr}\exp(F/2\pi i)$.
:::

## Example: two-dimensional flux and chiral zero modes

Let $M_2$ be a closed spin surface and let $L\to M_2$ be a complex line bundle. The twisted Dirac index is

$$
\operatorname{index}(D_L^+)=\int_{M_2}\widehat A(TM_2)\operatorname{ch}(L).
$$

In two dimensions, $\widehat A(TM_2)$ has no degree-two part, so

$$
\widehat A(TM_2)=1.
$$

Also

$$
\operatorname{ch}(L)=1+c_1(L)+\cdots .
$$

Therefore

$$
\operatorname{index}(D_L^+)=\int_{M_2}c_1(L)
=\int_{M_2}\frac{F}{2\pi}.
$$

Thus a two-dimensional Dirac fermion coupled to a $U(1)$ bundle with flux $m$ has

$$
n_+-n_-=m,
$$

where $n_\pm$ are the numbers of chiral zero modes. The total number $n_++n_-$ can change under deformations, but the difference is fixed by the flux.

This formula is the cleanest baby version of the index theorem. Magnetic flux forces chiral zero modes.

## Example: four-dimensional gauge instantons

Let $M_4$ be a closed spin four-manifold and let $E\to M_4$ be a complex vector bundle associated to a gauge representation. The degree-four part of

$$
\widehat A(TM)\operatorname{ch}(E)
$$

is

$$
\left[\widehat A(TM)\operatorname{ch}(E)\right]_4
=\operatorname{ch}_2(E)-\frac{\operatorname{rank}(E)}{24}p_1(TM).
$$

If $M_4=\mathbb R^4$ compactified to $S^4$ and the tangent contribution is trivial, the index is governed by the gauge bundle:

$$
\operatorname{index}(D_E^+)=\int_{M_4}\operatorname{ch}_2(E).
$$

For an $SU(N)$ instanton of charge $k$ and a Weyl fermion in representation $R$, physicists often write

$$
\operatorname{index}(D_R^+)=2T(R)k,
$$

where the Dynkin index is defined by

$$
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab}.
$$

For the fundamental representation of $SU(N)$,

$$
T(\mathbf N)=\frac{1}{2},
$$

so

$$
\operatorname{index}(D_{\mathbf N}^+)=k.
$$

For the adjoint representation,

$$
T(\operatorname{adj})=N,
$$

so

$$
\operatorname{index}(D_{\operatorname{adj}}^+)=2Nk.
$$

The sign depends on the orientation, the chirality convention, and whether one uses instantons or anti-instantons. The magnitude and representation dependence are the invariant content.

## Example: pure gravitational Dirac index in four dimensions

For the untwisted chiral Dirac operator on a closed spin four-manifold,

$$
\operatorname{index}(D^+)=\int_{M_4}\widehat A(TM_4).
$$

The degree-four part is

$$
\widehat A(TM_4)=-\frac{p_1(TM_4)}{24}.
$$

Therefore

$$
\operatorname{index}(D^+)=-\frac{1}{24}\int_{M_4}p_1(TM_4).
$$

Using the signature theorem

$$
\int_{M_4}p_1(TM_4)=3\sigma(M_4),
$$

we get

$$
\operatorname{index}(D^+)=-\frac{\sigma(M_4)}{8}.
$$

For a spin four-manifold, the right-hand side is an integer. This integrality is not obvious from the signature alone; it is a deep topological constraint.

## Gauss–Bonnet as an index theorem

The Euler characteristic of a compact oriented manifold is

$$
\chi(M)=\sum_k(-1)^k\dim H^k(M;\mathbb R).
$$

The de Rham operator

$$
d+d^*
$$

maps even forms to odd forms and odd forms to even forms. Its chiral index is

$$
\operatorname{index}(d+d^*)_{\mathrm{even}\to\mathrm{odd}}
=\dim H^{\mathrm{even}}(M)-\dim H^{\mathrm{odd}}(M)
=\chi(M).
$$

The index theorem gives

$$
\chi(M)=\int_M e(TM),
$$

where $e(TM)$ is the Euler class.

So Gauss–Bonnet is not separate folklore; it is the index theorem for the de Rham complex. The familiar curvature integral for a surface,

$$
\chi(\Sigma)=\frac{1}{2\pi}\int_\Sigma K\,dA,
$$

is the two-dimensional version of the same statement.

## The signature theorem

On an oriented compact $4k$-manifold, the intersection pairing on middle cohomology has a signature

$$
\sigma(M)=b_{2k}^+-b_{2k}^-.
$$

The corresponding signature operator has index

$$
\operatorname{index}(D_{\mathrm{sig}})=\sigma(M).
$$

The index theorem gives

$$
\sigma(M)=\int_M L(TM),
$$

where

$$
L(TM)=1+\frac{p_1}{3}+\frac{7p_2-p_1^2}{45}+\cdots .
$$

In four dimensions,

$$
\sigma(M_4)=\frac{1}{3}\int_{M_4}p_1(TM_4).
$$

This theorem is a useful reminder that Pontryagin classes are not abstract decorations. They measure the imbalance of self-dual and anti-self-dual middle-dimensional topology.

## Dolbeault and Riemann–Roch

Let $X$ be a compact complex manifold and $E\to X$ a holomorphic vector bundle. The Dolbeault complex is

$$
0\to \Omega^{0,0}(X,E)
\xrightarrow{\overline\partial}
\Omega^{0,1}(X,E)
\xrightarrow{\overline\partial}
\cdots
\xrightarrow{\overline\partial}
\Omega^{0,n}(X,E)\to 0.
$$

Its index is the holomorphic Euler characteristic

$$
\chi(X,E)=\sum_q(-1)^q\dim H^q(X,E).
$$

The Hirzebruch–Riemann–Roch theorem says

$$
\chi(X,E)=\int_X\operatorname{Td}(T^{1,0}X)\operatorname{ch}(E).
$$

The Todd class begins

$$
\operatorname{Td}(V)=1+\frac{c_1(V)}{2}+\frac{c_1(V)^2+c_2(V)}{12}+\cdots .
$$

This is the complex-geometric cousin of the Dirac index formula. It is central in supersymmetric theories, complex geometry, sheaf cohomology, and many compactification calculations.

## Heat-kernel proof idea

The cleanest physicist's derivation uses supersymmetric quantum mechanics or heat kernels. Consider the chiral Dirac operator $D$ and chirality operator $\Gamma$. Define

$$
I(t)=\operatorname{Tr}\left(\Gamma e^{-tD^2}\right).
$$

For $t\to\infty$, all nonzero eigenvalues are exponentially suppressed, so

$$
I(\infty)=n_+-n_-=
\operatorname{index}(D^+).
$$

For finite nonzero eigenvalues, states of opposite chirality pair up because $D$ anticommutes with $\Gamma$. Only zero modes contribute.

On the other hand, $I(t)$ is independent of $t$:

$$
\frac{dI}{dt}
=-\operatorname{Tr}\left(\Gamma D^2e^{-tD^2}\right)=0
$$

after using the chirality pairing and trace cyclicity in a regulated sense.

Therefore we may take $t\to 0$. The short-time heat-kernel expansion is local, and its top-degree term gives

$$
I(0)=\int_M \widehat A(TM)\operatorname{ch}(E).
$$

Thus

$$
\operatorname{index}(D_E^+)=I(\infty)=I(0)=\int_M\widehat A(TM)\operatorname{ch}(E).
$$

This is the bridge: long-time heat flow sees zero modes; short-time heat flow sees local curvature. The equality is the theorem.

## Why QFT cares

### Instanton zero modes

In a background with nonzero instanton number, chiral fermion zero modes are forced by the index theorem. These zero modes make certain correlation functions vanish unless operator insertions soak them up. This is the origin of many instanton selection rules and effective vertices.

For example, if a Weyl fermion has index $m$, then the path integral over fermions has $m$ Grassmann zero-mode integrations. A correlation function is nonzero only if the inserted operators contain enough fermion fields to saturate those integrations.

### Anomalies

Perturbative anomalies are encoded by index densities in two higher dimensions. A chiral fermion in $d=2n$ spacetime dimensions has anomaly polynomial

$$
I_{2n+2}=\left[\widehat A(TM)\operatorname{ch}(E)\right]_{2n+2}.
$$

The descent procedure converts this closed form into the anomalous variation of the effective action. The index theorem explains why the same polynomial appears in both zero-mode counting and anomaly formulas.

### Fermion determinant phases

For a nonchiral Dirac fermion, the determinant is often formally written as

$$
\det D.
$$

For chiral fermions, the determinant is a section of a determinant line rather than an ordinary function. Index theory controls the curvature and topology of this line bundle over the space of background fields. This is the geometric version of “the fermion measure is anomalous.”

### Spectral flow

In Hamiltonian language, an index can appear as spectral flow: as a background gauge field changes with time, eigenvalues of a spatial Dirac Hamiltonian cross zero. The net number of crossings equals an index on the spacetime swept out by the interpolation.

This is how Euclidean index theory speaks Lorentzian physics without pretending that Lorentzian Dirac operators are elliptic.

## Boundaries and eta invariants

The simplest index formulas above assume closed manifolds. If $M$ has boundary, the story changes. The Atiyah–Patodi–Singer index theorem adds a boundary correction involving the eta invariant:

$$
\eta(D_{\partial M}).
$$

Schematically,

$$
\operatorname{index}(D_M^+)=\int_M \widehat A(TM)\operatorname{ch}(E)-\frac{\eta(D_{\partial M})+h}{2},
$$

where $h$ is the dimension of the boundary kernel, and the precise formula depends on the operator and boundary condition.

This boundary term is not an aesthetic nuisance. It is the seed of anomaly inflow, parity anomalies, topological insulator boundary responses, and global anomaly phases.

For noncompact manifolds, one needs falloff conditions, weighted spaces, or a compactification prescription. Without such data, the phrase “the index on $\mathbb R^d$” is incomplete.

## Families and global anomalies

A family of Dirac operators parameterized by background fields or moduli can have an index bundle rather than a single index number. Its characteristic classes control anomalies of the family of fermion determinants.

A loop in background-field space can produce a determinant phase even if the local anomaly vanishes. Such global anomalies are often detected by an index theorem in one higher dimension or by eta invariants. The classic pattern is:

$$
\text{loop of backgrounds}
\quad\leadsto\quad
\text{mapping torus}
\quad\leadsto\quad
\text{eta invariant or mod-two index}.
$$

This is beyond the basic Atiyah–Singer formula, but it is the same moral universe: spectral data is constrained by topology.

## Common pitfalls

Do not say “the index counts zero modes” without the word signed. The index counts

$$
n_+-n_-,
$$

not

$$
n_++n_-.
$$

Do not apply elliptic index formulas directly to Lorentzian operators. Wick rotate, use a Euclidean problem, or translate the result into spectral flow.

Do not forget compactness and boundary conditions. On manifolds with boundary, APS or local boundary conditions change the formula. On noncompact manifolds, falloff conditions are part of the problem.

Do not confuse the local index density with the global index. The density depends on a connection. The integrated index is topological.

Do not assume a vanishing index means no zero modes. It means the signed count vanishes. Zero modes of opposite chirality may still exist.

Do not ignore normalization of $\operatorname{tr}F^2$. Instanton number and Dynkin indices depend on trace conventions.

## Exercises

### Exercise 1: Flux on a Riemann surface

Let $L\to\Sigma$ be a complex line bundle over a closed spin Riemann surface with

$$
\int_\Sigma c_1(L)=m.
$$

Compute the index of the Dirac operator twisted by $L$.

<details><summary><strong>Solution</strong></summary>

The twisted Dirac formula is

$$
\operatorname{index}(D_L^+)=\int_\Sigma\widehat A(T\Sigma)\operatorname{ch}(L).
$$

In two dimensions,

$$
\widehat A(T\Sigma)=1
$$

in degree zero, and

$$
\operatorname{ch}(L)=1+c_1(L)+\cdots .
$$

The degree-two part is $c_1(L)$, so

$$
\operatorname{index}(D_L^+)=\int_\Sigma c_1(L)=m.
$$

</details>

### Exercise 2: Untwisted Dirac index in four dimensions

Let $M_4$ be a closed spin four-manifold. Show that

$$
\operatorname{index}(D^+)=-\frac{\sigma(M_4)}{8}.
$$

<details><summary><strong>Solution</strong></summary>

For the untwisted Dirac operator,

$$
\operatorname{index}(D^+)=\int_{M_4}\widehat A(TM_4).
$$

The degree-four term is

$$
\widehat A(TM_4)=-\frac{p_1(TM_4)}{24}.
$$

Thus

$$
\operatorname{index}(D^+)=-\frac{1}{24}\int_{M_4}p_1(TM_4).
$$

The signature theorem gives

$$
\int_{M_4}p_1(TM_4)=3\sigma(M_4).
$$

Therefore

$$
\operatorname{index}(D^+)=-\frac{\sigma(M_4)}{8}.
$$

</details>

### Exercise 3: Fundamental fermion in an SU(N) instanton

Assume the instanton number is normalized so that $k=1$ for a single $SU(N)$ instanton and $T(\mathbf N)=1/2$. Compute the index of a chiral Dirac operator coupled to a fundamental fermion.

<details><summary><strong>Solution</strong></summary>

The standard physics normalization gives

$$
\operatorname{index}(D_R^+)=2T(R)k.
$$

For the fundamental representation,

$$
T(\mathbf N)=\frac{1}{2},
$$

and for a single instanton $k=1$. Therefore

$$
\operatorname{index}(D_{\mathbf N}^+)=2\cdot\frac{1}{2}\cdot 1=1.
$$

The sign depends on chirality and instanton versus anti-instanton conventions.

</details>

### Exercise 4: Vanishing index does not imply no zero modes

Construct a conceptual example showing why $\operatorname{index}(D^+)=0$ does not imply $D$ has no zero modes.

<details><summary><strong>Solution</strong></summary>

The index is

$$
\operatorname{index}(D^+)=n_+-n_-.
$$

It can vanish with $n_+=n_-=1$, or more generally with equal numbers of positive- and negative-chirality zero modes. Thus

$$
\operatorname{index}(D^+)=0
$$

only says the signed count vanishes. It does not imply

$$
n_++n_-=0.
$$

A deformation may pair and lift such zero modes, but symmetry or other structure can also protect them even when the index is zero.

</details>

## References

- Atiyah and Singer, “The Index of Elliptic Operators” series.
- Atiyah, Patodi, and Singer, “Spectral asymmetry and Riemannian geometry” series.
- Berline, Getzler, and Vergne, *Heat Kernels and Dirac Operators*.
- Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*.
- Nakahara, *Geometry, Topology and Physics*.
- Frankel, *The Geometry of Physics*.
- Eguchi, Gilkey, and Hanson, “Gravitation, gauge theories and differential geometry.”
- Alvarez-Gaumé and Ginsparg, “The structure of gauge and gravitational anomalies.”
- Fujikawa and Suzuki, *Path Integrals and Quantum Anomalies*.
- Bertlmann, *Anomalies in Quantum Field Theory*.

## Version history

- 2026-06-25: Initial polished draft. Added analytic and topological index definitions, ellipticity, Dirac, Gauss–Bonnet, signature, Dolbeault, heat-kernel proof idea, QFT applications, boundary cautions, global-anomaly preview, and exercises.
