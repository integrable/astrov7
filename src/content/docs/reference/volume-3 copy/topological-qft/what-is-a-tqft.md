---
title: "What Is a TQFT?"
description: "Defines topological quantum field theory from path-integral, functorial, and infrared-physics viewpoints, with examples and cautions."
sidebar:
  label: "What Is a TQFT?"
  order: 1
level: Advanced
status: "Polished draft"
source: "Atiyah; Segal; Schwarz; Witten; Dijkgraaf–Witten; Freed; Polyakov; Nakahara; Frankel; Altland–Simons."
topics:
  - topological quantum field theory
  - TQFT
  - functorial field theory
  - metric independence
  - Chern-Simons theory
  - BF theory
  - Dijkgraaf–Witten theory
canonicalTopics:
  - topological-qft
  - functorial-tqft
  - metric-independence
  - topological-gauge-theory
researchStatus:
  established:
    - "The basic path-integral and functorial meanings of TQFT are standard, and Chern–Simons, BF, finite gauge, and cohomological TQFTs are canonical examples."
  active:
    - "Extended TQFT, defect-complete formulations, non-semisimple examples, fermionic/spin refinements, and SymTFT applications remain active research areas."
---

## Summary

A **topological quantum field theory** is a quantum field theory whose protected observables depend on topology rather than on local metric geometry. In practice, the phrase is used in three closely related ways.

First, a TQFT can be a **path-integral theory** whose action and observables are metric-independent, as in Chern–Simons theory or BF theory. Second, a TQFT can be an **axiomatic functor**, assigning vector spaces to spatial manifolds and linear maps to bordisms. Third, a TQFT can be an **infrared effective theory** describing the protected long-distance sector of a gapped phase.

The shortest useful slogan is

$$
\text{TQFT}=\text{QFT whose protected data are invariant under smooth deformations}.
$$

That slogan is intentionally broad. It includes theories with no local propagating degrees of freedom, theories obtained by topological twisting, finite gauge theories, low-energy topological phases, and symmetry TFTs.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Three lenses on TQFT: path integral, functorial assignment, and infrared topological phase.](/figures/symmetry-anomalies-topology/what-is-tqft-lenses.svg)

<figcaption>

Three compatible lenses on topological quantum field theory. The path-integral lens emphasizes metric-independent actions and observables. The functorial lens emphasizes gluing. The infrared lens emphasizes protected topological data of gapped phases.

</figcaption>
</figure>

A TQFT is not empty physics. It can have finite-dimensional Hilbert spaces, nontrivial partition functions, line and surface operators, anyons, mapping-class-group actions, knot invariants, boundary theories, and anomaly-inflow data.

## Prerequisites

You should be comfortable with manifolds, orientations, boundaries, differential forms, gauge fields, Wilson lines, and basic path-integral language. The chapters on topological terms, defects and extended operators, higher-form symmetry, and Symmetry TFT and Anomaly Inflow are the natural preparation.

A first reading does not require higher categories. The page uses the ordinary Atiyah–Segal functorial picture only at the level of closed spatial manifolds, bordisms, and gluing.

## Core idea

Ordinary QFT usually asks for local metric-dependent information. A scalar field theory cares about distances, Laplacians, propagators, and particle momenta. A TQFT cares about global topological information: how manifolds are glued, how defects link, which bundles exist, which anyons fuse, and how boundary conditions are chosen.

The central contrast is

$$
\text{ordinary QFT: local geometry matters},
\qquad
\text{TQFT: protected topology matters}.
$$

In an ordinary massive QFT, long-distance correlators often decay exponentially and local excitations disappear from the infrared. What may remain is a protected topological sector: ground-state degeneracy on nontrivial spatial manifolds, topological line operators, braiding phases, or response terms. That protected sector is often described by a TQFT.

In a fundamental or standalone TQFT, topological invariance is not merely an infrared approximation. It is part of the definition.

## Setup and conventions

A $d$-dimensional TQFT is usually placed on a $d$-manifold $M_d$. If a Hamiltonian interpretation exists, a spatial slice is a closed $(d-1)$-manifold $\Sigma_{d-1}$.

The functorial notation is

