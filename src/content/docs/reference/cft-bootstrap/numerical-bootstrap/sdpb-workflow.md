---
title: 'SDPB Workflow'
description: 'A conceptual workflow for preparing, running, checking, and interpreting SDPB-style semidefinite programs in numerical conformal bootstrap calculations.'
sidebar:
  label: 'SDPB Workflow'
  order: 6
level: Graduate
status: 'Polished draft'
source: 'Simmons-Duffin 2015; Landry and Simmons-Duffin 2019; Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; SDPB documentation.'
topics:
  - SDPB
  - numerical conformal bootstrap
  - semidefinite programming
  - bootstrap workflow
  - reproducibility
canonicalTopics:
  - sdpb-workflow
  - bootstrap-software-workflow
  - numerical-bootstrap-reproducibility
researchStatus:
  established:
    - 'SDPB-style workflows are standard in high-precision numerical bootstrap computations based on polynomial matrix programs.'
  active:
    - 'Active work improves automation, block generation, solver scaling, navigator integration, certified outputs, reproducibility, and workflows for large mixed-correlator systems.'
---

## Summary

**SDPB** is a specialized semidefinite-programming solver built for numerical conformal bootstrap problems. An SDPB workflow takes crossing equations, derivative truncations, conformal block approximations, positivity constraints, and spectral assumptions, then turns them into a polynomial matrix program that a solver can test.

The workflow is not magic. It is a pipeline:

$$
\text{physics assumptions}
\to
\text{crossing equations}
\to
\text{derivative vectors}
\to
\text{polynomial matrix program}
\to
\text{SDP solve}
\to
\text{physics interpretation}.
$$

At the end, the solver may find a dual feasible solution, which often means an excluding functional exists. Or it may fail to find one, which means the point is not excluded at the chosen cutoff and precision.

The most important lesson is

$$
\text{SDPB output is evidence inside a specified bootstrap setup, not a standalone physics theorem.}
$$

A responsible workflow records the correlators, assumptions, gaps, derivative cutoff, spin treatment, block approximation, precision, solver settings, and convergence checks.

## Prerequisites

Read [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) first. You should also know [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/) and [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/).

This page is a conceptual workflow, not a replacement for official SDPB documentation or cluster-specific instructions. Command-line flags, file formats, and helper packages can change. Always check the documentation for the exact software version used in a real project.

## Core idea

The physics part of a bootstrap problem is continuous and infinite-dimensional. The solver needs a finite algebraic problem. The workflow translates between them.

A typical bootstrap question begins as:

> Given a unitary CFT in dimension $d$ with specified external operators and spectral gaps, can crossing be satisfied?

The numerical workflow converts this into:

> Is there a feasible solution to a semidefinite program built from derivative-truncated conformal block vectors and positivity constraints?

The result is then translated back:

| Solver-side result | Physics-side interpretation |
|---|---|
| excluding dual functional found | assumptions are ruled out at this cutoff and precision |
| no excluding functional found | assumptions are not excluded by this run |
| stable boundary under increasing cutoff | candidate robust bound |
| small stable allowed region | candidate island under stated assumptions |
| unstable or failed solve | numerical setup needs diagnosis |

The workflow is only as trustworthy as the weakest link in this translation chain.

## Stage 1: choose the bootstrap problem

Before touching software, specify the physics problem. This includes:

| Choice | Example |
|---|---|
| spacetime dimension | $d=3$ |
| external operators | identical scalar $\phi$, or mixed $\sigma,\epsilon$ |
| global symmetry | none, $\mathbb Z_2$, $O(N)$, flavor group |
| correlators | $\langle\phi\phi\phi\phi\rangle$ or a mixed system |
| sectors | singlet, traceless symmetric, antisymmetric, odd/even |
| gaps | first scalar gap, next-scalar gap, spin gaps |
| protected operators | stress tensor, conserved currents, supersymmetric multiplets |
| target quantity | dimension bound, OPE bound, island, navigator objective |

This is where many mistakes are born. If the problem is physically underspecified, the numerical result will also be underspecified.

