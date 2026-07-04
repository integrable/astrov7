---
title: "Saddle Points"
description: "Explains saddle-point, stationary-phase, and steepest-descent methods for complex integrals and QFT, including Gaussian fluctuations, Morse phases, contour deformation, thimbles, Stokes phenomena, and common sign mistakes."
sidebar:
  label: "Saddle Points"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard references on asymptotic analysis, complex analysis, WKB methods, functional integrals, instantons, and QFT, including Watson, Olver, Bender–Orszag, Wong, Bleistein–Handelsman, Fedoryuk, Berry, Delabaere–Pham, Witten, Coleman, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, and Mariño."
topics:
  - saddle points
  - stationary phase
  - steepest descent
  - asymptotic expansion
  - Gaussian fluctuations
  - Morse index
  - Lefschetz thimbles
  - Stokes phenomenon
  - instantons
  - semiclassical expansion
canonicalTopics:
  - saddle-point-method
  - stationary-phase-method
  - steepest-descent-method
  - asymptotic-expansion
  - gaussian-fluctuation
  - morse-index
  - lefschetz-thimble
  - stokes-phenomenon
  - instanton
  - semiclassical-expansion
researchStatus:
  established:
    - "The saddle-point method, stationary phase, steepest descent, Gaussian fluctuation determinants, and Stokes phenomena are standard tools of asymptotic analysis and mathematical physics."
    - "Semiclassical QFT uses the infinite-dimensional version: expand the action around classical solutions and integrate Gaussian fluctuations, with zero modes and negative modes treated separately."
  active:
    - "Modern work uses complex saddles, Lefschetz thimbles, resurgence, Picard–Lefschetz theory, and numerical contour deformation to analyze real-time path integrals, sign problems, nonperturbative effects, and large-order behavior."
---

## Summary

Saddle-point methods estimate integrals whose integrand has a large parameter in the exponent. The basic shape is

$$
I(\lambda)=\int_C dz\,a(z)e^{-\lambda S(z)},
\qquad
\lambda\to+\infty,
$$

or, for oscillatory integrals,

$$
I(\lambda)=\int_C dz\,a(z)e^{i\lambda f(z)}.
$$

The leading contributions come from points where the exponent stops changing to first order:

$$
S'(z_*)=0
\qquad\text{or}\qquad
f'(z_*)=0.
$$

These are called **saddle points** or **critical points**. The name is literal: in the complex plane, $\operatorname{Re}S$ and $\operatorname{Im}S$ are harmonic functions away from singularities, so an isolated nondegenerate critical point is not a local minimum of both. It is a saddle. The art is to deform the integration contour through the saddle along directions where the exponential decays.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Two-panel diagram showing steepest-descent and steepest-ascent directions near a complex saddle, and thimble decomposition with Stokes data.](/figures/math-toolkit/complex-saddle-thimbles.svg)

<figcaption>

For $e^{-\lambda S}$, a steepest-descent contour through $z_*$ keeps $\operatorname{Im}S$ constant and makes $\operatorname{Re}S$ increase away from the saddle. With several saddles, the decomposition of the original contour into steepest-descent cycles can jump across Stokes walls.

</figcaption>
</figure>

In QFT, this innocent-looking technique becomes the semiclassical expansion:

