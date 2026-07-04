---
title: "Finite-Difference Methods"
description: "A QFT-oriented guide to finite-difference discretizations, lattice derivatives, modified momenta, boundary conditions, stability, convergence, and gauge-covariant differences."
sidebar:
  label: "Finite-Difference Methods"
  order: 1
level: Graduate
status: "Polished draft"
source: "Finite-difference numerical analysis, lattice field theory, PDE discretization, stability theory, and QFT applications to propagators, spectra, and gauge-covariant lattice derivatives."
topics:
  - finite differences
  - lattice derivatives
  - discretization error
  - stability
  - boundary conditions
  - lattice Laplacian
  - gauge-covariant differences
canonicalTopics:
  - finite-difference-methods
  - lattice-derivatives
  - finite-difference-laplacian
  - modified-momentum
  - numerical-stability
researchStatus:
  established:
    - "Finite-difference formulas, truncation error, von Neumann stability analysis, sparse discretized operators, and continuum extrapolation are standard parts of numerical analysis and computational field theory."
  active:
    - "High-precision lattice calculations, structure-preserving discretizations, gauge-covariant finite differences, real-time stability, adaptive discretizations, and improved lattice actions remain active computational-QFT topics."
---

## Summary

Finite-difference methods replace derivatives by differences between nearby grid values. On a one-dimensional uniform grid

$$
x_i=x_0+ia,
\qquad
f_i=f(x_i),
$$

the simplest centered derivative is

$$
\partial_x f(x_i)
\approx
\frac{f_{i+1}-f_{i-1}}{2a}.
$$

This innocent-looking replacement is one of the main entrances from continuum field theory to lattice field theory. It turns differential operators into matrices, Green functions into matrix inverses, spectra into finite-dimensional eigenvalue problems, and continuum limits into extrapolations in the grid spacing $a$.

The key lesson is that a finite difference is not merely an approximate derivative. It is a **new operator** with its own spectrum, symmetries, boundary conditions, and ultraviolet behavior. In momentum space, the centered derivative replaces

$$
ik
\quad\longrightarrow\quad
\frac{i\sin(ka)}{a}.
$$

That replacement is harmless at small $ka$, but it deeply changes high-momentum physics. Numerical QFT begins when you stop pretending that the grid is invisible.

## Prerequisites

You should know Taylor expansions, Fourier transforms, basic linear algebra, and the difference between an initial-value problem and a boundary-value problem. Familiarity with Green functions and lattice regularization is helpful but not required.

The page uses the convention that $a$ denotes the grid spacing. It is unrelated to an index label unless the context makes that explicit.

## Core idea

A finite-difference method chooses three pieces of data:

1. a set of grid points,
2. a local stencil that approximates derivatives,
3. boundary or periodicity conditions that close the system.

The result is a finite-dimensional approximation to a continuum operator. For example, the differential operator

$$
L=-\frac{d^2}{dx^2}+m^2
$$

on a grid becomes a matrix

$$
(L_a f)_i
=-\frac{f_{i+1}-2f_i+f_{i-1}}{a^2}+m^2f_i.
$$

Solving

$$
LG=\delta
$$

becomes solving

$$
L_aG_a=I.
$$

Taking $a\to0$ is not optional fine print. It is how the continuum operator is recovered.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A finite-difference stencil and its Fourier-space modified momentum.](/figures/math-toolkit/finite-difference-stencil-dispersion.svg)

<figcaption>

A local stencil defines both a real-space operator and a Fourier-space symbol. The centered derivative has symbol $i\sin(ka)/a$, while the nearest-neighbor Laplacian has symbol $4\sin^2(ka/2)/a^2$ for $-\Delta_a$. The continuum limit is the small-$ka$ region.

</figcaption>
</figure>

## Uniform grids

On an interval $[0,L]$, a uniform grid has points

$$
x_i=ia,
\qquad
 i=0,1,\ldots,N,
\qquad
 a=\frac{L}{N}.
$$

For a periodic domain, one usually identifies

$$
f_{i+N}=f_i,
$$

and uses $N$ points with spacing $a=L/N$. For a nonperiodic interval, boundary values or boundary equations must be specified separately.

In $d$ dimensions with a hypercubic lattice,

