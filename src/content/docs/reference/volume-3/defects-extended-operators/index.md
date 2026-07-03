---
title: "Defects and Extended Operators"
description: "Chapter overview for local and extended operators, Wilson lines, 't Hooft lines, surface operators, disorder operators, twist operators, boundaries, interfaces, defect fusion, and line-operator algebras."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov Ch. 7; Srednicki §82; Gaiotto–Kapustin–Seiberg–Willett; standard CFT, gauge-theory, and TQFT defect references."
topics:
  - defects
  - extended operators
  - Wilson lines
  - "'t Hooft lines"
  - surface operators
  - disorder operators
  - twist operators
  - boundaries
  - interfaces
  - defect fusion
canonicalTopics:
  - defect-operator
  - extended-operator
  - wilson-line
  - thooft-line
  - surface-operator
  - disorder-operator
  - defect-fusion
researchStatus:
  established:
    - "Extended operators and defects are standard observables and probes in QFT, especially in gauge theory, CFT, statistical field theory, and topological field theory."
    - "Wilson lines, 't Hooft lines, disorder operators, twist defects, boundaries, and interfaces often give the cleanest operator-language version of topological sectors and generalized symmetries."
  active:
    - "Modern research studies defects through higher-form symmetries, non-invertible fusion, categorical symmetry, symmetry TFT, boundary anomalies, and extended TQFT structures."
---

Defects and Extended Operators is the chapter in the Symmetry, Anomalies, and Topology volume where observables stop being only local insertions. Fields can be probed by points, but also by lines, surfaces, walls, boundaries, interfaces, and disorder insertions. Those extended probes often see global information that local operators miss.

The previous chapter described topological sectors and solitonic charges as configurations. This chapter develops the operator version: Wilson lines detect gauge holonomy, ’t Hooft lines impose magnetic singularities, surface operators measure or create flux, twist operators impose monodromy, and domain walls or interfaces implement transformations between theories.

The guiding slogan is:

$$
\text{defect} = \text{operator supported on a submanifold, possibly defined by singular boundary data}.
$$

<figure class="doc-figure" style="--figure-width: 60rem;">

![Roadmap diagram showing local operators, line operators, surface operators, walls/interfaces, boundaries, disorder operators, and defect fusion as connected parts of the defects and extended operators chapter.](/figures/symmetry-anomalies-topology/defects-extended-operators-roadmap.svg)

<figcaption>

Extended operators organize QFT by support dimension and by how they are defined. Some are ordinary insertions integrated over submanifolds; some are disorder defects defined by prescribed singularities or branch cuts; some are topological defects whose deformation and fusion encode symmetry.

</figcaption>
</figure>

This chapter is placed before Higher-Form and Generalized Symmetries because higher-form symmetries are naturally diagnosed by extended charged operators. It is also placed before Non-Invertible and Categorical Symmetries because the categorical language begins with a simple observation: topological defects can be fused.

## Prerequisites

You should know [Ordinary Global Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/), [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/), [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), [Gauge Redundancy and BRST](/symmetry-anomalies-topology/gauge-redundancy-brst/), and [Topological Sectors and Solitonic Charges](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/).

For the first pass, it is enough to know what gauge holonomy is, why gauge-invariant operators must be dressed carefully, how a charged particle couples to a connection, and how a defect can be linked by a surrounding sphere or surface. Differential-form notation and homotopy language help, but the chapter introduces the operator viewpoint from scratch.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Local Versus Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/local-versus-extended-operators/) | The basic taxonomy: support dimension, codimension, topological versus non-topological defects, order versus disorder definitions. |
| 2 | [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/) | The canonical line operator built from gauge holonomy, with representation labels and confinement diagnostics. |
| 3 | [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) | Magnetic line defects defined by singular boundary conditions, duality, and line-operator classification. |
| 4 | [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) | Codimension-two and higher-dimensional defects, flux insertions, monodromy, and higher-form symmetry probes. |
| 5 | [Disorder Operators](/symmetry-anomalies-topology/defects-extended-operators/disorder-operators/) | Operators defined by changing allowed field configurations rather than by inserting a local polynomial. |
| 6 | [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/) | Branch cuts, replica defects, orbifold twists, symmetry twists, and monodromy conditions. |
| 7 | [Domain Walls as Defects](/symmetry-anomalies-topology/defects-extended-operators/domain-walls-as-defects/) | Walls as operators, interfaces between phases or theories, and symmetry/domain-wall actions on observables. |
| 8 | [Boundaries and Interfaces](/symmetry-anomalies-topology/defects-extended-operators/boundaries-and-interfaces/) | Boundary conditions as part of the QFT data, boundary degrees of freedom, folding tricks, and anomaly constraints. |
| 9 | [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) | What it means to bring defects together, when fusion is topological, and why fusion is the doorway to categorical symmetry. |
| 10 | [Defect Correlation Functions](/symmetry-anomalies-topology/defects-extended-operators/defect-correlation-functions/) | How to compute and interpret correlators involving extended insertions, including linking, framing, and defect-local operators. |
| 11 | [Line-Operator Algebras](/symmetry-anomalies-topology/defects-extended-operators/line-operator-algebras/) | Operator products, mutual locality, electric/magnetic charge lattices, one-form symmetry, and duality constraints. |

