---
title: "Osterwalder–Schrader Axioms"
description: "States the Osterwalder–Schrader axioms for Euclidean Schwinger functions and explains how each condition encodes a Lorentzian Wightman property."
sidebar:
  label: "OS Axioms"
  order: 3
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader I/II; Streater–Wightman; Glimm–Jaffe; Simon."
topics:
  - Osterwalder–Schrader axioms
  - Euclidean Green functions
  - reflection positivity
  - reconstruction theorem
  - Wightman axioms
canonicalTopics:
  - osterwalder-schrader-axioms
  - euclidean-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "Under standard regularity assumptions, Schwinger functions satisfying the Osterwalder–Schrader axioms reconstruct a Wightman quantum field theory."
  active:
    - "The hard part in most interacting models is not writing the axioms but constructing continuum Schwinger functions that satisfy them."
---

## Summary

The Osterwalder–Schrader axioms are the Euclidean counterpart of the Wightman axioms. They specify when a family of Euclidean Schwinger functions

$$
\underline S=(S_0,S_1,S_2,\ldots),
\qquad
S_n\in\mathcal S'((\mathbb R^d)^n),
\qquad
S_0=1,
$$

is not merely a collection of Euclidean distributions but the Euclidean shadow of a Lorentzian quantum field theory.

For a neutral scalar field, the standard package is:

| Axiom | Informal content | Lorentzian role |
|---|---|---|
| OS0 | regularity and growth | fields are distributions with controlled analytic continuation |
| OS1 | Euclidean covariance | Poincaré covariance after reconstruction |
| OS2 | reflection positivity | Hilbert-space positivity and positive energy |
| OS3 | symmetry | local commutativity after continuation |
| OS4 | clustering | uniqueness of the vacuum, when imposed strongly enough |

Different references package the regularity conditions in slightly different ways. This page uses the common scalar-field presentation: tempered Schwinger distributions, Euclidean invariance, permutation symmetry, reflection positivity, and clustering, with an explicit warning that reconstruction theorems require suitable growth hypotheses.

<figure class="doc-figure" style="--figure-width: 40rem;">

![Logical role of the Osterwalder–Schrader axioms](/figures/rigorous-qft/os-axioms-logic.svg)

<figcaption>

The Osterwalder–Schrader axioms turn Euclidean correlation distributions into reconstruction data. Reflection positivity is the key condition: it is the Euclidean remnant of Hilbert-space positivity and positive-energy time evolution.

</figcaption>
</figure>

## Prerequisites

Read [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/) and [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/) first. You should also know why fields are smeared distributions from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) and the Lorentzian axiomatic package from [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/).

This page treats bosonic scalar fields on flat Euclidean $\mathbb R^d$. Fermions, gauge fields, charged fields, curved manifolds, and finite-temperature theories require modified versions of the same ideas.

## Logical status

| Item | Status |
|---|---|
| Page type | Definition and theorem-framework page. |
| Framework | Euclidean scalar QFT on $\mathbb R^d$. |
| Data | A sequence of Schwinger distributions $S_n$. |
| Main condition | Reflection positivity on positive-time test functions. |
| Main theorem | Suitable OS data reconstructs a Wightman theory. |
| Main caveat | The list of axioms is not a construction of an interacting model. |

## Core idea

The Lorentzian Wightman framework starts with a Hilbert space, fields, a vacuum, a unitary representation of the Poincaré group, a spectrum condition, and locality. The Euclidean framework starts with correlation functions and asks whether these correlations remember all of that Hilbert-space structure.

The nontrivial answer is yes, but only with the right positivity condition. Euclidean invariance by itself is too weak. Symmetry by itself is too weak. Even pointwise positivity of a few functions is too weak. The condition that replaces unitarity is **reflection positivity**: a quadratic form built by reflecting positive Euclidean times into negative Euclidean times must be nonnegative.

The slogan is

$$
\begin{gathered}
\text{Euclidean covariance}
+\text{ symmetry}
+\text{ reflection positivity}
+\text{ regularity}
+\text{ clustering}
\\
\Longrightarrow
\text{Hilbert space, fields, vacuum, locality, positive energy}.
\end{gathered}
$$

