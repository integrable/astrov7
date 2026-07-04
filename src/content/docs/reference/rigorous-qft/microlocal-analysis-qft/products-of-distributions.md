---
title: "Products of Distributions"
description: "Explains Hörmander's wavefront-set criterion for multiplying distributions and why it is the local test behind Wick products and perturbative renormalization."
sidebar:
  label: "Products of Distributions"
  order: 2
level: Advanced
status: "Polished draft"
source: "Hörmander; Duistermaat–Hörmander; Brunetti–Fredenhagen; pAQFT literature."
topics:
  - distributions
  - wavefront sets
  - singular products
  - Wick products
  - Epstein–Glaser renormalization
canonicalTopics:
  - product-of-distributions
  - wavefront-set-criterion
  - microlocal-analysis
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "Hörmander's wavefront-set criterion gives a standard coordinate-invariant sufficient condition for multiplying distributions."
    - "In perturbative QFT, failures of this criterion at coincident points are the local analytic core of ultraviolet renormalization."
  active:
    - "Gauge theory, boundaries, non-globally-hyperbolic backgrounds, and nonlocal observables require additional hypotheses beyond the basic product criterion."
---

## Summary

A product of distributions is not automatically defined. A distribution may be paired with a test function, and a smooth function may multiply a distribution, but multiplying two singular distributions requires a compatibility condition on their singular directions.

Let $u,v\in \mathcal D'(X)$ be distributions on a smooth manifold $X$. The basic microlocal product criterion is

$$
\nexists\,(x,\xi)\in \operatorname{WF}(u)
\quad\text{with}\quad
(x,-\xi)\in \operatorname{WF}(v)
\quad\Longrightarrow\quad
uv\in\mathcal D'(X)\text{ is defined}.
$$

Equivalently, at no point may the wavefront cone of one factor contain a covector opposite to a singular covector of the other factor. This is the distributional version of the physics warning: two singular factors can sometimes be multiplied, but only when their high-frequency singularities do not collide head-on.

In QFT this criterion is everywhere. It explains why fields must be smeared, why composite fields require Wick ordering, why time-ordered products are first defined away from diagonals, and why renormalization can be viewed as an extension problem for distributions.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Wavefront-set criterion for products of distributions](/figures/rigorous-qft/products-of-distributions-criterion.svg)

<figcaption>

The product $uv$ is safe when the singular covectors of $u$ and $v$ at the same point cannot sum to zero. Opposite singular directions are the microlocal obstruction. The diagonal pullback formulation makes this criterion coordinate invariant.

</figcaption>
</figure>

## Prerequisites

