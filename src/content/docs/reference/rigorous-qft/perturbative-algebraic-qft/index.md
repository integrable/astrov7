---
title: "Perturbative Algebraic QFT"
description: "Chapter overview for perturbative algebraic quantum field theory in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Epstein–Glaser causal perturbation theory; Brunetti–Fredenhagen–Dütsch; Fredenhagen–Rejzner; Rejzner pAQFT"
topics:
  - perturbative algebraic QFT
  - causal perturbation theory
  - formal power series
  - renormalized time-ordered products
  - interacting fields
  - Feynman diagrams
canonicalTopics:
  - perturbative-algebraic-qft
  - causal-perturbation-theory
  - formal-power-series
  - interacting-fields
  - feynman-diagrams
researchStatus:
  established:
    - "Perturbative algebraic QFT gives a mathematically precise construction of interacting local algebras as formal power series, using causal factorization, renormalized time-ordered products, local covariance, finite renormalization, relative S-matrices, and diagrammatic expansions."
  active:
    - "The framework is perturbative: it constructs coefficientwise interacting theories, not generally convergent nonperturbative models. Gauge theories require BV-BRST refinements treated later."
---

Perturbative Algebraic QFT is the chapter in the Mathematical and Rigorous QFT volume where perturbation theory stops being a recipe for Feynman diagrams and becomes a local algebraic construction. Its central idea is to keep the algebraic locality of AQFT while constructing interactions only as formal power series.

The chapter is not an attempt to prove that perturbation series converge. Instead, it explains how much of perturbative QFT can be made exact coefficient by coefficient: fields are functionals, products are deformation products, time-ordering is a renormalized multilinear map, and interactions are introduced by relative $S$-matrices or retarded products.

Read this chapter when you want to understand the rigorous content of statements such as “renormalization is the extension of distributions,” “Feynman diagrams are derived from time-ordered products,” “interacting fields are formal power series,” and “scheme dependence is finite local freedom.”

$$
\text{pAQFT}
=\text{local algebras}
+\text{causal perturbation theory}
+\text{formal power series}.
$$

## Prerequisites

You should know the status conventions in [Conventions](/rigorous-qft/conventions/), the idea of [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), and the distributional warnings in [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). The pages on [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) and [Renormalization of Composite Fields](/rigorous-qft/rigorous-renormalization-rg/renormalization-of-composite-fields/) are useful companions, but not prerequisites for a first pass.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/) | The logical status of perturbative constructions: coefficientwise algebra, $\mathbb R[[\lambda]]$-modules, formal $S$-matrices, and what “formal” does and does not mean. |
| 2 | [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/) | The inductive construction of time-ordered products from causal factorization and distribution extension to diagonals. |
| 3 | [Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/) | The precise extension theorem behind causal renormalization: scaling degree, local ambiguity, and finite counterterm freedom. |
| 4 | [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/) | The multilinear maps $T_n$ that generate perturbation theory, encode Wick contractions, and require renormalization at coincident points. |
| 5 | [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) | The mathematical repair problem itself: extending distributions from the complement of a singular set while controlling scaling degree. |
| 6 | [Causal Factorization](/rigorous-qft/perturbative-algebraic-qft/causal-factorization/) | The structural axiom that assembles formal $S$-matrices and time-ordered products according to causal order. |
| 7 | [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) | The curved-spacetime strengthening of time-ordering: renormalization choices must be local, geometric, and natural under spacetime embeddings. |
| 8 | [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) | The finite local freedom left by the axioms, including diagonal counterterms and the Stückelberg–Petermann finite-renormalization viewpoint. |
| 9 | [Interacting Fields as Formal Series](/rigorous-qft/perturbative-algebraic-qft/interacting-fields-as-formal-series/) | The Bogoliubov formula, relative $S$-matrices, retarded products, and local interacting algebras. |
| 10 | [Comparison with Feynman Diagrams](/rigorous-qft/perturbative-algebraic-qft/comparison-with-feynman-diagrams/) | The dictionary between pAQFT constructions and textbook diagrams, including what diagrams do not define by themselves. |

