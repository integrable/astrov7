---
title: "Schwinger Functions"
description: "Defines Schwinger functions as the Euclidean analogue of Wightman functions and explains the distributional, symmetry, positivity, and reconstruction data they must carry."
sidebar:
  label: "Schwinger Functions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Schwinger; Symanzik; Osterwalder–Schrader; Nelson; Glimm–Jaffe."
topics:
  - Schwinger functions
  - Euclidean Green functions
  - Osterwalder–Schrader axioms
  - reflection positivity
  - reconstruction
canonicalTopics:
  - schwinger-functions
  - euclidean-green-functions
  - osterwalder-schrader-qft
researchStatus:
  established:
    - "Schwinger functions are the standard Euclidean correlation-function data in the Osterwalder–Schrader approach to rigorous QFT."
    - "A Schwinger family satisfying suitable OS hypotheses reconstructs a Lorentzian Wightman theory."
  active:
    - "For many physically important interacting theories, constructing Schwinger functions with all OS properties after removing cutoffs remains difficult or open."
---

## Summary

Schwinger functions are the Euclidean analogues of Wightman functions. For a scalar theory, they are a family

$$
(S_n)_{n\ge0},
\qquad
S_n\in\mathcal S'((\mathbb R^d)^n),
$$

usually written in kernel notation as

$$
S_n(x_1,\ldots,x_n)
=
\langle \Phi(x_1)\cdots\Phi(x_n)\rangle_E.
$$

They are not merely convenient perturbative Green functions. In the Osterwalder–Schrader framework, a Schwinger family is candidate nonperturbative QFT data. If it satisfies the appropriate regularity, Euclidean covariance, permutation symmetry, reflection positivity, and clustering or vacuum-selection assumptions, then one can reconstruct a Lorentzian Hilbert-space QFT.

The most important conceptual difference from Wightman functions is that scalar Schwinger functions are symmetric Euclidean distributions, while Wightman functions are ordered Lorentzian vacuum expectation values. The order is recovered by restricting to ordered Euclidean time regions and analytically continuing.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Schwinger functions and the Osterwalder–Schrader checklist](/figures/rigorous-qft/schwinger-functions-os-checklist.svg)

<figcaption>

A Schwinger family becomes Lorentzian QFT data only after passing structural checks. Reflection positivity is the key condition that produces the Hilbert-space inner product; the remaining conditions control covariance, symmetry, regularity, and vacuum structure.

</figcaption>
</figure>

## Prerequisites

Read [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/) first. You should also know [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/), [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/), and the smearing conventions from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

This page prepares for the later pages on OS axioms, reflection positivity, and OS reconstruction. It gives the data and the meaning of the conditions, not the full theorem.

## Logical status

| Item | Status |
|---|---|
| Type | Definition and framework page. |
| Framework | Osterwalder–Schrader Euclidean QFT. |
| Main object | A family of Euclidean distributions $S_n$ with $S_0=1$. |
| Main input | Distributional regularity, Euclidean covariance, symmetry, reflection positivity, and clustering or uniqueness conditions. |
| Main output | Candidate data for OS reconstruction of a Lorentzian Wightman theory. |
| Main caveat | A family of symmetric Euclidean functions is not automatically a unitary QFT. |

## Core idea

The Wightman framework starts from fields on a Hilbert space and then forms vacuum correlation functions. The OS framework can run in the opposite direction. It starts from Euclidean correlation functions and asks whether they contain enough positivity and regularity to reconstruct the Hilbert space.

The slogan is

$$
\text{Schwinger functions}
+
\text{OS positivity}
+
\text{regularity}
\Longrightarrow
\text{Lorentzian QFT}.
$$

This is the reason Schwinger functions are more than Euclidean Feynman integrals. They are the data from which states, fields, Hamiltonian, and Wightman functions may be recovered.

## Setup and conventions

For a scalar bosonic theory on $\mathbb R_E^d$, a Schwinger family consists of multilinear functionals

$$
S_n(f_1,\ldots,f_n),
\qquad
f_j\in\mathcal S(\mathbb R^d),
$$

or equivalently distributions

$$
S_n\in\mathcal S'((\mathbb R^d)^n).
$$

The normalization is

$$
S_0=1.
$$

If kernels are used, smearing means

$$
S_n(f_1,\ldots,f_n)
=
\int_{(\mathbb R^d)^n}
S_n(x_1,\ldots,x_n)
\prod_{j=1}^n f_j(x_j)\,d^d x_j.
$$

This integral notation is distributional. The kernel may be singular at coincident points $x_i=x_j$, and those singularities carry physical information.

