---
title: "Probability Measures"
description: "A QFT-oriented introduction to probability spaces, laws, expectations, pushforwards, product measures, conditioning, convergence, characteristic functions, and path-integral analogies."
sidebar:
  label: "Probability Measures"
  order: 1
level: Graduate
status: "Polished draft"
source: "Measure-theoretic probability, statistical mechanics, Euclidean field theory, stochastic processes, and QFT generating-functional language."
topics:
  - probability measures
  - expectations
  - pushforward measures
  - product measures
  - conditioning
  - weak convergence
  - characteristic functions
  - Euclidean path integrals
canonicalTopics:
  - probability-space
  - random-variable
  - law-of-a-random-variable
  - expectation-functional
  - weak-convergence
researchStatus:
  established:
    - "Probability spaces, random variables, pushforward laws, expectations, product measures, conditional expectations, and weak convergence are standard foundations of modern probability theory."
  active:
    - "In QFT, the construction of continuum probability measures for interacting fields, gauge fields, stochastic PDEs, and scaling limits remains subtle and often research-level."
---

## Summary

A probability measure is a rule for integrating observables against a positive, normalized weight. The basic object is not a random number; it is a triple

$$
(\Omega,\mathcal F,\mathbb P),
$$

where $\Omega$ is the sample space, $\mathcal F$ is the collection of measurable events, and $\mathbb P$ assigns probabilities with

$$
\mathbb P(\Omega)=1,
\qquad
\mathbb P(A)\ge 0.
$$

A random variable is a measurable map

$$
X:\Omega\to E,
$$

and its probability distribution, or law, is the pushforward measure

$$
\mu_X=X_*\mathbb P.
$$

This distinction is priceless in QFT. The field configuration $\phi$ is analogous to the random variable; the Euclidean path-integral weight is analogous to the measure; correlation functions are expectations; connected correlators are cumulants. But the analogy has limits: Lorentzian path integrals are oscillatory, gauge theories have redundancies, and continuum fields are often distributions rather than honest functions.

The slogan for this page is:

$$
\text{probability theory is the grammar of expectation values}.
$$

## Prerequisites

You should know basic set notation, integration in one and several variables, and the idea of a linear functional. Familiarity with delta functions and Fourier transforms helps, but is not required.

We will use $\mathbb E[\cdots]$ for probability expectations and $\langle\cdots\rangle$ for QFT or statistical-mechanical expectation values. In Euclidean settings, these notations may describe the same mathematical operation.

## Why QFT cares

The most common QFT formula shaped like a probability expectation is

$$
\langle \mathcal O\rangle
=\frac{1}{Z}\int \mathcal D\phi\,\mathcal O[\phi]e^{-S_E[\phi]}.
$$

If the regularized Euclidean action $S_E$ is real and bounded below, then

$$
d\mu(\phi)=\frac{1}{Z}e^{-S_E[\phi]}\mathcal D\phi
$$

behaves like a probability measure. Then the correlation function is simply

$$
\langle \mathcal O\rangle=\int \mathcal O[\phi]d\mu(\phi).
$$

This probabilistic viewpoint is central to lattice field theory, statistical mechanics, Euclidean constructive QFT, stochastic quantization, disordered systems, random matrix models, and continuum limits.

<figure class="doc-figure" style="--figure-width: 43rem;">

![A diagram showing a sample space, random variable, pushforward law, and expectation functional.](/figures/math-toolkit/probability-measure-pushforward.svg)

<figcaption>

A random variable $X:\Omega\to E$ transports the microscopic probability measure $\mathbb P$ to a law $\mu_X$ on the value space $E$. Expectations may be computed either on $\Omega$ or on $E$.

</figcaption>
</figure>

## Probability spaces

A probability space consists of three ingredients.

The sample space $\Omega$ is the set of possible microscopic outcomes. The sigma-algebra $\mathcal F$ is the collection of events to which probabilities are assigned. The probability measure $\mathbb P$ is a countably additive function

$$
\mathbb P:\mathcal F\to[0,1].
$$

Countable additivity means that if $A_1,A_2,\ldots$ are disjoint events, then

$$
\mathbb P\!\left(\bigcup_{n=1}^\infty A_n\right)
=\sum_{n=1}^\infty \mathbb P(A_n).
$$

For a finite or countable sample space, this looks like ordinary sums. If

$$
\Omega=\{\omega_i\},
\qquad
p_i=\mathbb P(\{\omega_i\}),
$$

then

$$
\mathbb P(A)=\sum_{\omega_i\in A}p_i,
\qquad
\sum_i p_i=1.
$$