A good project note starts with a sentence like:

> We bootstrap a unitary $d=3$ CFT with $\mathbb Z_2$ symmetry using mixed correlators of the leading odd scalar $\sigma$ and leading even scalar $\epsilon$, imposing the following gaps…

That sentence is part of the computation.

## Stage 2: write crossing equations

Next write the crossing equations in a form suitable for block generation. In the simplest identical-scalar case,

$$
\vec F_{\mathbf1}+\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0.
$$

With global symmetry, one has a sum over representation sectors:

$$
\sum_{R}\sum_{\mathcal O\in R}\lambda_{\mathcal O}^2\vec F^{R}_{\Delta,\ell}=0.
$$

With mixed correlators, block contributions become matrix-valued, and OPE coefficients assemble into positive semidefinite outer products.

At this stage, check:

- Are the tensor structures independent?
- Are spin selection rules correct?
- Is the identity contribution normalized consistently?
- Are conserved currents and stress tensors in the correct sectors?
- Are external-operator two-point functions normalized?
- Are parity or global-symmetry assumptions stated?

A solver cannot fix a wrong crossing equation. It will faithfully optimize the wrong problem. Classic computer goblin behavior.

## Stage 3: choose truncations

The derivative cutoff $\Lambda$ defines the finite functional space. A simple derivative set might include derivatives satisfying

$$
m+n\le\Lambda
$$

with the correct crossing parity.

A real workflow must also decide how to treat spin. For identical scalar external operators, one typically includes even spins

$$
\ell=0,2,4,\ldots .
$$

In practice, low spins are represented explicitly and large spins are handled by a chosen finite or asymptotic method.

Record:

| Truncation choice | Why it matters |
|---|---|
| derivative cutoff $\Lambda$ | controls functional search space |
| derivative basis | affects vector dimension and conditioning |
| spin list | controls which spin constraints are explicit |
| large-spin treatment | affects reliability of exclusions |
| pole order or block approximation order | affects rational approximation accuracy |
| precision | affects solver stability |

The cutoff is not merely bookkeeping. It is part of the result.

## Stage 4: generate conformal block data

The solver does not know conformal field theory. It receives numerical or algebraic approximations to block derivatives. These are generated before the SDP solve.

For each spin and sector, one computes or approximates derivative vectors such as

$$
\partial_z^m\partial_{\bar z}^nF_{\Delta,\ell}(z,\bar z)\bigg|_{z=\bar z=1/2}.
$$

Modern workflows often represent these derivatives as rational functions of $\Delta$:

$$
\chi_\ell(\Delta)\frac{P_{k,\ell}(\Delta)}{Q_\ell(\Delta)}.
$$

The goal is to convert continuous positivity in $\Delta$ into polynomial matrix positivity.

Check block data carefully. Bugs here can be subtle: a wrong normalization, a missing sector, or an inaccurate approximation can produce plausible-looking but wrong bounds.

## Stage 5: build the polynomial matrix program

The conformal block data and assumptions are assembled into a polynomial matrix program. For each sector and spin family, the functional must make a polynomial matrix positive semidefinite on an allowed interval:

$$
M_{R,\ell}(\Delta;\alpha)\succeq0
\qquad
\Delta\ge\Delta_{\min}(R,\ell).
$$

The lower endpoint $\Delta_{\min}$ is determined by a unitarity bound, a spectral gap assumption, or a protected operator treatment.

For example, a scalar gap assumption might replace the scalar lower bound by

$$
\Delta\ge\Delta_{\rm gap}.
$$

A stress tensor may be treated as a fixed isolated operator at

$$
\Delta=d,
\qquad
\ell=2,
$$

with its Ward-identity OPE coefficient related to $C_T$ if the computation is bounding stress-tensor data.

This stage is where the physics assumptions become solver constraints.

## Stage 6: choose the objective

Some runs are feasibility tests. They ask whether an excluding functional exists. Other runs optimize a quantity.

Common objectives include:

| Objective | Example |
|---|---|
| feasibility | exclude or not exclude a trial gap |
| scalar dimension bound | maximize an allowed gap until exclusion fails |
| OPE coefficient bound | bound $\lambda_{\phi\phi\mathcal O}^2$ |
| central-charge bound | bound $C_T$ or $C_J$ through Ward identities |
| navigator value | produce a smooth diagnostic over parameter space |
| island search | map allowed and excluded parameter regions |

A functional normalization is required, for example

$$
\alpha(\vec F_{\mathbf1})=1.
$$

Different objectives can use the same crossing equations but produce different solver inputs and different interpretations.

## Stage 7: run the solver

The solver attempts to find primal and dual solutions satisfying the SDP constraints to the requested precision. In practical terms, this means choosing numerical precision, stopping criteria, checkpointing behavior, parallelism, and resource allocation.

A serious run records:

- software version or commit;
- input files;
- command-line options;
- precision settings;
- machine or cluster environment;
- wall-clock time and memory usage;
- solver status;
- primal and dual residuals;
- duality gap or objective value;
- checkpoint or output files.

For small examples, this may feel fussy. For high-precision islands, it is the difference between science and vibes in a trench coat.

## Stage 8: interpret solver status

Solver statuses must be translated carefully.

A dual feasible solution often means an excluding functional has been found. Then the tested point or assumption is ruled out at the chosen cutoff and precision.

Failure to find a dual feasible solution does not prove that a CFT exists. It means the run did not find an exclusion certificate.

A primal feasible solution indicates that the primal finite problem appears satisfiable. But the primal solution may not correspond to a clean physical spectrum unless additional reconstruction and convergence checks are performed.

Numerical failure can mean many things: insufficient precision, bad conditioning, inconsistent input, too aggressive tolerances, or a problem near a very thin boundary.

The safe interpretation table is:

| Output pattern | Conservative reading |
|---|---|
| stable dual feasible | excluded under stated assumptions |
| stable not excluded | survives this test |
| changing status with small setting changes | numerical diagnosis needed |
| feasible only at low cutoff | not yet convincing |
| boundary stable across cutoffs | candidate robust bound |
| island stable and shrinking | strong evidence for isolated solution under assumptions |

## Stage 9: scan or navigate

One SDP solve gives one data point. Bounds and islands require many solves.

For a one-dimensional bound, scan a trial parameter such as

$$
\Delta_{\rm gap}.
$$

For an island, scan a multidimensional space such as

$$
(\Delta_\sigma,\Delta_\epsilon)
$$

or use more sophisticated search methods.

Modern workflows may use bisection, grid scans, Delaunay triangulation, cutting-surface methods, navigator functions, or other algorithms. These methods reduce the number of expensive SDP solves needed to map the allowed region.

Whatever the search method, each exclusion still comes from the same underlying logic: a functional or SDP certificate rules out a point.

## Stage 10: validate and reproduce

Validation is not optional. At minimum, check:

1. Increase $\Lambda$ and confirm the qualitative result persists.
2. Change precision and solver tolerances.
3. Check block approximation accuracy.
4. Test known limits, such as generalized free field behavior or known conserved operators.
5. Compare with previous literature when possible.
6. Save input files and scripts.
7. Record all assumptions in the final plot or table caption.

For spectrum extraction, also check that extracted operators converge with cutoff and appear consistently across related correlator systems.

A bootstrap plot without assumptions and cutoff labels is basically a treasure map with no scale bar. Charming, but do not build a bridge from it.

## Minimal reproducibility checklist

A reproducible SDPB-style result should include:

| Item | Example |
|---|---|
| theory assumptions | unitary $d=3$, $\mathbb Z_2$ symmetry |
| external operators | $\sigma$, $\epsilon$ |
| correlator system | mixed four-point system |
| imposed gaps | next odd scalar, next even scalar, spin-sector gaps |
| derivative cutoff | $\Lambda=27$, with definition of derivative set |
| spin treatment | spin list and large-spin assumptions |
| block generator | code/version and block parameters |
| solver | SDPB version or commit |
| precision | arithmetic precision and tolerances |
| scan method | grid, bisection, navigator, cutting surface |
| output interpretation | excluded, allowed, island, bound, spectrum extraction |

