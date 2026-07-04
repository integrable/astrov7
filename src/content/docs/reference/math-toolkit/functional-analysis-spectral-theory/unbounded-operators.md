---
title: "Unbounded Operators"
description: "Explains densely defined unbounded operators on Hilbert spaces, including domains, closures, adjoints, graph norms, cores, differential expressions, quadratic forms, and QFT domain warnings."
sidebar:
  label: "Unbounded Operators"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard functional-analysis and mathematical-physics references, including Reed–Simon, Teschl, Hall, Moretti, Yosida, Kato, and operator-domain discussions in quantum mechanics and QFT."
topics:
  - unbounded operators
  - densely defined operators
  - domains
  - closed operators
  - closable operators
  - graph norm
  - operator cores
  - adjoints
  - differential operators
  - quadratic forms
  - creation and annihilation operators
canonicalTopics:
  - unbounded-operator
  - densely-defined-operator
  - operator-domain
  - closed-operator
  - closable-operator
  - graph-norm
  - core-of-an-operator
  - adjoint-operator
  - differential-operator
  - quadratic-form
researchStatus:
  established:
    - "The theory of densely defined closed and closable unbounded operators is the standard framework for Hamiltonians, momenta, differential operators, and field-theoretic generators."
  active:
    - "Interacting QFT often requires operator-valued distributions, renormalized composite operators, local algebras, and domain choices that go beyond the elementary examples on this page."
---

## Summary

An unbounded operator is a linear operator that is not controlled by a global estimate of the form

$$
\|A\psi\|\le C\|\psi\|.
$$

The crucial point is not that such operators are large. The crucial point is that they cannot be treated as everywhere-defined matrices. Hamiltonians, momenta, positions, Laplacians, creation and annihilation operators, number operators, Dirac operators, and local quantum fields are all naturally unbounded. Their domains are part of their definition.

The safe object is therefore

$$
A:D(A)\subseteq\mathcal H\to\mathcal K,
$$

not merely the formal rule $\psi\mapsto A\psi$. A differential expression such as $-d^2/dx^2$ becomes different operators when supplied with different boundary conditions. A momentum operator on a line and a momentum operator on a half-line behave differently even though both are written $-i\,d/dx$. In field theory, this domain dependence is the analytic shadow of boundary conditions, zero modes, gauge constraints, and ultraviolet singularities.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing a formal rule, choice of dense domain, graph, graph norm, closure, adjoint, boundary data, and self-adjoint realizations of an unbounded operator.](/figures/math-toolkit/unbounded-operator-closure-flow.svg)

<figcaption>

An unbounded operator is not just a formula. One starts from a formal rule on a dense domain, studies the graph and graph norm, takes a closure when possible, forms the adjoint, and then asks whether boundary or extension data produce a self-adjoint operator. This is the route from formal differential expressions to physical Hamiltonians and generators.

</figcaption>
</figure>

This page is the bridge from [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/) to [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/). The slogan is

$$
\text{unbounded operator} = \text{linear rule} + \text{domain discipline}.
$$

## Prerequisites

You should know Hilbert spaces, dense subspaces, bounded linear operators, graphs, and adjoints from [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/) and [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/). For distributional examples, see [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), and [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/). For QFT determinants built from differential operators, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/).

## Core idea

A bounded operator on a Hilbert space is continuous and defined everywhere. An unbounded operator must be defined on a proper subspace. This is not a technicality that mathematicians add after the physics is done; it changes the physics.

For example, on $L^2([0,L])$ the formal expression

$$
P=-i\frac{d}{dx}
$$

may be equipped with the domain

$$
D(P_\theta)=\{\psi\in H^1([0,L])\mid \psi(L)=e^{i\theta}\psi(0)\},
$$

where $\theta\in\mathbb R/2\pi\mathbb Z$. Different $\theta$ give different momentum spectra,

$$
p_n=\frac{2\pi n+\theta}{L},
\qquad n\in\mathbb Z.
$$

