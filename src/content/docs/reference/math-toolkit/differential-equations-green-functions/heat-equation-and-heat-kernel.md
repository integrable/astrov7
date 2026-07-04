---
title: "Heat Equation and Heat Kernel"
description: "Explains the heat equation and heat kernel as a semigroup, inverse-kernel, spectral-filter, and proper-time tool for Green functions, determinants, and UV asymptotics."
sidebar:
  label: "Heat Equation and Heat Kernel"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard references on PDEs, spectral theory, heat kernels, functional determinants, and QFT one-loop methods, including Courant–Hilbert, Evans, Gilkey, Berline–Getzler–Vergne, Vassilevich, Reed–Simon, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, Marino, and localization literature."
topics:
  - heat equation
  - heat kernel
  - semigroups
  - spectral theory
  - Green functions
  - Schwinger proper time
  - functional determinants
  - Seeley–DeWitt coefficients
  - UV divergences
  - zero modes
  - boundary conditions
canonicalTopics:
  - heat-equation
  - heat-kernel
  - semigroup
  - spectral-theory
  - green-function
  - schwinger-proper-time
  - functional-determinant
  - seeley-dewitt-coefficient
  - uv-divergence
  - zero-mode
  - boundary-condition
researchStatus:
  established:
    - "For positive self-adjoint elliptic operators, the heat kernel is the integral kernel of the semigroup $e^{-\tau L}$ and controls Green functions, spectral traces, determinants, and short-distance asymptotics."
  active:
    - "Heat-kernel methods on singular spaces, boundaries and corners, nonlocal operators, gauge-fixing complexes, real-time continuations, and nonperturbative spectral reconstructions remain active in mathematical physics and QFT."
---

## Summary

The heat equation is the parabolic evolution equation

$$
(\partial_\tau+L)u(\tau,x)=0,
$$

where $L$ is usually a positive elliptic operator. The parameter $\tau$ is called heat time, diffusion time, or proper time depending on context. If $L\ge 0$ is self-adjoint, the solution is

$$
u(\tau)=e^{-\tau L}u(0).
$$

The **heat kernel** $K_\tau(x,y)$ is the integral kernel of this operator:

$$
[e^{-\tau L}f](x)=\int_X d\mu(y)\,K_\tau(x,y)f(y).
$$

It satisfies

$$
(\partial_\tau+L_x)K_\tau(x,y)=0,
\qquad
\lim_{\tau\downarrow0}K_\tau(x,y)=\delta_\mu(x,y),
$$

where $\delta_\mu$ is the delta distribution for the measure $d\mu$.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flow diagram showing a positive self-adjoint elliptic operator becoming a heat semigroup, a heat kernel, a heat equation, a semigroup law, a trace, a Green inverse, a determinant, and small-proper-time UV asymptotics.](/figures/math-toolkit/heat-kernel-semigroup-flow.svg)

<figcaption>

The heat kernel packages several ideas into one object. It is the kernel of $e^{-\tau L}$, solves a parabolic initial-value problem, obeys a semigroup law, gives the trace $\operatorname{Tr}e^{-\tau L}$, represents $L^{-1}$ by a proper-time integral, and exposes UV divergences through its small-$\tau$ diagonal asymptotics.

</figcaption>
</figure>

In QFT, the heat kernel is not just a PDE toy. It is the cleanest bridge between local geometry, spectra, Green functions, and one-loop physics. The proper-time identity

$$
L^{-1}=\int_0^\infty d\tau\,e^{-\tau L}
$$

turns inverse operators into heat kernels, while

$$
\log\det L=-\int_0^\infty\frac{d\tau}{\tau}\,\operatorname{Tr}e^{-\tau L}
$$

explains why one-loop determinants are governed by the short-time behavior of the heat trace. The small-$\tau$ expansion is local; that is why the divergent part of a one-loop effective action is built from local counterterms.

## Prerequisites

You should know [Partial Differential Equations](/math-toolkit/differential-equations-green-functions/partial-differential-equations/), [Elliptic, Hyperbolic, and Parabolic Equations](/math-toolkit/differential-equations-green-functions/elliptic-hyperbolic-parabolic/), [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/), and [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/).

For determinant applications, [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) give the one-loop continuation of this page.

