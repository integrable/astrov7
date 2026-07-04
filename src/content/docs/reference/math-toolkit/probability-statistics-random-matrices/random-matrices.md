---
title: "Random Matrices"
description: "A QFT-oriented guide to random matrix ensembles, eigenvalue densities, resolvents, the Wigner semicircle, eigenvalue gases, universality, Dyson classes, matrix models, and spectral statistics."
sidebar:
  label: "Random Matrices"
  order: 7
level: Graduate
status: "Polished draft"
source: "Random-matrix theory, spectral theory, large-N matrix models, statistical mechanics, quantum chaos, disordered systems, and QFT applications."
topics:
  - random matrices
  - spectral density
  - Wigner semicircle
  - eigenvalue gas
  - resolvent
  - Dyson ensembles
  - large N
  - matrix models
  - quantum chaos
canonicalTopics:
  - random-matrix-ensemble
  - eigenvalue-density
  - wigner-semicircle
  - resolvent
  - dyson-index
  - matrix-model
researchStatus:
  established:
    - "Classical random-matrix ensembles, eigenvalue repulsion, the Wigner semicircle law, resolvents, Dyson symmetry classes, and large-N saddle methods are standard tools in mathematical physics."
    - "In QFT, random matrices appear in matrix models, large-N limits, disordered systems, spectral statistics, quantum chaos, Chern–Simons/topological strings, and low-energy Dirac spectra."
  active:
    - "Modern research uses random matrices in quantum chaos, JT gravity, tensor models, non-Hermitian systems, bootstrap numerics, localization matrix models, and spectral statistics of many-body quantum systems."
---

## Summary

Random-matrix theory studies probability distributions on matrices and the statistics of their eigenvalues. The simplest object is a random Hermitian matrix $H$ with measure

$$
d\mathbb P(H)\propto e^{-\frac{N}{2}\operatorname{Tr}H^2}\,dH.
$$

Diagonalizing $H=U\Lambda U^\dagger$ produces eigenvalues $\lambda_i$ with a striking joint density:

$$
d\mathbb P(\lambda_1,\ldots,\lambda_N)
\propto
\prod_{i<j}|\lambda_i-\lambda_j|^\beta
\prod_i e^{-N V(\lambda_i)}d\lambda_i.
$$

The factor

$$
\prod_{i<j}|\lambda_i-\lambda_j|^\beta
$$

is eigenvalue repulsion. It is the source of much of random-matrix universality. In large $N$ language, the eigenvalues behave like a Coulomb gas: they repel one another while being confined by the potential $V$.

The QFT reason to care is simple: many field-theoretic problems reduce to spectral statistics or matrix integrals. Random matrices appear in large-$N$ gauge theory, matrix models, disordered systems, quantum chaos, localization, Dirac spectra, and two-dimensional gravity. They are not a trick for guessing spectra; they are a universal effective theory for spectral correlations when only symmetries and coarse constraints matter.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A flowchart from matrix ensemble to eigenvalues, Vandermonde repulsion, resolvent, large-N density, and QFT applications.](/figures/math-toolkit/random-matrix-eigenvalue-gas.svg)

<figcaption>

After diagonalization, invariant matrix measures become interacting eigenvalue gases. The large-$N$ saddle determines the spectral density $\rho(\lambda)$; the resolvent packages this density and is the natural analog of a Green function in the spectral plane.

</figcaption>
</figure>

## Prerequisites

You should know [Probability Measures](/math-toolkit/probability-statistics-random-matrices/probability-measures/), [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/), [Trace-Class and Hilbert–Schmidt Operators](/math-toolkit/functional-analysis-spectral-theory/trace-class-and-hilbert-schmidt-operators/), and the large-$N$ intuition from [Saddle Points](/math-toolkit/complex-analysis/saddle-points/) or [Steepest Descent](/math-toolkit/asymptotics-regularization-resurgence/steepest-descent/). The page uses Hermitian matrices first; non-Hermitian ensembles are mentioned only briefly.

