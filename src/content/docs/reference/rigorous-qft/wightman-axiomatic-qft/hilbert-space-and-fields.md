---
title: "Hilbert Space and Fields"
description: "Explains the Hilbert-space, vacuum, domain, and operator-valued-distribution data used in Wightman QFT."
sidebar:
  label: "Hilbert Space and Fields"
  order: 2
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Haag; Reed–Simon; Glimm–Jaffe."
topics:
  - Wightman fields
  - Hilbert space
  - vacuum sector
  - common domains
  - field polynomials
canonicalTopics:
  - wightman-axioms
  - hilbert-space-quantum-field-theory
  - operator-valued-distribution
researchStatus:
  established:
    - "In the Wightman framework, fields are operator-valued distributions on a positive Hilbert space with a common dense invariant domain."
    - "Vacuum cyclicity makes polynomial field vectors dense, so vacuum correlation functions determine the theory up to unitary equivalence after reconstruction."
  active:
    - "For interacting and gauge theories, constructing the physical Hilbert space, the correct fields or observables, and useful domains is often the hard part rather than a preliminary formality."
---

## Summary

A Wightman theory is not merely a list of correlation functions and not merely a classical action with hats added. Its Lorentzian data include a positive Hilbert space of states, a vacuum vector, a common dense domain, and fields that become operators only after smearing:

$$
(\mathcal H,U,\Omega,\mathcal D,\{\phi_i\}).
$$

Here $\mathcal H$ is the physical Hilbert space, $U$ is the unitary representation of spacetime symmetries, $\Omega$ is the vacuum, $\mathcal D$ is a common dense invariant domain, and each field is a map

$$
\phi_i:\mathcal S(\mathbb R^d)\longrightarrow
\operatorname{End}(\mathcal D),
\qquad
f\longmapsto \phi_i(f).
$$

The dense domain is not decorative. Smeared fields are usually unbounded operators, so products such as $\phi(f_1)\phi(f_2)\Omega$ are initially meaningful because $\Omega\in\mathcal D$ and $\phi(f)\mathcal D\subset\mathcal D$.

The key density condition is vacuum cyclicity:

$$
\overline{\operatorname{span}}
\{\phi_{i_1}(f_1)\cdots \phi_{i_n}(f_n)\Omega:n\ge0\}
=\mathcal H.
$$

This page explains what these objects mean before the later pages impose covariance, spectrum, locality, and reconstruction.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Hilbert-space data for Wightman fields](/figures/rigorous-qft/wightman-hilbert-field-data.svg)

<figcaption>

The Wightman field data keep three levels separate: test functions, unbounded smeared fields on a common dense domain, and Hilbert-space states obtained by applying field polynomials to the vacuum.

</figcaption>
</figure>

## Prerequisites

You should know the distributional viewpoint from [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), the smearing language from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and the operator-domain warnings from [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/).

It is also helpful to have read [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) once, even if the full list of axioms becomes clearer only after this page.

## Core idea

The Wightman framework begins from the part of quantum theory that should survive without perturbation theory: a positive Hilbert space of states and local fields acting on it as distributional operators.

The phrase **positive Hilbert space** means that the inner product is genuinely positive definite:

$$
\|\Psi\|^2=\langle\Psi,\Psi\rangle\ge0,
\qquad
\|\Psi\|=0\Longleftrightarrow \Psi=0.
$$

This is a physical condition, not a cosmetic one. It is what lets vectors represent states and probabilities. Covariant gauge-fixed formalisms often pass through ghosts or indefinite inner products, but a Wightman theory is stated on the physical Hilbert space or on a field system whose inner product is already positive.

The phrase **field** means something subtler than an operator at a point. A field is a distribution-valued operator assignment. For each test function $f$, one obtains an operator $\phi(f)$ on a common domain $\mathcal D$.

The phrase **common domain** means that all the finite field products used to build states and correlation functions share a controlled initial domain:

$$
\Omega\in\mathcal D,
\qquad
\phi_i(f)\mathcal D\subset\mathcal D.
$$

The phrase **vacuum sector** means that the Hilbert space is generated, after closure, by applying local field polynomials to a distinguished invariant vector $\Omega$. This is the sector described by the vacuum Wightman functions.

