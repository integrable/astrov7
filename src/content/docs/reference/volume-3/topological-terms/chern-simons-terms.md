---
title: "Chern–Simons Terms"
description: "Defines Abelian and non-Abelian Chern–Simons terms, explains level quantization, flat-connection equations, boundary modes, parity violation, and topological response."
sidebar:
  label: "Chern–Simons Terms"
  order: 5
level: Advanced
status: "Polished draft"
source: "Chern–Simons characteristic forms; Witten, Quantum Field Theory and the Jones Polynomial; Freed, Classical Chern–Simons Theory; Zee; Polyakov; Altland–Simons Ch. 8; standard TQFT and quantum Hall references."
topics:
  - Chern Simons terms
  - topological gauge theory
  - level quantization
  - large gauge transformations
  - Wilson lines
  - boundary WZW theory
  - topological response
canonicalTopics:
  - chern-simons-terms
  - level-quantization
  - topological-gauge-theory
  - boundary-anomaly
  - topological-response
researchStatus:
  established:
    - "Chern–Simons terms are secondary characteristic classes whose exterior derivative is a characteristic class such as Tr F wedge F."
    - "For compact gauge groups and appropriately normalized traces, gauge invariance of the quantum path integral quantizes the Chern–Simons level."
  active:
    - "Global forms of gauge groups, spin Chern–Simons theories, framing dependence, boundary conditions, non-invertible defects, and condensed-matter topological responses remain active sources of refined applications."
---

## Summary

A Chern–Simons term is a gauge-field topological term in odd spacetime dimension. The most important case is three dimensions. For an Abelian gauge field,

$$
S_{\mathrm{CS}}[A]=\frac{k}{4\pi}\int_{M_3}A\wedge dA.
$$

For a non-Abelian connection $A$ written with the Hermitian-generator convention

$$
D=d-iA,
\qquad
F=dA-iA\wedge A,
$$

a convenient three-dimensional Chern–Simons form is

$$
\omega_3(A)=\operatorname{Tr}\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right),
$$

which satisfies

$$
d\omega_3(A)=\operatorname{Tr}(F\wedge F).
$$

The action is

$$
S_{\mathrm{CS}}[A]=\frac{k}{4\pi}\int_{M_3}\omega_3(A).
$$

On a closed three-manifold, large gauge transformations shift the action by integer multiples of $2\pi k$. Thus the exponentiated action is well defined only for properly quantized $k$.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing the Chern–Simons action on a three-manifold, its flatness equation, level quantization under large gauge transformations, Wilson lines, and boundary anomaly/edge-mode logic.](/figures/symmetry-anomalies-topology/chern-simons-bulk-boundary-map.svg)

<figcaption>

A Chern–Simons term has no metric in its definition. Varying it gives flatness in the bulk, $F=0$. Large gauge transformations quantize the level, and boundaries require extra data: boundary conditions, edge modes, or a boundary WZW theory.

</figcaption>
</figure>

Chern–Simons terms sit at the meeting point of topology, gauge theory, anomalies, condensed-matter response, and low-dimensional TQFT. They are “only” first order in derivatives, but they carry a frankly suspicious amount of physics.

## Prerequisites

Read [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/) and [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/) first. You should know the distinction between background and dynamical gauge fields from [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) and the role of large transformations from [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

Differential forms are used freely. Boundary terms are not ignored unless explicitly stated.

## Core idea

Chern–Simons forms are **secondary characteristic classes**. A characteristic class such as

$$
\operatorname{Tr}(F\wedge F)
$$

is closed and gauge invariant. Locally it is the exterior derivative of a Chern–Simons form:

$$
\operatorname{Tr}(F\wedge F)=d\omega_3(A).
$$

The form $\omega_3(A)$ itself is not gauge invariant under all gauge transformations. That is not a flaw. It is the whole game. Its gauge variation is a total derivative plus a topological winding term, so the exponentiated action can still be well defined if the coefficient is quantized.

The essential pattern is

$$
\text{closed characteristic class in }4d
\quad\leadsto\quad
\text{Chern–Simons action in }3d.
$$

This is also why Chern–Simons terms constantly appear in anomaly inflow. A four-dimensional anomaly polynomial descends to a three-dimensional Chern–Simons action, whose boundary variation cancels a two-dimensional anomaly.

## Setup and conventions

Let $M_3$ be an oriented three-manifold. Unless stated otherwise, $M_3$ is closed. Let $A=A^aT^a$ be a connection for a compact gauge group $G$, with Hermitian generators and

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

We use

$$
\omega_3(A)=\operatorname{Tr}\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right),
$$

