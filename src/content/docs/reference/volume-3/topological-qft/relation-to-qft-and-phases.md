---
title: "Relation to QFT and Phases"
description: "Explains how topological quantum field theories arise from ordinary QFT, describe gapped phases, encode response and anomaly data, and serve as infrared effective theories."
sidebar:
  label: "Relation to QFT and Phases"
  order: 10
level: Advanced
status: "Polished draft"
source: "Wilson; Witten; Dijkgraaf–Witten; Altland–Simons Ch. 8; Kapustin–Seiberg; generalized symmetry and topological phases references."
topics:
  - TQFT
  - phases of matter
  - infrared QFT
  - gapped phases
  - topological order
  - SPT phases
  - response theory
canonicalTopics:
  - tqft-and-phases
  - infrared-topological-field-theory
  - topological-order
  - spt-response
  - anomaly-inflow
researchStatus:
  established:
    - "TQFTs are standard effective descriptions of many gapped phases and topological response theories, especially in low-dimensional quantum matter and topological gauge theory."
    - "Topological terms and topological sectors in ordinary QFT often survive in the infrared as TQFT data."
  active:
    - "The precise classification of phases, defects, generalized symmetries, non-invertible structures, and gapless-boundary constraints remains an active research area."
---

## Summary

A TQFT can appear in QFT in several different ways.

First, it can be a **standalone quantum field theory** whose observables are topological from the start, such as Chern–Simons theory, BF theory, or Dijkgraaf–Witten theory.

Second, it can be the **infrared limit of an ordinary QFT**. Many gapped systems forget local metric-dependent excitations at long distance but retain a finite topological sector. The low-energy theory is then a TQFT, possibly plus decoupled massive modes.

Third, it can be a **response theory** for a phase of matter. An SPT phase, integer quantum Hall state, or higher-form symmetry-protected phase may be described by an invertible topological action for background fields.

Fourth, it can be a **symmetry or anomaly theory**. SymTFT uses a one-higher-dimensional topological theory to package symmetry operators, background fields, gauging choices, and anomaly inflow.

The useful slogan is

$$
\text{ordinary QFT}
\quad\xrightarrow{\text{gap or topological sector}}\quad
\text{TQFT data}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic showing ordinary QFT flowing under RG to massive trivial phases, invertible response phases, and non-invertible topological order described by TQFT.](/figures/symmetry-anomalies-topology/tqft-qft-phases-map.svg)

<figcaption>

TQFTs often appear as infrared descriptions of ordinary QFTs. A gapped phase may be trivial, invertible with only response/anomaly data, or non-invertible with intrinsic topological order, ground-state degeneracy, and anyonic or extended excitations. SymTFT uses a related topological layer to encode symmetry data rather than only dynamical phases.

</figcaption>
</figure>

This page explains what survives from QFT into TQFT, what is lost, and why topological field theories are the right language for phases.

## Prerequisites

You should know the previous pages in this chapter: [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/), [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/), [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/), [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/), [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/), and [Observables in TQFT](/symmetry-anomalies-topology/topological-qft/observables-in-tqft/).

You should also know the basic meaning of RG flow, mass gap, correlation length, symmetry breaking, anomaly inflow, and background fields.

## Core idea

A generic QFT has local propagating degrees of freedom. Its correlation functions depend on distances, energies, temperatures, couplings, and metric data. A TQFT has no local propagating metric-dependent degrees of freedom. Its correlation functions depend only on topology, labels, and extra discrete structures.

The bridge is the infrared limit of a gapped theory. If a QFT has a mass gap $m$, then at distances

$$
L\gg m^{-1},
$$

local connected correlators of massive excitations decay exponentially. The only remaining long-distance data are global:

$$
\text{ground-state sectors},\quad
\text{defect fusion},\quad
\text{topological response},\quad
\text{boundary anomaly},\quad
\text{line and surface operators}.
$$

Those data can often be described by a TQFT.

This is not saying every gapped theory is interesting topologically. A completely trivial gapped phase has the trivial TQFT in the deep infrared. The point is that if anything nonlocal survives a gap, TQFT is the natural language for it.

## Setup and terminology

A **phase** is an equivalence class of theories or Hamiltonians under continuous deformations that do not close the gap and do not break the protecting assumptions, such as symmetry or spacetime structure.

A **trivial gapped phase** has a unique ground state on closed spatial manifolds and no nontrivial topological excitations or response, after allowing local counterterms.

An **invertible phase** has no intrinsic topological order but may have a nontrivial topological response or anomalous boundary. Its effective TQFT has an inverse under stacking.

