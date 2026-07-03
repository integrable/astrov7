---
title: "Gauge Redundancy and BRST"
description: "Chapter overview for gauge redundancy, gauge fixing, Faddeev–Popov ghosts, BRST symmetry, BRST cohomology, physical states, BV preview, Gribov ambiguities, and large gauge transformations."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Faddeev–Popov; Becchi–Rouet–Stora–Tyutin; Srednicki §§69–74; Weinberg Vol. II Ch. 15; Coleman on gauge-field functional integrals; Zinn-Justin on gauge theory and BRST."
topics:
  - gauge redundancy
  - gauge fixing
  - Faddeev-Popov ghosts
  - BRST symmetry
  - BRST cohomology
  - physical states
  - BV formalism
  - Gribov ambiguity
  - large gauge transformations
canonicalTopics:
  - gauge-redundancy
  - gauge-fixing
  - faddeev-popov-ghost
  - brst-symmetry
  - brst-cohomology
  - physical-state-space
  - bv-formalism
  - gribov-ambiguity
researchStatus:
  established:
    - "Gauge symmetry in QFT is a redundancy of description; gauge fixing and BRST are systematic ways to compute without changing gauge-invariant physics."
    - "For perturbative gauge theories with suitable gauge fixing, physical local observables and states are organized by BRST cohomology."
  active:
    - "Nonperturbative gauge fixing, Gribov regions, boundaries, edge modes, large gauge transformations, higher gauge fields, and BV-derived formulations remain central in modern gauge theory and mathematical QFT."
---

Gauge Redundancy and BRST is the chapter in the Symmetry, Anomalies, and Topology volume where the word “symmetry” stops meaning just one thing. A global symmetry acts on physical states and operators. A gauge symmetry identifies different field configurations as the same physical configuration.

This chapter exists because the distinction is load-bearing. If one treats gauge redundancy as an ordinary global symmetry, one misunderstands the Higgs mechanism, Ward identities, anomalies, ghosts, physical Hilbert spaces, and even what counts as an observable.

The guiding slogan is:

$$
\text{gauge symmetry is redundancy; BRST is its quantum bookkeeping.}
$$

Gauge fixing chooses coordinates on redundant field space. Faddeev–Popov ghosts account for the Jacobian of that choice. BRST symmetry packages the remaining gauge independence into a fermionic differential whose cohomology selects physical observables and states.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A roadmap diagram for the Gauge Redundancy and BRST chapter. It starts from redundant gauge field space, passes through quotienting and gauge fixing, introduces ghosts and the BRST differential, then ends with BRST cohomology and physical observables, with warnings for boundaries, large gauge transformations, Gribov copies, and BV.](/figures/symmetry-anomalies-topology/gauge-redundancy-brst-roadmap.svg)

<figcaption>

Gauge fixing does not remove physics; it removes overcounting. BRST turns the gauge-fixed theory into a cohomological problem: physical observables are BRST-closed modulo BRST-exact redundancies. Large gauge transformations, boundaries, Gribov copies, and open gauge algebras require extra structure.

</figcaption>
</figure>

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), and the [Higgs Mechanism Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/higgs-mechanism-preview/).

From the Noether chapter, the most useful pages are [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/), and [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/).

Mathematically, you should be comfortable with path integrals, determinants, Lie algebras, Grassmann variables, and the idea of quotienting a space by an equivalence relation.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Gauge Symmetry Is Redundancy | The conceptual reset: gauge transformations identify descriptions, while global symmetries act on physical data. |
| 2 | Local versus Global Transformations | Why compactly supported gauge transformations, boundary transformations, and large transformations do different jobs. |
| 3 | Gauge Fixing | How a gauge condition chooses representatives on gauge orbits, and why no single choice is globally innocent. |
| 4 | Faddeev–Popov Ghosts | The determinant behind gauge fixing and the origin of ghost fields in perturbation theory. |
| 5 | BRST Symmetry | The fermionic symmetry of the gauge-fixed action and the nilpotent differential $s$. |
| 6 | BRST Cohomology | Why physical operators are BRST-closed modulo BRST-exact operators. |
| 7 | Physical State Space | The Hilbert-space version: constraints, ghosts, indefinite metric, and physical states. |
| 8 | BV Formalism Preview | A preview of the antifield/master-equation formalism for general gauge systems. |
| 9 | Gribov Ambiguities Preview | Why gauge fixing can fail nonperturbatively and how copies complicate the quotient. |
| 10 | Large Gauge Transformations | How topology, boundary conditions, theta vacua, anomalies, and global form enter gauge redundancy. |

