---
title: "Characteristic Classes"
description: "Explains characteristic classes as natural cohomology classes of bundles, with emphasis on Chern–Weil representatives, curvature formulas, characteristic numbers, and QFT applications."
sidebar:
  label: "Characteristic Classes"
  order: 7
level: Advanced
status: "Polished draft"
source: "Standard geometry and QFT references, including Chern–Weil theory, Milnor–Stasheff, Bott–Tu, Nakahara, Frankel, Eguchi–Gilkey–Hanson, and physics treatments of instantons, anomalies, index theory, and gauge bundles."
topics:
  - characteristic classes
  - Chern classes
  - Chern character
  - Stiefel-Whitney classes
  - Pontryagin classes
  - Euler class
  - Chern-Weil theory
  - curvature
  - anomaly polynomials
  - index theorem
canonicalTopics:
  - characteristic-class
  - chern-class
  - chern-character
  - stiefel-whitney-class
  - pontryagin-class
  - euler-class
  - chern-weil-theory
  - curvature
  - anomaly-polynomial
  - index-theorem
researchStatus:
  established:
    - "Characteristic classes are standard natural cohomology classes attached to bundles and are central to gauge topology, fermion zero modes, topological terms, and anomaly formulas."
  active:
    - "Modern QFT often requires refined characteristic-class data in differential cohomology, equivariant cohomology, generalized cohomology, cobordism, and theories with singular defects or nontrivial global symmetry backgrounds."
---

## Summary

A characteristic class is a cohomology class naturally assigned to a bundle. If

$$
E\to M
$$

is a vector bundle, characteristic classes turn the global twisting of $E$ into cohomology classes on the base $M$:

$$
c_k(E),\quad w_k(E),\quad p_k(E),\quad e(E),\quad \operatorname{ch}(E),\quad \ldots
$$

The key physical point is that a bundle can look trivial in every local patch while still being globally nontrivial. Characteristic classes detect that global twisting. They are the bridge between transition functions, curvature, quantized fluxes, instanton number, index theorems, and anomaly polynomials.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing a bundle, a connection, curvature, invariant polynomials in curvature, closed forms, cohomology classes independent of the connection, characteristic numbers, standard characteristic classes, and QFT uses such as flux, instantons, anomalies, and indices.](/figures/math-toolkit/characteristic-classes-flow.svg)

<figcaption>

Chern–Weil theory converts local curvature into global cohomology classes. Changing the connection changes the differential-form representative by an exact form, so the cohomology class and its integrals over closed cycles remain topological.

</figcaption>
</figure>

The slogan is

$$
\text{curvature polynomials represent topology}.
$$

This is not magic. A connection gives a curvature form $\mathcal F$. Invariant polynomials in $\mathcal F$ produce closed differential forms. Their de Rham cohomology classes do not depend on the connection. With the right normalization, these classes are the real images of integral characteristic classes.

## Prerequisites

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) for transition functions, [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) for the curvature convention

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A,
$$

and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) for the translation between mathematical connection forms and physics gauge potentials.

Read [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) for closed forms modulo exact forms, and [Čech Cohomology Preview](/math-toolkit/topology-cohomology-characteristic-classes/cech-cohomology-preview/) for the patching-data viewpoint.

For spin applications, read [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/). For analytic applications, read [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/).

## Core idea

A vector bundle is locally a product:

$$
E|_{U_i}\simeq U_i\times V.
$$

The global information is in how these local products glue. Characteristic classes assign topological invariants to that gluing in a way that is **natural**: if $f:N\to M$ is a smooth map, then

$$
\operatorname{char}(f^*E)=f^*\operatorname{char}(E).
$$

This naturality is why characteristic classes are portable. You can restrict a gauge bundle to a two-sphere around a monopole, pull it back to a defect worldvolume, or evaluate it on a compactified spacetime, and the characteristic class behaves exactly as it should.

The most important examples are:

