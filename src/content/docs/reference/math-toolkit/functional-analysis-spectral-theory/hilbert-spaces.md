---
title: "Hilbert Spaces"
description: "Defines Hilbert spaces as complete inner-product spaces and explains why completion, orthogonality, bases, duals, tensor products, Fock spaces, and generalized states matter in QFT."
sidebar:
  label: "Hilbert Spaces"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard functional-analysis and mathematical-physics references, including Reed–Simon, Teschl, Hall, Moretti, Yosida, Rudin, Gelfand–Vilenkin, and QFT treatments of one-particle and Fock spaces."
topics:
  - Hilbert spaces
  - inner products
  - completeness
  - orthogonality
  - orthonormal bases
  - projections
  - Riesz representation theorem
  - tensor products
  - Fock spaces
  - rigged Hilbert spaces
canonicalTopics:
  - hilbert-space
  - inner-product-space
  - completion
  - orthonormal-basis
  - projection-theorem
  - riesz-representation
  - tensor-product-hilbert-space
  - fock-space
  - rigged-hilbert-space
researchStatus:
  established:
    - "Hilbert spaces are the standard complete inner-product spaces used for quantum-mechanical state spaces, one-particle spaces, and many free-field constructions."
  active:
    - "Continuum QFT often requires operator algebras, domains, rigged Hilbert spaces, gauge constraints, and local algebraic refinements beyond the elementary Hilbert-space picture."
---

## Summary

A Hilbert space is a complete inner-product space. That small word “complete” is the analytic upgrade from finite-dimensional linear algebra to quantum theory: limits of physically allowed approximations must still be available as vectors in the space. Without completeness, Fourier series, wave-packet limits, variational approximations, spectral decompositions, and unitary time evolution all become suspicious.

Throughout this page, Hilbert spaces are complex unless stated otherwise. The inner product is written in physics convention: $\langle \psi,\phi\rangle$ is conjugate-linear in the first argument and linear in the second. Thus

$$
\langle a\psi+b\chi,\phi\rangle=\overline a\langle\psi,\phi\rangle+\overline b\langle\chi,\phi\rangle,
\qquad
\langle\psi,a\phi+b\chi\rangle=a\langle\psi,\phi\rangle+b\langle\psi,\chi\rangle.
$$

The induced norm is

$$
\|\psi\|=\sqrt{\langle\psi,\psi\rangle}.
$$

In QFT, Hilbert spaces appear at several levels. There is the one-particle Hilbert space, the Fock space built from it, the physical Hilbert space after imposing constraints, the space of normalizable wave packets, and the larger distributional world containing plane waves and field eigenstates. The slogan is

$$
\text{Hilbert space} = \text{inner-product geometry} + \text{enough limits}.
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![Flow diagram showing a pre-Hilbert space with an inner product, the induced norm and metric, completion by Cauchy sequences, the resulting Hilbert space, and related structures: orthonormal bases, dense test spaces, duals, closed subspaces, projections, and Fock spaces.](/figures/math-toolkit/hilbert-space-completion-flow.svg)

<figcaption>

A Hilbert space is obtained by completing an inner-product space in the norm induced by the inner product. Once the space is complete, one can use orthogonal projections, orthonormal expansions, Riesz duality, and Fock-space constructions. Generalized states such as plane waves usually live in a larger rigged Hilbert-space setting $\Phi\subset\mathcal H\subset\Phi'$.

</figcaption>
</figure>

This page fixes the analytic language used later by [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), unbounded operators, self-adjointness, spectral theory, trace ideals, and rigged Hilbert spaces.

## Prerequisites

You should know finite-dimensional complex vector spaces, Hermitian inner products, Cauchy sequences, and basic Fourier series. The chapter overview [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/) explains why these ideas are needed for QFT.

For the distributional language used near the end, see [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/). For the Fourier convention used in examples, see [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/). For functional determinants and heat kernels, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

## Core idea

Finite-dimensional quantum mechanics can make Hilbert spaces look like fancy column-vector spaces. That impression is dangerous. In infinite dimensions, the inner product does three jobs at once:

| Structure | Formula | What it controls |
|---|---|---|
| Norm | $\|\psi\|^2=\langle\psi,\psi\rangle$ | convergence and normalization |
| Orthogonality | $\langle\psi,\phi\rangle=0$ | independent components and projections |
| Duality | $F(\phi)=\langle\psi_F,\phi\rangle$ | bras and continuous linear functionals |
| Geometry | $\|\psi-\phi\|$ | approximation and closure |
| Probability | $|\langle\psi,\phi\rangle|^2$ for normalized states | transition amplitudes |

