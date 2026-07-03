---
title: "Symmetry-Protected Topological Phases"
description: "Explains SPT phases as gapped short-range-entangled phases that become trivial without symmetry, with boundary anomalies, response actions, stacking, and gauging diagnostics."
sidebar:
  label: "SPT Phases"
  order: 2
level: Graduate
status: "Polished draft"
source: "Chen–Gu–Liu–Wen; Levin–Gu; Kapustin; Freed–Hopkins; Altland–Simons Ch. 8; standard topological-matter and anomaly references."
topics:
  - SPT phases
  - short-range entanglement
  - protected boundary modes
  - topological response
  - anomaly inflow
  - group cohomology
canonicalTopics:
  - symmetry-protected-topological-phase
  - short-range-entangled-phase
  - spt-boundary-anomaly
  - topological-response
researchStatus:
  established:
    - "SPT phases are standard examples of gapped phases distinguished not by local order parameters or intrinsic topological order, but by symmetry-protected boundary, defect, and response data."
  active:
    - "Interacting fermionic, crystalline, higher-form, subsystem, and beyond-group-cohomology SPT classifications remain active research areas."
---

## Summary

A **symmetry-protected topological phase**, or **SPT phase**, is a gapped phase that looks trivial if one ignores symmetry, but cannot be smoothly deformed to a product state while preserving the symmetry and the bulk gap.

The rough definition is:

$$
\text{SPT phase}
=
\text{short-range-entangled gapped phase}
+
\text{nontrivial symmetry realization}.
$$

“Short-range-entangled” means the phase has no intrinsic topological order: no deconfined anyons in the bulk, no topological ground-state degeneracy on closed spatial manifolds, and no fractionalized bulk excitations of the kind found in topologically ordered phases. “Protected” means that the distinction from the trivial phase disappears if one is allowed to break the symmetry, explicitly or along the deformation path.

SPT phases are therefore invisible to the simplest Landau question, “which symmetry is broken?” They are also not intrinsic topological order. Their fingerprints are more subtle:

- protected edge, surface, or defect degrees of freedom;
- quantized response actions for background fields;
- anomalous symmetry realization on the boundary;
- projective edge representations in one spatial dimension;
- nontrivial behavior after gauging the protecting symmetry;
- obstruction to a symmetric finite-depth circuit connecting the state to a product state.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Schematic of a trivial short-range-entangled phase and a nontrivial SPT phase. Both have no intrinsic bulk topological order, but the SPT has protected boundary or defect response when symmetry is enforced.](/figures/symmetry-anomalies-topology/spt-phase-diagnostics.svg)

<figcaption>

An SPT phase is short-range entangled in the bulk, just like a trivial product phase, but symmetry prevents the deformation that would trivialize it. The difference shows up at boundaries, defects, and in response to background fields.

</figcaption>
</figure>

The conceptual punchline is that SPT phases are best understood through the same language used for anomalies:

$$
\text{SPT bulk response}
\quad\longleftrightarrow\quad
\text{boundary ’t Hooft anomaly}.
$$

## Prerequisites

You should know [Landau Symmetry Breaking](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/landau-symmetry-breaking/), [Topological Terms](/symmetry-anomalies-topology/topological-terms/), [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/), [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/), and the basic meaning of a background field.

For a first pass, keep this dictionary in mind:

| Phrase | Meaning |
|---|---|
| Gapped phase | Correlations decay exponentially and the energy gap remains nonzero in the thermodynamic limit. |
| Short-range entangled | Deformable to a product state by a finite-depth local unitary if symmetry is ignored. |
| Protecting symmetry | The symmetry that forbids that deformation. |
| Boundary anomaly | A boundary realization of the symmetry that cannot occur in a strictly lower-dimensional standalone system. |
| Response action | A topological effective action for background fields encoding robust SPT data. |

## Core idea

Landau theory says that phases are distinguished by the pattern

$$
G\longrightarrow H,
$$

