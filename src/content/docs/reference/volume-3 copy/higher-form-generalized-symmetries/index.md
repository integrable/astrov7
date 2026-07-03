---
title: "Higher-Form and Generalized Symmetries"
description: "Chapter overview for higher-form global symmetries, charged extended operators, background higher-form gauge fields, gauging, center symmetry, and higher-group refinements."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Kapustin–Seiberg; Aharony–Seiberg–Tachikawa; Polyakov Ch. 7; Srednicki §82; standard gauge-theory and TQFT references."
topics:
  - higher-form symmetry
  - generalized global symmetry
  - charged extended operators
  - one-form symmetry
  - center symmetry
  - higher-group symmetry
  - generalized symmetry breaking
canonicalTopics:
  - higher-form-symmetry
  - generalized-global-symmetry
  - charged-extended-operator
  - center-one-form-symmetry
  - higher-group-symmetry
researchStatus:
  established:
    - "Higher-form global symmetries are now a standard structural language for charged extended operators, topological symmetry operators, background fields, gauging, and anomaly constraints."
  active:
    - "Higher-group, subsystem, fractonic, non-invertible, fermionic, and symmetry-TFT refinements remain active research areas, and the later chapters separate their roles carefully."
---

Higher-Form and Generalized Symmetries is the chapter in the Symmetry, Anomalies, and Topology volume where the word “symmetry” stops being tied only to local operators and particle states. Ordinary global symmetries act on pointlike local operators. Higher-form symmetries act on extended operators: lines, surfaces, membranes, and their higher-dimensional analogues.

The basic definition is compact. In $d$ spacetime dimensions, a $q$-form symmetry has topological symmetry operators supported on closed codimension-$q+1$ manifolds, and it acts on $q$-dimensional charged operators:

$$
U_g(\Sigma^{d-q-1})\quad\text{acts on}\quad W_q(M^q).
$$

Ordinary global symmetry is the case $q=0$. A one-form symmetry acts on line operators, such as Wilson lines. A two-form symmetry acts on surface operators. This chapter teaches the common structure behind these cases: topological charge operators, linking, higher-form currents, background higher-form gauge fields, gauging, symmetry breaking, and anomalies.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Schematic diagram of a higher-form symmetry operator supported on a closed surface linked with an extended charged operator.](/figures/symmetry-anomalies-topology/higher-form-symmetry-linking.svg)

<figcaption>

A $q$-form symmetry is measured by a topological operator $U_g(\Sigma^{d-q-1})$ linked with a charged $q$-dimensional operator $W_q(M^q)$. Deforming $\Sigma$ without crossing $M$ does not change the correlator; crossing or linking implements the symmetry action.

</figcaption>
</figure>

Read this chapter after Defects and Extended Operators. That chapter explains what extended insertions are. This chapter explains when those extended insertions are charged under a genuine global symmetry.

:::note[Source note]
This volume follows the modern convention that a $q$-form symmetry acts on $q$-dimensional charged operators. In older language, many of the same structures appear as conserved brane charges, topological currents, center symmetry, electric/magnetic flux conservation, or superselection sectors of line and surface operators.
:::

## Prerequisites

You should know [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/), especially local versus extended operators, Wilson lines, ’t Hooft lines, surface operators, defect fusion, and line-operator algebras. You should also know [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) and the distinction between background and dynamical gauge fields.

Differential-form notation is used throughout. The minimum needed facts are that a $p$-form can be integrated over a $p$-dimensional manifold, that $d$ is the exterior derivative, and that conserved higher-form currents are naturally written using Hodge duals. Readers who want a geometric refresher should use the Mathematical Toolkit pages on differential forms, bundles, and cohomology.

