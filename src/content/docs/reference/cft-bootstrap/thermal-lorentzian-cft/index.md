---
title: "Thermal and Lorentzian CFT"
description: "Chapter overview for real-time, causal, and finite-temperature conformal field theory: thermal states, KMS relations, analytic continuation, spectral functions, chaos, and Lorentzian bootstrap ideas."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Kubo; Martin and Schwinger; Haag, Hugenholtz, and Winnink; Son and Starinets; Maldacena, Shenker, and Stanford; thermal CFT and Lorentzian bootstrap literature."
topics:
  - thermal CFT
  - Lorentzian CFT
  - KMS condition
  - real-time correlators
  - chaos
  - spectral functions
canonicalTopics:
  - thermal-and-lorentzian-cft
  - real-time-cft
  - finite-temperature-cft
researchStatus:
  established:
    - "Thermal density matrices, KMS relations, Euclidean thermal circles, spectral representations, retarded correlators, and analytic continuation are standard tools for finite-temperature QFT and CFT."
    - "Lorentzian analyticity, causality, Regge limits, and chaos bounds are central to modern conformal bootstrap and holographic CFT."
  active:
    - "Current research studies thermal bootstrap, real-time CFT data, hydrodynamic and quasinormal spectra, OTOCs, modular flow, chaos, transport, non-equilibrium dynamics, and Lorentzian inversion at finite temperature."
---

## Summary

**Thermal and Lorentzian CFT** is the chapter where conformal field theory stops living only in Euclidean signature and starts caring about time, causality, temperature, response, and chaos.

Euclidean CFT is excellent for defining correlation functions, OPEs, crossing equations, and reflection positivity. Lorentzian CFT asks sharper physical questions:

$$
\text{Which operators can influence which other operators?}
$$

$$
\text{How do correlators respond to perturbations in real time?}
$$

$$
\text{What does a CFT do at finite temperature?}
$$

$$
\text{How fast can quantum information scramble?}
$$

Thermal CFT adds a density matrix

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\operatorname{Tr}e^{-\beta H},
$$

and Lorentzian CFT adds operator orderings, commutators, retarded functions, Wightman functions, branch cuts, and causal analyticity.

The guiding slogan is

$$
\text{Euclidean CFT organizes data; Lorentzian CFT tests causality and dynamics}.
$$

This chapter develops the bridge between Euclidean correlators, real-time response, thermal physics, and modern Lorentzian bootstrap.

## Prerequisites

Before entering this chapter, read [Euclidean and Lorentzian CFT](/cft-bootstrap/what-is-a-cft/euclidean-and-lorentzian-cft/), [Cylinder Picture](/cft-bootstrap/operators-states-radial-quantization/cylinder-picture/), [Correlation Functions](/cft-bootstrap/correlation-functions/), and [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/).

For analytic-bootstrap connections, read [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), and [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/).

For holographic applications, read [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/) and [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/).

