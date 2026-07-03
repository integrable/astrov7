---
title: "Fracton Symmetry: Preview"
description: "Preview of fracton phases, subsystem symmetries, foliation structure, tensor gauge theories, mobility constraints, and their relation to generalized symmetry."
sidebar:
  label: "Fracton Symmetry: Preview"
  order: 7
level: Research
status: "Polished draft"
source: "Pretko reviews; Nandkishore–Hermele review; Vijay–Haah–Fu; X-cube and Haah-code literature; recent higher-form/subsystem symmetry work."
topics:
  - fractons
  - subsystem symmetry
  - foliated order
  - tensor gauge theory
  - mobility constraints
  - fracton topological order
canonicalTopics:
  - fracton-symmetry
  - subsystem-symmetry
  - foliated-symmetry
  - tensor-gauge-theory
  - fracton-order
researchStatus:
  established:
    - "Fracton models provide robust lattice phases with subdimensional excitations, unusual ground-state degeneracy, and operator structures beyond ordinary topological order."
  active:
    - "The continuum field-theory, symmetry, anomaly, and categorical formulations of fracton phases are active research areas; this page is a careful preview rather than a final classification."
---

## Summary

Fracton phases are phases of matter in which some excitations cannot move freely. A **fracton** is an excitation that is immobile by itself. A **lineon** moves only along a line. A **planon** moves only inside a plane. These mobility restrictions are not ordinary symmetry-breaking degeneracies; they are enforced by a mixture of gauge constraints, subsystem symmetries, conservation laws, and extended operator structure.

The most famous examples are lattice models such as the X-cube model and Haah’s code. Continuum tensor gauge theories provide another window. In the scalar-charge rank-two $U(1)$ theory, Gauss’s law has the schematic form

$$
\partial_i\partial_j E^{ij}=\rho.
$$

This implies conservation not only of total charge,

$$
Q=\int d^3x\,\rho,
$$

but also of dipole moment,

$$
P^i=\int d^3x\,x^i\rho.
$$

Moving an isolated charge changes $P^i$, so the charge cannot move without creating additional excitations. That is the simplest continuum mechanism behind fractonic immobility.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Diagram showing fracton mobility classes: an immobile fracton, a lineon moving along a line, a planon moving in a plane, and a fully mobile particle.](/figures/symmetry-anomalies-topology/fracton-mobility-classes.svg)

<figcaption>

Fracton phases are organized by mobility constraints. Ordinary particles can move in all directions, planons move in a plane, lineons move along a line, and isolated fractons cannot move without violating conservation laws or creating additional excitations.

</figcaption>
</figure>

The preview slogan is:

$$
\text{fracton order} = \text{topological order with restricted mobility and subsystem structure}.
$$

That slogan is useful, but not a definition. The field is still young enough that several inequivalent definitions coexist.

## Prerequisites

You should know [Topological Order: Preview](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/topological-order-preview/), [Higher-Form Symmetry in Matter](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/higher-form-symmetry-in-matter/), [Subsystem Symmetries: Preview](/symmetry-anomalies-topology/higher-form-generalized-symmetries/subsystem-symmetries-preview/), and [Generalized Symmetry Breaking](/symmetry-anomalies-topology/higher-form-generalized-symmetries/generalized-symmetry-breaking/).

The page uses lattice-model language, basic gauge constraints, and the idea of an extended operator. It does not assume detailed knowledge of tensor gauge theory or stabilizer codes.

## Why fractons are surprising

Ordinary topological order has deconfined anyons or gauge charges that can move through space. Their braiding, fusion, and topological degeneracy are the main observables.

Fracton order keeps some of this topological flavor but changes mobility. Excitations can be pinned by conservation laws, not by energetic disorder. A fracton cannot move even in a perfectly translation-invariant model unless it emits or absorbs other excitations. A lineon can move along one axis but not perpendicular to it. A planon can move in a two-dimensional sheet.

This leads to unusual phenomena:

