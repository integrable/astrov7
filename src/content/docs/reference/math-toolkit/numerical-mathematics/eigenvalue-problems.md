---
title: "Eigenvalue Problems"
description: "A QFT-oriented guide to finite and discretized eigenvalue problems, generalized eigenproblems, spectra of operators, Rayleigh quotients, variational principles, sparse solvers, spectral pollution, and convergence checks."
sidebar:
  label: "Eigenvalue Problems"
  order: 6
level: Graduate
status: "Polished draft"
source: "Linear algebra, numerical spectral theory, functional analysis, differential operators, lattice field theory, fluctuation determinants, transfer matrices, and quantum many-body numerics."
topics:
  - eigenvalue problems
  - spectral theory
  - generalized eigenproblems
  - Rayleigh quotient
  - sparse matrices
  - transfer matrices
  - fluctuation operators
  - spectral convergence
canonicalTopics:
  - eigenvalue-problems
  - generalized-eigenproblem
  - rayleigh-ritz-method
  - sparse-spectral-solvers
  - spectral-convergence
researchStatus:
  established:
    - "Finite-dimensional eigenvalue problems, generalized Hermitian eigenproblems, Rayleigh–Ritz variational principles, Krylov subspace methods, and spectral convergence tests are standard tools of numerical linear algebra and spectral theory."
  active:
    - "Large-scale spectra in lattice QFT, quantum many-body systems, conformal bootstrap computations, random-matrix universality, tensor networks, and non-Hermitian or real-time problems remain active computational and theoretical areas."
---

## Summary

An eigenvalue problem asks for nonzero vectors $v$ and numbers $\lambda$ such that

$$
Av=\lambda v.
$$

A generalized eigenvalue problem asks instead for

$$
Av=\lambda Bv.
$$

In QFT and statistical field theory, eigenvalue problems appear everywhere:

| QFT object | Eigenvalue problem |
|---|---|
| small fluctuations around a saddle | Hessian spectrum |
| free field on a background | differential operator spectrum |
| functional determinant | product or trace over eigenvalues |
| transfer matrix | energy spectrum and correlation lengths |
| lattice Dirac operator | fermion spectrum, zero modes, topology |
| conformal bootstrap numerics | positive-semidefinite and spectral constraints |
| random matrix model | eigenvalue density and level statistics |
| finite-volume Hamiltonian | spectrum of states |

The hard part is not writing $Av=\lambda v$. The hard part is knowing which operator $A$ represents the physics, which inner product defines adjoints, how boundary conditions enter, which part of the spectrum matters, and whether the computed eigenvalues converge to the continuum spectrum rather than to numerical ghosts.

## Prerequisites

You should know finite-dimensional linear algebra, inner products, Hermitian matrices, basic differential operators, and discretization ideas. Helpful nearby pages include [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Finite-Difference Methods](/math-toolkit/numerical-mathematics/finite-difference-methods/), and [Spectral Methods](/math-toolkit/numerical-mathematics/spectral-methods/).

This page focuses on numerical eigenvalue problems. It assumes the exact operator has already been mathematically specified.

## The basic eigenvalue problem

For a finite matrix $A\in\mathbb C^{N\times N}$, an eigenpair is

$$
Av=\lambda v,
\qquad
v\ne0.
$$

The characteristic equation is

$$
\det(A-\lambda I)=0.
$$

That formula is conceptually useful but numerically useless for large matrices. Serious algorithms do not expand determinants. They use orthogonal transformations, Krylov subspaces, factorizations, or variational principles.

If $A$ is Hermitian,

$$
A^\dagger=A,
$$

then all eigenvalues are real and eigenvectors associated with distinct eigenvalues are orthogonal. This is the finite-dimensional shadow of self-adjoint operators in quantum mechanics and QFT.

If $A$ is non-Hermitian, eigenvalues may be complex, left and right eigenvectors differ, and numerical stability becomes much more delicate.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A workflow from continuum operator to discretized generalized eigenproblem, computed spectrum, convergence, and physical interpretation.](/figures/math-toolkit/eigenvalue-problem-spectrum-flow.svg)

<figcaption>

