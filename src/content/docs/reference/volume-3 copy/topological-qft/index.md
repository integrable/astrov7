---
title: "Topological Quantum Field Theory"
description: "Chapter overview for metric-independent quantum field theories, cohomological field theories, Chern–Simons theory, BF theory, Dijkgraaf–Witten theory, observables, and the relation between TQFT, phases, and ordinary QFT."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Atiyah; Schwarz; Witten; Dijkgraaf–Witten; Polyakov; Nakahara; Frankel; standard TQFT and topological gauge theory references."
topics:
  - topological quantum field theory
  - TQFT
  - metric independence
  - Chern-Simons theory
  - BF theory
  - Dijkgraaf–Witten theory
  - cohomological TQFT
  - observables
canonicalTopics:
  - topological-qft
  - metric-independence
  - functorial-tqft
  - cohomological-field-theory
  - topological-gauge-theory
researchStatus:
  established:
    - "TQFT is a standard framework for quantum field theories whose observables depend only on topology or protected geometric structures rather than on local metric dynamics."
    - "Chern–Simons theory, BF theory, Dijkgraaf–Witten theory, cohomological TQFTs, and functorial TQFT axioms are central examples."
  active:
    - "Extended TQFT, fully local boundary-defect data, higher categories, non-semisimple TQFT, and relations to phases of matter and generalized symmetry remain active research areas."
---

Topological Quantum Field Theory is the chapter where topological theories are studied as QFTs in their own right. In the previous chapter, topological theories appeared mainly as **SymTFTs**: one-higher-dimensional packages for symmetry, gauging, and anomaly data. Here the emphasis shifts. A TQFT is not merely a bookkeeping device for another theory; it can be a quantum field theory whose own observables, Hilbert spaces, defects, and partition functions are topological.

The simplest slogan is:

$$
\text{TQFT}=\text{QFT with no local metric-dependent propagating degrees of freedom}.
$$

That slogan is useful but incomplete. Some TQFTs are defined by metric-independent actions, such as Chern–Simons and BF theory. Some arise by twisting supersymmetric theories so that metric dependence becomes $Q$-exact. Some are best defined axiomatically as functors from bordisms to vector spaces. Some appear as low-energy effective descriptions of gapped topological phases. Some package symmetry and anomaly data.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A diagram showing the functorial TQFT assignment from closed spatial manifolds to Hilbert spaces, from bordisms to linear maps, and from closed spacetime manifolds to numbers.](/figures/symmetry-anomalies-topology/tqft-functorial-picture.svg)

<figcaption>

A functorial TQFT assigns a vector space to a closed spatial manifold $\Sigma_{d-1}$, a linear map to a bordism $M_d:\Sigma_{\mathrm{in}}\to\Sigma_{\mathrm{out}}$, and a number to a closed $d$-manifold. Physical path integrals, canonical quantization, and topological invariants meet in this diagram.

</figcaption>
</figure>

This chapter is deliberately placed after Symmetry TFT and Anomaly Inflow. By now, topological theories have already been used to organize symmetry. The goal here is to understand what those theories are.

## Prerequisites

You should be comfortable with differential forms, gauge fields, Wilson lines, background fields, topological terms, and basic defect language. The chapters on [Topological Terms](/symmetry-anomalies-topology/topological-terms/), [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/), [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/), and [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) are the natural preparation.

Mathematically, the most useful prerequisites are manifolds, orientations, differential forms, Stokes’ theorem, bundles, connections, holonomy, characteristic classes, and basic homology/cohomology. The relevant toolkit pages should be read as needed; this chapter uses the language but keeps the physical interpretation in view.

## What this chapter is for

TQFT appears in several roles in QFT:

| Role | Meaning |
|---|---|
| Topological QFT | A standalone quantum field theory whose observables are topological. |
| Topological sector | A decoupled or protected sector inside a larger QFT. |
| Low-energy phase theory | The infrared description of a gapped topological phase. |
| Symmetry package | A SymTFT encoding global symmetry, gauging, and anomaly data. |
| Mathematical invariant | A field-theoretic construction of manifold, knot, or moduli-space invariants. |
| Defect theory | A topological theory living on or between defects, boundaries, and interfaces. |

The chapter’s purpose is to make these roles precise enough that readers can move between physics and mathematics without losing track of assumptions.

## Reading path

