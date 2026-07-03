---
title: "SPT Phases and Anomalies"
description: "Explains symmetry-protected topological phases as invertible bulk phases whose boundaries carry ’t Hooft anomalies."
sidebar:
  label: "SPT Phases and Anomalies"
  order: 5
level: Advanced
status: "Polished draft"
source: "Chen–Gu–Liu–Wen; Kapustin–Seiberg; Freed–Hopkins; Gaiotto–Kapustin–Seiberg–Willett; modern anomaly-inflow and SymTFT references."
topics:
  - symmetry-protected topological phases
  - anomalies
  - invertible phases
  - anomaly inflow
  - boundary anomaly
  - topological response
canonicalTopics:
  - spt-phase
  - anomaly-boundary-correspondence
  - invertible-topological-response
  - protected-boundary-state
  - anomaly-matching
researchStatus:
  established:
    - "SPT phases are the condensed-matter and lattice many-body realization of invertible phases protected by symmetry, and their protected boundaries are naturally described by ’t Hooft anomalies."
    - "For many ordinary finite bosonic symmetries, group-cohomology response actions give an important family of SPT phases; more general bosonic, fermionic, crystalline, and higher-form cases require broader generalized-cohomology or bordism language."
  active:
    - "The classification and boundary realization of SPT phases with higher-form, subsystem, crystalline, fermionic, and non-invertible symmetries remains an active interface of QFT, topology, and quantum matter."
---

## Summary

A **symmetry-protected topological phase**, or **SPT phase**, is an invertible gapped phase that is trivial if the protecting symmetry is ignored but nontrivial if the symmetry is preserved. It has no intrinsic topological order in the bulk, but it can have a protected boundary anomaly.

The clean QFT slogan is:

$$
\text{SPT bulk}
\quad \longleftrightarrow \quad
\text{’t Hooft anomaly of the boundary symmetry}.
$$

If a $d$-dimensional boundary theory has a ’t Hooft anomaly for a symmetry $G$, it can often be realized as the boundary of a $(d+1)$-dimensional $G$-protected invertible phase. The bulk response cancels the anomalous boundary variation by inflow.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A symmetry-protected topological bulk with a protected boundary anomaly. The bulk response cancels the anomalous variation of the boundary theory.](/figures/symmetry-anomalies-topology/spt-boundary-anomaly.svg)

<figcaption>

An SPT phase is short-range entangled and invertible in the bulk, but a symmetric boundary need not be trivial. The boundary anomaly is cancelled by the bulk topological response. Breaking the protecting symmetry removes the protection and can trivialize the phase.

</figcaption>
</figure>

The point is subtle but powerful: an SPT phase may have no anyons, no topological ground-state degeneracy, and no deconfined bulk excitations. Its nontriviality is detected by response to background fields and by what is forced to happen at its boundary.

## Prerequisites

Read [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) and [Invertible Field Theories](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/invertible-field-theories/) first. You should also know what a background field is and what it means for a global symmetry to have a ’t Hooft anomaly.

Helpful earlier pages include [Obstruction to Gauging](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/obstruction-to-gauging/), [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/), and [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/).

## Core idea

An SPT phase is not topological order in the intrinsic sense. A typical intrinsic topological order has nontrivial bulk anyons, extended topological excitations, and ground-state degeneracy on nontrivial spatial manifolds. An SPT phase is short-range entangled and invertible; it can be cancelled by stacking with its inverse.

So why is it nontrivial?

Because the trivializing deformation is forbidden by symmetry. A nontrivial SPT phase cannot be smoothly deformed to a product state while preserving the protecting symmetry and the gap. If the symmetry is explicitly broken, the obstruction can disappear.

In QFT language, the bulk SPT defines an invertible response functional

$$
Z_{\mathrm{SPT}}[X_{d+1};A],
$$

where $A$ is a background for the protecting symmetry. On a closed spacetime $X_{d+1}$, this is a number, often a phase. On a spacetime with boundary $M_d=\partial X_{d+1}$, its anomalous variation can cancel the variation of a boundary theory:

$$
Z_{\mathrm{SPT}}[X;A^g]\,Z_{\partial}[M;A^g]
=
Z_{\mathrm{SPT}}[X;A]\,Z_{\partial}[M;A].
$$