A **topologically ordered phase** has intrinsic long-range entanglement. Its TQFT is generally non-invertible and may have ground-state degeneracy on nontrivial spatial manifolds, anyons or extended excitations, and nontrivial fusion/braiding data.

An **SPT phase** is a symmetry-protected invertible phase: it is trivial if the symmetry is ignored, but nontrivial with the symmetry preserved.

A **SymTFT** is not necessarily the infrared phase of a physical system. It is a topological theory used to encode symmetry and anomaly data of a boundary QFT.

:::note[Source note: phase language]
The same words are used slightly differently in high-energy, condensed-matter, and mathematical communities. This page uses the physics convention in which “phase” means equivalence under gapped symmetry-preserving deformations, while “TQFT” denotes the long-distance topological field theory capturing universal topological data.
:::

## RG flow to a TQFT

Renormalization group flow removes short-distance details. In a gapped phase, long-distance correlation functions of local operators approach constants or decay exponentially. If the theory has no topological sectors, the endpoint is trivial:

$$
Z_{\mathrm{IR}}(M)=1
$$

up to local counterterms and normalization choices.

If the theory has topological order or topological response, the endpoint is a nontrivial TQFT:

$$
\text{QFT}_{\mathrm{UV}}
\quad\longrightarrow\quad
\text{TQFT}_{\mathrm{IR}}.
$$

This statement is schematic. The real RG flow may contain irrelevant operators, massive modes, and finite-correlation-length corrections. The TQFT captures the universal part:

$$
Z_{\mathrm{QFT}}(M,g)
\sim
e^{-E_0\operatorname{Vol}(M)+\cdots}\,
Z_{\mathrm{TQFT}}(M)
$$

at long distances, where the omitted terms are nonuniversal local contributions. The topological factor is what remains after stripping away local metric-dependent pieces.

This is why TQFT is an infrared effective theory, not necessarily the microscopic theory.

## Topological response

A phase may have no fractionalized excitations but still have a topological response to background fields. For example, in $2+1$ dimensions an integer quantum Hall phase has an effective response

$$
S_{\mathrm{eff}}[A]=\frac{k}{4\pi}\int A\wedge dA
$$

for a background electromagnetic field $A$. This is an invertible TQFT response. It predicts Hall conductance and boundary anomaly, even though the bulk is gapped.

More generally, a response action is a functional

$$
Z_{\mathrm{response}}[M,A]
=
\exp(iS_{\mathrm{top}}[M,A])
$$

depending on spacetime topology and background fields. It may encode:

| Response | What it diagnoses |
|---|---|
| Chern–Simons term | Hall conductance, parity anomaly, boundary chiral modes |
| theta term | time-reversal and instanton-sector response |
| Dijkgraaf–Witten cocycle | finite-symmetry SPT phase |
| gravitational Chern–Simons term | chiral central charge or thermal Hall response |
| higher-form response | higher-form SPT or generalized-symmetry anomaly |

The response theory is topological when it is insensitive to metric deformations after all required structures are fixed.

## Intrinsic topological order

Intrinsic topological order is more than response. It has internal topological degrees of freedom that cannot be removed by local symmetric deformations.

Typical signatures include:

$$
\dim\mathcal H(\Sigma)\neq 1
$$

on some closed spatial manifolds $\Sigma$, nontrivial anyons or extended excitations, fusion and braiding, and topological entanglement entropy.

In $2+1$ dimensions, a modular tensor category often captures the anyon content of a semisimple topological order. Chern–Simons TQFTs provide many examples. Finite gauge theories and Dijkgraaf–Witten theories provide another family.

In higher dimensions, excitations can be loops, membranes, or higher-dimensional defects. BF theories often describe discrete higher-form topological order, with line-surface linking phases rather than just particle braiding.

A topologically ordered phase cannot be fully characterized by local order parameters. Its data are detected by placing the theory on nontrivial manifolds and by studying extended operators.

## Symmetry-protected phases

An SPT phase is short-range entangled but nontrivial in the presence of symmetry. Its bulk is invertible, but its boundary cannot be trivially gapped while preserving the symmetry unless additional topological order or anomaly cancellation is supplied.

The diagnostic is anomaly inflow. A $d$-dimensional boundary theory with a ’t Hooft anomaly can appear as the boundary of a $(d+1)$-dimensional SPT. The bulk response changes under background gauge transformations precisely to cancel the boundary anomaly.

Schematically,

$$
\delta S_{\mathrm{bulk}}[A]
+
\delta W_{\mathrm{boundary}}[A]
=0.
$$

