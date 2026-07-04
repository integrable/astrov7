---
title: "Wightman Reconstruction Theorem"
description: "Explains how Wightman functions satisfying positivity, covariance, spectral support, and locality reconstruct a Hilbert-space quantum field theory."
sidebar:
  label: "Reconstruction Theorem"
  order: 8
level: Advanced
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Borchers algebra; Haag."
topics:
  - Wightman reconstruction theorem
  - Wightman functions
  - Hilbert space reconstruction
  - positivity
  - Borchers algebra
canonicalTopics:
  - wightman-reconstruction
  - axiomatic-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "The Wightman reconstruction theorem is a standard theorem showing that suitable vacuum correlation distributions determine a cyclic Hilbert-space field theory up to unitary equivalence."
  active:
    - "The hard part in applications is not the abstract reconstruction step but producing nontrivial Wightman functions satisfying positivity, spectral support, locality, and suitable growth properties."
---

## Summary

The Wightman reconstruction theorem says that a quantum field theory can be recovered from its vacuum correlation functions, provided those functions satisfy the right analytic, covariance, positivity, and locality conditions. In its simplest scalar form, the input is a sequence of tempered distributions

$$
W_0=1,
\qquad
W_n\in \mathcal S'((\mathbb M^d)^n),
\qquad n\geq 1,
$$

and the output is Wightman field data

$$
(\mathcal H,\Omega,U,\mathcal D,\phi),
$$

such that

$$
W_n(f_1\otimes\cdots\otimes f_n)
=
\langle \Omega,
\phi(f_1)\cdots\phi(f_n)\Omega\rangle.
$$

The theorem is not a magic construction of interacting models from a Lagrangian. It is a reconstruction theorem: once one has a family of distributions with the Wightman-function properties, the Hilbert space, vacuum, unitary Poincaré representation, and field operators are forced on the cyclic sector.

The key move is simple and profound. Use the proposed correlation functions to define an inner product on formal field polynomials applied to the vacuum. Positivity makes this a semidefinite inner product; quotienting by null vectors and completing gives the Hilbert space.

<figure class="doc-figure" style="--figure-width: 44rem;">

![The Wightman reconstruction theorem as a quotient and completion procedure](/figures/rigorous-qft/wightman-reconstruction-quotient.svg)

<figcaption>

Reconstruction starts from Wightman distributions $W_n$, builds a positive semidefinite form on the test-function tensor algebra, quotients null vectors, completes to a Hilbert space, and represents fields by left multiplication. The theorem turns correlation-function data back into operator data.

</figcaption>
</figure>

## Prerequisites

You should know [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/), especially the distinction between Wightman functions and time-ordered correlators. You should also know [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/), [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/), and [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/).

For the test-function language, use [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/). For common-domain issues, use [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/).

## Logical status

| Item | Status |
|---|---|
| Type | Theorem. |
| Framework | Wightman axiomatic QFT on Minkowski spacetime. |
| Input | A full sequence of vacuum correlation distributions satisfying Wightman positivity, covariance, spectral support, Hermiticity, and locality. |
| Output | A cyclic Hilbert-space field theory whose vacuum expectation values are the given distributions. |
| Uniqueness | Up to unitary equivalence on the vacuum-generated sector. |
| Main limitation | The theorem reconstructs from valid data; it does not construct the data for an interacting Lagrangian. |

## Core idea

In ordinary quantum mechanics, knowing all matrix elements of an operator in a dense set determines the operator on that dense set. In Wightman reconstruction, the dense set is not given in advance. It is manufactured from formal expressions of the form

$$
\phi(f_1)\cdots\phi(f_n)\Omega.
$$

The correlation functions tell us what their inner products must be. For example, if the field is Hermitian and scalar, then formally

$$
\begin{aligned}
&\langle
\phi(f_1)\cdots\phi(f_m)\Omega,
\phi(g_1)\cdots\phi(g_n)\Omega
\rangle \\
&\qquad =
W_{m+n}(\overline f_m\otimes\cdots\otimes\overline f_1
\otimes g_1\otimes\cdots\otimes g_n),
\end{aligned}
$$