## Matrix ensembles

A random matrix ensemble is a probability measure on a space of matrices. The classical invariant ensembles are built from real symmetric, complex Hermitian, or quaternionic self-dual matrices. They have densities of the schematic form

$$
d\mathbb P(H)=\frac{1}{Z_N}e^{-N\operatorname{Tr}V(H)}dH.
$$

The potential $V$ confines the eigenvalues. The factor of $N$ is chosen so that the large-$N$ eigenvalue density has a nontrivial limit.

The most important symmetry is invariance under conjugation:

$$
H\mapsto UHU^{-1}.
$$

This means the probability distribution depends only on eigenvalues. For Hermitian matrices, $U$ is unitary; for real symmetric matrices, it is orthogonal.

The Dyson index $\beta$ records the underlying number system:

| Ensemble | Matrix type | Symmetry group | $\beta$ |
|---|---|---|---|
| GOE | real symmetric | orthogonal | $1$ |
| GUE | complex Hermitian | unitary | $2$ |
| GSE | quaternionic self-dual | symplectic | $4$ |

These are not random letters from the gods of notation. They encode antiunitary symmetry. In quantum systems, the correct ensemble depends on time-reversal symmetry, spin structure, and conserved charges.

## Diagonalization and the Vandermonde determinant

For a Hermitian matrix,

$$
H=U\Lambda U^\dagger,
\qquad
\Lambda=\operatorname{diag}(\lambda_1,\ldots,\lambda_N).
$$

The flat measure decomposes as

$$
dH=C\,\prod_{i<j}|\lambda_i-\lambda_j|^2
\prod_i d\lambda_i\,d\mu(U),
$$

where $d\mu(U)$ is Haar measure modulo phases and permutations. The factor

$$
\Delta(\lambda)=\prod_{i<j}(\lambda_i-\lambda_j)
$$

is the Vandermonde determinant.

For the unitary ensemble, the eigenvalue density becomes

$$
d\mathbb P(\lambda)
=\frac{1}{Z_N}
\prod_{i<j}|\lambda_i-\lambda_j|^2
\prod_i e^{-NV(\lambda_i)}d\lambda_i.
$$

This is equivalent to a Boltzmann weight

$$
e^{-S_{\rm eig}(\lambda)},
$$

with

$$
S_{\rm eig}(\lambda)
=N\sum_i V(\lambda_i)-2\sum_{i<j}\log|\lambda_i-\lambda_j|.
$$

The logarithm is a two-dimensional Coulomb repulsion between eigenvalues.

## Empirical spectral density

The empirical eigenvalue density is

$$
\rho_N(\lambda)=\frac1N\sum_{i=1}^N\delta(\lambda-\lambda_i).
$$

At large $N$, many invariant ensembles have a deterministic limiting density

$$
\rho_N(\lambda)\to\rho(\lambda).
$$

The normalization is

$$
\int d\lambda\,\rho(\lambda)=1.
$$

Expectation values of normalized traces become moments of the density:

$$
\frac1N\operatorname{Tr}H^k
=\int d\lambda\,\rho_N(\lambda)\lambda^k
\longrightarrow
\int d\lambda\,\rho(\lambda)\lambda^k.
$$

In QFT terms, $\rho(\lambda)$ is an order parameter for the large-$N$ saddle of the matrix integral.

## Resolvent

The resolvent is

$$
G(z)=\frac1N\left\langle\operatorname{Tr}\frac{1}{z-H}\right\rangle.
$$

For large $N$,

$$
G(z)=\int d\lambda\,\frac{\rho(\lambda)}{z-\lambda}.
$$

This is a Green function in the complex spectral plane. The density is recovered from its discontinuity across the cut:

$$
\rho(\lambda)
=-\frac{1}{\pi}\operatorname{Im}G(\lambda+i0).
$$

Equivalently,

