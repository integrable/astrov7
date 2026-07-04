---
title: "Cobordism Preview"
description: "Introduces bordism and cobordism as the global topological language behind boundaries, anomaly inflow, invertible phases, and modern QFT classification problems."
sidebar:
  label: "Cobordism Preview"
  order: 12
level: Research
status: "Polished draft"
source: "Standard references on bordism and QFT, including Thom, Milnor–Stasheff, Stong, Freed, Hopkins, Kapustin, Thorngren, and physics treatments of anomalies, invertible field theories, and SPT phases."
topics:
  - bordism
  - cobordism
  - tangential structures
  - anomaly inflow
  - invertible field theories
  - SPT phases
  - global anomalies
  - characteristic numbers
  - eta invariants
canonicalTopics:
  - bordism
  - cobordism
  - tangential-structure
  - anomaly-inflow
  - invertible-field-theory
  - symmetry-protected-topological-phase
  - global-anomaly
  - characteristic-number
  - eta-invariant
researchStatus:
  established:
    - "Bordism groups classify manifolds with chosen structures up to being boundaries, and their dual data organizes many topological actions, global anomalies, and invertible phases."
  active:
    - "Modern applications require refined structures: reflection positivity, unitarity, noninvertible symmetries, higher symmetries, defects, differential cohomology, generalized cohomology, and precise symmetry-extension data."
---

## Summary

Cobordism is the mathematics of asking when a closed space is a boundary. In QFT this question is not decorative. Boundaries control anomaly inflow, global anomalies, topological terms, domain walls, invertible phases, and the distinction between local curvature formulas and genuinely global phases.

The simplest version says that two closed $d$-manifolds $M_0$ and $M_1$ are bordant if there is a compact $(d+1)$-manifold $W$ whose boundary is

$$
\partial W=M_1\sqcup(-M_0).
$$

The minus sign means reversed orientation. If the manifolds carry extra structure, such as an orientation, spin structure, gauge bundle, or map to a classifying space $BG$, the bordism relation must preserve that structure.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing closed manifolds with a tangential structure passing to bordism classes, then to characteristic numbers, eta invariants, topological actions, invertible field theories, SPT phases, and anomaly inflow.](/figures/math-toolkit/cobordism-qft-dictionary.svg)

<figcaption>

Cobordism turns the question “what topological data can a QFT phase depend on?” into the question “which closed manifolds with the relevant background structures are nontrivial modulo boundaries?” Characteristic numbers detect many free parts; eta invariants and related global data detect torsion phases.

</figcaption>
</figure>

The slogan is

$$
\text{topological phase} \quad = \quad \text{a boundary-insensitive rule for closed backgrounds}.
$$

That slogan needs qualifiers. Some QFT terms are local and metric-dependent, not bordism invariants. Some global phases depend on torsion data invisible to differential forms. Some classifications require stable homotopy theory rather than a naive list of characteristic numbers. This page is a map, not a substitute for the machinery.

## Prerequisites

Read [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) for the idea that continuous deformations can carry discrete information, [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) for cycles and boundaries, and [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) for closed forms modulo exact forms.

For the characteristic-class side, read [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/), [Chern Classes](/math-toolkit/topology-cohomology-characteristic-classes/chern-classes/), [Stiefel–Whitney Classes](/math-toolkit/topology-cohomology-characteristic-classes/stiefel-whitney-classes/), and [Pontryagin Classes](/math-toolkit/topology-cohomology-characteristic-classes/pontryagin-classes/). For the analytic bridge to fermions and anomalies, read [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) and [Index Theorems](/math-toolkit/topology-cohomology-characteristic-classes/index-theorems/).

## Bordism versus cobordism

Mathematicians often distinguish **bordism** from **cobordism**.

Bordism is the equivalence relation on manifolds: $M_0$ and $M_1$ are bordant if their difference is the boundary of a higher-dimensional manifold. The resulting group is usually written

$$
\Omega_d^\xi(X),
$$

