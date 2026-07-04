---
title: "Osterwalder–Schrader Reconstruction Theorem"
description: "States and explains the Osterwalder–Schrader reconstruction theorem, which builds a Lorentzian Wightman QFT from suitable Euclidean Schwinger functions."
sidebar:
  label: "OS Reconstruction"
  order: 6
level: Advanced
status: "Polished draft"
source: "Osterwalder–Schrader I/II; Nelson; Streater–Wightman; Glimm–Jaffe; Simon."
topics:
  - Osterwalder–Schrader reconstruction
  - Schwinger functions
  - Wightman reconstruction
  - reflection positivity
  - Hilbert space reconstruction
canonicalTopics:
  - os-reconstruction-theorem
  - osterwalder-schrader-qft
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "Under the standard Osterwalder–Schrader hypotheses, Euclidean Schwinger functions reconstruct a Lorentzian Wightman quantum field theory."
  active:
    - "The theorem is a reconstruction result, not an existence theorem for a chosen interacting Lagrangian or gauge theory."
---

## Summary

The Osterwalder–Schrader reconstruction theorem is the rigorous bridge from Euclidean correlation functions to Lorentzian QFT. In scalar form, it says:

**Theorem.** Suppose a sequence of Schwinger distributions

$$
\underline S=(S_0,S_1,S_2,\ldots),
\qquad
S_0=1,
$$

satisfies the OS regularity, Euclidean covariance, symmetry, reflection positivity, and clustering hypotheses. Then one can reconstruct a Wightman QFT: a Hilbert space $\mathcal H$, vacuum $\Omega$, positive-energy Poincaré representation, and operator-valued distributions whose vacuum correlation functions analytically continue to the given Schwinger functions.

The theorem is not a proof that a formal path integral exists. It is a theorem of the form

$$
\text{valid Euclidean data}
\Longrightarrow
\text{Lorentzian QFT}.
$$

The hard constructive problem is often the premise: prove that the continuum Schwinger functions exist and satisfy the OS axioms.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Osterwalder–Schrader reconstruction pipeline](/figures/rigorous-qft/os-reconstruction-pipeline.svg)

<figcaption>

OS reconstruction starts with Schwinger distributions, uses reflection positivity to form a Hilbert space, obtains $e^{-\tau H}$ from positive Euclidean time translations, and reconstructs Lorentzian Wightman data by analytic continuation.

</figcaption>
</figure>

## Prerequisites

Read [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/), [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/), and [Euclidean Invariance](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-invariance/) first. The Lorentzian target is explained in [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) and [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/).

This page states the scalar bosonic flat-space theorem. Fermions, gauge theories, curved backgrounds, and finite-temperature theories require modified reconstruction statements.

## Logical status

| Item | Status |
|---|---|
| Page type | Theorem and construction page. |
| Framework | Scalar Osterwalder–Schrader Euclidean QFT on flat $\mathbb R^d$. |
| Input | A sequence of Schwinger distributions satisfying the OS hypotheses. |
| Output | A Wightman QFT with Hilbert space, vacuum, fields, positive energy, locality, and Poincaré covariance. |
| Main caveat | The theorem reconstructs from valid Euclidean data; it does not prove that a formal Lagrangian path integral produces such data. |

## Core idea

A Lorentzian QFT has a Hilbert space from the beginning. A Euclidean QFT may instead be given as correlation data. Reconstruction asks whether the Hilbert space was hidden in that data all along.

The OS answer is yes, provided the Euclidean data satisfy the right positivity condition. One cuts Euclidean space at $\tau=0$. Field polynomials supported in positive Euclidean time are treated as candidate kets. Their reflected conjugates are treated as candidate bras. The Schwinger functions then define a candidate inner product:

$$
\langle F,G\rangle_{\mathrm{OS}}
=
\langle\Theta F\,G\rangle_E.
$$

Reflection positivity says this form is positive semidefinite. Quotienting by null vectors and completing gives the Hilbert space.

The rest of the theorem shows that Euclidean covariance, symmetry, and regularity reconstruct the remaining Lorentzian structure: positive Hamiltonian, spatial momentum, Lorentz covariance, fields, locality, and vacuum correlation functions.

## Setup and conventions

Use Euclidean coordinates

$$
x=(\tau,\mathbf x)\in\mathbb R\times\mathbb R^{d-1},
\qquad
\theta(\tau,\mathbf x)=(-\tau,\mathbf x).
$$

Let $\mathbb R^d_+$ denote the positive-time half-space $\tau>0$. Let $\mathcal A_+$ be the vector space of finite sequences

$$
F=(f_0,f_1,\ldots,f_N,0,0,\ldots),
$$

