---
title: "Matching, Running, and Decoupling"
description: "Chapter overview for matching full theories to EFTs, evolving Wilson coefficients, crossing thresholds, and using decoupling consistently in the Renormalization, RG, and EFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II, ch. 18; Srednicki 2007, §§28–29; Schwartz 2014, chs. 22–23 and 31–36; Burgess 2020, chs. 2–3 and applications; Manohar EFT lectures."
topics:
  - matching
  - running
  - decoupling
  - threshold corrections
  - Wilson coefficients
  - operator bases
canonicalTopics:
  - eft-matching
  - renormalization-group-evolution
  - decoupling
  - threshold-matching
researchStatus:
  established:
    - "Matching, running, and decoupling form the standard EFT workflow for separating heavy-scale physics from low-energy matrix elements."
  active:
    - "Automated one-loop and multi-loop matching, evanescent-operator schemes, threshold corrections, nonperturbative matching, and basis conversion remain active research and infrastructure areas."
---

Matching, Running, and Decoupling is the chapter in the Renormalization, RG, and EFT volume where EFT becomes a working machine. The previous chapter explained why local low-energy theories are predictive. This chapter explains how to actually use them when more than one scale is present.

The workflow is simple enough to fit on one line:

$$
\text{match at }M
\quad\longrightarrow\quad
\text{run to }\mu\sim Q
\quad\longrightarrow\quad
\text{compute low-energy matrix elements}.
$$

The reason this chapter exists is that many bad EFT calculations fail at exactly this point. They mix up the heavy scale $M$, the renormalization scale $\mu$, the physical scale $Q$, and the cutoff or breakdown scale. They also mix up Wilson coefficients with matrix elements, matching with running, and decoupling with simply deleting fields. This chapter keeps those jobs separate.

A compact formula for the whole chapter is

$$
\mathcal A_{\text{low}}(Q)
=
\sum_i C_i(\mu)
\langle f|\mathcal O_i(\mu)|i\rangle
+
O\left(\frac{Q^{N+1}}{M^{N+1}}\right),
$$

with the coefficients $C_i$ fixed by matching and evolved by RG equations.

## Prerequisites

You should know the [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) chapter, especially [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/).

You should also be comfortable with [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/) | The cleanest way to see heavy exchange become local Wilson coefficients. |
| 2 | [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/) | How to separate full-theory loop effects from EFT loop effects without double counting. |
| 3 | [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) | What changes when a particle is removed from the active low-energy spectrum. |
| 4 | [Integrating Out Heavy Fields](/renormalization-rg-eft/matching-running-decoupling/integrating-out-heavy-fields/) | Functional and diagrammatic views of the high-energy/low-energy split. |
| 5 | [Matching Correlation Functions](/renormalization-rg-eft/matching-running-decoupling/matching-correlation-functions/) | Matching off-shell Green functions and understanding scheme and operator-basis dependence. |
| 6 | [Matching S-Matrix Elements](/renormalization-rg-eft/matching-running-decoupling/matching-s-matrix-elements/) | Matching on-shell amplitudes while avoiding redundant operators and gauge artifacts. |
| 7 | [Matching with Background Fields](/renormalization-rg-eft/matching-running-decoupling/matching-with-background-fields/) | A gauge-covariant route to effective actions and Wilson coefficients. |
| 8 | [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/) | How anomalous-dimension matrices evolve Wilson coefficients between scales. |
| 9 | [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/) | Why coefficient values depend on coordinates, while physical predictions do not. |

After this path, you should be able to decide where to match, which degrees of freedom remain active, how to run coefficients, where logarithms belong, and how to state the residual truncation uncertainty.

## Landmarks

| Landmark | Meaning | Where it appears |
|---|---|---|
| Matching scale $\mu_M$ | Scale near a heavy threshold where full and effective descriptions are equated. | Tree-level matching, one-loop matching, thresholds. |
| Wilson coefficient $C_i(\mu)$ | Short-distance coefficient multiplying a local EFT operator. | Every page in this chapter. |
| Matrix element $\langle\mathcal O_i(\mu)\rangle$ | Long-distance quantity computed inside the EFT. | Running, low-energy predictions, operator bases. |
| Threshold correction | Finite shift when a field is removed from the active theory. | Threshold corrections and decoupling. |
| Anomalous-dimension matrix $\gamma_i{}^j$ | Generator of operator mixing under RG evolution. | Renormalization group evolution. |
| Evolution matrix $U_i{}^j(\mu,M)$ | Solution that transports Wilson coefficients between scales. | Running and resummation of logarithms. |
| Basis transformation | Change of coordinates among operators and coefficients. | Operator basis choice, redundant operators. |
| Decoupling | Suppression or absorption of heavy effects into local terms at low energy. | Integrating out heavy fields and threshold pages. |

