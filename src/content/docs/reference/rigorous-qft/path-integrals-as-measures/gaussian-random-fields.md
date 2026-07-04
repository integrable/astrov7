---
title: "Gaussian Random Fields"
description: "A rigorous account of free Euclidean fields as Gaussian random distributions specified by test-function smearing and a covariance operator."
sidebar:
  label: "Gaussian Random Fields"
  order: 2
level: Graduate
status: "Polished draft"
source: "Gaussian Hilbert spaces; Gaussian measures; Nelson free Markoff field; Glimm–Jaffe constructive QFT; Osterwalder–Schrader Euclidean QFT."
topics:
  - Gaussian random fields
  - free Euclidean fields
  - covariance operators
  - random distributions
  - Wick products
canonicalTopics:
  - gaussian-random-field
  - euclidean-free-field
  - covariance-operator
  - random-distribution
researchStatus:
  established:
    - "Free Euclidean scalar fields are rigorously realized as centered Gaussian random distributions whose covariance is the Green function of an elliptic operator."
  active:
    - "Interacting fields require renormalized changes of measure; gauge, massless, boundary, and curved-background variants require model-specific care."
---

## Summary

A Gaussian random field is not first of all a random function $x\mapsto \Phi(x)$. In the rigorous Euclidean formulation it is a linear assignment

$$
f\longmapsto \Phi(f)
$$

from test functions to random variables, such that every finite vector

$$
\bigl(\Phi(f_1),
\ldots,
\Phi(f_n)\bigr)
$$

is jointly Gaussian. For a centered field, the law is determined by the covariance bilinear form

$$
\mathbb E[\Phi(f)\Phi(g)]=C(f,g).
$$

The free massive Euclidean scalar field in $d$ dimensions has covariance

$$
C_m(f,g)=
\int \frac{d^dp}{(2\pi)^d}
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2},
\qquad m>0.
$$

Equivalently, $C_m=(-\Delta+m^2)^{-1}$ in distributional notation. The random object $\Phi$ is typically a distribution, not an honest pointwise function. This is the probabilistic counterpart of the operator-valued distribution lesson in Lorentzian axiomatic QFT.

## Prerequisites

You should know [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/). The constructive page [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) gives a neighboring nonperturbative viewpoint, and [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) explains the Osterwalder–Schrader role of the same example.

## Core idea

A finite-dimensional Gaussian vector is determined by its covariance matrix. A Gaussian random field is the infinite-dimensional analog: it is determined by all covariances of smeared fields.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A Gaussian random field is specified by test functions, a positive covariance bilinear form, jointly Gaussian smeared variables, and a random distribution.](/figures/rigorous-qft/gaussian-random-field-data.svg)

<figcaption>

A Gaussian random field is a compatible family of finite-dimensional Gaussian laws. Each list of test functions gives a Gaussian vector. The whole compatible family is packaged as a random distribution $\Phi\in\mathcal D'(M)$ or $\mathcal S'(\mathbb R^d)$.

</figcaption>
</figure>

The shift from $\Phi(x)$ to $\Phi(f)$ is not pedantry. It is what makes the covariance finite, Wick's theorem meaningful, and ultraviolet singularities visible.

## Setup and conventions

Work on Euclidean $\mathbb R^d$ unless stated otherwise. Let $\mathcal S(\mathbb R^d)$ be the Schwartz space and $\mathcal S'(\mathbb R^d)$ its dual space of tempered distributions. For compactly supported smooth test functions one may use $C_c^\infty(\mathbb R^d)$ and $\mathcal D'(\mathbb R^d)$ instead.

A real centered Gaussian random field is a linear map

$$
\Phi:\mathcal S(\mathbb R^d)\longrightarrow
L^2(\Omega,\mathbb P)
$$

such that $\Phi(f)$ is real for real $f$, and every finite collection is jointly Gaussian. Its covariance is

$$
C(f,g)=\mathbb E[\Phi(f)\Phi(g)].
$$

The covariance must be symmetric and positive semidefinite:

$$
C(f,g)=C(g,f),
\qquad
C(f,f)\ge 0.
$$

For complex test functions, one extends sesquilinearly or bilinearly according to convention. This page uses real fields and real bilinear covariance; complexification is only a notational convenience.

## Characteristic functional

A centered Gaussian random field is equivalently described by its characteristic functional

$$
\chi(f)=
\mathbb E\left[e^{i\Phi(f)}\right]
=
\exp\left(-\frac12 C(f,f)\right).
$$

More generally,

$$
\mathbb E\left[
\exp\left(i\sum_{a=1}^n t_a\Phi(f_a)\right)
\right]
=
\exp\left(
-\frac12\sum_{a,b=1}^n
 t_a t_b C(f_a,f_b)
\right).
$$

This formula says that the random variables $\Phi(f_a)$ have covariance matrix

$$
C_{ab}=C(f_a,f_b).
$$

Thus the infinite-dimensional field is controlled by ordinary finite-dimensional Gaussian distributions for every finite list of test functions.

## The free scalar covariance

For the massive free scalar field, the covariance is the Green operator of the Euclidean Klein–Gordon operator:

$$
C_m=(-\Delta+m^2)^{-1},
\qquad m>0.
$$

In Fourier conventions compatible with this volume's Euclidean pages,

$$
C_m(f,g)=
\int \frac{d^dp}{(2\pi)^d}
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2}.
$$

Formally, one writes

$$
\mathbb E[\Phi(x)\Phi(y)]=C_m(x-y),
$$

where

$$
C_m(x-y)=
\int \frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

The word "formally" matters. $C_m(x-y)$ is singular at $x=y$, and $\Phi(x)$ itself is not a pointwise random variable in the usual continuum theory. The rigorous object is

$$
\Phi(f)=\int \Phi(x)f(x)\,d^dx,
$$

understood as distributional pairing.

## From modes to distributions

On a compact Euclidean manifold, or in finite volume with appropriate boundary conditions, let $(e_n)$ be eigenfunctions of a positive elliptic operator $A$ with eigenvalues $\lambda_n>0$. A cutoff Gaussian field can be written as

$$
\Phi_N=
\sum_{n=1}^N
\frac{\xi_n}{\sqrt{\lambda_n}}e_n,
$$

where the $\xi_n$ are independent standard real Gaussian random variables. Then

$$
\mathbb E[\Phi_N(f)\Phi_N(g)]
=
\sum_{n=1}^N
\frac{\langle f,e_n\rangle\langle g,e_n\rangle}{\lambda_n}.
$$

As $N\to\infty$, this may converge for every test pair $f,g$ even when $\Phi_N$ does not converge as an $L^2$ function. The limiting object lives in a negative Sobolev space with probability one.

For $A=-\Delta+m^2$ in $d$ dimensions, the heuristic Sobolev threshold is

$$
\Phi\in H^s_{\rm loc}
\quad\text{for every}\quad
s<1-\frac d2,
$$

but not at the borderline in general. Thus in $d=2$ the free field is already a random distribution of negative regularity, and in higher dimensions it is even rougher.

## Wick theorem and normal ordering

Since the field is Gaussian, smeared moments are sums over pairings:

$$
\mathbb E[\Phi(f_1)\cdots\Phi(f_{2n})]
=
\sum_{\text{pairings }P}
\prod_{\{r,s\}\in P} C(f_r,f_s),
$$

and odd moments vanish. This is Wick's theorem for the Euclidean free field.

Products at the same point are not automatically defined. A cutoff field $\Phi_\epsilon(x)$ has variance

$$
\mathbb E[\Phi_\epsilon(x)^2]
=C_\epsilon(x,x),
$$

which usually diverges as $\epsilon\downarrow0$. The Wick square is defined by subtracting this self-contraction before taking the limit:

$$
:\!\Phi_\epsilon(x)^2\!:
=
\Phi_\epsilon(x)^2-C_\epsilon(x,x).
$$

Higher Wick powers are defined similarly by Hermite-polynomial subtraction. These Wick powers are the building blocks of $P(\phi)_2$, $\phi^4_2$, $\phi^4_3$, and many constructive Euclidean interactions.

## White noise versus the free field

White noise $\eta$ has covariance

$$
\mathbb E[\eta(f)\eta(g)]
=
\int f(x)g(x)\,d^dx.
$$

The massive free field has covariance $(-\Delta+m^2)^{-1}$ instead. One can formally relate them by

$$
\Phi=(-\Delta+m^2)^{-1/2}\eta.
$$

This formula is useful because it shows that the free field is smoother than white noise by one derivative. It is still not usually a function. In $d$ dimensions, white noise has local regularity below $-d/2$, while the massive free field has local regularity below $1-d/2$.

## Reflection positivity and the Euclidean free field

Not every Gaussian random field is a relativistic free field. The covariance must have the right Euclidean invariance, positivity, and reflection structure.

For the massive scalar covariance on $\mathbb R^d$, reflection positivity follows from the representation

$$
\frac{1}{p_0^2+\omega(\mathbf p)^2},
\qquad
\omega(\mathbf p)=\sqrt{\mathbf p^2+m^2},
$$

which gives a positive semigroup in Euclidean time after Fourier transforming in $p_0$:

$$
\frac{e^{-\omega(\mathbf p)|\tau|}}{2\omega(\mathbf p)}.
$$

This positivity is what allows the Euclidean Gaussian field to reconstruct the ordinary free scalar Hilbert space. A Gaussian covariance chosen arbitrarily from probability theory may define a perfectly good random field but fail the Osterwalder–Schrader requirements for relativistic QFT.

## Massless and infrared caveats

The massless covariance is formally

$$
C_0=(-\Delta)^{-1}.
$$

On $\mathbb R^d$, infrared behavior depends on dimension and on the class of test functions. On compact spaces, the constant mode must be treated separately because $-\Delta$ has a zero eigenvalue. In two dimensions, the massless free scalar has logarithmic covariance and is usually defined modulo constants or through derivatives, vertex operators, or zero-mode prescriptions.

This is the first encounter with a theme that returns throughout rigorous QFT: ultraviolet and infrared singularities are different problems. Smearing cures pointwise ultraviolet singularities, but it does not automatically cure zero modes or long-distance divergences.

