---
title: "Domains of Unbounded Operators"
description: "Explains why smeared quantum fields are typically unbounded operators and how common dense invariant domains make field algebra meaningful."
sidebar:
  label: "Domains of Unbounded Operators"
  order: 3
level: Graduate
status: "Polished draft"
source: "Reed–Simon; Streater–Wightman; Haag; Wightman; Schmüdgen; Hall; Nelson's analytic-vector theorem."
topics:
  - unbounded operators
  - operator domains
  - common invariant domains
  - smeared fields
  - Wightman fields
canonicalTopics:
  - unbounded-operator
  - operator-valued-distribution
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "Smeared fields in relativistic QFT are typically unbounded operators, so a common dense invariant domain is part of the mathematical data of a Wightman field theory."
    - "For free fields, the finite-particle domain is a standard common invariant core, and real smeared fields are essentially self-adjoint on suitable dense domains."
  active:
    - "For interacting theories, gauge theories, and composite fields, proving useful domain, closability, self-adjointness, and strong-commutativity properties remains framework-dependent."
---

## Summary

Smearing a quantum field fixes its point singularity, but it does **not** usually make the result a bounded operator. A smeared field $\phi(f)$ is typically an unbounded operator defined only on a dense subspace of the Hilbert space. The correct first sentence is therefore not

$$
\phi(f):\mathcal H\to\mathcal H,
$$

but rather

$$
\phi(f):\operatorname{Dom}(\phi(f))\subset\mathcal H
\longrightarrow \mathcal H.
$$

The practical repair is to choose a common dense invariant domain $\mathcal D\subset\mathcal H$ on which all finite products of smeared fields act:

$$
\mathcal D\subset \operatorname{Dom}(\phi(f)),
\qquad
\phi(f)\mathcal D\subset\mathcal D.
$$

Then algebraic field equations, commutators, covariance formulas, and Wightman functions are initially statements on $\mathcal D$. Closures, adjoints, self-adjointness, spectral projections, and exponentials are additional operator-theoretic questions.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Dense domains and closures for smeared fields](/figures/rigorous-qft/domains-and-closures.svg)

<figcaption>

Smeared fields are first controlled on a common dense invariant domain $\mathcal D$. The closure $\overline{\phi(f)}$, adjoint $\phi(f)^*$, and self-adjoint extensions are extra operator-theoretic data, not automatic consequences of the symbol $\phi(f)$.

</figcaption>
</figure>

## Prerequisites