$$
Z(\Sigma_{d-1})=\mathcal H_\Sigma,
$$

for the state space assigned to a spatial manifold, and

$$
Z(M_d):\mathcal H_{\Sigma_{\mathrm{in}}}\to\mathcal H_{\Sigma_{\mathrm{out}}},
$$

for a bordism

$$
M_d:\Sigma_{\mathrm{in}}\to\Sigma_{\mathrm{out}}.
$$

If $M_d$ is closed, then

$$
Z(M_d)\in\mathbb C
$$

is the partition function or manifold invariant.

Orientation reversal is typically represented by dualization,

$$
Z(\overline\Sigma)\simeq Z(\Sigma)^*,
$$

though spin, Pin, framing, and other tangential structures require refinements.

:::note[Source note]
The functorial formulation is often called the Atiyah–Segal viewpoint. It packages the path-integral gluing law into a mathematical structure: spatial manifolds become vector spaces, spacetime bordisms become linear maps, and cutting/gluing becomes composition.
:::

## Three meanings of TQFT

### Metric-independent path integrals

The most physics-facing definition starts with a path integral

$$
Z(M)=\int \mathcal D\Phi\,e^{iS[\Phi]}.
$$

If the action and relevant observables do not use a metric, the result is expected to depend only on topological data of $M$ and of the inserted defects. Chern–Simons theory is the canonical example in three dimensions:

$$
S_{\mathrm{CS}}
=\frac{k}{4\pi}\int_M
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right),
$$

using Hermitian gauge fields in this volume’s convention. BF theory is another canonical example:

$$
S_{\mathrm{BF}}=\frac{k}{2\pi}\int_M B\wedge dA
$$

in the abelian schematic normalization. In both cases, the metric is not needed to write the classical action.

### Functorial field theories

The functorial definition emphasizes cutting and gluing rather than fields. It says that a TQFT is a rule $Z$ assigning algebraic data to manifolds in a way compatible with disjoint union and gluing.

The gluing law is the essential physical statement. If

$$
M=M_2\circ M_1
$$

is obtained by gluing two bordisms along a common spatial boundary $\Sigma$, then

$$
Z(M)=Z(M_2)\circ Z(M_1).
$$

If a closed manifold is cut along $\Sigma$, the path integral becomes a pairing of states in $Z(\Sigma)$ and $Z(\overline\Sigma)$. This is the topological version of canonical quantization.

### Infrared topological phases

A gapped many-body system can have no local gapless excitations and still have nontrivial topological order. The protected low-energy data can include a finite-dimensional ground-state space depending on spatial topology, anyon types, braiding phases, and topological response actions. A TQFT can describe this protected sector.

This does not mean the microscopic Hamiltonian is itself topological. It means its long-distance protected data are captured by a topological effective theory.

:::caution[Do not collapse these meanings]
A metric-independent action, a functorial assignment, and an infrared topological phase are deeply related but not identical definitions. A careful page should always say which meaning is being used.
:::

## Basic examples

### Finite gauge theory

A finite gauge theory sums over flat $G$-bundles on $M$. In its simplest untwisted form, the partition function is schematically

$$
Z(M)\sim \frac{\#\{\text{flat }G\text{-bundles on }M\}}{\#\{\text{gauge transformations}\}}.
$$

Dijkgraaf–Witten theory adds a topological action classified by group cohomology data. It is a finite, exactly topological theory and is also a basic model for finite-symmetry SymTFT.

### BF theory

BF theory imposes flatness constraints and produces linking phases between operators. In $d$ dimensions, the schematic abelian action

$$
S=\frac{N}{2\pi}\int B_{d-p-1}\wedge dA_p
$$

couples a $p$-form gauge field to a dual field. Its observables often include Wilson-type operators

$$
\exp\left(i\int_{\gamma_p} A_p\right),
\qquad
\exp\left(i\int_{\Gamma_{d-p-1}} B_{d-p-1}\right),
$$

with correlation functions controlled by linking.

### Chern–Simons theory

Chern–Simons theory is a three-dimensional TQFT with line operators labeled by representations, subject to level and quantum-group constraints. Wilson-loop expectation values compute knot and link invariants. The theory is topological but depends on framing in a subtle quantum way.

### Cohomological TQFT

A cohomological TQFT has a nilpotent scalar charge $Q$ and physical observables in $Q$-cohomology. Metric dependence is often $Q$-exact:

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\}.
$$

