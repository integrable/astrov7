---
title: "Model Calculation Library"
description: "Chapter overview for worked calculations involving Noether currents, Ward identities, anomalies, topological terms, line operators, and generalized symmetries."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki; Coleman; Schwartz; Weinberg; Polyakov; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - worked calculations
  - Noether currents
  - Ward identities
  - anomalies
  - topological terms
  - generalized symmetries
canonicalTopics:
  - model-calculation-library
  - worked-qft-calculation
  - symmetry-calculation
  - anomaly-calculation
researchStatus:
  established:
    - "The calculations collected in this chapter are standard templates for using symmetry, anomalies, topology, and generalized symmetry in concrete QFT examples."
  active:
    - "Some generalized-symmetry and non-invertible examples have active convention choices; pages will state assumptions and avoid pretending that all modern formulations are fully standardized."
---

The Model Calculation Library is the practical chapter of the Symmetry, Anomalies, and Topology volume. Earlier chapters explain concepts. This chapter shows the machinery working on concrete examples.

A good calculation page should do more than present an answer. It should show which convention is being used, which symmetry is being varied, which current or background field is normalized, which contact terms matter, and which signs are physical rather than artifacts of notation.

The chapter’s slogan is:

$$
\text{concept} \longrightarrow \text{calculation template} \longrightarrow \text{reusable diagnostic}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Map of the model calculation library, grouping calculations into Noether currents, Ward identities, anomalies, topological terms, line operators, and generalized symmetries.](/figures/symmetry-anomalies-topology/model-calculation-library-map.svg)

<figcaption>

The library collects reusable calculation templates. The goal is not to replace full chapters, but to give readers checked examples they can adapt: currents, Ward identities, anomalies, topological terms, line operators, and generalized-symmetry diagnostics.

</figcaption>
</figure>

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), ordinary global symmetry, Noether currents, background fields, anomalies, topological terms, defects, and higher-form symmetry at least at the level of the overview pages.

For the first pass, it is enough to know what a current is, how a background field sources it, why gauge redundancy differs from global symmetry, and how Wilson lines and topological terms enter path integrals.

## Reading path

Read these pages in clusters rather than strictly linearly. Each cluster corresponds to a standard calculation skill.

| Cluster | Pages | What you learn |
|---|---|---|
| Noether templates | Noether Current for Scalar Field; Noether Current for Dirac Field | How to derive and normalize currents from field transformations. |
| Ward identities | Ward Identity in QED | How current conservation becomes identities among correlation functions and amplitudes. |
| Spontaneous breaking | Goldstone Theorem Example | How symmetry, current algebra, and spectral reasoning force gapless modes. |
| Perturbative anomalies | ABJ Anomaly Triangle | How a triangle diagram detects anomalous current nonconservation. |
| Measure anomalies | Fujikawa Chiral Jacobian | How the path-integral measure sees the chiral anomaly. |
| Gauge consistency | Anomaly Cancellation in the Standard Model | How representation theory removes gauge anomalies. |
| Topological terms | Theta Term in Yang–Mills; Chern–Simons Level Quantization; Wess–Zumino Consistency Condition | How topology fixes periodicity, quantization, and anomaly consistency. |
| Extended operators | Wilson Loop Area Law Preview | How line operators diagnose phases. |
| Higher-form symmetry | One-Form Symmetry in Maxwell Theory; Center Symmetry in Yang–Mills | How extended charged operators and topological symmetry operators work in examples. |
| Low-dimensional duality | Kramers–Wannier Duality in Ising Model | How finite symmetry, disorder operators, and non-invertible duality appear concretely. |
| Inflow | WZW Term from Anomaly Inflow | How a bulk term explains an anomalous boundary or sigma-model term. |

The planned pages are:

```txt
noether-current-for-scalar-field.md
noether-current-for-dirac-field.md
ward-identity-in-qed.md
goldstone-theorem-example.md
abj-anomaly-triangle.md
fujikawa-chiral-jacobian.md
anomaly-cancellation-in-the-standard-model.md
theta-term-in-yang-mills.md
chern-simons-level-quantization.md
wess-zumino-consistency-condition.md
wilson-loop-area-law-preview.md
one-form-symmetry-in-maxwell-theory.md
center-symmetry-in-yang-mills.md
kramers-wannier-duality-in-ising-model.md
wzw-term-from-anomaly-inflow.md
```

## How to use this chapter

Use the calculation pages as templates.

If you want to compute a current, start with the scalar or Dirac current pages. If you want to understand contact terms, start with the QED Ward identity. If you want to compare anomaly derivations, read the triangle and Fujikawa pages side by side. If you want to understand topological normalization, read the theta and Chern–Simons pages before applying those terms in gauge theory or phases of matter.

