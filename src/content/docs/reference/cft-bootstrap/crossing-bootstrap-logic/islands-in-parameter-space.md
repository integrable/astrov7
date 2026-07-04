---
title: "Islands in Parameter Space"
description: "How mixed correlators, gap assumptions, and positivity can isolate small allowed regions of CFT data."
sidebar:
  label: "Islands in Parameter Space"
  order: 8
level: Graduate
status: "Polished draft"
source: "Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Reehorst et al. 2021; Liu et al. 2023; Rychkov–Su 2024"
topics:
  - conformal bootstrap
  - bootstrap islands
  - allowed regions
  - mixed correlators
  - CFT data
canonicalTopics:
  - bootstrap-islands
  - cft-parameter-space
  - mixed-correlator-bootstrap
researchStatus:
  established:
    - "Bootstrap islands are small connected allowed regions in a chosen parameter space, obtained under stated bootstrap assumptions and numerical precision controls."
  active:
    - "Modern island searches use larger mixed-correlator systems, improved conformal blocks, semidefinite programming, navigator functions, skydive-type algorithms, and careful stability checks."
---

## Summary

A **bootstrap island** is a small allowed region in a chosen space of CFT data. It appears when crossing symmetry, unitarity, global symmetries, mixed-correlator positivity, and spectral assumptions are strong enough to isolate a candidate CFT from nearby fake solutions.

For example, a mixed-correlator bootstrap may scan the dimensions of two low-lying scalar operators,

$$
(\Delta_\sigma,\Delta_\epsilon),
$$

and find that only a tiny region is consistent with the assumptions. That region is an island. Its size and shape depend on the correlators included, the spectral gaps imposed, and the numerical cutoff.

The point of an island is not aesthetic. An island turns a broad consistency problem into precision CFT data: operator dimensions, OPE coefficients, central charges, and sometimes approximate spectra. But an island is not magic. It is a conditional result:

$$
\text{island}
=
\text{crossing}+\text{unitarity}+\text{symmetry}+\text{assumptions}+\text{numerical control}.
$$

This page explains what islands mean, how they differ from bounds and kinks, how mixed correlators create them, and how to interpret them without accidentally overselling the result.

## Prerequisites

You should know [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/), [Four-Point Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/four-point-bootstrap/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/), and [Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/). It is also helpful to know why [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) are the coordinates of a CFT.

## Core idea

The conformal bootstrap defines an allowed set in a space of possible CFT data. At low numerical strength, this set is usually large. As one adds correlators, positivity constraints, and justified spectral gaps, the allowed set can shrink.

Sometimes the allowed set develops a small connected component around a physically interesting theory. This is an island.

A first-pass dictionary is:

| Object | Meaning |
|---|---|
| bound | An inequality on one datum, such as $\Delta_\epsilon\leq f(\Delta_\sigma)$. |
| kink | A sharp feature on the boundary of an allowed region. |
| island | A small connected allowed region surrounded by excluded points. |
| archipelago | Several separated islands or island-like components. |
| navigator | A method for moving efficiently through allowed and excluded regions. |

A kink is a clue. An island is a much stronger localization. But neither is automatically a proof that a particular microscopic lattice model flows to the CFT inside the plot. That identification requires a separate physics argument.

## Setup and conventions

Let $p$ denote a finite list of CFT data chosen as coordinates. Examples include

$$
p=(\Delta_\sigma,\Delta_\epsilon),
\qquad
p=(\Delta_\phi,\Delta_s,C_T/C_T^{\mathrm{free}}),
\qquad
p=(\Delta_1,\Delta_2,\lambda_{112},\ldots).
$$

For a fixed derivative cutoff $\Lambda$ and a set of hypotheses $\mathcal H$, define

$$
\mathcal A_\Lambda(\mathcal H)
\subset
\mathbb R^n
$$

to be the set of points $p$ not excluded by the numerical bootstrap problem. A bootstrap island is a small connected component of $\mathcal A_\Lambda(\mathcal H)$.

This notation is intentionally conservative. At finite cutoff, “allowed” means “not excluded by the finite computation,” not “proven to be realized by an actual CFT.” As $\Lambda$ increases and numerical controls improve, one hopes that the allowed region approaches the true consistency region.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Bootstrap island in a two-dimensional parameter space](/figures/cft-bootstrap/bootstrap-island-schematic.svg)

<figcaption>

A bootstrap island is a small connected component of the numerically allowed region in a chosen space of CFT data. Increasing the derivative cutoff, adding correlators, or imposing stronger assumptions can shrink the island, split it, move it, or eliminate it.

</figcaption>
</figure>

## From a bound to an island

The historical path into many island computations looks like this.

