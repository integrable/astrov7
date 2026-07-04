---
title: "Convolution"
description: "A QFT-oriented guide to convolution of functions and distributions, translation-invariant kernels, Green functions, approximate identities, and the Fourier convolution theorem."
sidebar:
  label: "Convolution"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard Fourier analysis and distribution theory, with QFT applications to Green functions, propagators, kernels, regulators, and momentum-space multiplication."
topics:
  - convolution
  - kernels
  - Green functions
  - Fourier transforms
  - distributions
canonicalTopics:
  - convolution
  - translation-invariant-kernels
  - green-functions
  - fourier-convolution-theorem
researchStatus:
  established:
    - "Convolution is the standard operation connecting translation-invariant kernels in position space with multiplication in momentum space."
  active:
    - "In singular QFT settings, convolution and related products require regularization, wavefront-set criteria, boundary prescriptions, or renormalized extensions."
---

## Summary

Convolution is the operation that combines a function with a translation-invariant kernel:

$$
(f*g)(x)=\int d^dy\,f(x-y)g(y).
$$

In QFT, this is everywhere. Green functions solve equations by convolution. Propagators are kernels. Regulators smooth fields by convolution with approximate identities. Translation-invariant quadratic actions become multiplication in momentum space. Loop integrals are convolution/product identities written in Fourier variables.

With the Euclidean Fourier convention

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
$$

convolution becomes multiplication:

$$
\widehat{f*g}(k)=\widehat f(k)\widehat g(k).
$$

That one formula explains why flat-space free theories are diagonal in momentum space.

<figure class="doc-figure" style="--figure-width: 38rem;">

