---
title: "Rigged Hilbert Spaces"
description: "Explains rigged Hilbert spaces, Gelfand triples, generalized eigenvectors, plane waves, delta-normalized states, and why QFT fields and continuous bases must be read weakly."
sidebar:
  label: "Rigged Hilbert Spaces"
  order: 9
level: Graduate
status: "Polished draft"
source: "Standard functional-analysis and mathematical-physics references, including Gelfand–Vilenkin, Reed–Simon, Maurin, Bohm, Gadella, Hall, Moretti, and QFT treatments of distributions, plane waves, and operator-valued fields."
topics:
  - rigged Hilbert spaces
  - Gelfand triples
  - generalized eigenvectors
  - plane waves
  - delta-normalized states
  - test functions
  - tempered distributions
  - weak identities
  - operator-valued distributions
  - continuous spectrum
canonicalTopics:
  - rigged-hilbert-space
  - gelfand-triple
  - generalized-eigenvector
  - plane-wave
  - delta-normalization
  - test-function
  - tempered-distribution
  - weak-identity
  - operator-valued-distribution
  - continuous-spectrum
researchStatus:
  established:
    - "Rigged Hilbert spaces provide a standard functional-analytic home for continuous-spectrum eigenvectors, plane waves, delta distributions, and weak spectral expansions."
  active:
    - "Continuum QFT often needs further operator-algebraic, distributional, microlocal, or constructive input beyond the rigged Hilbert-space framework, especially for interacting fields and local algebras."
---

## Summary

A rigged Hilbert space is a three-layer structure

$$
\Phi\subset\mathcal H\subset\Phi^{\times}.
$$

The middle space $\mathcal H$ is the Hilbert space of normalizable states. The smaller space $\Phi$ is a dense space of very nice test vectors. The larger space $\Phi^{\times}$ is a space of continuous linear functionals on $\Phi$; it contains generalized vectors such as plane waves, delta functions, and continuous-spectrum eigenstates.

The point is not to replace Hilbert space quantum mechanics. The point is to stop pretending that objects like $|x\rangle$, $|p\rangle$, and $\delta(x-y)$ are ordinary square-integrable vectors. They are not. They are distributional objects that become meaningful after pairing with test vectors.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a rigged Hilbert space triple: test vectors inside a Hilbert space inside a continuous dual, with smooth probes, normalizable wave packets, generalized vectors, and smeared QFT fields.](/figures/math-toolkit/rigged-hilbert-space-gelfand-triple.svg)

<figcaption>

A rigged Hilbert space inserts a test-vector space $\Phi$ and its continuous dual $\Phi^{\times}$ around the Hilbert space $\mathcal H$. The familiar example is $\mathcal S(\mathbb R^d)\subset L^2(\mathbb R^d)\subset\mathcal S'(\mathbb R^d)$. Continuous-basis formulas are weak identities: they make sense after inserting test vectors.

</figcaption>
</figure>

In QFT, this idea appears everywhere. Free-field mode expansions use delta-normalized plane waves. Scattering uses momentum eigenstates. Spectral representations use continuous labels. Point fields are operator-valued distributions and become honest operators only after smearing:

$$
\phi(f)=\int d^dx\, f(x)\phi(x).
$$

Rigged Hilbert spaces are the polite way to say: “Dirac notation works, but only because distributions are silently doing the heavy lifting.”

## Prerequisites