where $d$ is the dimension, $\xi$ encodes the allowed tangential structure, and $X$ is an optional target space that records background fields.

Cobordism is the dual generalized cohomology theory. In much of the physics literature, however, “cobordism group” is used informally for the bordism group $\Omega_d^\xi(X)$. This abuse is common enough that a reader must recognize both languages. We will use **bordism group** for $\Omega_d^\xi(X)$ and **cobordism classification** for the broader physics program that uses these groups to organize topological phases and anomalies.

The notation $\xi$ is deliberately schematic. Common choices include:

| Structure | What it remembers | Typical physics use |
|---|---|---|
| $SO$ | orientation | bosonic oriented Euclidean QFT, Chern and Pontryagin numbers |
| $Spin$ | spin structure | fermions without time reversal |
| $Pin^+$ or $Pin^-$ | unoriented spacetime with different reflections | time-reversal and reflection-protected fermionic systems |
| $Spin^c$ | spinors coupled to a background $U(1)$ bundle | charged fermions on manifolds that need not be spin |
| maps to $BG$ | background gauge fields for $G$ | SPT phases and ’t Hooft anomalies with global symmetry $G$ |

There are many refinements: spin-charge relations, higher-form backgrounds, crystalline symmetries, flavor bundles, boundaries, defects, and differential refinements. The table is only the first rung of the ladder.

## The bordism relation

Let $M$ be a closed $d$-manifold. “Closed” means compact and without boundary. If $M=\partial W$ for some compact $(d+1)$-manifold $W$, then $M$ is null-bordant.

For oriented manifolds the boundary carries the induced orientation. The oriented boundary of an interval is

$$
\partial[0,1]=\{1\}\sqcup(-\{0\}),
$$

and the oriented boundary of a cylinder $\Sigma\times[0,1]$ is

$$
\partial(\Sigma\times[0,1])
=\Sigma\times\{1\}\sqcup(-\Sigma\times\{0\}).
$$

This is the geometric reason the bordism relation compares $M_1$ with $M_0$ using

$$
\partial W=M_1\sqcup(-M_0).
$$

The set of bordism classes becomes an abelian group under disjoint union:

$$
[M]+[N]=[M\sqcup N].
$$

The inverse is orientation reversal when orientation is part of the structure:

$$
-[M]=[-M].
$$

The identity element is the empty manifold, or equivalently any null-bordant manifold.

A QFT reader should notice the resemblance to conservation laws. Bordism identifies configurations that differ by a process in one higher dimension. In anomaly inflow, that higher-dimensional process is not metaphorical; the anomalous $d$-dimensional theory can live on the boundary of a $(d+1)$-dimensional invertible theory.

## Background fields and maps to classifying spaces

A global symmetry background is often encoded by a bundle. Principal $G$-bundles over $M$ are classified, up to suitable equivalence, by maps

$$
f:M\to BG,
$$

where $BG$ is the classifying space of $G$.

So the bordism group relevant to a bosonic theory with ordinary internal symmetry $G$ is not just $\Omega_d^{SO}$, but

$$
\Omega_d^{SO}(BG).
$$

For fermionic theories it is often

$$
\Omega_d^{Spin}(BG),
$$

or a variant involving $Spin^c$, $Pin^\pm$, or a quotient that ties fermion parity to part of the symmetry group.

This notation has a simple physical meaning: two backgrounds $(M_0,f_0)$ and $(M_1,f_1)$ are equivalent if there is a bulk background $(W,F)$ whose boundary restricts to them. If a proposed topological partition function assigns different phases to bordant backgrounds, it is not a well-defined bordism invariant.

For higher-form symmetries the background field is not always a map to an ordinary $BG$ in a naive sense. It may be a higher bundle, a cocycle, a differential cocycle, or data in a generalized cohomology theory. But the same organizing idea survives: specify the allowed background structures, then ask which closed backgrounds are nontrivial modulo boundaries.