A numerical spectrum is a chain of choices: operator, domain, boundary conditions, discretization, matrix problem, solver, convergence test, and physical interpretation. Most mistakes enter before the eigensolver ever starts.

</figcaption>
</figure>

## Operators, domains, and boundary conditions

A continuum eigenvalue problem has the form

$$
L\psi=\lambda\psi.
$$

But $L$ alone is not the full problem. One must also specify:

1. the function space,
2. the domain of $L$,
3. boundary conditions,
4. the inner product.

For example, on an interval $[0,L]$, the operator

$$
-\frac{d^2}{dx^2}
$$

has different spectra depending on boundary conditions.

Dirichlet boundary conditions,

$$
\psi(0)=\psi(L)=0,
$$

give

$$
\lambda_n=\left(\frac{n\pi}{L}\right)^2,
\qquad
n=1,2,\ldots.
$$

Periodic boundary conditions,

$$
\psi(x+L)=\psi(x),
$$

give

$$
\lambda_n=\left(\frac{2\pi n}{L}\right)^2,
\qquad
n\in\mathbb Z.
$$

The differential expression is the same. The operator is not.

This is why boundary conditions are not implementation details. They are part of the physics.

## Generalized eigenvalue problems

Many discretizations produce

$$
Av=\lambda Bv
$$

rather than $Av=\lambda v$.

This happens naturally in finite-element methods. The matrix $A$ is often a stiffness matrix, while $B$ is a mass or overlap matrix:

$$
A_{ij}=a(\varphi_i,\varphi_j),
\qquad
B_{ij}=\langle \varphi_i,\varphi_j\rangle.
$$

If $B$ is positive definite, one can transform the problem into an ordinary Hermitian problem. Write, for example,

$$
B=C^\dagger C.
$$

Then

$$
Av=\lambda Bv
$$

becomes

$$
C^{-\dagger}AC^{-1}w=\lambda w,
\qquad
w=Cv.
$$

In practice, one often solves the generalized problem directly.

The generalized form is a warning: eigenvectors are normalized with respect to $B$,

$$
v_i^\dagger Bv_j=\delta_{ij},
$$

not necessarily with respect to the Euclidean dot product.

## Rayleigh quotient

For a Hermitian matrix $A$, the Rayleigh quotient is

$$
R[v]=\frac{v^\dagger Av}{v^\dagger v}.
$$

Stationary points of $R[v]$ are eigenvectors. Varying $v^\dagger$ gives

$$
Av=R[v]v.
$$

For the generalized Hermitian problem

$$
Av=\lambda Bv,
\qquad
B>0,
$$

the Rayleigh quotient is

$$
R[v]=\frac{v^\dagger Av}{v^\dagger Bv}.
$$

Stationarity gives

$$
Av=R[v]Bv.
$$

This quotient is the numerical ancestor of many variational estimates in quantum mechanics and QFT. If $A$ is a Hamiltonian and $B=I$, then minimizing $R[v]$ over trial states gives an upper bound on the ground-state energy.

## Min–max principle

If $A$ is Hermitian with ordered eigenvalues

$$
\lambda_1\le\lambda_2\le\cdots\le\lambda_N,
$$

then

$$
\lambda_k
=\min_{\dim S=k}\;\max_{v\in S,\,v\ne0}R[v].
$$

This is the Courant–Fischer min–max principle.

It has three practical consequences.

First, low-lying eigenvalues are variationally stable. A good subspace gives good upper estimates.

Second, symmetry decomposition helps. If the operator commutes with a symmetry, diagonalize in irreducible sectors rather than mixing everything.

Third, bad trial spaces can miss physics. If a subspace cannot represent the true eigenfunction’s nodal, topological, or boundary behavior, the variational estimate converges slowly or to the wrong state.

## Discretizing differential operators

A differential eigenproblem

$$
L\psi=\lambda\psi
$$

becomes a matrix eigenproblem after choosing a basis or grid. For finite differences on a uniform grid,

$$
-\frac{d^2\psi}{dx^2}
\quad\longrightarrow\quad
\frac{-\psi_{i+1}+2\psi_i-\psi_{i-1}}{a^2}.
$$

