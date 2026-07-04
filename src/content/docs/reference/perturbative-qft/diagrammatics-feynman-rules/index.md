---
title: "Diagrammatics and Feynman Rules"
description: "Chapter overview for perturbative expansion, Wick contractions, generating functionals, symmetry factors, vertices, propagators, connected diagrams, 1PI diagrams, and counterterms in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, perturbation theory and Feynman rules; Coleman 2019, Wick diagrams, Feynman diagrams, functional integrals, and 1PI functions; Weinberg 1995, Vol. I, Feynman rules and path integrals; Zee 2010, Feynman diagrams and rule summaries."
topics:
  - perturbative expansion
  - Wick theorem
  - Feynman rules
  - generating functionals
  - symmetry factors
  - connected diagrams
  - 1PI diagrams
  - counterterms
canonicalTopics:
  - diagrammatics-feynman-rules
  - perturbative-expansion
  - wick-contractions
  - momentum-space-feynman-rules
  - connected-and-1pi-diagrams
researchStatus:
  established:
    - "The Dyson–Wick expansion, functional derivation of diagrams, graph symmetry factors, momentum-space rules, and 1PI organization are standard perturbative QFT technology."
  active:
    - "Modern calculations automate and reorganize diagrammatic perturbation theory, especially in gauge theories and multiloop amplitudes, but the basic diagrammatic dictionary remains the common starting point."
---

Diagrammatics and Feynman Rules is the chapter in the Perturbative QFT and Scattering volume where interactions become a calculational language. The chapter explains how perturbative expansions, Wick contractions, source derivatives, propagators, vertices, symmetry factors, connected pieces, and one-particle-irreducible pieces fit together.

The chapter exists because Feynman diagrams are not decorative pictures. They are compressed algebra: each line, vertex, loop momentum, external leg, sign, and symmetry factor represents a specific part of the Dyson–Wick or source-functional expansion.

Read this chapter when you want to turn a Lagrangian into expressions for correlators and amplitudes without losing track of what is being computed.

$$
\text{interaction term}+\text{Wick contraction}
\quad\longrightarrow\quad
\text{vertex}+\text{propagator}.
$$

## Prerequisites

You should know the qft.org [Conventions and Normalizations](/foundations/conventions-and-normalizations/), the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), and the basic free-field [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/). The most useful Foundations prerequisites are [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), and [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/).

Readers who are mainly interested in scattering should pair this chapter with [From Correlators to the S-Matrix](/perturbative-qft/from-correlators-to-s-matrix/), because the same diagrams can represent different objects before and after amputation.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/) | The expansion of interacting QFT around a solvable free theory. |
| 2 | [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/) | The contraction combinatorics that turn free-field products into sums of propagators. |
| 3 | [Generating Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/) | The source-functional route to full, connected, and 1PI diagrams. |
| 4 | [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) | The practical counting rules that prevent overcounting identical Wick contractions. |
| 5 | [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) | The translation from position-space contractions to propagators, vertex factors, delta functions, and loop integrals. |
| 6 | [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/) | How quadratic and interaction terms in a Lagrangian become the local building blocks of diagrams. |
| 7 | [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) | How full correlators split into connected pieces, vacuum bubbles, and products of independent processes. |
| 8 | [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) | The proper vertices and self-energy blocks from which connected diagrams are assembled. |
| 9 | [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) | How local counterterm vertices enter diagrams and prepare the transition to renormalized perturbation theory. |

