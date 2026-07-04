---
title: "Linear Operators"
description: "Explains linear operators on Hilbert spaces, including domains, boundedness, kernels, ranges, graphs, adjoints, projections, unitary maps, multiplication and integral operators, and QFT domain warnings."
sidebar:
  label: "Linear Operators"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard functional-analysis and mathematical-physics references, including Reed–Simon, Teschl, Hall, Moretti, Yosida, Conway, Rudin, and QFT treatments of Hamiltonians, creation and annihilation operators, Green functions, and kernels."
topics:
  - linear operators
  - bounded operators
  - unbounded operators
  - domains
  - kernels
  - ranges
  - graphs
  - adjoints
  - projections
  - unitary operators
  - multiplication operators
  - integral kernels
canonicalTopics:
  - linear-operator
  - bounded-operator
  - operator-domain
  - kernel-and-range
  - graph-of-operator
  - adjoint-operator
  - projection-operator
  - unitary-operator
  - multiplication-operator
  - integral-operator
researchStatus:
  established:
    - "Bounded operators, densely defined unbounded operators, adjoints, projections, unitary maps, and integral kernels are standard analytic tools in quantum mechanics and QFT."
  active:
    - "In interacting QFT, local fields are usually unbounded operator-valued distributions; precise domains, closures, and local algebraic formulations require more refined treatment than elementary operator notation suggests."
---

## Summary

A linear operator is the infinite-dimensional cousin of a matrix, except that this cousin has opinions about where it is defined. In finite dimensions, a linear map acts on the whole vector space. In QFT and quantum mechanics, the most important operators—Hamiltonians, momenta, positions, number operators, creation and annihilation operators, differential operators, and quantum fields—are usually unbounded. An unbounded operator cannot be defined on every Hilbert-space vector.

So the basic object is not merely a formula $A\psi$. It is

$$
A:\mathcal D(A)\subseteq\mathcal H\to\mathcal K,
$$

where $\mathcal D(A)$ is the domain. The domain is part of the operator. Two operators can have the same formula and different domains; they can then have different adjoints, spectra, boundary conditions, and physical meanings.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Diagram showing a linear operator from a domain inside a Hilbert space to another Hilbert space, with kernel, range, graph, adjoint data, and a warning that QFT operators are often unbounded and not determined by formulas alone.](/figures/math-toolkit/linear-operator-domain-map.svg)

<figcaption>

A linear operator is a map $A:\mathcal D(A)\to\mathcal K$ from a domain $\mathcal D(A)$ inside a Hilbert space $\mathcal H$. Bounded operators extend continuously to all of $\mathcal H$; unbounded operators require domain data. Kernels, ranges, graphs, adjoints, and spectra all depend on the operator as a domain-equipped object.

</figcaption>
</figure>

This page explains the language needed before studying unbounded operators, self-adjointness, and the spectral theorem. It also sets up a practical warning that will reappear everywhere in QFT:

$$
\text{same formal expression} \neq \text{same operator unless the domain is fixed}.
$$

## Prerequisites

You should know the definition of a Hilbert space from [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), basic matrix algebra, and the idea of a dense subspace. For distributional kernels, see [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/). For QFT examples involving determinants and heat kernels, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

## Core idea

A linear operator from $\mathcal H$ to $\mathcal K$ consists of a linear subspace $\mathcal D(A)\subseteq\mathcal H$ and a linear map

$$
A:\mathcal D(A)\to\mathcal K.
$$

Linearity means

$$
A(a\psi+b\phi)=aA\psi+bA\phi
$$

for all $\psi,\phi\in\mathcal D(A)$ and $a,b\in\mathbb C$.

If $\mathcal D(A)=\mathcal H$ and there is a finite constant $C$ such that

$$
\|A\psi\|_{\mathcal K}\le C\|\psi\|_{\mathcal H}
$$

for all $\psi\in\mathcal H$, then $A$ is bounded. Bounded operators are the comfortable operators: they are continuous, defined everywhere, and form a Banach algebra when $\mathcal H=\mathcal K$.