The formula is the same, but the operator is not.

This is why the domain cannot be postponed. If $A$ is supposed to represent an observable or generator of time evolution, its domain and self-adjointness determine whether the spectral theorem applies and whether $e^{-itA}$ is unitary. If $A$ is supposed to be inverted, its domain and kernel determine the Green function. If $A$ enters a determinant, its spectrum, zero modes, and boundary conditions determine the determinant.

A useful mental model is:

| Finite-dimensional reflex | Infinite-dimensional repair |
|---|---|
| An operator is a matrix. | An operator is a domain-equipped map. |
| Hermitian means equal to its conjugate transpose. | Symmetric and self-adjoint are different domain statements. |
| Every linear map is continuous. | Unbounded operators are discontinuous and cannot be everywhere defined. |
| Boundary conditions are extra physics. | Boundary conditions are part of the operator. |
| Commutators are algebraic. | Commutators require a common invariant domain. |

The rest of this page explains the repair kit.

## Definitions

Let $\mathcal H$ and $\mathcal K$ be Hilbert spaces. A linear operator from $\mathcal H$ to $\mathcal K$ is a linear map

$$
A:D(A)\subseteq\mathcal H\to\mathcal K
$$

defined on a linear subspace $D(A)$, called its domain.

The operator is **bounded** if $D(A)=\mathcal H$ and

$$
\|A\|=\sup_{\psi\ne 0}\frac{\|A\psi\|}{\|\psi\|}<\infty.
$$

It is **unbounded** if no such global finite bound exists on a full Hilbert-space domain. In practice, one usually studies unbounded operators whose domains are dense:

$$
\overline{D(A)}=\mathcal H.
$$

Dense domains matter because they let the Hilbert-space inner product determine adjoints uniquely. If $D(A)$ were not dense, there would be nonzero vectors orthogonal to the whole domain, and the adjoint relation would not pin down a unique vector.

The graph of $A$ is

$$
\Gamma(A)=\{(\psi,A\psi)\mid \psi\in D(A)\}\subseteq\mathcal H\oplus\mathcal K.
$$

The operator is **closed** if $\Gamma(A)$ is a closed subspace of $\mathcal H\oplus\mathcal K$. Equivalently, if

$$
\psi_n\to\psi,
\qquad
A\psi_n\to\eta,
$$

then $\psi\in D(A)$ and $A\psi=\eta$.

The operator is **closable** if it has a closed extension. Its smallest closed extension, when it exists, is its closure $\overline A$.

An operator $B$ is an **extension** of $A$, written

$$
A\subset B,
$$

if

$$
D(A)\subseteq D(B),
\qquad
B\psi=A\psi\quad \text{for all }\psi\in D(A).
$$

This notation is extremely useful. It says that an operator is its graph: $A\subset B$ means $\Gamma(A)\subseteq\Gamma(B)$.

## Why unbounded operators cannot be everywhere defined

A first shock: a useful closed unbounded operator cannot be defined on all of a Hilbert space.

The reason is the closed graph theorem. If $\mathcal H$ and $\mathcal K$ are Banach spaces and a linear operator

$$
A:\mathcal H\to\mathcal K
$$

is defined everywhere and has a closed graph, then $A$ is bounded.

So if an operator is unbounded and closed, its domain must be a proper subspace:

$$
D(A)\ne\mathcal H.
$$

This fact is one of the main antidotes to matrix intuition. A Hamiltonian may be a perfectly good self-adjoint operator, but not every vector in the Hilbert space has finite energy. A state can be normalizable without lying in the domain of $H$. It can even be normalizable without lying in the domain of $H^2$, which means its energy expectation or variance may be ill-defined.

For example, on $L^2(\mathbb R)$ the position operator

$$
(X\psi)(x)=x\psi(x)
$$

has domain

$$
D(X)=\{\psi\in L^2(\mathbb R)\mid x\psi(x)\in L^2(\mathbb R)\}.
$$