For a continuous variable $x\in\mathbb R^n$ with density $\rho(x)$,

$$
d\mathbb P(x)=\rho(x)d^nx,
\qquad
\rho(x)\ge 0,
\qquad
\int_{\mathbb R^n}\rho(x)d^nx=1.
$$

The density $\rho$ is not the measure itself. It is the measure written relative to the chosen reference measure $d^nx$. Under a change of variables, the density and the Jacobian change together so that the measure remains invariant.

## Random variables and laws

A random variable is a measurable map

$$
X:\Omega\to E.
$$

The set $E$ is the value space. It might be $\mathbb R$, $\mathbb R^n$, a lattice spin set, a space of matrices, or a space of field configurations.

The law of $X$ is the probability measure $\mu_X$ on $E$ defined by

$$
\mu_X(B)=\mathbb P(X^{-1}(B)).
$$

This is the pushforward measure

$$
\mu_X=X_*\mathbb P.
$$

The expectation of a function $f:E\to\mathbb R$ or $\mathbb C$ is

$$
\mathbb E[f(X)]
=\int_\Omega f(X(\omega))d\mathbb P(\omega)
=\int_E f(x)d\mu_X(x).
$$

This formula is the whole reason laws are useful. Once you know $\mu_X$, you can compute every expectation involving $X$ alone without remembering the underlying sample space.

In QFT, one usually suppresses $\Omega$ entirely. A Euclidean field $\phi$ is treated as the configuration itself, and the path-integral measure is written directly as $d\mu(\phi)$.

## Expectation as a linear functional

Expectation is a positive normalized linear functional. For integrable observables $A$ and $B$,

$$
\mathbb E[\alpha A+\beta B]
=\alpha\mathbb E[A]+\beta\mathbb E[B].
$$

If $A\ge 0$, then

$$
\mathbb E[A]\ge 0.
$$

Finally,

$$
\mathbb E[1]=1.
$$

This abstract formulation is useful because QFT often starts from expectation values rather than from an explicit measure. A state in algebraic QFT, for instance, is a positive normalized linear functional on an algebra of observables. In Euclidean constructive field theory, one seeks a probability measure whose moments reproduce Schwinger functions.

The QFT analog of positivity is subtle. Euclidean reflection positivity is not the same as pointwise positivity of every expression, but it is the condition that allows reconstruction of a Hilbert space with positive norm.

## Moments

For a real random variable $X$, the $n$th moment is

$$
m_n=\mathbb E[X^n],
$$

when the integral exists. The mean and variance are

$$
\mu=\mathbb E[X],
$$

and

$$
\operatorname{Var}(X)=\mathbb E[(X-\mu)^2].
$$

For two random variables $X,Y$, the covariance is

$$
\operatorname{Cov}(X,Y)
=\mathbb E[(X-\mathbb E X)(Y-\mathbb E Y)].
$$

For a random vector $X^i$, the covariance matrix is

$$
C^{ij}
=\mathbb E[(X^i-\mu^i)(X^j-\mu^j)].
$$

In QFT, the analog is the connected two-point function

$$
G_c(x,y)
=\langle \phi(x)\phi(y)\rangle
-\langle\phi(x)\rangle\langle\phi(y)\rangle.
$$

When the field has zero expectation value, this is just the two-point function.

## Generating functions

The moment-generating function is

$$
M(J)=\mathbb E[e^{JX}],
$$

when it exists near $J=0$. Its derivatives give moments:

$$
\left.\frac{d^nM}{dJ^n}\right|_{J=0}
=\mathbb E[X^n].
$$

For a random vector,

$$
M(J)=\mathbb E[e^{J_iX^i}],
$$

and

$$
\left.\frac{\partial^n M}
{\partial J_{i_1}\cdots\partial J_{i_n}}\right|_{J=0}
=\mathbb E[X^{i_1}\cdots X^{i_n}].
$$

The cumulant-generating function is

$$
K(J)=\log M(J).
$$

Its derivatives give cumulants. In QFT notation, the corresponding objects are

$$
Z[J]=\left\langle e^{\int J\phi}\right\rangle,
\qquad
W[J]=\log Z[J].
$$

The derivatives of $Z[J]$ give all correlators; derivatives of $W[J]$ give connected correlators.

## Characteristic functions

The characteristic function is the Fourier transform of the probability measure:

$$
\varphi(k)=\mathbb E[e^{ikX}].
$$

For a probability measure $\mu$ on $\mathbb R^n$,