Unbounded operators are the interesting troublemakers. They may satisfy the same inequality on no global finite $C$, and they cannot be defined on all of $\mathcal H$ if they are genuinely unbounded and closed enough to be useful. Differential operators and Hamiltonians live here.

The finite-dimensional reflex says “write the matrix and multiply.” The infinite-dimensional repair is:

$$
\boxed{\text{operator} = \text{formula} + \text{domain} + \text{target space}.}
$$

The box is not a slogan for mathematical fussiness. Boundary conditions, gauge constraints, zero modes, and self-adjoint extensions all enter through this data.

## Basic definitions

Let $A:\mathcal D(A)\subseteq\mathcal H\to\mathcal K$ be linear.

The **kernel** of $A$ is

$$
\ker A=\{\psi\in\mathcal D(A)\mid A\psi=0\}.
$$

The **range** or image of $A$ is

$$
\operatorname{ran}A=\{A\psi\mid \psi\in\mathcal D(A)\}\subseteq\mathcal K.
$$

The **graph** of $A$ is

$$
\Gamma(A)=\{(\psi,A\psi)\mid \psi\in\mathcal D(A)\}\subseteq\mathcal H\oplus\mathcal K.
$$

The graph is a useful way to study domains. An operator is **closed** if its graph is closed in $\mathcal H\oplus\mathcal K$. Equivalently, whenever

$$
\psi_n\to\psi,
\qquad
A\psi_n\to\eta,
$$

with $\psi_n\in\mathcal D(A)$, then $\psi\in\mathcal D(A)$ and $A\psi=\eta$.

An operator is **closable** if it has a closed extension. Its closure is denoted $\overline A$. The closure is often what a formal differential expression is secretly trying to become.

A domain $\mathcal D(A)$ is **dense** if

$$
\overline{\mathcal D(A)}=\mathcal H.
$$

Dense domains are needed to define adjoints of unbounded operators in the usual Hilbert-space way.

## Bounded operators

A linear operator $A:\mathcal H\to\mathcal K$ defined on all of $\mathcal H$ is bounded if

$$
\|A\|=\sup_{\psi\neq 0}\frac{\|A\psi\|_{\mathcal K}}{\|\psi\|_{\mathcal H}}<\infty.
$$

Equivalently,

$$
\|A\|=\sup_{\|\psi\|=1}\|A\psi\|.
$$

The smallest constant $C$ in

$$
\|A\psi\|\le C\|\psi\|
$$

is exactly $\|A\|$.

For linear maps between normed spaces, boundedness is equivalent to continuity. This is why bounded operators are analytically gentle. If $\psi_n\to\psi$, then

$$
\|A\psi_n-A\psi\|=\|A(\psi_n-\psi)\|\le \|A\|\,\|\psi_n-\psi\|\to 0.
$$

The space of bounded linear operators from $\mathcal H$ to $\mathcal K$ is written

$$
\mathcal B(\mathcal H,\mathcal K).
$$

When $\mathcal H=\mathcal K$, one writes $\mathcal B(\mathcal H)$. It is a Banach algebra with the operator norm. Composition satisfies

$$
\|AB\|\le \|A\|\,\|B\|.
$$

In finite-dimensional Hilbert spaces, every linear operator is bounded. This is one of the many ways finite-dimensional intuition quietly lies to you.

## Examples of bounded operators

A rank-one operator is defined by two vectors $u\in\mathcal K$ and $v\in\mathcal H$:

$$
A\psi=u\langle v,\psi\rangle.
$$

In bra-ket notation, this is

$$
A=|u\rangle\langle v|.
$$

It is bounded, and

$$
\|A\|=\|u\|\,\|v\|.
$$

An orthogonal projection $P$ on $\mathcal H$ satisfies

$$
P^2=P,
\qquad
P^*=P.
$$

If $P\neq 0$, then $\|P\|=1$. Projection operators appear in constraints, gauge fixing, spectral decompositions, and decompositions into irreducible symmetry sectors.

A unitary operator $U:\mathcal H\to\mathcal K$ satisfies

$$
\langle U\psi,U\phi\rangle_{\mathcal K}=\langle\psi,\phi\rangle_{\mathcal H}
$$

