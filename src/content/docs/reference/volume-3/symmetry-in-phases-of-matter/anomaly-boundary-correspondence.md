---
title: "Anomaly–Boundary Correspondence"
description: "Explains how anomalous boundary theories arise as consistent boundaries of higher-dimensional bulk phases, with anomaly inflow, SPT boundaries, SET surfaces, and topological-order diagnostics."
sidebar:
  label: "Anomaly–Boundary Correspondence"
  order: 5
level: Graduate
status: "Polished draft"
source: "Callan–Harvey; Witten; Wen; Kapustin; Freed–Hopkins; Wang–Wen–Witten; standard SPT, SET, and anomaly-inflow references."
topics:
  - anomaly-boundary correspondence
  - anomaly inflow
  - SPT boundary
  - anomalous SET
  - topological order
  - symmetry protected phases
canonicalTopics:
  - anomaly-boundary-correspondence
  - anomaly-inflow
  - spt-boundary
  - anomalous-boundary-topological-order
researchStatus:
  established:
    - "The statement that ’t Hooft anomalies of a boundary theory can be canceled by inflow from a one-higher-dimensional bulk is a standard organizing principle in QFT and topological phases."
  active:
    - "Classifying all anomalous boundaries, especially with higher-form, crystalline, fermionic, non-invertible, or fractonic symmetries, remains an active research direction."
---

## Summary

The **anomaly–boundary correspondence** says that a quantum theory with an anomalous symmetry realization may be impossible as a standalone system in $d$ spacetime dimensions, but possible as the boundary of a nontrivial $(d+1)$-dimensional bulk.

The core equation is

$$
\delta_\lambda W_{\partial M}[A]
+
\delta_\lambda S_{\rm bulk}[A]
=0.
$$

The boundary effective action $W_{\partial M}[A]$ is anomalous by itself. The bulk topological action $S_{\rm bulk}[A]$ varies by the opposite amount. Together, the combined bulk-plus-boundary system is consistent.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Bulk anomaly inflow canceling anomalous boundary variation: a higher-dimensional bulk has a topological response whose gauge variation flows to the boundary.](/figures/symmetry-anomalies-topology/anomaly-boundary-correspondence.svg)

<figcaption>

An anomalous $d$-dimensional boundary can be consistent when attached to a $(d+1)$-dimensional bulk. The boundary variation is canceled by inflow from the bulk topological response.

</figcaption>
</figure>

In condensed-matter language, this is the reason a nontrivial SPT phase can have a protected boundary. In QFT language, it is the reason a theory with a ’t Hooft anomaly can be realized as a boundary condition of an anomaly theory or SymTFT. In both languages, the anomaly is not “bad” if it belongs to a global symmetry; it is a powerful constraint on what the boundary can do.

## Prerequisites

You should know [Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/), [Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/), [Topological Order: Preview](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/topological-order-preview/), [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/), and [SPT Phases and Anomalies](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/spt-phases-and-anomalies/).

The page uses the following dimension convention:

$$
\dim(\text{boundary spacetime})=d,
\qquad
\dim(\text{bulk spacetime})=d+1.
$$

## Core idea

A global anomaly is an obstruction to gauging a global symmetry. It does not necessarily make a theory inconsistent. Instead, it means the theory cannot be regularized as an ordinary standalone $d$-dimensional system with an on-site or internal symmetry action and a gauge-invariant background partition function.

A boundary can evade this obstruction because it is not standalone. It is allowed to borrow gauge variation from the bulk. If the boundary partition function transforms as

$$
Z_{\partial M}[A]\mapsto
Z_{\partial M}[A]\exp\left(i\mathcal A[\lambda,A]\right),
$$

and the bulk topological response transforms as

$$
\exp(iS_{\rm bulk}[A])
\mapsto
\exp(iS_{\rm bulk}[A])\exp\left(-i\mathcal A[\lambda,A]\right),
$$

then the product

$$
Z_{\rm total}[A]
=
\exp(iS_{\rm bulk}[A])Z_{\partial M}[A]
$$

is invariant.

This is anomaly inflow. The boundary has anomalous symmetry. The bulk supplies the missing piece.

## Setup and conventions

Let $M$ be a $(d+1)$-dimensional spacetime with boundary $\partial M$. Let $A$ denote background fields for a symmetry $G$. These may be ordinary gauge fields, higher-form gauge fields, discrete background bundles, spin structures, Pin structures, crystalline backgrounds, or combinations of these.