Completeness says that if a sequence of vectors becomes arbitrarily close to itself, then it converges to an actual vector in the space. More precisely, a sequence $\psi_n$ is Cauchy if

$$
\forall \epsilon>0\ \exists N\ \text{such that}\ m,n>N\Rightarrow \|\psi_m-\psi_n\|<\epsilon.
$$

A Hilbert space is an inner-product space in which every Cauchy sequence converges. This is what makes infinite sums meaningful. For example, if $\{e_n\}$ is an orthonormal basis and $\{c_n\}\in\ell^2$, then

$$
\sum_{n=1}^\infty c_n e_n
$$

converges as a vector of the Hilbert space. Without completeness, the formal series could define a perfectly good limit outside the space one started with. That would be a bit like quantizing with a state space that forgets some of its own limit states. Mathematically rude, physically unwise.

## Definition

A complex Hilbert space $\mathcal H$ is a complex vector space equipped with a map

$$
\langle\cdot,\cdot\rangle:\mathcal H\times\mathcal H\to\mathbb C
$$

such that for all $\psi,\phi,\chi\in\mathcal H$ and $a,b\in\mathbb C$:

$$
\langle\psi,a\phi+b\chi\rangle=a\langle\psi,\phi\rangle+b\langle\psi,\chi\rangle,
$$

$$
\langle\psi,\phi\rangle=\overline{\langle\phi,\psi\rangle},
$$

$$
\langle\psi,\psi\rangle\ge 0,
\qquad
\langle\psi,\psi\rangle=0\Longleftrightarrow \psi=0,
$$

and $\mathcal H$ is complete in the norm $\|\psi\|=\sqrt{\langle\psi,\psi\rangle}$.

The induced distance is

$$
d(\psi,\phi)=\|\psi-\phi\|.
$$

The Cauchy–Schwarz inequality says

$$
|\langle\psi,\phi\rangle|\le \|\psi\|\,\|\phi\|.
$$

The triangle inequality follows from it:

$$
\|\psi+\phi\|\le \|\psi\|+\|\phi\|.
$$

The parallelogram identity is

$$
\|\psi+\phi\|^2+\|\psi-\phi\|^2=2\|\psi\|^2+2\|\phi\|^2.
$$

This identity distinguishes Hilbert-space norms from arbitrary Banach-space norms. A Banach space is complete in some norm; a Hilbert space is complete in a norm that comes from an inner product.

## Pre-Hilbert spaces and completion

An inner-product space that is not necessarily complete is often called a pre-Hilbert space. The standard example in physics is a space of nice test functions, such as $C_c^\infty(\mathbb R^d)$ or the Schwartz space $\mathcal S(\mathbb R^d)$, with the $L^2$ inner product

$$
\langle f,g\rangle=\int_{\mathbb R^d} d^dx\,\overline{f(x)}g(x).
$$

This space is not complete in the $L^2$ norm. Its completion is $L^2(\mathbb R^d)$.

Completion is constructed by taking Cauchy sequences and identifying sequences whose difference goes to zero. Schematically,

$$
\widehat V=\{\text{Cauchy sequences in }V\}/\{\text{zero-distance sequences}\}.
$$

The original space $V$ embeds densely into $\widehat V$ by sending $v\in V$ to the constant sequence $(v,v,v,\ldots)$. Dense means that every vector in $\widehat V$ can be approximated in norm by vectors from $V$.

This is why physicists often compute on a dense set of very nice functions and then extend by continuity. The dense set is the workshop; the Hilbert space is the completed building.

## Basic examples

The finite-dimensional space $\mathbb C^n$ with

$$
\langle z,w\rangle=\sum_{i=1}^n \overline{z_i}w_i
$$

is a Hilbert space. It is the model that finite-dimensional linear algebra teaches us.

The sequence space $\ell^2(\mathbb N)$ consists of complex sequences $a=(a_1,a_2,\ldots)$ such that

$$
\sum_{n=1}^\infty |a_n|^2<\infty.
$$

Its inner product is

$$
\langle a,b\rangle=\sum_{n=1}^\infty \overline{a_n}b_n.
$$

The function space $L^2(X,d\mu)$ consists of equivalence classes of measurable functions $f:X\to\mathbb C$ such that