and maps $\mathcal H$ onto $\mathcal K$. Equivalently, when $\mathcal H=\mathcal K$,

$$
U^*U=UU^*=1.
$$

Fourier transform is unitary on $L^2(\mathbb R^d)$ with the appropriate normalization. Time evolution $e^{-itH}$ is unitary when $H$ is self-adjoint. That last condition is not optional; it is the functional-analytic reason self-adjointness matters.

The right-shift operator on $\ell^2(\mathbb N)$,

$$
S(a_1,a_2,a_3,\ldots)=(0,a_1,a_2,a_3,\ldots),
$$

is bounded with $\|S\|=1$. It is an isometry because $\|Sa\|=\|a\|$, but it is not unitary because it is not onto: no vector maps to $(1,0,0,\ldots)$.

## Multiplication operators

Let $(X,\mu)$ be a measure space and let $m:X\to\mathbb C$ be a measurable function. The multiplication operator is formally

$$
(M_m f)(x)=m(x)f(x).
$$

If $m\in L^\infty(X)$, then $M_m$ is bounded on $L^2(X,d\mu)$ and

$$
\|M_m\|=\operatorname*{ess\,sup}_{x\in X}|m(x)|.
$$

If $m$ is unbounded, the same formula may still define an unbounded operator with domain

$$
\mathcal D(M_m)=\{f\in L^2(X)\mid mf\in L^2(X)\}.
$$

This example is worth keeping close. The position operator on $L^2(\mathbb R)$ is just multiplication by $x$:

$$
(Xf)(x)=x f(x),
$$

with domain

$$
\mathcal D(X)=\{f\in L^2(\mathbb R)\mid xf(x)\in L^2(\mathbb R)\}.
$$

The formula $xf(x)$ does not define a vector in $L^2$ for every $f\in L^2$. Therefore $X$ is not an everywhere-defined operator on $L^2$.

## Integral kernels

Many QFT operators are written using kernels:

$$
(Af)(x)=\int_Y d\nu(y)\,K(x,y)f(y).
$$

This notation can represent a bounded operator, an unbounded operator, a compact operator, a distributional operator, or a purely formal expression, depending on $K$ and the function spaces.

One useful sufficient condition is the Hilbert–Schmidt condition. If

$$
\int_X d\mu(x)\int_Y d\nu(y)\,|K(x,y)|^2<\infty,
$$

then $A:L^2(Y)\to L^2(X)$ is bounded and Hilbert–Schmidt. In particular,

$$
\|A\|\le \left(\int_X d\mu(x)\int_Y d\nu(y)\,|K(x,y)|^2\right)^{1/2}.
$$

But many important kernels in QFT are not square-integrable. The identity kernel is a delta distribution:

$$
K(x,y)=\delta(x-y),
$$

and Green functions often have short-distance singularities. The kernel notation remains useful, but it must be interpreted distributionally and with the correct domain or test-function pairing.

A propagator is often an inverse kernel for a differential operator. For instance, the Euclidean free scalar Green function formally satisfies

$$
(-\partial^2+m^2)G(x,y)=\delta^{(d)}(x-y).
$$

This is not just an equation of functions. It is an operator equation, usually after specifying boundary conditions, function spaces, zero-mode treatment, and regularization if coincident points are used.

## Unbounded operators as a preview

The next page will treat unbounded operators systematically, but the basic reason they appear is simple. Derivatives and multiplication by unbounded functions are not controlled by the $L^2$ norm alone.

On $L^2(\mathbb R)$, define

$$
(Pf)(x)=-i\frac{df}{dx}.
$$

This formula does not make sense for every $L^2$ function. Even when a weak derivative exists, it need not be square-integrable. A natural domain is the Sobolev space

$$
\mathcal D(P)=H^1(\mathbb R).
$$

On a finite interval, the same formal expression $-i d/dx$ can define different operators depending on boundary conditions. Periodic, Dirichlet-like, and phase-twisted conditions lead to different domains and spectra.

Likewise, the harmonic-oscillator Hamiltonian