Each calculation page should make four things explicit:

1. **The convention.** Which metric, epsilon tensor, gamma matrix, generator normalization, and Fourier convention are used?
2. **The object being varied.** Are we varying fields, sources, background gauge fields, the metric, or a regulator?
3. **The physical diagnostic.** Does the result measure a charge, a Ward identity, an anomaly, a topological phase, or a symmetry-breaking pattern?
4. **The reusable pattern.** What part of the calculation generalizes?

## Landmarks

| Landmark | Meaning |
|---|---|
| Current normalization | The factor in $Q=\int d^{d-1}\mathbf x\,j^0$ determines how charges act on operators. |
| Contact term | A local term supported when a current insertion collides with another operator; essential in Ward identities. |
| Background variation | The cleanest way to define currents and anomalies is often by differentiating $W[A]$. |
| Regulator dependence | A regulator may preserve one symmetry while sacrificing another; anomaly calculations track the unavoidable sacrifice. |
| Counterterm ambiguity | Local terms can shift consistent versus covariant anomaly expressions without changing the underlying obstruction. |
| Quantization condition | Topological terms often have coefficients fixed by invariance under large gauge transformations or bundle topology. |
| Line-operator diagnostic | Wilson and ’t Hooft loops can distinguish phases even when local order parameters fail. |
| Higher-form charge | Extended operators can be charged under symmetries whose generators live on linking surfaces. |
| Inflow | A bulk topological term can cancel the anomalous variation of a boundary or defect theory. |

## Common confusions

**“A worked example is less conceptual.”** Often the opposite is true. An anomaly, topological term, or Ward identity becomes clear only when every sign and contact term is forced to show its face.

**“Noether’s theorem fixes the current uniquely.”** Currents can be improved by identically conserved terms. Charges and Ward identities are usually more robust than a particular local representative.

**“A Ward identity is just $\partial_\mu j^\mu=0$.”** Inside correlation functions, the useful Ward identity includes contact terms at charged insertions.

**“The anomaly is whatever one regularization gives.”** An anomaly is the regulator-independent obstruction left after allowing local counterterms. Individual formulas can shift.

**“The triangle anomaly and Fujikawa anomaly are different anomalies.”** They are different derivations of the same obstruction, presented in different languages.

**“Topological normalization is cosmetic.”** It is not. A missing factor of $2\pi$ can change whether a path integral is gauge invariant.

**“Wilson-loop area law is a theorem in every gauge theory.”** Area laws are diagnostics whose validity depends on dimension, matter content, representation, gauge group, and phase.

## Boundaries

This chapter is not a full computational QFT textbook. It gives targeted worked examples for symmetry, anomaly, topology, and generalized-symmetry concepts.

Detailed perturbative methods live in Perturbative QFT and Scattering. Full renormalization lives in Renormalization, RG, and EFT. Gauge dynamics lives in Gauge Theories and the Standard Model and Nonperturbative QFT. Full topological phases live in Matter, Statistical Physics, and Quantum Information. Rigorous versions of these arguments live in Mathematical and Rigorous QFT.

The pages here should be cross-linked heavily, but they should stay focused: each page proves or computes one thing well.

## Where to go next

If you are reading linearly, start with the two Noether-current pages, then Ward Identity in QED. After that, read Goldstone Theorem Example before entering the anomaly calculations. Once the anomaly calculations are familiar, continue to topological terms and higher-form examples.

If you are using this chapter as a lookup library, jump directly to the calculation closest to your problem and read its “Reusable pattern” and “Common pitfalls” sections first.

## References

### Standard QFT calculations

- Srednicki, *Quantum Field Theory*, especially §§22–24, §§67–77, §82, and §§92–94.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on spacetime/internal symmetries, Ward identities, gauge fields, and anomalies.
- Coleman, *Aspects of Symmetry*, especially “Soft Pions,” “Dilatations,” “Secret Symmetry,” and “The Uses of Instantons.”
- Schwartz, *Quantum Field Theory and the Standard Model*, especially chs. 3, 14, 25, 28, and 30.
- Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for symmetry, current algebra, gauge theory, and anomaly conventions.

### Topology and generalized symmetry

- Polyakov, *Gauge Fields and Strings*, especially the chapters on gauge systems, strong coupling, instantons, topology of gauge fields, and loop dynamics.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for higher-form symmetry examples and diagnostics.
- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for background fields, global form, and line-operator choices.
- Aharony, Seiberg, and Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line-operator lattices and global form.

## Version history

- 2026-06-23: Initial polished chapter overview. Added reading clusters, planned pages, calculation landmarks, common pitfalls, boundaries, and references.