$$
\int_X d\mu\,|f|^2<\infty.
$$

The phrase “equivalence classes” matters. Two functions that differ only on a set of measure zero represent the same vector of $L^2$. Consequently, a pointwise value $f(x)$ is not an intrinsic property of an $L^2$ vector. When QFT formulas write wavefunctions pointwise, they are usually choosing a representative or working with a smoother dense domain.

The Sobolev space $H^s(\mathbb R^d)$ is a Hilbert space of functions or distributions whose Fourier transforms obey

$$
\int \frac{d^dk}{(2\pi)^d}\,(1+|k|^2)^s |\widetilde f(k)|^2<\infty.
$$

Sobolev spaces become operator domains for differential operators. They are the grown-up version of the phrase “functions with enough derivatives.” See [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/) for the first pass.

A one-particle Hilbert space for a free massive scalar field can be written in momentum variables as

$$
\mathcal H_1=L^2\!\left(\mathbb R^3,\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}\right),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

with inner product

$$
\langle f,g\rangle=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}\,\overline{f(\mathbf p)}g(\mathbf p).
$$

The Lorentz-invariant measure is not decoration; it is part of the Hilbert-space structure.

## Quantum states and rays

A vector $\psi\in\mathcal H$ is often called a state, but physical pure states are really rays:

$$
\psi\sim e^{i\alpha}\psi,
\qquad \alpha\in\mathbb R,
$$

with $\psi\neq 0$. A normalized representative satisfies

$$
\|\psi\|=1.
$$

The transition amplitude from $\psi$ to $\phi$ is $\langle\phi,\psi\rangle$ in common bra-ket notation, and the transition probability is

$$
|\langle\phi,\psi\rangle|^2
$$

for normalized vectors.

For mixed states, one uses density operators rather than rays. A density operator $\rho$ is positive, trace class, and normalized by

$$
\operatorname{Tr}\rho=1.
$$

Trace-class conditions are not automatic in infinite dimensions. They will appear again in the trace-ideal page.

## Orthogonality and projections

Two vectors are orthogonal if

$$
\langle\psi,\phi\rangle=0.
$$

For a subset $S\subset\mathcal H$, its orthogonal complement is

$$
S^\perp=\{\psi\in\mathcal H\mid \langle s,\psi\rangle=0\text{ for all }s\in S\}.
$$

If $M\subset\mathcal H$ is a closed linear subspace, then every vector $\psi\in\mathcal H$ decomposes uniquely as

$$
\psi=P_M\psi+(1-P_M)\psi,
\qquad
P_M\psi\in M,
\qquad
(1-P_M)\psi\in M^\perp.
$$

The map $P_M$ is the orthogonal projection onto $M$. It satisfies

$$
P_M^2=P_M,
\qquad
P_M^*=P_M.
$$

Closedness is essential. Dense proper subspaces are not the same as the whole Hilbert space, but their orthogonal complement is zero. For example, $\mathcal S(\mathbb R^d)$ is dense in $L^2(\mathbb R^d)$, so

$$
\mathcal S(\mathbb R^d)^\perp=\{0\},
$$

but $\mathcal S(\mathbb R^d)\neq L^2(\mathbb R^d)$.

This distinction shows up constantly in QFT. We often define unbounded operators on a dense invariant domain and only later discuss their closures or self-adjoint extensions. Dense is good; closed is different.

## Orthonormal bases

An orthonormal set is a family $\{e_i\}_{i\in I}$ such that

$$
\langle e_i,e_j\rangle=\delta_{ij}.
$$

An orthonormal basis is a maximal orthonormal set, equivalently an orthonormal set whose closed span is all of $\mathcal H$:

$$
\overline{\operatorname{span}\{e_i\}}=\mathcal H.
$$

If $\mathcal H$ is separable, it has a countable orthonormal basis $\{e_n\}_{n=1}^\infty$. Then every vector $\psi\in\mathcal H$ has the expansion

$$
\psi=\sum_{n=1}^\infty e_n\langle e_n,\psi\rangle,
$$

where the sum converges in Hilbert-space norm. Parseval's identity says

$$
\|\psi\|^2=\sum_{n=1}^\infty |\langle e_n,\psi\rangle|^2.
$$

In bra-ket shorthand one writes

$$
1=\sum_n |e_n\rangle\langle e_n|.
$$