For finite elements, one uses a weak form:

$$
a(\psi,\eta)=\lambda\langle \psi,\eta\rangle,
$$

leading to

$$
A_{ij}=a(\varphi_i,\varphi_j),
\qquad
B_{ij}=\langle\varphi_i,\varphi_j\rangle.
$$

For spectral methods, one expands

$$
\psi_N(x)=\sum_{n=0}^{N}c_n\varphi_n(x)
$$

and obtains a dense or structured matrix problem in coefficient space.

Every discretization changes the spectrum. The numerical question is whether the part of the spectrum you care about converges as the discretization is refined.

## Modified spectra on lattices

For a periodic one-dimensional lattice, the nearest-neighbor discretization of $-d^2/dx^2$ has eigenvectors

$$
\psi_j=e^{ikaj}
$$

and eigenvalues

$$
\lambda_a(k)=\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right).
$$

For small $ka$,

$$
\lambda_a(k)=k^2+O(a^2k^4).
$$

For momenta near the edge of the Brillouin zone, it differs sharply from $k^2$. The lattice operator has a bounded spectrum, while the continuum Laplacian is unbounded.

This is not a bug. It is exactly what an ultraviolet regulator does.

## Sparse versus dense eigenproblems

A matrix from local finite differences or finite elements is usually sparse. A matrix from a global spectral method may be dense but structured.

For small dense Hermitian matrices, direct algorithms compute all eigenpairs. For large sparse matrices, one usually wants only part of the spectrum: the lowest eigenvalues, eigenvalues near a target, or singular values. Iterative methods are then essential.

Common strategies include:

| Goal | Typical method |
|---|---|
| extremal eigenvalues of Hermitian $A$ | Lanczos or Krylov subspace methods |
| eigenvalues near a shift $\sigma$ | shift-invert methods |
| generalized Hermitian eigenproblem | Lanczos or LOBPCG with $B$-inner product |
| many low modes | block Krylov or subspace iteration |
| non-Hermitian eigenvalues | Arnoldi methods |
| singular values | Lanczos bidiagonalization or SVD methods |

The algorithm is only part of the story. Preconditioning often determines whether a large eigenvalue computation is feasible.

## Power iteration

The simplest eigenvalue algorithm is power iteration:

$$
w_{n+1}=Av_n,
\qquad
v_{n+1}=\frac{w_{n+1}}{\|w_{n+1}\|}.
$$

If $A$ has a dominant eigenvalue $|\lambda_1|>|\lambda_2|\ge\cdots$, and the initial vector has overlap with the dominant eigenvector, then $v_n$ converges to that eigenvector.

The convergence factor is roughly

$$
\left|\frac{\lambda_2}{\lambda_1}\right|.
$$

Power iteration is conceptually important but often too slow and too limited. It finds the largest magnitude eigenvalue, not necessarily the physically interesting low-energy spectrum.

Transfer-matrix calculations often use the same idea: repeated application of a positive transfer matrix projects onto the leading eigenstate.

## Inverse iteration and shift-invert

To find eigenvalues near $\sigma$, apply power iteration to

$$
(A-\sigma I)^{-1}.
$$

If $A v_i=\lambda_i v_i$, then

$$
(A-\sigma I)^{-1}v_i=\frac{1}{\lambda_i-\sigma}v_i.
$$

The eigenvalue closest to $\sigma$ becomes dominant in magnitude. This is shift-invert iteration.

The price is that each iteration requires solving a linear system

$$
(A-\sigma I)x=b.
$$

For large sparse operators, the quality of the linear solver and preconditioner dominates the cost.

In QFT, shift-invert methods are useful for interior eigenvalues, near-zero Dirac modes, bound states near thresholds, and fluctuation operators around nontrivial backgrounds.

## Lanczos and Krylov subspaces

For Hermitian $A$, the Lanczos algorithm constructs an orthonormal basis of the Krylov subspace

$$
\mathcal K_m(A,v)=\operatorname{span}\{v,Av,A^2v,\ldots,A^{m-1}v\}.
$$

The projection of $A$ onto this subspace is tridiagonal. Its eigenvalues, called Ritz values, approximate eigenvalues of $A$.

