---
title: "Navigator and Modern Search Algorithms"
description: "How modern numerical bootstrap workflows search high-dimensional parameter spaces using bisection, adaptive triangulation, cutting surfaces, navigator functions, skydive-style methods, and related algorithms."
sidebar:
  label: "Navigator and Search Algorithms"
  order: 11
level: Graduate
status: "Polished draft"
source: "Rychkov and Su 2024; Poland, Rychkov, and Vichi 2019; navigator, cutting-surface, Delaunay, tiptop, skydive, and SDPB literature."
topics:
  - numerical conformal bootstrap
  - navigator function
  - search algorithms
  - bootstrap islands
  - high-dimensional optimization
canonicalTopics:
  - navigator-and-modern-search-algorithms
  - bootstrap-search-algorithms
  - high-dimensional-bootstrap-islands
researchStatus:
  established:
    - "Modern numerical bootstrap uses adaptive search algorithms to map allowed regions and islands more efficiently than brute-force grids."
  active:
    - "Algorithmic development remains active, especially for high-dimensional islands, mixed correlators, spinning systems, rigorous certification, and integration with large-scale SDP workflows."
---

## Summary

Modern numerical bootstrap is not just one semidefinite program. A serious island or bound computation may require hundreds, thousands, or millions of feasibility tests. The question is therefore not only

$$
\text{Is this point excluded?}
$$

but also

$$
\text{Which points should we test next?}
$$

This page explains the search layer that sits above SDPB-style feasibility. It covers bisection, grid scans, adaptive triangulation, cutting surfaces, tiptop-style boundary finding, navigator functions, skydive-style searches, and the practical logic behind high-dimensional island hunts.

The main conceptual distinction is:

$$
\text{SDP solver}\quad\text{tests one point or optimization problem},
$$

while

$$
\text{search algorithm}\quad\text{organizes many solver calls into a map of theory space}.
$$

A good search algorithm reduces wasted solver calls, finds boundaries accurately, and gives a reproducible picture of allowed and excluded regions. A bad one can miss islands, overstate precision, or turn a numerical artifact into a plot with very confident axis labels. The goblin has upgraded to cartography.

## Prerequisites

Read [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), and [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/) first.

You should know the difference between an excluded point, a not-excluded point, a bound, and an island. You should also know that every exclusion point ultimately comes from a functional or SDP certificate under stated assumptions.

## Core idea

A bootstrap search problem has a parameter space. Coordinates might be operator dimensions,

$$
(\Delta_\sigma,\Delta_\epsilon),
$$

central charges,

$$
(C_T,C_J),
$$

OPE coefficients,

$$
(\lambda_{\sigma\sigma\epsilon},\lambda_{\epsilon\epsilon\epsilon}),
$$

or trial gaps in several sectors. At each point, one asks whether the crossing equations with the chosen assumptions are feasible or excluded.

A brute-force grid becomes expensive very quickly. If a parameter space has dimension $p$ and one uses $M$ sample points per direction, then the number of grid points is

$$
M^p.
$$

This exponential growth is the curse of dimensionality. Search algorithms are ways to avoid wasting computations far from the boundary or in already-understood regions.

The slogan is

$$
\text{bootstrap search}=\text{adaptive exploration of allowed/excluded geometry}.
$$

The underlying physics is still crossing symmetry. The algorithms are the scouting party.

## Setup and vocabulary

Let $x$ denote a point in parameter space. For example,

$$
x=(\Delta_\sigma,\Delta_\epsilon).
$$

At fixed $x$, the bootstrap feasibility problem returns one of several statuses:

| Status | Conservative interpretation |
|---|---|
| excluded | an excluding functional or certificate was found |
| not excluded | no exclusion certificate found at this cutoff and precision |
| solver failed | numerical status is inconclusive |
| boundary-like | search suggests the point lies near the allowed/excluded frontier |

The search algorithm uses these statuses to decide where to evaluate next.

The boundary of the allowed region is the set of points where the answer changes from excluded to not excluded. At finite cutoff and precision, this boundary is approximate. Modern search algorithms try to resolve it efficiently.

The output might be:

- a one-dimensional bound curve;
- a two-dimensional island;
- a high-dimensional allowed body;
- a navigator minimum;
- a collection of certified excluded regions;
- candidate spectra along a boundary.

None of these outputs is independent of assumptions, cutoffs, and solver settings.

## Bisection

Bisection is the simplest search algorithm for one-dimensional bounds. Suppose we want to find the largest scalar gap not excluded at fixed external dimension $\Delta_\phi$. Let the trial gap be $g$.

