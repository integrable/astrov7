---
title: "Functional Integrals and Determinants"
description: "Chapter overview for finite-dimensional Gaussian models, Grassmann integration, determinants, Pfaffians, Jacobians, saddle points, and the regulated prototypes behind path integrals."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard QFT functional-method references, with finite-dimensional linear algebra and analysis used as the model for continuum path integrals and determinants."
topics:
  - functional integrals
  - Gaussian integrals
  - determinants
  - Grassmann variables
  - saddle points
canonicalTopics:
  - functional-integrals
  - gaussian-integrals
  - grassmann-integration
  - functional-determinants
researchStatus:
  established:
    - "Finite-dimensional Gaussian, Grassmann, determinant, and saddle-point formulas are standard and are the algebraic backbone of perturbative and semiclassical QFT."
  active:
    - "Infinite-dimensional functional integrals and determinants require regulators, measures, domains, and renormalization; rigorous definitions depend strongly on the theory and dimension."
---

Functional Integrals and Determinants is the chapter in the Mathematical Toolkit volume where the formal phrase “integrate over fields” is reduced to precise finite-dimensional prototypes before being used in QFT. The central objects are Gaussian integrals, Grassmann integrals, determinants, Pfaffians, Jacobians, heat kernels, saddle points, and regulated products of eigenvalues.

The chapter does not pretend that continuum path integrals are ordinary Lebesgue integrals over an infinite-dimensional vector space. The safer rule is: every functional-integral formula should first be understood in finite dimension, then carried to fields by a regulator, limiting procedure, or perturbative expansion.

The guiding pattern is

$$
\int d^n x\,e^{-\frac12 x^T A x+J^T x}
=(2\pi)^{n/2}(\det A)^{-1/2}
e^{\frac12 J^T A^{-1}J}
\quad\leadsto\quad
Z[J]\sim (\det K)^{-1/2}e^{\frac12 \langle J,K^{-1}J\rangle}.
$$

<figure class="doc-figure" style="--figure-width: 45rem;">

![Functional determinant flow from Gaussian identities to QFT uses.](/figures/math-toolkit/functional-determinant-flow.svg)

<figcaption>

Finite-dimensional Gaussian identities produce inverse kernels, determinant factors, source contractions, and fermionic numerator determinants. Continuum QFT adds regulators, domains, zero modes, and boundary data.

</figcaption>
</figure>

That arrow is useful, but it is not innocent. In infinite dimension, $\det K$, $K^{-1}(x,y)$, $\mathcal D\phi$, and even the space being integrated over need interpretation. This chapter teaches the algebra and the warning labels together.

## Prerequisites

You should know [Mathematical Conventions](/math-toolkit/conventions/), especially the conventions for functional derivatives, distributions, Fourier transforms, and determinants. The most relevant background in the previous chapter is [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/), and [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/).

You should also be comfortable with finite-dimensional linear algebra: symmetric and Hermitian matrices, eigenvalues, determinants, traces, changes of variables, and diagonalization. Grassmann variables are introduced inside the chapter; no prior fermionic path-integral experience is assumed.

## Reading path

Start with finite-dimensional Gaussian integrals. They are the Rosetta stone for the free scalar path integral, propagators, Wick contractions, one-loop determinants, and saddle-point expansions.

A natural reading order is:

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Finite-Dimensional Gaussians | The exact matrix formulas behind every free bosonic path integral. |
| 2 | Gaussian Integrals | Sources, covariance matrices, Wick contractions, completing the square, and normalization. |
| 3 | Grassmann Algebra | Anticommuting variables, exterior algebra intuition, signs, and fermionic bookkeeping. |
| 4 | Berezin Integration | Fermionic Gaussian integrals and why determinants move upstairs. |
| 5 | Pfaffians | Real fermions, antisymmetric quadratic forms, and the square root of a determinant with sign data. |
| 6 | Functional Determinants | How products of eigenvalues arise from Gaussian fluctuation integrals and why they need regulation. |
| 7 | Zeta Regularization | A clean spectral definition of determinant-like objects when the spectrum is discrete and suitable. |
| 8 | Heat-Kernel Expansion | Short-time asymptotics, Seeley–DeWitt coefficients, UV divergences, and local counterterms. |
| 9 | Stationary Phase and Saddle Points | Semiclassical expansion, fluctuation operators, zero modes, collective coordinates, and phases. |
| 10 | Jacobians and Measures | Change of variables, anomalies, field redefinitions, and the danger hidden inside “the measure is invariant.” |
| 11 | Faddeev–Popov Determinants Preview | Gauge redundancy as overcounting, ghost determinants, and the handoff to gauge theory and BRST. |

There are two useful checkpoints. After the Gaussian pages, you should be able to derive why a real bosonic quadratic integral gives $(\det A)^{-1/2}$, while a complex fermionic quadratic integral gives $\det A$. After the determinant pages, you should be able to say what is being regulated before writing $\det(-\Delta+m^2)$.

## Landmarks

| Landmark | Meaning | QFT use |
|---|---|---|
| Covariance | The inverse of the quadratic form in a Gaussian integral. | Free propagators and Wick contractions. |
| Completing the square | The algebraic move that extracts source dependence. | Generating functionals and connected two-point functions. |
| Wick theorem | Gaussian moments are sums over pairings. | Perturbation theory and Feynman diagrams. |
| Grassmann variable | An anticommuting generator. | Fermionic sources, ghosts, and spinor path integrals. |
| Berezin integral | The linear operation that extracts the top Grassmann coefficient. | Fermionic Gaussian integrals. |
| Pfaffian | The natural Gaussian answer for real antisymmetric fermion operators. | Majorana fermions and global sign questions. |
| Functional determinant | A regulated product of eigenvalues of an operator. | One-loop effective actions and fluctuation determinants. |
| Heat kernel | The trace of $e^{-tK}$ for an operator $K$. | UV asymptotics, anomalies, and determinant regularization. |
| Zero mode | A flat direction of the quadratic fluctuation operator. | Collective coordinates, moduli, gauge orbits, and instantons. |
| Jacobian | The determinant produced by a change of variables. | Field redefinitions, anomalies, and Faddeev–Popov ghosts. |