A bulk SPT or invertible phase is described at long distances by an invertible topological response

$$
Z_{\rm bulk}[M,A]=\exp(iS_{\rm top}[M,A]).
$$

If $M$ is closed, this is gauge invariant. If $M$ has boundary, its gauge variation can be a boundary term:

$$
\delta_\lambda S_{\rm top}[M,A]
=
-\mathcal A_{\partial M}[\lambda,A].
$$

The boundary theory is consistent if its anomalous variation is

$$
\delta_\lambda W_{\partial M}[A]=\mathcal A_{\partial M}[\lambda,A].
$$

:::note[Source note: global versus gauge anomaly]
A gauge anomaly of a dynamical gauge redundancy is an inconsistency unless canceled. A ’t Hooft anomaly of a global symmetry is allowed. The anomaly–boundary correspondence is primarily about ’t Hooft anomalies and their inflow realization. If the boundary symmetry is gauged dynamically, the combined bulk-plus-boundary system must still be gauge invariant.
:::

## SPT boundary as the basic example

An SPT phase is short-range entangled in the bulk but nontrivial as a symmetric phase. Its boundary cannot be both trivially gapped and symmetry preserving.

The anomaly–boundary correspondence explains why. A nontrivial SPT bulk carries a topological response. On a closed manifold the response is invariant. On a manifold with boundary, the response has a boundary variation. A boundary theory with the matching anomaly can live there.

The boundary may respond in several ways:

| Boundary option | How it matches the anomaly |
|---|---|
| Gapless boundary | The low-energy degrees of freedom carry the anomalous symmetry. |
| Symmetry-breaking boundary | The protecting symmetry is not realized, so the anomaly constraint is avoided. |
| Symmetric topological boundary | Intrinsic boundary topological order carries the anomaly through fractionalization or defect data. |
| Critical boundary | The boundary sits at a transition with anomalous symmetry realization. |

The invariant statement is not “the boundary must be gapless.” The invariant statement is:

$$
\text{no symmetric trivially gapped boundary}
$$

for a nontrivial SPT phase.

## Integer quantum Hall edge

The integer quantum Hall effect gives a clean anomaly-inflow example. A $2+1$-dimensional bulk with electromagnetic background $A$ has Chern–Simons response

$$
S_{\rm bulk}[A]=\frac{k}{4\pi}\int_M A\wedge dA.
$$

On a closed $M$, this is gauge invariant up to level-quantization subtleties. On a manifold with boundary, under

$$
A\mapsto A+d\lambda,
$$

the action changes by a boundary term:

$$
\delta_\lambda S_{\rm bulk}
=
\frac{k}{4\pi}\int_{\partial M}\lambda\, dA.
$$

The chiral edge theory has an opposite anomaly. The edge alone cannot be a purely one-dimensional nonanomalous system with the same $U(1)$ symmetry and chirality. Together, bulk and edge are gauge invariant.

This is the physical meaning of Hall conductance as an anomaly coefficient.

## Topological insulator surfaces

A three-dimensional topological insulator provides another example. The surface can support an odd number of Dirac cones protected by time reversal and charge conservation. Such a surface spectrum is anomalous: it cannot be realized as an isolated strictly two-dimensional lattice system with the same symmetry in the same way.

Interactions enrich the story. The surface need not remain gapless. It can become symmetry-breaking, or it can develop a symmetric gapped topological order whose anyons transform anomalously under the symmetry. That boundary topological order is not an ordinary standalone SET phase. It is anomalous and becomes consistent only as the surface of the bulk.

This is a central lesson:

$$
\text{an anomalous SET can be a perfectly good boundary}.
$$

The adjective “anomalous” means “not realizable strictly in the same dimension with an on-site symmetry,” not “inconsistent as a boundary.”

## Boundary topological order and anomaly matching

Suppose a bulk SPT has a boundary that is gapped, symmetric, and topologically ordered. The boundary anyons must carry the anomaly.

They can do this through:

- projective symmetry fractionalization on anyons;
- anyon permutations under symmetry;
- anomalous symmetry defects;
- obstruction classes preventing a standalone realization;
- fusion and braiding data that fail a purely $d$-dimensional consistency test but pass when coupled to the bulk.

This is anomaly matching in boundary form. The boundary cannot be trivial because it must reproduce the bulk anomaly. If it is gapped and symmetric, its topological order must be anomalous in exactly the right way.