## Core idea

The heat kernel is a spectral filter. If

$$
Lu_n=\lambda_n u_n,
\qquad
\lambda_n\ge0,
$$

then

$$
e^{-\tau L}u_n=e^{-\tau\lambda_n}u_n.
$$

High-eigenvalue modes are suppressed quickly; low-eigenvalue modes survive for long heat time. Therefore

$$
\tau\downarrow0
\quad\text{probes short distance and high spectrum},
$$

while

$$
\tau\to\infty
\quad\text{probes zero modes and the infrared spectrum}.
$$

This simple observation explains a ridiculous amount of physics. In Euclidean QFT, large eigenvalues are UV modes. The small-$\tau$ expansion of $K_\tau(x,x)$ therefore records the local UV structure of the theory. Its coefficients are built from local invariants: curvature, gauge field strengths, potentials, extrinsic curvature of boundaries, and so on. When you see a counterterm such as $F_{\mu\nu}F^{\mu\nu}$ or $R^2$, a heat-kernel coefficient is usually lurking nearby with a clipboard.

Heat flow is also smoothing. For $\tau>0$, the kernel $K_\tau(x,y)$ is typically much nicer than the delta function from which it starts. That is why heat kernels are excellent regulators: they replace a singular inverse or trace by a family of smooth objects and then let us study how the singularity returns as $\tau\downarrow0$.

## Setup and conventions

Let $X$ be a manifold, domain, graph, or measure space with measure $d\mu(x)$. Let $L$ be a positive self-adjoint operator on a Hilbert space such as $L^2(X,d\mu)$. In the most common geometric case,

$$
L=-\nabla^2+X(x)
$$

or, for a vector bundle,

$$
L=-g^{\mu\nu}\nabla_\mu\nabla_\nu+\mathcal X,
$$

where $\nabla$ includes both the Levi-Civita connection and any gauge or bundle connection.

The heat kernel is defined by

$$
K_\tau(x,y)=\langle x|e^{-\tau L}|y\rangle,
\qquad
\tau>0.
$$

With measure $d\mu$, the delta distribution is normalized by

$$
f(x)=\int_X d\mu(y)\,\delta_\mu(x,y)f(y).
$$

Thus the initial condition is

$$
K_{0^+}(x,y)=\delta_\mu(x,y).
$$

For a scalar field on a Riemannian manifold, the natural measure is

$$
d\mu(x)=d^dx\sqrt g.
$$

The corresponding delta distribution is

$$
\delta_g(x,y)=\frac{\delta^{(d)}(x-y)}{\sqrt{g(y)}}
$$

in a coordinate chart, because

$$
f(x)=\int d^dy\sqrt{g(y)}\,\delta_g(x,y)f(y).
$$

This measure factor is a classic source of wrong heat kernels. It is the same mild goblin that appears in Green functions and Sturm–Liouville theory.

## Matrix model: the whole story in finite dimensions

Before infinite-dimensional analysis gets misty, let $A$ be a positive Hermitian matrix. Define

$$
U(\tau)=e^{-\tau A}.
$$

Then

$$
\frac{dU}{d\tau}=-AU,
\qquad
U(0)=I.
$$

If $A$ has eigenvectors $v_n$ and eigenvalues $\lambda_n$, then

$$
U(\tau)v_n=e^{-\tau\lambda_n}v_n.
$$

The trace is

$$
\operatorname{Tr}e^{-\tau A}=\sum_n e^{-\tau\lambda_n}.
$$

If $A$ has no zero eigenvalues, then

$$
A^{-1}=\int_0^\infty d\tau\,e^{-\tau A},
$$

because, on each eigenvector,

$$
\int_0^\infty d\tau\,e^{-\tau\lambda_n}=\frac1{\lambda_n}.
$$

Similarly,

$$
\log\det A=\sum_n\log\lambda_n.
$$

Since

$$
\log\lambda=-\int_0^\infty \frac{d\tau}{\tau}e^{-\tau\lambda}
$$

is not literally convergent without subtractions, the determinant identity is always shorthand for a regulated expression. Differences are better behaved:

$$
\log\frac{\det A}{\det B}
=-\int_0^\infty\frac{d\tau}{\tau}\left(\operatorname{Tr}e^{-\tau A}-\operatorname{Tr}e^{-\tau B}\right),
$$

