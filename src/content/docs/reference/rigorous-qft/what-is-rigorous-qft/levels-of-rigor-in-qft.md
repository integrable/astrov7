---
title: "Levels of Rigor in QFT"
description: "Explains the main levels at which QFT statements can be formal, regulated, perturbative, axiomatic, constructive, or open."
sidebar:
  label: "Levels of Rigor"
  order: 1
level: Graduate
status: "Polished draft"
source: "Streater–Wightman; Osterwalder–Schrader; Haag–Kastler; Glimm–Jaffe; Rejzner; Costello; Clay Mathematics Institute."
topics:
  - rigorous QFT
  - axiomatic QFT
  - constructive QFT
  - perturbative QFT
  - continuum limits
canonicalTopics:
  - rigorous-quantum-field-theory
  - qft-foundations
  - constructive-quantum-field-theory
  - axiomatic-quantum-field-theory
researchStatus:
  established:
    - "Formal manipulations, perturbative constructions, axiomatic frameworks, and constructive existence theorems answer different mathematical questions."
    - "Finite regulators can make a theory well-defined without proving the existence of a continuum QFT."
  active:
    - "The nonperturbative construction of many physically central interacting four-dimensional continuum QFTs remains a major open direction."
---

## Summary

QFT is used at several levels of mathematical precision. A Feynman diagram computation, a lattice simulation, a Wightman reconstruction theorem, a Euclidean constructive measure, a perturbative algebraic construction, and an Atiyah–Segal topological field theory can all be rigorous in their own sense, but they are not the same kind of statement.

A useful test is

$$
\text{level of rigor}
=
\text{what object exists}
+
\text{in what topology or category}
+
\text{under what assumptions}.
$$

This page gives a map of the main levels: formal physics notation, finite regulated models, perturbative formal series, axiomatic frameworks, reconstruction theorems, constructive continuum models, and open mathematical problems. The point is not to shame useful heuristic reasoning. The point is to know exactly what has been made precise.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Levels of rigor in quantum field theory](/figures/rigorous-qft/levels-of-rigor.svg)

<figcaption>

A first-pass map of rigor levels in QFT. The arrows are not logical implications; they show common ways in which a physics idea can be made progressively more explicit. A finite regulator, a perturbative series, an axiomatic theorem, and a constructive continuum model answer different questions.

</figcaption>
</figure>

## Prerequisites

Read [Conventions and Logical Status](/rigorous-qft/conventions/) first. You should also know the basic roles of fields, correlation functions, path integrals, Feynman diagrams, and lattice cutoffs from graduate QFT.

## Core idea

Many disagreements about "rigor in QFT" come from using one word, "QFT," for several mathematical tasks. The task may be to compute a perturbative coefficient, prove that a set of axioms has consequences, reconstruct a Hilbert space from Euclidean data, construct an interacting measure, prove a scaling limit, or classify a categorical structure.

Those tasks are related, but they are not interchangeable. A theorem can be perfectly rigorous while conditional on axioms. A numerical lattice calculation can be extraordinarily useful while not proving the continuum limit. A formal perturbation series can be rigorously defined coefficient by coefficient while diverging as a series.

## Setup and conventions

We use the logical status labels fixed in [Conventions and Logical Status](/rigorous-qft/conventions/). Unless otherwise stated, Lorentzian physics notation uses mostly-minus metric and natural units,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\hbar=c=1.
$$

The word **model** means a specified mathematical object inside a specified framework. The word **regulator** means a modification such as a lattice spacing, momentum cutoff, finite volume, Pauli–Villars field, dimensional regularization parameter, or mollifier that makes otherwise singular expressions meaningful. The word **continuum limit** means a controlled limiting procedure in which the regulator is removed while suitable observables converge after renormalization.

## The main levels

The following table is a practical map. It is not a hierarchy of intellectual value; it is a map of what has been made mathematically explicit.

