---
title: "Spectral Theorem"
description: "Explains the spectral theorem for self-adjoint operators, projection-valued measures, functional calculus, domains, continuous spectrum, and QFT uses such as time evolution, resolvents, heat kernels, and determinants."
sidebar:
  label: "Spectral Theorem"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard spectral-theory and mathematical-physics references, including Reed–Simon, Teschl, Hall, Moretti, Stone, von Neumann, Rudin, Yosida, and QFT treatments of propagators, spectral representations, and functional determinants."
topics:
  - spectral theorem
  - projection-valued measures
  - self-adjoint operators
  - spectral measures
  - functional calculus
  - resolvents
  - continuous spectrum
  - point spectrum
  - unitary evolution
  - heat kernels
canonicalTopics:
  - spectral-theorem
  - projection-valued-measure
  - self-adjoint-operator
  - spectral-measure
  - functional-calculus
  - resolvent
  - continuous-spectrum
  - point-spectrum
  - stone-theorem
  - heat-kernel
researchStatus:
  established:
    - "The spectral theorem is the standard infinite-dimensional replacement for diagonalizing Hermitian matrices and underlies the functional calculus of self-adjoint operators."
  active:
    - "In interacting continuum QFT, the spectral theorem is fully reliable for self-adjoint generators, but identifying the correct Hilbert space, operator domains, local algebras, and spectral measures can be highly nontrivial."
---

## Summary

The spectral theorem is what remains of diagonalizing a Hermitian matrix after the Hilbert space becomes infinite-dimensional and the spectrum develops continuous parts. In finite dimensions, a Hermitian matrix can be written as

$$
A=\sum_j \lambda_j P_j,
$$

where $P_j$ projects onto the eigenspace with eigenvalue $\lambda_j$. The spectral theorem replaces the sum by a projection-valued integral:

$$
A=\int_{\mathbb R}\lambda\,dE_A(\lambda).
$$

Here $E_A$ is not an ordinary function. It is a projection-valued measure: for each Borel set $\Delta\subseteq\mathbb R$, the operator $E_A(\Delta)$ is an orthogonal projector onto the part of the Hilbert space where the observable $A$ has spectral values in $\Delta$.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing a self-adjoint operator producing a projection-valued measure, a spectral integral, scalar probability measures, functional calculus, and QFT outputs such as unitary evolution, heat kernels, resolvents, and determinants.](/figures/math-toolkit/spectral-theorem-functional-calculus.svg)

<figcaption>

The spectral theorem turns a self-adjoint operator $A=A^*$ into a projection-valued measure $E_A$. Scalar spectral measures $\mu_\psi(\Delta)=\langle\psi,E_A(\Delta)\psi\rangle$ give probabilities, while the spectral integral defines $A$ and the functional calculus $f(A)$. This is the common source of $e^{-itH}$, $(A-z)^{-1}$, $e^{-sA}$, and regulated expressions such as $\log A$.

</figcaption>
</figure>

The theorem is the analytic engine behind the formulas physicists write every day:

$$
e^{-itH},
\qquad
(H-z)^{-1},
\qquad
e^{-sD^2},
\qquad
\sqrt{-\Delta+m^2},
\qquad
\log\det A.
$$

It also explains why plane waves and scattering states are subtle. A free-particle Hamiltonian has a perfectly good self-adjoint realization, but its spectral resolution is continuous. The “eigenvectors” labeled by momentum are generalized distributions, not normalizable Hilbert-space vectors.

## Prerequisites