when the difference is sufficiently convergent. Infinite-dimensional QFT keeps this exact logic, then adds UV divergences, zero modes, anomalies, and the occasional brick wall with a name like ``multiplicative anomaly.''

## Heat kernels as integral kernels

For an operator on functions, the finite-dimensional matrix element becomes an integral kernel:

$$
[e^{-\tau L}f](x)=\int_X d\mu(y)\,K_\tau(x,y)f(y).
$$

The heat equation follows by differentiating:

$$
\partial_\tau[e^{-\tau L}f]=-Le^{-\tau L}f.
$$

Since this holds for all $f$,

$$
(\partial_\tau+L_x)K_\tau(x,y)=0.
$$

The initial condition is

$$
\lim_{\tau\downarrow0}\int_X d\mu(y)\,K_\tau(x,y)f(y)=f(x).
$$

That is the precise sense in which $K_\tau(x,y)$ approaches $\delta_\mu(x,y)$.

If $L$ is self-adjoint, then the heat kernel is symmetric in the appropriate Hermitian sense:

$$
K_\tau(x,y)=\overline{K_\tau(y,x)}
$$

for scalar real-measure problems. For bundle-valued kernels, the corresponding statement includes the fiber Hermitian inner product.

### Semigroup law

The heat semigroup obeys

$$
e^{-(\tau+\sigma)L}=e^{-\tau L}e^{-\sigma L}.
$$

In kernel language this becomes

$$
K_{\tau+\sigma}(x,y)
=\int_X d\mu(z)\,K_\tau(x,z)K_\sigma(z,y).
$$

This identity is not optional. It is one of the best checks that all measure factors and normalizations are right.

### Spectral expansion

If $L$ has a discrete orthonormal basis of eigenfunctions $u_n$, then

$$
K_\tau(x,y)=\sum_n e^{-\tau\lambda_n}u_n(x)\overline{u_n(y)}.
$$

On a space with continuous spectrum, the sum is replaced by a spectral integral. A typical schematic form is

$$
K_\tau(x,y)=\int d\lambda\,e^{-\tau\lambda}\,dE_\lambda(x,y),
$$

where $dE_\lambda$ is the kernel of the spectral measure. This is why heat kernels and spectral densities are essentially Laplace-transform cousins.

## The flat-space heat kernel

The model example is

$$
L=-\nabla^2+m^2
$$

on $\mathbb R^d$ with the Euclidean measure $d^dx$. The heat kernel is translation-invariant:

$$
K_\tau(x,y)=K_\tau(x-y).
$$

Using the Fourier convention

$$
f(x)=\int\frac{d^dp}{(2\pi)^d}e^{ip\cdot x}\widetilde f(p),
$$

the operator has eigenvalue

$$
p^2+m^2.
$$

Therefore

$$
K_\tau(x-y)
=\int\frac{d^dp}{(2\pi)^d}
\exp\left[ip\cdot(x-y)-\tau(p^2+m^2)\right].
$$

The Gaussian integral gives

$$
K_\tau(x,y)
=\frac{1}{(4\pi\tau)^{d/2}}
\exp\left[-\frac{|x-y|^2}{4\tau}-m^2\tau\right].
$$

This formula displays all the essential features:

$$
K_\tau(x,y)\to\delta^{(d)}(x-y)
\quad\text{as}\quad \tau\downarrow0,
$$

and high momenta are suppressed by $e^{-\tau p^2}$. The heat time $\tau$ has dimension of length squared, so the kernel smears over distances of order

$$
\sqrt\tau.
$$

In this sense, the heat kernel is a microscope with resolution $\sqrt\tau$.

## Green functions from heat kernels

If $L$ is positive and has no zero modes, then

$$
L^{-1}=\int_0^\infty d\tau\,e^{-\tau L}.
$$

Therefore the Green function is

$$
G(x,y)=\int_0^\infty d\tau\,K_\tau(x,y).
$$

For $L=-\nabla^2+m^2$ on $\mathbb R^d$, this gives

$$
G(x,y)=\int_0^\infty d\tau\,
\frac{1}{(4\pi\tau)^{d/2}}
\exp\left[-\frac{|x-y|^2}{4\tau}-m^2\tau\right].
$$

