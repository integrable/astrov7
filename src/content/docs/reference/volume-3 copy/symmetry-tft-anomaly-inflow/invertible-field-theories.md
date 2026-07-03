---
title: "Invertible Field Theories"
description: "Explains invertible field theories as topological phases with inverse under stacking, and as the natural bulk theories that encode anomalies."
sidebar:
  label: "Invertible Field Theories"
  order: 4
level: Advanced
status: "Polished draft"
source: "Freed; Freed–Hopkins; Kapustin–Seiberg; Witten; modern anomaly and SPT references."
topics:
  - invertible field theory
  - invertible topological phase
  - anomaly theory
  - stacking
  - SPT phase
  - bordism
canonicalTopics:
  - invertible-field-theory
  - anomaly-theory
  - invertible-topological-phase
  - stacking-law
  - symmetry-protected-topological-phase
researchStatus:
  established:
    - "Invertible field theories are the standard modern language for ordinary anomaly inflow and for short-range-entangled topological phases protected by symmetry."
    - "They form abelian groups under stacking, after choosing the allowed spacetime and background structures."
  active:
    - "The classification and physical realization of invertible phases with fermionic, crystalline, higher-form, subsystem, and non-invertible symmetries remains an active research interface between QFT, topology, and condensed matter."
---

## Summary

An **invertible field theory** is a field theory that has an inverse under stacking. If $\mathcal I$ is invertible, there exists another theory $\mathcal I^{-1}$ such that

$$
\mathcal I\otimes \mathcal I^{-1}
\simeq
\mathbf 1,
$$

where $\mathbf 1$ is the trivial theory.

For a topological invertible theory, the Hilbert space on every closed spatial manifold is one-dimensional, and the partition function on a closed spacetime is a nonzero number, often a phase:

$$
Z_{\mathcal I}(M)\in U(1)
$$

in unitary topological examples. The theory has no intrinsic topological order in the sense of nontrivial anyon sectors or ground-state degeneracy depending on topology. It may nevertheless be highly nontrivial.

Invertible field theories matter here because ordinary anomalies are naturally represented by invertible bulk theories. A $d$-dimensional anomalous QFT is often a boundary of a $(d+1)$-dimensional invertible theory:

$$
\partial \mathcal I_{d+1}=\mathcal T_d
\quad
\text{as anomaly data}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing invertible field theories forming an abelian group under stacking, with an inverse theory cancelling the original and an anomalous boundary supported by a bulk invertible theory.](/figures/symmetry-anomalies-topology/invertible-field-theory-stacking.svg)

<figcaption>

Invertible field theories form a group under stacking. The inverse theory cancels the original up to deformation. In anomaly inflow, an anomalous boundary QFT is not standalone; it is naturally attached to an invertible bulk.

</figcaption>
</figure>

The important warning is:

$$
\text{invertible}\neq\text{trivial}.
$$

An invertible theory may have no deconfined anyons, no nontrivial fusion category of bulk excitations, and no topological ground-state degeneracy, while still carrying a nontrivial response action, protected boundary anomaly, or gravitational phase.

## Prerequisites

Read [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) first. You should also know the SymTFT slab picture and the distinction between anomalous boundary theories and gauge-invariant bulk-boundary systems.

This page uses “stacking” language from phases of matter and “partition function as a line” language from anomaly theory. No bordism calculation is required, but the page explains why bordism and generalized cohomology appear in precise classifications.

## Core idea

A general topological field theory can have nontrivial topological excitations, nontrivial ground-state degeneracy, and higher-dimensional state spaces. Such a theory is not invertible. A typical Dijkgraaf–Witten gauge theory or nonabelian Chern–Simons theory has genuine topological order.

An invertible topological field theory is much leaner. It assigns one-dimensional state spaces to closed spatial manifolds and phases to closed spacetime manifolds. It has no room for a nontrivial spectrum of topological anyons, but it can still assign meaningful phases depending on topology, background gauge fields, spin structure, or geometry.

In a slogan:

$$
\text{ordinary TQFT: topological sectors;}
\qquad
\text{invertible TQFT: topological phases}.
$$

