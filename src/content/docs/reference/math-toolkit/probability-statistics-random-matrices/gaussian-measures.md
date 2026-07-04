---
title: "Gaussian Measures"
description: "A QFT-oriented guide to Gaussian probability measures, covariance operators, characteristic functionals, Wick’s theorem, and the free Euclidean field."
sidebar:
  label: "Gaussian Measures"
  order: 2
level: Graduate
status: "Polished draft"
source: "Measure-theoretic probability, Gaussian integration, Euclidean free fields, Wick’s theorem, and constructive-field-theory caveats."
topics:
  - Gaussian measures
  - covariance operators
  - characteristic functionals
  - Wick theorem
  - Gaussian free field
  - Euclidean QFT
  - random distributions
canonicalTopics:
  - gaussian-measure
  - covariance-operator
  - characteristic-functional
  - wick-theorem
  - gaussian-free-field
researchStatus:
  established:
    - "Finite-dimensional Gaussian measures, Gaussian characteristic functionals, covariance operators, and Wick factorization are standard tools in probability, statistical mechanics, and free Euclidean QFT."
  active:
    - "The construction and renormalized perturbation of continuum interacting measures, especially in gauge theories and singular stochastic field theories, remains subtle and often research-level."
---

## Summary

A Gaussian measure is the probability measure whose entire content is fixed by its mean and covariance. In finite dimensions, the centered nondegenerate Gaussian on $\mathbb R^n$ with covariance matrix $C$ is

$$
d\mu_C(x)
=(2\pi)^{-n/2}(\det C)^{-1/2}
\exp\!\left(-\frac12 x^i(C^{-1})_{ij}x^j\right)d^nx.
$$

Its generating function is

$$
\mathbb E_C[e^{J_ix^i}]
=\exp\!\left(\frac12 J_iC^{ij}J_j\right).
$$

This single formula is the finite-dimensional ancestor of the free Euclidean field:

$$
Z_0[J]
=Z_0[0]
\exp\!\left(\frac12\int d^dx\,d^dy\,J(x)G(x,y)J(y)\right),
$$

where $G=K^{-1}$ is the Green function of the quadratic kinetic operator $K$.

The physics slogan is:

$$
\text{free Euclidean fields are Gaussian random distributions.}
$$

The word **distributions** is not academic fussing. In continuum QFT, $\phi(x)$ often is not a pointwise random variable; the smeared field $\phi(f)$ is the honest Gaussian random variable.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A flowchart showing quadratic action, covariance inverse, Gaussian measure, generating functional, and Wick contractions.](/figures/math-toolkit/gaussian-measure-covariance-flow.svg)

<figcaption>

A Gaussian measure is controlled by a covariance. In free Euclidean QFT, the quadratic operator $K$ defines the covariance $G=K^{-1}$, the generating functional is exponential and quadratic in $J$, and all higher correlators reduce to pairings.

</figcaption>
</figure>

## Prerequisites

You should first know the language of [Probability Measures](/math-toolkit/probability-statistics-random-matrices/probability-measures/), especially expectation, laws, pushforwards, and generating functions. It also helps to know finite-dimensional Gaussian integrals from [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/).

For the continuum parts, you should be comfortable with [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/). The page uses Euclidean signature for probabilistic statements. Lorentzian Gaussian path integrals are oscillatory analogs, not probability measures.

## The one-dimensional model

The simplest centered Gaussian is

$$
d\mu_a(x)=\sqrt{\frac{a}{2\pi}}e^{-\frac12 ax^2}\,dx,
\qquad a>0.
$$

The variance is

$$
\mathbb E_a[x^2]=\frac1a.
$$

The generating function is obtained by completing the square:

$$
Z(J)=\int_{-\infty}^{\infty}d\mu_a(x)\,e^{Jx}
=\exp\!\left(\frac{J^2}{2a}\right).
$$

Differentiating gives all moments:

$$
\mathbb E_a[x^n]
=\left.\frac{d^n}{dJ^n}Z(J)\right|_{J=0}.
$$

In particular, all odd moments vanish and

$$
\mathbb E_a[x^{2m}]
=(2m-1)!!\,a^{-m}.
$$

That double factorial counts pairings. This is already Wick’s theorem in baby form.

## Multivariate Gaussians

Let $C$ be a real, symmetric, positive-definite $n\times n$ matrix. The centered Gaussian measure with covariance $C$ is

