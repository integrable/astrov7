---
title: "Phase Space, Cross Sections, and Decays"
description: "Chapter overview for turning invariant amplitudes into decay rates, scattering cross sections, resonant approximations, inclusive observables, and total rates in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, cross sections and decay rates; Coleman 2019, scattering applications and optical theorem; Weinberg 1995, Vol. I, rates and phase space; Schwartz 2014, cross sections, decay rates, and infrared-safe observables."
topics:
  - phase space
  - cross sections
  - decay rates
  - flux factors
  - inclusive observables
  - optical theorem
canonicalTopics:
  - lorentz-invariant-phase-space
  - cross-section-normalization
  - decay-rate-normalization
  - two-body-phase-space
  - inclusive-observables
researchStatus:
  established:
    - "Lorentz-invariant phase space, flux factors, differential cross sections, decay rates, and total-rate unitarity relations are standard parts of S-matrix perturbation theory for stable asymptotic particles."
  active:
    - "Precision predictions refine these formulas with finite-width schemes, infrared-safe measurement functions, PDFs, jet algorithms, detector cuts, and higher-order corrections."
---

Phase Space, Cross Sections, and Decays is the chapter in the Perturbative QFT and Scattering volume where amplitudes become measurable rates. The previous chapters explain how to obtain $\mathcal M$; this chapter explains what must be multiplied, integrated, averaged, divided, or summed before the answer is a physical decay width or scattering cross section.

The chapter exists because the slogan “probability is amplitude squared” is dangerously incomplete in relativistic QFT. The actual formula also needs relativistic state normalization, Lorentz-invariant final-state density, initial flux, identical-particle factors, spin and internal-state averages, and a statement of what final states the measurement includes.

Read this chapter when you have an invariant amplitude and want to know how it becomes $d\Gamma$, $d\sigma$, a branching ratio, a total inclusive rate, or a resonant approximation.

$$
\text{observable rate}
=
\text{initial normalization}^{-1}
\times |\mathcal M|^2
\times \text{final-state phase space}
\times \text{measurement definition}.
$$

## Prerequisites

You should know the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), the amplitude normalization in [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), and the basic amplitude calculations in [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/). The most useful specific preparation is [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), and [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/).

A reader who wants only tree-level $2\to2$ formulas can start here after reading the first two pages of Tree-Level Scattering. A reader interested in infrared-safe observables should also keep [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) in view.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) | The invariant final-state density of states for scattering and decays. |
| 2 | [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/) | The invariant initial-state normalization that converts transition probability into cross section. |
| 3 | [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) | The closed-form two-body measure and the Källén-function geometry behind it. |
| 4 | [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) | The practical formulas for $d\sigma/d\Omega$ and $d\sigma/dt$ from $|\mathcal M|^2$. |
| 5 | [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/) | Differential and total widths, partial widths, branching ratios, and two-body decay formulas. |
| 6 | [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) | How an isolated resonance factorizes into production, propagation, and decay at leading order in $\Gamma/M$. |
| 7 | [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) | How sums over experimentally indistinguishable final states produce finite, physical rates. |
| 8 | [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/) | How total inclusive rates are related to imaginary parts of forward amplitudes. |

After this path, you should be able to convert a stable-particle invariant amplitude into a differential cross section or decay rate, identify the required symmetry and averaging factors, and recognize when an observable must be defined inclusively.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $d\Pi_n(P)$ | The Lorentz-invariant density of $n$ on-shell final particles with total momentum $P$. | Decay rates, cross sections, cut diagrams. |
| Flux factor | The invariant normalization of the two-particle initial state. | Scattering cross sections and partonic rates. |
| Källén function | The compact expression controlling two-body momentum and thresholds. | Two-body decays, $2\to2$ scattering, threshold behavior. |
| $d\Gamma$ | Decay probability per unit time, obtained from $|\mathcal M|^2$ and final-state phase space. | Partial widths, branching ratios, unstable particles. |
| $d\sigma$ | Scattering event rate divided by incident flux. | Collider observables, model calculations, precision predictions. |
| Identical final states | Phase space must divide by permutations of indistinguishable final particles. | Decays, scattering, inclusive event definitions. |
| Narrow-width approximation | An isolated resonance can factorize when $\Gamma/M$ is small and backgrounds vary slowly. | Resonance phenomenology, unstable-particle calculations. |
| Inclusive sum | Physical rates in theories with massless radiation require summing over unresolved final states. | KLN theorem, jets, precision observables. |

## Common confusions

**Phase space is not dynamics.** Phase space knows about kinematics, masses, state normalization, and allowed final momenta. The dynamics sits in $\mathcal M$ or in a matrix element of an operator.

**Flux is not just ordinary relative speed.** In relativistic scattering the useful expression is the invariant flux factor. In special frames it can look like a relative velocity times normalization factors, but the invariant form is the safe one.

**A total cross section is not obtained by dropping angles casually.** One must integrate the differential cross section over the correct physical region, include identical-particle factors, respect cuts or measurement functions, and average or sum over the stated spin and internal states.

**A decay width is not a mass by convention.** In natural units a width has dimensions of energy because it is an inverse lifetime. It becomes a lifetime through $\tau=1/\Gamma$ only after the total width has been computed.

**Inclusive does not mean vague.** An inclusive observable is defined by an explicit sum or measurement weight over final states. That definition is what allows real and virtual infrared singularities to cancel in physical quantities.

## Boundaries

This chapter does:

- derive and use Lorentz-invariant phase-space measures;
- explain flux factors, two-body phase space, differential cross sections, and decay rates;
- introduce resonant factorization through the narrow-width approximation;
- explain inclusive observables and the total-rate use of the optical theorem.

This chapter does not try to do:

- compute the underlying amplitudes, which belongs in [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/) and later loop chapters;
- develop full loop regularization or subtraction, which belongs in [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/);
- prove the full KLN theorem or factorization, which belongs in [Infrared Physics and Factorization](/perturbative-qft/infrared-physics-factorization/);
- treat PDFs, scale variation, fiducial cuts, and parton showers in detail, which belongs in [Precision Observables](/perturbative-qft/precision-observables/);
- handle finite-volume scattering, unstable-particle gauge-invariant pole schemes, or non-vacuum media beyond the preview level.

## Where to go next

For higher-order corrections to the same rates, go to [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/) and [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/). For massless radiation, continue to [Infrared Physics and Factorization](/perturbative-qft/infrared-physics-factorization/).

For research-facing predictions, go to [Precision Observables](/perturbative-qft/precision-observables/). For worked end-to-end examples using these formulas, use the [Model Calculation Library](/perturbative-qft/model-calculation-library/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for cross sections, decay rates, phase space, resonances, and infrared-safe inclusive logic.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for scattering applications, phase-space density, decay formulas, and the optical theorem.
- Schwartz, *Quantum Field Theory and the Standard Model*, for modern worked examples connecting amplitudes, phase space, infrared divergences, and collider observables.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the general S-matrix normalization, Lorentz-invariant phase space, and rates.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for classic cross-section and decay-rate examples in scalar theory, QED, and gauge theory.

## Version history

- **2026-06-14:** Initial standardized chapter overview with reading path, landmarks, boundaries, and references.
