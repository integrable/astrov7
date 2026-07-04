---
title: "Differential Equations and Green Functions"
description: "Chapter overview for ordinary and partial differential equations, boundary-value problems, Green functions, heat kernels, wave equations, and Schrödinger operators in the Mathematical Toolkit volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard mathematical physics and PDE references, including Courant–Hilbert, Evans, Folland, Taylor, Strauss, Teschl, Reed–Simon, Gilkey, Vassilevich, Moretti, and QFT treatments of propagators, heat kernels, and Green functions."
topics:
  - differential equations
  - Green functions
  - ordinary differential equations
  - partial differential equations
  - boundary-value problems
  - elliptic equations
  - hyperbolic equations
  - parabolic equations
  - heat kernels
  - wave equations
  - Schrödinger operators
canonicalTopics:
  - differential-equation
  - green-function
  - ordinary-differential-equation
  - partial-differential-equation
  - boundary-value-problem
  - elliptic-equation
  - hyperbolic-equation
  - parabolic-equation
  - heat-kernel
  - wave-equation
  - schrodinger-operator
researchStatus:
  established:
    - "Differential operators, boundary conditions, Green functions, heat kernels, wave propagators, and spectral methods form the standard bridge between local field equations and QFT propagators."
  active:
    - "Singular backgrounds, gauge redundancies, Lorentzian boundary conditions, nonlinear PDEs, numerical PDEs, and interacting QFT require additional analytic and physical input beyond the elementary Green-function picture."
---

Differential Equations and Green Functions is the chapter in the Mathematical Toolkit volume where local equations become global solutions. A field equation such as

$$
L\phi=J
$$

is not yet a complete problem. One must specify the domain, boundary or initial data, allowed singularities, zero modes, and the kind of inverse one wants. Only then does a Green function become meaningful.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Roadmap diagram showing differential equations, data, operator domains, inverses, resolvents, Green kernels, heat kernels, propagators, and QFT applications.](/figures/math-toolkit/differential-equations-green-functions-roadmap.svg)

<figcaption>

A differential equation becomes a Green-function problem only after the local operator $L$ is paired with domain and boundary or initial data. The inverse may be an elliptic Green function, a resolvent, a heat kernel, a retarded response, an advanced response, or a Feynman propagator. These are related, but not interchangeable.

</figcaption>
</figure>

In QFT, differential equations appear before quantization and after quantization. Classical equations determine stationary points of the action. Free-field equations determine propagators. Heat equations organize determinants and anomalies. Wave equations encode causality. Schrödinger operators control spectra, scattering, bound states, and stability. Green functions are the common language connecting all of these.

The chapter slogan is

$$
\text{operator} + \text{data} + \text{inverse prescription}
\quad\Longrightarrow\quad
\text{Green function}.
$$

Without the data and prescription, the phrase “the Green function” is usually missing a noun-sized chunk of information.

## Prerequisites

You should know multivariable calculus, integration by parts, Fourier transforms, distributions, and basic Hilbert-space language. The most relevant earlier chapters are [Analysis, Distributions, and Fourier Methods](/math-toolkit/analysis-distributions-fourier/), [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/), [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/), and [Calculus of Variations and Phase Space](/math-toolkit/calculus-of-variations-and-phase-space/).

For this chapter, the essential background ideas are:

| Tool | Why it matters here |
|---|---|
| distributions | Green functions are often distributional kernels |
| Fourier transforms | constant-coefficient equations are easiest in momentum space |
| domains | differential expressions become operators only after specifying domains |
| self-adjointness | spectra, unitary evolution, and real eigenvalues depend on it |
| spectral theorem | resolvents, heat kernels, and propagators can be built from spectra |
| boundary terms | integration by parts exposes boundary conditions and adjoints |

The chapter does not assume a rigorous PDE course, but it does assume you are willing to treat boundary conditions as part of the problem rather than as garnish. Boundary conditions are not garnish. They are the part of the sandwich that bites back.

## Reading path

This chapter is best read as a bridge from elementary equations to QFT kernels.

| Step | Page | Guiding question |
|---:|---|---|
| 1 | Ordinary Differential Equations | How do mode equations, Wronskians, and fundamental solutions work in one variable? |
| 2 | Partial Differential Equations | What changes when fields depend on spacetime or space? |
| 3 | Elliptic, Hyperbolic, and Parabolic Equations | How does the principal part determine the kind of problem? |
| 4 | Boundary-Value Problems | How do boundary conditions define operators, spectra, and inverses? |
| 5 | Sturm–Liouville Theory | Why do orthogonal modes and weighted inner products appear so often? |
| 6 | Green Functions | How does an inverse operator become a distributional kernel? |
| 7 | Heat Equation and Heat Kernel | Why does $e^{-sL}$ control determinants, anomalies, and short-distance asymptotics? |
| 8 | Wave Equation | How do support, finite propagation speed, and retarded response encode causality? |
| 9 | Schrödinger Operators | How do potentials, bound states, scattering states, and resolvents enter QFT? |

