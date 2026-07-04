---
title: "Conventions and Logical Status"
description: "Fixes the logical status labels, distributional notation, and framework conventions used throughout the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Conventions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Streater–Wightman; Osterwalder–Schrader; Haag–Kastler; Glimm–Jaffe; Rejzner; Costello."
topics:
  - rigorous QFT conventions
  - logical status labels
  - operator-valued distributions
  - reconstruction theorems
canonicalTopics:
  - rigorous-quantum-field-theory
  - axiomatic-quantum-field-theory
  - constructive-quantum-field-theory
researchStatus:
  established:
    - "Rigorous QFT uses several precise but inequivalent frameworks, so claims must state their framework and hypotheses."
    - "Quantum fields in the Wightman sense are operator-valued distributions, not ordinary pointwise operators."
  active:
    - "Many physically central interacting continuum theories remain difficult or open as nonperturbative mathematical constructions."
---

## Summary

This page fixes the conventions used when the Mathematical and Rigorous QFT volume says that a statement is a definition, theorem, construction, conjecture, open problem, or physics expectation. Its purpose is simple: a rigorous QFT page should make clear **what mathematical object is being discussed**, **which framework is being used**, and **what has actually been proved or constructed**.

The guiding convention is

$$
\text{claim in rigorous QFT}
=
\text{framework}+\text{object}+\text{hypotheses}+\text{status}.
$$

A formula such as $\int \mathcal D\phi\,e^{iS[\phi]}$ may be a useful physics notation, a finite-dimensional integral after discretization, a Gaussian or interacting Euclidean measure, an oscillatory distribution, or a formal perturbative expansion. These are different mathematical claims. This page fixes the vocabulary used to keep them separate.

Unless a page says otherwise, spacetime and Fourier conventions are inherited from the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus Lorentzian metric, natural units, and plane waves $e^{-ip\cdot x}$,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\hbar=c=1.
$$

## Prerequisites

You should be comfortable with ordinary graduate QFT notation, basic functional analysis vocabulary, and the idea that distributions must be tested against functions. The detailed mathematical tools are developed in later pages; this page only fixes the language used to state them.

## Core idea

The same physics sentence can mean different things in different rigorous frameworks. For example, "the scalar field exists" may mean that there is an operator-valued tempered distribution satisfying the Wightman axioms, a Euclidean random distribution satisfying Osterwalder–Schrader positivity, a local net of algebras with suitable covariance and locality, or a perturbative formal power series satisfying causal factorization.

The point is not to rank all frameworks on one ladder. The point is to prevent category mistakes. A perturbative construction may be fully rigorous order by order while saying nothing about convergence. A finite lattice model may be perfectly well-defined while not yet proving a continuum limit. A theorem in algebraic QFT may prove a structural consequence of axioms while not constructing a new interacting model.

## Setup and conventions

Pages in this volume should state their **framework** before making a theorem-level claim. The most common framework labels are:

| Framework | Basic object | Typical output | Main caution |
|---|---|---|---|
| Wightman QFT | Hilbert space, vacuum, fields as operator-valued distributions | Reconstruction, spin–statistics, CPT, analyticity | Existence of interacting models is separate from the axioms. |
| Osterwalder–Schrader QFT | Euclidean Schwinger functions or measures | Lorentzian reconstruction from Euclidean data | Euclidean invariance alone is not enough; reflection positivity is essential. |
| Algebraic QFT | Net $\mathcal O\mapsto\mathcal A(\mathcal O)$ of local observable algebras | Locality, covariance, superselection, modular theory | Field coordinatizations are not primary objects. |
| Constructive QFT | Cutoff theory plus controlled removal of cutoffs | Actual nonperturbative models and correlation functions | Technically hard; many central four-dimensional cases remain open. |
| Perturbative algebraic QFT | Local algebras and interacting fields as formal series | Renormalized perturbation theory with causal locality | Usually formal in coupling constants. |
| BV-BRST | Cohomological description of gauge redundancy | Gauge-invariant observables and anomalies as cohomology | Gauge-fixed fields are not automatically observables. |
| CFT, VOA, conformal net | Chiral algebras, local nets, or conformal data | Rigorous chiral and conformal structures | Different definitions capture different parts of physical CFT. |
| Functorial TQFT | Symmetric monoidal functor from bordisms | Topological invariants and extended structures | Usually topological, not a full local QFT with propagating degrees of freedom. |

