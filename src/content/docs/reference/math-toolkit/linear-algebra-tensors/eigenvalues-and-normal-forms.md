---
title: "Eigenvalues and Normal Forms"
description: "Explains eigenvalues, eigenspaces, diagonalization, Jordan form, normal and Hermitian matrices, spectral projectors, singular values, generalized eigenvalue problems, and QFT uses in quadratic actions and stability."
sidebar:
  label: "Eigenvalues and Normal Forms"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard references on finite-dimensional linear algebra, spectral theory, matrix analysis, quadratic forms, and QFT convention practice, including Axler, Hoffman–Kunze, Horn–Johnson, Roman, Srednicki, Weinberg, Schwartz, Zee, and Zinn-Justin."
topics:
  - eigenvalue
  - eigenvector
  - diagonalization
  - Jordan form
  - normal matrix
  - Hermitian matrix
  - spectral projector
  - singular value decomposition
  - quadratic form
  - stability analysis
canonicalTopics:
  - eigenvalue
  - eigenvector
  - diagonalization
  - jordan-form
  - normal-matrix
  - hermitian-matrix
  - spectral-projector
  - singular-value-decomposition
  - quadratic-form
  - stability-analysis
researchStatus:
  established:
    - "Finite-dimensional eigenvalue theory, diagonalization criteria, Jordan normal form, spectral projectors, singular values, and normal-matrix spectral theorems are standard results in linear algebra."
    - "Quadratic actions, mass matrices, small-oscillation problems, transfer matrices, propagators, and stability analysis all use finite-dimensional normal-form ideas before passing to operator theory."
  active:
    - "Infinite-dimensional spectral theory, non-self-adjoint operators, continuous spectrum, resonances, pseudospectra, and unbounded domains require additional functional-analytic tools developed elsewhere in the Mathematical Toolkit."
---

## Summary

Eigenvalues turn a linear operator into a list of possible scaling factors along special directions:

$$
Av=\lambda v,
\qquad v\neq0.
$$

When enough eigenvectors exist, a linear problem decomposes into independent one-dimensional modes. When they do not, Jordan blocks keep track of the leftover nilpotent mixing. When an operator is Hermitian, real symmetric, unitary, or more generally normal, an inner product gives an orthogonal spectral decomposition. That is the safe case. Much of mathematical physics is the art of reducing problems to that safe case — and recognizing when it has failed.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing an operator leading to characteristic data, eigenvectors, diagonalization, Jordan blocks, normal/Hermitian spectral decompositions, and QFT uses in modes, stability, zero modes, and propagators.](/figures/math-toolkit/eigenvalue-normal-form-map.svg)

<figcaption>

Normal forms translate an operator into usable spectral data. If there are enough eigenvectors, diagonalization gives decoupled modes. If not, Jordan blocks record nilpotent mixing. If an inner product makes the operator normal or Hermitian, the decomposition is orthogonal and stable. In QFT this language appears in mass matrices, quadratic actions, transfer matrices, propagators, zero modes, ghosts, and stability analysis.

</figcaption>
</figure>

This page is finite-dimensional. The infinite-dimensional versions — self-adjoint operators, spectral measures, compact operators, continuous spectrum, trace-class assumptions, and rigged Hilbert spaces — are treated in [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/).

## Prerequisites

You should know [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), [Bilinear Forms and Metrics](/math-toolkit/linear-algebra-tensors/bilinear-forms-and-metrics/), [Index Notation](/math-toolkit/linear-algebra-tensors/index-notation/), and [Determinants, Traces, and Jacobians](/math-toolkit/linear-algebra-tensors/determinants-traces-and-jacobians/).

We work with a finite-dimensional vector space $V$ over $\mathbb C$ unless the real case is stated explicitly. This is not because physics is always complex-linear at the classical level, but because characteristic polynomials split over $\mathbb C$, and eigenvalue language becomes cleaner.

## Eigenvalues and eigenspaces

An eigenvalue of $A:V\to V$ is a scalar $\lambda$ such that

$$
Av=\lambda v
$$

for some nonzero vector $v$. The corresponding eigenspace is

$$
E_\lambda=\ker(A-\lambda I).
$$

Eigenvalues are roots of the characteristic polynomial

$$
p_A(\lambda)=\det(\lambda I-A).
$$