You should know [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), and the [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/). You should also know [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), and [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

The inner product convention is the one used in this chapter: $\langle\psi,\phi\rangle$ is conjugate-linear in the first entry and linear in the second.

## Core idea

A Hilbert space is excellent for normalizable states. It is not large enough for the generalized eigenvectors used in continuous spectra.

For a particle on the line, a square-integrable wave packet belongs to

$$
L^2(\mathbb R).
$$

But the position eigenstate at $a$ is represented by the delta distribution

$$
\delta_a(\varphi)=\varphi(a),
$$

and the momentum eigenstate with momentum $k$ is represented by the plane-wave distribution

$$
u_k(\varphi)=\int_{\mathbb R^d}d^dx\,e^{-ik\cdot x}\varphi(x)
=\widehat\varphi(k).
$$

Neither $\delta_a$ nor $e^{ik\cdot x}$ has finite $L^2$ norm. Nevertheless, both act perfectly well on a Schwartz test function $\varphi\in\mathcal S(\mathbb R^d)$. This suggests the triple

$$
\mathcal S(\mathbb R^d)\subset L^2(\mathbb R^d)\subset\mathcal S'(\mathbb R^d),
$$

where $\mathcal S'(\mathbb R^d)$ is the space of tempered distributions.

The rigging remembers three different kinds of object:

| Layer | Typical element | Meaning in physics |
|---|---|---|
| $\Phi$ | smooth rapidly decaying test vector | safe probe, wave packet, domain vector |
| $\mathcal H$ | square-integrable vector | normalizable state |
| $\Phi^{\times}$ | continuous functional on $\Phi$ | plane wave, delta state, generalized eigenvector |

The slogan is

$$
\text{generalized states are not in }\mathcal H,
\qquad
\text{but they pair with a dense set inside }\mathcal H.
$$

That pairing is enough for Fourier transforms, spectral decompositions, scattering normalizations, and distributional kernels.

## The Gelfand triple

A rigged Hilbert space, also called a Gelfand triple, consists of a dense inclusion

$$
\Phi\subset\mathcal H,
$$

where $\Phi$ has a locally convex topology stronger than the Hilbert norm topology, together with the continuous dual $\Phi^{\times}$:

$$
\Phi^{\times}=\{\text{continuous linear maps }\Phi\to\mathbb C\}.
$$

Some mathematics references use an anti-dual depending on inner-product conventions. With the physics convention used here, the embedding of $\mathcal H$ into $\Phi^{\times}$ is

$$
\psi\in\mathcal H
\quad\longmapsto\quad
F_\psi\in\Phi^{\times},
\qquad
F_\psi(\varphi)=\langle\psi,\varphi\rangle_{\mathcal H}.
$$

This is linear in $\varphi$. The map is injective because $\Phi$ is dense in $\mathcal H$: if

$$
\langle\psi,\varphi\rangle=0
\qquad\text{for all }\varphi\in\Phi,
$$

then $\psi=0$.

The topology on $\Phi$ is not a decorative detail. It controls which functionals count as continuous, and therefore which generalized vectors are included in $\Phi^{\times}$. For the Schwartz triple, the topology on $\mathcal S$ is generated by seminorms such as

$$
p_{\alpha\beta}(\varphi)
=\sup_{x\in\mathbb R^d}\left|x^\alpha\partial^\beta\varphi(x)\right|.
$$

Continuity with respect to these seminorms is exactly what defines tempered distributions.

## Why the test space is smaller than the Hilbert space

The space $\Phi$ is smaller than $\mathcal H$ as a set, but it has more structure. It is chosen to be stable under the operations one wants to perform.

For the Schwartz triple, the Fourier transform maps

$$
\mathcal S(\mathbb R^d)\to\mathcal S(\mathbb R^d),
$$

and differential operators with polynomial coefficients map $\mathcal S$ to itself. That makes $\mathcal S$ a good common domain for momentum, position, harmonic-oscillator operators, and many model Hamiltonians.

The Hilbert space $L^2(\mathbb R^d)$ is too large to support all these operations pointwise. A generic $L^2$ function need not be differentiable, need not have a value at a point, and need not decay pointwise in any pleasant way. It is normalizable, but not necessarily testable in the ways physicists casually use wavefunctions.

The smaller space $\Phi$ gives a safe arena for formal manipulations. The larger dual $\Phi^{\times}$ then receives the generalized results of those manipulations.

## Position and momentum states

Let

$$
\mathcal S(\mathbb R^d)\subset L^2(\mathbb R^d)\subset\mathcal S'(\mathbb R^d).
$$

A position generalized vector at $a\in\mathbb R^d$ is the delta distribution

$$
\delta_a(\varphi)=\varphi(a).
$$

It is not a vector in $L^2$, since there is no square-integrable function whose value as a distribution is $\delta(x-a)$. But it is a perfectly good element of $\mathcal S'$.

A momentum generalized vector with momentum $k$ is the plane-wave distribution

$$
u_k(\varphi)=\int d^dx\,e^{-ik\cdot x}\varphi(x)=\widehat\varphi(k).
$$

With the spatial Fourier convention

$$
\varphi(x)=\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot x}\widehat\varphi(k),
\qquad
\widehat\varphi(k)=\int d^dx\,e^{-ik\cdot x}\varphi(x),
$$

