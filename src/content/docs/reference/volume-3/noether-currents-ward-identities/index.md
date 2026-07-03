---
title: "Noether Currents and Ward Identities"
description: "Chapter overview for Noether currents, conserved charges, local current conservation, contact terms, and Ward identities in the Symmetry, Anomalies, and Topology volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §22 and §§67–68; Coleman lectures on spacetime/internal symmetries and current algebra; Weinberg Vol. I on symmetry generators and Ward identities."
topics:
  - Noether currents
  - conserved charges
  - Ward identities
  - current conservation
  - contact terms
  - current algebra
canonicalTopics:
  - noether-current
  - ward-identity
  - conserved-charge
  - current-contact-term
researchStatus:
  established:
    - "Noether currents, conserved charges, and Ward identities are standard consequences of continuous symmetries when the symmetry is nonanomalous and boundary conditions are controlled."
  active:
    - "Modern QFT refines these statements through contact-term schemes, background-field dependence, anomalies, defects, generalized symmetries, and nonperturbative definitions of currents."
---

Noether Currents and Ward Identities is the chapter in the Symmetry, Anomalies, and Topology volume where continuous symmetry becomes a local spacetime statement. The previous chapter explained symmetry as an action on states, fields, operators, and defects. This chapter explains how an infinitesimal continuous symmetry produces currents, conserved charges, contact terms, and Ward identities.

The chapter exists because the sentence “the current is conserved” is too small for QFT. In correlation functions, conservation is modified by contact terms at operator insertions. In gauge theories, currents can be improved, mixed, constrained, or redundant. In quantum theory, a classically conserved current can fail because of anomalies. The useful object is therefore not just a current but the full package:

$$
\text{continuous symmetry}
\quad\leadsto\quad
\text{current}\; j_a^\mu,
\quad
\text{charge}\; Q_a,
\quad
\text{Ward identities}.
$$

Read this chapter when you want to know how symmetry constrains correlation functions locally, how charges act on operators, why contact terms are not optional, and where the anomaly chapters will later modify the story.


<figure class="doc-figure" style="--figure-width: 50rem;">

![A schematic map from a continuous symmetry to a Noether current, a conserved charge, Ward identities, contact terms, and possible anomaly or explicit-breaking terms.](/figures/symmetry-anomalies-topology/noether-ward-identity-map.svg)

<figcaption>

A continuous symmetry has two complementary local expressions. Integrating $j^0$ over a surface gives the charge $Q$ acting on states and operators. Inserting $\partial_\mu j^\mu$ in correlation functions gives Ward identities; contact terms encode the action on insertions.

</figcaption>
</figure>

## Prerequisites

You should know the [volume overview](/symmetry-anomalies-topology/), the [Conventions and Notation](/symmetry-anomalies-topology/conventions/), and the Ordinary Global Symmetries chapter through [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/).

You should be comfortable with classical field variations, equal-time commutators, time-ordered correlation functions, and basic path-integral generating functionals. The chapter does not require anomaly theory, BRST, background fields, or spontaneous symmetry breaking, but it is designed to prepare for all four.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Noether Currents | The derivation of currents from continuous field variations and the meaning of on-shell conservation. |
| 2 | Improved Currents and Ambiguities | Why currents are not unique, and which ambiguities change nothing physical. |
| 3 | Conserved Charges | How spatial integrals of currents generate symmetry transformations on states and operators. |
| 4 | Current Conservation in Correlation Functions | Why $\partial_\mu j^\mu=0$ is true away from insertions but incomplete at coincident points. |
| 5 | Ward Identities: Operator Form | The canonical/operator derivation of local and integrated Ward identities. |
| 6 | Ward Identities: Path-Integral Form | The change-of-variables derivation, including the role of the measure and sources. |
| 7 | Contact Terms | A careful repair page for delta functions, coincident insertions, scheme choices, and local counterterms. |
| 8 | Current Algebra | Equal-time commutators, charge algebras, Schwinger terms, and the preview of central extensions. |
| 9 | Charges Acting on Local Operators | The precise relation between $Q_a$, commutators, operator multiplets, and representation matrices. |
| 10 | Soft Theorems Preview | The first bridge from Ward identities to low-energy emission theorems and asymptotic symmetries. |

For a minimal first pass, read steps 1, 3, 4, 5, and 7. Then move to Background Fields and Gauging. Return to the path-integral and current-algebra pages before studying anomalies.

## Landmarks

**Noether currents localize continuous symmetry.** A continuous global symmetry has an infinitesimal parameter. If one temporarily lets that parameter depend on spacetime, the variation of the action identifies a current. Schematically,

$$
\delta S
=-\int d^dx\, (\partial_\mu\alpha^a)j_a^\mu
$$

up to equation-of-motion terms and convention-dependent signs. Constant $\alpha^a$ then gives a symmetry, while local $\alpha^a(x)$ diagnoses the current.

**Conservation is an operator statement with qualifications.** Away from insertions, an exact nonanomalous symmetry gives

$$
\partial_\mu j_a^\mu(x)=0.
$$

Inside correlation functions, the derivative also sees the transformation of operator insertions. The useful schematic identity is

$$
\partial_\mu\langle j_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=\text{contact terms at }x=x_i.
$$

Those contact terms are not dirt under the rug. They are how the current knows that the symmetry acts on operators.

**Charges are integrals of currents.** On a time slice,

$$
Q_a=\int d^{d-1}\mathbf x\, j_a^0(t,\mathbf x)
$$