The procedure is:

1. Choose a lower value $g_{\rm low}$ that is not excluded.
2. Choose an upper value $g_{\rm high}$ that is excluded.
3. Test the midpoint

$$
g_{\rm mid}=\frac{g_{\rm low}+g_{\rm high}}{2}.
$$

4. If $g_{\rm mid}$ is excluded, replace $g_{\rm high}$ by $g_{\rm mid}$.
5. If $g_{\rm mid}$ is not excluded, replace $g_{\rm low}$ by $g_{\rm mid}$.
6. Repeat until the interval is small enough.

This works when exclusion is monotonic in the scanned parameter. For a scalar gap, increasing the gap removes allowed operators and should make exclusion easier. Thus the excluded region is expected to be one-sided.

Bisection is robust, easy, and boring in the best way. It is the hammer of one-dimensional bootstrap bounds.

## Grid scans

A grid scan evaluates a rectangular lattice of points in parameter space. For two parameters,

$$
x=(x_1,x_2),
$$

one samples

$$
x_1\in\{a_1,a_2,\ldots,a_M\},
\qquad
x_2\in\{b_1,b_2,\ldots,b_M\}.
$$

Then one colors each point excluded, not excluded, or inconclusive.

Grid scans are useful for first looks. They are easy to parallelize and simple to audit. But they are inefficient for thin islands or higher-dimensional spaces. If the island occupies a tiny fraction of the bounding box, most grid points are wasted.

A grid can also miss a small island entirely if the spacing is too coarse. This is why exploratory scans should not be confused with precision mapping.

The rule of thumb is:

$$
\text{grid scans are good for finding the continent, not surveying every coastline.}
$$

## Adaptive triangulation

Adaptive triangulation methods refine the search near boundaries. In two or more dimensions, one can triangulate sampled points and add new points where the current triangulation suggests the allowed/excluded boundary passes.

The basic idea is:

1. Start with a coarse set of sample points.
2. Classify them by feasibility.
3. Build a triangulation of parameter space.
4. Identify simplices whose vertices have different statuses.
5. Add new points inside or near those simplices.
6. Repeat.

This focuses solver calls where they matter: near the boundary.

Delaunay triangulation is a common geometric tool for building stable triangulations from scattered points. It avoids badly shaped simplices when possible and gives a systematic way to refine a sampled region.

Adaptive triangulation is especially useful when the boundary has unknown shape. It is less useful when the dimension becomes too large, because triangulations themselves become expensive and hard to visualize.

## Cutting-surface methods

Cutting-surface methods build an approximation to the allowed boundary by repeatedly adding cuts. A cut is a separating surface inferred from solver information, feasibility information, or local boundary probes.

The rough picture is:

$$
\text{start with a large region}
\quad\longrightarrow\quad
\text{cut away excluded pieces}
\quad\longrightarrow\quad
\text{approximate the allowed body}.
$$

This is natural when the allowed region is convex or approximately convex in the variables being used. In more complicated spaces, one must be careful because allowed regions may be nonconvex, disconnected, or thin.

Cutting surfaces are part of a broader algorithmic theme: use information from previous SDP solves to avoid treating every point as unrelated.

The bootstrap version of wisdom is:

$$
\text{every expensive solver call should teach the search algorithm where not to look next.}
$$

## Tiptop-style boundary searches

Tiptop-style methods are designed to efficiently locate boundaries or instability thresholds in bootstrap parameter spaces. The exact implementation details depend on the problem, but the philosophy is to use local boundary information and targeted updates rather than brute-force scanning.

These methods are useful when the physical question is not simply “map the whole island,” but something sharper, such as:

- locate the edge of stability for an anisotropy;
- determine when an allowed region disappears;
- find a critical gap value;
- resolve a narrow boundary feature.

The output is still conditional on the same bootstrap data: correlators, assumptions, derivative cutoff, spin treatment, and solver precision.

Tiptop-style searches are a reminder that many bootstrap questions are really boundary-location problems, not full-volume mapping problems.

## Navigator functions

A **navigator function** is a smooth diagnostic function on parameter space designed to distinguish allowed from excluded regions and guide searches efficiently.

A schematic navigator is a function

$$
\mathcal N(x)
$$

with a convention such as

$$
\mathcal N(x)<0\quad\text{inside the allowed region},
$$

$$
\mathcal N(x)>0\quad\text{outside the allowed region},
$$

and

$$
\mathcal N(x)=0\quad\text{near the boundary}.
$$

