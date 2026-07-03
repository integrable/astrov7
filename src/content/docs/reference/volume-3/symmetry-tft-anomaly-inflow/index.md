---
title: "Symmetry TFT and Anomaly Inflow"
description: "Chapter overview for symmetry topological field theory, anomaly inflow, invertible phases, boundary conditions, gauging, defects, and relative QFT."
sidebar:
  label: "Overview"
  order: 0
level: Research
status: "Polished draft"
source: "Kapustin–Seiberg; Freed–Hopkins; Gaiotto–Kapustin–Seiberg–Willett; modern SymTFT and generalized-symmetry literature."
topics:
  - symmetry TFT
  - anomaly inflow
  - invertible field theory
  - SPT phases
  - boundary conditions
  - generalized symmetry
  - relative QFT
canonicalTopics:
  - symmetry-tft
  - anomaly-inflow
  - invertible-field-theory
  - spt-phase
  - relative-qft
  - boundary-condition-gauging
researchStatus:
  established:
    - "Anomaly inflow and invertible one-higher-dimensional field theories are standard ways to encode ’t Hooft anomalies."
    - "For finite and topological generalized symmetries, the SymTFT viewpoint gives a powerful unifying language for symmetry defects, charges, gauging, and boundary conditions."
  active:
    - "Continuous symmetries, spacetime symmetries, non-invertible symmetries, nonsemisimple settings, and fully extended categorical formulations of SymTFT remain active research areas."
---

Symmetry TFT and Anomaly Inflow is the chapter where symmetry data is lifted one dimension higher.

The guiding idea is that a $d$-dimensional QFT with symmetry can often be understood as living on the boundary of a $(d+1)$-dimensional topological field theory. The bulk topological theory is not an extra dynamical spacetime. It is a bookkeeping device, and sometimes a physical inflow theory, whose topological defects encode symmetry operators, charges, anomalies, gaugings, and boundary conditions.

The central slogan is:

$$
\text{symmetry data of }\mathcal T_d
\quad\longleftrightarrow\quad
\text{bulk topological theory }\mathfrak S_{d+1}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![A slab picture of symmetry TFT: a (d+1)-dimensional topological bulk sits between a physical QFT boundary and a topological/reference boundary; bulk defects encode symmetry, anomaly inflow, and gauging choices.](/figures/symmetry-anomalies-topology/symmetry-tft-sandwich.svg)

<figcaption>

The SymTFT picture represents a $d$-dimensional theory $\mathcal T$ as a boundary condition for a $(d+1)$-dimensional topological theory $\mathfrak S$. Bulk topological defects encode symmetry operators and charges. Different topological boundary conditions encode different choices such as gauging, orbifolding, or changing the global form.

</figcaption>
</figure>

This chapter is advanced because it unifies several ideas that are often learned separately: background fields, ’t Hooft anomalies, SPT phases, topological defects, gauging, higher-form symmetry, non-invertible symmetry, and relative QFT.

## Prerequisites

You should know [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/), [Topological Terms](/symmetry-anomalies-topology/topological-terms/), [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/), [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/), and [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/).

The main mathematical prerequisites are differential forms, basic cohomology, the idea of a topological field theory, and the ability to think of a QFT as a boundary condition. You do not need a full course in extended TQFT or higher categories for the first pass.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Symmetry TFT Idea | The basic slab picture: a $d$-dimensional QFT as a boundary condition of a $(d+1)$-dimensional topological theory. |
| 2 | Bulk-Boundary Viewpoint | How symmetry operators, charged objects, and background fields appear as bulk defects ending on boundaries. |
| 3 | Anomaly Inflow | How a non-invariant boundary variation is cancelled by a bulk topological term. |
| 4 | Invertible Field Theories | Why many anomalies are encoded by invertible one-higher-dimensional theories. |
| 5 | SPT Phases and Anomalies | The relation between anomalous boundaries and symmetry-protected topological phases. |
| 6 | Boundary Conditions and Gaugings | How different topological boundary conditions encode gauging, orbifolding, and global-form choices. |
| 7 | Defects from the Bulk | How topological defects in the SymTFT descend to symmetry operators, duality defects, and charged operators in the boundary QFT. |
| 8 | Relative QFT: Preview | Why some QFTs are naturally defined only relative to a bulk topological theory. |
| 9 | Examples of Symmetry TFT | Finite groups, higher-form symmetries, Dijkgraaf–Witten theories, BF theories, Chern–Simons examples, and non-invertible previews. |

After this path, you should be able to read a modern paper that says “the symmetry is encoded by a SymTFT” and understand what information is being packaged.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Background field | A nondynamical source for a global symmetry. | The first probe of anomaly data. |
| ’t Hooft anomaly | An obstruction to gauging a global symmetry. | It is represented by inflow from one higher dimension. |
| Invertible field theory | A field theory with one-dimensional state spaces and invertible partition functions. | Standard home for anomaly phases and SPT responses. |
| Symmetry TFT | A topological theory whose defects encode symmetry data of a boundary QFT. | Packages symmetry operators, charges, and gaugings. |
| Physical boundary | The boundary condition representing the QFT of interest. | Where local dynamics lives. |
| Topological boundary | A gapped/reference boundary condition for the SymTFT. | Encodes a choice of absolute theory, gauging, or global form. |
| Bulk defect | A topological operator in the SymTFT. | Becomes a symmetry operator, charge, or interface for the boundary theory. |
| Anomaly inflow | Cancellation of a boundary anomaly by a bulk variation. | Explains how anomalous global symmetries can exist on boundaries. |
| Relative QFT | A theory defined only together with a bulk topological theory. | Clarifies theories with nontrivial anomaly or global-form dependence. |
| Gauging boundary | A boundary condition or interface implementing a sum over symmetry backgrounds. | Makes gauging a geometric operation. |

