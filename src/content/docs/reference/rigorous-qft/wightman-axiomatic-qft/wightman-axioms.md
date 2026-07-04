---
title: "Wightman Axioms"
description: "States the Wightman axioms for relativistic quantum fields and explains what the axioms do, what they imply, and what they do not construct."
sidebar:
  label: "Wightman Axioms"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Haag; Glimm–Jaffe; Reed–Simon."
topics:
  - Wightman axioms
  - axiomatic QFT
  - operator-valued distributions
  - spectral condition
  - locality
canonicalTopics:
  - wightman-axioms
  - axiomatic-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "The Wightman axioms are a standard Hilbert-space and operator-valued-distribution framework for relativistic QFT, strong enough to imply major structural theorems such as CPT and spin–statistics under their hypotheses."
    - "The Wightman reconstruction theorem gives an equivalence between suitable vacuum correlation functions and Wightman field theories up to unitary equivalence."
  active:
    - "Constructing interacting four-dimensional gauge theories satisfying Wightman-type conditions remains a major open problem; gauge fixing, massless charges, and infrared sectors often require modified or algebraic frameworks."
---

## Summary

The Wightman axioms are a precise Lorentzian framework for relativistic quantum fields. They say, roughly, that a QFT consists of

$$
(\mathcal H,U,\Omega,\mathcal D,\{\phi_i\}),
$$

where $\mathcal H$ is a Hilbert space with positive inner product, $U$ is a unitary representation of the Poincaré group, $\Omega$ is an invariant vacuum, $\mathcal D$ is a common dense invariant domain, and the fields $\phi_i$ are operator-valued tempered distributions satisfying covariance, positive energy, locality, and cyclicity.

For a scalar field, the axioms turn the familiar informal object $\phi(x)$ into the smeared operator

$$
\phi(f):\mathcal D\to\mathcal D,
\qquad
f\in\mathcal S(\mathbb R^d),
$$

and require local commutativity in the form

$$
[\phi(f),\phi(g)]\Psi=0
\quad
\text{if }\operatorname{supp}f
\text{ and }\operatorname{supp}g
\text{ are spacelike separated},
\qquad
\Psi\in\mathcal D.
$$

The axioms are not a path integral and not a construction algorithm. They are a theorem-level definition of a class of relativistic QFTs. Once the axioms hold, many deep consequences follow; proving that a nontrivial interacting model satisfies them is a separate, much harder task.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Map of Wightman data, axioms, functions, and consequences](/figures/rigorous-qft/wightman-axioms-map.svg)

<figcaption>

Wightman QFT starts from Hilbert-space field data. The axioms constrain the vacuum correlation distributions, and reconstruction reverses the direction: suitable Wightman functions recover the Hilbert space and fields.

</figcaption>
</figure>

## Prerequisites

You should know the distributional field viewpoint from [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), the smearing conventions from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and the domain vocabulary from [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/).

A standard first course in QFT is enough for the physical motivation: Hilbert space, particles, Poincaré symmetry, locality, vacuum correlation functions, and the free scalar field.

## Core idea

The Wightman framework asks for a Lorentzian QFT directly in Hilbert space. It does not begin with a classical Lagrangian or a path integral. It begins with the objects that a relativistic quantum theory should have after quantization:

- a positive Hilbert space of states;
- a unitary action of spacetime symmetries;
- a vacuum state;
- local quantum fields as operator-valued distributions;
- positive energy;
- commutativity or anticommutativity at spacelike separation.

The point of the axioms is not to make QFT look formal. The point is to make the physical principles sharp enough that they have mathematical consequences. The spin–statistics theorem, CPT theorem, Reeh–Schlieder theorem, analyticity of correlation functions, and reconstruction from vacuum expectation values all live naturally in this setting.

A useful slogan is:

$$
\text{Wightman QFT}
=
\text{positive-energy local fields on a Hilbert space}.
$$

## Setup and conventions

Work on $d$-dimensional Minkowski space, usually $d=4$, with the mostly-minus metric convention. Let

$$
\mathcal P_+^\uparrow
=
\mathbb R^d\rtimes SO^+(1,d-1)
$$

