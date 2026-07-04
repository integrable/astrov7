---
title: "Loop Integral Technology"
description: "Chapter overview for parameter representations, tensor reduction, Passarino–Veltman reduction, IBP identities, master integrals, differential equations, cuts, Landau singularities, and special functions in perturbative QFT."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Srednicki 2007, §§14–20; Coleman 2019, chs. 15–16; Weinberg 1995, Vol. I, chs. 10–11; Schwartz 2014, app. B and chs. 15–20; Smirnov 2012; Henn 2013."
topics:
  - loop integrals
  - Feynman parameters
  - tensor reduction
  - integration by parts
  - master integrals
  - analytic structure
canonicalTopics:
  - loop-integral-technology
  - feynman-parameters
  - integration-by-parts
  - master-integrals
  - differential-equations-for-integrals
researchStatus:
  established:
    - "Parameter representations, tensor reduction, IBP identities, master integrals, differential equations, and cut-based analytic checks are standard tools in modern perturbative QFT."
  active:
    - "Efficient high-loop reduction, canonical bases, elliptic and beyond-elliptic integral classes, numerical stability, and automated finite-field workflows remain active research areas."
---

Loop Integral Technology is the chapter in the Perturbative QFT and Scattering volume where loop diagrams become calculable objects. The previous chapter explains why loop integrals arise and why they need regulators; this chapter teaches the methods used to transform those integrals into standard functions, master integrals, discontinuities, and checks.

The chapter exists because writing down a loop integral is not the same as evaluating it. Even a modest one-loop graph may require parameterization, momentum shifts, tensor decomposition, threshold analysis, analytic continuation, and a careful separation of ultraviolet and infrared regions.

Read this chapter when you want the bridge from “the diagram contains an integral” to “the amplitude is a controlled analytic or numerical expression.”

$$
\text{loop integral}
\longrightarrow
\text{representation}
\longrightarrow
\text{reduction}
\longrightarrow
\text{master integrals}
\longrightarrow
\text{analytic structure}.
$$

## Prerequisites

You should know [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), and [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/).

For scattering applications, review [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/), and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/). For modern amplitude applications, [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/) is the natural later companion.

## Reading path

Read these pages in order on a first pass if your goal is to understand the standard pipeline from raw integrals to reusable results.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) | The basic denominator-combining trick that converts products of propagators into integrals over simplex variables. |
| 2 | [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/) | The exponential representation of propagators and its geometric relation to proper time, Gaussian momentum integrals, and worldline intuition. |
| 3 | [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/) | How Lorentz covariance reduces loop integrals with numerator momenta to scalar coefficient functions. |
| 4 | [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/) | The standard one-loop tensor-reduction system in terms of scalar coefficient functions. |
| 5 | [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/) | The total-derivative identities that relate many integrals inside one family. |
| 6 | [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) | The finite basis of integrals left after reduction and the practical meaning of a master basis. |
| 7 | [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) | How derivatives with respect to kinematic variables produce coupled equations for master integrals. |
| 8 | [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) | How on-shell cuts expose discontinuities, check integral bases, and connect loop integrals to phase space. |
| 9 | [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) | The geometric conditions for where Feynman integrals can develop singularities. |
| 10 | [Polylogarithms and Symbols Preview](/perturbative-qft/loop-integral-technology/polylogarithms-and-symbols-preview/) | A preview of the function classes that solve many massless and one-scale loop integrals. |
| 11 | [Elliptic Integrals Preview](/perturbative-qft/loop-integral-technology/elliptic-integrals-preview/) | A preview of the next function layer that appears when maximal cuts define elliptic curves. |

After this path, you should be able to recognize the standard integral pipeline: combine denominators, reduce tensor and family complexity, choose master integrals, solve or check them using differential equations and cuts, and interpret their singularities.

## Landmarks