$$
H=-\frac12\frac{d^2}{dx^2}+\frac12x^2
$$

is not an operator on all of $L^2(\mathbb R)$. Its useful definition requires a domain on which both the second derivative and $x^2f$ are square-integrable in the appropriate sense.

The moral is not “avoid unbounded operators.” The moral is “do not pretend their domains are optional.”

## Adjoints

For a bounded operator $A:\mathcal H\to\mathcal K$, the adjoint is the unique bounded operator

$$
A^*:\mathcal K\to\mathcal H
$$

such that

$$
\langle\chi,A\psi\rangle_{\mathcal K}=\langle A^*\chi,\psi\rangle_{\mathcal H}
$$

for all $\psi\in\mathcal H$ and $\chi\in\mathcal K$. The existence and uniqueness follow from the Riesz representation theorem.

With the physics inner-product convention, this formula matches the bra-ket rule

$$
\langle\chi|A|\psi\rangle=\langle A^*\chi|\psi\rangle.
$$

For bounded operators,

$$
(A+B)^*=A^*+B^*,
\qquad
(\lambda A)^*=\overline\lambda A^*,
\qquad
(AB)^*=B^*A^*,
\qquad
(A^*)^*=A.
$$

The norm satisfies

$$
\|A^*A\|=\|A\|^2.
$$

For unbounded operators, the adjoint is subtler. The operator must be densely defined, and the domain of $A^*$ is itself a condition:

$$
\mathcal D(A^*)=\left\{\chi\in\mathcal K\mid \exists\eta\in\mathcal H\text{ such that }\langle\chi,A\psi\rangle=\langle\eta,\psi\rangle\text{ for all }\psi\in\mathcal D(A)\right\}.
$$

Then $A^*\chi=\eta$. This is where integration by parts becomes domain-sensitive. Boundary terms decide which vectors belong to the adjoint domain.

## Symmetric, self-adjoint, normal, positive

An operator $A$ on $\mathcal H$ is symmetric if

$$
\langle\psi,A\phi\rangle=\langle A\psi,\phi\rangle
$$

for all $\psi,\phi\in\mathcal D(A)$. Equivalently,

$$
A\subseteq A^*,
$$

meaning that $A^*$ extends $A$.

A densely defined operator is self-adjoint if

$$
A=A^*,
$$

including equality of domains. Symmetric is not the same as self-adjoint. This distinction is the gatekeeper for real spectra and unitary time evolution.

A bounded operator is normal if

$$
AA^*=A^*A.
$$

Self-adjoint and unitary bounded operators are normal. Normality is the condition under which the spectral theorem resembles diagonalization most closely.

An operator $A$ is positive if

$$
\langle\psi,A\psi\rangle\ge 0
$$

on its domain. For bounded positive operators, one writes $A\ge 0$. In QFT, positive operators appear as Hamiltonians bounded below, Laplace-type operators, covariance operators in Gaussian measures, and density matrices.

## Matrix elements and infinite matrices

Given orthonormal bases $\{e_n\}$ for $\mathcal H$ and $\{f_m\}$ for $\mathcal K$, one can define matrix elements

$$
A_{mn}=\langle f_m,Ae_n\rangle,
$$

provided $e_n\in\mathcal D(A)$. In finite dimensions, the matrix determines the operator. In infinite dimensions, this statement becomes much less innocent.

An infinite matrix $A_{mn}$ may fail to define a bounded operator on $\ell^2$. Even when it defines an operator on finite sequences, it may have many closures or domain choices. Conversely, an operator may be best understood spectrally rather than by its matrix entries.

Mode expansions in QFT often turn operators into infinite matrices. That is useful, but the analytic questions do not disappear. They become questions about convergence, domains, trace ideals, and regularization.

## Composition and commutators

For bounded operators, products are straightforward:

$$
AB\psi=A(B\psi),
\qquad
\mathcal D(AB)=\mathcal H.
$$

For unbounded operators, the domain of the product is

$$
\mathcal D(AB)=\{\psi\in\mathcal D(B)\mid B\psi\in\mathcal D(A)\}.
$$

