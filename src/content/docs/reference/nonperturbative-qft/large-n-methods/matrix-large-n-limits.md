---
title: "Matrix Large-N Limits"
description: "Explains how large-N matrix integrals become eigenvalue-density saddle-point problems and how this leads to planar and double-scaling expansions."
sidebar:
  label: "Matrix Large-N Limits"
  order: 3
level: Advanced
status: "Polished draft"
source: "Mariño; Polyakov; Brézin–Itzykson–Parisi–Zuber; Pestun et al.; standard random-matrix and large-N literature."
topics:
  - matrix models
  - large-N limits
  - eigenvalue density
  - resolvent
  - planar diagrams
  - double scaling
  - random matrices
  - saddle-point equations
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - matrix-large-n-limits
  - eigenvalue-density
  - planar-expansion
  - double-scaling
researchStatus:
  established:
    - "Large-N matrix integrals reduce to saddle-point problems for eigenvalue densities, with a planar expansion organized by powers of 1/N squared."
  active:
    - "Modern matrix-model uses in localization, holography, topological strings, random geometry, and nonperturbative completions require model-specific status checks."
---

## Summary

A matrix large-$N$ limit studies variables with $O(N^2)$ degrees of freedom, such as an $N\times N$ Hermitian matrix $M$. The simplest zero-dimensional example is the one-matrix integral

$$
Z_N=\int dM\,\exp\left[-N\operatorname{Tr}V(M)\right].
$$

After diagonalizing

$$
M=U\Lambda U^\dagger,
\qquad
\Lambda=\operatorname{diag}(\lambda_1,\dots,\lambda_N),
$$

the measure contains the Vandermonde factor

$$
\Delta(\lambda)^2=\prod_{i<j}(\lambda_i-\lambda_j)^2.
$$

The large-$N$ variable is not a single number, but an eigenvalue density

$$
\rho(\lambda)=\frac1N\sum_{i=1}^N\delta(\lambda-\lambda_i),
\qquad
\int d\lambda\,\rho(\lambda)=1.
$$

At leading order, the eigenvalues form a continuous distribution determined by a saddle equation,

$$
V'(\lambda)=2\,\mathcal P\int d\mu\,\frac{\rho(\mu)}{\lambda-\mu},
\qquad \lambda\in \operatorname{supp}\rho.
$$

This page explains how that equation arises, why the free energy has a topological expansion, and why matrix large $N$ is the natural bridge from vector-model saddles to planar gauge theory.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Matrix large-N workflow: matrix fields, double-line notation, ribbon graphs, topological weighting, diagonalization, Vandermonde repulsion, eigenvalue density, and resolvent saddle.](/figures/nonperturbative-qft/matrix-large-n-limits-map.svg)

<figcaption>

The large-$N$ matrix saddle. Diagonalizing a Hermitian matrix turns the integral into an eigenvalue gas: the potential $V(\lambda)$ confines the eigenvalues while the Vandermonde determinant produces logarithmic repulsion. At $N=\infty$, the discrete eigenvalues become a density $\rho(\lambda)$, and the saddle equation can be recast as an analytic problem for the resolvent $\omega(z)$.

</figcaption>
</figure>

## Prerequisites

Read [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) and [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) first. You should also know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) and the basic idea of [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/).

No serious random-matrix background is assumed. The only linear algebra input is that a Hermitian matrix can be diagonalized by a unitary transformation and that the change of variables from matrix entries to eigenvalues and angles has a nontrivial Jacobian.

## Core idea

Vector large $N$ has $O(N)$ microscopic variables, and the collective action scales like $N$. Matrix large $N$ has $O(N^2)$ variables, so the natural action and free energy scale like $N^2$.

The main chain is

$$
N\times N\text{ matrix}
\quad\Longrightarrow\quad
\text{eigenvalues plus angles}
\quad\Longrightarrow\quad
\text{Vandermonde repulsion}
\quad\Longrightarrow\quad
\rho(\lambda)\text{ saddle}
\quad\Longrightarrow\quad
\text{planar expansion}.
$$

This is a different kind of classical limit. The saddle variable is not a Lagrange multiplier or an order parameter; it is a continuous distribution of eigenvalues.

## Setup and conventions

Consider a Hermitian one-matrix model

$$
Z_N=\int dM\,\exp\left[-N\operatorname{Tr}V(M)\right],
$$

where $V(M)$ is usually a polynomial or analytic potential. The factor $N$ in front of the trace is the standard large-$N$ normalization. Since $\operatorname{Tr}V(M)$ is typically $O(N)$ for eigenvalues of order one, the exponent is $O(N^2)$.

After diagonalization,

