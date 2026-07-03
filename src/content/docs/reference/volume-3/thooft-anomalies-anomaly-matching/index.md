---
title: "’t Hooft Anomalies and Anomaly Matching"
description: "Chapter overview for ’t Hooft anomalies, anomaly matching, obstruction to gauging, inflow, boundaries, and symmetry-protected phases in the Symmetry, Anomalies, and Topology volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "’t Hooft anomaly matching; anomaly inflow; Wess–Zumino consistency; Gaiotto–Kapustin–Seiberg–Willett generalized symmetries; Coleman; Srednicki; Schwartz; Weinberg; modern invertible-field-theory viewpoint."
topics:
  - thooft anomalies
  - anomaly matching
  - obstruction to gauging
  - anomaly inflow
  - RG invariance
  - global symmetries
  - symmetry-protected phases
canonicalTopics:
  - thooft-anomalies
  - anomaly-matching
  - obstruction-to-gauging
  - anomaly-inflow
  - spt-boundary-anomaly
researchStatus:
  established:
    - "’t Hooft anomalies are invariant obstruction data for global symmetries and must be reproduced by any infrared description preserving the symmetry."
    - "Anomaly matching is a robust nonperturbative constraint on RG flow, phases, dualities, and boundary dynamics."
  active:
    - "Modern work extends anomaly matching to higher-form, higher-group, subsystem, non-invertible, crystalline, fermionic, and symmetry-TFT settings."
---

’T Hooft Anomalies and Anomaly Matching is the chapter in the Symmetry, Anomalies, and Topology volume where anomalies stop being only a failure of a current equation and become a diagnostic of possible long-distance physics.

The previous chapter explained how anomalies arise and how local perturbative anomalies are computed. This chapter asks a different question: once a global symmetry has an anomaly, what does that force the infrared theory to do?

The answer is one of the strongest pieces of nonperturbative reasoning in QFT: an anomaly of a global symmetry is an obstruction to gauging, and that obstruction cannot disappear along RG flow. If the UV theory has it, the IR must match it by massless degrees of freedom, topological order, spontaneous symmetry breaking, gapless modes, boundary states, or some other nontrivial realization.

$$
\text{UV anomaly} = \text{IR anomaly},
\qquad
\text{if the symmetry is preserved along the flow}.
$$

<figure class="doc-figure" style="--figure-width: 60rem;">

![Roadmap diagram showing a global symmetry coupled to backgrounds, an obstruction to gauging, RG-invariant anomaly data, and possible infrared matching mechanisms.](/figures/symmetry-anomalies-topology/thooft-anomaly-matching-roadmap.svg)

<figcaption>

A ’t Hooft anomaly is not an inconsistency of the original theory. It is an obstruction to gauging a global symmetry. Because it can be represented by background-field or inflow data, the same obstruction must be visible in every symmetry-preserving infrared description.

</figcaption>
</figure>

## Prerequisites