A page may use more than one framework, but it should say when it changes language.

## Logical status labels

Use these labels consistently.

| Label | Meaning | What the page must include |
|---|---|---|
| Definition | A convention or structure being introduced. | The objects, ambient category or space, and equivalence relation if any. |
| Theorem | A proved result under stated hypotheses. | Assumptions, conclusion, scope, and proof idea or reference. |
| Construction | A mathematical object is built. | Input data, output object, topology or convergence mode, and limitations. |
| Proof sketch | A guide to why a theorem is true. | The main steps and where hard estimates or external results enter. |
| Standard result | A settled fact used often, but not proved on the page. | A precise statement and a reliable reference. |
| Conjecture | A precise expected mathematical statement. | Evidence, known cases, and what remains unproved. |
| Open problem | A problem not known to be solved. | Precise formulation, partial results, and common misconceptions. |
| Physics expectation | A physically well-motivated claim not established at theorem level here. | What the expectation predicts and why it is not being treated as a theorem. |

For theorem-oriented pages, use a small status card near the statement when it helps:

| Field | What to write |
|---|---|
| Type | Definition, theorem, construction, example, conjecture, or open problem. |
| Framework | Wightman, Osterwalder–Schrader, algebraic, constructive, perturbative algebraic, BV-BRST, VOA, TQFT, etc. |
| Assumptions | Positivity, locality, covariance, spectral condition, regularity, cutoff bounds, finite energy, compactness, or other hypotheses. |
| Output | Hilbert space, fields, net, measure, Schwinger functions, formal series, category, invariant, or bound. |
| Limitations | What the statement does not prove. |

## Distributions and smearing

The default test-function spaces are

$$
C_c^\infty(M)
\quad\text{for compactly supported smooth functions,}
\qquad
\mathcal S(\mathbb R^d)
\quad\text{for Schwartz functions.}
$$

The corresponding distribution spaces are written

$$
\mathcal D'(M)=(C_c^\infty(M))',
\qquad
\mathcal S'(\mathbb R^d)=\mathcal S(\mathbb R^d)'.
$$

For a distribution $T$ and a test function $f$, the pairing is written $\langle T,f\rangle$. When an integral is displayed,

$$
\langle T,f\rangle = \int T(x) f(x)\,dx,
$$

the right-hand side is notation unless $T$ is represented by an honest function or measure.

In Wightman-style language, a quantum field is not an operator $\phi(x)$ at a point. It is an operator-valued distribution. Its meaningful objects are smeared fields

$$
\phi(f)
\equiv
\int_M d\mu(x)\,\phi(x)f(x),
\qquad
f\in C_c^\infty(M)\ \text{or}\ \mathcal S(\mathbb R^d),
$$

where the integral sign is again a compact notation for the distributional pairing. If domains matter, a page should specify a common dense invariant domain $\mathcal D\subset\mathcal H$ on which the smeared unbounded operators are defined.

The support of a test function is written $\operatorname{supp} f$. A typical locality statement for smeared fields is

$$
[\phi(f),\psi(g)]_\pm=0
\quad\text{if}\quad
\operatorname{supp} f\ \text{and}\ \operatorname{supp} g
\ \text{are spacelike separated}.
$$

The symbol $[A,B]_\pm$ denotes the commutator for bosonic fields and the anticommutator for fermionic fields.

## Correlator notation

For Lorentzian Wightman functions, use

$$
W_n(f_1,\dots,f_n)
=
\langle \Omega,
\phi_1(f_1)\cdots \phi_n(f_n)\Omega\rangle,
$$

where $\Omega$ is the vacuum vector. When unsmeared notation is useful, write

