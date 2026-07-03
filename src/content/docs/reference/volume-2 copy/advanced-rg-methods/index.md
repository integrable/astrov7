---
title: "Advanced RG Methods"
description: "Chapter overview for exact RG equations, functional RG, local RG, conformal perturbation theory, monotonicity theorems, exotic RG flows, nonperturbative RG, and holographic RG."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Wilson and Kogut 1974; Polchinski 1984; Wetterich 1993; Morris; Coleman 1985; Weinberg 1995; Zinn-Justin 2021; Berges, Tetradis, and Wetterich; Rosten."
topics:
  - exact renormalization group
  - functional renormalization group
  - local renormalization group
  - conformal perturbation theory
  - RG monotonicity
  - nonperturbative RG
canonicalTopics:
  - advanced-rg-methods
  - exact-rg-equations
  - functional-rg
  - local-rg
researchStatus:
  established:
    - "Exact RG equations, functional RG flows, local RG identities, conformal perturbation theory, and RG monotonicity theorems are standard advanced tools for organizing scale dependence beyond elementary beta functions."
  active:
    - "Nonperturbative truncations, conformal-manifold constraints, scheme-independent observables, exotic RG flows, and holographic interpretations remain active research areas."
---

Advanced RG Methods is the chapter in the Renormalization, RG, and EFT volume where the renormalization group stops being only a set of beta functions for a few couplings and becomes a set of functional, geometric, and nonperturbative tools.

Earlier chapters taught the basic languages: renormalized perturbation theory, Callan–Symanzik equations, Wilsonian coarse graining, fixed points, operator mixing, EFT matching, and critical phenomena. This chapter collects methods that refine or generalize those ideas: exact RG equations, functional RG, local RG, conformal perturbation theory, monotonicity theorems, limit cycles, nonperturbative RG, and holographic RG.

The guiding discipline is:

$$
\text{advanced RG method}
\neq
\text{magic solution of a QFT}.
$$

An exact RG equation is often an exact identity, but solving it usually requires a truncation, an ansatz, a symmetry input, a numerical projection, or a controlled expansion. This chapter is about keeping that distinction sharp.

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/).

For the functional equations, comfort with Euclidean path integrals and functional derivatives is essential. For local RG and conformal perturbation theory, you should know the basics of composite operators, operator mixing, OPEs, and stress tensors.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Exact RG Equations](/renormalization-rg-eft/advanced-rg-methods/exact-rg-equations/) | The common logic behind exact Wilsonian, Polchinski, Wetterich, and related functional flow equations. |
| 2 | [Polchinski Equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/) | A Wilsonian flow equation for the cutoff-dependent interaction action. |
| 3 | [Wetterich Equation](/renormalization-rg-eft/advanced-rg-methods/wetterich-equation/) | The effective-average-action version of functional RG used in many nonperturbative truncations. |
| 4 | [Local Renormalization Group](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/) | How RG becomes a spacetime-dependent Weyl identity involving sources, anomalies, and operator mixing. |
| 5 | [Conformal Perturbation Theory](/renormalization-rg-eft/advanced-rg-methods/conformal-perturbation-theory/) | How to perturb away from a CFT using OPE coefficients and regulated integrated operator insertions. |
| 6 | [c-Theorem, F-Theorem, and a-Theorem Preview](/renormalization-rg-eft/advanced-rg-methods/c-theorem-f-theorem-a-theorem-preview/) | What is known about irreversible RG flow and monotonic quantities in special dimensions. |
| 7 | [Limit Cycles and Exotic RG Flows](/renormalization-rg-eft/advanced-rg-methods/limit-cycles-and-exotic-rg-flows/) | What changes when RG flow is not a simple gradient-like trajectory between fixed points. |
| 8 | [Nonperturbative RG Preview](/renormalization-rg-eft/advanced-rg-methods/nonperturbative-rg-preview/) | How exact equations are projected into truncations, derivative expansions, and numerical flows. |
| 9 | [Holographic RG Preview](/renormalization-rg-eft/advanced-rg-methods/holographic-rg-preview/) | How radial evolution in a gravitational dual can encode field-theory scale evolution. |

After this path, you should be able to read an advanced RG paper without confusing the exactness of a formal identity with the accuracy of a chosen approximation.

## Landmarks

