---
title: "Partial Differential Equations"
description: "Explains partial differential equations in QFT: differential operators, principal symbols, elliptic/hyperbolic/parabolic type, weak solutions, characteristics, data, boundary conditions, pole prescriptions, and propagators."
sidebar:
  label: "Partial Differential Equations"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard PDE and mathematical-physics references, including Evans, Folland, Hörmander, Taylor, Strauss, Courant–Hilbert, Reed–Simon, Bär–Ginoux–Pfäffle, and QFT treatments of wave equations, Euclidean operators, propagators, and heat kernels."
topics:
  - partial differential equations
  - differential operators
  - principal symbols
  - elliptic equations
  - hyperbolic equations
  - parabolic equations
  - weak solutions
  - characteristics
  - boundary conditions
  - initial-value problems
  - pole prescriptions
  - propagators
canonicalTopics:
  - partial-differential-equation
  - differential-operator
  - principal-symbol
  - elliptic-equation
  - hyperbolic-equation
  - parabolic-equation
  - weak-solution
  - characteristic-variety
  - boundary-condition
  - initial-value-problem
  - pole-prescription
  - propagator
researchStatus:
  established:
    - "The principal symbol, equation type, weak formulation, and boundary or initial data are standard tools for understanding PDEs that occur in classical field theory and QFT."
  active:
    - "Nonlinear PDEs, singular spacetimes, gauge constraints, microlocal propagation of singularities, stochastic PDEs, and interacting QFT require techniques beyond this introductory page."
---

## Summary

Partial differential equations are where local field theory first becomes mathematical physics. A classical field equation, a free quantum propagator, a heat kernel, a linear response function, and a one-loop determinant all begin with the same kind of object: a differential operator acting on functions or sections over a space or spacetime.

The bare expression

$$
Lu=f
$$

is not enough. To know what it means, one must ask:

$$
\text{What is }L?\quad
\text{On what domain?}\quad
\text{With what data?}\quad
\text{With what inverse prescription?}
$$

This page gives the minimal PDE toolkit needed before Green functions, heat kernels, wave equations, boundary-value problems, and Schrödinger operators.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing a linear PDE, its principal symbol, problem data, elliptic, hyperbolic, and parabolic types, and the corresponding QFT readings.](/figures/math-toolkit/pde-principal-symbol-classification.svg)

<figcaption>

The principal symbol $\sigma_L(x,\xi)$ is the highest-derivative part of a linear differential operator. It controls the local type of a PDE. Elliptic equations are naturally tied to boundary-value problems and Euclidean inverses; hyperbolic equations to initial-value problems and causal propagation; parabolic equations to heat semigroups and smoothing. The data and pole prescription still matter.

</figcaption>
</figure>

The working slogan is

$$
\text{PDE} = \text{local differential rule} + \text{global problem data}.
$$

Leaving out the second half is the source of many fake paradoxes about Green functions, boundary conditions, gauge fixing, and causality.

## Prerequisites

You should know multivariable calculus, Fourier transforms, distributions, integration by parts, and basic linear-operator language. The most relevant earlier pages are [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/), [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), and [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/).

The previous page, [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), explains first-order systems, Wronskians, boundary data, and one-dimensional Green kernels. This page upgrades those ideas to fields depending on several variables.

## Differential operators and multi-index notation

Let $x=(x^1,\ldots,x^n)$ be local coordinates. A multi-index is

$$
\alpha=(\alpha_1,\ldots,\alpha_n),
\qquad
|\alpha|=\alpha_1+\cdots+\alpha_n,
$$

and

$$
\partial^\alpha
=\partial_1^{\alpha_1}\cdots\partial_n^{\alpha_n}.
$$

A linear differential operator of order $m$ can be written locally as

$$
L=\sum_{|\alpha|\le m}a_\alpha(x)\partial^\alpha.
$$

The highest-derivative terms are the principal part:

$$
L_{\mathrm{pr}}=\sum_{|\alpha|=m}a_\alpha(x)\partial^\alpha.
$$

Replacing $\partial_j$ by a covector component $\xi_j$ gives the principal symbol,

