---
title: "Reproducing the 3D Ising Island"
description: "A conceptual reproduction guide for the 3D Ising mixed-correlator bootstrap island, emphasizing assumptions, workflow, checks, and interpretation rather than black-box software commands."
sidebar:
  label: "Reproducing the 3D Ising Island"
  order: 13
level: Advanced
status: "Polished draft"
source: "El-Showk et al.; Kos, Poland, Simmons-Duffin, and Vichi; Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; SDPB workflow literature."
topics:
  - 3D Ising CFT
  - bootstrap island
  - mixed correlators
  - numerical conformal bootstrap
  - reproducibility
canonicalTopics:
  - reproducing-the-3d-ising-island
  - ising-bootstrap-island
  - mixed-correlator-reproduction
researchStatus:
  established:
    - "The 3D Ising island is a benchmark mixed-correlator numerical bootstrap result based on crossing, unitarity, Z2 symmetry, and spectral gap assumptions."
  active:
    - "Reproducing precision islands remains technically demanding because results depend on derivative cutoff, block generation, solver precision, gap assumptions, and search strategy."
---

## Summary

The **3D Ising island** is the benchmark example of a precision numerical conformal bootstrap result. It isolates the leading scaling dimensions of the three-dimensional Ising CFT using mixed correlators of the two leading scalar primaries:

$$
\sigma \quad \text{and} \quad \epsilon.
$$

Here $\sigma$ is the leading $\mathbb Z_2$-odd scalar and $\epsilon$ is the leading $\mathbb Z_2$-even scalar. The classic mixed system studies

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle \epsilon\epsilon\epsilon\epsilon\rangle.
$$

The goal is to constrain the plane

$$
(\Delta_\sigma,\Delta_\epsilon).
$$

Under appropriate assumptions, the allowed region shrinks to a tiny island around the Ising CFT data. This page explains how to reproduce the logic of that calculation: what inputs are needed, what assumptions are imposed, what software stages appear, what checks matter, and how to interpret the result.

This is not a promise that a single laptop run will reproduce published world-record precision. The real calculation is a high-precision workflow. The point here is to make the pipeline transparent.

## Prerequisites

Read [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/) first.

You should know how crossing equations become semidefinite programs, why mixed correlators lead to matrix positivity, and why island results are conditional on gap assumptions.

## Core idea

The 3D Ising island is obtained by asking a highly targeted question:

> Which values of $(\Delta_\sigma,\Delta_\epsilon)$ are compatible with unitary $d=3$ CFT crossing, $\mathbb Z_2$ symmetry, and Ising-like spectral assumptions?

The computation does not start from the cubic-lattice Ising Hamiltonian. It starts from the continuum CFT hypothesis.

The essential assumptions are:

$$
\sigma = \text{lowest }\mathbb Z_2\text{-odd scalar},
$$

$$
\epsilon = \text{lowest }\mathbb Z_2\text{-even scalar},
$$

plus gaps above the next relevant operators in selected sectors.

The slogan is

$$
\text{single-correlator kink}
\quad\longrightarrow\quad
\text{mixed-correlator island}
\quad\longrightarrow\quad
\text{precision CFT data}.
$$

The island appears because the same operator algebra must solve several crossing equations at once.

## The CFT data being targeted

The main target coordinates are

$$
\Delta_\sigma,
\qquad
\Delta_\epsilon.
$$

These determine standard critical exponents by scaling relations. In $d=3$,

$$
\nu=\frac{1}{3-\Delta_\epsilon},
$$

and

$$
\eta=2\Delta_\sigma-1.
$$

But the mixed-correlator system actually constrains more than two numbers. It also sees OPE coefficients such as

$$
\lambda_{\sigma\sigma\epsilon},
\qquad
\lambda_{\epsilon\epsilon\epsilon},
$$

as well as stress-tensor data, subleading scalar dimensions, and higher-spin operator data through the allowed spectrum.

A reproduction project should decide at the beginning whether the goal is:

| Goal | What it requires |
|---|---|
| see the island qualitatively | modest cutoff, approximate gaps, exploratory scan |
| reproduce a published plot | same assumptions, comparable cutoff, compatible software settings |
| reproduce precision numbers | high cutoff, careful extrapolation, solver logs, block checks |
| extract spectra | stable extremal or island-boundary data |
| test assumptions | gap scans and alternate correlator systems |

The required computational effort grows quickly as one moves down the table.

## Operator sectors

The $\mathbb Z_2$ selection rules are

$$
\sigma\times\sigma=\text{even},
$$

$$
\epsilon\times\epsilon=\text{even},
$$

and

$$
\sigma\times\epsilon=\text{odd}.
$$

The even sector contains the identity, the energy operator $\epsilon$, the stress tensor, and subleading even operators:

$$
\mathbf1,\quad \epsilon,\quad T_{\mu\nu},\quad \epsilon',\ldots .
$$