For a real scalar field with a $\Phi\mapsto-\Phi$ symmetry, one often has

$$
S_{2k+1}=0.
$$

This is a model-dependent symmetry statement, not part of the definition of Schwinger functions.

## Basic structural properties

A Schwinger family intended for OS reconstruction must satisfy several kinds of conditions. Different references package the hypotheses slightly differently, especially the growth conditions, but the following checklist captures the core content.

| Property | Meaning | Why it matters |
|---|---|---|
| Regularity | $S_n$ are distributions with suitable growth or temperedness bounds. | Allows smearing, analytic continuation, and reconstruction of fields. |
| Euclidean covariance | Translations and rotations act correctly. | Becomes Poincaré covariance after reconstruction. |
| Symmetry | Bosonic $S_n$ are invariant under permutations of arguments. | Encodes Euclidean locality and loss of Lorentzian operator ordering. |
| Reflection positivity | Positive-time functionals have nonnegative reflected norm. | Produces the Hilbert-space inner product. |
| Clustering or vacuum selection | Far separated correlators factor appropriately. | Selects a vacuum sector and controls uniqueness of the vacuum. |

The next pages turn these entries into precise axiom-level statements. The point here is that no single item is enough by itself. For example, a Euclidean-invariant symmetric two-point function can still fail reflection positivity.

## Symmetry and Euclidean covariance

For scalar fields, Euclidean covariance says

$$
S_n(Rx_1+a,\ldots,Rx_n+a)
=
S_n(x_1,\ldots,x_n),
$$

for Euclidean transformations

$$
R\in O(d),
\qquad
a\in\mathbb R^d.
$$

Permutation symmetry says

$$
S_n(x_{\sigma(1)},\ldots,x_{\sigma(n)})
=
S_n(x_1,\ldots,x_n),
\qquad
\sigma\in S_n,
$$

for a bosonic scalar field. For fermionic fields, the Schwinger functions carry Grassmann or spinor data, and permutations introduce signs or matrix actions. Fermionic Euclidean reconstruction has additional bookkeeping, so the scalar case is the clean first model.

Translation invariance lets one reduce the number of independent variables. For example,

$$
S_n(x_1,\ldots,x_n)
=
S_n(x_1-x_n,\ldots,x_{n-1}-x_n,0).
$$

In practice, singularities occur when relative variables approach the diagonal. This is the Euclidean version of the short-distance singularity problem.

## Reflection positivity in Schwinger notation

Let

$$
\mathbb R_+^d
=
\{(\tau,\mathbf x):\tau>0\}.
$$

For a test function $f$ supported in positive Euclidean time, define reflected conjugation by

$$
(\Theta f)(\tau,\mathbf x)
=
\overline{f(-\tau,\mathbf x)}.
$$

A finite positive-time polynomial functional can be represented schematically as

$$
F
=
\sum_\alpha c_\alpha\,
\Phi(f_{\alpha,1})\cdots
\Phi(f_{\alpha,n_\alpha}),
$$

with all $f_{\alpha,j}$ supported in $\tau>0$. Reflection positivity requires

$$
\langle \Theta F\,F\rangle_E\ge0.
$$

In terms of Schwinger functions, this means

$$
\begin{aligned}
0\le
\sum_{\alpha,\beta}
\overline{c_\alpha}c_\beta\,
S_{n_\alpha+n_\beta}(&
\Theta f_{\alpha,n_\alpha},\ldots,
\Theta f_{\alpha,1},\\
&f_{\beta,1},\ldots,
f_{\beta,n_\beta}).
\end{aligned}
$$

The reversal of the reflected factors is the Euclidean shadow of taking an adjoint. This is the same pattern as

$$
\langle A\Omega,B\Omega\rangle
=
\langle\Omega,A^*B\Omega\rangle
$$

in a Hilbert space.

## How reconstruction begins

The OS construction starts from positive-time polynomial functionals $F$. Reflection positivity defines a semidefinite inner product

$$
(F,G)_E=\langle \Theta F\,G\rangle_E.
$$

Null vectors are quotiented out:

$$
\mathcal N
=
\{F:(F,F)_E=0\}.
$$

Then one completes

$$
\mathcal H
=
\overline{\mathcal P_+/\mathcal N},
$$

where $\mathcal P_+$ is the vector space of positive-time polynomial functionals. The constant functional $1$ becomes the vacuum vector.

Positive Euclidean time translations act as a contraction semigroup on $\mathcal H$:

$$
T(a)=e^{-aH},
\qquad
a\ge0,
$$

and the generator satisfies