A compact slogan is:

$$
\text{Wightman Hilbert space}
=
\overline{\text{field polynomials acting on the vacuum}}.
$$

## Setup and conventions

Work on $d$-dimensional Minkowski space, usually $d=4$, with the mostly-minus metric convention fixed in [Conventions and Logical Status](/rigorous-qft/conventions/). In the basic Wightman setting, test functions are Schwartz functions:

$$
f\in\mathcal S(\mathbb R^d).
$$

For fields with spin or internal labels, write $\phi_i$, where $i$ may stand for a component, tensor index, spinor index, flavor label, or a combined field label. A smeared multiplet may be written schematically as

$$
\phi(f)=\sum_i \phi_i(f^i),
\qquad
f=(f^i)_i.
$$

The Hilbert-space inner product is written in bra-ket order as $\langle\Psi,\Phi\rangle$. Operator adjoints are denoted by $A^*$, and domain inclusions are always part of a statement about unbounded operators.

The finite field-polynomial vectors are

$$
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega,
\qquad
n\ge0.
$$

For $n=0$, this vector is just $\Omega$.

## The Hilbert space is physical, not automatically Fock

In a free scalar theory, one constructs $\mathcal H$ as a symmetric Fock space. This is an example, not a Wightman axiom. The Wightman framework does not assume that interacting theories have a preferred particle-number decomposition.

A general Wightman Hilbert space is a representation space for the field algebra and spacetime symmetry. The axioms require a positive Hilbert space, a vacuum, and a unitary action of the Poincaré group, but they do not require a canonical splitting

$$
\mathcal H
\stackrel{?}{=}
\mathbb C\Omega\oplus\mathcal H_1\oplus\mathcal H_2\oplus\cdots .
$$

Such a splitting may exist in a free theory or in an asymptotic scattering theory. It is not part of the starting definition of a local interacting theory.

This distinction prevents a common misconception: **canonical quantization intuition is allowed as motivation, but Fock space is not the definition of QFT**. Haag's theorem and related results warn that the interaction picture cannot generally be implemented as a unitary equivalence between a free Fock representation and an interacting field representation at fixed time.

## The vacuum vector

The vacuum is a unit vector

$$
\Omega\in\mathcal H,
\qquad
\|\Omega\|=1.
$$

In the full Wightman setting it is invariant under Poincaré transformations:

$$
U(g)\Omega=\Omega.
$$

This page focuses on the Hilbert-space role of $\Omega$. It is the reference vector from which vacuum expectation values are computed:

$$
W_{i_1\cdots i_n}(f_1,\ldots,f_n)
=
\langle\Omega,
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)
\Omega\rangle.
$$

It is also the cyclic vector for the field system. Cyclicity says that vectors obtained from the vacuum by finite field operations are dense. It does **not** say that every vector is literally a finite field-polynomial state. Most vectors in a Hilbert space are limits.

Some formulations include uniqueness of the vacuum as an axiom. Others add it when cluster properties or scattering questions are discussed. If several translation-invariant vacua exist, one is usually describing a chosen vacuum sector rather than all phases at once.

## The common dense domain

A field $\phi(f)$ is typically unbounded, so it is not an operator $\mathcal H\to\mathcal H$. The Wightman repair is to specify a dense subspace $\mathcal D$ satisfying

$$
\Omega\in\mathcal D,
\qquad
\phi_i(f)\mathcal D\subset\mathcal D,
\qquad
U(g)\mathcal D\subset\mathcal D.
$$

Then finite products are well-defined on $\mathcal D$:

$$
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n):
\mathcal D\longrightarrow\mathcal D.
$$

This is the right level of control for algebraic field identities. For example, locality is first a statement such as

$$
[\phi_i(f),\phi_j(g)]\Psi=0,
\qquad
\Psi\in\mathcal D,
$$

when the supports of $f$ and $g$ are spacelike separated.

Closures, adjoints, self-adjoint extensions, and exponentials are later operator-theoretic questions. A formal expression such as $e^{i\phi(f)}$ is not automatically defined just because $\phi(f)$ is symmetric on $\mathcal D$.

## Fields as weakly continuous operator-valued distributions

