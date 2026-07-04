---
title: "Microlocal Analysis in QFT"
description: "Chapter overview for wavefront sets, singular products, Hadamard singularities, and local spectral conditions in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Hörmander; Duistermaat–Hörmander; Radzikowski; Brunetti–Fredenhagen–Köhler; Brunetti–Fredenhagen; Hollands–Wald"
topics:
  - microlocal analysis
  - wavefront sets
  - products of distributions
  - microlocal spectrum condition
  - Hadamard states
  - propagation of singularities
canonicalTopics:
  - microlocal-analysis
  - wavefront-set
  - product-of-distributions
  - microlocal-spectrum-condition
  - hadamard-state
researchStatus:
  established:
    - "Wavefront sets, Hörmander's product criterion, Hadamard two-point functions, and propagation of singularities are standard tools for controlling singular distributions in rigorous QFT."
  active:
    - "The same tools remain central in current work on curved-spacetime QFT, gauge theory, boundaries, defects, and perturbative renormalization."
---

Microlocal Analysis in QFT is the chapter in the Mathematical and Rigorous QFT volume where singular formulas become controlled operations on distributions. It is the technical bridge between the warning "fields are distributions" and the constructive machinery of Wick products, time-ordered products, Hadamard states, and curved-spacetime perturbation theory.

The chapter exists because ordinary distribution theory is too coarse for QFT. Singular support tells us where a propagator or correlation function is singular, but QFT also needs to know the directions of those singularities. Wavefront sets provide exactly that directional information.

Read this chapter when you want to understand why some singular products are well defined, why some require renormalization, why Hadamard two-point functions have universal light-cone singularities, and how the flat-space spectral condition survives on curved spacetimes without global momentum.

$$
\text{QFT singularity control}
\quad=
\quad
\text{location}+\text{cotangent direction}+\text{propagation}+\text{extension}.
$$

## Prerequisites

You should know the status conventions in [Conventions](/rigorous-qft/conventions/), the distributional warning in [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), and the role of smearing from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/). For the QFT motivation, [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/), and [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) are the closest companions.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) | The directional singular support $\operatorname{WF}(u)\subset T^*X\setminus0$ and the reason singularities in QFT must be tracked in cotangent directions. |
| 2 | [Products of Distributions](/rigorous-qft/microlocal-analysis-qft/products-of-distributions/) | Hörmander's criterion for multiplying distributions and the diagonal-pullback view behind coincident-point products. |
| 3 | [Microlocal Spectrum Condition](/rigorous-qft/microlocal-analysis-qft/microlocal-spectrum-condition/) | The curved-spacetime replacement for the flat-space positive-energy spectral condition, expressed as a wavefront-set constraint. |
| 4 | [Hadamard Two-Point Functions](/rigorous-qft/microlocal-analysis-qft/hadamard-two-point-functions/) | The local Hadamard parametrix, the smooth state-dependent remainder, and the two-point singularity used for Wick powers. |
| 5 | [Propagation of Singularities](/rigorous-qft/microlocal-analysis-qft/propagation-of-singularities/) | The theorem explaining why hyperbolic singularities propagate along bicharacteristics and project to null geodesics. |

After this path, you should be able to say when a singular product is canonical, when it requires extension or renormalization, why Hadamard singularities are lightlike, and why future-directed wavefront sets are the local remnant of positive energy.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\operatorname{WF}(u)$ | The set of singular base points and singular cotangent directions of a distribution. | Products, pullbacks, propagation of singularities. |
| $uv$ exists if no opposite covectors occur | Hörmander's product criterion for distributions on the same manifold. | Wick products, composite fields, time-ordered products. |
| $uv=\Delta^*(u\boxtimes v)$ | Product as pullback to the diagonal. | Renormalization as extension at diagonals. |
| $N^*\Delta$ | Conormal bundle of a diagonal; the obstruction locus for coincident-point restriction. | Epstein–Glaser renormalization and local counterterms. |
| $\operatorname{WF}(\omega_2)$ Hadamard form | The two-point singularity is null, paired, and future-directed. | Hadamard states and stress tensors. |
| $\operatorname{WF}(\omega_n)\subset\Gamma_n$ | The microlocal spectrum condition for $n$-point functions. | Curved-spacetime QFT and perturbative interacting fields. |
| $\operatorname{Char}(P)=\{p=0\}$ | The characteristic set of the principal symbol. | Propagation of singularities and hyperbolic parametrices. |
| Flow of $H_p$ | Singular covectors propagate along Hamiltonian bicharacteristics. | Null-geodesic singularities of propagators. |

