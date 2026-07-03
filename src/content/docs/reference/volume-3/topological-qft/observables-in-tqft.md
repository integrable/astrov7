---
title: "Observables in TQFT"
description: "Explains what observables are in topological quantum field theory: partition functions, state spaces, Wilson lines, surface operators, defects, categories, and topological correlation functions."
sidebar:
  label: "Observables in TQFT"
  order: 9
level: Advanced
status: "Polished draft"
source: "Atiyah–Segal TQFT; Witten on Chern–Simons theory; Dijkgraaf–Witten theory; BF theory; standard defect and extended-TQFT references."
topics:
  - TQFT
  - observables
  - Wilson lines
  - defects
  - state spaces
  - correlation functions
  - topological invariants
canonicalTopics:
  - tqft-observable
  - topological-observable
  - extended-operator
  - defect-correlation-function
researchStatus:
  established:
    - "Partition functions, state spaces, line and surface operators, and defect networks are standard observables in topological field theories."
    - "In a TQFT, correlation functions depend on topology, linking, framing, labels, and boundary data rather than on local metric distances."
  active:
    - "In extended, non-semisimple, higher-categorical, and symmetry-TFT settings, the word observable can include categories, module categories, boundary conditions, and defect networks rather than only numbers."
---

## Summary

An observable in an ordinary local QFT is often introduced as a local operator $\mathcal O(x)$ or a correlation function

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle .
$$

In a topological quantum field theory, this is too narrow. A TQFT has observables supported on points, lines, surfaces, boundaries, interfaces, and general defect networks. It also assigns state spaces to spatial manifolds and numbers to closed spacetimes. The central feature is not the dimension of the support, but **topological invariance**: after the observable is inserted, smooth deformations that preserve topology should not change the answer, except for controlled data such as linking, framing, orientation, spin structure, or boundary condition.

The basic list is:

| Observable-like object | Output |
|---|---|
| closed spacetime $M_d$ | partition function $Z(M_d)\in\mathbb C$ |
| closed spatial manifold $\Sigma_{d-1}$ | state space $\mathcal H_\Sigma$ |
| bordism $M:\Sigma_0\to\Sigma_1$ | linear map $Z(M):\mathcal H_{\Sigma_0}\to\mathcal H_{\Sigma_1}$ |
| line, surface, or defect network | number, state, map, or category depending on codimension |
| boundary condition | allowed endpoint/topological sector data |
| local operator in a TQFT | often an element of an algebra or cohomology ring |

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic showing TQFT observables: partition functions on closed manifolds, state spaces on spatial cuts, defect networks, and local or extended insertions.](/figures/symmetry-anomalies-topology/tqft-observables-map.svg)

<figcaption>

TQFT observables are not only local insertions. The theory assigns numbers to closed manifolds, state spaces to cuts, maps to bordisms, and additional data to defect networks. In an extended TQFT, lower-codimension observables can be algebraic or categorical objects rather than just complex numbers.

</figcaption>
</figure>

The goal of this page is to make the word “observable” precise enough for Chern–Simons theory, BF theory, Dijkgraaf–Witten theory, cohomological TQFT, extended TQFT, and SymTFT.

## Prerequisites

You should know [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/), [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/), [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/), [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/), [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/), and [Extended TQFT: Preview](/symmetry-anomalies-topology/topological-qft/extended-tqft-preview/).

You should also be comfortable with the idea that cutting a path integral along a spatial hypersurface creates a state, and gluing path integrals pairs or composes states.

## Core idea

In a metric-dependent QFT, the most familiar observable is a local field insertion. Its correlation functions depend on distances, angles, cross ratios, scales, and sometimes time ordering:

$$
\langle \mathcal O(x)\mathcal O(y)\rangle
=
F((x-y)^2,\mu,\text{couplings}).
$$

In a TQFT, metric dependence is absent or $Q$-exact. As a result, the important questions change:

$$
\text{Where is the operator?}
\quad\leadsto\quad
\text{How is it embedded, linked, labeled, framed, and glued?}
$$

For example, in three-dimensional Chern–Simons theory, a Wilson loop observable is labeled by a representation $R$ and an embedded knot $K$:

$$
W_R(K)=\operatorname{Tr}_R\,P\exp\left(i\oint_K A\right).
$$

Its expectation value is not a function of the geometric length of $K$. It is a topological invariant of the framed knot or link, with dependence on the gauge group, level, orientation, and representations.

In four-dimensional BF theory, a line operator and a surface operator can have a topological linking phase. The observable is not the distance between line and surface; it is their linking pairing.

## Setup and conventions

We write a $d$-dimensional TQFT as a functor-like assignment

$$
Z:\operatorname{Bord}_d^{\mathcal S}\longrightarrow \operatorname{Vect}
$$