The most important shift is this:

$$
\text{symmetry as operators inside }\mathcal T_d
\quad\leadsto\quad
\text{symmetry as bulk topological data in }\mathfrak S_{d+1}.
$$

## Common confusions

**“The SymTFT is the same as the QFT.”** No. The SymTFT is topological and one dimension higher. The physical QFT is a boundary condition or boundary sector. The SymTFT packages symmetry data, not the full local dynamics.

**“Anomaly inflow means the anomalous theory is inconsistent.”** A gauge anomaly in a redundancy is dangerous. A ’t Hooft anomaly of a global symmetry is allowed and can be consistently realized on the boundary of a bulk invertible theory.

**“Every SymTFT is invertible.”** No. Invertible field theories encode many anomaly phases. A full SymTFT for non-invertible or categorical symmetry is often non-invertible and contains a richer spectrum of topological defects.

**“Gauging is just deleting symmetry.”** Gauging changes the boundary condition and often produces dual symmetry data. In the SymTFT picture, gauging is a controlled change of topological boundary condition or an interface.

**“The bulk is physical spacetime.”** Usually the bulk is an auxiliary topological device. In condensed matter or holographic settings it can sometimes be realized physically, but the abstract SymTFT construction should not be confused with ordinary extra dimensions.

**“An anomaly is just a local divergence equation.”** Some anomalies are visible as local current nonconservation. The more invariant definition is obstruction to gauging, and the inflow/SymTFT picture captures global, discrete, higher-form, and non-invertible anomaly data as well.

## Boundaries

This chapter is the canonical home for the SymTFT and anomaly-inflow viewpoint. It does not replace the anomaly, defect, or higher-form chapters.

The [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter explains perturbative, global, gravitational, trace, consistent, covariant, polynomial, and descent viewpoints.

The [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/) chapter explains obstruction to gauging and RG invariance. This chapter repackages those obstructions as one-higher-dimensional topological data.

The [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) chapter explains charged extended operators and background higher-form fields. This chapter explains how that data can be encoded in a bulk topological theory.

The [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) chapter develops defect fusion and categorical actions. This chapter explains how those categories often appear as boundary categories or centers of a bulk topological theory.

The [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/) chapter studies TQFTs as theories in their own right. This chapter uses TQFTs as symmetry-packaging devices for ordinary QFTs.

## Where to go next

For anomaly-focused readers, read Symmetry TFT Idea, Anomaly Inflow, Invertible Field Theories, and SPT Phases and Anomalies.

For generalized-symmetry readers, read Symmetry TFT Idea, Boundary Conditions and Gaugings, Defects from the Bulk, and Examples of Symmetry TFT.

For non-invertible readers, read the non-invertible chapter first, then return here. The natural sequence is:

$$
\text{defect fusion}
\longrightarrow
\text{categorical symmetry}
\longrightarrow
\text{bulk topological theory}
\longrightarrow
\text{boundary conditions}.
$$

For readers coming from condensed matter, the best route is SPT Phases and Anomalies, then Anomaly Inflow, then Examples of Symmetry TFT. For readers coming from gauge theory, start with Boundary Conditions and Gaugings and Examples of Symmetry TFT.

## References

### First-pass references

- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for the global-form, line-operator, and TQFT-coupling viewpoint.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for background fields, gauging, anomalies, and higher-form operators.
- Freed and Hopkins, “Reflection Positivity and Invertible Topological Phases,” for invertible phases and anomaly classification.
- Witten, “Global Aspects of Current Algebra,” for the classic anomaly-inflow/Wess–Zumino–Witten perspective.

### Modern SymTFT and categorical references

- Recent lecture notes and reviews by Schäfer-Nameki and collaborators on SymTFT, generalized symmetries, and non-invertible symmetries.
- Papers on brane constructions of SymTFT and generalized charges, where bulk topological defects encode symmetry generators and charges.
- Work on Dijkgraaf–Witten, BF, Chern–Simons, and higher-form examples as concrete SymTFT models.

### Nearby mathematical references

- Nakahara, *Geometry, Topology and Physics*, for bundles, characteristic classes, monopoles, instantons, and topological terms.
- Frankel, *The Geometry of Physics*, for differential forms, bundles, connections, Chern forms, and gauge-field geometry.
- Etingof, Gelaki, Nikshych, and Ostrik, *Tensor Categories*, for the categorical language underlying fusion, centers, and module categories.

## Version history

- **2026-06-20:** Initial polished chapter overview. Introduced the SymTFT slab picture, anomaly inflow, invertible field theories, SPT boundaries, topological boundary conditions, bulk defects, gauging, and relative QFT.
