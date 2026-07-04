---
title: "Compact Operators"
description: "Explains compact operators, finite-rank approximations, compact spectra, compact resolvents, Fredholm alternatives, trace ideals, and why compactness turns some infinite-dimensional problems into matrix-like spectral problems."
sidebar:
  label: "Compact Operators"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard functional-analysis and mathematical-physics references, including Reed–Simon, Teschl, Hall, Moretti, Conway, Kato, Yosida, and QFT treatments of mode sums, compact resolvents, heat kernels, and Fredholm determinants."
topics:
  - compact operators
  - finite-rank operators
  - compact spectrum
  - compact resolvent
  - Fredholm alternative
  - Hilbert-Schmidt operators
  - trace-class operators
  - singular values
  - spectral theorem
  - elliptic operators
canonicalTopics:
  - compact-operator
  - finite-rank-operator
  - compact-spectrum
  - compact-resolvent
  - fredholm-alternative
  - hilbert-schmidt-operator
  - trace-class-operator
  - singular-value
  - spectral-theorem
  - elliptic-operator
researchStatus:
  established:
    - "Compact operators are the standard infinite-dimensional analog of matrix-like operators with discrete nonzero spectral data accumulating only at zero."
  active:
    - "In QFT, compactness is common after finite-volume, Euclidean, elliptic, or regulated reductions, but infinite-volume Lorentzian theories usually have continuous spectra and require additional spectral-density methods."
---

## Summary

Compact operators are the operators that make infinite-dimensional Hilbert spaces behave, for a moment, like very large matrices. A compact operator $K:\mathcal H\to\mathcal K$ sends bounded sets to relatively compact sets: every bounded sequence $\psi_n$ has a subsequence such that $K\psi_{n_j}$ converges.

That definition sounds topological, but its spectral consequence is wonderfully concrete. If $K$ is compact and self-adjoint, then its nonzero spectrum consists of isolated eigenvalues of finite multiplicity, and the only possible accumulation point is $0$.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing a compact operator mapping a bounded set to a relatively compact image, finite-rank approximants, compact self-adjoint spectra with eigenvalues accumulating only at zero, and a shrunken unit ball image.](/figures/math-toolkit/compact-operator-spectrum-flow.svg)

<figcaption>

A compact operator maps bounded sets to relatively compact images. Finite-rank operators are the basic model, and many compact operators can be approximated by finite-rank ones in useful settings. For compact self-adjoint operators, nonzero eigenvalues are discrete with finite multiplicity and can accumulate only at $0$.

</figcaption>
</figure>

Compactness is why many finite-volume or elliptic QFT calculations reduce to countable mode sums. It is also why inverse Laplacians on compact spaces, integral kernels with enough square integrability, and resolvents of elliptic operators have discrete spectral data.

But compactness is not automatic. The identity operator on an infinite-dimensional Hilbert space is not compact. Infinite-volume Hamiltonians and momenta usually have continuous spectrum. So compact operators are not “all nice operators”; they are a special class that marks when the matrix intuition is partly justified.

## Prerequisites

