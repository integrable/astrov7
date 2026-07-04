---
title: "Delta Functions"
description: "A precise QFT-oriented guide to delta distributions, derivatives, Jacobians, constraint deltas, on-shell measures, finite-volume deltas, and functional delta functions."
sidebar:
  label: "Delta Functions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard distribution theory and QFT applications to Fourier inversion, phase space, Green functions, functional derivatives, and gauge-fixing identities."
topics:
  - delta functions
  - distributions
  - constraint delta functions
  - Jacobians
  - phase space
  - functional delta functions
canonicalTopics:
  - delta-distribution
  - constraint-delta-functions
  - on-shell-measure
  - qft-analysis
researchStatus:
  established:
    - "Delta functions are rigorously understood as distributions and are standard infrastructure in Fourier analysis, Green functions, canonical commutators, and scattering theory."
  active:
    - "Functional delta functions, products of singular distributions, zero-mode constraints, and gauge-fixing determinants require regulator- and framework-dependent care in interacting QFT."
---

## Summary

The delta function is not a function with an infinite spike. It is the distribution that evaluates test functions. In $d$ dimensions,

$$
\int d^dx\,\delta^{(d)}(x-y)f(x)=f(y),
$$

whenever the integral is understood as a distributional pairing. That single formula is the source of most delta-function technology in QFT: Fourier inversion, identity kernels, momentum conservation, canonical commutators, on-shell phase space, functional derivatives, and gauge-fixing determinants.

The most useful identities are

$$
f(x)\delta^{(d)}(x-y)=f(y)\delta^{(d)}(x-y),
$$

$$
\delta(Ax)=\frac{1}{|\det A|}\delta(x),
$$

and, for a one-dimensional function $g$ with simple zeros $x_i$,

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}.
$$

The caveat is just as important as the formulas: delta functions are linear objects. Multiplying them, restricting them to their singular support, or squaring momentum-conservation deltas requires a regulator, a finite-volume interpretation, or a renormalized prescription.

## Prerequisites