in the ordinary Atiyah–Segal setting. The structure $\mathcal S$ can include orientation, spin, framing, or background symmetry data.

A closed $d$-manifold gives a number,

$$
Z(M_d)\in\mathbb C.
$$

A closed $(d-1)$-manifold gives a state space,

$$
Z(\Sigma_{d-1})=\mathcal H_\Sigma.
$$

A bordism gives a map,

$$
Z(M:\Sigma_0\to\Sigma_1):\mathcal H_{\Sigma_0}\to\mathcal H_{\Sigma_1}.
$$

An insertion of a defect network $\mathcal N$ in $M$ modifies the assignment:

$$
Z(M;\mathcal N).
$$

Depending on whether $M$ is closed, has boundary, or is regarded as a bordism, this object can be a number, vector, covector, or linear map. In an extended theory, it may also be a functor, category, bimodule, or higher morphism.

:::note[Source note: observable versus operator]
Physics papers often call any inserted defect an “operator,” even when it is not local and even when the output is not an operator on a Hilbert space. This page uses “observable” broadly for anything one can insert, label, or measure inside the TQFT path integral.
:::

## Partition functions as observables

The closed-manifold partition function is the most basic TQFT observable:

$$
M_d\longmapsto Z(M_d).
$$

In an ordinary QFT, the partition function on a compact manifold depends on metric data such as volume, curvature radii, temperature, and shape. In a TQFT, it should depend only on topological and discrete structure:

$$
Z(M_d,g_{\mu\nu})=Z(M_d)
$$

up to framing, spin, orientation, anomaly, and regulator choices stated by the theory.

Examples:

| Theory | Closed-manifold observable |
|---|---|
| Chern–Simons theory | 3-manifold invariant, often with framing dependence |
| Dijkgraaf–Witten theory | weighted count of flat $G$-bundles |
| BF theory | finite topological gauge-theory invariant after compact quantization |
| cohomological TQFT | intersection or enumerative invariant after localization |
| invertible TQFT | pure phase depending on topology and background fields |

The partition function is an observable because it is a measurable topological amplitude of the theory. In an invertible TQFT, it may be essentially the whole theory on closed manifolds. In a non-invertible TQFT, closed partition functions are far from enough; one also needs state spaces and defect data.

## State spaces and cutting

A TQFT assigns a state space to a spatial manifold:

$$
\Sigma\mapsto \mathcal H_\Sigma.
$$

This is an observable-like assignment because $\dim\mathcal H_\Sigma$, its grading, its basis, its mapping-class-group action, and its operator algebra are all topological data.

For example, in Chern–Simons theory on a Riemann surface $\Sigma$, $\mathcal H_\Sigma$ is the space of conformal blocks of the associated boundary WZW model. Mapping class group transformations of $\Sigma$ act on this space. In finite gauge theory, $\mathcal H_\Sigma$ can be understood in terms of functions on flat bundles over $\Sigma$, with gauge equivalence carefully included.

Cutting turns partition functions into states. If a closed manifold $M$ is cut along $\Sigma$, then the path integral on one side gives a vector

$$
|\Psi_{M_1}\rangle\in \mathcal H_\Sigma,
$$

and the other side gives a covector

$$
\langle \Psi_{M_2}|\in \mathcal H_\Sigma^*.
$$

Gluing pairs them:

$$
Z(M)=\langle \Psi_{M_2}|\Psi_{M_1}\rangle.
$$

This is the operational meaning of the state space. It is the place where topological amplitudes live before gluing.

## Line and surface observables

Extended observables are supported on submanifolds. If $L$ is a line and $\Sigma$ is a surface, one may write schematically

$$
Z(M;L,\Sigma).
$$

The labels on these observables matter. Wilson lines are labeled by representations. Surface operators may be labeled by conjugacy classes, holonomies, fluxes, two-form charges, or boundary conditions depending on the theory. Defects in finite gauge theory can be labeled by group-theoretic or categorical data.

A common pattern is:

| Observable | Support | Typical label |
|---|---:|---|
| Wilson line | line | representation or electric charge |
| ’t Hooft line | line | magnetic charge or singularity class |
| Wilson–’t Hooft line | line | electric–magnetic pair |
| BF surface | surface | higher-form charge |
| twist defect | codimension one or two | symmetry element or monodromy |
| boundary condition | boundary | module/category/condensate data |

Metric independence says the expectation value is invariant under smooth deformations that avoid crossings and singular events. When an extended observable crosses another observable, the value can change by a braiding, linking phase, fusion rule, or action on a charged operator.

This is why observables in TQFT are inseparable from defects and their algebra.

## Defect networks

A defect network is a configuration of labeled strata: lines ending on junctions, surfaces meeting along lines, boundaries carrying boundary-local operators, and so on.

