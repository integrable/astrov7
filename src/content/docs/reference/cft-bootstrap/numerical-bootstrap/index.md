---
title: "Numerical Conformal Bootstrap"
description: "Chapter overview for numerical conformal bootstrap methods, including crossing equations, positivity, linear functionals, semidefinite programming, islands, spectrum extraction, and modern algorithms."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; Simmons-Duffin TASI lectures; numerical bootstrap software and algorithm literature."
topics:
  - numerical conformal bootstrap
  - crossing equations
  - semidefinite programming
  - bootstrap islands
  - spectrum extraction
canonicalTopics:
  - numerical-conformal-bootstrap
  - semidefinite-bootstrap
  - bootstrap-islands
researchStatus:
  established:
    - "Numerical conformal bootstrap turns crossing symmetry, unitarity, and spectral assumptions into rigorous-looking exclusion problems and precision determinations of CFT data."
  active:
    - "Current work improves algorithms, software, rigorous error control, spectrum extraction, mixed-correlator systems, spinning correlators, gauge-theory targets, and integration with analytic bootstrap ideas."
---

Numerical Conformal Bootstrap is the chapter where crossing symmetry becomes a computational engine. Earlier chapters explain CFT data, OPEs, conformal blocks, positivity, and benchmark higher-dimensional theories. This chapter explains how those ingredients are turned into concrete bounds, islands, and extracted spectra.

The chapter is not a software manual only. It is a conceptual guide to the numerical bootstrap as a physics method: how to choose correlators, formulate crossing equations, impose unitarity, encode assumptions, interpret allowed regions, and avoid overclaiming what a finite computation proves.

The central picture is

$$
\text{crossing}+\text{unitarity}+\text{gaps}
\quad\longrightarrow\quad
\text{convex optimization problem}
\quad\longrightarrow\quad
\text{bounds, islands, and CFT data}.
$$

The numerical bootstrap is powerful because it does not require a weakly coupled Lagrangian. It can constrain strongly coupled CFTs directly from consistency of the operator algebra. Its flagship successes include high-precision studies of the 3D Ising CFT, $O(N)$ models, supersymmetric CFTs, boundary and defect systems, and increasingly gauge-theory CFTs.

## Prerequisites

You should know [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), and [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/).

For physics examples, first read [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), and [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/). For the optimization viewpoint, basic linear algebra and convex optimization are helpful but not required on a first pass.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [What the Numerical Bootstrap Computes](/cft-bootstrap/numerical-bootstrap/what-the-numerical-bootstrap-computes/) | The conceptual input-output map: assumptions in, excluded regions or candidate CFT data out. |
| 2 | [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/) | How conformal block decompositions become finite or infinite vector equations. |
| 3 | [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) | The separating-hyperplane idea behind exclusion proofs. |
| 4 | [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/) | How an infinite-dimensional problem is approximated by finitely many derivatives at the crossing-symmetric point. |
| 5 | [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) | Why positivity of OPE coefficients and polynomial matrix positivity lead to SDP methods. |
| 6 | [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/) | The practical pipeline from crossing equations to numerical feasibility runs. |
| 7 | [Identical Scalar Bounds](/cft-bootstrap/numerical-bootstrap/identical-scalar-bounds/) | The cleanest example: bounding scalar dimensions using one four-point function. |
| 8 | [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/) | How special CFTs appear as sharp features or isolated allowed regions. |
| 9 | [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/) | How several correlators and matrix positivity make the bootstrap dramatically stronger. |
| 10 | [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/) | How spectra and OPE coefficients are extracted near an optimal boundary. |
| 11 | [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/) | How modern algorithms move through high-dimensional parameter spaces and locate islands efficiently. |
| 12 | [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/) | What numerical precision, truncation, assumptions, and convergence do and do not justify. |
| 13 | [Reproducing the 3D Ising Island](/cft-bootstrap/numerical-bootstrap/reproducing-the-3d-ising-island/) | A guided model calculation that connects the method to a flagship physics result. |
| 14 | [Software Ecosystem](/cft-bootstrap/numerical-bootstrap/software-ecosystem/) | A map of SDPB, block generators, workflow tools, and reproducibility practices. |