Read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) first. You should also know why fields are distributional from [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and how renormalization appears as distribution extension in [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/).

The page uses the convention that $T^*X\setminus 0$ means the cotangent bundle with the zero section removed.

## Core idea

The ordinary singular support of a distribution is too crude for multiplication. It tells us where a distribution is singular, but not how it is singular. Wavefront sets add the missing directional information.

The reason direction matters is Fourier convolution. Locally, the Fourier transform of a product behaves like a convolution of Fourier transforms. If the high-frequency singular directions of $u$ and $v$ can cancel, then the convolution may produce uncontrolled high-frequency behavior even after testing against a smooth function. If the bad directions cannot cancel, the product is well defined.

The slogan is

$$
\text{singularities may multiply if their covectors do not add to zero}.
$$

This is why the sign in the criterion matters. Having two singularities at the same point is not by itself fatal. The fatal event is an opposite pair of cotangent directions.

## Setup and conventions

Let $X$ be a smooth manifold and let $u,v\in\mathcal D'(X)$. The product $uv$, when it exists, is a distribution satisfying

$$
\langle uv,f\rangle
=
\lim_{j\to\infty}\int_X u_j(x)v_j(x)f(x)\,dx
$$

for any regularizing sequence $u_j\to u$, $v_j\to v$ compatible with the construction. This formula is not the definition one should use in full generality, but it captures the intended object: a canonical limit independent of the chosen smoothing.

The invariant way to define the product is through the diagonal map

$$
\Delta:X\longrightarrow X\times X,
\qquad
\Delta(x)=(x,x).
$$

First form the tensor product distribution $u\boxtimes v$ on $X\times X$. Then define

$$
uv=\Delta^*(u\boxtimes v),
$$

provided that the pullback exists.

The conormal bundle of the diagonal is

$$
N^*\Delta
=
\{(x,\xi;x,-\xi):x\in X,\ \xi\in T_x^*X\}.
$$

The pullback criterion says that $\Delta^*(u\boxtimes v)$ exists if

$$
\operatorname{WF}(u\boxtimes v)\cap N^*\Delta=\varnothing.
$$

Using the standard estimate for the wavefront set of a tensor product, this becomes the practical criterion

$$
\operatorname{WF}(u)\oplus\operatorname{WF}(v)
\not\ni (x,0)
\quad\text{for every }x\in X,
$$

where

$$
\operatorname{WF}(u)\oplus\operatorname{WF}(v)
=
\{(x,\xi+\eta):(x,\xi)\in\operatorname{WF}(u),
(x,\eta)\in\operatorname{WF}(v)\}.
$$

Equivalently, there is no $(x,\xi)\in\operatorname{WF}(u)$ and $(x,-\xi)\in\operatorname{WF}(v)$.

## The product theorem

**Theorem.** If

$$
\{(x,\xi):(x,\xi)\in\operatorname{WF}(u)
\text{ and }(x,-\xi)\in\operatorname{WF}(v)\}=\varnothing,
$$

then there is a canonical distribution $uv\in\mathcal D'(X)$ extending pointwise multiplication on smooth functions. Moreover,

$$
\operatorname{WF}(uv)
\subset
\operatorname{WF}(u)
\cup
\operatorname{WF}(v)
\cup
\bigl(\operatorname{WF}(u)\oplus\operatorname{WF}(v)\bigr).
$$

This theorem is local. It can be checked in coordinate charts and then patched invariantly. It is also stable under multiplication by smooth functions: if $a\in C^\infty(X)$, then $au$ is always defined and

$$
\operatorname{WF}(au)\subset\operatorname{WF}(u).
$$

The criterion is sufficient and, in the right sense, sharp. If it fails, the product may still be defined by extra structure, symmetry, boundary values, or a chosen renormalization prescription, but it is no longer a canonical product forced by distribution theory alone.

:::caution[Failure is not the same as impossibility]
When the criterion fails, distribution theory is saying: no canonical product follows from the two distributions alone. A particular regularization may still assign a value. Such an assignment is extra data and must be tracked as a convention or renormalization choice.
:::

## Basic examples

A smooth factor is harmless. If $a\in C^\infty(X)$ and $u\in\mathcal D'(X)$, then $au$ is defined. This is why test functions can smear fields and why coefficients in a differential operator can multiply distributions.

The square of a delta function is not canonically defined. On $\mathbb R$,

$$
\operatorname{WF}(\delta_0)
=
\{(0,\xi):\xi\ne0\}.
$$

For every nonzero $\xi$, both $(0,\xi)$ and $(0,-\xi)$ occur. Hence $\delta_0^2$ fails the criterion.

Delta functions at different points multiply without trouble. If $a\ne b$, then $\delta_a\delta_b$ is the zero distribution because the singular base points do not coincide. The wavefront obstruction is local in the base point.

A one-sided singular direction can multiply another singularity with the same orientation. For example, boundary-value distributions whose wavefront sets at a point contain only positive covectors can often be multiplied with each other. The obstruction requires opposite directions.

The Heaviside function times a delta function is not canonical from this criterion alone. One often sees assignments such as $H\delta=\frac12\delta$ in physics or engineering. Such formulas depend on a symmetric regularization or a convention; they are not consequences of ordinary distribution multiplication.

## Why QFT cares

Quantum fields are operator-valued distributions. Even before interactions, pointwise products such as $\phi(x)^2$ are not literal products of operators at a point. The problem has two layers:

1. fields are unbounded operator-valued distributions, so their operator domains matter;
2. their correlation functions are scalar distributions, and products of those distributions can fail microlocally.

Microlocal analysis addresses the second layer. If every matrix element or $n$-point distribution has wavefront sets compatible with the relevant product, then the distributional product can be defined before addressing operator-domain questions.

For Wick products, one subtracts a universal singular part before taking a coincident-point limit. In a free scalar theory, the informal formula

$$
:\!\phi^2\!:(x)
=\lim_{y\to x}\bigl(\phi(x)\phi(y)-\omega_2(x,y)\bigr)
$$

is a shorthand for a distributional extension problem. The subtraction removes the singular part whose wavefront behavior blocks the diagonal restriction.

For time-ordered products, the first construction is away from coincident points. On the configuration space

$$
M^n\setminus\{\text{partial diagonals}\},
$$

the causal order of the points separates factors. Renormalization is the problem of extending the resulting distribution to the diagonals while preserving locality, covariance, scaling, causal factorization, and symmetry requirements.

Thus in perturbative algebraic QFT and Epstein–Glaser renormalization, ultraviolet divergences are not primarily infinite integrals. They are obstructions to extending singular distributions from the complement of diagonals to all of configuration space.

## Products, pullbacks, and restrictions

Restriction to a submanifold is a special case of pullback. Let $i:Y\hookrightarrow X$ be an embedded submanifold. The restriction $i^*u$ exists if

$$
\operatorname{WF}(u)\cap N^*Y=\varnothing,
$$

where $N^*Y$ is the conormal bundle of $Y$. The product is exactly this idea applied to the diagonal.

This perspective is useful in QFT because coincident-point limits are restrictions to diagonals. A singular two-point function $G(x,y)$ may be perfectly good as a distribution on $X\times X$, but the expression $G(x,x)$ asks for the pullback by the diagonal. The conormal test determines whether that restriction is canonical.

For Feynman propagators, products are typically well defined away from diagonals and require extension at diagonals. The freedom in extension is the local counterterm freedom. The scaling degree controls how many derivatives of delta functions can appear in the ambiguity.

## Checks

**Locality check.** The criterion only compares wavefront cones over the same base point. Singularities at different points do not obstruct multiplication.

**Smooth-factor check.** Since $\operatorname{WF}(a)=\varnothing$ for $a\in C^\infty(X)$, the product $au$ always passes the test.

**Delta-square check.** Since $\operatorname{WF}(\delta_0)$ contains all nonzero covectors over $0$, it contains opposite pairs and $\delta_0^2$ fails.

**Diagonal check.** If a distribution $T$ on $X\times X$ has wavefront set meeting $N^*\Delta$, then its restriction $T(x,x)$ is not canonical. This is the geometric version of coincident-point singularity.

## Common pitfalls

**Thinking support is enough.** Disjoint singular supports are sufficient for products to be easy, but not necessary. Wavefront directions can allow multiplication even when singular supports meet.

**Treating failed criteria as zero.** If the criterion fails, the product is not automatically zero. It is undefined without extra data.

**Forgetting the zero covector is excluded.** Wavefront sets live in $T^*X\setminus0$. The obstruction is that the sum of two nonzero singular covectors can be zero.

**Assuming every regularization gives the same answer.** When a canonical product exists, reasonable regularizations agree. When the criterion fails, different regularizations can differ by local terms.

**Confusing ordinary multiplication with renormalized multiplication.** Wick products and time-ordered products are not naive products. They are renormalized operations satisfying additional axioms.

**Ignoring operator domains.** Microlocal compatibility of scalar distributions does not by itself solve all operator-theoretic domain questions for operator-valued distributions.

## Relations to other pages

- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) defines the directional singular support used here.
- [Microlocal Spectrum Condition](/rigorous-qft/microlocal-analysis-qft/microlocal-spectrum-condition/) explains the QFT positivity condition that makes many products possible in curved spacetime.
- [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) explains how renormalization extends distributions across diagonals.
- [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/) uses this criterion to motivate why time ordering must be constructed rather than assumed.
- [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) records the universal wavefront behavior of physically acceptable free states on curved spacetime.