After this path, the central question changes from “what field configuration is allowed?” to “what operators can probe, create, or transform those configurations?”

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Support dimension | A defect may live on a point, line, surface, wall, boundary, or general submanifold $M_p$. | Local Versus Extended Operators. |
| Codimension | The dimension of a small linking sphere around the defect controls possible charges and singular boundary data. | Disorder Operators, Surface Operators. |
| Wilson line | A gauge-invariant holonomy operator, usually labeled by a representation. | Wilson Lines, Center Symmetry. |
| ’t Hooft line | A magnetic disorder line defined by prescribed monopole-like singularity around the line. | ’t Hooft Lines, Electric and Magnetic One-Form Symmetries. |
| Surface operator | An operator supported on a surface, often creating or measuring flux, monodromy, or two-form background data. | Surface Operators, Higher-Form Symmetries. |
| Disorder operator | An operator specified by boundary conditions on fields near its support rather than by a local expression in fields. | Vortices, Monopoles, Twist Operators. |
| Twist operator | A defect implementing a symmetry action or branch condition when fields encircle or cross it. | Orbifolds, Replica Trick, Non-Invertible Symmetry. |
| Topological defect | A defect whose correlation functions are invariant under smooth deformations avoiding other insertions. | Defect Fusion, Non-Invertible Symmetry. |
| Defect fusion | The operation of bringing two compatible defects together and replacing them by an effective sum or product of defects. | Categorical Symmetry, TQFT. |
| Defect-local operator | A local operator living on the defect worldvolume rather than in the ambient bulk. | Boundaries, Interfaces, Defect CFT. |

The chapter uses “defect” broadly. Some defects are dynamical objects, some are probe operators, some are boundary conditions, and some are topological symmetry operators. The point of the chapter is to keep those roles distinct while showing how they talk to each other.

## Common confusions

**“An extended operator is just a smeared local operator.”** Sometimes, but not usually. A Wilson line is a path-ordered exponential of a connection, an ’t Hooft line is a singular boundary condition, and a twist operator changes monodromy. These cannot be reduced to ordinary smearing of local polynomials.

**“Defects must be physical branes or solitons.”** A defect can be a probe insertion, an imposed boundary condition, a topological operator, or a dynamical excitation. The same geometric support can play different roles in different theories.

**“Gauge-variant line integrals are observables.”** A line integral of $A$ is not automatically gauge invariant. Gauge-invariant line operators require traces, endpoints attached to charged fields, boundary conditions, or other dressing data.

**“Wilson and ’t Hooft lines are dual in every theory.”** They are electric and magnetic analogues, but the precise line-operator lattice depends on the gauge group global form, matter content, spin structure, and allowed endpoints.

**“Topological means tensionless or dynamically free.”** Topological means deformation-invariant as an operator statement. It does not mean there is no energy cost for a physical soliton, nor does it mean every defect is topological.

**“Fusion is always group multiplication.”** Invertible topological defects fuse like group elements. Non-invertible defects can fuse into sums of defects or more general algebraic objects. That is why fusion quickly leads to categorical language.

## Boundaries

This chapter is the canonical home for the operator viewpoint on defects and extended observables. It does not replace the chapters around it.

Topological solitons as field configurations belong to [Topological Sectors and Solitonic Charges](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/). This chapter starts when those configurations are treated as insertions, probes, worldvolumes, or boundary conditions in correlation functions.

Higher-form symmetry belongs to [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/). This chapter builds the extended-operator vocabulary needed there.

Non-invertible and categorical symmetry belongs to [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/). This chapter introduces the fusion and topological-defect ideas that make that language natural.

Detailed confinement physics, lattice Wilson loops, Polyakov loops, and phase diagrams belong to the Nonperturbative QFT and Gauge Theories volumes. Here Wilson loops and line operators are treated as symmetry/topology objects.

Full boundary CFT, defect CFT, and conformal bootstrap of defects belong to the CFT and Bootstrap volume. Here the goal is to explain what defects are and how they fit into the symmetry/anomaly/topology story.

## Where to go next

After this chapter, read [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) to see how extended operators become charged objects under higher-form symmetries. Then read [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) to see how topological defects can encode symmetry structures beyond groups.

For anomaly-focused readers, go from this chapter to [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/). For gauge-theory readers, use this chapter as the conceptual bridge to Wilson loops, confinement diagnostics, electric/magnetic duality, and line-operator classification.

## References

### Standard first pass

- Wilson, “Confinement of Quarks,” for the Wilson-loop viewpoint on gauge theories.
- Polyakov, *Gauge Fields and Strings*, especially the chapters on non-Abelian phase factors, loop dynamics, and topology of gauge fields.
- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice theory, and confinement orientation.
- Coleman, *Aspects of Symmetry*, for symmetry, soliton, instanton, and gauge-theory intuition.

### Modern symmetry and defect references

- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for charged extended operators, topological symmetry operators, higher-form Ward identities, gauging, and anomalies.
- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for global form, line operators, and higher-form symmetry refinements.
- Aharony, Seiberg, and Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line-operator lattices and global-form choices.

### Nearby topics

- Nakahara, *Geometry, Topology and Physics*, for holonomy, bundles, monopoles, and characteristic classes.
- Altland and Simons, *Condensed Matter Field Theory*, for topological defects, response, and condensed-matter field-theory examples.
- Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*, for twist fields, defect lines, and two-dimensional examples.

## Version history

- **2026-06-18:** Initial polished draft.
