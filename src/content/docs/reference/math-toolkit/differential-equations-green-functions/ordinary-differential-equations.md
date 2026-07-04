---
title: "Ordinary Differential Equations"
description: "Explains ordinary differential equations as mode equations in QFT: first-order systems, fundamental matrices, Wronskians, boundary data, singular points, eigenvalue problems, Green kernels, and stability."
sidebar:
  label: "Ordinary Differential Equations"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard mathematical physics and ODE references, including Coddington–Levinson, Hartman, Teschl, Olver, Courant–Hilbert, Bender–Orszag, and QFT treatments of oscillators, mode functions, radial equations, fluctuation operators, and RG flows."
topics:
  - ordinary differential equations
  - first-order systems
  - fundamental matrices
  - Wronskians
  - variation of constants
  - boundary-value problems
  - eigenvalue problems
  - singular points
  - Sturm–Liouville preview
  - Green kernels
  - stability
canonicalTopics:
  - ordinary-differential-equation
  - first-order-system
  - fundamental-matrix
  - wronskian
  - variation-of-constants
  - boundary-value-problem
  - eigenvalue-problem
  - singular-point
  - sturm-liouville-theory
  - green-kernel
  - stability-analysis
researchStatus:
  established:
    - "Linear ODE theory, fundamental systems, Wronskians, variation of constants, boundary-value problems, and eigenvalue problems are standard mathematical-physics tools used throughout QFT."
  active:
    - "Singular ODEs from defects, black-hole backgrounds, non-self-adjoint spectral problems, resurgence, and nonlinear dynamics often require specialized analytic or numerical methods beyond this introductory toolkit page."
---

## Summary

Ordinary differential equations are the one-dimensional skeleton behind many QFT calculations. They appear when a field equation is separated into modes, when a radial problem is reduced to partial waves, when a path integral is expanded around a saddle, when a renormalization-group equation is followed along scale, and when a one-dimensional quantum-mechanical model is used as a training ground for field theory.

The basic QFT pattern is simple:

$$
\text{field equation}
\quad\longrightarrow\quad
\text{mode equation in one variable}
\quad\longrightarrow\quad
\text{boundary data, spectrum, Green kernel}.
$$

For a scalar field in a static background, for example, expanding in spatial modes often reduces the equation to many oscillator equations. For a radial scattering problem, angular variables separate and each partial wave satisfies an ODE. For an instanton or soliton, the one-loop correction is controlled by a fluctuation operator that is often an ODE in the transverse coordinate. For a beta function, the coupling $g(\mu)$ satisfies an ODE in $\log\mu$.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram showing how a scalar ODE is rewritten as a first-order system, solved with a fundamental matrix, paired with data, Wronskians, and Green-kernel technology.](/figures/math-toolkit/ode-fundamental-solution-flow.svg)

<figcaption>

A linear ODE becomes usable after it is paired with data. Rewriting a scalar equation as a first-order system exposes the fundamental matrix $\Phi$, the Wronskian $W=\det\Phi$, and the variation-of-constants formula. Boundary or jump conditions then select the particular solution, spectrum, or Green kernel relevant to the physics problem.

</figcaption>
</figure>

This page is a compact repair manual for the ODE tools used later in Green functions, Sturm–Liouville theory, Schrödinger operators, heat kernels, semiclassics, and perturbation theory. It is not a replacement for a full ODE course. The goal is sharper: know what object is being solved for, what data are part of the problem, and what formulas are safe to use.

## Prerequisites

You should know single-variable calculus, linear algebra, integration by parts, complex numbers, and basic distribution language. The most relevant earlier pages are [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), and [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/).

We use the default conventions of the Mathematical Toolkit. Derivatives with respect to the ODE variable are written either as $d/dx$, primes, or $\partial_x$, depending on context.

## What an ODE problem really contains

A differential expression by itself is not a solved problem. The expression

$$
L=-\frac{d^2}{dx^2}+V(x)
$$

only tells us the local rule. To get a mathematical or physical problem, we must also specify the interval or domain, regularity assumptions, endpoint behavior, boundary or initial data, and sometimes an inner product. On the interval $[a,b]$, for instance, the same expression $-d^2/dx^2$ gives different spectra for Dirichlet, Neumann, Robin, and periodic boundary conditions.

