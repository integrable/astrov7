---
title: "Heat-Kernel Expansion"
description: "A QFT-oriented guide to heat kernels, short-time asymptotics, Seeley–DeWitt coefficients, proper-time determinants, ultraviolet divergences, anomalies, and local counterterms."
sidebar:
  label: "Heat-Kernel Expansion"
  order: 8
level: Graduate
status: "Polished draft"
source: "Seeley–DeWitt heat-kernel theory; standard QFT proper-time and background-field treatments in Coleman, Schwartz, Weinberg, Zinn-Justin, Nakahara, and spectral-geometry references."
topics:
  - heat kernels
  - Seeley–DeWitt coefficients
  - proper-time regularization
  - one-loop effective actions
  - ultraviolet divergences
canonicalTopics:
  - heat-kernel-expansion
  - seeley-dewitt-coefficients
  - proper-time-regularization
  - one-loop-effective-actions
researchStatus:
  established:
    - "The short-time heat-kernel expansion of Laplace-type operators is a standard local tool for organizing one-loop ultraviolet divergences, anomalies, and determinant regularization."
  active:
    - "Boundary conditions, nonminimal operators, manifolds with singularities, gauge zero modes, Lorentzian continuation, and global spectral information remain subtle in advanced QFT applications."
---

## Summary

The heat kernel of an operator $K$ is the kernel of $e^{-tK}$. In coordinates, it is the object $H(t;x,y)$ satisfying

$$
(\partial_t+K_x)H(t;x,y)=0,
\qquad
H(t;x,y)\to\delta(x,y)
\quad\text{as }t\to0^+.
$$

The trace

$$
\operatorname{Tr}(e^{-tK})
=\int d^d x\,\operatorname{tr}H(t;x,x)
$$

is the heat trace. It connects directly to one-loop determinants because formally

$$
\operatorname{Tr}\log K
=-\int_0^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tK})+\text{constant}.
$$

The ultraviolet region of a one-loop determinant is the short-time region $t\to0^+$. For a Laplace-type operator on a smooth compact $d$-dimensional Euclidean space without boundary, the heat trace has the asymptotic expansion

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{r\ge0}A_r(K)t^r,
\qquad t\to0^+.
$$

The coefficients $A_r(K)$ are local. They are integrals of polynomials in background fields, curvature, gauge field strengths, endomorphism terms, and their derivatives. This is the clean mathematical reason one-loop ultraviolet divergences are local and can be matched to counterterms.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Flow diagram showing the heat trace, its short-time expansion, and how the first few coefficients generate one-loop ultraviolet divergences.](/figures/math-toolkit/heat-kernel-divergence-ladder.svg)

<figcaption>

The heat-kernel expansion converts the ultraviolet part of a one-loop determinant into local coefficients. In four dimensions, $A_0$, $A_1$, and $A_2$ are the divergent coefficients; $A_2$ controls the logarithmic divergence.

</figcaption>
</figure>

The slogan is:

$$
\text{short heat time} = \text{high eigenvalues} = \text{ultraviolet locality}.
$$

## Prerequisites

You should know [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/). Functional determinants explain why $\operatorname{Tr}\log K$ appears; zeta regularization explains how the heat trace enters spectral analytic continuation.

The distributional and Fourier background from [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), and [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) is useful for understanding kernels and Green functions. The operator-domain warnings in [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/) are also relevant: the heat kernel depends on the operator, its domain, and its boundary conditions.

## Core idea

In finite dimension, if $K$ has positive eigenvalues $\lambda_n$, then

$$
\operatorname{Tr}(e^{-tK})=\sum_n e^{-t\lambda_n}.
$$

For small $t$, large eigenvalues are not strongly suppressed. For large $t$, large eigenvalues are exponentially suppressed and the trace is controlled by small eigenvalues. Thus $t$ behaves like an inverse energy-squared resolution scale.

The determinant is related to the heat trace by

$$
\log\lambda
=-\int_0^\infty\frac{dt}{t}e^{-t\lambda}+\text{constant}.
$$

Summing over eigenvalues gives

$$
\operatorname{Tr}\log K
=-\int_0^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tK})+\text{constant}.
$$

The constant is divergent and independent of $\lambda$; in determinant ratios or renormalized quantities, it is fixed by a convention. The useful regulated version is