| Feature | Ordinary topological order | Fracton order |
|---|---|---|
| Excitations | mobile anyons or charges | fractons, lineons, planons |
| Degeneracy | depends on topology | often depends on system size and foliation |
| Operators | loops and membranes | rigid strings, fractal operators, membrane corners |
| Field theory | TQFT often works well | tensor, foliated, or lattice-sensitive field theories |
| Entanglement | topological constant terms | subleading structure can depend on geometry |
| Mobility | unconstrained in space | subdimensional or immobile |

The result is a kind of order that is topological, geometric, and lattice-sensitive all at once.

## Subsystem symmetry intuition

A subsystem symmetry acts not on all space, but on lower-dimensional subspaces such as rows, columns, planes, or leaves of a foliation. For example, a spin model might have independent $\mathbb Z_2$ symmetries on every row and every column.

Gauging such subsystem symmetries can produce fracton-like gauge theories. The intuition is simple: if charges are tied to many overlapping symmetry constraints, moving a single charge violates constraints along an extended set of subsystems. Only certain composites can move.

A row symmetry can forbid motion perpendicular to the row. A family of plane symmetries can allow particles to move within planes but not between them. Intersections of constraints can produce immobile charges.

This is not ordinary global symmetry and not ordinary gauge redundancy. It sits between them: rigid, extensive, and geometry-dependent.

:::note[Source note]
Subsystem symmetry is not the same thing as higher-form symmetry. Higher-form symmetry operators are topological and deformable. Subsystem symmetry operators are usually rigid: their support is tied to rows, planes, foliations, or other geometric structures.
:::

## Foliated order

Some fracton phases are best understood as **foliated** phases. This means that their long-distance structure is invariant not under adding a trivial product state, but under adding or removing layers of two-dimensional topological order.

The X-cube model is the central example. It can be built conceptually from stacks of two-dimensional toric-code layers arranged in three directions, then coupled in a way that produces fracton excitations. Its ground-state degeneracy on a three-torus depends on linear system sizes rather than only on the topology of the underlying manifold.

This is one reason ordinary TQFT is not enough. A fully topological theory would not care about lattice size or foliation data. A foliated fracton phase can care about the number of leaves or the geometry of the foliation while still being robust against local perturbations.

Foliated order is therefore a refinement of topological order, not merely a complicated example of it.

## Tensor gauge theory intuition

Continuum tensor gauge theories provide an elegant way to see mobility restrictions. The scalar-charge rank-two $U(1)$ gauge theory uses a symmetric tensor gauge field $A_{ij}$ with gauge transformation

$$
A_{ij}\mapsto A_{ij}+\partial_i\partial_j\alpha.
$$

The Gauss law is

$$
\partial_i\partial_j E^{ij}=\rho.
$$

Integrating over space gives charge conservation,

$$
\frac{d}{dt}\int d^3x\,\rho=0.
$$

Multiplying by $x^k$ and integrating by parts gives dipole conservation, under suitable boundary conditions,

$$
\frac{d}{dt}\int d^3x\,x^k\rho=0.
$$

An isolated charge moved from $x$ to $x+a$ changes the dipole moment by $qa^k$. If dipole moment is conserved, the isolated charge cannot move. A neutral dipole can move without changing total dipole moment, so it may be mobile. This is the rank-two gauge-theory explanation of fracton and dipole mobility.

:::note[Convention-sensitive caveat]
Tensor gauge theories are not ordinary Maxwell theories with more indices. Gauge transformations, compactness, allowed monopoles, lattice regularization, and matter couplings are all more delicate. Continuum notation is a guide, not a complete microscopic definition.
:::

## Operator diagnostics

Fracton models have characteristic extended operators, but they are often not freely deformable like topological Wilson loops.

In the X-cube model, membrane operators can create fractons at the corners of a rectangular membrane. String operators can create lineons at endpoints, but only along allowed directions. Planon composites can be moved within planes. In Haah’s code, logical operators can have fractal support, reflecting even more rigid mobility restrictions.