A first-year QFT reader should prioritize Green Functions, Heat Equation and Heat Kernel, and Wave Equation. A reader studying one-loop determinants, anomalies, Casimir energies, or curved-space QFT should add Boundary-Value Problems and Sturm–Liouville Theory. A reader studying scattering, solitons, stability, tunneling, or spectral density should add Schrödinger Operators.

## Landmarks

The first landmark is the **operator versus expression** distinction. The expression

$$
-\frac{d^2}{dx^2}
$$

is not yet an operator. On an interval, Dirichlet, Neumann, Robin, and periodic boundary conditions define different operators with different spectra. In QFT language, the differential expression is local; the domain is global.

The second landmark is the **principal symbol**. For a linear differential operator, the highest-derivative part controls the local type of the equation. Roughly, elliptic equations behave like boundary-value problems, hyperbolic equations behave like initial-value problems, and parabolic equations behave like diffusion or Euclidean-time evolution.

The third landmark is the **fundamental solution**. A fundamental solution solves

$$
L_xG(x,y)=\delta(x-y)
$$

locally or distributionally. It may not satisfy the boundary conditions of a particular problem. A Green function for a boundary-value problem is a fundamental solution plus the correct global conditions.

The fourth landmark is the **resolvent**. For an operator $L$, the object

$$
(L-z)^{-1}
$$

is often better behaved than $L^{-1}$. Its kernel is a Green function with spectral parameter $z$. Poles and cuts of the resolvent encode eigenvalues, resonances, continuous spectrum, and spectral density.

The fifth landmark is the **heat kernel**:

$$
K(s;x,y)=\langle x|e^{-sL}|y\rangle.
$$

For suitable positive elliptic $L$, it solves

$$
(\partial_s+L_x)K(s;x,y)=0,
\qquad
K(0;x,y)=\delta(x-y).
$$

The short-time expansion of $K$ is a local microscope. It detects dimension, curvature, boundary geometry, gauge curvature, divergences, and anomaly coefficients.

The sixth landmark is the **wave kernel**. Hyperbolic equations remember causal support. Retarded Green functions vanish outside the future light cone; advanced Green functions vanish outside the past light cone. The Feynman propagator is another prescription, designed for time-ordered quantum amplitudes, not classical response.

The seventh landmark is **zero modes**. If $L$ has a nontrivial kernel, then $L^{-1}$ does not exist on the whole space. One may need to project out zero modes, impose constraints, fix a gauge, add collective coordinates, or define a pseudo-inverse. Zero modes are where many beautiful calculations first develop teeth.

The eighth landmark is **spectral decomposition**. When $L$ has eigenfunctions $u_n$ with eigenvalues $\lambda_n$, one often writes

$$
G(x,y)=\sum_n\frac{u_n(x)\overline{u_n(y)}}{\lambda_n}.
$$

When the spectrum is continuous, the sum becomes an integral over a spectral measure. This is where this chapter meets [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/) and [Rigged Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/rigged-hilbert-spaces/).

The ninth landmark is **regularity**. Solving $Lu=f$ may improve, preserve, or degrade regularity depending on the operator and the problem type. Elliptic operators tend to smooth. Hyperbolic operators propagate singularities. Parabolic operators smooth forward in time. QFT sees these facts as UV behavior, propagation, and analytic continuation.

The tenth landmark is **kernel composition**. If operators have kernels, composition looks like

$$
(AB)(x,z)=\int dy\,A(x,y)B(y,z).
$$

This simple formula underlies propagator composition, heat-kernel semigroups, Schwinger proper time, transfer matrices, and many diagrammatic calculations.

## How this chapter connects to QFT

A free scalar field satisfies the Klein–Gordon equation

$$
(\Box+m^2)\phi=0
$$

with our mostly-minus convention. Its propagators are Green functions for the operator $\Box+m^2$ with different pole prescriptions.

In momentum space, the formal inverse is

$$
\frac1{p^2-m^2}.
$$

The physical propagator is not just this rational expression; it includes a prescription such as

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

That $i\epsilon$ tells the distribution how to pass poles and encodes time ordering.

In Euclidean field theory, a typical free operator is

$$
L=-\Delta+m^2.
$$

Its Green function solves

$$
(-\Delta_x+m^2)G(x,y)=\delta^{(d)}(x-y),
$$

and its heat kernel controls the determinant:

$$
\log\det L
=-\int_0^\infty\frac{ds}{s}\operatorname{Tr}e^{-sL}
$$