so that

$$
d\omega_3(A)=\operatorname{Tr}(F\wedge F).
$$

The Chern–Simons action is

$$
S_{\mathrm{CS}}=\frac{k}{4\pi}\int_{M_3}\omega_3(A).
$$

For $U(1)$, this reduces to

$$
S_{\mathrm{CS}}=\frac{k}{4\pi}\int_{M_3}A\wedge dA,
$$

with the normalization chosen so that a charge-one Wilson line is

$$
W(C)=\exp\left(i\int_C A\right).
$$

:::note[Convention-sensitive source note]
Many mathematical references use anti-Hermitian connections $\mathcal A$ with $\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A$ and write $\operatorname{Tr}(\mathcal A d\mathcal A+\frac23\mathcal A^3)$. This page uses the volume convention $D=d-iA$ with Hermitian $A$. Translating between the two conventions sends $\mathcal A=-iA$ and moves signs and factors of $i$ between $A$, $F$, and $\omega_3$.
:::

## Variation and equations of motion

On a closed three-manifold, varying the non-Abelian action gives

$$
\delta S_{\mathrm{CS}}
=\frac{k}{2\pi}\int_{M_3}\operatorname{Tr}(\delta A\wedge F).
$$

Therefore the classical equation of motion of pure Chern–Simons theory is

$$
F=0.
$$

The gauge field is flat. Locally, this means that

$$
A=i\,g^{-1}dg
$$

in the Hermitian convention. There are no local propagating bulk degrees of freedom. The theory is not empty, because flat connections can have nontrivial global holonomy, Wilson lines can braid, and boundaries can carry edge modes.

If $M_3$ has boundary, the variation includes a boundary term:

$$
\delta S_{\mathrm{CS}}
=\frac{k}{2\pi}\int_{M_3}\operatorname{Tr}(\delta A\wedge F)
-\frac{k}{4\pi}\int_{\partial M_3}\operatorname{Tr}(A\wedge\delta A).
$$

A well-defined variational principle then requires boundary conditions or additional boundary degrees of freedom.

## Gauge transformations and level quantization

Under a gauge transformation $g:M_3\to G$,

$$
A\longmapsto A^g=gAg^{-1}+i\,g\,dg^{-1}
$$

in the Hermitian convention. On a closed manifold, the Chern–Simons action changes by

$$
S_{\mathrm{CS}}[A^g]-S_{\mathrm{CS}}[A]=2\pi k\,n(g),
$$

where $n(g)$ is the winding number of the map $M_3\to G$, once the trace is normalized in the standard integral way.

Therefore

$$
e^{iS_{\mathrm{CS}}[A^g]}=e^{iS_{\mathrm{CS}}[A]}
$$

requires

$$
k\in\mathbb Z.
$$

This is the simplest level-quantization statement. It is correct for compact simply connected simple groups with the standard trace normalization. For non-simply connected groups, for quotient groups such as $SO(3)=SU(2)/\mathbb Z_2$, for spin Chern–Simons theories, and for theories coupled to fermions, the quantization law can be refined.

The moral is not “$k$ is always an integer no matter what.” The moral is:

$$
\text{large gauge transformations quantize the coefficient.}
$$

The exact lattice of allowed coefficients depends on the global data of the theory.

## Abelian Chern–Simons theory

The Abelian action

$$
S=\frac{k}{4\pi}\int A\wedge dA
$$

is already rich. In components,

$$
S=\frac{k}{8\pi}\int d^3x\,\epsilon^{\mu\nu\rho}A_\mu F_{\nu\rho}.
$$

The equation of motion for a dynamical $A$ is

$$
dA=0,
$$

in the absence of sources. With a conserved current coupled by

$$
S_{\mathrm{source}}=\int A\wedge *j,
$$

the equation of motion ties charge to flux. In components, the time component gives a Gauss-law constraint of the form

