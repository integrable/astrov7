---
title: "Loop Expansion and Regularization"
description: "Chapter overview for loop order, ultraviolet power counting, regularization schemes, self-energies, vertex corrections, vacuum bubbles, and counterterm insertions in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman, perturbation theory and renormalization chapters; Srednicki, loop corrections and renormalization; Weinberg Vol. I, Feynman rules and renormalization; Schwartz, regularization and renormalized perturbation theory."
topics:
  - loop expansion
  - ultraviolet divergences
  - regularization
  - dimensional regularization
  - self-energy diagrams
  - vertex corrections
  - counterterms
canonicalTopics:
  - loop-expansion
  - regularization
  - superficial-degree-of-divergence
  - self-energy-diagrams
  - counterterm-insertions
researchStatus:
  established:
    - "Loop counting, ultraviolet power counting, regularization, one-loop self-energy and vertex corrections, vacuum bubbles, and counterterm insertions are standard ingredients of perturbative QFT."
  active:
    - "Modern calculations refine the same logic with multi-loop integral reduction, infrared subtraction, gauge-invariant schemes, automated workflows, and EFT matching."
---

Loop Expansion and Regularization is the chapter in the Perturbative QFT and Scattering volume where perturbation theory stops being only a sum of tree diagrams. Loops introduce integrations over momenta not fixed by external kinematics, and those integrations are the first place where ultraviolet divergences become unavoidable rather than decorative.

The chapter exists to separate three ideas that students often meet at the same time: loop order is graph topology, divergence is large-momentum behavior, and regularization is a temporary way of making intermediate expressions well defined. Renormalization comes next; this chapter prepares the objects that renormalization acts on.

Read this chapter when you know how to write tree amplitudes and want to understand what changes at one loop: new momentum integrals, self-energies, vertex corrections, vacuum bubbles, regulator dependence, and local counterterm insertions.

$$
\text{loop calculation}
\quad=\quad
\text{graph topology}
+\text{unfixed momentum integrals}
+\text{regularization}
+\text{local counterterms}.
$$

## Prerequisites

You should know the qft.org [Conventions and Notation](/perturbative-qft/conventions/), the diagrammatic dictionary in [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/), and the amplitude normalization from [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/).

The most useful preparation is [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), and [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/). Readers who want the observable meaning of loop corrections should also keep [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) in view.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) | The graph-theoretic and semiclassical meaning of loop order. |
| 2 | [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/) | The first diagnostic for ultraviolet behavior before cancellations and subtractions. |
| 3 | [Cutoff Regularization](/perturbative-qft/loop-expansion-regularization/cutoff-regularization/) | A direct regulator that exposes powers and logarithms of a high-momentum scale. |
| 4 | [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) | The analytic-continuation regulator used in most modern perturbative calculations. |
| 5 | [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) | The canonical one-loop scalar integral, including its ultraviolet pole and threshold cut. |
| 6 | [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) | Two-point loop insertions, propagator corrections, pole shifts, and residues. |
| 7 | [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) | Loop corrections to interaction vertices and the first examples of corrected couplings. |
| 8 | [Vacuum Bubbles](/perturbative-qft/loop-expansion-regularization/vacuum-bubbles/) | Vacuum diagrams, their exponentiation, and why they cancel from normalized correlators. |
| 9 | [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) | How local counterterms enter perturbation theory as diagrammatic vertices. |

After this path, you should be able to identify the loop order and superficial ultraviolet behavior of a diagram, choose a regulator, recognize basic one-loop structures, and see why renormalized perturbation theory needs local counterterms.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $L=I-V+1$ | The number of independent loop momenta in a connected graph. | Loop expansion, integral families, unitarity cuts. |
| $\int d^d\ell/(2\pi)^d$ | The regulated loop-momentum integration measure. | Dimensional regularization, one-loop bubbles, master integrals. |
| Superficial degree of divergence | The large-momentum power count before cancellations, subtractions, and symmetries are used. | Renormalizability tests and counterterm classification. |
| Regulator | A temporary modification that makes divergent expressions calculable. | Cutoff schemes, dimensional regularization, renormalized amplitudes. |
| $1/\epsilon$ pole | The dimensional-regularization signal of a logarithmic ultraviolet divergence. | Minimal subtraction and beta functions. |
| Self-energy | A one-particle-irreducible two-point insertion correcting a propagator. | Mass renormalization, wavefunction renormalization, pole schemes. |
| Vertex correction | A loop correction to an interaction vertex or form factor. | Coupling renormalization, Ward identities, precision observables. |
| Vacuum bubble | A diagram with no external insertions. | Vacuum energy, effective action, normalization of correlators. |
| Counterterm insertion | A local vertex introduced to cancel regulator dependence order by order. | Renormalized perturbation theory and scheme dependence. |

