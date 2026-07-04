---
title: "Elliptic Functions and Integrals"
description: "Explains elliptic integrals and elliptic functions for QFT: square roots of cubics and quartics, elliptic curves, periods, complete elliptic integrals, Jacobi and Weierstrass functions, degenerations, modular parameters, and elliptic Feynman integrals."
sidebar:
  label: "Elliptic Functions and Integrals"
  order: 6
level: Advanced
status: "Polished draft"
source: "Standard references on elliptic integrals, elliptic functions, Riemann surfaces, algebraic curves, modular parameters, Feynman integrals, and Seiberg–Witten periods, including Whittaker–Watson, Abramowitz–Stegun, NIST DLMF, Lawden, Chandrasekharan, Silverman–Tate, Ahlfors, Fay, Olver, Temme, Bloch–Vanhove, Adams–Bogner–Weinzierl, Broedel et al., Remiddi–Tancredi, Seiberg–Witten, and modern references on elliptic polylogarithms and amplitudes."
topics:
  - elliptic integral
  - elliptic function
  - elliptic curve
  - period
  - Jacobi elliptic function
  - Weierstrass elliptic function
  - modular parameter
  - elliptic Feynman integral
  - Seiberg–Witten period
  - genus one curve
canonicalTopics:
  - elliptic-integral
  - elliptic-function
  - elliptic-curve
  - period-integral
  - jacobi-elliptic-function
  - weierstrass-elliptic-function
  - modular-parameter
  - elliptic-feynman-integral
  - seiberg-witten-period
  - genus-one-curve
researchStatus:
  established:
    - "Elliptic integrals arise from integrating rational functions over square roots of cubic or quartic polynomials, equivalently from period integrals on genus-one curves."
    - "Jacobi and Weierstrass elliptic functions are doubly periodic meromorphic functions, with standard relations to complete elliptic integrals and elliptic curves."
  active:
    - "Elliptic and higher-genus structures in multiloop Feynman integrals, elliptic polylogarithms, Calabi–Yau periods, finite-gap systems, and Seiberg–Witten theory remain active parts of QFT and amplitudes research."
---

## Summary

Elliptic functions appear when a calculation contains a square root of a cubic or quartic polynomial that cannot be removed by a rational substitution. The prototype is

$$
\int {R(x)\,dx\over \sqrt{P_3(x)}}
\qquad\text{or}\qquad
\int {R(x)\,dx\over \sqrt{P_4(x)}},
$$

where $R(x)$ is rational and $P_3$ or $P_4$ has distinct roots. The equation

$$
y^2=P_3(x)
\qquad\text{or}\qquad
y^2=P_4(x)
$$

defines an elliptic curve, which is a genus-one Riemann surface. Integrating around its independent cycles gives periods. The ratio of periods gives a modular parameter $\tau$, and the functions naturally living on the curve are elliptic functions.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing square roots of cubic or quartic polynomials leading to an elliptic curve, periods, complete elliptic integrals, elliptic functions, and QFT applications.](/figures/math-toolkit/elliptic-curve-periods-flow.svg)

<figcaption>

Elliptic functions begin when a one-dimensional integral secretly lives on a genus-one curve. The same data can be read as a branch-cut problem in the $x$-plane, a torus with $A$- and $B$-cycles, a pair of periods $\omega_A,\omega_B$, or a modular parameter $\tau=\omega_B/\omega_A$. In QFT, this is the structure behind elliptic loop integrals, Seiberg–Witten periods, finite-temperature tori, and finite-gap spectra.

</figcaption>
</figure>

A useful slogan is:

$$
\text{logs come from }\sqrt{\text{quadratic}},
\qquad
\text{elliptic objects come from }\sqrt{\text{cubic or quartic}}.
$$

The slogan is not a theorem in that exact form, because degenerations and special substitutions matter, but it is the right alarm bell. When a Feynman parameter integral contains $\sqrt{(x-e_1)(x-e_2)(x-e_3)(x-e_4)}$, ordinary logarithms and classical polylogarithms usually stop being the natural language. The answer wants periods of an elliptic curve.

## Prerequisites

You should know [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/), and [Heun Equations](/math-toolkit/special-functions-exact-equations/heun-equations/).

This page uses the common elliptic-integral convention in which $k$ is the modulus and $m=k^2$ is the parameter. Many references write $K(m)$ when they mean what this page would call $K(k)$ with $m=k^2$. Tiny notation difference, maximum opportunity for chaos. Always check whether the argument is $k$ or $m$.

