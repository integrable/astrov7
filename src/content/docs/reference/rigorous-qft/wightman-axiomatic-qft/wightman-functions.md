---
title: "Wightman Functions"
description: "Defines Wightman functions as vacuum correlation distributions and explains their covariance, spectral support, locality, positivity, and role in reconstruction."
sidebar:
  label: "Wightman Functions"
  order: 7
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Haag; Källén–Lehmann representation."
topics:
  - Wightman functions
  - vacuum expectation values
  - tempered distributions
  - reconstruction theorem
  - correlation functions
canonicalTopics:
  - wightman-functions
  - vacuum-correlation-functions
  - axiomatic-quantum-field-theory
researchStatus:
  established:
    - "Wightman functions are tempered vacuum correlation distributions whose covariance, spectral support, locality, Hermiticity, and positivity encode the Wightman axioms at the level of correlation functions."
    - "The Wightman reconstruction theorem reconstructs a Hilbert space, vacuum, and fields from a suitable family of Wightman functions."
  active:
    - "For gauge theories, massless charged sectors, and curved-spacetime QFT, related correlation-function frameworks require additional structure beyond the simplest Wightman-function package."
---

## Summary

Wightman functions are the vacuum expectation values of ordered products of quantum fields. For a family of fields $\phi_i$, their distributional kernels are written

$$
W_n^{i_1\cdots i_n}(x_1,\ldots,x_n)
=
\langle \Omega,
\phi_{i_1}(x_1)\cdots\phi_{i_n}(x_n)
\Omega\rangle.
$$

This formula is kernel notation. The actual object is a tempered distribution tested against smearing functions:

$$
W_n^{i_1\cdots i_n}(f_1,\ldots,f_n)
=
\langle \Omega,
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)
\Omega\rangle.
$$

Wightman functions are not time-ordered Feynman correlators. The order of the fields is the order written. Timelike exchanges generally change the distribution; spacelike exchanges are constrained by locality.

The reason Wightman functions are central is that they translate Hilbert-space QFT into correlation-function data. A suitable sequence $\{W_n\}_{n\ge0}$ satisfying temperedness, Poincaré covariance, spectral support, locality, Hermiticity, and positivity determines a Wightman theory up to unitary equivalence. The reconstruction theorem is a precise version of this slogan:

$$
\text{vacuum correlation distributions}
+
\text{positivity}
\quad\Longrightarrow\quad
\text{Hilbert space and fields}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![Wightman functions as correlation-function data for reconstruction](/figures/rigorous-qft/wightman-functions-data.svg)

<figcaption>

Hilbert-space data produce Wightman functions by vacuum expectation values. Conversely, the Wightman reconstruction theorem starts from distributions $W_n$ satisfying the Wightman-function axioms and reconstructs the Hilbert-space theory.

</figcaption>
</figure>

## Prerequisites

You should know the axioms from [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/), the smearing and domain setup from [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/), and the vacuum-cyclicity language from [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/).

The support statement below uses [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), and the permutation property uses [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/).

## Core idea

A Wightman function is a coordinate function on the theory. It probes the fields by asking: if the vacuum is first disturbed by one smeared field, then another, and so on, what complex number is obtained by pairing the final vector back with the vacuum?

For a scalar Hermitian field, the first few are

$$
W_0=1,
\qquad
W_1(f)=\langle\Omega,\phi(f)\Omega\rangle,
$$

$$
W_2(f,g)=
\langle\Omega,\phi(f)\phi(g)\Omega\rangle,
$$

and similarly for higher products. In an interacting theory these higher functions are not determined by $W_2$. In a free Gaussian theory they are determined by $W_2$ through Wick's theorem.

The Wightman viewpoint is powerful because many axioms become visible directly on the $W_n$:

| Hilbert-space axiom | Correlation-function shadow |
|---|---|
| Vacuum invariance | Translation and Lorentz covariance of $W_n$. |
| Positive energy | Momentum-space support in future cones. |
| Locality | Graded symmetry under spacelike adjacent interchange. |
| Positive Hilbert space | Wightman positivity inequalities. |
| Cyclicity | Reconstruction from the span of field-polynomial states. |

## Setup and conventions

Work on $d$-dimensional Minkowski space with the mostly-minus metric and Fourier convention fixed in [Conventions and Logical Status](/rigorous-qft/conventions/). Let $\mathcal S(\mathbb M^d)$ denote Schwartz test functions.

For a finite-component field family $\phi_i$, define

$$
W_n^{i_1\cdots i_n}
\in
\mathcal S'((\mathbb M^d)^n)
$$