$$
\sigma_L(x,\xi)=\sum_{|\alpha|=m}a_\alpha(x)\xi^\alpha,
$$

up to conventional factors of $i$ depending on whether one wants the polynomial associated with $\partial\to \xi$ or the Fourier symbol associated with $\partial\to ip$. In this page, the classification only depends on the zero set and signature of the highest-derivative part, so these harmless powers of $i$ will not matter.

For systems of equations, $a_\alpha(x)$ can be matrices and $\sigma_L(x,\xi)$ is a matrix. Gauge theories add another layer: the principal symbol may have null directions because gauge transformations are redundancies, not physical waves.

## Why the principal symbol matters

Lower-derivative terms matter for spectra, masses, potentials, damping, and detailed solutions. But the principal symbol controls the local analytic character of the equation. It tells us whether the equation behaves locally like a boundary-value problem, an initial-value problem, or diffusion.

For a second-order scalar equation in two variables,

$$
A u_{xx}+2B u_{xy}+C u_{yy}+\text{lower-order terms}=f,
$$

the principal symbol is

$$
A\xi_x^2+2B\xi_x\xi_y+C\xi_y^2.
$$

The discriminant is

$$
\Delta=B^2-AC.
$$

The equation is locally:

| Type | Condition | Prototype |
|---|---:|---|
| elliptic | $\Delta<0$ | Laplace equation $u_{xx}+u_{yy}=0$ |
| hyperbolic | $\Delta>0$ | wave equation $u_{tt}-u_{xx}=0$ |
| parabolic | $\Delta=0$ | heat equation $u_t-u_{xx}=0$ after choosing time |

This two-variable criterion is not the general definition, but it is the best first mental model.

In higher dimensions, ellipticity means the principal symbol is invertible for every nonzero real covector $\xi$. Hyperbolicity involves a distinguished time direction and real characteristic cones. Parabolic equations mix first order in time with elliptic behavior in space.

## Constant coefficients and Fourier space

For constant-coefficient linear PDEs, Fourier transform turns differential equations into algebraic equations. With the convention

$$
\widehat f(p)=\int d^nx\,e^{ip\cdot x}f(x),
\qquad
f(x)=\int\frac{d^np}{(2\pi)^n}e^{-ip\cdot x}\widehat f(p),
$$

we have

$$
\partial_\mu f(x)
\longleftrightarrow
-ip_\mu\widehat f(p).
$$

Thus

$$
P(\partial)u=f
$$

becomes

$$
P(-ip)\widehat u(p)=\widehat f(p).
$$

The formal solution is

$$
\widehat u(p)=\frac{\widehat f(p)}{P(-ip)}.
$$

This formula is useful and dangerous. It is useful because it makes translation-invariant kernels explicit. It is dangerous because $P(-ip)$ may vanish. At its zeros, the inverse must be interpreted as a distribution with a prescription.

For the Klein–Gordon operator in Lorentzian signature,

$$
(\Box+m^2)\phi=J,
$$

the denominator is related to

$$
p^2-m^2.
$$

As a distribution, $1/(p^2-m^2)$ is incomplete. Retarded, advanced, principal-value, and Feynman prescriptions give different inverses.

## Elliptic equations

The prototype elliptic operator is

$$
L=-\Delta+m^2
$$

on a Euclidean domain. Its principal symbol is

$$
|\xi|^2,
$$

which is positive for $\xi\neq0$. Elliptic equations are rigid: boundary data control the interior, and solutions tend to be smoother than the sources.

A typical elliptic boundary-value problem is

$$
(-\Delta+m^2)u=f\quad\text{in }\Omega,
\qquad
u|_{\partial\Omega}=g,
$$

where $\Omega$ is a spatial or Euclidean spacetime domain. Other boundary conditions include Neumann and Robin data:

$$
\partial_n u|_{\partial\Omega}=h,
\qquad
(\partial_n u+\kappa u)|_{\partial\Omega}=h.
$$

Elliptic operators are central in Euclidean QFT. Free Euclidean scalar theory uses

$$
L=-\Delta+m^2.
$$

