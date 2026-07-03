---
title: "BF Theory"
description: "Introduces BF theory as a metric-independent topological gauge theory, including abelian and nonabelian actions, gauge invariance, linking observables, compact quantization, boundaries, and its relation to higher-form symmetry."
sidebar:
  label: "BF Theory"
  order: 5
level: Advanced
status: "Polished draft"
source: "Schwarz; Blau–Thompson; Horowitz; Nakahara; Frankel; Altland–Simons; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - BF theory
  - topological gauge theory
  - higher-form gauge fields
  - linking phases
  - finite gauge theory
  - topological order
canonicalTopics:
  - bf-theory
  - topological-gauge-theory
  - higher-form-gauge-field
  - linking-pairing
  - discrete-gauge-theory
researchStatus:
  established:
    - "BF theory is a standard Schwarz-type TQFT whose action is metric-independent and whose observables detect linking, holonomy, flux, and flat-connection data."
    - "Compact abelian BF theory gives a continuum description of many finite abelian gauge theories and higher-form topological gauge theories."
  active:
    - "Modern uses include higher-form symmetry, topological phases, SymTFTs, subsystem/fracton generalizations, boundary topological orders, and continuum descriptions of discrete gauge theory."
---

## Summary

**BF theory** is a topological gauge theory built from a pair of differential-form gauge fields. In its simplest abelian form in $d$ spacetime dimensions, one chooses a $p$-form gauge field $A_p$ and a $(d-p-1)$-form gauge field $B_{d-p-1}$ and writes

$$
S_{\mathrm{BF}}
=
\frac{k}{2\pi}\int_M B_{d-p-1}\wedge dA_p.
$$

For the most common four-dimensional case, $A$ is an ordinary one-form gauge field and $B$ is a two-form gauge field:

$$
S_{\mathrm{BF}}
=
\frac{k}{2\pi}\int_{M_4} B\wedge dA.
$$

The action contains no Hodge star, no metric, and no local kinetic energy. The classical equations of motion are flatness conditions,

$$
dA=0,
\qquad
 dB=0,
$$

up to source insertions and nonabelian refinements. The theory is therefore not about propagating waves. It is about global sectors, holonomies, fluxes, linking phases, boundaries, and topological response.

The shortest slogan is

$$
\text{BF theory}=
\text{topological gauge theory pairing two complementary form fields}.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![BF theory linking diagram showing complementary extended operators linked in spacetime and coupled through the BF action.](/figures/symmetry-anomalies-topology/bf-theory-linking.svg)

<figcaption>

In abelian BF theory, complementary extended operators supported on $\Sigma_p$ and $\Gamma_{d-p-1}$ detect their linking. This is the topological analogue of electric–magnetic pairing.

</figcaption>
</figure>

BF theory is the natural partner of Chern–Simons theory in the TQFT chapter. Chern–Simons theory is odd-dimensional and built from one connection. BF theory exists in many dimensions and pairs two gauge fields of complementary degree.

## Prerequisites

You should know [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/), [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/), and [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/). You should also be comfortable with differential forms, Stokes’ theorem, gauge fields, holonomy, Wilson lines, compact gauge fields, and the basic higher-form symmetry convention that a $q$-form symmetry acts on $q$-dimensional charged operators.

The page uses the convention that $A_p$ is a $p$-form, $B_{d-p-1}$ is a $(d-p-1)$-form, and $M_d$ is an oriented $d$-manifold. When compactness matters, $A$ and $B$ are not globally defined ordinary forms; they should be understood as higher-form connections with quantized periods or as differential-cohomology data. The page keeps the notation differential-form friendly but flags the places where this shorthand matters.

## Core idea

A Yang–Mills action measures curvature with a metric:

$$
S_{\mathrm{YM}}
\sim
\int F\wedge *F.
$$

A BF action pairs a field strength with a Lagrange-multiplier-type form:

$$
S_{\mathrm{BF}}
\sim
\int B\wedge F.
$$

The Hodge star $*$ is absent. This makes BF theory a **Schwarz-type** TQFT: the action is metric-independent before using any cohomological supercharge.

In the abelian theory $F=dA$, varying $B$ gives

$$
dA=0,
$$

and varying $A$ gives

$$
dB=0
$$

on a closed manifold. Thus $A$ and $B$ are flat away from insertions. The nontrivial content comes from global holonomies and fluxes. If a charged operator creates a singularity or holonomy for one field, the other field detects it by linking.

This is why BF theory appears everywhere in symmetry and topology: it is the minimal topological action encoding a perfect pairing between complementary electric and magnetic data.