The chapter's central separation is

$$
\text{short-distance physics}
\longleftrightarrow
C_i(\mu),
\qquad
\text{long-distance physics}
\longleftrightarrow
\langle\mathcal O_i(\mu)\rangle.
$$

The scale dependence cancels between the two when the calculation is performed consistently:

$$
\mu\frac{d}{d\mu}
\left[
C_i(\mu)\langle\mathcal O_i(\mu)\rangle
\right]=0
$$

up to the truncation order and any explicitly neglected effects.

## Common confusions

**Matching is not running.** Matching fixes Wilson coefficients by comparing two theories at a scale. Running evolves those coefficients within one theory.

**Decoupling is not deleting a particle and pretending nothing happened.** When a heavy field is removed from the active spectrum, its low-energy effects remain as shifts of light parameters and higher-dimension operators.

**The matching scale is not the physical scale.** One usually chooses $\mu_M\sim M$ to avoid large logarithms in matching, then runs to $\mu\sim Q$ to avoid large logarithms in matrix elements.

**Wilson coefficients are not observables.** They depend on scheme, scale, operator basis, evanescent conventions, and normalization choices. Observable predictions are built from coefficients and matrix elements together.

**Full-theory loops and EFT loops should not both include the same momentum region.** Matching subtracts the EFT contribution from the full-theory contribution so that low-energy loops are not double counted.

**A zero tree-level coefficient is not necessarily zero after matching or running.** Loops can generate operators allowed by symmetry, and RG evolution can mix operators inside the allowed basis.

## Boundaries

This chapter does:

- explain matching calculations as equality of low-energy observables or Green functions;
- distinguish tree-level matching, one-loop matching, threshold corrections, and RG evolution;
- show how decoupling is implemented in practice;
- explain the scheme and basis dependence of Wilson coefficients;
- prepare readers for major EFT examples such as Fermi theory, chiral perturbation theory, HQET, SCET, SMEFT, and gravitational EFT.

This chapter does not try to do:

- teach all EFT philosophy from scratch, which belongs in [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/);
- develop general loop-integral technology, which belongs in Perturbative QFT and Scattering;
- provide full Standard Model EFT phenomenology, which belongs in the later Major Effective Field Theories and Standard Model pages;
- replace dedicated nonperturbative matching methods such as lattice matching;
- treat every possible threshold convention in QCD, SCET, HQET, SMEFT, or nuclear EFT.

The boundary is this: this chapter teaches the general scale-separation workflow. Specific EFTs later specialize it.

## Where to go next

After this chapter, readers interested in conceptual EFT should continue to Naturalness and Power Counting. Readers interested in gauge-theory applications should continue to Gauge Theories and RG. Readers interested in examples should continue to Major Effective Field Theories and the Model Calculation Library.

For immediate practice, work through tree-level heavy exchange, then a one-loop matching problem where the full theory and EFT have different loop contributions but the same infrared behavior. The skill is not memorizing a formula; the skill is knowing which part of the answer belongs to matching, which part belongs to running, and which part belongs to the low-energy matrix element.

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for renormalization group methods, large logarithms, fixed-point behavior, minimal subtraction, and nonrenormalizable interactions.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on the renormalization group and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on nonrenormalizable theories, renormalization group methods, Standard Model logarithms, HQET, and SCET.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, power counting, matching, decoupling, and applications.
- Aneesh Manohar, EFT lectures and reviews, for practical matching, anomalous dimensions, and operator-basis methods.
- Howard Georgi, classic EFT lectures, for the viewpoint that low-energy physics is organized by degrees of freedom, symmetries, and power counting.

## Version history

- 2026-06-18: First polished draft. Added chapter role, prerequisites, reading path, landmarks, common confusions, boundaries, next routes, and references.