You should first read [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and know the Fourier signs fixed in [Mathematical Conventions](/math-toolkit/conventions/). The page uses basic multivariable calculus, changes of variables, and the idea of integrating over a constraint surface.

No advanced measure theory is required. When a formula depends on a chosen integration measure, we will say so explicitly.

## Core idea

A delta function is best understood as an identity kernel or constraint operator.

As an identity kernel, it does nothing except copy a function from one variable to another:

$$
f(x)=\int d^dy\,\delta^{(d)}(x-y)f(y).
$$

As a constraint operator, it localizes an integral onto the locus where its argument vanishes:

$$
\int d^nx\,\delta(F(x))h(x)
$$

is an integral over the hypersurface $F(x)=0$, with a Jacobian. The Jacobian is not optional bookkeeping. It is the statement that the delta distribution has the inverse dimension of its argument.

In QFT, this viewpoint explains why delta functions appear in so many unrelated-looking places:

| Where it appears | What the delta function is doing |
|---|---|
| Fourier inversion | It is the identity kernel between position and momentum space. |
| Canonical commutators | It says equal-time fields are conjugate at the same spatial point. |
| Feynman rules | It enforces momentum conservation at each vertex. |
| Phase space | It puts momenta on shell and imposes total energy–momentum conservation. |
| Functional derivatives | It is the identity kernel on field space. |
| Gauge fixing | It constrains redundant variables and produces a determinant. |

So the slogan is:

$$
\text{a delta function is an instruction inside an integral, not a pointwise function}.
$$

## Setup and conventions

On flat $\mathbb R^d$, the delta distribution at $y$ is defined by

$$
\langle\delta_y,\varphi\rangle=\varphi(y),
\qquad \varphi\in C_c^\infty(\mathbb R^d).
$$

In physicists' integral notation,

$$
\langle\delta_y,\varphi\rangle
=\int d^dx\,\delta^{(d)}(x-y)\varphi(x).
$$

The superscript in $\delta^{(d)}$ records the dimension of the variable being integrated. We often omit it when the dimension is clear, but it should be restored when factors of volume, mass dimension, or phase space matter.

The delta distribution depends on the measure used in the integral. In Cartesian coordinates with measure $d^dx$, the symbol $\delta^{(d)}(x-y)$ means

$$
\int d^dx\,\delta^{(d)}(x-y)f(x)=f(y).
$$

On a Riemannian manifold with volume form $d\operatorname{vol}_g=\sqrt{g(x)}\,d^dx$, the invariant delta kernel is defined by

$$
\int d^dx\sqrt{g(x)}\,\delta_g(x,y)f(x)=f(y).
$$

In a coordinate patch,

$$
\delta_g(x,y)=\frac{\delta^{(d)}_{\mathrm{coord}}(x-y)}{\sqrt{g(x)}}
=\frac{\delta^{(d)}_{\mathrm{coord}}(x-y)}{\sqrt{g(y)}}
$$

as distributions. The two displayed expressions agree after multiplication by $\delta^{(d)}_{\mathrm{coord}}(x-y)$.

Unless stated otherwise, this page uses flat Cartesian measures. Lorentzian formulas use the mostly-minus metric from the site conventions,

$$
p^2=(p^0)^2-\mathbf p^2,
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

## Evaluation and identity kernels

The defining property immediately gives the multiplication rule

$$
f(x)\delta^{(d)}(x-y)=f(y)\delta^{(d)}(x-y)
$$

for any smooth $f$. To check it, pair both sides with a test function $\varphi$:

$$
\int d^dx\,f(x)\delta^{(d)}(x-y)\varphi(x)
=f(y)\varphi(y)
=\int d^dx\,f(y)\delta^{(d)}(x-y)\varphi(x).
$$

The identity operator on functions has kernel $\delta^{(d)}(x-y)$:

$$
(If)(x)=\int d^dy\,\delta^{(d)}(x-y)f(y)=f(x).
$$

This is the continuum version of the matrix identity

$$
(Iv)_i=\sum_j\delta_{ij}v_j=v_i.
$$

The continuum delta has the inverse dimension of the integration measure. If $x$ has dimension of length, then

$$
[\delta^{(d)}(x)]=\text{length}^{-d}.
$$

If $p$ has dimension of momentum, then

$$
[\delta^{(d)}(p)]=\text{momentum}^{-d}.
$$

This dimension check catches many wrong Jacobians.

## Delta sequences

A common visualization is a sequence of narrow bumps whose area remains one. Let $\rho\in C_c^\infty(\mathbb R^d)$, or more generally a rapidly decreasing smooth function, satisfy

$$
\int d^dx\,\rho(x)=1.
$$

Define

$$
\rho_\epsilon(x)=\frac{1}{\epsilon^d}\rho\!\left(\frac{x}{\epsilon}\right).
$$

Then

$$
\rho_\epsilon\to\delta^{(d)}(x)
$$

distributionally, meaning

$$
\lim_{\epsilon\to0^+}\int d^dx\,\rho_\epsilon(x)\varphi(x)=\varphi(0).
$$

For example, the Gaussian family

$$
\rho_\epsilon(x)=\frac{1}{(\sqrt{\pi}\epsilon)^d}
\exp\!\left(-\frac{|x|^2}{\epsilon^2}\right)
$$

has unit integral and tends to $\delta^{(d)}(x)$ after smearing.

<figure class="doc-figure" style="--figure-width: 36rem;">

![Three approximate delta functions becoming narrower and taller while their area remains one.](/figures/math-toolkit/delta-sequence.svg)

<figcaption>

A delta sequence $\rho_\epsilon(x)=\epsilon^{-1}\rho(x/\epsilon)$ is not a function at $\epsilon=0$. The meaningful statement is distributional convergence: $\int dx\,\rho_\epsilon(x)\varphi(x)\to\varphi(0)$ for every test function $\varphi$.

</figcaption>
</figure>

The warning is sharp: distributional convergence is linear. It does not imply that nonlinear expressions converge. For instance, $\rho_\epsilon^2$ usually diverges as $\epsilon\to0$, and different choices of $\rho$ can lead to different subtractions. That is the toy version of why products of singular fields require renormalization.

## Scaling and linear changes of variables

In one dimension,

$$
\delta(ax)=\frac{1}{|a|}\delta(x),
\qquad a\neq0.
$$

The absolute value is forced by the change of variables $u=ax$:

$$
\int dx\,\delta(ax)\varphi(x)
=\frac{1}{|a|}\int du\,\delta(u)\varphi(u/a)
=\frac{1}{|a|}\varphi(0).
$$

In $d$ dimensions, if $A$ is an invertible real matrix, then

$$
\delta^{(d)}(Ax)=\frac{1}{|\det A|}\delta^{(d)}(x).
$$

More generally,

$$
\delta^{(d)}(A(x-x_0))=\frac{1}{|\det A|}\delta^{(d)}(x-x_0).
$$

This rule is the local form of every delta-function Jacobian. It is also why determinants appear in Gaussian integrals, Faddeev–Popov gauge fixing, collective-coordinate measures, and changes of variables in path integrals.

## Delta functions of one variable

Let $g:\mathbb R\to\mathbb R$ be smooth, and suppose its zeros $x_i$ are simple:

$$
g(x_i)=0,
\qquad g'(x_i)\neq0.
$$

Then

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}.
$$

