---
title: "Fourier Transform Conventions"
description: "A convention-complete guide to Lorentzian, Euclidean, spatial, finite-volume, thermal, and distributional Fourier transforms used in QFT calculations."
sidebar:
  label: "Fourier Conventions"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard Fourier analysis and QFT conventions for propagators, mode expansions, Feynman rules, finite volume, and thermal field theory."
topics:
  - Fourier transforms
  - momentum space
  - propagators
  - delta functions
  - finite volume
  - Matsubara frequencies
canonicalTopics:
  - fourier-transform-conventions
  - momentum-space-normalization
  - qft-analysis
  - distributional-fourier-transform
researchStatus:
  established:
    - "Fourier-transform conventions are settled once signs and measures are fixed; the main challenge is translating consistently between sources."
  active:
    - "In curved spacetime, finite-density real-time systems, gauge theories with constraints, and non-tempered correlation functions, Fourier methods require additional analytic or functional-analytic structure."
---

## Summary

Fourier transforms turn differential equations into algebraic equations and locality into momentum conservation. They also produce half the normalization mistakes in QFT. This page fixes the conventions used in this chapter and gives a translation guide for the most common alternatives.

For Lorentzian spacetime, the default convention is

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x),
\qquad
\int_p\equiv\int\frac{d^4p}{(2\pi)^4}.
$$

For Euclidean and spatial Fourier transforms, the default convention is

$$
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
\int_k\equiv\int\frac{d^dk}{(2\pi)^d}.
$$

These two choices are compatible. The Lorentzian convention is adapted to positive-energy plane waves $e^{-ip\cdot x}=e^{-ip^0t+i\mathbf p\cdot\mathbf x}$, while the Euclidean convention is the standard analysis convention with inverse transform $e^{ik\cdot x}$.

The main rule is simple: never write a momentum-space formula until you know which exponential and which measure produced it.

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/), especially the mostly-minus metric convention, and the basic distributional interpretation of delta functions from [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/).

This page assumes ordinary multivariable calculus, integration by parts, and basic linear algebra. It treats Fourier transforms as operations on functions first, then extends them to distributions.

## Core idea

A Fourier convention is a package deal. It consists of

$$
\text{phase choice} + \text{measure normalization} + \text{derivative rule} + \text{delta normalization}.
$$

Changing one part changes the others. For example, with the Euclidean convention

$$
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
$$

one has

$$
\partial_i f(x)=\int_k ik_i e^{ik\cdot x}\widehat f(k),
$$

and

$$
\delta^{(d)}(x-y)=\int_k e^{ik\cdot(x-y)}.
$$

With the Lorentzian convention

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
$$

one has

$$
\partial_\mu f(x)=\int_p(-ip_\mu)e^{-ip\cdot x}\widetilde f(p),
\qquad
i\partial_\mu\leftrightarrow p_\mu.
$$

The physics is not changed by a convention. But signs in propagators, factors of $2\pi$, and momentum-conservation delta functions absolutely are.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A compact Fourier-transform dictionary showing the transform pair, derivative rule, convolution rule, product rule, and delta-function rule.](/figures/math-toolkit/fourier-dictionary.svg)

<figcaption>

The Euclidean Fourier dictionary: differentiation becomes multiplication by $ik_i$, convolution becomes multiplication, ordinary products become momentum convolutions, and translated delta functions become phases.

</figcaption>
</figure>

## Setup and conventions

Lorentzian spacetime uses coordinates

$$
x^\mu=(t,\mathbf x),
\qquad
p\cdot x=p_\mu x^\mu=p^0t-\mathbf p\cdot\mathbf x,
$$

with mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-).
$$

Thus

$$
e^{-ip\cdot x}=e^{-ip^0t+i\mathbf p\cdot\mathbf x}.
$$

We use the compact measures

$$
\int_p=\int\frac{d^4p}{(2\pi)^4},
\qquad
\int_{\mathbf p}=\int\frac{d^3\mathbf p}{(2\pi)^3},
\qquad
\int d\Pi_p=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
$$

For Euclidean or spatial variables, we write $x,k\in\mathbb R^d$ and

$$
k\cdot x=\sum_{i=1}^d k_i x_i,
\qquad
k^2=k\cdot k.
$$