This is anomaly inflow. The boundary anomaly is not a nuisance added after the fact; it is the operational way to detect the SPT bulk.

## Setup and conventions

Let $X_{d+1}$ be the bulk spacetime and let $M_d=\partial X_{d+1}$ be the boundary. Let $G$ be the protecting symmetry, which may be an ordinary group, a higher-form symmetry, a fermionic symmetry involving $(-1)^F$, a spacetime symmetry, or a more general structure.

The SPT partition function is written

$$
Z_{\mathrm{SPT}}[X_{d+1};A].
$$

For an invertible topological phase, $Z_{\mathrm{SPT}}$ is nonzero on closed $X_{d+1}$ and multiplies under stacking:

$$
Z_{\mathrm{SPT}_1\otimes\mathrm{SPT}_2}[X;A]
=
Z_{\mathrm{SPT}_1}[X;A]\,Z_{\mathrm{SPT}_2}[X;A].
$$

The inverse phase has

$$
Z_{\mathrm{SPT}^{-1}}[X;A]=Z_{\mathrm{SPT}}[X;A]^{-1}.
$$

A boundary theory is anomalous when its partition function is not a gauge-invariant number in background-field space. The combined bulk-boundary object is gauge invariant.

:::note[Source note: classification language]
For finite bosonic internal symmetries, a large and important family of SPT phases is described by group-cohomology actions. More generally, especially for fermions, time reversal, crystalline symmetries, higher-form symmetries, and gravitational responses, the natural classification uses generalized cohomology, bordism, or fully extended field-theoretic data. This page uses the term SPT for the physical phase and treats the classification technology as input, not as the definition.
:::

## SPT phases versus intrinsic topological order

The contrast between SPT phases and intrinsic topological order is load-bearing.

| Feature | SPT phase | Intrinsic topological order |
|---|---|---|
| Bulk entanglement | Short-range entangled | Long-range entangled |
| Invertible under stacking | Yes | Usually no |
| Bulk anyons or deconfined sectors | None intrinsically | Usually yes |
| Ground-state degeneracy on topology | Usually none protected by topology alone | Often yes |
| Boundary | May be anomalous if symmetry preserved | May support anyon condensation, topological boundaries, edge modes |
| Protection | Requires symmetry or spacetime structure | Does not require symmetry |

An SPT phase is therefore “topological” in the response and boundary sense, not because it contains intrinsic topological order. Its bulk path integral can still depend on topology, background gauge fields, spin structures, or characteristic classes.

This distinction is why anomaly language is so useful. An anomaly is also not a propagating bulk excitation. It is an obstruction phase, and so it is naturally represented by an invertible bulk response.

## Boundary anomaly as the diagnostic

Suppose the boundary theory has symmetry $G$ and background $A$. If the boundary were standalone, we would want

$$
Z_{\partial}[A^g]=Z_{\partial}[A].
$$

For an anomalous boundary, instead,

$$
Z_{\partial}[A^g]
=
Z_{\partial}[A]\exp\bigl(i\mathcal A[A,g]\bigr).
$$

A bulk SPT phase supplies

$$
Z_{\mathrm{SPT}}[A^g]
=
Z_{\mathrm{SPT}}[A]\exp\bigl(-i\mathcal A[A,g]\bigr).
$$

Thus the product is invariant:

$$
Z_{\mathrm{SPT}}[A]Z_{\partial}[A]
$$

is the physical bulk-boundary partition function.

The boundary cannot be removed without changing the problem. A symmetric boundary of a nontrivial SPT phase must do something nontrivial:

1. stay gapless,
2. spontaneously break the symmetry,
3. develop intrinsic topological order,
4. or remain attached to the bulk as a relative theory.

This is often the most practical way to identify an SPT phase: not by looking for bulk anyons, but by asking what boundary behavior is impossible in a purely $d$-dimensional symmetric system.

## Response actions

Many SPT phases are represented at low energy by topological response actions for background fields. For a finite group $G$, a group-cohomology response in $(d+1)$ dimensions is often written schematically as

$$
Z_{\omega}[X;A]
=
\exp\left(2\pi i\int_X A^*\omega\right),
\qquad
\omega\in H^{d+1}(BG,U(1)).
$$