| Landmark | Meaning | Where it appears |
|---|---|---|
| Exact RG equation | A functional identity expressing cutoff independence or controlled cutoff variation. | Wilsonian RG, Polchinski equation, Wetterich equation. |
| Flowing functional | An action, effective action, or generating functional that depends on a scale. | $S_\Lambda$, $\Gamma_k$, $W[g_{\mu\nu},J_i]$. |
| Regulator kernel | A smooth function that suppresses high or low momentum modes. | ERG and FRG formulations. |
| Operator projection | The act of expanding a functional flow onto a chosen operator basis. | Beta functions, anomalous dimensions, EFT running. |
| Truncation | A finite ansatz for an infinite functional flow. | Local potential approximation, derivative expansion, vertex expansion. |
| Scheme dependence | Dependence on regulator shape, coordinates on theory space, or subtraction convention. | Almost every advanced RG method. |
| Local RG | RG with spacetime-dependent couplings and background fields. | Trace anomalies, Weyl consistency, curved spacetime. |
| Monotonic quantity | A function that changes irreversibly along special RG flows. | Zamolodchikov $c$, three-dimensional $F$, four-dimensional $a$. |
| Limit cycle | A closed RG trajectory rather than an isolated fixed point. | Few-body EFT, scale anomalies, exotic flows. |
| Holographic radial flow | Evolution in a bulk radial direction interpreted as RG flow. | AdS/CFT, domain walls, holographic renormalization. |

The repeated pattern is that a complicated QFT is replaced by a flow problem on a large space of functionals or couplings. The hard part is not writing a formal equation. The hard part is choosing faithful coordinates, preserving symmetries, controlling truncation error, and extracting scheme-independent statements.

## Common confusions

**Exact equation does not mean exact answer.** The Polchinski and Wetterich equations are exact identities under their assumptions. Their practical use usually requires truncating an infinite-dimensional functional flow.

**Functional RG is not automatically nonperturbative wisdom.** It can capture nonperturbative effects when the truncation is appropriate, but a poor truncation can be worse than a well-controlled perturbative calculation.

**Changing the regulator changes the coordinates.** Smooth cutoff choices and regulator shape functions affect intermediate beta functions and truncation artifacts. Universal quantities must be checked for regulator stability.

**Local RG is not just beta functions with $x$ labels.** Once couplings become spacetime-dependent sources, contact terms, background curvature, flavor rotations, Weyl anomalies, and operator mixing become part of the story.

**Monotonicity theorems have hypotheses.** The two-dimensional $c$-theorem, three-dimensional $F$-theorem, and four-dimensional $a$-theorem are not interchangeable slogans. Their assumptions and dimensions matter.

**Holographic RG is not the definition of RG.** It is a powerful realization of RG-like evolution in theories with suitable gravitational duals. Ordinary QFT RG exists without holography.

## Boundaries

This chapter does:

- explain exact RG equations as identities behind Wilsonian and functional RG;
- compare Polchinski-type and Wetterich-type flows;
- show how beta functions and anomalous dimensions are extracted from functional equations;
- introduce local RG, Weyl consistency, and anomaly-aware scale transformations;
- preview monotonicity theorems, exotic flows, nonperturbative RG, and holographic RG;
- emphasize what is exact, what is truncated, and what is universal.

This chapter does not try to do:

- replace the introductory development of [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/);
- provide a full numerical FRG manual, which belongs partly in Computational QFT and Tools;
- prove the complete $c$-, $F$-, or $a$-theorem in full rigor;
- develop the full AdS/CFT dictionary, which belongs in Spacetime, Gravity, and Holography;
- give a theorem-first constructive definition of QFT, which belongs in Mathematical and Rigorous QFT.

## Where to go next

For the immediate continuation, read [Exact RG Equations](/renormalization-rg-eft/advanced-rg-methods/exact-rg-equations/), then specialize to the [Polchinski Equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/) and [Wetterich Equation](/renormalization-rg-eft/advanced-rg-methods/wetterich-equation/).

For conceptual background, return to [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/). For operator-based methods, use [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/) and [Conformal Perturbation Theory Preview](/renormalization-rg-eft/local-operators-and-ope/conformal-perturbation-theory-preview/).

## References

- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), for the conceptual foundation of modern RG and exact RG viewpoints.
- J. Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984), for the Wilsonian exact RG equation used in perturbative renormalization proofs.
- C. Wetterich, "Exact Evolution Equation for the Effective Potential," *Physics Letters B* **301** (1993), for the effective-average-action flow equation.
- T. R. Morris, reviews and lectures on exact renormalization group methods.
- O. J. Rosten, "Fundamentals of the Exact Renormalization Group," for a modern account of ERG structure and universality.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, fixed points, critical exponents, and RG equations.
- J. Berges, N. Tetradis, and C. Wetterich, "Non-Perturbative Renormalization Flow in Quantum Field Theory and Statistical Physics," for the functional RG perspective.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on dilatations, anomalous dimensions, and Callan–Symanzik equations.

## Version history

- 2026-06-19: First polished draft. Opened the Advanced RG Methods chapter with reading path, landmarks, boundaries, and references.
