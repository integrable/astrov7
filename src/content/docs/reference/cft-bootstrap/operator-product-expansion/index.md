---
title: "Operator Product Expansion"
description: "Chapter overview for the operator product expansion in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Wilson 1969; Kadanoff 1969; Polyakov 1974; Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - operator product expansion
  - local operators
  - CFT data
  - radial quantization
  - crossing symmetry
canonicalTopics:
  - operator-product-expansion
  - ope-coefficients
  - conformal-data
  - radial-quantization
  - bootstrap-consistency
researchStatus:
  established:
    - "In Euclidean unitary CFT, the OPE is a convergent expansion inside correlation functions when the fused operators are separated from all other insertions."
    - "The OPE coefficients, together with the spectrum of primary operators and global-symmetry representation data, are part of the CFT data."
  active:
    - "Lorentzian limits, lightcone OPEs, defect OPEs, spinning structures, nonunitary theories, logarithmic theories, and efficient numerical use of OPE data remain active research areas."
---

The Operator Product Expansion chapter explains the multiplication law of local operators in a conformal field theory. It is the chapter where correlation functions stop looking like unrelated functions and start looking like matrix elements of an algebra.

The central idea is that when two local operators approach one another, their product can be replaced, inside correlation functions, by a sum over local operators at a nearby point:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k(x,\partial)\,\mathcal O_k(0).
$$

In a CFT this is not merely dimensional analysis. Conformal symmetry fixes the descendant terms once the exchanged primary and the three-point coefficient are known. The OPE is therefore the bridge between local operator data, conformal blocks, and crossing symmetry.

Read this chapter when you want to understand why a small sphere surrounding two insertions can be traded for a sum over states, why three-point coefficients are structure constants, and why bootstrap equations are associativity constraints for the operator algebra.

## Prerequisites

You should know the [Conventions and Notation](/cft-bootstrap/conventions/), the meaning of [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), and the radial-quantization ideas developed in [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) and [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/).

For a first pass, it is enough to know scalar two- and three-point functions from the [Correlation Functions](/cft-bootstrap/correlation-functions/) chapter. For the convergence and associativity pages, the Hilbert-space viewpoint from [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) and [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) becomes more useful.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) | The meaning of the OPE inside correlators, the scalar primary formula, identity terms, descendants, and simple examples. |
| 2 | [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) | Why the Euclidean OPE is a convergent expansion in radial quantization, not just a formal short-distance asymptotic series. |
| 3 | [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) | How three-point coefficients become structure constants, how normalization choices enter, and how global symmetries constrain coefficients. |
| 4 | [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/) | The conceptual origin of crossing symmetry: different orders of fusing operators must define the same correlator. |
| 5 | [Radial Ordering](/cft-bootstrap/operator-product-expansion/radial-ordering/) | How ordering by radius replaces time ordering in Euclidean radial quantization and organizes operator products. |
| 6 | [Identity Operator in the OPE](/cft-bootstrap/operator-product-expansion/identity-operator-in-the-ope/) | How two-point normalization, disconnected pieces, and the vacuum channel appear as the identity contribution. |
| 7 | [Stress-Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/) | How the universal stress-tensor contribution encodes conformal Ward identities and the normalization $C_T$. |
| 8 | [Current OPE](/cft-bootstrap/operator-product-expansion/current-ope/) | How global symmetry currents act on charged local operators through singular OPE terms and Ward identities. |
| 9 | [Conformal Data from OPE](/cft-bootstrap/operator-product-expansion/conformal-data-from-ope/) | How the spectrum and OPE coefficients together define the local CFT data used by the bootstrap. |
| 10 | [Lightcone OPE Preview](/cft-bootstrap/operator-product-expansion/lightcone-ope-preview/) | A controlled preview of Lorentzian and analytic-bootstrap limits where one separation becomes lightlike. |

After this path, you should be able to read a four-point function as a sum over exchanged conformal multiplets and recognize crossing symmetry as OPE associativity.

## Landmarks

The chapter has four landmarks.