$$
\operatorname{Tr}\log K\big|_{\epsilon}
=-\int_{\epsilon}^{\infty}\frac{dt}{t}\operatorname{Tr}(e^{-tK}),
$$

where $\epsilon$ is a proper-time cutoff. Since small $t$ corresponds to high eigenvalues, $\epsilon\sim \Lambda^{-2}$ is an ultraviolet cutoff.

The heat-kernel expansion tells us exactly what local expressions appear as $\epsilon\to0^+$.

## Setup and conventions

This page focuses on Euclidean Laplace-type operators. A clean model is

$$
K=-g^{\mu\nu}\nabla_\mu\nabla_\nu+X,
$$

acting on sections of a vector bundle over a $d$-dimensional Riemannian manifold $M$. Here:

- $\nabla_\mu$ is a connection that may include spin, gauge, or bundle data;
- $X$ is an endomorphism, often called a potential term;
- the bundle curvature is

$$
\Omega_{\mu\nu}=[\nabla_\mu,\nabla_\nu].
$$

The sign convention matters. With this convention, the flat scalar operator is

$$
K=-\partial^2+m^2,
$$

so $X=m^2$.

For clarity, first assume $M$ is compact and has no boundary, and assume $K$ is positive. Boundaries, zero modes, negative modes, noncompact spaces, and Lorentzian signatures are discussed later as caveats.

The heat kernel $H(t;x,y)$ is a section of the external tensor product of the bundle at $x$ and the dual bundle at $y$. In practical physics formulas, one can first think of it as a matrix-valued kernel satisfying

$$
(e^{-tK}f)(x)=\int_M d^d y\sqrt{g(y)}\,H(t;x,y)f(y).
$$

The trace is

$$
\operatorname{Tr}(e^{-tK})
=\int_M d^d x\sqrt{g}\,\operatorname{tr}_{\mathrm{bundle}}H(t;x,x).
$$

The lowercase trace is over internal bundle indices; the uppercase trace includes integration over spacetime.

## The flat heat kernel

For

$$
K=-\partial^2+m^2
$$

on flat $\mathbb R^d$, the heat kernel is

$$
H(t;x,y)
=\int\frac{d^d p}{(2\pi)^d}
\exp\left[ip\cdot(x-y)-t(p^2+m^2)\right].
$$

The Gaussian momentum integral gives

$$
H(t;x,y)
=\frac{1}{(4\pi t)^{d/2}}
\exp\left[-\frac{(x-y)^2}{4t}-m^2t\right].
$$

This formula already shows the geometry of heat time. The kernel is localized near $x=y$ with width

$$
|x-y|\sim \sqrt t.
$$

As $t\to0^+$, the kernel probes only an arbitrarily small neighborhood of each point. That locality is why the short-time expansion is built from local invariants.

For finite volume $V$ with translation-invariant boundary conditions, the trace per unit volume is

$$
\frac{1}{V}\operatorname{Tr}(e^{-tK})
=\frac{e^{-m^2t}}{(4\pi t)^{d/2}}.
$$

Expanding the mass factor gives

$$
\frac{1}{V}\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\left(1-m^2t+\frac12m^4t^2-\frac16m^6t^3+\cdots\right).
$$

This is the simplest heat-kernel expansion. In curved space and background fields, the coefficients become local curvature and field-strength invariants.

## Local expansion and coefficient notation

We use the convention

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{r\ge0}A_r(K)t^r.
$$

Some references instead label the same coefficients as $a_0,a_2,a_4,\ldots$, because the corresponding local invariants have increasing mass dimension $0,2,4,\ldots$. In this page, $A_r$ is the coefficient of $t^r$.

For a closed manifold and the operator

$$
K=-g^{\mu\nu}\nabla_\mu\nabla_\nu+X,
$$

the first integrated coefficients are

$$
A_0=\int_M d^d x\sqrt g\,\operatorname{tr}\mathbf 1,
$$

and

$$
A_1=\int_M d^d x\sqrt g\,\operatorname{tr}\left(\frac{R}{6}\mathbf 1-X\right).
$$

Ignoring total derivatives on a closed manifold, the next coefficient is

$$
A_2=\int_M d^d x\sqrt g\,\operatorname{tr}\left[
\frac12X^2-\frac16RX+\frac{1}{12}\Omega_{\mu\nu}\Omega^{\mu\nu}
+\frac{1}{360}\left(5R^2-2R_{\mu\nu}R^{\mu\nu}+2R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}\right)\mathbf 1
\right].
$$