A wavefunction may be square-integrable while $x\psi$ is not square-integrable. Such a vector is a legitimate Hilbert-space vector, but it is not in the domain of $X$. The expectation value $\langle\psi,X\psi\rangle$ is not automatically meaningful.

## Graph norm

For an operator $A:D(A)\subseteq\mathcal H\to\mathcal K$, the graph norm is

$$
\|\psi\|_A=\sqrt{\|\psi\|_{\mathcal H}^2+\|A\psi\|_{\mathcal K}^2},
\qquad \psi\in D(A).
$$

This norm measures both the size of the vector and the size of its image under $A$.

An operator is closed exactly when $D(A)$ is complete in the graph norm. Thus $D(A)$ can be a Hilbert space in its own right, with inner product

$$
\langle\psi,\phi\rangle_A=\langle\psi,\phi\rangle_{\mathcal H}+\langle A\psi,A\phi\rangle_{\mathcal K}.
$$

This is why Sobolev spaces appear so naturally as domains of differential operators. For the derivative operator on $L^2(\mathbb R)$, the graph norm is equivalent to an $H^1$ norm:

$$
\|\psi\|^2+\|\psi'\|^2.
$$

For the Laplacian, the graph norm resembles an $H^2$ norm, modulo boundary and elliptic-regularity details.

The graph norm also defines a **core**. A subspace $\mathcal C\subseteq D(A)$ is a core for $A$ if the closure of $A|_{\mathcal C}$ is $A$. Equivalently, $\mathcal C$ is dense in $D(A)$ with respect to the graph norm. In practice, one often proves statements on a convenient core such as $C_c^\infty(\mathbb R^d)$ or the Schwartz space $\mathcal S(\mathbb R^d)$, then extends them to the closed operator.

Dense in $\mathcal H$ is not enough. A core must be dense in the graph norm. This is a common source of quiet mistakes.

## Adjoints of unbounded operators

Let $A:D(A)\subseteq\mathcal H\to\mathcal K$ be densely defined. A vector $\phi\in\mathcal K$ lies in $D(A^*)$ if there exists a vector $\eta\in\mathcal H$ such that

$$
\langle A\psi,\phi\rangle_{\mathcal K}=\langle\psi,\eta\rangle_{\mathcal H}
$$

for every $\psi\in D(A)$. Then

$$
A^*\phi=\eta.
$$

The vector $\eta$ is unique because $D(A)$ is dense.

For bounded operators, the adjoint is defined everywhere. For unbounded operators, $D(A^*)$ can be a proper subspace, and its domain must be computed. This is where boundary terms enter.

For a differential operator, integration by parts gives a formal adjoint plus boundary terms. The domain of the adjoint consists of functions for which the integration-by-parts identity can be represented by an $L^2$ function. The difference between $A$ and $A^*$ is therefore often controlled by a boundary form.

For example, consider

$$
P_0=-i\frac{d}{dx}
$$

on $L^2([0,L])$ with domain $C_c^\infty(0,L)$. Its adjoint is the same formal derivative on the larger domain

$$
D(P_0^*)=H^1([0,L]).
$$

The boundary term is

$$
\langle P_0^*\psi,\phi\rangle-\langle\psi,P_0^*\phi\rangle
=i\left[\overline{\psi(x)}\phi(x)\right]_{0}^{L}.
$$

Self-adjoint boundary conditions are precisely those that kill this boundary form on a maximal domain. That is why the self-adjoint momentum operators on the interval are labeled by the phase condition

$$
\psi(L)=e^{i\theta}\psi(0).
$$

## Closed versus merely defined

A formula on a dense test domain is often too small to be the final operator. The derivative on $C_c^\infty(\mathbb R)$ is densely defined but not closed. Its closure has domain $H^1(\mathbb R)$. The Laplacian on $C_c^\infty(\mathbb R^d)$ closes to a self-adjoint operator with a Sobolev domain, under standard choices.

This pattern is so common that it deserves a name:

$$
\text{nice test domain} \longrightarrow \text{minimal operator} \longrightarrow \text{closure or self-adjoint extension}.
$$

The minimal operator is often the operator initially defined on $C_c^\infty$ by a formal differential expression. The maximal operator is usually the adjoint of the minimal one. Boundary conditions select operators between them.

If $A$ is closable, then $A\subseteq\overline A\subseteq A^*$ when $A$ is symmetric. If $A$ is not closable, it is usually not a good candidate for a physical observable or generator.

A useful criterion: if $A$ is densely defined, then $A$ is closable if and only if $D(A^*)$ is dense. In that case,

$$
\overline A=A^{**}.
$$

## Examples

### Position on the real line

On $\mathcal H=L^2(\mathbb R)$, define

$$
(X\psi)(x)=x\psi(x),
$$

with domain

$$
D(X)=\{\psi\in L^2(\mathbb R)\mid x\psi\in L^2(\mathbb R)\}.
$$

This operator is unbounded and self-adjoint. It is a multiplication operator by a real measurable function. Its spectrum is continuous and equals $\mathbb R$.

The domain condition is physically meaningful. It says the state has finite second moment of position. Normalization alone does not guarantee that.

### Momentum on the real line

On $L^2(\mathbb R)$, the momentum operator is

$$
P=-i\frac{d}{dx},
$$

with domain

$$
D(P)=H^1(\mathbb R).
$$

In Fourier variables, $P$ becomes multiplication by $p$:

$$
\widetilde{P\psi}(p)=p\widetilde\psi(p).
$$

Thus

$$
D(P)=\{\psi\in L^2(\mathbb R)\mid p\widetilde\psi(p)\in L^2(\mathbb R)\}.
$$

This operator is unbounded and self-adjoint. The smaller operator on $\mathcal S(\mathbb R)$ or $C_c^\infty(\mathbb R)$ is not closed, but it is essentially self-adjoint: its closure is the self-adjoint momentum operator.

### Momentum on a half-line

On $L^2(0,\infty)$, the same formal rule

$$
P_0=-i\frac{d}{dx},
\qquad D(P_0)=C_c^\infty(0,\infty),
$$

is symmetric, but it has no self-adjoint extension. Intuitively, translations generated by momentum do not preserve the half-line: a wave packet translated left can fall off the boundary. This intuition is made precise by deficiency indices in the next page.

This is a lovely example of a physically obvious fact hiding inside a domain theorem. The formula $-i\,d/dx$ did not change. The configuration space did.

### Laplacian with boundary conditions

On an interval or region $\Omega$, the formal operator

$$
-\Delta
$$

becomes different self-adjoint operators depending on boundary conditions. Common examples are Dirichlet,

$$
\psi|_{\partial\Omega}=0,
$$

Neumann,

$$
\partial_n\psi|_{\partial\Omega}=0,
$$

and Robin,

$$
\partial_n\psi+\alpha\psi=0\quad \text{on }\partial\Omega.
$$

These choices change eigenvalues, heat kernels, Green functions, Casimir energies, and determinants. Boundary conditions are not an afterthought; they are part of the operator whose determinant or inverse is being computed.

### Harmonic oscillator

The harmonic oscillator Hamiltonian

$$
H=\frac{1}{2}(P^2+X^2)
$$

is unbounded but self-adjoint on an appropriate domain. Its eigenvectors $|n\rangle$ satisfy

$$
H|n\rangle=\left(n+\frac12\right)|n\rangle.
$$

The annihilation and creation operators

$$
a=\frac{1}{\sqrt2}(X+iP),
\qquad
a^\dagger=\frac{1}{\sqrt2}(X-iP)
$$

are also unbounded. They are not defined on every vector of the oscillator Hilbert space. If

$$
\psi=\sum_{n=0}^\infty c_n |n\rangle,
$$

then

$$
a\psi=\sum_{n=1}^\infty \sqrt n\,c_n|n-1\rangle
$$

exists in the Hilbert space only when