This can be smaller than either domain, and it can even be trivial if handled carelessly.

The commutator is formally

$$
[A,B]=AB-BA.
$$

For unbounded operators, this is defined on

$$
\mathcal D(AB)\cap\mathcal D(BA).
$$

The canonical commutator

$$
[X,P]=i
$$

is therefore not an equality of bounded operators on all of $L^2(\mathbb R)$. It is an equality on a suitable dense domain such as $\mathcal S(\mathbb R)$, or a statement encoded more robustly by the Weyl relations for exponentiated unitary operators.

This is one of the healthiest habits in mathematical physics: when a commutator contains unbounded operators, silently ask “on what domain?”

## Inverses and Green operators

An operator $A:\mathcal D(A)\subseteq\mathcal H\to\mathcal K$ is injective if

$$
\ker A=\{0\}.
$$

If $A$ is injective, one can define an inverse on the range:

$$
A^{-1}:\operatorname{ran}A\to\mathcal D(A).
$$

This does not mean $A^{-1}$ is defined on all of $\mathcal K$, nor that it is bounded. If $\operatorname{ran}A$ is dense but not closed, the inverse can be unbounded.

Green functions are often inverse operators in this sense. If

$$
L G = 1
$$

is written schematically, the honest questions are:

- What is the domain of $L$?
- Does $L$ have zero modes?
- What boundary conditions are imposed?
- Is the inverse defined on all sources or only on sources orthogonal to the kernel?
- Is $G$ a bounded operator, an unbounded operator, or a distributional kernel?

For gauge theories, the kinetic operator before gauge fixing has gauge zero modes. It cannot be inverted on the full field space. Gauge fixing, constraints, ghosts, or quotient spaces are not optional decorations; they are how one makes the inverse problem well-posed.

## Resolvent and spectrum preview

For a bounded operator $A\in\mathcal B(\mathcal H)$, the resolvent set $\rho(A)$ consists of complex numbers $z$ such that

$$
A-z1
$$

has a bounded inverse defined on all of $\mathcal H$. The spectrum is the complement:

$$
\sigma(A)=\mathbb C\setminus\rho(A).
$$

In finite dimensions, the spectrum is just the set of eigenvalues. In infinite dimensions, the spectrum can contain points that are not eigenvalues. The unilateral shift is a friendly warning sign: its spectrum is the closed unit disk, not just a list of eigenvectors.

For self-adjoint operators, the spectrum lies on the real line. For unitary operators, it lies on the unit circle. These facts are the infinite-dimensional descendants of Hermitian and unitary matrix diagonalization.

The resolvent is not just abstract vocabulary. In QFT and PDE, resolvents are Green operators:

$$
(A-z)^{-1}.
$$

Propagators, spectral densities, and contour representations are all resolvent-adjacent technology.

## Operators from symmetries

A symmetry acting on a Hilbert space is usually represented by a unitary or antiunitary operator. Continuous unitary symmetries are generated by self-adjoint operators. For example, if $U(t)$ is a strongly continuous one-parameter unitary group, Stone's theorem says there is a self-adjoint generator $H$ such that

$$
U(t)=e^{-itH}.
$$

This is the analytic backbone of the Schrödinger equation. It is also why Hamiltonians must be self-adjoint, not merely symmetric-looking.

Translations, rotations, internal symmetries, time evolution, and gauge transformations all use operator representations. In relativistic QFT, the Poincaré group acts by unitary operators on the Hilbert space of states, and the generators satisfy the Poincaré algebra on appropriate domains.

## Operators in QFT

Here is a small dictionary of how linear operators appear in QFT:

| QFT object | Operator-theoretic role | Main caveat |
|---|---|---|
| Hamiltonian $H$ | generator of time evolution | must be self-adjoint or suitably defined |
| Momentum $P_i$ | generator of translations | unbounded; domain matters |
| Field $\phi(x)$ | operator-valued distribution | pointwise operator is usually not defined |
| Smeared field $\phi(f)$ | densely defined operator | depends on test function and domain |
| Propagator | inverse or boundary value of inverse | zero modes and boundary conditions matter |
| Kinetic operator | differential operator in quadratic action | domain and gauge fixing matter |
| Creation operator $a^\dagger(f)$ | maps $n$-particle to $n+1$-particle sectors | unbounded on Fock space |
| Number operator $N$ | counts particles | unbounded |
| Transfer matrix | evolution operator in Euclidean/lattice setting | positivity and self-adjointness are model-dependent |
| Projector | selects sector or constraint solution | may be formal in gauge theory |

