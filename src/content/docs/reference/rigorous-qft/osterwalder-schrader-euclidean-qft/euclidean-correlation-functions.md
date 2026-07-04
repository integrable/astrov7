---
title: "Euclidean Correlation Functions"
description: "Defines Euclidean correlation functions as moments of Euclidean fields or analytic continuations of Lorentzian correlators, and explains the role of Euclidean invariance and reflection positivity."
sidebar:
  label: "Euclidean Correlators"
  order: 1
level: Graduate
status: "Polished draft"
source: "Schwinger; Symanzik; Nelson; Osterwalder–Schrader; Glimm–Jaffe."
topics:
  - Euclidean correlation functions
  - Schwinger functions
  - Euclidean QFT
  - Wick rotation
  - reflection positivity
canonicalTopics:
  - euclidean-correlation-functions
  - schwinger-functions
  - osterwalder-schrader-qft
researchStatus:
  established:
    - "Euclidean correlation functions are the standard Euclidean data used in constructive QFT, lattice QFT, statistical field theory, and Osterwalder–Schrader reconstruction."
    - "Euclidean invariance by itself does not imply the existence of a unitary Lorentzian quantum field theory."
  active:
    - "For interacting continuum theories, the hard part is usually constructing the Euclidean measure or Schwinger functions and proving the positivity, regularity, and limit properties needed for reconstruction."
---

## Summary

Euclidean correlation functions are correlation functions on Euclidean space $\mathbb R_E^d$ rather than on Lorentzian spacetime. For a scalar Euclidean field $\Phi$, their unsmeared notation is

$$
S_n(x_1,\ldots,x_n)
=
\langle \Phi(x_1)\cdots \Phi(x_n)\rangle_E,
\qquad
x_j=(\tau_j,\mathbf x_j)\in\mathbb R_E^d.
$$

The notation has two common mathematical meanings. If a Euclidean probability measure $\mu_E$ on distributions has been constructed, then $S_n$ is a moment of that measure. If one starts from a Lorentzian Wightman theory, then $S_n$ can also be obtained by analytic continuation to imaginary time in an appropriate ordering domain. The two viewpoints agree in the cases covered by Osterwalder–Schrader reconstruction, but they are not the same definition.

The central warning is:

$$
\text{Euclidean invariance}
\quad\not\Rightarrow\quad
\text{unitary Lorentzian QFT}.
$$

The missing bridge is reflection positivity, together with regularity and growth assumptions. Euclidean correlators are therefore not just a convenient way to hide factors of $i$; they are a possible nonperturbative definition of QFT only when they pass the Osterwalder–Schrader tests.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Two ways Euclidean correlation functions enter rigorous QFT](/figures/rigorous-qft/euclidean-correlators-two-roads.svg)

<figcaption>

Euclidean correlators can arise as moments of a Euclidean measure or as analytic continuations of Lorentzian correlation functions. Osterwalder–Schrader conditions, especially reflection positivity, are what allow Euclidean data to reconstruct a Hilbert-space theory.

</figcaption>
</figure>

## Prerequisites

You should know the logical-status conventions from [Conventions and Logical Status](/rigorous-qft/conventions/), the distributional meaning of fields from [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), and the Lorentzian correlator language from [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/).

The page uses only the free scalar field as an example. The role of reflection positivity is explained here, but its precise axiom-level form is developed in the following pages.

## Logical status

| Item | Status |
|---|---|
| Type | Concept and definition page. |
| Framework | Euclidean QFT, constructive QFT, and Osterwalder–Schrader QFT. |
| Main object | A family of Euclidean distributions or moments $S_n$. |
| Main output | A precise language for Euclidean correlators before imposing the full OS axioms. |
| Main caveat | A formal expression $e^{-S_E[\Phi]}\mathcal D\Phi$ does not by itself define a measure or a Lorentzian theory. |

## Core idea

In ordinary perturbative QFT, one often says: rotate time to imaginary time, replace $e^{iS}$ by $e^{-S_E}$, and compute Euclidean Green functions. That sentence compresses several different mathematical operations.

The rigorous version separates them:

| Physics phrase | Mathematical question |
|---|---|
| Wick rotate $t=-i\tau$ | Does the Lorentzian correlation function have the required analytic continuation? |
| Write $e^{-S_E}\mathcal D\Phi$ | Is there a measure, or only a formal expression? |
| Compute $\langle\Phi(x_1)\cdots\Phi(x_n)\rangle_E$ | Is this a distributional moment, a perturbative coefficient, or a lattice cutoff quantity? |
| Rotate back to real time | Do the Schwinger functions satisfy reflection positivity and reconstruction hypotheses? |

This separation is why Euclidean QFT is so powerful. The Euclidean side often looks like statistical mechanics: correlations are moments, $e^{-S_E}$ resembles a Boltzmann weight, and correlation decay resembles a mass gap. But the Lorentzian side requires Hilbert-space positivity and unitary time evolution. Reflection positivity is the Euclidean remnant of that Hilbert-space structure.

## Setup and conventions

Euclidean spacetime is written

$$
\mathbb R_E^d
=
\{x=(\tau,\mathbf x):\tau\in\mathbb R,
\mathbf x\in\mathbb R^{d-1}\},
$$

with Euclidean inner product

$$
x\cdot_E y=\tau\sigma+\mathbf x\cdot\mathbf y,
\qquad
|x|_E^2=\tau^2+\mathbf x^2.
$$

The Euclidean group is

$$
E(d)=\mathbb R^d\rtimes O(d),
$$

or its orientation-preserving subgroup, depending on the field content. For a scalar field, Euclidean invariance says

$$
S_n(Rx_1+a,\ldots,Rx_n+a)
=
S_n(x_1,\ldots,x_n),
\qquad
R\in O(d),\ a\in\mathbb R^d.
$$

For tensor, spinor, or internal multiplet fields, the right-hand side includes the appropriate finite-dimensional representation matrices. Euclidean spinors require care: the Euclidean rotation group and the Lorentzian spin group are related by analytic continuation, not by a naive replacement of every gamma matrix.

The Euclidean time reflection used later is

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x).
$$

It is one particular reflection, not a general rotation. Its special role is that it cuts Euclidean space into negative-time and positive-time halves, just as a Hilbert-space inner product pairs bras and kets.

## Moments of a Euclidean field

A clean nonperturbative definition starts with a probability measure $\mu_E$ on a space of distributions, often a subspace of $\mathcal S'(\mathbb R^d)$. The Euclidean field $\Phi$ is then a random distribution. For a test function $f\in\mathcal S(\mathbb R^d)$, the smeared field is the random variable

$$
\Phi(f)=\langle \Phi,f\rangle.
$$

If the moments exist, define

