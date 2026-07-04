---
title: "Constructive QFT"
description: "Chapter overview for constructive quantum field theory in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Glimm–Jaffe constructive QFT; Simon P(φ)₂; Rivasseau constructive renormalization; Osterwalder–Schrader reconstruction; Wilsonian RG; cluster expansions and correlation inequalities."
topics:
  - constructive QFT
  - Euclidean measures
  - continuum limits
  - rigorous renormalization
  - nonperturbative QFT
canonicalTopics:
  - constructive-quantum-field-theory
  - euclidean-quantum-field-theory
  - continuum-limit
  - rigorous-renormalization
researchStatus:
  established:
    - "Constructive QFT has produced rigorous interacting continuum models, especially in low-dimensional scalar, exponential, and fermionic theories."
  active:
    - "Four-dimensional interacting gauge theories and several physically central continuum limits remain open or only partially controlled."
---

Constructive QFT is the chapter in the Mathematical and Rigorous QFT volume where formal quantum field theories are asked to exist. It is the nonperturbative construction wing: start with regularized models, prove estimates, remove cutoffs, and verify that the limit satisfies precise QFT axioms.

The chapter is not trying to replace physical intuition. It explains which parts of the intuition can be made into theorems. A finite lattice model or cutoff path integral is often easy to define; the constructive problem is proving that a nontrivial continuum object survives after the regulators are removed.

Read this chapter when you want to understand what it means to say that an interacting QFT has been constructed, not merely written down.

$$
\text{constructive QFT}
=
\text{cutoff model}
+
\text{uniform estimates}
+
\text{continuum limit}
+
\text{axiom verification}.
$$

## Prerequisites

You should know [Levels of Rigor in QFT](/rigorous-qft/what-is-rigorous-qft/levels-of-rigor-in-qft/), [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/), and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) is the free example behind most scalar Euclidean constructions.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) | The proof strategy: regularize, estimate, remove cutoffs, reconstruct, and prove nontriviality. |
| 2 | [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) | The probability-measure interpretation of Euclidean path integrals and Schwinger functions. |
| 3 | [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) | The free scalar measure, covariance, support, Wick powers, and reflection positivity. |
| 4 | [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) | The first general interacting construction from Wick-ordered polynomial perturbations. |
| 5 | [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/) | The canonical quartic two-dimensional model and its phases. |
| 6 | [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/) | The first scalar model where mass renormalization becomes essential. |
| 7 | [Sine-Gordon Model: Rigorous Construction](/rigorous-qft/constructive-qft/sine-gordon-model-rigorous-construction/) | A non-polynomial construction using Wick-ordered vertex operators and Coulomb-gas expansions. |
| 8 | [Gross–Neveu Model: Preview](/rigorous-qft/constructive-qft/gross-neveu-model-preview/) | A fermionic asymptotically free example controlled by determinant and RG estimates. |
| 9 | [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) | Polymer and connected-cluster technology for analyticity, thermodynamic limits, and clustering. |
| 10 | [Correlation Inequalities](/rigorous-qft/constructive-qft/correlation-inequalities/) | Positivity, monotonicity, domination, and mass-gap tools from statistical mechanics. |
| 11 | [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) | How bare parameters, field normalizations, and estimates are tuned while cutoffs are removed. |
| 12 | [What Is Open in Four Dimensions?](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/) | A status map of scalar triviality, Yang–Mills, chiral gauge theory, and other four-dimensional problems. |

After this path, you should be able to distinguish a cutoff model from a constructed continuum QFT, explain why Euclidean fields live on distributions, recognize the main estimates behind low-dimensional constructive examples, and state why four-dimensional continuum QFT is mathematically special.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Cutoff model | A finite-volume, lattice, mollified, or momentum-cutoff theory. | All constructive estimates. |
| $\mu_C$ | Gaussian free-field measure with covariance $C=(-\Delta+m^2)^{-1}$. | Gaussian measures and interacting perturbations. |
| Wick powers and counterterms | Renormalized local functions of a singular Gaussian field. | $P(\phi)_2$, $\phi^4_2$, $\phi^4_3$, and composite fields. |
| Non-polynomial and fermionic interactions | Vertex operators in sine-Gordon and four-fermion terms in Gross–Neveu. | Constructive examples beyond scalar polynomials. |
| Polymer activity $w(\gamma)$ | Local weight assigned to a finite polymer. | Analyticity, thermodynamic limits, and exponential clustering. |
| FKG/GKS/Ginibre inequalities | Positivity and monotonicity theorems for ordered systems. | Boundary comparisons, phase information, and mass-gap estimates. |
| $a\to0$ with tuned bare data | The constructive ultraviolet continuum limit. | Renormalized Schwinger functions and OS reconstruction. |
| $[\lambda_{\phi^4}]=4-d$ | The power-counting reason four dimensions are marginal for scalar quartic interactions. | Triviality and four-dimensional open problems. |

## Common confusions

**A cutoff model is not yet a constructed QFT.** A finite-dimensional integral, finite lattice system, or regularized Hamiltonian is usually rigorous by itself. Constructive QFT is the proof that the relevant continuum limit exists and satisfies QFT axioms.

**Euclidean probability is not automatically Lorentzian quantum theory.** A positive Euclidean measure gives moments, but OS reconstruction needs reflection positivity and other hypotheses. Without them, the measure may define a statistical field theory rather than a relativistic QFT.