## Abelian BF theory

Let $A_p$ be a compact $p$-form gauge field and $B_{d-p-1}$ a compact $(d-p-1)$-form gauge field. The action is

$$
S
=
\frac{k}{2\pi}\int_{M_d} B_{d-p-1}\wedge dA_p.
$$

The gauge transformations are

$$
A_p\mapsto A_p+d\lambda_{p-1},
\qquad
B_{d-p-1}\mapsto B_{d-p-1}+d\Lambda_{d-p-2}.
$$

For noncompact fields, the coefficient $k$ could be rescaled away. For compact gauge fields, large gauge transformations and flux quantization make $k$ physical. With standard normalizations, gauge invariance of the path-integral phase requires

$$
k\in\mathbb Z.
$$

The two basic gauge-invariant operators are

$$
W_e(\Sigma_p)
=
\exp\left(i e\int_{\Sigma_p} A_p\right),
$$

and

$$
V_m(\Gamma_{d-p-1})
=
\exp\left(i m\int_{\Gamma_{d-p-1}} B_{d-p-1}\right),
$$

where $\Sigma_p$ is a closed $p$-dimensional submanifold and $\Gamma_{d-p-1}$ is a closed $(d-p-1)$-dimensional submanifold. Their correlation function depends on the linking number,

$$
\langle W_e(\Sigma_p)V_m(\Gamma_{d-p-1})\rangle
\propto
\exp\left(\frac{2\pi i\,em}{k}\operatorname{Link}(\Sigma_p,\Gamma_{d-p-1})\right),
$$

up to normalization, framing, torsion-sector, and compactness refinements.

This formula is the abelian BF analogue of the Wilson-line linking formula in abelian Chern–Simons theory. The difference is that the two linked operators have complementary dimensions rather than both being lines in three dimensions.

:::note[Source note: compact fields]
The compact theory is not fully captured by treating $A$ and $B$ as globally defined real forms. A clean definition uses Deligne–Beilinson/differential-cohomology language, lattice cochains, or bundle gerbes depending on dimension and audience. The differential-form expression is the right local mnemonic, but not the whole global definition.
:::

## Four-dimensional BF theory

The most common example in QFT is four-dimensional BF theory,

$$
S=\frac{k}{2\pi}\int_{M_4}B\wedge dA,
$$

where $A$ is a one-form and $B$ is a two-form. The natural operators are a line and a surface:

$$
W_e(\gamma)=\exp\left(i e\oint_\gamma A\right),
$$

and

$$
V_m(\Sigma)=\exp\left(i m\int_\Sigma B\right).
$$

If the line $\gamma$ links the surface $\Sigma$, the correlator acquires the phase

$$
\exp\left(\frac{2\pi i\,em}{k}\operatorname{Link}(\gamma,\Sigma)\right).
$$

This theory is a continuum model for a $\mathbb Z_k$ topological gauge theory in four dimensions. It also describes the universal infrared topological response of certain gapped phases with $\mathbb Z_k$ topological order.

The equations of motion say that $A$ and $B$ are flat away from line and surface insertions. The line creates a source for $B$; the surface creates a source for $A$. Their mutual phase is topological because it depends only on how the supports are linked.

## Relation to finite gauge theory

Compact abelian BF theory often gives a continuum presentation of finite abelian gauge theory. The simplest slogan is

$$
\frac{k}{2\pi}\int B\wedge dA
\quad\leadsto\quad
\mathbb Z_k\text{ gauge theory}.
$$

A quick way to see this is to integrate out $B$. Formally, the $B$ path integral imposes

$$
dA=0
$$

with a compactness condition that leaves only $\mathbb Z_k$ holonomies. Equivalently, integrating out $A$ constrains $B$ to have discrete flux data.

This is why BF theory is a bridge between continuous differential-form notation and discrete topological gauge theory. Dijkgraaf–Witten theory, treated on the next page, is the more intrinsically finite-group version. Abelian BF theory is the continuum-looking cousin for finite abelian groups and their higher-form generalizations.

:::caution[Do not overread the continuum notation]
A BF action with compact fields is not just a Gaussian integral over ordinary real-valued forms. The finite gauge theory appears because the gauge fields are compact and because large gauge transformations and quantized periods are part of the definition.
:::

## Nonabelian BF theory

For a Lie group $G$, a nonabelian BF action has the schematic form

$$
S=\int_M \operatorname{tr}(B\wedge F_A),
$$

where $A$ is a connection, $F_A=dA+iA\wedge A$ in the Hermitian convention, and $B$ is a Lie-algebra-valued $(d-2)$-form.