$$
\frac{k}{2\pi}B=\rho,
$$

where $B=F_{12}$ and $\rho=j^0$. Thus charged particles carry magnetic flux. In $2+1$ dimensions, charge-flux composites can have anyonic statistics.

For a background electromagnetic field $A_{\mathrm{em}}$, an effective response action

$$
S_{\mathrm{response}}=\frac{\nu}{4\pi}\int A_{\mathrm{em}}\wedge dA_{\mathrm{em}}
$$

encodes Hall response. Restoring units, the Hall conductivity is

$$
\sigma_{xy}=\nu\frac{e^2}{h}.
$$

This is one of the cleanest examples where a topological term directly measures a physical transport coefficient.

## Wilson lines and topology

The natural observables of Chern–Simons theory are Wilson lines,

$$
W_R(C)=\operatorname{Tr}_R\,\mathcal P\exp\left(i\oint_C A\right),
$$

where $C$ is a closed curve and $R$ is a representation of $G$.

Because the theory is topological, correlation functions of Wilson lines depend on the topology of the link rather than on a metric shape. In Abelian Chern–Simons theory, the phase knows about linking numbers. In non-Abelian Chern–Simons theory, Wilson-line expectation values produce quantum link invariants such as the Jones polynomial and its generalizations, after the necessary regularization and framing choices are made.

The framing caveat matters. A Wilson loop has a self-linking ambiguity. Regularizing it often requires a choice of framing, and changing the framing changes the answer by a known phase. This is not a bug in the calculation; it is part of the quantum definition of the observable.

## Boundary modes and WZW theory

If $M_3$ has a boundary, Chern–Simons theory is not automatically gauge invariant. Under a gauge transformation, the action produces a boundary variation. One may respond in several ways:

1. restrict gauge transformations at the boundary;
2. impose boundary conditions that make the variation vanish;
3. add boundary degrees of freedom whose anomaly cancels the bulk boundary variation.

The third option leads to WZW theory. Roughly,

$$
\text{Chern–Simons theory on }M_3\text{ with boundary }\Sigma_2
\quad\leadsto\quad
\text{WZW theory on }\Sigma_2.
$$

The Chern–Simons level $k$ becomes the affine-current level on the boundary. This is the field-theoretic prototype of bulk-boundary correspondence: a topological bulk action supports anomalous edge modes.

The same mechanism appears in quantum Hall systems, where a bulk Chern–Simons response is accompanied by chiral edge degrees of freedom. The edge is not optional decoration; it is required for gauge-invariant physics on a manifold with boundary.

## Parity, time reversal, and orientation

The Chern–Simons action depends on the orientation of $M_3$. Under orientation reversal,

$$
\int_{M_3}\omega_3(A)\longmapsto -\int_{M_3}\omega_3(A).
$$

In Lorentzian $2+1$ dimensions, parity and time reversal reverse orientation. Therefore a single Chern–Simons term with nonzero level generally violates $P$ and $T$.

There are ways to restore a larger symmetry. One can pair sectors with opposite levels, let the symmetry act nontrivially on the gauge fields, or put the boundary theory at the edge of a higher-dimensional bulk. But a lone Chern–Simons term is the canonical parity-odd topological action in three dimensions.

This is also why integrating out a massive fermion in three dimensions generates a half-integer Chern–Simons term whose sign depends on the fermion mass. The precise gauge-invariant interpretation is the parity anomaly, developed in the anomaly pages.

## Pure Chern–Simons versus topologically massive gauge theory

A pure Chern–Simons gauge field has no local bulk propagating modes. A Maxwell term changes that:

$$
S= -\frac{1}{2e^2}\int F\wedge *F+\frac{k}{4\pi}\int A\wedge dA.
$$

This is Maxwell–Chern–Simons theory. The Chern–Simons term gives the gauge boson a topological mass of order

$$
m\sim \frac{e^2 k}{2\pi},
$$

up to normalization conventions. This theory is not topological, because the Maxwell term uses the metric. But at energies far below the Maxwell scale, the topological Chern–Simons sector can dominate the long-distance response.

Thus “Chern–Simons term” and “Chern–Simons theory” are not synonyms. A Chern–Simons term can be part of an ordinary metric-dependent QFT.