The equation is meaningful as a statement about norm convergence on each vector, or more generally strong operator convergence. It is not a finite matrix identity.

For a continuous spectrum, the analogous formula becomes distributional. For example, in $L^2(\mathbb R)$ one often writes

$$
1=\int_{-\infty}^{\infty} dx\,|x\rangle\langle x|,
$$

but $|x\rangle$ is not a normalizable Hilbert-space vector. It is a generalized eigenvector. The rigged Hilbert-space section below explains the typing.

## Riesz representation and bras

The continuous dual $\mathcal H^*$ is the vector space of continuous linear maps

$$
F:\mathcal H\to\mathbb C.
$$

The Riesz representation theorem says that for every continuous linear functional $F\in\mathcal H^*$, there exists a unique vector $\psi_F\in\mathcal H$ such that

$$
F(\phi)=\langle\psi_F,\phi\rangle
$$

for all $\phi\in\mathcal H$. With the physics inner-product convention, the functional is represented by the vector in the first slot. This is the rigorous Hilbert-space content of the bra-ket identification

$$
|\psi\rangle\longleftrightarrow \langle\psi|.
$$

The word continuous is vital. There are many discontinuous linear functionals on infinite-dimensional vector spaces if one allows the axiom of choice. They are almost never physically relevant. More importantly, point evaluation is not a continuous functional on $L^2(\mathbb R^d)$:

$$
f\mapsto f(x)
$$

is not well-defined on $L^2$ equivalence classes. This is one reason distributions and rigged Hilbert spaces enter so quickly.

## Tensor products and composite systems

For two Hilbert spaces $\mathcal H_A$ and $\mathcal H_B$, their algebraic tensor product consists of finite sums

$$
\sum_i \psi_i\otimes\phi_i.
$$

It carries the inner product

$$
\langle \psi_1\otimes\phi_1,\psi_2\otimes\phi_2\rangle
=\langle\psi_1,\psi_2\rangle_A\,\langle\phi_1,\phi_2\rangle_B,
$$

extended sesquilinearly. The Hilbert-space tensor product $\mathcal H_A\widehat\otimes\mathcal H_B$ is the completion of this algebraic tensor product.

For ordinary quantum systems, tensor products describe composites. For example, two spin-$1/2$ systems have Hilbert space

$$
\mathbb C^2\otimes\mathbb C^2.
$$

In continuum QFT, spatial factorization is subtler. It is tempting to write

$$
\mathcal H \overset{?}{=} \mathcal H_R\otimes \mathcal H_{R^c}
$$

for a spatial region $R$ and its complement. This can be a useful regulated or lattice intuition, but the continuum local-algebraic structure is more delicate. Gauge constraints make it more delicate still. So: tensor products are fundamental, but not every physically natural split of spacetime gives a naive tensor factorization.

## Fock spaces

Given a one-particle Hilbert space $\mathcal H_1$, the bosonic Fock space is

$$
\mathcal F_+(\mathcal H_1)=\bigoplus_{n=0}^\infty \operatorname{Sym}^n\mathcal H_1,
$$

and the fermionic Fock space is

$$
\mathcal F_-(\mathcal H_1)=\bigoplus_{n=0}^\infty \wedge^n\mathcal H_1.
$$

The $n=0$ summand is the vacuum sector, canonically isomorphic to $\mathbb C$. A vector in Fock space is a sequence

$$
\Psi=(\Psi_0,\Psi_1,\Psi_2,\ldots),
$$

with $\Psi_n$ in the $n$-particle sector and

$$
\|\Psi\|^2=\sum_{n=0}^\infty \|\Psi_n\|^2<\infty.
$$

Creation and annihilation operators move between the summands. They are usually unbounded operators, so their natural domains are not all of Fock space. This is one of the first places where the next page, [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), becomes unavoidable.

Fock space is perfect for free fields and perturbation theory around a particle vacuum. It is not the universal Hilbert-space construction for every QFT. Interacting theories, gauge theories, thermal representations, curved backgrounds, inequivalent vacua, and algebraic QFT can require representations that are not simply one Fock space built once and for all. Infinite systems have a talent for refusing to fit into one favorite box.

## Dense domains and test spaces

A dense subspace $\Phi\subset\mathcal H$ is often used as a common domain for useful unbounded operators. In flat-space quantum mechanics, a standard choice is

$$
\mathcal S(\mathbb R^d)\subset L^2(\mathbb R^d),
$$