$$
x_{\mathbf n}=a\mathbf n,
\qquad
\mathbf n=(n_1,\ldots,n_d)\in\mathbb Z^d.
$$

The unit vector in direction $\mu$ is denoted $\hat\mu$. A lattice scalar field is a list of values

$$
\phi_{\mathbf n}\approx \phi(a\mathbf n).
$$

A lattice gauge field is not naturally a list of vector potentials at sites. The gauge-covariant object lives on links, a point we return to below.

## Forward, backward, and centered differences

The forward difference is

$$
(D_+f)_i=\frac{f_{i+1}-f_i}{a}.
$$

The backward difference is

$$
(D_-f)_i=\frac{f_i-f_{i-1}}{a}.
$$

The centered difference is

$$
(D_0f)_i=\frac{f_{i+1}-f_{i-1}}{2a}.
$$

Taylor expansion gives

$$
D_+f(x_i)=f'(x_i)+\frac a2f''(x_i)+O(a^2),
$$

$$
D_-f(x_i)=f'(x_i)-\frac a2f''(x_i)+O(a^2),
$$

and

$$
D_0f(x_i)=f'(x_i)+\frac{a^2}{6}f'''(x_i)+O(a^4).
$$

Thus $D_+$ and $D_-$ are first-order accurate, while $D_0$ is second-order accurate.

This does not mean centered differences are always better. Upwind differences are often used for advection-like problems because stability and monotonicity can matter more than formal order.

## The second derivative and lattice Laplacian

The standard second derivative is

$$
(D_+D_-f)_i
=\frac{f_{i+1}-2f_i+f_{i-1}}{a^2}.
$$

Taylor expansion gives

$$
\frac{f_{i+1}-2f_i+f_{i-1}}{a^2}
=f''(x_i)+\frac{a^2}{12}f^{(4)}(x_i)+O(a^4).
$$

In $d$ dimensions, the nearest-neighbor lattice Laplacian is

$$
(\Delta_a f)_{\mathbf n}
=\frac{1}{a^2}\sum_{\mu=1}^d
\left(f_{\mathbf n+\hat\mu}-2f_{\mathbf n}+f_{\mathbf n-\hat\mu}\right).
$$

The corresponding positive operator $-\Delta_a$ is central in Euclidean lattice field theory. A free scalar quadratic action is commonly discretized as

$$
S_a[\phi]
=\frac{a^d}{2}\sum_{\mathbf n}
\left[
\sum_\mu \left(\frac{\phi_{\mathbf n+\hat\mu}-\phi_{\mathbf n}}{a}\right)^2
+m^2\phi_{\mathbf n}^2
\right].
$$

After summation by parts on a periodic lattice, this is

$$
S_a[\phi]
=\frac{a^d}{2}\sum_{\mathbf n}
\phi_{\mathbf n}(-\Delta_a+m^2)\phi_{\mathbf n}.
$$

This formula is the finite-difference ancestor of the free Euclidean path integral.

## Difference operators as matrices

For interior points of a one-dimensional grid, the negative second derivative becomes the tridiagonal matrix

$$
-\frac{d^2}{dx^2}
\quad\leadsto\quad
\frac{1}{a^2}
\begin{pmatrix}
2&-1&0&\cdots&0\\
-1&2&-1&\cdots&0\\
0&-1&2&\cdots&0\\
\vdots&\vdots&\vdots&\ddots&-1\\
0&0&0&-1&2
\end{pmatrix},
$$

for Dirichlet boundary conditions on the omitted endpoints. Other boundary conditions change the first and last rows.

This matrix viewpoint is usually the cleanest way to think about numerical Green functions. If

$$
L_a=-\Delta_a+m^2,
$$

then the lattice Green matrix is

$$
G_a=L_a^{-1}.
$$

A local operator gives a sparse matrix. Sparse structure is the reason finite differences scale to large lattices.

## Fourier symbols and modified momenta

On an infinite or periodic uniform grid, discrete plane waves are eigenvectors:

$$
f_i=e^{ikx_i}=e^{ikai}.
$$

The centered derivative acts as

$$
D_0e^{ikx_i}
=\frac{e^{ika}-e^{-ika}}{2a}e^{ikx_i}
=\frac{i\sin(ka)}{a}e^{ikx_i}.
$$

Thus the continuum momentum $k$ is replaced by the modified momentum