where

$$
f_n\in\mathcal S((\mathbb R^d)^n),
\qquad
\operatorname{supp} f_n\subset (\mathbb R^d_+)^n.
$$

Think of $F$ as a Euclidean polynomial observable

$$
F\sim f_0+
\sum_{n\ge1}
\int f_n(x_1,\ldots,x_n)
\phi(x_1)\cdots\phi(x_n)
\,d^dx_1\cdots d^dx_n.
$$

This notation is mnemonic. At the starting point, $\phi(x)$ need not be an operator; the only input is the sequence of distributions $S_n$.

## The theorem

A compact scalar version of the theorem is as follows.

**Osterwalder–Schrader reconstruction theorem.** Let $\underline S=(S_n)_{n\ge0}$ be a sequence of scalar Schwinger distributions on $(\mathbb R^d)^n$ satisfying the OS hypotheses: normalization, regularity and growth, Euclidean covariance, permutation symmetry, reflection positivity, and a suitable cluster property. Then there exists a Wightman QFT

$$
(\mathcal H,\Omega,U,\Phi)
$$

such that:

| Reconstructed object | Origin in the Euclidean data |
|---|---|
| Hilbert space $\mathcal H$ | OS positive form on positive-time test polynomials. |
| Vacuum $\Omega$ | The class of the constant polynomial $1$. |
| Hamiltonian $H\ge0$ | Positive Euclidean time translations. |
| Spatial momenta and rotations | Euclidean translations and rotations preserving the time-zero plane. |
| Lorentz boosts | Analytic continuation of Euclidean rotations mixing time and space. |
| Wightman functions | Boundary values analytically continued from Schwinger functions. |
| Locality | Euclidean permutation symmetry plus analytic continuation. |

The reconstructed Wightman functions have Schwinger functions $S_n$ as their Euclidean restrictions in the appropriate time-ordered Euclidean region. Conversely, Wightman theories satisfying the usual analytic assumptions produce Schwinger functions satisfying the OS axioms.

The statement is unique in the expected sense: the reconstructed cyclic Wightman theory is determined by the Schwinger functions up to unitary equivalence.

## Step 1: The OS inner product

For $F,G\in\mathcal A_+$, define the reflected conjugate of $f_m$ schematically by

$$
(\theta \overline f_m)(x_1,\ldots,x_m)
=
\overline{f_m(\theta x_m,\ldots,\theta x_1)}.
$$

The reversal of order is important for noncommutative or fermionic generalizations. For scalar symmetric Schwinger functions it is harmless but conventional.

The OS sesquilinear form is

$$
\langle F,G\rangle_{\mathrm{OS}}
=
\sum_{m,n\ge0}
\left\langle
S_{m+n},
(\theta\overline f_m)\otimes g_n
\right\rangle.
$$

In expanded notation, this pairs the reflected negative-time insertions from $F$ with the positive-time insertions from $G$.

Reflection positivity is exactly

$$
\langle F,F\rangle_{\mathrm{OS}}\ge0
\qquad
\text{for all }F\in\mathcal A_+.
$$

Thus $\mathcal A_+$ is a pre-Hilbert space except that some vectors may have zero norm.

## Step 2: Quotient and completion

Define the null space

$$
\mathcal N=
\{F\in\mathcal A_+:
\langle F,F\rangle_{\mathrm{OS}}=0\}.
$$

Because the form is positive semidefinite, $\mathcal N$ is a subspace. The reconstructed Hilbert space is

$$
\mathcal H=
\overline{\mathcal A_+/\mathcal N}.
$$

The vacuum vector is

$$
\Omega=[1],
$$

where $1$ denotes the sequence with $f_0=1$ and all higher components zero.

This is the same logic as the GNS construction: a positive functional defines a Hilbert space by quotienting null vectors. The OS twist is that positivity is not ordinary positivity of a Euclidean algebra; it is positivity after time reflection.

## Step 3: Time translations and positive energy

Let $T(a)$ translate Euclidean time by $a\ge0$:

$$
(T(a)f)(\tau,\mathbf x)=f(\tau-a,\mathbf x)
$$

with the induced action on all test variables. Positive translations preserve the positive-time half-space, so they act on $\mathcal A_+$ and descend to $\mathcal H$.

The OS axioms imply that these operators form a strongly continuous contraction semigroup:

$$
T(a+b)=T(a)T(b),
\qquad
\|T(a)\|\le1,
\qquad
T(0)=1.
$$

By the spectral theorem for self-adjoint contraction semigroups, there is a positive self-adjoint Hamiltonian $H$ such that