$$
W_n(x_1,\dots,x_n)
=
\langle\Omega,
\phi_1(x_1)\cdots\phi_n(x_n)\Omega\rangle,
$$

but remember that this is usually a distributional kernel.

For Euclidean Schwinger functions, use $S_n$:

$$
S_n(f_1,\dots,f_n)
=
\langle \Phi(f_1)\cdots\Phi(f_n)\rangle_E.
$$

The subscript $E$ indicates Euclidean correlation functions. It does not by itself assert that a measure exists, that reflection positivity holds, or that a Lorentzian theory has been reconstructed.

For algebraic QFT, local observable algebras are written

$$
\mathcal O\longmapsto \mathcal A(\mathcal O),
$$

where $\mathcal O$ is a spacetime region. Isotony is the condition

$$
\mathcal O_1\subset \mathcal O_2
\quad\Longrightarrow\quad
\mathcal A(\mathcal O_1)\subset \mathcal A(\mathcal O_2).
$$

For locally covariant QFT, a typical schematic notation is

$$
\mathfrak A:\mathbf{Loc}\longrightarrow\mathbf{Alg},
$$

where $\mathbf{Loc}$ is a category of suitable spacetimes and embeddings, and $\mathbf{Alg}$ is a category of algebras. Pages using this notation should say what class of spacetimes and morphisms is intended.

For functorial TQFT, write

$$
Z:\mathbf{Bord}_d\longrightarrow\mathbf{Vect}
$$

or the appropriate target category. The notation means a symmetric monoidal functor only after the source, target, and monoidal structures have been specified.

## Path integrals and formal series

A path-integral expression is not automatically a mathematical definition. When using

$$
Z[J]=\int \mathcal D\phi\,
\exp\left(iS[\phi]+i\int J\phi\right),
$$

say which interpretation is meant:

| Interpretation | Meaning |
|---|---|
| Finite-dimensional integral | A discretized or truncated system with finitely many degrees of freedom. |
| Euclidean measure | A probability or complex measure on a space of distributions. |
| Oscillatory integral | A Lorentzian object defined by stationary phase, distribution theory, or another analytic construction. |
| Formal perturbative expansion | A rule that defines coefficients of a power series. |
| Physics notation | A compact heuristic expression whose rigorous meaning is not being claimed on that page. |

A formal power series is written

$$
F(g)\sim \sum_{n\ge 0} a_n g^n.
$$

The symbol $\sim$ means asymptotic or formal expansion, not equality to a convergent function unless the page explicitly proves convergence or summability.

## Common pitfalls

**Mistaking notation for definition.** Writing $\phi(x)$, $\mathcal D\phi$, or $\prod_x d\phi(x)$ does not define an object. A rigorous page must say whether the object is a distribution, measure, formal series, algebra, or functor.

**Forgetting domains of unbounded operators.** Smeared fields are typically unbounded. Algebraic QFT often avoids this by focusing on bounded observable algebras, but Wightman-style pages must be careful about dense domains.

**Treating Euclidean invariance as enough.** Euclidean covariance is not the Osterwalder–Schrader theorem. Reflection positivity, regularity, symmetry, and growth conditions are what allow reconstruction of a Lorentzian Hilbert space theory.

**Using perturbative rigor as nonperturbative existence.** Epstein–Glaser, BV, and perturbative algebraic constructions can be mathematically precise order by order. That does not imply that the perturbation series converges or that a nonperturbative continuum model exists.

**Calling gauge-fixed fields observables.** Gauge fixing can be a powerful computational device, but physical observables are gauge-invariant or BRST/BV cohomological objects. Pages on gauge theory should identify which level is being used.

## Relations to other pages

- [Levels of Rigor in QFT](/rigorous-qft/what-is-rigorous-qft/levels-of-rigor-in-qft/) explains how to classify claims as formal, perturbative, axiomatic, constructive, or open.
- [Conventions and Normalizations](/foundations/conventions-and-normalizations/) fixes the metric, Fourier, state-normalization, propagator, spinor, and Wick-rotation conventions used by physics-facing pages.
- Later Wightman, Osterwalder–Schrader, algebraic, constructive, BV-BRST, and microlocal pages should use the labels and notation fixed here rather than redefining them.