$$
S_n(f_1,\ldots,f_n)
=
\int_{\mathcal S'(\mathbb R^d)}
\prod_{j=1}^n \Phi(f_j)\,d\mu_E(\Phi).
$$

When a distributional kernel exists, this is written as

$$
S_n(f_1,\ldots,f_n)
=
\int_{(\mathbb R^d)^n}
S_n(x_1,\ldots,x_n)
\prod_{j=1}^n f_j(x_j)\,d^d x_j.
$$

The unsmeared notation is convenient, but the smeared version is the safer definition. Singularities at coincident points are part of the theory, not a defect in notation.

A formal Euclidean path integral is the mnemonic

$$
\langle \mathcal O\rangle_E
=
\frac{\int \mathcal D\Phi\,\mathcal O(\Phi)e^{-S_E[\Phi]}}
{\int\mathcal D\Phi\,e^{-S_E[\Phi]}}.
$$

This is a definition only after the integral has been interpreted: finite-dimensional cutoff integral, Gaussian measure, constructive interacting measure, perturbative formal series, or another precise object.

## Generating functionals

When exponential moments exist, the Euclidean generating functional is

$$
Z_E[J]
=
\left\langle e^{\Phi(J)}\right\rangle_E.
$$

The moments are recovered by functional differentiation:

$$
S_n(x_1,\ldots,x_n)
=
\left.
\frac{\delta^n Z_E[J]}
{\delta J(x_1)\cdots\delta J(x_n)}
\right|_{J=0}.
$$

Connected Euclidean correlations come from

$$
W_E[J]=\log Z_E[J].
$$

In perturbation theory, one often writes $Z_E[J]$ by expanding around a Gaussian measure. In constructive QFT, $Z_E[J]$ or the moments $S_n$ must be controlled uniformly as cutoffs are removed. In the OS framework, one can formulate the axioms directly at the level of the family $S_n$, without first proving that a measure exists.

## Analytic continuation from Lorentzian QFT

A Lorentzian Wightman function is ordered and lives on Minkowski spacetime:

$$
W_n(x_1,\ldots,x_n)
=
\langle\Omega,
\phi(x_1)\cdots\phi(x_n)\Omega\rangle.
$$

The spectral condition makes these distributions boundary values of holomorphic functions in tube domains. For ordered Euclidean times

$$
\tau_1>\tau_2>\cdots>\tau_n,
$$

one formally obtains a Euclidean correlator by setting

$$
z_j=(-i\tau_j,\mathbf x_j)
$$

and writing

$$
S_n((\tau_1,\mathbf x_1),\ldots,(\tau_n,\mathbf x_n))
=
W_n(z_1,\ldots,z_n).
$$

The ordering condition matters. Wightman functions remember operator order; scalar Euclidean Schwinger functions are usually symmetric in their arguments. The symmetric Euclidean object is assembled from different time-ordering regions of the Lorentzian theory. Thus the slogan "Euclidean correlator equals Wick-rotated correlator" is true only after specifying which Lorentzian correlator, which ordering domain, and which boundary-value prescription are meant.

For time-ordered Lorentzian Green functions, the same relation is often written as

$$
\begin{aligned}
&S_n(\tau_1,\mathbf x_1;\ldots;\tau_n,\mathbf x_n)
\\
&\qquad =
G_n^T(t_1,\mathbf x_1;\ldots;t_n,\mathbf x_n)
\big|_{t_j=-i\tau_j},
\end{aligned}
$$

again with analytic and distributional qualifications.

## The free scalar two-point function

For the free massive scalar field in $d$ Euclidean dimensions, the covariance is

$$
C_m(x)
=
\int\frac{d^d p_E}{(2\pi)^d}
\frac{e^{ip_E\cdot_E x}}{p_E^2+m^2},
\qquad
m>0.
$$

Writing $p_E=(p_\tau,\mathbf p)$ and

$$
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

one can integrate over $p_\tau$ to obtain

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}
 e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}}.
$$

This formula is the Euclidean version of the free two-point function. The exponential $e^{-\omega|\tau|}$ is the Euclidean-time trace of positive energy. It is also the seed of reflection positivity: positive Euclidean time evolution becomes a positive contraction semigroup, and its generator becomes the Hamiltonian after reconstruction.

The full free scalar Euclidean field is Gaussian. Its higher correlations are determined by Wick's rule:

$$
S_{2k}(x_1,\ldots,x_{2k})
=
\sum_{\text{pairings }P}
\prod_{\{a,b\}\in P} C_m(x_a-x_b),
\qquad
S_{2k+1}=0.
$$

This is a rigorous Gaussian random distribution, not merely a formal path integral.

## Why reflection positivity is the bridge

Euclidean invariance says that rotations and translations act correctly. It does not say that a Lorentzian Hilbert space exists.

Reflection positivity supplies the missing positive inner product. Very schematically, if $F$ is a polynomial functional of fields supported at positive Euclidean time, then one demands

$$
\langle \Theta F\,F\rangle_E\ge0,
$$

where $\Theta$ reflects Euclidean time and complex conjugates coefficients. This expression becomes the Hilbert-space norm of the state represented by $F$ after OS reconstruction.

Without this condition, a Euclidean-invariant collection of functions can reconstruct to a theory with negative-norm states, no unitary time evolution, or no Lorentzian Hilbert-space interpretation at all. This is why lattice actions, continuum Euclidean actions, and proposed Schwinger functions must be checked for reflection positivity when the goal is a unitary relativistic QFT.

## Common pitfalls

**Calling every Euclidean Green function a QFT.** A Euclidean Green function is data. It becomes a Euclidean QFT in a strong sense only after positivity, regularity, covariance, and reconstruction conditions are specified.

**Confusing damping with unitarity.** The Euclidean factor $e^{-\tau H}$ is a contraction semigroup. Lorentzian unitarity is recovered only after analytic continuation and the Hilbert-space reconstruction.