Near a simple zero,

$$
g(x)=g'(x_i)(x-x_i)+O((x-x_i)^2),
$$

so the formula is just the linear scaling rule applied locally. The absolute value again matters.

A useful special case is

$$
\delta(x^2-a^2)=\frac{1}{2|a|}\left[\delta(x-a)+\delta(x+a)\right],
\qquad a\neq0.
$$

For $a>0$,

$$
\delta(\omega^2-E^2)
=\frac{1}{2E}\left[\delta(\omega-E)+\delta(\omega+E)\right].
$$

Multiplying by $\theta(\omega)$ selects the positive-energy root:

$$
\theta(\omega)\delta(\omega^2-E^2)
=\frac{1}{2E}\delta(\omega-E).
$$

This identity is the elementary source of the relativistic on-shell measure.

## Constraint deltas in several variables

Let $F:\mathbb R^n\to\mathbb R^m$ with $m\leq n$, and suppose $F^{-1}(0)$ is a smooth submanifold. If the gradients $\nabla F^a$ are independent on the constraint surface, then

$$
\int d^nx\,\delta^{(m)}(F(x))h(x)
=\int_{F=0}\frac{d\Sigma(x)}{\sqrt{\det G(x)}}\,h(x),
$$

where $d\Sigma$ is the induced measure on the level set and

$$
G_{ab}(x)=\nabla F^a(x)\cdot\nabla F^b(x).
$$

For one constraint $F(x)=g(x)$, this reduces to

$$
\int d^nx\,\delta(g(x))h(x)
=\int_{g=0}\frac{d\Sigma}{|\nabla g|}h(x).
$$

This formula explains the geometric meaning of the Jacobian. A delta function removes one integration direction, but it also divides by the rate at which the constraint changes in the normal direction.

### Example: The sphere constraint

In $\mathbb R^3$,

$$
\int d^3x\,\delta(r^2-R^2)h(x)
=\int_{r=R}\frac{d\Sigma}{2R}h(x),
\qquad R>0.
$$

Since $d\Sigma=R^2d\Omega$, this is

$$
\frac{R}{2}\int d\Omega\,h(R\hat n).
$$

If $h=1$, the answer is $2\pi R$, not the surface area $4\pi R^2$. The delta function $\delta(r^2-R^2)$ has dimension $\text{length}^{-2}$, so this is dimensionally correct.

## Fourier representations

With the Euclidean or spatial convention

$$
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
\int_k=\int\frac{d^dk}{(2\pi)^d},
$$

Fourier inversion is encoded by

$$
\delta^{(d)}(x-y)=\int_k e^{ik\cdot(x-y)}.
$$

The complementary identity is

$$
\int d^dx\,e^{-i(k-q)\cdot x}=(2\pi)^d\delta^{(d)}(k-q).
$$

The second equation is not an ordinary improper integral. It is a distributional identity in momentum space.

For Lorentzian spacetime, the default convention is

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x),
\qquad
\int_p=\int\frac{d^4p}{(2\pi)^4}.
$$

Then

$$
\delta^{(4)}(x-y)=\int_p e^{-ip\cdot(x-y)},
$$