$$
\rho(\lambda)=\frac{1}{2\pi i}
\left(G(\lambda-i0)-G(\lambda+i0)\right).
$$

The analogy with QFT propagators is not superficial. Branch cuts encode continua of eigenvalues, and isolated poles encode separated eigenvalues or finite-rank effects.

## Gaussian unitary ensemble and the semicircle

For the Gaussian unitary ensemble, take

$$
V(\lambda)=\frac12\lambda^2.
$$

At large $N$, the eigenvalue density minimizes

$$
S[\rho]
=\int d\lambda\,\rho(\lambda)\frac{\lambda^2}{2}
-
\int d\lambda d\mu\,\rho(\lambda)\rho(\mu)\log|\lambda-\mu|,
$$

subject to $\int\rho=1$.

The saddle equation on the support is

$$
\frac{\lambda^2}{2}-2\int d\mu\,\rho(\mu)\log|\lambda-\mu|=\text{constant}.
$$

Differentiating gives the singular integral equation

$$
\lambda=2\,\operatorname{PV}\int d\mu\,\frac{\rho(\mu)}{\lambda-\mu}.
$$

The solution is Wigner’s semicircle law:

$$
\rho(\lambda)=\frac{1}{2\pi}\sqrt{4-\lambda^2},
\qquad
-2\le\lambda\le2.
$$

The corresponding resolvent is

$$
G(z)=\frac12\left(z-\sqrt{z^2-4}\right),
$$

where the branch is chosen so that

$$
G(z)\sim\frac1z
$$

as $z\to\infty$.

## Eigenvalue repulsion

Because the joint density contains

$$
|\lambda_i-\lambda_j|^\beta,
$$

two nearby eigenvalues are suppressed. Locally, the probability of a small spacing $s$ behaves like

$$
P(s)\sim s^\beta
$$

as $s\to0$.

This is a sharp diagnostic. Independent random levels have no level repulsion and typically obey Poisson statistics. Chaotic quantum systems with appropriate symmetries often show Wigner–Dyson statistics. Integrable systems often show Poisson-like statistics after unfolding. As usual, this is a universal expectation, not a theorem about every Hamiltonian one writes down.

## Unfolding

Raw eigenvalues have a nonuniform mean density. To study local universal correlations, one unfolds the spectrum by mapping eigenvalues to variables with unit mean spacing.

If

$$
\bar N(\lambda)=N\int_{-\infty}^{\lambda}d\mu\,\rho(\mu)
$$

is the smooth counting function, define

$$
\xi_i=\bar N(\lambda_i).
$$

The unfolded spacings are

$$
s_i=\xi_{i+1}-\xi_i.
$$

Only after unfolding does it make sense to compare local spacing statistics across different systems. Forgetting this is one of the fastest ways to produce fake random-matrix evidence.

## Universality

Random-matrix universality means that local spectral correlations often depend only on symmetry class, not on microscopic details of the potential $V$.

For unitary ensembles, the bulk local correlations are governed by the sine kernel:

$$
K_{\rm sine}(x,y)=\frac{\sin\pi(x-y)}{\pi(x-y)}.
$$

At spectral edges, different universal kernels appear, such as the Airy kernel. Near hard edges, Bessel kernels appear.

The field-theory moral is familiar: microscopic details flow to universal long-distance or low-energy data. In random matrices, the “long-distance” variable is often not spacetime but position in the unfolded spectrum.

## Matrix models as zero-dimensional QFTs

A matrix integral

$$
Z=\int dM\,e^{-N\operatorname{Tr}V(M)}
$$

is a zero-dimensional QFT with matrix-valued fields. Observables are traces:

$$
\left\langle\frac1N\operatorname{Tr}M^k\right\rangle.
$$

The large-$N$ expansion has the form

$$
\log Z=\sum_{g=0}^{\infty}N^{2-2g}F_g.
$$

This topological expansion organizes Feynman diagrams by genus. Double-line notation turns matrix indices into discretized surfaces. This is the algebraic seed of the relation among matrix models, two-dimensional gravity, topological strings, and large-$N$ gauge theory.