The implication is a reconstruction theorem. It is not the assertion that every formal Euclidean action defines a QFT. Most formal actions do not come with a proof that their continuum Schwinger functions exist, let alone that they satisfy the axioms.

## Setup and conventions

Write a Euclidean point as

$$
x=(\tau,\mathbf x)\in\mathbb R\times\mathbb R^{d-1}.
$$

The Euclidean time reflection is

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x).
$$

The positive-time region is

$$
\mathbb R^d_+=\{(\tau,\mathbf x):\tau>0\}.
$$

For a scalar field, the Schwinger functions are distributions

$$
S_n(x_1,\ldots,x_n)
\quad\text{on}\quad
(\mathbb R^d)^n.
$$

When ordinary function notation is used, it should be read distributionally. For example,

$$
S_n(f)
=
\int S_n(x_1,\ldots,x_n)f(x_1,\ldots,x_n)
\,d^dx_1\cdots d^dx_n
$$

means the pairing of $S_n$ with the test function $f$ whenever the integral is not literally defined.

A useful bookkeeping device is a finite sequence of test functions

$$
F=(f_0,f_1,\ldots,f_N,0,0,\ldots),
\qquad
f_n\in\mathcal S((\mathbb R^d)^n),
$$

with $f_n$ supported where all $n$ Euclidean times are positive. These sequences form the pre-Hilbert-space test objects used by reflection positivity.

## OS0: regularity and growth

The minimal regularity statement is that each $S_n$ is a tempered distribution,

$$
S_n\in\mathcal S'((\mathbb R^d)^n).
$$

This gives a controlled meaning to smearing and Fourier transformation. It is the Euclidean analogue of treating Lorentzian Wightman functions as tempered distributions.

For reconstruction, temperedness alone is usually not the whole story. One also needs growth bounds strong enough to continue the Schwinger functions to Wightman distributions and to control the reconstructed fields. References differ in how they state this part. A common formulation imposes a **linear growth condition** on the seminorms needed to bound $S_n$ as $n$ increases.

The reason is simple. Reconstruction constructs a Hilbert space from all $n$-point functions at once. If the high-point distributions grow too wildly, the formal inner products may exist one at a time but fail to produce well-defined operator-valued distributions.

A safe reader's summary is:

$$
\text{OS0}=
\text{Schwinger functions are distributions with enough growth control for reconstruction}.
$$

This is the most technical axiom, and it is often suppressed in physics discussions. It should not be suppressed in rigorous QFT.

## OS1: Euclidean covariance

Let $E(d)=\mathbb R^d\rtimes O(d)$ be the Euclidean group. For a scalar field, Euclidean covariance says

$$
S_n(Rx_1+a,\ldots,Rx_n+a)
=
S_n(x_1,\ldots,x_n)
$$

for $R\in O(d)$ and $a\in\mathbb R^d$, again in the sense of distributions.

For fields with spin or internal indices, this equation gains representation matrices. For example, vector or spinor fields transform their indices under the appropriate Euclidean rotation representation. This page avoids those complications.

Euclidean covariance has two jobs. Translations lead to the reconstructed energy-momentum operators. Rotations and Euclidean boosts analytically continue to Lorentz transformations. The ordinary-looking $O(d)$ symmetry of Euclidean space is therefore the source of Lorentz covariance after reconstruction.

A common mistake is to think that Euclidean invariance alone guarantees a unitary Lorentzian theory. It does not. One can write Euclidean-invariant kernels whose reconstructed time-evolution norm would be indefinite or negative. Reflection positivity is the missing condition.

## OS2: reflection positivity

Reflection positivity is the central Osterwalder–Schrader axiom. Define an antilinear reflection of test functions by reflecting Euclidean time and reversing the order of reflected insertions. For a sequence $F=(f_0,f_1,\ldots)$ supported at positive times, the OS quadratic form is schematically

$$
\langle F,F\rangle_{\mathrm{OS}}
=
\sum_{m,n\ge0}
S_{m+n}\bigl(\theta f_m\otimes f_n\bigr).
$$

Written in coordinates for scalar symmetric Schwinger functions, this means