After this path, you should be able to read a numerical bootstrap paper and identify the correlators used, the assumptions imposed, the optimization problem solved, and the meaning of the resulting bound or island.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\sum_{\mathcal O} \lambda_{\mathcal O}^2 F_{\Delta,\ell}=0$ | Schematic identical-scalar crossing equation. | Linear functionals and exclusion. |
| $\lambda_{\mathcal O}^2\ge0$ | Positivity from unitarity for identical external scalars. | Convex optimization. |
| Linear functional $\alpha$ | A linear map applied to the crossing vector equation. | Bounds and separating hyperplanes. |
| $\alpha(F_{\Delta,\ell})\ge0$ | Positivity condition proving that a proposed spectrum is impossible. | Exclusion plots. |
| Derivative cutoff $\Lambda$ | Number of derivatives or search-space size used in a truncated problem. | Convergence studies. |
| Spin cutoff $\ell_{\max}$ | Maximum spin explicitly represented before asymptotic treatment. | Numerical implementation. |
| Gap assumption | A lower bound on the next operator in a sector. | Islands and targeted CFT searches. |
| Mixed correlators | Crossing equations for several external operators at once. | 3D Ising and $O(N)$ precision islands. |
| Semidefinite program | Convex optimization problem with positive semidefinite matrix constraints. | SDPB and modern bootstrap codes. |
| Extremal functional | Functional saturating an optimal bound. | Spectrum extraction. |
| Navigator function | A smooth diagnostic for allowed versus excluded parameter points. | High-dimensional island searches. |

These landmarks are the numerical counterpart of the conceptual bootstrap slogan: the OPE must be associative and unitary.

## Common confusions

**A numerical exclusion is conditional.** It depends on the crossing equations, assumptions, truncation, precision, and implementation. The strongest papers make these dependencies explicit.

**A kink is not automatically a CFT.** Kinks often signal interesting theories, but a kink must be supported by additional evidence: spectrum extraction, mixed-correlator islands, agreement with other methods, or theoretical understanding.

**An island is not assumption-free.** Islands usually require spectral gaps or assumptions about leading operators. This is a feature, not a bug, if the assumptions are physically motivated and clearly stated.

**A finite derivative cutoff is not the full bootstrap problem.** Increasing $\Lambda$ often strengthens bounds, but convergence and numerical stability must be checked.

**OPE positivity has conditions.** The simple $\lambda^2\ge0$ statement applies in unitary identical-scalar setups with appropriate normalizations. Spinning, mixed, fermionic, nonunitary, and non-identical systems need careful matrix or sign structure.

**Spectrum extraction is delicate.** Extremal spectra can be extremely informative, but they are not raw exact spectra unless convergence, degeneracies, and assumptions are controlled.

**Software output is not physics by itself.** The physical result is the interpretation of a well-posed crossing problem, not merely a successful run of an optimizer.

## Boundaries

This chapter focuses on the method of numerical conformal bootstrap for local CFT correlators: crossing equations, positivity, optimization, implementation, and interpretation.

It does not replace the general chapters on OPEs, conformal blocks, crossing symmetry, or higher-dimensional CFT. Those chapters explain the physics input. This chapter explains the numerical machinery built from that input.

It also does not attempt to be a complete programming textbook. The software pages explain workflows and reproducibility, but they do not replace official documentation for SDPB, block-generation packages, or cluster environments.

Finally, this chapter does not claim that numerical bootstrap is the only nonperturbative method. Lattice simulations, Monte Carlo, perturbative RG, large-$N$, supersymmetric localization, integrability, and analytic bootstrap all provide complementary evidence and intuition.

## Where to go next

After this chapter, move to [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) to understand large-spin expansions, Lorentzian inversion, lightcone methods, and asymptotic CFT data.

For physics applications, return to [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/), [Boundary, Defect, and Interface CFT](/cft-bootstrap/boundary-defect-interface-cft/), and [Supersymmetric CFT](/cft-bootstrap/supersymmetric-cft/).

For implementation details, go to [Computational CFT and Bootstrap](/cft-bootstrap/computational-cft-bootstrap/) once the conceptual pages here feel familiar.

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- W. Landry and D. Simmons-Duffin, “Scaling the semidefinite program solver SDPB,” 2019.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**, for analytic methods that increasingly interact with numerical bootstrap.

## Version history

- 2026-07-01: Replaced scaffold with a polished chapter overview. Added prerequisites, reading path, landmarks, common confusions, boundaries, next routes, references, and version history.