$$
\varphi(k)=\int_{\mathbb R^n}e^{ik\cdot x}d\mu(x).
$$

Characteristic functions always exist because $|e^{ikX}|=1$. Moment-generating functions may fail to exist if the distribution has heavy tails.

This is one reason Fourier transforms are so natural in probability theory. The distribution of a sum of independent variables is a convolution, and Fourier transforms turn convolution into multiplication.

If $X$ and $Y$ are independent, then

$$
\varphi_{X+Y}(k)=\varphi_X(k)\varphi_Y(k).
$$

The central limit theorem is, at heart, a statement about how repeated multiplication of characteristic functions approaches a Gaussian.

## Independence and product measures

Two random variables $X$ and $Y$ are independent if

$$
\mathbb P(X\in A,\;Y\in B)
=\mathbb P(X\in A)\mathbb P(Y\in B)
$$

for all measurable $A,B$. Equivalently, their joint law factorizes:

$$
\mu_{X,Y}=\mu_X\otimes \mu_Y.
$$

For independent variables,

$$
\mathbb E[f(X)g(Y)]
=\mathbb E[f(X)]\mathbb E[g(Y)].
$$

In field theory, exact factorization is rare for local observables in an interacting state. But locality often implies approximate factorization at long distances in a gapped theory:

$$
\langle \mathcal O_1(x)\mathcal O_2(y)\rangle
-\langle \mathcal O_1(x)\rangle\langle \mathcal O_2(y)\rangle
\to 0
$$

as $|x-y|\to\infty$, with a rate determined by the mass gap or by power laws at criticality.

This is cluster decomposition, not literal independence of microscopic field variables.

## Conditional probability

For events $A$ and $B$ with $\mathbb P(B)>0$,

$$
\mathbb P(A|B)=\frac{\mathbb P(A\cap B)}{\mathbb P(B)}.
$$

For random variables, conditioning is encoded by conditional expectation. The conditional expectation $\mathbb E[X|\mathcal G]$ is the best $\mathcal G$-measurable approximation to $X$, characterized by

$$
\int_G \mathbb E[X|\mathcal G]d\mathbb P
=
\int_G Xd\mathbb P
$$

for all $G\in\mathcal G$.

In physics language, conditioning is what happens when you fix partial information and average over the rest. In path integrals, this appears when imposing boundary data, inserting delta-function constraints, or integrating out high-energy modes while holding low-energy modes fixed.

A Wilsonian effective action can be read as a sophisticated conditional or marginal construction:

$$
e^{-S_{\mathrm{eff}}[\phi_<]}
=\int \mathcal D\phi_>\,e^{-S[\phi_<+\phi_>]}.
$$

This formula is schematic, but the probability idea is sharp: integrate over variables you no longer observe to obtain a measure for the variables you keep.

## Marginals

If $(X,Y)$ has joint law $\mu_{X,Y}$, the marginal law of $X$ is obtained by integrating over $Y$:

$$
\mu_X(A)=\mu_{X,Y}(A\times E_Y).
$$

With a density,

$$
\rho_X(x)=\int dy\,\rho_{X,Y}(x,y).
$$

Marginalization is the probability ancestor of “integrating out” degrees of freedom. The difference is that in QFT the result is usually not just another simple probability density. It may be nonlocal, regulator-dependent, or expressible only through an effective action with infinitely many terms.

## Changes of variables

Suppose $X$ has density $\rho_X(x)$ and $Y=f(X)$, where $f:\mathbb R^n\to\mathbb R^n$ is invertible and smooth. Then

$$
\rho_Y(y)
=
\rho_X(f^{-1}(y))
\left|\det\frac{\partial f^{-1}}{\partial y}\right|.
$$

Equivalently,

$$
\rho_X(x)d^nx=\rho_Y(y)d^ny.
$$

The invariant object is the measure, not the density.

This is the same Jacobian logic that appears in path integrals. If fields are redefined,

$$
\phi\mapsto \phi',
$$

the formal measure may acquire a functional determinant. In finite dimensions the formula is elementary; in infinite dimensions it can encode anomalies or require regularization.

## Weak convergence

A sequence of probability measures $\mu_n$ on a topological space converges weakly to $\mu$ if

$$
\int f\,d\mu_n\to \int f\,d\mu
$$

for every bounded continuous test function $f$.

This is often the right notion of convergence for continuum limits. A lattice field theory does not need pointwise convergence of every microscopic variable. It needs convergence of distributions of observables, correlation functions, or smeared fields.

In probability notation,

$$
X_n\Rightarrow X
$$

