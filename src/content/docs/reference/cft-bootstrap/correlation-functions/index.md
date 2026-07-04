---
title: "Correlation Functions"
description: "Chapter overview for conformal correlation functions, two- and three-point kinematics, four-point cross-ratios, tensor structures, and Ward identities in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Osborn and Petkou 1994; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - correlation functions
  - conformal covariance
  - two-point functions
  - three-point functions
  - four-point functions
  - cross-ratios
  - tensor structures
  - Ward identities
canonicalTopics:
  - conformal-correlation-functions
  - scalar-correlators
  - spinning-correlators
  - cross-ratios
  - conformal-ward-identities
researchStatus:
  established:
    - "Conformal symmetry fixes scalar two- and three-point functions up to constants, reduces four-point functions to functions of cross-ratios, and strongly constrains spinning correlators through tensor structures."
    - 'In a normalized primary basis, two-point and three-point data are the first visible pieces of the CFT data that later enter the OPE and conformal-block expansion.'
  active:
    - "Efficient tensor-structure bases, spinning conformal blocks, Lorentzian correlators, defect correlators, and numerical bootstrap implementations remain active technical areas."
---

Correlation Functions is the chapter in the CFT and Bootstrap volume where conformal symmetry first becomes a precision machine. The previous chapters explained which transformations act, how local operators transform, and how radial quantization organizes the Hilbert space. This chapter asks what those facts imply for the actual observables of a CFT:

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

The short answer is striking. Two-point functions define the operator inner product and normalization. Three-point functions define the basic interaction data of the operator algebra. Four-point functions are the first place where symmetry leaves nontrivial functions undetermined, and those functions are where the OPE, conformal blocks, and crossing symmetry begin to bite.

Read this chapter when you want to understand the kinematic grammar of CFT before learning the dynamical bootstrap equations. A CFT is not solved by knowing the allowed forms of correlators, but the allowed forms are the frame in which the solution is stated.

$$
\text{CFT data}
\quad\Longrightarrow\quad
\text{correlators}
\quad\Longrightarrow\quad
\text{OPE, blocks, and crossing}.
$$

## Prerequisites

You should know the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/), the basic meaning of [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), and the operator language from [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/). The pages [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/), and [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/) are especially useful.

This chapter mostly uses Euclidean flat-space correlators at separated points. Lorentzian orderings, contact terms, anomalies, thermal correlators, and defect correlators require extra choices and are flagged when they appear.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/) | The normalization, orthogonality, and tensor structures that make the operator spectrum measurable. |
| 2 | [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/) | The first nontrivial CFT data: scalar three-point coefficients and the beginning of OPE coefficients. |
| 3 | [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) | The first correlators with undetermined functions, hence the natural home of OPE channels and crossing. |
| 4 | [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/) | The conformal invariants $u,v$ and the $z,\bar z$ variables used throughout bootstrap calculations. |
| 5 | [Conformal Frame](/cft-bootstrap/correlation-functions/conformal-frame/) | How conformal transformations fix points to convenient positions and reduce correlators to invariant data. |
| 6 | [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/) | The tensor-structure problem for operators with spin. |
| 7 | [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) | Correlators involving conserved spin-one currents and the normalization of global-symmetry charges. |
| 8 | [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) | The normalization $C_T$, stress-tensor Ward identities, and the universal role of $T_{\mu\nu}$. |
| 9 | [Embedding-Space Formalism Preview](/cft-bootstrap/correlation-functions/embedding-space-formalism-preview/) | A compact formalism for conformal covariance and spinning tensor structures. |
| 10 | [Conformal Ward Identities for Correlators](/cft-bootstrap/correlation-functions/conformal-ward-identities-for-correlators/) | How conserved charges and stress tensors impose differential and contact-term constraints on correlators. |