$$
\begin{aligned}
\langle F,F\rangle_{\mathrm{OS}}
&=
\sum_{m,n\ge0}
\int
\overline{f_m(x_1,\ldots,x_m)}
\\
&\quad\times
S_{m+n}(\theta x_m,\ldots,\theta x_1,
 y_1,\ldots,y_n)
\\
&\quad\times
f_n(y_1,\ldots,y_n)
\,dX_m\,dY_n,
\end{aligned}
$$

where all variables $x_i,y_j$ have positive Euclidean time. The axiom says

$$
\langle F,F\rangle_{\mathrm{OS}}\ge0
\qquad
\text{for every positive-time sequence }F.
$$

The order reversal is harmless for a single neutral scalar field because the Schwinger functions are symmetric, but it is the correct memory of operator ordering and becomes important in more general settings.

Reflection positivity is the Euclidean form of Hilbert-space positivity. The reconstructed Hilbert space is obtained by quotienting by the null space

$$
\mathcal N=\{F:\langle F,F\rangle_{\mathrm{OS}}=0\}
$$

and completing:

$$
\mathcal H
=
\overline{\mathcal S_+/\mathcal N}^{\,\langle\cdot,\cdot\rangle_{\mathrm{OS}}}.
$$

This is why reflection positivity is not an optional technicality. Without it, the Euclidean data might reconstruct an indefinite inner-product space or no acceptable quantum theory at all.

## OS3: symmetry

For a scalar bosonic field, symmetry says

$$
S_n(x_{\pi(1)},\ldots,x_{\pi(n)})
=
S_n(x_1,\ldots,x_n)
$$

for every permutation $\pi\in S_n$.

This condition is easy to misunderstand. In Lorentzian QFT, fields do not commute at timelike separation. Why then are Euclidean Schwinger functions symmetric?

The answer is analytic continuation. Euclidean insertions are not Lorentzian operators at arbitrary real times. They are boundary values of analytic functions in imaginary time. The symmetry of the Euclidean functions, together with the analytic reconstruction, becomes local commutativity for Lorentzian fields at spacelike separation.

For fermionic fields, symmetry is replaced by graded antisymmetry with the appropriate signs. For fields with internal indices, the permutation also permutes those labels. For gauge-dependent fields, the statement must be made after choosing the right gauge-invariant or gauge-fixed framework.

## OS4: clustering

Clustering says that widely separated Euclidean experiments become independent. A typical scalar formulation is

$$
\lim_{|a|\to\infty}
S_{m+n}(x_1,\ldots,x_m,
 x_{m+1}+a,\ldots,x_{m+n}+a)
=
S_m(x_1,\ldots,x_m)S_n(x_{m+1},\ldots,x_{m+n}),
$$

for suitable large translations $a$.

The precise version depends on the desired conclusion. Clustering is commonly used to obtain uniqueness of the vacuum in the reconstructed theory. Stronger decay estimates can encode a mass gap or exponential clustering. Weaker cluster properties may be enough for some reconstruction statements but not for uniqueness claims.

Physically, OS4 prevents the Euclidean data from describing a direct sum of independent superselection copies with many invariant vacua. It is therefore a condition about the large-distance phase of the theory, not just about short-distance regularity.

## Reconstruction dictionary

The OS axioms are best remembered through the reconstruction dictionary.

| Euclidean datum | Reconstructed Lorentzian object |
|---|---|
| $S_0=1$ | normalized vacuum vector $\Omega$. |
| Positive-time test sequences | dense set of vectors. |
| Reflection-positive quadratic form | Hilbert-space inner product. |
| Time translations preserving the half-space | contraction semigroup $e^{-\tau H}$. |
| Positivity of the semigroup generator | spectral condition $H\ge0$. |
| Euclidean rotations and translations | Poincaré covariance after continuation. |
| Euclidean symmetry of $S_n$ | locality of Wightman fields. |
| Clustering | vacuum uniqueness, in standard formulations. |

The most important line is

$$
\text{positive Euclidean-time semigroup}
\quad\Longrightarrow\quad
\text{positive-energy Lorentzian time evolution}.
$$

After reconstruction, the analytic continuation of Schwinger functions gives Wightman functions in appropriate tube domains and then as boundary-value distributions on Minkowski spacetime.

## How the free scalar fits

The massive free scalar Euclidean two-point function is

$$
C_E(x-y)=
\int\frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