$$
d\mu_C(x)
=(2\pi)^{-n/2}(\det C)^{-1/2}
\exp\!\left(-\frac12 x^TC^{-1}x\right)d^nx.
$$

In index notation,

$$
x^TC^{-1}x=x^i(C^{-1})_{ij}x^j.
$$

The normalization is chosen so that

$$
\int_{\mathbb R^n}d\mu_C(x)=1.
$$

The covariance is

$$
\mathbb E_C[x^ix^j]=C^{ij}.
$$

The generating function is

$$
Z_C(J)=\mathbb E_C[e^{J_ix^i}]
=\exp\!\left(\frac12J_iC^{ij}J_j\right).
$$

This formula is the most efficient definition of a centered Gaussian. If a random vector has this generating function near $J=0$, then it is Gaussian with covariance $C$.

For a nonzero mean $m^i$, the measure is shifted:

$$
d\mu_{m,C}(x)
=(2\pi)^{-n/2}(\det C)^{-1/2}
\exp\!\left[-\frac12(x-m)^i(C^{-1})_{ij}(x-m)^j\right]d^nx,
$$

and

$$
\mathbb E_{m,C}[e^{J_ix^i}]
=\exp\!\left(J_im^i+\frac12J_iC^{ij}J_j\right).
$$

A Gaussian is therefore completely specified by the pair

$$
(m,C).
$$

## Covariance is the inverse quadratic form

In finite-dimensional QFT-style notation, write the action as

$$
S(x)=\frac12x^iK_{ij}x^j,
$$

where $K$ is symmetric and positive definite. Then the probability measure is

$$
d\mu_K(x)
=\frac1Z e^{-\frac12x^iK_{ij}x^j}d^nx,
$$

with

$$
Z=(2\pi)^{n/2}(\det K)^{-1/2}.
$$

The covariance is the inverse matrix:

$$
C^{ij}=(K^{-1})^{ij}.
$$

So there are two dual pieces of data:

| Object | Role |
|---|---|
| $K$ | precision matrix, kinetic operator, inverse propagator |
| $C=K^{-1}$ | covariance matrix, Green function, propagator |

This is the finite-dimensional reason free QFT propagators are inverses of kinetic operators.

## Wick’s theorem

For a centered Gaussian, every odd moment vanishes:

$$
\mathbb E_C[x^{i_1}\cdots x^{i_{2m+1}}]=0.
$$

Every even moment is a sum over pairings:

$$
\mathbb E_C[x^{i_1}\cdots x^{i_{2m}}]
=
\sum_{\text{pairings }P}
\prod_{(a,b)\in P}C^{i_ai_b}.
$$

For four variables,

$$
\mathbb E_C[x^ix^jx^kx^\ell]
=C^{ij}C^{k\ell}+C^{ik}C^{j\ell}+C^{i\ell}C^{jk}.
$$

This is not an approximation. It is an exact theorem for Gaussian measures.

The quickest proof uses the generating function. Since

$$
Z_C(J)=\exp\!\left(\frac12J_iC^{ij}J_j\right),
$$

each derivative with respect to $J$ must eventually hit one of the $J$’s in the quadratic exponent. At $J=0$, only complete pairings survive.

## Gaussian measures on Hilbert spaces

Let $H$ be a real separable Hilbert space. A Gaussian measure on $H$ should be a probability measure such that every continuous linear functional is a Gaussian random variable. If $\phi\in H$ is distributed according to a centered Gaussian measure with covariance operator $C$, then

$$
\mathbb E[\langle f,\phi\rangle\langle g,\phi\rangle]
=\langle f,Cg\rangle.
$$

The formal density would be

$$
d\mu_C(\phi)
\propto
\exp\!\left(-\frac12\langle\phi,C^{-1}\phi\rangle\right)D\phi.
$$

In infinite dimensions, this formula is only a mnemonic unless a measure has been constructed. One immediate warning is that a Gaussian measure lives on the Hilbert space $H$ only under restrictive conditions. For a genuine probability measure on $H$, the covariance operator must be trace class:

$$
\operatorname{Tr}_H C<\infty.
$$

Free fields in continuum QFT usually violate this condition on the naive configuration space. The correct home is often a larger space of distributions.

## Characteristic functionals

The clean definition of a centered Gaussian field uses its characteristic functional. For test functions $f$, define the smeared field

$$
\phi(f)=\int d^dx\,\phi(x)f(x).
$$