In a two-dimensional TQFT, a network of topological lines may evaluate to an algebraic expression involving multiplication, comultiplication, traces, or Frobenius algebra data. In three-dimensional TQFT, a framed link colored by simple objects of a modular tensor category gives a link invariant. In SymTFT, networks of bulk defects encode symmetry actions, gauging operations, and anomaly data.

The local rules of a defect network include:

$$
\text{fusion},\qquad
\text{braiding},\qquad
\text{junction spaces},\qquad
\text{duals},\qquad
\text{associators}.
$$

For group-like topological symmetry defects,

$$
U_g U_h=U_{gh}.
$$

For non-invertible defects,

$$
\mathcal N_a\mathcal N_b\simeq \bigoplus_c N_{ab}{}^c\mathcal N_c.
$$

Thus a defect network is an observable whose value is computed by topological moves and local algebraic data. The observable is not merely the set of defects; it is the network plus its embedding, labels, junctions, and allowed moves.

## Local operators in a TQFT

Local operators do exist in TQFT, but their role differs from generic local QFT.

In a cohomological TQFT, physical local operators often live in $Q$-cohomology:

$$
Q\mathcal O=0,\qquad
\mathcal O\sim \mathcal O+Q\Lambda.
$$

Correlation functions of $Q$-closed observables are independent of insertion positions, provided no contact singularities are crossed. Products of local operators define a finite-dimensional algebra in many examples.

In a two-dimensional oriented TQFT, local operators are described by a commutative Frobenius algebra $A$. The product is the pair-of-pants amplitude,

$$
m:A\otimes A\to A,
$$

and the trace pairing comes from the sphere with two marked points. This is the simplest example where local TQFT observables are algebraic rather than analytic functions of position.

In Chern–Simons theory, gauge-invariant local operators are often sparse or topologically trivial compared with line operators. The lines are the interesting observables. This is not a defect of the theory; it is the point.

## Correlation functions

A TQFT correlation function is written

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_M
=
Z(M;\mathcal O_1,\ldots,\mathcal O_n).
$$

For local operators in a cohomological theory, this may be independent of insertion positions. For extended observables, the answer depends on topology of embeddings.

Examples:

| Observable configuration | Topological dependence |
|---|---|
| local operators in 2d TQFT | algebra product and trace |
| Wilson link in Chern–Simons | knot/link type, coloring, framing |
| line and surface in BF theory | linking number or intersection pairing |
| twist defects in finite gauge theory | branch data and flat-bundle counting |
| defect networks | fusion, braiding, and junction data |

A useful rule of thumb:

$$
\text{ordinary QFT correlators depend on geometry;}
\qquad
\text{TQFT correlators depend on topology and labels.}
$$

The word “topology” here is not license to ignore all choices. Framing, spin structure, orientation, boundary condition, and background fields are often essential labels.

## Framing and regularization

Some topological observables require framing. In Chern–Simons theory, Wilson-loop expectation values depend on a choice of framing because the quantum regularization of self-linking is not canonical. A framing is roughly a choice of normal vector field along a knot, or equivalently a nearby push-off used to define self-linking.

Thus the observable is not simply

$$
(K,R),
$$

but

$$
(K,R,\text{framing}).
$$

This is a recurring lesson: topological observables often need extra structure. A spin TQFT needs a spin structure. An oriented TQFT needs an orientation. A framed TQFT needs a framing. A theory with background symmetry fields needs those backgrounds as part of the input.

:::caution[Topological does not mean structure-free]
A TQFT observable can be independent of the metric while still depending on orientation, spin structure, framing, flat bundle, background field, or boundary condition.
:::

## Boundary observables

With boundaries, observables become richer. A boundary condition $\mathcal B$ can support boundary-local operators,

$$
\mathcal O_{\partial}(x)\in \operatorname{End}(\mathcal B),
$$

and line operators may end on boundary operators if the boundary condition allows it.

In extended TQFT language, boundary conditions are themselves objects or modules. Interfaces are bimodules or functors. Junctions are morphisms. A correlation function with boundaries therefore depends on both bulk labels and boundary labels.

The simplest physical example is a Wilson line ending on a boundary that carries a charged degree of freedom. In an ordinary closed system the line might be non-endable, but the boundary supplies an endpoint. This is the same logic used in SymTFT: topological boundary conditions determine which bulk defects may end and therefore which symmetry operators or charged objects survive on the physical boundary.

## What counts as a complete observable set?

A few partition functions rarely determine a TQFT. To specify a theory, one often needs a hierarchy:

$$
\text{closed partition functions}
\quad+\quad
\text{state spaces}
\quad+\quad
\text{defect labels}
\quad+\quad
\text{fusion and gluing rules}
\quad+\quad
\text{boundary data}.
$$