$$
\widehat k_1(k)=\frac{\sin(ka)}{a}.
$$

Similarly,

$$
-\Delta_a e^{ikx_i}
=\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right)e^{ikx_i}.
$$

In $d$ dimensions,

$$
\widehat k^2
=\frac{4}{a^2}\sum_{\mu=1}^d\sin^2\!\left(\frac{k_\mu a}{2}\right).
$$

The lattice free scalar propagator is therefore

$$
G_a(k)=\frac{1}{\widehat k^2+m^2}
$$

in Euclidean signature, with the appropriate finite-volume momentum set.

At small $ka$,

$$
\widehat k^2=k^2+O(a^2k^4).
$$

At large $ka$, the difference is not small. The finite grid has a Brillouin zone,

$$
-\frac{\pi}{a}<k_\mu\le \frac{\pi}{a},
$$

and momenta outside it are aliased back inside.

## Numerical dispersion

Consider the wave equation

$$
\partial_t^2u=\partial_x^2u.
$$

If only space is discretized with the nearest-neighbor Laplacian, a plane wave has frequency

$$
\omega^2(k)=\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right).
$$

The continuum dispersion $\omega^2=k^2$ is recovered only at small $ka$. The group velocity is

$$
\frac{d\omega}{dk}=\cos\!\left(\frac{ka}{2}\right)
$$

for positive $k$ in the first Brillouin zone. High-frequency waves propagate incorrectly. This is not a bug in an implementation; it is the dispersion relation of the discretized theory.

In lattice QFT, modified dispersion is often acceptable because the lattice is a regulator. The correct question is whether low-energy observables converge after the continuum extrapolation.

## Higher-order stencils

Higher-order stencils cancel more Taylor terms. A fourth-order centered derivative is

$$
f'(x_i)
\approx
\frac{-f_{i+2}+8f_{i+1}-8f_{i-1}+f_{i-2}}{12a}.
$$

A fourth-order second derivative is

$$
f''(x_i)
\approx
\frac{-f_{i+2}+16f_{i+1}-30f_i+16f_{i-1}-f_{i-2}}{12a^2}.
$$

These reduce truncation error for smooth functions. They also enlarge the stencil, complicate boundaries, and can alter sparsity and locality. Improved lattice actions use this idea systematically: add carefully chosen local terms so that leading lattice artifacts cancel.

## Boundary conditions

Boundary conditions are part of the operator. They determine the domain, zero modes, spectra, Green functions, and finite-volume artifacts.

Common choices are:

| Boundary condition | Continuum form | Finite-difference implementation |
|---|---|---|
| Dirichlet | $f(0)=f(L)=0$ | fix endpoint values or remove them from unknowns |
| Neumann | $f'(0)=f'(L)=0$ | one-sided derivatives, ghost points, or modified rows |
| Robin | $af+bf'=0$ | boundary equation mixing value and derivative |
| Periodic | $f(0)=f(L)$ | identify $f_{i+N}=f_i$ |
| Antiperiodic | $f(x+L)=-f(x)$ | identify $f_{i+N}=-f_i$ |

For QFT, periodic boundary conditions are common for bosons in spatial directions, antiperiodic boundary conditions appear for fermions in thermal Euclidean time, and Dirichlet or Neumann conditions appear in boundary field theories, defects, cavities, and numerical boundary-value problems.

A common mistake is to use an interior stencil at the boundary without changing the domain. That silently imposes a boundary condition, often not the one intended.

## Summation by parts

Finite differences have discrete analogs of integration by parts. On a periodic grid,

$$
a\sum_i f_i(D_+g)_i
=-a\sum_i (D_-f)_i g_i.
$$

This identity is called summation by parts. It implies that $D_+$ and $-D_-$ are adjoints of each other with respect to the lattice inner product

$$
\langle f,g\rangle_a=a\sum_i f_i^*g_i.
$$

Similarly, the lattice Laplacian satisfies

$$
-a\sum_i f_i(\Delta_a g)_i
=a\sum_i (D_+f)_i(D_+g)_i
$$

for periodic real fields. This positivity is the discrete version of

$$
\int dx\,f(-\partial_x^2)f=\int dx\,(\partial_xf)^2.
$$

Structure-preserving discretizations are built around identities like this. They keep self-adjointness, positivity, conservation laws, or gauge covariance exact at finite $a$.