$$
H\ge0.
$$

This is the Euclidean origin of the Lorentzian spectral condition. The full reconstruction then recovers fields and Wightman functions by analytic continuation. The details require the precise OS axioms and are the subject of the later reconstruction page.

## Comparison with Wightman functions

| Feature | Wightman functions | Schwinger functions |
|---|---|---|
| Spacetime | Minkowski spacetime. | Euclidean space. |
| Typical notation | $W_n(x_1,\ldots,x_n)$ | $S_n(x_1,\ldots,x_n)$ |
| Ordering | Operator order matters. | Bosonic scalar functions are symmetric. |
| Positivity | Hilbert-space positivity is built in. | Reflection positivity must be imposed. |
| Symmetry | Poincaré covariance. | Euclidean covariance. |
| Time evolution | Unitary group $e^{-itH}$. | Contraction semigroup $e^{-\tau H}$. |
| Reconstruction | Wightman reconstruction from $W_n$. | OS reconstruction from $S_n$. |

For ordered Euclidean times

$$
\tau_1>\cdots>\tau_n,
$$

the relation to Wightman functions is schematically

$$
\begin{aligned}
&S_n((\tau_1,\mathbf x_1),\ldots,(\tau_n,\mathbf x_n))
\\
&\qquad =
W_n((-i\tau_1,\mathbf x_1),\ldots,
(-i\tau_n,\mathbf x_n)),
\end{aligned}
$$

where the right-hand side denotes the analytic continuation of the Wightman function in its appropriate tube domain. A different Euclidean time ordering corresponds to a different Lorentzian operator ordering. This is why the symmetric Euclidean distribution can still encode noncommuting Lorentzian fields.

## Free scalar Schwinger functions

The free massive scalar Euclidean covariance is

$$
C_m(x-y)
=
\int\frac{d^d p_E}{(2\pi)^d}
\frac{e^{ip_E\cdot_E(x-y)}}{p_E^2+m^2}.
$$

The centered Gaussian Schwinger family is

$$
S_{2k+1}=0,
$$

and

$$
S_{2k}(x_1,\ldots,x_{2k})
=
\sum_{\text{pairings }P}
\prod_{\{a,b\}\in P}
C_m(x_a-x_b).
$$

The two-point function has the positive-time representation

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}
 e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}},
$$

with

$$
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

This representation makes reflection positivity visible. If $f$ is supported in positive Euclidean time, then

$$
\int \overline{f(\theta x)}C_m(x-y)f(y)\,d^dx\,d^dy
\ge0,
$$

because after spatial Fourier transform it becomes an integral of absolute squares with positive weights.

## Moment problem caveat

A Schwinger family may or may not come from an actual probability measure. If a measure exists and has sufficient moments, then its moments define $S_n$. Conversely, reconstructing a measure from a family of moments is an infinite-dimensional moment problem and requires positivity and continuity conditions beyond formal formulas.

The OS theorem does not always need a previously constructed measure. It can reconstruct a Lorentzian theory directly from a suitable family $S_n$. Constructive QFT often takes the measure route because Euclidean probability methods are powerful, but the Schwinger-function formulation is more flexible as axiomatic data.

## Common pitfalls

**Assuming symmetry means commutativity of Lorentzian fields at all separations.** Bosonic Schwinger functions are symmetric Euclidean distributions. Lorentzian locality is recovered after reconstruction and only gives commutation at spacelike separation.

**Ignoring the positive-time restriction.** Reflection positivity is not ordinary pointwise positivity of $S_n$. It is positivity of reflected pairings of functionals supported in $\tau>0$.

**Replacing reflection positivity by positivity of the two-point function.** Two-point positivity is necessary in simple cases, but the OS condition involves all positive-time polynomial functionals and all $n$-point functions.

**Forgetting null vectors.** Reflection positivity gives a semidefinite form. The Hilbert space is obtained only after quotienting by zero-norm vectors and completing.

**Treating OS conditions as automatic for every lattice action.** Some common lattice discretizations preserve reflection positivity, but others do not. The property must be checked.

## Relations to other pages

- [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/) explains the two ways Euclidean correlators arise: moments of a measure and analytic continuation.
- [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) gives the Lorentzian correlation-function data that Schwinger functions reconstruct.
- [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) is the Lorentzian analogue: it reconstructs fields and Hilbert space from Wightman functions.
- [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) explains the positive-energy condition that appears on the Euclidean side as positive-time decay.

## Research status

The definition and use of Schwinger functions are established. The OS reconstruction theorem gives a precise equivalence, under suitable hypotheses, between Euclidean Schwinger functions and Lorentzian Wightman theories.