where $G$ is the microscopic symmetry and $H$ is the unbroken subgroup. SPT phases show that this is incomplete. Two phases can have the same unbroken symmetry and no intrinsic topological order, yet still be distinct.

The simplest modern definition uses finite-depth local circuits. Ignore symmetry for a moment. A short-range-entangled gapped state $|\Psi\rangle$ is trivial if there exists a finite-depth local unitary circuit $U_{\rm fd}$ such that

$$
|\Psi\rangle=U_{\rm fd}|\text{product}\rangle.
$$

If such a circuit exists only after allowing symmetry-breaking gates, but not when every layer respects the symmetry, then the state is an SPT state.

Equivalently, an SPT phase is trivial as an ordinary gapped phase but nontrivial as a **symmetric** gapped phase.

This is why the word “protected” matters. Break the protecting symmetry, and the distinction can disappear.

## Setup and conventions

Let $G$ be the protecting symmetry. It may be an internal unitary group, a finite group, time reversal, fermion parity, a crystalline symmetry, or a higher-form symmetry. This page begins with internal bosonic symmetries, because they are the cleanest examples, and then explains the caveats.

A $d$-dimensional SPT phase can often be probed by coupling $G$ to a background field $A$. The long-distance effective action is topological:

$$
Z_{\rm SPT}[A]\simeq \exp\left(iS_{\rm top}[A]\right).
$$

If the phase is trivial, $S_{\rm top}[A]$ can be removed by a symmetric local counterterm or by a symmetric finite-depth circuit. If the phase is nontrivial, this topological response cannot be removed without leaving the allowed equivalence class.

For a boundary theory on $\partial M$, the bulk variation of $S_{\rm top}[A]$ can cancel an anomalous boundary variation:

$$
\delta_\lambda S_{\rm bulk}[A]
+
\delta_\lambda W_{\partial M}[A]
=0.
$$

That is the anomaly-inflow version of the protected-boundary statement.

:::note[Source note: classification language]
For bosonic internal finite symmetries, group-cohomology models give a large and important class of SPT phases, often expressed through classes in $H^{d+1}(G,U(1))$. They are not the final classification in all settings. Cobordism and generalized-cohomology viewpoints are needed for many beyond-group-cohomology, fermionic, orientation-reversing, crystalline, and spacetime-symmetry cases.
:::

## What SPT phases are not

An SPT phase is not a symmetry-breaking phase. The protecting symmetry is unbroken in the bulk.

An SPT phase is not intrinsic topological order. A closed sample of an SPT phase does not have the robust topological ground-state degeneracy characteristic of a fractional quantum Hall state or a deconfined gauge theory.

An SPT phase is not merely “a phase with edge states.” Edge states can occur for many reasons. The SPT claim is that a symmetric boundary cannot be trivially gapped by a local boundary perturbation unless something else happens: symmetry breaking, topological order on the boundary, gapless boundary modes, or a boundary phase transition.

An SPT phase is not always captured by free-fermion band topology. Free-fermion topological insulators and superconductors are important SPT phases, but interactions can reduce, enlarge, or modify free classifications.

The safe sentence is:

$$
\text{SPT}=\text{no intrinsic bulk topological order, but nontrivial symmetric structure}.
$$

## One-dimensional SPT phases and projective edge states

One spatial dimension is the best place to build intuition. A gapped spin chain with an on-site symmetry $G$ may have a unique symmetric gapped bulk, but nontrivial edge degrees of freedom on an open interval.

The Haldane phase of spin chains is the standard physical example. With appropriate symmetries, its ends carry effective spin-$1/2$ edge modes, even though the bulk has no intrinsic topological order.

The mathematical diagnostic is projective representation at the boundary. A projective representation obeys

$$
V_gV_h=\omega(g,h)V_{gh},
$$

where $\omega(g,h)\in U(1)$ is a phase. Changing phases of $V_g$ changes $\omega$ by a coboundary, so the invariant data are cohomology classes. In the simplest bosonic one-dimensional setting, the classification is