This formula is a convention-sensitive reference point. If a source defines the Laplace-type operator as

$$
K=-(\nabla^2+E),
$$

then $E=-X$ in the convention of this page. Sign errors in $X$ are one of the most common ways heat-kernel calculations go sideways. Delightful little trapdoor, that one.

The first few coefficients have familiar QFT meanings:

| Coefficient | Local content | Typical QFT role |
|---|---|---|
| $A_0$ | volume and number of components | vacuum energy, cosmological term |
| $A_1$ | mass/potential and scalar curvature | mass terms, curvature coupling, Einstein–Hilbert term |
| $A_2$ | $X^2$, $RX$, $\Omega_{\mu\nu}^2$, curvature squared | gauge kinetic terms, four-dimensional log divergences, trace anomalies |

The exact interpretation depends on the theory and the background fields.

## Divergences from the proper-time cutoff

A one-loop bosonic determinant contains

$$
\Gamma^{(1)}=\frac12\operatorname{Tr}\log K.
$$

With a proper-time cutoff,

$$
\Gamma^{(1)}_\epsilon
=-\frac12\int_\epsilon^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tK}).
$$

Insert the heat-kernel expansion:

$$
\Gamma^{(1)}_\epsilon
\sim
-\frac12\frac{1}{(4\pi)^{d/2}}
\sum_{r\ge0}A_r
\int_\epsilon dt\,t^{r-d/2-1}.
$$

The term $A_r$ is ultraviolet divergent if

$$
r-\frac d2-1\le -1,
$$

or

$$
r\le\frac d2.
$$

If $r<d/2$, the divergence is a power divergence. If $r=d/2$, the divergence is logarithmic.

In four dimensions,

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^2}
\left(A_0+A_1t+A_2t^2+\cdots\right).
$$

Then

$$
\Gamma^{(1)}_\epsilon
\sim
-\frac{1}{2(4\pi)^2}
\left[
\frac{A_0}{2\epsilon^2}
+\frac{A_1}{\epsilon}
+A_2\log\frac{1}{\epsilon}
+\cdots
\right]
+\text{finite and infrared terms}.
$$

The coefficient $A_2$ controls the logarithmic divergence in $d=4$. This is why $A_2$ is so prominent in four-dimensional anomalies and one-loop beta-function calculations.

Power divergences are regulator-dependent. Logarithmic divergences are more robust, though their finite parts still depend on the renormalization scheme.

## Relation to zeta regularization

For positive $K$,

$$
\zeta_K(s)
=\frac{1}{\Gamma(s)}
\int_0^\infty dt\,t^{s-1}\operatorname{Tr}(e^{-tK}).
$$

The small-$t$ heat-kernel term

$$
\frac{1}{(4\pi)^{d/2}}A_r t^{r-d/2}
$$

produces a possible pole at

$$
s=\frac d2-r.
$$

Thus the heat-kernel coefficients determine the meromorphic structure of $\zeta_K(s)$. In particular, the value $\zeta_K(0)$ is tied to the coefficient of $t^0$ in the heat trace, with zero-mode subtleties:

$$
\zeta_K(0)
=\frac{A_{d/2}}{(4\pi)^{d/2}}
\quad\text{if }K\text{ has no zero modes and }d/2\text{ is an integer,}
$$

with appropriate modifications for boundaries and primed determinants. More generally, if zero modes are omitted, one subtracts their contribution to the large-$t$ heat trace.

This is the local origin of the scale dependence in zeta determinants:

$$
\mu\frac{\partial}{\partial\mu}\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-2\zeta_K(0).
$$

When $\zeta_K(0)$ is a local heat-kernel coefficient, scale dependence is local. That is exactly what renormalization needs.

## Green functions and variations

The heat kernel also represents the inverse of $K$. If $K$ is positive and invertible, then

$$
K^{-1}=\int_0^\infty dt\,e^{-tK}.
$$

In kernel notation,

$$
G(x,y)=\int_0^\infty dt\,H(t;x,y),
$$

where

$$
KG(x,y)=\delta(x,y).
$$

The determinant variation identity

$$
\delta\log\det K=\operatorname{Tr}(K^{-1}\delta K)
$$

can therefore be written as