## From bordism groups to topological actions

A topological action on closed $d$-manifolds should assign a phase

$$
Z_{\mathrm{top}}(M)\in U(1)
$$

that is invariant under allowed equivalences. If it is multiplicative under disjoint union,

$$
Z_{\mathrm{top}}(M\sqcup N)=Z_{\mathrm{top}}(M)Z_{\mathrm{top}}(N),
$$

then it behaves like a character of the bordism group:

$$
Z_{\mathrm{top}}:\Omega_d^\xi(X)\to U(1).
$$

This is the most elementary way cobordism enters the classification of invertible topological phases. It says: once the allowed backgrounds are fixed, a purely topological invertible partition function is a bordism invariant.

For the free part of a bordism group, such phases can often be written using integrals of characteristic-class densities. For example, on a closed oriented four-manifold one encounters integrals such as

$$
\int_M p_1(TM),
$$

or combinations related to the signature. For a complex vector bundle, Chern numbers come from integrals such as

$$
\int_M c_1(E)^2,
\qquad
\int_M c_2(E).
$$

These are characteristic numbers. They are stable under bordism, and they detect much of the free part of many bordism groups.

But characteristic forms with real coefficients do **not** see everything. Torsion phases are often invisible in de Rham cohomology. Fermionic phases and global anomalies can require eta invariants, Arf invariants, mod-two indices, quadratic refinements, and other global data. This is where cobordism becomes more than “integrate a polynomial in curvature.” Tiny sentence, large iceberg.

## Boundaries and anomaly inflow

A $d$-dimensional theory with an anomaly may fail to have a well-defined partition function as a number on a closed $d$-manifold with background fields. Instead, it transforms by a phase under large gauge transformations, diffeomorphisms, or changes of auxiliary choices.

The modern viewpoint packages this failure as an invertible field theory in one higher dimension. If the anomalous theory lives on $M=\partial W$, the combined system has the schematic form

$$
Z_{\mathrm{bulk}}(W)\,Z_{\mathrm{boundary}}(M).
$$

The variation of the bulk factor cancels the anomalous variation of the boundary factor.

When the anomaly is perturbative, it is often described by a local anomaly polynomial. When the anomaly is global, it may be detected only by evaluating a bordism invariant on a closed $(d+1)$-dimensional background. This distinction matters in QFT because two theories can have the same local anomaly polynomial but differ by a torsion global anomaly.

A common example is the difference between a differential-form expression and an exponentiated eta invariant. The former is local and sees curvature. The latter is spectral and global. Index theory explains why they are related, but cobordism tells you when the remaining global phase can still be nontrivial.

## Characteristic numbers as bordism tests

Characteristic numbers give practical bordism invariants. For an oriented $4k$-manifold, Pontryagin numbers are integrals of products of Pontryagin classes whose total degree is $4k$:

$$
\int_M p_{i_1}(TM)\cdots p_{i_r}(TM),
\qquad
4(i_1+\cdots+i_r)=4k.
$$

For complex bundles, Chern numbers are similar:

$$
\int_M c_{i_1}(E)\cdots c_{i_r}(E).
$$

For real bundles and unoriented manifolds, Stiefel–Whitney numbers are mod-two invariants:

$$
\int_M w_{i_1}(E)\cdots w_{i_r}(E)
\in\mathbb Z_2.
$$

If $M=\partial W$ and the relevant classes extend over $W$, these numbers vanish in the appropriate sense. This follows from Stokes-type reasoning and naturality: characteristic classes of the boundary are restrictions of bulk classes, and top-degree evaluations become boundary evaluations of bulk data.

The warning is that characteristic numbers are tests, not always complete diagnostics in the form a physicist first writes down. The complete bordism classification can involve subtle torsion and stable homotopy information.

## Simple examples

Every closed oriented one-manifold is a disjoint union of circles, and each oriented circle bounds a disk. Therefore

$$
\Omega_1^{SO}=0.
$$