## Research status

The product criterion is settled mathematical analysis. Its use in QFT on globally hyperbolic spacetimes is also a standard part of perturbative algebraic QFT and the microlocal approach to Hadamard states.

The active work is not the basic criterion, but its deployment in harder settings: gauge theories with constraints and ghosts, theories with boundaries, non-globally-hyperbolic backgrounds, defects and extended observables, nonlocal algebras, and nonperturbative constructions. In those settings one often needs extra geometric, algebraic, or functional-analytic input in addition to the wavefront-set test.

## Exercises

### Exercise 1: Delta functions at different points

Let $a,b\in\mathbb R$ with $a\ne b$. Explain why $\delta_a\delta_b$ is canonically defined and equal to zero.

<details>
<summary><strong>Solution</strong></summary>

The singular support of $\delta_a$ is $\{a\}$ and the singular support of $\delta_b$ is $\{b\}$. Since $a\ne b$, there is no base point at which singular covectors from both factors occur. A test function supported near $a$ sees only $\delta_a$ and a zero contribution from $\delta_b$, while a test function supported near $b$ sees the reverse. Thus the product is the zero distribution. Equivalently, the wavefront obstruction requires the same base point, and there is none.

</details>

### Exercise 2: Why delta squared fails

Use the wavefront set

$$
\operatorname{WF}(\delta_0)=\{(0,\xi):\xi\ne0\}
$$

