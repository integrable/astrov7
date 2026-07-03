---
title: "Topological Order: Preview"
description: "Preview of intrinsic topological order as long-range entangled gapped phases with anyons, ground-state degeneracy, topological entanglement entropy, emergent gauge structure, and TQFT descriptions."
sidebar:
  label: "Topological Order: Preview"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wen; Kitaev; Levin–Wen; Kitaev–Preskill; Altland–Simons Ch. 8; standard anyon, TQFT, and condensed-matter field theory references."
topics:
  - topological order
  - anyons
  - long-range entanglement
  - topological entanglement entropy
  - ground-state degeneracy
  - emergent gauge theory
canonicalTopics:
  - intrinsic-topological-order
  - long-range-entangled-phase
  - anyon
  - topological-ground-state-degeneracy
  - topological-entanglement-entropy
researchStatus:
  established:
    - "Intrinsic topological order is a standard organizing notion for gapped phases with long-range entanglement, robust topological degeneracy, and fractionalized or extended excitations."
  active:
    - "Higher-dimensional, fermionic, gapless, fractonic, non-invertible, and symmetry-enriched topological orders remain active research areas."
---

## Summary

**Topological order** is the kind of order that survives after Landau symmetry breaking has run out of vocabulary. A topologically ordered phase can have no local order parameter, no broken symmetry, and yet still be sharply distinct from a trivial gapped phase.

The short slogan is:

$$
\text{intrinsic topological order}
=
\text{long-range entangled gapped order}.
$$

In two spatial dimensions, its most famous signatures are:

- anyonic excitations with nontrivial braiding;
- robust ground-state degeneracy on spatial manifolds with nontrivial topology;
- topological entanglement entropy;
- emergent gauge fields or deconfined gauge constraints;
- a low-energy topological quantum field theory;
- boundaries and defects with nontrivial algebraic data.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Topological order diagnostics: ground-state degeneracy on a torus, anyon braiding, topological entanglement entropy, and low-energy TQFT.](/figures/symmetry-anomalies-topology/topological-order-diagnostics.svg)

<figcaption>

Topological order is not diagnosed by a local order parameter. Its stable signatures are global: topology-dependent ground states, braided excitations, universal entanglement constants, and a low-energy TQFT sector.

</figcaption>
</figure>

This page is a preview. It gives the conceptual map needed for the surrounding pages on SPT phases, SET phases, anomaly-boundary correspondence, higher-form symmetry, and response theory. A full treatment of anyon categories, lattice Hamiltonians, modular tensor categories, and topological quantum computation belongs to more specialized pages.

## Prerequisites

You should know [Landau Symmetry Breaking](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/landau-symmetry-breaking/), [Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/), [Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/), and the [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/) chapter overview.

For a first pass, keep this contrast in mind:

| Phase type | Short slogan | Needs symmetry? | Has intrinsic topological order? |
|---|---|---:|---:|
| Landau ordered phase | symmetry is broken | yes | no |
| SPT phase | short-range entangled but symmetry-protected | yes | no |
| SET phase | topological order plus symmetry enrichment | yes | yes |
| Intrinsic topological order | long-range entangled phase | no | yes |

## Core idea

Landau theory classifies phases by local order parameters and symmetry-breaking patterns. This works beautifully for ferromagnets, crystals, superfluids, and many familiar phases. It fails for phases such as fractional quantum Hall states and deconfined gauge phases.

Topological order is a statement about the structure of the many-body ground state and the algebra of excitations. A topologically ordered phase cannot be transformed into a product state by any finite-depth local unitary, even if all global symmetries are ignored. This is why it is called **intrinsic** topological order.

Compare this with an SPT phase. An SPT phase becomes trivial if one breaks or ignores the protecting symmetry. A topologically ordered phase does not. Its nontriviality is built into long-range entanglement and deconfined topological excitations.

The most useful diagnostic sentence is:

$$
\text{topological order is invisible locally but visible globally}.
$$

Local correlators may look completely unremarkable, while the Hilbert space on a torus, the braiding of quasiparticles, or the entanglement constant reveals the phase.

## Setup and conventions

Let the spatial dimension be $D$ and spacetime dimension be $d=D+1$. Most explicit examples on this page are in $D=2$, where pointlike excitations can braid nontrivially. The low-energy topological sector is often described by a $2+1$-dimensional TQFT.