The table has a theme: QFT formulas are operator formulas with analytic hypotheses usually suppressed. Suppression is fine for fast calculation; forgetting is not.

## Relations to other pages

- [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/) defines the complete inner-product spaces on which the operators here act.
- [Functional Analysis and Spectral Theory](/math-toolkit/functional-analysis-spectral-theory/) gives the chapter map from operators to self-adjointness, spectral theorem, trace ideals, and spectral density.
- [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/) explains why domains of differential operators are often Sobolev-type spaces.
- [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/) explain why operator kernels and fields must often be smeared.
- [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) uses operator spectra and regularized products in one-loop path integrals.
- [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) is a geometric source of unbounded operators whose kernels and indices carry physical information.

## Research status

Bounded operators on Hilbert spaces are textbook-standard. Their adjoints, norms, projections, unitary operators, and operator topologies form the controlled part of infinite-dimensional linear algebra.

The active-looking complications in QFT usually come from stepping beyond the bounded setting. Hamiltonians and differential operators need self-adjoint domains, fields are typically operator-valued distributions, gauge theories require constraints and quotients, and local continuum QFT is often better described through operator algebras. This page is therefore a foundation, not the endpoint.

## Common pitfalls

**Identifying an operator with its formula.** The expression $-d^2/dx^2$ is not a complete operator until the domain and boundary conditions are specified.

**Assuming every linear operator is bounded.** This is true in finite dimensions and false in the spaces used for quantum mechanics and QFT.

**Using the adjoint without checking domains.** For unbounded operators, integration by parts may produce boundary terms that change the adjoint domain.

**Treating commutators as everywhere-defined.** $[X,P]=i$ is not an equality of bounded operators on all of $L^2$. It is a domain-sensitive statement.

**Assuming kernel notation is harmless.** A kernel may be a distribution, not a function. It may define an operator only after smearing or regularization.

**Inverting operators with zero modes.** Gauge redundancies, constant modes, and moduli can obstruct inverses. One must project out the kernel, fix gauge, or modify the operator.

**Moving operators inside traces freely.** Cyclicity of trace requires hypotheses. For divergent traces or unbounded products, formal cyclicity can fail and is closely related to anomalies.

**Calling a symmetric operator self-adjoint.** Symmetric means matrix elements look Hermitian on a domain. Self-adjoint means equality with the adjoint, including domains. Not the same beast.

## Exercises

### Exercise 1: Bounded implies continuous

Let $A:\mathcal H\to\mathcal K$ be a bounded linear operator. Show that if $\psi_n\to\psi$ in $\mathcal H$, then $A\psi_n\to A\psi$ in $\mathcal K$.

<details><summary><strong>Solution</strong></summary>

By boundedness,

$$
\|A\psi_n-A\psi\|=\|A(\psi_n-\psi)\|\le \|A\|\,\|\psi_n-\psi\|.
$$

Since $\psi_n\to\psi$, the right-hand side goes to zero. Therefore $A\psi_n\to A\psi$.

</details>

### Exercise 2: Rank-one adjoint

Let $A=|u\rangle\langle v|$ with

$$
A\psi=u\langle v,\psi\rangle.
$$

Find $A^*$.

<details><summary><strong>Solution</strong></summary>

For $\chi\in\mathcal K$ and $\psi\in\mathcal H$,

$$
\langle\chi,A\psi\rangle_{\mathcal K}
=\langle\chi,u\langle v,\psi\rangle\rangle
=\langle v,\psi\rangle\langle\chi,u\rangle.
$$

Using conjugate symmetry,

$$
\langle\chi,u\rangle=\overline{\langle u,\chi\rangle}.
$$

