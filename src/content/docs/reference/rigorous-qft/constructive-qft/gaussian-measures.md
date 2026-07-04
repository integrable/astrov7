---
title: "Gaussian Measures"
description: "Constructs the free Euclidean scalar field as a Gaussian probability measure on distributions and explains covariance, Cameron–Martin space, Wick powers, and reflection positivity."
sidebar:
  label: "Gaussian Measures"
  order: 3
level: Advanced
status: "Polished draft"
source: "Glimm–Jaffe functional integrals; Simon P(φ)₂; Bogachev Gaussian measures; Janson Gaussian Hilbert spaces."
topics:
  - Gaussian measures
  - Euclidean free fields
  - Cameron–Martin space
  - Wick products
  - constructive QFT
canonicalTopics:
  - gaussian-random-fields
  - euclidean-quantum-field-theory
  - constructive-quantum-field-theory
  - wick-ordering
researchStatus:
  established:
    - 'The massive free Euclidean scalar field is rigorously a centered Gaussian measure on a space of tempered distributions, with covariance $(-\Delta+m^2)^{-1}$.'
  active:
    - "Interacting constructive models use Gaussian measures as reference objects, but the renormalized non-Gaussian measures require model-specific estimates."
---

## Summary

Gaussian measures are the rigorous replacement for the free Euclidean path integral. The expression

$$
\mathcal D\phi\,
\exp\left[-\frac12\int \phi(-\Delta+m^2)\phi\,d^dx\right]
$$

is not a density with respect to an infinite-dimensional Lebesgue measure. The rigorous object is instead a probability measure $\mu_C$ on generalized fields whose smeared random variables are jointly Gaussian.

For the massive scalar field on Euclidean $\mathbb R^d$, the covariance is

$$
C=(-\Delta+m^2)^{-1},
\qquad m>0,
$$

and the measure is characterized by the characteristic functional

$$
\int e^{i\phi(f)}\,d\mu_C(\phi)
=
\exp\left(-\frac12\langle f,Cf\rangle\right).
$$

This one formula determines all free Schwinger functions. It also explains why free fields are distributions, why products such as $\phi(x)^2$ require Wick ordering, and why the Gaussian measure is the reference measure for $P(\phi)_2$, $\phi^4_3$, and many other constructive models.

:::note[Main convention]
This page uses Euclidean signature. The covariance $C=(-\Delta+m^2)^{-1}$ is the inverse of the positive elliptic operator $-\Delta+m^2$ on Euclidean space. Lorentzian fields appear only after Osterwalder–Schrader reconstruction.
:::

## Prerequisites

You should know [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/), [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), and [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/). The distributional viewpoint is developed in [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

## Core idea

A Gaussian Euclidean field is not a random function $x\mapsto \phi(x)$. It is a random distribution

$$
\phi\in \mathcal S'(\mathbb R^d)
$$

such that $\phi(f)$ is a real Gaussian random variable for every real test function $f\in\mathcal S(\mathbb R^d)$. The covariance is the bilinear form

$$
\mathbb E_{\mu_C}[\phi(f)\phi(g)]
=
\langle f,Cg\rangle.
$$

Once the covariance is known, every finite list

$$
\phi(f_1),\ldots,\phi(f_n)
$$

has a jointly Gaussian distribution. Thus the free field is specified by covariance data, not by a pointwise formula for $\phi(x)$.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Gaussian measure data](/figures/rigorous-qft/gaussian-measure-data.svg)

<figcaption>

The free Euclidean field is built from covariance data. The covariance determines the characteristic functional, hence the Gaussian measure on distributions, whose moments give Wick's theorem and whose Cameron–Martin space describes the exceptional directions along which the measure can be shifted quasi-invariantly.

</figcaption>
</figure>

The clean slogan is

$$
\text{free Euclidean field}
=
\text{centered Gaussian measure on }\mathcal S'
\text{ with covariance }C.
$$

## Setup and conventions

Let $E=\mathcal S(\mathbb R^d)$ be the real Schwartz space and $E'=\mathcal S'(\mathbb R^d)$ its continuous dual. A covariance is a continuous symmetric positive semidefinite bilinear form

$$
q(f,g)=\langle f,Cg\rangle,
\qquad f,g\in E.
$$

Continuity is important: it makes $q$ compatible with the topology on test functions. Positivity means

$$
q(f,f)\ge0.
$$

The associated characteristic functional is

$$
\chi(f)
=
\exp\left(-\frac12q(f,f)\right).
$$

By the Bochner–Minlos theorem, since $\mathcal S(\mathbb R^d)$ is nuclear, this continuous positive-definite functional with $\chi(0)=1$ defines a unique probability measure $\mu_C$ on $\mathcal S'(\mathbb R^d)$ satisfying