Read the pages in this order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | What Is a TQFT? | The conceptual definition, basic examples, and the difference between topological and merely low-energy effective. |
| 2 | Metric Independence | Stress tensor criteria, deformation invariance, topological correlators, and the difference between Schwarz-type and cohomological mechanisms. |
| 3 | Cohomological TQFT | BRST-like scalar supercharges, $Q$-closed observables, descent, localization-style intuition, and topological twists. |
| 4 | Chern–Simons Theory | The canonical three-dimensional topological gauge theory, Wilson lines, framing, levels, knots, and boundary WZW connections. |
| 5 | BF Theory | A flexible topological gauge theory for finite and continuous higher-form symmetry, constraints, and linking phases. |
| 6 | Dijkgraaf–Witten Theory | Finite gauge theory, group cohomology actions, flat bundles, state sums, and finite-symmetry SymTFT examples. |
| 7 | Donaldson–Witten Theory Preview | Four-dimensional cohomological gauge theory and the bridge between supersymmetric twisting and manifold invariants. |
| 8 | Extended TQFT Preview | Assignments to points, lines, surfaces, defects, and the higher-categorical refinement of ordinary functorial TQFT. |
| 9 | Observables in TQFT | Local, line, surface, and defect observables; linking, fusion, framing, and defect-local operators. |
| 10 | Relation to QFT and Phases | How TQFT appears in infrared limits, topological order, anomalies, generalized symmetry, and ordinary QFT. |

The chapter does not demand that every reader become a category theorist. The first goal is physical fluency: know what kind of topological theory you are using and what information it is allowed to encode.

## Landmarks

### Metric independence

The most recognizable feature of a TQFT is that its observables do not change under smooth metric deformations:

$$
\frac{\delta}{\delta g_{\mu\nu}(x)}
\langle \mathcal O_1\cdots\mathcal O_n\rangle
=0
$$

for appropriate topological observables and away from possible anomalies, contact terms, or framing subtleties.

This does not always mean the action contains no metric. Chern–Simons theory can be written without a metric. Cohomological TQFTs often use a metric in the action, but metric dependence is $Q$-exact, so $Q$-closed observables are metric-independent.

### No local propagating degrees of freedom

Many TQFTs have finite-dimensional Hilbert spaces on compact spatial manifolds. Their observables depend on global topology, linking, holonomy, and boundary data rather than on local particle excitations. This is why they can describe gapped topological phases and protected sectors.

But “no local propagating degrees of freedom” does not mean “nothing happens.” TQFTs can have nontrivial Hilbert spaces, ground-state degeneracy, anyons, knot invariants, mapping-class-group actions, and rich defect fusion.

### Functorial viewpoint

The Atiyah-style axioms summarize a TQFT as a symmetric monoidal functor:

$$
Z:\operatorname{Bord}_d\to \operatorname{Vect}.
$$

A closed $(d-1)$-manifold $\Sigma$ gets a state space:

$$
\Sigma\mapsto Z(\Sigma).
$$

A bordism $M:\Sigma_{\mathrm{in}}\to\Sigma_{\mathrm{out}}$ gets a linear map:

$$
Z(M):Z(\Sigma_{\mathrm{in}})\to Z(\Sigma_{\mathrm{out}}).
$$

A closed $d$-manifold gets a number:

$$
M_d\mapsto Z(M_d)\in\mathbb C.
$$

This formulation is not the only way physicists use TQFT, but it is the cleanest map between path integrals, topology, and algebraic structure.

### Defects and extended observables

TQFT is naturally a theory of extended operators. Wilson loops in Chern–Simons theory, surface operators in BF theory, twist defects in finite gauge theory, and boundary conditions in extended TQFT are not optional decorations. They are often the main observables.

Because topological defects can be freely deformed, their correlation functions depend on topology: linking, fusion, junctions, framing, and boundary attachment.

### Boundary sensitivity

A TQFT on a closed manifold may be simple, but adding a boundary can reveal a rich boundary theory. Chern–Simons theory on a manifold with boundary is tied to chiral current algebra and WZW models. A finite gauge theory with boundary conditions can encode gauging and orbifolding operations. SymTFT is built precisely by using topological boundary conditions.

## Common confusions

**“Topological” means “the action has no metric.”** Sometimes, but not always. Cohomological TQFTs may use a metric while producing metric-independent observables.

**“TQFT means trivial.”** No. TQFTs can have nontrivial state spaces, defects, fusion rules, anyons, ground-state degeneracy, and mapping-class-group actions.

**“A topological term is a TQFT.”** A topological term inside an ordinary QFT is usually not a standalone TQFT. A theta term can affect phases and anomalies while the full theory still has local propagating degrees of freedom.

**“Every gapped theory is a TQFT.”** A gapped theory may flow in the infrared to a TQFT, possibly plus invertible response data, but the microscopic theory need not be topological at finite distance.

**“Metric independence removes all choices.”** Framing, spin structure, orientation, background fields, and boundary conditions may still be essential data.