This is the Schwinger proper-time representation of the Euclidean propagator. In momentum space it is just the identity

$$
\frac1{p^2+m^2}=\int_0^\infty d\tau\,e^{-\tau(p^2+m^2)}.
$$

That identity is absurdly useful. It turns rational denominators into Gaussian integrals, exposes UV behavior through small $\tau$, and often makes symmetries more visible.

### Massless warning

For $m=0$ on infinite space, the large-$\tau$ behavior can diverge in the infrared. That is not a heat-kernel failure. It is the same IR problem as the massless Green function. The proper-time integral sees both ends:

$$
\tau\downarrow0
\quad\text{UV},
\qquad
\tau\to\infty
\quad\text{IR}.
$$

Regulators have to say which end they are regulating. A cutoff at $\tau=\epsilon^2$ is a UV cutoff; a mass $m$ or finite volume can also regulate the IR.

## Heat trace and density of states

The heat trace is

$$
\operatorname{Tr}e^{-\tau L}
=\sum_n e^{-\tau\lambda_n}
$$

for discrete spectrum. If the spectrum has density $\rho(\lambda)$, then formally

$$
\operatorname{Tr}e^{-\tau L}
=\int d\lambda\,\rho(\lambda)e^{-\tau\lambda}.
$$

Thus the heat trace is a Laplace transform of the spectral density. Small $\tau$ is sensitive to the large-$\lambda$ asymptotics of $\rho(\lambda)$.

On a compact $d$-dimensional Riemannian manifold, the leading term is Weyl's law in heat-kernel clothing:

$$
\operatorname{Tr}e^{-\tau L}
\sim \frac{\operatorname{Vol}(X)}{(4\pi\tau)^{d/2}}
\qquad
(\tau\downarrow0)
$$

for a scalar Laplace-type operator with no bundle multiplicity. This leading term says that locally, at very short heat time, every smooth manifold looks like flat space.

## Local heat-kernel asymptotics

For a Laplace-type operator on a smooth compact manifold without boundary, the diagonal heat kernel has an asymptotic expansion

$$
K_\tau(x,x)
\sim
\frac{1}{(4\pi\tau)^{d/2}}
\sum_{n=0}^\infty \tau^n a_n(x),
\qquad
\tau\downarrow0.
$$

The coefficients $a_n(x)$ are local invariants made from the operator and the geometry. For a scalar operator

$$
L=-\nabla^2+X
$$

with the convention used here,

$$
a_0(x)=1,
\qquad
a_1(x)=\frac{R}{6}-X.
$$

The sign of the $X$ term is worth checking. In flat space with $X=m^2$,

$$
K_\tau(x,x)=\frac{1}{(4\pi\tau)^{d/2}}e^{-m^2\tau}
=\frac{1}{(4\pi\tau)^{d/2}}
\left(1-m^2\tau+\frac12m^4\tau^2-\cdots\right),
$$

so $a_1=-m^2$ when $R=0$.

For bundle-valued operators, the $a_n$ are endomorphisms and the trace includes a fiber trace:

$$
\operatorname{Tr}e^{-\tau L}
\sim
\frac{1}{(4\pi\tau)^{d/2}}
\sum_{n=0}^\infty \tau^n
\int_X d^dx\sqrt g\,\operatorname{tr}_{\text{fib}}a_n(x).
$$

The coefficient $a_2$ contains terms such as curvature squared, gauge field strength squared, and potential squared. Those are precisely the kinds of local terms that appear in one-loop counterterms and anomalies.

### Boundaries change the expansion

If $X$ has a boundary, the heat trace generally includes both integer and half-integer powers:

$$
\operatorname{Tr}e^{-\tau L}
\sim
\frac{1}{(4\pi\tau)^{d/2}}
\left(
A_0+\tau^{1/2}A_{1/2}+\tau A_1+\tau^{3/2}A_{3/2}+\cdots
\right).
$$

The boundary coefficients depend on the boundary condition: Dirichlet, Neumann, Robin, mixed, spectral, Atiyah–Patodi–Singer, and so on. This is why one cannot say ``the heat kernel of $L$'' near a boundary without specifying the domain. The boundary condition is part of the operator.