to show that $\delta_0^2$ fails Hörmander's product criterion.

<details>
<summary><strong>Solution</strong></summary>

Take any nonzero $\xi$. Then $(0,\xi)\in\operatorname{WF}(\delta_0)$ and also $(0,-\xi)\in\operatorname{WF}(\delta_0)$. Therefore the forbidden opposite pair occurs at the same base point. The criterion does not define $\delta_0^2$.

</details>

### Exercise 3: Same cone, safe product

Suppose $u,v\in\mathcal D'(\mathbb R)$ satisfy

$$
\operatorname{WF}(u),\operatorname{WF}(v)
\subset\{(0,\xi):\xi>0\}.
$$

Does the product criterion allow $uv$?

<details>
<summary><strong>Solution</strong></summary>

Yes. If $(0,\xi)$ occurs in either wavefront set, then $\xi>0$. The opposite covector $(0,-\xi)$ has negative fiber coordinate and does not lie in either cone. Hence no forbidden opposite pair exists. The product is defined by the criterion.

</details>

### Exercise 4: Product as diagonal pullback

Show that the condition

$$
\operatorname{WF}(u\boxtimes v)\cap N^*\Delta=\varnothing
$$

reduces to the no-opposite-covector criterion for $u$ and $v$.

<details>
<summary><strong>Solution</strong></summary>

The conormal bundle of the diagonal consists of covectors of the form $(x,\xi;x,-\xi)$. The tensor product $u\boxtimes v$ can have singular covectors with first component from $\operatorname{WF}(u)$ and second component from $\operatorname{WF}(v)$, together with zero components allowed when the other factor is singular. The intersection with $N^*\Delta$ can occur precisely when $(x,\xi)\in\operatorname{WF}(u)$ and $(x,-\xi)\in\operatorname{WF}(v)$ for some nonzero $\xi$. Excluding this is exactly the product criterion.

</details>

## References

### Standard first pass

- Lars Hörmander, *The Analysis of Linear Partial Differential Operators I: Distribution Theory and Fourier Analysis*, for wavefront sets, products, and pullbacks of distributions.
- Michael E. Taylor, *Partial Differential Equations I: Basic Theory*, for a readable PDE-oriented path into wavefront sets and distribution operations.
- Kasia Rejzner, *Perturbative Algebraic Quantum Field Theory*, for the use of microlocal analysis in pAQFT and renormalized products.

### Deeper references

- J. J. Duistermaat and L. Hörmander, "Fourier Integral Operators. II," *Acta Mathematica* **128** (1972), 183–269. [DOI: 10.1007/BF02392165](https://doi.org/10.1007/BF02392165).
- Romeo Brunetti and Klaus Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [DOI: 10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- Stefan Hollands and Robert M. Wald, "Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [DOI: 10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).

## Version history

- **2026-07-01:** Initial page on the microlocal product criterion and its QFT role.