Then correlation functions of $Q$-closed observables are metric-independent, assuming no boundary or anomaly obstruction. Donaldson–Witten theory is the standard four-dimensional example.

## What TQFTs compute

A TQFT can compute several kinds of topological data:

| Object | TQFT output |
|---|---|
| Closed manifold $M_d$ | Number $Z(M_d)$ |
| Spatial manifold $\Sigma_{d-1}$ | State space $Z(\Sigma_{d-1})$ |
| Bordism $M:\Sigma_{\mathrm{in}}\to\Sigma_{\mathrm{out}}$ | Linear map |
| Link in a three-manifold | Link invariant |
| Defect network | Number, vector, or morphism depending on boundary |
| Mapping class of $\Sigma$ | Linear operator on $Z(\Sigma)$ |
| Boundary condition | Module-like object or boundary theory |
| Gluing operation | Pairing, trace, or composition |

This is why TQFTs are unusually precise. They do not merely predict a scaling exponent or a scattering amplitude. They often assign algebraic invariants to topological objects.

## State spaces and gluing

Suppose a closed $d$-manifold $M$ is cut into two pieces along a closed spatial manifold $\Sigma$:

$$
M=M_L\cup_\Sigma M_R.
$$

The path integral on $M_L$ prepares a state

$$
|M_L\rangle\in Z(\Sigma),
$$

and the path integral on $M_R$ prepares a dual state

$$
\langle M_R|\in Z(\Sigma)^*.
$$

The partition function is their pairing:

$$
Z(M)=\langle M_R|M_L\rangle.
$$

This is the topological ancestor of many constructions used elsewhere: conformal blocks, anomaly lines, relative QFT, SymTFT slabs, and state-sum models.

## Extended operators and defects

TQFTs are naturally rich in extended operators. A local operator in a fully extended TQFT may be less important than line operators, surface operators, boundary conditions, and junctions.

For example, in Chern–Simons theory, Wilson lines are not probes added at the end. They are central observables:

$$
W_R(K)=\operatorname{tr}_R\,P\exp\left(i\oint_K A\right).
$$

Their correlation functions depend on topology of links and framing data. In BF theory, Wilson operators and dual surface operators can have pure linking phases. In finite gauge theory, twist defects and holonomy insertions encode flat-bundle data.

This is why TQFT is so close to generalized symmetry. A topological defect is already the kind of object that can implement a symmetry, measure a charge, or encode an anomaly.

## What a TQFT is not

A TQFT is not the same thing as a topological term. Four-dimensional Yang–Mills theory with a theta term has local propagating gluons; it is not a TQFT merely because one term in the action is topological.

A TQFT is not necessarily trivial. It may have no local propagating particles, but it can have a complicated Hilbert space, anyon spectrum, braiding, modular data, mapping-class-group action, and boundary theory.

A TQFT is not automatically independent of all extra structures. Many important TQFTs depend on orientation, spin structure, Pin structure, framing, background bundles, or boundary conditions.

A TQFT is not always fully captured by a simple finite-dimensional vector space assigned to a closed spatial manifold. Extended TQFT asks for data on lower-dimensional manifolds too, and modern applications often need defects and boundaries from the start.

## Common pitfalls

**“No metric” does not mean “no choices.”** Orientation, framing, spin structure, and background bundles can be essential.

**“No local degrees of freedom” does not mean “no observables.”** Wilson lines, anyons, defects, and boundary states can carry rich data.

**“Topological in the infrared” does not mean “topological microscopically.”** A lattice Hamiltonian may flow to a TQFT only after gapped nonuniversal modes are ignored.

**“Functorial TQFT is optional abstraction.”** The functorial view is the clean language of gluing. It is what makes precise the idea that cutting a path integral prepares a state.

**“All TQFTs are bosonic and oriented.”** Fermionic and unoriented theories require spin, Pin, or other tangential structures. Ignoring those structures changes the theory.

