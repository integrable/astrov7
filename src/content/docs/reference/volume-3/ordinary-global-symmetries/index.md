---
title: "Ordinary Global Symmetries"
description: "Chapter overview for ordinary global symmetries, their action on operators and states, and their role as the entry point to the symmetry volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman, Weinberg, Srednicki, Zee; Gaiotto–Kapustin–Seiberg–Willett for the topological-operator viewpoint."
topics:
  - global symmetries
  - operator algebra
  - symmetry representations
  - selection rules
  - topological symmetry operators
canonicalTopics:
  - ordinary-global-symmetry
  - symmetry-actions-on-operators
  - selection-rules
researchStatus:
  established:
    - "Ordinary internal global symmetries, their representations on states and operators, and their selection rules are standard graduate QFT material."
  active:
    - "The topological-operator language used here is now standard for generalized symmetry, while its non-invertible and categorical extensions remain active research areas."
---

Ordinary Global Symmetries is the chapter in the Symmetry, Anomalies, and Topology volume where the word “symmetry” is made precise before currents, gauging, anomalies, or topology add extra structure. The chapter’s main job is to replace the slogan “a symmetry leaves the Lagrangian invariant” by a more durable QFT statement: a symmetry acts on physical observables and states while preserving the structure of the theory.

That shift matters. Lagrangians are presentations; observables are physics. Two dual descriptions may use different fields, an infrared fixed point may have symmetries not obvious in the ultraviolet variables, and a classical transformation may fail quantum mechanically because of an anomaly. This chapter gives the language needed to talk about all of these without getting hypnotized by the first set of fields one writes down.

A useful first slogan is

$$
\text{ordinary global symmetry}
=\text{physical automorphism of observables compatible with locality and dynamics}.
$$

The pages here are deliberately conservative. They focus on ordinary zero-form global symmetries: symmetries acting on local operators and particle-like states. The later chapters broaden this to currents, background fields, gauge redundancy, higher-form symmetries, non-invertible symmetries, and symmetry TFT.

## Prerequisites

You should first know the [volume overview](/symmetry-anomalies-topology/) and the [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

The mathematical prerequisites are modest: basic Hilbert spaces, operators, correlation functions, group actions, and finite-dimensional representations. Noether currents, Ward identities, spontaneous symmetry breaking, anomalies, and higher-form symmetries are not prerequisites; they are what this chapter prepares you to study.

Readers who have not seen group representations before can still read the chapter if they accept the idea that a group element $g$ may act on a multiplet of operators by a matrix $R(g)$.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/) | The operator-first definition of symmetry, the role of the Lagrangian as a presentation, and the topological-operator picture. |
| 2 | Internal Versus Spacetime Symmetries | The distinction between symmetries acting on fields at fixed spacetime point and symmetries that also move spacetime itself. |
| 3 | Continuous and Discrete Symmetries | Why continuous symmetries lead to currents while discrete symmetries usually do not. |
| 4 | Symmetry Groups and Representations | How fields, operators, and states organize into representations of a symmetry group. |
| 5 | Action on Fields and Operators | The difference between transforming elementary fields, composite operators, order parameters, and extended probes. |
| 6 | Symmetry Defects and Topological Operators | The modern codimension-one defect viewpoint for ordinary symmetries. |
| 7 | Charges and Hilbert Space | How global charges label sectors, commute with the Hamiltonian, and organize the spectrum. |
| 8 | Selection Rules | How symmetry forces correlation functions and amplitudes to vanish unless representation-theoretic conditions are met. |
| 9 | Symmetry Algebras | The infinitesimal structure of continuous symmetries and the relation between charges and Lie algebras. |
| 10 | Projective Representations Preview | Why quantum symmetries may be represented up to phases, and why this matters for spin, central extensions, and anomalies. |

For a minimal first pass, read steps 1, 3, 4, 7, and 8. Then move to the Noether Currents and Ward Identities chapter. Return to the topological-operator page before studying higher-form or non-invertible symmetry.

## Landmarks

**Symmetry acts on observables.** A field transformation is often the easiest way to write a symmetry, but it is not the invariant definition. The same QFT can have different field variables. The symmetry is the action on the algebra of observables, on the Hilbert space, and on correlation functions.

**A global symmetry relates distinct physical configurations.** Gauge transformations do not. A global symmetry can take a state or operator to a physically different state or operator with the same energy and correlation structure. A gauge transformation changes the description of the same physical configuration.

**The vacuum matters.** The theory may have a symmetry even if a particular state does not. When the vacuum is invariant, correlators obey ordinary selection rules. When the vacuum is not invariant, the symmetry is spontaneously broken and the Hilbert space splits into sectors connected by the symmetry but not by local dynamics in infinite volume.