After this path, you should be able to distinguish a formal interacting algebra from a convergent model and recognize why renormalization is local ambiguity rather than an infinite subtraction ritual.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $A[[\lambda]]$ | Formal power series with coefficients in an algebra $A$. | Interacting fields, relative $S$-matrices, perturbative observables. |
| $F\star_H G$ | Deformation product of functionals using a two-point distribution $H$. | Free pAQFT algebra and time-ordered products. |
| $T_n(F_1,\ldots,F_n)$ | Renormalized $n$-fold time-ordered product. | Formal $S$-matrices, Epstein–Glaser induction, local Wick powers. |
| $\mathcal S(V)=\exp_T(iV/\hbar)$ | Formal $S$-matrix built from renormalized time-ordered products. | Relative $S$-matrices and local interacting algebras. |
| Causal factorization | Time-ordered products and formal $S$-matrices factor when supports are causally ordered. | Epstein–Glaser induction and retarded products. |
| Scaling degree | A measure of singularity near a diagonal. | Distribution extension and finite renormalization freedom. |
| Local covariance | Renormalization choices must be local and geometric, not dependent on global coordinates or states. | Curved-spacetime pAQFT and local covariant time-ordered products. |
| $\widehat{\mathcal S}=\mathcal S\circ Z$ | Finite renormalization in the Stückelberg–Petermann sense. | Renormalization ambiguities, beta functions, comparison with Wilsonian RG. |
| $\mathcal S_V(F)=\mathcal S(V)^{-1}\star\mathcal S(V+F)$ | Relative $S$-matrix comparing $V+F$ to $V$. | Interacting fields and local interacting algebras. |
| $R_V(F)=\frac{\hbar}{i}\partial_s\mathcal S_V(sF)|_{s=0}$ | Bogoliubov formula for the interacting field associated with $F$. | Retarded products and local algebraic adiabatic limits. |
| Graph $\Gamma$ | Bookkeeping for contractions, vertices, and local extension choices. | Practical perturbative calculations and comparison with standard QFT. |

## Common confusions

**“Formal” means vague.** Formal means algebraically exact coefficient by coefficient in a specified formal parameter.

**pAQFT proves convergence of perturbation theory.** It usually does not. It constructs perturbative objects in the $\lambda$-adic or $\hbar$-adic sense.

**Feynman diagrams are the definition.** In pAQFT, diagrams are a bookkeeping expansion of time-ordered products, relative $S$-matrices, and functional derivatives.

**Renormalization means cancelling infinity.** In causal perturbation theory, renormalization is the local freedom in extending distributions to coincident configurations.

**Causal factorization is the same as commutativity.** It is not. It is a time-ordering and locality axiom for causally ordered supports; spacelike commutativity is a compatibility condition.

**Local covariance means isometry invariance.** Isometry covariance is only the fixed-spacetime shadow. The local covariant condition is naturality under embeddings between spacetimes.

**The interacting field is a global interaction-picture operator.** In pAQFT, interacting fields are local formal observables derived from relative $S$-matrices. A global interaction-picture interpretation requires additional assumptions.

**The adiabatic limit is automatic.** Removing spacetime cutoffs can fail or require local algebraic formulations; infrared behavior is separate from ultraviolet renormalization.

## Boundaries

This chapter treats perturbative interacting QFT as a rigorous formal construction. It does not replace the Constructive QFT chapter, which asks for genuine measures and nonperturbative limits. It also does not yet treat gauge theory in full; BV-BRST methods enter in the later BV-BRST and Gauge Theory chapter.

The framework is strongest when its status is stated honestly. It can construct local algebras and interacting fields as formal series, classify renormalization ambiguities, compare different renormalization prescriptions, and work on globally hyperbolic curved spacetimes. It does not by itself solve the Yang–Mills existence problem, prove convergence of QED perturbation theory, or produce a unique physical state for every interacting theory.

## Where to go next

For gauge theories, go next to the BV-BRST and Gauge Theory chapter, beginning with the BRST complex and BV formalism when those pages are available. For the microlocal foundations behind the product and extension theorems, return to [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). For the nonperturbative contrast, read [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) and [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/).

## References

- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” in *Mathematical Aspects of Quantum Field Theories* (2015), 17–55. [arXiv:1208.1428](https://arxiv.org/abs/1208.1428), [doi:10.1007/978-3-319-09949-1_2](https://doi.org/10.1007/978-3-319-09949-1_2).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).
- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [doi:10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- S. Hollands and R. M. Wald, “Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [doi:10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).

## Version history

- **2026-07-01:** First polished draft of the chapter overview, created with the first two pAQFT pages.
- **2026-07-01:** Updated chapter overview after adding Epstein–Glaser renormalization and time-ordered products.
- **2026-07-01:** Updated chapter overview after adding extension of distributions and causal factorization.
- **2026-07-01:** Updated chapter overview after adding local covariant time-ordered products and renormalization ambiguities.
- **2026-07-01:** Updated chapter overview after adding interacting fields as formal series and comparison with Feynman diagrams.
