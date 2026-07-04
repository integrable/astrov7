---
title: "Computational Perturbative QFT"
description: "Chapter overview for reproducible symbolic, diagrammatic, loop-reduction, phase-space, and benchmarking workflows in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007; Schwartz 2014; Ellis, Stirling, and Webber; Smirnov; Vermaseren; Hahn"
topics:
  - computational perturbative QFT
  - symbolic amplitudes
  - diagram generation
  - loop reduction
  - phase-space integration
  - reproducibility
canonicalTopics:
  - computational-perturbative-qft
  - reproducible-amplitude-workflows
  - diagram-and-loop-automation
  - validation-and-benchmarks
researchStatus:
  established:
    - "Symbolic algebra, diagram generation, loop reduction, numerical integration, and benchmark validation are standard components of modern perturbative QFT workflows."
  active:
    - "Computational perturbative QFT remains active because higher multiplicities, higher loops, numerical stability, automation, reproducibility, and public benchmarking continue to improve."
---

Computational Perturbative QFT is the chapter in the Perturbative QFT and Scattering volume where hand-derived formulas become reproducible calculations. It explains how to move from a Lagrangian and observable definition to checked amplitudes, reduced loop integrals, numerical predictions, and documented benchmarks.

The chapter is not a package catalog. Packages change; workflows endure. The goal is to teach the task structure behind computational perturbative QFT: canonicalize the algebra, generate the diagrams, assign the rules, reduce the integrals, integrate over phase space, test identities, compare benchmarks, and record enough metadata that someone else can reproduce the number.

Read this chapter when the calculation is too large to do reliably by hand, but too important to trust to a black box. The mood is practical but not casual: automation is only useful when every convention, approximation, and validation check is visible.

$$
\text{trustworthy computation}
=
\text{automation}
\,+\,
\text{cross-checks}
\,+\,
\text{reproducibility}.
$$

## Prerequisites

You should know the diagrammatic rules in [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/), the loop-integral language in [Loop Integral Technology](/perturbative-qft/loop-integral-technology/), and the observable-level checks in [Precision Observables](/perturbative-qft/precision-observables/).

For amplitude-heavy workflows, also review [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/), and [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Symbolic Amplitude Tools](/perturbative-qft/computational-perturbative-qft/symbolic-amplitude-tools/) | The algebraic tasks behind spin sums, traces, color factors, simplification, and amplitude manipulation. |
| 2 | [Diagram Generation Workflows](/perturbative-qft/computational-perturbative-qft/diagram-generation-workflows/) | How model files, external states, perturbative order, diagrams, and rules fit into an auditable pipeline. |
| 3 | [Loop Reduction Workflows](/perturbative-qft/computational-perturbative-qft/loop-reduction-workflows/) | How tensor reduction, IBP identities, master integrals, and consistency checks organize loop calculations. |
| 4 | [Numerical Phase-Space Integration](/perturbative-qft/computational-perturbative-qft/numerical-phase-space-integration/) | How multidimensional integration, singular regions, event weights, and errors enter numerical predictions. |
| 5 | [Reproducibility and Benchmarks](/perturbative-qft/computational-perturbative-qft/reproducibility-and-benchmarks/) | The validation culture: fixed inputs, independent checks, benchmark points, metadata, and documented failures. |

After this path, you should be able to sketch a reproducible perturbative calculation from model definition to benchmark table, and identify which checks protect each stage from silent errors.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `model file` | A machine-readable statement of fields, parameters, interactions, gauges, and counterterms. | Diagram generation, amplitude construction, benchmark reproducibility. |
| `canonicalization` | Rewriting algebraic expressions into stable forms so equality checks and simplification are meaningful. | Spinor traces, color algebra, tensor reduction, code comparison. |
| `Ward or gauge check` | Replacing a polarization by momentum, or varying gauge data, tests whether the implementation respects gauge structure. | QED and Yang–Mills workflows, helicity amplitudes, generated rules. |
| `IBP reduction` | Integration-by-parts identities reduce large families of loop integrals to master integrals. | Loop reduction workflows and master-integral calculations. |
| `phase-space mapping` | A change of variables designed to sample the important regions of final-state kinematics efficiently. | Numerical cross sections, fiducial predictions, event generation. |
| `benchmark point` | A specified kinematic and parameter point used to compare independent implementations. | Reproducibility, regression tests, public calculation tables. |
| `metadata` | The record of conventions, versions, inputs, schemes, cuts, seeds, and precision goals. | Long-term maintenance and trustworthy reuse of results. |

## Common confusions

**Software output is not a derivation.** A package can generate a correct-looking expression from an incorrect model file, wrong convention, missing factor, or incompatible scheme. The calculation becomes trustworthy only after independent checks survive.

**Automation does not remove convention dependence.** Metric signature, Fourier phases, coupling signs, gauge parameters, normalization of generators, and external-state conventions still matter. The computer is wonderfully fast at propagating a bad convention.

**Numerical precision is not physical accuracy.** A number with many digits can still omit a relevant correction, use inconsistent inputs, or integrate the wrong observable. Numerical errors, perturbative uncertainties, and modeling uncertainties are different things.

**Diagram generation and amplitude generation are not the same task.** A diagram list is a combinatorial object. A usable amplitude requires rules, signs, symmetry factors, external-state conventions, color and spin treatment, and simplification choices.

**Reproducibility is not bureaucracy.** It is part of the physics result. If a prediction cannot be regenerated with stated inputs and checks, it is fragile even if the final number is plausible.

## Boundaries

This chapter does:

- explain package-independent computational workflows for perturbative calculations;
- identify validation checks that protect symbolic and numerical stages;
- connect diagram generation, amplitude manipulation, loop reduction, and phase-space integration;
- emphasize reproducible inputs, benchmark points, and maintenance records;
- prepare readers to use external tools without treating them as oracles.

This chapter does not try to do:

- provide installation manuals for every package;
- maintain a complete software registry;
- replace package documentation or source-code tutorials;
- cover lattice field theory, tensor networks, numerical bootstrap, or holographic PDEs beyond perturbative-scattering interfaces;
- certify any external tool as correct for all conventions and models.

Those broader computational topics belong in a dedicated Computational QFT and Tools volume. This chapter stays focused on perturbative amplitudes, loop calculations, phase space, and precision-prediction workflows.

## Where to go next

For physics examples to test workflows against, go to the [Model Calculation Library](/perturbative-qft/model-calculation-library/). For observable-level uncertainty accounting, go to [Precision Observables](/perturbative-qft/precision-observables/).

For the analytic machinery behind loop reduction, return to [Loop Integral Technology](/perturbative-qft/loop-integral-technology/). For modern tree and loop amplitude inputs, continue in [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for clear perturbative examples and convention-sensitive Feynman-rule calculations.
- Schwartz, *Quantum Field Theory and the Standard Model*, for modern scattering, QED, QCD, spinor-helicity, jets, and precision-oriented calculations.
- Ellis, Stirling, and Webber, *QCD and Collider Physics*, for collider-facing computational structure and observable-level QCD practice.

### Deeper references

- Smirnov, *Analytic Tools for Feynman Integrals*, for loop-integral reduction and evaluation methods.
- Vermaseren, *New Features of FORM*, and related FORM documentation, for large symbolic manipulation in high-energy calculations.
- Hahn, *Generating Feynman diagrams and amplitudes with FeynArts 3*, for a classic automated diagram-and-amplitude workflow.

## Version history

- **2026-06-14:** Initial standardized chapter overview for the Computational Perturbative QFT chapter.