The Euclidean measure abbreviation is

$$
\int_k=\int\frac{d^dk}{(2\pi)^d}.
$$

When a page uses a different convention, it should say so before the first formula that depends on the choice.

## Convention table

| Setting | Inverse transform | Forward transform | Measure |
|---|---|---|---|
| Lorentzian spacetime | $f(x)=\int_p e^{-ip\cdot x}\widetilde f(p)$ | $\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x)$ | $\int_p=d^4p/(2\pi)^4$ |
| Spatial or Euclidean | $f(x)=\int_k e^{ik\cdot x}\widehat f(k)$ | $\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x)$ | $\int_k=d^dk/(2\pi)^d$ |
| Periodic box | $f(x)=\sum_k e^{ik\cdot x}f_k$ | $f_k=V^{-1}\int_V d^dx\,e^{-ik\cdot x}f(x)$ | $V^{-1}\sum_k$ replaces $\int_k$ |
| Euclidean thermal time | $f(\tau,\mathbf x)=\beta^{-1}\sum_n\int_{\mathbf k}e^{i\omega_n\tau+i\mathbf k\cdot\mathbf x}\widehat f_n(\mathbf k)$ | $\widehat f_n(\mathbf k)=\int_0^\beta d\tau\int d^d\mathbf x\,e^{-i\omega_n\tau-i\mathbf k\cdot\mathbf x}f$ | $\beta^{-1}\sum_n\int_{\mathbf k}$ |

For thermal fields,

$$
\omega_n=\frac{2\pi n}{\beta}\quad\text{for bosons},
\qquad
\omega_n=\frac{(2n+1)\pi}{\beta}\quad\text{for fermions}.
$$

The fermionic frequencies come from antiperiodic boundary conditions in Euclidean time.

## Lorentzian spacetime transforms

The Lorentzian convention is

$$
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x).
$$

The inversion formula follows from

$$
\int_p e^{-ip\cdot(x-y)}=\delta^{(4)}(x-y).
$$

Equivalently,

$$
\int d^4x\,e^{i(p-q)\cdot x}=(2\pi)^4\delta^{(4)}(p-q).
$$

The derivative rules are

$$
\partial_\mu f(x)=\int_p(-ip_\mu)e^{-ip\cdot x}\widetilde f(p),
$$

so

$$
i\partial_\mu\leftrightarrow p_\mu.
$$

Raising the derivative index gives

$$
\partial^\mu f(x)=\int_p(-ip^\mu)e^{-ip\cdot x}\widetilde f(p).
$$

Therefore

$$
\Box f(x)=\partial_\mu\partial^\mu f(x)
=\int_p(-p^2)e^{-ip\cdot x}\widetilde f(p).
$$

For the Klein–Gordon operator,

$$
(\Box+m^2)e^{-ip\cdot x}=-(p^2-m^2)e^{-ip\cdot x}.
$$

This minus sign is the reason the Lorentzian scalar Feynman propagator is conventionally written with a numerator $i$:

$$
\Delta_F(x-y)=\int_p\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i0},
$$

so that

$$
(\Box_x+m^2)\Delta_F(x-y)=-i\delta^{(4)}(x-y).
$$

Some authors absorb factors of $i$ into the definition of the Green function. Always check whether the object called $G_F$, $D_F$, or $\Delta_F$ includes the numerator $i$.

## Spatial transforms in canonical QFT

Canonical quantization often Fourier transforms only the spatial variables. With

$$
f(t,\mathbf x)=\int_{\mathbf p}e^{i\mathbf p\cdot\mathbf x}\widehat f(t,\mathbf p),
\qquad
\widehat f(t,\mathbf p)=\int d^3\mathbf x\,e^{-i\mathbf p\cdot\mathbf x}f(t,\mathbf x),
$$

one has

$$
\nabla f(t,\mathbf x)=\int_{\mathbf p}i\mathbf p\,e^{i\mathbf p\cdot\mathbf x}\widehat f(t,\mathbf p),
$$

and

$$
-\nabla^2\leftrightarrow \mathbf p^2.
$$

The free real scalar field is often expanded as