$$
\chi(f)
=
\int_{\mathcal S'}e^{i\phi(f)}\,d\mu_C(\phi).
$$

This is the rigorous meaning of the Gaussian free Euclidean path integral.

## The massive scalar covariance

For the massive scalar field, take

$$
C_m=(-\Delta+m^2)^{-1},
\qquad m>0.
$$

In momentum space, using the Fourier conventions of this volume,

$$
\langle f,C_m g\rangle
=
\int \frac{d^dp}{(2\pi)^d}
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2}.
$$

The two-point Schwinger distribution has kernel

$$
C_m(x-y)
=
\int \frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

The kernel notation is useful, but the smeared form is safer. At coincident points $C_m(0)$ is ultraviolet divergent for $d\ge2$, which is the first warning that $\phi(x)$ is not an honest pointwise random variable.

In finite volume, for example on a flat torus, one can see the field through modes. Formally,

$$
\phi(x)
=
\sum_k \frac{\xi_k}{\sqrt{k^2+m^2}}e_k(x),
$$

where the $\xi_k$ are Gaussian coefficients with the appropriate real-field condition. This formula is only a distributional expansion. It is useful because it shows why high-momentum modes prevent typical fields from being smooth.

## Moments and Wick's theorem

The centered Gaussian measure satisfies

$$
\mathbb E_{\mu_C}[\phi(f)]=0,
\qquad
\mathbb E_{\mu_C}[\phi(f)\phi(g)]
=
\langle f,Cg\rangle.
$$

All higher moments are determined by pairings. If $n$ is odd, then

$$
\mathbb E_{\mu_C}
[\phi(f_1)\cdots\phi(f_n)]
=0.
$$

If $n=2r$ is even, then

$$
\mathbb E_{\mu_C}
[\phi(f_1)\cdots\phi(f_{2r})]
=
\sum_P
\prod_{\{i,j\}\in P}
\langle f_i,Cf_j\rangle,
$$

where $P$ runs over pairings of $\{1,\ldots,2r\}$. This is Wick's theorem in its probabilistic form.

For example,

$$
\mathbb E[\phi(f_1)\phi(f_2)\phi(f_3)\phi(f_4)]
=
\langle f_1,Cf_2\rangle\langle f_3,Cf_4\rangle
+
\langle f_1,Cf_3\rangle\langle f_2,Cf_4\rangle
+
\langle f_1,Cf_4\rangle\langle f_2,Cf_3\rangle.
$$

This formula is the measure-theoretic source of free-field Wick contractions. Perturbative Feynman diagrams start by combining this Gaussian pairing rule with interactions.

## Why typical fields are distributions

The Cameron–Martin space and the support of the measure should not be confused. The covariance $C_m$ suggests a quadratic action

$$
\frac12\langle h,C_m^{-1}h\rangle
=
\frac12\int_{
\mathbb R^d}
\left(|\nabla h|^2+m^2h^2\right)d^dx,
$$

so the Cameron–Martin space is essentially $H^1(\mathbb R^d)$, with this massive Sobolev norm. Shifts by $h$ in this space are special: the translated measure is absolutely continuous with respect to the original Gaussian measure.

But a typical sample $\phi$ drawn from $\mu_{C_m}$ is not in $H^1$. In fact, it is much rougher. On a compact $d$-dimensional space, the free field belongs almost surely to negative Sobolev spaces $H^{-s}$ for

$$
s>\frac d2-1,
$$

and not to the corresponding positive-energy Cameron–Martin space. Thus the path-integral phrase "integrate over fields" should not be read as integration over classical finite-action configurations.

This distinction is one of the conceptual repairs provided by constructive QFT:

$$
\text{classical action space}
\neq
\text{probability support of the quantum field}.
$$

## Cameron–Martin shifts

Let $H_C$ be the Cameron–Martin space of the Gaussian measure. For $h\in H_C$, translation by $h$ changes the measure by the Cameron–Martin formula:

$$
\frac{d\mu_C(\phi-h)}{d\mu_C(\phi)}
=
\exp\left(
\phi(C^{-1}h)-\frac12\langle h,C^{-1}h\rangle
\right),
$$

where the expression is interpreted by approximation if $C^{-1}h$ is not an ordinary test function. In finite-dimensional notation this is just completing the square.

For $h\notin H_C$, the translated measure is singular with respect to $\mu_C$. This is one of the sharp differences between finite-dimensional Gaussian integrals and field measures. It also explains why shifts by classical background fields must be handled with care in infinite-dimensional path integrals.

## Wick powers

Because $\phi(x)$ is not a pointwise random variable, powers such as $\phi(x)^2$ are not directly defined. The Gaussian measure nevertheless provides canonical renormalized powers by Wick ordering.