$$
H^2(G,U(1)).
$$

This is not just formal. The edge modes remember the nontrivial projective class even though the bulk has a unique gapped ground state on a circle.

## Higher-dimensional SPT phases and response actions

In higher dimensions, edge projective representations are replaced by boundary anomalies and topological response actions.

A familiar response form is a Chern–Simons action in $2+1$ dimensions,

$$
S_{\rm CS}[A]=\frac{k}{4\pi}\int A\wedge dA,
$$

which encodes Hall response. For an integer quantum Hall state, this response can be understood as an invertible phase: there are no anyons in the bulk, but the edge theory carries a chiral anomaly.

For bosonic finite internal symmetries, group-cohomology SPT phases can be represented by discrete topological actions for flat $G$ background fields. In continuum notation this is schematic, but the idea is robust:

$$
Z_{\rm SPT}[A]=\exp\left(2\pi i\int_M \omega_{d+1}(A)\right),
$$

where $\omega_{d+1}$ is a cocycle representative.

For time-reversal or orientation-reversing symmetries, the response can involve unoriented manifolds, Pin structures, or eta invariants. For fermionic phases, spin or Pin structures are part of the background data. The phrase “the symmetry group” is then not enough; one must also specify the spacetime structure.

## Boundary possibilities

A nontrivial SPT phase forces the boundary to do something nontrivial if the symmetry is preserved. The boundary may be:

| Boundary behavior | Meaning |
|---|---|
| Gapless | The boundary has protected low-energy modes. |
| Symmetry-breaking | The boundary gaps out by breaking the protecting symmetry. |
| Topologically ordered | The boundary gaps out while preserving symmetry by developing intrinsic topological order. |
| Degenerate or critical | The boundary sits at a transition or carries protected degeneracy. |

Which option occurs depends on dimension, symmetry, interactions, and microscopic details. The invariant statement is not “the boundary is always gapless.” The invariant statement is that the boundary cannot be both trivially gapped and symmetrically short-range entangled.

This is the anomaly-boundary correspondence in condensed-matter clothing. The boundary symmetry action is anomalous as a standalone $d$-dimensional system, but becomes consistent as the boundary of the $(d+1)$-dimensional SPT bulk.

## Gauging diagnostic

A powerful diagnostic is to gauge the protecting symmetry. If two phases differ only by an SPT layer, gauging $G$ can turn the difference into distinct statistics or topological terms for gauge fluxes.

In two spatial dimensions with finite $G$, gauging a trivial symmetric phase gives an ordinary discrete gauge theory. Gauging a nontrivial SPT gives a twisted gauge theory. The flux excitations can have different braiding statistics.

This is the logic behind the braiding-statistics diagnostic for bosonic SPT phases: couple to a $G$ gauge field, make it dynamical, and examine the resulting gauge fluxes. A phase that had no intrinsic topological order before gauging can become a topologically ordered gauge theory after gauging; the way fluxes braid remembers the original SPT response.

## Stacking and inverses

SPT phases form an abelian group under stacking. If $|\Psi_1\rangle$ and $|\Psi_2\rangle$ are two SPT states with the same symmetry, stacking means putting the systems side by side:

$$
|\Psi_1\rangle\otimes|\Psi_2\rangle.
$$

The trivial product phase is the identity element. The inverse of an SPT phase is another SPT phase which cancels it under stacking:

$$
[\Psi]+[-\Psi]=0.
$$

At the response level, stacking adds topological actions:

$$
S_{\rm top}^{(1\oplus2)}=S_{\rm top}^{(1)}+S_{\rm top}^{(2)}.
$$

This group structure is a major reason SPT classifications can be phrased in cohomological or bordism language.

## Decorated domain walls

A very useful construction is the decorated-domain-wall picture. Suppose a symmetry $G$ has domain walls. One can decorate those domain walls with lower-dimensional SPT phases or invertible phases, then proliferate the walls while preserving $G$.