with the order of the first block reversed because it comes from the bra. Wightman positivity is precisely the assertion that all finite linear combinations of such formal vectors have nonnegative norm squared.

Once this inner product is positive semidefinite, the standard Hilbert-space recipe applies:

$$
\text{formal vectors}
\quad \longrightarrow \quad
\frac{\text{formal vectors}}{\text{null vectors}}
\quad \longrightarrow \quad
\text{Hilbert completion}.
$$

The theorem is powerful because it says that the rest of the Wightman structure also descends: translations and Lorentz transformations become unitary operators, the vacuum is the class of the empty product, and fields act by adding one more test function on the left.

## Setup and conventions

We use $d$-dimensional Minkowski spacetime $\mathbb M^d$ with the conventions fixed in [Conventions and Logical Status](/rigorous-qft/conventions/). To keep the notation readable, this page first states the scalar Hermitian case. Multiple fields, charged fields, spinor indices, and internal labels are handled by replacing scalar test functions with test functions valued in the appropriate finite-dimensional field space and by inserting the correct adjoint operation.

The input distributions are written as

$$
W_n(x_1,\ldots,x_n)
=
\langle \Omega,
\phi(x_1)\cdots\phi(x_n)\Omega\rangle,
$$

but this is kernel notation. The actual input is the smeared functional

$$
W_n(f_n)
\quad\text{for}\quad
f_n\in\mathcal S((\mathbb M^d)^n).
$$

For product test functions,

$$
h=f_1\otimes\cdots\otimes f_n,
$$

this notation agrees with the usual $n$-fold smearing $W_n(h)$. General test functions in $\mathcal S((\mathbb M^d)^n)$ are needed for the functional-analytic construction.

## Statement of the theorem

A standard scalar version of the theorem can be stated as follows.

:::note[Wightman reconstruction theorem]
Let $\{W_n\}_{n\geq0}$ be a sequence of tempered distributions with $W_0=1$. Suppose the sequence satisfies the Wightman-function conditions:

1. temperedness and normalization;
2. Poincaré covariance;
3. the spectral condition in momentum space;
4. Hermiticity;
5. Wightman positivity;
6. local commutativity at spacelike separation.

Then there exist a Hilbert space $\mathcal H$, a vacuum vector $\Omega$, a strongly continuous unitary representation $U$ of the proper orthochronous Poincaré group, a dense invariant domain $\mathcal D\subset\mathcal H$, and an operator-valued tempered distribution $\phi$ on $\mathcal D$ whose Wightman functions are the given $W_n$.

The reconstructed theory is unique up to unitary equivalence on the cyclic sector generated from $\Omega$.
:::

Some formulations include a cluster condition, vacuum uniqueness, or irreducibility among the hypotheses. These strengthen the conclusion. The algebraic reconstruction of the cyclic Hilbert space and fields uses positivity, covariance, spectral support, and locality; uniqueness of the vacuum and cluster behavior require additional assumptions or separate arguments.

## The test-function algebra

Let

$$
\mathfrak S
=
\bigoplus_{n=0}^{\infty}\mathcal S((\mathbb M^d)^n)
$$

be the vector space of finite sequences

$$
F=(f_0,f_1,f_2,\ldots),
$$

where $f_0\in\mathbb C$ and only finitely many components are nonzero. This is often called the Borchers test-function algebra or tensor algebra of test functions.

Multiplication is concatenation. If $F=(f_n)$ and $G=(g_n)$, define

$$
(FG)_n(x_1,\ldots,x_n)
=
\sum_{k=0}^{n}
 f_k(x_1,\ldots,x_k)
 g_{n-k}(x_{k+1},\ldots,x_n).
$$

The empty argument case means multiplication by the scalar components $f_0$ or $g_0$. The involution is reversal plus complex conjugation:

$$
(F^*)_n(x_1,\ldots,x_n)
=
\overline{f_n(x_n,\ldots,x_1)}.
$$

This algebra is the rigorous version of finite field polynomials. The component $f_n$ represents a smeared $n$-fold monomial, and multiplication corresponds to writing one polynomial after another.

## Positivity and the Hilbert space

The Wightman functions define a linear functional on $\mathfrak S$:

$$
\mathcal W(F)
=
\sum_{n=0}^{\infty} W_n(f_n).
$$

Because $F$ has only finitely many nonzero components, this sum is finite.

Now define a sesquilinear form by

$$
\langle F,G\rangle_0
=
\mathcal W(F^*G).
$$

Wightman positivity says

$$
\langle F,F\rangle_0\geq0
\qquad\text{for all }F\in\mathfrak S.
$$

This is the exact place where Hilbert-space positivity enters. Without it, the construction may produce an indefinite inner-product space, not a physical Hilbert space.

The form may have null vectors. Define

$$
\mathcal N
=
\{F\in\mathfrak S:\langle F,F\rangle_0=0\}.
$$

Cauchy–Schwarz for positive semidefinite forms implies that $\mathcal N$ is orthogonal to all of $\mathfrak S$, so the quotient

$$
\mathcal D_0
=
\mathfrak S/\mathcal N
$$

has a genuine inner product. The reconstructed Hilbert space is the completion:

$$
\mathcal H
=
\overline{\mathcal D_0}^{\|\cdot\|}.
$$

The vacuum is the class of the empty product:

$$
\Omega=[(1,0,0,\ldots)].
$$

The dense domain $\mathcal D$ is usually taken to be the image of $\mathfrak S$ in this completion:

$$
\mathcal D=\mathcal D_0\subset\mathcal H.
$$

This domain is dense by construction.

## Reconstructed fields

For a test function $h\in\mathcal S(\mathbb M^d)$, let

$$
A(h)=(0,h,0,0,\ldots)\in\mathfrak S.
$$

Define the smeared field on the dense domain by left multiplication:

$$
\phi(h)[F]=[A(h)F].
$$

This is the operator-theoretic version of saying that a field creates one more field insertion. Since multiplication in $\mathfrak S$ preserves finite sequences, $\phi(h)$ maps $\mathcal D$ into $\mathcal D$.

The vacuum expectation values are now automatic:

$$
\begin{aligned}
\langle\Omega,
\phi(f_1)\cdots\phi(f_n)\Omega\rangle
&=
\langle (1,0,\ldots),
A(f_1)\cdots A(f_n)\rangle_0 \\
&=
W_n(f_1\otimes\cdots\otimes f_n).
\end{aligned}
$$

Thus the input distributions are exactly recovered.

For fields with several components, $A(h)$ is replaced by a generator carrying a component label, and the input includes distributions

$$
W_{i_1\ldots i_n}(x_1,\ldots,x_n).
$$

The construction is the same, but the involution must encode which field is the adjoint of which component.

## Reconstructed symmetries

Poincaré covariance of $W_n$ defines a representation on the test-function algebra. For a scalar field, set

$$
((a,\Lambda)F)_n(x_1,\ldots,x_n)
=
f_n(\Lambda^{-1}(x_1-a),\ldots,\Lambda^{-1}(x_n-a)).
$$

Covariance of the Wightman functions implies

$$
\langle (a,\Lambda)F,(a,\Lambda)G\rangle_0
=
\langle F,G\rangle_0.
$$

Therefore this action preserves the null space and descends to an isometry of $\mathcal D_0$. It extends by completion to a unitary operator on $\mathcal H$:

$$
U(a,\Lambda):\mathcal H\to\mathcal H.
$$

The vacuum is invariant because the empty product is invariant:

$$
U(a,\Lambda)\Omega=\Omega.
$$

For spinor, vector, or tensor fields, the transformation law includes the finite-dimensional field representation $D(\Lambda)$, but the logic is unchanged.