| class | bundle type | coefficients | degree | first physics use |
|---|---|---|---|---|
| $c_k(E)$ | complex vector bundle | $\mathbb Z$ | $2k$ | line bundles, gauge flux, instantons |
| $\operatorname{ch}(E)$ | complex vector bundle | $\mathbb Q$ or $\mathbb R$ | even | index theorem, anomalies |
| $w_k(E)$ | real vector bundle | $\mathbb Z_2$ | $k$ | orientation, spin obstruction, mod-2 data |
| $p_k(E)$ | real vector bundle | $\mathbb Z$ | $4k$ | gravitational topology, anomaly polynomials |
| $e(E)$ | oriented real rank-$n$ bundle | $\mathbb Z$ | $n$ | Euler number, zero counting |

Characteristic classes are not extra decorations added after the physics is done. They are often the invariant content of the physics: flux sectors, instanton number, global obstructions, anomaly coefficients, and zero-mode counts.

## Setup and conventions

This page uses the mathematical connection notation

$$
\nabla=d+\mathcal A,
$$

where $\mathcal A$ is a matrix-valued or Lie-algebra-valued one-form, and

$$
\mathcal F=\nabla^2=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

For a unitary connection, $\mathcal A$ and $\mathcal F$ are anti-Hermitian matrices. In the site’s compact-gauge-group physics convention, Hermitian generators $T^a$ are used and

$$
D=d+igA^aT^a,
\qquad
\mathcal A=igA^aT^a,
\qquad
\mathcal F=igF^aT^a.
$$

Chern–Weil formulas are cleanest in terms of $\mathcal F$. Translating to a physics gauge field $A$ can introduce signs and factors of $g$, depending on whether $A$ is normalized as a connection or as a physical field coupled by charge. The invariant statement is the characteristic class, not the sign of a convention-dependent local expression.

When this page says that a differential form represents an integral class, it means the normalization has been chosen so that periods over closed cycles are integers.

## Chern–Weil theory

Let $E\to M$ be a complex vector bundle with connection $\nabla$ and curvature $\mathcal F$. The total Chern class has the de Rham representative

$$
c(E)_{\mathbb R}
=\bigg[\det\left(1+\frac{i}{2\pi}\mathcal F\right)\bigg].
$$

The notation means: expand the determinant as a sum of differential forms of even degree, and take the corresponding de Rham cohomology classes. Thus

$$
c(E)=1+c_1(E)+c_2(E)+\cdots.
$$

The Chern character is represented by

$$
\operatorname{ch}(E)
=\bigg[\operatorname{tr}\exp\left(\frac{i}{2\pi}\mathcal F\right)\bigg].
$$

It expands as

$$
\operatorname{ch}(E)=\operatorname{rank}(E)+c_1(E)+\frac12\left(c_1(E)^2-2c_2(E)\right)+\cdots.
$$

Why are these forms closed? The curvature satisfies the Bianchi identity

$$
D\mathcal F=0,
$$

and invariant polynomials obey a cyclic trace identity. For example,

$$
d\operatorname{tr}(\mathcal F\wedge\mathcal F)
=\operatorname{tr}(D\mathcal F\wedge\mathcal F-\mathcal F\wedge D\mathcal F)=0.
$$

So curvature polynomials give closed forms.

Why are their cohomology classes independent of the chosen connection? If $\mathcal A_t$ is a smooth family of connections, then for an invariant polynomial $P$,

$$
\frac{d}{dt}P(\mathcal F_t)=d(\text{Chern–Simons transgression form}).
$$

Thus changing the connection changes the form representative by an exact form. The de Rham class remains fixed.

This is the precise form of the slogan:

$$
\text{geometry chooses a representative; topology is the cohomology class}.
$$

## First Chern class and flux

For a complex line bundle $L\to M$, the first Chern class

$$
c_1(L)\in H^2(M;\mathbb Z)
$$

is the primary topological invariant. In a geometric normalization where the connection one-form is written so that the curvature is $F_{\mathrm{geom}}$, the de Rham representative is

$$
c_1(L)_{\mathbb R}=\left[\frac{F_{\mathrm{geom}}}{2\pi}\right].
$$

Therefore, for a closed oriented two-cycle $\Sigma$,

$$
\int_\Sigma \frac{F_{\mathrm{geom}}}{2\pi}\in\mathbb Z.
$$