| Level | Typical object | What is rigorous at that level | What is not automatic |
|---|---|---|---|
| Formal physics notation | $\int \mathcal D\phi\,e^{iS}$, $\phi(x)$, Feynman rules | Compact encoding of physical expectations and calculational rules. | Existence of a measure, operators at points, convergence, or a Hilbert space. |
| Finite regulated model | Finite lattice, finite-dimensional integral, truncated Hilbert space | The regulated object is often an honest integral, matrix model, finite algebra, or finite-dimensional quantum system. | The regulator-independent continuum theory. |
| Perturbative formal series | $\sum_n a_n g^n$, time-ordered products, renormalized coefficients | Coefficients can be defined and renormalized with precise locality and covariance properties. | Convergence, nonperturbative uniqueness, and global phase structure. |
| Axiomatic framework | Wightman fields, OS Schwinger functions, Haag–Kastler nets | Consequences of stated axioms: reconstruction, CPT, spin–statistics, analyticity, locality structures. | Existence of a physically desired interacting model satisfying the axioms. |
| Constructive continuum QFT | Cutoff removal producing fields, measures, Schwinger functions, or nets | Actual nonperturbative mathematical construction of a continuum theory. | Broad availability in four-dimensional gauge theories. |
| Categorical or protected structure | VOA, conformal net, functorial TQFT, factorization algebra | Exact algebraic, topological, or local-to-global structure. | That the structure is a complete description of a full physical QFT with propagating degrees of freedom. |
| Open mathematical problem | Yang–Mills mass gap, rigorous chiral gauge theory, full CFT classification | Precise target statement and partial results. | A proof or complete construction. |

## Formal physics notation

Formal notation is the compressed language in which physicists discover structure. It is not useless, and it is not automatically false. It is also not automatically a definition.

For example,

$$
Z[J]=\int \mathcal D\phi\,
\exp\left(iS[\phi]+i\int J\phi\right)
$$

may serve as a mnemonic for Schwinger–Dyson equations, perturbative Feynman rules, Ward identities, or semiclassical expansions. To become a mathematical object, the page must say whether $Z[J]$ is a finite-dimensional integral, a Euclidean measure, an oscillatory integral, or a formal power series.

The same applies to point fields. The notation $\phi(x)$ is often useful, but in Wightman-style QFT the field is an operator-valued distribution. The robust object is the smeared field $\phi(f)$.

## Finite regulated models

A regulator can make a theory completely well-defined. On a finite lattice with finite local Hilbert spaces, the Hamiltonian is an operator on a finite-dimensional Hilbert space. In a finite-dimensional Euclidean integral, the measure is an ordinary measure. In a finite volume with ultraviolet cutoff, many expressions become honest finite-dimensional or well-controlled infinite-dimensional objects.

This level is indispensable. It is the starting point for lattice gauge theory, constructive QFT, numerical simulations, Hamiltonian truncation, and renormalization.

The subtlety is that the regulated model is not yet the desired continuum QFT. One must show that correlation functions, spectra, local algebras, or other observables have a limit as the cutoff is removed, usually after tuning bare parameters. The limiting object should be independent of irrelevant regulator details in the appropriate universality class.

## Perturbative rigor

Perturbative QFT can be rigorous without being convergent. The object is usually a formal power series,

$$
F(g)\sim \sum_{n\ge 0} a_n g^n,
$$

where the coefficients $a_n$ are distributions, operators, local functionals, or algebraic elements. Renormalization then becomes a precise problem of extending distributions, choosing finite local counterterms, and preserving locality, covariance, unitarity, and symmetries.

Epstein–Glaser renormalization and perturbative algebraic QFT are examples of this kind of rigor. They avoid treating divergent integrals as intermediate mysteries. Instead, they define time-ordered products recursively and identify renormalization freedom as local ambiguity.

The limitation is equally important: a formal series need not converge. It may be asymptotic, Borel summable in favorable cases, non-Borel summable, or incomplete because of instanton and other nonperturbative sectors. Perturbative rigor is a theorem about coefficients and algebraic structure, not automatically a theorem about an exact function of the coupling.

## Axiomatic and reconstruction rigor

Axiomatic frameworks ask: if a QFT satisfies certain structural principles, what follows?