First, a single-correlator bootstrap gives a bound. For an identical scalar $\phi$, one may bound the lowest scalar in the $\phi\times\phi$ OPE as a function of $\Delta_\phi$:

$$
\Delta_s \leq f_\Lambda(\Delta_\phi).
$$

Second, the boundary of the allowed region may show a kink. A kink suggests that a special CFT may sit at or near the boundary. This is a hint, not a theorem.

Third, one adds more information: mixed correlators, global-symmetry sectors, stress-tensor or current Ward identities, or gaps above low-lying operators. The allowed region may shrink from a band to a compact region.

Fourth, if the compact region becomes small and stable under improved computations, it is interpreted as an island for a candidate CFT.

The important lesson is that islands are usually not produced by one idea alone. They come from the collision of several consistency requirements.

## Why mixed correlators help

Single-correlator equations see only part of the operator algebra. A mixed-correlator system sees how several OPEs fit together.

For two scalars $\sigma$ and $\epsilon$, one may include correlators such as

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle \epsilon\epsilon\epsilon\epsilon\rangle.
$$

The same exchanged operator can appear in more than one OPE channel, and its OPE coefficients are related. For an exchanged operator $\mathcal O$, the relevant coefficient vector might be

$$
\lambda_{\mathcal O}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}.
$$

Its contribution to crossing is positive semidefinite:

$$
\lambda_{\mathcal O}^{\mathsf T}
\vec V_{\Delta,\ell}
\lambda_{\mathcal O}.
$$

This matrix structure is much stronger than a collection of unrelated positive numbers. It forces the same operator to behave consistently across correlators. That consistency is often what turns a broad region into an island.

## Islands as conditional localization

A clean island statement has the form:

> Under hypotheses $\mathcal H$, at numerical cutoff $\Lambda$ and with specified precision controls, the allowed region in parameter space $p$ is contained in the displayed island.

The phrase “under hypotheses $\mathcal H$” includes the whole assumption stack:

- spacetime dimension,
- unitarity,
- global symmetry,
- external operator identities,
- relevant OPE channels,
- gap assumptions,
- uniqueness assumptions for stress tensors or currents,
- numerical truncation and precision choices.

An island is therefore a localization of possible CFT data inside a model class. It is not, by itself, a construction of the CFT.

This distinction matters especially when connecting to lattice models. Suppose a lattice model is believed to flow to a CFT. A bootstrap island may provide extremely precise candidate CFT data. To identify the lattice model with the island, one also needs evidence that the lattice model has the same symmetries, the same relevant-deformation pattern, and no extra low-lying operators that violate the assumed gaps.

## The anatomy of an island computation

A typical island computation has the following pieces.

### Choose external operators

Pick low-lying operators that strongly constrain the theory. For the Ising universality class, the natural choices are the lowest $\mathbb Z_2$-odd scalar and the lowest $\mathbb Z_2$-even scalar. For an $O(N)$ model, one may choose a vector scalar and a singlet scalar.

### Write all crossing equations

Include all four-point functions of these external operators that are related by symmetry. In mixed systems, the bookkeeping can be heavy, but the payoff is large because shared exchanged operators create matrix positivity constraints.

### Split into symmetry sectors

Decompose the exchanged operators by spin, parity, and global-symmetry representation. Each sector has its own unitarity bound and possible gap assumptions.

### Add physical gaps

Use conservative, stated gap assumptions to exclude unwanted solutions. Examples include:

$$
\Delta_{\sigma'}\geq \Delta_{\mathrm{odd}}^{\mathrm{gap}},
\qquad
\Delta_{\epsilon'}\geq \Delta_{\mathrm{even}}^{\mathrm{gap}},
\qquad
\Delta_{T'}\geq \Delta_{2}^{\mathrm{gap}}.
$$

The art is to choose gaps strong enough to isolate the target but weak enough to remain credible.

### Scan parameter space

At each candidate point $p$, solve the feasibility problem. If a separating functional exists, the point is excluded. If no separating functional is found, the point remains allowed at that cutoff.

### Test stability

Increase $\Lambda$, vary gaps, refine block approximations, check solver precision, and compare independent correlator systems. A robust island should not be a one-cutoff ghost.

## Reading island plots

A bootstrap island plot often shows axes such as $(\Delta_\sigma,\Delta_\epsilon)$. Shaded regions may be allowed, excluded, or untested depending on plotting convention. Always check the caption.

A good island plot should tell you:

| Feature | What to ask |
|---|---|
| axes | Which CFT data are being scanned? |
| assumptions | What gaps and symmetry assignments are imposed? |
| cutoff | What derivative order $\Lambda$ is used? |
| solver status | Are allowed points feasible, primal feasible, or merely not excluded? |
| convergence | How does the island change as $\Lambda$ increases? |
| comparison | Are previous bootstrap, Monte Carlo, perturbative, or experimental values overlaid? |

If the plot does not answer these questions, it may still be useful, but it is not yet a reusable precision result.

## Kinks, islands, and false friends

Kinks and islands are related but different.

A **kink** is a sharp feature on a boundary. It often indicates that the extremal solution changes character. Famous kinks have led to major insights, but a kink alone does not isolate a CFT. Several different mechanisms can produce sharp boundary features.

An **island** is surrounded by excluded regions in the scanned directions. It gives both upper and lower constraints on the chosen parameters.

A **false island** can occur if assumptions are too strong, if numerical precision is insufficient, if a gap accidentally excludes the target CFT, or if the plotted region is not stable under increasing $\Lambda$. The cure is not cynicism; it is stability testing.

## Precision data from an island

Once an island is stable, one can quote ranges for the scanned coordinates. One may also extract additional data:

- OPE coefficients,
- central charges,
- current two-point coefficients,
- dimensions of additional low-lying operators,
- approximate spectra from extremal functionals near the island boundary.

The extraction step should be distinguished from the exclusion step. Exclusion is based on separating functionals. Spectrum extraction is an additional diagnostic, powerful but more delicate.

A clean precision statement looks like:

$$
\Delta_\sigma\in[a,b],
\qquad
\Delta_\epsilon\in[c,d]
$$

under stated assumptions and numerical settings. A less clean statement says “the bootstrap predicts $\Delta_\sigma=\cdots$” without saying what was assumed. That version is shorter, punchier, and less trustworthy. The internet has enough of that already.

## Assumptions and status

- **Exact:** An island computation still rests on exact CFT principles: conformal covariance, OPE associativity, crossing, and unitarity in the target class.
- **Numerical:** The displayed island is computed at finite derivative order, finite arithmetic precision, and finite block accuracy. Stability under increasing numerical strength is essential.
- **Assumption-dependent:** The island depends on global symmetries, external operator choices, sector gaps, uniqueness assumptions, and any imported information about the target theory.
- **Open:** It remains an active methodological question how to turn more island computations into fully reproducible, independently checked, high-precision CFT-data pipelines.

## Common pitfalls

**Treating allowed as proven.** A point that survives a finite bootstrap search is not proven to be a CFT. It has not been excluded by the chosen finite test.

**Treating an island as assumption-free.** Islands are usually born from assumptions. The right question is not “is the island real?” but “under which assumptions and numerical controls does this island persist?”

**Forgetting parameter-space projection.** An island in $(\Delta_\sigma,\Delta_\epsilon)$ may hide variation in other CFT data. Projected regions can look simpler than the full allowed set.

**Comparing islands with different assumptions.** Two plots at the same $\Lambda$ but with different gaps are not two measurements of the same object. They are different conditional problems.

**Confusing a CFT island with a universality-class proof.** A lattice model, continuum Lagrangian, or experimental critical point must still be connected to the CFT by RG and symmetry arguments.

**Ignoring disconnected solutions.** Sometimes a parameter space contains multiple allowed components. The target CFT may be one island in a larger archipelago.

## Relations to other pages

- [Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/) explains the hypotheses that often make islands possible.
- [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) explains the matrix positivity that powers many precision islands.
- [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/) explains the single-correlator bounds and kinks that often motivate island searches.
- [Extremal Functional Method](/cft-bootstrap/crossing-bootstrap-logic/extremal-functional-method/) explains how boundary solutions can be used to estimate spectra.
- [Scalar Bootstrap Numerics](/cft-bootstrap/numerical-bootstrap/scalar-bootstrap-numerics/) gives a computational entry point for implementing simple scans.
- [Precision and Error Control](/cft-bootstrap/numerical-bootstrap/precision-and-error-control/) explains how to make numerical claims reproducible.
- [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) records the flagship example as CFT data rather than as a plotting phenomenon.

## Research status

Bootstrap islands are now part of the standard vocabulary of the numerical conformal bootstrap. They are especially important for the three-dimensional Ising and $O(N)$ universality classes, supersymmetric examples, and increasingly sophisticated mixed-correlator systems.

The frontier is not merely making prettier islands. It is making island computations faster, more reproducible, more assumption-transparent, and more capable of handling spinning operators, global symmetries, defects, boundaries, and gauge-theory-like CFTs. Modern methods such as navigator functions and related search algorithms are best understood as tools for navigating this high-dimensional consistency landscape.

## Exercises

### Exercise 1: Island as a connected component

Let $\mathcal A_\Lambda(\mathcal H)\subset\mathbb R^2$ be the allowed region in the plane $(\Delta_1,\Delta_2)$ at cutoff $\Lambda$. Give a precise mathematical definition of an island in this plane.

<details>
<summary><strong>Solution</strong></summary>

An island is a connected component $I$ of $\mathcal A_\Lambda(\mathcal H)$ that is bounded and small compared with the larger scale of the scan. More formally, one can say

$$
I\subset \mathcal A_\Lambda(\mathcal H),
\qquad
I\text{ is connected},
\qquad
I\cap J=\varnothing
$$

for every other connected component $J$ of $\mathcal A_\Lambda(\mathcal H)$. The adjective “small” is not a topological property; it is a practical statement about the precision with which the selected CFT data have been localized.

</details>

### Exercise 2: Why mixed correlators shrink regions

Explain why adding the correlator $\langle \epsilon\epsilon\epsilon\epsilon\rangle$ to a system that already contains $\langle \sigma\sigma\sigma\sigma\rangle$ can shrink the allowed region in $(\Delta_\sigma,\Delta_\epsilon)$.

<details>
<summary><strong>Solution</strong></summary>

The additional correlator imposes new crossing equations and new positivity constraints. It also forces operators appearing in multiple OPEs to have compatible dimensions and OPE coefficients. Therefore the set of spectra and OPE data satisfying the enlarged system is a subset of the set satisfying the smaller system. Projecting onto $(\Delta_\sigma,\Delta_\epsilon)$ can only shrink or leave unchanged the allowed region.

</details>

### Exercise 3: Projection can hide data

Suppose an island is shown in the two-dimensional plane $(\Delta_\sigma,\Delta_\epsilon)$. Does this mean all other CFT data are uniquely fixed? Explain.

<details>
<summary><strong>Solution</strong></summary>

No. The plot shows the projection of the allowed set onto two coordinates. Other data, such as OPE coefficients, central charges, and dimensions of higher operators, may vary over the island or over hidden directions. A very small island often strongly constrains other data, but that requires additional analysis.

</details>

### Exercise 4: Conditional interpretation

A computation finds a tiny island after imposing $\Delta_{\epsilon'}\geq4$. Later evidence suggests that the target CFT has $\Delta_{\epsilon'}=3.8$. What happens to the interpretation of the island?

<details>
<summary><strong>Solution</strong></summary>

The island remains a valid conditional result for theories satisfying $\Delta_{\epsilon'}\geq4$, but it can no longer be interpreted as isolating the target CFT if the target has $\Delta_{\epsilon'}=3.8$. The gap assumption would have excluded the target theory. One must rerun or reinterpret the bootstrap with a weaker or different gap assumption.

</details>

### Exercise 5: Bounds versus islands

Why does an upper bound on $\Delta_\epsilon$ as a function of $\Delta_\sigma$ not by itself determine a CFT?

<details>
<summary><strong>Solution</strong></summary>

An upper bound says that any CFT satisfying the assumptions must lie below a boundary. It does not give a lower bound, does not isolate a connected region, and does not determine OPE coefficients or the rest of the spectrum. A CFT may sit near a kink on the boundary, but identifying it requires additional constraints, assumptions, or evidence. An island is stronger because it bounds the data from multiple sides in the chosen parameter space.

</details>

## References

### Standard first pass

- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in $D\geq3$ Dimensions*, 2016.
- David Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, 2017.
- David Poland, Slava Rychkov, and Alessandro Vichi, *The Conformal Bootstrap: Theory, Numerical Techniques, and Applications*, Reviews of Modern Physics, 2019.

### Deeper references

- Sheer El-Showk, Miguel F. Paulos, David Poland, Slava Rychkov, David Simmons-Duffin, and Alessandro Vichi, *Solving the 3D Ising Model with the Conformal Bootstrap*, 2012.
- Sheer El-Showk, Miguel F. Paulos, David Poland, Slava Rychkov, David Simmons-Duffin, and Alessandro Vichi, *Solving the 3D Ising Model with the Conformal Bootstrap II: c-Minimization and Precise Critical Exponents*, 2014.
- Filip Kos, David Poland, David Simmons-Duffin, and Alessandro Vichi, *Precision Islands in the Ising and $O(N)$ Models*, 2016.
- Marten Reehorst, Slava Rychkov, David Simmons-Duffin, Benoit Sirois, Ning Su, and Balt van Rees, *Navigator Function for the Conformal Bootstrap*, 2021.
- Aike Liu, David Simmons-Duffin, Ning Su, and Balt C. van Rees, *Skydiving to Bootstrap Islands*, 2023.
- Slava Rychkov and Ning Su, *New Developments in the Numerical Conformal Bootstrap*, 2024.

## Version history

- **2026-06-28:** Initial polished draft.