Every closed oriented two-manifold is an oriented boundary as well, so

$$
\Omega_2^{SO}=0.
$$

In four dimensions, oriented bordism becomes nontrivial:

$$
\Omega_4^{SO}\cong\mathbb Z.
$$

A generator can be detected by the signature, equivalently by the Pontryagin number through the Hirzebruch signature theorem,

$$
\sigma(M)=\frac{1}{3}\int_M p_1(TM).
$$

For spin manifolds, low-dimensional torsion already appears. The circle has two spin structures; one bounds a disk and one does not. This gives the familiar

$$
\Omega_1^{Spin}\cong\mathbb Z_2.
$$

In two spin dimensions, the Arf invariant detects

$$
\Omega_2^{Spin}\cong\mathbb Z_2.
$$

These examples are small but instructive. Bosonic oriented phases in very low dimensions can be trivial from the bordism viewpoint, while fermionic phases can already remember spin structures. That is why spin and pin data are not bookkeeping annoyances; they change the answer.

## What classification means

A phrase like “classified by cobordism” can mean several nearby but distinct claims.

It may mean that topological terms are homomorphisms out of a bordism group:

$$
\operatorname{Hom}(\Omega_d^\xi(X),U(1)).
$$

It may mean that deformation classes of invertible topological field theories are controlled by maps from a Thom spectrum. This statement is more refined and remembers locality, dimensional hierarchy, and sometimes reflection positivity.

It may mean that possible ’t Hooft anomalies of a $d$-dimensional theory are captured by invertible theories in $(d+1)$ dimensions.

It may mean that SPT phases in $d$ spacetime dimensions, or $d-1$ spatial dimensions, are organized by bordism data for the symmetry and tangential structure.

These statements are related, but not identical. The safest habit is to specify the dimension, the allowed manifolds, the symmetry backgrounds, whether the theory is bosonic or fermionic, whether time reversal or reflection is present, whether one imposes unitarity or reflection positivity, and whether one is classifying actions, partition functions, anomalies, or full extended field theories.

## How this appears in QFT calculations

Cobordism usually enters through one of five doors.

First, a topological term is only well-defined modulo $2\pi$ because changing a filling $W$ should not change the exponentiated action. The obstruction to this independence is a bordism invariant.

Second, a fermion determinant has a phase. Perturbatively this phase is described by anomaly polynomials; globally it may be controlled by eta invariants and bordism classes.

Third, an anomalous theory can be consistently defined as the boundary of an invertible bulk theory. The bulk phase is evaluated on a $(d+1)$-dimensional background.

Fourth, SPT phases and some topological response actions are organized by the same data: spacetime dimension, symmetry backgrounds, and tangential structure.

Fifth, defects and domain walls often carry lower-dimensional anomalies. Their inflow terms are again bordism-sensitive, now for manifolds with singular strata or additional defect data.

So cobordism is not a new replacement for Lagrangians. It is a global consistency layer for the parts of QFT that Lagrangians can hide.

## Common pitfalls

**Bordism is not homology.** Homology studies cycles inside a fixed space modulo boundaries inside that space. Bordism studies manifolds, possibly mapped to a space, modulo being boundaries of higher-dimensional manifolds with compatible structure.

**Cobordism is not just “put a boundary on it.”** The boundary must carry the correct induced structure. A spin manifold must bound as a spin manifold, not merely as an oriented manifold.

**Characteristic classes do not see all global phases.** De Rham characteristic forms miss torsion. Many fermionic and time-reversal-sensitive phases require mod-two indices, eta invariants, Arf invariants, or pin structures.

**A local anomaly polynomial is not the full anomaly.** It captures perturbative information. Global anomalies can remain after the local polynomial vanishes.

**The word “dimension” can shift by one.** A $d$-dimensional anomalous boundary theory is often classified by a $(d+1)$-dimensional invertible bulk. Condensed matter authors may count spatial dimension, while relativistic QFT authors often count spacetime dimension.