the weak completeness relation is

$$
\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot(x-y)}=\delta^{(d)}(x-y).
$$

Similarly, the formal orthogonality relation is

$$
\int d^dx\,e^{-ik\cdot x}e^{ik'\cdot x}
=(2\pi)^d\delta^{(d)}(k-k').
$$

These formulas are not statements about finite-norm vectors. They are distributional identities. To check one, insert a test function and use Fourier inversion.

## Weak equalities

A weak equality is an equality after pairing with test vectors. For example,

$$
\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot(x-y)}=\delta^{(d)}(x-y)
$$

means that for every suitable test function $\varphi$,

$$
\int d^dy\left[\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot(x-y)}\right]\varphi(y)
=\varphi(x).
$$

The brackets are not an ordinary convergent integral in $k$ at fixed $x,y$. They are a distributional kernel.

The same repair applies to the symbolic identity

$$
I=\int\frac{d^dk}{(2\pi)^d}|k\rangle\langle k|.
$$

This is not an operator-valued Riemann integral over vectors $|k\rangle\in\mathcal H$, because $|k\rangle$ is not in $\mathcal H$. It means that for test vectors $\varphi,\psi$,

$$
\langle\varphi,\psi\rangle
=\int\frac{d^dk}{(2\pi)^d}\,
\overline{\widehat\varphi(k)}\widehat\psi(k).
$$

That is just Plancherel's theorem in the chosen normalization.

This is the safest way to read continuous bases: first translate the formula into a pairing of test vectors; then evaluate the distributional kernel.

## Generalized eigenvectors

Suppose $A$ is a self-adjoint operator on $\mathcal H$ and $\Phi$ is chosen so that $A\Phi\subseteq\Phi$. A generalized eigenvector with eigenvalue $\lambda$ is a nonzero functional $F_\lambda\in\Phi^{\times}$ satisfying

$$
F_\lambda(A\varphi)=\lambda F_\lambda(\varphi)
\qquad
\text{for all }\varphi\in\Phi,
$$

up to the adjoint convention appropriate to the chosen pairing. The important part is not the exact notation but the logic: the eigenvalue equation is tested on $\Phi$.

For the momentum operator

$$
P_j=-i\partial_j
$$

on $L^2(\mathbb R^d)$, the plane wave $e^{ik\cdot x}$ satisfies

$$
P_j e^{ik\cdot x}=k_j e^{ik\cdot x}
$$

as a distribution. It is an eigenvector in $\mathcal S'(\mathbb R^d)$, not in $L^2(\mathbb R^d)$.

For a Hamiltonian with continuous spectrum, the same idea underlies generalized energy eigenstates. The spectral theorem gives projection-valued measures in $\mathcal H$; the rigged Hilbert-space language gives a controlled way to talk about the corresponding generalized eigenfunctions when a suitable test space exists.

## Relation to the spectral theorem

The spectral theorem does not require rigged Hilbert spaces. It already gives the honest Hilbert-space statement:

$$
A=\int_{\sigma(A)}\lambda\,dE(\lambda),
$$

where $E$ is a projection-valued measure. Matrix elements are