The basic loop count is topological, but the physical interpretation is not. A loop graph can correct a pole, modify a coupling, generate a branch cut, shift a vacuum energy, or cancel regulator dependence against a counterterm.

## Common confusions

**A loop is not a literal particle orbit.** A loop means an independent momentum integration in a term of the perturbative expansion. Internal lines are propagators, not observed trajectories.

**A divergence is not automatically a physical infinity.** A divergent integral signals that the unregulated expression is incomplete. The physical question is whether regulator dependence can be absorbed into local parameters and whether the final observable is well defined.

**Regularization is not renormalization.** Regularization makes expressions meaningful. Renormalization relates bare parameters, counterterms, schemes, and measured quantities.

**Power counting is only the first diagnosis.** Symmetries, gauge cancellations, equations of motion, numerator algebra, and subtractions can improve or change the actual divergence structure.

**Dimensional regularization does not show every kind of cutoff sensitivity.** In particular, scaleless integrals vanish and power divergences are not displayed as powers of a cutoff. That is a feature, not magic.

**Vacuum bubbles are not meaningless.** They cancel from normalized ordinary correlators in flat-space scattering calculations, but they matter for vacuum energy, thermodynamics, effective actions, and gravity.

## Boundaries

This chapter does:

- explain loop order, loop momentum, and the first ultraviolet divergences;
- introduce cutoff and dimensional regularization as practical regulators;
- derive and interpret basic one-loop bubble, self-energy, and vertex structures;
- explain vacuum bubbles and counterterm insertions as diagrammatic objects.

This chapter does not try to do:

- develop the full interpretation of renormalization and RG flow, which belongs in [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/) and the site-wide Renormalization, RG, and EFT volume;
- teach the full technology of integral reduction and evaluation, which belongs in [Loop Integral Technology](/perturbative-qft/loop-integral-technology/);
- handle gauge-theory Slavnov–Taylor structure, which belongs in [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/);
- treat infrared singularities, which belong in [Infrared Physics and Factorization](/perturbative-qft/infrared-physics-factorization/);
- build full collider predictions, which belongs in [Precision Observables](/perturbative-qft/precision-observables/).

## Where to go next

For the mathematical technology needed to evaluate more complicated loop integrals, continue to [Loop Integral Technology](/perturbative-qft/loop-integral-technology/). For the physical interpretation of counterterms, schemes, and renormalized amplitudes, continue to [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/).

For gauge-theory loops, go to [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/). For cuts and imaginary parts, go to [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/). For worked examples, use the [Model Calculation Library](/perturbative-qft/model-calculation-library/).

## References

### Standard first pass

- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for the transition from Wick diagrams to Feynman diagrams, early counterterms, self-energies, and the logic of perturbative renormalization.
- Srednicki, *Quantum Field Theory*, for loop corrections to propagators and vertices, perturbation theory to all orders, and the first renormalization examples.
- Schwartz, *Quantum Field Theory and the Standard Model*, for modern treatments of regularization, vacuum polarization, mass renormalization, and infrared-aware loop calculations.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the general Feynman-rule derivation, renormalization structure, and scheme-aware organization of perturbation theory.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, loop expansions, ultraviolet divergences, dimensional regularization, and the relation to statistical field theory.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for standard one-loop examples and counterterm practice.

## Version history

- **2026-06-14:** Initial standardized chapter overview with reading path, landmarks, boundaries, and references.