You should first understand [Ordinary Global Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/), [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), and the [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter.

The most important immediate prerequisites are [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

A reader who knows only triangle anomalies can enter this chapter, but should keep one translation in mind:

$$
\text{gauge anomaly} = \text{fatal for a dynamical gauge redundancy},
$$

while

$$
\text{’t Hooft anomaly} = \text{allowed for a global symmetry, but obstructs gauging it}.
$$

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | ’t Hooft Anomalies | The definition of a ’t Hooft anomaly as background-field non-invariance or obstruction to gauging. |
| 2 | Anomaly Matching | The UV–IR matching principle and the logic behind using anomalies as nonperturbative constraints. |
| 3 | Anomalies as RG Invariants | Why anomaly classes are unchanged by integrating out massive modes, up to counterterms and decoupled sectors. |
| 4 | Obstruction to Gauging | The clean operational test: try to couple to backgrounds and sum over them. |
| 5 | Anomaly Inflow: Preview | The one-higher-dimensional picture that makes matching geometrically transparent. |
| 6 | Anomalies and Boundaries | How boundary degrees of freedom, edge modes, and relative theories carry anomaly data. |
| 7 | Anomalies and Symmetry-Protected Phases | The relationship between anomalous boundary theories and one-higher-dimensional SPT or invertible phases. |
| 8 | Examples of Anomaly Matching | Worked examples: chiral symmetry in QCD-like theories, discrete anomalies, higher-form anomalies, and duality tests. |

Readers mainly interested in particle theory should focus on Steps 1–4 and 8. Readers heading toward generalized symmetry, condensed matter, or symmetry TFT should include Steps 5–7 carefully.

## Landmarks

The first landmark is the **background-field definition**. A global symmetry $G$ is tested by coupling the theory to a nondynamical background $G$ gauge field $A$. If no choice of local counterterms makes

$$
Z[A]
$$

invariant under background gauge transformations, then the symmetry has a ’t Hooft anomaly.

The second landmark is the **obstruction-to-gauging test**:

$$
\text{nontrivial ’t Hooft anomaly}
\quad\Longleftrightarrow\quad
\text{cannot gauge the symmetry as an ordinary standalone operation}.
$$

For continuous local perturbative anomalies, the obstruction may be encoded by an anomaly polynomial and descent. For finite, fermionic, reflection, or global anomalies, the obstruction may instead be encoded by a cocycle, eta invariant, bordism class, or invertible field theory.

The third landmark is **RG invariance**. If the UV theory flows to an IR theory while preserving the symmetry, the anomaly class is unchanged:

$$
\mathcal A_{\rm UV}=\mathcal A_{\rm IR}.
$$

The fourth landmark is the list of **matching mechanisms**. A symmetric, trivially gapped, unique vacuum cannot match a nonzero ’t Hooft anomaly. Therefore a theory with anomaly must do something nontrivial in the IR, such as:

- remain gapless;
- spontaneously break the symmetry;
- develop topological order;
- have protected boundary or defect degrees of freedom;
- realize the symmetry in a higher-form, higher-group, or non-invertible way;
- combine several sectors whose total anomaly matches the UV.

The fifth landmark is **inflow**. The anomalous $d$-dimensional theory can often be viewed as the boundary of a $(d+1)$-dimensional invertible theory:

$$
Z_{\rm bulk}[A]Z_{\rm boundary}[A]
$$

is gauge invariant even when $Z_{\rm boundary}[A]$ alone is not. This is not merely a trick. It is now one of the cleanest definitions of anomaly data.

## Common confusions

**“A ’t Hooft anomaly means the theory is inconsistent.”**  No. A gauge anomaly in a dynamical gauge redundancy is fatal. A ’t Hooft anomaly of a global symmetry is allowed; it says that the global symmetry cannot be gauged without extra bulk data or additional degrees of freedom.

**“Anomaly matching means the same particles must appear in the IR.”**  No. The anomaly must match, not the microscopic fields. The IR can match through different massless fields, a Wess–Zumino term, a TQFT, symmetry breaking, a boundary theory, or a dual description.

**“If the current is not conserved, the symmetry is gone.”**  Not always. A background-field anomaly can mean that the partition function transforms by a local phase under background gauge transformations. The original global symmetry may still act on the Hilbert space, while gauging it is obstructed.

**“A local anomaly polynomial is the full anomaly.”**  Only for local perturbative anomaly data. Global, torsion, finite-group, spin, Pin, and some generalized-symmetry anomalies require more refined global data.

**“Anomaly matching only applies to chiral symmetries in QCD.”**  That is the historical flagship example, but the principle is much broader. It applies to ordinary, discrete, higher-form, mixed, spacetime, crystalline, and sometimes non-invertible symmetries, with suitable definitions of background fields and gauging.

**“Adding a counterterm changes the anomaly.”**  It changes the representative, not the class. A genuine anomaly is the part that cannot be removed by local counterterms.

## Boundaries

This chapter is the canonical home for the **meaning and consequences** of ’t Hooft anomalies. It does not try to redo every anomaly calculation from the previous chapter.

Detailed calculations of triangle anomalies, Fujikawa Jacobians, perturbative gauge anomalies, gravitational anomalies, Wess–Zumino consistency, anomaly polynomials, and descent belong in the [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter.

The full classification of generalized symmetries belongs later in [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/), [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/), and [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/). This chapter introduces only the parts needed to understand anomaly matching.

The detailed physics of QCD, chiral symmetry breaking, pions, and confinement belongs in Gauge Theories and the Standard Model and Nonperturbative QFT. This chapter uses QCD-like examples because they are the cleanest anomaly-matching training ground.

Topological phases of matter, SPT phases, and edge theories are developed in more physical detail in Matter, Statistical Physics, and Quantum Information. This chapter isolates their anomaly logic.

## Where to go next

After this chapter, the natural next chapter is [Topological Terms](/symmetry-anomalies-topology/topological-terms/). Theta terms, Wess–Zumino terms, Wess–Zumino–Witten terms, Chern–Simons terms, and BF terms are the concrete actions that often carry or cancel anomaly data.

For symmetry-centered readers, continue later to [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) and [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/). For nonperturbative readers, pair this chapter with confinement, chiral symmetry breaking, and topological sectors in the Nonperturbative QFT volume.

A good minimal route is:

$$
\text{anomalies}
\longrightarrow
\text{’t Hooft anomalies}
\longrightarrow
\text{topological terms}
\longrightarrow
\text{defects and generalized symmetries}.
$$

## References

- G. ’t Hooft, **Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking**, in *Recent Developments in Gauge Theories*, Cargèse 1979. The classic source of anomaly matching as an infrared constraint.
- S. Coleman and B. Grossman, **’t Hooft’s Consistency Condition as a Consequence of Analyticity and Unitarity**, *Nuclear Physics B* 203 (1982). A classic analysis of the matching condition.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on soft pions, secret symmetry, instantons, and $1/N$.
- E. Witten, **Global Aspects of Current Algebra**, *Nuclear Physics B* 223 (1983). Wess–Zumino–Witten terms and anomaly matching for chiral symmetries.
- C. G. Callan and J. A. Harvey, **Anomalies and Fermion Zero Modes on Strings and Domain Walls**, *Nuclear Physics B* 250 (1985). A foundational anomaly-inflow reference.
- J. A. Harvey, **TASI 2003 Lectures on Anomalies**, arXiv:hep-th/0509097. A broad physics review of anomalies, descent, inflow, and applications.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, **Generalized Global Symmetries**, arXiv:1412.5148. Modern higher-form symmetry, background-field, gauging, and anomaly-matching viewpoint.
- D. S. Freed, **Anomalies and Invertible Field Theories**, and related lecture notes. A modern mathematical formulation of anomaly inflow.
- M. Srednicki, *Quantum Field Theory*, §§75–77 and §83. Anomalies and chiral symmetry breaking.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30. Triangle anomalies, global anomalies, and anomaly matching.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II. Gauge theories, chiral symmetries, and anomaly-related consistency conditions.

## Version history

- 2026-06-18: First polished draft. Added chapter orientation, prerequisites, reading path, landmarks, common confusions, boundaries, and handoff to topological terms and generalized symmetries.