$$
T(a)=e^{-aH},
\qquad
H\ge0.
$$

This is how the Lorentzian spectral condition enters from Euclidean data. Positive energy is not put in by hand; it is reconstructed from reflection positivity and the semigroup structure of Euclidean time.

## Step 4: Spatial symmetries and the Poincaré group

Spatial translations and spatial rotations preserve the hyperplane $\tau=0$ and the positive-time half-space. They therefore act directly as unitary transformations on $\mathcal H$.

Euclidean rotations mixing $\tau$ with a spatial coordinate are subtler. They do not preserve $\mathbb R^d_+$ globally, so they are not initially operators on $\mathcal H$ in the same elementary way. The OS theorem uses analyticity and Euclidean covariance to continue these rotations to Lorentz boosts.

The outcome is a unitary representation of the proper orthochronous Poincaré group, with joint energy-momentum spectrum in the closed forward light cone:

$$
\operatorname{spec}(P^0,\mathbf P)
\subset
\overline V_+.
$$

Thus Euclidean invariance becomes Lorentzian Poincaré covariance only after the full reconstruction argument.

## Step 5: Fields and Wightman functions

There are two equivalent ways to describe the field reconstruction.

The first route constructs field operators on a dense domain generated by positive-time Euclidean insertions and then analytically continues their correlation functions.

The second route reconstructs Lorentzian Wightman distributions from the Schwinger functions and then applies the Wightman reconstruction theorem. This route is often cleaner conceptually because it separates two tasks:

$$
\begin{gathered}
\text{OS data}
\Longrightarrow
\text{Wightman distributions},
\\
\text{Wightman distributions}
\Longrightarrow
\text{Hilbert-space fields}.
\end{gathered}
$$

The resulting Lorentzian fields are operator-valued distributions on a common dense invariant domain. Their vacuum correlation functions are

$$
W_n(x_1,\ldots,x_n)
=
\langle\Omega,
\Phi(x_1)\cdots\Phi(x_n)
\Omega\rangle,
$$

again understood distributionally.

The Euclidean Schwinger functions are recovered by analytic continuation to imaginary time with the correct Euclidean ordering. The exact formula is most transparent in difference variables, because Wightman functions are boundary values of analytic functions in tube domains.

## What each OS axiom reconstructs

| OS input | Reconstructed Lorentzian feature |
|---|---|
| Regularity and growth | Tempered Wightman distributions and controllable field domains. |
| Euclidean covariance | Poincaré covariance. |
| Reflection positivity | Positive Hilbert-space inner product and $H\ge0$. |
| Symmetry of Schwinger functions | Local commutativity of bosonic fields. |
| Clustering | Vacuum uniqueness, under suitable hypotheses. |
| Normalization $S_0=1$ | Unit vacuum norm. |

This table should not be read as six independent switches. The theorem uses the assumptions together. For example, locality is not merely permutation symmetry; it is permutation symmetry plus the analytic structure that connects Euclidean and Lorentzian configurations.

## The converse direction

The reconstruction theorem is often paired with the converse statement. Starting from a Wightman QFT satisfying the usual spectral, locality, covariance, and vacuum assumptions, the Wightman functions extend analytically to tube domains. Evaluating the analytic continuation at imaginary time gives Schwinger functions.

Under suitable hypotheses, those Schwinger functions satisfy the OS axioms. Symbolically,

$$
\text{Wightman QFT}
\Longleftrightarrow
\text{OS Schwinger data}.
$$

The arrow from right to left is reconstruction. The arrow from left to right is Euclidean continuation.

The equivalence is one of the deepest reasons Euclidean QFT is useful: it lets one study Lorentzian quantum theories through Euclidean distributions, measures, and statistical mechanics.

## What the theorem does not prove

The OS reconstruction theorem does **not** prove that the formal expression

$$
\frac{1}{Z}\int \mathcal D\phi\,
\phi(x_1)\cdots\phi(x_n)e^{-S_E[\phi]}
$$

defines distributions $S_n$.

It also does **not** prove that a cutoff limit exists, that the limit is non-Gaussian, that gauge fixing is harmless, or that a chosen renormalized Lagrangian has a nonperturbative continuum realization.

The theorem says that once suitable Schwinger functions are constructed and verified, their Lorentzian interpretation is not a guess. It is reconstructed.

## Common pitfalls

**Calling every Euclidean correlator a Schwinger function.** In this chapter, a Schwinger family means correlation distributions intended to satisfy the OS requirements, not merely any Euclidean-looking Green function.

**Forgetting the quotient by null vectors.** Reflection positivity gives a semidefinite form. The Hilbert space is obtained only after removing zero-norm vectors.