There are three common ODE problem types in QFT.

| Problem type | Typical data | QFT role |
|---|---|---|
| initial-value problem | $y(x_0)$ and derivatives at $x_0$ | time evolution, mode propagation, RG flow |
| boundary-value problem | conditions at two or more endpoints | normal modes, finite-volume spectra, determinants |
| matching problem | continuity and jump conditions at singular points | Green functions, defects, delta potentials, interfaces |

The same ODE can appear in all three roles. For the harmonic oscillator,

$$
\ddot q+\omega^2q=0,
$$

an initial-value problem gives a trajectory. A boundary-value problem gives a classical path in a path integral. A matching problem gives the oscillator Green function.

That is the first anti-confusion device: the equation is not the whole problem. Data are part of the object.

## Linear equations and fundamental systems

A scalar $n$th-order linear ODE has the form

$$
a_n(x)y^{(n)}(x)+a_{n-1}(x)y^{(n-1)}(x)+\cdots+a_0(x)y(x)=f(x).
$$

Where $a_n(x)\neq 0$ and the coefficients are sufficiently regular, it can be rewritten as a first-order system. Define

$$
Y(x)=
\begin{pmatrix}
y(x)\\
y'(x)\\
\vdots\\
y^{(n-1)}(x)
\end{pmatrix}.
$$

Then

$$
Y'(x)=A(x)Y(x)+b(x),
$$

for an $n\times n$ matrix $A(x)$ and source vector $b(x)$. This is not just a trick. It is the cleanest way to understand solution spaces.

For the homogeneous equation

$$
Y'=A(x)Y,
$$

a fundamental matrix is a matrix $\Phi(x)$ whose columns are linearly independent solutions:

$$
\Phi'(x)=A(x)\Phi(x).
$$

If $\Phi(x_0)=I$, then the solution of the homogeneous initial-value problem is

$$
Y(x)=\Phi(x)Y(x_0).
$$

For the inhomogeneous system,

$$
Y'=A(x)Y+b(x),
$$

the variation-of-constants formula gives

$$
Y(x)=\Phi(x)Y(x_0)
+\int_{x_0}^{x}ds\,\Phi(x)\Phi(s)^{-1}b(s).
$$

This formula is the finite-dimensional ancestor of propagators, evolution kernels, time-ordered exponentials, and Dyson series. When $A(x)$ is a constant matrix, $\Phi(x)=e^{(x-x_0)A}$. When $A(x)$ does not commute with itself at different points, the solution is a path-ordered exponential:

$$
\Phi(x)=\mathcal P\exp\!\left(\int_{x_0}^{x}ds\,A(s)\right).
$$

That is already a Wilson-line-shaped formula in disguise.

## Wronskians and why they are conserved

For a second-order homogeneous equation

$$
y''+p(x)y'+q(x)y=0,
$$

the Wronskian of two solutions $u$ and $v$ is

$$
W[u,v](x)=u(x)v'(x)-u'(x)v(x).
$$

Differentiating and using the equation gives Abel's identity:

$$
W'[u,v](x)=-p(x)W[u,v](x),
$$

so

$$
W[u,v](x)=W[u,v](x_0)\exp\!\left[-\int_{x_0}^{x}ds\,p(s)\right].
$$

In particular, if the equation has no first-derivative term,

$$
y''+q(x)y=0,
$$

then $W[u,v]$ is constant.

More generally, for the first-order system $Y'=AY$, the determinant of a fundamental matrix satisfies

$$
\frac{d}{dx}\det\Phi(x)=\operatorname{tr}A(x)\det\Phi(x),
$$

and hence

$$
\det\Phi(x)=\det\Phi(x_0)
\exp\!\left(\int_{x_0}^{x}ds\,\operatorname{tr}A(s)\right).
$$

Wronskians are useful because they measure whether solutions are independent, normalize Green functions, and encode conserved fluxes. In scattering theory, the constancy of an appropriate Wronskian is the one-dimensional expression of current conservation.

## Boundary conditions and self-adjoint form

Many ODEs in QFT are most naturally written in self-adjoint form:

$$
L[y]= -\frac{1}{w(x)}\frac{d}{dx}\!\left(p(x)\frac{dy}{dx}\right)
+\frac{q(x)}{w(x)}y,
$$

or equivalently

$$
-(p y')'+qy=\lambda w y.
$$

Here $w(x)>0$ is a weight. This is the beginning of Sturm–Liouville theory. The natural inner product is

$$
\langle u,v\rangle_w=\int_a^b dx\,w(x)\overline{u(x)}v(x).
$$

Integrating by parts gives the boundary form

$$
\int_a^b dx\,\overline{u}\,[-(pv')'+qv]
-\int_a^b dx\,[-(p\overline{u}')'+q\overline{u}]v
=\left[p(\overline{u}v'-\overline{u}'v)\right]_{a}^{b}.
$$

Self-adjoint boundary conditions are precisely those that make this boundary form vanish on the chosen domain. Dirichlet conditions, Neumann conditions, many Robin conditions, and periodic conditions can do this, but they define different operators.

This is the ODE version of a theme that will return everywhere: self-adjointness is not a mood. It is a domain statement.

## Green kernels in one dimension

Consider the second-order operator

$$
L=-\frac{d^2}{dx^2}+V(x)
$$

on an interval $[a,b]$. A Green kernel $G(x,y)$ for a boundary-value problem satisfies

$$
L_xG(x,y)=\delta(x-y),
$$

plus the boundary conditions in the $x$ variable.

Let $u_L$ be a homogeneous solution satisfying the left boundary condition at $a$, and let $u_R$ be a homogeneous solution satisfying the right boundary condition at $b$. Assume they are linearly independent, and define

$$
W[u_L,u_R]=u_Lu_R'-u_L'u_R.
$$

For the operator $L=-d^2/dx^2+V$, this Wronskian is constant. The Green kernel is

$$
G(x,y)=
-\frac{u_L(x_<)u_R(x_>)}{W[u_L,u_R]},
\qquad
x_<=\min(x,y),\quad x_>=\max(x,y).
$$

The minus sign is not decorative. It comes from the jump condition. Integrating $L_xG(x,y)=\delta(x-y)$ across $x=y$ gives

$$
G'(y^- ,y)-G'(y^+,y)=1.
$$

If instead the differential operator begins with $+d^2/dx^2$, the sign changes. This is one of those tiny sign traps that quietly eats afternoons.

If $L$ has a zero mode satisfying both boundary conditions, the construction fails: $W[u_L,u_R]=0$. The inverse does not exist on the full space. In QFT this is the mathematical reason zero modes require special treatment in soliton quantization, instanton calculus, collective coordinates, and gauge fixing.

## Initial-value Green functions

Boundary Green kernels are not the only kernels. For an initial-value problem, the relevant kernel is often causal. For the driven oscillator

$$
\left(\frac{d^2}{dt^2}+\omega^2\right)q(t)=j(t),
$$

the retarded Green function satisfies

$$
\left(\frac{d^2}{dt^2}+\omega^2\right)G_R(t,t')=\delta(t-t'),
\qquad
G_R(t,t')=0\quad\text{for }t<t'.
$$

The solution is

$$
G_R(t,t')=\Theta(t-t')\frac{\sin\omega(t-t')}{\omega}.
$$

The advanced Green function has the opposite support. The Feynman Green function has a time-ordering prescription instead. They solve related equations but answer different questions.

This is already the entire propagator moral in miniature:

$$
\text{same differential expression} + \text{different prescription}
= \text{different Green function}.
$$

## Singular points and endpoint behavior

An ODE point is ordinary if the coefficients are regular there and the leading coefficient does not vanish. Otherwise it is singular. In field theory, singular points arise from origins in polar coordinates, horizons, defects, inverse-square potentials, turning points, and boundary degenerations.

For a second-order equation written as

$$
y''+p(x)y'+q(x)y=0,
$$

the point $x_0$ is a regular singular point if

$$
(x-x_0)p(x),
\qquad
(x-x_0)^2q(x)
$$

are analytic near $x_0$. In that case Frobenius analysis looks for solutions of the form

$$
y(x)=(x-x_0)^\alpha\sum_{n=0}^{\infty}a_n(x-x_0)^n.
$$

The leading power $\alpha$ is found from an indicial equation. This is why powers, logarithms, and special functions appear in radial equations.

A standard example is the radial part of the Laplacian. In $d$ Euclidean dimensions, separating angular variables produces equations with terms such as

$$
\frac{\ell(\ell+d-2)}{r^2}.
$$

The origin $r=0$ is singular, but the allowed physical solution is usually selected by regularity, square integrability, or finite action.

Endpoint behavior is not optional. Saying “regular at the origin” or “purely outgoing at infinity” is a boundary condition, even when it does not look like one.

## Eigenvalue problems and mode expansions

A linear ODE often contains a spectral parameter:

$$
L u_n=\lambda_n u_n.
$$

For a well-posed self-adjoint boundary-value problem on a compact interval, the eigenvalues are real and the eigenfunctions can be chosen orthogonal. In the weighted Sturm–Liouville setting,

$$
-(p u_n')'+q u_n=\lambda_n w u_n,
$$

the orthogonality relation is

$$
\int_a^b dx\,w(x)\overline{u_m(x)}u_n(x)=0
\qquad (\lambda_m\neq\lambda_n).
$$

Mode expansions then express functions as sums over eigenfunctions:

$$
f(x)=\sum_n f_n\,u_n(x),
\qquad
f_n=\int_a^b dx\,w(x)\overline{u_n(x)}f(x),
$$

after choosing a normalization.

This is the mathematical backbone of normal-mode quantization. A free field is often an infinite collection of oscillators because an elliptic spatial operator supplies a set of modes and eigenfrequencies.

In noncompact problems the spectrum may be continuous. Then sums become integrals, eigenfunctions may be delta-normalized, and the language of distributions or rigged Hilbert spaces becomes necessary. This connects directly to [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/) and [Rigged Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/rigged-hilbert-spaces/).

## Stability and fluctuation operators

Suppose $\phi_\star$ is a classical solution of an action $S[\phi]$. Expanding around it,

$$
\phi=\phi_\star+\eta,
$$

gives

$$
S[\phi_\star+\eta]=S[\phi_\star]
+\frac12\int dx\,\eta L\eta+\cdots,
$$

where $L$ is the fluctuation operator. If the background depends on one coordinate, $L$ may reduce to an ODE operator after separating the remaining variables.

The spectrum of $L$ carries physical information:

| Spectral feature | Meaning |
|---|---|
| positive eigenvalues | stable quadratic fluctuations |
| zero modes | moduli, symmetries, collective coordinates, gauge redundancies |
| negative eigenvalues | instability directions, tunneling saddles, false-vacuum decay |
| continuous spectrum | scattering states, radiation modes, infinite-volume effects |

This is why the humble equation

$$
\left[-\frac{d^2}{dx^2}+V''(\phi_\star(x))\right]\eta=\lambda\eta
$$

shows up in soliton physics, instantons, false-vacuum decay, and one-loop determinants.

## Nonlinear ODEs and phase portraits

Not every important ODE is linear. Classical mechanics, beta functions, soliton profiles, and saddle equations are often nonlinear:

$$
y'=F(y,x),
\qquad
\text{or}\qquad
\ddot q=-V'(q).
$$

Even when the nonlinear equation is hard to solve exactly, its linearization is often decisive. Near a fixed point $y_\star$ of an autonomous equation

$$
\frac{dy}{dt}=F(y),
\qquad F(y_\star)=0,
$$

write $y=y_\star+\eta$. Then

$$
\frac{d\eta}{dt}=F'(y_\star)\eta+O(\eta^2).
$$

The sign of $F'(y_\star)$ determines local attraction or repulsion in one dimension. For multiple couplings $g^i$, the RG equation

$$
\frac{dg^i}{d\log\mu}=\beta^i(g)
$$

linearizes near a fixed point $g_\star$ as

$$
\frac{d\eta^i}{d\log\mu}=B^i{}_j\eta^j+\cdots,
\qquad
B^i{}_j=\left.\frac{\partial\beta^i}{\partial g^j}\right|_{g=g_\star}.
$$

The eigenvalues of $B$ are the first approximation to relevance, irrelevance, and marginality. So RG flow is also ODE theory wearing a field-theory jacket.

## WKB and semiclassical thinking

When an ODE contains a small parameter, asymptotic methods become central. A common Schrödinger-type equation is

$$
-\epsilon^2\frac{d^2\psi}{dx^2}+V(x)\psi=E\psi,
$$

with $\epsilon$ small. The WKB ansatz

$$
\psi(x)=\exp\!\left[\frac1\epsilon S_0(x)+S_1(x)+\epsilon S_2(x)+\cdots\right]
$$

turns the differential equation into a hierarchy of algebraic and first-order differential equations. Away from turning points, the leading behavior is controlled by the classical momentum

$$
p(x)=\sqrt{E-V(x)}.
$$

The WKB approximation is not merely a trick for quantum mechanics. It is the one-dimensional prototype of saddle-point expansions, semiclassical path integrals, instanton calculus, tunneling exponents, and large-parameter asymptotics. Near turning points, ordinary WKB fails and must be matched to special-function behavior, typically Airy functions.

## How ODEs enter QFT calculations

Here are the most common appearances.

**Harmonic oscillators.** Every free mode of a linear field theory behaves like an oscillator. The oscillator Green function is the seed from which free-field propagators grow.

**Partial waves.** Scattering in central backgrounds reduces PDEs to radial ODEs labeled by angular momentum.

**Instantons and solitons.** Classical profiles are often nonlinear ODEs; one-loop fluctuations are linear spectral ODEs.

**Thermal and finite-size modes.** Compact directions produce ODE eigenvalue problems with periodic or antiperiodic boundary conditions.

**Renormalization-group flow.** Couplings follow ODEs in logarithmic scale.

**Special functions.** Bessel, Legendre, Airy, hypergeometric, and Heun equations appear when symmetry or singularity structure reduces a physical PDE to a canonical ODE.

**Determinants.** One-dimensional functional determinants can often be computed through boundary-value ODE methods such as the Gelfand–Yaglom theorem.

**Quasinormal modes and resonances.** In dissipative, black-hole, or open systems, ODE boundary conditions may be non-self-adjoint, leading to complex spectra.

## Common pitfalls

**Treating the differential expression as the operator.** The expression $-d^2/dx^2$ is not enough. The domain and boundary conditions define the operator.

**Forgetting the sign in the Green-function jump.** The jump depends on the coefficient of the highest derivative. For $L=-d^2/dx^2+V$, the derivative jump is $G'(y^-)-G'(y^+)=1$.

**Calling every solution mode normalizable.** Plane waves and scattering states are not normalizable in the Hilbert-space sense. They are usually delta-normalized distributions.

**Ignoring singular endpoints.** Regularity at an origin, ingoing behavior at a horizon, and decay at infinity are boundary conditions.

**Assuming self-adjointness from a symmetric-looking formula.** A formally symmetric expression is not necessarily self-adjoint. Boundary terms decide.

**Confusing initial-value and boundary-value Green functions.** Retarded, advanced, Euclidean, and boundary Green kernels answer different questions.

**Dividing by a Wronskian without checking zero modes.** A vanishing Wronskian in the Green-function construction signals an obstruction to inversion.

**Using WKB across a turning point without matching.** Standard WKB formulas fail where $p(x)=0$.

## Exercises

### Exercise 1: Abel's identity

Let $u$ and $v$ solve

$$
y''+p(x)y'+q(x)y=0.
$$

Show that their Wronskian satisfies

$$
W'[u,v]=-pW[u,v].
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
W=uv'-u'v.
$$

Differentiate:

$$
W'=u'v'+uv''-u''v-u'v'=uv''-u''v.
$$

The equation gives

$$
u''=-pu'-qu,
\qquad
v''=-pv'-qv.
$$

Therefore

$$
W'=u(-pv'-qv)-(-pu'-qu)v
=-puv'+pu'v
=-p(uv'-u'v)
=-pW.
$$

</details>

### Exercise 2: Retarded oscillator kernel

Verify that

$$
G_R(t,t')=\Theta(t-t')\frac{\sin\omega(t-t')}{\omega}
$$

satisfies

$$
\left(\frac{d^2}{dt^2}+\omega^2\right)G_R(t,t')=\delta(t-t')
$$

as a distribution.

<details><summary><strong>Solution</strong></summary>

For $t\neq t'$, the function is either zero or a homogeneous solution, so the left side vanishes. The only possible contribution comes from $t=t'$. Integrate the equation across a small interval $[t'-\varepsilon,t'+\varepsilon]$:

$$
\int_{t'-\varepsilon}^{t'+\varepsilon}dt\,
\left(\frac{d^2}{dt^2}+\omega^2\right)G_R
=G_R'(t'^+,t')-G_R'(t'^-,t')+O(\varepsilon).
$$

Since $G_R=0$ for $t<t'$, $G_R'(t'^-,t')=0$. For $t>t'$,

$$
G_R'(t,t')=\cos\omega(t-t'),
$$

so $G_R'(t'^+,t')=1$. The integral tends to $1$, which is the defining jump condition for a delta function.

</details>

### Exercise 3: Green kernel from two endpoint solutions

Let

$$
L=-\frac{d^2}{dx^2}+V(x)
$$

on $[a,b]$. Suppose $u_L$ satisfies the left boundary condition and $u_R$ satisfies the right boundary condition. Show that

$$
G(x,y)=-\frac{u_L(x_<)u_R(x_>)}{W[u_L,u_R]}
$$

has the correct derivative jump at $x=y$.

<details><summary><strong>Solution</strong></summary>

The kernel is continuous at $x=y$ because both one-sided values equal

$$
-\frac{u_L(y)u_R(y)}{W[u_L,u_R]}.
$$

For $x<y$,

$$
\partial_xG(x,y)=-\frac{u_L'(x)u_R(y)}{W},
$$

so

$$
G'(y^-,y)=-\frac{u_L'(y)u_R(y)}{W}.
$$

For $x>y$,

$$
\partial_xG(x,y)=-\frac{u_L(y)u_R'(x)}{W},
$$

so

$$
G'(y^+,y)=-\frac{u_L(y)u_R'(y)}{W}.
$$

Therefore

$$
G'(y^-)-G'(y^+)
=\frac{u_L(y)u_R'(y)-u_L'(y)u_R(y)}{W}
=1.
$$

This is the required jump for $L=-d^2/dx^2+V$.

</details>

### Exercise 4: Linearized RG flow

Let a single coupling obey

$$
\frac{dg}{d\log\mu}=\beta(g),
$$

and suppose $\beta(g_\star)=0$. Set $g=g_\star+\eta$. Show that, to first order,

$$
\eta(\mu)=\eta(\mu_0)\left(\frac{\mu}{\mu_0}\right)^{\beta'(g_\star)}.
$$

<details><summary><strong>Solution</strong></summary>

Expanding the beta function gives

$$
\beta(g_\star+\eta)=\beta(g_\star)+\beta'(g_\star)\eta+O(\eta^2)
=\beta'(g_\star)\eta+O(\eta^2).
$$

To linear order,

$$
\frac{d\eta}{d\log\mu}=\beta'(g_\star)\eta.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
\log\frac{\eta(\mu)}{\eta(\mu_0)}
=\beta'(g_\star)\log\frac{\mu}{\mu_0},
$$

hence

$$
\eta(\mu)=\eta(\mu_0)\left(\frac{\mu}{\mu_0}\right)^{\beta'(g_\star)}.
$$

</details>

## References

For ODE theory and boundary-value problems, see Coddington and Levinson, *Theory of Ordinary Differential Equations*; Hartman, *Ordinary Differential Equations*; Teschl, *Ordinary Differential Equations and Dynamical Systems*; and Olver, *Asymptotics and Special Functions*. For asymptotic and WKB methods, see Bender and Orszag, *Advanced Mathematical Methods for Scientists and Engineers*. For mathematical-physics examples, see Courant and Hilbert, *Methods of Mathematical Physics*; Reed and Simon, *Methods of Modern Mathematical Physics*; and standard QFT texts such as Srednicki, Zee, Weinberg, Coleman, Schwartz, Zinn-Justin, and Marino.

## Version history

- 2026-06-25: Initial polished draft.