## Loop equations

The simplest matrix model Schwinger–Dyson equations are called loop equations. They follow from the fact that the integral of a total derivative vanishes:

$$
0=\int dM\,\frac{\partial}{\partial M_{ij}}
\left[(M^k)_{ij}e^{-N\operatorname{Tr}V(M)}\right].
$$

These identities generate recursive constraints on trace correlators. In terms of the resolvent, the large-$N$ loop equation often becomes an algebraic equation for $G(z)$.

For the Gaussian model, it is

$$
G(z)^2-zG(z)+1=0,
$$

whose physical solution is

$$
G(z)=\frac12\left(z-\sqrt{z^2-4}\right).
$$

The square root is the spectral cut. It is the matrix-model version of a branch cut in a Green function.

## Random matrices and quantum chaos

Random matrices model universal spectral correlations of quantum systems whose classical or many-body dynamics is chaotic. The basic idea is not that the Hamiltonian is literally random. It is that after fixing symmetries, microscopic details become irrelevant for local spectral statistics.

Important diagnostics include:

| Quantity | What it probes |
|---|---|
| nearest-neighbor spacing | level repulsion versus Poisson statistics |
| number variance | rigidity of spectra over windows |
| spectral form factor | correlations across time scales |
| ramp and plateau | random-matrix behavior in chaotic spectra |
| Thouless time | onset of universal spectral behavior |

In QFT and quantum gravity, these diagnostics are used with care. One must specify the sector, conserved charges, unfolding procedure, finite-volume regulator, and symmetry class.

## Dirac spectra and chiral ensembles

Gauge theories also use random matrices through the spectrum of the Dirac operator. Chiral symmetry implies a block structure near zero eigenvalue, leading to chiral random-matrix ensembles.

The Banks–Casher relation connects the density of small Dirac eigenvalues to the chiral condensate:

$$
\langle\bar\psi\psi\rangle
=-\pi\rho_D(0)
$$

up to conventional normalization and volume limits. Here $\rho_D(0)$ is the spectral density of the Dirac operator near zero.

The conceptual point is profound: spontaneous chiral symmetry breaking can be read from spectral accumulation near the origin.

## Non-Hermitian warning

Many modern problems involve non-Hermitian matrices: open systems, real-time evolution with damping, sign-problem deformations, and finite-density Dirac operators. Then eigenvalues live in the complex plane, and the Hermitian one-cut story no longer applies directly.

For non-Hermitian ensembles, one studies two-dimensional eigenvalue densities such as the circular law, pseudospectra, singular values, or biorthogonal eigenvectors. The resolvent must be modified because holomorphic functions alone cannot detect a two-dimensional density without additional structure.

This page focuses on Hermitian ensembles because they are the basic entry point and the most common source of QFT matrix-model intuition.

## Common pitfalls

### Matching the wrong symmetry class

GOE, GUE, and GSE correspond to different antiunitary symmetries. Picking one because it “looks random” is not physics. Identify time-reversal properties, spin, particle-hole symmetries, and conserved sectors.

### Confusing global density with local statistics

The semicircle is a global density. Level repulsion and sine-kernel correlations are local unfolded statistics. These are related but distinct questions.

### Forgetting the Vandermonde

The eigenvalues of an invariant matrix ensemble are not independent. The Jacobian of diagonalization produces repulsion. Dropping the Vandermonde destroys the main phenomenon.

### Treating modular-looking curves as proof of chaos

A spacing histogram is not enough. One needs unfolding, symmetry resolution, finite-size checks, and comparison to integrable or localized alternatives.

### Assuming random matrices replace dynamics

Random-matrix theory gives universal effective descriptions of spectra. It does not derive the microscopic Hamiltonian or identify the relevant physical degrees of freedom.

## Exercises

### Exercise 1: Vandermonde for two Hermitian eigenvalues