## Non-Abelian quantum shifts

In non-Abelian Chern–Simons theory, the effective level that appears in some quantum observables is shifted by the dual Coxeter number,

$$
k\longrightarrow k+h^\vee,
$$

in common regularization conventions. This shift is closely tied to the framing anomaly, one-loop determinants, and the relation between Chern–Simons theory and WZW conformal blocks.

This does not mean that the bare level was not quantized. It means that the integer used to define the classical action and the combination appearing in exact quantum formulas must be related with care.

:::note[Convention-sensitive source note]
Some authors define the quantum theory with the shifted level already built into notation; others reserve $k$ for the integer in the classical action and write $k+h^\vee$ explicitly. Always check the convention before comparing central charges, modular $S$ matrices, or Wilson-line invariants.
:::

## Gravitational Chern–Simons terms

There is also a gravitational Chern–Simons term built from the spin connection $\omega$:

$$
S_{\mathrm{gCS}}\propto\int\operatorname{Tr}\left(\omega\wedge d\omega+\frac23\omega\wedge\omega\wedge\omega\right).
$$

Its exterior derivative is related to the Pontryagin density

$$
\operatorname{Tr}(R\wedge R).
$$

Gravitational Chern–Simons terms encode framing dependence, thermal Hall response, and gravitational anomaly inflow. They are more sensitive to spin and framing data than the simplest gauge Chern–Simons terms, so their quantization is correspondingly subtler.

For this chapter, the important lesson is structural: Chern–Simons terms are not only gauge-field terms. They are the odd-dimensional descendants of characteristic classes.

## Common pitfalls

The first pitfall is saying that Chern–Simons theory is trivial because $F=0$. Flat connections can have nontrivial holonomy, Wilson lines braid, moduli spaces of flat connections are nontrivial, and boundaries carry edge modes.

The second pitfall is ignoring level quantization. The coefficient $k$ is not a generic real coupling when the gauge field is compact and dynamical. Large gauge transformations see it.

The third pitfall is forgetting boundaries. On a manifold with boundary, gauge invariance and the variational principle require extra data. The boundary is where many of the most physical degrees of freedom live.

The fourth pitfall is mixing Hermitian and anti-Hermitian conventions. The Chern–Simons form changes appearance, but the transgression equation and level quantization are invariant.

The fifth pitfall is treating Wilson-line expectation values as ordinary metric-dependent correlation functions. In Chern–Simons theory, they are topological but framed; the framing data must be included.

## Relations to other pages

This page follows [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/), because the Chern–Simons/WZW boundary relation is one of the best ways to understand both terms.

It prepares for [BF Theory Terms](/symmetry-anomalies-topology/topological-terms/bf-theory-terms/), [Topological Response](/symmetry-anomalies-topology/topological-terms/topological-response/), and [Quantization of Couplings](/symmetry-anomalies-topology/topological-terms/quantization-of-couplings/). It also connects to [Anomaly Inflow](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/), [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), and later pages on topological QFT.

## Research status

Chern–Simons theory is one of the best-understood interacting topological quantum field theories. Its role in three-manifold topology, knot invariants, WZW conformal blocks, quantum Hall response, anyons, and anomaly inflow is established.

The active frontier is global and categorical. Modern work refines which Chern–Simons theories exist for non-simply connected groups, spin versus non-spin manifolds, nonsemisimple or finite gauge data, defects and anyon categories, generalized symmetries, non-invertible lines, and interfaces. In condensed matter, Chern–Simons response remains a central language for topological order and anomaly-protected edge physics.

## Exercises

### Exercise 1: Variation of Abelian Chern–Simons theory

For

$$
S[A]=\frac{k}{4\pi}\int_{M_3}A\wedge dA
$$

on a closed three-manifold, show that

$$
\delta S=\frac{k}{2\pi}\int_{M_3}\delta A\wedge dA.
$$

<details><summary><strong>Solution</strong></summary>

Vary the action:

$$
\delta S=\frac{k}{4\pi}\int \delta A\wedge dA+A\wedge d\delta A.
$$

Using

$$
A\wedge d\delta A=dA\wedge\delta A-d(A\wedge\delta A),
$$