**Treating $e^{-\tau H}$ as an assumption.** In the reconstruction theorem, $H\ge0$ is recovered from Euclidean time translations and reflection positivity.

**Assuming Euclidean covariance directly gives Lorentz boosts.** Spatial symmetries act directly; boosts require analytic continuation and the full theorem.

**Confusing reconstruction with construction.** Reconstruction turns valid data into a QFT. Constructive QFT supplies valid data for specific models.

**Ignoring growth conditions.** Positivity and symmetry at each fixed $n$ are not enough if the sequence of distributions grows too wildly to reconstruct fields.

## Relations to other pages

This page is the endpoint of the first OS arc: [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/), [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/), [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/), and [Euclidean Invariance](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-invariance/).

For the Lorentzian analogue, compare [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) and [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/). The constructive use of this theorem belongs later in the Constructive QFT and Path Integrals as Measures chapters.

## Research status

The OS reconstruction theorem is established mathematical physics. It is one of the standard equivalence bridges between Euclidean and Lorentzian axiomatic QFT for scalar bosonic theories under appropriate regularity hypotheses.

The active work lies around the theorem: constructing interacting Schwinger functions, handling gauge theories without losing positivity, proving continuum limits from lattice models, adapting reflection positivity to fermions and gauge-invariant observables, and understanding which Euclidean data arise from physically interesting Lorentzian theories.

## Exercises

### Exercise 1. The null vectors form a subspace

Let $\langle\cdot,\cdot\rangle$ be a positive semidefinite sesquilinear form on a vector space $V$. Show that

$$
\mathcal N=\{v\in V:\langle v,v\rangle=0\}
$$

is a subspace.

<details><summary><strong>Solution</strong></summary>

A positive semidefinite sesquilinear form obeys the Cauchy–Schwarz inequality on the quotient by null vectors, or directly by considering

$$
0\le \langle v+\lambda w,v+\lambda w\rangle
$$

as a quadratic polynomial in $\lambda$. If $v\in\mathcal N$, then Cauchy–Schwarz gives

$$
|\langle v,w\rangle|^2
\le
\langle v,v\rangle\langle w,w\rangle
=0,
$$

so $\langle v,w\rangle=0$ for all $w$.

If $v_1,v_2\in\mathcal N$, then for any scalars $a,b$,

$$
\langle av_1+bv_2,av_1+bv_2\rangle=0
$$

because every term contains $\langle v_i,w\rangle$ for some $w$. Hence $av_1+bv_2\in\mathcal N$, and $\mathcal N$ is a subspace.

</details>

### Exercise 2. Why the Hamiltonian is positive

Suppose reconstructed Euclidean time translations form a self-adjoint contraction semigroup $T(\tau)$ for $\tau\ge0$. Explain why its generator can be written as $T(\tau)=e^{-\tau H}$ with $H\ge0$.

<details><summary><strong>Solution</strong></summary>

A strongly continuous self-adjoint contraction semigroup has a self-adjoint generator $-H$ by the spectral theorem for semigroups. Since $\|T(\tau)\|\le1$, the spectral values of $T(\tau)$ lie in $[0,1]$ for $\tau>0$. Writing spectral values as $e^{-\tau E}$ gives $E\ge0$. Therefore the generator $H$ is positive and

$$
T(\tau)=e^{-\tau H}.
$$

In OS reconstruction, reflection positivity is the input that makes the Euclidean time-translation semigroup compatible with the Hilbert-space norm.

</details>

### Exercise 3. Reconstruction versus construction

A physicist writes the formal Euclidean expression

$$
S_n(x_1,\ldots,x_n)=
\frac{1}{Z}\int \mathcal D\phi\,
\phi(x_1)\cdots\phi(x_n)e^{-S_E[\phi]}.
$$

List three additional tasks needed before OS reconstruction can be applied.

<details><summary><strong>Solution</strong></summary>

One must first give mathematical meaning to the expression, usually by a cutoff, a probability measure, or a limiting family of distributions. Second, one must prove that the cutoff can be removed or that the proposed limit exists as tempered Schwinger distributions. Third, one must verify the OS axioms: Euclidean covariance, symmetry, reflection positivity, regularity/growth, and clustering if vacuum uniqueness is desired.

Only after these tasks are complete does the OS reconstruction theorem produce the Lorentzian Wightman theory.

</details>

## References

- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- E. Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press, 2000.
- J. Fröhlich, "Schwinger Functions and Their Generating Functionals. I," *Helvetica Physica Acta* **47** (1974), 265–306.

## Version history

- **2026-06-28:** Initial polished draft.