$$
dM=C_N\,dU\,\prod_{i=1}^N d\lambda_i\,\prod_{i<j}(\lambda_i-\lambda_j)^2,
$$

where $C_N$ is a normalization constant and $dU$ is the angular measure. For potentials that depend only on eigenvalues, the angular integral factors out. The partition function becomes

$$
Z_N\propto\int\prod_i d\lambda_i\,
\exp\left[-N\sum_i V(\lambda_i)+2\sum_{i<j}\log|\lambda_i-\lambda_j|\right].
$$

Equivalently,

$$
Z_N\propto\int\prod_i d\lambda_i\,e^{-S_{\rm eig}(\lambda)},
$$

with

$$
S_{\rm eig}(\lambda)
=N\sum_i V(\lambda_i)-2\sum_{i<j}\log|\lambda_i-\lambda_j|.
$$

The logarithm is repulsive. Eigenvalues do not simply fall independently to the minimum of $V$; they spread out.

## Eigenvalue density and saddle equation

Define the normalized eigenvalue density

$$
\rho(\lambda)=\frac1N\sum_i\delta(\lambda-\lambda_i),
\qquad
\int d\lambda\,\rho(\lambda)=1.
$$

At large $N$,

$$
\sum_i f(\lambda_i)\to N\int d\lambda\,\rho(\lambda)f(\lambda),
$$

and

$$
\sum_{i<j}\log|\lambda_i-\lambda_j|
\to \frac{N^2}{2}\int d\lambda d\mu\,\rho(\lambda)\rho(\mu)\log|\lambda-\mu|,
$$

up to subleading self-energy and measure effects. Thus the leading effective action is

$$
S_{\rm eff}[\rho]
=N^2\left[
\int d\lambda\,\rho(\lambda)V(\lambda)
-\int d\lambda d\mu\,\rho(\lambda)\rho(\mu)\log|\lambda-\mu|
\right]
+\text{constraint terms}.
$$

The normalization constraint is imposed by a Lagrange multiplier. Varying $\rho$ gives

$$
V(\lambda)-2\int d\mu\,\rho(\mu)\log|\lambda-\mu|=\ell,
\qquad \lambda\in \operatorname{supp}\rho,
$$

where $\ell$ is constant on the support. Differentiating with respect to $\lambda$ gives the singular integral equation

$$
V'(\lambda)=2\,\mathcal P\int d\mu\,\frac{\rho(\mu)}{\lambda-\mu}.
$$

The principal value is essential because the kernel is singular at $\mu=\lambda$.

## The Gaussian example

For the Gaussian matrix model,

$$
V(\lambda)=\frac12\lambda^2,
$$

the saddle equation is

$$
\lambda=2\,\mathcal P\int d\mu\,\frac{\rho(\mu)}{\lambda-\mu}.
$$

The solution is the Wigner semicircle distribution,

$$
\rho(\lambda)=\frac1{2\pi}\sqrt{4-\lambda^2},
\qquad -2\le \lambda\le 2.
$$

The square-root behavior at the endpoints is typical of one-cut matrix-model saddles. It is also the seed of critical behavior: when cuts merge, when an endpoint becomes higher order, or when eigenvalues are tuned to an edge, new continuum limits can appear.

## Resolvent method

The resolvent is the analytic function

$$
\omega(z)=\int d\lambda\,\frac{\rho(\lambda)}{z-\lambda}.
$$

It has the large-$z$ expansion

$$
\omega(z)=\frac1z+\frac{\langle \lambda\rangle}{z^2}+\frac{\langle \lambda^2\rangle}{z^3}+\cdots,
$$

so it packages the moments of the eigenvalue distribution. Across the support of $\rho$, the discontinuity determines the density:

$$
\rho(\lambda)=\frac{1}{2\pi i}\left[\omega(\lambda-i0)-\omega(\lambda+i0)\right].
$$

For the Gaussian model,

$$
\omega(z)=\frac12\left(z-\sqrt{z^2-4}\right),
$$

where the branch is chosen so that

$$
\omega(z)\sim \frac1z
\qquad z\to\infty.
$$

Resolvents are useful because they convert a real singular integral equation into a problem in complex analysis. This is why matrix models sit at the crossroads of QFT, random matrices, spectral theory, and algebraic geometry.

## Planar expansion

Matrix large $N$ also has a diagrammatic interpretation. In a matrix field or matrix integral with interaction vertices built from traces, propagators carry two matrix indices. Drawing each propagator as a double line gives a ribbon graph. The power of $N$ is controlled by

$$
N^{F-E+V}=N^\chi,
$$

where $F$ is the number of index loops, $E$ is the number of propagators, $V$ is the number of vertices, and

$$
\chi=2-2h-b
$$