A gapped topologically ordered phase has a correlation length $\xi$. For distances much larger than $\xi$, local microscopic details are invisible, and robust observables are captured by topological data. The effective partition function on a closed spacetime manifold $M_d$ has the schematic form

$$
Z_{\rm IR}(M_d)\simeq Z_{\rm TQFT}(M_d)
$$

up to nonuniversal massive contributions.

In $2+1$ dimensions, the quasiparticle types are often denoted

$$
a,b,c,\ldots,
$$

with fusion rules

$$
a\times b=\sum_c N_{ab}{}^c\,c.
$$

They also have topological spins $\theta_a$, quantum dimensions $d_a$, and braiding data. This page uses those symbols only as orientation; the full categorical formalism appears later.

:::note[Source note: vocabulary]
The phrase “topological order” was introduced to describe phases not characterized by symmetry breaking. Modern usage often distinguishes **intrinsic topological order**, meaning long-range entangled order, from broader uses of “topological phase” that include SPT phases and band topology.
:::

## Diagnostic 1: topology-dependent ground states

A topologically ordered phase can have a ground-state degeneracy that depends on the topology of space. For example, the toric code has four ground states on a spatial torus.

This degeneracy is not the same as symmetry-breaking degeneracy. In a symmetry-breaking phase, degenerate ground states are locally distinguishable by an order parameter. In a topologically ordered phase, the different ground states on a closed manifold are locally indistinguishable. No local operator supported in a disk can reliably tell them apart in the infinite-size limit.

The splitting between these states in a finite system is exponentially small:

$$
\Delta E\sim e^{-L/\xi},
$$

where $L$ is the system size and $\xi$ is the correlation length. The degeneracy is therefore stable against arbitrary local perturbations that do not close the gap.

On a genus-$g$ surface, many $2+1$-dimensional topological orders have a ground-state degeneracy determined by their anyon data. This is one of the reasons TQFT is the natural low-energy language: the TQFT assigns a vector space to a spatial manifold, and the dimension of that vector space is the topological ground-state degeneracy.

## Diagnostic 2: anyons and braiding

In two spatial dimensions, pointlike excitations can have exchange statistics more general than bosonic or fermionic signs. These are **anyons**.

There are two kinds of braiding data. Abelian anyons acquire phases under exchange or braiding. Nonabelian anyons act on a degenerate fusion space by matrices.

If an anyon $a$ encircles an anyon $b$, a correlation function or state can acquire a topological phase or a linear transformation. This effect depends only on the topology of the braid, not on the detailed path, as long as the gap remains open and no other excitations are crossed.

The fusion rule

$$
a\times b=\sum_c N_{ab}{}^c\,c
$$

means that bringing anyons $a$ and $b$ together can produce superselection sector $c$ with multiplicity $N_{ab}{}^c$. This fusion algebra is one of the central pieces of topological order.

For Abelian anyons, fusion is group-like. For nonabelian anyons, fusion can have multiple outcomes. That is one reason topological order, non-invertible defects, and categorical symmetry keep speaking similar algebraic languages.

## Diagnostic 3: topological entanglement entropy

For a gapped phase in two spatial dimensions, the entanglement entropy of a large simply connected region often has the form

$$
S(A)=\alpha |\partial A|-\gamma+O(e^{-L/\xi}),
$$

where $\alpha$ is nonuniversal and $\gamma$ is universal. The constant

$$
\gamma=\log\mathcal D
$$

is the **topological entanglement entropy**, with

$$
\mathcal D=\sqrt{\sum_a d_a^2}
$$

the total quantum dimension of the anyon theory.

The area-law coefficient $\alpha$ depends on the UV cutoff and microscopic details. The constant correction $\gamma$ is long-distance data. It sees long-range entanglement invisible to local order parameters.

This diagnostic is extremely useful conceptually, but one should not oversell it. Extracting $\gamma$ in numerical systems can be hard; gapless systems, corners, finite-size effects, and symmetry defects can complicate the interpretation.

## Diagnostic 4: emergent gauge structure

Many topologically ordered phases can be understood as deconfined gauge theories at low energy. The toric code is the canonical example: it is a deconfined $\mathbb Z_2$ gauge theory.

Its anyons are

$$
1,\quad e,\quad m,\quad \epsilon=e\times m.
$$

Here $e$ is the electric charge, $m$ is the magnetic flux or vison, and $\epsilon$ is their composite. The fusion rules are