You should know density matrices, traces, commutators, analytic continuation, radial quantization, and the basic CFT operator-state correspondence.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Thermal States and KMS](/cft-bootstrap/thermal-lorentzian-cft/thermal-states-and-kms/) | The thermal density matrix, Euclidean time circle, KMS relation, and basic thermal correlators. |
| 2 | [Euclidean Thermal Circle and Matsubara Modes](/cft-bootstrap/thermal-lorentzian-cft/euclidean-thermal-circle-and-matsubara-modes/) | Why finite temperature means periodic imaginary time and discrete frequencies. |
| 3 | [Real-Time Correlators](/cft-bootstrap/thermal-lorentzian-cft/real-time-correlators/) | Wightman, time-ordered, retarded, advanced, and spectral correlators. |
| 4 | [Analytic Continuation and Branch Cuts](/cft-bootstrap/thermal-lorentzian-cft/analytic-continuation-and-branch-cuts/) | How Euclidean correlators continue to different Lorentzian orderings. |
| 5 | [Causality and Commutators](/cft-bootstrap/thermal-lorentzian-cft/causality-and-commutators/) | Microcausality, lightcones, support properties, and response. |
| 6 | [Thermal OPE and One-Point Functions](/cft-bootstrap/thermal-lorentzian-cft/thermal-ope-and-one-point-functions/) | How finite temperature breaks conformal symmetry down to spatial rotations and translations. |
| 7 | [Spectral Functions and Sum Rules](/cft-bootstrap/thermal-lorentzian-cft/spectral-functions-and-sum-rules/) | Positivity, dispersion relations, and frequency-space constraints. |
| 8 | [Hydrodynamic Poles and Transport](/cft-bootstrap/thermal-lorentzian-cft/hydrodynamic-poles-and-transport/) | Diffusion, sound, conductivity, viscosity, and long-time effective dynamics. |
| 9 | [OTOCs and Chaos](/cft-bootstrap/thermal-lorentzian-cft/otocs-and-chaos/) | Out-of-time-order correlators, scrambling, Lyapunov growth, and the chaos bound. |
| 10 | [Thermal Bootstrap](/cft-bootstrap/thermal-lorentzian-cft/thermal-bootstrap/) | Bootstrap constraints on finite-temperature one-point data and thermal correlators. |
| 11 | [Modular Flow and Relative Entropy](/cft-bootstrap/thermal-lorentzian-cft/modular-flow-and-relative-entropy/) | Modular Hamiltonians, relative entropy, and information-theoretic constraints. |
| 12 | [Non-Equilibrium and Quenches](/cft-bootstrap/thermal-lorentzian-cft/non-equilibrium-and-quenches/) | Time-dependent states, quenches, relaxation, and thermalization diagnostics. |

The first few pages build thermal QFT basics. The middle pages explain real-time analytic structure. The later pages connect to transport, chaos, modular theory, and bootstrap constraints.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| thermal density matrix | $\rho_\beta=e^{-\beta H}/Z$ | Defines equilibrium expectation values. |
| KMS condition | Thermal correlators are periodic or antiperiodic in imaginary time with operator-ordering shifts. | Encodes equilibrium in operator algebra form. |
| Euclidean thermal circle | Imaginary time has period $\beta$. | Turns finite temperature into geometry. |
| Matsubara frequency | Discrete Euclidean frequency. | Natural basis for thermal perturbation theory. |
| Wightman correlator | Real-time unordered correlator. | Basic spectral building block. |
| retarded correlator | Commutator with causal support. | Computes linear response. |
| spectral density | Difference of Wightman functions or imaginary part of retarded response. | Carries positivity and dispersion information. |
| branch cut | Nontrivial analytic continuation in time or cross-ratios. | Distinguishes Lorentzian orderings. |
| lightcone | Boundary of causal influence. | Organizes singularities and commutators. |
| OTOC | Out-of-time-order correlator. | Diagnoses scrambling and chaos. |
| Lyapunov exponent | Exponential growth rate in an OTOC regime. | Bounded by $2\pi/\beta$ under standard assumptions. |
| hydrodynamic pole | Long-wavelength pole fixed by conservation laws. | Encodes transport. |

These landmarks are the vocabulary of real-time CFT.

## Core themes

### Thermal equilibrium

Thermal equilibrium is not just a probability distribution. It is an analytic condition on correlators. The KMS relation says that moving an operator around the thermal circle changes its ordering:

$$
\langle A(t)B(0)\rangle_\beta
=
\langle B(0)A(t+i\beta)\rangle_\beta
$$

for bosonic operators, with fermionic signs when appropriate.

This is the seed from which Euclidean thermal circles, Matsubara frequencies, fluctuation-dissipation relations, and spectral positivity grow.

### Lorentzian causality

In Lorentzian signature, commutators know about causal structure. For local bosonic operators,

$$
[\mathcal O(x),\mathcal O(y)]=0
$$

at spacelike separation under standard microcausality assumptions.

Retarded correlators vanish outside the future lightcone, and this support property becomes analyticity in frequency space.

### Analytic continuation

Euclidean correlators do not become Lorentzian correlators by changing one symbol. One must specify operator ordering and an $i\epsilon$ prescription. Different orderings live on different analytic sheets.

That sheet structure is the source of double discontinuities, Regge limits, OTOCs, and chaos diagnostics.

### Thermal CFT is less symmetric than vacuum CFT