$$
\phi(x)=\int_{\mathbf p}\frac{1}{\sqrt{2E_{\mathbf p}}}
\left(a_{\mathbf p}e^{-ip\cdot x}+a_{\mathbf p}^\dagger e^{ip\cdot x}\right),
\qquad p^0=E_{\mathbf p}.
$$

This is not the same as a general four-dimensional Fourier transform. It is an on-shell mode expansion: $p^0$ is not integrated independently. The measure and the factors of $2E_{\mathbf p}$ are fixed by the chosen commutation relations and state normalization.

A closely related Lorentz-invariant measure is

$$
\int d\Pi_p
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=\int\frac{d^4p}{(2\pi)^4}\,2\pi\theta(p^0)\delta(p^2-m^2).
$$

Mode expansions and phase-space integrals look similar but use different normalizations. This is a classic source of factor-of-$2E$ accidents.

## Euclidean transforms

For $x,k\in\mathbb R^d$, the Euclidean convention is

$$
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x).
$$

Then

$$
\delta^{(d)}(x-y)=\int_k e^{ik\cdot(x-y)},
$$

and

$$
\int d^dx\,e^{-i(k-q)\cdot x}=(2\pi)^d\delta^{(d)}(k-q).
$$

The derivative rules are

$$
\partial_i f(x)=\int_k ik_i e^{ik\cdot x}\widehat f(k),
$$

and, after Fourier transforming,

$$
\widehat{\partial_i f}(k)=ik_i\widehat f(k).
$$

The Laplacian gives

$$
\widehat{-\Delta f}(k)=k^2\widehat f(k).
$$

Thus the Euclidean massive Green function

$$
G_E(x-y)=\int_k\frac{e^{ik\cdot(x-y)}}{k^2+m^2}
$$

satisfies

$$
(-\Delta_x+m^2)G_E(x-y)=\delta^{(d)}(x-y).
$$

This clean positivity is one reason Euclidean conventions are so convenient in statistical field theory, heat kernels, lattice QFT, and Gaussian path integrals.

## Products and convolutions

For Euclidean or spatial transforms, define convolution by

$$
(f*g)(x)=\int d^dy\,f(x-y)g(y).
$$

Then

$$
\widehat{f*g}(k)=\widehat f(k)\widehat g(k).
$$

The product in position space becomes convolution in momentum space:

$$
\widehat{fg}(k)=\int_q\widehat f(q)\widehat g(k-q).
$$

The asymmetric $2\pi$ convention has a benefit: convolution does not carry extra $2\pi$ factors. The price is that the inverse transform carries all factors of $(2\pi)^{-d}$.

For $n$ functions,

$$
\widehat{f_1\cdots f_n}(k)
=\int_{q_1}\cdots\int_{q_n}
(2\pi)^d\delta^{(d)}(k-q_1-\cdots-q_n)
\widehat f_1(q_1)\cdots\widehat f_n(q_n).
$$

This is the position-space origin of momentum conservation at interaction vertices.

## Translation invariance and momentum conservation

If a two-point function is translationally invariant,

$$
G(x,y)=G(x-y),
$$

then its momentum-space form is diagonal:

$$
G(p,q)=(2\pi)^d\delta^{(d)}(p+q)\widehat G(p)
$$

for Euclidean conventions where the two external Fourier factors are usually $e^{-ip\cdot x}$ and $e^{-iq\cdot y}$.

For an $n$-point Lorentzian correlator, translation invariance gives

$$
\widetilde G(p_1,\ldots,p_n)
=(2\pi)^4\delta^{(4)}(p_1+\cdots+p_n)\,\bar G(p_1,\ldots,p_n).
$$

The reduced correlator $\bar G$ is the object with the overall momentum-conservation delta stripped off.

In Feynman rules, one often assigns all external momenta as incoming. Then a vertex from a local interaction produces

$$
(2\pi)^4\delta^{(4)}\!\left(\sum_i p_i\right).
$$

If some particles are physically outgoing, their momenta appear with the opposite sign in an all-incoming convention. Many sign errors in scattering amplitudes are not physics errors; they are bookkeeping errors in this convention.

## Fourier transforms of distributions

Fourier transforms extend naturally to tempered distributions. In Euclidean convention, the Fourier transform of a tempered distribution $T$ is defined by duality:

$$
\langle\widehat T,\varphi\rangle
=\langle T,\widehat\varphi\rangle
$$

up to the convention-dependent placement of inverse transforms. Operationally, the identities below are the ones used most often:

$$
\widehat{\delta^{(d)}(x)}(k)=1,
\qquad
\widehat{1}(k)=(2\pi)^d\delta^{(d)}(k),
$$

$$
\widehat{\partial_i T}(k)=ik_i\widehat T(k),
\qquad
\widehat{x_iT}(k)=i\partial_{k_i}\widehat T(k).
$$

For the shifted delta distribution,

$$
\widehat{\delta^{(d)}(x-a)}(k)=e^{-ik\cdot a}.
$$

For a plane wave,

$$
\widehat{e^{iq\cdot x}}(k)=(2\pi)^d\delta^{(d)}(k-q).
$$

These are distributional identities. The expression $\int d^dx\,e^{-ik\cdot x}$ means $(2\pi)^d\delta^{(d)}(k)$ only after smearing in $k$.

A useful one-dimensional singular transform is

$$
\widehat{\operatorname{PV}\frac{1}{x}}(k)=-i\pi\operatorname{sgn}(k)
$$

with the Euclidean convention $\widehat f(k)=\int dx\,e^{-ikx}f(x)$. This identity is closely related to

$$
\frac{1}{x\pm i0}=\operatorname{PV}\frac{1}{x}\mp i\pi\delta(x).
$$

## Reality, parity, and complex conjugation

If $f(x)$ is real and the Euclidean transform convention is used, then

$$
\widehat f(-k)=\widehat f(k)^*.
$$

The same relation holds for the Lorentzian transform:

$$
\widetilde f(-p)=\widetilde f(p)^*
$$

when $f(x)$ is an ordinary real function or real distribution.

If $f$ is even, $f(-x)=f(x)$, then $\widehat f(k)$ is even. If $f$ is odd, $f(-x)=-f(x)$, then $\widehat f(k)$ is odd. For real even functions, the Fourier transform is real and even; for real odd functions, it is imaginary and odd.

For quantum fields, one must distinguish reality of the field from reality of the Fourier coefficient. A real scalar field satisfies $\phi^\dagger(x)=\phi(x)$, but its annihilation and creation operators are independent operator coefficients related by Hermitian conjugation, not by the simple classical rule $\widehat\phi(-p)=\widehat\phi(p)^*$.

## Finite volume

Put a system in a periodic box of side length $L$ and volume $V=L^d$. The allowed momenta are

$$
k_i=\frac{2\pi n_i}{L},
\qquad n_i\in\mathbb Z.
$$

The finite-volume transform is

$$
f(x)=\sum_k e^{ik\cdot x}f_k,
\qquad
f_k=\frac{1}{V}\int_V d^dx\,e^{-ik\cdot x}f(x).
$$

The orthogonality and completeness relations are

$$
\int_V d^dx\,e^{i(k-q)\cdot x}=V\delta_{kq},
$$

and

$$
\frac{1}{V}\sum_k e^{ik\cdot(x-y)}=\delta_V^{(d)}(x-y).
$$

The continuum dictionary is

$$
\frac{1}{V}\sum_k\longrightarrow\int\frac{d^dk}{(2\pi)^d},
\qquad
V\delta_{kq}\longrightarrow(2\pi)^d\delta^{(d)}(k-q).
$$

Finite volume is not just a regulator. It is often the cleanest way to understand why continuum delta functions should not be squared and how density-of-states factors arise.

## Thermal Euclidean transforms

At temperature $T=1/\beta$, Euclidean time is compact:

$$
\tau\sim\tau+\beta.
$$

Bosonic fields are periodic and fermionic fields are antiperiodic:

$$
\phi(\tau+\beta,\mathbf x)=\phi(\tau,\mathbf x),
\qquad
\psi(\tau+\beta,\mathbf x)=-\psi(\tau,\mathbf x).
$$

The corresponding Matsubara frequencies are

$$
\omega_n=\frac{2\pi n}{\beta}\quad\text{for bosons},
\qquad
\omega_n=\frac{(2n+1)\pi}{\beta}\quad\text{for fermions}.
$$

For a bosonic field,