**Representations organize physics.** Local operators, particles, multiparticle states, and order parameters usually come in representations of the symmetry group. This is why symmetry predicts degeneracies, forbids processes, constrains operator products, and makes “quantum numbers” meaningful.

**Discrete symmetries are not second-class citizens.** A $\mathbb Z_2$ spin-flip symmetry or charge conjugation symmetry can be as physically consequential as a continuous $U(1)$ symmetry, even though it has no Noether current of the usual kind.

**The global form matters.** A Lie algebra does not determine the full symmetry. The distinction between $SU(2)$ and $SO(3)=SU(2)/\mathbb Z_2$, or between $U(1)$ and $\mathbb R$, can affect allowed charges, line operators, background bundles, and anomalies.

**Topological operators are the modern bridge.** An ordinary global symmetry element $g\in G$ can often be represented in Euclidean spacetime by a codimension-one topological operator $U_g(\Sigma_{d-1})$. Moving this operator across an insertion applies $g$ to that insertion. This is the seed of the generalized-symmetry language used later in the volume.

## Common confusions

**“The Lagrangian is invariant, so the quantum theory has the symmetry.”** Not always. A classical transformation must also be compatible with the path-integral measure, regulator, counterterms, and operator definition of the quantum theory. Anomalies are precisely failures of this upgrade.

**“The field changes, so the symmetry is broken.”** A nontrivial symmetry is supposed to transform charged fields or operators. Symmetry breaking is about the state, usually the vacuum, not about whether individual operators transform.

**“Gauge symmetry is a kind of global symmetry with a local parameter.”** This sentence causes carnage. Gauge symmetry is redundancy in description. Global symmetry is physical structure. Large gauge transformations and boundary symmetries add subtleties, but the first distinction should be kept sharp.

**“The infinitesimal algebra is enough.”** The Lie algebra misses the global form of the group, disconnected components, projective phases, allowed bundles, and possible topological terms. Many anomaly and line-operator questions live exactly in this missing global data.

**“A symmetry must be visible in the elementary fields.”** Duality, bosonization, confinement, and emergent infrared symmetry all violate this expectation. A symmetry may act simply on nonlocal operators or on a dual set of fields.

**“Selection rules are just particle-physics bookkeeping.”** Selection rules are correlation-function statements. They constrain amplitudes, operator product expansions, matrix elements, finite-volume spectra, and allowed terms in effective actions.

## Boundaries

This chapter introduces ordinary global symmetries. It stops before the technologies that diagnose, derive, break, gauge, or generalize them.

| Topic | Treated here | Continued in |
|---|---|---|
| Definition of symmetry | Action on states, operators, fields, and correlators | Noether Currents and Ward Identities |
| Continuous symmetry | Charges and representations at the introductory level | Noether currents, current algebra, Ward identities |
| Discrete symmetry | Basic actions and selection rules | Discrete, Spacetime, and Antiunitary Symmetries |
| Gauge transformations | Only as a contrast with physical global symmetry | Gauge Redundancy and BRST |
| Background fields | Mentioned as a diagnostic | Background Fields and Gauging |
| Symmetry breaking | Only the basic distinction between theory and state | Spontaneous Symmetry Breaking |
| Anomalies | Only as warnings about quantization | Anomalies and ’t Hooft Anomalies |
| Higher-form symmetry | Only the codimension-one preview for ordinary symmetry | Higher-Form and Generalized Symmetries |
| Non-invertible symmetry | Only a later handoff | Non-Invertible and Categorical Symmetries |

## Where to go next

After this chapter, the natural next stop is Noether Currents and Ward Identities. There, continuous symmetry becomes local in spacetime through currents, charges, contact terms, and Ward identities.

For anomaly theory, continue next to Background Fields and Gauging. The cleanest modern definition of many anomalies is not “the current is not conserved” but “the symmetry cannot be consistently coupled to and gauged through background fields.”

For gauge theory, jump to Gauge Redundancy and BRST after you are comfortable saying what a global symmetry is. Most gauge-theory confusions are just global-symmetry intuitions applied to redundancies.

For modern generalized symmetry, return to the topological-operator viewpoint in this chapter, then read Defects and Extended Operators followed by Higher-Form and Generalized Symmetries.

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters 5–6. Clear operator-level treatment of spacetime and internal symmetries, currents, and conservation laws.
- Sidney Coleman, *Aspects of Symmetry*. Especially useful for symmetry breaking, current algebra, scale symmetry, and solitons.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 2. The foundational quantum-mechanical symmetry viewpoint, including unitary and antiunitary implementations and projective representations.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24. Compact treatment of continuous, discrete, and nonabelian symmetries in Lagrangian QFT.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the early symmetry chapter and later chapters on symmetry breaking and anomaly physics.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” The standard modern entry point for the topological-operator viewpoint that generalizes ordinary global symmetry.

## Version history

- **2026-06-16:** Initial polished chapter overview for Ordinary Global Symmetries.