For a $2\times2$ Hermitian matrix, explain why eigenvalue coincidence has measure zero and why the joint eigenvalue density contains a factor proportional to $(\lambda_1-\lambda_2)^2$ in the unitary case.

<details><summary><strong>Solution</strong></summary>

A Hermitian matrix can be diagonalized as

$$
H=U\operatorname{diag}(\lambda_1,\lambda_2)U^\dagger.
$$

The flat metric on matrix space separates into eigenvalue variations and angular variations. Off-diagonal angular variations are multiplied by differences of eigenvalues. For $2\times2$, this produces a Jacobian factor

$$
|\lambda_1-\lambda_2|^2
$$

for complex Hermitian matrices. Thus the measure vanishes when $\lambda_1=\lambda_2$. Eigenvalue coincidence has codimension three in the space of Hermitian $2\times2$ matrices, so it has measure zero.

</details>

### Exercise 2: Normalization of the semicircle

Show that

$$
\rho(\lambda)=\frac{1}{2\pi}\sqrt{4-\lambda^2},
\qquad
-2\le\lambda\le2,
$$

is normalized to one.

<details><summary><strong>Solution</strong></summary>

Use the area of a semicircle of radius $2$:

$$
\int_{-2}^2 d\lambda\,\sqrt{4-\lambda^2}
=\frac12\pi(2)^2=2\pi.
$$

Therefore

$$
\int_{-2}^2 d\lambda\,\rho(\lambda)
=\frac{1}{2\pi}(2\pi)=1.
$$

</details>

### Exercise 3: Large-z expansion of the resolvent

Let

$$
G(z)=\int d\lambda\,\frac{\rho(\lambda)}{z-\lambda}.
$$

Show that its large-$z$ expansion generates moments of $\rho$.

<details><summary><strong>Solution</strong></summary>

For large $z$,

$$
\frac{1}{z-\lambda}
=\frac1z\frac{1}{1-\lambda/z}
=\sum_{n=0}^{\infty}\frac{\lambda^n}{z^{n+1}}.
$$

Thus

$$
G(z)=\sum_{n=0}^{\infty}\frac{1}{z^{n+1}}
\int d\lambda\,\rho(\lambda)\lambda^n.
$$

The coefficient of $z^{-n-1}$ is the $n$th moment of the spectral density.

</details>

### Exercise 4: Gaussian loop equation

Assume the large-$N$ Gaussian resolvent satisfies

$$
G(z)^2-zG(z)+1=0.
$$

Solve for $G(z)$ and choose the branch with $G(z)\sim1/z$ as $z\to\infty$.

<details><summary><strong>Solution</strong></summary>

The quadratic equation gives

$$
G(z)=\frac12\left(z\pm\sqrt{z^2-4}\right).
$$

For large $z$,

$$
\sqrt{z^2-4}=z\sqrt{1-4/z^2}
=z-\frac{2}{z}+O(z^{-3}).
$$

The minus branch gives

$$
G(z)=\frac12\left(z-z+\frac{2}{z}+O(z^{-3})\right)
=\frac1z+O(z^{-3}).
$$

Thus

$$
G(z)=\frac12\left(z-\sqrt{z^2-4}\right).
$$

</details>

## References

- Mehta, *Random Matrices*.
- Forrester, *Log-Gases and Random Matrices*.
- Anderson, Guionnet, and Zeitouni, *An Introduction to Random Matrices*.
- Eynard, *Counting Surfaces*.
- Marino, *Les Houches Lectures on Matrix Models and Topological Strings*.
- Altland and Simons, *Condensed Matter Field Theory*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Verbaarschot and Wettig, “Random matrix theory and chiral symmetry in QCD.”

## Version history

- **2026-06-27:** First polished draft. Introduces invariant ensembles, Vandermonde repulsion, eigenvalue densities, resolvents, Wigner semicircle, universality, matrix models, loop equations, quantum chaos, and Dirac spectral applications.