$$
\phi(\tau,\mathbf x)
=\frac{1}{\beta}\sum_{n\in\mathbb Z}\int_{\mathbf k}
 e^{i\omega_n\tau+i\mathbf k\cdot\mathbf x}\phi_n(\mathbf k),
$$

with

$$
\phi_n(\mathbf k)=\int_0^\beta d\tau\int d^d\mathbf x\,
 e^{-i\omega_n\tau-i\mathbf k\cdot\mathbf x}\phi(\tau,\mathbf x).
$$

The Euclidean thermal delta function is

$$
\delta_\beta(\tau-\tau')\delta^{(d)}(\mathbf x-\mathbf x')
=\frac{1}{\beta}\sum_n\int_{\mathbf k}
 e^{i\omega_n(\tau-\tau')+i\mathbf k\cdot(\mathbf x-\mathbf x')}.
$$

For fermions, the same formula uses fermionic frequencies and acts on antiperiodic test functions.

## Wick rotation and Euclidean momenta

A full Wick-rotation argument requires analytic hypotheses and pole prescriptions. At the convention level, the key scalar dictionary is

$$
\frac{i}{p^2-m^2+i0}
\quad\longrightarrow\quad
\frac{1}{p_E^2+m^2},
$$

where

$$
p_E^2=(p_E^0)^2+\mathbf p^2.
$$

The Lorentzian quadratic operator is

$$
\Box+m^2\leftrightarrow -(p^2-m^2),
$$

while the Euclidean quadratic operator is

$$
-\Delta_E+m^2\leftrightarrow p_E^2+m^2.
$$

For the scalar action, the usual continuation $t=-i\tau$ turns the oscillatory factor $e^{iS_M}$ into a damped factor $e^{-S_E}$, with

$$
S_E=\frac12\int d^d x_E\,
\left[(\partial_E\phi)^2+m^2\phi^2\right]
$$

for the free scalar. The $i0$ prescription tells the contour how to avoid poles during this rotation. Without it, Wick rotation is not a convention; it is a wish.

## Alternative conventions and translation

Many sources use one of the following alternatives.

| Alternative | Common form | Translation |
|---|---|---|
| Opposite phase | $f(x)=\int_p e^{ip\cdot x}f_+(p)$ | $f_+(p)=\widetilde f(-p)$ relative to the Lorentzian convention here. |
| Symmetric $2\pi$ split | $f(x)=(2\pi)^{-d/2}\int d^dk\,e^{ikx}f_s(k)$ | $f_s(k)=(2\pi)^{-d/2}\widehat f(k)$ relative to the Euclidean convention here. |
| No $2\pi$ in inverse | $f(x)=\int d^dk\,e^{ikx}f_0(k)$ | $f_0(k)=\widehat f(k)/(2\pi)^d$. |
| Mostly-plus metric | $p^2=-(p^0)^2+\mathbf p^2$ | Rewrite $p\cdot x$ and the Klein–Gordon denominator before comparing propagators. |

The safest translation procedure is:

1. write the formula as an integral with explicit exponentials and measures;
2. translate the exponential phase;
3. translate the metric convention if Lorentzian;
4. translate the measure normalization;
5. only then simplify notation.

Trying to translate only the final denominator is one of the most common sources of sign errors.

## Quick lookup identities

For Euclidean or spatial transforms:

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
f(x)=\int_k e^{ik\cdot x}\widehat f(k).
$$

Then

$$
\widehat{\partial_i f}=ik_i\widehat f,
\qquad
\widehat{-\Delta f}=k^2\widehat f,
$$

$$
\widehat{f*g}=\widehat f\,\widehat g,
\qquad
\widehat{fg}(k)=\int_q\widehat f(q)\widehat g(k-q),
$$

$$
\widehat{\delta(x-a)}=e^{-ik\cdot a},
\qquad
\widehat{1}=(2\pi)^d\delta(k),
$$

and

$$
\int_k e^{ik\cdot(x-y)}=\delta^{(d)}(x-y).
$$

For Lorentzian transforms:

$$
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x),
\qquad
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
$$

$$
i\partial_\mu\leftrightarrow p_\mu,
\qquad
\Box\leftrightarrow -p^2,
$$

and

$$
\int_p e^{-ip\cdot(x-y)}=\delta^{(4)}(x-y).
$$

