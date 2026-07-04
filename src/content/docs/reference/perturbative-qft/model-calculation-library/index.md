---
title: "Model Calculation Library"
description: "Chapter overview for reusable worked calculations in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Schwartz 2014; Weinberg 1995, Vol. I."
topics:
  - model calculations
  - scattering amplitudes
  - cross sections
  - loop benchmarks
  - QED examples
canonicalTopics:
  - model-calculation-library
  - worked-scattering-calculations
  - perturbative-qft-benchmarks
researchStatus:
  established:
    - "The calculations in this chapter are textbook-standard benchmarks for perturbative amplitudes, cross sections, spin sums, Ward checks, and one-loop renormalization."
  active:
    - "The same benchmark calculations remain useful for testing symbolic tools, numerical workflows, precision corrections, detector definitions, and higher-order generalizations."
---

Model Calculation Library is the chapter in the Perturbative QFT and Scattering volume where the machinery is put to work in complete examples. Earlier chapters teach Feynman rules, amplitudes, phase space, loops, gauge checks, and renormalization as methods. This chapter shows how those methods behave when the calculation has a beginning, middle, and final observable.

The purpose is not to collect every known process. It is to provide canonical worked templates: a scalar contact interaction, a one-loop scalar correction, scalar exchange between fermions, and the first QED scattering processes that every perturbative QFT reader should be able to reproduce.

Read this chapter when you want to see all the factors line up: external states, vertices, propagators, spin sums, symmetry factors, flux factors, phase space, Ward identities, counterterms, and limiting cases. The little demons of QFT live in those factors. This chapter is where we make them show identification.

$$
\text{calculation}
\quad = \quad
\text{rules} + \text{kinematics} + \text{normalization} + \text{checks}.
$$

## Prerequisites

You should know the site conventions summarized in [Conventions and Notation](/perturbative-qft/conventions/), especially the normalization of amplitudes and phase space. You should also be comfortable with [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/), and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/).