You should know Hilbert spaces, bounded operators, adjoints, self-adjointness, and the spectral theorem from [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), and [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/). For kernel examples, see [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

## Core idea

In finite dimensions, closed bounded sets are compact. Therefore every linear map between finite-dimensional normed spaces maps bounded sets to relatively compact sets. In infinite dimensions, this fails dramatically. The unit ball in an infinite-dimensional Hilbert space is bounded but not compact in norm.

A bounded linear operator

$$
K:\mathcal H\to\mathcal K
$$

is **compact** if the image of every bounded set has compact closure. Equivalently, whenever $\psi_n$ is a bounded sequence in $\mathcal H$, there is a subsequence $\psi_{n_j}$ such that

$$
K\psi_{n_j}
$$

converges in $\mathcal K$.

The sequence formulation is often the most useful one. Compactness says that although the original sequence may wander around infinitely many directions, its image under $K$ has a convergent subsequence. The operator has crushed enough high-dimensional freedom to restore compactness.

A good mental model is an operator whose singular values shrink to zero. In a friendly basis, a compact operator behaves like an infinite matrix whose axes get shorter and shorter:

$$
K\sim \operatorname{diag}(s_1,s_2,s_3,\dots),
\qquad
s_n\to0.
$$

This formula is not the definition, and it is not available for every compact operator in every naive way. But it captures the geometric picture.

## Finite-rank operators

The simplest compact operators are finite-rank operators. An operator $F:\mathcal H\to\mathcal K$ has finite rank if

$$
\dim\operatorname{ran}F<\infty.
$$

If $B\subseteq\mathcal H$ is bounded, then $F(B)$ is a bounded subset of a finite-dimensional subspace of $\mathcal K$. Closed bounded sets are compact in finite dimensions, so $F(B)$ has compact closure. Therefore $F$ is compact.

A typical finite-rank operator has the form

$$
F\psi=\sum_{j=1}^N \langle u_j,\psi\rangle v_j,
$$

where $u_j\in\mathcal H$ and $v_j\in\mathcal K$.

In bra-ket notation,

$$
F=\sum_{j=1}^N |v_j\rangle\langle u_j|.
$$

This is one reason finite-rank projections and finite-volume truncations are so useful. They give compact approximations to more complicated operators, and their spectra are ordinary matrix spectra plus an enormous kernel.

Finite-rank operators are compact, but not every compact operator is finite-rank. Compact operators can have infinitely many nonzero singular values or eigenvalues, as long as these tend to zero.

## Norm limits and the compact ideal

If $K_n$ are compact operators and

$$
\|K_n-K\|\to0,
$$

then $K$ is compact. Thus compact operators form a norm-closed subspace of the bounded operators.

When $\mathcal H=\mathcal K$, compact operators form a two-sided ideal in $\mathcal B(\mathcal H)$. If $K$ is compact and $A,B$ are bounded, then

$$
AKB
$$

is compact.

This ideal property is powerful. Compactness is stable under bounded operators on either side. For instance, if a Green operator is compact, composing it with bounded multiplication or projection operators often remains compact.

Not every compact operator is a norm limit of finite-rank operators on arbitrary Banach spaces. On Hilbert spaces, however, compact operators are norm limits of finite-rank operators. This is one way Hilbert spaces remain friendlier than general Banach spaces.

## The identity is not compact

The identity operator on an infinite-dimensional Hilbert space is the canonical nonexample.

Let $\{e_n\}_{n=1}^\infty$ be an orthonormal sequence. Then $\|e_n\|=1$, so the sequence is bounded. But

$$
\|e_n-e_m\|^2=2
$$

for $n\ne m$. Hence no subsequence is Cauchy, and no subsequence converges.

If the identity $\mathbf 1$ were compact, then $\mathbf 1 e_n=e_n$ would have a convergent subsequence. It does not. Therefore

$$
\mathbf 1
$$

is not compact on an infinite-dimensional Hilbert space.

This is the quickest way to remember that compactness is genuinely infinite-dimensional information. In finite dimensions every operator is compact; in infinite dimensions even the most innocent operator is not.

## Compact self-adjoint operators

The spectral theorem for compact self-adjoint operators is much closer to finite-dimensional diagonalization than the general spectral theorem.

Let $K=K^*$ be compact on a Hilbert space $\mathcal H$. Then there is an orthonormal set of eigenvectors $e_n$ with real nonzero eigenvalues $\lambda_n$ such that

$$
Ke_n=\lambda_n e_n,
$$

and

$$
\lambda_n\to0
$$

if there are infinitely many nonzero eigenvalues. The nonzero eigenvalues have finite multiplicity and are isolated in the spectrum.

On the closure of the range of $K$, one has the expansion

$$
K\psi=\sum_n \lambda_n\langle e_n,\psi\rangle e_n,
$$

with norm convergence. Including the kernel, the Hilbert space decomposes as

$$
\mathcal H=\ker K\oplus \overline{\operatorname{span}\{e_n\}}.
$$

The spectrum has the form

$$
\sigma(K)=\{0\}\cup\{\lambda_n\},
$$

where the set $\{\lambda_n\}$ is finite or countable and can accumulate only at $0$.

This is the compact-operator version of “diagonalize the matrix.” The crucial difference from finite dimensions is that $0$ plays a special role. If $\mathcal H$ is infinite-dimensional and $K$ is compact, then $0\in\sigma(K)$. It may or may not be an eigenvalue, but it is always spectral.

## Compact normal operators and singular values

A bounded operator $K$ is normal if

$$
KK^*=K^*K.
$$

Compact normal operators also admit an orthonormal spectral decomposition with nonzero eigenvalues tending to zero. Self-adjoint compact operators are the real-spectrum case.

For a general compact operator $K$, one studies singular values. These are the eigenvalues of the positive compact operator

$$
|K|=(K^*K)^{1/2}.
$$

The nonzero singular values $s_n(K)$ satisfy

$$
s_n(K)\to0.
$$

In favorable cases, one has a singular-value decomposition

$$
K\psi=\sum_n s_n\langle v_n,\psi\rangle u_n,
$$

where $u_n$ and $v_n$ are orthonormal families. This is the infinite-dimensional cousin of the matrix singular-value decomposition.

Singular values are the bridge to Hilbert–Schmidt and trace-class operators. Compactness says $s_n\to0$. Hilbert–Schmidt requires roughly

$$
\sum_n s_n^2<\infty,
$$

and trace class requires roughly

$$
\sum_n s_n<\infty.
$$

So trace ideals are stronger than compactness. They measure how fast the compact axes shrink.

## Integral operators

Many compact operators appear as integral kernels. Let

$$
(Kf)(x)=\int_Y K(x,y)f(y)\,d\nu(y)
$$

act from $L^2(Y)$ to $L^2(X)$. If the kernel is square-integrable,

$$
\int_Xd\mu(x)\int_Yd\nu(y)\,|K(x,y)|^2<\infty,
$$

then $K$ is Hilbert–Schmidt and therefore compact.

This is one of the cleanest analytic reasons kernels can behave like infinite matrices. A square-integrable kernel is the continuum analog of a matrix with square-summable entries.

Not every important QFT kernel is square-integrable. Propagators often have singularities at coincident points or long-distance tails. But after imposing finite volume, adding a mass, applying heat-kernel damping, or composing with enough smoothing, compactness frequently returns.

## Compact embeddings and smoothing

Compactness often comes from smoothing. A basic principle is:

$$
\text{extra regularity plus bounded geometry}
\quad\Rightarrow\quad
\text{compact inclusion}.
$$

For example, on a bounded interval or compact manifold, the inclusion of a higher Sobolev space into a lower one is compact under suitable hypotheses. Symbolically,

$$
H^s(M)\hookrightarrow H^t(M)
\qquad s>t
$$

is compact when $M$ is compact and the standard assumptions hold.

This is the analytic content behind the statement that elliptic inverse operators are compact on compact spaces. Solving an elliptic equation usually gains derivatives. The gained regularity plus compact embedding makes the inverse compact.

For QFT, this is why finite-volume elliptic operators often have discrete spectra. The inverse of a positive elliptic operator is compact after zero modes are handled.

## Compact resolvent

An unbounded operator $A$ is not compact as a map on the Hilbert space because it is not even defined everywhere. Instead, one asks whether its resolvent is compact. If $A$ is closed and $z$ lies in the resolvent set, then

$$
(A-z)^{-1}
$$

is a bounded operator. We say $A$ has **compact resolvent** if

$$
(A-z)^{-1}
$$

is compact for one, and hence all, $z$ in the resolvent set.

Self-adjoint operators with compact resolvent have discrete spectral behavior. Their spectrum consists of eigenvalues of finite multiplicity with no finite accumulation point except possibly at infinity:

$$
|\lambda_n|\to\infty.
$$

The Laplacian on a compact manifold is the standard example. Its inverse, after removing zero modes if necessary, is compact. Therefore the Laplacian has a countable discrete spectrum.

This is the setting behind many mode expansions:

$$
-\Delta e_n=\lambda_ne_n,
\qquad
\phi(x)=\sum_n q_n e_n(x).
$$

In infinite volume, compact resolvent usually fails. The spectrum develops continuous parts, sums become integrals, and spectral densities replace discrete eigenvalue lists.

## Fredholm alternative

Compact operators are also the natural home of the Fredholm alternative. Let $K$ be compact on a Hilbert space. The equation

$$
(\mathbf 1-K)\psi=\eta
$$

behaves much more like a finite-dimensional linear equation than a generic infinite-dimensional equation.

The Fredholm alternative says, roughly, that exactly one of the following happens:

1. $\mathbf 1-K$ is invertible.
2. The homogeneous equation

$$
(\mathbf 1-K)\psi=0
$$

has nonzero solutions.

More precisely, the kernel of $\mathbf 1-K$ is finite-dimensional, the range is closed, and solvability of the inhomogeneous equation is controlled by orthogonality to the kernel of the adjoint equation

$$
(\mathbf 1-K^*)\chi=0.
$$

For integral equations, this is the infinite-dimensional analog of the statement that a linear system can be solved unless the source has a component along a zero mode of the adjoint.

In QFT language, the Fredholm alternative is a clean way to think about zero modes, collective coordinates, gauge-fixing obstructions, and solvability conditions in linearized equations.

## Trace ideals and determinants

Compactness alone does not make traces or determinants finite. A compact positive operator may have eigenvalues $\lambda_n\to0$ so slowly that

$$
\sum_n\lambda_n
$$

diverges. Thus compactness is weaker than trace class.

For a compact operator $K$, the singular values $s_n(K)$ measure the size of its axes. The operator is Hilbert–Schmidt if

$$
\sum_n s_n(K)^2<\infty,
$$

and trace class if

$$
\sum_n s_n(K)<\infty.
$$

Trace-class operators have a well-defined trace, and certain trace-class perturbations have Fredholm determinants. Hilbert–Schmidt operators have a finite Hilbert–Schmidt norm and many useful compactness properties, but they need not be trace class.

This hierarchy is important for one-loop physics. A Gaussian determinant is rarely justified by saying “the operator has discrete eigenvalues.” One must also control the divergence of products or sums. Heat-kernel subtraction, zeta regularization, Pauli–Villars regularization, and Fredholm determinants are different ways of adding the missing analytic data.

The hierarchy is:

$$
\text{trace class}
\quad\Rightarrow\quad
\text{Hilbert--Schmidt}
\quad\Rightarrow\quad
\text{compact}
\quad\Rightarrow\quad
\text{bounded}.
$$

The reverse implications are false in infinite dimensions.

## Examples in QFT and mathematical physics

**Finite-volume mode sums.** On compact spatial regions with suitable boundary conditions, elliptic operators often have compact resolvent. Their spectra are discrete, producing sums over modes rather than integrals over momenta.

**Massive Green operators.** On a compact Riemannian manifold, operators like

$$
(-\Delta+m^2)^{-1}
$$

are compact for $m^2>0$. If $m=0$, zero modes must be handled separately.

**Heat kernels.** For positive elliptic operators on compact spaces, $e^{-sA}$ is often trace class for $s>0$. This is stronger than compactness and underlies heat-trace asymptotics.

**Fredholm determinants.** Operators of the form

$$
\mathbf 1+K
$$

with $K$ trace class have Fredholm determinants. These appear in integrable systems, scattering, random matrices, and some exact QFT calculations.

**Instanton and soliton fluctuations.** Linearizing around a classical solution often gives a differential operator with zero modes and a discrete finite-volume spectrum. Compact-resolvent language clarifies which mode sums are legitimate and where collective coordinates are needed.

**Infinite-volume scattering.** Compactness usually fails in infinite volume. The free Hamiltonian on $L^2(\mathbb R^d)$ has continuous spectrum, not compact resolvent. Scattering theory therefore uses resolvents, wave operators, and spectral densities rather than pure compact spectral sums.

## Common pitfalls

**Assuming bounded implies compact.** In infinite dimensions this is false. The identity operator is bounded but not compact.

**Assuming compact means finite-rank.** Finite-rank operators are compact, but compact operators may have infinitely many nonzero eigenvalues or singular values.

**Forgetting that compactness depends on topology.** Compactness here means compactness in Hilbert-space norm, not weak compactness or pointwise convergence.

**Treating every discrete spectrum as compactness.** Compact resolvent implies a discrete spectrum with eigenvalues escaping to infinity, but not every discrete-looking formal spectrum comes from a well-defined compact-resolvent operator.

**Ignoring zero modes.** For compact operators, $0$ is special. For inverse elliptic operators, zero modes may obstruct the inverse and must be projected out or treated as collective coordinates.

**Using determinants from compactness alone.** Compactness controls eigenvalue accumulation, not summability of eigenvalues or logarithms. Determinants need stronger conditions or regularization.

**Forgetting infinite volume.** A finite box may give a compact-resolvent operator and a discrete spectrum. Removing the box can turn sums into integrals and eigenvalues into continuous spectral density.

## Exercises

### Exercise 1: The identity is not compact

Let $\mathcal H$ be infinite-dimensional and let $\{e_n\}$ be an orthonormal sequence. Show that the identity operator $\mathbf 1$ is not compact.

<details><summary><strong>Solution</strong></summary>

The sequence $e_n$ is bounded because

$$
\|e_n\|=1.
$$

For $n\ne m$,

$$
\|e_n-e_m\|^2
=\|e_n\|^2+\|e_m\|^2-2\operatorname{Re}\langle e_n,e_m\rangle
=2.
$$

Therefore no subsequence of $e_n$ is Cauchy, so no subsequence converges. If $\mathbf 1$ were compact, then the image of every bounded sequence would have a convergent subsequence. But $\mathbf 1 e_n=e_n$, so this fails. Hence $\mathbf 1$ is not compact.

</details>

### Exercise 2: Finite-rank operators are compact

Let

$$
F\psi=\sum_{j=1}^N\langle u_j,\psi\rangle v_j
$$

with fixed $u_j\in\mathcal H$ and $v_j\in\mathcal K$. Show that $F$ is compact.

<details><summary><strong>Solution</strong></summary>

The range of $F$ lies in the finite-dimensional subspace

$$
V=\operatorname{span}\{v_1,\dots,v_N\}\subseteq\mathcal K.
$$

If $\psi$ lies in a bounded set, then each coefficient $\langle u_j,\psi\rangle$ is bounded by Cauchy–Schwarz:

$$
|\langle u_j,\psi\rangle|\le \|u_j\|\,\|\psi\|.
$$

Thus $F\psi$ lies in a bounded subset of the finite-dimensional space $V$. In finite dimensions, bounded sets have compact closure. Therefore the image of every bounded set under $F$ has compact closure, so $F$ is compact.

</details>

### Exercise 3: A diagonal compact operator

On $\ell^2(\mathbb N)$, define

$$
(Kx)_n=\frac{x_n}{n}.
$$

Show that $K$ is compact.

<details><summary><strong>Solution</strong></summary>

Define finite-rank truncations

$$
(K_Nx)_n=
\begin{cases}
 x_n/n, & n\le N,\\
 0, & n>N.
\end{cases}
$$

Each $K_N$ has finite rank and is compact. The operator norm of $K-K_N$ is

$$
\|K-K_N\|=\sup_{n>N}\frac{1}{n}=\frac{1}{N+1}.
$$

Therefore

$$
\|K-K_N\|\to0.
$$

Since compact operators are closed in operator norm, $K$ is compact.

</details>

### Exercise 4: Nonzero eigenvalues of a compact operator cannot stay away from zero

Suppose $K$ is compact and has normalized eigenvectors $e_n$ with eigenvalues $\lambda_n$ satisfying

$$
|\lambda_n|\ge c>0
$$

for infinitely many mutually orthogonal $e_n$. Show that this is impossible.

<details><summary><strong>Solution</strong></summary>

The sequence $e_n$ is bounded. Compactness implies that $Ke_n$ has a convergent subsequence. But

$$
Ke_n=\lambda_ne_n.
$$

For $n\ne m$,

$$
\|\lambda_ne_n-\lambda_me_m\|^2
=|\lambda_n|^2+|\lambda_m|^2
\ge 2c^2,
$$

because $e_n$ and $e_m$ are orthogonal. Hence no subsequence of $Ke_n$ is Cauchy, so no subsequence converges. This contradicts compactness. Therefore an infinite sequence of orthogonal eigenvectors can only have eigenvalues tending to zero.

</details>

### Exercise 5: Compact inverse of the Dirichlet Laplacian on an interval

Let $A=-d^2/dx^2$ on $L^2([0,L])$ with Dirichlet boundary conditions. Its eigenvalues are

$$
\lambda_n=\left(\frac{n\pi}{L}\right)^2.
$$

Show that $A^{-1}$ is compact.

<details><summary><strong>Solution</strong></summary>

On the normalized sine basis $e_n$, one has

$$
Ae_n=\lambda_ne_n.
$$

Thus

$$
A^{-1}e_n=\lambda_n^{-1}e_n
=\left(\frac{L}{n\pi}\right)^2e_n.
$$

The eigenvalues of $A^{-1}$ are

$$
\mu_n=\left(\frac{L}{n\pi}\right)^2,
$$

and

$$
\mu_n\to0.
$$

The inverse is diagonal with eigenvalues tending to zero. Equivalently, it is the norm limit of finite-rank truncations, so it is compact.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis* and *IV: Analysis of Operators*. Standard references for compact operators, trace ideals, and spectral theory.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. Useful for compact resolvents and Schrödinger operators.
- B. C. Hall, *Quantum Theory for Mathematicians*. Clear treatment of compact operators and spectral theory in quantum mechanics.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Physics-friendly treatment of compactness, resolvents, and spectra.
- J. B. Conway, *A Course in Functional Analysis*. Standard functional-analysis reference.
- T. Kato, *Perturbation Theory for Linear Operators*. Classic reference for compact perturbations and spectral stability.
- M. Srednicki, *Quantum Field Theory*. Useful for functional determinants and mode expansions in QFT.
- M. Nakahara, *Geometry, Topology and Physics*. Useful for elliptic operators, zero modes, and geometric applications.

## Version history

- 2026-06-25: Initial polished draft.