because the Schwartz space is stable under differentiation, multiplication by polynomials, and Fourier transform.

For $\psi\in\mathcal S(\mathbb R)$, the position and momentum operators are

$$
(X\psi)(x)=x\psi(x),
\qquad
(P\psi)(x)=-i\frac{d\psi}{dx}.
$$

Both map $\mathcal S(\mathbb R)$ to itself. On this domain the canonical commutator is exactly

$$
[X,P]\psi=i\psi.
$$

The dense domain lets the formal calculation make sense. The self-adjointness and domain questions come later.

In QFT, fields are often defined first as smeared objects on a dense domain:

$$
\phi(f)=\int d^dx\,f(x)\phi(x).
$$

The test function $f$ tames the distributional dependence on $x$. The dense domain controls on which vectors the operator acts.

## Generalized states and rigged Hilbert spaces

Plane waves are everywhere in QFT, but they are not normalizable vectors of $L^2(\mathbb R^d)$. For example,

$$
e^{i\mathbf p\cdot\mathbf x}\notin L^2(\mathbb R^d),
$$

because

$$
\int_{\mathbb R^d} d^dx\,|e^{i\mathbf p\cdot\mathbf x}|^2=\infty.
$$

Nevertheless, plane waves act naturally as distributions on test functions. This motivates a rigged Hilbert space, also called a Gelfand triple,

$$
\Phi\subset\mathcal H\subset\Phi',
$$

where $\Phi$ is a dense test space and $\Phi'$ is a suitable space of continuous antilinear or linear functionals, depending on convention. A standard example is

$$
\mathcal S(\mathbb R^d)\subset L^2(\mathbb R^d)\subset \mathcal S'(\mathbb R^d).
$$

Position eigenstates $|x\rangle$ and momentum eigenstates $|p\rangle$ live naturally in the distributional side. Their formal normalizations,

$$
\langle x|x'\rangle=\delta(x-x'),
\qquad
\langle p|p'\rangle=(2\pi)^d\delta^{(d)}(p-p'),
$$

are distributional identities, not Hilbert-space inner products between finite-norm vectors.

This viewpoint removes a lot of fake mystery. Plane waves are not illegal; they are just not in the same space as wave packets.

## Separability and basis size

A Hilbert space is separable if it contains a countable dense subset. Most Hilbert spaces used in elementary quantum mechanics and perturbative QFT are separable. Separable Hilbert spaces have countable orthonormal bases.

For a separable infinite-dimensional Hilbert space, all orthonormal bases have the same countable size, and the space is isomorphic to $\ell^2(\mathbb N)$. This does not mean all physical Hilbert spaces are physically the same. Operators, Hamiltonians, symmetry representations, algebras of observables, and domains carry the physics.

The same abstract Hilbert space can support many inequivalent operator structures. “The Hilbert space is $L^2$” is rarely the end of a quantum theory; it is the beginning of the analytic bookkeeping.

## Positive cones and density matrices

A vector norm gives pure states, but statistical mixtures require operators. A bounded operator $A$ on $\mathcal H$ is positive if

$$
\langle\psi,A\psi\rangle\ge 0
$$

for all $\psi\in\mathcal H$. A density operator is a positive trace-class operator with unit trace.

Expectation values are then written

$$
\langle A\rangle_\rho=\operatorname{Tr}(\rho A),
$$

when the product is trace class. In finite dimensions this formula is harmless. In infinite dimensions, trace-class and domain hypotheses matter. Thermal states, reduced density matrices, entanglement entropy, and modular Hamiltonians all live near this boundary between Hilbert-space geometry and operator-algebraic structure.

## Why QFT needs Hilbert spaces but not only Hilbert spaces

Hilbert spaces are indispensable in QFT. They support state vectors, inner products, positive probabilities, unitary time evolution, spectral decompositions, one-particle spaces, and Fock spaces. The Wigner classification of particles is classification of unitary representations on Hilbert spaces. Scattering theory uses asymptotic Hilbert spaces. Canonical quantization uses operators on dense domains. Spectral representations insert complete sets of states.

At the same time, Hilbert spaces alone are not enough. A QFT is not specified merely by saying “choose a Hilbert space.” One also needs observables, locality, symmetry representations, a vacuum or state, dynamics, domains, renormalization, and perhaps gauge constraints. In algebraic language, one often emphasizes local operator algebras and states on those algebras rather than a preferred global Hilbert-space construction.

So the right attitude is balanced:

$$
\text{Hilbert spaces are essential infrastructure, not the whole theory.}
$$

They are the stage on which many quantum formulas make sense, but the play includes operators, algebras, symmetries, spectra, and fields.

## Relations to other pages

- [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/) explains why Hilbert spaces are the first step toward domains, adjoints, self-adjointness, spectral measures, and trace ideals.
- [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/) uses the Hilbert-space norm, inner product, projections, and Riesz theorem to define bounded operators and adjoints.
- [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) explains the distributional objects that appear when plane waves, delta functions, and field operators are written as if they were ordinary vectors or functions.
- [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) fixes the normalizations behind momentum-space bases and completeness relations.
- [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) use Hilbert-space spectra to define one-loop quantities.
- [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) gives a geometric example where Hilbert spaces of sections, kernels, adjoints, and spectra become physical.

## Research status

The Hilbert-space formalism used here is standard mathematics and standard quantum theory. It is the right language for normalizable states, one-particle spaces, Fock spaces of free fields, unitary representations, projections, and spectral decompositions.

The caveats are also standard: continuum QFT is not specified by a Hilbert space alone. Interacting fields, local algebras, gauge constraints, renormalized composite operators, indefinite intermediate state spaces, and entanglement across spatial regions often require denser operator-theoretic or algebraic language. Hilbert space is the stage; the full theory also needs operators, domains, algebras, symmetries, and states.

## Common pitfalls

**Forgetting completeness.** An inner-product space is not automatically a Hilbert space. The missing limits can be exactly the limits that Fourier analysis or variational methods need.

**Treating $L^2$ functions as pointwise functions.** Elements of $L^2$ are equivalence classes modulo measure-zero changes. Pointwise values require extra regularity or a chosen representative.

**Confusing dense with equal.** A dense subspace can approximate every vector, but it can still be a proper subspace. Dense domains are wonderful; they are not the whole Hilbert space.

**Treating plane waves as normalizable states.** Plane waves and position eigenstates are generalized states. Wave packets are Hilbert-space vectors.

**Assuming all infinite sums converge.** An orthonormal expansion converges in norm only when the coefficients are square-summable.

**Assuming tensor factorization for every spatial split.** Lattice models often factorize by sites. Continuum QFT and gauge theory may not factorize in such a naive way.

**Thinking Fock space is the definition of QFT.** Fock space is central for free fields and perturbation theory. It is not the only possible representation of the canonical commutation relations in infinite volume or interacting theories.

## Exercises

### Exercise 1: Cauchy–Schwarz from positivity

Show that for any $\psi,\phi\in\mathcal H$,

$$
|\langle\psi,\phi\rangle|^2\le \|\psi\|^2\|\phi\|^2.
$$

<details><summary><strong>Solution</strong></summary>

If $\phi=0$, the result is immediate. Otherwise, for any $\lambda\in\mathbb C$,

$$
0\le \|\psi-\lambda\phi\|^2
=\|\psi\|^2-\overline\lambda\langle\phi,\psi\rangle-\lambda\langle\psi,\phi\rangle+|\lambda|^2\|\phi\|^2.
$$

Choose

$$
\lambda=\frac{\langle\phi,\psi\rangle}{\|\phi\|^2}.
$$

Then

$$
0\le \|\psi\|^2-\frac{|\langle\phi,\psi\rangle|^2}{\|\phi\|^2},
$$

so

$$
|\langle\psi,\phi\rangle|^2\le \|\psi\|^2\|\phi\|^2.
$$

</details>

### Exercise 2: Plane waves are not Hilbert-space vectors

Using the ordinary Lebesgue measure on $\mathbb R^d$, show that the plane wave $f_{\mathbf p}(\mathbf x)=e^{i\mathbf p\cdot\mathbf x}$ is not an element of $L^2(\mathbb R^d)$.

<details><summary><strong>Solution</strong></summary>

Its modulus is one everywhere:

$$
|f_{\mathbf p}(\mathbf x)|^2=1.
$$

Therefore

$$
\|f_{\mathbf p}\|^2=\int_{\mathbb R^d}d^dx=\infty.
$$

Thus $f_{\mathbf p}$ is not square-integrable. It is better understood as a generalized eigenfunction or distributional object.

</details>

### Exercise 3: Parseval for a finite partial sum

Let $\{e_n\}$ be an orthonormal set and define

$$
\psi_N=\sum_{n=1}^N e_n\langle e_n,\psi\rangle.
$$