denote the proper orthochronous Poincaré group, or its relevant spin cover when spinor fields are present. Write a Poincaré transformation as

$$
g=(a,\Lambda),
\qquad
x\mapsto gx=\Lambda x+a.
$$

For simplicity, first think about a neutral scalar field. Fields with spin or internal indices are handled by adding finite-dimensional representation matrices and test functions valued in the appropriate dual bundle.

The test-function space in the usual Wightman formulation is the Schwartz space $\mathcal S(\mathbb R^d)$. This choice makes the vacuum correlation functions tempered distributions and allows Fourier-transform statements such as the spectral condition.

## The axioms

Different books package the axioms with slightly different numbering. The following version separates the pieces that are most useful for reading later pages.

### Axiom 1: Hilbert space and symmetry

There is a complex Hilbert space $\mathcal H$ with positive inner product and a strongly continuous unitary representation

$$
U:\mathcal P_+^\uparrow\to\mathcal U(\mathcal H).
$$

For translations,

$$
U(a,I)=e^{ia^\mu P_\mu},
$$

where the self-adjoint generators $P_\mu$ are the energy-momentum operators, with sign convention tied to the Fourier convention of the volume.

**Status.** This is part of the definition. Positivity of the Hilbert-space inner product is crucial. Gauge-fixed covariant descriptions with ghosts or indefinite metric do not directly satisfy this axiom before passing to a physical Hilbert space or observable algebra.

### Axiom 2: Spectral condition

The joint spectrum of the translation generators lies in the closed future light cone:

$$
\operatorname{Spec}(P)
\subset \overline V_+
=
\{p\in\mathbb R^d:p^0\ge0,
\ p^2\ge0\}.
$$

Physically, this says energy is nonnegative and momenta are compatible with relativistic causality. It also drives the analyticity properties of Wightman functions.

For a massive one-particle state, $p^2=m^2$ and $p^0>0$. For a multiparticle state, the total momentum remains in $\overline V_+$.

### Axiom 3: Vacuum

There is a unit vector $\Omega\in\mathcal H$ such that

$$
U(g)\Omega=\Omega
\qquad
\text{for all }g\in\mathcal P_+^\uparrow.
$$

Often one also assumes that the vacuum is unique up to phase among translation-invariant vectors. Some presentations include uniqueness as an axiom; others derive or add it when cluster properties are needed.

The vacuum is the vector used to define Wightman functions:

$$
W_n(x_1,\ldots,x_n)
=
\langle\Omega,
\phi(x_1)\cdots\phi(x_n)
\Omega\rangle.
$$

This formula is distributional kernel notation. The actual object is the smeared distribution obtained by pairing with a test function of $n$ variables.

### Axiom 4: Fields as operator-valued distributions

There is a dense domain $\mathcal D\subset\mathcal H$ with

$$
\Omega\in\mathcal D,
\qquad
U(g)\mathcal D\subset\mathcal D,
$$

and for each field label $i$ a linear map

$$
\phi_i:\mathcal S(\mathbb R^d)\to\operatorname{End}(\mathcal D),
\qquad
f\mapsto \phi_i(f).
$$

Matrix elements are tempered distributions:

$$
f\longmapsto
\langle\Psi,\phi_i(f)\Phi\rangle
\in\mathcal S'(\mathbb R^d),
\qquad
\Psi,\Phi\in\mathcal D.
$$

The domain is invariant under fields:

$$
\phi_i(f)\mathcal D\subset\mathcal D.
$$

For real scalar fields one also imposes the appropriate Hermiticity condition, first as a domain statement:

$$
\phi(f)^*\supset \phi(\overline f).
$$

For real $f$, this says $\phi(f)$ is symmetric on the common domain. Essential self-adjointness is a further property, not part of the bare notation.

### Axiom 5: Covariance of fields

The fields transform covariantly under the Poincaré representation. For a scalar field,

$$
U(a,\Lambda)\phi(f)U(a,\Lambda)^{-1}
=
\phi(f_{a,\Lambda}),
$$

where