is the Euler characteristic of the associated surface, with genus $h$ and boundary number $b$. For vacuum diagrams with no boundaries,

$$
\chi=2-2h.
$$

Thus the free energy has the topological expansion

$$
\log Z_N=N^2F_0+F_1+\frac1{N^2}F_2+\cdots.
$$

The leading term $F_0$ is planar. Corrections add handles and are suppressed by powers of $1/N^2$.

This is the diagrammatic reason matrix large $N$ is string-like: ribbon diagrams are discretized surfaces. It does not mean every matrix model is a literal string theory, but it explains why surfaces keep showing up.

## Multi-cut saddles and phases

If $V(\lambda)$ has several wells, the eigenvalue distribution may have several disconnected intervals of support:

$$
\operatorname{supp}\rho=\bigcup_{a=1}^k [A_a,B_a].
$$

These are multi-cut saddles. The filling fractions

$$
\nu_a=\int_{A_a}^{B_a}d\lambda\,\rho(\lambda),
\qquad
\sum_a\nu_a=1,
$$

can label different saddle sectors. In many applications, changing the support of $\rho$ is the matrix-model analogue of a phase transition.

The important lesson is that large-$N$ matrix models have global saddle data. It is not enough to solve a local equation; one must choose the support, branch cuts, filling fractions, and stability conditions.

## Matrix integrals versus matrix field theories

A zero-dimensional matrix model is an integral. A matrix quantum mechanics is a one-dimensional path integral. A matrix field theory is a QFT whose fields are matrices. These are different objects, but they share a large-$N$ grammar:

$$
\text{matrix indices}
\quad\Longrightarrow\quad
\text{ribbon diagrams}
\quad\Longrightarrow\quad
\text{topological expansion}.
$$

In supersymmetric localization, some genuine QFT observables reduce exactly to finite-dimensional matrix integrals. In that setting, a matrix model may compute a partition function or Wilson-loop observable of a higher-dimensional field theory. The interpretation of the saddle then belongs to the original QFT, not just to the auxiliary matrix integral.

## Nonperturbative effects in N

The $1/N$ expansion is usually asymptotic. Effects of the form

$$
e^{-cN}
\qquad\text{or}\qquad
 e^{-cN^2}
$$

are invisible in ordinary planar perturbation theory. In matrix models, such effects may come from eigenvalue tunneling out of a cut, instanton-like saddles, or competing eigenvalue distributions.

This is the matrix-model version of a recurring theme: a good asymptotic expansion can know a great deal and still miss exponentially small sectors.

## Checks and diagnostics

**Check the scaling of the exponent.** With $N\operatorname{Tr}V(M)$, the potential term is $O(N^2)$ and competes with the $O(N^2)$ logarithmic repulsion from the Vandermonde determinant.

**Check normalization of the density.** The density must obey $\int\rho=1$. Forgetting this constraint changes the saddle equation.

**Check the large-$z$ behavior of the resolvent.** The condition $\omega(z)\sim 1/z$ enforces normalization and selects the correct branch.

**Check positivity.** A formal solution of the singular integral equation is not enough. The density must be nonnegative on its support.

**Check the support.** One-cut and multi-cut solutions can describe different saddle sectors or phases. The endpoint conditions are part of the solution.

## Common pitfalls

**Letting eigenvalues independently minimize the potential.** The Vandermonde determinant causes logarithmic repulsion. The eigenvalues spread into a distribution even for a simple quadratic potential.

**Confusing $1/N$ and $1/N^2$.** Matrix and adjoint gauge-theory vacuum amplitudes usually organize in powers of $1/N^2$, while vector models often organize in powers of $1/N$.

**Treating the matrix model as automatically a gauge theory.** Matrix integrals are not gauge theories by themselves. They become connected to QFT in specific ways: as toy models, as reduced models, as large-$N$ diagram generators, or as exact localization formulas.

**Ignoring nonperturbative-in-N saddles.** The planar expansion can miss eigenvalue tunneling and competing saddles. These are not small corrections to any finite order in $1/N$; they are beyond the expansion.

**Calling every surface expansion a string dual.** Ribbon graphs suggest string-like organization, but a full string theory requires more structure: continuum limits, worldsheet dynamics, observables, and a consistent interpretation.

## Relations to other pages

[Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) and [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) develop saddle-point methods for $O(N)$ singlet variables. [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) abstracts the shared steepest-descent logic. This page replaces singlet auxiliary fields by eigenvalue densities; [Eigenvalue-Density Methods](/nonperturbative-qft/large-n-methods/eigenvalue-density-methods/) develops that method in detail.

[Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) gives the gauge-theory motivation for planar dominance. [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) makes the double-line counting explicit for field theory, while [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) explains the connected-correlator consequence of the same topology.

[QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/) and [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/) explain why the surface interpretation is tempting in confining gauge theories. Matrix models provide a simpler arena where surfaces arise directly from diagram topology, and [Double-Scaling Limits Preview](/nonperturbative-qft/large-n-methods/double-scaling-limits-preview/) explains how those surfaces can survive a continuum critical limit.

## Research status

**Established.** The eigenvalue-density saddle and resolvent method are standard tools for large-$N$ matrix integrals. The planar expansion and the Euler-characteristic counting of ribbon graphs are also standard.

**Established with context.** Matrix models compute exact observables in some supersymmetric theories after localization, and they model random surfaces and spectral statistics in many settings. The interpretation depends on the original problem.

**Active.** Nonperturbative completions, eigenvalue instantons, double-scaling limits, higher-dimensional reductions, holographic matrix models, and real-time matrix dynamics remain active research areas.

## Exercises

### Exercise 1: Derive the eigenvalue saddle

Starting from

$$
S_{\rm eig}
=N\sum_i V(\lambda_i)-2\sum_{i<j}\log|\lambda_i-\lambda_j|,
$$

show that the finite-$N$ saddle equation is

$$
N V'(\lambda_i)=2\sum_{j\ne i}\frac1{\lambda_i-\lambda_j}.
$$

Then take the large-$N$ limit to obtain

$$
V'(\lambda)=2\,\mathcal P\int d\mu\,\frac{\rho(\mu)}{\lambda-\mu}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate $S_{\rm eig}$ with respect to $\lambda_i$:

$$
\frac{\partial S_{\rm eig}}{\partial\lambda_i}
=N V'(\lambda_i)-2\sum_{j\ne i}\frac1{\lambda_i-\lambda_j}.
$$

Setting this to zero gives the finite-$N$ saddle. At large $N$,

$$
\frac1N\sum_{j\ne i}\frac1{\lambda_i-\lambda_j}
\to \mathcal P\int d\mu\,\frac{\rho(\mu)}{\lambda-\mu},
$$

where the principal value removes the singular self-interaction. Dividing by $N$ gives the continuum saddle equation.

</details>

### Exercise 2: Check the semicircle normalization

Verify that

$$
\rho(\lambda)=\frac1{2\pi}\sqrt{4-\lambda^2},
\qquad -2\le\lambda\le2,
$$

is normalized to one.

<details>
<summary><strong>Solution</strong></summary>

Use the area of a semicircle of radius $2$:

$$
\int_{-2}^{2}d\lambda\,\sqrt{4-\lambda^2}
=\frac12\pi(2)^2=2\pi.
$$

Therefore

$$
\int_{-2}^{2}d\lambda\,\rho(\lambda)
=\frac1{2\pi}\,2\pi=1.
$$

</details>

### Exercise 3: Why vacuum ribbon graphs scale as N to the Euler characteristic

A ribbon graph has $V$ vertices, $E$ propagators, and $F$ closed index loops. Explain why its power of $N$ is

$$
N^{F-E+V}.
$$

<details>
<summary><strong>Solution</strong></summary>

Each closed index loop gives a free sum over $1,\dots,N$, hence a factor of $N$. With the conventional large-$N$ normalization, each propagator and vertex contributes powers arranged so that the net graph weight is $N^{F-E+V}$. The combination

$$
F-E+V=\chi
$$

is the Euler characteristic of the ribbon surface. For a closed orientable surface of genus $h$,

$$
\chi=2-2h,
$$

so planar vacuum graphs scale as $N^2$, while each handle costs $1/N^2$.

</details>

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the chapters on matrix models and matrix quantum mechanics at large $N$.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the large-$N$ and random-surface chapters.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for saddle methods, large-$N$ expansions, and matrix-model background.

### Deeper references

- E. Brézin, C. Itzykson, G. Parisi, and J.-B. Zuber, “Planar Diagrams,” for the classic matrix-model planar expansion.
- M. L. Mehta, *Random Matrices*, for the mathematical random-matrix background.
- V. Pestun et al., *Localization Techniques in Quantum Field Theories*, for modern appearances of matrix models in supersymmetric localization.
- D. Gross and A. Migdal, and E. Brézin and V. Kazakov, for classic double-scaling limits in matrix models and two-dimensional gravity.

## Version history

- **2026-06-28:** Linked to the dedicated eigenvalue-density and double-scaling pages.
- **2026-06-27:** Added handoff link to saddle-points-at-large-N.
- **2026-06-27:** Added handoff links to planar diagrams and large-N factorization.
- **2026-06-27:** Initial polished page introducing eigenvalue-density saddles, resolvents, planar expansion, and double-scaling motivation.