after regularization. This connects directly to [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

In gauge theory, the quadratic fluctuation operator may have zero modes because gauge-equivalent field configurations are not physically distinct. Inverting such an operator requires gauge fixing and ghosts. This is why Green functions, determinants, and gauge conditions are inseparable in perturbative gauge theory.

In curved backgrounds, the operator may be a Laplace-type operator, a Dirac operator squared, or a wave operator on a Lorentzian manifold. The Green function then depends on geometry, causal structure, boundary conditions, and sometimes global topology.

## Common confusions

**A fundamental solution is not automatically the Green function for your problem.** A fundamental solution solves the delta-function equation locally. A Green function for a boundary-value problem must also satisfy the boundary conditions.

**The inverse depends on the function space.** The same formal expression can define different operators on different domains. Different domains can give different kernels.

**Retarded, advanced, Euclidean, and Feynman Green functions are not the same object.** They solve related differential equations, but they encode different boundary, support, or analytic-continuation prescriptions.

**Elliptic does not mean Euclidean and hyperbolic does not mean Lorentzian in every context.** The classification concerns the principal symbol of an operator. Euclidean QFT often uses elliptic operators; Lorentzian QFT often uses hyperbolic operators, but the words are not merely coordinate labels.

**A Green function may fail to exist because of zero modes.** If $L\psi=0$ has nonzero solutions in the allowed domain, then $L^{-1}$ is obstructed. One must project, constrain, regularize, or choose a generalized inverse.

**The heat kernel is not just a warm Green function.** It is the kernel of $e^{-sL}$ and solves a diffusion-type equation in the auxiliary parameter $s$. Its small-$s$ expansion is local and controls UV divergences.

**A pole prescription is part of the definition.** Expressions such as $1/(p^2-m^2)$ are ambiguous as distributions. The $i\epsilon$ prescription, principal value prescription, or retarded prescription changes the answer.

**Boundary terms are not harmless.** Integration by parts creates boundary terms. Setting them to zero is a boundary condition, not a law of nature.

**Mode sums are often distributions or regulated objects.** A formal sum over eigenfunctions may converge weakly, require regularization, or fail without smoothing.

## Boundaries

This chapter is not a complete PDE textbook. It gives the PDE and Green-function technology most often needed in QFT, not the full theory of weak solutions, nonlinear PDE, microlocal analysis, inverse problems, or global Lorentzian geometry.

It is not a numerical PDE chapter. Finite differences, finite elements, spectral methods, stability of discretizations, and solver conditioning belong in Numerical Mathematics for QFT. This chapter supplies the continuum equations that those methods approximate.

It is not a replacement for Functional Analysis and Spectral Theory. Operator domains, self-adjointness, spectral measures, compactness, trace ideals, and rigged Hilbert spaces are developed there. This chapter uses that language to build kernels and solve equations.

It is not a replacement for Analysis, Distributions, and Fourier Methods. Delta functions, principal values, Fourier transforms, test functions, and tempered distributions are developed there. This chapter uses them to interpret Green functions.

It is not a full treatment of propagators in interacting QFT. Interactions turn Green functions into correlation functions with perturbative, nonperturbative, and renormalization subtleties. This chapter explains the linear analytic backbone.

## Where to go next

After this overview, the natural first technical page is Ordinary Differential Equations, followed by Partial Differential Equations and Elliptic, Hyperbolic, and Parabolic Equations. Those pages set up the local language before Green functions enter.

For immediate QFT use, jump to Green Functions after reviewing the classification page. Then read Heat Equation and Heat Kernel if you care about determinants, anomalies, or effective actions; read Wave Equation if you care about causality, retarded response, or Lorentzian propagation.

Pair this chapter with [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/) for domains and spectra, [Analysis, Distributions, and Fourier Methods](/math-toolkit/analysis-distributions-fourier/) for kernels and singularities, and [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/) for one-loop determinants and heat-kernel regularization.

## References

- R. Courant and D. Hilbert, *Methods of Mathematical Physics*. Classic source for differential equations, eigenvalue problems, and mathematical physics methods.
- L. C. Evans, *Partial Differential Equations*. Standard modern reference for PDE concepts, weak solutions, elliptic/parabolic/hyperbolic problems, and regularity.
- G. B. Folland, *Introduction to Partial Differential Equations*. Concise reference for distributions, fundamental solutions, Fourier methods, and PDE classification.
- M. E. Taylor, *Partial Differential Equations*, Vols. I–III. Broad reference for PDE theory, pseudodifferential methods, and geometric analysis.
- W. A. Strauss, *Partial Differential Equations: An Introduction*. Pedagogical route through first-order equations, waves, heat flow, and elliptic equations.
- G. Teschl, *Ordinary Differential Equations and Dynamical Systems* and *Mathematical Methods in Quantum Mechanics*. Useful for ODEs, Sturm–Liouville theory, Schrödinger operators, and spectral methods.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, especially Vols. I–IV. Standard mathematical physics reference for operators, spectra, scattering, and Schrödinger equations.
- P. B. Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*. Classic reference for heat kernels and geometric operators.
- D. V. Vassilevich, “Heat Kernel Expansion: User’s Manual.” A physics-friendly reference for heat-kernel coefficients, boundaries, and QFT applications.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Useful for Green functions, resolvents, self-adjointness, and quantum-mechanical operators.
- B. S. DeWitt, *Dynamical Theory of Groups and Fields*. Classic reference for Green functions and heat-kernel methods in curved-space field theory.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*. Useful for propagators, Green functions, and curved-background QFT.

## Version history

- 2026-06-25: Initial polished draft.