For a semisimple three-dimensional TQFT, modular data such as $S$ and $T$ matrices gives powerful information, but may still not determine all extended data in every setting. For non-semisimple theories, logarithmic theories, and non-invertible symmetry systems, even more care is needed.

A healthy attitude is:

> A TQFT is known when you know how to evaluate its labeled manifolds and defect networks under cutting and gluing.

Closed-manifold numbers are important, but they are only the beginning.

## Common pitfalls

**“Topological observable means local observable.”** No. In many TQFTs, line and surface observables are more important than local ones.

**“Metric-independent means independent of all choices.”** No. Framing, spin structure, orientation, background bundles, and boundary conditions may remain essential.

**“The partition function determines the theory.”** Not generally. State spaces, maps, operators, and defects can distinguish theories with similar closed partition functions.

**“A defect network is just a picture.”** The picture encodes an observable: labels, junctions, fusion, braiding, and embedding data.

**“Wilson loops are always topological.”** In Chern–Simons theory they are topological after framing choices. In ordinary Yang–Mills theory, Wilson loops usually depend on geometry and dynamics.

## Relations to other pages

[Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/) supplies the canonical line-observable example. [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/) supplies line-surface linking examples. [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) supplies finite-gauge-theory observables. [Extended TQFT: Preview](/symmetry-anomalies-topology/topological-qft/extended-tqft-preview/) explains why lower-dimensional observables naturally become algebraic or categorical.

The Defects and Extended Operators chapter develops the same ideas from the QFT side. Symmetry TFT uses bulk topological observables to encode symmetry operators, charged objects, gauging choices, and anomalies.

## Research status

The basic observables of semisimple TQFTs, Chern–Simons theory, BF theory, Dijkgraaf–Witten theory, and cohomological TQFTs are well established. The active frontier concerns extended, non-semisimple, derived, categorical, and symmetry-enriched versions where observables may be categories or higher categories, and where defect networks encode non-invertible symmetry.

## Exercises

### Exercise 1: Gluing as an inner product

Suppose a closed manifold $M$ is obtained by gluing two pieces $M_1$ and $M_2$ along a common boundary $\Sigma$. Explain why a TQFT assigns a vector to $M_1$, a covector to $M_2$, and a number to $M$.

<details><summary><strong>Solution</strong></summary>

The piece $M_1$ can be regarded as a bordism from the empty set to $\Sigma$, so it assigns a vector

$$
|\Psi_{M_1}\rangle\in\mathcal H_\Sigma.
$$

The piece $M_2$ is a bordism from $\Sigma$ to the empty set, so it assigns a covector

$$
\langle\Psi_{M_2}|\in\mathcal H_\Sigma^*.
$$

Gluing corresponds to composition, hence

$$
Z(M)=\langle\Psi_{M_2}|\Psi_{M_1}\rangle.
$$

</details>

### Exercise 2: Charge conservation as a TQFT observable

In a two-dimensional finite-group TQFT, suppose topological line defects are labeled by group elements and local operators are charged under them. Explain how moving a closed defect line around local insertions gives a selection rule.

<details><summary><strong>Solution</strong></summary>

Because the line is topological, a closed loop can be deformed freely unless it crosses charged insertions. If a large loop surrounding all insertions can be shrunk to nothing, then the product of the phases or representation actions acquired while crossing the insertions must be trivial. Otherwise the correlator must vanish. This is the finite-defect version of a Ward identity.

</details>

### Exercise 3: Framing dependence

Why is a framed Wilson loop in Chern–Simons theory a better-defined observable than an unframed Wilson loop?

<details><summary><strong>Solution</strong></summary>

Quantum Wilson-loop expectation values require regularizing coincident points on the loop. The regularization naturally uses a nearby push-off of the loop, and the self-linking of the loop with its push-off depends on a framing. Therefore the topological observable is not just a knot and representation, but a framed knot and representation.

</details>

## References

- M. Atiyah, “Topological Quantum Field Theories.”
- G. Segal, “The Definition of Conformal Field Theory.”
- E. Witten, “Quantum Field Theory and the Jones Polynomial.”
- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology.”
- M. Blau and G. Thompson, “Topological Gauge Theories of Antisymmetric Tensor Fields.”
- M. Nakahara, *Geometry, Topology and Physics*, for topology, bundles, characteristic classes, and gauge-theory examples.
- T. Frankel, *The Geometry of Physics*, for differential forms, integration, bundles, and gauge geometry.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for topological field theory and topological matter examples.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for extended operators and topological symmetry operators.

## Version history

- **2026-06-23:** Initial polished draft. Added partition-function, state-space, line/surface, defect-network, local-operator, framing, boundary, and extended-observable viewpoints.
