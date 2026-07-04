---
title: "Linear Algebra, Tensors, and Index Notation"
description: "Chapter overview for linear algebra, tensors, bilinear forms, exterior algebra, determinants, and index notation in the Mathematical Toolkit volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard references on finite-dimensional linear algebra, tensors, exterior algebra, representation-ready index notation, differential geometry prerequisites, and QFT convention practice."
topics:
  - linear algebra
  - vector space
  - dual vector space
  - tensor product
  - bilinear form
  - metric
  - index notation
  - exterior algebra
  - determinant
  - trace
canonicalTopics:
  - linear-algebra
  - vector-space
  - dual-vector-space
  - tensor-product
  - bilinear-form
  - metric
  - index-notation
  - exterior-algebra
  - determinant
  - trace
researchStatus:
  established:
    - "The finite-dimensional linear-algebra material in this chapter is standard and forms the type system for tensors, spinors, fields, currents, metrics, and symmetry representations throughout QFT."
  active:
    - "The later uses of this language in infinite-dimensional spaces, operator algebras, derived geometry, tensor categories, and rigorous QFT require additional hypotheses and are handled in later chapters."
---

Linear Algebra, Tensors, and Index Notation is the chapter in the Mathematical Toolkit volume where the symbolic language of QFT gets its type system. Fields carry spacetime indices, spinor indices, flavor indices, gauge indices, form degrees, and sometimes all of them at once. Linear algebra tells us which operations are meaningful before physics gives those operations dynamics.

The chapter is deliberately not a generic linear-algebra course. It focuses on the pieces that prevent QFT formulas from becoming shape-shifting glyph soup: vector spaces and duals, tensor products, bilinear forms, metrics, traces, determinants, exterior powers, symmetry types, and index notation. Once those are clear, many later “mysterious” rules become simple type checks.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing vector spaces, duals, tensor products, bilinear forms, index notation, exterior algebra, determinants, and QFT applications.](/figures/math-toolkit/linear-algebra-tensor-roadmap.svg)

<figcaption>

The chapter builds the algebraic grammar behind QFT notation. Vectors and duals define pairings; tensor products define multi-index objects; bilinear forms allow raising and lowering; symmetry operations produce exterior powers and traces; index notation is the compact language that keeps these maps visible in calculations.

</figcaption>
</figure>

The main lesson is simple: an index is not just a decoration. It tells you what kind of object you have, which space it lives in, which pairing is being used, and which transformations are allowed.

## Prerequisites

You should know matrix multiplication, determinants, eigenvalues, bases, and basic complex vector spaces. You should also know the site’s [Mathematical Conventions](/math-toolkit/conventions/), especially the distinction between convention-dependent formulas and invariant statements.

Nothing in this chapter requires functional analysis. Infinite-dimensional Hilbert spaces, unbounded operators, spectral measures, rigged Hilbert spaces, and trace-class subtleties belong to [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/). This chapter keeps the finite-dimensional algebra sharp before the infinite-dimensional version begins doing infinite-dimensional things.

## Reading path

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Vector Spaces and Duals | The difference between vectors, covectors, bases, dual bases, linear maps, and pairings. |
| 2 | Tensor Products | The universal operation behind multi-index objects, product Hilbert spaces, multiplets, and local tensor fields. |
| 3 | Bilinear Forms and Metrics | Inner products, Lorentzian metrics, invariant pairings, signatures, and when raising/lowering indices is legal. |
| 4 | Index Notation | Einstein summation, free and dummy indices, covariance/contravariance, tensor densities, and common QFT index conventions. |
| 5 | Symmetrization and Antisymmetrization | Projection onto symmetry types, identical particles, angular momentum, and Young-tableau prerequisites. |
| 6 | Exterior Algebra | Forms, wedge products, orientations, determinants, Hodge-dual prerequisites, and the algebra behind gauge-field strengths. |
| 7 | Determinants, Traces, and Jacobians | Volume scaling, change of variables, functional determinants, anomalies, and path-integral measures. |
| 8 | Eigenvalues and Normal Forms | Diagonalization, Jordan forms, spectral decompositions, quadratic actions, mass matrices, and stability analysis. |

A learner beginning graduate QFT should read the first four pages before using serious tensor notation. A reader headed toward gauge theory should add Exterior Algebra and Determinants, Traces, and Jacobians. A reader headed toward representation theory should read Symmetrization and Antisymmetrization before Young tableaux.

## Landmarks

**Vector spaces are not their coordinate columns.** A vector space is an abstract object. A column vector is its coordinate representation after a basis is chosen. QFT formulas often look coordinate-based, but covariance is the statement that the object does not depend on that choice.

**The dual space is not optional.** Covectors act on vectors. Gradients, momenta, one-forms, sources, linear functionals, and bras are dual objects. Confusing a vector with a covector is harmless only after a metric or inner product has silently identified them. Silent identifications are where signs breed.

**Tensor products are not component arrays.** A tensor is a multilinear object or an element of a tensor product. Its components depend on bases. Tensor products organize composite systems, tensor fields, multiplets, two-point structures, operator products, and multilinear couplings.

**A metric is extra structure.** Raising and lowering indices requires a nondegenerate bilinear form. In Lorentzian signature that form is not positive definite. In gauge theory, flavor theory, and spinor algebra, different spaces carry different pairings, so the same index position convention need not mean the same thing everywhere.