The physical picture is elegant: from one trial vector, repeatedly apply the operator to generate a variational subspace adapted to the spectrum. Then diagonalize $A$ inside that subspace.

Lanczos is powerful for low-energy spectra of large sparse Hamiltonians, lattice fluctuation operators, transfer matrices, and Dirac operators. But finite precision can spoil orthogonality, leading to duplicate or spurious Ritz values unless reorthogonalization or careful convergence checks are used.

## Residuals of eigenpairs

An approximate eigenpair $(\lambda,v)$ should be checked by its residual:

$$
r=Av-\lambda v.
$$

For a generalized problem,

$$
r=Av-\lambda Bv.
$$

A normalized residual such as

$$
\frac{\|r\|}{\|A\|\|v\|+|\lambda|\|v\|}
$$

or the analogous generalized norm gives a scale-aware measure of accuracy.

The residual tests whether $(\lambda,v)$ is an eigenpair of the **discrete** problem. It does not test whether the discrete problem approximates the continuum problem. For that one must refine the discretization.

## Spectral convergence

A numerical eigenvalue should be studied as the discretization parameter changes. For grid spacing $a$, one hopes for

$$
\lambda_a=\lambda+c_1a^p+O(a^{p+1})
$$

or, for spectral methods on smooth problems,

$$
|\lambda_N-\lambda|\le Ce^{-\alpha N}.
$$

But convergence may fail or slow down when:

| Problem | Effect |
|---|---|
| nonsmooth eigenfunctions | spectral convergence degrades |
| wrong boundary conditions | converges to wrong operator |
| singular potentials | low regularity and domain subtleties |
| gauge zero modes | spurious near-zero eigenvalues |
| finite-volume effects | shifted bound states or gaps |
| noncompact domain truncation | artificial boundary spectrum |
| non-self-adjoint discretization | unstable complex eigenvalues |

A continuum claim should be supported by refinement, finite-volume checks, and symmetry checks.

## Spectral pollution

Spectral pollution occurs when a discretization produces eigenvalues that converge to points outside the true spectrum or miss spectral gaps incorrectly.

This is especially dangerous for unbounded operators, indefinite problems, constrained systems, and variational truncations that do not preserve the correct operator domain.

In QFT language, spectral pollution can look like fake bound states, fake zero modes, wrong instability counts, or unphysical regulator modes.

The antidotes are problem-dependent: structure-preserving discretization, variational bounds, comparison with exact limits, residual estimates, independent discretizations, and careful treatment of constraints.

## Zero modes

A zero mode satisfies

$$
Av=0.
$$

Zero modes are common in QFT:

| Source | Zero mode |
|---|---|
| translation symmetry of a soliton | derivative of the solution |
| global symmetry breaking | Goldstone direction |
| gauge symmetry | pure gauge direction |
| moduli space | tangent to family of solutions |
| index theorem | chiral Dirac zero mode |
| critical point | diverging correlation length, vanishing mass gap |

Numerically, zero modes are both important and annoying. They make determinants vanish, linear solves singular, and Newton steps nonunique. One must separate physical zero modes from numerical near-zero artifacts.

A good check is to compare the computed zero vector to the expected symmetry derivative. For a soliton $\phi_0(x-X)$, translation invariance predicts

$$
v_0(x)=\frac{d\phi_0(x-X)}{dX}=-\partial_x\phi_0(x-X).
$$

## Negative modes

For a fluctuation operator around a stationary point, negative eigenvalues indicate instability directions. If

$$
S[u_*+\eta]
=S[u_*]+\frac12\langle \eta,L\eta\rangle+O(\eta^3),
$$

then a negative eigenvalue of $L$ lowers the action to quadratic order.

Examples:

| Configuration | Expected negative modes |
|---|---|
| stable vacuum | none |
| metastable false vacuum | none locally |
| bounce saddle | usually one negative mode |
| sphaleron | one or more unstable directions |
| gauge orbit | zero modes, not negative modes after proper gauge fixing |

Counting negative modes is part of interpreting a saddle. A nonlinear solver that finds $F(u)=0$ has not finished the physics.