## Research status

The terminology on this page is established. The open part is not the vocabulary, but the existence and comparison of many mathematically precise QFTs. Some frameworks have powerful reconstruction and structure theorems; some have strong perturbative constructions; some have nonperturbative lower-dimensional examples. A unified theorem-level construction of all physically important four-dimensional continuum QFTs is not known.

## Exercises

### Exercise 1: Classify the claim

Classify each claim as a definition, theorem, construction, conjecture, open problem, or physics expectation.

1. "Assume the Wightman axioms. Then the CPT theorem holds."
2. "The four-dimensional Yang–Mills theory with compact simple gauge group exists and has a mass gap."
3. "Define a local net by assigning to each double cone $\mathcal O$ a von Neumann algebra $\mathcal A(\mathcal O)$."
4. "The perturbative interacting scalar field is a formal power series satisfying causal factorization."

<details>
<summary><strong>Solution</strong></summary>

1. This is a theorem-level claim, provided the precise version of the Wightman axioms and the field content are stated.
2. This is an open problem in four-dimensional constructive QFT and mathematical Yang–Mills theory.
3. This is the beginning of a definition. It becomes a definition of an algebraic QFT only after adding axioms such as isotony, locality, covariance, and suitable state or representation conditions.
4. This is a construction in perturbative algebraic QFT. It is rigorous order by order but does not assert convergence of the formal series.

</details>

### Exercise 2: Why smearing is not optional

Suppose a scalar two-point function has a short-distance singularity at $x=y$. Explain why $\phi(x)\phi(y)$ at coincident points is not automatically a well-defined operator product, while $\phi(f)\phi(g)$ can be meaningful for suitable test functions $f$ and $g$.

<details>
<summary><strong>Solution</strong></summary>

A distribution is defined by its action on test functions, not by pointwise values. The singularity at $x=y$ means that the kernel may fail to have a well-defined restriction or product on the diagonal. Smearing against $f$ and $g$ integrates the distributional kernel against smooth test functions, which can produce a well-defined quadratic form or operator expression. Composite fields such as $\phi^2(x)$ require an additional renormalized definition, not merely setting $y=x$.

</details>

### Exercise 3: Formal series versus convergent function

Let

$$
F(g)\sim \sum_{n\ge 0} a_n g^n.
$$

What extra information is needed before this notation can be read as defining an actual function of $g$?

<details>
<summary><strong>Solution</strong></summary>

One needs a topology or analytic category in which the series is interpreted. For ordinary convergence, one needs a nonzero radius of convergence and a proof that the sum equals $F(g)$ there. For asymptotic analysis, one needs estimates on the remainder after truncation. For Borel summation, one needs growth bounds, analytic continuation of the Borel transform, and a prescription for the Laplace transform. Without such information, the expression is a formal or asymptotic expansion, not an equality of functions.

</details>

## References

### Standard references

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. Haag and D. Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. DOI: [10.1063/1.1704187](https://doi.org/10.1063/1.1704187).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, Springer. DOI: [10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- K. Costello, *Renormalization and Effective Field Theory*, American Mathematical Society. DOI: [10.1090/surv/170](https://doi.org/10.1090/surv/170).

### Useful bridges

- R. Brunetti and K. Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. arXiv: [math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), DOI: [10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- R. Brunetti, K. Fredenhagen, and R. Verch, "The Generally Covariant Locality Principle: A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041), DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7).
- K. Fredenhagen and K. Rejzner, "Batalin–Vilkovisky Formalism in the Functional Approach to Classical Field Theory," *Communications in Mathematical Physics* **314** (2012), 93–127. arXiv: [1101.5112](https://arxiv.org/abs/1101.5112), DOI: [10.1007/s00220-012-1487-y](https://doi.org/10.1007/s00220-012-1487-y).

## Version history

- **2026-06-27:** Initial polished draft for the Mathematical and Rigorous QFT volume.