This is flux quantization.

For a Dirac monopole on $S^2$,

$$
\frac{1}{2\pi}\int_{S^2}F_{\mathrm{geom}}=n
$$

is the first Chern number of the line bundle. In the Čech description, the same integer is the winding of the transition function on the equator.

In physics notation, signs and charges depend on whether the covariant derivative is written $D=d+iqA$ or $D=d-iqA$. The integral class does not care which notation you chose; the local formula does.

## Higher Chern classes and instanton number

For a rank-$r$ complex vector bundle,

$$
c_k(E)\in H^{2k}(M;\mathbb Z),
\qquad
0\le k\le r.
$$

The first Chern class measures determinant-line-bundle twisting. For an $SU(N)$ bundle, the determinant is trivial, so

$$
c_1(E)=0.
$$

The next class, $c_2(E)$, is central in four-dimensional gauge theory. On a compact oriented four-manifold $M$, the integer

$$
\int_M c_2(E)
$$

is, up to convention-dependent sign choices, the instanton number of an $SU(N)$ gauge bundle in the associated fundamental representation.

Many physics texts write a normalized topological charge schematically as

$$
k\sim \frac{1}{8\pi^2}\int_M \operatorname{tr}(F\wedge F),
$$

with the trace and sign fixed by the chosen Hermitian or anti-Hermitian convention. The invariant statement is that the properly normalized curvature polynomial represents an integral characteristic class. That integer labels topological sectors in the path integral and appears in theta terms such as

$$
S_\theta=i\theta k
$$

in Euclidean signature.

This is why instanton number is robust. Small changes of the gauge field change the local density by a total derivative; they cannot change the integral unless the field leaves the topological sector.

## Stiefel–Whitney classes and spin obstructions

For a real vector bundle $E\to M$, the Stiefel–Whitney classes are

$$
w_k(E)\in H^k(M;\mathbb Z_2).
$$

They measure mod-2 obstruction data. The first class $w_1(E)$ obstructs orientability:

$$
w_1(E)=0
\quad\Longleftrightarrow\quad
E\text{ is orientable}.
$$

For the tangent bundle $TM$, this says $M$ is orientable when

$$
w_1(TM)=0.
$$

If $M$ is oriented, the second Stiefel–Whitney class obstructs the existence of a spin structure:

$$
w_2(TM)=0
\quad\Longleftrightarrow\quad
M\text{ admits a spin structure}.
$$

This is a genuine QFT constraint. Fermions are not fields on an arbitrary oriented manifold; they require spin, or sometimes spin$^c$ or Pin variants depending on the theory. A local gamma-matrix formula for the Dirac operator is not enough. The relevant bundle must exist globally.

Stiefel–Whitney classes also appear in global anomalies, discrete theta terms, generalized symmetry backgrounds, and topological phases. Because they have $\mathbb Z_2$ coefficients, they are invisible to ordinary de Rham cohomology.

## Pontryagin classes, Euler class, and gravitational terms

For a real vector bundle $E$, the Pontryagin classes are

$$
p_k(E)\in H^{4k}(M;\mathbb Z).
$$

They are closely related to Chern classes of the complexification $E\otimes\mathbb C$. In physics, Pontryagin classes often appear for the tangent bundle $TM$ and enter gravitational theta terms, anomaly polynomials, and index theorems.

The first Pontryagin class has a de Rham representative built from curvature two-forms. With convention-dependent normalization,

$$
p_1(E)_{\mathbb R}\sim \left[\operatorname{tr}(\mathcal R\wedge\mathcal R)\right],
$$

where $\mathcal R$ is the curvature of a connection on $E$, such as the Levi-Civita connection on $TM$.

If $E$ is an oriented real rank-$n$ bundle, the Euler class is

$$
e(E)\in H^n(M;\mathbb Z).
$$

For the tangent bundle of a compact oriented $n$-manifold, the Euler number is

$$
\int_M e(TM)=\chi(M),
$$

where $\chi(M)$ is the Euler characteristic.

This fits a useful pattern:

$$
\text{Chern classes: complex bundles},
\qquad
\text{Stiefel–Whitney classes: real mod-2 data},
$$

$$
\text{Pontryagin classes: real bundles in degrees }4k,
\qquad
\text{Euler class: oriented real bundles in top degree}.
$$

## Characteristic numbers

A characteristic class becomes a number when integrated over a cycle of matching dimension. If $M$ is closed, oriented, and $\dim M=d$, then a degree-$d$ characteristic class $\alpha$ gives

$$
\int_M \alpha.
$$

Examples include

$$
\int_{S^2}c_1(L),
\qquad
\int_{M^4}c_2(E),
\qquad
\int_{M^4}p_1(TM),
\qquad
\int_M e(TM).
$$

With integral normalization, these are topological numbers. They cannot change under smooth deformations of the connection or metric.

In QFT, such numbers often appear in exponentials:

$$
\exp\left(i\theta\int_M \alpha\right).
$$

Quantization of $\int_M\alpha$ controls periodicity in $\theta$. If the normalization is wrong, the periodicity is wrong. That is not a cosmetic error; it changes the quantum theory.

## Index-theorem package

Characteristic classes become especially powerful in index theorems. A schematic Dirac index formula says

$$
\operatorname{index}(D_E)=\int_M \widehat A(TM)\operatorname{ch}(E),
$$

where $D_E$ is a Dirac operator coupled to a bundle $E$, $\widehat A(TM)$ is a characteristic class built from Pontryagin classes of the tangent bundle, and $\operatorname{ch}(E)$ is the Chern character of the gauge bundle.

The left-hand side is analytic:

$$
\operatorname{index}(D_E)=\dim\ker D_E^+-\dim\ker D_E^-.
$$

The right-hand side is topological. This is why characteristic classes organize chiral zero modes, instanton zero modes, anomaly polynomials, determinant phases, and spectral flow.

The index theorem is not proved on this page, but the structure should already feel inevitable: curvature supplies closed characteristic forms, cohomology classes make them topological, and integration gives numbers that can equal robust analytic counts.

## Anomaly polynomials and descent

In even-dimensional QFT, perturbative anomalies are often encoded by an anomaly polynomial

$$
I_{d+2}
$$

in two degrees higher than spacetime. This polynomial is built from characteristic classes of background gauge bundles and the tangent bundle. Schematically,

$$
I_{d+2}=\left[\widehat A(TM)\operatorname{ch}(E)\right]_{d+2}
$$

for a chiral fermion system, with the appropriate representation and normalization.

The local anomaly is obtained by a descent procedure. A characteristic form is closed,

$$
dI_{d+2}=0,
$$

and locally one writes

$$
I_{d+2}=dI_{d+1}^{(0)}.
$$

Under a gauge transformation,

$$
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

The $d$-form $I_d^{(1)}$ gives the local anomaly. This is another place where the exact-form ambiguity is not a nuisance; it is the mechanism.

Global anomalies and torsion effects require more refined tools than ordinary characteristic forms, but characteristic classes remain the starting language.

## What characteristic classes measure

A characteristic class can be used in several closely related ways:

1. It can **detect nontrivial bundles**. If a characteristic class is nonzero, the bundle is not globally trivial.
2. It can **classify in favorable cases**. For line bundles, $c_1$ classifies complex line bundles over reasonable spaces.
3. It can **obstruct structures**. The class $w_2(TM)$ obstructs spin structures.
4. It can **normalize topological terms**. Integral classes control theta-angle periodicity.
5. It can **count zeros or zero modes**. Euler classes and index-theorem combinations turn topology into counts.
6. It can **organize anomalies**. Anomaly polynomials are built from characteristic classes.

The word “detect” is deliberately weaker than “classify.” Characteristic classes do not always completely classify bundles. Different bundles can have the same characteristic classes, especially when torsion or unstable information matters.

## Common pitfalls

**Confusing the class with a representative.** The form $\operatorname{tr}(\mathcal F\wedge\mathcal F)$ is a representative. The characteristic class is its cohomology class with the correct normalization.

**Forgetting integral normalization.** A de Rham class only gives real periods. Flux quantization and theta periodicity require knowing the integral class that the form represents.

