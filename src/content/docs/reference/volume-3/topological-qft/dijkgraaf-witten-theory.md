---
title: "Dijkgraaf–Witten Theory"
description: "Introduces Dijkgraaf–Witten theory as finite-group topological gauge theory, including flat bundles, cocycle actions, Wilson and flux defects, twisted sectors, boundaries, and relation to BF theory and SymTFT."
sidebar:
  label: "Dijkgraaf–Witten Theory"
  order: 6
level: Advanced
status: "Polished draft"
source: "Dijkgraaf–Witten; Freed–Quinn; Turaev–Viro; Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; Nakahara; Altland–Simons."
topics:
  - Dijkgraaf-Witten theory
  - finite gauge theory
  - group cohomology
  - twisted gauge theory
  - orbifolds
  - topological order
canonicalTopics:
  - dijkgraaf-witten-theory
  - finite-gauge-theory
  - group-cohomology-action
  - twisted-sector
  - discrete-topological-gauge-theory
researchStatus:
  established:
    - "Dijkgraaf–Witten theory is the standard finite-group TQFT: a path integral over flat finite-group gauge fields, optionally weighted by a group-cohomology cocycle."
    - "In low dimensions it gives a precise laboratory for orbifolds, discrete gauge theory, topological order, twisted sectors, boundaries, and finite-symmetry gauging."
  active:
    - "Modern uses include SymTFTs, non-invertible symmetries, generalized gauging, higher-group finite gauge theories, lattice topological phases, and categorical boundary/defect constructions."
---

## Summary

**Dijkgraaf–Witten theory** is topological gauge theory for a finite group $G$. Unlike Yang–Mills theory, it has no Lie-algebra-valued gauge boson, no curvature two-form in the usual differential-geometric sense, and no local propagating modes. A gauge field is instead a flat finite-group bundle, or equivalently a locally constant $G$-connection.

On a closed $d$-dimensional spacetime manifold $M$, the untwisted theory is roughly

$$
Z_G(M)=
\sum_{\text{flat }G\text{-bundles on }M}
\frac{1}{|\operatorname{Aut}(P)|},
$$

with normalization conventions depending on the precise extended-TQFT setup. A **twisted** Dijkgraaf–Witten theory weights each flat bundle by a topological action determined by a group-cohomology class

$$
\omega\in H^d(BG,U(1)),
$$

where $d$ is the spacetime dimension.

The shortest slogan is

$$
\text{Dijkgraaf–Witten theory}=
\text{finite-group gauge theory with optional cocycle action}.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Dijkgraaf-Witten theory diagram showing a triangulated manifold with finite group labels on edges, flatness around faces, and cocycle weights on higher simplices.](/figures/symmetry-anomalies-topology/dijkgraaf-witten-simplicial.svg)

<figcaption>

A lattice presentation of Dijkgraaf–Witten theory assigns group elements to edges, imposes flatness around faces, and multiplies cocycle weights over top-dimensional simplices. The result is independent of triangulation when the cocycle condition holds.

</figcaption>
</figure>

Dijkgraaf–Witten theory is one of the cleanest bridges between lattice gauge theory, group cohomology, orbifolds, finite symmetry gauging, topological phases, and SymTFT.

## Prerequisites

You should know [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/), [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/), and the finite-symmetry part of [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/). It is helpful to know what a principal bundle, holonomy, group cohomology, triangulation, and flat connection are, but this page explains the physical meaning of each ingredient.

The notation $H^d(BG,U(1))$ is the cohomology of the classifying space $BG$. For finite groups, physicists often write this as group cohomology $H^d(G,U(1))$. The two notations are closely related in this context; the $BG$ notation makes the topological-gauge-field interpretation more visible.

:::note[Dimension convention]
This page uses $d$ for spacetime dimension. A bosonic $d$-dimensional Dijkgraaf–Witten action is labeled by a class in $H^d(BG,U(1))$. A $d$-dimensional boundary anomaly or SPT inflow problem often involves a one-higher-dimensional class. Keep this shift in mind when comparing to SPT classification formulas.
:::

## Core idea

Ordinary gauge theory for a Lie group begins with a connection $A$ and curvature $F$. Dijkgraaf–Witten theory begins with a finite group $G$. Since $G$ is finite, there is no infinitesimal connection and no local curvature field strength. Instead, the gauge field records finite holonomies.

On a triangulated manifold, one assigns a group element $g_{ij}\in G$ to each oriented edge $ij$. Reversing the edge inverts the group element:

$$
g_{ji}=g_{ij}^{-1}.
$$