| Landmark | Meaning |
|---|---|
| Local replacement | A cluster of nearby operators can be replaced by a sum of local operators at one point, inside correlators. |
| Primary plus descendants | In a CFT the contribution of a primary includes its whole conformal multiplet. Descendant coefficients are fixed by symmetry. |
| Structure constants | Once two-point functions are normalized, three-point coefficients are the OPE coefficients of the operator algebra. |
| Associativity | Different OPE channels of the same correlator must agree. This is the origin of bootstrap equations. |

The most important schematic formula is

$$
\mathcal O_i\times \mathcal O_j
=\sum_{\mathcal O_k}\lambda_{ijk}\,\mathcal O_k+\text{descendants}.
$$

The notation hides spacetime dependence, spin structures, global-symmetry tensors, and descendant differential operators. Those details are not decoration. They are what make the OPE usable in actual correlators.

## Common confusions

Do not read the OPE as a statement that the literal product of two unrenormalized fields at the same point is always well-defined. The OPE is a statement about separated insertions, local operators, and correlation functions. Coincident-point singularities are organized by the expansion; they are not wished away.

Do not confuse a CFT OPE with an ordinary Taylor expansion. Taylor expanding one operator around another would only produce derivatives of that operator. The OPE sums over all operators allowed by symmetry, including operators that are not descendants of either original insertion.

Do not assume that the symbol $\sim$ always means “asymptotic and divergent.” In many two-dimensional formulas $\sim$ means “has the following singular part.” In Euclidean radial quantization for a unitary CFT, the OPE inside correlators has a genuine convergence domain.

Do not identify an OPE coefficient before fixing operator normalization. Rescaling a primary rescales every OPE coefficient involving it. Bootstrap statements are convention-independent only after the two-point metric and representation conventions are fixed.

Do not forget the identity operator. The identity channel is responsible for the leading disconnected or vacuum contribution in many correlators. Omitting it is one of the fastest ways to make a four-point function fail basic limits.

## Boundaries

This chapter focuses on the local operator OPE in ordinary CFT. It does not replace the [Conformal Blocks](/cft-bootstrap/conformal-blocks/) chapter, which builds the conformal-block expansion after a multiplet is exchanged. It also does not replace the [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) chapter, where OPE associativity becomes numerical and analytic constraints.

The chapter treats two-dimensional holomorphic OPE notation only as needed for orientation. The full Virasoro version belongs in [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/).

The chapter also does not attempt to classify extended defects, line operators, or higher-form charged objects. Defect OPEs and boundary OPEs belong later in [Boundary, Defect, and Interface CFT](/cft-bootstrap/boundary-defect-interface-cft/). Higher-form symmetry ideas belong primarily in the symmetry and topology volumes, with cross-links when needed.

## Where to go next

After this chapter, the natural next step is [Conformal Blocks](/cft-bootstrap/conformal-blocks/). The OPE tells you which primary multiplets can appear; conformal blocks tell you the full kinematic contribution of each multiplet to a four-point function.

Then read [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/). The bootstrap begins when the same correlator is expanded using two different OPE channels and the two answers are required to agree.

For specializations, go to [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) for holomorphic OPEs and Virasoro methods, [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/) for spinning operators and higher-dimensional tensor structures, [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) for lightcone limits, and [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) for positivity constraints derived from OPE coefficients.

## References

- K. G. Wilson, “Non-Lagrangian Models of Current Algebra,” *Physical Review* **179** (1969). The original operator-product viewpoint in quantum field theory.
- L. P. Kadanoff, “Operator Algebra and the Determination of Critical Indices,” *Physical Review Letters* **23** (1969). Early operator-algebra language in critical phenomena.
- A. M. Polyakov, “Nonhamiltonian Approach to Conformal Quantum Field Theory,” *Soviet Physics JETP* **39** (1974). Classic bootstrap and OPE perspective.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory* (Springer, 1997). Standard reference for two-dimensional OPEs, radial quantization, conformal families, and crossing.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016). Efficient modern introduction to higher-dimensional CFT and the OPE.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017). Clear account of radial quantization, OPE convergence, conformal blocks, and bootstrap equations.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019). Broad review of CFT data, OPE, blocks, crossing, and numerical bootstrap.

## Version history

- 2026-06-27: Replaced scaffold with a polished chapter overview and reading path for the OPE chapter.
