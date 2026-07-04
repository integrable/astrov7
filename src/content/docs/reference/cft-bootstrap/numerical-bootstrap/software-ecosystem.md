---
title: "Software Ecosystem"
description: "A map of the numerical conformal bootstrap software ecosystem, including block generators, workflow frameworks, SDP solvers, search tools, reproducibility practices, and what each layer does."
sidebar:
  label: "Software Ecosystem"
  order: 14
level: Graduate
status: "Polished draft"
source: "SDPB literature; Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; public numerical-bootstrap software documentation."
topics:
  - numerical conformal bootstrap
  - software ecosystem
  - SDPB
  - conformal blocks
  - reproducibility
canonicalTopics:
  - software-ecosystem
  - numerical-bootstrap-software
  - bootstrap-reproducibility
researchStatus:
  established:
    - "Modern numerical bootstrap computations use a layered software ecosystem: conformal block generation, crossing-equation assembly, SDP solving, search algorithms, and post-processing."
  active:
    - "Software changes quickly, so exact package names, commands, versions, and best practices should be checked against current project documentation before running production computations."
---

## Summary

The numerical conformal bootstrap has a software stack. A solver such as SDPB is only one layer. A real computation also needs conformal block generation, crossing-equation assembly, polynomial-matrix-program construction, search scripts, post-processing, plotting, logging, and reproducibility tools.

The conceptual pipeline is

$$
\text{CFT problem}
\to
\text{crossing equations}
\to
\text{block data}
\to
\text{polynomial matrix program}
\to
\text{SDP solver}
\to
\text{search and interpretation}.
$$

Different software packages live at different points in this pipeline. Some generate scalar conformal blocks. Some assemble bootstrap equations. Some run semidefinite programs. Some navigate high-dimensional islands. Some visualize results or extract spectra.

This page is a map, not an installation manual. Software changes faster than physics notation, which is impressive because physics notation is already a tiny chaos goblin. For commands, flags, file formats, and current versions, always check the official documentation of the package you are using.

## Prerequisites

Read [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/), [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/), and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/) first.

You should know what conformal blocks, derivative truncations, linear functionals, polynomial matrix programs, and SDP feasibility tests are.

## Core idea

Do not think of numerical bootstrap software as one program. Think of it as a layered instrument.

| Layer | Job |
|---|---|
| physics specification | choose CFT, external operators, symmetries, gaps, objective |
| symbolic/group-theory layer | build crossing equations and sector decompositions |
| conformal-block layer | compute block derivatives or rational approximations |
| SDP-input layer | assemble polynomial matrix programs |
| solver layer | test feasibility or optimize objectives |
| search layer | scan, bisect, navigate, or map islands |
| post-processing layer | plot bounds, extract spectra, report uncertainty |
| reproducibility layer | record versions, settings, inputs, logs, and outputs |

A failure in any layer can spoil the final result. A solver can be perfect and still optimize the wrong crossing equations. A block generator can be accurate and still be used with the wrong normalization. A search algorithm can be clever and still miss an island if the assumptions are wrong.

The ecosystem mindset is:

$$
\text{every software layer is part of the scientific claim}.
$$

## Block generators

Conformal blocks are the special functions of the bootstrap. The software stack needs their derivatives at the crossing-symmetric point or related approximations.

Block-generation tools may provide:

- scalar conformal blocks in arbitrary or fixed dimension;
- three-dimensional blocks with spin and parity structures;
- recursion relations or radial-coordinate expansions;
- rational approximations in $\Delta$;
- derivatives up to a cutoff $\Lambda$;
- normalization conventions compatible with downstream solvers.

The output is usually not a plot of a block. It is data used to build positivity constraints such as

$$
\alpha(\vec F_{\Delta,\ell})\ge0
$$

or

$$
M_{\Delta,\ell}(\alpha)\succeq0.
$$

Block data are easy to take for granted and hard to debug. If a bound looks wrong, block conventions are one of the first suspects.

## Crossing-equation frameworks

A crossing-equation framework helps assemble the algebraic problem. It knows about external operators, tensor structures, global symmetry sectors, parity selection rules, and OPE-channel bookkeeping.

For an $O(N)$ model, such a framework must know the decomposition

$$
\phi_i\times\phi_j=S+T+A.
$$

For an Ising mixed system, it must know

$$
\sigma\times\sigma=\text{even},
\qquad
\epsilon\times\epsilon=\text{even},
\qquad
\sigma\times\epsilon=\text{odd}.
$$

For spinning systems, it must handle tensor structures. For supersymmetric systems, it may use superconformal blocks or multiplet selection rules.

Examples of framework-style tools in the literature include names such as autoboot, simpleboot, hyperion, and related packages. Their exact scope and status should be checked from current documentation.

The main point is architectural: large bootstrap projects need software that prevents hand-written crossing equations from becoming a haunted spreadsheet.

## SDP solvers