$$
f_{a,\Lambda}(x)=f(\Lambda^{-1}(x-a)).
$$

Equivalently, in point-kernel notation,

$$
U(a,\Lambda)\phi(x)U(a,\Lambda)^{-1}
=\phi(\Lambda x+a).
$$

For fields with spin or tensor indices, one inserts the finite-dimensional Lorentz representation. Schematically,

$$
U(a,\Lambda)\phi_i(x)U(a,\Lambda)^{-1}
=\sum_j S_i{}^j(\Lambda^{-1})\phi_j(\Lambda x+a),
$$

with the precise placement of indices determined by the field type.

### Axiom 6: Local commutativity

If the supports of $f$ and $g$ are spacelike separated, then bosonic fields commute and fermionic fields anticommute on the common domain. For scalar bosonic fields,

$$
[\phi_i(f),\phi_j(g)]\Psi=0,
\qquad
\Psi\in\mathcal D.
$$

For a graded family of fields, the statement is

$$
\phi_i(f)\phi_j(g)
=
(-1)^{|i||j|}\phi_j(g)\phi_i(f)
\quad\text{on }\mathcal D
$$

when the supports are spacelike separated.

This is the rigorous version of microcausality. It is a statement about smeared operators, not about literal point operators.

### Axiom 7: Cyclicity of the vacuum

The vacuum is cyclic for the polynomial field algebra:

$$
\overline{
\operatorname{span}\{
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)\Omega:
 n\ge0
\}
}
=\mathcal H.
$$

Cyclicity says that field polynomials applied to the vacuum generate a dense set of states. This makes the vacuum correlation functions complete data for the theory in the reconstruction theorem.

Cyclicity is not the same as irreducibility, though related formulations may use irreducibility or add assumptions to rule out superselection multiplicities.

## Wightman functions

Given the field data, define vacuum expectation values by

$$
W_{i_1\cdots i_n}(f_1,\ldots,f_n)
=
\langle\Omega,
\phi_{i_1}(f_1)\cdots\phi_{i_n}(f_n)
\Omega\rangle.
$$

Equivalently, one writes distributional kernels

$$
W_{i_1\cdots i_n}(x_1,\ldots,x_n)
=
\langle\Omega,
\phi_{i_1}(x_1)\cdots\phi_{i_n}(x_n)
\Omega\rangle.
$$

These are tempered distributions on $(\mathbb R^d)^n$. Translation invariance means they depend only on differences, for example

$$
W_n(x_1+a,\ldots,x_n+a)=W_n(x_1,\ldots,x_n).
$$

The spectral condition becomes a support property of Fourier transforms in difference variables. For scalar fields, write

$$
\xi_k=x_k-x_{k+1},
\qquad
k=1,\ldots,n-1.
$$

Then the Fourier transform of the reduced $n$-point distribution is supported where each relevant partial momentum lies in $\overline V_+$. This support condition is the analytic engine behind many Wightman theorems.

## Positivity in correlation-function language

Hilbert-space positivity becomes a positivity condition on Wightman functions. If

$$
\Psi
=
\sum_\alpha c_\alpha
\phi_{i_{\alpha,1}}(f_{\alpha,1})
\cdots
\phi_{i_{\alpha,n_\alpha}}(f_{\alpha,n_\alpha})
\Omega
$$

is a finite field-polynomial vector, then

$$
\|\Psi\|^2\ge0.
$$

Expanding this norm expresses positivity as an infinite family of inequalities among smeared Wightman functions. This condition is the Lorentzian analog of reflection positivity in the Osterwalder–Schrader Euclidean framework.

Positivity is easy to forget because it is not a compact local formula. It is also indispensable: without it, reconstruction may produce an indefinite inner product rather than a physical Hilbert space.

## Reconstruction theorem preview

The Wightman reconstruction theorem reverses the direction of construction.

**Theorem-level statement.** Suppose a sequence of distributions $\{W_n\}_{n\ge0}$ satisfies the Wightman-function versions of temperedness, covariance, spectral support, locality, Hermiticity, normalization, and positivity. Then one can reconstruct a Hilbert space $\mathcal H$, a vacuum $\Omega$, a unitary Poincaré representation $U$, and operator-valued distributions $\phi_i$ realizing those $W_n$ as vacuum expectation values. The reconstructed theory is unique up to unitary equivalence, subject to the standard formulation choices.

