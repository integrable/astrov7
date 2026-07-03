---
title: "Classical Field Theory"
description: "Chapter overview for the classical field-theory layer of the Foundations of QFT volume: actions, equations, symmetries, stress tensors, Hamiltonian structure, constraints, and normal modes."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman 2019, chs. 4–6; Srednicki 2007, §§1–3, 12, and 22; Schwartz 2014, ch. 3; Weinberg 1995, Vol. I, ch. 7."
topics:
  - classical field theory
  - action principle
  - Euler–Lagrange equations
  - Noether theorem
  - stress tensor
  - Hamiltonian field theory
  - constraints
  - normal modes
canonicalTopics:
  - classical-field-theory
  - action-principle
  - noether-currents
  - stress-tensor
  - normal-mode-decomposition
researchStatus:
  established:
    - "The variational, Hamiltonian, Noether-current, stress-tensor, constraint, and normal-mode machinery of classical fields is standard prerequisite material for QFT."
  active:
    - "Boundaries, gauge constraints, defects, gravity couplings, and nontrivial backgrounds require later chapters and volumes for their full quantum interpretation."
---

Classical Field Theory is the chapter in the Foundations of QFT volume where fields first become dynamical objects. Before a field is an operator or a path-integral variable, it is a spacetime-dependent degree of freedom governed by an action.

This chapter exists to make the objects used later feel inevitable: Euler–Lagrange equations, Noether currents, stress tensors, canonical momenta, constraints, and normal modes. These are not decorative preliminaries. They are the classical grammar inherited by canonical quantization, path integrals, perturbation theory, gauge theory, and curved-spacetime QFT.

Read this chapter when you want to know what data a field theory has before quantization. By the end, you should be able to start from a local Lagrangian density, derive the field equations, identify conserved currents and energy–momentum, recognize constraints, and see why a free field decomposes into oscillator modes.

$$
\text{quadratic classical field theory}
\quad\longrightarrow\quad
\text{normal modes}
\quad\longrightarrow\quad
\text{oscillators waiting to be quantized}.
$$

## Prerequisites

You should know ordinary Lagrangian mechanics, Hamiltonian mechanics, special relativity, integration by parts, and Fourier modes. The site conventions are fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/), especially the mostly-minus metric and natural units $\hbar=c=1$.

Readers who are rusty on variational calculus can still begin here. The first page introduces field variations and boundary terms slowly enough to repair the needed background.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) | Fields as spacetime degrees of freedom, local actions, Euler–Lagrange equations, and boundary terms. |
| 2 | [Scalar Fields](/foundations/classical-field-theory/scalar-fields/) | The simplest real and complex fields, the Klein–Gordon equation, potentials, $U(1)$ charge, and mass dimensions. |
| 3 | [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) | The route from continuous symmetries to conserved currents, charges, and improvements. |
| 4 | [Stress Tensor](/foundations/classical-field-theory/stress-tensor/) | Energy–momentum conservation, canonical and Hilbert stress tensors, improvements, and trace information. |
| 5 | [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) | Canonical momenta, Hamiltonian density, functional derivatives, and equal-time Poisson brackets. |
| 6 | [Constraints](/foundations/classical-field-theory/constraints/) | Singular Legendre transforms, first- and second-class constraints, Dirac brackets, and the Maxwell–Proca contrast. |
| 7 | [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) | Small fluctuations, quadratic actions, Fourier modes, zero modes, and stability. |

After this path, you should be able to explain why a free scalar field becomes a tower of harmonic oscillators and why gauge fields require constraint care before quantization.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$S[\phi]=\int d^4x\,\mathcal L$` | Local dynamics are encoded in an action functional. | Path integrals, stationary phase, Feynman rules. |
| Euler–Lagrange equations | Varying the action gives field equations plus boundary terms. | Classical solutions, propagator inverses, saddle points. |
| Noether current `$j^\mu$` | A continuous global symmetry gives a conserved current on shell. | Ward identities, charges, anomalies. |
| Stress tensor `$T^{\mu\nu}$` | Translations lead to energy–momentum conservation and local energy flow. | Poincaré generators, CFT, gravity coupling. |
| Equal-time Poisson bracket | Classical phase space has local canonical brackets on a time slice. | Equal-time commutators and canonical quantization. |
| Constraint | Not every field component is necessarily an independent physical degree of freedom. | Gauge fields, BRST, reduced phase space. |
| Normal modes | Quadratic fluctuations diagonalize into independent oscillators when the background permits it. | Free fields, particles, propagators. |

## Common confusions

**A field is not a particle position.** In field theory, $\mathbf x$ labels where the field degree of freedom lives. It is not the position coordinate of one particle moving through space.

**Boundary terms are not automatically irrelevant.** They often vanish in a first derivation because boundary variations are fixed. In later chapters they control charges, gauge transformations, edge modes, topological terms, and gravitational actions.

**Noether currents are not unique.** Improvement terms can change the current or stress tensor without changing the conserved charge under suitable boundary conditions. This is a feature, not a mistake.

**Gauge symmetry is not ordinary physical symmetry.** Global symmetries can move a physical state to another physical state. Gauge transformations usually change the description of the same physical state, unless boundary behavior makes them physical.

**Normal modes depend on the background.** Plane waves are natural around translation-invariant vacua. Around solitons, defects, curved backgrounds, finite boxes, or time-dependent solutions, the mode problem changes.

## Boundaries

This chapter does:

- introduce fields, local actions, and Euler–Lagrange equations;
- explain Noether currents, charges, stress tensors, and improvements;
- build the Hamiltonian and constraint language needed for canonical quantization;
- show how quadratic field theories decompose into normal modes.

This chapter does not try to do:

- quantum commutators, Fock space, or particle creation;
- full path-integral quantization;
- full gauge fixing, BRST, ghosts, or non-Abelian gauge theory;
- anomalies, boundaries, edge modes, or curved-spacetime stress tensors in depth.

Those topics belong later in the Foundations of QFT volume and in the Gauge Theories, Symmetry, Nonperturbative QFT, and Spacetime volumes.

## Where to go next

For the operator route, go next to [Relativistic Particles and Fields](/foundations/relativistic-particles-and-fields/) and then [Canonical Quantization](/foundations/canonical-quantization/). The state-space and oscillator language there turns the classical normal-mode story into creation and annihilation operators.

For the path-integral route, the same action returns in [Quantum Mechanical Path Integral](/foundations/path-integral-formalism/quantum-mechanical-path-integral/) and [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/). For gauge redundancy, continue later with [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/).

## References

### Standard first pass

- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for the route from many-particle quantum mechanics to classical fields, currents, and charges.
- Srednicki, *Quantum Field Theory*, for spin-zero fields, canonical quantization, dimensional analysis, and continuous symmetries.
- Schwartz, *Quantum Field Theory and the Standard Model*, ch. 3, for a compact classical-field-theory introduction.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the Lagrangian and Hamiltonian foundations of QFT.
- Dirac, *Lectures on Quantum Mechanics*, for constrained Hamiltonian systems.
- Henneaux and Teitelboim, *Quantization of Gauge Systems*, for a systematic treatment of constraints and gauge systems.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