## Common pitfalls

**Thinking a random field must be a random function.** A random field in rigorous QFT is often a random distribution. Pointwise notation is shorthand for smeared statements.

**Confusing the covariance kernel with an ordinary function.** The expression $C(x-y)$ may be a distribution. The safe definition is $C(f,g)$.

**Assuming every Gaussian random field is a QFT.** A covariance can define a Gaussian probability law without satisfying Euclidean invariance, reflection positivity, spectral positivity, or locality after reconstruction.

**Multiplying fields before renormalizing.** Products such as $\Phi(x)^2$ and $\Phi(x)^4$ are singular in the continuum. Wick ordering and further counterterms are not optional in interacting low-dimensional models.

**Ignoring infrared zero modes.** The massless field can fail to exist as an ordinary scalar field without restrictions or quotienting by constants.

## Relations to other pages

This page is the probability-theoretic bridge from [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/) to cylinder measures and Minlos-type construction. It is also the measure-theoretic counterpart of [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/).

For Euclidean reconstruction, see [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). For interacting constructive uses, see [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/), and [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/).

## Research status

The Gaussian free field is one of the best-understood continuum QFT objects. Its probability law, covariance, Wick products, Markov properties, reflection positivity, and OS reconstruction are classical.

The active difficulties begin when one changes the Gaussian measure by singular interactions, imposes gauge constraints, studies massless or boundary-sensitive limits, or tries to take non-Gaussian continuum limits. In modern probability, Gaussian free fields also appear in statistical mechanics, conformal probability, stochastic PDEs, and random geometry; those applications use the same distributional lesson but often impose different physical structures.

## Exercises

### Exercise 1

Let $\Phi$ be a centered Gaussian random field with covariance $C$. Show that

$$
\mathbb E\left[e^{i\Phi(f)}\right]
=
\exp\left(-\frac12 C(f,f)\right).
$$

<details><summary><strong>Solution</strong></summary>

The random variable $X=\Phi(f)$ is an ordinary centered Gaussian random variable with variance

$$
\sigma^2=\mathbb E[X^2]=C(f,f).
$$

The characteristic function of a centered one-dimensional Gaussian is

$$
\mathbb E[e^{itX}]
=\exp\left(-\frac12 t^2\sigma^2\right).
$$

Setting $t=1$ gives

$$
\mathbb E[e^{i\Phi(f)}]
=\exp\left(-\frac12 C(f,f)\right).
$$

</details>

### Exercise 2

Use Wick's theorem to compute $\mathbb E[\Phi(f)^2\Phi(g)^2]$.

<details><summary><strong>Solution</strong></summary>

There are three pairings of the four smeared fields:

$$
\mathbb E[\Phi(f)^2\Phi(g)^2]
=
C(f,f)C(g,g)+2C(f,g)^2.
$$

The factor of $2$ comes from the two pairings that connect one copy of $f$ with one copy of $g$.

</details>

### Exercise 3

On a compact $d$-dimensional manifold, suppose $A=-\Delta+m^2$ has eigenvalues $\lambda_n\sim c n^{2/d}$. For the Gaussian field with covariance $A^{-1}$, show heuristically that $\Phi\in H^s$ requires $s<1-d/2$.

<details><summary><strong>Solution</strong></summary>

Write

$$
\Phi=\sum_n \frac{\xi_n}{\sqrt{\lambda_n}}e_n,
$$

with independent standard Gaussians $\xi_n$. The expected squared $H^s$ norm is comparable to

$$
\mathbb E\|\Phi\|_{H^s}^2
\sim
\sum_n (1+\lambda_n)^s\frac{1}{\lambda_n}.
$$

For large $n$, use $\lambda_n\sim c n^{2/d}$, giving summand proportional to

$$
n^{2(s-1)/d}.
$$

The series $\sum_n n^{\alpha}$ converges when $\alpha<-1$. Thus

$$
\frac{2(s-1)}{d}<-1,
\qquad
s<1-\frac d2.
$$

This is a regularity heuristic; precise almost-sure statements require standard Gaussian estimates.

</details>

## References

### Gaussian measures and random fields

- Svante Janson, *Gaussian Hilbert Spaces*, Cambridge University Press, 1997. Cambridge Core DOI: [10.1017/CBO9780511526169](https://doi.org/10.1017/CBO9780511526169).
- Vladimir I. Bogachev, *Gaussian Measures*, American Mathematical Society, 1998. DOI: [10.1090/surv/062](https://doi.org/10.1090/surv/062).
- Hui-Hsiung Kuo, *Gaussian Measures in Banach Spaces*, Lecture Notes in Mathematics **463**, Springer, 1975. DOI: [10.1007/BFb0082007](https://doi.org/10.1007/BFb0082007).
- Edward Nelson, "The Free Markoff Field," *Journal of Functional Analysis* **12** (1973), 211–227. DOI: [10.1016/0022-1236(73)90025-6](https://doi.org/10.1016/0022-1236(73)90025-6).
- Edward Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).

### QFT references

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

## Version history

- **2026-06-30:** Initial version.