**Assuming nonzero curvature means nontrivial topology.** A trivial bundle can have nonzero curvature. Nontrivial topology is detected by characteristic classes and their periods, not by the pointwise value of curvature.

**Assuming zero curvature means trivial topology.** A flat bundle can have nontrivial holonomy. Characteristic forms may vanish in de Rham cohomology while discrete or torsion data remain.

**Treating all traces as equivalent.** Trace normalization matters. The fundamental trace, adjoint trace, and representation-dependent traces differ by group-theoretic factors. This affects instanton number and anomaly coefficients.

**Mixing Hermitian and anti-Hermitian conventions.** Chern–Weil formulas are clean in anti-Hermitian mathematical notation $\mathcal F$. Physics notation with Hermitian generators introduces signs and couplings. Translate the whole convention, not just one formula.

**Thinking characteristic classes fully classify every bundle.** They often do not. They are powerful invariants, not a universal barcode.

**Using de Rham representatives for mod-2 classes.** Stiefel–Whitney classes live in $\mathbb Z_2$ cohomology. They cannot be represented by ordinary real differential forms.

## Exercises

### Exercise 1: Closedness of the second Chern–Weil form

Let $\mathcal F$ be the curvature of a connection and assume the Bianchi identity

$$
D\mathcal F=0.
$$

Show that

$$
d\operatorname{tr}(\mathcal F\wedge\mathcal F)=0.
$$

<details><summary><strong>Solution</strong></summary>

For a trace of an adjoint-valued form, the exterior derivative can be replaced by the covariant derivative inside the trace because commutator terms drop out cyclically:

$$
d\operatorname{tr}(\mathcal F\wedge\mathcal F)
=\operatorname{tr}\left(D(\mathcal F\wedge\mathcal F)\right).
$$

Using the graded Leibniz rule and the fact that $\mathcal F$ has degree $2$,

$$
D(\mathcal F\wedge\mathcal F)
=D\mathcal F\wedge\mathcal F+\mathcal F\wedge D\mathcal F.
$$

By the Bianchi identity $D\mathcal F=0$, both terms vanish. Therefore

$$
d\operatorname{tr}(\mathcal F\wedge\mathcal F)=0.
$$

</details>

### Exercise 2: Connection independence up to an exact form

Let

$$
\mathcal A_t=\mathcal A_0+t\alpha,
\qquad
0\le t\le1,
$$

be a family of connections with curvature $\mathcal F_t$. Show that

$$
\frac{d}{dt}\operatorname{tr}(\mathcal F_t\wedge\mathcal F_t)
=2d\operatorname{tr}(\alpha\wedge\mathcal F_t).
$$

<details><summary><strong>Solution</strong></summary>

The variation of curvature is

$$
\frac{d\mathcal F_t}{dt}=D_t\alpha,
$$

where $D_t$ is the covariant derivative defined by $\mathcal A_t$. Therefore

$$
\frac{d}{dt}\operatorname{tr}(\mathcal F_t\wedge\mathcal F_t)
=2\operatorname{tr}(D_t\alpha\wedge\mathcal F_t).
$$

Now use

$$
d\operatorname{tr}(\alpha\wedge\mathcal F_t)
=\operatorname{tr}(D_t\alpha\wedge\mathcal F_t)-\operatorname{tr}(\alpha\wedge D_t\mathcal F_t).
$$

The second term vanishes by the Bianchi identity. Hence

$$
\frac{d}{dt}\operatorname{tr}(\mathcal F_t\wedge\mathcal F_t)
=2d\operatorname{tr}(\alpha\wedge\mathcal F_t).
$$

This is the simplest transgression formula behind Chern–Simons forms.

</details>

### Exercise 3: First Chern class of a tensor product

Let $L_1$ and $L_2$ be complex line bundles with curvatures $F_1$ and $F_2$ in a normalization where

$$
c_1(L_a)=\left[\frac{F_a}{2\pi}\right].
$$

Show that

$$
c_1(L_1\otimes L_2)=c_1(L_1)+c_1(L_2).
$$