Flatness around a triangle $ijk$ is

$$
g_{ij}g_{jk}g_{ki}=1.
$$

Gauge transformations attach group elements $h_i\in G$ to vertices and act by

$$
g_{ij}\mapsto h_i g_{ij} h_j^{-1}.
$$

Thus a field configuration is a flat finite-group connection modulo gauge equivalence. In continuum language, this is a map

$$
M\to BG,
$$

or a principal $G$-bundle with flat connection.

The untwisted theory counts such configurations. The twisted theory multiplies each configuration by a phase built from a cocycle.

## Untwisted finite gauge theory

The untwisted Dijkgraaf–Witten theory sums over flat $G$-bundles. On a connected closed manifold, a flat $G$-bundle is equivalent to a homomorphism

$$
\rho:\pi_1(M)\to G
$$

modulo conjugation by $G$. Thus the partition function can be described as a weighted count of homomorphisms:

$$
Z_G(M)
\sim
\frac{1}{|G|}\#\operatorname{Hom}(\pi_1(M),G)
$$

for many common normalization conventions on connected closed manifolds.

A more invariant expression is the groupoid cardinality of the groupoid of flat $G$-bundles:

$$
Z_G(M)=\sum_{[P]}\frac{1}{|\operatorname{Aut}(P)|}.
$$

This formula is better than a naive count because gauge fields can have automorphisms. In path-integral language, it is the finite-group analogue of dividing by the volume of the gauge group.

The result depends only on the topology of $M$, not on a metric. This is exactly what a TQFT should do.

## Twisted theory and cocycle actions

A twisted Dijkgraaf–Witten theory includes a topological action. Choose

$$
[\omega]\in H^d(BG,U(1)).
$$

Given a flat $G$-bundle $P$ on a closed $d$-manifold $M$, the classifying map $f_P:M\to BG$ pulls back $\omega$ to a $U(1)$-valued top-degree cohomology class on $M$. Evaluating it on the fundamental class gives a phase,

$$
\exp\left(2\pi i\int_M f_P^*\omega\right).
$$

The twisted partition function is schematically

$$
Z_{G,\omega}(M)
=
\sum_{[P]}
\frac{1}{|\operatorname{Aut}(P)|}
\exp\left(2\pi i\int_M f_P^*\omega\right).
$$

In a triangulated lattice presentation, the same phase is a product of $d$-cocycle factors over oriented $d$-simplices. The cocycle condition is precisely what makes the amplitude invariant under retriangulation moves.

:::note[Source note: cochains versus forms]
Unlike Chern–Simons or BF theory, Dijkgraaf–Witten theory is most naturally written with cochains rather than differential forms. The expression $\int_M f_P^*\omega$ means evaluation of a cohomology class on the fundamental cycle, not integration of an ordinary differential form.
:::

## Triangulated construction

A triangulated presentation makes the theory concrete.

1. Choose a triangulation of $M$.
2. Assign $g_{ij}\in G$ to each oriented edge.
3. Impose flatness on every triangle:

$$
g_{ij}g_{jk}g_{ki}=1.
$$

4. Identify configurations related by vertex gauge transformations.
5. Multiply by cocycle weights on top-dimensional simplices.
6. Sum over all flat assignments.

For example, in three dimensions the twist is a $3$-cocycle. Each tetrahedron receives a phase determined by the group elements on its edges, with an orientation-dependent exponent. The product over tetrahedra is invariant under Pachner moves because $\omega$ satisfies the cocycle condition.

Changing $\omega$ by a coboundary changes the action by a boundary term. On closed manifolds, cohomologous cocycles define equivalent theories. On manifolds with boundary, that boundary term matters and changes the boundary theory or boundary anomaly data.

## Operators and excitations

Dijkgraaf–Witten theory has no local propagating particles, but it has topological operators. The details depend strongly on dimension.

In two spacetime dimensions, finite gauge theory is closely related to orbifolds and sums over twisted sectors. Hilbert spaces on a circle are class functions or twisted-sector spaces, depending on boundary conditions and twist.

In three spacetime dimensions, line operators and particle-like anyons are central. In the untwisted theory, sectors are labeled by conjugacy classes and irreducible representations of centralizers. In categorical language, the anyons are described by the Drinfeld center of $\operatorname{Vec}_G$; with a twist, by the twisted center $Z(\operatorname{Vec}_G^\omega)$.

Physically, this means an excitation can carry both flux and charge:

$$
\text{anyon label}\sim
(\text{conjugacy class of flux},\ \text{charge representation of stabilizer}).
$$