The odd sector contains the spin operator $\sigma$ and subleading odd operators:

$$
\sigma,\quad \sigma',\ldots .
$$

For even operators appearing in both diagonal OPEs, one has an OPE vector

$$
\lambda_{\mathcal O^+}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O^+}\\
\lambda_{\epsilon\epsilon\mathcal O^+}
\end{pmatrix}.
$$

This produces positive semidefinite matrix constraints. That matrix positivity is one of the main reasons the Ising island is much sharper than a single-correlator kink.

## Minimal reproduction workflow

A conceptual reproduction has ten stages.

1. Choose the external dimensions:

$$
(\Delta_\sigma,\Delta_\epsilon).
$$

2. Build the mixed crossing equations for

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\quad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\quad
\langle \epsilon\epsilon\epsilon\epsilon\rangle.
$$

3. Decompose operators by $\mathbb Z_2$ parity and spin.

4. Specify which operators are isolated:

$$
\sigma,\quad \epsilon,\quad \mathbf1,\quad T_{\mu\nu}.
$$

5. Impose gaps above selected subleading operators, such as $\sigma'$ and $\epsilon'$.

6. Choose derivative cutoff $\Lambda$ and spin treatment.

7. Generate conformal block derivative data.

8. Convert the problem to a polynomial matrix program.

9. Use an SDP solver to test whether the point is excluded.

10. Scan or navigate parameter space to map the allowed region.

This pipeline is the result. Skipping the assumptions and reporting only the final island is like giving someone the treasure chest but not the map. Fun, but suspicious.

## Gap assumptions

The island depends on spectral gaps. A typical assumption says that after the leading operator in a sector, the next operator has dimension above a chosen threshold.

For example:

$$
\Delta_{\sigma'}\ge g_{\sigma'},
$$

and

$$
\Delta_{\epsilon'}\ge g_{\epsilon'}.
$$

The exact values depend on the calculation being reproduced. They should be taken from the target paper or chosen deliberately for an exploratory run.

A clean reproduction should record:

| Gap | Sector | Meaning |
|---|---|---|
| odd scalar gap | $\mathbb Z_2$ odd, spin $0$ | assumes $\sigma$ is isolated below $\sigma'$ |
| even scalar gap | $\mathbb Z_2$ even, spin $0$ | assumes $\epsilon$ is isolated below $\epsilon'$ |
| spin-two gap | even spin $2$ | can encode uniqueness of the stress tensor |
| higher-spin gaps | selected even or odd sectors | optional, more specialized assumptions |

Gaps should be physically motivated and varied as a check. If an island appears only for an aggressive gap that the target CFT likely violates, the island is not evidence for that CFT.

## Derivative cutoff and precision

The derivative cutoff $\Lambda$ controls the finite functional space. A low value of $\Lambda$ may show a rough feature. A high value is needed for precision.

At each cutoff, record:

- the definition of $\Lambda$;
- the derivative basis;
- the spin list;
- block approximation settings;
- solver precision;
- feasibility tolerances;
- raw solver statuses.

One should not quote a final island from a single cutoff. Instead, compare a sequence such as

$$
\Lambda_1<\Lambda_2<\Lambda_3<\cdots .
$$

A trustworthy island persists and shrinks in a controlled way. If the island moves erratically, the computation is not yet stable.

## What to plot

The standard first plot is the allowed region in

$$
(\Delta_\sigma,\Delta_\epsilon).
$$

Each sampled point is classified as excluded or not excluded under the chosen assumptions. The island is the connected not-excluded region that remains near the expected Ising data.

For a serious reproduction, also plot or tabulate:

| Diagnostic | Why |
|---|---|
| cutoff sequence | shows convergence |
| gap scan | shows assumption dependence |
| failed solver points | exposes numerical trouble |
| boundary samples | distinguishes solved points from interpolation |
| OPE coefficient ranges | checks mixed-correlator consistency |
| $C_T$ or stress-tensor data | tests Ward-identity normalization |

A clean reproduction is more than a pretty colored blob. The blob is the headline; the diagnostics are the receipts.

## Extracting data from the island

Once the island is found, one can estimate CFT data by reporting coordinate ranges:

$$
\Delta_\sigma\in[\Delta_\sigma^{\min},\Delta_\sigma^{\max}],
$$

$$
\Delta_\epsilon\in[\Delta_\epsilon^{\min},\Delta_\epsilon^{\max}].
$$

One can also optimize OPE coefficients or central-charge-related quantities over the island. For example, one may constrain

$$
\lambda_{\sigma\sigma\epsilon},
\qquad
\lambda_{\epsilon\epsilon\epsilon},
\qquad
C_T.
$$

The interpretation is conditional:

> Any CFT satisfying the stated assumptions and surviving the tested crossing system lies in this allowed region.