You should know why fields are smeared from [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and the test-function language from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

A first course in Hilbert spaces is helpful: dense subspaces, adjoints, symmetric operators, and the spectral theorem. The page reviews the needed vocabulary but does not replace a functional analysis course.

## Core idea

A bounded operator on a Hilbert space is defined on all of $\mathcal H$ and satisfies

$$
\|A\Psi\|\le C\|\Psi\|
\qquad
\text{for all }\Psi\in\mathcal H.
$$

Most observables in quantum mechanics are not bounded. Position, momentum, Hamiltonians, number operators, and fields all have spectra that are not confined to a finite interval. Their natural domains are proper dense subspaces.

Quantum fields inherit both difficulties at once. First, the point field $\phi(x)$ is distributional, so it must be smeared. Second, even after smearing, $\phi(f)$ changes particle number and behaves like a sum of creation and annihilation operators. It is therefore usually unbounded.

The Wightman framework handles this by treating a field as an operator-valued distribution on a common dense domain:

$$
f\longmapsto \phi(f),
\qquad
\phi(f)\in\operatorname{End}(\mathcal D),
$$

where $\operatorname{End}(\mathcal D)$ means linear maps $\mathcal D\to\mathcal D$, not necessarily bounded operators on $\mathcal H$.

The moral is simple but load-bearing:

$$
\text{smearing controls spacetime singularities};
\qquad
\text{domains control operator singularities}.
$$

## Setup and conventions

Let $\mathcal H$ be a complex Hilbert space. A possibly unbounded linear operator $A$ consists of a linear subspace $\operatorname{Dom}(A)\subset\mathcal H$ and a linear map

$$
A:\operatorname{Dom}(A)\to\mathcal H.
$$

The operator is **densely defined** if $\operatorname{Dom}(A)$ is dense in $\mathcal H$. Density is essential because the Hilbert-space adjoint $A^*$ is defined using inner products against all vectors in a dense domain.

For a Wightman field, one usually specifies a dense subspace $\mathcal D\subset\mathcal H$ such that

$$
\Omega\in\mathcal D,
\qquad
\phi_i(f)\mathcal D\subset\mathcal D,
\qquad
U(g)\mathcal D\subset\mathcal D,
$$

for all test functions $f$, field labels $i$, and Poincaré transformations $g$ in the relevant connected group. Algebraic formulas are then read as formulas on $\mathcal D$.

For example, a commutator identity means

$$
[A,B]\Psi
=
AB\Psi-BA\Psi,
\qquad
\Psi\in\mathcal D,
$$

with $A\mathcal D\subset\mathcal D$ and $B\mathcal D\subset\mathcal D$ ensuring that both products are defined on $\mathcal D$.

## Why smeared fields are unbounded

The simplest reason is already visible in the harmonic oscillator. Let $a^*$ be the creation operator on Fock space. On normalized $n$-particle oscillator states,

$$
a^*|n\rangle=\sqrt{n+1}\,|n+1\rangle.
$$

Thus

$$
\|a^*|n\rangle\|=\sqrt{n+1},
$$

which is not bounded uniformly in $n$. Hence $a^*$ cannot extend to a bounded operator on the whole Hilbert space.

A free scalar field has the same structure. In Fock-space notation,

$$
\phi(f)=a^*(f_+)+a(\overline{f_+}),
$$

up to convention-dependent complex conjugations. The creation part raises particle number with a factor growing like $\sqrt{n+1}$. Therefore $\phi(f)$ is typically unbounded even when $f$ is a perfectly smooth test function.

There is also a general obstruction behind canonical commutation relations. If two bounded operators $A,B$ obeyed

$$
[A,B]=iI,
$$

then repeated commutators would force impossible norm estimates. This is the content of the Wintner-type obstruction to bounded canonical commutation relations. At least one of the canonical variables must be unbounded.

The lesson for QFT is that one should not expect field operators to be globally defined bounded maps. The best one can usually ask for is a well-chosen dense domain on which the field algebra acts.

## The finite-particle domain

For free fields, the standard model domain is the finite-particle domain

$$
\mathcal F_{\mathrm{fin}}
=
\bigoplus_{n=0}^{\mathrm{finite}}\mathcal H_n,
$$

where only finitely many particle-number components are nonzero. More explicitly, a vector in $\mathcal F_{\mathrm{fin}}$ is a finite sum

$$
\Psi=\Psi_0\oplus\Psi_1\oplus\cdots\oplus\Psi_N.
$$

Creation and annihilation operators send finite-particle vectors to finite-particle vectors:

$$
a^*(h)\mathcal F_{\mathrm{fin}}\subset\mathcal F_{\mathrm{fin}},
\qquad
 a(h)\mathcal F_{\mathrm{fin}}\subset\mathcal F_{\mathrm{fin}}.
$$

Therefore the free smeared field satisfies

$$
\phi(f)\mathcal F_{\mathrm{fin}}
\subset\mathcal F_{\mathrm{fin}}.
$$

This is why finite-particle vectors are the cleanest elementary example of a common invariant domain. They are not the whole Hilbert space, but they are dense and stable under the algebraic operations that appear in field formulas.

For real test functions $f$, the free scalar $\phi(f)$ is symmetric on this domain and is essentially self-adjoint under standard hypotheses. Its closure is the self-adjoint field operator used to define spectral projections and exponentials.

## The Wightman domain

In an abstract Wightman theory, a canonical dense domain is generated from the vacuum by polynomials in smeared fields:

$$
\mathcal D_W
=
\operatorname{span}
\left\{
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega:
 n\ge0
\right\}.
$$

The case $n=0$ means the vector $\Omega$ itself. Vacuum cyclicity says that this domain is dense in $\mathcal H$:

$$
\overline{\mathcal D_W}=\mathcal H.
$$

By construction, applying another smeared field to a vector of this form gives another vector of the same form:

$$
\phi_j(g)
\bigl(
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega
\bigr)
=
\phi_j(g)\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega.
$$

Thus $\mathcal D_W$ is invariant under the field algebra. This is the domain on which Wightman functions are most naturally encoded as inner products of field-polynomial vectors.

The important point is that $\mathcal D_W$ is an algebraic domain. It lets one define the products needed for correlation functions and local commutativity. It does not by itself answer every question about closures, spectral projections, or self-adjoint extensions.

## Symmetric, self-adjoint, and essentially self-adjoint

Let $A$ be densely defined. Its adjoint $A^*$ is the operator whose domain consists of those $\Psi\in\mathcal H$ for which the map

$$
\Phi\longmapsto \langle \Psi,A\Phi\rangle,
\qquad
\Phi\in\operatorname{Dom}(A),
$$

is continuous in the Hilbert norm. Then there is a vector $A^*\Psi$ satisfying

$$
\langle A^*\Psi,\Phi\rangle
=
\langle \Psi,A\Phi\rangle
$$

up to the convention for which slot is linear. The convention does not change the domain issue.

An operator $A$ is **symmetric** if

$$
A\subset A^*.
$$

This means

$$
\langle \Psi,A\Phi\rangle
=
\langle A\Psi,\Phi\rangle
$$

for all $\Psi,\Phi\in\operatorname{Dom}(A)$, again up to inner-product convention. A symmetric operator is not necessarily self-adjoint.

An operator is **self-adjoint** if

$$
A=A^*,
$$

including equality of domains. This is the condition needed for the spectral theorem and for Stone's theorem to produce a one-parameter unitary group $e^{itA}$.

A symmetric operator is **essentially self-adjoint** on a domain $\mathcal D$ if its closure is self-adjoint. In that case, the formula on $\mathcal D$ determines a unique self-adjoint operator.

This distinction matters for real fields. The formal Hermiticity condition

$$
\phi(f)^\dagger=\phi(f)
\qquad
\text{for real } f
$$

should first be read as symmetry on a dense domain. Self-adjointness, or essential self-adjointness on a chosen core, is a stronger statement.

## Closures and cores

The graph of an operator $A$ is

$$
\Gamma(A)=
\{(\Psi,A\Psi):\Psi\in\operatorname{Dom}(A)\}
\subset \mathcal H\oplus\mathcal H.
$$

The operator is **closed** if $\Gamma(A)$ is closed. It is **closable** if the closure of $\Gamma(A)$ is itself the graph of an operator, denoted $\overline A$.

A subspace $\mathcal C\subset\operatorname{Dom}(A)$ is a **core** for a closed operator $A$ if the closure of $A|_{\mathcal C}$ is $A$. Equivalently, $\mathcal C$ is dense in $\operatorname{Dom}(A)$ in the graph norm

$$
\|\Psi\|_A^2
=
\|\Psi\|^2+
\|A\Psi\|^2.
$$

For free fields, finite-particle vectors are often cores for the closures of smeared fields and for many polynomial expressions. In interacting theories, identifying good cores can be much harder.

The distinction between an operator and its closure is not cosmetic. Two operators may agree on a small domain but have different closures if the domain is not a core. Conversely, a formula proved on a core can determine a closed operator uniquely.

## Products and commutators need domains

If $A$ and $B$ are unbounded, then the product $AB$ is not automatically defined on $\operatorname{Dom}(B)$. Its domain is

$$
\operatorname{Dom}(AB)
=
\{
\Psi\in\operatorname{Dom}(B):
B\Psi\in\operatorname{Dom}(A)
\}.
$$

The commutator $[A,B]$ is defined only where both $AB$ and $BA$ are defined. A common invariant domain $\mathcal D$ avoids this problem for algebraic field manipulations because

$$
A\mathcal D\subset\mathcal D,
\qquad
B\mathcal D\subset\mathcal D
\quad\Longrightarrow\quad
AB\mathcal D\subset\mathcal H,
\quad
BA\mathcal D\subset\mathcal H.
$$

Thus a local commutativity statement such as

$$
[\phi(f),\phi(g)]\Psi=0,
\qquad
\Psi\in\mathcal D,
$$

is meaningful even when the closed operators $\overline{\phi(f)}$ and $\overline{\phi(g)}$ have complicated domains.

One must not silently upgrade this to every possible stronger statement. In particular, there is a difference between:

| Statement | Meaning |
|---|---|
| $[A,B]\Psi=0$ on $\mathcal D$ | Algebraic commutation on a chosen invariant domain. |
| $\overline A\,\overline B=\overline B\,\overline A$ | Equality of closed products on their domains. |
| $e^{it\overline A}e^{is\overline B}=e^{is\overline B}e^{it\overline A}$ | Strong commutativity of self-adjoint operators. |
| Local von Neumann algebras commute | Bounded spectral or algebraic observables commute. |

Algebraic QFT often avoids unbounded point-field domains by assigning bounded operator algebras to spacetime regions. That does not make point fields disappear; it changes which objects are taken as primitive.

## Weak, strong, and quadratic-form readings

Many formulas involving unbounded operators have several possible levels of meaning.

A **strong domain statement** says

$$
A\Psi=B\Psi
\qquad
\text{for all }\Psi\in\mathcal D.
$$

A **weak statement** says

$$
\langle \Xi,A\Psi\rangle
=
\langle \Xi,B\Psi\rangle
\qquad
\text{for all }\Xi,\Psi\in\mathcal D.
$$

A **quadratic-form statement** may define an expression only through matrix elements

$$
Q(\Xi,\Psi),
\qquad
\Xi,\Psi\in\mathcal Q,
$$

without first constructing an operator on a domain. Hamiltonians and stress tensors often appear naturally as forms before they appear as self-adjoint operators.

When reading a rigorous QFT statement, always ask which level is being claimed. Physics notation often uses the same symbol for all three.

## Covariance and domains

Suppose a field transforms covariantly under a unitary representation $U(g)$ of the Poincaré group. A scalar field formula is often written

$$
U(g)\phi(f)U(g)^{-1}
=
\phi(f_g),
$$

where $f_g$ is the transformed test function. For this formula to be a genuine operator statement on a common domain, one needs

$$
U(g)\mathcal D\subset\mathcal D,
\qquad
U(g)^{-1}\mathcal D\subset\mathcal D.
$$

Then for $\Psi\in\mathcal D$ the expression

$$
U(g)\phi(f)U(g)^{-1}\Psi
$$

is defined because $U(g)^{-1}\Psi$ is again in $\mathcal D$, $\phi(f)$ maps it back into $\mathcal D$, and $U(g)$ maps that vector into $\mathcal D$.

Without a domain-invariance statement, a covariance formula for unbounded fields is incomplete.

## How bounded algebras enter

Given a self-adjoint smeared field $\overline{\phi(f)}$, the spectral theorem produces bounded operators such as

$$
e^{it\overline{\phi(f)}}.
$$

For free bosonic fields, the Weyl operators

$$
W(f)=e^{i\overline{\phi(f)}}
$$

are bounded unitaries satisfying a Weyl form of the canonical commutation relations. One can build local algebras from such bounded operators.

This explains a common bridge between Wightman and algebraic viewpoints:

$$
\text{unbounded smeared fields}
\quad\leadsto\quad
\text{bounded functions or exponentials}
\quad\leadsto\quad
\text{local operator algebras}.
$$

The bridge is powerful but not automatic. It requires self-adjointness and, for locality at the algebra level, appropriate strong commutativity properties.

## Common pitfalls

**Thinking smearing makes fields bounded.** Smearing turns point fields into operator-valued objects, but those operators are still usually unbounded.

**Writing adjoints without domains.** The equality $A=A^*$ includes equality of domains. Symmetry on a common domain is weaker.

**Confusing formal Hermiticity with an observable.** A symmetric operator may fail to be self-adjoint. A physical observable requires a self-adjoint operator, or an appropriate algebraic replacement.

**Multiplying unbounded operators freely.** The product $AB$ has its own domain. It is not defined merely because $A$ and $B$ are each densely defined.

**Assuming a commutator on a core implies strong commutativity.** Vanishing of $[A,B]$ on $\mathcal D$ is not the same as commutation of spectral projections.

**Treating the Wightman domain as all of Hilbert space.** The field-polynomial domain is dense, but dense is not the same as complete.

## Relations to other pages

- [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) explains why point fields need smearing.
- [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) explains the test-function side of the construction.
- [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) uses common dense invariant domains as part of the axiomatic definition.
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) addresses a different problem: when singular distributions can be multiplied.