For abelian $G$, conjugacy classes are group elements and centralizers are all of $G$, so the labels simplify to electric and magnetic charges.

In higher dimensions, topological defects of various dimensions encode holonomy, flux, domain-wall, and higher-form data.

## Wilson operators and flux defects

A Wilson line in finite gauge theory is labeled by a representation $R$ of $G$. Along a closed loop $\gamma$, it evaluates the holonomy of the flat $G$-connection:

$$
W_R(\gamma)=\operatorname{tr}_R\operatorname{Hol}_\gamma.
$$

Because the connection is flat, the holonomy depends only on the homotopy class of $\gamma$.

A magnetic or flux defect imposes prescribed holonomy around a linking loop or sphere. For nonabelian finite groups, flux is labeled not by a single group element but by a conjugacy class, because gauge transformations conjugate holonomies.

The interplay between Wilson operators and flux defects is the finite-group version of electric–magnetic charge pairing. In three dimensions it becomes anyon braiding. In higher dimensions it becomes linking between extended defects.

## Relation to orbifolds and gauging

Dijkgraaf–Witten theory is what appears when a finite global symmetry is gauged. If a QFT $\mathcal T$ has a finite symmetry $G$, gauging $G$ means summing over background flat $G$-bundles:

$$
Z_{\mathcal T/G}(M)
=
\sum_{[P]}
\frac{1}{|\operatorname{Aut}(P)|}
Z_{\mathcal T}[P],
$$

possibly with a Dijkgraaf–Witten phase inserted:

$$
Z_{\mathcal T/G,\omega}(M)
=
\sum_{[P]}
\frac{1}{|\operatorname{Aut}(P)|}
Z_{\mathcal T}[P]
\exp\left(2\pi i\int_M f_P^*\omega\right).
$$

In two-dimensional CFT, this operation is the orbifold construction: one sums over twisted sectors and projects onto gauge-invariant states. Dijkgraaf–Witten phases are discrete torsion.

This is why finite gauge theory belongs both to TQFT and to symmetry: it is the pure topological part of finite-symmetry gauging.

## Relation to BF theory

For finite abelian groups such as $G=\mathbb Z_k$, Dijkgraaf–Witten theory is closely related to compact BF theory. In suitable dimensions, the continuum action

$$
\frac{k}{2\pi}\int B\wedge dA
$$

encodes the same topological data as a discrete $\mathbb Z_k$ gauge theory.

The BF description is often easier for continuum QFT readers because it uses differential forms and higher-form gauge fields. The Dijkgraaf–Witten description is often more fundamental for finite groups because it works directly with finite bundles and cochains.

The relationship is a dictionary, not an identity of notation. BF theory naturally handles finite abelian and higher-form cases. Dijkgraaf–Witten theory naturally handles nonabelian finite groups and cocycle twists.

## Boundaries and interfaces

A Dijkgraaf–Witten theory on a manifold with boundary requires boundary conditions. These can include:

- fixing the finite gauge field at the boundary;
- allowing only a subgroup $H\subset G$ at the boundary;
- adding boundary degrees of freedom;
- choosing a boundary cocycle that cancels the bulk cocycle variation;
- condensing an algebra object in the associated category.

In physical language, a topological boundary condition decides which bulk defects can end. In SymTFT language, changing the topological boundary implements gauging, orbifolding, global-form changes, or projection onto different symmetry sectors.

Interfaces between two Dijkgraaf–Witten theories can be built from group homomorphisms, subgroup data, cocycles, or bimodule categories. This is one of the simplest places where categorical language becomes unavoidable but also concrete.

## Dijkgraaf–Witten theory as SymTFT

Dijkgraaf–Witten theory is a canonical example of a symmetry TFT. For a finite symmetry $G$, the one-higher-dimensional Dijkgraaf–Witten theory encodes:

- topological symmetry defects;
- twisted sectors;
- gauging operations;
- orbifold projection;
- finite-symmetry anomalies;
- boundary choices corresponding to different absolute theories.

For an anomalous $d$-dimensional finite symmetry, the anomaly is represented by a $(d+1)$-dimensional Dijkgraaf–Witten action. The $d$-dimensional theory is then naturally a boundary or relative theory for that bulk.

This is the finite-group prototype of the more general SymTFT philosophy.

## Common pitfalls

**“Finite gauge theory has no gauge field.”** It has a gauge field, but not an infinitesimal one-form connection in the Lie-algebra sense. It is a flat finite-group bundle or cochain gauge field.