The proof is a field-theoretic version of a GNS construction. One starts from a vector space of test-function sequences, defines a sesquilinear form using the $W_n$, quotients by null vectors, completes to get $\mathcal H$, and represents fields by left multiplication.

This is a reconstruction theorem, not an existence theorem for arbitrary Lagrangians. The hard part in concrete interacting QFT is proving that the candidate $W_n$ exist and satisfy all required conditions.

## Example: free scalar field

The free massive scalar field satisfies the Wightman axioms. Its one-particle Hilbert space is

$$
\mathcal H_1
=L^2\left(
\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}2E_{\mathbf p}}
\right),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

and the full Hilbert space is the symmetric Fock space

$$
\mathcal H=\mathcal F_s(\mathcal H_1).
$$

The vacuum is the zero-particle vector. The field has the schematic form

$$
\phi(f)=a^*(f_+)+a(\overline{f_+}),
$$

where $f_+$ is the restriction of the Fourier transform of $f$ to the positive-energy mass shell. The finite-particle domain is dense and invariant.

The two-point function is

$$
W_2(x-y)
=
\int \frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}2E_{\mathbf p}}
\,e^{-ip\cdot(x-y)},
\qquad
p^0=E_{\mathbf p}.
$$

Its Fourier transform is supported on the positive-energy mass shell, so the spectral condition holds. The commutator is the Pauli–Jordan distribution,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and $\Delta$ is supported in the causal cone, so smeared fields commute at spacelike separation.

## Example: generalized free fields

Generalized free fields are useful cautionary examples. They are determined by a positive spectral measure $\rho$ through a two-point function of Källén–Lehmann type,

$$
W_2(x)
=
\int_0^\infty d\rho(\mu^2)\,\Delta_+^{(\mu)}(x),
$$

and higher $n$-point functions are defined by Wick's rule. Under suitable positivity and growth conditions on $\rho$, they satisfy Wightman axioms.

Yet a generalized free field need not come from an ordinary local Lagrangian with a standard stress tensor or particle interpretation. This shows that the Wightman axioms are structural axioms, not a complete classification of physically preferred dynamics.

## What follows from the axioms

The axioms are strong enough to imply deep results.

| Result | Rough content | Status |
|---|---|---|
| Wightman reconstruction | Correlation functions satisfying the Wightman conditions reconstruct fields on Hilbert space. | Theorem. |
| Analyticity in tube domains | Spectrum condition makes Wightman functions boundary values of holomorphic functions. | Theorem. |
| Reeh–Schlieder theorem | Local fields applied to the vacuum in any open region generate a dense set of states. | Theorem under standard assumptions. |
| Spin–statistics theorem | Integer-spin fields commute and half-integer-spin fields anticommute at spacelike separation. | Theorem under Wightman-type hypotheses. |
| CPT theorem | Local Lorentz-covariant QFT has a CPT symmetry with the expected action. | Theorem under Wightman-type hypotheses. |

The point is not that the axioms make QFT trivial. The point is that locality, positivity, covariance, and spectrum are mutually powerful.

## What the axioms do not say

The Wightman axioms do not provide a general method for constructing interacting QFTs. They tell you what must be proved after a construction is proposed.

They do not say that every useful QFT has pointlike fundamental fields. Algebraic QFT may take local algebras as primary. Topological QFT may not fit the same Lorentzian point-field template. Gauge theories may be better formulated through gauge-invariant observables, BRST/BV cohomology, or local nets.

They do not make perturbation theory convergent. Perturbative QFT is usually a formal power series. A formal series can satisfy Ward identities or locality order by order without defining nonperturbative Wightman distributions.

They do not automatically handle all infrared phenomena. In theories with massless particles, charged sectors may fail to have ordinary Wigner particle states, and fields carrying charge may have nonlocal features. Algebraic and scattering-theoretic refinements are often needed.

