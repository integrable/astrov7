---
title: "Rigorous Renormalization and RG"
description: "Chapter overview for rigorous renormalization and the renormalization group in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut; Polchinski; constructive RG literature"
topics:
  - rigorous renormalization
  - Wilsonian RG
  - continuum limits
  - constructive QFT
canonicalTopics:
  - rigorous-renormalization
  - wilsonian-rg
  - constructive-qft
researchStatus:
  established:
    - "Finite-cutoff RG steps can be formulated as exact transformations of measures, densities, effective interactions, local observables, or local algebras."
  active:
    - "The hard mathematical problem is proving uniform control of the flow as cutoffs are removed, especially in physically central four-dimensional theories and gauge theories."
---

Rigorous Renormalization and RG is the chapter where the renormalization group is treated as a mathematical operation on cutoff theories, not merely as a rule for drawing beta-function arrows. The central object is an exact scale transformation of measures, effective interactions, or local observables, together with estimates strong enough to remove regulators.

The chapter explains why the Wilsonian viewpoint is more than intuition. A cutoff QFT defines an honest finite-dimensional or regularized object. A renormalization step integrates out a scale, rewrites the result in local coordinates, and controls the generated remainder. The familiar language of relevant, marginal, and irrelevant operators is the linearized shadow of this exact map.

Read this chapter when you want to understand what a rigorous RG proof has to prove: not only a formal beta function, but a controlled trajectory in a space of interactions, measures, local fields, or algebras.

## Prerequisites

You should know the measure language in [Path Integrals as Measures](/rigorous-qft/path-integrals-as-measures/), especially [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/) and [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/). You should also know the constructive perspective from [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) and [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/) | The exact measure-theoretic meaning of blocking, pushforward, Gaussian integration, rescaling, and fixed points. |
| 2 | [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/) | The scale-by-scale proof strategy: covariance decompositions, local coupling coordinates, irrelevant remainders, and stability estimates. |
| 3 | [Scaling Limits](/rigorous-qft/rigorous-renormalization-rg/scaling-limits/) | The target of cutoff removal: convergence of rescaled fields, Schwinger functions, measures, or local algebras. |
| 4 | [Relevant, Irrelevant, and Marginal Directions](/rigorous-qft/rigorous-renormalization-rg/relevant-irrelevant-and-marginal-directions/) | The fixed-point linearization that explains tuning, universality, marginal logarithms, and corrections to scaling. |
| 5 | [Fixed Points and Stable Manifolds](/rigorous-qft/rigorous-renormalization-rg/fixed-points-and-stable-manifolds/) | The dynamical-systems geometry behind critical surfaces, counterterm tuning, and renormalized trajectories. |
| 6 | [Rigorous φ⁴ Renormalization](/rigorous-qft/rigorous-renormalization-rg/rigorous-phi-four-renormalization/) | The scalar-field laboratory for Wick ordering, counterterms, constructive RG, and dimension-dependent status. |
| 7 | [Polymer Expansions](/rigorous-qft/rigorous-renormalization-rg/polymer-expansions/) | The cluster-expansion technology that turns small local activities into convergent connected estimates. |
| 8 | [Multiscale Analysis](/rigorous-qft/rigorous-renormalization-rg/multiscale-analysis/) | Scale decompositions, fluctuation integration, localization, power counting, and uniform remainder bounds. |
| 9 | [Renormalization of Composite Fields](/rigorous-qft/rigorous-renormalization-rg/renormalization-of-composite-fields/) | How local observables beyond the bare field are defined by smearing, subtraction, mixing, source derivatives, and RG flow. |
| 10 | [Constructive RG Methods](/rigorous-qft/rigorous-renormalization-rg/constructive-rg-methods/) | A programmatic proof template: coordinates, polymer remainders, norms, regulators, tuning, and convergence. |