In Wightman QFT, the basic objects are a Hilbert space, vacuum, unitary Poincaré representation, and fields as operator-valued distributions satisfying covariance, spectral condition, locality, and domain assumptions. Powerful theorems such as CPT and spin–statistics are consequences of these assumptions.

In Osterwalder–Schrader Euclidean QFT, the basic objects are Euclidean Schwinger functions satisfying conditions such as symmetry, Euclidean covariance, regularity, cluster properties, and reflection positivity. The reconstruction theorem explains when Euclidean data determine a Lorentzian Hilbert-space QFT.

In algebraic QFT, the basic object is a local net of observable algebras,

$$
\mathcal O\longmapsto \mathcal A(\mathcal O),
$$

with axioms such as isotony, locality, covariance, and suitable state conditions.

Axioms are not empty formalism: they make structural facts precise. But they do not by themselves construct the interacting four-dimensional theory one may want. That is a separate existence problem.

## Constructive rigor

Constructive QFT asks for an actual model, not merely formal rules or conditional consequences. A constructive result typically starts from a regulated theory, derives uniform estimates, renormalizes parameters, removes the cutoff, and proves that the limiting correlation functions satisfy suitable axioms.

The constructive program has rigorous successes, especially in low-dimensional scalar and fermionic models. It also gives the clearest mathematical interpretation of some Euclidean path integrals as measures on spaces of distributions.

The difficulty grows sharply with dimension, gauge symmetry, and nonperturbative phenomena. Four-dimensional non-Abelian Yang–Mills theory is the canonical example where the physics is compelling and the mathematical construction problem is still profound.

## Open problems are not failures of QFT

A central lesson of rigorous QFT is that physics can be extraordinarily predictive while some mathematical existence problems remain open. The Standard Model works as a calculational framework. Lattice gauge theory gives strong numerical evidence for nonperturbative phenomena. Perturbation theory and effective field theory produce precision predictions. None of that by itself proves the existence of a continuum four-dimensional Yang–Mills theory with a mass gap in the sense required by the Clay Millennium problem.

The right conclusion is not "QFT is meaningless." The right conclusion is that different standards answer different questions. Physics can guide mathematics, and mathematics can clarify which parts of the physics are theorems, constructions, conjectures, or expectations.

## Where modern bridge methods enter

Two modern tools will appear early in this volume.

First, **wavefront sets** refine the idea of singular support by recording singular directions in cotangent space. They explain when products of distributions are meaningful and why the singularity structure of two-point functions matters in curved spacetime and perturbative renormalization.

Second, **BRST and BV formalisms** turn gauge redundancy into cohomological structure. They make precise the distinction between fields used for computation and observables that survive gauge equivalence.

These bridge pages are not prerequisites for the first axiomatic pages, but they are essential for understanding modern rigorous perturbative QFT and gauge theory.

## Common pitfalls

**Thinking formal means worthless.** Formal physics notation is often the fastest way to find the right structure. The problem is not using it; the problem is forgetting which rigorous interpretation is being claimed.

**Thinking finite cutoff means finished.** A finite lattice model or cutoff Hamiltonian can be completely rigorous. The continuum limit is a separate mathematical statement.

**Thinking perturbative rigor proves nonperturbative existence.** A formal series can be defined with perfect mathematical care and still fail to converge or fail to determine a unique nonperturbative theory.

**Thinking axioms construct examples.** Axioms let one prove consequences and reconstruction theorems. Constructing a nontrivial model satisfying them is another task.

**Thinking all rigorous frameworks are equivalent.** Wightman fields, OS Schwinger functions, Haag–Kastler nets, VOAs, conformal nets, factorization algebras, and functorial TQFTs overlap in important cases, but none is simply a translation of all the others.

## Relations to other pages

- [Conventions and Logical Status](/rigorous-qft/conventions/) fixes the status labels used on this page.
- Later pages on operator-valued distributions explain why fields are smeared against test functions.
- Later Wightman and Osterwalder–Schrader pages explain the main reconstruction theorems.
- The first modern bridge page should be **Wavefront Sets**, because it explains the singularity language used in perturbative algebraic QFT and curved-spacetime QFT.

## Research status