by its action on a Schwartz test function $f\in\mathcal S((\mathbb M^d)^n)$:

$$
W_n^{i_1\cdots i_n}(f)
=
\int
W_n^{i_1\cdots i_n}(x_1,\ldots,x_n)
 f(x_1,\ldots,x_n)
 \,d^dx_1\cdots d^dx_n,
$$

where this integral is distributional notation. For a factorized test function $f=f_1\otimes\cdots\otimes f_n$, the definition means

$$
W_n^{i_1\cdots i_n}(f_1\otimes\cdots\otimes f_n)
=
\langle \Omega,
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)
\Omega\rangle.
$$

The extension from factorized test functions to general Schwartz functions on $(\mathbb M^d)^n$ is part of the distributional formulation.

For a single Hermitian scalar field, we usually suppress the field labels and write $W_n$. For fields with spin, internal indices, or fermion parity, the labels and transformation matrices must be retained.

## Structural properties

### Temperedness

Each $W_n$ is a tempered distribution. This means it acts continuously on Schwartz functions:

$$
W_n\in\mathcal S'((\mathbb M^d)^n).
$$

Temperedness makes Fourier transforms well-defined as tempered distributions. It is also a growth condition: Wightman functions may be singular, but not arbitrarily wild at infinity.

### Translation invariance

Vacuum invariance under translations gives

$$
W_n(x_1+a,\ldots,x_n+a)
=
W_n(x_1,\ldots,x_n)
$$

in distributional notation. Therefore $W_n$ depends only on relative variables. A convenient convention is

$$
\xi_j=x_j-x_{j+1},
\qquad j=1,\ldots,n-1,
$$

so

$$
W_n(x_1,\ldots,x_n)
=
w_n(\xi_1,\ldots,\xi_{n-1}).
$$

### Poincaré covariance

For a scalar field,

$$
W_n(\Lambda x_1+a,\ldots,\Lambda x_n+a)
=
W_n(x_1,\ldots,x_n).
$$

For fields transforming in finite-dimensional representations $S_i(\Lambda)$, covariance includes the corresponding matrices. Schematically,

$$
W_n^{i_1\cdots i_n}(\Lambda x_1+a,\ldots,\Lambda x_n+a)
=
S_{i_1}{}^{j_1}(\Lambda)\cdots
S_{i_n}{}^{j_n}(\Lambda)
W_n^{j_1\cdots j_n}(x_1,\ldots,x_n),
$$

with the precise placement of indices depending on the field representation.

### Spectral support

Using the relative variables above, write

$$
w_n(\xi_1,\ldots,\xi_{n-1})
=
\int
\prod_{j=1}^{n-1}\frac{d^dp_j}{(2\pi)^d}
\, e^{-i\sum_j p_j\cdot \xi_j}
\widetilde w_n(p_1,\ldots,p_{n-1}).
$$

The spectral condition implies

$$
\operatorname{supp}\widetilde w_n
\subset
(\overline V_+)^{n-1}.
$$

This is the momentum-space version of positive energy. It is also the gateway to tube analyticity and the structural theorems behind CPT and spin–statistics.

### Locality

For two adjacent fields whose arguments are spacelike separated, locality gives a graded interchange rule. For bosonic scalar fields,

$$
W_n(\ldots,x_j,x_{j+1},\ldots)
=
W_n(\ldots,x_{j+1},x_j,\ldots)
$$

when $(x_j-x_{j+1})^2<0$, interpreted distributionally. For fermionic fields, the right side acquires the sign dictated by the $\mathbb Z_2$ grading.

This is not full permutation symmetry. It is a local statement attached to spacelike interchange. Timelike-ordered Wightman functions generally differ from one another.

### Hermiticity

For a Hermitian scalar field,

$$
\overline{W_n(x_1,\ldots,x_n)}
=
W_n(x_n,\ldots,x_1)
$$

as distributions. This is the correlation-function form of the operator identity $\phi(f)^*=\phi(\overline f)$ on the common domain, with the reversal coming from the adjoint of a product.

### Wightman positivity

Hilbert-space positivity becomes a family of inequalities for the $W_n$. Let $F=(f_0,f_1,\ldots,f_N)$ be a finite sequence with

$$
f_n\in \mathcal S((\mathbb M^d)^n),
\qquad f_0\in\mathbb C.
$$

For a scalar Hermitian field, define formally