means the laws of $X_n$ converge weakly to the law of $X$.

The central limit theorem is the model example:

$$
\frac{X_1+\cdots+X_N-N\mu}{\sqrt N}
\Rightarrow \mathcal N(0,\sigma^2)
$$

under standard hypotheses. In QFT, scaling limits of lattice models are vastly richer versions of the same theme: rescale observables and ask for convergence of correlation functions to a continuum field theory.

## Measures on function spaces

For a stochastic process or Euclidean field, the random variable may take values in a function or distribution space. For example, Brownian motion is described by a probability measure on paths

$$
x:[0,T]\to\mathbb R^d.
$$

A free Euclidean scalar field is described, after appropriate construction, by a Gaussian measure whose covariance is the Green function of an elliptic operator. Formally,

$$
d\mu(\phi)\propto
\exp\!\left[-\frac12\int d^dx\,\phi(x)K\phi(x)\right]\mathcal D\phi,
$$

with covariance

$$
K^{-1}=G.
$$

The word “formally” matters. In dimensions $d\ge 2$, the Gaussian free field is typically a random distribution, not a pointwise-defined random function. Products such as $\phi(x)^4$ require renormalization before they define interacting measures.

## Euclidean QFT as probability, carefully

When the Euclidean measure exists, Schwinger functions are expectations:

$$
S_n(x_1,\ldots,x_n)
=\int \phi(x_1)\cdots \phi(x_n)d\mu(\phi).
$$

To reconstruct a Lorentzian QFT, these Schwinger functions must satisfy additional conditions, including Euclidean invariance, symmetry, regularity, clustering, and reflection positivity.

Reflection positivity is the probability-like condition that remembers Hilbert-space positivity after Wick rotation. It is not automatic for every classical-looking statistical measure.

Gauge theories add another layer. The naive space of gauge fields includes physically redundant configurations. One may work with gauge-invariant observables, fix a gauge and include determinants, or formulate the theory on a quotient. The probability measure lives on the physical or gauge-fixed structure, not naively on all vector potentials with equal meaning.

## Discrete example: Ising spins

For $N$ Ising spins $\sigma_i=\pm 1$, a configuration is

$$
\sigma=(\sigma_1,\ldots,\sigma_N)\in\{\pm1\}^N.
$$

A Gibbs measure has the form

$$
\mathbb P(\sigma)=\frac{1}{Z}e^{-\beta H(\sigma)},
$$

where

$$
Z=\sum_{\sigma\in\{\pm1\}^N}e^{-\beta H(\sigma)}.
$$

The expectation of an observable $A(\sigma)$ is

$$
\langle A\rangle
=\sum_\sigma A(\sigma)\mathbb P(\sigma).
$$

This is an honest finite probability measure. The continuum field theory appears only after taking a thermodynamic and scaling limit near criticality. That limit is the hard part.

## Continuous example: one Gaussian variable

Let

$$
d\mu(x)=\sqrt{\frac{a}{2\pi}}e^{-\frac12 ax^2}dx,
\qquad
a>0.
$$

Then

$$
\mathbb E[x]=0,
\qquad
\mathbb E[x^2]=\frac1a.
$$

The generating function is

$$
Z(J)=\int dx\,\sqrt{\frac{a}{2\pi}}
\exp\!\left(-\frac12 ax^2+Jx\right)
=\exp\!\left(\frac{J^2}{2a}\right).
$$

This finite-dimensional formula is the prototype of the free Euclidean field generating functional. The number $a^{-1}$ becomes the propagator.

## Common pitfalls

### Calling every weight a probability

A probability measure must be positive and normalized. Complex weights, signed measures, Grassmann integrals, and gauge-fixed expressions may imitate probability formulas without being probabilities.

### Confusing a density with a measure

The expression $\rho(x)$ depends on the reference measure $dx$. The measure $\rho(x)dx$ is the coordinate-invariant object. This distinction prevents many Jacobian mistakes.

### Treating fields as pointwise random variables too early

Continuum quantum fields and Gaussian free fields are often distributions. Smeared fields

$$
\phi(f)=\int d^dx\,\phi(x)f(x)
$$

are usually better-defined than $\phi(x)$ itself.

### Assuming moments determine everything

Moments often characterize common distributions, especially Gaussians under good hypotheses, but moment problems can be subtle. In QFT, formal moment expansions may fail to define a unique measure without additional analytic control.

### Ignoring normalization

The partition function $Z$ is not decorative. Without it, expectation values are not normalized:

$$
\langle 1\rangle=1.
$$