The distinctions on this page are settled and standard in mathematical physics. The active research lies in comparing frameworks, constructing more models, extending perturbative constructions, understanding gauge theories nonperturbatively, and formulating physical dualities at theorem level.

The most famous open example is four-dimensional Yang–Mills existence and mass gap. The Clay problem asks for a mathematically rigorous construction of quantum Yang–Mills theory on $\mathbb R^4$ for any compact simple gauge group and a proof of a positive mass gap. Official Clay descriptions emphasize that no proof of the mass gap is known.

## Exercises

### Exercise 1: Identify the level

For each statement, identify the level of rigor.

1. "Expanding $e^{i\int g\phi^4}$ gives the usual Feynman diagrams."
2. "For each lattice spacing $a>0$ and finite box $\Lambda$, the scalar lattice measure is finite-dimensional."
3. "The OS axioms reconstruct a Hilbert space and Wightman functions."
4. "The perturbative interacting field exists as a formal power series in $g$."
5. "The continuum four-dimensional Yang–Mills theory exists and has a mass gap."

<details>
<summary><strong>Solution</strong></summary>

1. Formal physics notation, unless a renormalization scheme and formal-series framework are specified.
2. Finite regulated model.
3. Axiomatic reconstruction theorem.
4. Perturbative rigor.
5. Open mathematical problem in the nonperturbative continuum theory.

</details>

### Exercise 2: Why a regulator is not enough

Explain why defining a theory on a finite lattice does not by itself define a continuum QFT.

<details>
<summary><strong>Solution</strong></summary>

The finite lattice theory depends on the lattice spacing, volume, boundary conditions, and bare parameters. A continuum QFT requires a limiting procedure in which the lattice spacing is removed, the volume is controlled, and observables converge after tuning or renormalizing parameters. One must also identify the limiting fields, correlation functions, Hilbert space, local algebras, or other framework-specific objects. The finite theory is rigorous input; the continuum limit is the hard output.

</details>

### Exercise 3: Perturbative but not convergent

Give an example of a mathematically meaningful perturbative statement that does not assert convergence.

<details>
<summary><strong>Solution</strong></summary>

One example is: "The renormalized time-ordered products of a scalar theory can be defined recursively as formal power series satisfying causal factorization and locality." This statement concerns the coefficients and their algebraic properties. It does not say that the resulting series converges for any nonzero coupling.

</details>

### Exercise 4: Reflection positivity as a level jump

Why does reflection positivity change the status of Euclidean correlation functions?

<details>
<summary><strong>Solution</strong></summary>

Euclidean invariance alone gives symmetry under Euclidean motions. Reflection positivity gives a positive semidefinite inner product on functionals supported at positive Euclidean time after reflecting one factor. After quotienting null vectors and completing, this inner product is the starting point for the reconstructed Hilbert space. Thus reflection positivity is what lets Euclidean correlation functions become Lorentzian quantum states rather than merely Euclidean distributions.

</details>

## References

### Axiomatic and Euclidean frameworks

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. Haag and D. Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. DOI: [10.1063/1.1704187](https://doi.org/10.1063/1.1704187).

### Constructive and perturbative frameworks

- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- A. S. Wightman and G. Velo, eds., *Constructive Quantum Field Theory*, Springer. DOI: [10.1007/BFb0113079](https://doi.org/10.1007/BFb0113079).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, Springer. DOI: [10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- K. Costello, *Renormalization and Effective Field Theory*, American Mathematical Society. DOI: [10.1090/surv/170](https://doi.org/10.1090/surv/170).

### Modern bridges and open problems

- R. Brunetti and K. Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. arXiv: [math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), DOI: [10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- R. Brunetti, K. Fredenhagen, and R. Verch, "The Generally Covariant Locality Principle: A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041), DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7).
- Clay Mathematics Institute, "Yang–Mills and the Mass Gap." Official problem page: [claymath.org](https://www.claymath.org/millennium/yang-mills-the-maths-gap/). Problem description by A. Jaffe and E. Witten: [PDF](https://www.claymath.org/wp-content/uploads/2022/06/yangmills.pdf).

## Version history

- **2026-06-27:** Initial polished draft for the What Is a Rigorous QFT? chapter.
