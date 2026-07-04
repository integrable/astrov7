---
title: "Nonperturbative Definitions of QFT"
description: "Chapter overview for definitions of quantum field theory beyond formal perturbative expansions."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader; Wilson–Kogut; Glimm–Jaffe; Zinn-Justin; Srednicki; Schwartz."
topics:
  - nonperturbative definitions
  - Euclidean path integrals
  - lattice regularization
  - continuum limits
  - reflection positivity
  - Hilbert space reconstruction
  - Hamiltonian definitions
  - constructive QFT
  - algebraic QFT
  - sign problem
canonicalTopics:
  - nonperturbative-qft
  - euclidean-qft
  - lattice-field-theory
  - continuum-limit
  - reflection-positivity
  - hamiltonian-qft
  - constructive-qft
  - algebraic-qft
  - sign-problem
researchStatus:
  established:
    - "A nonperturbative definition requires more than a formal Lagrangian: it must specify a regulator or construction, observables, limits, symmetries, and Hilbert-space or Euclidean consistency conditions."
  active:
    - "Complete nonperturbative constructions are routine for many lattice-regulated theories and special low-dimensional models, but remain subtle for chiral gauge theories, real-time dynamics, finite density, and continuum four-dimensional interacting theories."
---

Nonperturbative Definitions of QFT is the chapter in the Nonperturbative QFT volume where formal expressions become actual theories. The central question is not “which Feynman rules follow from this Lagrangian?” but “what mathematical object are we claiming exists, and how would we compute its observables without expanding around one Gaussian saddle?”

The chapter exists because many expressions that look like definitions are only perturbative recipes. A continuum Lagrangian plus the symbol $\mathcal D\Phi$ can generate diagrams, but it does not by itself specify the integration cycle, regulator, boundary conditions, global sectors, Hilbert space, or continuum limit. Nonperturbative work forces these details out into the open.

The chapter’s practical goal is to teach the main routes by which QFTs are defined beyond formal perturbation theory: Euclidean path integrals, lattice regularization, canonical Hamiltonian constructions, finite-volume limits, continuum limits, reflection positivity, and rigorous algebraic or constructive frameworks.

A useful slogan is

$$
\text{a nonperturbative definition is not a formal integral; it is a controlled limiting procedure for observables.}
$$

## Prerequisites

You should know the basic path-integral generating functional, Gaussian integration, Wick rotation in simple examples, and the idea of renormalization. You should also be comfortable with correlation functions as primary observables.

It helps to have read the conceptual entrance to this volume, especially [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/), [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/), and [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/). The conventions for Euclidean continuation, gauge fields, topological sectors, and lattice notation are fixed in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

No prior rigorous QFT background is assumed. The chapter introduces reflection positivity, continuum limits, and constructive or algebraic viewpoints as physics-facing tools before sending the reader to more theorem-first treatments.

## Reading path

Read the first five pages in order on a first pass. The later pages can then be used as specialized references.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) | How $e^{-S_E}$, Schwinger functions, ground-state projection, spectral gaps, and reflection positivity turn Euclidean data into QFT data. |
| 2 | [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/) | How a finite lattice turns the path integral into an ordinary finite-dimensional integral or finite Hilbert-space problem. |
| 3 | [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) | Why boxes, tori, boundary conditions, and the order of limits are part of the definition rather than harmless decorations. |
| 4 | [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) | How renormalized QFT emerges from a regulated family by tuning toward a critical surface or renormalized trajectory. |
| 5 | [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) | The condition that lets Euclidean correlation functions reconstruct a positive-norm Lorentzian Hilbert space. |
| 6 | [Canonical Hamiltonian Definition](/nonperturbative-qft/nonperturbative-definitions/canonical-hamiltonian-definition/) | How a QFT may be defined by local operators and a Hamiltonian, especially in finite volume or on a spatial lattice. |
| 7 | [Constructive QFT Preview](/nonperturbative-qft/nonperturbative-definitions/constructive-qft-preview/) | A handoff to theorem-level constructions of interacting models, measures, and limits. |
| 8 | [Algebraic QFT Preview](/nonperturbative-qft/nonperturbative-definitions/algebraic-qft-preview/) | A handoff to local operator algebras, nets of observables, locality, states, and representation theory. |
| 9 | [Sign Problem Preview](/nonperturbative-qft/nonperturbative-definitions/sign-problem-preview/) | Why complex Euclidean weights obstruct probability-based Monte Carlo methods and simple positivity arguments. |

The most important page for later nonperturbative physics is the Euclidean path-integral page. Lattice gauge theory, instantons, theta sectors, thermal QFT, finite-volume spectra, and mass-gap diagnostics all reuse its language.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Regulated theory | A finite-cutoff or finite-volume object whose observables are well-defined before limits are taken. | A formal continuum integral is usually not the definition; the regulated object is. |
| Schwinger functions | Euclidean correlation functions $S_n(x_1,\ldots,x_n)=\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle_E$. | These are the usual nonperturbative Euclidean data. |
| Reflection positivity | A Euclidean positivity condition under reflection of Euclidean time. | It is the bridge from Euclidean correlators to a positive Hilbert space. |
| Transfer matrix | The Euclidean time-evolution operator, schematically $T\sim e^{-aH}$. | It extracts spectra and makes the Hamiltonian connection explicit. |
| Continuum limit | A limit in which the cutoff is removed while selected physical quantities are held fixed. | This is where universality and renormalization enter the definition. |
| Universality class | A set of regulators or microscopic systems flowing to the same long-distance QFT. | Different lattice actions can define the same continuum theory. |
| Global definition data | Boundary conditions, spin structure, gauge-group global form, line operators, and topological-sector sums. | These choices can change the theory even when the local Lagrangian density is the same. |
| Analytic continuation | The relation between Euclidean and Lorentzian correlators when the necessary spectral and positivity conditions hold. | It explains why Euclidean data can encode real-time QFT, but also why real-time observables are delicate. |