The connection to anomalies is immediate. An anomaly is not a set of propagating bulk excitations. It is an obstruction phase. Therefore the bulk theory that represents an ordinary anomaly is expected to be invertible.

## Setup and conventions

Let $\mathcal I_d$ be a $d$-dimensional field theory. Stacking two theories means taking their tensor product:

$$
(\mathcal I_1\otimes\mathcal I_2)(M)
=
\mathcal I_1(M)\otimes\mathcal I_2(M)
$$

on state spaces, and

$$
Z_{\mathcal I_1\otimes\mathcal I_2}(M)
=
Z_{\mathcal I_1}(M)\,Z_{\mathcal I_2}(M)
$$

on closed spacetimes.

The trivial theory $\mathbf 1$ assigns

$$
Z_{\mathbf 1}(M)=1
$$

and one-dimensional trivial state spaces.

An invertible theory is one that has an inverse under this product. In unitary examples, the inverse is often the orientation-reversed or complex-conjugate theory:

$$
Z_{\mathcal I^{-1}}(M)=Z_{\mathcal I}(M)^{-1}.
$$

Precise statements require specifying the allowed structures on $M$: orientation, spin or Pin structure, background $G$-bundle, higher-form background, framing, metric, or crystalline structure. Invertibility is always invertibility **relative to a chosen class of backgrounds**.

:::note[Source note: structure matters]
The classification of invertible phases changes when one changes the allowed spacetime structure. Oriented, spin, Pin$^\pm$, framed, and $G$-background theories can have different invertible phases. This is why anomaly classifications always state the symmetry and tangential structure.
:::

## Invertible versus non-invertible topological theories

The phrase “topological field theory” is broad. Invertible theories form a special subgroup inside the much larger world of TQFTs.

| Feature | Invertible topological theory | Non-invertible topological theory |
|---|---|---|
| State space on closed space $\Sigma$ | One-dimensional line | Often higher-dimensional |
| Closed-spacetime partition function | Nonzero number, often a phase | May encode sums over sectors |
| Bulk topological excitations | None intrinsically | Anyons, lines, surfaces, defects |
| Stacking inverse | Exists | Usually does not |
| Typical role | Anomaly theory, SPT response | Topological order, gauge TQFT, anyon theory |

This distinction is essential. A theory can be topological without being invertible. For example, many Chern–Simons theories have nontrivial line operators and Hilbert spaces of dimension greater than one on a torus. They are topological, but not invertible.

Conversely, an invertible phase can be physically nontrivial even though it has no anyons. The nontriviality is detected by response phases and by anomalous boundaries.

## Stacking and the group of phases

Stacking makes invertible theories into an abelian group.

If $\mathcal I_1$ and $\mathcal I_2$ are invertible, then so is

$$
\mathcal I_1\otimes\mathcal I_2.
$$

The inverse satisfies

$$
\mathcal I\otimes\mathcal I^{-1}\simeq\mathbf 1.
$$

The equivalence relation is usually deformation through gapped theories preserving the chosen symmetry and spacetime structure. Under this relation, invertible phases form a group:

$$
\operatorname{Inv}_d(\mathcal S),
$$

where $\mathcal S$ denotes the chosen structure: orientation, spin, symmetry group, higher-form symmetry, and so on.

The identity element is the trivial product state or trivial field theory. The inverse is the phase that cancels the response of the original. Stacking is commutative up to the usual equivalences in local bosonic/fermionic systems, hence the group is abelian in standard settings.

This group viewpoint is the reason anomalies can be added and cancelled. If two boundary sectors have opposite anomaly theories, stacking them cancels the total anomaly.

## Anomalies as invertible bulk theories

A $d$-dimensional anomaly is represented by a $(d+1)$-dimensional invertible theory

$$
\mathcal I_{d+1}^{\mathrm{anom}}.
$$

The anomalous $d$-dimensional partition function is not an ordinary number by itself. It is naturally an element of a line determined by $\mathcal I_{d+1}^{\mathrm{anom}}$.

If two boundary theories have anomaly theories $\mathcal I$ and $\mathcal I^{-1}$, then their product is anomaly-free:

$$
\mathcal I\otimes\mathcal I^{-1}\simeq\mathbf 1.
$$