and

$$
\int d^4x\,e^{i(p-q)\cdot x}=(2\pi)^4\delta^{(4)}(p-q).
$$

The signs look different only because the Lorentzian convention is adapted to positive-energy plane waves $e^{-ip\cdot x}$.

## Derivatives of delta functions

The derivative of a delta function is defined by integration by parts:

$$
\int d^dx\,\partial_{x^i}\delta^{(d)}(x-y)\varphi(x)
=-\partial_i\varphi(y).
$$

Equivalently,

$$
\langle\partial_i\delta_y,\varphi\rangle=-\partial_i\varphi(y).
$$

A key identity is

$$
\partial_{x^i}\delta^{(d)}(x-y)
=-\partial_{y^i}\delta^{(d)}(x-y).
$$

It is often used to move derivatives between arguments of a kernel.

In one dimension,

$$
x\delta'(x)=-\delta(x).
$$

Indeed,

$$
\langle x\delta',\varphi\rangle
=\langle\delta',x\varphi\rangle
=-\left.\frac{d}{dx}(x\varphi(x))\right|_{x=0}
=-\varphi(0).
$$

More generally,

$$
x^n\delta^{(m)}(x)=0\quad(n>m),
$$

and

$$
x^m\delta^{(m)}(x)=(-1)^m m!\,\delta(x).
$$

These identities are distributional. They should not be read as pointwise statements at $x=0$.

## On-shell delta functions and Lorentz-invariant phase space

In the mostly-minus convention,

$$
p^2=(p^0)^2-\mathbf p^2,
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The mass-shell constraint is

$$
p^2-m^2=0.
$$

Using the one-dimensional delta rule in the variable $p^0$,

$$
\delta(p^2-m^2)
=\frac{1}{2E_{\mathbf p}}
\left[\delta(p^0-E_{\mathbf p})+\delta(p^0+E_{\mathbf p})\right].
$$

Thus

$$
\theta(p^0)\delta(p^2-m^2)
=\frac{1}{2E_{\mathbf p}}\delta(p^0-E_{\mathbf p}).
$$

For any test function $F(p)$,

$$
\int d^4p\,\theta(p^0)\delta(p^2-m^2)F(p)
=\int\frac{d^3\mathbf p}{2E_{\mathbf p}}F(E_{\mathbf p},\mathbf p).
$$

With the standard QFT $2\pi$ normalization,

$$
\int\frac{d^4p}{(2\pi)^4}\,2\pi\theta(p^0)\delta(p^2-m^2)F(p)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}F(E_{\mathbf p},\mathbf p).
$$

This motivates the compact notation

$$
\int d\Pi_p
\equiv
\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=
\int\frac{d^4p}{(2\pi)^4}\,2\pi\theta(p^0)\delta(p^2-m^2).
$$

The factor $\theta(p^0)$ is not cosmetic. Without it, both energy sheets of the mass hyperboloid are included.

## Momentum conservation deltas

Translation invariance produces momentum-conservation delta functions. With the Lorentzian convention,

$$
\int d^4x\,e^{-i(p_1+\cdots+p_n)\cdot x}
=(2\pi)^4\delta^{(4)}(p_1+\cdots+p_n).
$$

This is why momentum-space vertices in Feynman rules carry factors enforcing

$$
\sum_{\text{incoming}}p_i=\sum_{\text{outgoing}}p_j.
$$

For an $n$-point correlator in a translationally invariant vacuum, one typically writes

$$
\widetilde G(p_1,\ldots,p_n)
=(2\pi)^4\delta^{(4)}(p_1+\cdots+p_n)\,\bar G(p_1,\ldots,p_n),
$$

where $\bar G$ is the reduced correlator with the overall delta function stripped off.

One should not literally square the delta function when computing probabilities. In a finite spacetime box of volume $VT$, the heuristic replacement is

$$
\left[(2\pi)^4\delta^{(4)}(P)\right]^2
\longrightarrow
(2\pi)^4\delta^{(4)}(P)\,VT.
$$

This is the continuum shadow of ordinary Kronecker-delta algebra in finite volume. It is the reason total transition probabilities become rates after division by time and cross sections after division by flux.

## Finite-volume and periodic deltas