For each field label $i$, the map

$$
f\longmapsto \phi_i(f)
$$

is linear. The distributional requirement is usually expressed through matrix elements. For every $\Psi,\Phi\in\mathcal D$, the map

$$
f\longmapsto
\langle\Psi,\phi_i(f)\Phi\rangle
$$

is a tempered distribution. In other words,

$$
\langle\Psi,\phi_i(\,\bullet\,)\Phi\rangle
\in\mathcal S'(\mathbb R^d).
$$

This is often called **weak distributional continuity**. It is weaker than saying $f\mapsto\phi_i(f)$ is continuous in operator norm; operator norm would be much too strong for unbounded fields.

The point-field notation

$$
\phi_i(x)
$$

is shorthand for the distributional kernel of this assignment. The actual operator input is $\phi_i(f)$.

## Hermitian fields and adjoints

A real scalar field is expected to be Hermitian. In the unbounded setting, the safe first statement is an adjoint inclusion:

$$
\phi(f)^*\supset \phi(\overline f).
$$

For real-valued $f$, this says $\phi(f)$ is symmetric on the common domain:

$$
\langle\Psi,\phi(f)\Phi\rangle
=
\langle\phi(f)\Psi,\Phi\rangle,
\qquad
\Psi,\Phi\in\mathcal D.
$$

Symmetry is not the same as self-adjointness. A symmetric operator may have no self-adjoint extension, one self-adjoint closure, or many self-adjoint extensions. In many free-field cases, real smeared fields are essentially self-adjoint on natural finite-particle domains, but this is a theorem about a model, not a consequence of notation alone.

For charged fields, the adjoint field is usually a different field:

$$
\phi(f)^*\supset \phi^*(\overline f).
$$

For gauge-theory fields, extra care is needed because gauge-dependent objects may live in an auxiliary indefinite-metric or BRST space before passing to physical states.

## Field-polynomial vectors

Define the algebraic field-polynomial vectors by finite sums of the form

$$
\Psi
=
\sum_\alpha c_\alpha
\phi_{i_{\alpha,1}}(f_{\alpha,1})
\cdots
\phi_{i_{\alpha,n_\alpha}}(f_{\alpha,n_\alpha})
\Omega.
$$

These vectors are the basic test states of the Wightman framework. Their inner products are completely expressible in terms of Wightman functions.

For example, if the fields are Hermitian scalars and domain issues are controlled, then

$$
\begin{aligned}
&\left\langle
\phi(f_1)\cdots\phi(f_m)\Omega,
\phi(g_1)\cdots\phi(g_n)\Omega
\right\rangle \\
&\hspace{2rem}=
\left\langle\Omega,
\phi(f_m)^*\cdots\phi(f_1)^*
\phi(g_1)\cdots\phi(g_n)
\Omega\right\rangle .
\end{aligned}
$$

Thus field-polynomial inner products are correlation functions. Positivity of the Hilbert-space norm gives the Wightman positivity condition:

$$
\|\Psi\|^2\ge0
$$

for every finite field-polynomial vector $\Psi$.

## Cyclicity and reconstruction

Vacuum cyclicity says

$$
\mathcal H
=
\overline{\mathcal D_{\operatorname{poly}}},
$$

where

$$
\mathcal D_{\operatorname{poly}}
=
\operatorname{span}
\{\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega:n\ge0\}.
$$

This condition is what makes vacuum correlation functions complete data. If two cyclic Wightman field systems have the same Wightman functions, then the map

$$
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega
\longmapsto
\phi'_{i_1}(f_1)\cdots\phi'_{i_n}(f_n)\Omega'
$$

preserves all inner products on a dense subspace. After quotienting any null vectors and completing, it extends to a unitary equivalence under the hypotheses of the reconstruction theorem.

Without cyclicity, there could be an invisible orthogonal sector not generated by fields acting on $\Omega$. Vacuum expectation values would then fail to determine the full Hilbert space.

## Example: the free scalar Hilbert space

For the free real scalar field of mass $m\ge0$, the one-particle Hilbert space is

$$
\mathcal H_1=L^2(\Sigma_m^+,d\mu_m),
$$

where