It is tempting to say “the bootstrap computes the Ising dimensions.” More precisely, the bootstrap excludes everything else under the assumptions and cutoffs tested. The distinction is small in a mature benchmark and huge in a new research problem.

## Common failure modes

Reproduction can fail for boring reasons. Boring reasons are still real reasons.

| Failure mode | Symptom |
|---|---|
| wrong crossing equation | results disagree completely with literature |
| wrong normalization | OPE or $C_T$ values look shifted |
| missing sector | island too large or absent |
| gap applied to wrong sector | unphysical exclusion or artificial island |
| low precision | unstable solver statuses near boundary |
| low cutoff | broad region or drifting island |
| block error | inconsistent bounds across settings |
| interpolation error | boundary looks smoother than solved data justify |

A good reproduction plan isolates these possibilities one by one.

## Common pitfalls

**Do not treat the island as assumption-free.** The Ising island depends on $\mathbb Z_2$ symmetry, operator ordering, gap assumptions, and the chosen correlator system.

**Do not confuse lattice data with bootstrap input.** The bootstrap calculation uses continuum CFT consistency, not a lattice Hamiltonian.

**Do not hide failed solver points.** They are part of the numerical story.

**Do not quote more digits than the cutoff sequence supports.** Precision requires convergence, not just small fixed-cutoff regions.

**Do not impose gaps without sector labels.** “Next scalar” is ambiguous unless parity, spin, and representation are specified.

**Do not compare OPE coefficients without normalization conventions.** Two-point normalizations and block conventions matter.

**Do not expect a beginner run to reproduce world-record numbers.** Reproducing the logic is easier than reproducing the final precision.

## Relations to other pages

This page follows [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/) and applies that reliability logic to the flagship 3D Ising example.

It connects to [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), and [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/).

For implementation context, see [Software Ecosystem](/cft-bootstrap/numerical-bootstrap/software-ecosystem/) and [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/).

## Research status

The 3D Ising mixed-correlator island is an established benchmark of the numerical conformal bootstrap. It is one of the clearest examples where crossing, unitarity, symmetry, and spectral assumptions produce precision CFT data.

Active work continues to refine related data: stress-tensor correlators, subleading spectra, defects and boundaries, off-critical perturbations, finite-size spectra, fuzzy-sphere comparisons, and methods for making reproduction more automated and certified.

## Exercises

### Exercise 1

Why are mixed correlators essential for the precision Ising island?

<details><summary><strong>Solution</strong></summary>

A single correlator such as $\langle\sigma\sigma\sigma\sigma\rangle$ gives one projection of crossing and can produce a kink. Mixed correlators involving $\sigma$ and $\epsilon$ require the same operator dimensions and OPE data to solve several crossing equations simultaneously. Even operators couple to both $\sigma\sigma$ and $\epsilon\epsilon$, producing matrix positivity. This extra consistency shrinks the allowed region into an island.

</details>

### Exercise 2

State the $\mathbb Z_2$ selection rules for the Ising mixed system.

<details><summary><strong>Solution</strong></summary>

Since $\sigma$ is odd and $\epsilon$ is even,

$$
\sigma\times\sigma=\text{even},
$$

$$
\epsilon\times\epsilon=\text{even},
$$

and

$$
\sigma\times\epsilon=\text{odd}.
$$

</details>

### Exercise 3

Why should one vary the assumed gaps when reproducing the island?

<details><summary><strong>Solution</strong></summary>

The island is conditional on gap assumptions. Varying the gaps shows whether the island is robust or artificially produced by overly strong assumptions. A stable island over a physically motivated gap range is more trustworthy than an island that appears only for one aggressive choice.

</details>

### Exercise 4

What is the conservative interpretation of a point inside the island?

<details><summary><strong>Solution</strong></summary>

A point inside the island is not excluded by the tested crossing equations at the chosen cutoff, precision, and assumptions. It is not automatically an exact CFT. The conservative statement is that any CFT satisfying the assumptions and tested constraints must lie within the allowed region.

</details>

### Exercise 5

List five pieces of information needed for a reproducible Ising-island computation.

<details><summary><strong>Solution</strong></summary>

Examples include the external operators, crossing equations, $\mathbb Z_2$ sectors, imposed gaps, derivative cutoff and basis, spin treatment, block generator settings, solver version, precision and tolerances, scan method, and raw solver statuses. Any five are acceptable.

</details>

## References

- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- F. Kos, D. Poland, and D. Simmons-Duffin, “Bootstrapping mixed correlators in the 3D Ising model,” *Journal of High Energy Physics* **2014**.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.

## Version history

- 2026-07-01: First polished draft. Added Ising mixed-correlator reproduction logic, sector selection rules, gap assumptions, workflow stages, cutoff and precision checks, plotting guidance, failure modes, exercises, and references.