The **algebraic multiplicity** of $\lambda$ is its multiplicity as a root of $p_A$. The **geometric multiplicity** is

$$
\dim E_\lambda.
$$

Always,

$$
1\le \dim E_\lambda\le \text{algebraic multiplicity of }\lambda.
$$

The gap between algebraic and geometric multiplicity is the first warning that diagonalization may fail.

:::note[Eigenvectors are directions, not coordinates]
An eigenvector is an element of $V$, not a column of numbers. Its coordinate column changes with the basis. The eigenvalue is basis-independent, and the eigenspace is a basis-independent subspace.
:::

## Diagonalization

An operator $A$ is diagonalizable if $V$ has a basis of eigenvectors. Equivalently,

$$
V=\bigoplus_\lambda E_\lambda.
$$

In such a basis,

$$
A=SDS^{-1},
$$

where $D$ is diagonal:

$$
D=\operatorname{diag}(\lambda_1,\dots,\lambda_n).
$$

Diagonalization turns powers, exponentials, and functions of $A$ into scalar operations:

$$
A^k=SD^kS^{-1},
\qquad
f(A)=Sf(D)S^{-1},
$$

with

$$
f(D)=\operatorname{diag}(f(\lambda_1),\dots,f(\lambda_n)).
$$

For time evolution in a linear system

$$
\dot x=Ax,
$$

diagonalization gives

$$
x(t)=e^{tA}x(0)=Se^{tD}S^{-1}x(0).
$$

Each eigenmode evolves as $e^{\lambda t}$. This is why eigenvalues diagnose oscillation, growth, decay, and instability.

## Minimal polynomial criterion

The characteristic polynomial tells you the eigenvalues with multiplicities. The minimal polynomial tells you the normal form more efficiently. It is the monic polynomial $m_A(z)$ of least degree such that

$$
m_A(A)=0.
$$

Over $\mathbb C$, the operator $A$ is diagonalizable if and only if the minimal polynomial has no repeated roots:

$$
m_A(z)=\prod_\lambda (z-\lambda)
$$

with each factor appearing once.

This criterion is useful because it separates the two issues:

- whether the characteristic polynomial splits;
- whether generalized eigenvectors beyond ordinary eigenvectors are needed.

Over $\mathbb C$, the first issue disappears. The second issue is the real one.

## Jordan blocks

If $A$ is not diagonalizable, it can still be put into Jordan normal form over $\mathbb C$:

$$
A=SJS^{-1},
$$

where $J$ is block diagonal and each block has the form

$$
J_\lambda=
\begin{pmatrix}
\lambda&1&0&\cdots&0\\
0&\lambda&1&\cdots&0\\
\vdots&\vdots&\vdots&\ddots&\vdots\\
0&0&0&\cdots&1\\
0&0&0&\cdots&\lambda
\end{pmatrix}.
$$

A Jordan block is

$$
J_\lambda=\lambda I+N,
$$

where $N$ is nilpotent:

$$
N^r=0
$$

for a block of size $r$.

Then

$$
e^{tJ_\lambda}=e^{\lambda t}e^{tN}
=e^{\lambda t}\left(I+tN+\frac{t^2}{2!}N^2+\cdots+\frac{t^{r-1}}{(r-1)!}N^{r-1}\right).
$$

Thus Jordan blocks create polynomial factors multiplying the usual exponential behavior. In differential equations and transfer-matrix problems, those polynomial factors are the footprint of non-diagonalizable mixing.

:::caution[Jordan form is exact but often numerically fragile]
Jordan normal form is mathematically sharp, but small perturbations can split a Jordan block. In numerical work and many physical applications, Schur form, singular values, or spectral projectors are more stable. Jordan blocks are still conceptually essential because they diagnose the failure of a complete eigenbasis.
:::

## Generalized eigenspaces

The generalized eigenspace for $\lambda$ is

$$
G_\lambda=\ker(A-\lambda I)^N
$$

for $N$ sufficiently large. In finite dimension, taking $N=\dim V$ is enough. The space decomposes as

$$
V=\bigoplus_\lambda G_\lambda.
$$

On each $G_\lambda$, the operator has the form

$$
A=\lambda I+\text{nilpotent}.
$$

Ordinary eigenspaces are kernels of one power. Generalized eigenspaces are kernels of sufficiently high powers. The distinction matters whenever algebraic multiplicity exceeds geometric multiplicity.

## Spectral projectors in finite dimension