![Convolution diagram showing a kernel sliding over a function in position space and multiplication by the kernel's Fourier transform in momentum space.](/figures/math-toolkit/convolution-kernel.svg)

<figcaption>

A translation-invariant kernel acts by convolution in position space and by multiplication in momentum space. This is the analytic backbone behind Green functions, propagators, response kernels, heat kernels, and smooth regulators.

</figcaption>
</figure>

## Prerequisites

You should know the distributional pairing from [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), the delta distribution from [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), and the distinction between compactly supported and Schwartz test functions from [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/).

The Fourier conventions used here are those of [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

## Core idea

A convolution is what a linear operator looks like when it is translation invariant.

A general integral operator has a kernel $K(x,y)$:

$$
(Af)(x)=\int d^dy\,K(x,y)f(y).
$$

If $A$ is invariant under translations, then the kernel depends only on $x-y$:

$$
K(x,y)=K(x-y).
$$

Then

$$
(Af)(x)=\int d^dy\,K(x-y)f(y)=(K*f)(x).
$$

Momentum space diagonalizes this operation:

$$
\widehat{Af}(k)=\widehat K(k)\widehat f(k).
$$

So a translation-invariant differential equation becomes algebraic after Fourier transformation. That is the everyday miracle behind propagators.

## Setup and conventions

On $\mathbb R^d$, define

$$
(f*g)(x)=\int_{\mathbb R^d}d^dy\,f(x-y)g(y),
$$

whenever the integral makes sense. Equivalent forms are

$$
(f*g)(x)=\int d^dy\,f(y)g(x-y)
$$

and, after the substitution $z=x-y$,

$$
(f*g)(x)=\int d^dz\,f(z)g(x-z).
$$

The delta distribution is the identity element:

$$
\delta*f=f*\delta=f.
$$

We use the Euclidean/spatial Fourier convention

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\int_k=\int\frac{d^dk}{(2\pi)^d}.
$$

For Lorentzian spacetime, the same ideas apply with the Lorentzian phase convention

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p).
$$

Only the signs in derivative rules and propagator denominators change.

## Convolution of nice functions

For sufficiently nice functions, convolution has the expected algebraic properties:

$$
f*g=g*f,
$$

$$
(f*g)*h=f*(g*h),
$$

and

$$
\partial_i(f*g)=(\partial_i f)*g=f*(\partial_i g),
$$

assuming boundary terms vanish or the identities are interpreted distributionally.

The derivative identity follows by differentiating under the integral:

$$
\partial_i(f*g)(x)=\int d^dy\,(\partial_i f)(x-y)g(y).
$$

To move the derivative onto $g$, write

$$
(f*g)(x)=\int d^dy\,f(y)g(x-y)
$$

and differentiate the second factor.

The support obeys

$$
\operatorname{supp}(f*g)
\subseteq
\operatorname{supp}f+\operatorname{supp}g,
$$

where

$$
A+B=\{a+b\mid a\in A,\ b\in B\}.
$$

This simple containment is surprisingly useful. Compact support remains controlled under convolution:

$$
f,g\in C_c^\infty(\mathbb R^d)
\quad\Rightarrow\quad
f*g\in C_c^\infty(\mathbb R^d).
$$

Schwartz functions are also stable under convolution:

$$
f,g\in\mathcal S(\mathbb R^d)
\quad\Rightarrow\quad
f*g\in\mathcal S(\mathbb R^d).
$$

## Fourier convolution theorem

Using the convention above,

$$
\widehat{f*g}(k)=\widehat f(k)\widehat g(k).
$$

Indeed,

$$
\widehat{f*g}(k)
=\int d^dx\,e^{-ik\cdot x}\int d^dy\,f(x-y)g(y).
$$

Set $z=x-y$, so $x=z+y$. Then

$$
\widehat{f*g}(k)
=\int d^dz\,d^dy\,e^{-ik\cdot(z+y)}f(z)g(y)
=\widehat f(k)\widehat g(k).
$$

The dual identity says that pointwise multiplication in position space becomes convolution in momentum space:

$$
\widehat{fg}(k)=\int_q\widehat f(q)\widehat g(k-q).
$$

This is the origin of momentum-flow integrals at interaction vertices. A local product of fields at the same point produces an integral over momenta constrained by total momentum conservation.

## Convolution with a test function

If $T\in\mathcal D'(\mathbb R^d)$ and $\varphi\in C_c^\infty(\mathbb R^d)$, define

$$
(T*\varphi)(x)=\langle T_y,\varphi(x-y)\rangle.
$$

Here the subscript $y$ reminds us that $T$ acts on the $y$ variable. For fixed $x$, the function $y\mapsto\varphi(x-y)$ is again a compactly supported smooth test function.

The result $T*\varphi$ is a smooth function of $x$. Differentiating under the distributional pairing gives

$$
\partial_i(T*\varphi)(x)
=\langle T_y,\partial_i\varphi(x-y)\rangle.
$$

Equivalently,

$$
\partial_i(T*\varphi)=(\partial_iT)*\varphi=T*(\partial_i\varphi).
$$

Examples:

$$
(\delta_a*\varphi)(x)=\varphi(x-a),
$$

and

$$
(\partial_i\delta_a*\varphi)(x)=\partial_i\varphi(x-a).
$$

This operation is smoothing. Even if $T$ is singular, $T*\varphi$ is smooth. That is why mollifiers and smooth regulators are built from convolution.

## Convolution of distributions

Convolution of two arbitrary distributions is not always defined. There are, however, important safe cases.

If $S,T\in\mathcal D'(\mathbb R^d)$ and at least one of them has compact support, then their convolution is defined by

$$
\langle S*T,\varphi\rangle
=\left\langle S_x,\left\langle T_y,\varphi(x+y)\right\rangle\right\rangle.
$$

When $S$ and $T$ come from ordinary functions, this reproduces the usual convolution pairing:

$$
\int d^dz\,(S*T)(z)\varphi(z)
=\int d^dx\,d^dy\,S(x)T(y)\varphi(x+y).
$$

The support estimate becomes

$$
\operatorname{supp}(S*T)
\subseteq
\operatorname{supp}S+\operatorname{supp}T.
$$

For tempered distributions, convolution can also be defined in many cases, but not by wishful thinking. A safe route is to use Fourier space only when the product

$$
\widehat S(k)\widehat T(k)
$$

is itself a meaningful tempered distribution. This condition is automatic when one factor is a Schwartz function, often manageable when one factor is smooth with polynomial growth, and dangerous when both factors are singular on overlapping sets.

This is not a technical footnote. It is the analytic shadow of renormalization. Loop integrals often try to multiply or convolve singular distributions. A regulator gives a temporary definition; renormalization asks which limit or extension is physically and mathematically acceptable.

## Approximate identities and smoothing

Let $\rho\in\mathcal S(\mathbb R^d)$ satisfy

$$
\int d^dx\,\rho(x)=1,
$$

and define

$$
\rho_\epsilon(x)=\epsilon^{-d}\rho(x/\epsilon).
$$

Then $\rho_\epsilon$ is an approximate identity:

$$
\rho_\epsilon\to\delta
$$

distributionally. For a nice function $f$,

$$
\rho_\epsilon*f\to f
$$

as $\epsilon\to0$ in the appropriate sense. If $f$ is smooth, the convergence is local and controlled. If $f$ is a distribution, $\rho_\epsilon*T$ is a smooth approximation to $T$.

Fourier space makes the regulator role transparent:

$$
\widehat{\rho_\epsilon*f}(k)=\widehat\rho(\epsilon k)\widehat f(k).
$$

If $\widehat\rho(0)=1$ and $\widehat\rho$ decays at large argument, then convolution with $\rho_\epsilon$ suppresses momenta $|k|\gtrsim1/\epsilon$ while leaving low momenta nearly unchanged.

This is the clean version of "smearing a field over a short distance." It is also a model for smooth ultraviolet cutoffs.

## Translation-invariant kernels

A kernel $K(x,y)$ defines an integral operator

$$
(Af)(x)=\int d^dy\,K(x,y)f(y).
$$

If $K(x,y)=K(x-y)$, then

$$
A f=K*f.
$$

Fourier transformation gives

$$
\widehat{Af}(k)=\widehat K(k)\widehat f(k).
$$

The function or distribution $\widehat K(k)$ is called the symbol of the translation-invariant operator. For differential operators with constant coefficients, the symbol is a polynomial. For example,

$$
(-\Delta+m^2)e^{ik\cdot x}=(k^2+m^2)e^{ik\cdot x}.
$$

Thus the symbol of $-\Delta+m^2$ is

$$
P(k)=k^2+m^2.
$$

An inverse kernel, if it exists with chosen boundary conditions, has symbol

$$
\widehat G(k)=\frac{1}{P(k)}.
$$

When $P(k)$ has zeros, the reciprocal is singular and must be interpreted as a distribution with a prescription.

## Green functions as convolution inverses

Let

$$
L=-\Delta+m^2
$$

on $\mathbb R^d$ with $m>0$. A translation-invariant Green function $G_m$ satisfies

$$
(-\Delta+m^2)G_m(x)=\delta^{(d)}(x).
$$

Taking the Fourier transform gives

$$
(k^2+m^2)\widehat G_m(k)=1,
$$

so

$$
\widehat G_m(k)=\frac{1}{k^2+m^2}.
$$

Therefore

$$
G_m(x)=\int_k\frac{e^{ik\cdot x}}{k^2+m^2}.
$$

If $f$ is a suitable source, then

$$
u=G_m*f
$$

solves

$$
(-\Delta+m^2)u=f.
$$

The massless three-dimensional case gives the Coulomb kernel:

$$
G_0(x)=\frac{1}{4\pi|x|},
\qquad
-\Delta G_0=\delta^{(3)}(x).
$$

In Lorentzian QFT, the operator is hyperbolic rather than elliptic, so inverses are not unique. Retarded, advanced, Feynman, anti-Feynman, and Wightman prescriptions are different distributional inverses or boundary values. Same differential operator, different physics. Sneaky little kernel, big consequences.

## Propagators and composition

A free Euclidean scalar action has quadratic form

$$
S[\phi]=\frac12\int d^dx\,\phi(x)(-\Delta+m^2)\phi(x).
$$

The free two-point function is the inverse kernel:

$$
\langle\phi(x)\phi(y)\rangle=G_m(x-y).
$$

With a source $J$, the Gaussian generating functional contains

$$
\frac12\int d^dx\,d^dy\,J(x)G_m(x-y)J(y)
=\frac12\int d^dx\,J(x)(G_m*J)(x).
$$

Momentum space turns this into

$$
\frac12\int_k\widehat J(-k)\frac{1}{k^2+m^2}\widehat J(k),
$$

with the usual reality assumptions on $J$.

Composition of translation-invariant kernels corresponds to convolution in position space and multiplication in momentum space. If

$$
A f=K_A*f,
\qquad
B f=K_B*f,
$$

then

$$
AB f=(K_A*K_B)*f,
$$

and

$$
\widehat{K_{AB}}(k)=\widehat K_A(k)\widehat K_B(k).
$$

This is why propagator chains become products of denominators in momentum space.

## Heat kernels and semigroups

The heat kernel on $\mathbb R^d$ is

$$
K_t(x)=\frac{1}{(4\pi t)^{d/2}}\exp\!\left(-\frac{|x|^2}{4t}\right),
\qquad t>0.
$$

It satisfies

$$
(\partial_t-\Delta)K_t=0,
\qquad
K_t\to\delta
\quad\text{as }t\to0^+.
$$

Its Fourier transform is

$$
\widehat K_t(k)=e^{-tk^2}.
$$

Therefore

$$
\widehat{K_t*K_s}(k)=e^{-tk^2}e^{-sk^2}=e^{-(t+s)k^2},
$$

so

$$
K_t*K_s=K_{t+s}.
$$

This semigroup property is the analytic seed of heat-kernel regularization, Schwinger proper-time formulas, diffusion intuition, and many determinant computations.

## Products, loops, and local singularities

The Fourier duality

$$
\widehat{fg}(k)=\int_q\widehat f(q)\widehat g(k-q)
$$

is harmless for Schwartz functions. In QFT, $f$ and $g$ are often singular kernels. Then the momentum convolution can diverge.

A simple symbolic example is the square of a propagator in position space. If $G(x)$ is singular at $x=0$, then $G(x)^2$ may be too singular to define as an ordinary distribution. In momentum space, the corresponding expression is a loop integral:

$$
\int_q\widehat G(q)\widehat G(k-q).
$$

Divergence in the loop integral is the same problem as an ill-defined product of singular distributions at coincident points. Renormalization is, among other things, the art of extending these products while preserving locality, symmetry, and chosen normalization conditions.

The local ambiguity in such an extension is made of contact terms:

$$
\sum_{|\alpha|\le N}c_\alpha\partial^\alpha\delta^{(d)}(x).
$$

Momentum space sees these as polynomials in $k$. That is the bridge between contact terms and local counterterms.

## Boundary conditions and non-unique inverses

The equation

$$
LG=\delta
$$

does not uniquely determine $G$. If $H$ satisfies

$$
LH=0,
$$

then

$$
G+H
$$

is another Green function. Boundary conditions, support conditions, analyticity, positivity, or vacuum choice select the one that appears in a physical problem.

For elliptic Euclidean operators, decay at infinity or regularity often selects a preferred Green function. For Lorentzian hyperbolic operators, causal support gives retarded and advanced Green functions:

$$
\operatorname{supp}G_R\subseteq\{t\ge0\},
\qquad
\operatorname{supp}G_A\subseteq\{t\le0\}.
$$

Time ordering gives the Feynman propagator. Thermal boundary conditions give Matsubara kernels. Different convolution inverses encode different experiments.

## Finite volume and discrete convolution

On a periodic box of volume $V=L^d$, momenta are discrete:

$$
k_i=\frac{2\pi n_i}{L},
\qquad n_i\in\mathbb Z.
$$

The Fourier series convention is

$$
f(x)=\sum_k e^{ik\cdot x}f_k,
\qquad
f_k=\frac1V\int_V d^dx\,e^{-ik\cdot x}f(x).
$$

Periodic convolution is

$$
(f*g)(x)=\int_V d^dy\,f(x-y)g(y),
$$

where $x-y$ is understood modulo the periodic box. Then

$$
(f*g)_k=V f_k g_k.
$$

If one instead uses the continuum-like coefficients $\widehat f_k=Vf_k$, then

$$
\widehat{f*g}_k=\widehat f_k\widehat g_k.
$$

This is one reason finite-volume conventions are so good at exposing hidden factors of $V$.

## Common pitfalls

**Convolving distributions without checking hypotheses.** Convolution is automatic for nice functions and safe in several distributional cases, but two arbitrary distributions do not have a canonical convolution.

**Forgetting which operation Fourier transform swaps.** Convolution in position space becomes multiplication in momentum space. Multiplication in position space becomes convolution in momentum space.

**Ignoring boundary conditions in Green functions.** The equation $LG=\delta$ is incomplete. Retarded, advanced, Feynman, Euclidean, thermal, finite-volume, and Dirichlet kernels can all invert related operators with different boundary data.

**Treating smoothing as harmless.** Convolution with an approximate identity changes a distribution at short distances. Taking the regulator away can expose divergences or ambiguities.

**Dropping contact terms.** Contact terms are invisible at separated points but become polynomials in momentum space. They control counterterms, Ward identities, and operator mixing.

**Losing finite-volume factors.** In a box, convolution coefficients depend on whether the Fourier series is normalized with $f_k$ or $\widehat f_k=Vf_k$. This is a classic source of stray $V$ factors.

## Relations to other pages

[Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) gives the normalization dictionary behind the convolution theorem. [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/) explains which test spaces make distributional convolution and Fourier transforms meaningful. [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) explains why $\delta$ acts as the identity kernel.

This page prepares the later pages on principal values, Green functions, heat kernels, propagators, loop integrals, regulators, and distributional products in QFT.

## Research status

The convolution theory for functions, test functions, compactly supported distributions, and many tempered distributions is established.

The active QFT issues begin when convolution is used as a proxy for products of singular kernels, time-ordered products, restrictions to coincident points, or loop integrals. In modern rigorous perturbation theory, the safe extension of such objects is governed by microlocal criteria and renormalization conditions. In practical perturbative QFT, the same issue appears as regulator dependence, counterterms, and scheme choices.

## Exercises

### Exercise 1: Delta is the identity for convolution

Show that

$$
\delta*f=f
$$

for a test function $f$.

<details>
<summary><strong>Solution</strong></summary>

Using the definition of convolution with a distribution,

$$
(\delta*f)(x)=\langle\delta_y,f(x-y)\rangle=f(x).
$$

Similarly,

$$
(f*\delta)(x)=\langle\delta_y,f(x-y)\rangle=f(x),
$$

after writing the ordinary function in the first slot equivalently as $\int dy\,f(x-y)\delta(y)$.

</details>

### Exercise 2: Prove the convolution theorem

With

$$
(f*g)(x)=\int d^dy\,f(x-y)g(y),
$$

prove

$$
\widehat{f*g}(k)=\widehat f(k)\widehat g(k).
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\widehat{f*g}(k)
=\int d^dx\,e^{-ik\cdot x}\int d^dy\,f(x-y)g(y).
$$

Let $z=x-y$, so $x=z+y$ and $d^dx=d^dz$. Then

$$
\widehat{f*g}(k)
=\int d^dz\,d^dy\,e^{-ik\cdot(z+y)}f(z)g(y).
$$

The integral factors:

$$
\widehat{f*g}(k)
=\left(\int d^dz\,e^{-ik\cdot z}f(z)\right)
\left(\int d^dy\,e^{-ik\cdot y}g(y)\right)
=\widehat f(k)\widehat g(k).
$$

</details>

### Exercise 3: Product becomes momentum convolution

Show that

$$
\widehat{fg}(k)=\int_q\widehat f(q)\widehat g(k-q).
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the inverse transforms:

$$
f(x)=\int_q e^{iq\cdot x}\widehat f(q),
\qquad
g(x)=\int_\ell e^{i\ell\cdot x}\widehat g(\ell).
$$

Then

$$
\widehat{fg}(k)
=\int d^dx\,e^{-ik\cdot x}\int_q\int_\ell
 e^{i(q+\ell)\cdot x}\widehat f(q)\widehat g(\ell).
$$

The $x$ integral gives

$$
(2\pi)^d\delta^{(d)}(k-q-\ell).
$$

Using the delta function to do the $\ell$ integral gives

$$
\widehat{fg}(k)=\int_q\widehat f(q)\widehat g(k-q).
$$

</details>

### Exercise 4: Derivatives commute with convolution

For rapidly decreasing smooth functions, show

$$
\partial_i(f*g)=(\partial_i f)*g=f*(\partial_i g).
$$

<details>
<summary><strong>Solution</strong></summary>

From

$$
(f*g)(x)=\int d^dy\,f(x-y)g(y),
$$

we get

$$
\partial_i(f*g)(x)=\int d^dy\,(\partial_i f)(x-y)g(y)=((\partial_i f)*g)(x).
$$

Using the equivalent form

$$
(f*g)(x)=\int d^dy\,f(y)g(x-y),
$$

we also get

$$
\partial_i(f*g)(x)=\int d^dy\,f(y)(\partial_i g)(x-y)=(f*(\partial_i g))(x).
$$

Rapid decay justifies differentiating under the integral. The same identity holds distributionally under the usual hypotheses.

</details>

### Exercise 5: The massive Euclidean Green function

Let

$$
G_m(x)=\int_k\frac{e^{ik\cdot x}}{k^2+m^2}.
$$

Show that

$$
(-\Delta+m^2)G_m=\delta^{(d)}(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Act on the Fourier representation. Since

$$
-\Delta e^{ik\cdot x}=k^2e^{ik\cdot x},
$$

we have

$$
(-\Delta+m^2)G_m(x)
=\int_k\frac{k^2+m^2}{k^2+m^2}e^{ik\cdot x}
=\int_k e^{ik\cdot x}.
$$

By the Fourier representation of the delta distribution,

$$
\int_k e^{ik\cdot x}=\delta^{(d)}(x).
$$

</details>

### Exercise 6: Heat-kernel semigroup

For

$$
K_t(x)=\frac{1}{(4\pi t)^{d/2}}\exp\!\left(-\frac{|x|^2}{4t}\right),
$$

use Fourier transforms to show

$$
K_t*K_s=K_{t+s}.
$$

<details>
<summary><strong>Solution</strong></summary>

The Fourier transform of $K_t$ is

$$
\widehat K_t(k)=e^{-tk^2}.
$$

Therefore

$$
\widehat{K_t*K_s}(k)=\widehat K_t(k)\widehat K_s(k)
=e^{-tk^2}e^{-sk^2}=e^{-(t+s)k^2}.
$$

But $e^{-(t+s)k^2}$ is the Fourier transform of $K_{t+s}$. Fourier inversion gives

$$
K_t*K_s=K_{t+s}.
$$

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for convolution as it appears in Green functions, Fourier transforms, propagators, and Feynman integrals.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for practical uses of kernels, propagators, Fourier transforms, and loop-momentum convolutions.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for momentum-space normalization, propagators, scattering kernels, and distributional identities in relativistic QFT.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for convolution, Green functions, Fourier methods, and heat-kernel/proper-time technology in field integrals.

### Deeper references

- F. G. Friedlander and M. Joshi, *Introduction to the Theory of Distributions*, for convolution of distributions and support properties.
- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for generalized convolution and Fourier transformation.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for convolution, wavefront sets, and conditions for multiplying or composing distributions.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. II, for Fourier methods, kernels, spectral theory, and Green functions.

## Version history

- **2026-06-23:** Initial polished draft. Added convolution of functions and distributions, smoothing, approximate identities, translation-invariant kernels, Green functions, heat kernels, finite-volume convolution, contact terms, and exercises with solutions.