$$
Z=\int \mathcal D\phi\,e^{-S[\phi]/\hbar}
\sim
\sum_{\phi_{\mathrm{cl}}}
e^{-S[\phi_{\mathrm{cl}}]/\hbar}
\frac{1}{\sqrt{\det' S^{(2)}[\phi_{\mathrm{cl}}]}}
\times
(\text{zero modes, phases, interactions}).
$$

The finite-dimensional saddle method is therefore not optional background. It is the local model for WKB approximations, instantons, soliton quantization, tunneling amplitudes, thermal bounces, large-$N$ limits, matrix models, localization, and the large-order behavior of perturbation theory.

The shortest slogan is

$$
\text{saddle points turn large parameters into Gaussian integrals.}
$$

The longer slogan is more useful:

$$
\text{saddles matter only together with the contour that reaches them.}
$$

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), and [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/). It also helps to know [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/), and [Jacobian and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/).

This page uses the Euclidean-looking convention $e^{-\lambda S}$ for steepest descent and the oscillatory convention $e^{i\lambda f}$ for stationary phase. The two are related by analytic continuation, but they should not be mentally blurred. That blur is a remarkably efficient sign-error machine.

## The real one-dimensional prototype

Start with a real integral

$$
I(\lambda)=\int_{-\infty}^{\infty} dx\,a(x)e^{-\lambda S(x)},
\qquad
\lambda\gg1,
$$

where $S$ has a nondegenerate minimum at $x_*$:

$$
S'(x_*)=0,
\qquad
S''(x_*)>0.
$$

Expanding near $x_*$ gives

$$
S(x)=S_*+\frac12 S''_*(x-x_*)^2+\cdots,
\qquad
 a(x)=a_*+\cdots.
$$

The leading approximation is the Gaussian integral

$$
I(\lambda)
\sim
a_* e^{-\lambda S_*}
\int_{-\infty}^{\infty} dx\,
\exp\left[-\frac{\lambda}{2}S''_*(x-x_*)^2\right].
$$

Thus

$$
I(\lambda)
\sim
a_*e^{-\lambda S_*}
\sqrt{\frac{2\pi}{\lambda S''_*}}.
$$

The correction series is obtained by expanding $a(x)$ and the cubic, quartic, and higher terms in $S(x)$, then evaluating Gaussian moments. It is usually an asymptotic expansion, not a convergent Taylor series in $1/\lambda$.

The same local computation survives in more dimensions. If $x\in\mathbb R^n$ and $H_{ij}=\partial_i\partial_jS(x_*)$ is positive definite, then

$$
I(\lambda)
\sim
(2\pi)^{n/2}\lambda^{-n/2}
\frac{a(x_*)e^{-\lambda S(x_*)}}{\sqrt{\det H}}.
$$

This formula is the finite-dimensional ancestor of the one-loop determinant in Euclidean field theory.

## Stationary phase and the Morse index

For oscillatory integrals, decay is not the starting point. Cancellation is. Consider

$$
I(\lambda)=\int_{\mathbb R^n}d^nx\,a(x)e^{i\lambda f(x)},
\qquad
\lambda\to+\infty,
$$

where $f$ is real and has a nondegenerate critical point $x_*$. Let $H_{ij}=\partial_i\partial_jf(x_*)$. If $H$ has $n_+$ positive eigenvalues and $n_-$ negative eigenvalues, define the signature

$$
\sigma=n_+-n_-.
$$

Then the leading stationary-phase approximation is

$$
I(\lambda)
\sim
\left(\frac{2\pi}{\lambda}\right)^{n/2}
\frac{a(x_*)e^{i\lambda f(x_*)}e^{i\pi\sigma/4}}{\sqrt{|\det H|}}.
$$

The phase $e^{i\pi\sigma/4}$ is not decoration. It is the product of one-dimensional Fresnel phases:

$$
\int_{-\infty}^{\infty}dx\,e^{i\lambda h x^2/2}
=
e^{i\pi\operatorname{sgn}(h)/4}
\sqrt{\frac{2\pi}{\lambda |h|}},
\qquad
\lambda>0.
$$

In real-time QFT, this is one reason Gaussian fluctuations carry phases. The other reason is that the contour is fixed by the $i\epsilon$ prescription, not by wishful rotation to a positive quadratic form.

## Complex steepest descent

Now return to

$$
I(\lambda)=\int_C dz\,a(z)e^{-\lambda S(z)},
$$

where $S$ and $a$ are holomorphic in the relevant region, except perhaps at isolated singularities or cuts. Suppose $z_*$ is a nondegenerate critical point:

$$
S'(z_*)=0,
\qquad
S''(z_*)\ne0.
$$

Near $z_*$,

$$
S(z)=S_*+\frac12S''_*(z-z_*)^2+\cdots.
$$

Write

$$
S''_*=|S''_*|e^{i\alpha},
\qquad
z-z_*=re^{i\theta}.
$$

The quadratic contribution is

$$
\frac12 S''_*(z-z_*)^2
=\frac12 |S''_*|r^2 e^{i(\alpha+2\theta)}.
$$

For $e^{-\lambda S}$, the steepest-descent directions are those for which this quadratic term is real and positive:

$$
\alpha+2\theta=2\pi k,
\qquad
k\in\mathbb Z.
$$

Along those directions, $\operatorname{Im}S$ is constant and $\operatorname{Re}S$ increases away from the saddle. The steepest-ascent directions instead satisfy

$$
\alpha+2\theta=(2k+1)\pi.
$$

A local steepest-descent coordinate $u$ can be chosen so that

$$
S(z(u))=S_*+\frac12 u^2+\cdots.
$$

Then the leading contribution has the form

$$
I_*
\sim
n_*\,a(z_*)e^{-\lambda S_*}
\sqrt{\frac{2\pi}{\lambda S''_*}},
$$

where the square-root phase and the integer coefficient $n_*$ are not determined by local Taylor expansion alone. They encode how the original contour $C$ is decomposed into steepest-descent cycles. This is the practical reason contour data matter.

## Thimbles: the clean contour language

A useful modern language is **Lefschetz thimbles**. For $e^{-\lambda S(z)}$, the downward flow equation is commonly written schematically as

$$
\frac{dz}{d\tau}=\overline{\frac{\partial S}{\partial z}},
$$

with signs depending on whether one wants increasing or decreasing $\operatorname{Re}S$ as $\tau$ increases. The important properties are

$$
\frac{d}{d\tau}\operatorname{Im}S=0,
\qquad
\frac{d}{d\tau}\operatorname{Re}S\ge0
$$

for the descent direction away from the saddle. The **thimble** $\mathcal J_*$ is the steepest-descent cycle attached to $z_*$. Its dual upward cycle $\mathcal K_*$ determines whether the original contour intersects it. One writes morally

$$
C=\sum_* n_*\mathcal J_*,
\qquad
n_*\in\mathbb Z.
$$

Then

$$
I(\lambda)=\sum_* n_*\int_{\mathcal J_*} dz\,a(z)e^{-\lambda S(z)}.
$$

This formula is powerful because it separates two questions that are often mixed up:

1. What is the local expansion around a saddle?
2. Does the original contour actually contain that saddle contribution?

The second question is topological and global. A saddle with a beautiful local expansion contributes nothing if its thimble has zero intersection number with the original contour.

## Stokes phenomena

Suppose there are two saddles $z_1$ and $z_2$. Their relative contribution is controlled by

$$
\exp\{-\lambda(S_1-S_2)\}.
$$

For $\lambda>0$, dominance changes when

$$
\operatorname{Re}(S_1-S_2)=0.
$$

The contour decomposition itself can jump when steepest-descent and steepest-ascent cycles connect saddles. This occurs on Stokes walls, often characterized by

$$
\operatorname{Im}(S_1-S_2)=0,
$$

with additional conditions on the flow. Terminology varies: some communities call the equal-magnitude walls Stokes lines and the cycle-jumping walls anti-Stokes lines, or vice versa. The invariant content is better than the vocabulary:

$$
\text{one condition controls relative size, another controls thimble jumps.}
$$

Across a Stokes wall, a saddle contribution can turn on or off discontinuously in an asymptotic representation even though the original integral remains smooth. The asymptotic bookkeeping jumps; the exact function does not.

This matters in QFT because different saddles often represent different semiclassical sectors: perturbative vacuum, instantons, bounces, complex instantons, monopoles, flux sectors, or large-$N$ eigenvalue configurations.

## The field-theory saddle expansion

The field-theory version begins with a functional integral. In Euclidean signature,

$$
Z[J]=\int \mathcal D\phi\,
\exp\left[-\frac{1}{\hbar}S_E[\phi]+\frac{1}{\hbar}\int d^dx\,J(x)\phi(x)\right].
$$

A saddle $\phi_{\mathrm{cl}}$ satisfies

$$
\left.\frac{\delta S_E}{\delta\phi(x)}\right|_{\phi_{\mathrm{cl}}}=J(x).
$$

Set

$$
\phi=\phi_{\mathrm{cl}}+\eta.
$$

Then

$$
S_E[\phi]
=S_E[\phi_{\mathrm{cl}}]
+\frac12\int d^dx\,d^dy\,\eta(x)K(x,y)\eta(y)
+S_{\mathrm{int}}[\eta],
$$

where

$$
K(x,y)=
\left.
\frac{\delta^2 S_E}{\delta\phi(x)\delta\phi(y)}
\right|_{\phi_{\mathrm{cl}}}.
$$

Ignoring zero modes and interactions for the moment,

$$
Z[J]
\sim
\sum_{\phi_{\mathrm{cl}}}
\exp\left[-\frac{1}{\hbar}S_E[\phi_{\mathrm{cl}}]
+\frac{1}{\hbar}\int J\phi_{\mathrm{cl}}\right]
(\det K)^{-1/2}.
$$

Several qualifications are not optional:

- **Zero modes** are not included in $\det K$. They are collective coordinates and must be integrated with the correct measure.
- **Negative modes** indicate an instability direction. In false-vacuum decay, a single negative mode is essential and produces an imaginary part of the energy.
- **Gauge zero modes** are gauge redundancy, not physical moduli. They require gauge fixing and Faddeev–Popov determinants.
- **Complex saddles** require contour data. The formal equation $\delta S=0$ is not enough.

The prime in

$$
(\det' K)^{-1/2}
$$

means “remove modes that should not be treated as ordinary Gaussian variables.” The prime is small, but it carries a lot of physics.

## Degenerate saddles and uniform approximations

The previous formulas assume the Hessian is nonzero. If

$$
S''(z_*)=0,
$$

the Gaussian approximation fails. Degenerate saddles require different scalings. A simple model is

$$
I(\lambda)=\int_C dz\,e^{-\lambda z^m/m}.
$$

The saddle width scales as

$$
z\sim \lambda^{-1/m},
$$

not $\lambda^{-1/2}$. When two saddles merge, Airy-type approximations often replace separate Gaussian saddle expansions. This is why Airy functions appear near turning points in WKB and why special functions are not random visitors in asymptotics; they are local normal forms for degenerate critical behavior.

In physics language, a degenerate saddle often signals a soft mode, a critical point, a caustic, a phase transition, or a change in the number of relevant semiclassical contributions.

## Common pitfalls

The most common mistake is to find all solutions of $S'(z)=0$ and assume all of them contribute. Saddles contribute through contours, not through wishful thinking.

A second mistake is to use a Gaussian formula without checking whether the Hessian has zero modes or negative modes. In field theory, this often gives nonsense determinants.

A third mistake is to rotate a contour across singularities. Cauchy’s theorem permits contour deformation only when the crossed region is analytic and endpoint contributions are controlled.

A fourth mistake is to drop the phase of the square root. In oscillatory integrals, the Morse phase is often the leading physically relevant information.

A fifth mistake is to confuse exact equalities with asymptotic expansions. A saddle expansion usually means

$$
I(\lambda)\sim e^{-\lambda S_*}\sum_{n=0}^{\infty}c_n\lambda^{-n-1/2},
$$

not that the series converges to $I(\lambda)$.

## Exercises

### Exercise 1: Gaussian saddle with a quartic correction

For $g>0$, find the first two terms of the large-$\lambda$ expansion of

$$
I(\lambda)=\int_{-\infty}^{\infty}dx\,
\exp\left[-\lambda\left(\frac{x^2}{2}+\frac{g x^4}{4}\right)\right].
$$

<details><summary><strong>Solution</strong></summary>

The saddle is at $x=0$. Rescale $x=y/\sqrt\lambda$:

$$
I(\lambda)=\lambda^{-1/2}\int_{-\infty}^{\infty}dy\,
\exp\left[-\frac{y^2}{2}-\frac{g y^4}{4\lambda}\right].
$$

Expand the quartic exponential:

$$
I(\lambda)=\lambda^{-1/2}\int dy\,e^{-y^2/2}
\left(1-\frac{g y^4}{4\lambda}+O(\lambda^{-2})\right).
$$

Using

$$
\int_{-\infty}^{\infty}dy\,e^{-y^2/2}=\sqrt{2\pi},
\qquad
\int_{-\infty}^{\infty}dy\,y^4e^{-y^2/2}=3\sqrt{2\pi},
$$

we get

$$
I(\lambda)
\sim
\sqrt{\frac{2\pi}{\lambda}}
\left(1-\frac{3g}{4\lambda}+O(\lambda^{-2})\right).
$$

</details>

### Exercise 2: The one-dimensional stationary-phase phase

Show that, with the usual $i0$ damping understood,

$$
\int_{-\infty}^{\infty}dx\,e^{i\lambda h x^2/2}
=e^{i\pi\operatorname{sgn}(h)/4}
\sqrt{\frac{2\pi}{\lambda |h|}},
\qquad
\lambda>0.
$$

<details><summary><strong>Solution</strong></summary>

For $h>0$, insert a convergence factor $e^{-\epsilon x^2/2}$ and take $\epsilon\to0^+$:

$$
\int dx\,e^{-(\epsilon-i\lambda h)x^2/2}
=\sqrt{\frac{2\pi}{\epsilon-i\lambda h}}.
$$

As $\epsilon\to0^+$,

$$
\epsilon-i\lambda h\to \lambda h e^{-i\pi/2},
$$

so

$$
\sqrt{\frac{1}{\epsilon-i\lambda h}}
\to
(\lambda h)^{-1/2}e^{i\pi/4}.
$$

This gives the $h>0$ result. For $h<0$, the argument approaches $+i\lambda |h|$, giving $e^{-i\pi/4}$. Combining the two cases yields the stated formula.

</details>

### Exercise 3: Which saddle contributes?

Consider

$$
I(\lambda)=\int_{-\infty}^{\infty}dx\,e^{-\lambda(x^2+1)}.
$$

The exponent has one real saddle at $x=0$. Now view the same integrand as an entire function of $z$ and solve $S'(z)=0$ in the complex plane. Does the complex viewpoint create additional saddle contributions?

<details><summary><strong>Solution</strong></summary>

Here

$$
S(z)=z^2+1,
\qquad
S'(z)=2z,
$$

so the only saddle is still $z=0$. More importantly, even in examples with additional complex saddles, one must check the contour decomposition. A saddle contributes only if the original contour has nonzero intersection with the corresponding upward cycle. The list of critical points is not the same as the list of contributions.

</details>

## References

Good mathematical references include Watson, Olver, Bender–Orszag, Wong, Bleistein–Handelsman, and Fedoryuk. Berry’s work is a classic source for Stokes smoothing and asymptotics. For complex saddles and thimbles in path integrals, see Witten’s work on analytic continuation of Chern–Simons theory and modern Picard–Lefschetz treatments. For QFT applications, Coleman, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, and Mariño are useful guides, with Mariño especially helpful for instantons, large order, and resurgence.

## Version history

- 2026-06-26: First polished draft.