If $A$ is diagonalizable with distinct eigenvalues $\lambda$, the projector onto $E_\lambda$ can be written algebraically as

$$
P_\lambda=\prod_{\mu\neq\lambda}\frac{A-\mu I}{\lambda-\mu}.
$$

These projectors obey

$$
P_\lambda P_\mu=\delta_{\lambda\mu}P_\lambda,
\qquad
\sum_\lambda P_\lambda=I,
$$

and

$$
A=\sum_\lambda\lambda P_\lambda.
$$

This is the finite-dimensional prototype of the spectral theorem. In infinite-dimensional QFT settings, sums over projectors become spectral integrals, and eigenvalue sums may become continuous spectral densities.

## Inner products and adjoints

If $V$ has a Hermitian inner product, each operator $A$ has an adjoint $A^\dagger$ defined by

$$
\langle v,Aw\rangle=\langle A^\dagger v,w\rangle.
$$

An operator is:

| Type | Condition | Spectral consequence |
|---|---|---|
| Hermitian or self-adjoint in finite dimension | $A^\dagger=A$ | real eigenvalues, orthonormal eigenbasis |
| anti-Hermitian | $A^\dagger=-A$ | imaginary eigenvalues, orthonormal eigenbasis |
| unitary | $A^\dagger A=I$ | eigenvalues have $|\lambda|=1$ |
| normal | $A^\dagger A=AA^\dagger$ | unitarily diagonalizable |
| positive semidefinite | $\langle v,Av\rangle\ge0$ and $A=A^\dagger$ | eigenvalues $\lambda\ge0$ |

The finite-dimensional spectral theorem says:

:::note[Normal-matrix spectral theorem]
A complex matrix is unitarily diagonalizable if and only if it is normal:

$$
A^\dagger A=AA^\dagger.
$$

Hermitian, anti-Hermitian, and unitary matrices are special cases.
:::

For real vector spaces with a positive-definite inner product, real symmetric matrices are orthogonally diagonalizable:

$$
A=O\Lambda O^T,
\qquad O^TO=I.
$$

This is the version used in small-oscillation problems, real scalar mass matrices, and many Euclidean Gaussian integrals.

## Quadratic forms and diagonalization

A quadratic form on a real vector space is

$$
Q(x)=\frac12 x^TKx
$$

with $K=K^T$ after symmetrizing. If the inner product is Euclidean and $K$ is real symmetric, then

$$
K=O\Lambda O^T,
$$

so with $x=Oy$,

$$
Q(x)=\frac12\sum_i\lambda_i y_i^2.
$$

This is the algebra behind decoupled Gaussian modes. Positive eigenvalues give convergent Euclidean Gaussians. Zero eigenvalues are flat directions or gauge directions. Negative eigenvalues signal an instability, a saddle, or a contour-rotation problem depending on context.

In classical field theory and QFT, the quadratic expansion around a background often has the form

$$
S[\phi_0+\eta]=S[\phi_0]+\frac12\langle\eta,K\eta\rangle+O(\eta^3).
$$

The operator $K$ controls fluctuations. In finite-dimensional approximation, its eigenvalues determine Gaussian determinants, propagators, stability, and zero modes.

## Generalized eigenvalue problems

Sometimes the quadratic kinetic term is not written with the Euclidean inner product. A common finite-dimensional model is

$$
\frac12 \dot q^T M\dot q-\frac12 q^T Kq,
$$

where $M$ is a positive-definite mass matrix and $K$ is a stiffness matrix. Normal modes obey

$$
Kv=\omega^2 Mv.
$$

This is a generalized eigenvalue problem.

If $M$ is positive definite, choose $M^{1/2}$ and set

$$
u=M^{1/2}v.
$$

Then

$$
M^{-1/2}KM^{-1/2}u=\omega^2u.
$$

The problem reduces to an ordinary Hermitian eigenvalue problem. The eigenvectors are orthogonal with respect to the $M$-inner product:

$$
v_i^TMv_j=0
\qquad i\neq j.
$$

This is the finite-dimensional version of diagonalizing a kinetic operator with respect to a nontrivial field-space metric.

## Similarity versus congruence

Two matrix transformations appear constantly:

$$
A\mapsto SAS^{-1}
$$

and

$$
K\mapsto S^TKS.
$$

They mean different things.