The solver layer takes a polynomial matrix program and attempts to solve it. SDPB is the best-known solver designed specifically for conformal bootstrap semidefinite programs.

A solver may report primal and dual feasibility, objective values, residuals, duality gaps, and numerical failure modes. In the common exclusion interpretation, a suitable dual feasible solution corresponds to an excluding functional.

The solver does not know what the 3D Ising model is. It sees matrices, polynomials, variables, and precision settings. The physics interpretation comes from the input construction and the post-processing.

Important solver settings include:

| Setting | Why it matters |
|---|---|
| arithmetic precision | controls numerical stability |
| stopping tolerances | affects feasibility status near boundaries |
| checkpointing | protects long runs |
| parallelism | controls runtime and memory use |
| primal-dual settings | affects convergence behavior |
| normalization choices | affects conditioning |

A solver log is part of the result. Keep it.

## Search and navigation tools

Search tools organize many solver calls. They are used to find bounds, islands, and extrema.

Common search patterns include:

| Search method | Use |
|---|---|
| bisection | one-dimensional bounds |
| grid scan | first look in low-dimensional spaces |
| adaptive triangulation | refine two-dimensional boundaries |
| cutting surface | iteratively approximate allowed regions |
| navigator function | guide high-dimensional searches |
| skydive-style methods | approach small feasible regions efficiently |
| constrained optimization | optimize one datum over an island |

Search tools do not replace SDP certificates. They decide where to ask for certificates.

A final plot should make clear which points were actually solved and which boundary curves were interpolated or inferred. Otherwise the search layer can accidentally turn sparse samples into overconfident geography.

## Post-processing and spectrum extraction

After solver runs, one needs post-processing.

Post-processing tasks include:

- parse solver statuses;
- identify excluded and not-excluded points;
- plot bounds or islands;
- fit cutoff sequences;
- compare assumptions;
- extract extremal spectra;
- estimate OPE coefficients;
- compute derived critical exponents;
- write tables with uncertainties.

For the 3D Ising CFT, once one has ranges for

$$
\Delta_\sigma,
\qquad
\Delta_\epsilon,
$$

one may compute

$$
\eta=2\Delta_\sigma-1,
$$

and

$$
\nu=\frac{1}{3-\Delta_\epsilon}.
$$

Post-processing should preserve provenance. A number in a table should know which cutoff, assumptions, block data, solver settings, and scan produced it. Future-you is a stakeholder. Future-you is also easily annoyed.

## Reproducibility tools

A reproducible bootstrap computation records the full chain from assumptions to plots. This usually requires ordinary software-engineering discipline:

- version control;
- tagged input files;
- machine-readable parameter files;
- solver logs;
- plotting scripts;
- environment records;
- random seeds or deterministic search settings;
- checksums for large generated data;
- README files explaining how to rerun key steps.

For small calculations, this may feel excessive. For precision islands, it is survival equipment.

A minimal directory structure for a project might separate:

```txt
inputs/
blocks/
sdp/
runs/
logs/
plots/
notebooks/
```

The exact names do not matter. The separation of roles does.

## Common package roles

The following names occur in the numerical-bootstrap literature and software discussions. This table is meant as orientation, not a current compatibility chart.

| Name or category | Typical role |
|---|---|
| SDPB | high-precision semidefinite-program solver for bootstrap polynomial matrix programs |
| scalar block tools | generate scalar conformal block derivatives and approximations |
| blocks 3d-style tools | generate three-dimensional conformal blocks for selected systems |
| autoboot-style frameworks | automate crossing-equation and SDP-input generation |
| simpleboot-style frameworks | provide accessible bootstrap setup and experimentation tools |
| hyperion-style tools | support larger or more automated bootstrap workflows |
| navigator implementations | search high-dimensional allowed regions |
| plotting notebooks | visualize bounds, islands, and convergence |
| custom scripts | glue everything together, often project-specific |

Names, APIs, installation methods, and maintenance status change. Always check the repository or documentation before relying on a package.

## Choosing tools

Choose software based on the physics problem, not the other way around.

| Problem | Software needs |
|---|---|
| identical scalar bound | scalar blocks, simple crossing setup, SDP solver, bisection |
| Ising mixed island | mixed crossing framework, matrix positivity, high precision, search tools |
| $O(N)$ bootstrap | global-symmetry tensor structures, sector gaps, mixed systems |
| spinning correlators | spinning conformal blocks and tensor-structure handling |
| supersymmetric bootstrap | superblocks or multiplet constraints |
| gauge-theory bootstrap | global symmetry, monopoles or bilinears, often custom sectors |
| reproduction project | exact target assumptions, versions, and settings |

The best tool is the one that makes the intended crossing problem explicit and auditable. Fancy automation is useful only if you can still inspect what it generated.

## Installation and environments

Production bootstrap software may require compiled dependencies, arbitrary-precision arithmetic, MPI, cluster schedulers, or containerized environments. Installation instructions change, so this page does not provide commands.

Good environment practice includes:

| Practice | Why |
|---|---|
| pin software versions | results depend on generated inputs and solver behavior |
| record compiler and library versions | high-precision software can be environment-sensitive |
| use containers when practical | improves portability |
| save generated input files | avoids regenerating with changed code accidentally |
| archive logs and settings | makes results auditable |
| test a known benchmark | catches installation mistakes |

The first run of any setup should be a small benchmark, not a heroic island search. Make sure the bicycle has wheels before entering the mountain stage.

## Documentation habits

Every project should document the full sentence it computes. For example:

> We test unitary $d=3$ $\mathbb Z_2$-symmetric CFTs with external scalars $\sigma$ and $\epsilon$, imposing these gaps, using this derivative cutoff, this spin list, these block-generation settings, and this solver precision.

This sentence should appear in a README, paper draft, or notebook before the first plot.

Documentation should also explain:

- how to regenerate block data;
- how to create SDP inputs;
- how to launch solver runs;
- how to parse statuses;
- how to reproduce each figure;
- which files are too large to store directly;
- which outputs are intermediate and which are final.

Documentation is not decoration. It is how a computation becomes reusable knowledge.

## Common pitfalls

**Do not call SDPB “the bootstrap.”** SDPB is a solver layer. The bootstrap includes crossing equations, assumptions, block data, searches, and interpretation.

**Do not trust generated equations without inspection.** Automation can faithfully automate a mistake.

**Do not mix block conventions accidentally.** Normalizations must be consistent across block generation, crossing equations, and OPE data.

**Do not update software mid-project without recording it.** Version drift can change inputs or outputs.

**Do not hide custom glue scripts.** They often contain the most project-specific assumptions.

**Do not treat package names as stable physics.** Software evolves. The physics claim should be stated independently of the tool that computed it.

**Do not skip small benchmark tests.** Reproduce a known simple bound before attempting a new high-dimensional island.

## Relations to other pages

This page follows [Reproducing the 3D Ising Island](/cft-bootstrap/numerical-bootstrap/reproducing-the-3d-ising-island/) and closes the first numerical-bootstrap sequence by mapping the computational ecosystem.

It connects back to [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/), [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/), and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/).

For broader computational methods, see [Computational CFT and Bootstrap](/cft-bootstrap/computational-cft-bootstrap/) when that chapter is expanded.

## Research status

The numerical-bootstrap software ecosystem is mature enough to support high-precision results in benchmark systems, especially scalar and mixed-correlator bootstrap. SDPB-style solvers and block-generation frameworks are standard tools.

Active work continues on scalability, automation, reproducibility, rigorous certification, spinning blocks, high-dimensional search, integration with analytic bootstrap, and workflows for gauge-theory, defect, boundary, and supersymmetric systems.

## Exercises

### Exercise 1

Explain why SDPB is not the whole numerical bootstrap workflow.

<details><summary><strong>Solution</strong></summary>

SDPB solves semidefinite programs. A full bootstrap workflow also requires specifying the CFT assumptions, deriving crossing equations, generating conformal block data, assembling polynomial matrix programs, choosing search algorithms, parsing solver output, checking convergence, and interpreting the result. SDPB is the solver layer, not the entire pipeline.

</details>

### Exercise 2

List four software layers in a numerical bootstrap project.

<details><summary><strong>Solution</strong></summary>

Examples include the physics-specification layer, crossing-equation framework, conformal-block generator, SDP-input generator, SDP solver, search or navigator layer, post-processing scripts, plotting tools, and reproducibility infrastructure. Any four are acceptable.

</details>

### Exercise 3

Why should block-generation settings be recorded?

<details><summary><strong>Solution</strong></summary>

The solver uses block derivative data as input. If the block approximation order, normalization, derivative basis, or precision changes, the SDP input can change. Recording block-generation settings makes the result reproducible and helps diagnose discrepancies between runs or between different groups.

</details>

### Exercise 4

Why is a small benchmark run useful after installing bootstrap software?

<details><summary><strong>Solution</strong></summary>

A benchmark run tests that the software, dependencies, precision settings, block generation, and solver interface are working. If the setup cannot reproduce a known simple result, then a new high-dimensional island calculation is not trustworthy. Benchmarks catch installation and convention mistakes early.

</details>

### Exercise 5

What information should a plot script preserve or be able to recover?

<details><summary><strong>Solution</strong></summary>

A plot script should preserve or recover which solver points were used, their statuses, the assumptions and gaps, derivative cutoff, spin treatment, block settings, solver precision, search method, and whether displayed boundaries are direct solves or interpolation. This prevents a plot from losing the provenance of the numerical result.

</details>

## References

- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- W. Landry and D. Simmons-Duffin, “Scaling the semidefinite program solver SDPB,” 2019.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.

## Version history

- 2026-07-01: First polished draft. Added software-stack map, block-generator and framework roles, SDPB solver context, search and post-processing layers, reproducibility practices, package-role orientation, documentation habits, exercises, and references.