When $Z$ diverges or vanishes formally, the measure needs regularization, renormalization, or reinterpretation.

## Exercises

### Exercise 1: Pushforward of a two-point space

Let $\Omega=\{a,b\}$ with $\mathbb P(a)=p$ and $\mathbb P(b)=1-p$. Define $X(a)=1$ and $X(b)=-1$. Find the law of $X$, its mean, and its variance.

<details><summary><strong>Solution</strong></summary>

The law is

$$
\mu_X=p\,\delta_1+(1-p)\,\delta_{-1}.
$$

The mean is

$$
\mathbb E[X]=p-(1-p)=2p-1.
$$

Since $X^2=1$,

$$
\operatorname{Var}(X)
=\mathbb E[X^2]-\mathbb E[X]^2
=1-(2p-1)^2
=4p(1-p).
$$

</details>

### Exercise 2: Gaussian generating function

Evaluate

$$
Z(J)=\int_{-\infty}^{\infty} dx\,
\sqrt{\frac{a}{2\pi}}
\exp\!\left(-\frac12 ax^2+Jx\right)
$$

for $a>0$.

<details><summary><strong>Solution</strong></summary>

Complete the square:

$$
-\frac12 ax^2+Jx
=
-\frac12 a\left(x-\frac{J}{a}\right)^2+\frac{J^2}{2a}.
$$

The shifted Gaussian integrates to $1$ with the chosen normalization. Therefore

$$
Z(J)=\exp\!\left(\frac{J^2}{2a}\right).
$$

Differentiating gives

$$
\mathbb E[X]=0,
\qquad
\mathbb E[X^2]=\left.\frac{d^2Z}{dJ^2}\right|_{J=0}=\frac1a.
$$

</details>

### Exercise 3: Marginal of a two-variable Gaussian

Let $(X,Y)$ have density

$$
\rho(x,y)=\frac{ab}{2\pi}
\exp\!\left[-\frac12(a^2x^2+b^2y^2)\right],
$$

with $a,b>0$. Find the marginal density of $X$.

<details><summary><strong>Solution</strong></summary>

Integrate out $y$:

$$
\rho_X(x)
=\int_{-\infty}^{\infty}dy\,\rho(x,y)
=
\frac{ab}{2\pi}e^{-\frac12a^2x^2}
\int_{-\infty}^{\infty}dy\,e^{-\frac12b^2y^2}.
$$

The Gaussian integral is

$$
\int dy\,e^{-\frac12b^2y^2}
=\frac{\sqrt{2\pi}}{b}.
$$

Thus

$$
\rho_X(x)
=
\frac{a}{\sqrt{2\pi}}e^{-\frac12a^2x^2}.
$$

So $X$ is Gaussian with variance $1/a^2$.

</details>

### Exercise 4: Connected two-point function

Let $X,Y$ be random variables. Show that

$$
\frac{\partial^2}{\partial J_X\partial J_Y}
\log \mathbb E[e^{J_XX+J_YY}]
\bigg|_{J_X=J_Y=0}
=
\mathbb E[XY]-\mathbb E[X]\mathbb E[Y].
$$

<details><summary><strong>Solution</strong></summary>

Let

$$
M(J_X,J_Y)=\mathbb E[e^{J_XX+J_YY}],
\qquad
K=\log M.
$$

Then

$$
\partial_X\partial_Y K
=
\frac{\partial_X\partial_Y M}{M}
-\frac{(\partial_X M)(\partial_Y M)}{M^2}.
$$

At $J_X=J_Y=0$, $M=1$,

$$
\partial_X M|_0=\mathbb E[X],
\qquad
\partial_Y M|_0=\mathbb E[Y],
$$

and

$$
\partial_X\partial_Y M|_0=\mathbb E[XY].
$$

Therefore

$$
\partial_X\partial_Y K|_0
=
\mathbb E[XY]-\mathbb E[X]\mathbb E[Y].
$$

This is the covariance, and in QFT language it is the connected two-point function.

</details>

## References

- Billingsley, *Probability and Measure*.
- Kallenberg, *Foundations of Modern Probability*.
- Feller, *An Introduction to Probability Theory and Its Applications*.
- Simon, *Functional Integration and Quantum Physics*.
- Glimm and Jaffe, *Quantum Physics: A Functional Integral Point of View*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Altland and Simons, *Condensed Matter Field Theory*.

## Version history

- **2026-06-27:** First polished draft. Introduces probability spaces, laws, expectations, moments, generating functions, independence, conditioning, marginals, weak convergence, function-space measures, and Euclidean QFT analogies.