## Functional determinants

Gaussian functional integrals produce determinants. For a real bosonic fluctuation operator $L$, one formally gets

$$
Z_{\text{1-loop}}\propto(\det L)^{-1/2},
$$

so the one-loop effective action contains

$$
\Gamma_{\text{1-loop}}=\frac12\log\det L.
$$

The proper-time form is

$$
\Gamma_{\text{1-loop}}
=-\frac12\int_0^\infty\frac{d\tau}{\tau}\,\operatorname{Tr}e^{-\tau L},
$$

with a regulator understood. A common UV cutoff is

$$
\Gamma_{\text{1-loop}}(\epsilon)
=-\frac12\int_{\epsilon^2}^\infty\frac{d\tau}{\tau}\,\operatorname{Tr}e^{-\tau L}.
$$

In $d=4$, the heat-trace expansion gives divergences from the terms

$$
\tau^{-2},\qquad \tau^{-1},\qquad \tau^0
$$

inside $\operatorname{Tr}e^{-\tau L}$, because the determinant integral has an additional $d\tau/\tau$. These correspond to quartic, quadratic, and logarithmic UV divergences in a cutoff scheme. The logarithmic divergence is tied to the coefficient $A_2$ in four dimensions.

This is the local reason renormalization works for local QFTs: the divergent part of the determinant is made from finitely many local invariants at each fixed dimension.

## Zeta functions and Mellin transforms

The spectral zeta function of $L$ is

$$
\zeta_L(s)=\operatorname{Tr}L^{-s}.
$$

For positive spectrum, it is related to the heat trace by a Mellin transform:

$$
\zeta_L(s)
=\frac1{\Gamma(s)}\int_0^\infty d\tau\,\tau^{s-1}\operatorname{Tr}e^{-\tau L}.
$$

The zeta-regularized determinant is

$$
\log\det_\zeta L=-\zeta_L'(0),
$$

assuming zero modes have been removed or otherwise treated. The heat-kernel expansion controls the meromorphic continuation of $\zeta_L(s)$ and identifies its poles. This is why heat kernels and zeta regularization are two faces of the same spectral machine.

## Zero modes

If $L$ has zero modes, then $e^{-\tau L}$ does not decay on those modes:

$$
e^{-\tau L}u_0=u_0.
$$

The heat trace then approaches the number of zero modes as $\tau\to\infty$:

$$
\operatorname{Tr}e^{-\tau L}\to \dim\ker L.
$$

Consequently,

$$
\int_0^\infty d\tau\,e^{-\tau L}
$$

is not an inverse on the zero-mode subspace, and

$$
\int_0^\infty\frac{d\tau}{\tau}\operatorname{Tr}e^{-\tau L}
$$

has an IR divergence from zero modes.

The usual options are:

1. project out zero modes and define $\det' L$;
2. add a small mass or regulator and take limits carefully;
3. replace zero-mode Gaussian integration by collective-coordinate integration;
4. keep the zero-mode sector separate because it carries physical moduli or gauge redundancy.

In instanton, soliton, gauge, and gravity problems, this is not a footnote. It is the part where many wrong prefactors are born.

## Boundary conditions and domains

The heat kernel depends on the domain of $L$. For example, on the half-line $x>0$, the heat kernel for $L=-d^2/dx^2$ with Dirichlet boundary condition at $x=0$ is obtained by images:

$$
K_D(\tau;x,y)
=\frac1{\sqrt{4\pi\tau}}
\left[
\exp\left(-\frac{(x-y)^2}{4\tau}\right)
-
\exp\left(-\frac{(x+y)^2}{4\tau}\right)
\right].
$$

The Neumann kernel is

$$
K_N(\tau;x,y)
=\frac1{\sqrt{4\pi\tau}}
\left[
\exp\left(-\frac{(x-y)^2}{4\tau}\right)
+
\exp\left(-\frac{(x+y)^2}{4\tau}\right)
\right].
$$

Both solve the same heat equation in the interior and both approach a delta function as $\tau\downarrow0$ away from the boundary. They differ because the boundary condition is different:

$$
K_D(\tau;0,y)=0,
\qquad
\partial_xK_N(\tau;x,y)|_{x=0}=0.
$$