**“Flat means trivial.”** Flat finite-group bundles can have nontrivial holonomy around noncontractible cycles. That is the whole point.

**“The partition function just counts bundles.”** In the untwisted theory it is a weighted groupoid count. In the twisted theory each bundle carries a cocycle phase.

**“A cocycle is a differential form.”** In Dijkgraaf–Witten theory it is usually a group cochain or class in $H^d(BG,U(1))$.

**“All finite gauge theories are abelian BF theories.”** No. Abelian finite gauge theories often admit BF descriptions; nonabelian finite groups and cocycle twists require the more general Dijkgraaf–Witten framework.

**“The twist is optional decoration.”** The twist can change anyon statistics, boundary categories, anomalies, and the topological order. It is physical data.

## Relations to other pages

[BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/) is the continuum abelian cousin. [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) explains how finite-symmetry gauging generates new theories and defects. [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) explains how topological boundary conditions encode gauging choices. [Examples of Symmetry TFT](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/examples-of-symmetry-tft/) uses finite-group topological gauge theories as basic SymTFT examples.

## Research status

Dijkgraaf–Witten theory is established. Its path integral, cocycle action, triangulated construction, and relation to finite gauge theory are standard.

Active research uses Dijkgraaf–Witten theory as a workhorse for finite symmetries, generalized gauging, topological phases, non-invertible symmetries, categorical boundaries, higher-group symmetries, anomaly inflow, and lattice models. In modern language, it is one of the simplest fully controlled laboratories for the idea that symmetry data can be packaged in a topological field theory.

## Exercises

### Exercise 1: Flatness on a triangle

Let a finite-group gauge field assign $g_{ij}\in G$ to oriented edges of a triangle. Explain why the condition

$$
g_{ij}g_{jk}g_{ki}=1
$$

is the finite-group analogue of zero curvature.

<details><summary><strong>Solution</strong></summary>

The product $g_{ij}g_{jk}g_{ki}$ is the holonomy around the triangle. In ordinary gauge theory, curvature measures infinitesimal holonomy around small loops. For a finite group there is no infinitesimal curvature two-form, but nontrivial holonomy around a contractible face is the discrete version of curvature. Setting the product to $1$ imposes flatness.

</details>

### Exercise 2: Gauge transformation of edge labels

Show that the triangle flatness condition is preserved by

$$
g_{ij}\mapsto h_i g_{ij}h_j^{-1}.
$$

<details><summary><strong>Solution</strong></summary>

The transformed product is

$$
(h_i g_{ij}h_j^{-1})(h_j g_{jk}h_k^{-1})(h_k g_{ki}h_i^{-1})
=
h_i(g_{ij}g_{jk}g_{ki})h_i^{-1}.
$$

If $g_{ij}g_{jk}g_{ki}=1$, then the transformed product is

$$
h_i1h_i^{-1}=1.
$$

Thus flatness is gauge invariant.

</details>

### Exercise 3: Flat bundles on a circle

Classify flat $G$-bundles on $S^1$ up to gauge equivalence.

<details><summary><strong>Solution</strong></summary>

A flat bundle on $S^1$ is specified by its holonomy $g\in G$ around the circle. A gauge transformation can conjugate this holonomy:

$$
g\mapsto hgh^{-1}.
$$

Therefore flat $G$-bundles on $S^1$ up to gauge equivalence are labeled by conjugacy classes of $G$.

</details>

### Exercise 4: Why the twist is topological

Why does a cocycle action give a topological phase rather than a metric-dependent action?

<details><summary><strong>Solution</strong></summary>

The cocycle action is evaluated on the cohomology class of the classifying map $f_P:M\to BG$ and the fundamental class of the manifold. It uses only the topology of the flat bundle and the oriented triangulated manifold. No metric appears. The cocycle condition ensures invariance under retriangulation moves, so the phase is topological.

</details>

## References

- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology.”
- D. Freed and F. Quinn, “Chern–Simons Theory with Finite Gauge Group.”
- V. Turaev and O. Viro, “State Sum Invariants of 3-Manifolds and Quantum 6j-Symbols.”
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality.”
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- M. Nakahara, *Geometry, Topology and Physics*, for bundles, homotopy, cohomology, and gauge geometry.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for topological field theory and topological matter context.

## Version history

- 2026-06-22: Initial polished draft. Added finite-group gauge fields, groupoid partition functions, cocycle actions, triangulated construction, operators, orbifold/gauging relation, BF relation, boundaries, SymTFT role, and exercises.