$$
\langle\psi,f(A)\phi\rangle
=\int_{\sigma(A)}f(\lambda)\,d\mu_{\psi,\phi}(\lambda),
$$

with

$$
\mu_{\psi,\phi}(\Delta)=\langle\psi,E(\Delta)\phi\rangle.
$$

This is the fully rigorous core.

Rigged Hilbert spaces add a more concrete language in favorable cases: instead of speaking only about spectral measures, one may speak about generalized eigenvectors $u_\lambda$ and expansions like

$$
\psi\sim\int d\mu(\lambda)\,\widehat\psi(\lambda)u_\lambda,
$$

understood weakly. The symbol $\sim$ is doing real work here. The equality is not an equality of ordinary vectors in a pointwise basis. It is a statement about how test-vector pairings and spectral transforms reconstruct the state.

The moral is useful:

$$
\text{spectral theorem} = \text{measure-theoretic truth},
$$

while

$$
\text{rigged Hilbert space} = \text{distributional language for the same truth when available}.
$$

## QFT fields as operator-valued distributions

A scalar quantum field is usually written as $\phi(x)$, but in continuum QFT $\phi(x)$ is rarely an honest operator at a sharp point. The meaningful object is the smeared field

$$
\phi(f)=\int d^dx\,f(x)\phi(x),
$$

where $f$ is a test function. Similarly, a two-point function

$$
W(x,y)=\langle\Omega,\phi(x)\phi(y)\Omega\rangle
$$

is a distributional kernel. Its honest meaning is

$$
W(f,g)
=\langle\Omega,\phi(f)\phi(g)\Omega\rangle
=\int d^dx\,d^dy\,f(x)g(y)W(x,y),
$$

with the obvious complex conjugations inserted when using conjugate test functions.

This is the field-theoretic analogue of the rigged Hilbert-space idea. Point labels are convenient, but test functions are the actual probes. Delta functions, propagators, contact terms, and equal-time commutators all become safer when read this way.

For example, a canonical equal-time commutator is often written

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

The mathematically meaningful version is smeared:

$$
[\phi(t,f),\pi(t,g)]
=i\int d^{d-1}\mathbf x\, f(\mathbf x)g(\mathbf x),
$$

for suitable spatial test functions $f$ and $g$.

## Scattering and delta normalization

Scattering theory is full of states that are not normalizable in the strict Hilbert-space sense. A single exact momentum state in infinite volume has delta normalization, not unit normalization. Physical beams and wave packets are normalizable; the delta-normalized states are idealized distributions that make translation invariance and momentum conservation transparent.

For one-particle relativistic states, a common convention is

$$
\langle p|q\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q),
$$

with the Lorentz-invariant measure

$$
\int\frac{d^3\mathbf p}{(2\pi)^3}\frac1{2E_{\mathbf p}}.
$$

The rigorous mental model is: construct wave packets using square-integrable amplitudes, compute the pairing, and only then use delta-normalized formulas as a distributional shorthand. This removes a lot of fake infinities. The infinity in $\langle p|p\rangle$ is not a mysterious physical divergence; it says that an exact plane wave is not a normalizable state.

## Operators and domains

Rigged Hilbert spaces do not eliminate domain questions. They make them more visible.

To use a rigged Hilbert space with an operator $A$, one often wants

$$
A\Phi\subseteq\Phi.
$$

This allows $A$ to act on test vectors and, by duality, to act on generalized vectors. If $A$ does not preserve the test space, the naive generalized eigenvector equation may not even be well-posed.

This is why one should not read a formal differential expression as a complete operator. Boundary conditions, domains, self-adjoint extensions, and the choice of test space affect the spectrum and the generalized eigenfunctions. The rigging is part of the analytic setup, not wallpaper.

## What rigged Hilbert spaces do not do

Rigged Hilbert spaces are powerful, but they are not magic fairy dust for all formal QFT expressions.

They do not by themselves construct interacting quantum fields. They do not automatically define products of distributions at coincident points. They do not solve ultraviolet divergences. They do not replace renormalization. They do not decide which local operator algebra is associated to a spacetime region. They do not justify every path integral.