## Initial-value stability

For time-dependent equations, discretization must be stable. Consider the heat equation

$$
\partial_tu=\partial_x^2u.
$$

The explicit finite-difference scheme

$$
u_i^{n+1}=u_i^n+r\left(u_{i+1}^n-2u_i^n+u_{i-1}^n\right),
\qquad
r=\frac{\Delta t}{a^2},
$$

is accurate but stable only for

$$
r\le \frac12
$$

in one spatial dimension.

A quick von Neumann analysis shows why. Insert the Fourier mode

$$
u_i^n=\lambda^n e^{ikai}.
$$

Then

$$
\lambda(k)=1-4r\sin^2\!\left(\frac{ka}{2}\right).
$$

Stability requires $|\lambda(k)|\le1$ for all $k$, giving $r\le1/2$.

The moral is brutal but useful: an algorithm can approximate the equation correctly for one step and still explode after many steps.

## Elliptic problems and sparse solves

For elliptic equations such as

$$
(-\Delta+m^2)u=f,
$$

finite differences produce sparse linear systems

$$
A u=b.
$$

In one dimension, $A$ is tridiagonal. In higher dimensions, it is sparse with a local stencil pattern. Direct dense inversion is almost never the right mental model. Instead one uses sparse direct solvers, conjugate-gradient methods for positive definite systems, Krylov methods, preconditioners, multigrid, or domain-decomposition methods.

The condition number matters. For the massless one-dimensional Dirichlet Laplacian, the smallest eigenvalue scales like $L^{-2}$ while the largest scales like $a^{-2}$, so the condition number grows like

$$
\kappa(A)\sim \frac{L^2}{a^2}.
$$

As the grid is refined, the linear solve can become harder even though the discretization is more accurate.

## Continuum extrapolation

Suppose an observable $Q(a)$ has a second-order discretization error:

$$
Q(a)=Q_0+c_2a^2+c_4a^4+\cdots.
$$

Then $Q_0$ is the continuum value. A calculation at one lattice spacing cannot determine it. One must compute at several $a$ values and extrapolate.

If the leading $a^2$ behavior is reliable, Richardson extrapolation gives

$$
Q_0\approx \frac{4Q(a/2)-Q(a)}{3}.
$$

This formula is only as good as its assumptions. If the leading error is not really $a^2$, or if finite-volume and statistical errors are comparable, the extrapolation may lie beautifully.

A credible convergence study varies all relevant regulators:

```txt
lattice spacing a
volume L
basis or field cutoff
solver tolerance
Monte Carlo statistics
```

One regulator at a time is a good habit; all regulators at once is a fog machine.

## Gauge-covariant finite differences

For a scalar field charged under a gauge field, the continuum covariant derivative is

$$
D_\mu\phi=(\partial_\mu+iA_\mu)\phi
$$

for a simple Abelian convention. On a lattice, the gauge field is naturally represented by a link variable

$$
U_{\mathbf n,\mu}\approx
\exp\!\left(i a A_\mu(x_{\mathbf n}+a\hat\mu/2)\right).
$$

A forward gauge-covariant difference is

$$
(D_\mu^+\phi)_{\mathbf n}
=\frac{U_{\mathbf n,\mu}\phi_{\mathbf n+\hat\mu}-\phi_{\mathbf n}}{a}.
$$

Under a lattice gauge transformation

$$
\phi_{\mathbf n}\mapsto g_{\mathbf n}\phi_{\mathbf n},
$$

the link transforms as

$$
U_{\mathbf n,\mu}
\mapsto
 g_{\mathbf n}U_{\mathbf n,\mu}g_{\mathbf n+\hat\mu}^{-1}.
$$

Then

$$
(D_\mu^+\phi)_{\mathbf n}
\mapsto
 g_{\mathbf n}(D_\mu^+\phi)_{\mathbf n}.
$$

This is the reason lattice gauge theory puts gauge fields on links. It makes exact gauge covariance possible at nonzero lattice spacing.

## Fermion doubling preview

Finite differences for first-order operators have an infamous surprise. The centered derivative has symbol

$$
\frac{i\sin(ka)}{a}.
$$

This vanishes not only at $k=0$ but also at the edge of the Brillouin zone, $k=\pi/a$. For a naive lattice Dirac operator, these extra zeros become extra light fermion species called doublers.