A centered Gaussian field with covariance distribution $G$ satisfies

$$
\mathbb E[e^{i\phi(f)}]
=\exp\!\left(-\frac12 G(f,f)\right),
$$

where

$$
G(f,g)=\int d^dx\,d^dy\,f(x)G(x,y)g(y).
$$

Equivalently, the source generating functional is

$$
Z[J]=\mathbb E[e^{\phi(J)}]
=\exp\!\left(\frac12G(J,J)\right),
$$

when $J$ is a suitable test function.

The factor of $i$ in the characteristic functional is conventional probability notation. The source functional without $i$ is the Euclidean QFT convention. Both encode the same covariance, with an analytic continuation in the source.

## The Gaussian free field

The Euclidean massive scalar field in $d$ dimensions has action

$$
S_E[\phi]
=\frac12\int d^dx\,\phi(x)(-\nabla^2+m^2)\phi(x),
$$

after integration by parts and with suitable boundary conditions. The kinetic operator is

$$
K=-\nabla^2+m^2.
$$

The covariance is its Green function:

$$
KG(x,y)=\delta^{(d)}(x-y).
$$

Thus the Gaussian free field is formally

$$
d\mu_G(\phi)
\propto
\exp\!\left[-\frac12\int d^dx\,\phi(x)K\phi(x)\right]D\phi,
$$

with two-point function

$$
\mathbb E[\phi(x)\phi(y)]=G(x,y).
$$

On $\mathbb R^d$, using the Fourier convention from the mathematical conventions page,

$$
G(x-y)=\int\frac{d^dp}{(2\pi)^d}\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

Here $p^2$ is Euclidean. The denominator is positive for $m^2>0$.

The same object appears in QFT under several names:

| Context | Name |
|---|---|
| probability | covariance kernel |
| PDE | Green function |
| Euclidean QFT | Schwinger two-point function |
| perturbation theory | Euclidean propagator |
| lattice field theory | inverse quadratic form |

## Smearing and ultraviolet singularities

The expression $G(x,x)$ is often divergent in continuum dimensions of interest. For example,

$$
G(0)=\int\frac{d^dp}{(2\pi)^d}\frac1{p^2+m^2}
$$

is ultraviolet divergent for $d\ge 2$.

This is not a small technical glitch. It means $\phi(x)$ is too singular to be treated as an ordinary random variable. The smeared field

$$
\phi(f)=\int d^dx\,\phi(x)f(x)
$$

has finite variance if

$$
G(f,f)<\infty.
$$

So the honest statement is:

$$
\phi(f)\text{ is Gaussian for each test function }f.
$$

Products such as $\phi(x)^2$ and $\phi(x)^4$ require regularization and renormalization. In free theory, normal ordering subtracts the divergent self-contractions. In interacting theory, this becomes the beginning of renormalization.

## Lattice regularization

A lattice makes the Gaussian measure honest and finite-dimensional. Let $\Lambda$ be a finite set of lattice sites. A scalar field is a vector

$$
\phi=(\phi_x)_{x\in\Lambda}.
$$

A typical quadratic action is

$$
S[\phi]
=\frac12\sum_{x,y\in\Lambda}\phi_xK_{xy}\phi_y,
$$

where $K$ is a positive matrix. Then

$$
Z[J]
=(2\pi)^{N/2}(\det K)^{-1/2}
\exp\!\left(\frac12\sum_{x,y}J_x(K^{-1})_{xy}J_y\right),
$$

where $N=|\Lambda|$.

All Gaussian field formulas are rigorous on the finite lattice. Continuum QFT asks whether useful limits survive as the lattice spacing goes to zero and the volume goes to infinity.

## Massless fields and zero modes

The massless scalar kinetic operator on a compact space is often

$$
K=-\nabla^2.
$$

But constants lie in the kernel:

$$
-\nabla^2(1)=0.
$$

Therefore $K$ is not invertible, and the naive Gaussian normalization diverges. This is the zero-mode problem.

Common repairs include:

| Repair | Meaning |
|---|---|
| add $m^2>0$ | use an infrared regulator |
| fix the average field | remove the constant mode |
| work with derivatives of $\phi$ | use observables insensitive to the zero mode |
| put the theory in infinite volume carefully | define limits of smeared observables |

Zero modes are not rare edge cases. They appear in gauge theories, moduli spaces, collective coordinates, instantons, Goldstone modes, and finite-volume path integrals.

