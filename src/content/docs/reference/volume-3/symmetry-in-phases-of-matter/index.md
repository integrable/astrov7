---
title: "Symmetry in Phases of Matter"
description: "Chapter overview for symmetry breaking, SPT phases, SET phases, anomaly-boundary correspondence, higher-form symmetry, fracton previews, and response theory."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Altland–Simons Chs. 5, 8, 10; Coleman, Aspects of Symmetry; Wilson–Kogut; Gaiotto–Kapustin–Seiberg–Willett; standard SPT/SET and topological-order references."
topics:
  - symmetry breaking
  - phases of matter
  - SPT phases
  - SET phases
  - topological order
  - anomaly-boundary correspondence
canonicalTopics:
  - symmetry-in-phases
  - landau-order
  - spt-phase
  - set-phase
  - anomaly-boundary-correspondence
researchStatus:
  established:
    - "Landau symmetry breaking, order parameters, Goldstone modes, topological response, and many basic topological phases are standard parts of modern field-theoretic condensed matter and QFT."
  active:
    - "Symmetry enrichment, crystalline and subsystem symmetries, fracton order, higher-form symmetry in matter, and anomaly-based classification remain active research areas."
---

Symmetry in Phases of Matter is the chapter in the Symmetry, Anomalies, and Topology volume where symmetry stops being only a property of equations and becomes a way of organizing phases. The same symmetry group can be unbroken, explicitly broken, spontaneously broken, gauged, anomalous, realized projectively on excitations, or hidden in a topological response.

The chapter connects three languages that are often taught separately. Landau theory describes phases by local order parameters and symmetry breaking. Topological field theory describes phases by robust long-distance data such as anyons, ground-state degeneracy, and response actions. Modern symmetry language describes phases by how ordinary, higher-form, crystalline, subsystem, and sometimes non-invertible symmetry structures act on operators, defects, and boundaries.

The guiding slogan is:

$$
\text{phase} = \text{long-distance organization of symmetry, excitations, defects, and response}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![Map of symmetry-based phases, from Landau symmetry breaking to SPT phases, SET phases, topological order, anomaly-boundary correspondence, higher-form symmetry, fracton previews, and response theory.](/figures/symmetry-anomalies-topology/symmetry-phases-of-matter-map.svg)

<figcaption>

A rough map of the chapter. Landau theory starts with local order parameters and broken symmetry. Modern phases also include short-range-entangled SPT phases, long-range-entangled topological orders, symmetry-enriched topological orders, higher-form symmetry diagnostics, fracton-style subsystem structures, and response theories.

</figcaption>
</figure>

Read this chapter after the ordinary symmetry, anomaly, topological-term, defect, higher-form, non-invertible, and TQFT chapters if you want to see how those structures appear in actual phases of matter. Read it earlier if your motivation comes from condensed matter, quantum information, statistical mechanics, or lattice models.

## Prerequisites

You should know the basic distinction between explicit and spontaneous symmetry breaking, what an order parameter is, and why a conserved symmetry can impose selection rules. It is useful to have read the chapters on [Ordinary Global Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/), [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/), [Topological Terms](/symmetry-anomalies-topology/topological-terms/), [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/), [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/), and [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/).

For a first pass, you only need the following dictionary:

| Word | Minimal meaning |
|---|---|
| Order parameter | A local or sometimes extended observable whose expectation value distinguishes phases. |
| Symmetry breaking | The theory has the symmetry, but the chosen state does not. |
| SPT phase | A gapped short-range-entangled phase nontrivial only when a symmetry is enforced. |
| Topological order | A long-range-entangled phase with intrinsic topological data such as anyons or ground-state degeneracy. |
| SET phase | A topologically ordered phase enriched by a global symmetry action. |
| Response theory | An effective action for background fields encoding robust phase data. |

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Landau Symmetry Breaking](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/landau-symmetry-breaking/) | The local-order-parameter paradigm: phases classified by symmetry breaking, order-parameter manifolds, domain walls, Goldstone modes, and effective potentials. |
| 2 | Symmetry-Protected Topological Phases | Gapped short-range-entangled phases that require symmetry to remain distinct from a trivial product state. |
| 3 | Symmetry-Enriched Topological Phases | Long-range-entangled topological orders with additional symmetry fractionalization, anyon permutation, and anomaly constraints. |
| 4 | Topological Order Preview | Intrinsic topological order: anyons, long-range entanglement, topological ground-state degeneracy, and effective TQFT data. |
| 5 | Anomaly-Boundary Correspondence | Why anomalous boundary theories signal one-higher-dimensional bulk phases. |
| 6 | Higher-Form Symmetry in Matter | How line and surface operators, flux conservation, confinement diagnostics, and generalized order parameters diagnose phases. |
| 7 | Fracton Symmetry Preview | Subsystem symmetry, restricted mobility, foliation ideas, and why ordinary symmetry language is not enough. |
| 8 | Response Theory Preview | Background-field effective actions, Hall response, theta terms, Chern–Simons response, mixed responses, and quantization. |