and dropping the total derivative on a closed manifold, we get

$$
\delta S=\frac{k}{4\pi}\int \delta A\wedge dA+dA\wedge\delta A.
$$

Since $dA$ is a two-form and $\delta A$ is a one-form,

$$
dA\wedge\delta A=\delta A\wedge dA.
$$

Therefore

$$
\delta S=\frac{k}{2\pi}\int\delta A\wedge dA.
$$

</details>

### Exercise 2: Bulk equation of motion

Use Exercise 1 to find the equation of motion of pure Abelian Chern–Simons theory without sources.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta S=\frac{k}{2\pi}\int\delta A\wedge dA.
$$

For arbitrary $\delta A$, stationarity implies

$$
dA=0.
$$

Thus the Abelian connection is flat in the bulk.

</details>

### Exercise 3: Boundary warning

Repeat the variation of Exercise 1 when $M_3$ has a boundary. What extra term appears?

<details><summary><strong>Solution</strong></summary>

The variation gives

$$
\delta S=\frac{k}{4\pi}\int_{M_3}\delta A\wedge dA+A\wedge d\delta A.
$$

Using

$$
A\wedge d\delta A=dA\wedge\delta A-d(A\wedge\delta A),
$$

we find

$$
\delta S=\frac{k}{2\pi}\int_{M_3}\delta A\wedge dA
-\frac{k}{4\pi}\int_{\partial M_3}A\wedge\delta A.
$$

The boundary term must be cancelled or made to vanish by boundary conditions. Otherwise the variational principle is not well defined.

</details>

### Exercise 4: Hall response

Given

$$
S_{\mathrm{response}}[A]=\frac{\nu}{4\pi}\int A\wedge dA,
$$

show that the current is proportional to the dual field strength and identify the Hall conductivity in units where $e^2/h=1$.

<details><summary><strong>Solution</strong></summary>

Varying the action gives

$$
\delta S=\frac{\nu}{2\pi}\int\delta A\wedge dA.
$$

In components,

$$
j^\mu=\frac{\delta S}{\delta A_\mu}
=\frac{\nu}{2\pi}\epsilon^{\mu\nu\rho}\partial_\nu A_\rho.
$$

For an electric field $E_j$, this gives

$$
j^i=\frac{\nu}{2\pi}\epsilon^{ij}E_j
$$

in the convention where the $2\pi$ is absorbed into $h$. Restoring the standard condensed-matter unit gives

$$
\sigma_{xy}=\nu\frac{e^2}{h}.
$$

Thus $\nu$ is the dimensionless Hall conductance.

</details>

### Exercise 5: Why boundary modes are natural

Explain in words why a Chern–Simons theory on a manifold with boundary naturally leads to boundary degrees of freedom.

<details><summary><strong>Solution</strong></summary>

On a closed manifold, gauge variation of the Chern–Simons action is invisible in the exponentiated path integral when the level is quantized. On a manifold with boundary, gauge variation leaves a boundary term. If one wants to keep gauge transformations that act nontrivially at the boundary, this boundary variation must be cancelled by something. Boundary degrees of freedom can have precisely the opposite anomalous variation. In the non-Abelian case, those boundary fields are described by a WZW model in standard boundary conditions.

</details>

## References

- S.-S. Chern and J. Simons, “Characteristic Forms and Geometric Invariants.”
- E. Witten, “Quantum Field Theory and the Jones Polynomial.”
- D. Freed, “Classical Chern–Simons Theory, Part 1.”
- E. Witten, “(2+1)-Dimensional Gravity as an Exactly Soluble System.”
- A. Zee, *Quantum Field Theory in a Nutshell*, sections on Chern–Simons terms, fractional statistics, and topological field theory.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, topological field theory chapter.
- G. Moore and N. Seiberg, papers on Chern–Simons theory, rational conformal field theory, and modular tensor categories.
- X.-G. Wen, standard references on Chern–Simons effective theory and topological order.

## Version history

- 2026-06-18: First polished draft. Added Hermitian-generator convention, Abelian and non-Abelian actions, variation, level quantization, Wilson lines, boundary/WZW relation, parity warning, topological response, gravitational Chern–Simons orientation, pitfalls, and exercises.