Show that

$$
\|\psi-\psi_N\|^2=\|\psi\|^2-\sum_{n=1}^N |\langle e_n,\psi\rangle|^2.
$$

<details><summary><strong>Solution</strong></summary>

Since the $e_n$ are orthonormal,

$$
\langle \psi_N,\psi\rangle
=\sum_{n=1}^N \overline{\langle e_n,\psi\rangle}\langle e_n,\psi\rangle
=\sum_{n=1}^N |\langle e_n,\psi\rangle|^2,
$$

and similarly

$$
\|\psi_N\|^2=\sum_{n=1}^N |\langle e_n,\psi\rangle|^2.
$$

Therefore

$$
\|\psi-\psi_N\|^2
=\|\psi\|^2-\langle\psi,\psi_N\rangle-\langle\psi_N,\psi\rangle+\|\psi_N\|^2
=\|\psi\|^2-\sum_{n=1}^N |\langle e_n,\psi\rangle|^2.
$$

</details>

### Exercise 4: Dense but not closed

Show that the set $c_{00}$ of sequences with only finitely many nonzero entries is dense in $\ell^2(\mathbb N)$ but is not closed.

<details><summary><strong>Solution</strong></summary>

For any $a=(a_1,a_2,\ldots)\in\ell^2$, define its truncation

$$
a^{(N)}=(a_1,
\ldots,a_N,0,0,\ldots).
$$

Then $a^{(N)}\in c_{00}$ and

$$
\|a-a^{(N)}\|^2=\sum_{n=N+1}^\infty |a_n|^2\to 0
$$

because $a\in\ell^2$. Thus $c_{00}$ is dense.

It is not closed because the sequence $a=(1,1/2,1/3,\ldots)$ is in $\ell^2$ since $\sum_n 1/n^2<\infty$, but $a\notin c_{00}$. The truncations $a^{(N)}\in c_{00}$ converge to $a$, so the limit of a sequence in $c_{00}$ can lie outside $c_{00}$.

</details>

### Exercise 5: One-particle to bosonic Fock norm

Let $f,g\in\mathcal H_1$. In the bosonic two-particle sector, define the symmetrized tensor

$$
f\vee g=\frac{1}{\sqrt2}(f\otimes g+g\otimes f).
$$

Compute $\|f\vee g\|^2$.

<details><summary><strong>Solution</strong></summary>

Using the tensor-product inner product,

$$
\|f\vee g\|^2
=\frac12\langle f\otimes g+g\otimes f,f\otimes g+g\otimes f\rangle.
$$

The four terms are

$$
\|f\|^2\|g\|^2,
\qquad
\langle f,g\rangle\langle g,f\rangle=|\langle f,g\rangle|^2,
$$

$$
\langle g,f\rangle\langle f,g\rangle=|\langle f,g\rangle|^2,
\qquad
\|g\|^2\|f\|^2.
$$

Therefore

$$
\|f\vee g\|^2=\|f\|^2\|g\|^2+|\langle f,g\rangle|^2.
$$

If $f$ and $g$ are orthonormal, this norm is $1$.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. I. Standard reference for Hilbert spaces and operator methods in mathematical physics.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. Clear introduction to Hilbert spaces, operators, and spectral theory.
- B. C. Hall, *Quantum Theory for Mathematicians*. Useful for the bridge between Hilbert-space formalism and quantum mechanics.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Detailed physics-friendly treatment of Hilbert spaces and unbounded operators.
- K. Yosida, *Functional Analysis*. Classic functional-analysis reference.
- W. Rudin, *Functional Analysis*. Concise reference for Hilbert spaces, locally convex spaces, and distributions.
- I. M. Gelfand and N. Y. Vilenkin, *Generalized Functions*, Vol. 4. Classic source for rigged Hilbert spaces and generalized eigenfunction expansions.
- M. Srednicki, *Quantum Field Theory*. Useful for practical QFT uses of one-particle states, Fock spaces, spectral representations, and functional determinants.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for Hilbert-space and representation-theoretic foundations of relativistic QFT.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for the operational role of Hilbert spaces, states, spinors, path integrals, and spectral decompositions in QFT.

## Version history

- **2026-06-25:** Initial polished draft. Defined Hilbert spaces, completion, examples, orthogonality, bases, projections, Riesz duality, tensor products, Fock spaces, dense domains, generalized states, QFT caveats, and exercises.