$$
e^2=m^2=\epsilon^2=1,\qquad e\times m=\epsilon.
$$

The $e$ and $m$ particles have mutual semionic braiding: taking $e$ around $m$ gives a phase $-1$. The composite $\epsilon$ is a fermion.

This example is simple but profound. It shows that a bosonic spin system can have emergent gauge structure and emergent excitations with fractionalized statistics. Nothing in the microscopic Hilbert space had to contain literal fundamental anyons.

## What makes the order intrinsic?

An intrinsic topological order cannot be removed by adding local symmetric or nonsymmetric perturbations, unless the bulk gap closes or the phase transition changes the long-range entanglement pattern.

This distinguishes it from:

- a trivial product phase;
- a conventional symmetry-breaking phase;
- an SPT phase that becomes trivial when the symmetry is ignored;
- a free-fermion band topology that may depend on protecting symmetries or stable equivalence.

A useful operational test is finite-depth circuits. A short-range entangled state can be mapped to a product state by a finite-depth local unitary. A long-range entangled topologically ordered state cannot.

That statement is sharper in lattice systems than in continuum QFT, but the continuum intuition is the same: intrinsic topological order contains global entanglement and superselection structure that local deformations cannot erase.

## Relation to SPT and SET phases

SPT phases and intrinsic topological orders sit on different sides of a crucial line.

An SPT phase has no intrinsic topological order. On a closed spatial manifold, it has no topological ground-state degeneracy and no deconfined anyons. Its nontriviality is protected by symmetry and appears through boundary anomalies or response actions.

A SET phase has intrinsic topological order plus symmetry. The symmetry can permute anyons, fractionalize on anyons, or produce nontrivial symmetry defects. SET phases therefore combine two kinds of data:

$$
\text{SET}=
\text{topological order}
+
\text{symmetry action/enrichment}.
$$

This distinction matters because the same underlying topological order can support many inequivalent symmetry enrichments. For example, a $\mathbb Z_2$ spin liquid may have $e$ or $m$ particles carrying projective representations of spin rotation or time reversal.

## Boundaries of topological order

Topological order often has nontrivial boundaries. Some boundaries are gapless. Some are gapped by condensing a subset of anyons. Some support lower-dimensional topological or anomalous degrees of freedom.

For the toric code, one can have rough and smooth boundaries, roughly corresponding to condensing $e$ or $m$ anyons. Boundary choices are not decoration. They are part of the extended topological data.

A topological order may or may not admit a fully gapped boundary to the vacuum. The answer is controlled by anyon condensation or, more generally, by algebraic data in the anyon category. In higher-dimensional language, whether a topological order can live as a standalone bulk or only as an anomalous boundary is a deep question.

This is the bridge to the next page: anomaly-boundary correspondence.

## Higher-dimensional topological order

In three spatial dimensions and higher, the excitations of topological order are not only pointlike anyons. They can include loops, strings, membranes, and higher-dimensional defects. Braiding is replaced or supplemented by linking and higher-dimensional motion.

A $3+1$-dimensional $\mathbb Z_N$ gauge theory has pointlike electric charges and looplike magnetic fluxes. The robust statistics are captured by linking between worldlines and worldsheets. This is naturally described using higher-form symmetries and BF-type topological field theories.

The moral is that topological order is not a purely two-dimensional phenomenon. What is special about two dimensions is the richness and familiarity of point-particle braiding.

## Common pitfalls

**“Topological order means any phase with topology.”** Not quite. SPT phases and Chern numbers are often called topological, but intrinsic topological order specifically means long-range entangled order with robust topological excitations or degeneracy.

**“Topological ground-state degeneracy is just symmetry breaking.”** No. Symmetry-breaking vacua are locally distinguishable. Topological ground states are locally indistinguishable on closed manifolds.

**“Anyons are optional decoration.”** In $2+1$ dimensions, anyon fusion and braiding are the operational content of the topological order.

**“A TQFT is always the whole phase.”** A TQFT captures the universal long-distance topological sector. It does not encode microscopic spectra, nonuniversal edge velocities, lattice-scale details, or every possible irrelevant deformation.

**“Topological order requires a microscopic gauge field.”** No. Gauge structure can emerge in the infrared from a spin or boson model.

**“SPT phases are topologically ordered in the intrinsic sense.”** Usually no. SPT phases are short-range entangled; intrinsic topological order is long-range entangled.