We want $\langle A^*\chi,\psi\rangle_{\mathcal H}$. Taking

$$
A^*\chi=v\langle u,\chi\rangle
$$

gives

$$
\langle A^*\chi,\psi\rangle=\langle v\langle u,\chi\rangle,\psi\rangle
=\overline{\langle u,\chi\rangle}\langle v,\psi\rangle
=\langle\chi,u\rangle\langle v,\psi\rangle.
$$

Thus

$$
A^*=|v\rangle\langle u|.
$$

</details>

### Exercise 3: Multiplication by a bounded function

Let $m\in L^\infty(X)$ and define $M_mf=mf$ on $L^2(X,d\mu)$. Show that

$$
\|M_m\|\le \|m\|_\infty.
$$

<details><summary><strong>Solution</strong></summary>

For $f\in L^2$,

$$
\|M_m f\|_2^2=\int_X d\mu\,|m(x)f(x)|^2
\le \|m\|_\infty^2\int_X d\mu\,|f(x)|^2
=\|m\|_\infty^2\|f\|_2^2.
$$

Taking square roots gives

$$
\|M_m f\|_2\le \|m\|_\infty\|f\|_2,
$$

so $M_m$ is bounded and $\|M_m\|\le \|m\|_\infty$.

</details>

### Exercise 4: The canonical commutator on Schwartz space

Let $X$ and $P$ act on $\mathcal S(\mathbb R)$ by

$$
(Xf)(x)=xf(x),
\qquad
(Pf)(x)=-i f'(x).
$$

Show that $[X,P]f=i f$ for $f\in\mathcal S(\mathbb R)$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
(XPf)(x)=x(-if'(x))=-ixf'(x),
$$

while

$$
(PXf)(x)=-i\frac{d}{dx}(xf(x))=-i(f(x)+xf'(x)).
$$

Therefore

$$
([X,P]f)(x)=(XPf)(x)-(PXf)(x)
=-ixf'(x)+i f(x)+i x f'(x)=i f(x).
$$

Thus

$$
[X,P]f=if
$$

on $\mathcal S(\mathbb R)$. The domain statement is part of the result.

</details>

### Exercise 5: The right shift is not unitary

On $\ell^2(\mathbb N)$, define

$$
S(a_1,a_2,a_3,\ldots)=(0,a_1,a_2,a_3,\ldots).
$$

Show that $S$ is an isometry but not unitary.

<details><summary><strong>Solution</strong></summary>

The norm is preserved:

$$
\|Sa\|^2=|0|^2+|a_1|^2+|a_2|^2+\cdots=\|a\|^2.
$$

So $S$ is an isometry. It is not onto, because no vector $a\in\ell^2$ satisfies

$$
Sa=(1,0,0,\ldots).
$$

The first component of $Sa$ is always zero. A unitary operator must be an onto isometry, so $S$ is not unitary.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. I. Standard reference for Hilbert-space operators, boundedness, adjoints, closed operators, and spectral theory.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. Clear treatment of operators, domains, adjoints, and Schrödinger operators.
- B. C. Hall, *Quantum Theory for Mathematicians*. Useful bridge between operator theory and quantum mechanics.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Detailed mathematical-physics treatment of domains, adjoints, and self-adjointness.
- J. B. Conway, *A Course in Functional Analysis*. Standard functional-analysis reference for bounded operators and Hilbert-space methods.
- K. Yosida, *Functional Analysis*. Classic reference for operator theory and functional analysis.
- W. Rudin, *Functional Analysis*. Concise mathematical reference for topological vector spaces and operators.
- M. Srednicki, *Quantum Field Theory*. Useful for practical appearances of operators, functional determinants, creation and annihilation operators, and QFT kernels.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for operator and representation-theoretic foundations of relativistic QFT.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for QFT applications of operators, propagators, path integrals, and spectral decompositions.

## Version history

- **2026-06-25:** Initial polished draft. Defined linear operators with domains, boundedness, examples, multiplication and kernel operators, adjoints, operator classes, products, commutators, inverses, resolvents, QFT uses, common pitfalls, and exercises.
