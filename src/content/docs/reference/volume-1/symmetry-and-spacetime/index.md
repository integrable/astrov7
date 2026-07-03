---
title: "Symmetry and Spacetime Structure"
description: "Chapter overview for symmetry and spacetime structure in the Foundations of QFT volume: Poincaré symmetry, Lorentz representations, spinors, internal symmetries, currents, Ward identities, discrete symmetries, spin–statistics, and CPT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, chs. 2 and 5; Coleman 2019, chs. 5–6 and 18–22; Srednicki 2007, §§2, 4, 22–24, and 33–40; Zee 2010, chs. I.10 and II.3–II.4."
topics:
  - symmetry
  - spacetime symmetry
  - Poincaré symmetry
  - Lorentz representations
  - spinors
  - currents
  - Ward identities
  - discrete symmetries
canonicalTopics:
  - symmetry-and-spacetime-structure
  - poincare-symmetry
  - lorentz-representations
  - noether-charges
  - ward-identities
  - spin-statistics
  - cpt-theorem
researchStatus:
  established:
    - "Poincaré symmetry, Lorentz representations, spinor fields, Noether currents, Ward identities, spin–statistics, and CPT are standard structural material in relativistic QFT."
  active:
    - "Modern symmetry language extends these foundations to generalized symmetries, defects, anomalies, boundary charges, and categorical structures in later volumes."
---

Symmetry and Spacetime Structure is the chapter in the Foundations of QFT volume where the kinematic and algebraic constraints of relativistic QFT are made explicit. Symmetry is not decoration. It organizes fields, states, currents, correlators, selection rules, and structural theorems.

The chapter exists because QFT uses two related but different symmetry languages at the same time. Particle states carry unitary representations of spacetime symmetry. Local fields carry finite-dimensional Lorentz representations and internal labels. Currents and Ward identities connect symmetry transformations to correlation functions.

Read this chapter when you want to understand why particles are labeled by mass and spin, why fields have scalar, vector, or spinor indices, how charges act on operators, and why locality plus relativity leads to spin–statistics and CPT constraints.

$$
\text{symmetry}
\quad\longrightarrow\quad
\text{representations, currents, Ward identities, and selection rules}.
$$

## Prerequisites

You should know [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) and [Stress Tensor](/foundations/classical-field-theory/stress-tensor/), because many charges begin as integrals of conserved currents. You should also know [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) and [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/) for the particle-state side of Poincaré symmetry.

For spinors, it helps to have read [Dirac Field](/foundations/free-fields/dirac-field/) and [Weyl and Majorana Fields](/foundations/free-fields/weyl-and-majorana-fields/). The conventions are fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Poincaré Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/) | Spacetime translations, Lorentz transformations, generators, and particle labels. |
| 2 | [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/) | The difference between finite-dimensional field representations and unitary particle-state representations. |
| 3 | [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/) | Why two-component spinors and dotted or undotted indices arise in four dimensions. |
| 4 | [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/) | Symmetries that act on field labels rather than spacetime points. |
| 5 | [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) | How conserved currents generate charges and transformations of operators. |
| 6 | [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) | The correlation-function form of symmetry constraints. |
| 7 | [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) | Charge conjugation, parity, time reversal, antiunitarity, and selection rules. |
| 8 | [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/) | The standard relation between integer or half-integer spin and Bose or Fermi statistics. |
| 9 | [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/) | The combined discrete symmetry forced by ordinary local relativistic QFT under standard assumptions. |