| Landmark | Meaning | Where used |
|---|---|---|
| Feynman parameters | Denominators are combined by introducing simplex variables. | One-loop bubbles, triangles, boxes, and many multi-loop representations. |
| Schwinger parameters | Propagators are written as exponentials integrated over positive parameters. | Proper-time methods, Gaussian momentum integration, and parametric graph polynomials. |
| Tensor reduction | Numerator loop momenta are decomposed into external momenta and metric tensors. | Converting tensor amplitudes into scalar integrals. |
| Passarino–Veltman coefficients | One-loop tensor integrals are expressed through scalar coefficient functions. | Electroweak and QED one-loop calculations. |
| IBP identity | A total derivative in loop momentum space gives a linear relation among integrals. | Multi-loop reduction and master-integral bases. |
| Master integral | An integral not reducible further within the chosen IBP system. | Organizing final answers and differential equations. |
| Differential equation | Kinematic derivatives of master integrals close on the master basis. | Analytic evaluation, boundary data, and canonical forms. |
| Cut integral | Replacing propagators by on-shell delta functions exposes a discontinuity. | Unitarity checks and integral-basis reconstruction. |
| Landau equations | Singularities can occur when propagators go on shell and loop momenta are pinched. | Thresholds, anomalous thresholds, and analytic continuation. |
| Polylogarithmic and elliptic functions | Distinct classes of special functions needed to express loop integrals. | Analytic amplitudes and high-precision numerical evaluation. |

A good loop-integral calculation keeps two records at once: an algebraic record of reductions and a physical record of analytic structure. Losing either one is how beautiful formulas turn into booby traps.

## Common confusions

**Feynman parameters are not just a trick for homework integrals.** They reveal the geometry of denominator combinations, expose thresholds, and provide the entry point to graph polynomials and Landau analysis.

**Tensor reduction is not the same as gauge invariance.** Reducing numerator tensors into scalar coefficients is algebraic. Gauge invariance is a physical and symmetry constraint on the final amplitude or appropriate building blocks.

**IBP identities do not evaluate integrals by themselves.** They reduce large families to master integrals. The masters still need boundary conditions, differential equations, direct integration, numerical methods, or known function bases.

**A master basis is not unique.** Different bases can be better for different purposes: compact reduction, uniform transcendental weight, numerical stability, manifest symmetries, or simple boundary data.

**Cuts do not always determine everything immediately.** In many applications cuts reconstruct the cut-constructible part or constrain an ansatz. Rational terms, regulator dependence, and contact terms must be handled with care.

**A branch cut is not a pathology.** Branch cuts encode physical thresholds and analytic continuation. The problem is not that they exist; the problem is choosing the wrong sheet or crossing a cut without tracking the prescription.

## Boundaries

This chapter is about integral technology: parameter representations, reductions, master integrals, differential equations, cuts, singularities, and special-function previews.

It does not try to teach the physical origin of loops from scratch; that belongs to [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/). It does not give the final scheme-dependent interpretation of counterterms and renormalized amplitudes; that belongs to [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/).

It also does not replace the general mathematics of special functions. Polylogarithms, elliptic integrals, symbols, and differential equations have broader homes in the Mathematical Toolkit. Here they are introduced only insofar as they organize Feynman integrals.

## Where to go next

After this chapter, go to [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/) to see how loop results become finite scheme-dependent amplitudes and physical predictions.

Go to [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/) to understand the physical meaning of discontinuities, thresholds, dispersion relations, and positivity constraints.

Go to [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/) if you want to use generalized unitarity and on-shell methods to build loop integrands and amplitudes without starting from every Feynman diagram separately.

## References

- M. Srednicki, *Quantum Field Theory*, §§14–20, for scalar loop corrections and early one-loop scattering examples.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 15–16, for self-energies, one-loop integrals, and Feynman parametrization in a pedagogical model.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 10–11, for renormalization and loop calculation structure.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, appendix B and chs. 15–20, for regularization identities, Feynman parameters, dimensional regularization, and loop examples.
- V. A. Smirnov, *Analytic Tools for Feynman Integrals*, for systematic multi-loop integral technology.
- J. M. Henn, “Multiloop Integrals in Dimensional Regularization Made Simple,” for the canonical differential-equation viewpoint.
- Z. Bern, L. Dixon, and D. A. Kosower, reviews and lecture notes on unitarity methods, for the cut-based approach to integral coefficients and amplitudes.

## Version history

- **2026-06-14:** Replaced the scaffold with a polished chapter overview for loop-integral representations, reduction methods, master integrals, differential equations, cuts, singularities, and special-function previews.