Later pages on equal-time fields, Wick products, and time-ordered products will combine both issues: distributional singularities and operator-domain control.

## Research status

For free fields, the domain story is well understood. The finite-particle domain is dense and invariant, smeared fields are closable, and real smeared scalar fields are essentially self-adjoint on standard cores. Nelson's analytic-vector methods give a robust way of proving essential self-adjointness in many Fock-space situations.

For axiomatic QFT, the use of common dense invariant domains is part of the standard Wightman setup. Many general theorems are formulated at this domain level.

For interacting QFT, domain questions become part of construction. A model is not fully under mathematical control merely because its correlation functions have plausible formulas. One must specify Hilbert space, domains, field operators or local algebras, positivity, covariance, and limiting procedures. Gauge theories add a further complication: gauge-fixed fields may live in indefinite-metric spaces, while physical fields or observables may need BRST/BV cohomology or local algebraic formulations.

## Exercises

### Exercise 1: Creation operators are unbounded

Let $a^*$ be the creation operator of a harmonic oscillator, with

$$
a^*|n\rangle=\sqrt{n+1}\,|n+1\rangle.
$$

Show that $a^*$ is not bounded.

<details>
<summary><strong>Solution</strong></summary>

If $a^*$ were bounded, there would be a constant $C$ such that

