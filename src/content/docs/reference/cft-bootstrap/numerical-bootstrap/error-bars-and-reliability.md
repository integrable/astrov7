---
title: "Error Bars and Reliability"
description: "How to interpret numerical bootstrap precision, cutoff dependence, solver tolerances, assumptions, systematic uncertainty, and reproducibility."
sidebar:
  label: "Error Bars and Reliability"
  order: 12
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; SDPB literature; numerical bootstrap reproducibility and precision studies."
topics:
  - numerical conformal bootstrap
  - error bars
  - reliability
  - reproducibility
  - cutoff convergence
canonicalTopics:
  - error-bars-and-reliability
  - bootstrap-reliability
  - numerical-bootstrap-uncertainty
researchStatus:
  established:
    - "Numerical bootstrap results are conditional on crossing equations, assumptions, derivative cutoff, spin treatment, block approximations, and solver precision."
  active:
    - "Reliable uncertainty quantification, rigorous certification, finite-cutoff extrapolation, reproducibility standards, and high-dimensional island error analysis remain active practical and conceptual issues."
---

## Summary

Numerical bootstrap results often quote tiny intervals for operator dimensions and OPE coefficients. These numbers can be extremely precise, but their meaning is not the same as an experimental one-sigma error bar.

A bootstrap “error bar” usually combines several ingredients:

| Ingredient | Meaning |
|---|---|
| allowed interval | region not excluded at a chosen cutoff and assumptions |
| cutoff dependence | change as derivative order or spin treatment improves |
| solver tolerance | numerical precision of the SDP solve |
| block approximation error | accuracy of conformal block derivative data |
| scan resolution | how finely a boundary or island was mapped |
| assumption dependence | how gaps and spectral hypotheses affect the result |
| extrapolation | estimate of the infinite-cutoff limit |

The central warning is

$$
\text{more digits}\ne\text{more truth unless the systematics are controlled}.
$$

This page explains how to read bootstrap precision responsibly: what can be certified, what is numerical, what is assumption-driven, and what should be checked before quoting a result as CFT data.

## Prerequisites

Read [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/), [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), and [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/) first.

You should know that a numerical bootstrap result is produced by a finite derivative cutoff, finite precision, conformal block approximations, and explicit assumptions about the spectrum.

## Core idea

A bootstrap computation is a conditional mathematical-numerical statement. It has the form:

> Under these assumptions, with this crossing system, at this cutoff and precision, these parameter values are excluded or not excluded.

A high-quality result then studies how this statement changes as the numerical setup improves. The goal is to infer something about the exact bootstrap problem:

$$
\Lambda\to\infty,
\qquad
\ell_{\max}\to\infty,
\qquad
\text{block error}\to0,
\qquad
\text{solver tolerance}\to0.
$$

In practice, one never reaches this limit exactly. One builds evidence through convergence, independent checks, benchmark comparisons, and reproducibility.

The slogan is

$$
\text{reliability}=\text{assumptions stated}+\text{numerics controlled}+\text{convergence checked}.
$$

This is less glamorous than a tiny island plot, but it is what makes the tiny island worth trusting.

## Types of uncertainty

Bootstrap uncertainty is not one thing. It is a stack.

| Type | Source | Typical diagnostic |
|---|---|---|
| feasibility uncertainty | solver tolerances and precision | primal/dual residuals, reruns |
| truncation uncertainty | finite derivative cutoff $\Lambda$ | compare several $\Lambda$ values |
| spin uncertainty | finite spin list or large-spin treatment | vary spin handling |
| block uncertainty | rational approximation or recursion error | increase block precision/order |
| search uncertainty | coarse grid or adaptive sampling | refine boundary samples |
| assumption uncertainty | imposed gaps and operator ordering | vary assumptions |
| interpretation uncertainty | kink, island, extremal spectrum | compare methods and spectra |

A single quoted number may depend on all of these. The cleanest papers separate them as much as possible.

For example, an interval in an island may be narrow at fixed $\Lambda$, but the island may shift when $\Lambda$ increases. The final uncertainty should reflect the latter, not only the former.

## Finite cutoff dependence