when the integral converges and boundary conditions are controlled. The charge should generate the symmetry action,

$$
\delta_a\mathcal O=i[Q_a,\mathcal O]
$$

with the convention used in this volume.

**Current conservation implies surface independence.** In Euclidean language, a conserved current can be integrated over a codimension-one surface. Deforming the surface without crossing charged insertions does not change the result. This is the current version of the topological-operator picture introduced in the ordinary symmetry chapter.

**Currents are not unique.** One can often shift

$$
j^\mu\mapsto j^\mu+\partial_\nu B^{[\mu\nu]}
$$

without changing the conserved charge under suitable boundary conditions. Stress tensors have analogous improvement ambiguities. Composite-operator renormalization can also mix currents with other local operators.

**Ward identities are symmetry constraints on correlators.** They are not merely perturbative Feynman-diagram tricks. Ward identities express the fact that changing variables by a symmetry in the path integral does not change the integral, unless the measure, regulator, sources, or boundary conditions transform anomalously.

**Anomalies are the controlled failure mode.** When the classical current conservation equation fails quantum mechanically, the right-hand side is not random. It is constrained by locality, background fields, Wess–Zumino consistency, and anomaly inflow. This chapter teaches the nonanomalous baseline so the anomaly chapters have something precise to modify.

## Common confusions

**“Noether currents are unique.”** They are not. Improvement terms, equation-of-motion terms, local counterterms, and operator mixing can change the current. Charges, Ward identities, and background-field responses are usually more invariant than a particular formula for $j^\mu$.

**“Current conservation means Ward identities have zero right-hand side.”** Only away from insertions. At coincident points, contact terms encode the symmetry variation of the inserted operators.

**“Discrete symmetries should have Noether currents too.”** Ordinary Noether currents come from continuous parameters. Discrete symmetries still give selection rules and topological defects, but not a local Noether current of the usual kind.

**“The charge always exists.”** The integral defining $Q$ can fail because of infrared behavior, massless modes, boundaries, gauge constraints, spontaneous symmetry breaking, or noncompact spatial slices. The current may still exist locally even when the global charge is subtle.

**“A gauge current is just a global current with a spacetime-dependent parameter.”** Gauge transformations are redundancies. Global currents generate physical transformations. Coupling to gauge fields introduces constraints, BRST structure, and boundary subtleties that need their own chapter.

**“Ward identities are only path-integral identities.”** They can be derived in both operator and path-integral language. The two derivations illuminate different issues: equal-time commutators and contact terms on one side, measure and source variations on the other.

**“An anomalous current is simply not conserved, end of story.”** The anomaly is highly structured. It must satisfy consistency conditions and is often better understood as an obstruction to gauging the symmetry.

## Boundaries

This chapter is about ordinary continuous symmetries and their local current consequences. It deliberately stops before the following subjects take over.

| Topic | Treated here | Continued in |
|---|---|---|
| Ordinary symmetry action | Used as input for currents and charges | Ordinary Global Symmetries |
| Noether theorem | Current derivation and current ambiguities | Foundations of QFT for the basic classical theorem |
| Ward identities | Operator and path-integral forms, including contact terms | Background Fields and Gauging; Anomalies |
| Discrete symmetry | Mentioned mainly by contrast | Discrete, Spacetime, and Antiunitary Symmetries |
| Spontaneous symmetry breaking | Charge/current subtleties and Goldstone handoff only | Spontaneous Symmetry Breaking |
| Gauge redundancy | Only contrasted with global currents | Gauge Redundancy and BRST |
| Background fields | Previewed as a clean source-current formalism | Background Fields and Gauging |
| Anomalies | Only the nonanomalous baseline and warning signs | Anomalies; ’t Hooft Anomalies and Anomaly Matching |
| Higher-form symmetry | Surface-independence analogy only | Higher-Form and Generalized Symmetries |
| Soft theorems | Introductory preview | Perturbative QFT, scattering, and asymptotic symmetry chapters |

## Where to go next

After this chapter, continue to Background Fields and Gauging. That chapter upgrades currents into source couplings and explains why background fields are the clean diagnostic for gauging, anomalies, and global-form questions.

If your goal is symmetry breaking, go next to Spontaneous Symmetry Breaking. Goldstone's theorem is essentially a statement about currents, charges, locality, and the vacuum, so the current technology here is the right preparation.

If your goal is anomaly physics, read the path-integral Ward identity and contact-term pages carefully, then move to Anomalies and ’t Hooft Anomalies and Anomaly Matching.

If your goal is gauge theory, read Gauge Redundancy and BRST after this chapter. Ward identities in gauge theories become Slavnov–Taylor identities and BRST cohomology statements; the ordinary current story is the warm-up, not the final form.

## References

- Mark Srednicki, *Quantum Field Theory*, §22 and §§67–68. Compact derivation of continuous symmetries, Noether currents, and Ward identities, with later QED applications.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters 5–6. Operator-minded discussion of spacetime and internal symmetries, currents, and conservation laws.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” “Dilatations,” and “Renormalization and Symmetry.” Classic source for current algebra, Ward identities, broken symmetry, and scale-current reasoning.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I. Foundational treatment of symmetries, generators, and operator constraints in relativistic quantum theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on Noether's theorem, path integrals, Ward–Takahashi identities, and anomalies.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*. Standard reference for path-integral Ward identities and perturbative gauge-theory Ward identities.

## Version history

- **2026-06-17:** Initial polished chapter overview for Noether Currents and Ward Identities.