The chapter is conceptually advanced, but the first two pages are designed to be readable after ordinary global symmetries, Wilson lines, and basic gauge theory.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) | The basic definition, the $q=0$ reduction to ordinary symmetry, and the topological-operator viewpoint. |
| 2 | [Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/) | The charged objects: Wilson lines, ’t Hooft lines, surface operators, strings, branes, and their linking tests. |
| 3 | [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) | The higher-form analogue of coupling an ordinary current to a background gauge field. |
| 4 | [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) | What it means to sum over higher-form background fields and how gauging changes line and surface operators. |
| 5 | [Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/) | The canonical gauge-theory example: center one-form symmetry, Wilson lines, screening, confinement diagnostics, and global form. |
| 6 | [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) | Maxwell theory and gauge theory examples where electric and magnetic line operators reveal dual one-form structures. |
| 7 | [Higher-Group Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-group-symmetries/) | Situations where ordinary and higher-form symmetries do not factor independently but mix through background-field transformations. |
| 8 | [Subsystem Symmetries Preview](/symmetry-anomalies-topology/higher-form-generalized-symmetries/subsystem-symmetries-preview/) | A preview of symmetries acting on rigid submanifolds rather than all deformable cycles, important in fracton-like systems. |
| 9 | [Generalized Symmetry Breaking](/symmetry-anomalies-topology/higher-form-generalized-symmetries/generalized-symmetry-breaking/) | Order parameters, perimeter/area/volume laws, generalized Goldstone modes, and phases organized by higher-form symmetry realization. |

After this path, you should be able to identify the charged extended operators of a theory, say which topological operators measure them, decide what background fields are needed, and recognize the first signs of higher-form anomalies or generalized symmetry breaking.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $q$-form symmetry | A global symmetry whose charged operators have spacetime dimension $q$. | The whole chapter. |
| Topological charge operator | A closed codimension-$q+1$ operator $U_g(\Sigma)$ that can be deformed without changing correlators unless it crosses charged objects. | Charged Extended Operators, Symmetry TFT. |
| Linking action | The symmetry action is detected when $\Sigma^{d-q-1}$ links or crosses a charged $q$-dimensional operator. | One-form symmetry, line-operator algebras. |
| Higher-form current | For continuous Abelian higher-form symmetries, a conserved $(q+1)$-form current $J_{q+1}$ obeys $d{*J}_{q+1}=0$. | Background fields and Ward identities. |
| Higher-form background field | A $(q+1)$-form gauge field $B_{q+1}$ couples to a $q$-form symmetry. | Gauging, anomalies, symmetry TFT. |
| Gauging | Summing over higher-form backgrounds changes which extended operators are genuine and may quotient or dualize global symmetry data. | Symmetry TFT, topological terms. |
| Center one-form symmetry | A gauge-theory symmetry acting on Wilson lines by their center charge. | Confinement, global form, Wilson loops. |
| Electric/magnetic one-form symmetry | Symmetries measuring electric or magnetic flux sectors, especially transparent in Maxwell theory and Abelian gauge theories. | Duality, line operators, mixed anomalies. |
| Higher-group symmetry | A symmetry structure where ordinary and higher-form background gauge transformations mix. | Higher-group page, anomaly inflow. |
| Generalized symmetry breaking | Higher-form analogues of broken/unbroken phases, diagnosed by extended order parameters rather than local order parameters. | Phases of matter, confinement, TQFT. |

The most important conceptual move is replacing “charge inside a spatial region” by “charge measured by linking.” For ordinary symmetry, one surrounds a local operator by a codimension-one surface. For a one-form symmetry in four dimensions, one surrounds or links a line operator by a closed two-surface. The geometry changes, but the Ward-identity idea remains.

## Common confusions

**“Higher-form symmetry means higher-spin symmetry.”** No. “Form” labels the dimension of the charged operators, not particle spin. A one-form symmetry acts on line operators; it is not a symmetry generated by a spin-one current in the ordinary particle sense.

**“A higher-form symmetry is just a gauge redundancy.”** No. A higher-form *global* symmetry acts on physical extended operators and gives selection rules. A higher-form *gauge redundancy* is a redundancy in a description. As with ordinary symmetry, confusing global symmetry with gauge redundancy causes trouble.

**“Wilson lines are always charged under a one-form symmetry.”** Only unscreened genuine Wilson lines can carry conserved one-form charge. If dynamical matter allows the line to end, the corresponding one-form charge is screened or explicitly broken.

**“Every extended operator defines a higher-form symmetry.”** No. Extended operators are possible charged objects, not automatically symmetries. A symmetry requires topological charge operators with deformation-invariant Ward identities.

**“Continuous higher-form symmetries always behave like ordinary compact Lie groups.”** They often have Abelian continuous groups because extended charged objects have different locality constraints. Non-Abelian higher-form symmetry requires more refined categorical language and is not the default elementary case.

**“Center symmetry is only a statement about the center of a group.”** In gauge theory, center symmetry as a physical one-form global symmetry depends on the spectrum of genuine line operators, matter content, and global form of the gauge group. The group-theoretic center is only part of the story.

