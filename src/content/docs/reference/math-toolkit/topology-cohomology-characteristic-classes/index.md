---
title: "Topology, Cohomology, and Characteristic Classes"
description: "Chapter overview for homotopy, homology, cohomology, winding numbers, characteristic classes, index theory, and cobordism in the Mathematical Toolkit volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Standard topology and geometry references for physicists, including Nakahara, Frankel, Bott–Tu, Hatcher, Milnor–Stasheff, Eguchi–Gilkey–Hanson, and QFT treatments of instantons, anomalies, and topological terms."
topics:
  - topology
  - homotopy groups
  - homology
  - cohomology
  - de Rham cohomology
  - characteristic classes
  - index theory
  - cobordism
canonicalTopics:
  - topology
  - homotopy-groups
  - homology
  - cohomology
  - de-rham-cohomology
  - characteristic-classes
  - index-theorem
  - cobordism
researchStatus:
  established:
    - "Homotopy, homology, cohomology, characteristic classes, and index theory are standard tools for describing topological sectors, defects, gauge bundles, theta terms, zero modes, and anomalies in QFT."
  active:
    - "Modern QFT uses refined versions of these tools, including differential cohomology, generalized cohomology, equivariant and stacky refinements, higher bundles, and cobordism classifications of anomalies and phases."
---

Topology, Cohomology, and Characteristic Classes is the chapter in the Mathematical Toolkit volume where local geometry is connected to global information. A local coordinate patch can tell you the value of a field, a connection, or a curvature form near one point. Topology asks which global features survive all smooth deformations and therefore cannot be removed by changing coordinates, choosing a different gauge, or improving a local formula.

This chapter exists because many of the most important QFT effects are global in exactly this sense. Vortices are classified by winding, monopoles by maps from surrounding spheres, instantons by bundle topology, theta terms by characteristic numbers, fermion zero modes by index theorems, and many anomaly questions by whether certain topological data can be consistently extended. These are not optional decorations on QFT; they are how the theory remembers global sectors.

The slogan is

$$
\text{local fields live on geometry; global sectors live in topology}.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Roadmap diagram linking homotopy, homology, cohomology, characteristic classes, index theory, anomalies, topological terms, and cobordism.](/figures/math-toolkit/topology-characteristic-classes-roadmap.svg)

<figcaption>

The topology pipeline used throughout QFT. Homotopy classifies maps and defects, homology and cohomology organize cycles and charges, characteristic classes measure bundle topology, and index theorems connect topology to zero modes and anomalies. Cobordism and generalized cohomology refine this story in modern applications.

</figcaption>
</figure>

Read this chapter when a QFT page says winding number, instanton number, monopole charge, theta term, Chern class, Pontryagin class, Stiefel–Whitney class, index, anomaly inflow, spin bordism, topological sector, or “large” gauge transformation, and you want the mathematical object behind the phrase.

## Prerequisites

You should be comfortable with the geometric language developed in [Geometry of Fields](/math-toolkit/geometry-of-fields/), especially [Manifolds](/math-toolkit/geometry-of-fields/manifolds/), [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/), [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), and [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/).

For gauge-theory examples, it helps to know [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/), [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/), and [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/). For spin and fermion examples, read [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/), [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/), and [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/).

The chapter assumes basic comfort with quotient spaces, continuous maps, and smooth manifolds, but it does not assume a prior topology course. The point is to build the exact amount of topology needed for field theory without turning the chapter into a pure-math marathon. Tempting, but no.

## Reading path

Read these pages in order on a first pass. Page names that are not yet published are listed as the intended route through the chapter rather than as links.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) | Continuous maps from spheres, winding, fundamental groups, higher homotopy groups, and the defect dictionary. |
| 2 | Homology and Cohomology | Cycles, boundaries, cocycles, cochains, conserved charges, and the first algebraic replacement for pictures of holes. |
| 3 | Winding Numbers | Integer topological charges for maps into circles, spheres, and groups, with QFT examples. |
| 4 | Degree of a Map | The signed count behind many topological charges, including sigma-model and instanton formulas. |
| 5 | de Rham Cohomology | Closed forms modulo exact forms, periods, Stokes’ theorem, and differential-form representatives of cohomology classes. |
| 6 | Čech Cohomology Preview | How local patching data becomes global topology, especially for bundles and gauge fields. |
| 7 | Characteristic Classes | Cohomology classes naturally attached to bundles, including the bridge from curvature to topology. |
| 8 | Chern Classes | Complex vector bundles, Chern characters, gauge fields, instanton number, and anomaly polynomials. |
| 9 | Stiefel–Whitney Classes | Obstructions for real bundles, orientation, spin structures, and fermionic global data. |
| 10 | Pontryagin Classes | Real-bundle characteristic classes, gravitational topological terms, and index-theorem input. |
| 11 | Index Theorems | The equality between analytic data of differential operators and topological characteristic numbers. |
| 12 | Cobordism Preview | The modern language for anomaly classifications, invertible phases, and global consistency conditions. |