The result can be a symmetric, gapped, short-range-entangled bulk whose boundary remembers the decoration. This gives physical intuition for many group-cohomology constructions and for crystalline or higher-order SPT phases.

The phrase “decorate and proliferate” is worth remembering:

$$
\text{decorate defects}
\quad+\quad
\text{sum over them symmetrically}
\quad=\quad
\text{SPT bulk}.
$$

This construction is also a bridge to higher-form and crystalline SPT phases, where the relevant defects may be lines, planes, symmetry twists, or crystalline domain walls.

## Free fermions, interactions, and reductions

Free-fermion topological insulators and superconductors are SPT phases protected by symmetries such as time reversal, particle-hole symmetry, chiral symmetry, and charge conservation. Their famous “periodic table” is a free-fermion classification.

Interactions can change this classification. Some free-fermion phases that look distinct at the noninteracting level become smoothly connected once interactions are allowed. Conversely, interactions can create bosonic or fermionic SPT phases with no free-fermion representative.

Thus one must always ask:

1. What is the symmetry?
2. Are we classifying free fermions or interacting many-body phases?
3. Are bosonic, fermionic, spin, Pin, or crystalline structures part of the background?
4. Are we allowing stacking with invertible phases?

The same notation can mean different classification problems if these choices are not fixed.

## Diagnostics

A practical SPT checklist:

| Diagnostic | What it tests |
|---|---|
| Symmetric finite-depth circuit | Can the state be symmetrically disentangled to a product state? |
| Boundary anomaly | Can the boundary be realized as a standalone symmetric system? |
| Background response | Is there a nontrivial topological action for symmetry backgrounds? |
| Gauging | Do gauge fluxes have nontrivial statistics or topological terms? |
| Defect decoration | Do symmetry defects carry lower-dimensional invertible phases? |
| Entanglement spectrum | Are there symmetry-protected degeneracies or edge-like structures? |

No single diagnostic is universal. For some phases, response actions are easiest. For one-dimensional spin chains, edge projective representations are easiest. For two-dimensional bosonic phases, gauging and flux statistics can be especially revealing. For crystalline and fermionic cases, manifold and structure-dependence become unavoidable.

## Common pitfalls

**“SPT means topological order.”** No. SPT phases are usually short-range-entangled and have no intrinsic bulk topological order. Their nontriviality is symmetry-protected.

**“Protected boundary means always gapless.”** No. A boundary can also break symmetry or develop topological order. What is forbidden is a trivially gapped symmetric boundary.

**“If the bulk has no anyons, it is trivial.”** Not with symmetry. A short-range-entangled bulk can still have nontrivial response or anomalous boundary realization.

**“Group cohomology classifies all SPT phases.”** It classifies an important class of bosonic internal-symmetry SPT phases. It is not the final answer for all symmetries, fermions, spacetime symmetries, or beyond-group-cohomology phases.

**“Breaking the symmetry slightly should not matter.”** It matters by definition. If the protecting symmetry is broken, distinct SPT phases can become connected.

**“Every topological insulator is just a band effect.”** Free-fermion band topology is a crucial subclass. Interactions can modify classifications and produce phases not captured by band theory.

## Relations to other pages

[Landau Symmetry Breaking](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/landau-symmetry-breaking/) explains what SPT phases are not: they do not require a local order parameter or broken symmetry. [Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/) adds intrinsic topological order and studies how symmetry acts on anyons. [Anomaly-Boundary Correspondence](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/anomaly-boundary-correspondence/) develops the boundary-anomaly viewpoint in more detail.

[Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) gives the one-higher-dimensional language behind SPT responses. [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/) explains invertible and non-invertible TQFTs. [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) explains the source and gauging language used to diagnose SPT phases.

## Research status

