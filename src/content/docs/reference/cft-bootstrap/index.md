---
title: "CFT and Bootstrap"
description: "A polished graduate-level roadmap to conformal field theory, CFT data, conformal blocks, crossing symmetry, and the conformal bootstrap."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - conformal field theory
  - conformal bootstrap
  - CFT data
  - conformal symmetry
  - operator product expansion
  - conformal blocks
  - crossing symmetry
  - numerical bootstrap
  - analytic bootstrap
canonicalTopics:
  - cft-and-bootstrap
  - conformal-data
  - conformal-bootstrap
  - cft-roadmap
researchStatus:
  established:
    - "Conformal symmetry, local operator algebras, radial quantization, OPEs, conformal blocks, and crossing equations form the standard structural language of CFT."
    - "The modern conformal bootstrap treats CFT data as constrained by symmetry, unitarity, locality, and crossing, often without assuming a Lagrangian."
  active:
    - "Numerical and analytic bootstrap methods, Lorentzian techniques, defect bootstrap, modular bootstrap, supersymmetric bootstrap, and holographic CFT remain active research areas."
---

## Summary

**CFT and Bootstrap** is the volume where quantum field theories at scale-invariant fixed points are studied through their local operator algebra rather than through perturbation theory around particles.

The central object is the **CFT data**:

$$
\left\{\Delta_i,\ \rho_i,\ \lambda_{ijk},\ \text{global symmetries},\ \text{defects and extended data when present}\right\}.
$$

Here $\Delta_i$ are scaling dimensions, $\rho_i$ are spin or representation labels, and $\lambda_{ijk}$ are OPE coefficients in a chosen normalization. Once this data is known, conformal symmetry and the operator product expansion determine correlation functions, subject to consistency conditions.

The conformal bootstrap is the program of using those consistency conditions — especially crossing symmetry, unitarity, locality, and symmetry selection rules — to solve or constrain CFTs. Its sharpest slogan is

$$
\text{CFT} = \text{consistent conformal operator algebra}.
$$

This slogan is not a definition by itself. It becomes useful only after the words “consistent”, “operator”, and “algebra” are made precise. That is the job of this volume.

## What this volume is for

Read this volume when you want to understand CFT as a nonperturbative language for QFT. A Lagrangian may exist, and often gives valuable intuition, but it is not the primary organizing object here. The primary objects are local operators, their correlation functions, the OPE, and the constraints that make all OPE channels agree.

The first half of the volume builds the common spine:

$$
\text{conformal symmetry}
\longrightarrow
\text{operators and states}
\longrightarrow
\text{correlators}
\longrightarrow
\text{OPE}
\longrightarrow
\text{blocks}
\longrightarrow
\text{crossing}.
$$

The second half develops the major branches: two-dimensional CFT, Virasoro symmetry, minimal models, current algebras, higher-dimensional CFT, numerical bootstrap, analytic bootstrap, modular bootstrap, defect CFT, Lorentzian CFT, supersymmetric CFT, holographic CFT, and applications to statistical physics and matter.

The guiding boundary is simple: this volume is the canonical home of **conformal structure, CFT data, and bootstrap consistency**. General RG flows, the full epsilon expansion, lattice critical phenomena, string worldsheet theory, supersymmetric localization, and categorical symmetry appear here only when they illuminate conformal data or bootstrap constraints.

## Prerequisites

You should know the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/), the basic idea of [renormalization group fixed points](/renormalization-rg-eft/fixed-points-critical-phenomena/), and the operator language of [Correlation Functions and Propagators](/foundations/correlators-and-propagators/). The [Conventions and Notation](/cft-bootstrap/conventions/) page fixes the CFT-specific choices used throughout this volume.

For a first serious pass, it helps to have seen Euclidean path integrals, Noether currents, stress tensors, Hilbert spaces, and the distinction between operators and states. You do not need to know Virasoro representation theory, semidefinite programming, AdS/CFT, or conformal Regge theory before beginning.

## Reading path

A first pass should prioritize the structural spine before specialized branches.