The deepest landmark is the determinant. In finite dimension it is a number. In field theory it becomes a spectral object, a regulator-dependent expression, a source of anomalies, and often the first place where formal manipulations collide with ultraviolet physics.

## Common confusions

**“A path integral is just an integral over all functions.”** Usually not. In finite dimension, yes, it is an ordinary integral. In continuum QFT, the phrase may mean a lattice limit, a Gaussian measure on distributions, a formal perturbation series, an oscillatory integral, a Euclidean measure, or a rigorously constructed object in special dimensions.

**“The measure is translation invariant.”** There is no infinite-dimensional Lebesgue measure with all the finite-dimensional properties one might want. Translation invariance is safe in regulated finite-dimensional approximations; in the continuum it must be interpreted with care.

**“Bosons and fermions differ only by signs.”** The sign bookkeeping is only part of the story. Bosonic Gaussian integration gives inverse square roots of determinants. Fermionic Gaussian integration gives determinants or Pfaffians because Berezin integration extracts top-degree coefficients rather than damping ordinary variables.

**“A functional determinant is a determinant of an infinite matrix.”** That phrase is a mnemonic, not a definition. A functional determinant is normally defined through a regulator: eigenvalue cutoff, heat kernel, zeta function, Pauli–Villars subtraction, dimensional regularization, lattice discretization, or determinant ratios.

**“Zero modes can be ignored because they are measure zero.”** Zero modes make the Gaussian determinant vanish or diverge. They usually signal a symmetry, modulus, collective coordinate, constraint, or instability. They must be separated before applying the ordinary Gaussian formula.

**“A Jacobian is always harmless.”** In field theory a Jacobian can be a local counterterm, a Faddeev–Popov determinant, or an anomaly. The phrase “the measure is invariant” is a claim, not a default law of nature.

**“Euclidean and Lorentzian Gaussian integrals differ only by replacing $S_E$ with $iS$.”** That is the slogan, not the full analytic story. Oscillatory integrals require contours, $i\epsilon$ prescriptions, boundary conditions, and sometimes analytic continuation. The Euclidean formulas are often the cleanest mathematical starting point.

## Boundaries

This chapter is not the main home of the physical path-integral formalism. The foundations pages explain how path integrals represent quantum time evolution, correlation functions, perturbation theory, and Wick rotation. This chapter supplies the mathematical prototypes those pages use.

The chapter is not a full course in measure theory, constructive QFT, stochastic analysis, or perturbative algebraic QFT. It points toward those subjects when infinite-dimensional integration becomes subtle, but it does not replace theorem-first treatments.

The chapter also does not own renormalization. Heat-kernel coefficients, determinant divergences, and Jacobians naturally point to counterterms and anomalies, but the conceptual theory of scale dependence belongs to renormalization and EFT pages. Likewise, full gauge fixing, BRST symmetry, and the Faddeev–Popov procedure belong to gauge and symmetry pages after the determinant idea is introduced here.

Finally, this chapter is not a table of special functions. Determinants often reduce to gamma functions, zeta functions, eta invariants, modular functions, or elliptic functions in examples, but the special-function technology has its own chapter.

## Where to go next

After this chapter, the mathematically natural next stop is Calculus of Variations and Phase Space: functional derivatives, Euler–Lagrange operators, boundary terms, Legendre transforms, symplectic forms, and Poisson brackets explain what the action is doing before quantization.

For analytic control of fluctuation operators, continue to Functional Analysis and Spectral Theory, then Differential Equations and Green Functions. For anomalies, determinant line bundles, index densities, and topological terms, continue to Geometry of Fields and Topology, Cohomology, and Characteristic Classes.

For physics applications, the immediate handoffs are the path-integral formalism in Foundations of QFT, loop expansion in Perturbative QFT and Scattering, renormalization and EFT, gauge fixing and ghosts in gauge theory, and semiclassical methods in nonperturbative QFT.

A good practical sequence for a graduate QFT reader is: distributions and Fourier methods, this chapter through Berezin integration, functional derivatives, Lie groups, spinors, then return here for determinants and heat kernels when one-loop calculations or anomalies appear.

## References

- M. Srednicki, *Quantum Field Theory*. Practical treatment of bosonic and fermionic path integrals, generating functionals, and functional determinants.
- A. Zee, *Quantum Field Theory in a Nutshell*. Intuitive discussion of Gaussian integration, path integrals, symmetry, anomalies, and functional methods.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* and *Aspects of Symmetry*. Functional integration, instantons, determinants, false-vacuum decay, and semiclassical reasoning.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Generating functionals, effective action, gauge fixing, ghosts, and determinant-based one-loop methods.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, Gaussian integrals, Grassmann variables, saddle points, and renormalization.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*. Mathematical perspective on Euclidean functional integrals and constructive field theory.
- B. Simon, *Functional Integration and Quantum Physics*. Foundational reference for functional integration and Gaussian measures.
- P. Deligne et al., *Quantum Fields and Strings: A Course for Mathematicians*. Useful for determinant lines, fermions, anomalies, and geometric viewpoints.

## Version history

- 2026-06-24: First polished draft. Established the chapter scope, reading path, determinant and Grassmann landmarks, common confusions, boundaries, and handoffs to path integrals, renormalization, gauge theory, and rigorous QFT.