They do not replace Euclidean methods. Osterwalder–Schrader axioms give a Euclidean route to reconstructing Lorentzian Wightman theories, with reflection positivity replacing Hilbert-space positivity.

## Common variants

Some presentations list the axioms in terms of fields; others list them in terms of vacuum expectation values. These are equivalent after reconstruction, but they emphasize different tasks.

Some presentations require a unique vacuum. Others include cluster decomposition as an additional condition. Cluster properties are important for scattering and phase structure, but they are not always part of the minimal first statement of the Wightman axioms.

Some presentations include irreducibility of the field algebra. In the presence of superselection sectors, irreducibility of a chosen representation can be too restrictive or must be interpreted carefully.

Some presentations formulate locality as local commutativity for all fields. Others use a graded local commutativity condition from the start. The spin–statistics theorem then tells us when the grading matches Lorentz spin under the standard hypotheses.

## Common pitfalls

**Treating $\phi(x)$ as an operator.** The Wightman field is $f\mapsto\phi(f)$. The point notation is a distributional kernel.

**Ignoring the common domain.** Products of unbounded fields are defined first on $\mathcal D$. Without a domain, formulas such as $\phi(f)\phi(g)\Omega$ are incomplete.

**Confusing positivity with positive energy.** Hilbert-space positivity says inner products have nonnegative norm. The spectral condition says energy-momentum lies in $\overline V_+$. Both are needed.

**Thinking the axioms are merely philosophy.** They imply hard theorems. Conversely, satisfying them is a substantial mathematical claim.

**Assuming gauge-fixed fields satisfy Wightman axioms.** Gauge-fixed covariant formulations may use ghosts or indefinite metric. The Wightman Hilbert-space axioms are expected for physical gauge-invariant content after construction, not automatically for every gauge-dependent field symbol.

**Forgetting existence.** Writing down a Lagrangian does not prove that the corresponding Wightman theory exists.

## Relations to other pages

- [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/) explains the domain clauses used in the field axioms.
- [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) explains the operator-valued-distribution clause.
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) gives modern tools for controlling distributional singularities beyond the original Wightman setup.

Later pages in this chapter will treat Hilbert space and fields, Poincaré covariance, the spectral condition, locality, Wightman functions, reconstruction, spin–statistics, and CPT separately.

## Research status

The Wightman axioms are an established rigorous framework. The free scalar, free spinor, and many lower-dimensional constructive models fit naturally into Wightman-style formulations. The axioms also remain a benchmark for what it means to have a nonperturbative Lorentzian QFT with pointlike fields.

The frontier lies in construction and comparison. Important interacting models are known in low dimensions, while four-dimensional interacting gauge theories remain much harder. The Yang–Mills existence and mass gap problem can be viewed as asking for a nonperturbative construction with properties compatible with rigorous QFT expectations.

Modern rigorous QFT often uses frameworks adjacent to Wightman theory: Osterwalder–Schrader Euclidean QFT, Haag–Kastler algebraic QFT, locally covariant QFT, constructive QFT, perturbative algebraic QFT, and factorization algebras. These frameworks do not replace the Wightman axioms; they answer different construction and organization questions.

## Exercises

### Exercise 1: Smeared covariance for a scalar field

Assume the point-kernel covariance formula

$$
U(a,\Lambda)\phi(x)U(a,\Lambda)^{-1}
=\phi(\Lambda x+a).
$$

Show that

$$
U(a,\Lambda)\phi(f)U(a,\Lambda)^{-1}
=\phi(f_{a,\Lambda}),
\qquad
f_{a,\Lambda}(y)=f(\Lambda^{-1}(y-a)).
$$

<details>
<summary><strong>Solution</strong></summary>

Start from the smeared field in kernel notation:

$$
\phi(f)=\int d^dx\,f(x)\phi(x).
$$

Then

$$
U\phi(f)U^{-1}
=\int d^dx\,f(x)\phi(\Lambda x+a).
$$

Set $y=\Lambda x+a$. Proper Lorentz transformations have unit absolute determinant, so $d^dy=d^dx$. Thus