## From algebraic integrals to tori

Consider

$$
E:\quad y^2=P_4(x)=(x-e_1)(x-e_2)(x-e_3)(x-e_4),
$$

with distinct complex roots. The square root $y=\sqrt{P_4(x)}$ has two branches. Moving around a branch point swaps the branches. Gluing the two sheets along branch cuts produces a compact Riemann surface of genus one.

The basic holomorphic differential is

$$
\omega={dx\over y}.
$$

Choose two independent cycles $A$ and $B$ on the torus. Their periods are

$$
\omega_A=\oint_A {dx\over y},
\qquad
\omega_B=\oint_B {dx\over y}.
$$

The ratio

$$
\tau={\omega_B\over \omega_A}
$$

is the modular parameter of the torus after choosing a basis of cycles and a normalization. Changing the cycle basis by

$$
\begin{pmatrix}A'\\ B'\end{pmatrix}
=
\begin{pmatrix}a&b\\ c&d\end{pmatrix}
\begin{pmatrix}A\\ B\end{pmatrix},
\qquad
\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in SL(2,\mathbb Z),
$$

changes

$$
\tau\longmapsto {a\tau+b\over c\tau+d}.
$$

So an elliptic curve is not merely a funny square root. It comes with modular ambiguity, periods, cycles, and monodromy. That is why elliptic integrals sit naturally between complex analysis, topology, and QFT.

## Legendre normal form

A large class of elliptic integrals can be put into Legendre normal form. Define the incomplete elliptic integrals

$$
F(\phi,k)=\int_0^\phi {d\theta\over \sqrt{1-k^2\sin^2\theta}},
$$

$$
E(\phi,k)=\int_0^\phi d\theta\,\sqrt{1-k^2\sin^2\theta},
$$

and

$$
\Pi(n;\phi,k)=\int_0^\phi
{d\theta\over (1-n\sin^2\theta)\sqrt{1-k^2\sin^2\theta}}.
$$

The complete elliptic integrals are obtained at $\phi=\pi/2$:

$$
K(k)=F\left({\pi\over2},k\right),
\qquad
E(k)=E\left({\pi\over2},k\right),
\qquad
\Pi(n,k)=\Pi\left(n;{\pi\over2},k\right).
$$

The first kind $K(k)$ measures a period. The second kind $E(k)$ appears when the differential is not holomorphic but still has controlled singularity structure. The third kind $\Pi(n,k)$ appears when the integrand has an additional simple pole on the curve.

A useful hypergeometric representation is

$$
K(k)={\pi\over2}\,{}_2F_1\left({1\over2},{1\over2};1;k^2\right),
$$

and

$$
E(k)={\pi\over2}\,{}_2F_1\left(-{1\over2},{1\over2};1;k^2\right).
$$

These formulae are a warning and a bridge. Locally, elliptic integrals can be written using hypergeometric functions. Globally, the pair of independent periods and their modular transformations are the real story.

## Jacobi elliptic functions

Jacobi elliptic functions invert the elliptic integral of the first kind. If

$$
u=F(\phi,k),
$$

then

$$
\operatorname{sn}(u,k)=\sin\phi,
\qquad
\operatorname{cn}(u,k)=\cos\phi,
\qquad
\operatorname{dn}(u,k)=\sqrt{1-k^2\sin^2\phi}.
$$

They obey

$$
\operatorname{sn}^2 u+\operatorname{cn}^2 u=1,
$$

and

$$
k^2\operatorname{sn}^2 u+\operatorname{dn}^2 u=1,
$$

where the modulus $k$ is suppressed on the left. Their derivatives are

$$
{d\over du}\operatorname{sn}u=\operatorname{cn}u\operatorname{dn}u,
$$

$$
{d\over du}\operatorname{cn}u=-\operatorname{sn}u\operatorname{dn}u,
$$

$$
{d\over du}\operatorname{dn}u=-k^2\operatorname{sn}u\operatorname{cn}u.
$$

The function $\operatorname{sn}u$ satisfies the nonlinear first-order equation

$$
\left({d\over du}\operatorname{sn}u\right)^2
=(1-\operatorname{sn}^2u)(1-k^2\operatorname{sn}^2u).
$$

This is the Jacobi version of the elliptic curve. If $x=\operatorname{sn}u$, then $u$ is an integral over $dx/\sqrt{(1-x^2)(1-k^2x^2)}$.

The periods are generated by $K(k)$ and the complementary complete integral

$$
K'(k)=K(k'),
\qquad
k'=\sqrt{1-k^2}.
$$