The spectral condition on the input Wightman functions implies the positive-energy spectral condition for the reconstructed translation representation. In other words, the support condition imposed on the Fourier transforms of $W_n$ is exactly what becomes

$$
\operatorname{Spec}(P)\subset\overline V_+.
$$

## Reconstructed locality

Locality is also inherited from the input distributions. For a scalar field, the Wightman-function locality condition says that if adjacent test functions have spacelike separated supports, then

$$
W_n(\ldots\otimes f\otimes g\otimes\ldots)
=
W_n(\ldots\otimes g\otimes f\otimes\ldots).
$$

This identity implies

$$
[\phi(f),\phi(g)]\Psi=0
$$

for every $\Psi\in\mathcal D$, whenever $\operatorname{supp}f$ and $\operatorname{supp}g$ are spacelike separated.

For fermionic fields, the sign is the graded one. If the field parity is $p_i\in\{0,1\}$, the local relation is

$$
\phi_i(f)\phi_j(g)
-
(-1)^{p_i p_j}\phi_j(g)\phi_i(f)
=0
$$

on $\mathcal D$ for spacelike separated supports.

This is why reconstruction requires the locality property at the correlation-function level. It is not an optional aesthetic condition; it is exactly what becomes operator locality.

## What the theorem really proves

The theorem proves that the following two descriptions are equivalent, under the stated hypotheses:

| Correlation-function language | Hilbert-space field language |
|---|---|
| Tempered distributions $W_n$. | Operator-valued tempered distribution $\phi$. |
| Poincaré covariance of $W_n$. | Unitary Poincaré representation $U$. |
| Spectral support of Fourier transforms. | Positive joint spectrum of translations. |
| Wightman positivity. | Positive Hilbert-space inner product. |
| Local symmetry of distributions. | Local commutativity or graded locality. |
| Normalization $W_0=1$. | Unit vacuum vector $\Omega$. |

This equivalence is conceptually important. It means that a theory can be specified by its vacuum correlators, not only by a Lagrangian or canonical commutation relations. But it is also demanding: positivity and spectral support are highly nontrivial constraints.

## What the theorem does not prove

The theorem does **not** prove that a given formal path integral exists. It starts only after one has honest distributions satisfying the Wightman-function axioms.

It does **not** say that the reconstructed fields are self-adjoint operators in the strong spectral-theorem sense. It gives operator-valued distributions on a common dense invariant domain. Essential self-adjointness and affiliated local observables are additional questions.

It does **not** solve gauge theory. Gauge-fixed fields may live in indefinite metric spaces, and physical observables may be better organized algebraically or cohomologically. A positive Wightman reconstruction applies directly only after the physical positive Hilbert-space data have been identified.

It does **not** make locality automatic. The input distributions must already satisfy the appropriate local commutativity identities.

It does **not** guarantee a unique vacuum unless the input includes a suitable uniqueness or clustering condition.

## Common pitfalls

**Confusing reconstruction with construction.** Reconstruction turns a valid sequence of correlation distributions into fields. Constructive QFT tries to produce such distributions in the first place.

**Treating positivity as pointwise positivity.** Wightman positivity is not the claim that $W_n(x_1,\ldots,x_n)$ is nonnegative. It is an infinite family of quadratic inequalities for smeared field polynomials.

**Forgetting the null quotient.** The raw formal vector space usually has zero-norm combinations. Quotienting by them is not a technical nuisance; it is how the Hilbert space is made honest.

**Using Feynman correlators as input.** Reconstruction uses Wightman functions, not time-ordered Green functions. Euclidean Schwinger functions require Osterwalder–Schrader reconstruction instead.

**Ignoring domains.** The reconstructed field $\phi(f)$ is defined on a dense invariant domain. It is not automatically a bounded operator on the whole Hilbert space.

**Assuming all physically useful QFTs are point-field Wightman theories.** Many modern settings use algebras of observables, defects, extended operators, gauge-invariant line operators, or functorial structures rather than ordinary point fields as fundamental data.