**Treating $\mathcal D\Phi$ as a measure.** The symbol $\mathcal D\Phi$ is not a measure on an infinite-dimensional space. A Gaussian measure can often be constructed; an interacting measure requires work.

**Forgetting coincident-point singularities.** Euclidean correlators are distributions. Products, restrictions to diagonals, and composite fields require renormalization.

**Assuming all Wick rotations are contour rotations.** In rigorous QFT, the robust statement is analytic continuation of correlation functions in domains controlled by spectrum and positivity assumptions. A contour picture may be useful but is not the theorem.

## Relations to other pages

- [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/) turns the informal family $S_n$ into the standard Euclidean analogue of Wightman functions.
- [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) gives the Lorentzian ordered correlation functions from which Euclidean functions can be analytically continued.
- [Jost Points and Analyticity](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/) explains the tube-domain analyticity behind the Lorentzian-to-Euclidean passage.
- [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) explains why correlation functions should be read distributionally.

## Research status

The Euclidean framework is standard. It is central in constructive QFT, lattice QFT, statistical mechanics, and rigorous treatments of free fields. The OS reconstruction theorem gives precise conditions under which Euclidean data determine a Lorentzian Wightman theory.

The difficult part is existence. In many lower-dimensional models, Euclidean measures or Schwinger functions have been constructed and shown to satisfy the required axioms. For physically central four-dimensional interacting gauge theories, nonperturbative continuum construction with all desired properties remains a major open area.

## Exercises

### Exercise 1: Gaussian moments

Let $\mu$ be a centered Gaussian measure with covariance $C$. Show that

$$
S_2(f,g)=\int \Phi(f)\Phi(g)\,d\mu(\Phi)=C(f,g)
$$

and that the four-point function is

$$
\begin{aligned}
S_4(f_1,f_2,f_3,f_4)
={}&C(f_1,f_2)C(f_3,f_4)
+C(f_1,f_3)C(f_2,f_4)
\\
&+C(f_1,f_4)C(f_2,f_3).
\end{aligned}
$$

<details>
<summary><strong>Solution</strong></summary>

For a centered Gaussian random field, all odd moments vanish and all even moments are determined by the covariance through Wick's theorem. Thus the two-point moment is exactly the covariance. The fourth moment is the sum over the three pairings of four labels, giving the displayed expression.

</details>

### Exercise 2: Euclidean time decay of the free propagator

Starting from

$$
C_m(\tau,\mathbf x)
=
\int\frac{dp_\tau}{2\pi}
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{ip_\tau\tau+i\mathbf p\cdot\mathbf x}}
{p_\tau^2+\mathbf p^2+m^2},
$$

perform the $p_\tau$ integral and recover the factor $e^{-\omega_{\mathbf p}|\tau|}/(2\omega_{\mathbf p})$.

<details>
<summary><strong>Solution</strong></summary>

For fixed $\mathbf p$, set $\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}$. The remaining integral is

$$
I(\tau)=\int\frac{dp_\tau}{2\pi}
\frac{e^{ip_\tau\tau}}{p_\tau^2+\omega_{\mathbf p}^2}.
$$

For $\tau>0$, close the contour in the upper half-plane and pick the pole at $p_\tau=i\omega_{\mathbf p}$. For $\tau<0$, close in the lower half-plane and pick the pole at $p_\tau=-i\omega_{\mathbf p}$. In both cases,

$$
I(\tau)=\frac{e^{-\omega_{\mathbf p}|\tau|}}{2\omega_{\mathbf p}}.
$$

Substituting this into the spatial momentum integral gives the stated formula.

</details>

### Exercise 3: Euclidean invariance is not enough

Explain why the condition

$$
S_2(Rx+a,Ry+a)=S_2(x,y)
$$

for all Euclidean rotations $R$ and translations $a$ is not enough to reconstruct a physical Lorentzian scalar field.

<details>
<summary><strong>Solution</strong></summary>

Euclidean invariance only says that the two-point function transforms correctly under the Euclidean symmetry group. A physical Lorentzian reconstruction also needs positivity. In the OS framework, reflection positivity is what turns positive-time Euclidean functionals into vectors with nonnegative norm. Without it, the reconstructed object may have negative-norm states or fail to produce a Hilbert space with unitary time evolution. Regularity and growth assumptions are also needed to control the distributional and analytic continuation steps.

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