Gauge-fixed Yang–Mills theory and fermion determinants often lead to Laplace-type or Dirac-type elliptic operators. Heat kernels and zeta determinants are most naturally built from positive elliptic operators.

The key elliptic slogan is:

$$
\text{elliptic operator} + \text{boundary/domain data}
\quad\Rightarrow\quad
\text{inverse, spectrum, determinant}.
$$

## Hyperbolic equations

The prototype hyperbolic equation is the wave equation

$$
(\partial_t^2-\Delta)u=f.
$$

With the mostly-minus QFT convention, the Klein–Gordon equation is

$$
(\Box+m^2)\phi=J,
\qquad
\Box=\partial_t^2-\nabla^2.
$$

Hyperbolic equations are evolution equations. Their natural data are initial data on a time slice:

$$
u(0,\mathbf x)=u_0(\mathbf x),
\qquad
\partial_tu(0,\mathbf x)=u_1(\mathbf x).
$$

For the wave equation, disturbances propagate at finite speed. In relativistic QFT, this is the PDE origin of light cones and causal support. Retarded Green functions vanish outside the future light cone of their source. Advanced Green functions vanish outside the past light cone. The Feynman propagator is not a classical response function; it is the inverse selected by time ordering and the $i\epsilon$ prescription.

The characteristic covectors of the wave operator satisfy

$$
\xi_0^2-\boldsymbol\xi^2=0.
$$

This is the light cone in cotangent space. Characteristics are where singularities can propagate. For the Klein–Gordon equation, the mass term $m^2$ changes dispersion but not the principal symbol, so it does not change the characteristic cone.

## Parabolic equations

The prototype parabolic equation is the heat equation

$$
\partial_su-\Delta u=0.
$$

The parameter $s$ is often called heat time or proper time. For a positive elliptic operator $L$, the abstract heat equation is

$$
(\partial_s+L)K(s;x,y)=0,
\qquad
K(0;x,y)=\delta(x-y).
$$

Its solution is the heat kernel

$$
K(s;x,y)=\langle x|e^{-sL}|y\rangle.
$$

Parabolic equations smooth forward in $s$. Even rough initial data can become smooth for $s>0$ when the operator is elliptic in space. In QFT this smoothing is a feature, not a bug. It is why the heat kernel acts as a UV microscope: small $s$ probes short distances, while positive $s$ regularizes high modes.

The heat-kernel trace appears in determinants:

$$
\log\det L
=-\int_0^\infty\frac{ds}{s}\,\operatorname{Tr}e^{-sL}
$$

after regularization and treatment of zero modes. This connects PDE theory to one-loop effective actions, anomalies, Casimir energies, and spectral geometry.

## Weak solutions and distributions

Many QFT kernels are not ordinary functions. They are distributions. The equation

$$
L_xG(x,y)=\delta(x-y)
$$

usually means a weak identity. For a test function $\varphi$, one defines the action of $L$ on a distribution $T$ by moving derivatives onto the test function:

$$
\langle LT,\varphi\rangle
=\langle T,L^\dagger\varphi\rangle,
$$

up to the convention for adjoints and complex conjugation. Boundary terms must be accounted for if the domain has a boundary.

For example, the distributional equation

$$
-\Delta G(x)=\delta^{(n)}(x)
$$

means

$$
\int d^nx\,G(x)(-\Delta\varphi(x))=\varphi(0)
$$

for suitable test functions, with signs determined by integration by parts.

Weak formulations are not a retreat from rigor. They are the correct language for delta sources, discontinuities, shocks, Green functions, propagators, and operator-valued distributions.

## Boundary data, initial data, and well-posedness

A PDE problem is well posed if the solution exists, is unique, and depends continuously on the data in the chosen norms. This is the PDE version of “small input errors should not explode for no physical reason.”

Different equation types want different data.

| Equation type | Natural data | Typical QFT interpretation |
|---|---|---|
| elliptic | boundary data | Euclidean inverse, spectrum, determinant |
| hyperbolic | initial data and causal prescription | Lorentzian propagation, commutators, response |
| parabolic | initial data in heat time plus boundary data in space | heat kernel, proper-time regulator |