After this path, you should be able to distinguish spacetime and internal symmetries, field and particle representations, ordinary currents and Ward identities, and the structural roles of spin–statistics and CPT.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$x'^\mu=\Lambda^\mu{}_{\nu}x^\nu+a^\mu$` | A Poincaré transformation combines Lorentz transformations and translations. | Particle classification, stress tensor. |
| `$P^\mu` and `$M^{\mu\nu}$` | Momentum and Lorentz generators implement spacetime symmetry on states. | One-particle representations, Ward identities. |
| `$(j_L,j_R)$` | Finite-dimensional Lorentz field representations in four dimensions are labeled by two spins after complexification. | Scalar, spinor, vector, and tensor fields. |
| Noether charge `$Q_a=\int d^3\mathbf x\,j_a^0$` | A continuous global symmetry gives a conserved charge under suitable assumptions. | Currents, selection rules, Ward identities. |
| `$\Delta_a\mathcal O=i[Q_a,\mathcal O]$` | Charges act on operators by commutators, with grading and convention caveats when needed. | Internal symmetries, current algebra. |
| Ward identity | Current conservation inserted into correlators produces contact terms and constraints. | Gauge theory, anomalies, perturbation theory. |
| `spin–statistics` | Local relativistic QFT ties integer spin to bosons and half-integer spin to fermions. | Free fields, structural principles. |
| `CPT` | Locality, Lorentz covariance, positive spectrum, and Hilbert-space positivity imply a combined discrete symmetry. | Scattering, particle–antiparticle relations. |

## Common confusions

**A symmetry of the equations need not be a symmetry of the state.** The action or operator algebra may have a symmetry while a vacuum, thermal state, boundary condition, or background does not. Spontaneous symmetry breaking begins exactly with this distinction.

**Field representations are not the same as particle representations.** A vector potential has four components, a massive vector particle has three spin polarizations, and a photon has two helicities. Local fields are covariant bookkeeping objects; particle states live in the Hilbert space.

**Gauge redundancy is not an ordinary global symmetry.** Global symmetries can act on physical states and generate charges. Gauge transformations relate different descriptions of the same physical configuration, and their full treatment belongs to the gauge-field chapters.

**Ward identities are not merely diagram tricks.** In perturbation theory they become identities among diagrams. More generally, they are correlation-function statements about how symmetry acts on operator insertions.

**Discrete symmetries have no Noether currents.** Charge conjugation, parity, and time reversal are implemented by operators and selection rules rather than conserved local currents. Time reversal and CPT are antiunitary, so complex conjugation is part of the story.

## Boundaries

This chapter does:

- explain Poincaré symmetry and Lorentz representations;
- connect global symmetries to currents, charges, and Ward identities;
- introduce discrete symmetries, spin–statistics, and CPT as foundational constraints.

This chapter does not try to do:

- full gauge theory, BRST, or BV formalism;
- spontaneous symmetry breaking and Goldstone physics beyond necessary orientation;
- anomalies, generalized symmetries, defects, or topological terms;
- theorem-level axiomatic proofs of spin–statistics and CPT.

Those topics belong in later Foundations chapters and in the Symmetry, Anomalies, and Topology, Gauge Theories and the Standard Model, and Mathematical and Rigorous QFT volumes.

## Where to go next

For the next Foundations step, go to [Gauge Fields: First Principles](/foundations/gauge-fields-first-principles/), where symmetry language must be separated from gauge redundancy. For the structural assumptions behind spin–statistics and CPT, go to [Structural Principles of QFT](/foundations/structural-principles/).

For the full modern symmetry story, including anomalies, higher-form symmetries, defects, and topological terms, continue later to the Symmetry, Anomalies, and Topology volume.

## References

### Standard first pass

- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for Noether currents, charges, Lorentz representations, spinors, and discrete symmetries in lecture form.
- Srednicki, *Quantum Field Theory*, for Lorentz invariance, spin–statistics, continuous and discrete symmetries, and spinor technology.
- Zee, *Quantum Field Theory in a Nutshell*, for compact physical motivation for symmetry, spinors, and spin–statistics.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for particle representations, causal fields, Lorentz covariance, and structural constraints.
- Streater and Wightman, *PCT, Spin and Statistics, and All That*, for theorem-level perspective on locality, spin–statistics, and CPT.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