**Index notation is a compressed typing discipline.** A valid equation must match free indices on both sides. Repeated dummy indices indicate a contraction with a specified pairing. The notation is powerful because it hides sums; it is dangerous for the same reason.

**Exterior algebra is the algebra of antisymmetry.** Differential forms, field strengths, volume forms, orientation, wedge products, and characteristic classes all start with the finite-dimensional exterior algebra. The geometric chapter later turns this algebra into calculus on manifolds.

**Determinants measure volume, Jacobians, and zero modes.** Determinants are not merely computational tricks. They encode change of variables, Gaussian integrals, path-integral normalization, one-loop fluctuations, and the failure of a linear map to be invertible.

**Normal forms organize dynamics.** Diagonalizing a quadratic form gives propagating modes when possible. Jordan blocks, indefinite signatures, zero modes, and nonnormal operators warn that the naive “sum of decoupled oscillators” picture has left the building.

## Common confusions

**A lower index does not automatically mean “component of a covector.”** In Euclidean vector calculus this shortcut is often harmless. In relativity, gauge theory, and spinor calculus it is not. The index’s meaning depends on which vector space and which pairing are being used.

**A metric is not the same thing as a dot product in every context.** A positive-definite inner product, a Lorentzian spacetime metric, a symplectic form, a Killing form, and an invariant Hermitian form are different structures. They all pair things, but they do not have the same symmetry, signature, or physical meaning.

**Einstein summation is not magic cancellation.** You may contract a vector with a covector, or two indices using a specified metric or invariant tensor. You may not delete matching symbols just because they look repeated. The notation is a compact language, not a coupon code.

**The Kronecker delta and the metric do different jobs.** $\delta^i{}_j$ is the identity map from a vector space to itself in components. A metric $g_{ij}$ identifies vectors with covectors. In orthonormal Euclidean coordinates they look suspiciously similar; in most serious QFT contexts they should be kept separate.

**Complex vector spaces have conjugation subtleties.** A complex-linear dual, Hermitian inner product, bra-ket dual, and complex conjugate representation are related but distinct. This matters for unitary representations, spinors, Hilbert spaces, and path integrals.

**A determinant is basis-dependent until used correctly.** The determinant of a linear operator on a finite-dimensional vector space is invariant, but the determinant of a matrix representing a bilinear form or a change of coordinates transforms with Jacobian factors. This is exactly why densities and volume forms exist.

**Antisymmetrization conventions differ by factorials.** Some authors define brackets with a factor $1/p!$; some do not. This site uses normalized symmetrization and antisymmetrization unless a page says otherwise. The wedge product conventions page will make the factors explicit.

## Boundaries

This chapter develops finite-dimensional algebraic language. It does not construct quantum Hilbert spaces, Fock spaces, C*-algebras, von Neumann algebras, or domains of unbounded operators. Those belong to functional analysis and rigorous QFT.

It does not teach full representation theory. It supplies the tensor, symmetry, trace, and index notation needed before reading [Lie Groups, Lie Algebras, and Representations](/math-toolkit/groups-representations/) and [Clifford Algebras and Spinors](/math-toolkit/clifford-spinors/).

It does not teach differential geometry. It supplies the tangent-space algebra that later becomes differential forms, metrics, bundles, connections, curvature, and spin structures in [Geometry of Fields](/math-toolkit/geometry-of-fields/).

It does not replace physics pages on particles, fields, Lagrangians, quantization, or scattering. Instead, it explains the algebraic operations those pages use when they write objects such as $F_{\mu\nu}$, $\bar\psi\gamma^\mu D_\mu\psi$, $\operatorname{tr}(F\wedge F)$, $\epsilon_{\mu\nu\rho\sigma}$, or $\delta^a{}_b$.

## Where to go next

After this chapter, the natural next stop depends on the reader’s problem. For variational formulas and Hamiltonian structure, go to [Calculus of Variations and Phase Space](/math-toolkit/calculus-of-variations-and-phase-space/). For distributions and Fourier transforms, go to [Analysis, Distributions, and Fourier Methods](/math-toolkit/analysis-distributions-fourier/). For gauge and flavor symmetries, go to [Lie Groups, Lie Algebras, and Representations](/math-toolkit/groups-representations/). For spinors and gamma matrices, go to [Clifford Algebras and Spinors](/math-toolkit/clifford-spinors/). For forms, bundles, and curvature, go to [Geometry of Fields](/math-toolkit/geometry-of-fields/).

The next page in this chapter should be Vector Spaces and Duals. It will make explicit the distinction between an abstract vector, its components, a covector, a dual basis, and a pairing.

## References

For linear algebra with a mathematics-first orientation, standard references include Axler, *Linear Algebra Done Right*; Hoffman and Kunze, *Linear Algebra*; and Roman, *Advanced Linear Algebra*.

For tensor and exterior-algebra language aimed at geometry and physics, useful references include Frankel, *The Geometry of Physics*; Nakahara, *Geometry, Topology and Physics*; and the geometry preliminaries in many gauge-theory and relativity texts.

For QFT-facing conventions and examples, useful anchors include Weinberg, *The Quantum Theory of Fields*; Srednicki, *Quantum Field Theory*; Schwartz, *Quantum Field Theory and the Standard Model*; and Zee, *Quantum Field Theory in a Nutshell*. The purpose here is not to copy their conventions, but to make translation among them painless.

## Version history

- **2026-06-26:** Initial polished draft. Added the chapter orientation, reading path, landmarks, common confusions, boundaries, and handoff to the first ordinary page.