A CFT vacuum on flat space has the full conformal group. A thermal state chooses a rest frame and a scale $\beta$, so the symmetry is reduced. Correlators can depend on dimensionless combinations such as

$$
\omega/T,
\qquad
|\mathbf k|/T,
\qquad
Tx.
$$

Thermal one-point functions of operators may be nonzero when symmetries allow them.

## What this chapter is not

This chapter is not a general statistical-mechanics textbook. It uses thermal density matrices and partition functions only as needed for CFT and real-time QFT.

It is not the full story of hydrodynamics. Hydrodynamics appears here as the universal long-time, long-distance limit of thermal correlators.

It is not only about holography. Holographic black holes provide major examples, but KMS relations, retarded correlators, spectral functions, and thermal bootstrap apply far more broadly.

It is not only about chaos. Chaos is one dramatic Lorentzian application, but the chapter also covers ordinary response, causality, analytic continuation, and finite-temperature operator data.

## Common confusions

**Thermal does not mean non-conformal.** A CFT at finite temperature is still governed by a conformal operator algebra, but the thermal state breaks the full conformal symmetry by introducing a scale.

**Euclidean periodicity is not optional.** The KMS condition is the equilibrium statement behind the Euclidean thermal circle.

**Not every Euclidean continuation gives the same Lorentzian correlator.** Operator ordering determines the $i\epsilon$ prescription and analytic sheet.

**A retarded correlator is not a time-ordered correlator.** Retarded correlators compute causal response; time-ordered correlators are useful for perturbation theory.

**Spectral functions are not arbitrary imaginary parts.** They obey positivity, oddness or sign relations, and sum rules depending on the operators.

**Chaos is not just any exponential.** The chaos bound applies under specific assumptions and in a specific intermediate-time regime.

**Thermal one-point functions are CFT data in a state, not new operators.** The operator algebra remains the same; the state changes expectation values.

## Boundaries with other chapters

The [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) chapter develops Lorentzian inversion, double discontinuities, Regge behavior, and large-spin methods. This chapter uses those ideas for real-time and finite-temperature physics.

The [Holographic CFT](/cft-bootstrap/holographic-cft/) chapter treats thermal states when they become black holes, quasinormal modes, horizons, and entanglement wedges. This chapter gives the boundary thermal and Lorentzian language.

The [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) chapter focuses on torus partition functions and modular invariance, especially in two dimensions. This chapter treats KMS, real-time correlators, spectral functions, and thermal response more generally.

The [CFT Deformations and RG Flows](/cft-bootstrap/cft-deformations-rg-flows/) chapter studies moving away from fixed points by changing the Hamiltonian. A thermal state changes the density matrix, not the underlying CFT Hamiltonian.

## Where to go next

Start with [Thermal States and KMS](/cft-bootstrap/thermal-lorentzian-cft/thermal-states-and-kms/). Then read real-time correlators and analytic continuation before jumping to OTOCs or hydrodynamics.

For holographic examples, pair this chapter with [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/).

For Lorentzian bootstrap, return to [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/) and [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/).

For entropy and modular theory, read [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) and later modular-flow pages.

## References

- R. Kubo, “Statistical-Mechanical Theory of Irreversible Processes. I,” *Journal of the Physical Society of Japan* **12** (1957).
- P. C. Martin and J. Schwinger, “Theory of Many-Particle Systems. I,” *Physical Review* **115** (1959).
- R. Haag, N. M. Hugenholtz, and M. Winnink, “On the equilibrium states in quantum statistical mechanics,” *Communications in Mathematical Physics* **5** (1967).
- A. L. Fetter and J. D. Walecka, *Quantum Theory of Many-Particle Systems*, Dover, 2003.
- M. Le Bellac, *Thermal Field Theory*, Cambridge University Press, 1996.
- D. T. Son and A. O. Starinets, “Minkowski-space correlators in AdS/CFT correspondence,” *Journal of High Energy Physics* **2002**.
- J. Maldacena, S. H. Shenker, and D. Stanford, “A bound on chaos,” *Journal of High Energy Physics* **2016**.

## Version history

- 2026-07-02: Replaced scaffold with a polished chapter overview. Added prerequisites, reading path, landmarks, core themes, boundaries, common confusions, references, and version history.