Here $A$ is a $G$ background, equivalently a map to $BG$ in a topological description, and $A^*\omega$ is the pulled-back cocycle. This formula is schematic but captures the key structure: the SPT partition function is a topological phase depending on the background field.

For continuous symmetries, responses may involve characteristic classes. For example, in three spacetime dimensions, a background Chern–Simons response can have the form

$$
S_{\mathrm{resp}}[A]
=
\frac{k}{4\pi}\int_X A\wedge dA
$$

for a background $U(1)$ field, subject to quantization and spin-structure subtleties. Such a response indicates a boundary anomaly if $X$ has a boundary.

For fermionic SPT phases, spin structure is part of the data. For time-reversal or reflection-protected phases, Pin structures may appear. For higher-form SPT phases, the background fields are higher-degree gauge fields. The formula changes, but the principle is the same:

$$
\text{bulk response to backgrounds}
\quad =
\quad
\text{boundary anomaly}.
$$

## A few canonical examples

### Haldane chain

A one-dimensional spin chain with appropriate spin-rotation and discrete symmetries can realize a nontrivial SPT phase. Its bulk is gapped and short-range entangled, but an open chain carries protected edge degrees of freedom. In anomaly language, the edge transforms projectively under the protecting symmetry. The projective edge action is the boundary remnant of the bulk SPT class.

### Integer quantum Hall response

The integer quantum Hall phase has a bulk Chern–Simons response for the electromagnetic background. Its edge theory has a chiral anomaly that is cancelled by inflow from the bulk response. This is an especially concrete example of the principle that a protected boundary anomaly diagnoses the bulk response.

### Topological insulators and superconductors

Fermionic SPT phases protected by charge conservation, time reversal, particle-hole symmetry, or combinations thereof require fermionic structure. Their boundaries can host protected Dirac or Majorana modes. Interactions can change free-fermion classifications, which is one reason modern classifications are phrased in terms of interacting invertible phases rather than only band theory.

### Higher-form SPT phases

A theory may have a higher-form global symmetry protected by a higher-form background. An SPT response can involve terms such as

$$
\int_X B_{p+1}\wedge B_{d-p}
$$

or discrete cup-product analogues. Such phases can have boundaries with anomalous higher-form symmetries, forcing unusual behavior of line or surface operators.

## Stacking, cancellation, and anomaly matching

SPT phases stack:

$$
\mathrm{SPT}_1+\mathrm{SPT}_2
\quad\leftrightarrow\quad
Z_1[A]Z_2[A].
$$

The inverse phase cancels the response:

$$
\mathrm{SPT}+(-\mathrm{SPT})=0.
$$

This is the same algebra as anomaly cancellation. If two boundary sectors have opposite anomalies, their product can be anomaly-free. If a UV theory has a certain anomaly, any symmetric IR description must reproduce it. In SPT language, the UV and IR boundaries must be boundaries of the same bulk invertible phase.

This is often the most economical form of anomaly matching:

$$
\mathcal I_{\mathrm{UV}}^{\mathrm{anom}}
=
\mathcal I_{\mathrm{IR}}^{\mathrm{anom}}.
$$

The IR may match the anomaly through massless fields, spontaneous symmetry breaking, topological order, a Wess–Zumino term, or a nontrivial boundary of an SPT-like response. The matching condition does not care which mechanism is used; it cares that the bulk anomaly theory is the same.

## Relation to SymTFT

In the SymTFT picture, the SPT response is an invertible part of the one-higher-dimensional symmetry theory. A fully non-invertible SymTFT may have many sectors, defects, and boundary conditions. An SPT anomaly is the special case where the relevant bulk data is invertible.

This is why the sequence of ideas in this chapter is:

$$
\text{anomaly inflow}
\rightarrow
\text{invertible field theory}
\rightarrow
\text{SPT phase}
\rightarrow
\text{boundary condition and gauging}.
$$

SPT phases explain the physical meaning of invertible anomaly theories. Boundary conditions and gaugings explain how one obtains different absolute theories from the same bulk symmetry data.

## Common pitfalls

**“SPT means topological order.”** Not in the intrinsic sense. SPT phases are invertible and short-range entangled; intrinsic topological order is non-invertible and long-range entangled.

**“If the bulk has no anyons, it is trivial.”** False. The nontriviality can be in the response to background fields and in protected boundary behavior.