Thus the operator support is part of the phase data. Instead of asking only whether a loop can be deformed, one asks:

- Is the operator flexible or rigid?
- Does it create excitations at endpoints, corners, edges, or fractal boundaries?
- Which composites are mobile?
- Does the ground-state degeneracy depend on lattice size, foliation, or arithmetic data?
- Which subsystem or higher-moment conservation laws protect the restricted motion?

This is why fracton order is naturally adjacent to higher-form symmetry but not identical to it.

## Relation to higher-form symmetry

Higher-form symmetry and fracton order overlap in several ways.

First, many fracton models contain ordinary higher-form symmetries in certain limits or sectors. Second, foliated symmetries can be interpreted as exotic higher-form-like symmetries supported on leaves. Third, condensation of extended objects, such as strings or membranes, can generate fracton phases. Fourth, tensor gauge theories can sometimes be viewed as generalized gauge theories with higher-moment conservation laws.

But the differences are equally important. Higher-form symmetry operators are topological and can be smoothly deformed. Subsystem symmetry operators are typically rigid. Ordinary higher-form charges are measured by linking; fracton charges may require foliated, rectangular, or fractal probes. Higher-form symmetry is usually compatible with continuum topology; fracton order often remembers lattice geometry.

The safe statement is:

$$
\text{fracton symmetry generalizes higher-form symmetry in a geometry-sensitive direction}.
$$

## Relation to topological order

Fracton order shares several properties with topological order: robust degeneracy, nonlocal operators, emergent gauge constraints, and excitations not created singly by local operators. But it is not captured by ordinary TQFT.

Ordinary topological order depends on global topology. Fracton degeneracy can scale with system size, such as linear dimensions of a torus. Ordinary anyons can move and braid. Fractons may not move, and braiding must be replaced by restricted motion processes, cage operators, or statistical processes involving composites.

Thus fracton order is not simply “topological order plus anisotropy.” It is a genuinely different organization of quantum information in space.

## Examples

### X-cube model

The X-cube model is a stabilizer model on a cubic lattice. Its excitations include immobile fractons and lineons. It can be understood through coupled layers of toric code, and it is the archetype of foliated fracton order.

A membrane operator creates four fractons at its corners. Moving a single corner would require changing the membrane boundary in a way that creates more excitations. Certain bound states of fractons are planons and can move within planes.

### Haah code

Haah’s code is a stabilizer model with fractal logical operators. Its excitations cannot be moved by ordinary string operators. The model has strikingly slow dynamics and unusual quantum-memory properties.

The lesson is that fracton order is not always foliated in a simple layer sense. Some phases have fractal rather than planar operator structure.

### Rank-two scalar-charge theory

The rank-two $U(1)$ scalar-charge theory gives a continuum model of fractonic immobility through dipole conservation. It is not a complete replacement for lattice models, but it gives an analytically transparent mechanism.

The Gauss law

$$
\partial_i\partial_j E^{ij}=\rho
$$

is the heart of the story. It forces both charge and dipole conservation, making isolated charges immobile and dipoles mobile.

## Dynamics and glassiness

Fracton phases often have slow dynamics. If isolated excitations cannot move, relaxation requires creating additional excitations or moving composites. This can produce long-lived memory, constrained thermalization, and glassy behavior.

This is one reason fracton physics connects to quantum information. Restricted mobility can protect information, but it also complicates equilibration. The same constraints that make fractons interesting as phases can make them hard to characterize by ordinary continuum methods.

## Common pitfalls

**“Fractons are just heavy particles.”** No. A heavy particle can move slowly. A fracton is kinematically restricted by conservation laws or constraints.

**“Subsystem symmetry is just many copies of ordinary symmetry.”** It is more structured. The geometry of the symmetry support matters and controls mobility.

**“Fracton phases are ordinary TQFTs.”** Many fracton phases depend on foliation, lattice size, or fractal geometry. Ordinary TQFT is usually too coarse.

