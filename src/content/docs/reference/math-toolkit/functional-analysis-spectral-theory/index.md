---
title: "Functional Analysis and Spectral Theory"
description: "Chapter overview for Hilbert spaces, operators, domains, self-adjointness, spectral theory, compactness, trace ideals, spectral density, and rigged Hilbert spaces in the Mathematical Toolkit volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard mathematical physics references, including Reed–Simon, Teschl, Hall, Moretti, Yosida, Rudin, Gelfand–Vilenkin, and QFT treatments of Hilbert spaces, unbounded operators, propagators, spectral densities, and functional determinants."
topics:
  - functional analysis
  - spectral theory
  - Hilbert spaces
  - linear operators
  - unbounded operators
  - self-adjointness
  - spectral theorem
  - compact operators
  - trace ideals
  - spectral density
  - rigged Hilbert spaces
canonicalTopics:
  - functional-analysis
  - spectral-theory
  - hilbert-space
  - linear-operator
  - unbounded-operator
  - self-adjointness
  - spectral-theorem
  - compact-operator
  - trace-class-operator
  - spectral-density
  - rigged-hilbert-space
researchStatus:
  established:
    - "Hilbert-space methods, operator domains, self-adjointness, and the spectral theorem provide the standard analytic foundation for quantum mechanics, free QFT, Green functions, and determinants."
  active:
    - "Interacting QFT, gauge constraints, indefinite metrics, factorization of Hilbert spaces, type-III von Neumann algebras, and continuum entanglement require refinements beyond the elementary Hilbert-space picture."
---

Functional Analysis and Spectral Theory is the chapter in the Mathematical Toolkit volume where the analytic words in QFT formulas become precise. Hilbert spaces, adjoints, spectra, domains, resolvents, projectors, traces, determinants, Green functions, and spectral densities are not decorative vocabulary; they are the grammar behind quantization and correlation functions.

The chapter exists because many QFT mistakes are really operator mistakes. A Hamiltonian is not automatically self-adjoint just because it is symmetric on a nice set of functions. A delta-normalized state is not an honest vector in the Hilbert space. A determinant of a differential operator is not a finite product. A spectrum can have continuous, discrete, and residual pieces, and only some of them look like elementary eigenvalues.

The central slogan is

$$
\text{operator equation} \quad + \quad \text{domain and spectrum} \quad = \quad \text{well-defined physics}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Roadmap showing Hilbert spaces leading to operators, domains and adjoints, self-adjointness, spectral theorem, functional calculus, and QFT uses such as Green functions, determinants, spectral densities, and generalized eigenstates.](/figures/math-toolkit/spectral-theory-roadmap.svg)

<figcaption>

The chapter moves from Hilbert spaces and operators to spectral calculus. QFT uses the output in propagators, heat kernels, determinants, Källén–Lehmann representations, scattering theory, generalized eigenstates, and operator-valued distributions.

</figcaption>
</figure>

Read this chapter when a QFT page says “invert the operator,” “sum over modes,” “take the determinant,” “insert a complete set of states,” “diagonalize the Hamiltonian,” or “use the spectral representation” and you want to know what is actually being assumed.

## Prerequisites

You should know basic linear algebra, inner products, eigenvectors, adjoints of finite matrices, and ordinary Fourier series. Some comfort with metric spaces and convergence helps, but the chapter will introduce the functional-analytic language as it is needed.

For the distributional side, read [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), and [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/). For regularity, [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/) gives the first hint of why operator domains are usually Sobolev spaces rather than arbitrary smooth functions.

For QFT applications, [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) show how spectra enter one-loop path integrals. [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) and [Index Theorems](/math-toolkit/topology-cohomology-characteristic-classes/index-theorems/) show how spectral theory meets geometry and topology.

## Reading path

The chapter should be read as a repair manual for infinite-dimensional linear algebra. The pages are planned in this order:

| Step | Page | Main question |
|---:|---|---|
| 1 | Hilbert Spaces | What is the complete inner-product space in which quantum states live? |
| 2 | Linear Operators | What changes when matrices become operators on infinite-dimensional spaces? |
| 3 | Unbounded Operators | Why do Hamiltonians, momenta, and differential operators require domains? |
| 4 | Self-Adjointness | Why is “symmetric” weaker than “self-adjoint,” and why does time evolution care? |
| 5 | Spectral Theorem | How does an operator become an integral over its spectrum rather than a finite diagonal matrix? |
| 6 | Compact Operators | Why do some infinite-dimensional operators behave like matrices with discrete spectra? |
| 7 | Trace Class and Hilbert–Schmidt Operators | When do traces, determinants, and mode sums make analytic sense? |
| 8 | Spectral Density | How do continuous spectra become densities, discontinuities, and spectral representations? |
| 9 | Rigged Hilbert Spaces | Where do plane waves, position eigenstates, and delta-normalized states live? |

A perturbative QFT reader should prioritize steps 1 through 5, then step 8. A reader focused on one-loop determinants, heat kernels, and zeta regularization should add steps 6 and 7. A reader focused on scattering, plane waves, and generalized states should add step 9.

## Landmarks

The first landmark is **completion**. A Hilbert space is not just a vector space with an inner product. It is complete in the norm induced by that inner product. Completeness is what lets limits of Cauchy sequences stay inside the space. Without it, the analytic machinery leaks.

The second landmark is the **domain of an operator**. In finite-dimensional linear algebra, a linear map acts on the whole vector space. In quantum mechanics and QFT, the important operators are often unbounded and cannot be defined on every vector. Momentum, position, Hamiltonians, Laplacians, and Dirac operators all carry domain information.

The third landmark is the difference between **symmetric** and **self-adjoint**. An operator $A$ is symmetric if

$$
\langle \psi,A\phi\rangle=\langle A\psi,\phi\rangle
$$

for vectors in its domain. It is self-adjoint if

$$
A=A^*
$$

including equality of domains. This is the difference between a formally real expectation value and a genuine generator of unitary time evolution.

The fourth landmark is the **resolvent**. Instead of studying an unbounded operator $A$ directly, one often studies

$$
(A-z)^{-1}.
$$

The values of $z$ where this inverse exists form the resolvent set. The complement is the spectrum. In QFT, resolvents are cousins of Green functions and propagators.

The fifth landmark is the **spectral theorem**. For a self-adjoint operator $A$, one can write schematically

$$
A=\int_{\sigma(A)} \lambda\,dE(\lambda),
$$

where $E(\lambda)$ is a projection-valued spectral measure. This is the infinite-dimensional replacement for diagonalizing a Hermitian matrix.

The sixth landmark is **functional calculus**. Once $A$ has a spectral measure, functions of $A$ are defined by

$$
f(A)=\int_{\sigma(A)} f(\lambda)\,dE(\lambda).
$$

This is how one defines $e^{-itH}$, $e^{-sD^2}$, $\log A$, $A^{-1}$ when allowed, and many regulated determinants.

The seventh landmark is the **continuous spectrum**. A free particle does not have normalizable momentum eigenvectors in $L^2(\mathbb R^d)$, but momentum is still a self-adjoint operator. Its “eigenstates” are generalized distributions. This is why plane waves belong to a rigged Hilbert-space picture rather than to the Hilbert space itself.

The eighth landmark is the **trace ideal**. Not every operator has a trace. Not every compact operator has a determinant. Hilbert–Schmidt and trace-class conditions are analytic hypotheses that make common physics manipulations honest.

The ninth landmark is the **spectral density**. QFT often packages a continuous spectrum into a density $\rho(\mu^2)$, as in spectral representations of two-point functions. This density is not merely a change of notation; it expresses positivity, completeness, and the physical spectrum.

The tenth landmark is **operator-valued distributions**. A quantum field $\phi(x)$ is usually not an operator at a point in the naive sense. It becomes meaningful after smearing against a test function:

$$
\phi(f)=\int d^dx\,f(x)\phi(x).
$$

This is where functional analysis and distribution theory meet.

## Common confusions

**A Hermitian-looking differential expression is not automatically self-adjoint.** The expression $-d^2/dx^2$ can define different self-adjoint operators depending on boundary conditions and domain.

**The domain is part of the operator.** Two operators with the same formula but different domains can have different spectra, different adjoints, and different physics.

**Eigenvectors need not span the Hilbert space as ordinary vectors.** Continuous spectra are represented by spectral measures and generalized eigenvectors, not by a countable orthonormal basis of normalizable eigenstates.