$$
U\phi(f)U^{-1}
=\int d^dy\,f(\Lambda^{-1}(y-a))\phi(y)
=\phi(f_{a,\Lambda}).
$$

</details>

### Exercise 2: Spectral support of the free two-point function

The free scalar two-point function has Fourier-space support on

$$
p^2=m^2,
\qquad
p^0\ge0.
$$

Explain why this is compatible with the Wightman spectral condition.

<details>
<summary><strong>Solution</strong></summary>

The Wightman spectral condition requires energy-momentum to lie in the closed future cone

$$
\overline V_+=\{p:p^0\ge0,
\ p^2\ge0\}.
$$

For the free massive scalar, the two-point spectral measure is supported on the positive-energy mass shell $p^2=m^2$ with $m^2\ge0$ and $p^0\ge0$. This mass shell is a subset of $\overline V_+$, so the condition holds.

</details>

### Exercise 3: Locality from support of the commutator

Suppose

$$
[\phi(x),\phi(y)]=i\Delta(x-y)
$$

as distributions and $\operatorname{supp}\Delta\subset\overline V_+\cup\overline V_-$. Show that $[\phi(f),\phi(g)]=0$ if the supports of $f$ and $g$ are spacelike separated.

<details>
<summary><strong>Solution</strong></summary>

The smeared commutator is the distributional pairing

$$
[\phi(f),\phi(g)]
=i\int d^dx\,d^dy\,f(x)g(y)\Delta(x-y).
$$

If the supports of $f$ and $g$ are spacelike separated, then $x-y$ is spacelike on the support of $f(x)g(y)$. Since $\Delta$ is supported in the causal cone, the test function $f(x)g(y)$ does not meet the support of $\Delta(x-y)$. The pairing is therefore zero.

</details>

### Exercise 4: Positivity from Hilbert space

Let

$$
\Psi=\sum_\alpha c_\alpha
\phi(f_{\alpha,1})\cdots\phi(f_{\alpha,n_\alpha})\Omega.
$$

Explain why $\|\Psi\|^2\ge0$ gives a nontrivial condition on Wightman functions.

<details>
<summary><strong>Solution</strong></summary>

Expanding the norm gives

$$
\|\Psi\|^2
=
\sum_{\alpha,\beta}
\overline{c_\alpha}c_\beta
\langle
\phi(f_{\alpha,n_\alpha})^*\cdots\phi(f_{\alpha,1})^*\Omega,
\phi(f_{\beta,1})\cdots\phi(f_{\beta,n_\beta})\Omega
\rangle,
$$

with the precise order depending on the adjoint convention. Each inner product is a smeared Wightman function of order $n_\alpha+n_\beta$. Since Hilbert-space norms are nonnegative, every finite quadratic combination of Wightman functions obtained this way must be nonnegative. This is the Wightman positivity condition.

</details>

### Exercise 5: Why reconstruction needs cyclicity

Why is vacuum cyclicity natural if one wants the Wightman functions to determine the theory?

<details>
<summary><strong>Solution</strong></summary>

Wightman functions are vacuum expectation values of products of fields. They determine inner products between vectors of the form

$$
\phi(f_1)\cdots\phi(f_n)\Omega.
$$

If the span of such vectors is dense, then these inner products determine the Hilbert space after completion, up to unitary equivalence. If the span were not dense, there could be an orthogonal sector invisible to all vacuum correlation functions, so the Wightman functions would not determine the full representation.

</details>

## References

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- L. Gårding and A. S. Wightman, "Fields as Operator-Valued Distributions in Relativistic Quantum Theory," *Arkiv för Fysik* **28** (1964/65), 129–184.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- A. S. Wightman, "How It Was Learned that Quantized Fields Are Operator-Valued Distributions," *Fortschritte der Physik* **44** (1996), 143–178. DOI: [10.1002/prop.2190440204](https://doi.org/10.1002/prop.2190440204).
- R. Haag and D. Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. DOI: [10.1063/1.1704187](https://doi.org/10.1063/1.1704187).

## Version history

- **2026-06-28:** Initial polished draft for the Wightman and Axiomatic QFT chapter.