$$
\Psi_F
=
\sum_{n=0}^N
\int f_n(x_1,\ldots,x_n)
\phi(x_1)\cdots\phi(x_n)\Omega
\, d^dx_1\cdots d^dx_n.
$$

Then $\langle\Psi_F,\Psi_F\rangle\ge0$ becomes

$$
\sum_{m,n=0}^N
\int
\overline{f_m(x_1,\ldots,x_m)}
 f_n(y_1,\ldots,y_n)
 W_{m+n}(x_m,\ldots,x_1,y_1,\ldots,y_n)
 \, dx\,dy
\ge0.
$$

This positivity condition is the indispensable bridge from distributions to a Hilbert space. Without it, one may have Lorentz-covariant distributions, but not a positive-norm quantum theory.

## The free scalar two-point function

For the free real scalar field of mass $m\ge0$, the two-point Wightman function is the positive-frequency distribution

$$
W_2(x,y)=\Delta_+(x-y),
$$

where

$$
\Delta_+(x)
=
\int \frac{d^dp}{(2\pi)^d}
\, 2\pi\theta(p^0)\delta(p^2-m^2)
 e^{-ip\cdot x}.
$$

This is not the Feynman propagator. It has support on the positive-energy mass shell in momentum space:

$$
\operatorname{supp}\widetilde\Delta_+
\subset
\overline V_+.
$$

For the centered free scalar field, $W_1=0$, and the higher Wightman functions are sums over pairings:

$$
W_{2r}(x_1,\ldots,x_{2r})
=
\sum_{\text{pairings}}
\prod_{(a,b)}\Delta_+(x_a-x_b),
\qquad
W_{2r+1}=0.
$$

This is Wick's theorem in Wightman-function language. In an interacting theory, higher Wightman functions contain genuinely new data.

## Relation to other correlators

Wightman functions are ordered vacuum correlators. Feynman correlators are time-ordered vacuum correlators:

$$
G_n(x_1,\ldots,x_n)
=
\langle\Omega,
T\{\phi(x_1)\cdots\phi(x_n)\}
\Omega\rangle.
$$

For two scalar fields,

$$
G_2(x,y)
=
\theta(x^0-y^0)W_2(x,y)
+
\theta(y^0-x^0)W_2(y,x),
$$

up to the usual distributional care at coincident times. The Feynman propagator is the object used in perturbation theory; the Wightman function is the object used in the axiomatic Hilbert-space reconstruction.

Schwinger functions are Euclidean correlation functions. Under Osterwalder–Schrader hypotheses, they analytically continue to Wightman functions. Euclidean invariance alone is not enough; reflection positivity is the Euclidean analogue of Hilbert-space positivity.

The Källén–Lehmann representation is a useful bridge for two-point functions. In a scalar theory with positive metric, the exact two-point Wightman function can be represented as a positive superposition of free positive-frequency two-point functions:

$$
W_2(x)
=
\int_0^\infty d\mu^2\,
\rho(\mu^2)\Delta_+^{(\mu)}(x),
\qquad
\rho(\mu^2)\ge0,
$$

under the usual assumptions. This positivity is a visible two-point shadow of Hilbert-space positivity.

## Reconstruction preview

The reconstruction theorem starts from a candidate sequence $\{W_n\}$ and builds a Hilbert space as follows.

First form the vector space of finite sequences of test functions,

$$
F=(f_0,f_1,\ldots,f_N).
$$

Second define a sesquilinear form using the Wightman positivity formula. Third quotient by the null vectors and complete. The class of $(1,0,0,\ldots)$ becomes the vacuum. Fields act by adding a test function at the front or back, depending on conventions. Translation and Lorentz transformations act by moving the test functions.

This construction explains why the properties of the $W_n$ are not arbitrary. Each is the correlation-function imprint of a Hilbert-space axiom:

$$
\begin{array}{c}
\text{positive Wightman distributions}\\
\text{with covariance, spectrum, and locality}
\end{array}
\quad\Longrightarrow\quad
\begin{array}{c}
\text{vacuum Hilbert-space QFT}\\
\text{with operator-valued distributions}
\end{array}
$$

[Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) states the theorem more carefully.

## Common pitfalls

**Treating Wightman functions as ordinary functions.** They are usually distributions. Products, restrictions, and coincident-point limits require distributional control.

**Confusing Wightman and Feynman correlators.** Wightman functions are ordered but not time-ordered. The Feynman propagator combines different Wightman orderings with step functions.

**Assuming full symmetry under permutations.** Locality gives graded symmetry under spacelike interchange. It does not say that timelike-ordered Wightman functions are equal.