The variation with respect to $B$ gives

$$
F_A=0,
$$

so $A$ is flat. The variation with respect to $A$ gives

$$
D_A B=0.
$$

Thus nonabelian BF theory is closely related to the moduli space of flat connections. It is topological, but less elementary than the abelian theory because gauge fixing, reducible flat connections, one-loop determinants, and global moduli-space issues become important.

In three dimensions, nonabelian BF theory with suitable groups is related to first-order formulations of gravity. In four dimensions, constrained BF theory is one route toward formulations of general relativity. Those gravitational applications belong mostly to the Spacetime, Gravity, and Holography volume; here the point is the symmetry/topology role of the BF action.

## Observables and linking

The most important observables in BF theory are extended. A $p$-form field naturally integrates over a $p$-dimensional support. A $(d-p-1)$-form field naturally integrates over a $(d-p-1)$-dimensional support.

The supports have complementary dimensions:

$$
p+(d-p-1)=d-1.
$$

That is precisely the dimension count that allows linking in $d$ dimensions.

For closed supports, the operator algebra is often a finite Heisenberg-like algebra. In the four-dimensional $\mathbb Z_k$ BF theory, a line and a surface that link once obey a phase relation of the form

$$
V_m(\Sigma)W_e(\gamma)
=
\exp\left(\frac{2\pi iem}{k}\right)
W_e(\gamma)V_m(\Sigma),
$$

when the operators are radially or canonically ordered so that their linking is measured. This is the higher-dimensional version of anyonic braiding.

The phrase “operator algebra” here means an algebra of topological extended operators, not an algebra of local fields at equal time.

## Higher-form symmetry viewpoint

BF theory is a natural home for higher-form symmetries. In a $d$-dimensional theory with action

$$
\frac{k}{2\pi}\int B_{d-p-1}\wedge dA_p,
$$

one can think of $A_p$ and $B_{d-p-1}$ as coupling to complementary higher-form currents. The topological operators generated by one field act on charged operators built from the other.

For example, in four-dimensional BF theory, the surface operator built from $B$ acts on Wilson lines built from $A$. The Wilson line is charged under a one-form symmetry. The surface operator is the corresponding symmetry operator.

The mutual linking phase is then a Ward identity in geometric clothing:

$$
\text{move symmetry surface across charged line}
\quad\Rightarrow\quad
\text{multiply by a phase}.
$$

This makes BF theory a model laboratory for generalized global symmetry, gauging higher-form symmetries, and SymTFT constructions.

## Boundaries

On a manifold with boundary, variation of the abelian BF action produces a boundary term,

$$
\delta S
=
\frac{k}{2\pi}\int_M
\left(
\delta B\wedge dA+(-1)^{d-p}dB\wedge\delta A
\right)
+
\text{boundary term}.
$$

To define the theory, one must choose boundary conditions or add boundary degrees of freedom. Typical choices include fixing $A$ at the boundary, fixing $B$, imposing a relation between them, or adding a boundary topological theory.

Boundaries are not afterthoughts. They determine which bulk operators can end, which symmetries remain, and what boundary topological order appears. This is exactly why BF theory is useful in the SymTFT viewpoint: different topological boundary conditions encode different gauging choices and global forms.

## Relation to Chern–Simons theory

BF theory and Chern–Simons theory are cousins.

| Feature | Chern–Simons | BF theory |
|---|---|---|
| Typical dimension | Odd, especially $d=3$ | Many dimensions |
| Fields | One connection $A$ | Pair $A_p$, $B_{d-p-1}$ |
| Action | $A\wedge dA+\frac{2i}{3}A^3$ | $B\wedge dA$ or $B\wedge F$ |
| Classical equation | Flatness | Flatness and covariant constancy |
| Observables | Wilson lines, links | Complementary extended operators, linking |
| Common use | Knot invariants, anyons, boundary WZW | Finite gauge theory, higher-form symmetry, topological order |

In three dimensions, abelian BF theory with two one-form gauge fields can be rewritten as a difference of abelian Chern–Simons theories after a linear change of variables, if the levels and compactness conditions allow it. This is useful but can hide the higher-form pairing structure that is explicit in BF notation.

## Common pitfalls

**“BF theory is trivial because the equations say the fields are flat.”** Flat does not mean globally trivial. Flat connections can have holonomy, torsion sectors, boundary states, and nontrivial linking with extended operators.

**“The coefficient can always be rescaled away.”** Not for compact gauge fields. Periodicities and large gauge transformations make $k$ physical.