This is the modern form of anomaly cancellation.

For perturbative anomalies, $\mathcal I_{d+1}^{\mathrm{anom}}$ may be represented locally by a Chern–Simons-like action. For global anomalies, it may be represented by an eta invariant, Arf invariant, bordism invariant, or another global topological phase.

The point is not that every anomaly can be written as a simple integral of differential forms. The point is that ordinary anomalies are invertible: their data multiply like phases and can be cancelled by inverse phases.

## Symmetry-protected topological phases

An invertible phase with a symmetry is often called a **symmetry-protected topological phase** when it becomes trivial if the symmetry is forgotten but remains nontrivial when symmetry is preserved.

The phrase “protected” means that the phase cannot be smoothly deformed to the trivial product state without either closing the gap, breaking the symmetry, changing the allowed spacetime structure, or adding an inverse phase.

The boundary of a nontrivial SPT phase cannot be a trivially gapped symmetric boundary with no topological order. It must do something interesting:

1. remain gapless,
2. spontaneously break the protecting symmetry,
3. develop intrinsic topological order,
4. or exist only together with the bulk.

This is the condensed-matter face of anomaly inflow. The boundary has a ’t Hooft anomaly for the protecting symmetry, and the bulk SPT phase is the inflow theory.

## Response actions

Many invertible phases are detected by response actions. Examples include:

- Chern–Simons response terms,
- gravitational Chern–Simons terms,
- theta terms with quantized coefficients,
- Arf or Arf–Brown–Kervaire invariants,
- eta invariants,
- discrete group cocycle actions,
- bordism invariants.

A response action is a topological functional of background fields and spacetime structures:

$$
Z_{\mathcal I}[M,A]=\exp\bigl(2\pi i\,S_{\mathrm{top}}[M,A]\bigr).
$$

If $S_{\mathrm{top}}$ is well-defined modulo integers, then $Z_{\mathcal I}$ is a well-defined phase.

However, response actions must be used with care. A formula that is correct on closed manifolds may fail on manifolds with boundary unless boundary degrees of freedom or boundary conditions are included. That failure is precisely the anomaly inflow phenomenon.

## Invertible field theories and local counterterms

Some invertible theories correspond to local counterterms in $d$ dimensions. Others represent genuine $(d+1)$-dimensional anomaly data. The distinction depends on whether the invertible theory is a boundary variation of something defined in one lower dimension.

If an anomaly theory is trivial as an invertible field theory, then the anomaly can be removed by a local counterterm. If it is nontrivial, no allowed counterterm removes it.

In symbols, a trivial anomaly theory has the form

$$
\mathcal I_{d+1}\simeq \partial J_d
$$

for some local $d$-dimensional counterterm $J_d$. This notation is schematic: it means that the bulk phase is the change induced by a boundary functional.

The group of anomaly classes is therefore a quotient:

$$
\frac{\text{possible inflow phases}}{\text{trivial inflow phases from counterterms}}.
$$

This is why anomaly classification is naturally a cohomology or generalized-cohomology problem.

## Bordism viewpoint

A fully topological invertible theory assigns phases to closed manifolds with specified structure. If the partition function is invariant under bordism, then it defines a homomorphism

$$
\Omega_d^{\mathcal S}\longrightarrow U(1),
$$

where $\Omega_d^{\mathcal S}$ is a bordism group of $d$-manifolds with structure $\mathcal S$.

This is the mathematical reason bordism appears in anomaly and SPT classification. Roughly:

$$
\text{invertible phases}
\quad\leftrightarrow\quad
\text{homomorphisms from structured bordism groups}.
$$

The word “roughly” matters. Some classifications require spectra, Anderson duals, reflection positivity, torsion/free refinements, or careful distinctions between deformation classes and partition-function invariants. But the basic physical message is simple: an invertible topological theory is a rule that assigns compatible phases to structured manifolds.

For practical QFT work, one usually does not compute bordism groups from scratch. One uses the consequence: global anomalies may exist even when local anomaly polynomials vanish.