Different implementations may use different sign conventions. The point is not the sign; the point is that the navigator turns a feasibility landscape into something one can optimize and differentiate.

This is powerful in high-dimensional island searches. Instead of blindly sampling a grid, one can minimize or follow gradients of $\mathcal N(x)$ to find allowed regions, boundaries, or special points.

The navigator is not a new physical observable. It is an algorithmic object built from the bootstrap feasibility problem.

## What the navigator buys you

Navigator methods help with several hard tasks.

| Task | Why navigator helps |
|---|---|
| finding an island | minimization can move toward allowed regions |
| mapping a boundary | level sets of $\mathcal N$ approximate the frontier |
| high-dimensional scans | gradients guide search directions |
| optimizing irrelevant dimensions | one can navigate to extrema on an island |
| comparing families of CFTs | continuous movement in parameter space becomes practical |

For example, one may search for an island in a space such as

$$
(\Delta_\sigma,\Delta_\epsilon,\lambda_{\sigma\sigma\epsilon},\lambda_{\epsilon\epsilon\epsilon})
$$

or track an $O(N)$ family as $N$ varies.

Without a navigator, a high-dimensional search can be a foggy swamp of SDP calls. With a navigator, it becomes a foggy swamp with a compass. Still damp, but progress happens.

## Skydive-style searches

Skydive-style methods are designed to move efficiently from an excluded or exterior point toward an allowed region, especially in high-dimensional parameter spaces. The name evokes diving down toward the feasible set rather than mapping everything from the outside.

The rough logic is:

1. Start from a point or direction in parameter space.
2. Use feasibility or navigator-like information to choose a descent direction.
3. Move toward lower obstruction or more feasible values.
4. Adjust the path as solver feedback changes.
5. Land near or inside the allowed region.

The exact implementation is algorithm-dependent, but the physics role is clear: find islands or feasible regions that would be too expensive to locate by brute force.

Skydive-style methods are most useful when the allowed region is small, high-dimensional, or not well bracketed by simple one-dimensional scans.

## Search algorithms versus certificates

A search algorithm finds where to look. A bootstrap certificate proves exclusion at a point.

This distinction matters. A navigator value, triangulation, or skydive trajectory is not by itself an exclusion proof. The proof still comes from the underlying functional or SDP feasibility certificate.

The hierarchy is:

$$
\text{search heuristic}\quad\text{chooses trial points},
$$

$$
\text{SDP solve}\quad\text{tests each point},
$$

$$
\text{functional certificate}\quad\text{supports exclusion claims}.
$$

A final plot should therefore distinguish between:

- points actually solved;
- interpolated boundaries;
- heuristic navigator contours;
- certified exclusions;
- inconclusive or failed solves.

Search algorithms make bootstrap possible at scale. They do not remove the need for certification.

## High-dimensional islands

Many modern bootstrap targets require more than two parameters. For the 3D Ising CFT, one may care not only about

$$
(\Delta_\sigma,\Delta_\epsilon),
$$

but also OPE coefficients, irrelevant scalar dimensions, stress-tensor data, or gaps. For $O(N)$ models, one may track dimensions across $N$. For gauge-theory CFTs, one may include monopole dimensions, bilinear dimensions, current central charges, and several sector gaps.

High-dimensional islands are difficult because they cannot be fully visualized. One must use projections, slices, marginal ranges, or optimized quantities.

A common strategy is:

1. find a feasible interior point;
2. use navigator or local searches to locate boundaries;
3. optimize selected coordinates over the allowed region;
4. report intervals or slices;
5. check stability under cutoff and assumptions.

The plot is no longer the whole result. The algorithmic notebook becomes part of the scientific content.

## Choosing a search strategy

Different problems call for different search tools.

| Problem | Natural strategy |
|---|---|
| one-dimensional bound | bisection |
| first look in two dimensions | coarse grid scan |
| irregular two-dimensional island | adaptive triangulation |
| boundary of a stable island | cutting surface or boundary refinement |
| high-dimensional island | navigator or skydive-style method |
| optimizing one quantity over an island | navigator plus constrained search |
| checking a published bound | reproduce bisection or selected SDP points |

The best strategy is often hybrid. One might start with a grid, refine with triangulation, switch to a navigator for high-dimensional directions, and use bisection for final one-dimensional intervals.

A mature workflow does not worship one algorithm. It uses the simplest reliable tool for each stage.

## Reliability checks

Search algorithms introduce their own failure modes. In addition to solver precision and cutoff convergence, check:

| Check | What it catches |
|---|---|
| rerun selected boundary points | false interpolation or solver instability |
| vary search seed or initial grid | missed islands or path dependence |
| compare algorithms | algorithm-specific artifacts |
| refine near sharp corners | underresolved boundaries |
| record failed points | hidden numerical trouble |
| test known benchmark points | workflow sanity |
| increase cutoff on selected samples | finite-derivative artifacts |

A boundary drawn only by interpolation between sparse points is a hypothesis. A boundary supported by many stable solver calls is a result.

Search methods are wonderful, but they are not a substitute for paranoia. In numerical bootstrap, paranoia is just professionalism with better shoes.

## Common pitfalls

**Do not confuse search output with proof.** A navigator contour or triangulated boundary guides the search; exclusion still needs functional or SDP certificates.

**Do not use a brute-force grid in high dimension unless you enjoy expensive sadness.** The number of points grows exponentially with dimension.

**Do not ignore solver failures.** Failed points are data about numerical conditioning, not empty space to paint over.

**Do not overinterpolate thin islands.** A pretty smooth boundary may hide sparse sampling.

**Do not compare algorithms without matching assumptions.** Different gap assumptions, cutoffs, or precision settings can change the landscape.

**Do not report high-dimensional islands only through one projection.** Important structure may be lost in projection.

**Do not treat navigator sign conventions as universal.** Different papers may define the navigator with opposite signs or different normalizations.

## Relations to other pages

This page follows [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/) and prepares [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/), where cutoff dependence, solver precision, and assumption-driven uncertainty are treated systematically.

It also connects to [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), because search algorithms are how islands are mapped in practice, and to [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), because each search step usually triggers an SDP solve.

For physics applications, see [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), and [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/).

## Research status

Modern search algorithms are established as essential infrastructure for high-precision numerical bootstrap, especially for mixed-correlator islands and high-dimensional parameter spaces.

Active work develops faster and more reliable search methods, better integration with SDP solvers, certified boundary reconstruction, navigator-based optimization, skydive-style island finding, adaptive sampling, parallel workflows, and reproducibility standards for large bootstrap computations.

## Exercises

### Exercise 1

Why is bisection appropriate for a one-dimensional scalar gap bound?

<details><summary><strong>Solution</strong></summary>

A scalar gap bound is usually monotonic in the trial gap. Increasing the assumed gap removes operators from the allowed spectrum, making crossing harder to satisfy and exclusion easier. Therefore there is a transition between not-excluded lower gaps and excluded higher gaps. Bisection efficiently locates this transition by repeatedly testing midpoints.

</details>

### Exercise 2

Explain why a grid scan becomes inefficient in high dimension.

<details><summary><strong>Solution</strong></summary>

If one samples $M$ points along each of $p$ parameter directions, the total number of grid points is

$$
M^p.
$$

This grows exponentially with dimension. For large $p$, most grid points may lie far from the allowed boundary or miss a small island entirely. Adaptive algorithms try to place points where they are informative.

</details>

### Exercise 3

What is the difference between a navigator function and a physical CFT observable?

<details><summary><strong>Solution</strong></summary>

A navigator function is an algorithmic diagnostic built from a bootstrap feasibility problem. It helps search parameter space by indicating allowed and excluded regions or guiding gradients. It is not a local operator, OPE coefficient, central charge, or observable of the CFT. Its value depends on the bootstrap setup, normalization, cutoff, and implementation.

</details>

### Exercise 4

Why should failed solver points be recorded during a search?

<details><summary><strong>Solution</strong></summary>

Solver failures may indicate numerical conditioning problems, insufficient precision, bad block approximations, or proximity to a thin boundary. Ignoring them can make an allowed region look cleaner than it really is. Recording failed points helps diagnose reliability and prevents accidental overinterpretation of interpolated plots.

</details>

### Exercise 5

Give two reasons why a high-dimensional island should not be reported only as a two-dimensional projection.

<details><summary><strong>Solution</strong></summary>

A projection can hide correlations between parameters, merge disconnected components, or make a thin region look larger than it is. It can also hide which assumptions or gap directions determine the allowed range. Reporting slices, optimized intervals, and the search procedure gives a more faithful description of the high-dimensional allowed region.

</details>

## References

- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- W. Landry and D. Simmons-Duffin, “Scaling the semidefinite program solver SDPB,” 2019.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.

## Version history

- 2026-07-01: First polished draft. Added bisection, grid scans, adaptive triangulation, cutting-surface methods, tiptop-style searches, navigator functions, skydive-style searches, high-dimensional island strategy, reliability checks, exercises, and references.