Same differential expression, different heat kernel. Yes, the boundary gets a vote.

## Heat equation versus wave equation

The heat equation

$$
\partial_\tau u-\nabla^2u=0
$$

is parabolic. It smooths initial data and has infinite propagation speed: a localized bump immediately develops nonzero tails everywhere for $\tau>0$.

The wave equation

$$
\partial_t^2u-\nabla^2u=0
$$

is hyperbolic. It propagates initial data with finite speed along characteristic cones.

This distinction matters in QFT. Euclidean propagators and determinants are often controlled by elliptic and parabolic tools. Real-time causality is controlled by hyperbolic tools. Wick rotation connects them in favorable cases, but it does not erase the difference between diffusion time and physical time.

## Common pitfalls

**Forgetting the measure.** The heat kernel satisfies $K_{0^+}=\delta_\mu$, not automatically the coordinate delta function. On a curved manifold the correct delta is normalized with $\sqrt g$.

**Treating the heat kernel as unique without a domain.** Boundary conditions, self-adjoint extensions, gauge choices, and zero-mode prescriptions are part of the definition.

**Confusing heat time with real time.** The parameter $\tau$ in $e^{-\tau L}$ is Euclidean diffusion or proper time. It is not Lorentzian time unless the problem is actually a diffusion problem.

**Ignoring large heat time.** Small $\tau$ is UV. Large $\tau$ is IR. Determinant integrals can diverge at either end.

**Writing $\log\det L$ without regularization.** In infinite dimensions, $\log\det L$ is not a number until a regularization and subtraction scheme is specified.

**Using the wrong sign for the potential term.** With $L=-\nabla^2+X$, the flat constant-potential kernel includes $e^{-X\tau}$, so the first coefficient is $a_1=-X$ in flat space.

## Relations to other pages

[Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/) explains inverse kernels directly. The heat kernel gives one systematic way to build those inverses when the operator is positive and Euclidean.

[Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) use heat traces to define and expand one-loop determinants.

[Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/) treats the heat trace as a Laplace transform of spectral data.

[Wave Equation](/math-toolkit/differential-equations-green-functions/wave-equation/) contrasts the parabolic heat equation with hyperbolic propagation and causal Green functions.

## Research status

The basic theory of heat kernels for smooth elliptic operators is mature and central in analysis, geometry, index theory, and QFT. The short-time expansion, proper-time representation, and relation to one-loop determinants are standard tools.

The active frontier is not the flat-space Gaussian. It is what happens when the geometry, operator, or physical problem is less polite: boundaries with corners, singular spaces, defects, conical manifolds, nonlocal kinetic terms, gauge complexes with ghosts and zero modes, Lorentzian continuation, non-self-adjoint operators, and reconstruction of spectra from partial heat-trace data.

## Exercises

### Exercise 1: Check the flat heat kernel

Show that

$$
K_\tau(x,y)=\frac{1}{(4\pi\tau)^{d/2}}
\exp\left[-\frac{|x-y|^2}{4\tau}-m^2\tau\right]
$$

solves

$$
(\partial_\tau-\nabla_x^2+m^2)K_\tau(x,y)=0
$$

for $\tau>0$.

<details><summary><strong>Solution</strong></summary>

Let $r=x-y$. Write

$$
K_\tau=(4\pi\tau)^{-d/2}e^{-r^2/(4\tau)}e^{-m^2\tau}.
$$

Taking the logarithmic derivative gives

$$
\frac{\partial_\tau K_\tau}{K_\tau}
=-\frac d{2\tau}+\frac{r^2}{4\tau^2}-m^2.
$$

For the Laplacian,

$$
\nabla_x^2K_\tau
=\left(-\frac d{2\tau}+\frac{r^2}{4\tau^2}\right)K_\tau.
$$

Therefore

$$
(\partial_\tau-\nabla_x^2+m^2)K_\tau
=\left[-\frac d{2\tau}+\frac{r^2}{4\tau^2}-m^2
+\frac d{2\tau}-\frac{r^2}{4\tau^2}+m^2\right]K_\tau=0.
$$

</details>

### Exercise 2: Derive the semigroup law spectrally