The main research difficulty is not the definition but construction. Gaussian free fields are standard. Many interacting lower-dimensional models have rigorous Schwinger functions. Four-dimensional interacting gauge theories of central physical interest remain far harder to construct nonperturbatively in the continuum.

## Exercises

### Exercise 1: Why the reflected order reverses

Let $F=\Phi(f_1)\Phi(f_2)$ with both $f_1$ and $f_2$ supported at positive Euclidean time. Explain why the reflected factor in $\langle\Theta F\,F\rangle_E$ should involve

$$
\Theta f_2,\Theta f_1
$$

rather than

$$
\Theta f_1,\Theta f_2.
$$

<details>
<summary><strong>Solution</strong></summary>

The reflection operation plays the role of taking an adjoint. In an operator Hilbert space,

$$
(AB)^*=B^*A^*.
$$

Therefore the reflected copy of a product must reverse the order of its factors. For scalar Euclidean functions the final numerical value may be symmetric, but the order reversal is essential for matching the Hilbert-space inner product and for generalizing to noncommuting or fermionic fields.

</details>

### Exercise 2: Two-point reflection positivity for the free scalar

Using

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}
 e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}},
$$

show that

$$
\int \overline{f(\theta x)}C_m(x-y)f(y)\,d^dx\,d^dy\ge0
$$

for $f$ supported in $\tau>0$.

<details>
<summary><strong>Solution</strong></summary>

Write $x=(\tau,\mathbf x)$ and $y=(\sigma,\mathbf y)$ with $\sigma>0$. Since $f(\theta x)$ is supported when $\tau<0$, the difference $x-y$ has Euclidean time component $\tau-\sigma<0$, so

$$
|\tau-\sigma|=\sigma-\tau.
$$

After spatial Fourier transform, the quadratic form becomes

$$
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{1}{2\omega_{\mathbf p}}
\left|
\int_0^\infty d\sigma\,
 e^{-\omega_{\mathbf p}\sigma}
 \widehat f(\sigma,\mathbf p)
\right|^2,
$$

up to the conventional Fourier normalization. This is nonnegative because it is an integral of absolute squares with positive weight $1/(2\omega_{\mathbf p})$.

</details>

### Exercise 3: Symmetric Euclidean data and ordered Lorentzian data

A real scalar Schwinger function satisfies

$$
S_2(x_1,x_2)=S_2(x_2,x_1).
$$

Why does this not imply that the reconstructed Lorentzian fields commute at timelike separation?

<details>
<summary><strong>Solution</strong></summary>

The symmetric Euclidean two-point function combines boundary values from different Lorentzian ordering domains. In one Euclidean time ordering it analytically continues to $\langle\Omega,\phi(x_1)\phi(x_2)\Omega\rangle$; in the opposite ordering it continues to $\langle\Omega,\phi(x_2)\phi(x_1)\Omega\rangle$. These are different Wightman functions at timelike separation. Locality only forces equality for spacelike separation, not for timelike separation.

</details>

## References

### Original and standard references

- J. Schwinger, "On the Euclidean Structure of Relativistic Field Theory," *Proceedings of the National Academy of Sciences* **44** (1958), 956–965. DOI: [10.1073/pnas.44.9.956](https://doi.org/10.1073/pnas.44.9.956).
- J. Schwinger, "Euclidean Quantum Electrodynamics," *Physical Review* **115** (1959), 721–731. DOI: [10.1103/PhysRev.115.721](https://doi.org/10.1103/PhysRev.115.721).
- K. Symanzik, "Euclidean Quantum Field Theory. I. Equations for a Scalar Model," *Journal of Mathematical Physics* **7** (1966), 510–525. DOI: [10.1063/1.1704960](https://doi.org/10.1063/1.1704960).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

### Textbook and constructive references

- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- E. Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).
- F. Guerra, L. Rosen, and B. Simon, "The $P(\phi)_2$ Euclidean Quantum Field Theory as Classical Statistical Mechanics. Part I," *Annals of Mathematics* **101** (1975), 111–189. DOI: [10.2307/1970988](https://doi.org/10.2307/1970988).
- F. Guerra, L. Rosen, and B. Simon, "The $P(\phi)_2$ Euclidean Quantum Field Theory as Classical Statistical Mechanics. Part II," *Annals of Mathematics* **101** (1975), 191–259. DOI: [10.2307/1970989](https://doi.org/10.2307/1970989).

## Version history

- **2026-06-28:** Initial polished draft for the Osterwalder–Schrader and Euclidean QFT chapter.