A reader whose immediate goal is defects and solitons should start with Homotopy Groups, Winding Numbers, and Degree of a Map. A reader focused on anomalies should read de Rham Cohomology, Characteristic Classes, Chern Classes, Pontryagin Classes, and Index Theorems. A reader focused on fermions on general manifolds should read Stiefel–Whitney Classes before Cobordism Preview.

## Landmarks

The first landmark is **homotopy**. Homotopy remembers when two maps can be continuously deformed into each other. In QFT, this becomes a classification principle whenever finite-energy boundary conditions turn field configurations into maps from spheres, compactified spacetime, or surrounding surfaces into a target space. The simplest example is a map $S^1\to S^1$ with integer winding.

The second landmark is the **surrounding sphere** of a defect. A codimension-$c$ defect has a small linking sphere $S^{c-1}$ around it. If the order parameter takes values in a vacuum manifold $\mathcal V$, then a topological charge often lives in

$$
\pi_{c-1}(\mathcal V).
$$

This one line explains the familiar pattern: domain walls use $\pi_0$, vortices and strings use $\pi_1$, monopoles and hedgehogs use $\pi_2$, and some textures and instanton-like objects use higher homotopy groups.

The third landmark is **homology**. Homotopy classifies maps. Homology classifies cycles modulo boundaries. A loop that is not the boundary of a disk is a nontrivial one-cycle. A closed surface that is not the boundary of a three-chain is a nontrivial two-cycle. Homology gives the natural language for integration cycles, linking, fluxes, and conserved extended charges.

The fourth landmark is **cohomology**. Cohomology is dual to homology: it pairs with cycles to produce numbers. In differential-form language, a closed $p$-form $\omega$ defines periods

$$
\int_\Sigma \omega
$$

on $p$-cycles $\Sigma$. If $\omega=d\alpha$, then the integral over a closed cycle vanishes by Stokes’ theorem. That is why closed forms modulo exact forms are the natural objects.

The fifth landmark is the **bundle**. Gauge fields are not merely Lie-algebra-valued one-forms on one global patch. They are connections on principal bundles, and the topology of the bundle is measured by characteristic classes. A locally pure-gauge-looking field may still have nontrivial global content.

The sixth landmark is the **characteristic class**. A characteristic class is a cohomology class naturally assigned to a bundle. It turns local geometric data, such as curvature, into global topological information. Chern classes measure complex bundles, Stiefel–Whitney classes measure real mod-2 obstruction data, and Pontryagin classes measure real-bundle topology relevant to gravitational and gauge backgrounds.

The seventh landmark is the **Chern–Weil representative**. Given a connection with curvature $F$, invariant polynomials such as $\operatorname{tr}(F\wedge F)$ define closed forms whose cohomology class is independent of the connection. This is one of the cleanest bridges between physicists’ local curvature formulas and mathematicians’ global topology.

The eighth landmark is the **index theorem**. A Dirac operator has analytic data: zero modes, kernels, determinants, eta invariants, and spectral asymmetry. Topology enters through the index, schematically

$$
\operatorname{index}(D)=\int_M \text{characteristic classes}.
$$

That bridge is central to instanton zero modes, chiral anomalies, anomaly inflow, and supersymmetric localization.

The ninth landmark is **global structure**. A gauge algebra does not determine every global question. The difference between $SU(N)$ and $SU(N)/\mathbb Z_N$, or between $Spin(n)$ and $SO(n)$ bundles, can affect line operators, allowed bundles, theta angles, discrete fluxes, and global anomalies.

The tenth landmark is **cobordism and generalized cohomology**. Ordinary cohomology captures a great deal, but not everything. Modern anomaly and phase classifications often require spin, Pin, equivariant, or generalized cohomology data. This chapter only opens that door; later volumes use it more seriously.

## Common confusions