Their job is narrower and still extremely useful: they give a clean language for generalized states, weak expansions, test-function smearing, and continuous spectral labels.

## Common pitfalls

**Treating generalized eigenvectors as normalizable states.** A plane wave is not in $L^2(\mathbb R^d)$. A delta function is not in $L^2(\mathbb R^d)$. Their normalization is distributional, not probabilistic.

**Forgetting the test space topology.** The dual $\Phi^{\times}$ depends on the topology of $\Phi$, not just on the set of vectors. The algebraic dual is far too large for analysis.

**Thinking the rigging is unique.** Different problems use different test spaces. The Schwartz triple is natural for flat-space Fourier analysis, but other operators may require other nuclear spaces or dense invariant domains.

**Mistaking weak identities for pointwise identities.** The formula $\int_k e^{ik\cdot(x-y)}=\delta(x-y)$ is not a convergent pointwise integral. It is a statement after testing.

**Ignoring domains because distributions are present.** Distributional notation does not bypass self-adjointness, boundary conditions, or domain choices. It just gives a better language once those choices are made.

**Multiplying distributions casually.** Rigged Hilbert spaces let distributions act on test vectors. They do not automatically define products like $\delta(x)^2$ or coincident-point operator products.

**Overusing Dirac notation.** Dirac notation is excellent shorthand when the weak meaning is clear. When the calculation is delicate, translate it into test functions, kernels, and pairings.

## Exercises

### Exercise 1: Embedding the Hilbert space into the dual

Let $\Phi\subset\mathcal H$ be dense. Define

$$
F_\psi(\varphi)=\langle\psi,\varphi\rangle
$$

for $\psi\in\mathcal H$ and $\varphi\in\Phi$. Show that if the inclusion $\Phi\to\mathcal H$ is continuous, then $F_\psi$ is continuous on $\Phi$.

<details><summary><strong>Solution</strong></summary>

Continuity of the inclusion means that convergence in $\Phi$ implies convergence in $\mathcal H$. Equivalently, locally one can bound the Hilbert norm by one or more seminorms defining the topology of $\Phi$.

For fixed $\psi\in\mathcal H$, Cauchy–Schwarz gives

$$
|F_\psi(\varphi)|
=|\langle\psi,\varphi\rangle|
\le \|\psi\|_{\mathcal H}\|\varphi\|_{\mathcal H}.
$$

Since $\varphi\mapsto\|\varphi\|_{\mathcal H}$ is continuous as a seminorm on $\Phi$, $F_\psi$ is continuous. Thus every Hilbert-space vector defines an element of $\Phi^{\times}$.

</details>

### Exercise 2: The delta functional is tempered

For $a\in\mathbb R^d$, define

$$
\delta_a(\varphi)=\varphi(a)
$$

for $\varphi\in\mathcal S(\mathbb R^d)$. Show that $\delta_a\in\mathcal S'(\mathbb R^d)$.

<details><summary><strong>Solution</strong></summary>

The Schwartz topology includes the seminorm

$$
p_{00}(\varphi)=\sup_{x\in\mathbb R^d}|\varphi(x)|.
$$

Then

$$
|\delta_a(\varphi)|=|\varphi(a)|\le p_{00}(\varphi).
$$

So $\delta_a$ is a continuous linear functional on $\mathcal S(\mathbb R^d)$. Therefore $\delta_a\in\mathcal S'(\mathbb R^d)$.

</details>

### Exercise 3: Plane waves are tempered distributions

For fixed $k\in\mathbb R^d$, define

$$
u_k(\varphi)=\int d^dx\,e^{-ik\cdot x}\varphi(x).
$$

Show that $u_k\in\mathcal S'(\mathbb R^d)$.

<details><summary><strong>Solution</strong></summary>

Linearity is immediate. To show continuity, use rapid decay. Choose $N>d$. Then