SPT phases are standard and central in modern condensed matter and QFT. One-dimensional bosonic SPT phases, many group-cohomology bosonic SPTs, free-fermion topological insulators and superconductors, and anomaly-inflow interpretations are well established.

Active research includes interacting fermionic classifications, crystalline SPT phases, higher-order SPT phases, subsystem and fracton-like SPTs, higher-form SPT phases, mixed spacetime-internal symmetries, non-invertible symmetry-protected phases, and precise classification beyond group cohomology using cobordism and generalized homology/cohomology methods.

## Exercises

### Exercise 1: Why symmetry matters

Explain why a nontrivial SPT phase can be trivialized if the protecting symmetry is broken.

<details><summary><strong>Solution</strong></summary>

The defining obstruction is the absence of a **symmetric** finite-depth local circuit connecting the SPT state to a product state. If symmetry-breaking gates are allowed, that obstruction is removed by definition. Since an SPT phase has no intrinsic topological order, it is short-range entangled as an ordinary gapped phase, so it can be disentangled once the symmetry constraint is dropped.

</details>

### Exercise 2: Edge projective representation

Let a one-dimensional bosonic SPT phase with symmetry $G$ have edge operators $V_g$ satisfying

$$
V_gV_h=\omega(g,h)V_{gh}.
$$

Why does changing $V_g\mapsto e^{i\alpha(g)}V_g$ not change the physical SPT class?

<details><summary><strong>Solution</strong></summary>

The phase factor changes the cocycle by

$$
\omega(g,h)\mapsto e^{i\alpha(g)}e^{i\alpha(h)}e^{-i\alpha(gh)}\omega(g,h).
$$

This is multiplication by a coboundary. Such a redefinition is only a change of basis or phase convention for edge operators. The invariant data are therefore cohomology classes, not individual cocycle representatives.

</details>

### Exercise 3: Boundary options

List three possible symmetry-preserving or symmetry-resolving fates of the boundary of a nontrivial SPT phase.

<details><summary><strong>Solution</strong></summary>

A boundary may remain gapless, break the protecting symmetry, or become gapped with intrinsic topological order. It may also sit at a critical point or carry protected degeneracy. What is forbidden is a boundary that is simultaneously trivially gapped, short-range entangled, and symmetry-preserving.

</details>

### Exercise 4: Gauging diagnostic

Why can gauging a finite protecting symmetry distinguish two SPT phases that had no intrinsic topological order before gauging?

<details><summary><strong>Solution</strong></summary>

Before gauging, both phases are short-range entangled and have no deconfined anyons. After gauging, symmetry fluxes become dynamical excitations. A nontrivial SPT response can change the braiding statistics, fusion, or topological action of those fluxes. Thus the gauged theories can be distinct topological orders even though the ungauged SPT phases had no intrinsic topological order.

</details>

## References

- X. Chen, Z.-C. Gu, Z.-X. Liu, and X.-G. Wen, “Symmetry-Protected Topological Orders in Interacting Bosonic Systems.”
- X. Chen, Z.-X. Liu, and X.-G. Wen, “Two-Dimensional Symmetry-Protected Topological Orders and Their Protected Gapless Edge Excitations.”
- M. Levin and Z.-C. Gu, “Braiding Statistics Approach to Symmetry-Protected Topological Phases.”
- A. Kapustin, “Symmetry Protected Topological Phases, Anomalies, and Cobordisms: Beyond Group Cohomology.”
- A. Kapustin, R. Thorngren, A. Turzillo, and Z. Wang, “Fermionic Symmetry Protected Topological Phases and Cobordisms.”
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases.”
- A. Altland and B. Simons, *Condensed Matter Field Theory*, especially the chapters on broken symmetry, topological field theory, relativistic field theory, and gauge theory.
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*.

## Version history

- **2026-06-23:** Initial polished draft. Added finite-depth-circuit definition, boundary anomaly viewpoint, response actions, group-cohomology and cobordism caveats, gauging diagnostic, decorated-domain-wall picture, and exercises.