For a minimal first pass, read steps 1–6. Then read Physical State Space before studying covariant quantization of non-Abelian gauge theory. Return to BV, Gribov ambiguities, and large gauge transformations when you study anomalies, instantons, topological terms, or nonperturbative gauge theory.

## Landmarks

**Gauge transformations identify descriptions.** If $A$ and $A^g$ are related by an allowed gauge transformation, they represent the same physical configuration. The physical configuration space is therefore not the raw field space but a quotient:

$$
\mathcal F_{\rm phys}\sim \mathcal F_{\rm fields}/\mathcal G_{\rm gauge}.
$$

This quotient is easy to write and hard to do.

**Gauge redundancy is not global symmetry.** A global symmetry maps physical states to physical states. A gauge transformation with trivial boundary action maps a description to an equivalent description. This is why local gauge-variant fields are not physical observables by themselves.

**Boundary transformations can become physical.** A gauge transformation that does not die at the boundary may act nontrivially on physical states. In electrodynamics, the distinction between a compactly supported gauge transformation and one approaching a nonzero function at infinity is the difference between redundancy and charge.

**Gauge fixing chooses representatives.** The path integral over gauge fields overcounts configurations because it integrates along gauge orbits. Gauge fixing inserts a condition such as

$$
\mathcal F[A]=0
$$

and a determinant that compensates for the change of variables from fields to orbits plus gauge directions.

**Faddeev–Popov ghosts are determinant fields.** In non-Abelian gauge theory, the Faddeev–Popov determinant depends on the gauge field. It can be represented by Grassmann fields $c$ and $\bar c$. These ghosts are not physical negative-probability particles. They are auxiliary fields that make the gauge-fixed path integral local and preserve unitarity of the physical sector.

**BRST is the remnant of gauge redundancy after gauge fixing.** Perturbative gauge fixing usually destroys manifest gauge invariance, but it leaves a fermionic symmetry. In the conventions of this volume, a typical non-Abelian BRST transformation is schematically

$$
sA=Dc,
\qquad
sc=ic^2,
\qquad
s\psi=ic\psi,
$$

with $s^2=0$ on the fields, up to standard auxiliary-field details.

:::note[Convention-sensitive source note]
The compact formula $sc=ic^2$ uses Hermitian generators and $[T_a,T_b]=if_{ab}^{\ \ c}T_c$. In components it is the familiar $sc^a=-\frac12 f^a_{\ bc}c^bc^c$, up to index-placement conventions. Anti-Hermitian generator conventions move the factors of $i$ and can make the same formula look sign-reversed.
:::

**Physical observables are cohomology classes.** An observable $\mathcal O$ is physical if

$$
s\mathcal O=0,
$$

and two observables that differ by

$$
\mathcal O\sim\mathcal O+s\mathcal X
$$

are physically equivalent. This is the BRST cohomology at ghost number zero.

**Gauge anomalies are consistency failures.** A global anomaly is physical data. A gauge anomaly is different: it means the proposed redundancy cannot be consistently imposed. In BRST language, a gauge anomaly obstructs BRST invariance or nilpotency at the quantum level.

**The quotient can have topology.** Large gauge transformations, nontrivial bundles, theta sectors, instantons, line operators, and global form all come from the fact that gauge orbits and gauge-field configuration space can have nontrivial topology.

**Gauge fixing can fail globally.** A local gauge condition may intersect a gauge orbit more than once or miss some orbits. These are Gribov-copy issues. They are often invisible in perturbation theory around a simple background, but crucial nonperturbatively.

## Common confusions

**“Gauge symmetry is a physical symmetry like rotation symmetry.”** Not in the local redundancy sense. Spatial rotations act on physical configurations. Gauge transformations with trivial boundary action identify descriptions of the same physical configuration.

**“Gauge fixing breaks gauge symmetry, so physics depends on the gauge.”** Gauge fixing changes the description, not the gauge-invariant physics. BRST identities are the gauge-fixed expression of this independence.

**“Ghosts are particles with negative probability.”** Faddeev–Popov ghosts are Grassmann fields used to represent a determinant. They can run in internal lines of perturbative diagrams but are not external physical states.

**“BRST is just another global symmetry.”** BRST is a fermionic symmetry of the gauge-fixed formulation whose cohomology implements gauge redundancy. It is not an ordinary physical flavor symmetry.