**“All fracton models are the same.”** X-cube, Haah code, checkerboard models, scalar-charge theories, and foliated models capture different mechanisms and may belong to different equivalence notions.

**“Continuum tensor gauge theory solves the classification.”** It is powerful but incomplete. Compactness, lattice regularization, defects, and microscopic operator structure are essential.

## Relations to other pages

This page follows [Higher-Form Symmetry in Matter](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/higher-form-symmetry-in-matter/) and connects back to [Subsystem Symmetries: Preview](/symmetry-anomalies-topology/higher-form-generalized-symmetries/subsystem-symmetries-preview/).

It also relates to [Topological Order: Preview](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/topological-order-preview/), because fracton phases are often viewed as beyond ordinary topological order, and to [Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/), because subsystem symmetry can enrich or constrain topological sectors.

## Research status

Fracton physics is established as a concrete subject through exactly solvable lattice models, tensor gauge theories, subsystem-symmetry constructions, and quantum-information diagnostics. Its general classification is not settled. Open questions include the right continuum definitions, the relation between foliated and fractal orders, anomaly and SymTFT-like formulations, thermal stability, experimental realization, and the role of fracton constraints in quantum dynamics.

This page is therefore intentionally labeled as a preview. It gives a map, not a final taxonomy.

## Exercises

### Exercise 1: Dipole conservation and immobility

Suppose a charge $q$ moves from position $x^i$ to $x^i+a^i$. Show that the dipole moment

$$
P^i=\int d^3x\,x^i\rho
$$

changes by $qa^i$. Why does dipole conservation forbid motion of an isolated charge?

<details><summary><strong>Solution</strong></summary>

For a point charge at $x^i$, the contribution to the dipole moment is $qx^i$. After moving to $x^i+a^i$, the contribution is $q(x^i+a^i)$. The change is

$$
\Delta P^i=qa^i.
$$

If $P^i$ is exactly conserved and $q\ne0$, a displacement with $a^i\ne0$ is forbidden unless some other excitation changes the dipole moment by $-qa^i$. Thus an isolated charge is immobile.

</details>

### Exercise 2: Mobile dipoles

Why can a neutral dipole be mobile even when isolated charges are immobile?

<details><summary><strong>Solution</strong></summary>

A neutral dipole consists of charges $+q$ and $-q$ separated by a fixed vector. Translating the whole dipole by $a^i$ changes the dipole moment by

$$
q a^i-q a^i=0.
$$

Thus the total dipole moment is unchanged. Conservation of dipole moment forbids motion of an isolated charge, but it need not forbid motion of a neutral dipole.

</details>

### Exercise 3: Rigid versus topological operators

Explain why subsystem symmetry operators are usually not topological operators in the ordinary higher-form sense.

<details><summary><strong>Solution</strong></summary>

A topological higher-form symmetry operator can be smoothly deformed as long as it does not cross charged insertions. A subsystem symmetry operator is tied to a rigid subspace such as a row, plane, or foliation leaf. Moving it to a generic nearby surface is not a symmetry operation. Therefore its support geometry is part of the definition, not an irrelevant deformation choice.

</details>

## References

- Rahul M. Nandkishore and Michael Hermele, “Fractons.”
- Michael Pretko, Xie Chen, and Yizhi You, “Fracton Phases of Matter.”
- Vijay, Haah, and Fu, “Fracton Topological Order, Generalized Lattice Gauge Theory, and Duality.”
- Jeongwan Haah, “Local stabilizer codes in three dimensions without string logical operators.”
- Marvin Qi, Leo Radzihovsky, and Michael Hermele, “Fracton Phases via Exotic Higher-Form Symmetry Breaking.”
- Altland and Simons, *Condensed Matter Field Theory*, for broken symmetry, gauge theory, topological quantum matter, and field-theory methods in matter.

## Version history

- 2026-06-23: Initial polished preview. Added subsystem symmetry, foliated order, rank-two tensor gauge theory, X-cube, Haah code, mobility constraints, and research-status caveats.