**“A differential-form action is automatically globally well-defined.”** Not necessarily. Compact gauge fields and higher-form connections require patching or differential-cohomology data. The local form notation is a shorthand.

**“BF theory has no observables because it has no local particles.”** TQFT observables are often extended and global: Wilson operators, surface operators, boundary states, and mapping-class-group actions.

**“BF theory and Dijkgraaf–Witten theory are the same thing.”** BF theory gives continuum descriptions of many finite abelian cases. Dijkgraaf–Witten theory is the intrinsic finite-group gauge theory and includes nonabelian finite groups and cocycle twists.

## Relations to other pages

[Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/) is the closest previous page. [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) follows naturally because finite gauge theory is often the discrete version of the BF story. [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) uses BF theory as a canonical model for higher-form background fields, gauging, and linking Ward identities. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) uses BF-like topological gauge theories as bulk symmetry theories.

## Research status

BF theory itself is established. Compactness, boundary conditions, torsion sectors, and nonabelian moduli-space issues require care, but the basic theory is standard.

Active research uses BF-type actions in SymTFT, higher-form symmetry, topological phases, fracton/subsystem generalizations, finite higher-group gauge theory, and continuum descriptions of lattice topological order. The formulas on this page are deliberately conservative; more refined versions replace differential forms by cochains, differential cocycles, higher stacks, or extended TQFT data.

## Exercises

### Exercise 1: Equations of motion

Vary the abelian action

$$
S=\frac{k}{2\pi}\int_M B_{d-p-1}\wedge dA_p
$$

on a closed manifold. Derive the equations of motion.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta S
=
\frac{k}{2\pi}\int_M
\delta B\wedge dA+B\wedge d(\delta A).
$$

Integrating the second term by parts on a closed manifold gives

$$
\delta S
=
\frac{k}{2\pi}\int_M
\delta B\wedge dA+(-1)^{d-p}dB\wedge\delta A,
$$

up to the standard sign from moving $d$ past a $(d-p-1)$-form. Since $\delta A$ and $\delta B$ are arbitrary, the equations of motion are

$$
dA=0,
\qquad
 dB=0.
$$

</details>

### Exercise 2: Dimension count for linking

Show that a $p$-dimensional operator and a $(d-p-1)$-dimensional operator can have a linking number in $d$ dimensions.

<details><summary><strong>Solution</strong></summary>

Two closed submanifolds of dimensions $r$ and $s$ can link in $d$ dimensions when

$$
r+s=d-1.
$$

Here $r=p$ and $s=d-p-1$, so

$$
p+(d-p-1)=d-1.
$$

Thus their supports have exactly the complementary dimensions needed for a linking pairing.

</details>

### Exercise 3: Four-dimensional line-surface phase

In four-dimensional $\mathbb Z_k$ BF theory, suppose a line operator of charge $e$ links once with a surface operator of charge $m$. What phase should their correlator acquire?

<details><summary><strong>Solution</strong></summary>

The linking formula gives

$$
\exp\left(\frac{2\pi iem}{k}\operatorname{Link}(\gamma,\Sigma)\right).
$$

For one unit of linking,

$$
\operatorname{Link}(\gamma,\Sigma)=1,
$$

so the phase is

$$
\exp\left(\frac{2\pi iem}{k}\right).
$$

</details>

### Exercise 4: Why compactness matters

Why does the integer $k$ become physical for compact BF theory, while a noncompact Gaussian-looking action might allow rescalings?

<details><summary><strong>Solution</strong></summary>

For compact gauge fields, the periods of $A$ and $B$ are quantized and gauge transformations can be large. Rescaling a compact gauge field changes its periodicity and therefore changes the allowed operator charges and flux sectors. The coefficient $k$ controls the pairing between quantized sectors and must be integral for the path-integral phase to be well-defined. Thus $k$ is not a removable normalization; it is topological data.

</details>

## References

- A. S. Schwarz, “The Partition Function of a Degenerate Quadratic Functional and Ray–Singer Invariants.”
- G. T. Horowitz, “Exactly Soluble Diffeomorphism Invariant Theories.”
- M. Blau and G. Thompson, “Topological Gauge Theories of Antisymmetric Tensor Fields.”
- M. Nakahara, *Geometry, Topology and Physics*, for differential forms, bundles, characteristic classes, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*, for differential forms, integration, Stokes’ theorem, bundles, and gauge geometry.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, especially the topological-field-theory chapters.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for higher-form symmetry and charged extended operators.

## Version history

- 2026-06-22: Initial polished draft. Added abelian and nonabelian BF theory, compact quantization, linking observables, higher-form symmetry interpretation, boundary discussion, and exercises.