## Cameron–Martin shifts

For a finite-dimensional Gaussian, shifting the variable by $h$ changes the measure by an explicit density:

$$
\frac{d\mu_{h,C}}{d\mu_C}(x)
=\exp\!\left(h^TC^{-1}x-\frac12h^TC^{-1}h\right).
$$

In infinite dimensions, not every shift is allowed. The Cameron–Martin space is the set of shifts $h$ for which the translated Gaussian measure is absolutely continuous with respect to the original one. For covariance $C$, it is morally the range of $C^{1/2}$ with norm

$$
\|h\|_{CM}^2=\langle h,C^{-1}h\rangle.
$$

This matters because typical samples of a Gaussian field are rougher than the functions one uses to shift them. The path-integral phrase “shift the integration variable” is harmless in finite dimensions, but in infinite dimensions it has a theorem behind it — and hypotheses.

## Complex Gaussian fields

For a complex scalar field, write $\phi$ and $\phi^*$ as independent integration variables in Euclidean functional integrals, or equivalently decompose into two real fields. A finite-dimensional complex Gaussian often takes the form

$$
d\mu_A(z,z^*)
\propto
\exp(-z_i^*A^i_{\ j}z^j)\prod_i d\operatorname{Re}z_i\,d\operatorname{Im}z_i,
$$

with $A$ positive Hermitian. The covariance is

$$
\mathbb E[z^i z_j^*]=(A^{-1})^i_{\ j},
$$

while

$$
\mathbb E[z^iz^j]=0
$$

for the circularly symmetric centered Gaussian.

In QFT this is the probabilistic form behind the free complex scalar propagator. For charged fields, only charge-neutral correlators survive in the symmetric Gaussian state.

## Fermions are Gaussian but not probabilistic

Fermionic free fields also have “Gaussian” integrals, but over Grassmann variables:

$$
\int D\overline\psi D\psi\,
\exp(-\overline\psi D\psi+\overline\eta\psi+\overline\psi\eta)
=\det D\,\exp(\overline\eta D^{-1}\eta).
$$

This is algebraically parallel to the bosonic Gaussian, but it is not a probability measure. Grassmann variables are nilpotent algebraic generators, not random numbers.

The shared word **Gaussian** means “quadratic exponent and pairwise contractions.” Positivity belongs only to the bosonic probability-measure side.

## Relation to free QFT

In perturbative QFT, the free Gaussian measure supplies the contractions. An interacting Euclidean scalar theory is formally written as

$$
\langle \mathcal O\rangle
=\frac{\mathbb E_G[\mathcal O[\phi]e^{-S_{\mathrm{int}}[\phi]}]}
{\mathbb E_G[e^{-S_{\mathrm{int}}[\phi]}]}.
$$

The Gaussian expectation $\mathbb E_G$ is the free theory. Expanding $e^{-S_{\mathrm{int}}}$ produces products of fields. Wick’s theorem reduces those products to sums over propagators. That is the probabilistic skeleton of Feynman diagrams.

The denominator removes vacuum bubbles and ensures

$$
\langle 1\rangle=1.
$$

This is the same normalization lesson from probability, with diagrammatic consequences.

## Common pitfalls

### Treating the covariance as optional notation

The covariance is the theory. For a centered Gaussian, changing $C$ changes every correlation function.

### Forgetting positivity

A probability Gaussian requires a positive covariance. Lorentzian quadratic actions lead to oscillatory Gaussian integrals, not probability measures.

### Confusing the kinetic operator with the propagator

The kinetic operator $K$ appears in the exponent. The propagator is $K^{-1}$. Mixing them is the most common Gaussian sign-and-inverse bug.

### Evaluating fields at points too casually

In continuum QFT, $\phi(x)$ may be a distribution-valued random object. Smeared fields $\phi(f)$ are safer.

### Ignoring zero modes

If $K$ has a kernel, $\det K=0$ and $K^{-1}$ does not exist on the full space. Remove zero modes, fix a gauge, add a regulator, or restrict observables.

### Assuming Gaussian means free of divergences

Gaussian theories are exactly solvable, not automatically finite. Coincident-point correlators and determinants can still diverge.

## Exercises

### Exercise 1: Four-point Wick formula

Let $x^i$ be a centered Gaussian vector with covariance $C^{ij}$. Use the generating function to compute

$$
\mathbb E[x^ix^jx^kx^\ell].
$$