Giving the wrong kind of data can overdetermine or underdetermine the problem. For the Laplace equation, arbitrary initial data on a time slice are usually not the right data. For the wave equation, boundary data on a spatial boundary may be needed in a finite cavity, but initial data drive the evolution.

This matters in QFT because boundary conditions encode physical choices: finite volume, thermal compactification, reflecting walls, defects, branes, asymptotic scattering states, or horizon regularity.

## Characteristics and propagation

For a first-order PDE

$$
a^\mu(x)\partial_\mu u(x)=f(x),
$$

characteristics are curves $x^\mu(s)$ satisfying

$$
\frac{dx^\mu}{ds}=a^\mu(x(s)).
$$

Along such curves, the PDE becomes an ODE:

$$
\frac{d}{ds}u(x(s))=f(x(s)).
$$

This is the method of characteristics.

For higher-order PDEs, the characteristic set is controlled by the principal symbol. Covectors $\xi$ satisfying

$$
\sigma_L(x,\xi)=0
$$

are characteristic. For the wave operator, this set is the null cone. Singularities of solutions can propagate along characteristic directions.

This is one of the deep bridges to microlocal analysis: high-frequency behavior is controlled by the principal symbol, much as classical mechanics is controlled by a Hamiltonian. In semiclassical QFT, geometric optics, WKB, and propagation of singularities are all descendants of this idea.

## PDEs on bundles and in gauge theory

Fields are not always scalar functions. They may be sections of vector bundles: spinors, differential forms, gauge fields, or tensor fields. A differential operator may therefore act as

$$
L:\Gamma(E)\to\Gamma(F),
$$

where $E$ and $F$ are bundles over spacetime or space.

Examples include:

$$
D\psi=\gamma^\mu\nabla_\mu\psi
$$

for a Dirac operator, and

$$
d_A^\dagger d_A+d_Ad_A^\dagger
$$

for gauge-covariant Laplace-type operators on forms.

Gauge theories are special because gauge redundancy makes the naive PDE underdetermined. Maxwell's equations, Yang–Mills equations, and linearized gravity contain constraints and gauge directions. To invert the quadratic operator in perturbation theory, one usually fixes a gauge. The resulting operator may become elliptic in Euclidean signature or hyperbolic in Lorentzian signature, but ghost operators and residual zero modes must also be treated.

The PDE slogan becomes:

$$
\text{gauge PDE} + \text{gauge fixing} + \text{residual-zero-mode treatment}
= \text{invertible problem}.
$$

Skipping that middle term is how one ends up trying to invert a symmetry.

## Nonlinear PDEs and linearization

Classical field equations are usually nonlinear. Yang–Mills theory, general relativity, nonlinear sigma models, Gross–Pitaevskii equations, and soliton equations all involve nonlinear PDEs.

A nonlinear field equation can be written schematically as

$$
F(\phi)=0.
$$

Near a solution $\phi_\star$, write

$$
\phi=\phi_\star+\eta.
$$

Then

$$
F(\phi_\star+\eta)=F(\phi_\star)+L_{\phi_\star}\eta+O(\eta^2),
$$

where

$$
L_{\phi_\star}=\left.\frac{\delta F}{\delta\phi}\right|_{\phi_\star}
$$

is the linearized operator. This operator controls stability, small fluctuations, zero modes, one-loop determinants, and the first approximation to dynamics near the background.

In path-integral language, the same operator appears as the Hessian of the action:

$$
S[\phi_\star+\eta]
=S[\phi_\star]+\frac12\langle\eta,L_{\phi_\star}\eta\rangle+\cdots.
$$

So even when the original PDE is nonlinear, linear PDE theory is the doorway to perturbation theory.

## Propagators as PDE inverses

In free scalar QFT, the Feynman propagator satisfies

$$
(\Box_x+m^2)\Delta_F(x-y)=-i\delta^{(d)}(x-y)
$$

or an equivalent convention-dependent variant. With the usual momentum-space convention, it is represented by

$$
\Delta_F(x-y)=\int\frac{d^dp}{(2\pi)^d}
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