## Relations to other pages

[Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/) explains the stress-tensor and deformation criteria for topological behavior.

[Cohomological TQFT](/symmetry-anomalies-topology/topological-qft/cohomological-tqft/) explains the $Q$-cohomological mechanism behind Witten-type theories.

[Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/), [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/), and [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) develop the standard examples.

[Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) explains how a TQFT can package symmetry, gauging, boundary conditions, and anomaly data.

## Research status

The basic definition of TQFT through metric-independent path integrals and functorial gluing is established. Chern–Simons, BF, finite gauge, and cohomological TQFTs are standard examples.

Active research includes extended TQFT, non-semisimple and logarithmic TQFT, fermionic and unoriented refinements, defect-complete TQFT, higher-categorical formulations, SymTFT applications to generalized and non-invertible symmetry, and the interface between TQFT and topological phases of matter.

## Exercises

### Exercise 1: Gluing as composition

Let $M_1:\Sigma_0\to\Sigma_1$ and $M_2:\Sigma_1\to\Sigma_2$ be bordisms. What should a functorial TQFT assign to the glued bordism $M_2\circ M_1$?

<details><summary><strong>Solution</strong></summary>

It should assign the composition of the corresponding linear maps:

$$
Z(M_2\circ M_1)=Z(M_2)\circ Z(M_1).
$$

This is the algebraic form of the path-integral gluing law.

</details>

### Exercise 2: Why a theta term is not enough

Explain why adding

$$
S_\theta=\frac{\theta}{32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu}
$$

to four-dimensional Yang–Mills theory does not make the full theory a TQFT.

<details><summary><strong>Solution</strong></summary>

The theta term is topological, but Yang–Mills theory also contains the metric-dependent kinetic term

$$
-\frac{1}{4g^2}\int d^4x\,F^a_{\mu\nu}F^{a\mu\nu}.
$$

That term gives local propagating gauge-field degrees of freedom. A TQFT is topological as a whole protected theory, not merely a QFT containing one topological term.

</details>

### Exercise 3: State from a path integral

Let $M$ be a compact $d$-manifold with boundary $\partial M=\Sigma$. What does the TQFT path integral on $M$ define?

<details><summary><strong>Solution</strong></summary>

It defines a vector in the state space associated to the boundary:

$$
Z(M)\in Z(\Sigma).
$$

If the boundary orientation is reversed, this may instead be regarded as a dual vector. Gluing two such manifolds along $\Sigma$ pairs the corresponding vectors.

</details>

### Exercise 4: TQFT and observables

Why can a TQFT with no local propagating degrees of freedom still have nontrivial line operators?

<details><summary><strong>Solution</strong></summary>

“No local propagating degrees of freedom” means there are no particle-like local excitations governed by metric-dependent wave propagation. Line operators can still carry global topological data, such as holonomy, representation labels, linking, braiding, and fusion. Chern–Simons theory is the standard example: Wilson-loop correlators are nontrivial knot and link invariants.

</details>

## References

- Michael Atiyah, “Topological Quantum Field Theories.”
- Graeme Segal, axiomatic conformal and topological field theory viewpoint.
- Albert Schwarz, early work on topological quantum field theories and metric-independent actions.
- Edward Witten, “Topological Quantum Field Theory.”
- Edward Witten, “Quantum Field Theory and the Jones Polynomial.”
- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology.”
- Daniel S. Freed, “Remarks on Chern–Simons Theory.”
- A. M. Polyakov, *Gauge Fields and Strings*, especially topology of gauge fields and loop dynamics.
- Mikio Nakahara, *Geometry, Topology and Physics*, for manifolds, forms, bundles, monopoles, instantons, and characteristic classes.
- Theodore Frankel, *The Geometry of Physics*, for geometric physics with differential forms, bundles, gauge fields, and Chern forms.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially topological field theory, theta terms, Wess–Zumino terms, Chern–Simons terms, and topological gauge theory.

## Version history

- 2026-06-22: Initial polished draft. Defined TQFT through path-integral, functorial, and infrared lenses; added examples, gluing, pitfalls, and exercises.