**Forgetting positivity.** Covariant distributions with the right support do not automatically define a physical Hilbert space. Wightman positivity is the condition that makes reconstruction positive-norm.

**Ignoring field labels.** Spinor, vector, charged, and fermionic fields carry representation and grading data. Dropping indices can hide signs and covariance matrices.

**Assuming Euclidean correlators are automatically Wightman functions.** Analytic continuation from Euclidean data requires reflection positivity and the other Osterwalder–Schrader conditions.

## Relations to other pages

[Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) explains why vacuum matrix elements are enough to probe the Hilbert space sector. [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) explains the support property of $\widetilde w_n$. [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) explains the spacelike interchange rule.

[Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) turns the properties listed here into a Hilbert-space construction. The future Schwinger functions page will present the Euclidean analogue, where reflection positivity replaces Wightman positivity.

## Research status

The Wightman-function framework is a classic, established formulation of axiomatic QFT in Minkowski space. It is mathematically powerful because it turns operator-domain questions into distributional and analytic properties of vacuum expectation values.

Its limitations are also well known. Gauge theories may require working with gauge-invariant observables, indefinite auxiliary spaces, or BRST/BV cohomology. Theories with long-range massless forces may not have ordinary particle sectors. Curved-spacetime QFT replaces global energy-momentum spectrum by microlocal spectrum conditions. These are refinements of the basic idea, not reasons to ignore the Wightman-function viewpoint.

## Exercises

### Exercise 1: Translation invariance and relative variables

Assume $U(a)\Omega=\Omega$ and

$$
U(a)\phi(x)U(a)^{-1}=\phi(x+a).
$$

Show that $W_n(x_1+a,\ldots,x_n+a)=W_n(x_1,\ldots,x_n)$.

<details>
<summary><strong>Solution</strong></summary>

Using covariance and vacuum invariance,

$$
\begin{aligned}
W_n(x_1+a,\ldots,x_n+a)
&=
\langle\Omega,
U(a)\phi(x_1)U(a)^{-1}\cdots
U(a)\phi(x_n)U(a)^{-1}
\Omega\rangle \\
&=
\langle U(a)^{-1}\Omega,
\phi(x_1)\cdots\phi(x_n)
U(a)^{-1}\Omega\rangle \\
&=
W_n(x_1,\ldots,x_n).
\end{aligned}
$$

Thus $W_n$ depends only on translation-invariant differences, for example $x_1-x_2,\ldots,x_{n-1}-x_n$.

</details>

### Exercise 2: Positivity of the free two-point function

For the free scalar two-point function,

$$
W_2(f,g)
=
\int \frac{d^dp}{(2\pi)^d}
\,2\pi\theta(p^0)\delta(p^2-m^2)
\overline{\widetilde f(p)}\widetilde g(p),
$$

show that $W_2(f,f)\ge0$.

<details>
<summary><strong>Solution</strong></summary>

Setting $g=f$ gives

$$
W_2(f,f)
=
\int \frac{d^dp}{(2\pi)^d}
\,2\pi\theta(p^0)\delta(p^2-m^2)
|\widetilde f(p)|^2.
$$

The distribution $2\pi\theta(p^0)\delta(p^2-m^2)$ is a positive measure on the positive-energy mass shell. Since $|\widetilde f(p)|^2\ge0$, the integral is nonnegative. This is the one-particle version of Wightman positivity.

</details>

### Exercise 3: Wightman versus Feynman two-point functions

For a Hermitian scalar field, explain why

$$
G_2(x,y)
=
\theta(x^0-y^0)W_2(x,y)
+
\theta(y^0-x^0)W_2(y,x)
$$

is not the same distribution as $W_2(x,y)$.

<details>
<summary><strong>Solution</strong></summary>

$W_2(x,y)$ has a fixed operator ordering: $\phi(x)$ is to the left of $\phi(y)$. The time-ordered correlator changes the operator order depending on the sign of $x^0-y^0$. For $x^0>y^0$, it uses $W_2(x,y)$; for $y^0>x^0$, it uses $W_2(y,x)$.

In general $W_2(x,y)$ and $W_2(y,x)$ differ. Their difference is the vacuum expectation value of the commutator. Locality implies this difference vanishes at spacelike separation, but not at timelike separation. Therefore the Feynman two-point function and the Wightman two-point function are different distributions.

</details>

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.

### Deeper references

- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics III: Scattering Theory*, Academic Press.

## Version history

- **2026-06-28:** Updated relations after adding the reconstruction theorem page.
- **2026-06-28:** Initial polished draft.