## Functional determinants

A formal determinant of an operator $L$ is a product over eigenvalues:

$$
\det L=\prod_n\lambda_n.
$$

Numerically, after discretization one may compute

$$
\log\det A=\sum_n\log\lambda_n.
$$

But in QFT this quantity is ultraviolet divergent in the continuum limit and needs regularization and renormalization. Low eigenvalues may be computed directly; high eigenvalues often require asymptotic subtraction, heat-kernel methods, zeta regularization, or continuum counterterms.

Also, zero modes must be omitted or treated separately:

$$
\det{}' L=\prod_{\lambda_n\ne0}\lambda_n.
$$

The prime means the determinant is over nonzero modes. The missing zero-mode integrals become collective-coordinate factors.

## Transfer matrices and correlation lengths

A transfer matrix $T$ evolves a statistical system by one Euclidean time step. If its eigenvalues are

$$
\Lambda_0>\Lambda_1\ge\Lambda_2\ge\cdots,
$$

then the leading correlation length is often

$$
\xi^{-1}=\log\frac{\Lambda_0}{\Lambda_1}.
$$

Equivalently, if

$$
T=e^{-aH},
$$

then

$$
E_n-E_0=-\frac1a\log\frac{\Lambda_n}{\Lambda_0}.
$$

Thus transfer-matrix eigenvalues encode the finite-volume energy spectrum.

This is one of the cleanest bridges between statistical mechanics and Euclidean QFT.

## Non-Hermitian and sign-problem settings

Some physically important eigenvalue problems are not Hermitian. Real-time evolution generators, non-Hermitian effective Hamiltonians, Fokker–Planck operators, complex Langevin linearizations, and transfer matrices with sign problems can have complex spectra.

For a non-Hermitian matrix,

$$
Av_R=\lambda v_R,
\qquad
v_L^\dagger A=\lambda v_L^\dagger.
$$

Left and right eigenvectors are different. Orthogonality is replaced by biorthogonality,

$$
v_{L,i}^\dagger v_{R,j}=\delta_{ij},
$$

when the matrix is diagonalizable and properly normalized.

Non-Hermitian spectra can be extremely sensitive to perturbations. Pseudospectra, not just eigenvalues, may control stability.

## Practical workflow

A reliable eigenvalue calculation usually follows this chain.

1. Define the continuum operator, domain, and inner product.
2. Choose boundary conditions that match the physics.
3. Pick a discretization that preserves key structures.
4. Identify symmetries and block-diagonalize when possible.
5. Choose a solver appropriate to sparse, dense, Hermitian, generalized, or non-Hermitian structure.
6. Check residuals of computed eigenpairs.
7. Refine the discretization and volume.
8. Compare with exact limits, sum rules, trace identities, or known zero modes.
9. Interpret the spectrum physically.

The eigensolver is item 5. The calculation is all nine items.

## Common pitfalls

### Diagonalizing the wrong operator

A differential expression without a domain is not an operator. Boundary conditions, inner product, and constraints are part of the eigenvalue problem.

### Trusting all computed eigenvalues equally

Low modes often converge before high modes. Near the cutoff, lattice eigenvalues describe regulator physics, not continuum physics.

### Ignoring generalized normalization

For $Av=\lambda Bv$, normalize with $B$:

$$
v_i^\dagger Bv_j=\delta_{ij}.
$$

Using the Euclidean dot product can produce wrong overlaps and matrix elements.

### Mistaking gauge modes for physical particles

Gauge zero modes and constraint modes must be removed, fixed, or projected. Otherwise the spectrum includes unphysical directions.

### Forgetting finite-volume effects

A small gap in finite volume may not be a mass gap in infinite volume. Study how eigenvalues scale with $L$ as well as with lattice spacing $a$.

## Exercises

### Exercise 1: Lattice Laplacian spectrum

On a periodic lattice with $N$ sites and spacing $a$, define

$$
(-\Delta_a\psi)_j=
\frac{-\psi_{j+1}+2\psi_j-\psi_{j-1}}{a^2}.
$$

Show that $\psi_j=e^{ikaj}$ is an eigenvector and find the eigenvalue.