**“Functorial TQFT is too mathematical for physics.”** It is the clean language for gluing, Hilbert spaces, boundaries, interfaces, and extended defects. You do not need to start there, but eventually it explains why the path-integral gluing rules work.

## Boundaries

This chapter is the canonical home for topological field theories as quantum field theories. It does not replace neighboring chapters.

Topological terms such as theta terms, Wess–Zumino terms, and Chern–Simons terms inside ordinary QFTs belong to [Topological Terms](/symmetry-anomalies-topology/topological-terms/). This chapter studies theories that are topological as theories.

Generalized symmetries and non-invertible symmetries belong to their chapters. This chapter explains the TQFT technology they use.

Topological phases of matter belong primarily to Symmetry in Phases of Matter and the Matter volume. This chapter supplies the TQFT language.

The full mathematical theory of extended TQFT, higher categories, factorization homology, and functorial field theory belongs also to Mathematical and Rigorous QFT. This chapter gives the physics-facing version.

## Where to go next

For a physics-first route, read What Is a TQFT?, Metric Independence, Chern–Simons Theory, BF Theory, and Observables in TQFT. For a symmetry route, read Dijkgraaf–Witten Theory and BF Theory after the Symmetry TFT chapter. For a geometry route, read Cohomological TQFT and Donaldson–Witten Theory Preview after reviewing characteristic classes and moduli spaces.

After this chapter, the natural continuation is Low-Dimensional Symmetry Technology if your interest is two-dimensional duality, orbifolds, current algebras, and bosonization. If your interest is phases of matter, go to Symmetry in Phases of Matter. If your interest is mathematical foundations, go to Mathematical and Rigorous QFT.

## Checkpoint exercises

### Exercise 1: Closed manifold versus bordism

In a functorial TQFT, what is assigned to a closed spatial manifold $\Sigma_{d-1}$, and what is assigned to a closed spacetime manifold $M_d$?

<details><summary><strong>Solution</strong></summary>

A closed spatial manifold $\Sigma_{d-1}$ is assigned a vector space or Hilbert space $Z(\Sigma_{d-1})$. A closed spacetime manifold $M_d$ is assigned a number $Z(M_d)\in\mathbb C$, interpreted as the partition function or path integral on $M_d$.

</details>

### Exercise 2: Metric independence and stress tensor

Why does $T_{\mu\nu}=0$ as an operator imply metric independence, at least formally?

<details><summary><strong>Solution</strong></summary>

The stress tensor measures variation of the action or generating functional with respect to the metric. If insertions are topological and no contact terms or anomalies interfere, then

$$
\frac{\delta}{\delta g_{\mu\nu}(x)}
\langle \mathcal O_1\cdots\mathcal O_n\rangle
\sim
\langle T^{\mu\nu}(x)\mathcal O_1\cdots\mathcal O_n\rangle.
$$

If $T^{\mu\nu}=0$ in the relevant cohomological or operator sense, the correlator is invariant under metric deformations.

</details>

### Exercise 3: TQFT versus topological term

Why is a theta term in four-dimensional Yang–Mills theory not by itself the same as saying Yang–Mills theory is a TQFT?

<details><summary><strong>Solution</strong></summary>

The theta term is topological, but the full Yang–Mills action also contains the metric-dependent kinetic term $\operatorname{tr}F_{\mu\nu}F^{\mu\nu}$. The theory has local propagating gauge-field degrees of freedom. A TQFT is topological as a whole theory, not merely a theory containing one topological term.

</details>

## References

### First-pass references

- Michael Atiyah, “Topological Quantum Field Theories.”
- Edward Witten, “Topological Quantum Field Theory.”
- Edward Witten, “Quantum Field Theory and the Jones Polynomial.”
- Albert Schwarz, early work on topological quantum field theories and Schwarz-type metric-independent actions.
- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology.”

### Physics and geometry references

- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on topology of gauge fields, loop dynamics, and strings/random surfaces.
- Mikio Nakahara, *Geometry, Topology and Physics*, for bundles, characteristic classes, monopoles, instantons, and geometric QFT examples.
- Theodore Frankel, *The Geometry of Physics*, for differential forms, bundles, gauge fields, Chern forms, and physical geometric intuition.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially topological field theory, theta terms, Wess–Zumino terms, Chern–Simons terms, and topological gauge theory.
- Daniel S. Freed and Constantin Teleman, “Relative Quantum Field Theory,” for modern functorial and relative viewpoints.

## Version history

- 2026-06-22: Initial polished chapter overview. Added functorial TQFT map, reading path, landmarks, boundaries, and checkpoint exercises.