After this path, you should be able to distinguish an exact finite-cutoff RG identity, a perturbative coupling flow, a stable-manifold tuning statement, a polymer convergence estimate, a composite-field renormalization, and a full constructive continuum-limit proof.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\mathcal R_b\nu=(S_bB)_*\nu$ | RG as pushforward plus rescaling of a cutoff measure. | Scaling limits, fixed points, universality. |
| $e^{-V'}=\mathbb E_\Gamma(e^{-V(\phi+\zeta)})$ | Exact Gaussian fluctuation integration. | Wilsonian RG, Polchinski-type equations, constructive RG. |
| $C=\sum_j C_j$ | Multiscale covariance decomposition. | Cluster expansions, polymer expansions, finite-range estimates. |
| $D\mathcal R_b|_*h_i=b^{y_i}h_i$ | Linearized RG eigen-directions at a fixed point. | Relevant, irrelevant, and marginal classification. |
| $W^s(g_*)$ | Stable manifold or critical surface of a fixed point. | Counterterm tuning and renormalized trajectories. |
| $V_j=V_j^{\mathrm{loc}}+K_j$ | Local coupling coordinates plus controlled irrelevant remainder. | Rigorous phi-four renormalization, polymer expansions. |
| $[O_A]_R=Z_A{}^B O_B$ | Composite fields mix under renormalization. | Local observables, OPEs, Ward identities. |
| $\|K_{j+1}\|\le q\|K_j\|+O(\|V_j\|^2)$ | A constructive RG step closes only when the irrelevant remainder is contractive or summable. | Constructive RG methods and continuum-limit proofs. |

## Common confusions

**RG is just a change of variables.** Coarse-graining loses microscopic information; it is usually a semigroup operation, not an invertible reparametrization.

**The beta function is the RG.** A beta function is a coordinate projection of the full RG map. A rigorous RG proof controls the full effective interaction, including remainders and observable insertions.

**Irrelevant means nonexistent.** Irrelevant terms are generated and must be bounded. They are not literally absent; they are controlled by contraction estimates or improved power counting.

**Renormalizing the action automatically renormalizes every observable.** Local products such as $\phi^2(x)$ or $T_{\mu\nu}(x)$ have their own short-distance singularities. They usually require separate subtraction, mixing, and normalization conditions.

**A constructive RG method is a black-box algorithm.** The architecture is general, but the norms, regulators, local coordinates, covariance decomposition, and large-field estimates are tailored to the model.

**A scaling limit is just $a\to 0$.** One must specify rescaled observables, field normalizations, tuning, topology of convergence, and limiting axioms.

## Boundaries

This chapter focuses on theorem-oriented renormalization and RG. It does not replace the physical introduction to renormalization, Feynman counterterms, or EFT power counting elsewhere in the site. It also does not attempt to solve each constructive model in detail; model-specific constructions remain in the Constructive QFT chapter.

The pages here use scalar Euclidean examples for clarity. Gauge theories, fermions, BRST/BV methods, curved-spacetime renormalization, and perturbative algebraic QFT need additional pages because their mathematical difficulties are not just notational variants of scalar RG. Polymer and multiscale technology generalize beyond scalar models, but the norms and regulators are model-specific.

Composite fields are treated here from the RG and constructive point of view. Their distributional and microlocal definition in perturbation theory is developed more systematically in the Perturbative Algebraic QFT and Microlocal Analysis chapters.

## Where to go next

For examples where these ideas are used to build models, go to [Constructive QFT](/rigorous-qft/constructive-qft/). For the measure-theoretic background, go to [Path Integrals as Measures](/rigorous-qft/path-integrals-as-measures/). The natural next chapter is Perturbative Algebraic QFT, beginning with formal power series and causal perturbation theory.

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200. [doi:10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- L. P. Kadanoff, “Scaling Laws for Ising Models Near $T_c$,” *Physics Physique Fizika* **2** (1966) 263–272. [doi:10.1103/PhysicsPhysiqueFizika.2.263](https://doi.org/10.1103/PhysicsPhysiqueFizika.2.263).
- F. J. Wegner, “Corrections to Scaling Laws,” *Physical Review B* **5** (1972) 4529–4536. [doi:10.1103/PhysRevB.5.4529](https://doi.org/10.1103/PhysRevB.5.4529).
- J. Polchinski, “Renormalization and Effective Lagrangians,” *Nuclear Physics B* **231** (1984) 269–295. [doi:10.1016/0550-3213(84)90287-6](https://doi.org/10.1016/0550-3213(84)90287-6).
- K. G. Wilson and W. Zimmermann, “Operator Product Expansions and Composite Field Operators in the General Framework of Quantum Field Theory,” *Communications in Mathematical Physics* **24** (1972) 87–106. [doi:10.1007/BF01878448](https://doi.org/10.1007/BF01878448).
- W. Zimmermann, “Composite Operators in the Perturbation Theory of Renormalizable Interactions,” *Annals of Physics* **77** (1973) 536–569. [doi:10.1016/0003-4916(73)90430-2](https://doi.org/10.1016/0003-4916(73)90430-2).
- W. Zimmermann, “Normal Products and the Short Distance Expansion in the Perturbation Theory of Renormalizable Interactions,” *Annals of Physics* **77** (1973) 570–601. [doi:10.1016/0003-4916(73)90429-6](https://doi.org/10.1016/0003-4916(73)90429-6).
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).
- D. C. Brydges and G. Slade, “A Renormalisation Group Method. V. A Single Renormalisation Group Step.” [arXiv:1403.7256](https://arxiv.org/abs/1403.7256).
- V. Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991.
- G. Gallavotti and F. Nicolò, “Renormalization Theory in Four-Dimensional Scalar Fields I,” *Communications in Mathematical Physics* **100** (1985) 545–590. [doi:10.1007/BF01217729](https://doi.org/10.1007/BF01217729).

## Version history

- **2026-07-01:** Updated after adding composite-field renormalization and constructive RG methods.
- **2026-07-01:** Updated after adding polymer expansions and multiscale analysis.
- **2026-06-30:** Updated after adding fixed points, stable manifolds, and rigorous phi-four renormalization.
- **2026-06-30:** Updated after adding scaling limits and relevant/irrelevant/marginal directions.
- **2026-06-30:** First polished draft. Added the chapter doorway after the first two ordinary RG pages were created.