Let $\rho_\epsilon$ be a smooth approximate identity and set

$$
\phi_\epsilon(x)=\phi(\rho_\epsilon(x-\cdot)).
$$

Then $\phi_\epsilon(x)$ is an ordinary Gaussian random variable with variance

$$
c_\epsilon(x)
=
\mathbb E[\phi_\epsilon(x)^2].
$$

In translation-invariant situations this is independent of $x$; write it as $c_\epsilon$. The first Wick powers are

$$
:\!\phi_\epsilon^2\!:(x)
=
\phi_\epsilon(x)^2-c_\epsilon,
$$

and

$$
:\!\phi_\epsilon^4\!:(x)
=
\phi_\epsilon(x)^4
-6c_\epsilon\phi_\epsilon(x)^2
+3c_\epsilon^2.
$$

More generally,

$$
:\!\phi_\epsilon^n\!:(x)
=
c_\epsilon^{n/2}
H_n\left(\frac{\phi_\epsilon(x)}{\sqrt{c_\epsilon}}\right),
$$

where $H_n$ is the probabilists' Hermite polynomial. The renormalized Wick power $:\!\phi^n\!:(f)$ is then defined, when the limit exists, by

$$
:\!\phi^n\!:(f)
=
\lim_{\epsilon\downarrow0}
\int f(x):\!\phi_\epsilon^n\!:(x)\,d^dx.
$$

This is the mathematical origin of normal ordering in Euclidean constructive scalar models.

## Reflection positivity for the free scalar

A Gaussian measure gives Euclidean moments, but reflection positivity is an additional structure. Let $\theta$ reflect Euclidean time:

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x).
$$

For functionals $F$ depending only on the field in positive Euclidean time, reflection positivity says

$$
\mathbb E_{\mu_C}\left[\overline{F(\theta\phi)}F(\phi)\right]
\ge0.
$$

For the massive scalar covariance $C_m=(-\Delta+m^2)^{-1}$, this positivity holds. One way to see the mechanism is to use the representation

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}|\tau|}}{2\omega_{\mathbf p}},
\qquad
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

For positive-time test functions, the reflected covariance becomes a positive kernel built from $e^{-\omega_{\mathbf p}\tau}$. This is the Euclidean shadow of the positive-energy one-particle Hilbert space.

Not every Gaussian covariance has this property. Reflection positivity is a physical condition, not a consequence of Gaussianity alone.

## Relation to Fock space

The Gaussian measure representation and the Fock-space representation are equivalent descriptions of the free field, but they organize the data differently.

| Euclidean measure language | Lorentzian/Fock language |
|---|---|
| Probability space of distributions | Hilbert space of states |
| Covariance $(-\Delta+m^2)^{-1}$ | One-particle energy $\omega_{\mathbf p}$ |
| Schwinger functions | Wightman functions after analytic continuation |
| Wick powers | Normal-ordered operators |
| Reflection positivity | Positive Hilbert-space inner product |
| Markov property in Euclidean time | Local Hamiltonian evolution |

Osterwalder–Schrader reconstruction turns the reflection-positive Euclidean Gaussian measure into the usual free scalar QFT. Constructive interacting models imitate this path: build a non-Gaussian Euclidean measure, prove OS positivity and regularity, then reconstruct.

## Common pitfalls

**Do not write $\mathcal D\phi$ as if it were Lebesgue measure.** The Gaussian measure is the primary object. There is no flat infinite-dimensional measure behind it.

**Do not confuse the Cameron–Martin space with the support of the field.** The Cameron–Martin space contains finite-action shifts. Typical field configurations are much rougher.

**Do not evaluate $\phi(x)$ before smearing.** Pointwise field values are usually ill-defined. Use $\phi(f)$ or a mollified field $\phi_\epsilon(x)$ and then take renormalized limits.

**Do not assume all covariances reconstruct relativistic QFTs.** A covariance can define a perfectly good Gaussian random distribution while failing reflection positivity.

**Do not treat Wick ordering as a cosmetic notation.** In constructive scalar QFT, Wick ordering subtracts divergent local Gaussian contractions. It is part of the definition of the renormalized interaction.

## Relations to other pages

[Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) explains why probability measures are the rigorous version of Euclidean path integrals. This page gives the free Gaussian model in detail.

[P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) uses $\mu_C$ as the reference measure and defines interactions by exponential weights built from Wick polynomials.

[OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains how reflection-positive Schwinger functions become a Lorentzian Hilbert-space QFT.

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) gives a more refined language for singularities of distributions. Gaussian covariance kernels are among the first examples where singular support and microlocal direction matter.

## Research status