For $m>0$, this covariance is Euclidean invariant and tempered. The Gaussian Schwinger functions are defined by Wick's rule:

$$
S_{2n}(x_1,\ldots,x_{2n})
=
\sum_{\text{pairings}}
\prod_{(i,j)}C_E(x_i-x_j),
\qquad
S_{2n+1}=0.
$$

The nontrivial positivity check reduces to the positivity of the covariance kernel on reflected positive-time test functions. This is the prototype example for the next page. It is also the cleanest reminder that a Euclidean covariance is acceptable only when it has a positive spectral representation.

## Common pitfalls

**Treating the axioms as a path integral definition.** The OS axioms are conditions on Schwinger functions. A formal expression $e^{-S_E[\phi]}\mathcal D\phi$ must still be shown to produce such functions.

**Forgetting that reflection positivity is half-space positivity.** It is not positivity of $S_2(f,f)$ for arbitrary test functions. The reflection and the positive-time support are essential.

**Using a regulator as if it were a physical theory.** Some UV regulators improve convergence by adding negative-norm degrees of freedom. Such regulators may violate reflection positivity even if they are useful intermediate devices.

**Ignoring growth assumptions.** Reconstruction is a theorem about a whole sequence of distributions, not a slogan about analytic continuation of one two-point function.

**Equating Euclidean symmetry with Lorentzian commutativity.** The symmetry of Schwinger functions becomes locality only after analytic reconstruction.

**Applying scalar axioms blindly to gauge theory.** Gauge-fixed correlators can violate positivity even when the gauge-invariant theory is expected to be unitary.

## Relations to other pages

[Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/) introduces the Euclidean distributions that the OS axioms constrain. [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) studies the key positivity axiom in detail.

The Lorentzian comparison pages are [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/), [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/), and [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/). The Euclidean reconstruction theorem will make the dictionary above precise in a later page.

## Research status

The OS theorem is an established theorem-level bridge between Euclidean and Lorentzian axiomatic QFT. It is one of the cleanest ways to explain why Euclidean methods can preserve unitarity.

The difficult research problem is existence. For many interacting models, especially in four spacetime dimensions and in gauge theories, one can write plausible Euclidean actions but cannot yet prove that the continuum limit satisfies the full OS package. Constructive QFT, lattice field theory, and stochastic/SPDE approaches can be viewed partly as different strategies for producing OS-positive Euclidean data.

## Exercises

### Exercise 1

For a scalar Schwinger family, show that Euclidean covariance implies translation invariance of the two-point function:

$$
S_2(x,y)=C(x-y)
$$

for some distribution $C$.

<details><summary><strong>Solution</strong></summary>

Translation covariance says

$$
S_2(x+a,y+a)=S_2(x,y)
$$

for every $a\in\mathbb R^d$. Choose $a=-y$. Then

$$
S_2(x,y)=S_2(x-y,0).
$$

Define $C(z)=S_2(z,0)$. Distributionally this means $S_2$ factors through the difference variable $x-y$, so $S_2(x,y)=C(x-y)$.

</details>

### Exercise 2

Explain why the condition

$$
S_2(f,f)\ge0
$$

for all test functions $f$ is not the same as OS reflection positivity.

<details><summary><strong>Solution</strong></summary>

The expression $S_2(f,f)$ tests the covariance as an ordinary positive-definite kernel on all of Euclidean space. OS reflection positivity instead tests

$$
S_2(\theta\overline f,f)
$$

with $f$ supported in positive Euclidean time. The reflection is essential because it reconstructs a Hilbert inner product from a bra at negative Euclidean time and a ket at positive Euclidean time. A kernel may satisfy one positivity condition and not the other. The OS condition is the one tied to unitary Lorentzian reconstruction.

</details>

### Exercise 3

Why does clustering have no purely local meaning?

<details><summary><strong>Solution</strong></summary>

Clustering is a statement about the limit in which two groups of insertions are translated far apart. It cannot be checked from the behavior of Schwinger functions in a fixed bounded region or near coincident points. It probes the large-distance phase of the theory and is related to vacuum uniqueness and long-range order.

</details>

## References

- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- E. Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).

## Version history

- **2026-06-28:** Initial polished draft.