<details><summary><strong>Solution</strong></summary>

The tensor product connection has curvature

$$
F_{12}=F_1+F_2.
$$

Therefore

$$
c_1(L_1\otimes L_2)
=\left[\frac{F_{12}}{2\pi}\right]
=\left[\frac{F_1+F_2}{2\pi}\right]
=\left[\frac{F_1}{2\pi}\right]+\left[\frac{F_2}{2\pi}\right].
$$

Thus

$$
c_1(L_1\otimes L_2)=c_1(L_1)+c_1(L_2).
$$

</details>

### Exercise 4: Euler class and zeros of a vector field

For an oriented rank-$n$ real vector bundle $E\to M^n$, the Euler class $e(E)$ is Poincaré dual to the zero locus of a generic section. Explain why, for $E=TM$ on a compact oriented manifold, this is compatible with

$$
\int_M e(TM)=\chi(M).
$$

<details><summary><strong>Solution</strong></summary>

A generic vector field on $M$ is a generic section of $TM$. Its isolated zeros carry signs determined by the local orientation of the derivative map. The Euler class is Poincaré dual to the signed zero set, so

$$
\int_M e(TM)
$$

counts the signed zeros of a generic vector field.

The Poincaré–Hopf theorem says that this signed count equals the Euler characteristic:

$$
\sum_{\text{zeros}}\operatorname{index}(X)=\chi(M).
$$

Thus

$$
\int_M e(TM)=\chi(M).
$$

</details>

## Relations to other pages

This page uses [Čech Cohomology Preview](/math-toolkit/topology-cohomology-characteristic-classes/cech-cohomology-preview/) for the transition-function viewpoint and [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) for curvature representatives as closed forms modulo exact forms.

The necessary geometry is in [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/), [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/), [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/), and [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/).

The next natural pages are Chern Classes, Stiefel–Whitney Classes, Pontryagin Classes, Index Theorems, and Cobordism Preview. Those pages will expand the individual families of characteristic classes and their QFT applications.

## Research status

The standard characteristic classes and Chern–Weil representatives described here are established. The active QFT issues are usually not about whether these classes exist, but about which refinement is required in a given quantum theory: integral versus real classes, torsion, differential cohomology, equivariant backgrounds, global forms of gauge groups, spin or Pin structures, singular defects, generalized symmetries, and cobordism-valued anomalies.

The safest habit is to treat a curvature polynomial as the local shadow of a global object. Before using it in a quantum path integral, check the integral normalization, the allowed bundles, the trace convention, and the background structure of spacetime.

## References

- J. Milnor and J. Stasheff, *Characteristic Classes*. Classic mathematical reference for Stiefel–Whitney, Chern, Pontryagin, and Euler classes.
- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*. Clear treatment of Chern–Weil representatives, de Rham methods, and characteristic classes.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented reference for characteristic classes, monopoles, instantons, spin structures, and index theory.
- T. Frankel, *The Geometry of Physics*. Geometric reference for bundles, curvature, Chern classes, gauge fields, and Dirac operators.
- T. Eguchi, P. B. Gilkey, and A. J. Hanson, “Gravitation, Gauge Theories and Differential Geometry.” Classic review connecting characteristic classes, index theory, gauge fields, and gravitational backgrounds.
- M. F. Atiyah and I. M. Singer, papers on the index theorem. The original source of the index-theoretic bridge between characteristic classes and analytic zero-mode counts.
- S. Coleman, *Aspects of Symmetry*. Physics reference for topology in field theory, solitons, monopoles, and instantons.
- A. M. Polyakov, *Gauge Fields and Strings*. Classic reference for gauge topology, instantons, Wilson loops, and nonperturbative uses of characteristic data.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for gauge theory, anomalies, instantons, and translating characteristic-class statements into QFT calculations.

## Version history

- **2026-06-25:** Initial polished draft. Explained characteristic classes, Chern–Weil representatives, first Chern class and flux, higher Chern classes and instanton number, Stiefel–Whitney obstructions, Pontryagin and Euler classes, characteristic numbers, index-theorem packages, anomaly polynomials, common pitfalls, and exercises.