**“All gauge transformations are redundancies.”** Gauge transformations that act nontrivially at boundaries, change topological sectors, or represent global-form data may have physical consequences. One must specify the allowed gauge group and boundary conditions.

**“Gauge-invariant means local and simple.”** Gauge-invariant operators can be nonlocal, composite, dressed, boundary-attached, or line-like. Charged operators in gauge theory often require dressing or boundary conditions.

**“The Faddeev–Popov procedure solves all gauge fixing.”** It works beautifully in perturbation theory under suitable assumptions. Nonperturbatively, Gribov copies and global issues require more care.

**“BRST cohomology is optional formalism.”** For covariant quantization of gauge theories, BRST is one of the cleanest ways to prove that unphysical polarizations and ghosts decouple from physical amplitudes.

## Boundaries

This chapter is about the symmetry and redundancy structure of gauge theory. It is not the full gauge-theory or Standard Model volume.

| Topic | Treated here | Continued in |
|---|---|---|
| Gauge redundancy | Conceptual distinction from global symmetry | Gauge Theories and the Standard Model for physical Yang–Mills dynamics |
| Gauge fixing | General logic and common choices | Perturbative QFT for propagators and diagram rules |
| Faddeev–Popov ghosts | Determinant origin and role in gauge-fixed actions | Gauge theory and perturbative scattering pages |
| BRST symmetry | Nilpotent differential and gauge-fixed invariance | Renormalization of gauge theories; Mathematical and Rigorous QFT |
| BRST cohomology | Physical operators and states | Anomalies, BV formalism, and cohomological TQFT |
| Physical Hilbert space | Constraint and cohomological viewpoint | Canonical quantization and scattering volumes |
| BV formalism | Preview only | Mathematical and Rigorous QFT; Supersymmetry/Duality for localization and cohomological theories |
| Gribov copies | Warning and nonperturbative preview | Nonperturbative QFT and lattice gauge theory |
| Large gauge transformations | Topological and boundary role | Topological Terms; Anomalies; Defects and Extended Operators |
| Higgs mechanism | Conceptual handoff only | Spontaneous Symmetry Breaking; Gauge Theories and the Standard Model |

## Where to go next

After this overview, start with Gauge Symmetry Is Redundancy and Local versus Global Transformations. Those two pages fix the language needed for every later use of gauge theory.

If your goal is perturbative gauge theory, read through Faddeev–Popov Ghosts and BRST Symmetry, then continue to the gauge-theory chapters in the Perturbative QFT and Gauge Theories volumes.

If your goal is anomalies, read BRST Cohomology and Large Gauge Transformations before entering the Anomalies chapter. Gauge anomalies are most sharply understood as obstructions to maintaining BRST consistency after quantization.

If your goal is topology, line operators, and confinement, return to Large Gauge Transformations after reading Defects and Extended Operators, Higher-Form and Generalized Symmetries, and Topological Terms.

## References

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967) 29–30.
- C. Becchi, A. Rouet, and R. Stora, classic papers on BRST symmetry.
- I. V. Tyutin, “Gauge Invariance in Field Theory and Statistical Physics in Operator Formalism,” Lebedev preprint (1975).
- Mark Srednicki, *Quantum Field Theory*, sections on non-Abelian gauge theory, path integrals for gauge theory, and BRST symmetry.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15. Gauge theories, Faddeev–Popov quantization, ghosts, BRST symmetry, and BV preview.
- Sidney Coleman, *Aspects of Symmetry*, especially the gauge-field and Faddeev–Popov parts of “Secret Symmetry.”
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters on gauge fields, Faddeev–Popov quantization, and Ward identities.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on gauge fields, BRST symmetry, and the Zinn-Justin equation.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Standard reference for constraints, BRST, and Hamiltonian quantization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on gauge invariance, path integrals, and Yang–Mills theory.
- V. N. Gribov, “Quantization of Non-Abelian Gauge Theories,” *Nuclear Physics B* **139** (1978) 1–19.
- I. M. Singer, “Some Remarks on the Gribov Ambiguity,” *Communications in Mathematical Physics* **60** (1978) 7–12.

## Version history

- 2026-06-17: Initial polished chapter overview. Added the redundancy-versus-symmetry distinction, reading path, BRST cohomology landmarks, anomaly and boundary warnings, Gribov and large-gauge handoffs, and references.