Similarity transforms a linear operator under a basis change. It preserves eigenvalues, trace, determinant, characteristic polynomial, and Jordan structure.

Congruence transforms a bilinear form under a basis change. It preserves rank and signature over $\mathbb R$, but it does not preserve eigenvalues in general.

This distinction is a signpost for many QFT calculations. A mass matrix may be an operator after an inner product is chosen, but a quadratic form by itself transforms by congruence. Do not ask for “the eigenvalues of a quadratic form” until the pairing used to identify vectors and covectors has been specified.

## Singular values

For a general linear map

$$
A:V\to W
$$

between finite-dimensional inner-product spaces, eigenvalues may not even be defined if $V\neq W$. Singular values are defined instead. They are the square roots of eigenvalues of

$$
A^\dagger A.
$$

The singular value decomposition says

$$
A=U\Sigma V^\dagger,
$$

where $U,V$ are unitary and $\Sigma$ is diagonal rectangular with nonnegative entries.

In QFT, singular values appear whenever left and right spaces differ: chiral mass matrices, flavor mixing, Yukawa matrices, rectangular maps between constraints and gauge parameters, and numerical conditioning. Eigenvalues describe an endomorphism. Singular values describe the size of a general map.

## QFT dictionary

| Linear-algebra object | QFT interpretation | Warning |
|---|---|---|
| eigenvalue of $K$ | fluctuation stiffness, squared mass, inverse propagator mode | depends on kinetic normalization |
| zero eigenvalue | gauge direction, modulus, Goldstone direction, flat direction | must be treated separately |
| negative eigenvalue | instability, false-vacuum decay mode, saddle direction | contour and signature matter |
| diagonalization | decoupled modes | only legal when enough eigenvectors or a spectral theorem applies |
| Jordan block | non-diagonalizable mixing | usually unstable under perturbations |
| Hermitian operator | observable or Euclidean quadratic kernel | infinite-dimensional self-adjointness is subtler |
| unitary operator | time evolution or symmetry action | finite-dimensional unitarity is not enough for field-theory domains |
| spectral projector | mode extraction | becomes spectral measure in infinite dimension |
| singular values | mixing strengths, conditioning, rectangular maps | not phases or signed masses |
| generalized eigenproblem | normal modes with nontrivial metric | pairing must be specified |

## Mass matrices and mode normalization

For real scalar fields with canonical quadratic Lagrangian

$$
\mathcal L_2=\frac12\partial_\mu\phi^i\partial^\mu\phi^i-\frac12\phi^iM^2_{ij}\phi^j,
$$

where $M^2$ is real symmetric, an orthogonal transformation diagonalizes $M^2$:

$$
O^TM^2O=\operatorname{diag}(m_1^2,\dots,m_N^2).
$$

The fields

$$
\varphi=O^T\phi
$$

have canonical kinetic terms and diagonal masses.

If the kinetic term is not canonical,

$$
\mathcal L_2=\frac12 G_{ij}\partial_\mu\phi^i\partial^\mu\phi^j-\frac12 H_{ij}\phi^i\phi^j,
$$

then the physical squared masses come from the generalized eigenvalue problem

$$
H v=m^2 G v
$$

provided $G$ is positive definite. If $G$ is indefinite, as in gauge-fixed systems or constrained systems, the interpretation needs more care. Negative-norm directions and ghost fields are not ordinary particles with funny signs; they belong to a constrained quantization framework.

## Normal forms and propagators

Suppose a finite-dimensional Gaussian has kernel $K$. If $K$ is diagonalizable with eigenvectors $v_i$ and eigenvalues $\lambda_i$, then formally

$$
K^{-1}=\sum_i\lambda_i^{-1}P_i,
$$

where $P_i$ projects onto the corresponding mode. This is the finite-dimensional version of a spectral representation of a propagator.

If $K$ has a zero eigenvalue, this formula fails. One may define a reduced inverse on the complement of the kernel, but that requires choosing what happens to the zero mode. In gauge theory, this is tied to gauge fixing. In soliton physics, it is tied to collective coordinates. In spontaneous symmetry breaking, it may signal Goldstone directions.

## Stability and signatures

For a Euclidean quadratic form

$$
Q(x)=\frac12x^TKx,
$$

with $K=K^T$, the signs of eigenvalues determine the local shape:

| Eigenvalue type | Local behavior of $Q$ | Physical reading |
|---|---|---|
| all positive | local minimum | stable Euclidean Gaussian |
| some zero | flat directions | moduli, symmetries, gauge or collective coordinates |
| some negative | saddle | instability or steepest-descent contour issue |

For Lorentzian actions, the same table cannot be used directly because the oscillatory weight $e^{iS}$ is not a positive Gaussian measure. Stability is then usually diagnosed by the Hamiltonian, energy positivity, pole prescriptions, or Euclidean continuation when available.

## Common pitfalls

**Assuming every matrix is diagonalizable.** Most matrices over $\mathbb C$ with distinct eigenvalues are diagonalizable, but repeated eigenvalues can come with too few eigenvectors. Jordan blocks are the warning label.

**Confusing algebraic and geometric multiplicity.** Algebraic multiplicity counts roots of $p_A(\lambda)$. Geometric multiplicity counts eigenvectors. Diagonalization needs enough eigenvectors, not merely enough repeated roots.

**Diagonalizing a bilinear form as though it were an operator.** A quadratic form needs a pairing before it becomes an operator. Congruence and similarity are different transformations.

**Trusting eigenvalues of nonnormal matrices too much.** Nonnormal matrices can have nearly parallel eigenvectors and large transient growth even when eigenvalues look harmless. Orthogonal spectral decompositions require normality.

**Ignoring the kinetic term.** Physical masses are not always eigenvalues of the potential Hessian $H$. With nontrivial kinetic metric $G$, solve $Hv=m^2Gv$.

**Treating zero modes as small nonzero modes.** Zero modes change the structure of the integral or solution space. They are not just determinants that happen to vanish; they are directions requiring separate coordinates or constraints.

**Importing finite-dimensional spectral intuition into unbounded operators without checking domains.** In QFT, the Hamiltonian, Laplacian, Dirac operator, and wave operator live on infinite-dimensional spaces. Self-adjointness, boundary conditions, and spectrum are part of the definition.

## Exercises

### Exercise 1: Algebraic versus geometric multiplicity

Consider

$$
A=\begin{pmatrix}
1&1\\
0&1
\end{pmatrix}.
$$

Find the characteristic polynomial, algebraic multiplicity, eigenspace dimension, and Jordan form.

<details><summary><strong>Solution</strong></summary>

The characteristic polynomial is

$$
p_A(\lambda)=\det\begin{pmatrix}\lambda-1&-1\\0&\lambda-1\end{pmatrix}
=(\lambda-1)^2.
$$

Thus $\lambda=1$ has algebraic multiplicity $2$.

The eigenspace is

$$
\ker(A-I)=\ker\begin{pmatrix}0&1\\0&0\end{pmatrix}.
$$

This imposes $v_2=0$, so

$$
E_1=\left\{\begin{pmatrix}v_1\\0\end{pmatrix}\right\}
$$

has dimension $1$. The matrix is already a Jordan block:

$$
A=J_1=\begin{pmatrix}1&1\\0&1\end{pmatrix}.
$$

It is not diagonalizable because the geometric multiplicity is smaller than the algebraic multiplicity.

</details>

### Exercise 2: Exponential of a Jordan block

For

$$
J=\begin{pmatrix}
\lambda&1\\
0&\lambda
\end{pmatrix},
$$

compute $e^{tJ}$.

<details><summary><strong>Solution</strong></summary>

Write

$$
J=\lambda I+N,
\qquad
N=\begin{pmatrix}0&1\\0&0\end{pmatrix}.
$$

Since $N^2=0$ and $\lambda I$ commutes with $N$,

$$
e^{tJ}=e^{t\lambda I}e^{tN}=e^{\lambda t}(I+tN).
$$

Therefore

$$
e^{tJ}=e^{\lambda t}
\begin{pmatrix}
1&t\\
0&1
\end{pmatrix}.
$$

The extra factor of $t$ is the signature of the nontrivial Jordan block.

</details>

### Exercise 3: Orthogonal diagonalization of a real symmetric matrix

Let

$$
K=\begin{pmatrix}
2&1\\
1&2
\end{pmatrix}.
$$

Find an orthonormal eigenbasis and diagonalize the quadratic form $Q(x)=\frac12x^TKx$.

<details><summary><strong>Solution</strong></summary>

The eigenvectors are