$$
|u_k(\varphi)|
\le \int d^dx\,|\varphi(x)|
=\int d^dx\,(1+|x|^2)^{-N/2}(1+|x|^2)^{N/2}|\varphi(x)|.
$$

Hence

$$
|u_k(\varphi)|
\le C_N\sup_x (1+|x|^2)^{N/2}|\varphi(x)|,
$$

where

$$
C_N=\int d^dx\,(1+|x|^2)^{-N/2}<\infty.
$$

The right-hand side is controlled by a Schwartz seminorm, so $u_k$ is continuous on $\mathcal S$.

</details>

### Exercise 4: Momentum eigenvalue equation in weak form

Let $P_j=-i\partial_j$ on $\mathcal S(\mathbb R^d)$ and let the plane-wave distribution be

$$
u_k(\varphi)=\int d^dx\,e^{-ik\cdot x}\varphi(x).
$$

Show that the generalized eigenvalue equation for momentum is equivalent to

$$
P_j e^{ik\cdot x}=k_j e^{ik\cdot x}
$$

as a distribution.

<details><summary><strong>Solution</strong></summary>

As an ordinary derivative of a smooth function,

$$
-i\partial_j e^{ik\cdot x}=k_j e^{ik\cdot x}.
$$

To read this distributionally, pair both sides with a Schwartz function. The left-hand side gives

$$
\int d^dx\,(-i\partial_j e^{ik\cdot x})\varphi(x)
=k_j\int d^dx\,e^{ik\cdot x}\varphi(x).
$$

Equivalently, using integration by parts and the rapid decay of $\varphi$ gives the dual action with no boundary term. The equality therefore holds as an equality of tempered distributions.

</details>

### Exercise 5: Completeness of plane waves as a weak identity

Using the spatial Fourier convention

$$
\varphi(x)=\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot x}\widehat\varphi(k),
$$

show that

$$
\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot(x-y)}=\delta^{(d)}(x-y)
$$

as a distribution in $y$.

<details><summary><strong>Solution</strong></summary>

Pair the left-hand side with a test function $\varphi(y)$:

$$
\int d^dy\left[\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot(x-y)}\right]\varphi(y).
$$

Formally exchanging the integrals gives

$$
\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot x}
\int d^dy\,e^{-ik\cdot y}\varphi(y)
=\int\frac{d^dk}{(2\pi)^d}e^{ik\cdot x}\widehat\varphi(k).
$$

By Fourier inversion, this is $\varphi(x)$. But $\delta^{(d)}(x-y)$ is defined by

$$
\int d^dy\,\delta^{(d)}(x-y)\varphi(y)=\varphi(x).
$$

Therefore the identity holds weakly.

</details>

## References

- I. M. Gelfand and N. Y. Vilenkin, *Generalized Functions*, Vol. 4. Classic reference for generalized eigenfunction expansions and rigged Hilbert spaces.
- K. Maurin, *Generalized Eigenfunction Expansions and Unitary Representations of Topological Groups*. A standard mathematical treatment of the nuclear spectral theorem.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis*. Useful for Hilbert spaces, operators, distributions, and spectral methods.
- A. Bohm and M. Gadella, *Dirac Kets, Gamow Vectors and Gelfand Triplets*. Physics-oriented treatment of rigged Hilbert spaces and generalized states.
- B. C. Hall, *Quantum Theory for Mathematicians*. Clear source for Hilbert-space quantum mechanics, spectral theory, and generalized eigenvectors.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Useful for self-adjoint operators, generalized eigenfunctions, and spectral decompositions.
- R. Haag, *Local Quantum Physics*. For the operator-algebraic framework needed beyond elementary Hilbert-space and rigged Hilbert-space language in continuum QFT.
- M. Srednicki, *Quantum Field Theory*. Useful for plane-wave normalizations, spectral representations, and practical QFT use of distributional states.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for the relation between Hilbert-space representation theory, particle states, and relativistic normalization.

## Version history

- 2026-06-25: Initial polished draft.