More precisely, $\operatorname{sn}u$ has periods $4K$ and $2iK'$, while $\operatorname{cn}u$ and $\operatorname{dn}u$ have related period lattices. This double periodicity is the defining feature of elliptic functions.

## Weierstrass elliptic functions

The Weierstrass form packages the torus directly. Let

$$
\Lambda=\{2m\omega_1+2n\omega_2:m,n\in\mathbb Z\}
$$

be a lattice in the complex plane, with $\omega_2/\omega_1\notin\mathbb R$. The Weierstrass function is

$$
\wp(z;\Lambda)
={1\over z^2}
+
\sum_{\omega\in\Lambda\setminus\{0\}}
\left[{1\over (z-\omega)^2}-{1\over \omega^2}\right].
$$

It is meromorphic and doubly periodic:

$$
\wp(z+\omega)=\wp(z),
\qquad
\omega\in\Lambda.
$$

It satisfies

$$
\big(\wp'(z)\big)^2=4\wp(z)^3-g_2\wp(z)-g_3,
$$

where

$$
g_2=60\sum_{\omega\in\Lambda\setminus\{0\}}{1\over\omega^4},
\qquad
g_3=140\sum_{\omega\in\Lambda\setminus\{0\}}{1\over\omega^6}.
$$

Thus

$$
E:\quad y^2=4x^3-g_2x-g_3
$$

is the elliptic curve associated with the lattice, under the parametrization

$$
x=\wp(z),
\qquad
y=\wp'(z).
$$

The discriminant

$$
\Delta=g_2^3-27g_3^2
$$

vanishes when the curve degenerates. In physics, such degenerations often signal thresholds, massless states, pinched cycles, or limiting regimes where elliptic functions collapse back to elementary or polylogarithmic functions.

## Elliptic curves as period machines

Many QFT examples do not ask for $\operatorname{sn}$ or $\wp$ explicitly. They ask for periods. Suppose a calculation produces a family of elliptic curves depending on kinematic invariants or moduli:

$$
E_s:\quad y^2=P(x;s).
$$

A period is an integral

$$
\Pi_A(s)=\oint_A \omega(s),
$$

where $\omega(s)$ is a differential on $E_s$. As $s$ changes, the periods satisfy a Picard–Fuchs differential equation. This equation is often easier to derive and solve than the original integral.

This is the perspective behind many exact calculations:

$$
\text{integral family}
\quad\longrightarrow\quad
\text{algebraic curve}
\quad\longrightarrow\quad
\text{periods}
\quad\longrightarrow\quad
\text{Picard–Fuchs equation}.
$$

In Seiberg–Witten theory, for example, the low-energy physics of certain supersymmetric gauge theories is encoded by periods of a meromorphic differential on a family of curves. The variables often denoted $a$ and $a_D$ are period integrals, and their monodromy controls electric–magnetic duality.

In multiloop Feynman integrals, the same period logic appears in a less supersymmetric outfit. The two-loop sunrise integral with massive propagators is the classic example: after Feynman parametrization, the maximal cut defines an elliptic curve. The result cannot generally be expressed using ordinary multiple polylogarithms alone.

## Degeneration limits

Elliptic functions contain trigonometric, hyperbolic, and rational functions as degenerations.

As $k\to0$,

$$
K(k)\to {\pi\over2},
\qquad
\operatorname{sn}(u,k)\to \sin u,
\qquad
\operatorname{cn}(u,k)\to \cos u,
\qquad
\operatorname{dn}(u,k)\to 1.
$$

As $k\to1$,

$$
K(k)\to\infty,
$$

and

$$
\operatorname{sn}(u,k)\to \tanh u,
\qquad
\operatorname{cn}(u,k)\to \operatorname{sech}u,
\qquad
\operatorname{dn}(u,k)\to \operatorname{sech}u.
$$

Geometrically, a cycle of the torus is becoming infinitely long or pinching. Analytically, a pair of branch points is colliding. Physically, this is often where an elliptic answer simplifies to logarithms, dilogarithms, or elementary functions.

A useful expansion for small $k$ is

$$
K(k)={\pi\over2}
\left(1+{1\over4}k^2+{9\over64}k^4+{25\over256}k^6+\cdots\right).
$$

Near $k=1$, write $k'=\sqrt{1-k^2}$. Then

$$
K(k)\sim \log{4\over k'}
$$

up to terms suppressed by powers of $k'^2$ times logarithms. That logarithm is the analytic trace of a degenerating cycle.

## Modular parameter and nome

For Legendre form, a standard modular parameter is

$$
\tau=i{K'(k)\over K(k)},
$$

for $0<k<1$, and the nome is

$$
q=e^{i\pi\tau}=e^{-\pi K'(k)/K(k)}.
$$

Some QFT and CFT conventions instead use

$$
Q=e^{2\pi i\tau}=q^2.
$$

Both are common. The difference is not deep, but it absolutely matters in expansions.

Theta functions express Jacobi elliptic functions in terms of $q$. This is often the cleanest way to build convergent series when the elliptic curve is naturally described by $\tau$. For example, the modulus can be written in terms of theta constants as

$$
k^2=\left({\vartheta_2(0|\tau)\over \vartheta_3(0|\tau)}\right)^4.
$$

The full modular-forms technology belongs to the modular-forms page. The point here is simply that elliptic functions bring a torus, and a torus brings modular transformations.

## Why ordinary polylogarithms are not enough

Ordinary multiple polylogarithms are iterated integrals over rational kernels such as

$$
{dt\over t-a}.
$$

Elliptic integrals require kernels on a genus-one curve, for example

$$
{dx\over y},
\qquad
{R(x)\,dx\over y},
\qquad
y^2=P_4(x).
$$

That replacement changes the analytic category. The alphabet is no longer just a finite set of points on the Riemann sphere; it includes the period lattice and elliptic kernels. This is why elliptic polylogarithms, modular forms, and iterated integrals on elliptic curves enter modern multiloop amplitudes.

A practical diagnostic is this: if differentiating an integral leads to a closed system whose homogeneous solutions are elliptic periods, then the full answer is usually an iterated integral over elliptic kernels rather than an ordinary polylogarithm.

## QFT examples and interpretations

**Two-loop sunrise integrals.** With generic masses, the maximal cut of the sunrise graph defines an elliptic curve. The full integral can be organized using periods and elliptic polylogarithms.

**Seiberg–Witten theory.** Low-energy effective couplings are encoded by period integrals on a family of curves. Monodromy of periods describes electric–magnetic duality and the behavior near singular loci.

**Finite-gap and integrable systems.** Classical solutions of integrable field equations often live on algebraic curves. Genus one gives elliptic functions; higher genus gives theta functions on higher-dimensional Jacobians.

**Finite temperature and torus physics.** Thermal compactification and two-dimensional CFT naturally involve tori. The elliptic curve language overlaps with modular forms and theta functions.

**Worldline and instanton problems.** Classical solutions in periodic or double-well-like potentials can be expressed in Jacobi elliptic functions before taking dilute-instanton or degeneration limits.

The moral is not that every elliptic function is a deep nonperturbative miracle. Sometimes it is just the exact solution of a separable ODE. But when elliptic curves appear inside loop integrals or moduli spaces, they often signal genuinely new analytic structure.

## Common pitfalls

**Confusing modulus and parameter.** Some authors write $K(k)$, others write $K(m)$ with $m=k^2$. Check the convention before using identities.

**Treating an elliptic integral as a single-valued function.** Periods depend on cycles. Analytic continuation can mix cycles by an $SL(2,\mathbb Z)$ transformation.

**Ignoring degenerations.** The limits $k\to0$ and $k\to1$ are not just numerical limits. They correspond to changes in the curve: branch points collide, cycles shrink or stretch, and the analytic class can simplify.

**Assuming all loop integrals are polylogarithmic.** Many are, many are not. Elliptic curves are the first common obstruction.

**Forgetting branch choices.** The integral $\int dx/\sqrt{P(x)}$ is meaningless until a branch, contour, and cycle are specified.

**Calling every torus function modular.** Elliptic functions are functions on a torus as a complex curve. Modular forms are functions of the torus modulus $\tau$ with controlled transformation properties. Related, but not the same beast.

## Exercises

### Exercise 1: Hypergeometric form of K

Show that

$$
K(k)={\pi\over2}\,{}_2F_1\left({1\over2},{1\over2};1;k^2\right).
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
K(k)=\int_0^{\pi/2}{d\theta\over\sqrt{1-k^2\sin^2\theta}}.
$$

Set $t=\sin^2\theta$. Then

$$
d\theta={dt\over2\sqrt{t(1-t)}}.
$$

Therefore

$$
K(k)={1\over2}\int_0^1
{dt\over \sqrt{t}\sqrt{1-t}\sqrt{1-k^2t}}.
$$

Using the Euler integral for the hypergeometric function,

$$
\int_0^1 dt\,t^{b-1}(1-t)^{c-b-1}(1-zt)^{-a}
=B(b,c-b){}_2F_1(a,b;c;z),
$$

with $a=b=1/2$, $c=1$, and $z=k^2$, gives

$$
K(k)={1\over2}B\left({1\over2},{1\over2}\right)
{}_2F_1\left({1\over2},{1\over2};1;k^2\right).
$$

Since $B(1/2,1/2)=\pi$, the result follows.

</details>

### Exercise 2: The Jacobi identities

Using the definitions

$$
\operatorname{sn}u=\sin\phi,
\qquad
\operatorname{cn}u=\cos\phi,
\qquad
\operatorname{dn}u=\sqrt{1-k^2\sin^2\phi},
$$

show that

$$
\operatorname{sn}^2u+\operatorname{cn}^2u=1,
\qquad
k^2\operatorname{sn}^2u+\operatorname{dn}^2u=1.
$$

<details><summary><strong>Solution</strong></summary>

The first identity is simply

$$
\sin^2\phi+\cos^2\phi=1.
$$

The second follows from

$$
\operatorname{dn}^2u=1-k^2\sin^2\phi=1-k^2\operatorname{sn}^2u.
$$

Rearranging gives

$$
k^2\operatorname{sn}^2u+\operatorname{dn}^2u=1.
$$

</details>

### Exercise 3: Degeneration to trigonometric functions

Show that when $k=0$, the Jacobi elliptic functions reduce to

$$
\operatorname{sn}(u,0)=\sin u,
\qquad
\operatorname{cn}(u,0)=\cos u,
\qquad
\operatorname{dn}(u,0)=1.
$$

<details><summary><strong>Solution</strong></summary>

For $k=0$,

$$
F(\phi,0)=\int_0^\phi d\theta=\phi.
$$

Thus $u=\phi$. The definitions immediately give

$$
\operatorname{sn}(u,0)=\sin u,
\qquad
\operatorname{cn}(u,0)=\cos u,
\qquad
\operatorname{dn}(u,0)=\sqrt{1}=1.
$$

</details>

### Exercise 4: Small-k expansion of K

Use the binomial expansion to derive the first two correction terms in

$$
K(k)={\pi\over2}\left(1+{k^2\over4}+{9k^4\over64}+\cdots\right).
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
(1-k^2\sin^2\theta)^{-1/2}
=1+{1\over2}k^2\sin^2\theta+{3\over8}k^4\sin^4\theta+O(k^6).
$$

Then

$$
K(k)=\int_0^{\pi/2}d\theta
\left[1+{1\over2}k^2\sin^2\theta+{3\over8}k^4\sin^4\theta+O(k^6)\right].
$$

The needed integrals are

$$
\int_0^{\pi/2}d\theta={\pi\over2},
\qquad
\int_0^{\pi/2}\sin^2\theta\,d\theta={\pi\over4},
$$

and

$$
\int_0^{\pi/2}\sin^4\theta\,d\theta={3\pi\over16}.
$$

Therefore

$$
K(k)={\pi\over2}+{1\over2}k^2{\pi\over4}+{3\over8}k^4{3\pi\over16}+O(k^6),
$$

which is

$$
K(k)={\pi\over2}\left(1+{k^2\over4}+{9k^4\over64}+O(k^6)\right).
$$

</details>

## Related pages

For the hypergeometric representation of complete elliptic integrals, see [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/). For the curve and cycle language, see [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/), and [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/). For the next layer of iterated-integral technology, see [Polylogarithms](/math-toolkit/special-functions-exact-equations/polylogarithms/).

## References and further reading

Classic references include Whittaker and Watson, Abramowitz and Stegun, Lawden, Chandrasekharan, Ahlfors, Silverman and Tate, and the NIST Digital Library of Mathematical Functions. For elliptic curves and periods in physics, see standard discussions of Seiberg–Witten theory, finite-gap systems, and algebraic curves in integrable models. For elliptic Feynman integrals and elliptic polylogarithms, see work by Bloch, Vanhove, Adams, Bogner, Weinzierl, Remiddi, Tancredi, Broedel, Duhr, Dulat, and collaborators.

## Version history

- **2026-06-26:** Initial polished draft. Added elliptic curves from cubic and quartic roots, Legendre integrals, Jacobi and Weierstrass functions, periods and modular parameter, degeneration limits, QFT examples, common pitfalls, exercises with solutions, and TikZ/SVG figure.