**“The boundary must be gapless.”** A symmetric boundary of a nontrivial SPT cannot be trivially gapped and nondegenerate, but it may be gapped by symmetry breaking or by developing intrinsic topological order.

**“Group cohomology classifies every SPT.”** It classifies an important family, especially bosonic finite internal-symmetry phases, but not all interacting bosonic, fermionic, crystalline, gravitational, or higher-form phases.

**“An SPT anomaly is a gauge anomaly.”** The boundary has a ’t Hooft anomaly for a global symmetry. It becomes an inconsistency only if one insists on gauging the anomalous boundary symmetry without the bulk or compensating data.

## Relations to other pages

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) explains the bulk-boundary cancellation mechanism. [Invertible Field Theories](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/invertible-field-theories/) explains the stacking group of anomaly theories. [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) explains how different choices of topological boundary condition produce different absolute theories.

The nearby [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/) page treats the same idea from the anomaly-matching chapter. This page treats it from the SymTFT and invertible-bulk viewpoint.

## Research status

The basic relationship between SPT phases, invertible field theories, and boundary ’t Hooft anomalies is established. The precise classification is highly sensitive to dimension, symmetry, spacetime structure, and whether one allows interactions.

Active questions include classification beyond group cohomology, crystalline and subsystem SPT phases, fermionic and spin/Pin refinements, higher-form and higher-group SPT phases, boundaries with intrinsic topological order, and the extension of SPT/anomaly language to non-invertible and categorical symmetries.

## Exercises

### Exercise 1: Why the boundary is anomalous

Suppose a boundary theory transforms as

$$
Z_{\partial}[A^g]=Z_{\partial}[A]e^{i\mathcal A[A,g]}.
$$

What must the bulk SPT partition function do for the combined bulk-boundary system to be gauge invariant?

<details><summary><strong>Solution</strong></summary>

It must transform oppositely:

$$
Z_{\mathrm{SPT}}[A^g]=Z_{\mathrm{SPT}}[A]e^{-i\mathcal A[A,g]}.
$$

Then

$$
Z_{\mathrm{SPT}}[A^g]Z_{\partial}[A^g]
=
Z_{\mathrm{SPT}}[A]Z_{\partial}[A].
$$

</details>

### Exercise 2: SPT versus intrinsic topological order

Give one diagnostic that distinguishes an SPT phase from intrinsic topological order.

<details><summary><strong>Solution</strong></summary>

An SPT phase is invertible under stacking and has no intrinsic bulk anyon sectors or topology-dependent ground-state degeneracy. Intrinsic topological order is generally non-invertible and has nontrivial bulk topological excitations and/or ground-state degeneracy on nontrivial spatial manifolds.

</details>

### Exercise 3: Breaking the protecting symmetry

Why can a nontrivial SPT phase become trivial if the protecting symmetry is explicitly broken?

<details><summary><strong>Solution</strong></summary>

The obstruction to deforming the SPT to a product state is imposed by symmetry. If the protecting symmetry is not required along the deformation, the response term and boundary anomaly no longer define the same protected invariant. A path to a trivial product phase may then be allowed without closing the gap.

</details>

### Exercise 4: Boundary options

List three possible fates of the boundary of a nontrivial SPT phase if the protecting symmetry is preserved.

<details><summary><strong>Solution</strong></summary>

A symmetric boundary can remain gapless, spontaneously break the protecting symmetry, or become gapped with intrinsic topological order. It can also be understood as a relative boundary theory that is only well-defined together with the bulk.

</details>

## References

- X. Chen, Z.-C. Gu, Z.-X. Liu, and X.-G. Wen, “Symmetry Protected Topological Orders and the Group Cohomology of Their Symmetry Group.”
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality.”
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases.”
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- E. Witten and K. Yonekura, “Anomaly Inflow and the Eta-Invariant.”
- A. Altland and B. Simons, *Condensed Matter Field Theory*, especially the chapters on topological quantum matter and response.
- M. Nakahara, *Geometry, Topology and Physics*, for characteristic classes, bundles, and topological terms.

## Version history

- **2026-06-20:** Initial polished draft. Added SPT/anomaly dictionary, response-action conventions, boundary diagnostics, examples, and exercises.