:::note[Source note: differential forms do not see everything]
De Rham characteristic classes detect the free, perturbative part of many anomalies. Torsion anomalies and fermionic phases often require integral cohomology, eta invariants, spin/Pin bordism, or related tools. This is one reason global anomalies are subtler than local current-divergence formulas.
:::

## Examples and non-examples

### A local Chern–Simons inflow phase

The three-dimensional Abelian Chern–Simons action

$$
\frac{k}{4\pi}\int A\wedge dA
$$

can represent an invertible response theory for suitable integer $k$ and background $A$, when the theory has no dynamical anyons and is used as a background response. If $A$ is instead a dynamical gauge field, the resulting Chern–Simons theory may have nontrivial line operators and need not be invertible. The same formula can therefore play different roles depending on what is background and what is dynamical.

### The E₈ phase

The bosonic $E_8$ quantum Hall state in $2+1$ dimensions is a standard invertible topological phase. It has no nontrivial anyons but has a nonzero chiral central charge. Its boundary cannot be a trivially gapped edge preserving the relevant structure.

### Dijkgraaf–Witten gauge theory

A Dijkgraaf–Witten theory with dynamical finite gauge fields is generally not invertible. It has nontrivial topological sectors. However, a group-cohomology SPT response action for a background finite $G$ gauge field is invertible. The difference is whether the $G$ field is background or dynamical.

### A theta term

A theta term on a closed manifold can define an invertible response phase when its coefficient and allowed bundles make the exponential well-defined. With boundaries, defects, or dynamical gauge fields, additional care is needed. The boundary variation or periodicity can encode an anomaly.

These examples are designed to prevent the most common mistake: a topological-looking action is not automatically an invertible field theory in every role.

## Role inside SymTFT

In a SymTFT, invertible theories appear in several ways.

First, the anomaly of a boundary QFT is an invertible bulk factor. Second, an SPT phase is an invertible bulk whose boundary carries an anomalous symmetry realization. Third, changing topological boundary conditions can stack or unstack invertible phases, thereby shifting anomaly representatives.

For ordinary invertible symmetries, the symmetry TFT may itself be non-invertible as a topological gauge theory, while the anomaly is an invertible part of its data. For non-invertible symmetries, the relation is richer: the full SymTFT may contain non-invertible defects, while anomaly-like obstructions can still include invertible response factors.

A useful mental split is:

$$
\text{SymTFT}=
\text{symmetry defects and gaugings}
+
\text{invertible anomaly data}.
$$

This split is not always literal, but it is a good first approximation.

## Common pitfalls

**“Invertible means physically empty.”** No. It means invertible under stacking. The theory can carry nontrivial response phases and anomalous boundaries.

**“Every TQFT is invertible.”** No. Most interesting TQFTs have nontrivial state spaces, anyons, defects, or topological sectors and are not invertible.

**“Chern–Simons theory is always invertible.”** No. A Chern–Simons response for background fields may define an invertible phase. A dynamical Chern–Simons gauge theory usually has nontrivial line operators and is not invertible.

**“Anomaly classifications are just de Rham cohomology.”** No. Differential forms miss torsion and many global anomalies.

**“Forgetting symmetry never matters.”** For SPT phases it matters completely. The phase may become trivial when the protecting symmetry or spin/Pin structure is forgotten.

**“The inverse phase is always obtained by changing the sign of a local action.”** Often, but not always. Global phases may require orientation reversal, complex conjugation, or more sophisticated inverse data.

## Relations to other pages

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) explains how invertible bulk theories cancel boundary anomalies. [SPT Phases and Anomalies](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/spt-phases-and-anomalies/) develops the condensed-matter interpretation. [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) explains how changing topological boundaries can stack, gauge, or remove invertible factors.