| Step | Chapter | What it gives you |
|---:|---|---|
| 1 | [Conventions and Notation](/cft-bootstrap/conventions/) | The Euclidean, operator, OPE, two-point, block, and crossing conventions used everywhere else. |
| 2 | [What Is a CFT?](/cft-bootstrap/what-is-a-cft/) | The relation between RG fixed points, scale invariance, conformal invariance, local operators, and CFT data. |
| 3 | [Conformal Symmetry](/cft-bootstrap/conformal-symmetry/) | The conformal group, conformal algebra, conformal transformations, and Ward identities. |
| 4 | [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/) | Primary operators, descendants, multiplets, radial quantization, the cylinder picture, and unitarity bounds. |
| 5 | [Correlation Functions](/cft-bootstrap/correlation-functions/) | Two-, three-, and four-point functions, cross-ratios, conformal frames, and spinning structures. |
| 6 | [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) | How local products are reorganized into sums over operators and why OPE coefficients are CFT data. |
| 7 | [Conformal Blocks](/cft-bootstrap/conformal-blocks/) | The decomposition of four-point functions into contributions from conformal multiplets. |
| 8 | [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) | The bootstrap equations, positivity, assumptions, bounds, islands, and the meaning of a consistency constraint. |

After this path, you should be able to read the standard four-point bootstrap equation for identical scalars, identify the role of conformal blocks, and understand what data a numerical or analytic bootstrap calculation is constraining.

## Major branches

Once the spine is in place, the natural branches are these.

| Branch | When to read it |
|---|---|
| [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) | When complex coordinates, local conformal maps, holomorphic factorization, and the cylinder-plane map become central. |
| [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) | When the stress tensor in two dimensions enlarges global conformal symmetry to the Virasoro algebra. |
| [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/) | When you want exact solvable examples such as the Ising CFT and the logic of null states, fusion, characters, and modular data. |
| [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) | When affine Lie algebras, Sugawara construction, WZW models, and cosets enter. |
| [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/) | When spin, tensor structures, conserved currents, large-$N$ CFTs, and examples such as the three-dimensional Ising CFT matter. |
| [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) | When crossing plus positivity is turned into rigorous bounds, allowed regions, islands, and spectrum extraction. |
| [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) | When lightcone limits, large spin, inversion formulas, and asymptotic CFT data become the main tools. |
| [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) | When torus partition functions, modular invariance, and spectral constraints are the main consistency equations. |
| [Boundary, Defect, and Interface CFT](/cft-bootstrap/boundary-defect-interface-cft/) | When conformal symmetry survives only along a submanifold and bulk, boundary, and defect OPEs interact. |
| [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) | When analytic continuation, causal ordering, lightcones, thermal states, chaos, and Regge behavior matter. |
| [CFT Deformations and RG Flows](/cft-bootstrap/cft-deformations-rg-flows/) | When relevant, marginal, and irrelevant deformations move the theory away from the fixed point. |
| [Supersymmetric CFT](/cft-bootstrap/supersymmetric-cft/) | When superconformal algebras, protected operators, indices, chiral rings, and supersymmetric bootstrap constraints enter. |
| [Holographic CFT](/cft-bootstrap/holographic-cft/) | When large-$N$ CFTs are read through AdS duality, Witten diagrams, bulk locality, and stress-tensor dynamics. |
| [CFT in Statistical Physics and Matter](/cft-bootstrap/cft-in-statistical-physics-matter/) | When CFT data describes universality classes, critical exponents, finite-size scaling, and condensed-matter critical points. |

The [Model Calculation Library](/cft-bootstrap/model-calculation-library/) and [Data and Reference Tables](/cft-bootstrap/data-reference-tables/) are for worked examples and lookup. The [Bibliography](/cft-bootstrap/bibliography/) collects broader references.

## Landmarks