On a circle of length $L$ with periodic coordinate $x\sim x+L$, the periodic delta function is

$$
\delta_L(x-y)=\frac{1}{L}\sum_{n\in\mathbb Z}e^{i(2\pi n/L)(x-y)}.
$$

It satisfies

$$
\int_0^L dx\,\delta_L(x-y)f(x)=f(y)
$$

for periodic $f$. In $d$ spatial dimensions with a box of volume $V=L^d$,

$$
\delta_V^{(d)}(\mathbf x-\mathbf y)
=\frac{1}{V}\sum_{\mathbf n\in\mathbb Z^d}
 e^{i\mathbf k_{\mathbf n}\cdot(\mathbf x-\mathbf y)},
\qquad
\mathbf k_{\mathbf n}=\frac{2\pi}{L}\mathbf n.
$$

The orthogonality relation is

$$
\int_V d^d\mathbf x\,
 e^{i(\mathbf k-\mathbf q)\cdot\mathbf x}
=V\delta_{\mathbf k,\mathbf q}.
$$

The continuum limit replaces

$$
\frac{1}{V}\sum_{\mathbf k}\longrightarrow\int\frac{d^d\mathbf k}{(2\pi)^d},
\qquad
V\delta_{\mathbf k,\mathbf q}\longrightarrow(2\pi)^d\delta^{(d)}(\mathbf k-\mathbf q).
$$

This dictionary is indispensable when translating canonical quantization in a box into continuum normalization.

## Functional delta functions

The finite-dimensional identity

$$
\delta^{(n)}(Ax)=\frac{1}{|\det A|}\delta^{(n)}(x)
$$

has a formal infinite-dimensional analogue:

$$
\delta[F[\phi]]
=\frac{\delta[\phi-\phi_*]}{|\det(\delta F/\delta\phi)|_{\phi_*}}
$$

when $F[\phi_*]=0$ and the functional derivative has no zero modes. This formula is formal, but it captures the source of functional determinants.

The basic normalization is

$$
\int \mathcal D\phi\,\delta[\phi-\phi_0]F[\phi]=F[\phi_0].
$$

For ordinary bosonic fields,

$$
\frac{\delta\phi^a(x)}{\delta\phi^b(y)}
=\delta^a{}_b\delta^{(d)}(x-y).
$$

In gauge theory, a schematic Faddeev–Popov identity has the form

$$
1=\int \mathcal D\alpha\,
\delta[G(A^\alpha)]\,
\det\!\left(\frac{\delta G(A^\alpha)}{\delta\alpha}\right),
$$

where $G(A)=0$ is a gauge condition and $\alpha$ parametrizes the gauge transformation. The determinant is the functional Jacobian that compensates for imposing the delta-functional constraint.

This formula hides serious issues: zero modes, Gribov copies, boundary conditions, regularization, and the meaning of the measure. Still, as a local perturbative identity, it is the same delta-function Jacobian you already know from finite-dimensional calculus.

## Delta functions in Green functions

A Green function is often defined as a distributional inverse. If $P_x$ is a differential operator, then a Green kernel $G(x,y)$ satisfies

$$
P_xG(x,y)=\delta^{(d)}(x-y)
$$

with boundary, support, or analyticity conditions.

For the Euclidean massive scalar operator,

$$
G_E(x-y)=\int_k\frac{e^{ik\cdot(x-y)}}{k^2+m^2}
$$

satisfies

$$
(-\Delta_x+m^2)G_E(x-y)=\delta^{(d)}(x-y).
$$

For the Lorentzian Feynman propagator in mostly-minus signature,

$$
\Delta_F(x-y)=\int_p\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i0},
$$

one has

$$
(\Box_x+m^2)\Delta_F(x-y)=-i\delta^{(4)}(x-y).
$$

The factor $-i$ is a convention-dependent consequence of the Lorentzian path-integral and propagator normalization. The delta function itself is the unambiguous statement that the propagator is an inverse kernel with a specified pole prescription.

## Common pitfalls

**Writing $\delta(0)$ as though it were a number.** The delta distribution has no value at the origin. In a finite box, $\delta^{(d)}(0)$ may be represented by a volume-dependent quantity such as $V/(2\pi)^d$, but that belongs to the regulator.