This is not a small numerical error. It is a structural consequence of locality, chiral symmetry, and lattice momentum periodicity. Wilson fermions, staggered fermions, domain-wall fermions, and overlap fermions are different ways to navigate this obstruction.

This page does not develop lattice fermions, but the finite-difference origin of the problem is worth seeing early.

## When finite differences are the right tool

Finite differences are often a good first choice when:

| Situation | Why finite differences help |
|---|---|
| the geometry is simple | grids are easy to build |
| the operator is local | matrices are sparse |
| boundary conditions are standard | stencils can be modified cleanly |
| one needs a transparent regulator | $a$ has a direct physical meaning |
| one studies lattice field theory | locality and finite spacing are part of the setup |
| one needs robust low-order accuracy | simple methods are easy to test |

They are less ideal when the domain has complicated geometry, the solution is extremely smooth and high precision is needed, the boundary is curved, or global constraints are more naturally represented in another basis. Then finite elements or spectral methods may be better.

## Common pitfalls

### Confusing order with accuracy

A fourth-order stencil can be less accurate than a second-order stencil on a nonsmooth function, near a badly treated boundary, or in an unstable evolution. Formal order describes the asymptotic truncation error under assumptions.

### Forgetting boundary rows

Interior stencils do not define a boundary-value problem. The first and last rows of the matrix are where boundary conditions, self-adjointness, and zero modes often live.

### Treating the lattice derivative as $ik$

The centered derivative has symbol $i\sin(ka)/a$, not $ik$. The nearest-neighbor Laplacian has symbol $4\sin^2(ka/2)/a^2$, not $k^2$. At high momentum, the difference is the physics of the regulator.

### Reporting one lattice spacing

A single value of $a$ gives a result for the lattice theory at that spacing. It is not a continuum result unless the observable is protected or the continuum extrapolation is otherwise controlled.

### Ignoring zero modes

Periodic massless Laplacians have constant zero modes. Gauge theories have redundant directions. Solving $Lu=f$ without treating zero modes can produce singular matrices or meaningless inverses.

### Discretizing gauge fields as ordinary vectors

Gauge covariance is preserved by link variables, not by naively finite-differencing vector potentials at sites. The link is the lattice version of parallel transport.

## Exercises

### Exercise 1: centered derivative error

Show that

$$
\frac{f_{i+1}-f_{i-1}}{2a}
=f'(x_i)+\frac{a^2}{6}f'''(x_i)+O(a^4)
$$

for smooth $f$.

<details><summary><strong>Solution</strong></summary>

Taylor expand around $x_i$:

$$
f(x_i+a)=f+a f'+\frac{a^2}{2}f''+\frac{a^3}{6}f'''+\frac{a^4}{24}f^{(4)}+\frac{a^5}{120}f^{(5)}+O(a^6),
$$

and

$$
f(x_i-a)=f-a f'+\frac{a^2}{2}f''-\frac{a^3}{6}f'''+\frac{a^4}{24}f^{(4)}-\frac{a^5}{120}f^{(5)}+O(a^6).
$$

Subtracting cancels even powers:

$$
f(x_i+a)-f(x_i-a)=2a f'+\frac{a^3}{3}f'''+O(a^5).
$$

Divide by $2a$ to obtain

$$
\frac{f_{i+1}-f_{i-1}}{2a}
=f'(x_i)+\frac{a^2}{6}f'''(x_i)+O(a^4).
$$

</details>

### Exercise 2: symbol of the lattice Laplacian

For $f_i=e^{ikai}$, show that

$$
-\frac{f_{i+1}-2f_i+f_{i-1}}{a^2}
=\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right)f_i.
$$

<details><summary><strong>Solution</strong></summary>

Since

$$
f_{i+1}=e^{ika}f_i,
\qquad
f_{i-1}=e^{-ika}f_i,
$$

we have

$$
-\frac{f_{i+1}-2f_i+f_{i-1}}{a^2}
=-\frac{e^{ika}-2+e^{-ika}}{a^2}f_i.
$$

Using $e^{ika}+e^{-ika}=2\cos(ka)$,

$$
-\frac{2\cos(ka)-2}{a^2}f_i
=\frac{2-2\cos(ka)}{a^2}f_i.
$$