<details><summary><strong>Solution</strong></summary>

The generating function is

$$
Z(J)=\exp\!\left(\frac12J_aC^{ab}J_b\right).
$$

The four-point moment is

$$
\left.\partial_i\partial_j\partial_k\partial_\ell Z(J)\right|_{J=0}.
$$

At $J=0$, every surviving term must pair the four derivatives into two derivatives acting on the quadratic exponent. The possible pairings are

$$
(ij)(k\ell),\qquad (ik)(j\ell),\qquad (i\ell)(jk).
$$

Therefore

$$
\mathbb E[x^ix^jx^kx^\ell]
=C^{ij}C^{k\ell}+C^{ik}C^{j\ell}+C^{i\ell}C^{jk}.
$$

</details>

### Exercise 2: Source derivative for the free field

Let

$$
Z[J]=\exp\!\left(\frac12\int d^dx\,d^dy\,J(x)G(x,y)J(y)\right).
$$

Show that

$$
\left.\frac{\delta^2Z}{\delta J(x)\delta J(y)}\right|_{J=0}=G(x,y).
$$

<details><summary><strong>Solution</strong></summary>

Set

$$
A[J]=\frac12\int d^du\,d^dv\,J(u)G(u,v)J(v).
$$

Then

$$
\frac{\delta A}{\delta J(x)}=\int d^du\,G(x,u)J(u),
$$

assuming $G(x,y)=G(y,x)$. Since $Z=e^A$,

$$
\frac{\delta^2Z}{\delta J(x)\delta J(y)}
=\left(\frac{\delta^2A}{\delta J(x)\delta J(y)}
+\frac{\delta A}{\delta J(x)}\frac{\delta A}{\delta J(y)}\right)e^A.
$$

At $J=0$, the first derivatives of $A$ vanish and $A[0]=0$. Also

$$
\frac{\delta^2A}{\delta J(x)\delta J(y)}=G(x,y).
$$

Thus

$$
\left.\frac{\delta^2Z}{\delta J(x)\delta J(y)}\right|_{J=0}=G(x,y).
$$

</details>

### Exercise 3: A zero-mode divergence

Consider one real variable with action

$$
S(x)=\frac12kx^2.
$$

What happens to the Gaussian normalization as $k\to0^+$? Interpret the result as a zero-mode problem.

<details><summary><strong>Solution</strong></summary>

The partition function is

$$
Z(k)=\int_{-\infty}^{\infty}dx\,e^{-\frac12kx^2}
=\sqrt{\frac{2\pi}{k}}.
$$

As $k\to0^+$,

$$
Z(k)\to\infty.
$$

When $k=0$, the action does not suppress motion along the $x$ direction. The integral over that direction is an infinite volume. In field theory, the same phenomenon occurs when the kinetic operator has a zero eigenvector, such as the constant mode of the massless scalar Laplacian on a compact space.

</details>

### Exercise 4: Covariance after a linear map

Let $x$ be centered Gaussian with covariance $C$. Define $y=Ax$. Show that $y$ is centered Gaussian with covariance $ACA^T$.

<details><summary><strong>Solution</strong></summary>

The mean is

$$
\mathbb E[y]=A\mathbb E[x]=0.
$$

The covariance is

$$
\mathbb E[y^ay^b]
=A^a_{\ i}A^b_{\ j}\mathbb E[x^ix^j]
=A^a_{\ i}C^{ij}A^b_{\ j}.
$$

In matrix notation,

$$
C_y=ACA^T.
$$

The generating function confirms Gaussianity:

$$
\mathbb E[e^{J^Ty}]
=\mathbb E[e^{(A^TJ)^Tx}]
=\exp\!\left(\frac12J^TACA^TJ\right).
$$

</details>

## References

- Billingsley, *Probability and Measure*.
- Bogachev, *Gaussian Measures*.
- Glimm and Jaffe, *Quantum Physics: A Functional Integral Point of View*.
- Simon, *Functional Integration and Quantum Physics*.
- Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Srednicki, *Quantum Field Theory*, chapters on path integrals and free fields.
- Altland and Simons, *Condensed Matter Field Theory*, chapters on functional integration.

## Version history

- **2026-06-27:** First polished draft. Introduces finite and infinite-dimensional Gaussian measures, covariance operators, characteristic functionals, the Gaussian free field, Wick factorization, zero modes, smearing, and QFT applications.