## Common pitfalls

**Mixing Lorentzian and Euclidean inverse phases.** The Lorentzian inverse uses $e^{-ip\cdot x}$; the Euclidean inverse uses $e^{ik\cdot x}$. This is intentional, not a typo.

**Dropping the measure.** The symbol $\int_p$ includes $(2\pi)^{-4}$. The symbol $\int_{\mathbf p}$ includes $(2\pi)^{-3}$. Write the measure explicitly when comparing sources.

**Confusing a four-dimensional transform with an on-shell mode expansion.** A mode expansion integrates over $\mathbf p$ and sets $p^0=E_{\mathbf p}$. A four-dimensional Fourier transform integrates over $p^0$ independently.

**Forgetting that derivatives transform differently under different inverse phases.** In Euclidean convention, $\partial_i\leftrightarrow ik_i$. In Lorentzian convention, $\partial_\mu\leftrightarrow -ip_\mu$ in the inverse transform, or $i\partial_\mu\leftrightarrow p_\mu$.

**Treating $\int d^dx\,e^{-ik\cdot x}$ as an ordinary integral.** It is the distribution $(2\pi)^d\delta^{(d)}(k)$.

**Losing the finite-volume dictionary.** The replacements $V^{-1}\sum_k\to\int_k$ and $V\delta_{kq}\to(2\pi)^d\delta(k-q)$ are a pair. Do not use one without the other.

**Ignoring the $i0$ prescription before Wick rotation.** The prescription is what tells the contour where the poles are.

## Relations to other pages

This page is the convention companion to [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/). The distributional foundations are explained in [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), while the [chapter overview](/math-toolkit/analysis-distributions-fourier/) explains how Fourier methods fit into the broader Analysis, Distributions, and Fourier Methods chapter.

Later pages on convolution, principal values, Green functions, propagators, Gaussian integrals, loop integrals, finite temperature, and spectral representations should use these conventions unless they explicitly state a different convention.

## Research status

Fourier analysis on Euclidean space and on tempered distributions is established mathematics, and the QFT conventions listed here are standard once the signs and measures are fixed.

The delicate frontiers arise when Fourier transforms are used outside their simplest domain: non-tempered distributions, real-time finite-density correlators, curved spacetime without translation invariance, gauge theories with constrained variables, nonperturbative spectral problems, and Lorentzian analytic continuation. In those contexts, the formulas here remain local tools, but additional analytic structure is required.

## Exercises

### Exercise 1: Inversion with the Euclidean convention

Starting from

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
$$

show that

$$
f(x)=\int_k e^{ik\cdot x}\widehat f(k)
$$

provided

$$
\int_k e^{ik\cdot(x-y)}=\delta^{(d)}(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the forward transform into the inverse transform:

$$
\int_k e^{ik\cdot x}\widehat f(k)
=\int_k e^{ik\cdot x}\int d^dy\,e^{-ik\cdot y}f(y).
$$

Interchanging the integrals gives

$$
\int d^dy\,\left[\int_k e^{ik\cdot(x-y)}\right]f(y)
=\int d^dy\,\delta^{(d)}(x-y)f(y)
=f(x).
$$

</details>

### Exercise 2: Derivative rule

Using the Euclidean convention, prove

$$
\widehat{\partial_i f}(k)=ik_i\widehat f(k)
$$

for a smooth rapidly decreasing function $f$.

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\widehat{\partial_i f}(k)
=\int d^dx\,e^{-ik\cdot x}\partial_i f(x).
$$

Integrating by parts and dropping the boundary term because $f$ is rapidly decreasing,

$$
\int d^dx\,e^{-ik\cdot x}\partial_i f(x)
=-\int d^dx\,\partial_i(e^{-ik\cdot x})f(x).
$$

Since $\partial_i e^{-ik\cdot x}=-ik_i e^{-ik\cdot x}$,

$$
\widehat{\partial_i f}(k)
=ik_i\int d^dx\,e^{-ik\cdot x}f(x)
=ik_i\widehat f(k).
$$

</details>

### Exercise 3: Convolution theorem

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

Compute directly:

$$
\widehat{f*g}(k)
=\int d^dx\,e^{-ik\cdot x}\int d^dy\,f(x-y)g(y).
$$

Let $z=x-y$, so $x=z+y$ and $d^dx=d^dz$. Then

$$
\widehat{f*g}(k)
=\int d^dy\int d^dz\,e^{-ik\cdot(z+y)}f(z)g(y).
$$

The integral factorizes:

$$
\left(\int d^dz\,e^{-ik\cdot z}f(z)\right)
\left(\int d^dy\,e^{-ik\cdot y}g(y)\right)
=\widehat f(k)\widehat g(k).
$$

</details>

### Exercise 4: Lorentzian Klein–Gordon sign

Using

$$
\Delta_F(x-y)=\int_p\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i0},
$$