This is why SPT phases and anomalies are two sides of the same structure. The SPT is an invertible bulk TQFT; the anomaly is the obstruction seen by the boundary theory alone.

## Broken symmetry and TQFT

Spontaneous symmetry breaking is not automatically topological order. A ferromagnet or ordinary superfluid has gapless Goldstone modes if a continuous global symmetry is broken. Such a phase is not described purely by a TQFT at long distances because gapless modes remain.

A discrete symmetry-broken phase can be gapped, but it usually has multiple vacua rather than intrinsic topological order. A low-energy description may include a finite set of superselection sectors and domain walls, but whether one calls this a TQFT depends on the precise limit and boundary conditions.

The useful distinction is:

| Phase feature | Long-distance description |
|---|---|
| unbroken trivial gapped phase | trivial TQFT |
| discrete symmetry breaking | vacuum sectors and domain-wall data |
| continuous symmetry breaking | gapless Goldstone EFT, not pure TQFT |
| invertible SPT | invertible response TQFT |
| intrinsic topological order | non-invertible TQFT |
| deconfined gauge theory with finite gauge group | finite gauge TQFT |

TQFT is the right language when no local gapless metric-dependent modes survive.

## Gauge theory phases

Gauge theories supply many routes to TQFT.

A Higgs phase of a $U(1)$ gauge theory in which charge-$N$ matter condenses can leave a low-energy $\mathbb Z_N$ gauge theory. In four dimensions, a continuum description can be a BF theory,

$$
S=\frac{N}{2\pi}\int B\wedge dA.
$$

This TQFT captures line-surface linking and discrete electric/magnetic topological sectors.

A confining phase may have a different topological sector, especially when center symmetry, theta angles, or global form of the gauge group is important. A Coulomb phase with a massless photon is not a TQFT because the photon remains gapless, but its electric and magnetic one-form symmetries may still be described using topological symmetry operators.

Chern–Simons terms in three-dimensional gauge theory can gap gauge fields and leave a topological field theory. This is why Chern–Simons–matter theories often flow to topological or nearly topological sectors in the infrared.

## Boundaries and edge modes

A bulk TQFT often has nontrivial boundary physics. Sometimes the boundary is itself topological. Sometimes it is gapless. Sometimes it can be gapped only after adding boundary degrees of freedom or choosing a condensate.

Examples:

| Bulk | Boundary phenomenon |
|---|---|
| Chern–Simons theory | chiral WZW or edge current algebra |
| SPT response | anomalous boundary theory |
| finite gauge theory | boundary anyon condensation or module category |
| BF theory | boundary symmetry modes or dual scalar theories |
| SymTFT | topological boundary encodes gauging/global-form choice |

The boundary is not optional bookkeeping. It is often where the physical anomaly or protected mode appears.

This is one reason TQFT sits naturally in the Symmetry, Anomalies, and Topology volume: topological phases, anomaly inflow, and boundary conditions are one story.

## TQFT versus effective field theory

A TQFT is an effective field theory, but not every EFT is topological.

An EFT keeps the degrees of freedom relevant at a scale. A Goldstone EFT keeps massless fields. A Fermi-liquid EFT keeps quasiparticles near a Fermi surface. A hydrodynamic EFT keeps conserved densities. A TQFT keeps only topological data.

So the hierarchy is:

$$
\text{QFT}
\longrightarrow
\text{IR EFT}
\longrightarrow
\text{TQFT only if no local gapless modes remain}.
$$

This distinction prevents a common mistake: topological terms can appear inside non-topological EFTs. For example, a sigma model may contain a theta term or Wess–Zumino term but still have local propagating modes. The presence of a topological term does not make the whole theory a TQFT.

## Relation to generalized symmetries

Generalized symmetries are often most visible through topological operators. In a gapped phase, those topological symmetry operators may become part of the infrared TQFT.

A $q$-form symmetry acts on $q$-dimensional charged operators. If the phase is gapped and the charged operators have topological behavior, the symmetry action is encoded by linking and fusion in the TQFT.

Gauging a finite higher-form symmetry can produce a new TQFT. Condensing a bosonic anyon in a $2+1$-dimensional topological order is another kind of gauging or quotient operation in categorical language. These operations connect phases by changing the spectrum of genuine topological operators.

This is the bridge from TQFT to non-invertible symmetry, SymTFT, and categorical phases.

## What TQFT forgets

Because TQFT captures only universal topological data, it forgets many physically important quantities:

```txt
correlation length
microscopic Hamiltonian
nonuniversal ground-state energy density
velocities and dispersion relations
massive excitation gaps
local operator dimensions away from fixed points
thermal activation scales
```