Finally,

$$
1-\cos(ka)=2\sin^2\!\left(\frac{ka}{2}\right),
$$

so

$$
\frac{2-2\cos(ka)}{a^2}
=\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right).
$$

</details>

### Exercise 3: discrete summation by parts

On a periodic grid, prove

$$
a\sum_i f_i(D_+g)_i
=-a\sum_i (D_-f)_i g_i.
$$

<details><summary><strong>Solution</strong></summary>

Start from the left-hand side:

$$
a\sum_i f_i(D_+g)_i
=\sum_i f_i(g_{i+1}-g_i).
$$

Shift the index in the first term using periodicity:

$$
\sum_i f_i g_{i+1}
=\sum_i f_{i-1}g_i.
$$

Therefore

$$
\sum_i f_i(g_{i+1}-g_i)
=\sum_i(f_{i-1}-f_i)g_i
=-\sum_i(f_i-f_{i-1})g_i.
$$

Since

$$
(D_-f)_i=\frac{f_i-f_{i-1}}{a},
$$

we get

$$
a\sum_i f_i(D_+g)_i
=-a\sum_i(D_-f)_i g_i.
$$

</details>

### Exercise 4: stability of the explicit heat scheme

For

$$
u_i^{n+1}=u_i^n+r(u_{i+1}^n-2u_i^n+u_{i-1}^n),
$$

insert $u_i^n=\lambda^n e^{ikai}$ and derive the stability condition $r\le1/2$.

<details><summary><strong>Solution</strong></summary>

Substitution gives

$$
\lambda e^{ikai}
=e^{ikai}+r(e^{ika}e^{ikai}-2e^{ikai}+e^{-ika}e^{ikai}).
$$

Cancel $e^{ikai}$:

$$
\lambda=1+r(e^{ika}-2+e^{-ika})
=1+2r(\cos(ka)-1).
$$

Using $1-\cos(ka)=2\sin^2(ka/2)$,

$$
\lambda=1-4r\sin^2\!\left(\frac{ka}{2}\right).
$$

Stability requires $|\lambda|\le1$ for all $k$. The smallest possible value occurs when $\sin^2(ka/2)=1$, giving

$$
\lambda_{\min}=1-4r.
$$

The condition $\lambda_{\min}\ge -1$ gives

$$
1-4r\ge -1,
$$

so

$$
r\le\frac12.
$$

</details>

### Exercise 5: continuum limit of the lattice propagator

For the Euclidean lattice propagator

$$
G_a(k)=\frac{1}{m^2+\frac{4}{a^2}\sin^2(ka/2)},
$$

show that $G_a(k)=1/(m^2+k^2+O(a^2k^4))$ at fixed $k$ as $a\to0$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\sin\!\left(\frac{ka}{2}\right)
=\frac{ka}{2}-\frac{(ka)^3}{48}+O(a^5k^5).
$$

Then

$$
\frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right)
=\frac{4}{a^2}\left[\frac{k^2a^2}{4}+O(a^4k^4)\right]
=k^2+O(a^2k^4).
$$

Therefore

$$
G_a(k)=\frac{1}{m^2+k^2+O(a^2k^4)}.
$$

At fixed physical momentum $k$, the lattice propagator approaches the continuum propagator. This statement is not uniform over the entire Brillouin zone as $a\to0$.

</details>

## References

- LeVeque, *Finite Difference Methods for Ordinary and Partial Differential Equations*.
- Strikwerda, *Finite Difference Schemes and Partial Differential Equations*.
- Trefethen, *Finite Difference and Spectral Methods for Ordinary and Partial Differential Equations*.
- Saad, *Iterative Methods for Sparse Linear Systems*.
- Gattringer and Lang, *Quantum Chromodynamics on the Lattice*.
- DeGrand and DeTar, *Lattice Methods for Quantum Chromodynamics*.
- Rothe, *Lattice Gauge Theories: An Introduction*.
- Montvay and Münster, *Quantum Fields on a Lattice*.

## Version history

- **2026-06-27:** First polished draft. Introduces finite-difference stencils, lattice Laplacians, Fourier symbols, numerical dispersion, boundary conditions, stability, sparse solves, continuum extrapolation, gauge-covariant differences, fermion doubling preview, and worked exercises.