$$
\|a^*\Psi\|\le C\|\Psi\|
$$

for all vectors in its domain and hence, by extension, for all normalized basis vectors. But

$$
\|a^*|n\rangle\|=\sqrt{n+1}\,
\||n+1\rangle\|=\sqrt{n+1},
$$

which becomes arbitrarily large while $\||n\rangle\|=1$. No uniform $C$ exists.

</details>

### Exercise 2: Product domains

Let $A$ and $B$ be unbounded operators. Explain why $\Psi\in\operatorname{Dom}(B)$ is not enough to define $AB\Psi$.

<details>
<summary><strong>Solution</strong></summary>

The expression $AB\Psi$ means first apply $B$ to $\Psi$, then apply $A$ to the result. Thus we need

$$
\Psi\in\operatorname{Dom}(B)
\quad\text{and}\quad
B\Psi\in\operatorname{Dom}(A).
$$

The second condition is not automatic. Therefore

$$
\operatorname{Dom}(AB)
=
\{
\Psi\in\operatorname{Dom}(B):B\Psi\in\operatorname{Dom}(A)
\}.
$$

A common invariant domain $\mathcal D$ is useful because $B\mathcal D\subset\mathcal D\subset\operatorname{Dom}(A)$.

</details>

### Exercise 3: Symmetric is not the same as self-adjoint