$$
\Sigma_m^+=\{p:p^2=m^2,\ p^0>0\},
\qquad
d\mu_m(p)=
\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}2E_{\mathbf p}},
$$

and $E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}$.

The full Hilbert space is the symmetric Fock space

$$
\mathcal H=\mathcal F_s(\mathcal H_1),
$$

and a standard common domain is the finite-particle subspace

$$
\mathcal D_{\operatorname{fin}}
=\bigoplus_{n=0}^{\infty,\mathrm{alg}}
\mathcal H_1^{\widehat\otimes_s n}.
$$

Here $\mathrm{alg}$ means the algebraic direct sum: vectors have only finitely many nonzero particle-number components.

The smeared field has the schematic form

$$
\phi(f)=a^*(f_+)+a(\overline{f_+}),
$$

where $f_+$ is the positive-energy mass-shell part of the Fourier transform of $f$. Creation raises particle number by one and annihilation lowers it by one, so $\phi(f)$ preserves $\mathcal D_{\operatorname{fin}}$.

This example is important because it shows all the abstract clauses concretely. It is also dangerous if overgeneralized: an interacting Wightman theory need not be a free Fock representation.

## Example: fields versus observables

In many theories, the fields used to generate states are not themselves gauge-invariant observables. A charged scalar field, for example, may create a charged state from the vacuum, while neutral observables are generated by gauge-invariant or charge-neutral combinations.

The Wightman field system may therefore be larger than the observable system. Algebraic QFT often reverses the emphasis and begins from local observable algebras. Superselection sectors are then studied as representations or charged field extensions.

This distinction matters because a page may say "field" in one of three ways:

| Word | Meaning | Typical framework |
|---|---|---|
| Pointlike Wightman field | Operator-valued distribution generating states. | Wightman QFT. |
| Observable field | Gauge-invariant local quantity. | Wightman or algebraic QFT. |
| Auxiliary gauge-fixed field | Variable in a gauge-fixed formalism, possibly with ghosts. | BRST/BV or perturbative QFT. |

Confusing these meanings is a common source of false claims about whether a model satisfies Wightman axioms.

## Common pitfalls

**Assuming the Hilbert space is Fock.** Fock space is the free-field example. It is not part of the general Wightman definition.

**Treating the dense domain as a convenience.** The common domain is what makes products of unbounded fields meaningful.

**Saying every state is a field-polynomial state.** Cyclicity gives density after closure, not literal equality for every vector.

**Forgetting null vectors in reconstruction.** Correlation functions define a positive semidefinite form first. One must quotient zero-norm vectors before completing to a Hilbert space.

**Confusing fields and observables.** Charged fields, gauge-dependent fields, and gauge-invariant observables may have different mathematical status.

**Replacing weak distributional continuity by operator-norm continuity.** The matrix elements are distributions; the smeared fields are generally unbounded.

## Relations to other pages

- [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) states the full axiom system in which this page supplies the Hilbert-space and field clauses.
- [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/) explains the operator-theoretic language behind $\mathcal D$.
- [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) adds the spacetime symmetry action $U(g)$ and the covariance law for fields.

Later pages will treat the spectral condition, locality, vacuum cyclicity in more detail, Wightman functions, and reconstruction.

## Research status

The Hilbert-space and operator-valued-distribution clauses of Wightman QFT are established parts of axiomatic QFT. They are satisfied by free fields and by many rigorously constructed low-dimensional models.

The hard part is usually construction. For an interacting model, one must construct $\mathcal H$, $\Omega$, $\mathcal D$, and $\phi_i(f)$, then prove positivity, covariance, spectrum, locality, and cyclicity. For gauge theories, one must also identify the physical Hilbert space and the correct observable or charged-field content.

In modern rigorous QFT, related structures appear in several frameworks: GNS representations in algebraic QFT, reflection-positive reconstruction in Euclidean QFT, Hilbert-space representations of local nets, and state spaces of factorization-algebraic or functorial theories under additional hypotheses.

## Exercises

### Exercise 1: Cyclicity and invisible sectors

Suppose $\mathcal H=\mathcal H_0\oplus\mathcal K$, the fields act only on $\mathcal H_0$, and $\Omega\in\mathcal H_0$. Explain why vacuum Wightman functions cannot detect $\mathcal K$.