**“Gauging a higher-form symmetry is just adding another Maxwell field.”** Sometimes it can be represented by higher-form gauge fields, but the operation is more general: it changes background sums, line/surface operator genuineness, quotient data, and dual symmetry structure.

**“Generalized symmetry always means non-invertible symmetry.”** No. Higher-form symmetries can be perfectly group-like and invertible. Non-invertible and categorical symmetries are treated in the next chapter.

## Boundaries

This chapter is the canonical home for higher-form and closely related generalized global symmetries. It is not the canonical home for every topic involving extended objects.

Defects themselves belong to [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/). That chapter defines Wilson lines, ’t Hooft lines, surface operators, disorder operators, twist operators, defect fusion, and line-operator algebras. This chapter asks when such objects carry generalized global charges.

Full Yang–Mills dynamics, the confinement problem, QCD, and the Standard Model belong to Gauge Theories and the Standard Model and Nonperturbative QFT. Here, center symmetry and line operators are used as symmetry diagnostics, not as a complete theory of confinement.

The general theory of anomalies belongs to Anomalies and ’t Hooft Anomalies and Anomaly Matching. This chapter introduces higher-form anomalies only as part of the symmetry structure; detailed anomaly polynomials, inflow, and matching live later.

Non-invertible symmetry and categorical symmetry belong to Non-Invertible and Categorical Symmetries. Symmetry TFT and relative QFT belong to Symmetry TFT and Anomaly Inflow. This chapter prepares the reader for those ideas by making higher-form topological operators familiar first.

The mathematical foundations of differential cohomology, higher bundles, higher categories, and extended TQFT belong to the Mathematical Toolkit and Mathematical and Rigorous QFT. This chapter uses the minimum mathematics needed for QFT reasoning.

## Where to go next

After this chapter, read Non-Invertible and Categorical Symmetries if your goal is modern symmetry beyond groups. The most important bridge is this: once symmetry operators are topological defects, it is natural to ask whether their fusion must be group multiplication. The answer is no, and that is the doorway to non-invertible symmetry.

Read Symmetry TFT and Anomaly Inflow if your goal is a bulk-boundary packaging of symmetry, gauging, defects, and anomalies. Higher-form symmetries are especially naturally encoded by topological bulk theories and boundary conditions.

Read Topological Quantum Field Theory if you want metric-independent examples where higher-form symmetry, defect fusion, and topological correlation functions can often be computed exactly.

Read Symmetry in Phases of Matter if your goal is center symmetry, generalized symmetry breaking, topological order, SPT/SET distinctions, or condensed-matter realizations. Higher-form symmetry is one of the cleanest bridges between gauge theory and phases of matter.

For a gauge-theory route, continue to Center Symmetry, Electric and Magnetic One-Form Symmetries, then return to Topological Terms and the Nonperturbative QFT volume for Wilson loops, confinement diagnostics, and theta vacua.

## References

### Core references

- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” *Journal of High Energy Physics* **2015**, 172.
- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality,” for global forms, line operators, and higher-form gauge fields.
- Ofer Aharony, Nathan Seiberg, and Yuji Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line operators, global form, and one-form symmetry in gauge theory.

### Gauge-theory and defect background

- Kenneth Wilson, “Confinement of Quarks,” for Wilson loops as gauge-theory observables.
- Alexander M. Polyakov, *Gauge Fields and Strings*, especially Chs. 3, 5, 6, and 7, for strong coupling, topology of gauge fields, non-Abelian phase factors, and loop dynamics.
- Mark Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice gauge theory, and confinement orientation.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, §25.2, for gauge invariance and Wilson lines in Yang–Mills theory.

### Mathematical and condensed-matter complements

- Mikio Nakahara, *Geometry, Topology and Physics*, for homotopy, bundles, monopoles, instantons, and characteristic classes.
- Theodore Frankel, *The Geometry of Physics*, for differential forms, bundles, connections, Chern forms, and physics examples.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Chs. 8 and 10, for topological terms, homotopy, Chern–Simons terms, and gauge-theory viewpoints in matter systems.

## Version history

- **2026-06-20:** Initial polished chapter overview. Added reading path, linking/topological-operator figure, boundaries, common confusions, and handoff to non-invertible symmetry and symmetry TFT.