$$
\sum_{n=1}^\infty n|c_n|^2<\infty.
$$

Again: a normalizable state need not be in the domain of $a$ or $a^\dagger$.

### Number operator and Fock space

On bosonic Fock space, the number operator $N$ has eigenvalues $0,1,2,\ldots$. If

$$
\Psi=\bigoplus_{n=0}^\infty \Psi_n,
$$

then

$$
N\Psi=\bigoplus_{n=0}^\infty n\Psi_n
$$

is defined on the domain

$$
D(N)=\left\{\Psi\mid \sum_{n=0}^\infty n^2\|\Psi_n\|^2<\infty\right\}.
$$

A Fock-space vector may be normalizable while having infinite expected particle number or while not lying in $D(N)$. This distinction becomes important in infrared problems, coherent states, thermal representations, and algebraic formulations of QFT.

## Differential expressions and boundary data

A differential expression such as

$$
L=-\frac{d^2}{dx^2}+V(x)
$$

does not define a unique operator until one supplies:

| Data | Meaning |
|---|---|
| Hilbert space | Usually $L^2$ with a measure and target bundle. |
| Initial domain | A dense test domain such as $C_c^\infty$. |
| Closure or extension | The closed operator actually used. |
| Boundary conditions | Restrictions at finite boundaries, infinity, defects, or singularities. |
| Regularity | Sobolev requirements implied by the graph norm. |
| Zero-mode treatment | Kernel projection, collective coordinates, or gauge fixing. |

This is why heat-kernel and determinant formulas always hide boundary data. A compact expression like

$$
\log\det L=-\int_0^\infty \frac{dt}{t}\operatorname{Tr}e^{-tL}
$$

only has meaning after $L$ has become a suitable operator. Change the domain, and the trace may change.

In gauge theory, the situation is even more delicate. Gauge redundancy gives zero modes of kinetic operators. One must restrict to a slice, divide by gauge volume, introduce ghosts, or project away zero modes. Analytically, each of these choices modifies domains, kernels, and determinants.

## Quadratic forms

Sometimes the cleanest way to define an operator is through a quadratic form. A quadratic form is a map

$$
q:D(q)\subseteq\mathcal H\to\mathbb R
$$

or a sesquilinear form $q(\psi,\phi)$ on a dense form domain $D(q)$.

For a nonnegative operator $A$, the associated form is

$$
q_A(\psi,\phi)=\langle A^{1/2}\psi,A^{1/2}\phi\rangle,
$$

with

$$
D(q_A)=D(A^{1/2}).
$$

The form domain can be larger than the operator domain. For example, for the Dirichlet Laplacian on a region $\Omega$,

$$
D(q)=H_0^1(\Omega),
\qquad
q(\psi)=\int_\Omega d^dx\,|\nabla\psi|^2,
$$

while the operator domain is roughly $H^2(\Omega)\cap H_0^1(\Omega)$ under regularity assumptions.

This distinction matters in variational arguments. A state can have finite energy form $q(\psi)$ even if $A\psi$ is not an $L^2$ vector. In field theory, action functionals and Gaussian measures often naturally control form norms rather than operator norms.

If a densely defined semibounded symmetric operator is not self-adjoint, its quadratic form may still have a canonical self-adjoint realization, the Friedrichs extension. This is one of the main ways to turn a positive formal differential expression into a self-adjoint Hamiltonian.

## Commutators and common domains

For bounded operators, the commutator

$$
[A,B]=AB-BA
$$

is automatically defined on all of $\mathcal H$. For unbounded operators, the expression only makes sense on vectors satisfying

$$
\psi\in D(BA)\cap D(AB),
$$

where

$$
D(BA)=\{\psi\in D(A)\mid A\psi\in D(B)\}.
$$

Thus canonical commutation relations such as

$$
[X,P]=i
$$

are domain statements, not just algebraic slogans. A safe common domain for $X$ and $P$ on $L^2(\mathbb R)$ is the Schwartz space $\mathcal S(\mathbb R)$, which is invariant under $X$, $P$, and their polynomial combinations. On this domain,

