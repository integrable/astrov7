---
title: "Tree-Level Scattering"
description: "Chapter overview for tree-level amplitudes, Mandelstam kinematics, external-state factors, spin and polarization sums, helicity previews, and identical-particle effects in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman, scattering chapters; Srednicki, scattering amplitudes and spinor/gauge examples; Weinberg Vol. I, scattering theory and Feynman rules; Schwartz, QED and gluon amplitudes."
topics:
  - tree-level scattering
  - Mandelstam variables
  - invariant amplitudes
  - spin sums
  - polarization sums
  - helicity amplitudes
  - identical particles
canonicalTopics:
  - tree-level-scattering
  - mandelstam-variables
  - invariant-amplitudes
  - external-state-technology
  - identical-particle-scattering
researchStatus:
  established:
    - "Tree-level scattering amplitudes, Mandelstam kinematics, external spin and polarization sums, and identical-particle factors are standard perturbative QFT technology."
  active:
    - "Modern amplitude methods reorganize many tree-level results using on-shell recursion, color ordering, and soft limits; those developments are introduced later in this volume."
---

Tree-Level Scattering is the chapter in the Perturbative QFT and Scattering volume where diagrams first become explicit amplitudes. The goal is to make the passage from Feynman rules to invariant matrix elements feel mechanical, checked, and physically interpretable.

The chapter is intentionally conservative at first. It begins with Lorentz-invariant kinematics and scalar amplitudes, then adds spinors, photons, gluons, polarization sums, helicity language, and identical-particle bookkeeping. This order keeps the main lesson visible: a tree amplitude is a rational function of external momenta, masses, spin data, charges, and group-theory factors.

Read this chapter when you want to turn a Lagrangian interaction into a first scattering prediction, before phase-space integrals, loop corrections, infrared safety, or precision-observable machinery enter.

$$
\text{tree prediction}
\;=\;
\text{kinematics}
+\text{external states}
+\text{vertices and propagators}
+\text{symmetry checks}.
$$

## Prerequisites

You should know the qft.org [Conventions and Notation](/perturbative-qft/conventions/), the amplitude normalization in [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), and the relation between correlators and amplitudes from [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/).

For the diagrammatic input, review [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) and [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/). Readers entering the spinor and gauge examples should also be comfortable with spin sums, polarization vectors, and basic Lie-algebra generators.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) | The invariant kinematic language for $2\to2$ scattering and crossing. |
| 2 | [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) | The cleanest examples of contact terms, exchange diagrams, and channel sums. |
| 3 | [Yukawa Tree Amplitudes](/perturbative-qft/tree-level-scattering/yukawa-tree-amplitudes/) | The first spinor chains and scalar exchange between fermions. |
| 4 | [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) | Photon exchange, external spinors, Ward checks, and classic QED processes. |
| 5 | [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) | Gluon self-interactions, color factors, and gauge-theory tree structure. |
| 6 | [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) | How to sum or average over spin and polarization states without losing gauge invariance. |
| 7 | [Helicity Amplitudes Preview](/perturbative-qft/tree-level-scattering/helicity-amplitudes-preview/) | The bridge from covariant spin sums to compact helicity-specific amplitudes. |
| 8 | [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) | Exchange symmetry, interference, and final-state counting when particles are indistinguishable. |

After this path, you should be able to write and check basic tree amplitudes in scalar theories, Yukawa theory, QED, and Yang–Mills theory, and you should know which later chapter turns those amplitudes into cross sections and decay rates.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $s=(p_1+p_2)^2$, $t=(p_1-p_3)^2$, $u=(p_1-p_4)^2$ | The basic Lorentz-invariant variables for $2\to2$ scattering. | Channel identification, crossing, angular dependence. |
| $s+t+u=\sum_i m_i^2$ | The on-shell constraint for four external particles. | Reducing kinematic expressions and checking algebra. |
| $i\mathcal M$ | The amputated connected contribution inserted into the S-matrix convention. | Phase space, cross sections, decay rates. |
| `Tree graph` | A connected graph with no independent loop momentum. | Leading-order amplitudes, unitarity cuts, model calculations. |
| `Exchange diagram` | A propagator joins two interaction vertices, producing a channel denominator. | Scalar exchange, Yukawa forces, photon exchange, gluon exchange. |
| `External spinors and polarizations` | External wavefunctions encode the spin or helicity of asymptotic particles. | QED, Yukawa theory, gauge boson scattering, helicity amplitudes. |
| `Ward check` | Replacing a physical polarization by its momentum should annihilate a gauge-invariant amplitude. | Gauge-theory perturbation theory, BRST, infrared physics. |
| `Identical-particle factor` | Final-state phase space and amplitudes must respect indistinguishability. | Bose/Fermi exchange interference and cross-section normalization. |

The recurring pattern is simple: draw every allowed tree diagram, assign a factor to each line and vertex, attach external wavefunctions, enforce momentum conservation, and then simplify using on-shell kinematics and symmetry.

## Common confusions

**A tree amplitude is not yet a cross section.** The amplitude is a building block. A measurable rate also needs flux, phase space, spin and internal-state sums or averages, cuts, and sometimes detector definitions.

**The channel name is not just the picture.** The $s$-, $t$-, and $u$-channel labels refer to which invariant appears in the internal propagator. Drawings can be rotated or crossed; the invariant is the durable label.

**External legs are not internal propagators.** LSZ amputates external propagators and replaces them with external-state data. Forgetting this distinction is a reliable way to manufacture wrong factors.

**Gauge-dependent pieces are allowed inside a calculation.** Individual propagators and intermediate expressions may depend on gauge choice. The properly summed physical amplitude should pass the relevant Ward or Slavnov–Taylor checks.

**Identical particles create interference, not just division by a factorial.** The factorial prevents overcounting identical final states in phase space. The amplitude itself may also contain exchange-related diagrams whose interference is physical.

## Boundaries

This chapter does:

- introduce the Lorentz-invariant kinematics used in tree-level scattering;
- compute representative scalar, Yukawa, QED, and non-Abelian amplitudes;
- explain spin, polarization, color, helicity, and identical-particle bookkeeping at leading order.

This chapter does not try to do:

- derive the S-matrix from correlators or reconstruct LSZ;
- perform the phase-space integration that turns amplitudes into rates;
- compute loop corrections, UV divergences, or counterterm insertions;
- replace the full modern on-shell amplitudes program.

Those topics belong in [From Correlators to the S-Matrix](/perturbative-qft/from-correlators-to-s-matrix/), [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/), [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/), and [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/).

## Where to go next

If your goal is to compute measurable numbers, go next to [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/). That chapter explains how $\mathcal M$ becomes $d\sigma$ or $d\Gamma$.

If your goal is to improve a leading-order prediction, continue to [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/) and then [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/). If your goal is compact analytic amplitudes, continue to [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/).

## References

### Standard first pass

- Sidney Coleman, *Lectures on Quantum Field Theory*, for Mandelstam variables, phase-space preparation, LSZ, and early model scattering examples.
- Mark Srednicki, *Quantum Field Theory*, for scattering amplitudes, cross sections, spinor technology, QED, and spinor-helicity methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for QED examples, spin sums, gluon amplitudes, and the bridge to on-shell methods.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, for the S-matrix, relativistic normalization, spin, polarization, and general scattering structure.
- Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory*, for standard tree-level scattering calculations and gauge-theory examples.

## Version history

- **2026-06-14:** Replaced the placeholder with a standardized chapter overview, reading path, landmarks, boundaries, and references for Tree-Level Scattering.