## Relations to other pages

[Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/) explains short-range-entangled topological phases protected by symmetry.

[Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/) explains what happens when intrinsic topological order carries a global symmetry action.

[Anomaly–Boundary Correspondence](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/anomaly-boundary-correspondence/) explains when a topological order can appear only as a boundary of a higher-dimensional bulk.

[Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/) gives the long-distance language for many topologically ordered phases.

[Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) explains why extended operators and linking are natural symmetry diagnostics in topological phases.

## Research status

Intrinsic topological order is established physics in $2+1$-dimensional gapped systems, with a mature language of anyons, modular tensor categories, lattice models, Chern–Simons theory, and quantum error-correcting codes.

Active areas include higher-dimensional topological order, fermionic topological orders, fracton phases, gapless topological orders, non-invertible symmetry actions on topological phases, categorical classifications, and the precise interface between topological order and quantum information.

## Exercises

### Exercise 1: Local versus topological degeneracy

Explain why two symmetry-breaking vacua can be distinguished by a local order parameter, while topological ground states on a torus cannot be distinguished by any local operator in the infinite-size limit.

<details><summary><strong>Solution</strong></summary>

In a symmetry-breaking phase, different vacua have different expectation values of a local order parameter, such as magnetization:

$$
\langle M\rangle_+\neq \langle M\rangle_-.
$$

Thus a local measurement can tell which vacuum was chosen.

In a topologically ordered phase, ground states on a closed manifold differ by global flux or loop data. Local operators supported in a contractible region cannot detect which global cycle carries which topological data. Their matrix elements between different topological ground states vanish up to corrections exponentially small in the system size, while diagonal matrix elements agree up to similar corrections.

</details>

### Exercise 2: Toric code fusion

The toric code has anyons $1,e,m,\epsilon$ with $e^2=m^2=1$ and $\epsilon=e\times m$. Compute $e\times\epsilon$ and $m\times\epsilon$.

<details><summary><strong>Solution</strong></summary>

Using $\epsilon=e\times m$ and associativity,

$$
e\times\epsilon=e\times e\times m=1\times m=m.
$$

Similarly,

$$
m\times\epsilon=m\times e\times m=e\times m\times m=e.
$$

So $e$ and $m$ exchange when fused with $\epsilon$.

</details>

### Exercise 3: Topological entanglement entropy

Suppose a $2+1$-dimensional topological order has Abelian anyons $a=1,\ldots,N$, each with $d_a=1$. What is the topological entanglement entropy?

<details><summary><strong>Solution</strong></summary>

The total quantum dimension is

$$
\mathcal D=\sqrt{\sum_a d_a^2}=\sqrt{\sum_{a=1}^N 1}= \sqrt N.
$$

Therefore

$$
\gamma=\log\mathcal D=\frac12\log N.
$$

For the toric code, $N=4$, so $\gamma=\log 2$.

</details>

### Exercise 4: SPT versus intrinsic topological order

Give one diagnostic that distinguishes an SPT phase from an intrinsic topological order on a closed spatial manifold.

<details><summary><strong>Solution</strong></summary>

An intrinsic topological order can have topology-dependent ground-state degeneracy on a closed spatial manifold, such as a torus. An SPT phase, being short-range entangled and having no intrinsic topological order, does not have such robust topological degeneracy on a closed manifold. Its nontriviality instead appears through symmetry-protected boundary behavior or response to background fields.

</details>

## References

- X.-G. Wen, “Topological Orders in Rigid States,” and later reviews on quantum order and long-range entanglement.
- A. Kitaev, “Fault-Tolerant Quantum Computation by Anyons,” for the quantum-double/toric-code viewpoint.
- M. Levin and X.-G. Wen, “String-Net Condensation: A Physical Mechanism for Topological Phases.”
- A. Kitaev and J. Preskill, “Topological Entanglement Entropy.”
- M. Levin and X.-G. Wen, “Detecting Topological Order in a Ground State Wave Function.”
- Altland and Simons, *Condensed Matter Field Theory*, especially the chapters on topological field theory and gauge theory.
- Nakahara, *Geometry, Topology and Physics*, for the geometric and topological language used in gauge and topological field theories.

## Version history

- 2026-06-23: Initial polished preview. Added intrinsic-order diagnostics, toric-code example, anyon/fusion language, entanglement diagnostic, SPT/SET comparison, and exercises.
