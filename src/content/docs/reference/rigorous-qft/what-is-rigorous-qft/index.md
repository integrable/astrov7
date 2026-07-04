---
title: "What Is a Rigorous QFT?"
description: "Chapter overview for the logical status, frameworks, and reading habits needed to study rigorous QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Streater–Wightman; Osterwalder–Schrader; Haag–Kastler; Glimm–Jaffe; Rejzner; Costello."
topics:
  - rigorous QFT
  - mathematical physics
  - axiomatic QFT
  - constructive QFT
  - perturbative QFT
canonicalTopics:
  - rigorous-quantum-field-theory
  - mathematical-physics
  - qft-foundations
researchStatus:
  established:
    - "Rigorous QFT is best read as a collection of frameworks with explicit objects, hypotheses, and theorem-level status labels."
  active:
    - "The comparison and construction of physically central continuum QFTs remains an active research area, especially in four-dimensional gauge theory and dualities."
---

What Is a Rigorous QFT? is the chapter in the Mathematical and Rigorous QFT volume that teaches the reader how to read QFT statements with theorem-level discipline. It is the orientation chapter: before defining Wightman fields, Euclidean Schwinger functions, local nets, constructive measures, or BV complexes, it explains what kind of claim is being made.

The chapter is not a philosophy detour. It is practical training for avoiding category mistakes. A path integral, a Feynman graph, a lattice regulator, a formal power series, a Hilbert-space field, and a local algebra may describe related physics, but they are not the same mathematical object.

Read this chapter when you want to know what it means to say that a QFT is formal, regulated, perturbative, axiomatic, constructive, categorical, or still open.

$$
\text{rigorous QFT claim}
=
\text{object}+\text{hypotheses}+\text{framework}+\text{status}.
$$

## Prerequisites

You should know the basic language of graduate QFT: fields, correlation functions, Lagrangians, path integrals, Feynman diagrams, gauge symmetry, and renormalization. Read [Conventions and Logical Status](/rigorous-qft/conventions/) before using this chapter as a reference.

No specialized background in operator algebras, constructive field theory, or microlocal analysis is assumed here. Those tools appear later in the volume.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Levels of Rigor in QFT](/rigorous-qft/what-is-rigorous-qft/levels-of-rigor-in-qft/) | The map of formal, regulated, perturbative, axiomatic, constructive, categorical, and open levels. |
| 2 | [Physics QFT versus Mathematical QFT](/rigorous-qft/what-is-rigorous-qft/physics-qft-versus-mathematical-qft/) | The translation habit: how a useful physics sentence becomes a mathematical claim with objects, hypotheses, and scope. |

After this path, you should be able to identify whether a QFT statement is a heuristic formula, a definition, a theorem, a construction, a perturbative formal-series claim, or an open problem.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Object plus hypotheses plus status | A rigorous claim must say what exists, under what assumptions, and in what sense. | All later chapters. |
| Formal does not mean worthless | Formal notation can encode correct physics without already defining a mathematical object. | Path integrals, Feynman rules, BV–BRST. |
| Regulated does not mean continuum | A finite cutoff model can be rigorous while the continuum limit remains unproved. | Constructive QFT, lattice-to-continuum constructions. |
| Perturbative does not mean convergent | Formal power series may be rigorous coefficient by coefficient without defining a function of the coupling. | Perturbative algebraic QFT, renormalization. |
| Axioms do not construct examples | Wightman, OS, and algebraic axioms imply powerful theorems, but existence of desired interacting models is separate. | Wightman QFT, Osterwalder–Schrader QFT, algebraic QFT. |
| Mathematical QFT is plural | Different frameworks capture different structures: fields, algebras, measures, functors, categories, or formal series. | CFT, TQFT, factorization algebras, locally covariant QFT. |

## Common confusions

**Rigorous does not mean nonphysical.** Many rigorous frameworks were created to preserve physical principles such as locality, covariance, positivity, and causality with fewer hidden assumptions.

**Physics notation is not automatically a mathematical definition.** The notation $\int\mathcal D\phi\,e^{iS}$ may be a finite-dimensional integral, a Euclidean measure, a formal perturbative rule, an oscillatory object, or a heuristic mnemonic. The page must say which one.

**Open mathematical construction does not mean physical failure.** Four-dimensional gauge theory is extraordinarily useful in physics; a full nonperturbative theorem-level construction with mass gap is a sharper mathematical demand.

**Different frameworks are not merely notational variants.** A Wightman field, an OS Schwinger function, a Haag–Kastler net, a constructive measure, a factorization algebra, a VOA, and a functorial TQFT are different kinds of objects.

## Boundaries

This chapter does not teach the full mathematics of distributions, operator algebras, Euclidean measures, PDE, category theory, or homotopical methods. It teaches the reader how those tools will be used as QFT frameworks later.

This chapter also does not replace a standard physics introduction to QFT. It assumes that the reader has already seen the physical objects whose rigorous status will be clarified.

The chapter stops at orientation. Detailed definitions and theorems begin in the later chapters on operator-valued distributions, Wightman QFT, Osterwalder–Schrader reconstruction, algebraic QFT, constructive QFT, perturbative algebraic QFT, BV–BRST, and microlocal analysis.

## Where to go next

For a modern bridge from formal propagator manipulations to rigorous distribution theory, read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). It explains why the singularities of QFT correlators must be tracked in cotangent directions, not merely at spacetime points.

After that, the natural next chapter is Operator-Valued Distributions: fields in rigorous Lorentzian QFT are not ordinary functions $x\mapsto\phi(x)$ but distributions smeared against test functions.

## References

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. Haag and D. Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. DOI: [10.1063/1.1704187](https://doi.org/10.1063/1.1704187).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, Springer. DOI: [10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- K. Costello, *Renormalization and Effective Field Theory*, American Mathematical Society. DOI: [10.1090/surv/170](https://doi.org/10.1090/surv/170).

## Version history

- **2026-06-27:** Initial polished overview after the chapter reached two ordinary pages.