**Wick ordering is part of the definition.** In $P(\phi)_2$ and related scalar models, Wick ordering subtracts divergent Gaussian self-contractions. In $\phi^4_3$, Wick ordering is necessary but not sufficient; mass renormalization is also needed.

**Perturbative renormalization and constructive renormalization are related but not identical.** Perturbation theory identifies counterterms and asymptotic expansions. Constructive renormalization proves that a nonperturbative object exists behind those formal expansions.

**Cluster expansions are not the same as cluster decomposition.** A cluster expansion is a convergent polymer or Mayer series. Cluster decomposition is a property of correlations at large separation.

**Correlation inequalities are not automatic positivity.** A Euclidean measure may be positive without satisfying FKG, GKS, or Ginibre hypotheses. The relevant order, ferromagnetic sign, or reflection-positive structure must be checked model by model.

**Perturbative renormalization is not cutoff removal.** Perturbative counterterms can suggest the right approximating sequence. A constructive proof must still show that the full nonperturbative sequence converges and satisfies the intended axioms.

**Four dimensions are not merely harder low dimensions.** In four dimensions, marginality, triviality, asymptotic freedom, gauge redundancy, and infrared mass gaps create qualitatively new problems.

## Boundaries

This chapter does:

- explain constructive QFT as a theorem-level existence project;
- define Euclidean measures and Gaussian free fields as rigorous path-integral objects;
- introduce $P(\phi)_2$, $\phi^4_2$, $\phi^4_3$, sine-Gordon, and Gross–Neveu as benchmark constructive models;
- explain cluster expansions and correlation inequalities as proof technologies;
- distinguish cutoff regularization, renormalization, continuum limits, OS reconstruction, phases, and nontriviality.

This chapter does not try to do:

- teach all probability theory or measure theory from scratch;
- replace the physical Nonperturbative QFT volume;
- provide numerical lattice methods;
- give a full constructive proof of four-dimensional Yang–Mills theory;
- treat perturbative algebraic QFT, BV-BRST, or factorization algebras.

Those topics belong to later chapters in this volume or to neighboring volumes. Here the aim is to understand what rigorous nonperturbative existence claims mean.

## Where to go next

After the first twelve pages, the chapter has completed its first pass through constructive QFT: examples, proof technologies, cutoff removal, and four-dimensional obstructions. The continuum-limit page points toward rigorous renormalization and lattice-to-continuum constructions; the four-dimensional page points toward the later Open Problems and No-Go Theorems chapter.

For a different rigorous route, return to [Locally Covariant QFT](/rigorous-qft/locally-covariant-qft/) or continue later to Perturbative Algebraic QFT. For the physical nonperturbative story, use the Nonperturbative QFT volume once the corresponding pages exist.

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991. DOI: [10.1515/9781400862085](https://doi.org/10.1515/9781400862085).

### Deeper references

- James Glimm, Arthur Jaffe, and Thomas Spencer, "The Wightman Axioms and Particle Structure in the $P(\phi)_2$ Quantum Field Model," *Annals of Mathematics* **100** (1974), 585–632. DOI: [10.2307/1970959](https://doi.org/10.2307/1970959).
- Joel Feldman and Konrad Osterwalder, "The Wightman Axioms and the Mass Gap for Weakly Coupled $\phi^4_3$ Quantum Field Theories," *Annals of Physics* **97** (1976), 80–135. DOI: [10.1016/0003-4916(76)90223-2](https://doi.org/10.1016/0003-4916(76)90223-2).
- Roman Kotecký and David Preiss, "Cluster Expansion for Abstract Polymer Models," *Communications in Mathematical Physics* **103** (1986), 491–498. DOI: [10.1007/BF01211762](https://doi.org/10.1007/BF01211762).
- C. M. Fortuin, P. W. Kasteleyn, and J. Ginibre, "Correlation Inequalities on Some Partially Ordered Sets," *Communications in Mathematical Physics* **22** (1971), 89–103. DOI: [10.1007/BF01651330](https://doi.org/10.1007/BF01651330).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Michael Aizenman and Hugo Duminil-Copin, "Marginal Triviality of the Scaling Limits of Critical 4D Ising and $\phi^4_4$ Models," *Annals of Mathematics* **194** (2021), 163–235. DOI: [10.4007/annals.2021.194.1.3](https://doi.org/10.4007/annals.2021.194.1.3), arXiv: [1912.07973](https://arxiv.org/abs/1912.07973).
- Arthur Jaffe and Edward Witten, "Quantum Yang–Mills Theory," Clay Mathematics Institute Millennium Problem statement. PDF: [claymath.org/wp-content/uploads/2022/06/yangmills.pdf](https://www.claymath.org/wp-content/uploads/2022/06/yangmills.pdf).

## Version history

- **2026-06-30:** Added Continuum Limit and Renormalization and What Is Open in Four Dimensions to the overview.
- **2026-06-29:** Added Cluster Expansions and Correlation Inequalities to the overview.
- **2026-06-29:** Updated after adding Sine-Gordon Model: Rigorous Construction and Gross–Neveu Model: Preview.
- **2026-06-29:** Updated after adding φ⁴₂ Theory and φ⁴₃ Theory.
- **2026-06-29:** Updated after adding Gaussian Measures and P(φ)₂ Models.
- **2026-06-29:** Initial chapter overview created after the chapter reached two ordinary pages.