**Forgetting the absolute value in Jacobians.** The identity is $\delta(g(x))=\sum_i\delta(x-x_i)/|g'(x_i)|$, not $1/g'(x_i)$ unless an orientation-sensitive distribution has been explicitly defined.

**Confusing $\delta(x^2-a^2)$ with $\delta(x-a)$.** Both roots contribute unless a step function or integration range removes one of them.

**Dropping the on-shell factor $1/(2E_{\mathbf p})$.** This factor is the Jacobian from the constraint $p^2=m^2$. Forgetting it breaks Lorentz-invariant phase space.

**Squaring momentum-conservation deltas.** Work in finite volume/time or use wave packets. The symbolic square of a delta function is not a distribution.

**Using a coordinate delta on a curved manifold without the volume density.** The invariant delta is defined relative to the integration measure.

**Treating functional delta functions as rigorous measures without qualification.** They are often reliable perturbative shorthand, but zero modes, boundary conditions, and regularization can change the answer.

## Relations to other pages

This page specializes the general distributional framework developed in [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/). The sign and $2\pi$ normalizations used in the Fourier representations are fixed in [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

The [Mathematical Conventions](/math-toolkit/conventions/) page records the site-wide mathematical normalizations for delta distributions, functional derivatives, and principal values. Later pages on Green functions, principal values, convolution, Gaussian integrals, and functional determinants use the delta identities here without rederiving them each time.

## Research status

The delta distribution and its finite-dimensional transformation laws are settled mathematics. Their QFT uses in Fourier analysis, Green functions, canonical commutators, and phase space are standard.

The active subtleties occur when delta functions are embedded in more singular structures: products of distributions, composite operators, equal-time limits, constraints with zero modes, path-integral measures, gauge fixing beyond perturbation theory, and renormalized contact terms. In those settings the formal delta identity is only the first line of the calculation, not the whole definition.

## Exercises

### Exercise 1: Delta of a function with simple zeros

Let $g:\mathbb R\to\mathbb R$ be smooth with simple zeros $x_i$. Prove

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}.
$$

<details>
<summary><strong>Solution</strong></summary>

Pair the left-hand side with a test function $\varphi$ and decompose the integral into small neighborhoods of the simple zeros. Near $x_i$, the map $u=g(x)$ is a local diffeomorphism, so