show that

$$
(\Box_x+m^2)\Delta_F(x-y)=-i\delta^{(4)}(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

The plane wave satisfies

$$
\Box_x e^{-ip\cdot(x-y)}=-p^2 e^{-ip\cdot(x-y)}.
$$

Therefore

$$
(\Box_x+m^2)e^{-ip\cdot(x-y)}=-(p^2-m^2)e^{-ip\cdot(x-y)}.
$$

Acting on the propagator gives

$$
(\Box_x+m^2)\Delta_F(x-y)
=\int_p\frac{i[-(p^2-m^2)]e^{-ip\cdot(x-y)}}{p^2-m^2+i0}.
$$

As a distribution, the ratio is $1$ away from the pole with the prescribed boundary value, so

$$
(\Box_x+m^2)\Delta_F(x-y)
=-i\int_p e^{-ip\cdot(x-y)}
=-i\delta^{(4)}(x-y).
$$

</details>

### Exercise 5: Finite-volume continuum limit

Show that the finite-volume relations

$$
\frac{1}{V}\sum_k e^{ik\cdot(x-y)}=\delta_V^{(d)}(x-y),
\qquad
\int_V d^dx\,e^{i(k-q)\cdot x}=V\delta_{kq}
$$

lead to

$$
\int_k e^{ik\cdot(x-y)}=\delta^{(d)}(x-y),
\qquad
\int d^dx\,e^{i(k-q)\cdot x}=(2\pi)^d\delta^{(d)}(k-q)
$$

as $V\to\infty$.

<details>
<summary><strong>Solution</strong></summary>

In a periodic box, momenta are spaced by $\Delta k_i=2\pi/L$. Hence

$$
\frac{1}{V}\sum_k
=\prod_{i=1}^d\frac{1}{L}\sum_{n_i}
\longrightarrow
\prod_{i=1}^d\int\frac{dk_i}{2\pi}
=\int\frac{d^dk}{(2\pi)^d}.
$$

Thus the completeness relation becomes

$$
\int_k e^{ik\cdot(x-y)}=\delta^{(d)}(x-y).
$$

The orthogonality relation is the dual statement. Since

$$
V\delta_{kq}
$$

has the same action in sums as

$$
(2\pi)^d\delta^{(d)}(k-q)
$$

has in integrals, the continuum replacement is

$$
V\delta_{kq}\to(2\pi)^d\delta^{(d)}(k-q).
$$

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for Fourier conventions, relativistic normalization, propagators, and momentum-space perturbation theory.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for practical momentum-space Feynman rules, phase space, dimensional regularization conventions, and propagator signs.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for scattering normalization, Lorentz-invariant phase space, and the relation between Fourier transforms and the $S$-matrix.
- A. Zee, *Quantum Field Theory in a Nutshell*, for a physicist-friendly use of Fourier transforms across path integrals, propagators, and condensed-matter examples.

### Deeper references

- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for Fourier transforms of generalized functions.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for distributional Fourier transforms, singular support, and wavefront sets.
- E. M. Stein and R. Shakarchi, *Fourier Analysis: An Introduction*, for a clean mathematical treatment of Fourier analysis and tempered distributions at an accessible level.
- M. Le Bellac, *Thermal Field Theory*, for Matsubara conventions and real-time/imaginary-time finite-temperature transforms.

## Version history

- **2026-06-23:** Initial polished draft. Fixed Lorentzian, Euclidean, spatial, finite-volume, thermal, convolution, distributional, and Wick-rotation Fourier conventions, with translation rules and exercises.