After this path, you should be able to recognize which parts of a low-point correlator are fixed by symmetry, which constants are genuine CFT data, and why four-point functions are the doorway to the conformal bootstrap.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\langle \mathcal O_i(x)\mathcal O_j(0)\rangle=\delta_{ij}/|x|^{2\Delta_i}$ | The orthonormal scalar two-point convention. | OPE identity term, reflection positivity, bootstrap normalization. |
| $I_{\mu\nu}(x)=\delta_{\mu\nu}-2x_\mu x_\nu/x^2$ | The inversion tensor used in spinning two-point functions. | Currents, stress tensor, spinning correlators. |
| $\lambda_{123}$ | A scalar three-point coefficient in an orthonormal basis. | OPE coefficients and conformal-block coefficients. |
| $u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}$ and $v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}$ | The two independent four-point cross-ratios for scalar correlators in $d\geq2$. | Four-point bootstrap equations. |
| $\mathcal G(u,v)$ | The reduced four-point function after the fixed coordinate dependence is stripped off. | OPE channel decompositions and crossing. |
| Tensor structures | Independent conformally covariant ways to contract spin indices. | Spinning OPE coefficients and mixed-correlator bootstrap. |
| Ward identities | Relations imposed by conserved currents and stress tensors. | Current algebra, stress-tensor data, anomalies, conformal collider bounds. |

The conceptual landmark is this separation:

$$
\text{kinematics fixed by symmetry}
\quad + \quad
\text{dynamical constants and functions}
\quad = \quad
\text{CFT correlators}.
$$

For two and three scalar primaries, the functions are fixed and the dynamical information is a finite set of constants. For four scalar primaries, conformal symmetry leaves functions of cross-ratios. The bootstrap program is the statement that those functions are not arbitrary: they must admit consistent OPE decompositions in every channel.

## Common confusions

**A correlator is not automatically a time-ordered Lorentzian correlator.** In this chapter, an unqualified correlator means a Euclidean separated-point correlator. Lorentzian Wightman, time-ordered, retarded, and out-of-time-ordered correlators are related by analytic continuation and ordering choices, not by wishful notation.

**Conformal symmetry does not determine every correlator.** It fixes two- and three-point scalar correlators up to constants and reduces four-point scalar correlators to functions of cross-ratios. The remaining functions are where dynamics lives.

**Two-point normalization is a convention, but not a harmless afterthought.** Rescaling an operator changes its three-point coefficients and OPE coefficients. Bootstrap numbers are meaningful only after the two-point basis has been fixed.

**Spinning correlators are not just scalar correlators with indices attached.** Tensor structures are part of the data bookkeeping. A single set of external spins can allow several independent structures and therefore several independent coefficients.

**Contact terms are invisible at separated points.** Many simple formulas in this chapter hold away from coincident insertions. Contact terms become essential in Ward identities, anomalies, curved-space variations, and conserved-current normalizations.

## Boundaries

This chapter is about the conformal kinematics of low-point correlation functions. It explains the forms of two-, three-, and four-point functions and prepares the notation used in the OPE and bootstrap chapters.

The [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) chapter is the home for the operator algebra and OPE convergence. The [Conformal Blocks](/cft-bootstrap/conformal-blocks/) chapter is the home for packaging primary-plus-descendant exchange into blocks. The [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) chapter is the home for imposing consistency between different OPE channels.

Detailed two-dimensional Virasoro Ward identities, chiral correlators, current algebras, and minimal-model correlators are developed later in [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/), [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/), and [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/).

## Where to go next

After the scalar low-point pages, continue to [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/). The OPE explains why the constants in three-point functions and the spectra visible in two-point functions are enough to build higher-point correlators.

Readers interested in numerical bootstrap should move from [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) to [Conformal Blocks](/cft-bootstrap/conformal-blocks/) and then to [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/). Readers interested in two-dimensional CFT should next read [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/) and [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/).

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the chapters on global conformal invariance, two-dimensional conformal invariance, Ward identities, and operator formalism.
- H. Osborn and A. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals of Physics* **231** (1994), for higher-dimensional current and stress-tensor correlators.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for a compact modern path from conformal kinematics to the bootstrap.
- D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for conformal covariance, reflection positivity, OPE, and bootstrap setup.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), for correlation functions, conformal blocks, and bootstrap applications.

## Version history

- 2026-06-27: Replaced the scaffold chapter page with a polished chapter overview and reading path for correlation functions.
