---
title: "Model Calculation Library"
description: "Chapter overview for worked renormalization, RG, and EFT benchmark calculations in scalar theory, Yukawa theory, QED, Yang–Mills theory, matching examples, and Wilson–Fisher criticality."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Schwartz 2014; Weinberg 1995; Wilson and Kogut 1974; Zinn-Justin 2021; Burgess 2020."
topics:
  - worked examples
  - one-loop renormalization
  - beta functions
  - EFT matching
  - Wilson-Fisher fixed point
  - model calculations
canonicalTopics:
  - model-calculation-library
  - renormalization-worked-examples
  - eft-worked-examples
researchStatus:
  established:
    - "The chapter collects standard benchmark calculations whose role is to make renormalization, RG, and EFT conventions concrete and reproducible."
  active:
    - "Future pages may add multi-loop examples, gauge-theory checks, EFT threshold calculations, curved-spacetime examples, and computational notebooks; the first pass focuses on canonical analytic calculations."
---

## Summary

The **Model Calculation Library** is the worked-example chapter of the Renormalization, RG, and EFT volume. The rest of the volume explains concepts: counterterms, schemes, beta functions, Wilsonian flow, fixed points, matching, naturalness, and EFT power counting. This chapter shows those ideas in complete calculations.

A good model calculation should answer four questions:

| Question | What the calculation must show |
|---|---|
| What is being computed? | The correlator, amplitude, effective action, beta function, critical exponent, or Wilson coefficient. |
| What conventions are used? | Regulator, scheme, normalization, external kinematics, operator basis, and sign conventions. |
| What is subtracted or matched? | Counterterms, renormalization conditions, EFT subtraction, or threshold relation. |
| What survives as physics? | Running, anomalous dimensions, critical exponents, Wilson coefficients, or observable scale dependence. |

The chapter is intentionally selective. It is not a table of every integral in QFT. It is a curated set of benchmark calculations that anchor the conceptual pages. The reader should be able to return to these pages whenever a formula elsewhere feels too abstract.

:::note[What makes a model calculation useful]
A calculation is useful only if a reader can audit it. Each page in this chapter should state the theory, the normalization, the regulator, the scheme, the external kinematics, the diagram or functional determinant being evaluated, the subtraction or matching condition, and the interpretation of the final answer.
:::

## Prerequisites

You should already know the core pages in the following chapters:

- [Regularization and Counterterms](/renormalization-rg-eft/regularization-counterterms/), especially dimensional regularization and counterterms;
- [Renormalized Perturbation Theory](/renormalization-rg-eft/renormalized-perturbation-theory/), especially renormalized Lagrangians, schemes, and Green functions;
- [Renormalization Group Equations](/renormalization-rg-eft/renormalization-group-equations/), especially beta functions, anomalous dimensions, and running couplings;
- [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/), especially power counting and matching;
- [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/), especially tree-level and one-loop matching.

Readers who mainly want examples can start here and follow links backward when a concept appears. Readers who want conceptual order should read the earlier chapters first.

## Reading path

The recommended first pass is:

| Step | Page | What it teaches |
|---:|---|---|
| 1 | [Phi-Four One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/phi-four-one-loop-renormalization/) | How a simple scalar theory produces divergent two- and four-point functions and how counterterms cancel them. |
| 2 | [Phi-Four Beta Function](/renormalization-rg-eft/model-calculation-library/phi-four-beta-function/) | How the coefficient of a logarithmic divergence becomes a beta function in minimal subtraction. |
| 3 | [Wilson–Fisher Epsilon Expansion](/renormalization-rg-eft/model-calculation-library/wilson-fisher-epsilon-expansion/) | How the same scalar theory becomes an interacting critical fixed point in $d=4-\epsilon$. |
| 4 | [Yukawa Theory One Loop](/renormalization-rg-eft/model-calculation-library/yukawa-theory-one-loop/) | How fields of different spin renormalize masses, wavefunctions, and couplings together. |
| 5 | [QED One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/qed-one-loop-renormalization/) | How Ward identities constrain counterterms and charge renormalization. |
| 6 | [QED Beta Function](/renormalization-rg-eft/model-calculation-library/qed-beta-function/) | How vacuum polarization produces screening and a positive beta function. |
| 7 | [Yang–Mills One-Loop Beta Function](/renormalization-rg-eft/model-calculation-library/yang-mills-one-loop-beta-function/) | How gauge and ghost loops produce antiscreening and asymptotic freedom. |
| 8 | [Integrating Out a Heavy Scalar](/renormalization-rg-eft/model-calculation-library/integrating-out-heavy-scalar/) | How heavy fields leave local EFT operators. |
| 9 | [Fermi Theory from W Exchange](/renormalization-rg-eft/model-calculation-library/fermi-theory-from-w-exchange/) | How a heavy mediator becomes a four-fermion operator and why the coefficient is matched at a threshold. |
| 10 | [Tree-Level Matching Example](/renormalization-rg-eft/model-calculation-library/tree-level-matching-example/) | How to match amplitudes by expanding in $Q/M$. |
| 11 | [One-Loop Matching Example](/renormalization-rg-eft/model-calculation-library/one-loop-matching-example/) | How full-theory loops and EFT loops are subtracted to isolate Wilson coefficients. |

The first four pages are the scalar/Yukawa spine. The middle three pages are the gauge-theory spine. The last four pages are the EFT matching spine.