After this path, you should be able to read a simple Lagrangian, identify propagators and vertices, write the corresponding diagrammatic expansion, and state whether the result is a full correlator, connected correlator, amputated object, or 1PI kernel.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Dyson expansion | Interactions enter through a time-ordered exponential or its source-functional analogue. | Wick contractions, perturbative amplitudes, vacuum-bubble cancellation. |
| Wick contraction | A pair of free fields inside a time-ordered product becomes a free Feynman propagator. | Propagator lines, scalar examples, loop diagrams. |
| $Z[J]$, $W[J]$, and $\Gamma[\varphi]$ | Full, connected, and 1PI information are organized by different generating functionals. | Connected diagrams, effective action, self-energies. |
| Vertex factor | A local interaction term contributes a local rule with coupling constants, indices, and momenta. | Tree amplitudes, loop corrections, counterterms. |
| Symmetry factor | Identical contractions that give the same graph must be counted once with the correct divisor. | Vacuum bubbles, tadpoles, loop diagrams. |
| Momentum conservation at vertices | Fourier transforming local interactions produces delta functions enforcing energy–momentum conservation. | Momentum-space rules, loop momentum counting. |
| Connected versus 1PI | Connected diagrams describe full correlated responses; 1PI diagrams are proper building blocks. | Self-energy resummation, effective action, renormalization. |
| Counterterm vertex | Renormalization adds local interaction insertions with their own Feynman rules. | Renormalized perturbation theory, loop subtraction, scheme dependence. |

## Common confusions

**Diagrams are not literal particle histories.** Internal lines are propagators, not observed particles flying through a detector. A diagram is first a term in an expansion; its particle-language interpretation depends on the observable and kinematic regime.

**The same picture can compute different objects.** A diagram with external legs can represent a contribution to a Green function, an amputated correlator, or an S-matrix amplitude depending on the rules being applied. Always ask what object the diagram is supposed to compute.

**Symmetry factors are not optional decorations.** A graph may visually appear only once while many Wick contractions produce it. The symmetry factor is the leftover combinatoric information after the obvious factorials have canceled.

**Connected does not mean one-particle irreducible.** A connected graph may fall apart after one internal line is cut. A 1PI graph remains connected under that operation and plays a different role in the effective action and self-energy resummation.

**Counterterms are ordinary local vertices.** They are not mysterious after-the-fact erasers. They are local insertions required by the renormalized definition of the theory and are counted in perturbation theory like any other vertex.

## Boundaries

This chapter does:

- explain how perturbation theory produces diagrams;
- connect Wick contractions, source derivatives, propagators, and vertices;
- give scalar momentum-space rules and their diagrammatic meaning;
- organize full, connected, disconnected, and 1PI diagrams;
- introduce counterterm diagrams as the diagrammatic entrance to renormalized perturbation theory.

This chapter does not try to do:

- prove LSZ reduction or define the S-matrix, which belongs in [From Correlators to the S-Matrix](/perturbative-qft/from-correlators-to-s-matrix/);
- compute a catalog of physical amplitudes, which begins in [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/);
- derive cross-section and decay-rate formulas, which belongs in [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/);
- develop the technology of loop integration, which belongs in [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/) and [Loop Integral Technology](/perturbative-qft/loop-integral-technology/);
- give the full gauge-theory rule set, which belongs in [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/).

## Where to go next

For scattering normalization and LSZ, go to [From Correlators to the S-Matrix](/perturbative-qft/from-correlators-to-s-matrix/). For actual tree-level calculations, continue to [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/).

For loop calculations, go to [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/), then [Loop Integral Technology](/perturbative-qft/loop-integral-technology/). For renormalized diagrams and counterterms in earnest, continue to [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for scalar perturbation theory, Feynman rules, symmetry factors, all-orders perturbation theory, and 1PI organization.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for the operator and Wick-diagram route from Dyson expansion to Feynman diagrams.
- Schwartz, *Quantum Field Theory and the Standard Model*, for Lagrangian, Hamiltonian, and path-integral derivations of Feynman rules with many worked examples.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the covariant derivation of Feynman rules, path-integral formulation, and structural treatment of off-shell amplitudes.
- Zee, *Quantum Field Theory in a Nutshell*, for a compact, physically intuitive introduction to diagrammatic thinking and rule summaries.

## Version history

- **2026-06-14:** Replaced scaffold with standardized chapter overview, reading path, landmarks, boundaries, and references.