$$
[X,P]\psi=i\psi.
$$

Outside such a domain, blindly moving unbounded operators past each other is sign-hunting with a blindfold on.

The same warning applies to quantum fields. Equal-time commutators are distributional identities after smearing, not pointwise operator equations on the whole Hilbert space.

## Operator-valued distributions in QFT

A local quantum field $\phi(x)$ is usually not an operator at a point. It is an operator-valued distribution. The meaningful object is a smeared field

$$
\phi(f)=\int d^dx\,f(x)\phi(x),
$$

where $f$ is a test function.

Even after smearing, $\phi(f)$ is typically unbounded. It has a dense domain, often containing finite-particle vectors in free-field constructions. Products such as $\phi(x)^2$ require renormalization because multiplying distributions at the same point is singular.

This gives a clean hierarchy:

$$
\text{field symbol }\phi(x)
\quad\rightsquigarrow\quad
\text{smeared operator }\phi(f)
\quad\rightsquigarrow\quad
\text{domain and renormalized products}.
$$

The same logic underlies composite operators, stress tensors, currents, Ward identities, and contact terms. In practice, physicists often compute with formal fields, but the honest mathematical object is smeared and domain-sensitive.

## Practical checklist

When an unbounded operator appears, ask:

1. What is the Hilbert space?
2. What is the domain?
3. Is the domain dense?
4. Is the operator closed or closable?
5. What is its adjoint and adjoint domain?
6. Is it symmetric, self-adjoint, or essentially self-adjoint?
7. Are boundary conditions part of the definition?
8. What is the kernel?
9. Is zero-mode removal required?
10. Is the calculation using the operator domain or only the quadratic-form domain?

For routine physics, this checklist is often overkill. For edge cases—boundaries, singular potentials, gauge zero modes, anomalies, determinants, and infrared sectors—it is exactly the stuff that saves you from nonsense.

## Common pitfalls

**Pitfall 1: Treating a formal differential expression as an operator.** The expression $-d^2/dx^2$ is not yet an operator. It becomes one after choosing a Hilbert space and domain.

**Pitfall 2: Assuming a normalizable vector lies in every operator domain.** Normalization only says $\psi\in\mathcal H$. It does not imply $\psi\in D(X)$, $D(P)$, $D(H)$, or $D(H^2)$.

**Pitfall 3: Confusing dense with core.** A subspace can be dense in $\mathcal H$ without being dense in $D(A)$ in the graph norm. Only the latter makes it a core.

**Pitfall 4: Ignoring boundary terms.** Integration by parts is not free. Boundary terms determine adjoint domains and self-adjoint extensions.

**Pitfall 5: Manipulating commutators without a common domain.** For unbounded operators, $AB-BA$ is meaningful only where both compositions are meaningful.

**Pitfall 6: Calling every symmetric operator an observable.** A physical observable should be represented by a self-adjoint operator, or by a more refined structure such as a POVM or local algebra. Symmetry of matrix elements on a small domain is not enough.

## Exercises

### Exercise 1: Multiplication by an unbounded function

Let $X$ be the multiplication operator on $L^2(\mathbb R)$,

$$
(X\psi)(x)=x\psi(x),
\qquad
D(X)=\{\psi\in L^2(\mathbb R)\mid x\psi\in L^2(\mathbb R)\}.
$$

Show that $X$ is unbounded.

<details><summary><strong>Solution</strong></summary>

Let

$$
\psi_n(x)=\mathbf 1_{[n,n+1]}(x).
$$

Then

$$
\|\psi_n\|^2=\int_n^{n+1}dx=1.
$$

But

$$
\|X\psi_n\|^2=\int_n^{n+1}dx\,x^2\ge n^2.
$$

Thus $\|X\psi_n\|\ge n$ while $\|\psi_n\|=1$. No finite constant $C$ can satisfy $\|X\psi\|\le C\|\psi\|$ on the domain. Therefore $X$ is unbounded.

