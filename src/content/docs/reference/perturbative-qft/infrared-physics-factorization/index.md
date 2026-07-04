---
title: "Infrared Physics and Factorization"
description: "Chapter overview for soft and collinear physics, infrared-safe observables, factorization, resummation, and SCET previews in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Weinberg, Vol. I and II; Srednicki; Schwartz; Sterman; Collins; SCET reviews"
topics:
  - infrared divergences
  - soft physics
  - collinear physics
  - factorization
  - resummation
  - jets
  - SCET
canonicalTopics:
  - infrared-physics
  - factorization
  - infrared-safe-observables
  - soft-collinear-factorization
researchStatus:
  established:
    - "The cancellation of infrared divergences in sufficiently inclusive observables and the factorization of hard, collinear, and soft physics are standard pillars of perturbative gauge theory."
  active:
    - "Precision factorization, resummation, jet substructure, power corrections, Glauber effects, and effective-theory formulations remain active research areas."
---

Infrared Physics and Factorization is the chapter in the Perturbative QFT and Scattering volume where massless particles stop being a harmless detail. Photons and gluons can be emitted with arbitrarily small energy, and massless particles can become arbitrarily collinear. Those limits make individual perturbative amplitudes singular even when the physical measurement is perfectly finite.

The chapter exists to explain how QFT turns that apparent disaster into structure. Soft and collinear divergences are not random infinities. They know about charges, color, Wilson-line behavior, asymptotic states, detector resolution, jet definitions, and the difference between exclusive and inclusive observables.

Read this chapter when you want to understand why measurable cross sections require infrared-safe definitions, why unresolved radiation must be summed over, and why precision predictions are naturally organized into hard, jet, and soft factors.

$$
\text{observable}
\sim
H\otimes J\otimes S
+
\text{power corrections}.
$$

## Prerequisites

You should know the scattering normalization fixed in [Conventions and Notation](/perturbative-qft/conventions/), the relation between amplitudes and probabilities from [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), and the phase-space language of [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/).

It is also helpful to know [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/) and [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/), because infrared physics is where gauge theory, phase space, and measurement definitions collide.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) | Why low-energy massless emission produces singular factors and why the singularity is universal. |
| 2 | [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) | Why nearly parallel massless particles produce logarithms or poles, and why masses and jet definitions matter. |
| 3 | [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/) | The first cancellation mechanism: unresolved soft photons cancel between virtual and real radiation. |
| 4 | [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) | The general lesson: sum over degenerate initial and final states to obtain finite inclusive quantities. |
| 5 | [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) | The approximation that turns energetic charged particles into straight Wilson-line sources for soft radiation. |
| 6 | [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) | The leading universal factorization of amplitudes with an extra low-energy photon. |
| 7 | [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) | The non-Abelian version, where soft emission carries color operators and ordering information. |
| 8 | [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) | How real detectors turn partons into jet observables that can be finite and perturbatively meaningful. |
| 9 | [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) | The hard–jet–soft organization of short-distance scattering with long-distance radiation. |
| 10 | [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/) | Why large logarithms must be summed and how evolution equations do the bookkeeping. |
| 11 | [SCET Preview](/perturbative-qft/infrared-physics-factorization/scet-preview/) | The effective-theory language of soft and collinear modes, power counting, and factorization. |

After this path, you should be able to tell whether an observable is infrared safe, identify its unresolved limits, and recognize the factorized pieces that enter a precision prediction.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Soft limit | A massless momentum $k$ becomes small compared with hard scales. | Soft theorems, eikonal approximation, real–virtual cancellation. |
| Collinear limit | Two massless momenta become nearly parallel. | Splitting functions, jets, parton showers, factorization. |
| Degenerate states | States that differ only by experimentally unresolved soft or collinear radiation. | Bloch–Nordsieck and KLN cancellation. |
| Infrared safety | An observable is insensitive to adding or splitting unresolved massless radiation. | Collider event shapes, jet algorithms, fixed-order predictions. |
| Eikonal factor | Soft radiation sees the direction and charge of a hard particle more than its microscopic details. | Wilson lines, soft factors, soft photon and gluon theorems. |
| Factorization | Short-distance, collinear, and soft physics can often be separated into universal functions. | Precision observables, PDFs, SCET, resummation. |
| Resummation | Large logarithms from hierarchies of scales are summed to all orders using evolution. | Jet physics, threshold observables, transverse-momentum spectra. |
| Power corrections | Factorization is usually leading-power; subleading effects can matter at high precision. | SCET, hadronization estimates, precision uncertainty budgets. |

## Common confusions

**A divergent amplitude does not automatically mean a divergent observable.** Individual fixed-multiplicity amplitudes can be infrared divergent because they ask an unphysical question with infinitely sharp radiation resolution. Physical observables must include what the measurement cannot distinguish.

**Soft and collinear are related but not identical.** Soft means small energy. Collinear means small angle. A gluon can be soft but not collinear, collinear but not soft, or both.

**Inclusive does not mean careless.** An inclusive observable is defined by a specific measurement function or sum over degenerate states. Vague averaging is not a substitute for an infrared-safe definition.

**Factorization is not the claim that long-distance physics vanishes.** It says long-distance physics can often be isolated into universal soft, jet, beam, or parton-distribution functions. The long-distance pieces may be nonperturbative even when the hard factor is perturbative.

**Resummation is not just adding more diagrams.** It reorganizes perturbation theory when fixed-order coefficients contain large logarithms. The aim is not higher order for its own sake, but a better expansion parameter.

## Boundaries

This chapter does:

- explain soft and collinear singularities as physical long-distance limits;
- show how inclusive sums and infrared-safe measurement functions remove unphysical divergences;
- introduce factorization, resummation, jets, soft theorems, eikonal physics, and SCET at the level needed for perturbative calculations.

This chapter does not try to do:

- the full nonperturbative definition of PDFs, fragmentation functions, or hadronization;
- a complete phenomenology course on collider observables;
- the complete SCET formalism with operator bases, Glauber modes, and subleading-power factorization;
- a full treatment of confinement, parton showers, or detector simulation.

Those topics belong in Gauge Theories and the Standard Model, Renormalization, RG, and EFT, Matter, Statistical Physics, and Quantum Information, Nonperturbative QFT, Precision Observables, and Computational QFT and Tools.

## Where to go next

For probability and cuts behind inclusive rates, continue to [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/). For practical collider predictions, go to [Precision Observables](/perturbative-qft/precision-observables/). For automated real-radiation and shower workflows, go to [Computational Perturbative QFT](/perturbative-qft/computational-perturbative-qft/).

For the conceptual RG and EFT meaning of factorization, continue later in Renormalization, RG, and EFT. For QCD as a physical gauge theory, continue later in Gauge Theories and the Standard Model.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for infrared divergences, scattering, and perturbative examples.
- Schwartz, *Quantum Field Theory and the Standard Model*, for infrared divergences, jets, factorization, and SCET-oriented explanations.
- Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for infrared effects, scattering theory, and the structural role of soft massless quanta.

### Deeper references

- Sterman, *An Introduction to Quantum Field Theory*, for soft and collinear physics from the viewpoint of perturbative QCD.
- Collins, *Foundations of Perturbative QCD*, for factorization, PDFs, and the logic behind hadron-collider predictions.
- Becher, Broggio, and Ferroglia, *Introduction to Soft-Collinear Effective Theory*, and Stewart's SCET lecture notes, for the effective-theory formulation.

## Version history

- **2026-06-14:** Initial standardized chapter overview for the infrared physics and factorization chapter.