**The symmetry data matter as much as the manifold.** Changing $SO$ to $Spin$, adding a $G$-bundle, or changing time reversal from $Pin^+$ to $Pin^-$ can change the group completely.

**Not every invertible phase is captured by a naive homomorphism.** Fully local, extended, reflection-positive field theories require a more refined classification. The homomorphism picture is the useful first approximation, not the final theorem.

## Exercises

### Exercise 1: Oriented circles are null-bordant

Show that every closed oriented one-manifold is null-bordant.

<details><summary><strong>Solution</strong></summary>

A closed one-manifold is a finite disjoint union of circles. Each oriented circle is the boundary of an oriented disk. If the orientation of the boundary does not match the chosen orientation of the circle, reverse the orientation of the disk. The disjoint union of the corresponding disks is an oriented two-manifold whose boundary is the original one-manifold. Hence every closed oriented one-manifold is null-bordant, and $\Omega_1^{SO}=0$.

</details>

### Exercise 2: Why spin structure changes the answer

The circle has two spin structures. Explain why this makes $\Omega_1^{Spin}$ more subtle than $\Omega_1^{SO}$.

<details><summary><strong>Solution</strong></summary>

As an oriented manifold, $S^1$ bounds the disk $D^2$. But a spin bordism must extend the spin structure over the bounding disk. Of the two spin structures on $S^1$, only one extends over $D^2$. The other is nonbounding and defines a nontrivial class. Thus orientation alone gives no invariant in one dimension, while spin structure leaves a $\mathbb Z_2$ distinction.

</details>

### Exercise 3: Filling independence

Suppose a proposed topological phase in $d$ dimensions is defined by choosing a filling $W$ of $M$ and setting

$$
Z(M)=\exp\left(2\pi i\int_W I_{d+1}\right).
$$

What condition is needed for $Z(M)$ to be independent of the filling?

<details><summary><strong>Solution</strong></summary>

If $W$ and $W'$ are two fillings of $M$, gluing $W$ to $-W'$ along $M$ gives a closed $(d+1)$-manifold

$$
Y=W\cup_M(-W').
$$

The two choices give the same phase if

$$
\exp\left(2\pi i\int_Y I_{d+1}\right)=1
$$

for every closed allowed background $Y$. Equivalently, the integral over closed backgrounds must be integral. More generally, the exponentiated bulk rule must be trivial on closed backgrounds that can appear by changing fillings, with all relevant tangential and symmetry structures included.

</details>

## References

- R. Thom, foundational work on bordism and cobordism theory.
- J. Milnor and J. Stasheff, *Characteristic Classes*. A standard entry point for characteristic classes and their relation to cobordism.
- R. Stong, *Notes on Cobordism Theory*. A classic mathematical reference for computations and structures.
- D. Freed, *Anomalies and Invertible Field Theories*. A modern geometric account of anomalies as invertible field theories.
- D. Freed and M. Hopkins, *Reflection Positivity and Invertible Topological Phases*. A central reference for the refined classification of invertible phases using Thom spectra and reflection positivity.
- A. Kapustin, *Symmetry Protected Topological Phases, Anomalies, and Cobordisms: Beyond Group Cohomology*. A physics-oriented bridge between SPT phases, anomalies, and cobordism.
- A. Kapustin, R. Thorngren, A. Turzillo, and Z. Wang, *Fermionic Symmetry Protected Topological Phases and Cobordisms*. A useful source for fermionic examples and low-dimensional checks.
- M. Nakahara, *Geometry, Topology and Physics*. Useful background on homotopy, homology, characteristic classes, monopoles, instantons, and related physics.
- T. Frankel, *The Geometry of Physics*. Useful for differential forms, integration, characteristic classes, gauge fields, and geometric intuition.

## Version history

- **2026-06-25:** Initial polished draft. Introduced bordism and cobordism as the global topology language behind boundaries, anomaly inflow, invertible phases, SPT classifications, characteristic numbers, and global anomalies.