## Common confusions

**A Lagrangian is not automatically a nonperturbative definition.** The same local expression can support different global forms of the gauge group, different theta angles, different allowed line operators, different boundary conditions, and different continuum completions. A Lagrangian is often the beginning of a definition, not the end.

**A Euclidean path integral is not automatically a probability distribution.** Bosonic scalar theories with positive real $S_E$ often have positive weights after regularization. Fermions give determinants or Pfaffians, gauge theories require gauge quotienting or gauge fixing, theta terms are imaginary in Euclidean signature, and finite-density systems generally produce complex weights.

**Wick rotation is not a magic spell.** In perturbation theory one often rotates contours graph by graph. Nonperturbatively, one needs conditions such as reflection positivity, spectral positivity, locality, and suitable analyticity to reconstruct Lorentzian physics from Euclidean data.

**The cutoff is not merely an ugly artifact.** A cutoff makes the object finite enough to define. The physical QFT is recovered only after a continuum limit or an effective-field-theory interpretation is specified.

**The continuum limit is not just $a\to0$.** One must tune bare parameters with the cutoff so that renormalized masses, correlation lengths, couplings, or other physical observables remain meaningful. Sending the lattice spacing to zero at fixed bare parameters can give a trivial or divergent result.

**Finite volume is not always optional.** Degenerate vacua, tunneling, spontaneous symmetry breaking, topological sectors, and massless modes can depend sharply on the order in which infinite-time, infinite-volume, and zero-source limits are taken.

**Perturbatively equivalent theories may differ nonperturbatively.** Two descriptions can have identical local perturbation theory around one vacuum but differ by global sectors, instantons, line operators, or boundary conditions.

## Boundaries

This chapter does:

- explain what must be specified for a nonperturbative definition;
- introduce Euclidean correlation functions as nonperturbative observables;
- explain how lattice and finite-volume regulators make path integrals concrete;
- state why reflection positivity matters for reconstructing Lorentzian QFT;
- explain the continuum-limit logic behind renormalized QFT;
- mark the boundary between physics-facing definitions and theorem-first approaches.

This chapter does not try to do:

- a full course in constructive or algebraic QFT;
- a practical Monte Carlo programming tutorial;
- a complete treatment of the sign problem;
- a detailed proof of the Osterwalder–Schrader reconstruction theorem;
- a full treatment of chiral gauge theories, gauge fixing, BRST, or real-time contour integrals.

Those topics are developed later in this volume or in neighboring volumes on Mathematical and Rigorous QFT, Lattice Field Theory, Computational QFT and Tools, Gauge Theories, and Real-Time and Thermal QFT.

## Where to go next

Start with [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/). It gives the common language for the rest of the chapter.

Then continue to [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/), [Canonical Hamiltonian Definition](/nonperturbative-qft/nonperturbative-definitions/canonical-hamiltonian-definition/), and [Constructive QFT Preview](/nonperturbative-qft/nonperturbative-definitions/constructive-qft-preview/). Then read [Algebraic QFT Preview](/nonperturbative-qft/nonperturbative-definitions/algebraic-qft-preview/) and [Sign Problem Preview](/nonperturbative-qft/nonperturbative-definitions/sign-problem-preview/). Those pages explain how the formal integral becomes a family of regulated systems, how finite-volume limits are chosen, how a continuum QFT is extracted, why Euclidean data can reconstruct a positive-norm Hilbert space, how Hilbert-space and theorem-level definitions fit into the same nonperturbative picture, how local observable algebras define QFT intrinsically, and why complex weights obstruct probability-based sampling.

After this chapter, the natural physics route is [Vacuum Structure and Phases](/nonperturbative-qft/vacuum-structure-phases/), followed by [Order Parameters and Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/), Semiclassical Methods, Instantons and Theta Vacua, Confinement and Mass Gap, and Lattice Field Theory.

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, chapters on quantum-mechanical and field-theoretic path integrals, gauge-theory path integrals, Wilson loops, lattice theory, and confinement.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on path integrals, Schwinger–Dyson equations, Yang–Mills theory, and lattice gauge theories.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the Euclidean field-integral viewpoint, renormalization, critical phenomena, and the statistical-mechanics/QFT connection.

### Deeper references

- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” especially for the Wilsonian and statistical-mechanics viewpoint on continuum limits.
- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green’s Functions,” for the reconstruction viewpoint relating Euclidean correlators to Lorentzian QFT.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive Euclidean QFT and the measure-theoretic path-integral viewpoint.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling expansion, gauge fields, topology, and loop variables.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, and A. Altland and B. Simons, *Condensed Matter Field Theory*, for Euclidean field-theory definitions in statistical and condensed-matter settings.

## Version history

- **2026-06-26:** Linked the Order Parameters and Diagnostics chapter overview.
- **2026-06-26:** Added handoff link to Vacuum Structure and Phases.
- **2026-06-26:** Updated reading path with links to Algebraic QFT Preview and Sign Problem Preview.
- **2026-06-26:** Updated reading path with links to Canonical Hamiltonian Definition and Constructive QFT Preview.
- **2026-06-26:** Updated reading path with links to Finite-Volume Definition and Reflection Positivity.
- **2026-06-25:** Updated reading path with links to Lattice Regularization and Continuum Limit.
- **2026-06-25:** Initial polished chapter overview.