</details>

### Exercise 2: A normalizable vector outside the position domain

Find a vector in $L^2(\mathbb R)$ that is not in $D(X)$ for $X\psi=x\psi$.

<details><summary><strong>Solution</strong></summary>

Take, for large $|x|$,

$$
\psi(x)=\frac{1}{1+|x|^{3/2}},
$$

with any harmless smooth modification near the origin. Then

$$
|\psi(x)|^2\sim \frac{1}{|x|^3},
$$

so

$$
\int^\infty dx\,|\psi(x)|^2<\infty.
$$

However

$$
|x\psi(x)|^2\sim \frac{x^2}{|x|^3}=\frac{1}{|x|},
$$

and

$$
\int^\infty \frac{dx}{x}
$$

diverges. Hence $\psi\in L^2(\mathbb R)$ but $x\psi\notin L^2(\mathbb R)$, so $\psi\notin D(X)$.

</details>

### Exercise 3: Boundary form for the derivative on an interval

Let

$$
P=-i\frac{d}{dx}
$$

act on $H^1([0,L])$. Show that

$$
\langle P\psi,\phi\rangle-\langle\psi,P\phi\rangle
=i\left[\overline{\psi(x)}\phi(x)\right]_0^L.
$$

Then show that the boundary condition $\psi(L)=e^{i\theta}\psi(0)$ makes this boundary form vanish for any two vectors satisfying the same condition.

<details><summary><strong>Solution</strong></summary>

Using the physics inner-product convention,

$$
\langle P\psi,\phi\rangle
=\int_0^L dx\,\overline{-i\psi'(x)}\phi(x)
=i\int_0^L dx\,\overline{\psi'(x)}\phi(x).
$$

Integrating by parts gives

$$
i\int_0^L dx\,\overline{\psi'}\phi
=i[\overline\psi\phi]_0^L-i\int_0^L dx\,\overline\psi\phi'.
$$

But

$$
\langle\psi,P\phi\rangle
=\int_0^L dx\,\overline\psi(-i\phi')
=-i\int_0^L dx\,\overline\psi\phi'.
$$

Therefore

$$
\langle P\psi,\phi\rangle-\langle\psi,P\phi\rangle
=i[\overline\psi\phi]_0^L.
$$

If $\psi(L)=e^{i\theta}\psi(0)$ and $\phi(L)=e^{i\theta}\phi(0)$, then

$$
\overline{\psi(L)}\phi(L)
=e^{-i\theta}\overline{\psi(0)}e^{i\theta}\phi(0)
=\overline{\psi(0)}\phi(0).
$$

The boundary difference vanishes.

</details>

### Exercise 4: Domain of the annihilation operator

Let $a|n\rangle=\sqrt n|n-1\rangle$ on the harmonic-oscillator basis. For

$$
\psi=\sum_{n=0}^\infty c_n|n\rangle,
$$

show that $\psi\in D(a)$ exactly when

$$
\sum_{n=1}^\infty n|c_n|^2<\infty.
$$

<details><summary><strong>Solution</strong></summary>

Formally,

$$
a\psi=\sum_{n=1}^\infty \sqrt n\,c_n|n-1\rangle.
$$

Using orthonormality and shifting the basis label, its squared norm is

$$
\|a\psi\|^2
=\sum_{n=1}^\infty n|c_n|^2.
$$

Thus $a\psi$ is a Hilbert-space vector exactly when this series is finite.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis* and *II: Fourier Analysis, Self-Adjointness*.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*.
- B. C. Hall, *Quantum Theory for Mathematicians*.
- V. Moretti, *Spectral Theory and Quantum Mechanics*.
- T. Kato, *Perturbation Theory for Linear Operators*.
- M. Stone, *Linear Transformations in Hilbert Space and Their Applications to Analysis*.
- R. Haag, *Local Quantum Physics*, for the operator-algebraic perspective on QFT.

## Version history

- 2026-06-25: Initial polished draft.