Why is the condition

$$
\langle \Psi,A\Phi\rangle
=
\langle A\Psi,\Phi\rangle
$$

on a dense domain weaker than $A=A^*$?

<details>
<summary><strong>Solution</strong></summary>

The displayed identity says that $A$ is symmetric on its domain, equivalently $A\subset A^*$. Self-adjointness requires equality of operators, including equality of domains:

$$
\operatorname{Dom}(A)=\operatorname{Dom}(A^*)
\quad\text{and}\quad
A\Psi=A^*\Psi.
$$

A symmetric differential operator on a small domain may have adjoint vectors satisfying different boundary behavior. Then $\operatorname{Dom}(A^*)$ is larger than $\operatorname{Dom}(A)$, so $A$ is not self-adjoint even though the integration-by-parts identity holds on the small domain.

</details>

### Exercise 4: The Wightman polynomial domain

Let

$$
\mathcal D_W
=
\operatorname{span}\{
\phi(f_1)\cdots\phi(f_n)\Omega:n\ge0
\}.
$$

Assuming all products are defined on $\mathcal D_W$, show that $\mathcal D_W$ is invariant under every smeared field $\phi(g)$.

<details>
<summary><strong>Solution</strong></summary>

A typical generator of $\mathcal D_W$ has the form

$$
\phi(f_1)\cdots\phi(f_n)\Omega.
$$

Applying $\phi(g)$ gives

$$
\phi(g)\phi(f_1)\cdots\phi(f_n)\Omega,
$$

which is again a finite product of smeared fields applied to the vacuum. Hence it is one of the generating vectors of $\mathcal D_W$. By linearity, $\phi(g)\mathcal D_W\subset\mathcal D_W$.

</details>

### Exercise 5: Why exponentials are extra data

A real smeared field $\phi(f)$ is symmetric on $\mathcal D$. Why does this not automatically define a unitary $e^{it\phi(f)}$?

<details>
<summary><strong>Solution</strong></summary>

Stone's theorem produces a one-parameter unitary group from a self-adjoint operator, not merely from a symmetric operator on a dense domain. If $\phi(f)$ is only known to be symmetric, it may have zero, one, or many self-adjoint extensions. To define $e^{it\phi(f)}$ unambiguously, one needs a chosen self-adjoint operator, often the closure when $\phi(f)$ is essentially self-adjoint on the domain.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis*, Academic Press.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- K. Schmüdgen, *Unbounded Self-adjoint Operators on Hilbert Space*, Springer. DOI: [10.1007/978-94-007-4753-1](https://doi.org/10.1007/978-94-007-4753-1).
- B. C. Hall, *Quantum Theory for Mathematicians*, Springer. DOI: [10.1007/978-1-4614-7116-5](https://doi.org/10.1007/978-1-4614-7116-5).
- E. Nelson, "Analytic Vectors," *Annals of Mathematics* **70** (1959), 572–615. DOI: [10.2307/1970331](https://doi.org/10.2307/1970331).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- A. S. Wightman, "How It Was Learned that Quantized Fields Are Operator-Valued Distributions," *Fortschritte der Physik* **44** (1996), 143–178. DOI: [10.1002/prop.2190440204](https://doi.org/10.1002/prop.2190440204).
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).

## Version history

- **2026-06-28:** Initial polished draft for the Operator-Valued Distributions chapter.
