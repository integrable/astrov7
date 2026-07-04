---
title: "Unitarity, Analyticity, and Dispersion"
description: "Chapter overview for optical theorems, cuts, discontinuities, dispersion relations, partial-wave unitarity, threshold behavior, positivity bounds, and S-matrix bootstrap previews in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Weinberg, Vol. I; Srednicki; Schwartz; Eden et al.; Martin; modern amplitudes reviews"
topics:
  - unitarity
  - analyticity
  - dispersion relations
  - cuts
  - optical theorem
  - partial waves
  - positivity bounds
  - S-matrix bootstrap
canonicalTopics:
  - unitarity-analyticity-dispersion
  - optical-theorem
  - branch-cuts
  - dispersion-relations
  - partial-wave-unitarity
researchStatus:
  established:
    - "The optical theorem, Cutkosky rules, branch cuts, dispersion relations, threshold behavior, and partial-wave unitarity are standard consequences of perturbative QFT together with probability conservation and analyticity assumptions."
  active:
    - "Modern positivity bounds, nonperturbative S-matrix bootstrap methods, analytic constraints on EFTs, and amplitudes beyond standard assumptions remain active research areas."
---

Unitarity, Analyticity, and Dispersion is the chapter in the Perturbative QFT and Scattering volume where scattering amplitudes become constrained functions, not just sums of diagrams. Probability conservation gives unitarity. Locality, causality, and spectrum conditions give analytic structure. Together they explain why amplitudes have cuts, thresholds, imaginary parts, dispersion relations, and positivity properties.

The chapter exists because perturbative calculations are most useful when we know how to check them. A loop integral with a branch cut is not just a complicated function; its discontinuity is tied to physical intermediate states. A forward amplitude is not just another matrix element; its imaginary part measures an inclusive rate.

Read this chapter when you want to understand how probability and causality leave fingerprints on scattering amplitudes, and why the same ideas support loop checks, effective-field-theory bounds, and modern S-matrix bootstrap programs.

$$
S^\dagger S=1
\quad\Longrightarrow\quad
2\,\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,\left|\mathcal M_{i\to X}\right|^2
$$

schematically, with the precise normalization fixed on the relevant pages.

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), and [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/).

For calculations with discontinuities, review [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) and [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/). A little complex analysis helps; the chapter keeps the physics assumptions visible rather than hiding them behind contour folklore.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) | The inclusive probability statement encoded in the imaginary part of a forward amplitude. |
| 2 | [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) | The diagrammatic rule that turns discontinuities of loop graphs into on-shell intermediate states. |
| 3 | [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) | The analytic language for thresholds, multi-valued functions, cuts, and physical sheets. |
| 4 | [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/) | How real parts of amplitudes can be reconstructed from imaginary parts, up to subtraction data. |
| 5 | [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/) | The angular-momentum form of unitarity and the resulting bounds on amplitudes. |
| 6 | [Threshold Behavior](/perturbative-qft/unitarity-analyticity-dispersion/threshold-behavior/) | How phase space and angular momentum control amplitude behavior near production thresholds. |
| 7 | [Positivity Bounds Preview](/perturbative-qft/unitarity-analyticity-dispersion/positivity-bounds-preview/) | The EFT-facing use of analyticity, crossing, and unitarity to constrain Wilson coefficients. |
| 8 | [S-Matrix Bootstrap Preview](/perturbative-qft/unitarity-analyticity-dispersion/s-matrix-bootstrap-preview/) | The modern program of carving out allowed amplitudes from consistency conditions. |