**A delta-normalized plane wave is not a vector of finite norm.** It is a distributional object. This is not a flaw; it is exactly what the rigged Hilbert-space formalism is designed to express.

**A Green function is not always a true inverse.** Zero modes, boundary conditions, gauge redundancies, and domain choices can obstruct invertibility. Sometimes one inverts only on the orthogonal complement of the kernel.

**A trace is not always cyclic.** Cyclicity is safe under suitable trace-class hypotheses. Moving operators around inside divergent traces is a classic way to manufacture false anomalies or erase real ones.

**The determinant of an infinite-dimensional operator is not a product you can casually multiply.** Zeta regularization, heat-kernel subtraction, Fredholm determinants, and Pauli–Villars regulators define different but related notions under different hypotheses.

**The Hilbert space of a continuum QFT is not always built by tensor-factorizing spatial regions.** Local operator algebras in continuum QFT have subtleties that go beyond elementary Hilbert-space intuition, especially in entanglement questions.

## Boundaries

This chapter is not a rigorous constructive QFT course. It explains the analytic tools needed to read QFT formulas correctly, not the full existence theory of interacting relativistic fields.

It is also not a complete course in operator algebras. Von Neumann algebras, type-III factors, modular theory, Haag–Kastler nets, Tomita–Takesaki theory, and algebraic QFT will eventually need their own treatment. This chapter only prepares the Hilbert-space and spectral language that those subjects refine.

The chapter does not replace Analysis, Distributions, and Fourier Methods. Distribution theory explains smearing, Fourier transforms, principal values, and singular kernels. Functional analysis explains the spaces and operators on which those kernels act.

The chapter does not replace Differential Equations and Green Functions. Here the focus is on operators, domains, spectra, and functional calculus. The PDE chapter will focus on solving equations, boundary value problems, elliptic/hyperbolic/parabolic classification, and explicit Green functions.

Finally, this chapter does not make formal path integrals rigorous by itself. Spectral theory controls Gaussian integrals, determinants, heat kernels, and free fields very well. Interacting path integrals require renormalization, measure construction, stochastic or Euclidean methods, lattice limits, or algebraic frameworks.

## Where to go next

After this overview, the natural first page is Hilbert Spaces, followed by Linear Operators and Unbounded Operators. Those three pages establish the language needed for self-adjointness and the spectral theorem.

For immediate QFT applications, pair this chapter with [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/). For singular kernels and smearing, pair it with [Analysis, Distributions, and Fourier Methods](/math-toolkit/analysis-distributions-fourier/). For geometry-heavy operators, pair it with [Geometry of Fields](/math-toolkit/geometry-of-fields/).

The natural physics continuations are canonical quantization, free fields, scattering theory, Källén–Lehmann representations, spectral densities, one-loop determinants, heat kernels, Casimir energies, anomalies, and QFT on curved backgrounds.

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vols. I–IV. The standard mathematical physics reference for functional analysis, Fourier analysis, self-adjointness, scattering theory, and operator methods.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. A clear route into spectral theory, self-adjointness, and Schrödinger operators.
- B. C. Hall, *Quantum Theory for Mathematicians*. Useful for Hilbert spaces, unbounded operators, spectral theory, and mathematical quantum mechanics.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. A detailed physics-friendly reference for self-adjoint operators and spectral methods.
- K. Yosida, *Functional Analysis*. A classic functional-analysis reference.
- W. Rudin, *Functional Analysis*. A concise mathematical reference for locally convex spaces, distributions, and operator theory.
- I. M. Gelfand and N. Y. Vilenkin, *Generalized Functions*, Vol. 4. A classic source for rigged Hilbert spaces and generalized eigenfunction expansions.
- R. Haag, *Local Quantum Physics*. A standard reference for the operator-algebraic viewpoint beyond the elementary Hilbert-space picture.
- M. Srednicki, *Quantum Field Theory*. Useful for spectral representations, functional determinants, and how operator ideas enter practical QFT.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for the Hilbert-space and representation-theoretic foundations of relativistic QFT.

## Version history

- **2026-06-25:** Initial polished draft. Established the chapter map, prerequisites, reading path, landmarks, common confusions, boundaries, and follow-up route for Functional Analysis and Spectral Theory.