The same logic applies to interfaces. An interface between two SPT phases carries the difference of their anomalies. If the two bulks differ by an invertible phase $\mathcal I$, then the interface must realize the anomaly of $\mathcal I$.

## Symmetry extension and gapped boundaries

Sometimes an anomalous boundary can be symmetrically gapped by enlarging the symmetry in an intermediate description. Suppose there is a group extension

$$
1\longrightarrow K\longrightarrow H\longrightarrow G\longrightarrow 1.
$$

An anomaly for $G$ may become trivial when pulled back to $H$. One can then construct a boundary with emergent $K$ gauge structure. From the original $G$ viewpoint, the boundary is symmetric and topologically ordered; from the extended $H$ viewpoint, the anomaly is removed before gauging the kernel.

This is one mechanism behind symmetric gapped boundaries of some SPT phases. It is not the only mechanism, and it is not always available in the simplest possible form. But it gives a useful mental picture:

$$
\text{symmetry extension}
\quad+\quad
\text{boundary gauge theory}
\quad\Rightarrow\quad
\text{symmetric anomalous boundary}.
$$

## Higher-form and generalized versions

The anomaly–boundary correspondence is not limited to ordinary zero-form symmetries. Higher-form symmetries can have ’t Hooft anomalies, and those anomalies can be realized on boundaries of higher-dimensional bulk theories.

For a one-form symmetry with background two-form $B$, a bulk response might involve terms such as

$$
\int B\wedge B
$$

or mixed terms with ordinary background fields, depending on dimension and coefficients. On a boundary, the corresponding anomaly constrains line operators, surface operators, and allowed endpoint structure.

Non-invertible and categorical symmetries also have boundary versions. There, the anomaly may be encoded not by a simple cohomology class but by the impossibility of defining a standalone topological defect network with the required fusion, junction, and associator data. Symmetry TFT packages these generalized anomalies especially well.

## Relative QFT language

A standalone absolute QFT has a number-valued partition function on a closed spacetime:

$$
Z(M,A)\in\mathbb C.
$$

An anomalous theory is more naturally **relative** to a one-higher-dimensional invertible theory. Its partition function is not a number by itself; it is a vector or section in a state space or line assigned by the bulk anomaly theory.

The bulk chooses the line. The boundary supplies a vector in that line. Only after pairing with appropriate bulk data do we get a number.

This language is not required for first calculations, but it clarifies why anomalous boundary theories are not “almost inconsistent.” They are consistent objects of a slightly different kind.

## Diagnostic table

| Question | If yes, what it suggests |
|---|---|
| Can the $d$-dimensional theory be regularized with an on-site $G$ symmetry? | No anomaly of that type. |
| Does the background partition function transform by a phase? | Possible ’t Hooft anomaly. |
| Can the phase be removed by a local counterterm? | If yes, the apparent anomaly is scheme-dependent. |
| Can the theory live as a boundary of a $(d+1)$-dimensional response theory? | Anomaly inflow interpretation. |
| Can a symmetric trivially gapped boundary exist? | If no, boundary anomaly is nontrivial. |
| Can a symmetric topological boundary exist? | If yes, boundary topological order must match the anomaly. |

The phrase “can be removed by a counterterm” is important. Not every non-invariance is a genuine anomaly. Some are artifacts of convention or regularization choice. The genuine anomaly is the equivalence class that survives allowed counterterms.

## Common pitfalls

**“An anomalous boundary is inconsistent.”** Not as a boundary. It is inconsistent only if demanded to be a standalone theory with the same symmetry realization.

**“An SPT boundary must be gapless.”** It must be nontrivial. It can be gapless, symmetry-breaking, topologically ordered, or critical.

**“Boundary topological order is ordinary SET order.”** Sometimes yes, sometimes no. A boundary topological order of an SPT may be anomalous and impossible in strict lower dimension.

**“Inflow cancels only perturbative anomalies.”** Inflow also describes global anomalies, discrete anomalies, gravitational anomalies, higher-form anomalies, and generalized symmetry anomalies, provided the correct background data are included.

**“If the total system is anomaly-free, the boundary anomaly vanished.”** No. The boundary anomaly is still present; it is canceled by the bulk. Cancellation is not the same as absence.

**“Every anomaly has a unique boundary.”** A single bulk anomaly can have many boundary realizations: gapless, symmetry-breaking, topologically ordered, or interfaces to other phases.

## Relations to other pages