The [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/) chapter treats non-invertible TQFTs more broadly. The [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter explains local anomaly computations. The Mathematical Toolkit provides the necessary background on characteristic classes, bordism, spin structures, eta invariants, and differential cohomology.

## Research status

Invertible field theories are the standard language for modern anomaly theory and SPT phases. The broad picture is established: anomaly classes are represented by one-higher-dimensional invertible theories, and stacking gives an abelian group.

Active work continues on precise classifications with crystalline, fermionic, higher-form, subsystem, and non-invertible symmetries; on microscopic realizations of abstract invertible phases; and on the interplay between invertible anomaly data and non-invertible SymTFTs.

## Exercises

### Exercise 1: Stacking gives a group law

Suppose two invertible theories have partition functions $Z_1(M)$ and $Z_2(M)$ on closed spacetimes. Define stacking by

$$
Z_{1\otimes2}(M)=Z_1(M)Z_2(M).
$$

Show that if $Z_1(M)$ and $Z_2(M)$ are nonzero phases, then the stacked theory has an inverse.

<details><summary><strong>Solution</strong></summary>

If each $Z_i(M)$ is a phase, then

$$
Z_i(M)^{-1}=\overline{Z_i(M)}
$$

exists. The inverse of the stacked theory is the stack of inverses:

$$
Z_{(1\otimes2)^{-1}}(M)=Z_1(M)^{-1}Z_2(M)^{-1}.
$$

Then

$$
Z_{1\otimes2}(M)Z_{(1\otimes2)^{-1}}(M)
=
Z_1(M)Z_2(M)Z_1(M)^{-1}Z_2(M)^{-1}
=1.
$$

</details>

### Exercise 2: Why ordinary topological order is not invertible

A $2+1$-dimensional TQFT has a two-dimensional Hilbert space on the torus. Can it be invertible?

<details><summary><strong>Solution</strong></summary>

No, not as an invertible TQFT in the usual sense. An invertible topological field theory assigns one-dimensional state spaces to closed spatial manifolds. If the torus Hilbert space has dimension two, there is no tensoring with another finite-dimensional Hilbert space that produces a one-dimensional trivial Hilbert space, since dimensions multiply:

$$
2\times n\neq 1
$$

for any positive integer $n$.

</details>

### Exercise 3: Anomaly cancellation as stacking inverse

Suppose two boundary sectors have anomaly theories $\mathcal I$ and $\mathcal I^{-1}$. What is the anomaly of the product boundary theory?

<details><summary><strong>Solution</strong></summary>

Anomalies add by stacking their inflow theories. The product boundary has anomaly theory

$$
\mathcal I\otimes\mathcal I^{-1}\simeq\mathbf 1.
$$

Thus the total anomaly is trivial. This is the modern invertible-field-theory statement of anomaly cancellation.

</details>

### Exercise 4: Background versus dynamical fields

Why can the same Chern–Simons-looking formula sometimes describe an invertible response and sometimes a non-invertible TQFT?

<details><summary><strong>Solution</strong></summary>

If the gauge field in the Chern–Simons expression is a background, the expression can be a response phase assigned to background data. Such a response can be invertible if it has no independent topological sectors.

If the gauge field is dynamical, the path integral sums over gauge-field configurations and the theory may contain nontrivial Wilson lines, anyons, and higher-dimensional Hilbert spaces on nontrivial spatial manifolds. Then the theory is generally not invertible. The distinction is whether the field is a probe background or a dynamical topological degree of freedom.

</details>

## References

- D. Freed, “Anomalies and Invertible Field Theories.” Modern geometric treatment of anomalies as invertible field theories.
- D. Freed and M. Hopkins, “Reflection Positivity and Invertible Topological Phases.” Classification of invertible phases with reflection positivity and bordism spectra.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality.” QFT–TQFT coupling and global-form viewpoint.
- X. Chen, Z.-C. Gu, Z.-X. Liu, and X.-G. Wen, “Symmetry Protected Topological Orders and the Group Cohomology of Their Symmetry Group.” Group-cohomology SPT construction.
- E. Witten, “Fermion Path Integrals and Topological Phases.” Fermionic global phases, anomalies, and eta-invariant viewpoint.
- M. Atiyah, “Topological Quantum Field Theories.” Foundational axiomatic TQFT reference.
- A. Kitaev, “Anyons in an Exactly Solved Model and Beyond.” Standard source for topological phases and invertible/non-invertible distinctions in condensed matter.

## Version history

- **2026-06-20:** Initial polished draft. Added definitions, stacking group law, anomaly-theory interpretation, SPT connection, response actions, bordism viewpoint, examples, pitfalls, and exercises.
