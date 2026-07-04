---
title: "Conformal Blocks"
description: "Chapter overview for conformal blocks in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Ferrara–Gatto–Grillo 1973; Polyakov 1974; Dolan–Osborn 2003; Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - conformal blocks
  - conformal partial waves
  - conformal multiplets
  - four-point functions
  - Casimir equation
  - radial coordinates
  - bootstrap kinematics
canonicalTopics:
  - conformal-blocks
  - conformal-partial-waves
  - cft-data
  - ope-decomposition
  - bootstrap-kinematics
researchStatus:
  established:
    - "A conformal block is the kinematically fixed contribution of one conformal multiplet to a correlation function, once the external operators and exchanged quantum numbers are specified."
    - "For scalar four-point functions, conformal blocks may be characterized by the OPE limit, by conformal Casimir equations, or by radial-quantization expansions."
  active:
    - "Efficient computation of spinning blocks, mixed-correlator blocks, defect blocks, supersymmetric blocks, Lorentzian blocks, and Mellin-space reorganizations remains an active part of bootstrap technology."
---

Conformal Blocks is the chapter where the OPE becomes a usable expansion of four-point functions. The OPE says that a pair of nearby operators can be replaced by a sum over local primaries and descendants. A conformal block is the complete contribution of one such primary together with all of its descendants.

For scalar primaries, the basic four-point decomposition has the form

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}\lambda_{12\mathcal O}\lambda_{34\mathcal O}\,
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v),
$$

where $u$ and $v$ are conformal cross-ratios, $\mathcal O$ runs over exchanged primary operators, and $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}$ is fixed by conformal symmetry. The dynamical CFT data are the spectrum and the OPE coefficients. The block is the universal kinematic function that lets those data build a correlator.

Read this chapter when you want to understand what exactly is being summed in a bootstrap equation, why descendants do not introduce new independent OPE coefficients, and how conformal symmetry separates dynamics from kinematics.

## Prerequisites

You should know the [Conventions and Notation](/cft-bootstrap/conventions/), the definition of [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), and the operator-state language from [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) and [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/).

For the first pass, the essential previous pages are [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), and [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/). The [Conformal Casimir](/cft-bootstrap/conformal-symmetry/conformal-casimir/) page becomes important once blocks are derived from differential equations.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/) | The Hilbert-space and projector picture: one exchanged conformal multiplet contributes a fixed wave to a four-point function. |
| 2 | [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) | The standard scalar four-point block expansion, normalization conventions, OPE limits, and first examples. |
| 3 | [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) | The differential equation whose eigenfunctions are conformal blocks and whose eigenvalue is fixed by $\Delta$ and spin. |
| 4 | [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) | The radial variables that make convergence, descendant levels, and numerical evaluation transparent. |
| 5 | [Recursion Relations](/cft-bootstrap/conformal-blocks/recursion-relations/) | Efficient ways to compute blocks from analytic structure, poles, and descendant data. |
| 6 | [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/) | How blocks become tensor-valued or matrix-valued when external or exchanged operators carry spin. |
| 7 | [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/) | The special simplifications and factorization of global blocks in two-dimensional CFT. |
| 8 | [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/) | Why the infinite-dimensional Virasoro algebra repackages infinitely many global descendants and changes the block expansion. |
| 9 | [Conformal Blocks in Higher Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-higher-dimensions/) | The practical higher-dimensional block technology used in modern bootstrap calculations. |
| 10 | [Mellin-Space Blocks Preview](/cft-bootstrap/conformal-blocks/mellin-space-blocks-preview/) | A preview of Mellin-space reorganizations, especially useful for holographic and large-$N$ CFTs. |

After this path, you should be able to recognize a four-point function as a sum over exchanged conformal multiplets and understand what part of the expansion is universal.

## Landmarks

The chapter has five landmarks.

