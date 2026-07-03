---
title: "Free Relativistic Fields"
description: "Chapter overview for the free scalar, spinor, and vector fields that supply the basic particles, propagators, polarizations, and local building blocks of QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, parts I–III; Coleman 2019, chs. 3–4, 19–21, and 26–31; Weinberg 1995, Vol. I, chs. 2 and 5–8; Zee 2010, Parts I–II."
topics:
  - free fields
  - scalar fields
  - spinor fields
  - gauge fields
  - propagators
  - polarizations
canonicalTopics:
  - free-relativistic-fields
  - free-field-propagators
  - free-field-mode-expansions
  - spinor-bilinears
  - photon-polarizations
researchStatus:
  established:
    - "Free scalar, spinor, Maxwell, and Proca fields are textbook-standard examples of relativistic QFT."
    - "Their mode expansions, propagators, spin sums, and polarization sums form the reference layer for perturbation theory."
  active:
    - "Interacting, gauge-fixed, curved-spacetime, thermal, and nonperturbative uses of these fields require later chapters and volumes."
---

Free Relativistic Fields is the chapter in the Foundations of QFT volume where the abstract language of states, operators, and quantization becomes concrete. The basic free scalar, spinor, Maxwell, and Proca fields are collected here as reusable reference objects.

The chapter is not claiming that nature is free. It identifies the linearized building blocks around which perturbation theory, asymptotic particle states, propagators, spin sums, polarization sums, and model calculations are organized.

Read this chapter when you want to know what the Klein–Gordon, Dirac, Weyl, Majorana, Maxwell, and Proca fields are before interactions complicate the story. The governing idea is:

$$
\text{free field}
=
\text{relativistic particle representation plus locality plus a quadratic action}.
$$

## Prerequisites

You should know [Relativistic Particles and Fields](/foundations/relativistic-particles-and-fields/), especially one-particle states, antiparticles, Fock space, and relativistic normalization. You should also know [Canonical Quantization](/foundations/canonical-quantization/), especially oscillator modes, equal-time brackets, scalar quantization, normal ordering, and fermionic anticommutators.

For the classical starting point, review [Scalar Fields](/foundations/classical-field-theory/scalar-fields/), [Constraints](/foundations/classical-field-theory/constraints/), and [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/). The conventions are fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) | The scalar prototype: equations, mode expansions, charged scalars, commutators, and scalar propagators. |
| 2 | [Dirac Field](/foundations/free-fields/dirac-field/) | The massive spin-one-half field, gamma matrices, plane-wave spinors, anticommutators, spin sums, charge, and propagator. |
| 3 | [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/) | Chiral and self-conjugate fermions, two-component notation, and Dirac versus Majorana mass terms. |
| 4 | [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) | The covariant fermion building blocks used for currents, masses, Yukawa couplings, and symmetry classification. |
| 5 | [Maxwell Field](/foundations/free-fields/maxwell-field/) | The free massless spin-one gauge field, gauge redundancy, photon helicities, and gauge-fixed propagators. |
| 6 | [Proca Field](/foundations/free-fields/proca-field/) | The massive spin-one comparison case with a transversality constraint and three physical polarizations. |
| 7 | [Polarizations](/foundations/free-fields/polarizations/) | A compact dictionary of spin labels, spin sums, helicities, and polarization projectors. |
| 8 | [Free Field Summary](/foundations/free-fields/free-field-summary/) | Tables for quick lookup once the individual entries have a derivation and interpretation. |

After this path, you should be able to identify the equation of motion, mode expansion, propagator, statistics, and physical one-particle content of each basic free field.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Klein–Gordon operator `$\Box+m^2$` | The scalar kinetic operator and prototype denominator for relativistic propagators. | Scalar interactions, loop integrals, path integrals. |
| `$D_F(p)=i/(p^2-m^2+i\epsilon)$` | The scalar Feynman propagator in qft.org conventions. | Wick expansion, diagrams, spectral representation. |
| Dirac operator `$i\gamma^\mu\partial_\mu-m$` | The first-order spinor kinetic operator whose square gives the Klein–Gordon operator. | Fermion propagators, QED, Yukawa theory. |
| Spin sums | Sums over unobserved spin states produce compact numerator factors such as $\gamma^\mu p_\mu+m$. | Scattering, decay rates, loop traces. |
| Gauge redundancy `$A_\mu\sim A_\mu+\partial_\mu\alpha$` | The Maxwell potential contains descriptive redundancy, leaving two photon helicities. | Gauge fixing, Ward identities, BRST. |
| Proca transversality `$\partial_\mu A^\mu=0$` | A massive vector has no gauge redundancy but obeys a constraint that leaves three polarizations. | Massive vector bosons, Higgs mechanism previews. |
| Polarization projectors | External spin and vector labels become projectors when summed. | Cross sections, amplitudes, gauge checks. |

## Common confusions

**Free does not mean unphysical.** Free fields are the local linear building blocks used to define asymptotic states, Gaussian kernels, and propagators. Interacting QFT usually starts by perturbing around them.

**Field components are not physical degrees of freedom.** A Dirac spinor has four complex components, but its particle content is organized by spin and particle–antiparticle labels. A Maxwell potential has four spacetime components, but only two physical photon helicities.

**Antiparticle terms are not decorative.** The creation terms multiplying $e^{+ip\cdot x}$ are required for locality, charge conjugation, and positive-energy antiparticle sectors. Removing them breaks the relativistic field story.

**Gauge-field propagators are not observables.** A photon propagator depends on gauge fixing. Physical amplitudes become gauge independent only after gauge invariance, current conservation, or BRST structure is used correctly.

**The Dirac numerator is not an individual spinor.** The numerator $\gamma^\mu p_\mu+m$ comes from a spin sum or operator inverse. It should not be confused with a particular external wavefunction.

## Boundaries

This chapter does:

- collect the basic free scalar, spinor, Maxwell, and Proca fields;
- state their equations, mode expansions, propagators, and physical state counts;
- explain spinor bilinears, spin sums, helicities, and polarization sums;
- prepare the objects that become internal lines, external states, and Gaussian kernels.

This chapter does not try to do:

- interacting perturbation theory or full Feynman rules;
- full gauge quantization, ghosts, BRST, or non-Abelian Yang–Mills theory;
- renormalization, bound states, confinement, or curved-spacetime particle creation;
- theorem-level construction of operator-valued distributions.

Those topics belong in later Foundations chapters and in the Perturbative QFT, Gauge Theories, Renormalization, Nonperturbative QFT, Spacetime, and Mathematical and Rigorous QFT volumes.

## Where to go next

For two-point functions and causal structure, continue to [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), and [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/).

For interactions, go later to [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) and [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/). For the gauge-field story beyond Maxwell, continue with [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) and [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for the spin-zero, spin-one-half, and spin-one sequence in particle-physics conventions.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for scalar, spinor, and vector free fields with strong operator intuition.
- Zee, *Quantum Field Theory in a Nutshell*, for a physics-first treatment of fields, particles, spinors, and gauge fields.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the representation-theoretic and causal construction of free relativistic fields.
- Streater and Wightman, *PCT, Spin and Statistics, and All That*, for the structural role of locality, statistics, and fields as distributions.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