$$
\int dx\,\delta(g(x))\varphi(x)
=\sum_i\int du\,\delta(u)\,
\frac{\varphi(x_i(u))}{|g'(x_i(u))|}.
$$

Evaluating at $u=0$ gives

$$
\sum_i\frac{\varphi(x_i)}{|g'(x_i)|}.
$$

This is precisely the pairing of

$$
\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}
$$

with $\varphi$.

</details>

### Exercise 2: Moving derivatives between delta-function arguments

Show that

$$
\partial_{x^i}\delta^{(d)}(x-y)
=-\partial_{y^i}\delta^{(d)}(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

Pair the left-hand side with a test function $\varphi(x)$:

$$
\int d^dx\,\partial_{x^i}\delta^{(d)}(x-y)\varphi(x)
=-\partial_i\varphi(y).
$$

Now pair $-\partial_{y^i}\delta^{(d)}(x-y)$ with the same test function. Since $y$ is a parameter in the $x$ integral,

$$
-\partial_{y^i}\int d^dx\,\delta^{(d)}(x-y)\varphi(x)
=-\partial_i\varphi(y).
$$

The pairings agree for every $\varphi$, so the distributions are equal.

</details>

### Exercise 3: The positive-energy mass shell

Using $p^2=(p^0)^2-\mathbf p^2$, prove

$$
\int\frac{d^4p}{(2\pi)^4}\,2\pi\theta(p^0)\delta(p^2-m^2)F(p)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}F(E_{\mathbf p},\mathbf p).
$$

<details>
<summary><strong>Solution</strong></summary>

For fixed $\mathbf p$,

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2.
$$

Therefore

$$
\delta(p^2-m^2)
=\frac{1}{2E_{\mathbf p}}
\left[\delta(p^0-E_{\mathbf p})+\delta(p^0+E_{\mathbf p})\right].
$$

Multiplication by $\theta(p^0)$ keeps only the first term. The $p^0$ integral then gives

$$
\int\frac{dp^0}{2\pi}\,2\pi\theta(p^0)\delta(p^2-m^2)F(p)
=\frac{1}{2E_{\mathbf p}}F(E_{\mathbf p},\mathbf p).
$$

The remaining spatial measure is $d^3\mathbf p/(2\pi)^3$.

</details>

### Exercise 4: Delta function on a circle

Let $R>0$ and $g(x,y)=x^2+y^2-R^2$. Show that

$$
\int_{\mathbb R^2}dx\,dy\,\delta(g(x,y))h(x,y)
=\frac12\int_0^{2\pi}d\theta\,h(R\cos\theta,R\sin\theta).
$$

<details>
<summary><strong>Solution</strong></summary>

Use polar coordinates. Since $dx\,dy=r\,dr\,d\theta$,

$$
\int dx\,dy\,\delta(r^2-R^2)h(r,\theta)
=\int_0^{2\pi}d\theta\int_0^\infty r\,dr\,\delta(r^2-R^2)h(r,\theta).
$$

Set $u=r^2-R^2$, so $du=2r\,dr$. Then

$$
\int_0^\infty r\,dr\,\delta(r^2-R^2)h(r,\theta)
=\frac12 h(R,\theta).
$$

Thus the result is

$$
\frac12\int_0^{2\pi}d\theta\,h(R\cos\theta,R\sin\theta).
$$

Equivalently, the level-set formula gives $d\Sigma=R\,d\theta$ and $|\nabla g|=2R$.

</details>

### Exercise 5: Finite-volume normalization

In a periodic box of volume $V=L^d$, prove

$$
\delta_V^{(d)}(\mathbf x-\mathbf y)
=\frac{1}{V}\sum_{\mathbf k}e^{i\mathbf k\cdot(\mathbf x-\mathbf y)}
$$

acts as the identity kernel on periodic functions whose Fourier series uses momenta $\mathbf k=2\pi\mathbf n/L$.

<details>
<summary><strong>Solution</strong></summary>

Write the periodic Fourier series

$$
f(\mathbf x)=\sum_{\mathbf q}f_{\mathbf q}e^{i\mathbf q\cdot\mathbf x},
\qquad
f_{\mathbf q}=\frac{1}{V}\int_V d^d\mathbf x\,e^{-i\mathbf q\cdot\mathbf x}f(\mathbf x).
$$

Then

$$
\int_V d^d\mathbf y\,\delta_V^{(d)}(\mathbf x-\mathbf y)f(\mathbf y)
=\frac{1}{V}\sum_{\mathbf k}\int_V d^d\mathbf y\,
 e^{i\mathbf k\cdot(\mathbf x-\mathbf y)}
 \sum_{\mathbf q}f_{\mathbf q}e^{i\mathbf q\cdot\mathbf y}.
$$

Using

$$
\int_V d^d\mathbf y\,e^{i(\mathbf q-\mathbf k)\cdot\mathbf y}=V\delta_{\mathbf q,\mathbf k},
$$

the expression becomes

$$
\sum_{\mathbf k}f_{\mathbf k}e^{i\mathbf k\cdot\mathbf x}=f(\mathbf x).
$$

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for delta functions in canonical normalization, propagators, phase space, and perturbative calculations.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for practical uses of delta functions in Green functions, LSZ formulas, Feynman rules, and phase-space integrals.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for momentum-space normalization, scattering theory, principal values, and relativistic delta functions.

### Deeper references

- L. Schwartz, *Théorie des distributions*, for the foundational theory of distributions.
- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for generalized functions and transformation formulas.
- F. G. Friedlander and M. Joshi, *Introduction to the Theory of Distributions*, for a readable mathematical treatment of delta distributions and Green functions.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for distributions, pullbacks, restrictions, and the microlocal conditions behind singular operations.

## Version history

- **2026-06-23:** Initial polished draft. Added delta distributions, Jacobians, constraint deltas, Fourier representations, derivative identities, on-shell phase space, finite-volume deltas, functional deltas, and exercises with solutions.