The $i\epsilon$ is part of the PDE inverse. It tells the distribution how to avoid the mass-shell singularity and encodes time ordering.

The retarded Green function instead uses a prescription that gives causal support. The Euclidean Green function in $d$ dimensions solves

$$
(-\Delta_x+m^2)G_E(x-y)=\delta^{(d)}(x-y)
$$

and has Fourier representation

$$
G_E(x-y)=\int\frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

These are all Green functions, but they are not interchangeable. Different inverse prescriptions mean different physics.

## Regularity, singularities, and ultraviolet behavior

PDE regularity has a direct QFT interpretation.

Elliptic operators tend to improve regularity: if $Lu=f$ and $f$ is smooth, then $u$ is often smooth away from boundaries and singularities. This smoothing underlies the short-distance structure of Euclidean Green functions and heat kernels.

Hyperbolic operators propagate singularities. A sharp disturbance does not instantly smooth out; it travels along characteristic directions. This is the PDE core of causal propagation.

Parabolic operators smooth forward in heat time. This is why $e^{-sL}$ suppresses high eigenvalues for $s>0$:

$$
e^{-s\lambda}\to0
\qquad (\lambda\to\infty,\ s>0).
$$

In QFT, high eigenvalues are ultraviolet modes. Heat flow damps them; the small-$s$ limit reveals how many there are and how they diverge.

## Common pitfalls

**Thinking that a PDE is just an equation.** A PDE problem includes domain, data, function space, and sometimes gauge choice or pole prescription.

**Confusing the operator with its principal symbol.** The principal symbol controls local type and high-frequency behavior, but lower-order terms still affect masses, spectra, resonances, and exact kernels.

**Using elliptic intuition for hyperbolic equations.** Elliptic equations are controlled by boundary data; hyperbolic equations are controlled by initial data and causal propagation.

**Treating $1/P(p)$ as an ordinary function when $P(p)=0$.** Momentum-space inverses often require a distributional prescription.

**Calling the Feynman propagator a retarded response.** The Feynman propagator is time ordered. The retarded Green function is causal response. They are related, but not equal.

**Forgetting boundary terms in weak formulations.** Integration by parts creates boundary terms. Boundary conditions decide whether they vanish.

**Ignoring gauge redundancy.** Gauge-field equations usually have non-invertible quadratic operators until a gauge is fixed and residual zero modes are handled.

**Assuming Euclidean and Lorentzian problems are the same after replacing $t$ by $-i\tau$.** Wick rotation is powerful, but boundary conditions, singularities, contours, and operator domains matter.

## Exercises

### Exercise 1: Classify second-order equations

Classify the following equations in two variables using $\Delta=B^2-AC$ for

$$
Au_{xx}+2Bu_{xy}+Cu_{yy}+\cdots=0.
$$

1. $u_{xx}+u_{yy}=0$.
2. $u_{tt}-u_{xx}=0$.
3. $u_{xx}+2u_{xy}+u_{yy}=0$.

<details><summary><strong>Solution</strong></summary>

1. Here $A=1$, $B=0$, $C=1$, so

$$
\Delta=0^2-1\cdot1=-1<0.
$$

The equation is elliptic.

2. Taking variables $(t,x)$, we have $A=1$, $B=0$, $C=-1$, so

$$
\Delta=0^2-1(-1)=1>0.
$$

The equation is hyperbolic.

3. Here $A=1$, $2B=2$, so $B=1$, and $C=1$. Thus

$$
\Delta=1^2-1\cdot1=0.
$$

The equation is parabolic or degenerate in this second-order classification. Indeed the principal part is

$$
(\partial_x+\partial_y)^2u.
$$

</details>

### Exercise 2: Fourier symbol of the Euclidean massive scalar operator

Using the convention

$$
f(x)=\int\frac{d^dp}{(2\pi)^d}e^{ip\cdot x}\widehat f(p),
$$

show that

$$
L=-\Delta+m^2
$$

has Fourier multiplier $p^2+m^2$.

<details><summary><strong>Solution</strong></summary>

For a plane wave $e^{ip\cdot x}$,

$$
\partial_j e^{ip\cdot x}=ip_j e^{ip\cdot x},
$$