## Relations to other pages

[Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) gives the correlation-function properties that become the hypotheses of reconstruction. [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) explains why the reconstructed cyclic sector is the relevant Hilbert space. [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) explains the operator locality condition that comes out of distributional local commutativity.

The next page, [Spin–Statistics Theorem](/rigorous-qft/wightman-axiomatic-qft/spin-statistics-theorem/), is an example of what can be proved after the Wightman data have been assembled. Osterwalder–Schrader reconstruction will later explain the Euclidean analogue: how reflection-positive Schwinger functions reconstruct Lorentzian Wightman data.

## Research status

**Established theorem.** Wightman reconstruction is a standard result of axiomatic QFT. It is one of the main reasons Wightman functions are treated as complete data rather than merely as convenient observables.

**Constructive challenge.** The difficult part is to find nontrivial examples satisfying all hypotheses. Low-dimensional constructive models provide successes; four-dimensional interacting gauge theories remain much harder.

**Framework dependence.** In algebraic QFT, local observable algebras may be more intrinsic than point fields. In gauge theory, one often has to separate auxiliary gauge-fixed fields from physical positive-metric observables. In conformal and topological settings, other reconstruction theorems can play analogous but different roles.

## Exercises

### Exercise 1: The vacuum vector

Let $\Omega=[(1,0,0,\ldots)]$ in the reconstructed Hilbert space. Show that

$$
\|\Omega\|^2=1.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\|\Omega\|^2
=
\langle (1,0,\ldots),(1,0,\ldots)\rangle_0
=
\mathcal W((1,0,\ldots)^*(1,0,\ldots)).
$$

The product is again $(1,0,\ldots)$, so this equals $W_0$. The normalization hypothesis is $W_0=1$.

</details>

### Exercise 2: Why the order reverses

For a Hermitian scalar field, explain why the formal inner product of

$$
\phi(f_1)\cdots\phi(f_m)\Omega
\quad\text{and}\quad
\phi(g_1)\cdots\phi(g_n)\Omega
$$

involves the reversed sequence $\overline f_m,\ldots,\overline f_1$ in the first block.

<details><summary><strong>Solution</strong></summary>

The first vector appears as a bra. Since $\phi(f)^*=\phi(\overline f)$ for a Hermitian scalar field,

$$
(\phi(f_1)\cdots\phi(f_m)\Omega)^*
=
\langle\Omega,
\phi(\overline f_m)\cdots\phi(\overline f_1).
$$

Taking the adjoint reverses the order of operators. Therefore the Wightman function appearing in the inner product has the first block in reverse order.

</details>

### Exercise 3: Why quotient by null vectors?

Suppose $F\in\mathfrak S$ satisfies $\langle F,F\rangle_0=0$. Why must $F$ be identified with zero before completing to a Hilbert space?

<details><summary><strong>Solution</strong></summary>

A Hilbert-space norm must be positive definite: $\|v\|=0$ implies $v=0$. Wightman positivity gives only a positive semidefinite form on the formal algebra. If $F$ has zero norm but is not quotiented out, the form is not a Hilbert-space inner product.

Cauchy–Schwarz for positive semidefinite forms gives

$$
|\langle F,G\rangle_0|^2
\leq
\langle F,F\rangle_0\langle G,G\rangle_0=0,
$$

so every null vector is orthogonal to every vector. Quotienting by all null vectors therefore preserves all inner products among equivalence classes and produces a positive definite inner product.

</details>

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.

### Deeper references

- H. J. Borchers, "On Structure of the Algebra of Field Operators," *Il Nuovo Cimento* **24** (1962), 214–236. DOI: [10.1007/BF02745645](https://doi.org/10.1007/BF02745645).
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- N. N. Bogoliubov, A. A. Logunov, A. I. Oksak, and I. T. Todorov, *General Principles of Quantum Field Theory*, Kluwer, 1990.

## Version history

- **2026-06-28:** Initial polished draft.