$$
\delta\log\det K
=\int_0^\infty dt\,\operatorname{Tr}(e^{-tK}\delta K).
$$

If $\delta K=\delta X(x)$ is a local potential variation, then

$$
\delta\log\det K
=\int d^d x\sqrt g\,\operatorname{tr}\,G(x,x)\delta X(x).
$$

The coincident Green function $G(x,x)$ is singular in the ultraviolet. The small-$t$ heat-kernel expansion isolates precisely that singularity.

## Background fields and beta functions

Heat-kernel coefficients are especially powerful in background-field calculations. Suppose a heavy field is integrated out in a background gauge field. The one-loop determinant contains a term proportional to

$$
\int d^d x\,\operatorname{tr}F_{\mu\nu}F^{\mu\nu}
$$

inside the relevant heat-kernel coefficient. In four dimensions, that term appears in $A_2$ and controls a logarithmic divergence. After renormalization, it contributes to the running of the gauge coupling.

Similarly, in curved spacetime, $A_2$ contains curvature-squared terms such as

$$
R^2,
\qquad
R_{\mu\nu}R^{\mu\nu},
\qquad
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}.
$$

These terms organize one-loop gravitational counterterms and trace anomalies. The heat-kernel expansion is therefore a compact language for the local part of one-loop effective actions.

The nonlocal finite part of the determinant is not captured by a finite list of heat-kernel coefficients. Local coefficients tell you the ultraviolet counterterms. The full determinant also knows about the global spectrum.

## Boundaries and half-integer powers

If $M$ has a boundary, the heat-kernel expansion changes. Boundary conditions become part of the operator, and the trace generally contains half-integer powers:

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\left(A_0+A_{1/2}t^{1/2}+A_1t+A_{3/2}t^{3/2}+\cdots\right).
$$

The boundary coefficients involve intrinsic boundary geometry, extrinsic curvature, boundary potentials, and the chosen boundary condition. Dirichlet, Neumann, Robin, mixed, spectral, and gauge-compatible boundary conditions can give different coefficients.

This is not a nuisance term. In Casimir problems, finite-temperature manifolds, edge-mode physics, entanglement calculations, and gauge theories with boundaries, the boundary heat-kernel coefficients can carry physical information.

The safe rule is:

$$
\text{a heat-kernel coefficient is a coefficient of an operator plus boundary problem, not of a differential expression alone.}
$$

## Nonminimal operators and gauge theory

The clean formulas above apply to Laplace-type operators. Gauge theory often produces nonminimal operators before gauge fixing. For example, a vector fluctuation operator may contain terms such as

$$
\nabla_\mu\nabla_\nu
$$

in addition to a simple $-g_{\mu\nu}\nabla^2$ structure. Gauge fixing is usually chosen to produce Laplace-type operators plus ghost operators, because those are accessible to standard heat-kernel machinery.

In a background-field gauge, the one-loop gauge-field determinant and ghost determinant combine so that gauge-invariant local terms emerge. Separately, individual determinants may depend on gauge-fixing choices. The physical renormalized answer must be interpreted with the ghost contribution and counterterms included.

Zero modes from residual gauge transformations must be separated. Heat-kernel formulas for the nonzero spectrum do not divide by the volume of the gauge group automatically.

## Asymptotic does not mean convergent

The heat-kernel expansion is usually an asymptotic expansion:

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{r\ge0}A_r t^r
\quad(t\to0^+).
$$

It does not usually converge to the exact heat trace at finite $t$. It also says little by itself about large $t$, where zero modes, mass gaps, topology, volume, and boundary data dominate.

This distinction is crucial in QFT. Ultraviolet divergences are local, so the small-$t$ expansion is enough to classify counterterms and anomalies. But masses, finite-size effects, tunneling determinants, Casimir energies, and thermal free energies often depend on the full spectrum, not just the local asymptotic coefficients.

If a page or paper computes only the first few heat-kernel coefficients, it has computed the local ultraviolet part of the determinant, not the full one-loop effective action.

## Common pitfalls

**“The heat kernel is just another name for the propagator.”** They are related but not identical. The heat kernel is $e^{-tK}$; the Green function is $K^{-1}=\int_0^\infty dt\,e^{-tK}$ when the integral exists.