After this path, you should be able to recognize which part of an amplitude is fixed by on-shell states, where dispersion assumptions enter, and how unitarity becomes a practical diagnostic.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$S^\dagger S=1$` | Total probability is conserved. | Optical theorem, partial-wave bounds, cutting equations. |
| Completeness of intermediate states | Insert a sum over physical states between amplitudes. | Inclusive rates, cuts, Cutkosky rules. |
| Discontinuity | The jump of an analytic function across a branch cut. | Loop integrals, spectral densities, dispersion relations. |
| Physical threshold | The energy where a new on-shell intermediate state can be produced. | Branch cuts, phase space, threshold behavior. |
| Cut propagators | Cut internal lines are placed on shell by delta functions, with the correct phase-space measure. | Cutkosky rules, generalized unitarity, optical theorem checks. |
| Dispersion relation | Analyticity relates values of an amplitude to integrals over its discontinuities. | Positivity bounds, sum rules, EFT constraints. |
| Partial-wave unitarity | Each angular-momentum channel obeys its own unitarity condition. | Resonances, perturbative unitarity bounds, S-matrix bootstrap. |
| Positivity bounds | Under extra assumptions, low-energy expansion coefficients satisfy sign constraints. | EFT consistency, UV-completion diagnostics, frontier problems. |

## Common confusions

**The optical theorem is inclusive.** It does not say that one particular exclusive channel equals the imaginary part of the forward amplitude. It says that the imaginary part knows about the sum over all allowed intermediate states.

**A cut diagram is not merely a diagram with a line drawn through it.** The cut represents a precise replacement by on-shell phase-space factors and lower-order amplitudes. The drawing is a mnemonic for a unitarity equation.

**Analyticity is not automatic for every expression you write.** It depends on locality, causality, spectrum assumptions, regulator choices, and which variables are being continued. Off-shell Green functions, gauge-dependent objects, and approximations may have different analytic behavior from physical amplitudes.

**Dispersion relations need subtraction information.** If an amplitude grows too fast at large complex energy, an unsubtracted dispersion relation is not justified. Subtractions encode low-energy constants or boundary data not determined by the discontinuity alone.

**Positivity bounds are powerful but assumption-dependent.** They usually rely on analyticity, crossing, unitarity, polynomial boundedness, and a mass gap or controlled infrared treatment. If one of those assumptions fails, the conclusion may need modification.

## Boundaries

This chapter does:

- derive and use the optical theorem as a practical unitarity statement;
- explain cuts, discontinuities, thresholds, partial waves, and dispersion relations for perturbative amplitudes;
- preview positivity bounds and S-matrix bootstrap ideas as modern applications of analytic constraints.

This chapter does not try to do:

- a theorem-first construction of the analytic S-matrix from axioms;
- a complete nonperturbative bootstrap program;
- the full conformal bootstrap;
- detailed gravitational, cosmological, or massless-S-matrix subtleties;
- a complete classification of resonances or hadronic scattering data.

Those topics belong in Mathematical and Rigorous QFT, CFT and Bootstrap, Spacetime, Gravity, and Holography, Nonperturbative QFT, Gauge Theories and the Standard Model, and Research Frontiers and Open Problems.

## Where to go next

For amplitude construction methods that use cuts as input, continue to [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/). For the loop-integral side of discontinuities, go back to [Loop Integral Technology](/perturbative-qft/loop-integral-technology/). For rate computations, return to [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/).

For rigorous analytic structure, continue later in Mathematical and Rigorous QFT. For EFT consistency constraints, continue later in Renormalization, RG, and EFT.

## References

### Standard first pass

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for scattering theory, unitarity, analyticity, and partial waves.
- Srednicki, *Quantum Field Theory*, for the perturbative optical theorem, cuts, loop thresholds, and scattering examples.
- Schwartz, *Quantum Field Theory and the Standard Model*, for unitarity, optical-theorem applications, and modern amplitude-oriented explanations.

### Deeper references

- Eden, Landshoff, Olive, and Polkinghorne, *The Analytic S-Matrix*, for the classic analytic S-matrix framework.
- Martin, *Scattering Theory: Unitarity, Analyticity and Crossing*, for a more mathematical treatment of analytic constraints.
- Elvang and Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for modern on-shell and unitarity-based amplitude methods.

## Version history

- **2026-06-14:** Initial standardized chapter overview for the unitarity, analyticity, and dispersion chapter.