Assume $L$ has orthonormal eigenfunctions $u_n$ with eigenvalues $\lambda_n$. Use the spectral expansion of $K_\tau$ to prove

$$
K_{\tau+\sigma}(x,y)
=\int_X d\mu(z)\,K_\tau(x,z)K_\sigma(z,y).
$$

<details><summary><strong>Solution</strong></summary>

The spectral expansion is

$$
K_\tau(x,z)=\sum_n e^{-\tau\lambda_n}u_n(x)\overline{u_n(z)},
$$

and similarly

$$
K_\sigma(z,y)=\sum_m e^{-\sigma\lambda_m}u_m(z)\overline{u_m(y)}.
$$

Multiplying and integrating over $z$ gives

$$
\int_Xd\mu(z)K_\tau(x,z)K_\sigma(z,y)
=
\sum_{n,m}e^{-\tau\lambda_n}e^{-\sigma\lambda_m}
u_n(x)\overline{u_m(y)}
\int_Xd\mu(z)\overline{u_n(z)}u_m(z).
$$

Orthonormality gives $\delta_{nm}$, so this becomes

$$
\sum_n e^{-(\tau+\sigma)\lambda_n}u_n(x)\overline{u_n(y)}
=K_{\tau+\sigma}(x,y).
$$

</details>

### Exercise 3: Proper-time inverse

Let $L$ be positive self-adjoint with no zero modes. Prove formally that

$$
G(x,y)=\int_0^\infty d\tau\,K_\tau(x,y)
$$

satisfies

$$
L_xG(x,y)=\delta_\mu(x,y).
$$

<details><summary><strong>Solution</strong></summary>

Using the heat equation,

$$
L_xK_\tau(x,y)=-\partial_\tau K_\tau(x,y).
$$

Therefore

$$
L_xG(x,y)
=\int_0^\infty d\tau\,L_xK_\tau(x,y)
=-\int_0^\infty d\tau\,\partial_\tau K_\tau(x,y).
$$

Integrating in $\tau$ gives

$$
L_xG(x,y)=K_{0^+}(x,y)-K_{\infty}(x,y).
$$

If there are no zero modes and the positive spectrum is sufficiently well behaved, $K_{\infty}=0$ in the relevant sense. Since $K_{0^+}=\delta_\mu$, one obtains

$$
L_xG(x,y)=\delta_\mu(x,y).
$$

If zero modes exist, $K_\infty$ is the projection onto the zero-mode subspace, and the formula gives the inverse only on the orthogonal complement.

</details>

### Exercise 4: Identify the logarithmic divergence

Suppose in $d=4$ that

$$
\operatorname{Tr}e^{-\tau L}
\sim
\frac1{(4\pi\tau)^2}(A_0+\tau A_1+\tau^2A_2+\cdots)
$$

as $\tau\downarrow0$. Which term gives a logarithmic divergence in

$$
-\frac12\int_{\epsilon^2}^\infty\frac{d\tau}{\tau}\operatorname{Tr}e^{-\tau L}?
$$

<details><summary><strong>Solution</strong></summary>

Insert the expansion. The determinant integrand contains

$$
\frac{d\tau}{\tau}\frac1{(4\pi)^2}
\left(A_0\tau^{-2}+A_1\tau^{-1}+A_2+\cdots\right).
$$

Thus the $A_2$ term contributes

$$
-\frac12\frac{A_2}{(4\pi)^2}\int_{\epsilon^2}\frac{d\tau}{\tau},
$$

which is logarithmically divergent. The $A_0$ and $A_1$ terms give power divergences.

</details>

## References

- R. Courant and D. Hilbert, *Methods of Mathematical Physics*, Vol. II.
- L. C. Evans, *Partial Differential Equations*.
- P. B. Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*.
- N. Berline, E. Getzler, and M. Vergne, *Heat Kernels and Dirac Operators*.
- D. V. Vassilevich, "Heat kernel expansion: user's manual," *Physics Reports* 388 (2003).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II.
- M. Srednicki, *Quantum Field Theory*.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*.
- M. Marino, *Instantons and Large N*.
- V. Pestun et al., "Localization techniques in quantum field theories," *Journal of Physics A* 50 (2017).

## Version history

- 2026-06-25: First polished draft for the Mathematical Toolkit.