You should know Hilbert spaces, bounded and unbounded operators, adjoints, and self-adjointness from [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), and [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/). Distributional examples use [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/). Heat-kernel and determinant examples connect to [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

## Core idea

The finite-dimensional spectral theorem says that a Hermitian matrix has an orthonormal basis of eigenvectors. If

$$
A e_j=\lambda_j e_j,
$$

then every vector decomposes as

$$
\psi=\sum_j \langle e_j,\psi\rangle e_j,
$$

and

$$
A\psi=\sum_j \lambda_j\langle e_j,\psi\rangle e_j.
$$

Equivalently, if $P_j=|e_j\rangle\langle e_j|$ for a nondegenerate eigenvalue, then

$$
A=\sum_j \lambda_j P_j.
$$

For degenerate eigenvalues, $P_j$ is the projection onto the whole eigenspace. Either way, the operator is reconstructed from spectral values and orthogonal projections.

In infinite dimensions, this picture must be repaired in two ways.

First, the spectrum need not consist of isolated eigenvalues. The momentum operator on $L^2(\mathbb R)$ has continuous spectrum. There is no countable orthonormal basis of normalizable eigenvectors $|p\rangle$ inside $L^2(\mathbb R)$.

Second, important operators such as Hamiltonians, momenta, Laplacians, and Dirac operators are usually unbounded. Their domains are part of the data. A formula like $A=\int\lambda\,dE_A(\lambda)$ must therefore include a domain statement, not merely an algebraic identity.

The spectral theorem says that a self-adjoint operator $A$ is equivalent to a projection-valued measure $E_A$ on the real line. The projections satisfy

$$
E_A(\emptyset)=0,
\qquad
E_A(\mathbb R)=\mathbf 1,
$$

and

$$
E_A(\Delta_1\cap\Delta_2)=E_A(\Delta_1)E_A(\Delta_2)
$$

for Borel sets $\Delta_1,\Delta_2\subseteq\mathbb R$. If $\Delta_n$ are disjoint, then

$$
E_A\!\left(\bigcup_n\Delta_n\right)\psi
=\sum_n E_A(\Delta_n)\psi
$$

with convergence in Hilbert-space norm for every $\psi$.

The slogan is

$$
\text{self-adjoint operator}
\quad\longleftrightarrow\quad
\text{real projection-valued spectral measure}.
$$

This is more flexible than an eigenbasis. It treats isolated eigenvalues, continuous bands, thresholds, and mixed spectra in one language.

## Projection-valued measures

Let $\mathcal H$ be a Hilbert space. A projection-valued measure $E$ on $\mathbb R$ assigns to each Borel set $\Delta\subseteq\mathbb R$ an orthogonal projection $E(\Delta)$ on $\mathcal H$.

Orthogonal projection means

$$
E(\Delta)^2=E(\Delta),
\qquad
E(\Delta)^*=E(\Delta).
$$

The product rule

$$
E(\Delta_1)E(\Delta_2)=E(\Delta_1\cap\Delta_2)
$$

says that the spectral subspaces for disjoint regions of the spectrum are orthogonal. If $\Delta_1\cap\Delta_2=\emptyset$, then

$$
E(\Delta_1)E(\Delta_2)=0.
$$

Given a vector $\psi\in\mathcal H$, the projection-valued measure produces an ordinary scalar measure

$$
\mu_\psi(\Delta)=\langle\psi,E(\Delta)\psi\rangle.
$$

If $\|\psi\|=1$, then $\mu_\psi$ is a probability measure. In quantum-mechanical language,

$$
\mu_\psi(\Delta)
$$

is the probability that a measurement of the observable $A$ gives a result in $\Delta$.

More generally, for $\psi,\phi\in\mathcal H$, one defines a complex measure

$$
\mu_{\psi,\phi}(\Delta)=\langle\psi,E(\Delta)\phi\rangle.
$$

Matrix elements of functions of $A$ are then ordinary integrals against these scalar measures:

$$
\langle\psi,f(A)\phi\rangle
=\int_{\mathbb R} f(\lambda)\,d\mu_{\psi,\phi}(\lambda),
$$

whenever the expression is defined.

This is the clean replacement for “insert a complete set of eigenstates.” In the presence of continuous spectrum, the complete set is not a literal Hilbert-space basis of eigenvectors; it is the spectral measure.

## The bounded spectral theorem

The easiest version is for bounded self-adjoint operators. If $A=A^*$ and $A$ is bounded, then there exists a unique projection-valued measure $E_A$ supported on the spectrum $\sigma(A)$ such that

$$
A=\int_{\sigma(A)}\lambda\,dE_A(\lambda).
$$

For bounded Borel functions $f$, one defines

$$
f(A)=\int_{\sigma(A)} f(\lambda)\,dE_A(\lambda).
$$

This map has the expected algebraic properties:

$$
(f+g)(A)=f(A)+g(A),
$$

$$
(fg)(A)=f(A)g(A),
$$

and

$$
\overline f(A)=f(A)^*
$$

when $\overline f$ denotes complex conjugation of $f$. In particular, if $f$ is real-valued, then $f(A)$ is self-adjoint when defined as a bounded operator.

For polynomials, this agrees with the usual definition. If

$$
f(\lambda)=a_0+a_1\lambda+\cdots+a_n\lambda^n,
$$

then

$$
f(A)=a_0\mathbf 1+a_1A+\cdots+a_nA^n.
$$

The spectral theorem extends polynomial substitution to far less elementary functions, including characteristic functions of intervals:

$$
\mathbf 1_\Delta(A)=E_A(\Delta).
$$

This formula is important. It says that spectral projections are themselves functions of the operator.

## The unbounded spectral theorem

For an unbounded self-adjoint operator $A$, the same symbolic formula

$$
A=\int_{\mathbb R}\lambda\,dE_A(\lambda)
$$

is correct, but its meaning includes a domain.

The domain of $A$ is

$$
D(A)=\left\{\psi\in\mathcal H\,\middle|\,
\int_{\mathbb R}\lambda^2\,d\mu_\psi(\lambda)<\infty
\right\}.
$$

For $\psi\in D(A)$, the vector $A\psi$ is defined by the spectral integral. More generally, for a Borel function $f$, the operator $f(A)$ has domain

$$
D(f(A))=\left\{\psi\in\mathcal H\,\middle|\,
\int_{\mathbb R}|f(\lambda)|^2\,d\mu_\psi(\lambda)<\infty
\right\}.
$$

This is the domain rule that keeps infinite-dimensional formulas honest. For example, even if $A$ is self-adjoint, $A^2$ is not defined on all of $D(A)$; it is defined on vectors for which

$$
\int_{\mathbb R}\lambda^4\,d\mu_\psi(\lambda)<\infty.
$$

Physicists often write $f(A)$ as if it acts on every state. The actual rule is:

$$
\text{large growth of }f(\lambda)
\quad\Rightarrow\quad
\text{smaller domain of }f(A).
$$

Bounded functions are gentle. If $f$ is bounded, then $f(A)$ is a bounded operator on all of $\mathcal H$, even when $A$ itself is unbounded. That is why

$$
e^{-itA}
$$

is everywhere defined and unitary for self-adjoint $A$, while $A$ itself may be defined only on a dense domain.

## Functional calculus

Functional calculus is the process of defining functions of an operator by acting on its spectrum:

$$
f(A)=\int f(\lambda)\,dE_A(\lambda).
$$

It turns spectral data into useful operators.

For a self-adjoint Hamiltonian $H$, the function $f(\lambda)=e^{-it\lambda}$ gives

$$
U(t)=e^{-itH}.
$$

Since $|e^{-it\lambda}|=1$, the operator $U(t)$ is unitary. This is Stone's theorem in spectral clothing: a self-adjoint Hamiltonian generates unitary time evolution.

For a nonnegative self-adjoint operator $A\ge0$, the function $f(\lambda)=e^{-s\lambda}$ gives the heat semigroup

$$
e^{-sA},
\qquad s>0.
$$

This is central for heat-kernel regularization, index theory, one-loop determinants, and Euclidean free-field correlators.

For $z\notin\sigma(A)$, the function

$$
f_z(\lambda)=\frac{1}{\lambda-z}
$$

gives the resolvent

$$
(A-z)^{-1}=\int_{\mathbb R}\frac{1}{\lambda-z}\,dE_A(\lambda).
$$

If $\operatorname{Im}z\ne0$, then

$$
\|(A-z)^{-1}\|\le \frac{1}{|\operatorname{Im}z|}.
$$

This estimate is one reason resolvents are easier analytic objects than the original unbounded operator.

For a positive operator with suitable spectral behavior, the function $f(\lambda)=\log\lambda$ appears in determinant formulas:

$$
\log\det A \sim \operatorname{Tr}\log A.
$$

The symbol $\sim$ is doing work here. In infinite dimensions, traces and determinants require extra hypotheses or a regulator. The spectral theorem supplies the raw functional calculus; trace-class, heat-kernel, zeta, or Fredholm assumptions decide whether the trace or determinant exists.

## Spectrum through the spectral measure

For a self-adjoint operator, the spectrum is the support of the spectral measure. Informally, $\lambda$ lies in $\sigma(A)$ if every neighborhood of $\lambda$ has nonzero spectral projection.

The spectrum decomposes into several useful pieces.

The **point spectrum** consists of eigenvalues. A number $\lambda$ is an eigenvalue if there exists a nonzero vector $\psi\in D(A)$ such that

$$
A\psi=\lambda\psi.
$$

Equivalently,

$$
E_A(\{\lambda\})\ne0.
$$

The projection $E_A(\{\lambda\})$ is the projection onto the eigenspace.

The **continuous spectrum** consists of spectral values that are not eigenvalues but cannot be removed from the spectrum. The free momentum operator on $L^2(\mathbb R)$ is the standard example. There are no normalizable eigenvectors with sharp momentum, yet the spectrum is the whole real line.

For self-adjoint operators, the residual spectrum is absent. This is one of the benefits of self-adjointness: the spectral alternatives are much cleaner than for general closed operators.

The spectral theorem also lets one write a vector as a direct integral over spectral values. In physics language, this is the correct version of decomposing a state into energy or momentum components.

## Example: multiplication operators

The most transparent model of the spectral theorem is a multiplication operator. Let

$$
\mathcal H=L^2(X,\mu),
$$

and let $a:X\to\mathbb R$ be a measurable function. Define

$$
(A\psi)(x)=a(x)\psi(x).
$$

The natural domain is

$$
D(A)=\{\psi\in L^2(X,\mu)\mid a\psi\in L^2(X,\mu)\}.
$$

Then $A$ is self-adjoint. Its spectral projections are also multiplication operators:

$$
(E_A(\Delta)\psi)(x)=\mathbf 1_{a^{-1}(\Delta)}(x)\psi(x).
$$

In words, $E_A(\Delta)$ keeps only the part of the wavefunction supported where $a(x)\in\Delta$.

Functional calculus is immediate:

$$
(f(A)\psi)(x)=f(a(x))\psi(x).
$$

Many spectral-theorem proofs show that every self-adjoint operator is unitarily equivalent to a multiplication operator of this type, possibly with multiplicity. That is why the multiplication example is not merely an example. It is the normal form.

## Example: momentum and Fourier transform

On $L^2(\mathbb R)$, define

$$
P=-i\frac{d}{dx}
$$

with its standard self-adjoint domain $H^1(\mathbb R)$. Under the Fourier transform convention

$$
\widetilde\psi(p)=\int_{\mathbb R}dx\,e^{-ipx}\psi(x),
$$

the momentum operator becomes multiplication by $p$:

$$
\widetilde{P\psi}(p)=p\widetilde\psi(p).
$$

Thus

$$
P=\mathcal F^{-1}M_p\mathcal F,
$$

where $M_p$ multiplies by $p$.

The spectral projection $E_P(\Delta)$ is therefore

$$
E_P(\Delta)=\mathcal F^{-1}\mathbf 1_\Delta(p)\mathcal F.
$$

It projects onto wavefunctions whose Fourier support lies in $\Delta$. This is a rigorous version of “restrict the state to momenta in $\Delta$.”

The generalized eigenvectors $e^{ipx}$ are not elements of $L^2(\mathbb R)$. They are distributions. The spectral theorem does not require them to be Hilbert-space vectors; it works directly with the projection-valued measure.

## Example: Laplacian on a box

Let $A=-d^2/dx^2$ on $L^2([0,L])$ with Dirichlet boundary conditions

$$
\psi(0)=\psi(L)=0.
$$

The eigenfunctions are

$$
e_n(x)=\sqrt{\frac{2}{L}}\sin\frac{n\pi x}{L},
\qquad n=1,2,\dots,
$$

and the eigenvalues are

$$
\lambda_n=\left(\frac{n\pi}{L}\right)^2.
$$

The spectral resolution is discrete:

$$
A=\sum_{n=1}^\infty \lambda_n |e_n\rangle\langle e_n|.
$$

For a function $f$,

$$
f(A)=\sum_{n=1}^\infty f(\lambda_n)|e_n\rangle\langle e_n|,
$$

with domain determined by

$$
\sum_{n=1}^\infty |f(\lambda_n)|^2|\langle e_n,\psi\rangle|^2<\infty.
$$

This is the kind of formula behind finite-volume mode sums, Casimir energies, heat traces, and zeta functions.

## Example: positive square roots

If $A$ is nonnegative and self-adjoint, meaning

$$
\langle\psi,A\psi\rangle\ge0
$$

for all $\psi\in D(A)$, then $\sigma(A)\subseteq[0,\infty)$. The spectral theorem defines a unique nonnegative self-adjoint square root

$$
A^{1/2}=\int_0^\infty \sqrt\lambda\,dE_A(\lambda).
$$

This construction is everywhere in QFT. For a free scalar field, the one-particle frequency operator is formally

$$
\omega=\sqrt{-\nabla^2+m^2}.
$$

On flat space, the Fourier transform turns this into multiplication by

$$
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

On a curved spatial manifold or in a background potential, the same expression is interpreted spectrally. One first defines the nonnegative self-adjoint operator $-\nabla^2+m^2$ with appropriate domain and boundary conditions, then applies the square-root functional calculus.

## Normal operators and unitary operators

The self-adjoint theorem is the version most used for observables. There is also a spectral theorem for normal operators. A bounded operator $N$ is normal if

$$
NN^*=N^*N.
$$

Then $N$ has a projection-valued spectral measure on $\mathbb C$:

$$
N=\int_{\sigma(N)} z\,dE_N(z).
$$

Self-adjoint operators are normal with real spectrum. Unitary operators are normal with spectrum on the unit circle:

$$
U^*U=UU^*=\mathbf 1,
\qquad
\sigma(U)\subseteq S^1.
$$

This is useful when studying time-evolution operators directly, lattice transfer matrices, Floquet operators, scattering matrices, and Wilson-loop operators in finite-dimensional or regulated settings.

For unbounded normal operators, the theorem also exists, but the domain bookkeeping is heavier. For the QFT pages, the most important case is self-adjoint operators and their exponentials.

## Relation to Green functions and propagators

A Green function is often an inverse kernel for an operator. Spectral theory explains when that inverse exists and how singularities appear.

Suppose $A$ is self-adjoint. The resolvent is

$$
R(z)=(A-z)^{-1}
=\int\frac{1}{\lambda-z}\,dE_A(\lambda).
$$

If $z$ approaches the spectrum, the denominator becomes singular. This is the spectral origin of poles, branch cuts, thresholds, and discontinuities in propagators.

For a discrete eigenvalue $\lambda_n$, the resolvent contains a pole-like contribution

$$
\frac{P_n}{\lambda_n-z}.
$$

For continuous spectrum, it has a cut-like structure. Matrix elements take the form

$$
\langle\psi,R(z)\phi\rangle
=\int\frac{1}{\lambda-z}\,d\mu_{\psi,\phi}(\lambda).
$$

The discontinuity across the real axis recovers spectral density data. This is the analytic pattern behind Källén–Lehmann representations, dispersion relations, and many inverse-operator formulas.

In Minkowski QFT, the $i\epsilon$ prescription chooses boundary values of such resolvents or propagators. The spectral theorem supplies the real spectral measure; physics supplies the boundary condition appropriate to time ordering, retarded response, advanced response, or Euclidean continuation.

## Relation to QFT

The spectral theorem enters QFT in several recurring ways.

**Hamiltonians and time evolution.** If $H$ is self-adjoint, then

$$
U(t)=e^{-itH}
$$

is unitary. This is the analytic meaning of time evolution in canonical quantum theory.

**Energy projectors.** The projection

$$
E_H([E_1,E_2])
$$

selects states with energies in a chosen window. In finite volume this may be a sum over eigenstates; in infinite volume it may include continuous spectral bands.

**Spectral representations.** Two-point functions can often be written as integrals over spectral measures. Positivity of the Hilbert space becomes positivity of the spectral density.

**Free fields.** The one-particle Hamiltonian of a free scalar field is obtained by applying a square root to a positive spatial operator. Mode expansions are spectral decompositions in friendly clothing.

**Heat kernels.** Euclidean one-loop calculations use

$$
\operatorname{Tr}e^{-sA}
$$

for suitable positive operators. The trace may diverge as $s\to0^+$, but the operator $e^{-sA}$ itself is defined by functional calculus.

**Determinants.** Formal expressions like

$$
\det A=\prod_n\lambda_n
$$

are spectral expressions. In infinite dimensions they require regularization, but the spectral theorem is still the starting point.

**Scattering and thresholds.** Continuous spectrum is the home of scattering states. The singularity structure of resolvents and Green functions encodes physical thresholds.

## Common pitfalls

**Thinking the spectral theorem always gives an eigenbasis.** It gives a projection-valued measure. A discrete eigenbasis is a special case.

**Ignoring the domain in the unbounded case.** The formula $A=\int\lambda\,dE_A(\lambda)$ includes the domain condition $\int\lambda^2d\mu_\psi<\infty$.

**Treating plane waves as normalizable vectors.** Plane waves are generalized eigenvectors. They are useful, but the Hilbert-space theorem is stated in terms of spectral projections.

**Confusing the spectrum with measurement outcomes in one state.** The spectrum is an operator-level object. A particular state $\psi$ sees only the measure $\mu_\psi$.

**Applying arbitrary functions without checking domains.** If $f$ is unbounded, then $f(A)$ is usually unbounded and has a proper domain.

**Taking traces too early.** Functional calculus defines $f(A)$; it does not guarantee that $\operatorname{Tr}f(A)$ exists.

**Forgetting boundary conditions.** A differential expression becomes a spectral object only after one chooses a self-adjoint realization, including its domain and boundary conditions.

## Exercises

### Exercise 1: Recover the finite-dimensional formula

Let $A$ be a Hermitian matrix with distinct eigenvalues $\lambda_j$ and normalized eigenvectors $e_j$. Define

$$
E_A(\Delta)=\sum_{\lambda_j\in\Delta}|e_j\rangle\langle e_j|.
$$

Show that

$$
A=\int\lambda\,dE_A(\lambda)
$$

reduces to

$$
A=\sum_j\lambda_j|e_j\rangle\langle e_j|.
$$

<details><summary><strong>Solution</strong></summary>

The measure $E_A$ has atoms at the eigenvalues. Integrating the function $\lambda$ against this projection-valued atomic measure gives the sum over the atoms:

$$
\int\lambda\,dE_A(\lambda)
=\sum_j \lambda_j E_A(\{\lambda_j\})
=\sum_j\lambda_j|e_j\rangle\langle e_j|.
$$

This is exactly the usual diagonalization formula.

</details>

### Exercise 2: Spectral projections for multiplication by x

Let $X$ be the multiplication operator on $L^2(\mathbb R)$,

$$
(X\psi)(x)=x\psi(x).
$$

Show that the spectral projection $E_X([a,b])$ acts as multiplication by the characteristic function $\mathbf 1_{[a,b]}(x)$.

<details><summary><strong>Solution</strong></summary>

For a multiplication operator $X=M_x$, the spectral projection for a set $\Delta$ keeps the part of the function where $x\in\Delta$:

$$
(E_X(\Delta)\psi)(x)=\mathbf 1_\Delta(x)\psi(x).
$$

Taking $\Delta=[a,b]$ gives

$$
(E_X([a,b])\psi)(x)=\mathbf 1_{[a,b]}(x)\psi(x).
$$

This projection is orthogonal because multiplication by $\mathbf 1_{[a,b]}$ is self-adjoint and idempotent.

</details>

### Exercise 3: Domain of a multiplication operator

Let $A$ be multiplication by $x$ on $L^2(\mathbb R)$. Show that

$$
D(A)=\left\{\psi\in L^2(\mathbb R)\mid \int_{\mathbb R}x^2|\psi(x)|^2dx<\infty\right\}.
$$

<details><summary><strong>Solution</strong></summary>

By definition, $\psi\in D(A)$ exactly when $A\psi\in L^2(\mathbb R)$. Since

$$
(A\psi)(x)=x\psi(x),
$$

this condition is

$$
\int_{\mathbb R}|x\psi(x)|^2dx<\infty.
$$

Equivalently,

$$
\int_{\mathbb R}x^2|\psi(x)|^2dx<\infty.
$$

</details>

### Exercise 4: Unitary evolution from the spectral theorem

Let $H=H^*$. Use the spectral theorem to show that

$$
U(t)=e^{-itH}
$$

is unitary.

<details><summary><strong>Solution</strong></summary>

By functional calculus,

$$
U(t)=\int e^{-it\lambda}\,dE_H(\lambda).
$$

The adjoint is

$$
U(t)^*=\int e^{it\lambda}\,dE_H(\lambda).
$$

Using multiplicativity of the functional calculus,

$$
U(t)^*U(t)
=\int e^{it\lambda}e^{-it\lambda}\,dE_H(\lambda)
=\int 1\,dE_H(\lambda)
=\mathbf 1.
$$

Similarly $U(t)U(t)^*=\mathbf 1$. Hence $U(t)$ is unitary.

</details>

### Exercise 5: Resolvent norm estimate

Let $A=A^*$ and let $z\in\mathbb C$ with $\operatorname{Im}z\ne0$. Show that

$$
\|(A-z)^{-1}\|\le \frac{1}{|\operatorname{Im}z|}.
$$

<details><summary><strong>Solution</strong></summary>

By the spectral theorem,

$$
(A-z)^{-1}=\int \frac{1}{\lambda-z}\,dE_A(\lambda).
$$

For a bounded Borel function $f$, the operator norm of $f(A)$ is bounded by $\sup_{\lambda\in\sigma(A)}|f(\lambda)|$. Here

$$
\left|\frac{1}{\lambda-z}\right|
=\frac{1}{|\lambda-z|}.
$$

Since $\lambda$ is real,

$$
|\lambda-z|\ge |\operatorname{Im}z|.
$$

Therefore

$$
\|(A-z)^{-1}\|
\le \sup_{\lambda\in\mathbb R}\frac{1}{|\lambda-z|}
\le \frac{1}{|\operatorname{Im}z|}.
$$

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis* and *II: Fourier Analysis, Self-Adjointness*. Standard references for the spectral theorem, functional calculus, and self-adjoint operators.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. A clear route through spectral measures, Schrödinger operators, and resolvents.
- B. C. Hall, *Quantum Theory for Mathematicians*. Useful for the spectral theorem, Stone's theorem, and operator domains.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. A detailed physics-friendly treatment of self-adjoint operators and spectral methods.
- J. von Neumann, *Mathematical Foundations of Quantum Mechanics*. Classic source for the operator-theoretic foundations of quantum mechanics.
- K. Yosida, *Functional Analysis*. A classic functional-analysis reference.
- M. Srednicki, *Quantum Field Theory*. Useful for spectral representations and functional determinants in practical QFT.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for Hilbert-space, representation-theoretic, and spectral ideas in relativistic QFT.

## Version history

- 2026-06-25: Initial polished draft.