Derivative cutoff is usually the dominant systematic in a mature computation. A bound at cutoff $\Lambda$ is not the infinite-cutoff answer.

One should examine sequences such as

$$
B_{\Lambda=19},\quad
B_{\Lambda=27},\quad
B_{\Lambda=35},\quad
B_{\Lambda=43}.
$$

If the bound stabilizes, confidence grows. If it drifts, the result is not yet converged. If it changes nonmonotonically, one should investigate whether the derivative spaces are nested, whether solver precision is adequate, and whether block approximations changed between runs.

For islands, one should check whether the island:

- persists at higher $\Lambda$;
- shrinks in a controlled way;
- moves by less than the quoted uncertainty;
- keeps the same qualitative shape;
- remains compatible with extracted spectra.

A precision island at one cutoff is a snapshot. A precision result is a controlled movie.

## Solver precision and tolerances

SDP solvers work with finite arithmetic and stopping criteria. They report quantities such as primal residuals, dual residuals, duality gaps, objective values, and feasibility statuses.

A solver status should be read together with the requested precision. For a point near a boundary, small changes in tolerances or arithmetic precision can change the reported status.

Good practice includes:

| Check | Purpose |
|---|---|
| rerun boundary points at higher precision | test fragile exclusions |
| compare primal and dual residuals | diagnose numerical consistency |
| inspect duality gap | check optimization quality |
| use checkpointing and restart | test stability of long runs |
| keep solver logs | make results auditable |
| rerun selected points independently | catch machine or setup problems |

A beautiful plot with no solver logs is a little like a theorem whose proof is “trust me, bro.” The theorem may be true. Still: logs, please.

## Conformal block accuracy

Bootstrap solvers do not manipulate exact conformal blocks in closed form for every dimension and spin. They use numerical, recursive, or rational approximations to block derivatives.

Errors in block data can shift bounds or create false feasibility statuses. This is especially important at high derivative order, high spin, or in mixed systems with delicate cancellations.

Block reliability checks include:

- increasing radial expansion order;
- increasing pole order in rational approximations;
- comparing independent block generators;
- checking known limits such as generalized free fields;
- testing conserved-current and stress-tensor blocks;
- verifying normalization conventions;
- confirming positivity at sample dimensions.

The block generator is part of the scientific instrument. Calibrate it.

## Spin treatment

The operator spectrum contains infinitely many spins. A numerical setup typically handles low spins explicitly and treats high spin by a finite list, asymptotic arguments, or solver-specific positivity conditions.

Spin-related uncertainty can enter when:

- the spin list is too short;
- high-spin asymptotics are not controlled;
- odd or even spin selection rules are misapplied;
- global symmetry sectors have different spin parities;
- conserved currents or stress tensors are omitted or duplicated.

For identical scalar external operators, only even spins appear in the identical OPE. For mixed external operators, odd spins may appear. For spinning external operators, the spin bookkeeping becomes richer.

A reliability report should state the spin list and large-spin treatment. The symbol $\Lambda$ alone is not enough.

## Search resolution

An island boundary is often found by scanning or navigating parameter space. If the scan is coarse, the boundary is approximate even if every sampled point was solved accurately.

Search uncertainty includes:

| Issue | Example |
|---|---|
| grid spacing | island smaller than grid cells |
| interpolation | smooth boundary inferred from sparse points |
| missed components | another island lies outside sampled region |
| failed points | solver failures hidden by interpolation |
| projection | high-dimensional region projected to two dimensions |
| seed dependence | adaptive algorithm depends on starting points |

A high-quality plot distinguishes solved points from interpolated regions. It also reports how the search was performed.

When possible, quote intervals obtained by explicit optimization or boundary refinement rather than eyeballing a figure. Eyeballs are wonderful but not a numerical method.

## Assumption dependence

The most subtle uncertainty is often not numerical. It is assumption dependence.

A bootstrap island may rely on assumptions such as