| Landmark | Meaning |
|---|---|
| CFT data | The spectrum and OPE coefficients, plus symmetry and extended-operator data when needed. |
| Primary operator | A local operator that is not a conformal descendant; primaries label conformal multiplets. |
| Radial quantization | The Hilbert-space construction in which the dilatation operator becomes the Hamiltonian on the cylinder. |
| State–operator correspondence | In flat Euclidean CFT, local operators at the origin correspond to states on a surrounding sphere. |
| OPE | A convergent local expansion, in radial quantization, expressing products of nearby operators in terms of local operators. |
| Conformal block | The contribution of one conformal multiplet to a four-point function in a chosen OPE channel. |
| Crossing symmetry | The statement that different OPE decompositions of the same correlator agree. |
| Positivity | In unitary Euclidean CFT, reflection positivity implies positive norm states and, in suitable correlators, nonnegative squared OPE coefficients. |
| Central charge or $C_T$ | A normalization of the stress-tensor two-point function; in two dimensions it is the Virasoro central charge $c$. |
| Bootstrap island | A small allowed region in CFT-data space isolated by combining crossing, unitarity, and assumptions such as symmetry or gaps. |

These landmarks are not separate facts to memorize. They are the same structure seen from different angles: symmetry organizes operators, the OPE multiplies them, blocks package their descendants, and crossing tests associativity.

## Common confusions

**A CFT is not necessarily free or Lagrangian.** Free theories are useful examples, and Lagrangians are useful when available. But the bootstrap language is designed to make sense even when the microscopic description is unknown or not unique.

**Scale invariance is not automatically conformal invariance in every logical setting.** Many important unitary fixed points with a stress tensor are conformal, and most physics applications use this expectation. The assumptions matter, so pages in this volume state when conformal invariance is being assumed rather than derived.

**CFT data is more than critical exponents.** Critical exponents are combinations of scaling dimensions. A full CFT also contains OPE coefficients, spin and global-symmetry representations, current and stress-tensor normalizations, and sometimes defect, boundary, or modular data.

**The bootstrap is not just numerics.** Numerical bootstrap is one powerful branch. Analytic bootstrap, modular bootstrap, Lorentzian methods, exactly solvable two-dimensional CFT, and representation theory are equally part of the same consistency program.

**Two-dimensional CFT is special, not generic.** Local conformal symmetry in two dimensions gives the Virasoro algebra and many exact tools. Higher-dimensional CFTs share the OPE and crossing logic but usually require different methods.

## Boundaries

This volume stops at the edge of conformal structure. General perturbative renormalization lives in [Renormalization, RG, and EFT](/renormalization-rg-eft/). General scattering amplitudes live in [Perturbative QFT and Scattering](/perturbative-qft/). General gauge dynamics, confinement, lattice gauge theory, and topological phases have their own volumes. Holography, supersymmetry, and statistical physics are treated here only where the conformal field theory viewpoint is doing essential work.

This separation is not territorial. It is for navigation. A good page on the Wilson–Fisher fixed point, for example, may live in the RG volume when the question is epsilon expansion, in the statistical-physics chapter when the question is universality, and in this volume when the question is its CFT data and bootstrap constraints.

## Research status

The structural foundations of CFT used in this volume — conformal symmetry, Ward identities, radial quantization, OPE, conformal blocks, and crossing equations — are textbook-standard. The degree of mathematical rigor varies with dimension, signature, assumptions, and class of theories, so rigorous status is stated locally when needed.

The bootstrap is both mature and active. The modern numerical bootstrap has produced high-precision constraints on major three-dimensional universality classes and continues to evolve through improved algorithms and software. Analytic bootstrap methods have also transformed the large-spin and Lorentzian understanding of CFT data. Treat numerical values, software workflows, and current best bounds as versioned material rather than eternal constants.

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. The standard broad textbook for two-dimensional CFT.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988. A classic bridge between statistical physics and two-dimensional CFT.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996. A compact route from critical phenomena to CFT ideas.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. A clear modern introduction to CFT and bootstrap methods.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. The main review of the modern numerical bootstrap through its first decade.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” arXiv:2311.15844. A recent review of software, algorithms, and physics applications after the Poland–Rychkov–Vichi review.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. A concise entry point for higher-dimensional CFT.

## Version history

- **2026-06-26:** Replaced the scaffold with a polished lightweight volume overview, reading path, boundaries, and current-reference map.