For the QED examples, review [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) and [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/). For the one-loop scalar example, review [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [φ⁴ Theory: 2→2 Scattering](/perturbative-qft/model-calculation-library/phi-four-two-to-two-scattering/) | The cleanest complete route from one contact vertex to an invariant amplitude, identical-particle phase space, and a cross section. |
| 2 | [φ⁴ Theory: One-Loop Four-Point Amplitude](/perturbative-qft/model-calculation-library/phi-four-one-loop-four-point/) | The standard scalar one-loop benchmark: bubble diagrams, channel sums, threshold structure, and the coupling counterterm. |
| 3 | [Yukawa Exchange Scattering](/perturbative-qft/model-calculation-library/yukawa-exchange-scattering/) | A first fermionic scattering calculation with scalar exchange, spin averaging, and the nonrelativistic Yukawa potential. |
| 4 | [QED Electron–Muon Scattering](/perturbative-qft/model-calculation-library/qed-electron-muon-scattering/) | The canonical distinguishable-particle QED process: $t$-channel photon exchange, Ward checks, traces, and the Rutherford limit. |
| 5 | [QED Electron–Positron to Muons](/perturbative-qft/model-calculation-library/qed-electron-positron-to-muons/) | The canonical annihilation process: $s$-channel vector-current production, angular distributions, total cross section, and threshold behavior. |
| 6 | [QED Compton Scattering](/perturbative-qft/model-calculation-library/qed-compton-scattering/) | A first process where gauge invariance requires a sum of diagrams, leading to the Klein–Nishina formula and Thomson limit. |

After this path, you should be able to take a simple Lagrangian, identify the relevant diagrams, write $\mathcal M$, square or spin-average it when needed, and convert it into a physical rate or cross section with the correct normalization.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$S_{fi}=\delta_{fi}+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}$` | The invariant amplitude is the object that the model pages compute before phase-space integration. | Every scattering and decay calculation. |
| `$d\sigma=(\text{flux})^{-1}|\mathcal M|^2d\Pi_f$` | Cross sections are not amplitudes; they require flux, phase space, spin sums, and symmetry factors. | Scalar scattering, QED scattering, precision observables. |
| `spin sums` | Fermion amplitudes become traces only after summing final spins and averaging initial spins. | Yukawa exchange and QED processes. |
| `Ward replacement` | Replacing a photon polarization by its momentum is the fastest check of gauge invariance in QED tree calculations. | Electron–muon scattering, annihilation, Compton scattering. |
| `channel structure` | The same local rules produce $s$-, $t$-, and $u$-channel terms depending on the external assignment. | Crossing, scalar one-loop amplitudes, QED examples. |
| `counterterm plus loop` | A finite renormalized answer is obtained from the sum of loop diagrams and counterterm insertions, not from the bare loop alone. | One-loop scalar amplitudes and renormalized perturbation theory. |

## Common confusions

**A model calculation is not a bag of tricks.** Each example is meant to be a reusable template. The point is not only the final formula; it is the sequence of choices that turns a Lagrangian into an observable.

**The amplitude is not the cross section.** The amplitude knows about quantum interference and external kinematics. The cross section also knows about flux, final-state measure, spin and polarization averaging, identical-particle factors, and sometimes experimental cuts.

**Gauge checks are not optional decoration.** In QED examples with external photons, individual diagrams may fail a Ward check even when the sum passes. Dropping a diagram because it looks similar is the shortest route to a wrong answer with a confident haircut.

**Limits are part of the calculation.** Nonrelativistic limits, threshold limits, high-energy limits, and soft limits test whether the formula is physically sensible. A model page should not stop at algebra if a simple limiting case exposes the meaning of the result.

**One-loop examples are not just harder tree examples.** Loops introduce regulators, renormalization schemes, branch cuts, and counterterms. The one-loop scalar four-point page is a bridge from diagram rules to renormalized amplitudes.

## Boundaries

This chapter does:

- give complete, reproducible benchmark calculations;
- show how amplitudes become cross sections or limiting potentials;
- keep track of spin sums, symmetry factors, phase space, and Ward checks;
- connect tree-level examples to the first one-loop renormalized scalar amplitude.

This chapter does not try to do:

- derive the Feynman rules from scratch;
- replace the general chapters on phase space, loop integrals, or renormalization;
- give a full phenomenological treatment of QED or the Standard Model;
- include detector simulation, parton showers, hadronization, or experimental systematics;
- cover nonperturbative bound-state or confinement physics.

Those topics belong in the earlier method chapters of this volume, in Gauge Theories and the Standard Model, in Renormalization, RG, and EFT, in Precision Observables, and in Nonperturbative QFT.

## Where to go next

For more practice, use [Exercises](/perturbative-qft/exercises/) as the repair bench. The best capstone route is to reproduce the scalar and QED calculations without looking, then compare every factor of $2$, $2\pi$, $E_{\mathbf p}$, and spin average against the pages here.

For conceptual cleanup, go to [Common Confusions](/perturbative-qft/common-confusions/). For more realistic predictions, continue to [Precision Observables](/perturbative-qft/precision-observables/) and [Computational Perturbative QFT](/perturbative-qft/computational-perturbative-qft/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for scalar scattering, Feynman rules, cross sections, loops, QED scattering, and spinor technology.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for a physically careful route from perturbation theory to scattering, phase space, LSZ, and QED examples.
- Schwartz, *Quantum Field Theory and the Standard Model*, for direct connections between textbook amplitudes, QED cross sections, renormalization, jets, and Standard Model applications.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the structural S-matrix, cross-section, perturbative, and QED framework behind the model calculations.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for widely used worked examples in scalar theory, QED, loops, and renormalization.

## Version history

- **2026-06-14:** Initial standardized chapter overview for the Model Calculation Library.