<details><summary><strong>Solution</strong></summary>

Substitute:

$$
\psi_{j+1}=e^{ika(j+1)}=e^{ika}e^{ikaj},
$$

and

$$
\psi_{j-1}=e^{-ika}e^{ikaj}.
$$

Then

$$
(-\Delta_a\psi)_j
=\frac{-e^{ika}+2-e^{-ika}}{a^2}e^{ikaj}.
$$

Using

$$
2-e^{ika}-e^{-ika}=2-2\cos(ka)=4\sin^2\!\left(\frac{ka}{2}\right),
$$

we get

$$
\lambda_a(k)=\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right).
$$

</details>

### Exercise 2: Stationarity of the Rayleigh quotient

Let $A=A^\dagger$ and

$$
R[v]=\frac{v^\dagger Av}{v^\dagger v}.
$$

Show that a stationary point satisfies $Av=R[v]v$.

<details><summary><strong>Solution</strong></summary>

Vary $v^\dagger$ while holding $v$ fixed. Let

$$
N=v^\dagger Av,
\qquad
D=v^\dagger v.
$$

Then

$$
\delta R=\frac{(\delta v^\dagger)Av}{D}
-\frac{N}{D^2}(\delta v^\dagger)v.
$$

Since $R=N/D$,

$$
\delta R=\frac{(\delta v^\dagger)(Av-Rv)}{v^\dagger v}.
$$

For this to vanish for arbitrary $\delta v^\dagger$,

$$
Av=Rv.
$$

Thus stationary vectors of the Rayleigh quotient are eigenvectors.

</details>

### Exercise 3: Generalized Rayleigh quotient

For $A=A^\dagger$ and $B=B^\dagger>0$, show that stationarity of

$$
R[v]=\frac{v^\dagger Av}{v^\dagger Bv}
$$

gives

$$
Av=R[v]Bv.
$$

<details><summary><strong>Solution</strong></summary>

Set

$$
N=v^\dagger Av,
\qquad
D=v^\dagger Bv.
$$

Vary $v^\dagger$:

$$
\delta R=\frac{(\delta v^\dagger)Av}{D}
-\frac{N}{D^2}(\delta v^\dagger)Bv.
$$

Since $R=N/D$,

$$
\delta R=\frac{(\delta v^\dagger)(Av-RBv)}{v^\dagger Bv}.
$$

For arbitrary $\delta v^\dagger$ this implies

$$
Av=RBv.
$$

Therefore stationary points solve the generalized eigenvalue problem.

</details>

### Exercise 4: Transfer matrix gap

Suppose $T=e^{-aH}$ has eigenvalues $\Lambda_n=e^{-aE_n}$ with $E_0<E_1$. Show that

$$
E_1-E_0=-\frac1a\log\frac{\Lambda_1}{\Lambda_0}.
$$

<details><summary><strong>Solution</strong></summary>

We have

$$
\frac{\Lambda_1}{\Lambda_0}
=\frac{e^{-aE_1}}{e^{-aE_0}}
=e^{-a(E_1-E_0)}.
$$

Taking the logarithm gives

$$
\log\frac{\Lambda_1}{\Lambda_0}
=-a(E_1-E_0).
$$

Thus

$$
E_1-E_0=-\frac1a\log\frac{\Lambda_1}{\Lambda_0}.
$$

</details>

## References

- Trefethen and Bau, *Numerical Linear Algebra*.
- Golub and Van Loan, *Matrix Computations*.
- Saad, *Numerical Methods for Large Eigenvalue Problems*.
- Parlett, *The Symmetric Eigenvalue Problem*.
- Reed and Simon, *Methods of Modern Mathematical Physics, Vol. IV: Analysis of Operators*.
- Simon, *Trace Ideals and Their Applications*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Altland and Simons, *Condensed Matter Field Theory*.

## Version history

- **2026-06-27:** First polished draft. Introduces ordinary and generalized eigenproblems, domains and boundary conditions, Rayleigh quotients, min–max principles, discretized spectra, sparse methods, shift-invert ideas, Lanczos methods, residuals, spectral convergence, zero modes, negative modes, transfer matrices, and exercises.