## Landmarks

| Landmark | Meaning | Where it appears |
|---|---|---|
| Counterterm Lagrangian | Local terms added to cancel regulator dependence and define renormalized parameters. | Scalar, Yukawa, QED, Yang–Mills pages. |
| $Z$ factors | Multiplicative relations between bare and renormalized fields, masses, and couplings. | Renormalization examples. |
| $1/\epsilon$ pole | Dimensional-regularization signal of UV divergence in MS-like schemes. | One-loop examples. |
| Beta function | Scale dependence of a renormalized coupling at fixed bare data. | Scalar, QED, Yang–Mills pages. |
| Anomalous dimension | Scale dependence of fields or composite operators beyond engineering dimension. | Scalar, Yukawa, and operator examples. |
| Fixed point | Zero of beta functions; source of scaling behavior. | Wilson–Fisher example. |
| Matching coefficient | Wilson coefficient fixed by equating full-theory and EFT observables. | Heavy-scalar and Fermi-theory examples. |
| RG consistency | Cancellation of artificial matching-scale dependence between coefficients and matrix elements. | Matching and running examples. |

The chapter should make these landmarks visible, not hide them behind final answers.

## Calculation hygiene

Every model-calculation page should state:

| Item | What to state |
|---|---|
| Model | The Lagrangian, field content, symmetries, and normalization of couplings. |
| Regulator | Cutoff, dimensional regularization, Pauli–Villars, lattice, or other scheme. |
| Scheme | MS, $\overline{\mathrm{MS}}$, on-shell, MOM, Wilsonian cutoff, or a custom condition. |
| External kinematics | Momentum routing, on-shell/off-shell choice, Euclidean or Lorentzian continuation. |
| Diagram set | Which loop order, topology, channels, and counterterm insertions are included. |
| Symmetry factors | How identical contractions, channels, and group factors are counted. |
| Subtractions | Which divergent and finite pieces are removed or retained. |
| Checks | Dimensional analysis, symmetry identities, scheme dependence, limiting behavior, and RG consistency. |

The boring bookkeeping is the product. Without it, the final formula is a souvenir, not a calculation.

## Common confusions

**Thinking a benchmark result is convention-free.** Even famous formulas depend on coupling normalization. A page using $\lambda\phi^4/4!$ will not display the same coefficients as a page using $g\phi^4$.

**Confusing beta-function sign conventions.** This volume uses

$$
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare fixed}}.
$$

A flow toward the infrared may be described using the opposite RG time.

**Dropping finite terms without saying why.** In MS-like schemes, pole parts determine counterterms, but finite parts still matter for physical amplitudes and scheme conversion.

**Matching full-theory amplitudes without subtracting EFT loops.** One-loop matching is not usually “compute the full theory and call the answer $C$.” The EFT contribution at the same order must be included and subtracted under the same infrared conditions.

**Treating gauge-dependent intermediate quantities as observables.** Self-energies, off-shell Green functions, and effective potentials can be gauge-dependent. Gauge-invariant conclusions require the right objects and identities.

**Overfitting examples.** A one-loop scalar calculation is a benchmark, not a template for every theory. Symmetry, infrared physics, thresholds, and operator mixing can change the details.

## Boundaries

This chapter does:

- provide complete benchmark calculations with stated conventions;
- show how counterterms, $Z$ factors, beta functions, anomalous dimensions, and Wilson coefficients are extracted;
- connect calculations to the conceptual pages of this volume;
- emphasize checks that make a calculation trustworthy.

This chapter does not try to:

- replace the loop-integral technology chapter in Perturbative QFT and Scattering;
- provide a full multi-loop amplitudes course;
- be a table of Standard Model precision calculations;
- cover lattice Monte Carlo, conformal bootstrap numerics, or symbolic software workflows;
- prove general renormalization theorems.

When a calculation becomes a physical theory in its own right, the full explanation belongs elsewhere. For example, QCD running belongs partly here as a benchmark, but QCD as a physical theory belongs in Gauge Theories and the Standard Model.

## Where to go next

For conceptual repair, go back to the page whose idea appears in the calculation: [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), or [Matching](/renormalization-rg-eft/effective-field-theory/matching/).

For practical loop methods, continue to Perturbative QFT and Scattering. For physical gauge theories, continue to Gauge Theories and the Standard Model. For EFT applications, use [Major Effective Field Theories](/renormalization-rg-eft/major-efts/). For statistical applications, use [Statistical Field Theory and Criticality](/renormalization-rg-eft/statistical-field-theory-criticality/).

## References

### First-pass calculation references

- Mark Srednicki, *Quantum Field Theory*, for compact one-loop scalar, Yukawa, QED, Yang–Mills, RG, and EFT calculations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for counterterm logic, renormalization conditions, and physical explanation.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for modern worked examples in renormalized perturbation theory, QED, Yang–Mills theory, and EFT.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for general renormalization theory, gauge theory, and EFT logic.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for scalar field theory, perturbative RG, critical exponents, and statistical-field-theory applications.
- Kenneth Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” for the classic bridge between critical phenomena and field theory.
- C. P. Burgess, *Introduction to Effective Field Theory*, for matching, power counting, nonrenormalizable theories, and EFT examples across physics.

## Version history

- 2026-06-19: First polished chapter overview. Added reading path, landmarks, calculation hygiene checklist, boundaries, and references.