[SPT Phases and Anomalies](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/spt-phases-and-anomalies/) develops the general bulk-response viewpoint.

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) gives the field-theory inflow formalism.

[Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/) explains SPT phases from the matter perspective.

[Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/) explains topological order with symmetry, including anomalous boundary SETs.

[Topological Order: Preview](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/topological-order-preview/) introduces the intrinsic boundary topological orders that can absorb anomalies.

[Relative QFT Preview](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/relative-qft-preview/) explains the vector-valued partition-function language.

## Research status

Anomaly inflow and SPT boundary anomalies are established conceptual tools. They are used across particle physics, condensed matter, topological phases, CFT, and generalized symmetry.

Active work continues on classifying symmetric gapped boundaries, anomalous SET phases, fermionic and crystalline anomalies, higher-form and higher-group anomalies, subsystem and fracton anomalies, non-invertible anomaly data, and SymTFT descriptions of generalized symmetry categories.

## Exercises

### Exercise 1: Inflow cancellation

Suppose a boundary effective action varies as

$$
\delta_\lambda W_{\partial M}[A]=\int_{\partial M}\lambda\,\mathcal I[A].
$$

What bulk variation is needed for the combined system to be invariant?

<details><summary><strong>Solution</strong></summary>

The combined variation must vanish:

$$
\delta_\lambda W_{\partial M}[A]+\delta_\lambda S_{\rm bulk}[A]=0.
$$

Therefore the bulk must vary as

$$
\delta_\lambda S_{\rm bulk}[A]=-\int_{\partial M}\lambda\,\mathcal I[A].
$$

This is anomaly inflow from the bulk to the boundary.

</details>

### Exercise 2: Boundary options

List three possible fates of the boundary of a nontrivial SPT phase that preserve locality and the bulk gap.

<details><summary><strong>Solution</strong></summary>

The boundary may be:

1. gapless and symmetry preserving;
2. gapped by spontaneously breaking the protecting symmetry;
3. gapped and symmetry preserving by developing intrinsic topological order.

A fourth possibility is that the boundary sits at a critical point or interface. What is forbidden is a trivially gapped, short-range-entangled, symmetry-preserving boundary.

</details>

### Exercise 3: Integer quantum Hall inflow

For

$$
S_{\rm bulk}[A]=\frac{k}{4\pi}\int_M A\wedge dA,
$$

show that under $A\mapsto A+d\lambda$ the variation is a boundary term.

<details><summary><strong>Solution</strong></summary>

Using $d^2\lambda=0$,

$$
\delta S_{\rm bulk}
=
\frac{k}{4\pi}\int_M d\lambda\wedge dA.
$$

Since

$$
d(\lambda\,dA)=d\lambda\wedge dA+\lambda\,d^2A=d\lambda\wedge dA,
$$

we get

$$
\delta S_{\rm bulk}
=
\frac{k}{4\pi}\int_{\partial M}\lambda\,dA.
$$

This boundary variation is canceled by the anomaly of the chiral edge theory.

</details>

### Exercise 4: Anomalous SET

Why can a symmetric topologically ordered boundary of an SPT phase be impossible as a standalone lower-dimensional SET phase?

<details><summary><strong>Solution</strong></summary>

The boundary topological order must carry the bulk anomaly. Its anyons, symmetry fractionalization, symmetry defects, or braiding data realize a symmetry action that cannot be consistently defined in a strictly lower-dimensional system with an on-site symmetry. The inconsistency is canceled only when the boundary is attached to the bulk SPT response. Thus it is a valid boundary SET, but anomalous as a standalone SET.

</details>

## References

- C. Callan and J. Harvey, “Anomalies and Fermion Zero Modes,” for the classic anomaly-inflow mechanism.
- E. Witten, “Global Gravitational Anomalies,” and related work on global anomaly phases.
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems* and later work on topological order, SPT order, and anomalous boundaries.
- A. Kapustin, “Symmetry Protected Topological Phases, Anomalies, and Cobordisms.”
- J. Wang, X.-G. Wen, and E. Witten, “Symmetric Gapped Interfaces of SPT and SET States: Systematic Constructions.”
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases.”
- Altland and Simons, *Condensed Matter Field Theory*, especially the topological field theory and anomalies chapters.

## Version history

- 2026-06-23: Initial polished draft. Added anomaly-inflow equation, SPT boundary diagnostics, anomalous SET discussion, symmetry-extension mechanism, higher-form/generalized extensions, and exercises.