After this path, you should be able to say which part of a phase is Landau order, which part is intrinsic topological order, which part is symmetry enrichment, and which part is anomaly or response data.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Landau order parameter | A local observable whose expectation value transforms nontrivially under a symmetry. | Landau Symmetry Breaking. |
| Residual symmetry | The subgroup $H\subset G$ preserving the chosen order parameter. | Goldstone modes, domain walls, cosets. |
| Vacuum manifold | The space of degenerate symmetry-related vacua, often $G/H$ for continuous symmetry. | Defects, textures, sigma models. |
| Short-range entanglement | A gapped phase deformable to a product state if symmetries are ignored. | SPT phases. |
| Long-range entanglement | Entanglement structure not removable by finite-depth local circuits. | Topological order. |
| Symmetry fractionalization | Anyons or defects carry symmetry quantum numbers not available to strictly local excitations. | SET phases. |
| Anomalous boundary | A boundary theory that cannot exist as a standalone system with the same symmetry realization. | Anomaly-boundary correspondence. |
| Higher-form order parameter | An extended operator, such as a Wilson loop, whose scaling law diagnoses a phase. | Higher-form symmetry in matter. |
| Response action | A robust effective action for nondynamical background fields. | SPT phases and response theory. |

The main conceptual move is to stop expecting one diagnostic to do everything. A magnet is well described by a local order parameter. A fractional quantum Hall state is not. A topological insulator may have no intrinsic topological order but still cannot be trivialized while preserving its symmetry. A spin liquid can have intrinsic topological order and also a nontrivial symmetry enrichment.

## Common confusions

**“Every phase is classified by a local order parameter.”** Landau theory is powerful but incomplete. Topological order, SPT phases, and many gauge-theoretic phases are not classified by local order parameters alone.

**“Topological means no symmetry is involved.”** Some topological phases are intrinsic and do not require symmetry. SPT phases are topological in a symmetry-protected sense: remove or break the symmetry and the distinction can disappear.

**“An SPT phase has topological order.”** In the common condensed-matter terminology, an SPT phase is short-range entangled and has no intrinsic topological order. It is nontrivial because of symmetry and boundary/anomaly structure.

**“SET means SPT plus topological order.”** This slogan is too crude. An SET phase is topological order together with symmetry action on its anyons, defects, and fusion/braiding data. Some enrichments cannot be obtained by simply stacking an SPT.

**“Higher-form symmetry is only high-energy jargon.”** Wilson loops, vortex lines, magnetic flux conservation, and confinement diagnostics are natural higher-form symmetry objects in phases of matter.

**“A response action is just a transport coefficient.”** Sometimes it is, but the most robust response terms are quantized topological actions for background fields. They encode anomaly, SPT, Hall, theta, or mixed response data.

## Boundaries

This chapter is the canonical home for symmetry-based phase structure inside this volume. It does not replace nearby volumes and chapters.

The general machinery of spontaneous symmetry breaking belongs to [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/). This chapter uses that machinery to organize phases of matter.

The general theory of anomalies belongs to [Anomalies](/symmetry-anomalies-topology/anomalies/) and [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/). This chapter focuses on how anomaly data appears as boundary constraints and phase diagnostics.

The full theory of higher-form symmetry belongs to [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/). This chapter uses higher-form symmetry to discuss confinement, deconfinement, flux conservation, and matter phases.

The detailed condensed-matter model zoo belongs to Matter, Statistical Physics, and Quantum Information. This chapter gives the symmetry/anomaly/topology viewpoint, not a full course on materials, band theory, or many-body methods.

The theorem-first classification of phases, tensor categories, and operator algebras belongs to Mathematical and Rigorous QFT. This chapter uses those ideas only to the extent needed for physics.

## Where to go next

For a traditional route, read Landau Symmetry Breaking, then return to Spontaneous Symmetry Breaking for detailed Goldstone physics. For topological phases, read SPT Phases and Anomalies, Symmetry-Enriched Topological Phases, and Topological Order Preview. For anomaly-oriented readers, go from Anomaly-Boundary Correspondence to Symmetry TFT and Anomaly Inflow. For gauge-theory readers, read Higher-Form Symmetry in Matter and then revisit Wilson loops, center symmetry, and confinement diagnostics.

The cleanest conceptual sequence is:

$$
\text{Landau order}
\longrightarrow
\text{SPT response}
\longrightarrow
\text{intrinsic topological order}
\longrightarrow
\text{symmetry enrichment}
\longrightarrow
\text{anomaly constraints}.
$$

## References

- L. D. Landau and E. M. Lifshitz, *Statistical Physics*, for the classic symmetry-breaking and order-parameter viewpoint.
- S. Coleman, *Aspects of Symmetry*, especially “Secret Symmetry,” for the QFT version of spontaneous symmetry breaking.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” for the RG and critical-phenomena viewpoint.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, especially the chapters on broken symmetry, RG, topological field theory, relativistic field theory, and gauge theory.
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*, for topological order, quantum order, and effective field theory in matter systems.
- X. Chen, Z.-C. Gu, Z.-X. Liu, and X.-G. Wen, “Symmetry-Protected Topological Orders and the Group Cohomology of Their Symmetry Group,” for a standard group-cohomology entry into bosonic SPT phases.
- M. Barkeshli, P. Bonderson, M. Cheng, and Z. Wang, “Symmetry Fractionalization, Defects, and Gauging of Topological Phases,” for SET phases and defect-based symmetry enrichment.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for higher-form symmetry and anomaly connections.

## Version history

- **2026-06-23:** Initial polished chapter overview. Opened the Symmetry in Phases of Matter chapter and positioned Landau order, SPT phases, SET phases, topological order, higher-form symmetry, anomaly-boundary correspondence, fracton previews, and response theory as a coherent reading path.