The theory of Gaussian measures on nuclear spaces, Hilbert spaces, and Banach spaces is mature. The free scalar Euclidean field is a standard rigorous object. Its Schwinger functions satisfy the Euclidean axioms needed for reconstruction, and its Lorentzian reconstruction is the free Wightman scalar field.

The hard part is not the free measure. The hard part is controlling non-Gaussian perturbations of it after ultraviolet and infrared cutoffs are removed. In two Euclidean dimensions, Wick-ordered polynomial perturbations are among the classic constructive successes. In three dimensions, additional renormalization and deeper estimates are needed. In four dimensions, nontrivial scalar continuum limits and Yang–Mills existence remain much more delicate.

## Exercises

### Exercise 1

Differentiate the characteristic functional

$$
\chi(f)=\exp\left(-\frac12\langle f,Cf\rangle\right)
$$

to show that

$$
\mathbb E[\phi(f)\phi(g)]=\langle f,Cg\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Consider

$$
\chi(sf+tg)
=
\mathbb E\left[e^{i(s\phi(f)+t\phi(g))}\right].
$$

Then

$$
\mathbb E[\phi(f)\phi(g)]
=
-\left.
\frac{\partial^2}{\partial s\,\partial t}
\chi(sf+tg)
\right|_{s=t=0}.
$$

The exponent is

$$
-\frac12\left(
 s^2\langle f,Cf\rangle
 +2st\langle f,Cg\rangle
 +t^2\langle g,Cg\rangle
\right).
$$

Taking the mixed derivative at $s=t=0$ gives $-\langle f,Cg\rangle$, and the extra minus sign from differentiating $e^{i(s\phi(f)+t\phi(g))}$ gives

$$
\mathbb E[\phi(f)\phi(g)]=\langle f,Cg\rangle.
$$

</details>

### Exercise 2

Let $X$ be a centered Gaussian random variable with variance $c$. Define

$$
:\!X^2\!:=X^2-c,
\qquad
:\!X^4\!:=X^4-6cX^2+3c^2.
$$

Show that both Wick polynomials have expectation zero.

<details><summary><strong>Solution</strong></summary>

For a centered Gaussian variable,

$$
\mathbb E[X^2]=c,
\qquad
\mathbb E[X^4]=3c^2.
$$

Therefore

$$
\mathbb E[:\!X^2\!:]
=
\mathbb E[X^2]-c
=0.
$$

Also

$$
\mathbb E[:\!X^4\!:]
=
\mathbb E[X^4]
-6c\mathbb E[X^2]
+3c^2
=3c^2-6c^2+3c^2
=0.
$$

The coefficients are exactly the Gaussian self-contraction subtractions.

</details>

### Exercise 3

On a $d$-dimensional torus, write the massive free field formally as

$$
\phi=\sum_k \frac{\xi_k}{\sqrt{k^2+m^2}}e_k,
$$

with independent unit Gaussians $\xi_k$. Estimate when

$$
\mathbb E\|\phi\|_{H^{-s}}^2
<\infty.
$$

<details><summary><strong>Solution</strong></summary>

The Sobolev norm gives

$$
\mathbb E\|\phi\|_{H^{-s}}^2
\sim
\sum_k
\frac{(1+k^2)^{-s}}{k^2+m^2}.
$$

At large $|k|$, the summand behaves like $|k|^{-2s-2}$. A lattice sum in $d$ dimensions converges if

$$
2s+2>d.
$$

Thus $\phi\in H^{-s}$ almost surely for

$$
s>\frac d2-1.
$$

This explains why the two-dimensional massive free field is already distributional: it has arbitrarily small negative Sobolev regularity, but not ordinary function regularity.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974. DOI: [10.1515/9781400868759](https://doi.org/10.1515/9781400868759).
- Edward Nelson, "The Free Markoff Field," *Journal of Functional Analysis* **12** (1973), 211–227. DOI: [10.1016/0022-1236(73)90025-6](https://doi.org/10.1016/0022-1236(73)90025-6).

### Mathematical background on Gaussian measures

- Vladimir I. Bogachev, *Gaussian Measures*, Mathematical Surveys and Monographs 62, American Mathematical Society, 1998. DOI: [10.1090/surv/062](https://doi.org/10.1090/surv/062).
- Hui-Hsiung Kuo, *Gaussian Measures in Banach Spaces*, Lecture Notes in Mathematics 463, Springer, 1975. DOI: [10.1007/BFb0082008](https://doi.org/10.1007/BFb0082008).
- Svante Janson, *Gaussian Hilbert Spaces*, Cambridge University Press, 1997. DOI: [10.1017/CBO9780511526169](https://doi.org/10.1017/CBO9780511526169).

### Reconstruction and free fields

- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

## Version history

- **2026-06-29:** Initial page created.
