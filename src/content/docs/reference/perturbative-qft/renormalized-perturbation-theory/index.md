---
title: "Renormalized Perturbation Theory"
description: "Chapter overview for bare parameters, counterterms, renormalization conditions, schemes, wavefunction residues, and finite amplitudes in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki; Coleman; Weinberg Vol. I; Schwartz; Zinn-Justin"
topics:
  - renormalized perturbation theory
  - counterterms
  - renormalization schemes
  - wavefunction renormalization
  - renormalized amplitudes
canonicalTopics:
  - renormalized-perturbation-theory
  - counterterm-lagrangian
  - renormalization-schemes
  - finite-amplitudes
researchStatus:
  established:
    - "Perturbative renormalization by local counterterms, with scheme-dependent intermediate parameters and scheme-independent physical predictions, is textbook-standard for renormalizable QFTs and EFTs."
  active:
    - "At high orders and in realistic gauge theories, organizing finite remainders, scheme choices, matching conventions, and uncertainty estimates remains an active computational and phenomenological discipline."
---

Renormalized Perturbation Theory is the chapter in the Perturbative QFT and Scattering volume where regulated diagrams become finite predictions. Loop integrals may contain UV divergences, but local QFT tells us that those divergences can be absorbed into local counterterms when the theory is organized consistently.

The chapter exists because “subtract the infinity” is not a calculation. A renormalized calculation must say which parameters are bare, which are renormalized, which counterterms are inserted, which conditions or scheme define the finite parts, and how the final amplitude is independent of arbitrary bookkeeping choices.

Read this chapter when you already know how a loop integral diverges and want to understand how a perturbative prediction survives the regulator-removal limit.

$$
\text{regulated diagrams}+\text{counterterms}+\text{renormalization conditions}
\quad\longrightarrow\quad
\text{finite amplitudes}.
$$

## Prerequisites

You should know the qft.org [Conventions and Notation](/perturbative-qft/conventions/), the basic [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), and the diagrammatic role of [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/).

Readers who are rusty on propagator corrections should first skim [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) and [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/). The broader conceptual RG and EFT interpretation belongs in the Renormalization, RG, and EFT volume.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/) | The dictionary between regulator-dependent bare symbols and finite parameters used in perturbative predictions. |
| 2 | [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) | The split of the bare Lagrangian into renormalized terms plus local counterterm interactions. |
| 3 | [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/) | The operational rules that define masses, couplings, and residues from chosen Green functions or amplitudes. |
| 4 | [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/) | The scheme where particle masses and residues are fixed directly at physical poles. |
| 5 | [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) | The scheme where dimensional-regularization poles are subtracted systematically, leaving scale-dependent parameters. |
| 6 | [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/) | The relation between field normalization, pole residues, external legs, and LSZ factors. |
| 7 | [Mass Renormalization](/perturbative-qft/renormalized-perturbation-theory/mass-renormalization/) | How self-energies shift pole locations and how counterterms define physical or scheme masses. |
| 8 | [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) | How vertex corrections and counterterms define a renormalized interaction strength. |
| 9 | [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) | How loop diagrams, counterterm diagrams, external residues, and finite remainders combine into a prediction. |
| 10 | [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/) | The first bridge from renormalized perturbation theory to RG equations and scale dependence. |

After this path, you should be able to read a one-loop renormalized amplitude and identify which parts are physical, which parts define a scheme, and which parts are artifacts of the regulator.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$\mathcal L_0=\mathcal L_{\rm ren}+\mathcal L_{\rm ct}$` | The bare Lagrangian is rewritten as a renormalized calculation plus counterterm interactions. | Counterterm diagrams, renormalized amplitudes. |
| `bare parameters` | Regulator-dependent quantities held fixed while renormalized quantities are defined. | Minimal subtraction, coupling renormalization. |
| `renormalization condition` | A rule that fixes the finite part of a parameter or field normalization. | On-shell scheme, mass renormalization. |
| `scheme dependence` | Renormalized parameters and finite remainders depend on convention, while observables do not. | Scale variation, EFT matching, precision predictions. |
| `pole mass and residue` | The physical one-particle pole and its residue control external-leg normalization. | LSZ, wavefunction renormalization. |
| `$\mu\,d\mathcal A/d\mu=0$` | A physical amplitude cannot depend on the arbitrary renormalization scale once all orders are included. | Callan–Symanzik equations, RG improvement. |
| `finite remainder` | The part of a loop amplitude left after UV subtraction and external normalization. | Fixed-order predictions, loop-integral technology. |

## Common confusions

**Bare parameters are not measured numbers.** Bare masses and couplings depend on the regulator and generally do not have a direct experimental meaning. Measured quantities are defined through renormalization conditions or matched observables.

**Counterterms are not optional patches.** Counterterms are part of the perturbative definition of the theory once a regulator and renormalization prescription are chosen. They are local because UV divergences arise from short-distance behavior.

**Minimal subtraction is not less physical than the on-shell scheme.** The on-shell scheme makes some physical interpretation immediate, while minimal subtraction often makes RG structure and high-order calculations cleaner. The choice changes intermediate parameters, not the exact observable.

**Wavefunction renormalization is not only a field redefinition.** For Green functions it is a normalization convention, but for scattering it also controls the residue factors that LSZ extracts from external one-particle poles.

**A finite one-loop answer is not automatically a physical prediction.** One must specify the observable, external-state normalization, scheme, scale choice, and which perturbative order is being used. Otherwise two correct finite formulas may simply be written in different coordinates.

## Boundaries

This chapter does:

- explain how bare and renormalized parameters are related in perturbative calculations;
- organize counterterm Lagrangians and counterterm diagrams;
- compare on-shell and minimal-subtraction logic;
- show how self-energies, residues, masses, couplings, and amplitudes are renormalized;
- preview the Callan–Symanzik equation as the handoff from finite amplitudes to RG structure.

This chapter does not try to do:

- develop Wilsonian coarse graining or EFT as a full conceptual framework;
- prove all-order renormalizability in general theories;
- compute full Standard Model renormalization constants;
- replace loop-integral technology or automated high-order calculation methods;
- treat nonperturbative renormalization, lattice schemes, or constructive definitions.

Those topics belong in the Renormalization, RG, and EFT volume, the Gauge Theories and the Standard Model volume, Nonperturbative QFT, and Computational QFT and Tools.

## Where to go next

For the conceptual scale-dependence story, continue to the Renormalization, RG, and EFT volume. For physical gauge-theory applications, go next to [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/), especially the pages on Ward identities and gauge-parameter independence.

For observable predictions, move to [Precision Observables](/perturbative-qft/precision-observables/) after reading [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/). For explicit scalar practice, use the [Model Calculation Library](/perturbative-qft/model-calculation-library/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for a calculation-first route through loop corrections, counterterms, and renormalized perturbation theory.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for physical explanations of counterterms, propagator renormalization, and scattering normalization.
- Schwartz, *Quantum Field Theory and the Standard Model*, for a modern graduate treatment of counterterms, minimal subtraction, on-shell conditions, and QED examples.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the general structural treatment of renormalization, fields, and S-matrix perturbation theory.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for a systematic functional and RG-oriented treatment of renormalization.
- Collins, *Renormalization*, for a detailed account of perturbative renormalization and factorization logic.

## Version history

- **2026-06-14:** Initial standardized chapter overview for the Renormalized Perturbation Theory chapter.