$$
\Delta_{\epsilon'}\ge g_1,
\qquad
\Delta_{\sigma'}\ge g_2,
$$

or uniqueness of a stress tensor, or absence of additional conserved currents, or a particular global symmetry representation ordering.

Changing these assumptions can move, enlarge, shrink, or destroy the island. That does not make the result bad. It means the result is conditional.

Good practice is to perform gap scans. Vary a gap and observe how the allowed region responds. If the result is stable over a physically motivated range, confidence grows. If the result exists only for one aggressive gap value, it should be labeled exploratory.

A result should say:

$$
\text{under these gap assumptions, the allowed region is...}
$$

not merely

$$
\text{the CFT has these dimensions.}
$$

## Error bars in islands

An island gives a finite allowed region. A quoted interval such as

$$
\Delta_\sigma=0.5181488(3)
$$

should be understood as a summary of an allowed range under specified assumptions and numerical settings, possibly combined with extrapolation.

There are several possible meanings of parentheses:

| Notation source | Meaning |
|---|---|
| island width at fixed cutoff | finite allowed range in one projection |
| extrapolated width | estimate after $\Lambda\to\infty$ trend |
| conservative envelope | union over cutoffs or assumptions |
| statistical fit uncertainty | uncertainty from fitting a convergence model |
| literature convention | shorthand requiring explanation |

Always check the paper's definition. There is no universal bootstrap equivalent of an experimental standard deviation.

For QFT.org pages, avoid quoting many digits unless the source and meaning of the uncertainty are clear.

## Extrapolation

To estimate the infinite-cutoff limit, one may fit a sequence of bounds or island coordinates as a function of $\Lambda$. A schematic model might be

$$
X_\Lambda=X_\infty+\frac{a}{\Lambda^p}+\cdots .
$$

But the exponent $p$ and correction structure may not be known. Fits can be unstable if only a few cutoff values are available.

Extrapolation should therefore be treated as a model, not a miracle. Good extrapolation practice includes:

- using several fit forms;
- excluding low-cutoff points and checking stability;
- reporting raw cutoff data;
- comparing with independent methods;
- using conservative envelopes when appropriate;
- avoiding extra digits not supported by the trend.

If the extrapolated value changes significantly when one removes one data point, the error bar should not be tiny. The numbers are whispering. Listen.

## Spectrum-extraction reliability

Extremal functional spectra are even more delicate than bound locations. A zero of a functional at finite cutoff may be a physical operator, a degenerate cluster, or a numerical artifact.

Reliability checks include:

| Check | Meaning |
|---|---|
| zero stability with $\Lambda$ | candidate dimension converges |
| OPE positivity | extracted squared coefficients are nonnegative |
| derivative-subset stability | coefficients do not depend wildly on chosen equations |
| Ward identity checks | stress tensor and currents have correct couplings |
| mixed-system consistency | same operator appears across related correlators |
| gap sensitivity | extracted operator is not imposed by hand |

High-dimension operators generally converge more slowly than low-dimension ones. Near-degenerate spectra require extra care. In mixed systems, one must also extract OPE-vector directions and matrix kernels.

Spectrum extraction is valuable. It is not as clean as exclusion.

## Reproducibility

A result is reproducible when another researcher can reconstruct the computation well enough to verify it. Minimal reproducibility data include:

| Item | Example |
|---|---|
| crossing equations | correlator system and sector decomposition |
| external data | dimensions, spins, global representations |
| assumptions | gaps, protected operators, uniqueness assumptions |
| derivative basis | definition of $\Lambda$ and derivative set |
| spin treatment | explicit spin list and high-spin handling |
| block generation | code, version, precision, approximation order |
| solver | SDPB or other solver version and settings |
| search algorithm | grid, bisection, navigator, cutting surface |
| raw statuses | excluded, not excluded, failed points |
| scripts or inputs | enough to rerun key points |

Reproducibility is not busywork. It is how a numerical result becomes part of the literature rather than a screenshot with ambition.

## Conservative reporting

When reporting a bootstrap result, prefer conservative language:

| Stronger than justified | Better phrasing |
|---|---|
| “we prove the CFT exists here” | “points outside this region are excluded under these assumptions” |
| “the error bar is statistical” | “the interval is the allowed range at this cutoff and assumptions” |
| “the kink is the theory” | “the kink is consistent with this candidate CFT” |
| “the island is exact” | “the island is stable under the cutoffs tested” |
| “the spectrum is extracted” | “the extremal spectrum suggests these operator dimensions” |
| “no solution exists” | “no solution exists in the tested bootstrap setup” |

Precision and humility are not enemies. They are roommates. Occasionally one leaves dishes in the sink, but the arrangement works.

## Common pitfalls

**Do not equate a finite-cutoff island with an exact CFT solution.** It is a conditional allowed region in a truncated problem.

**Do not quote digits without explaining their origin.** State whether the interval is fixed-cutoff, extrapolated, or an envelope over assumptions.

**Do not hide solver failures.** Failed points can change the interpretation of a boundary.

**Do not ignore gap dependence.** Assumptions can dominate numerical uncertainty.

**Do not compare error bars from different bootstrap systems without matching assumptions.** Different correlators and gaps give different conditional statements.

**Do not overtrust high-dimension extremal zeros.** They are more sensitive to cutoff and numerical noise.

**Do not treat reproducibility as optional.** Input files, settings, and raw statuses are part of the result.

## Relations to other pages

This page follows [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/) and prepares [Reproducing the 3D Ising Island](/cft-bootstrap/numerical-bootstrap/reproducing-the-3d-ising-island/) and [Software Ecosystem](/cft-bootstrap/numerical-bootstrap/software-ecosystem/).

It also connects back to [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), and [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/).

For physics examples where reliability language matters, see [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), and [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/).

## Research status

The main sources of numerical-bootstrap uncertainty are well understood: finite derivative cutoff, solver precision, conformal block approximation, spin treatment, search resolution, and spectral assumptions. High-quality studies routinely test many of these effects.

Active research seeks sharper certification, better extrapolation methods, more robust high-dimensional island mapping, standardized reproducibility practices, rigorous error estimates, and better integration between numerical and analytic bootstrap constraints.

## Exercises

### Exercise 1

Why is a bootstrap error bar not automatically a statistical one-sigma error bar?

<details><summary><strong>Solution</strong></summary>

A bootstrap interval usually comes from an allowed region under crossing, unitarity, assumptions, cutoff, and numerical precision. It is not produced by repeated noisy measurements with a probability distribution. Its width may reflect finite cutoff, scan resolution, assumptions, or extrapolation. Therefore its meaning must be defined by the computation that produced it.

</details>

### Exercise 2

List three sources of systematic uncertainty in a numerical bootstrap island.

<details><summary><strong>Solution</strong></summary>

Examples include finite derivative cutoff, finite spin treatment, conformal block approximation error, solver tolerances, scan resolution, imposed gap assumptions, and extrapolation model dependence. Any three are acceptable.

</details>

### Exercise 3

Why should one vary gap assumptions when interpreting an island?

<details><summary><strong>Solution</strong></summary>

Gap assumptions remove operators from the allowed spectrum. If the island changes dramatically when a gap is varied, then the result is strongly assumption-dependent. Varying gaps shows which features are forced robustly by crossing and which are driven by the chosen spectral hypotheses.

</details>

### Exercise 4

What does it mean if a bound is stable as $\Lambda$ increases?

<details><summary><strong>Solution</strong></summary>

It means that increasing the derivative search space changes the bound only slightly. This is evidence that the finite-cutoff result is approaching the infinite-cutoff bootstrap bound. It does not prove exact convergence by itself, but it increases confidence in the numerical result.

</details>

### Exercise 5

Give five items needed to reproduce a bootstrap computation.

<details><summary><strong>Solution</strong></summary>

Examples include crossing equations, external operators, global symmetry sectors, imposed gaps, derivative cutoff and basis, spin list, conformal block generator and settings, solver version, precision and tolerances, search algorithm, input files, and raw solver statuses. Any five are acceptable.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- W. Landry and D. Simmons-Duffin, “Scaling the semidefinite program solver SDPB,” 2019.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.

## Version history

- 2026-07-01: First polished draft. Added uncertainty taxonomy, cutoff and solver precision guidance, block and spin reliability checks, search-resolution and assumption-dependence discussion, extrapolation caveats, reproducibility checklist, conservative reporting guidance, exercises, and references.