| Landmark | Meaning |
|---|---|
| Multiplet contribution | A block includes a primary and all descendants in its conformal multiplet. |
| Kinematics versus dynamics | The block is fixed by symmetry; the spectrum and OPE coefficients are theory-dependent. |
| Channel dependence | The same correlator has different block expansions depending on which pairs of operators are fused. |
| Casimir characterization | Blocks are eigenfunctions of the quadratic conformal Casimir acting on a chosen pair of points. |
| Radial convergence | In Euclidean signature, radial quantization explains why the block expansion converges in its OPE domain. |

The slogan is

$$
\text{OPE data}
+
\text{conformal blocks}
=
\text{four-point functions in one channel}.
$$

Bootstrap begins when two such channel expansions are required to define the same function.

## Common confusions

Do not confuse a conformal block with an OPE coefficient. A block is universal once the dimensions, spins, external quantum numbers, and normalization convention are fixed. The OPE coefficient is part of the particular CFT.

Do not confuse a primary exchange with only the primary operator. The primary term controls the leading OPE behavior, but the block includes every descendant contribution required by conformal symmetry.

Do not assume that “partial wave” and “block” always mean exactly the same thing in every paper. In some conventions a Euclidean conformal partial wave is a single-valued combination of a physical block and a shadow block. This chapter states the convention on each page whenever the distinction matters.

Do not treat blocks as independent observables. Individual blocks depend on a channel and a normalization convention. Physical correlators are sums of blocks with CFT-data coefficients and must obey crossing, symmetry, and positivity constraints.

Do not import two-dimensional Virasoro intuition too early. In $d>2$, the finite-dimensional conformal algebra fixes global blocks. In two dimensions, Virasoro symmetry often gives a more efficient and more powerful decomposition.

## Boundaries

This chapter is about conformal-block kinematics. It does not replace the [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) chapter, which explains why multiplets appear in the first place. It also does not replace [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/), where block expansions become constraints.

The chapter focuses first on local operators. Boundary, defect, and interface blocks belong later in [Boundary, Defect, and Interface CFT](/cft-bootstrap/boundary-defect-interface-cft/). Thermal blocks, Lorentzian inversion, Regge limits, and lightcone expansions are introduced only when they clarify the ordinary Euclidean block expansion; their deeper treatment belongs in [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) and [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/).

This chapter also does not try to be a software manual. Practical numerical block generation, polynomial approximations, SDPB input, and reproducible workflows belong in [Computational CFT and Bootstrap](/cft-bootstrap/computational-cft-bootstrap/) and [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/).

## Where to go next

After this chapter, read [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) and [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/). Blocks are useful because crossing relates different block expansions of the same correlator.

For exact two-dimensional methods, go to [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/). For higher-dimensional applications, go to [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/), [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/), and [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/).

## References

- A. M. Polyakov, “Nonhamiltonian Approach to Conformal Quantum Field Theory,” *Soviet Physics JETP* **39** (1974). Classic OPE and bootstrap perspective.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory,” *Nuclear Physics B* **241** (1984). Foundational two-dimensional conformal-block and bootstrap paper.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory* (Springer, 1997). Standard reference for two-dimensional global and Virasoro blocks, conformal families, and crossing.
- F. A. Dolan and H. Osborn, “Conformal Partial Waves and the Operator Product Expansion,” *Nuclear Physics B* **678** (2004). Classic higher-dimensional scalar-block technology.
- D. Simmons-Duffin, “Projectors, Shadows, and Conformal Blocks,” *Journal of High Energy Physics* **04** (2014). Modern projector and shadow-formalism treatment of blocks.
- M. Hogervorst and S. Rychkov, “Radial Coordinates for Conformal Blocks,” *Physical Review D* **87** (2013). Radial-coordinate expansion and convergence-oriented block technology.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016). Efficient graduate-level entry point to CFT data, OPE, blocks, and bootstrap.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017). Pedagogical treatment of radial quantization, blocks, crossing, and numerical bootstrap.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019). Broad review of conformal blocks and their role in modern bootstrap.

## Version history

- 2026-06-27: Replaced scaffold with a polished chapter overview and reading path for conformal blocks.