**“Small $t$ means infrared because $t$ is small.”** No. Small $t$ weakly suppresses large eigenvalues, so it probes the ultraviolet. Large $t$ suppresses large eigenvalues and probes the low spectrum.

**“The heat-kernel expansion gives the full determinant.”** Only the full heat trace gives the full determinant. The short-time expansion gives the ultraviolet asymptotics and local terms.

**“The coefficients are universal numbers.”** They are local invariants depending on the operator, connection, potential term, dimension, boundary conditions, and sign conventions.

**“$X=m^2$ always contributes $+m^2t$ in the expansion.”** With $K=-\partial^2+m^2$, the heat trace contains $e^{-m^2t}$, so the $t$ coefficient is $-m^2$. This sign is an excellent convention check.

**“Boundaries only affect finite terms.”** Boundaries can create half-integer heat-kernel coefficients and ultraviolet divergences localized on the boundary.

**“Gauge-field heat kernels can be computed field by field without ghosts.”** Gauge fixing, ghosts, residual gauge symmetries, and zero modes are part of the determinant problem. Omitting them usually breaks the calculation.

## Relations to other pages

[Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains why heat traces appear in one-loop effective actions. [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) explains the Mellin-transform relation between heat kernels and spectral zeta functions. [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) supplies the finite-dimensional determinant origin.

The kernel viewpoint connects back to [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/). Later pages on stationary phase, Jacobians, Faddeev–Popov determinants, anomalies, effective actions, curved-space QFT, and spectral theory should reuse this page as their local determinant technology.

## Research status

The heat-kernel expansion for Laplace-type operators on smooth manifolds is a mature and reliable tool. Its use in one-loop effective actions, anomalies, index theory, Casimir calculations, background-field methods, and zeta determinants is well established.

Active and delicate settings include manifolds with boundaries or corners, singular spaces, nonminimal gauge operators, noncompact backgrounds, time-dependent Lorentzian problems, spectral asymmetry, zero-mode normalization, and determinant phases. In these settings, the phrase “use the heat kernel” is the beginning of the calculation, not the end.

## Exercises

### Exercise 1: Flat heat kernel

Show that

$$
H(t;x,y)
=\frac{1}{(4\pi t)^{d/2}}
\exp\left[-\frac{(x-y)^2}{4t}-m^2t\right]
$$

satisfies

$$
(\partial_t-\partial_x^2+m^2)H(t;x,y)=0
$$

for $t>0$.

<details><summary><strong>Solution</strong></summary>

Write

$$
H(t;x,y)=e^{-m^2t}H_0(t;x,y),
$$

where

$$
H_0(t;x,y)=\frac{1}{(4\pi t)^{d/2}}
\exp\left[-\frac{(x-y)^2}{4t}\right]
$$

is the standard heat kernel for $-\partial^2$. It satisfies

$$
(\partial_t-\partial_x^2)H_0=0.
$$

Then

$$
\partial_t H=e^{-m^2t}\partial_tH_0-m^2e^{-m^2t}H_0,
$$

and

$$
-\partial_x^2 H=-e^{-m^2t}\partial_x^2H_0.
$$

Thus

$$
(\partial_t-\partial_x^2+m^2)H
=e^{-m^2t}(\partial_t-\partial_x^2)H_0=0.
$$

</details>

### Exercise 2: Four-dimensional divergence counting

Suppose

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^2}(A_0+A_1t+A_2t^2+A_3t^3+\cdots).
$$

Which terms are divergent in

$$
-\frac12\int_\epsilon^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tK})
$$

as $\epsilon\to0^+$?

<details><summary><strong>Solution</strong></summary>

Insert the expansion:

$$
-\frac12\int_\epsilon^\infty\frac{dt}{t}\operatorname{Tr}(e^{-tK})
\sim
-\frac{1}{2(4\pi)^2}
\int_\epsilon dt\,
\left(A_0t^{-3}+A_1t^{-2}+A_2t^{-1}+A_3+\cdots\right).
$$

The integrals of $t^{-3}$, $t^{-2}$, and $t^{-1}$ diverge at the lower limit. The $A_0$ term gives a power divergence proportional to $\epsilon^{-2}$, the $A_1$ term gives a power divergence proportional to $\epsilon^{-1}$, and the $A_2$ term gives a logarithmic divergence. The $A_3$ term and higher terms are finite at $t=0$.