**Topology is not just “curved geometry.”** Curvature is local. Topology is global. A flat connection can have nontrivial holonomy; a locally trivial bundle can be globally nontrivial; a torus can have zero curvature and still have noncontractible cycles.

**A nonzero curvature form is not the same as a nontrivial bundle.** Curvature can be nonzero on a trivial bundle. Conversely, topological information is encoded in cohomology classes built from curvature and transition functions, not in the pointwise value of $F$ alone.

**A winding number needs boundary conditions.** You only get a map from a sphere when the field approaches a well-defined vacuum at infinity, or when the domain is compactified in a controlled way. Without such conditions, the proposed charge may not be defined.

**Homotopy and homology are not interchangeable.** Homotopy groups see based maps from spheres and can be hard to compute. Homology groups see cycles modulo boundaries and are often easier. The Hurewicz map relates them in favorable cases, but they are different invariants.

**Characteristic classes are cohomology classes, not specific differential forms.** A curvature expression such as $\operatorname{tr}(F\wedge F)$ is a representative. Changing the connection changes the representative by an exact form, while the cohomology class remains fixed.

**Local gauge transformations do not exhaust global gauge data.** Large gauge transformations, nontrivial bundles, discrete quotients of gauge groups, and transition functions can all affect the theory. Ignoring them is a classic way to get theta angles, line operators, or anomalies wrong.

**Index theorems are not optional mathematical frosting.** Whenever a statement counts chiral zero modes, instanton fermion zero modes, anomaly coefficients, determinant phases, or spectral flow, index-theoretic thinking is probably nearby.

**Cobordism is not just homology with a fancier hat.** Cobordism asks whether manifolds with additional structure bound higher-dimensional manifolds with compatible structure. The extra structure — orientation, spin, Pin, symmetry background — is often the physics.

## Boundaries

This chapter explains the topology needed as a reusable toolkit for QFT. It does not attempt to be a complete algebraic-topology course. Proofs are included when they sharpen physical intuition or prevent common mistakes; major classification theorems are stated with examples and references rather than rederived from scratch.

The chapter also does not replace the Geometry of Fields chapter. There, the main characters are manifolds, forms, bundles, connections, curvature, spin structures, and Dirac operators. Here, the emphasis shifts to global invariants: homotopy classes, cohomology classes, characteristic classes, indices, and cobordism classes.

It is also not the canonical home of generalized symmetries, anomalies, topological phases, or nonperturbative gauge dynamics as physics subjects. Those later volumes use the mathematics developed here. This chapter supplies the definitions and computations that keep those discussions from floating three inches above the ground.

Finally, this chapter mostly uses smooth finite-dimensional manifolds and ordinary bundles. Singular spaces, stacks, higher categories, derived geometry, differential cohomology, and infinite-dimensional spaces of fields are mentioned only when the QFT motivation would otherwise be misleading.

## Where to go next

From this chapter, the nearest mathematical continuation is the rest of Geometry of Fields, especially [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/), [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/), [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/), and [Variational Calculus on Manifolds](/math-toolkit/geometry-of-fields/variational-calculus-on-manifolds/).

For path-integral applications, connect this chapter to [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/), [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

For group-theoretic global structure, return to [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/), [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/), and [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/).

The first technical page in this chapter is [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/). After that, the natural next pages are Homology and Cohomology and Winding Numbers.

## References

- M. Nakahara, *Geometry, Topology and Physics*. A broad physics-oriented reference for homotopy, homology, cohomology, bundles, characteristic classes, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*. Excellent for differential forms, integration, bundles, characteristic classes, and geometric intuition.
- A. Hatcher, *Algebraic Topology*. Standard reference for homotopy, homology, cohomology, exact sequences, and characteristic classes.
- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*. A classic bridge between differential forms and topology.
- J. Milnor and J. Stasheff, *Characteristic Classes*. Standard reference for characteristic classes.
- M. Atiyah and I. Singer, papers on the index theorem. Foundational source for the analytic-topological bridge behind index theory.
- T. Eguchi, P. Gilkey, and A. Hanson, “Gravitation, gauge theories and differential geometry.” A classic physics review of geometry, topology, characteristic classes, and index theory.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for gauge fields, topology, instantons, strings, and nonperturbative examples.
- S. Coleman, *Aspects of Symmetry*. Useful for solitons, lumps, instantons, and topology in field theory.

## Version history

- **2026-06-25:** Initial polished draft. Established the topology chapter map, prerequisites, landmarks, common confusions, boundaries, references, and route into Homotopy Groups.