$$
v_+=\frac{1}{\sqrt2}\begin{pmatrix}1\\1\end{pmatrix},
\qquad
v_-=\frac{1}{\sqrt2}\begin{pmatrix}1\\-1\end{pmatrix}.
$$

They have eigenvalues

$$
Kv_+=3v_+,
\qquad
Kv_-=v_-.
$$

Let $O=(v_+\ v_-)$, so

$$
O^TKO=\begin{pmatrix}3&0\\0&1\end{pmatrix}.
$$

Writing $x=Oy$, the quadratic form becomes

$$
Q=\frac12(3y_+^2+y_-^2).
$$

Thus the modes are decoupled and both directions are stable for a Euclidean Gaussian.

</details>

### Exercise 4: Generalized eigenvalues

Let

$$
M=\begin{pmatrix}2&0\\0&1\end{pmatrix},
\qquad
K=\begin{pmatrix}8&0\\0&3\end{pmatrix}.
$$

Solve $Kv=\omega^2 Mv$.

<details><summary><strong>Solution</strong></summary>

The equation is diagonal:

$$
\begin{pmatrix}8&0\\0&3\end{pmatrix}
\begin{pmatrix}v_1\\v_2\end{pmatrix}
=\omega^2
\begin{pmatrix}2&0\\0&1\end{pmatrix}
\begin{pmatrix}v_1\\v_2\end{pmatrix}.
$$

For the first coordinate,

$$
8v_1=2\omega^2v_1,
$$

so a nonzero $v_1$ gives $\omega^2=4$.

For the second coordinate,

$$
3v_2=\omega^2v_2,
$$

so a nonzero $v_2$ gives $\omega^2=3$.

Thus the generalized eigenvalues are

$$
\omega^2=4,
\qquad
\omega^2=3.
$$

They are not simply the diagonal entries of $K$; the kinetic matrix $M$ matters.

</details>

### Exercise 5: Spectral projectors for two eigenvalues

Suppose $A$ is diagonalizable and has only two distinct eigenvalues $\lambda_1\neq\lambda_2$. Show that

$$
P_1=\frac{A-\lambda_2 I}{\lambda_1-\lambda_2},
\qquad
P_2=\frac{A-\lambda_1 I}{\lambda_2-\lambda_1}
$$

are projectors onto the two eigenspaces.

<details><summary><strong>Solution</strong></summary>

On a vector $v\in E_{\lambda_1}$,

$$
P_1v=\frac{\lambda_1-\lambda_2}{\lambda_1-\lambda_2}v=v,
\qquad
P_2v=\frac{\lambda_1-\lambda_1}{\lambda_2-\lambda_1}v=0.
$$

On a vector $w\in E_{\lambda_2}$,

$$
P_1w=0,
\qquad
P_2w=w.
$$

Since $A$ is diagonalizable, every vector is a sum of vectors in these eigenspaces. Therefore $P_1$ and $P_2$ are the desired projectors. It follows immediately that

$$
P_i^2=P_i,
\qquad
P_1P_2=0,
\qquad
P_1+P_2=I.
$$

</details>

## References and further reading

For finite-dimensional eigenvalue theory, diagonalization, Jordan form, and normal matrices, see Sheldon Axler, *Linear Algebra Done Right*; Kenneth Hoffman and Ray Kunze, *Linear Algebra*; Steven Roman, *Advanced Linear Algebra*; and Roger Horn and Charles Johnson, *Matrix Analysis*. For quadratic forms and geometric uses, see Theodore Frankel, *The Geometry of Physics* and Mikio Nakahara, *Geometry, Topology and Physics*.

For QFT uses in mass matrices, Gaussian fluctuations, propagators, path integrals, and one-loop determinants, see Mark Srednicki, *Quantum Field Theory*; Steven Weinberg, *The Quantum Theory of Fields*; Matthew Schwartz, *Quantum Field Theory and the Standard Model*; A. Zee, *Quantum Field Theory in a Nutshell*; and Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. For the infinite-dimensional continuation, see [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Compact Operators](/math-toolkit/functional-analysis-spectral-theory/compact-operators/), and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/).

## Version history

- 2026-06-26: First polished draft. Added eigenvalues, eigenspaces, diagonalization, minimal polynomials, Jordan blocks, generalized eigenspaces, spectral projectors, normal and Hermitian matrices, quadratic forms, generalized eigenvalue problems, singular values, QFT dictionary, common pitfalls, and exercises with solutions.