<details>
<summary><strong>Solution</strong></summary>

Every field-polynomial vector has the form

$$
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega\in\mathcal H_0,
$$

because the fields preserve $\mathcal H_0$ and $\Omega\in\mathcal H_0$. Therefore every vacuum expectation value is an inner product entirely inside $\mathcal H_0$. The orthogonal summand $\mathcal K$ never appears. Cyclicity rules out such an invisible sector by requiring the field-polynomial vectors to be dense in all of $\mathcal H$.

</details>

### Exercise 2: Field-polynomial inner products

Let $\phi$ be a Hermitian scalar field. Express

$$
\langle \phi(f)\Omega,\phi(g)\Omega\rangle
$$

as a smeared Wightman two-point function.

<details>
<summary><strong>Solution</strong></summary>

Hermiticity gives $\phi(f)^*\supset\phi(\overline f)$. Therefore

$$
\langle \phi(f)\Omega,\phi(g)\Omega\rangle
=
\langle\Omega,\phi(\overline f)\phi(g)\Omega\rangle.
$$

This is the two-point Wightman distribution smeared against $\overline f$ in the first variable and $g$ in the second variable:

$$
W_2(\overline f,g)
=
\int d^dx\,d^dy\,
\overline{f(x)}g(y)W_2(x,y),
$$

where the last formula is kernel notation.

</details>

### Exercise 3: Why finite-particle vectors form a domain

For the free scalar field, explain why the finite-particle subspace is preserved by $\phi(f)=a^*(f_+)+a(\overline{f_+})$.

<details>
<summary><strong>Solution</strong></summary>

A vector in the finite-particle subspace has components only up to some maximum particle number $N$. The creation operator $a^*(f_+)$ raises particle number by one, so it produces components only up to $N+1$. The annihilation operator $a(\overline{f_+})$ lowers particle number by one, so it produces components only up to $N-1$. Their sum therefore maps finite-particle vectors to finite-particle vectors.

</details>

### Exercise 4: Why operator-norm continuity is too strong

Why is it unreasonable to require $f\mapsto\phi(f)$ to be continuous in operator norm in an ordinary Wightman theory?

<details>
<summary><strong>Solution</strong></summary>

Operator norm is defined for bounded operators on all of $\mathcal H$. Smeared fields are usually unbounded, so $\|\phi(f)\|$ is not finite and may not even be meaningful as an operator norm. The Wightman requirement is instead weak distributional continuity: for each $\Psi,\Phi\in\mathcal D$, the scalar map

$$
f\mapsto\langle\Psi,\phi(f)\Phi\rangle
$$

is a distribution.

</details>

### Exercise 5: Why a Lagrangian is not Hilbert-space data

A physicist writes the formal expression

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2-\frac\lambda{4!}\phi^4.
$$

List three Wightman objects that this expression does not by itself construct.

<details>
<summary><strong>Solution</strong></summary>

The formal Lagrangian does not by itself construct:

1. a positive Hilbert space $\mathcal H$;
2. a vacuum vector $\Omega$;
3. a common dense invariant domain $\mathcal D$;
4. operator-valued distributions $\phi(f)$ acting on $\mathcal D$;
5. a unitary Poincaré representation $U$;
6. Wightman functions satisfying positivity, spectrum, covariance, and locality.

The Lagrangian is powerful input for perturbation theory or for a proposed construction, but the Wightman framework asks for the resulting mathematical objects and their properties.

</details>

## References

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- L. Gårding and A. S. Wightman, "Fields as Operator-Valued Distributions in Relativistic Quantum Theory," *Arkiv för Fysik* **28** (1964/65), 129–184.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- K. Fredenhagen and K. Rejzner, "Perturbative Algebraic Quantum Field Theory," in *Mathematical Aspects of Quantum Field Theories*, Springer, 2015. DOI: [10.1007/978-3-319-09949-1_2](https://doi.org/10.1007/978-3-319-09949-1_2), arXiv: [1208.1428](https://arxiv.org/abs/1208.1428).

## Version history

- **2026-06-28:** Initial polished draft for the Wightman and Axiomatic QFT chapter.