This checklist is not glamorous. Neither is a seatbelt. Use both.

## Common pitfalls

**Do not start with software before specifying the physics problem.** The crossing equations and assumptions define the computation.

**Do not treat default solver settings as universal.** Precision and tolerances are problem-dependent.

**Do not forget to record the derivative basis.** The symbol $\Lambda$ is not enough across different workflows.

**Do not confuse solver infeasibility with a complete CFT theorem.** The result is tied to truncation, approximations, and assumptions.

**Do not compare plots without matching assumptions.** A bound with one gap assumption is not the same as a bound without it.

**Do not trust a single-point island.** Islands need scans, convergence, and stability.

**Do not publish only final plots.** Input files, scripts, and solver settings are part of the scientific content.

## Relations to other pages

This page follows [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/). It prepares [Identical Scalar Bounds](/cft-bootstrap/numerical-bootstrap/identical-scalar-bounds/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), and [Software Ecosystem](/cft-bootstrap/numerical-bootstrap/software-ecosystem/).

For algorithmic improvements beyond plain scans, see [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/). For output interpretation, see [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/) and [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/).

## Research status

SDPB-style workflows are established in numerical conformal bootstrap. They are the standard path from derivative-truncated crossing equations to high-precision exclusion bounds and islands.

Active work improves automation, scalability, certification, input generation, integration with navigator and cutting-surface methods, mixed-correlator performance, spinning-block workflows, and reproducibility practices for large collaborations and long-running computations.

## Exercises

### Exercise 1

List the main stages in an SDPB-style bootstrap workflow.

<details><summary><strong>Solution</strong></summary>

A typical workflow is:

1. choose the physics problem and assumptions;
2. write crossing equations;
3. choose derivative and spin truncations;
4. generate conformal block derivative data;
5. assemble a polynomial matrix program;
6. choose feasibility or optimization objective;
7. run the SDP solver;
8. interpret primal and dual status;
9. scan or navigate parameter space;
10. validate and record reproducibility data.

</details>

### Exercise 2

Why is failure to find an excluding functional not proof that a CFT exists?

<details><summary><strong>Solution</strong></summary>

The solver searches in a finite functional space at finite precision with chosen block approximations and spin treatment. A stronger functional may exist at higher cutoff, with better precision, or in a larger correlator system. Therefore not finding an exclusion certificate means only that the point is not excluded by that run.

</details>

### Exercise 3

Why should a bootstrap plot label the derivative cutoff $\Lambda$?

<details><summary><strong>Solution</strong></summary>

The derivative cutoff defines the finite set of crossing constraints and the functional search space. Bounds and islands can change as $\Lambda$ increases. Without the cutoff, the reader cannot judge convergence, compare computations, or know how close the result is to the intended infinite-dimensional crossing problem.

</details>

### Exercise 4

What is the role of rational conformal block approximations in an SDPB workflow?

<details><summary><strong>Solution</strong></summary>

The solver must impose positivity for a continuous range of dimensions. Rational approximations express block derivatives as rational functions of $\Delta$. After multiplying by positive denominators, positivity becomes polynomial matrix positivity on a half-line. That condition can be encoded as semidefinite constraints.

</details>

### Exercise 5

Give three items that should be recorded for reproducibility.

<details><summary><strong>Solution</strong></summary>

Examples include the derivative cutoff and derivative basis, spin list and large-spin treatment, imposed spectral gaps, block generator and version, SDPB version, precision and solver tolerances, input files, scan method, and final solver statuses. Any three of these are acceptable.

</details>

## References

- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- W. Landry and D. Simmons-Duffin, “Scaling the semidefinite program solver SDPB,” 2019.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.

## Version history

- 2026-07-01: First polished draft. Added conceptual SDPB workflow, stages from physics assumptions to solver interpretation, reproducibility checklist, scan and validation guidance, pitfalls, exercises, and references.