## Common confusions

**Singular support is enough.** Singular support says where a distribution is singular. Wavefront sets say in which cotangent directions. Products and pullbacks depend on the directions.

**Every failed product is meaningless forever.** A failed product criterion means there is no canonical product from distribution theory alone. Renormalization can still define an extension, but that extension carries local ambiguity.

**Microlocal spectrum means global energy.** On a generic curved spacetime there may be no global conserved energy. The microlocal spectrum condition is a local positive-frequency condition on singular covectors.

**Hadamard means vacuum.** A Hadamard condition fixes the universal ultraviolet singularity, not a unique global state. Different Hadamard states differ by smooth two-point functions.

**Propagation of singularities means all null geodesics are singular.** The theorem says existing singularities propagate along bicharacteristics. It does not say every solution is singular on every null geodesic.

**Wavefront sets solve all operator questions.** They control scalar distributional singularities. Operator domains, positivity, gauge constraints, and nonperturbative existence require additional arguments.

## Boundaries

This chapter does:

- define the microlocal data needed to control singular distributions in QFT;
- explain products and pullbacks through wavefront-set criteria;
- connect the flat-space spectral condition to the curved-spacetime microlocal spectrum condition;
- explain the Hadamard two-point singularity and its smooth state-dependent remainder;
- identify the propagation theorem behind null-geodesic singularities;
- prepare the analytic language for Wick powers, time-ordered products, and renormalization by extension.

This chapter does not try to be a full course in microlocal analysis, pseudodifferential operators, or Fourier integral operators. It also does not replace the locally covariant QFT chapter, where the same tools are used to build field algebras on curved spacetimes, or the perturbative algebraic QFT chapter, where time-ordered products and renormalization conditions are developed.

## Where to go next

For curved-spacetime physics, continue with [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) and [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/). For perturbative renormalization, continue with [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/).

## References

### Standard first pass

- Lars Hörmander, *The Analysis of Linear Partial Differential Operators I: Distribution Theory and Fourier Analysis*, for wavefront sets, products, and pullbacks of distributions.
- Lars Hörmander, *The Analysis of Linear Partial Differential Operators III: Pseudo-Differential Operators*, for propagation of singularities.
- Marek J. Radzikowski, "Micro-Local Approach to the Hadamard Condition in Quantum Field Theory on Curved Space-Time," *Communications in Mathematical Physics* **179** (1996), 529–553. [DOI: 10.1007/BF02100096](https://doi.org/10.1007/BF02100096).
- Romeo Brunetti, Klaus Fredenhagen, and Martin Köhler, "The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes," *Communications in Mathematical Physics* **180** (1996), 633–652. [arXiv:gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056), [DOI: 10.1007/BF02099626](https://doi.org/10.1007/BF02099626).

### Deeper references

- J. J. Duistermaat and L. Hörmander, "Fourier Integral Operators. II," *Acta Mathematica* **128** (1972), 183–269. [DOI: 10.1007/BF02392165](https://doi.org/10.1007/BF02392165).
- Romeo Brunetti and Klaus Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [DOI: 10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- S. A. Fulling, F. J. Narcowich, and Robert M. Wald, "Singularity Structure of the Two-Point Function in Quantum Field Theory in Curved Spacetime, II," *Annals of Physics* **136** (1981), 243–272. [DOI: 10.1016/0003-4916(81)90088-0](https://doi.org/10.1016/0003-4916(81)90088-0).
- Kasia Rejzner, *Perturbative Algebraic Quantum Field Theory*, for a modern account of microlocal methods in pAQFT.

## Version history

- **2026-07-01:** Updated after adding Hadamard two-point functions and propagation of singularities.
- **2026-07-01:** Initial chapter overview after adding products of distributions and the microlocal spectrum condition.