so

$$
\Delta e^{ip\cdot x}=\sum_j\partial_j^2e^{ip\cdot x}
=-\sum_jp_j^2e^{ip\cdot x}=-p^2e^{ip\cdot x}.
$$

Therefore

$$
(-\Delta+m^2)e^{ip\cdot x}=(p^2+m^2)e^{ip\cdot x}.
$$

Thus the Fourier-space equation is

$$
(p^2+m^2)\widehat u(p)=\widehat f(p).
$$

</details>

### Exercise 3: Dispersion relation for Klein–Gordon waves

For the free Klein–Gordon equation

$$
(\partial_t^2-\nabla^2+m^2)\phi=0,
$$

insert the plane wave

$$
\phi(t,\mathbf x)=e^{-iEt+i\mathbf p\cdot\mathbf x}
$$

and derive the dispersion relation.

<details><summary><strong>Solution</strong></summary>

Acting on the plane wave,

$$
\partial_t^2\phi=-E^2\phi,
\qquad
\nabla^2\phi=-\mathbf p^2\phi.
$$

Thus

$$
(\partial_t^2-\nabla^2+m^2)\phi
=(-E^2+\mathbf p^2+m^2)\phi.
$$

For a nonzero plane wave solution, the coefficient must vanish:

$$
-E^2+\mathbf p^2+m^2=0.
$$

Hence

$$
E^2=\mathbf p^2+m^2.
$$

This is the usual relativistic dispersion relation.

</details>

### Exercise 4: Heat-kernel semigroup property

Suppose $L$ is a positive self-adjoint operator and

$$
K(s;x,y)=\langle x|e^{-sL}|y\rangle.
$$

Show formally that

$$
K(s+t;x,z)=\int dy\,K(s;x,y)K(t;y,z).
$$

<details><summary><strong>Solution</strong></summary>

Use the operator identity

$$
e^{-(s+t)L}=e^{-sL}e^{-tL},
$$

which holds because both factors are functions of the same operator $L$. Insert a resolution of identity in the position basis:

$$
\langle x|e^{-(s+t)L}|z\rangle
=\int dy\,\langle x|e^{-sL}|y\rangle\langle y|e^{-tL}|z\rangle.
$$

Therefore

$$
K(s+t;x,z)=\int dy\,K(s;x,y)K(t;y,z).
$$

In rigorous settings, the measure and meaning of $|x\rangle$ must be specified, but the kernel composition formula is exactly the operator semigroup property.

</details>

### Exercise 5: Transport equation by characteristics

Solve

$$
\partial_tu+v\partial_xu=0,
\qquad
u(0,x)=u_0(x),
$$

where $v$ is a constant.

<details><summary><strong>Solution</strong></summary>

The characteristic curves satisfy

$$
\frac{dx}{dt}=v.
$$

Thus

$$
x(t)=x_0+vt,
\qquad
x_0=x-vt.
$$

Along a characteristic,

$$
\frac{d}{dt}u(t,x(t))=\partial_tu+\frac{dx}{dt}\partial_xu
=\partial_tu+v\partial_xu=0.
$$

So $u$ is constant along the curve, and

$$
u(t,x)=u_0(x-vt).
$$

The initial profile is transported rigidly with speed $v$.

</details>

## References

For PDE theory, see Evans, *Partial Differential Equations*; Folland, *Introduction to Partial Differential Equations*; Taylor, *Partial Differential Equations*; Strauss, *Partial Differential Equations*; Hörmander, *The Analysis of Linear Partial Differential Operators*; and Courant and Hilbert, *Methods of Mathematical Physics*. For spectral and operator-theoretic viewpoints, see Reed and Simon, *Methods of Modern Mathematical Physics*. For hyperbolic equations on Lorentzian manifolds, see Bär, Ginoux, and Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*. For QFT usage, compare standard treatments of classical field equations, propagators, Euclidean continuation, heat kernels, and functional determinants in Srednicki, Zee, Weinberg, Coleman, Schwartz, Zinn-Justin, Altland–Simons, and Marino.

## Version history

- 2026-06-25: Initial polished draft.