This forgetting is a feature, not a bug. A phase is universal precisely because many microscopic details do not matter. But if you need the energy gap, transport coefficient, spectral function, or finite-temperature crossover, the TQFT is not enough.

A mature analysis often combines:

$$
\text{TQFT data}
+
\text{irrelevant corrections}
+
\text{massive excitations}
+
\text{boundary dynamics}.
$$

## Common pitfalls

**“Every gapped phase is a nontrivial TQFT.”** No. Many gapped phases are topologically trivial.

**“Topological term means TQFT.”** No. A theory can have propagating modes and also contain a topological term.

**“SPT phases are topologically ordered.”** In the common condensed-matter usage, SPT phases are invertible and short-range entangled; intrinsic topological order is non-invertible and long-range entangled.

**“A TQFT knows all low-energy physics.”** It knows the universal topological part. It does not know nonuniversal local energetics or all finite-gap corrections.

**“Boundary modes contradict a gapped bulk.”** No. A gapped topological bulk can require gapless or topologically ordered boundary behavior when symmetry or anomaly constraints are imposed.

## Relations to other pages

[Observables in TQFT](/symmetry-anomalies-topology/topological-qft/observables-in-tqft/) explains the topological data that survive in the infrared. [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/), [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/), and [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) give concrete TQFTs used in phases.

[SPT Phases and Anomalies](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/spt-phases-and-anomalies/) develops the invertible/anomaly side. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) explains how topological theories encode symmetry data. The Matter, Statistical Physics, and Quantum Information volume develops physical phases of matter in more detail.

## Research status

The use of TQFT as the universal long-distance description of many gapped phases is established. Chern–Simons theory, BF theory, Dijkgraaf–Witten theory, and invertible response actions are standard tools.

Active work concerns classification beyond simple symmetry groups, fermionic and crystalline phases, fracton and subsystem-symmetric phases, non-semisimple and non-unitary topological orders, gapless boundaries, non-invertible symmetries, and the precise relation between categorical data and microscopic lattice or continuum QFTs.

## Exercises

### Exercise 1: Trivial versus invertible

Explain the difference between a trivial gapped phase and a nontrivial invertible phase.

<details><summary><strong>Solution</strong></summary>

Both can have no intrinsic topological order and no nontrivial bulk anyons or ground-state degeneracy. A trivial gapped phase has no protected topological response after allowing local counterterms. A nontrivial invertible phase has a topological response or anomalous boundary protected by symmetry or spacetime structure. It has an inverse under stacking, but it is not equivalent to the trivial phase while the protecting structure is preserved.

</details>

### Exercise 2: Why Goldstone phases are not pure TQFTs

Why is a phase with spontaneously broken continuous global symmetry not described solely by a TQFT?

<details><summary><strong>Solution</strong></summary>

Breaking a continuous global symmetry produces gapless Goldstone modes under the usual assumptions. These modes have local propagating degrees of freedom and correlation functions that depend on distances and momenta. A pure TQFT has no such local metric-dependent excitations. The phase may still have topological defects or topological terms, but its full infrared theory is a Goldstone EFT, not just a TQFT.

</details>

### Exercise 3: BF theory as a discrete gauge phase

A four-dimensional theory has low-energy action

$$
S=\frac{N}{2\pi}\int B\wedge dA.
$$

What topological feature does this encode?

<details><summary><strong>Solution</strong></summary>

This BF theory encodes a discrete $\mathbb Z_N$ gauge sector. It has topological line and surface operators with a linking phase. If a line of unit electric charge links a surface of unit magnetic or higher-form charge, the path integral acquires a phase of order $N$. The theory captures the universal topological data left after local massive modes are integrated out.

</details>

## References

- E. Witten, “Quantum Field Theory and the Jones Polynomial.”
- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology.”
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*, for topological order and phases.
- A. Kitaev, “Fault-tolerant quantum computation by anyons,” for anyonic/topological-order intuition.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for QFT–TQFT coupling and global-form choices.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for higher-form symmetries and gauging.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for topological field theory, topological quantum matter, theta terms, Wess–Zumino terms, Chern–Simons terms, and gauge-theory applications.
- M. Nakahara, *Geometry, Topology and Physics*, and T. Frankel, *The Geometry of Physics*, for geometry and topology background.

## Version history

- **2026-06-23:** Initial polished draft. Added RG-to-TQFT viewpoint, topological response, intrinsic topological order, SPT/anomaly relation, gauge-theory phases, boundary modes, EFT comparison, and generalized-symmetry connection.