Therefore $A_0$, $A_1$, and $A_2$ control the ultraviolet divergences in four dimensions.

</details>

### Exercise 3: Flat massive coefficients

For $K=-\partial^2+m^2$ in flat volume $V$, show that

$$
\operatorname{Tr}(e^{-tK})
=\frac{V}{(4\pi t)^{d/2}}e^{-m^2t}
$$

has coefficients

$$
A_r=V\frac{(-m^2)^r}{r!}.
$$

<details><summary><strong>Solution</strong></summary>

Expand the exponential:

$$
e^{-m^2t}=\sum_{r=0}^\infty\frac{(-m^2t)^r}{r!}.
$$

Then

$$
\operatorname{Tr}(e^{-tK})
=\frac{V}{(4\pi t)^{d/2}}
\sum_{r=0}^\infty\frac{(-m^2)^r}{r!}t^r.
$$

Comparing with

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{r\ge0}A_rt^r,
$$

we get

$$
A_r=V\frac{(-m^2)^r}{r!}.
$$

In particular, $A_0=V$, $A_1=-m^2V$, and $A_2=m^4V/2$.

</details>

### Exercise 4: Heat kernel and the Green function

Assume $K$ is positive and invertible. Show that

$$
K^{-1}=\int_0^\infty dt\,e^{-tK}
$$

by acting on an eigenvector of $K$.

<details><summary><strong>Solution</strong></summary>

Let $f_n$ be an eigenvector with

$$
Kf_n=\lambda_n f_n,
\qquad \lambda_n>0.
$$

Then

$$
e^{-tK}f_n=e^{-t\lambda_n}f_n.
$$

Acting with the proposed integral gives

$$
\left(\int_0^\infty dt\,e^{-tK}\right)f_n
=\int_0^\infty dt\,e^{-t\lambda_n}f_n
=\frac{1}{\lambda_n}f_n.
$$

But

$$
K^{-1}f_n=\frac{1}{\lambda_n}f_n.
$$

Since the eigenvectors form the spectral basis in this simplified setting, the operator identity follows.

</details>

### Exercise 5: Pole location from a heat coefficient

Assume a heat trace contains the term

$$
\frac{A_r}{(4\pi)^{d/2}}t^{r-d/2}.
$$

Use the Mellin transform relation to find the corresponding pole location of $\zeta_K(s)$.

<details><summary><strong>Solution</strong></summary>

The corresponding contribution to the Mellin integral is proportional to

$$
\frac{1}{\Gamma(s)}
\int_0 dt\,t^{s-1}t^{r-d/2}
=\frac{1}{\Gamma(s)}
\int_0 dt\,t^{s+r-d/2-1}.
$$

This integral has a pole when the exponent gives a logarithmic small-$t$ divergence:

$$
s+r-\frac d2=0.
$$

Therefore the possible pole is at

$$
s=\frac d2-r.
$$

This is the heat-kernel origin of the meromorphic structure of spectral zeta functions.

</details>

## References

- B. S. DeWitt, *Dynamical Theory of Groups and Fields*. Classic source for proper-time and heat-kernel methods in physics.
- P. B. Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*. Mathematical reference for heat coefficients and spectral geometry.
- D. V. Vassilevich, “Heat Kernel Expansion: User's Manual.” Practical QFT-oriented review of heat-kernel coefficients and applications.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Schwinger proper-time methods, effective actions, and background fields.
- S. Coleman, *Aspects of Symmetry*. Functional determinants, instantons, false-vacuum decay, and determinant ratios.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II. External field methods, gauge fixing, and one-loop determinant structure.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, saddle-point expansions, and renormalization.
- M. Nakahara, *Geometry, Topology and Physics*. Geometric operators, connections, curvature, index-theorem background, and heat-kernel-adjacent tools.
- V. Pestun et al., *Localization Techniques in Quantum Field Theories*. One-loop determinants, equivariant indices, and heat-kernel/spectral ideas in localization.

## Version history

- 2026-06-24: First polished draft. Introduced heat kernels as kernels of $e^{-tK}$, derived the flat kernel, fixed Laplace-type operator conventions, stated the first Seeley–DeWitt coefficients in the $K=-\nabla^2+X$ convention, connected short-time asymptotics to ultraviolet divergences, related heat kernels to zeta functions and Green functions, and discussed boundaries, gauge theory, asymptotic status, and exercises with solutions.
