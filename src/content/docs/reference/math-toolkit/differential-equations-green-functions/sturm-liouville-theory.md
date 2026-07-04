---
title: "Sturm–Liouville Theory"
description: "Explains Sturm–Liouville operators, weighted inner products, self-adjoint boundary conditions, orthogonal eigenfunction expansions, Green kernels, zero modes, and QFT mode decompositions."
sidebar:
  label: "Sturm–Liouville Theory"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard references on Sturm–Liouville theory, ODEs, spectral theory, and mathematical physics, including Courant–Hilbert, Teschl, Coddington–Levinson, Zettl, Reed–Simon, Evans, Folland, and QFT treatments of normal modes, Green functions, partial waves, determinants, and heat kernels."
topics:
  - Sturm–Liouville theory
  - spectral problems
  - weighted Hilbert spaces
  - orthogonal eigenfunctions
  - self-adjoint boundary conditions
  - Green functions
  - Rayleigh quotient
  - zero modes
  - normal modes
  - singular endpoints
  - partial waves
canonicalTopics:
  - sturm-liouville-theory
  - spectral-problem
  - weighted-hilbert-space
  - orthogonal-eigenfunction
  - self-adjoint-boundary-condition
  - green-function
  - rayleigh-quotient
  - zero-mode
  - normal-mode
  - singular-endpoint
  - partial-wave
researchStatus:
  established:
    - "Regular Sturm–Liouville problems on compact intervals give self-adjoint operators in weighted Hilbert spaces with real spectra, orthogonal eigenfunctions, variational characterizations, and spectral Green-function expansions."
  active:
    - "Singular endpoints, non-self-adjoint boundary conditions, indefinite weights, distributional coefficients, operator pencils, and resonant or non-Hermitian generalizations remain active in mathematical physics and applications."
---

## Summary

Sturm–Liouville theory is the spectral theory of one-dimensional second-order self-adjoint differential operators. Its canonical form is

$$
-(p(x)y'(x))'+q(x)y(x)=\lambda w(x)y(x),
$$

on an interval, together with boundary conditions. Here $p$, $q$, and $w$ are real functions, usually with

$$
p(x)>0,
\qquad
w(x)>0,
$$

on the interval. The function $w$ is the weight. It is not decoration: it tells you which inner product makes the eigenfunctions orthogonal.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Flow diagram showing Sturm–Liouville data becoming a self-adjoint operator, eigenmodes, orthogonal expansions, Green kernels, heat kernels, determinants, and zero modes.](/figures/math-toolkit/sturm-liouville-spectral-flow.svg)

<figcaption>

A Sturm–Liouville problem is a local second-order expression plus a weight plus boundary data. Together they define a self-adjoint operator in a weighted Hilbert space. The payoff is a controlled mode expansion, a spectral Green kernel, and a clean way to discuss determinants and zero modes.

</figcaption>
</figure>

In QFT this theory is everywhere, often wearing a fake mustache. It appears in normal-mode expansions in finite volume, Kaluza–Klein spectra, radial partial waves, fluctuation operators around solitons and instantons, Casimir problems, heat-kernel traces, and functional determinants. Whenever a field is separated as

$$
\phi(t,x)=\sum_n q_n(t)u_n(x),
$$

the functions $u_n$ are usually eigenfunctions of some Sturm–Liouville or Sturm–Liouville-like problem.

The most important slogan is:

$$
\text{Orthogonality comes from self-adjointness, and self-adjointness includes the boundary conditions.}
$$

## Prerequisites

You should know [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), and [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/).

This page treats regular problems first. Singular endpoints, continuous spectrum, and radial equations are introduced later as extensions, not swept under the rug. A little rug-sweeping is fine in life; not in spectral theory.

## The regular Sturm–Liouville problem

Let $I=[a,b]$ be a compact interval. A regular Sturm–Liouville problem has the form

$$
-(p y')'+q y=\lambda w y,
$$

where $p$, $p'$, $q$, and $w$ are sufficiently nice, $p>0$, and $w>0$ on $[a,b]$. The differential expression is

$$
\tau y=\frac{1}{w}\left[-(p y')'+q y\right].
$$

The natural Hilbert space is not always ordinary $L^2([a,b],dx)$. It is

$$
L^2_w([a,b])=L^2([a,b],w(x)dx),
$$

with inner product

$$
\langle f,g\rangle_w
=\int_a^b dx\,w(x)\overline{f(x)}g(x).
$$

Then the eigenvalue equation can be written as

$$
\tau y=\lambda y.
$$

Equivalently, it can be written in unweighted form as

$$
Ly=\lambda w y,
\qquad
L=-(p\partial_x)' +q.
$$

Both forms are useful. The weighted form emphasizes the Hilbert space. The unweighted form emphasizes the differential equation.

### Why the weight appears

Suppose $u_m$ and $u_n$ satisfy

$$
Lu_n=\lambda_n w u_n,
\qquad
Lu_m=\lambda_m w u_m.
$$

If the boundary conditions make $L$ symmetric, then

$$
\int_a^b dx\,\overline{u_m}Lu_n
=
\int_a^b dx\,\overline{Lu_m}u_n.
$$

Substituting the eigenvalue equations gives

$$
\lambda_n\int_a^b dx\,w\overline{u_m}u_n
=
\lambda_m\int_a^b dx\,w\overline{u_m}u_n.
$$

Thus

$$
(\lambda_n-\lambda_m)\langle u_m,u_n\rangle_w=0.
$$

If $\lambda_m\ne\lambda_n$, then

$$
\langle u_m,u_n\rangle_w=0.
$$

That is the entire reason Legendre polynomials, Bessel modes, spherical harmonics after separation, and many other special-function families come with nontrivial weights. The orthogonality measure is determined by the self-adjoint form of the equation.

## The boundary form

The heart of Sturm–Liouville theory is one integration by parts. For smooth $f$ and $g$,

$$
\int_a^b dx\,\overline f Lg
-
\int_a^b dx\,\overline{Lf}g
=
\left[p\left(\overline{f'}g-\overline f g'\right)\right]_a^b.
$$

The right-hand side is the boundary form. Self-adjoint boundary conditions are exactly those that make this form vanish for all allowed $f$ and $g$ in the domain.

For example, separated real boundary conditions have the form

$$
\alpha_a y(a)+\beta_a p(a)y'(a)=0,
$$

and

$$
\alpha_b y(b)+\beta_b p(b)y'(b)=0,
$$

with real coefficients and not both coefficients zero at each endpoint. Special cases include:

| Name | Boundary condition at an endpoint | Interpretation |
|---|---|---|
| Dirichlet | $y=0$ | fixed value |
| Neumann | $p y'=0$ | fixed flux |
| Robin | $\alpha y+\beta p y'=0$ | mixed value–flux condition |
| periodic | $y(a)=y(b)$ and $p(a)y'(a)=p(b)y'(b)$ | circle or compact direction |

These conditions do more than make the ODE solvable. They define the operator.

## Example: the interval Laplacian

The simplest example is

$$
-y''=\lambda y,
\qquad
0<x<L.
$$

Here

$$
p=1,
\qquad
q=0,
\qquad
w=1.
$$

With Dirichlet boundary conditions

$$
y(0)=y(L)=0,
$$

the normalized eigenfunctions are

$$
u_n(x)=\sqrt{\frac{2}{L}}\sin\frac{n\pi x}{L},
\qquad
\lambda_n=\left(\frac{n\pi}{L}\right)^2,
\qquad
n=1,2,3,\ldots.
$$

With Neumann boundary conditions

$$
y'(0)=y'(L)=0,
$$

the normalized eigenfunctions are

$$
u_0(x)=\frac{1}{\sqrt L},
\qquad
u_n(x)=\sqrt{\frac{2}{L}}\cos\frac{n\pi x}{L},
\qquad
n\ge 1,
$$

with

$$
\lambda_n=\left(\frac{n\pi}{L}\right)^2,
\qquad
n=0,1,2,\ldots.
$$

The Neumann problem has a zero mode. This is not a harmless extra line in a table. The inverse of $-d^2/dx^2$ with Neumann boundary conditions does not exist on all of $L^2([0,L])$, because constants are killed by the operator. If

$$
-u''=f,
\qquad
u'(0)=u'(L)=0,
$$

then integration over the interval gives

$$
0=-u'(L)+u'(0)=\int_0^L dx\,f(x).
$$

So the source must be orthogonal to the zero mode:

$$
\int_0^L dx\,f(x)=0.
$$

This is the one-dimensional baby version of a constraint equation, a gauge zero mode, or a collective coordinate.

## Reality, discreteness, and ordering of eigenvalues

For a regular self-adjoint Sturm–Liouville problem, the eigenvalues are real. Under standard separated or periodic boundary conditions, the spectrum is discrete and can be ordered as

$$
\lambda_0\le \lambda_1\le \lambda_2\le\cdots,
\qquad
\lambda_n\to +\infty.
$$

The precise starting index depends on convention and on the boundary condition. Dirichlet interval modes are often indexed from $n=1$, while Neumann modes naturally include $n=0$.

Eigenfunctions belonging to distinct eigenvalues are orthogonal in $L^2_w$. After normalization,

$$
\int_a^b dx\,w(x)\overline{u_m(x)}u_n(x)=\delta_{mn}.
$$

For many regular separated boundary conditions in one dimension, eigenvalues are simple. Periodic boundary conditions can produce degeneracies. Degeneracy is not a disaster; it just means one must choose an orthonormal basis inside each eigenspace.

## The variational principle and Rayleigh quotient

Assume for simplicity that the boundary conditions make all boundary terms vanish and that the functions are real. Multiplying the eigenvalue equation by $y$ and integrating gives

$$
\int_a^b dx\,\left[p(y')^2+q y^2\right]
=
\lambda\int_a^b dx\,w y^2.
$$

For an admissible nonzero trial function $y$, define the Rayleigh quotient

$$
R[y]
=
\frac{\int_a^b dx\,\left[p|y'|^2+q|y|^2\right]}
{\int_a^b dx\,w|y|^2}.
$$

For Dirichlet-type domains, the lowest eigenvalue is characterized by

$$
\lambda_0=\inf_{y\ne 0}R[y].
$$

Higher eigenvalues can be obtained by minimizing over functions orthogonal to the lower modes. This is one reason Sturm–Liouville operators are so useful for stability analysis. If the lowest eigenvalue of a fluctuation operator is negative, a classical solution is unstable. If it is zero, there may be a symmetry or modulus. If it is positive, the quadratic action is locally stable.

In QFT language, a classical background $\phi_{\rm cl}$ gives a quadratic fluctuation operator

$$
S[\phi_{\rm cl}+\eta]
=S[\phi_{\rm cl}]+rac12\langle \eta,L\eta\rangle+\cdots.
$$

The signs and zero modes of $L$ decide whether the Gaussian approximation is stable, unstable, or degenerate.

## Completeness and mode expansions

For a regular self-adjoint Sturm–Liouville problem, the normalized eigenfunctions form a complete orthonormal basis of $L^2_w([a,b])$. Thus a suitable function $f$ admits the expansion

$$
f(x)=\sum_n f_n u_n(x),
$$

where

$$
f_n=\langle u_n,f\rangle_w
=\int_a^b dx\,w(x)\overline{u_n(x)}f(x).
$$

The equality is in the Hilbert-space sense for general $L^2_w$ functions and pointwise under stronger regularity assumptions. This distinction matters. A Fourier series is not automatically pointwise equal to a discontinuous function at the jump; it converges in a more subtle sense. The same warning applies to general Sturm–Liouville expansions.

For a free field, this expansion diagonalizes the quadratic action. Suppose the spatial part of a wave operator has eigenfunctions $u_n$:

$$
A u_n=\omega_n^2 u_n.
$$

Then a real field can be expanded as

$$
\phi(t,x)=\sum_n q_n(t)u_n(x),
$$

and the free action becomes a sum of oscillator actions, schematically

$$
S=\frac12\sum_n\int dt\,\left(\dot q_n^2-\omega_n^2q_n^2\right).
$$

This is the bridge from PDEs to harmonic oscillators, Fock space, propagators, finite-volume spectra, and one-loop determinants.

## Green kernels from Sturm–Liouville modes

If $\tau u_n=\lambda_n u_n$ and the normalized eigenfunctions are complete in $L^2_w$, then the resolvent kernel is

$$
G_\zeta(x,y)=\sum_n\frac{u_n(x)\overline{u_n(y)}}{\lambda_n-\zeta},
$$

for $\zeta$ away from the spectrum. The kernel is written with respect to the weighted measure:

$$
[(\tau-\zeta)^{-1}f](x)
=
\int_a^b dy\,w(y)G_\zeta(x,y)f(y).
$$

Equivalently,

$$
(\tau_x-\zeta)G_\zeta(x,y)
=\frac{\delta(x-y)}{w(y)},
$$

where the right-hand side is the delta distribution appropriate to the $w(y)dy$ measure. This is the small convention trap that catches everyone once.

For the unweighted operator $L=-(p\partial_x)'+q$, the kernel $K_\zeta$ solving

$$
(L_x-\zeta w(x))K_\zeta(x,y)=\delta(x-y)
$$

is related to $G_\zeta$ by the same integral formula without an extra $w$ outside. The two notations are equivalent if handled consistently.

The next page, [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), explains this inverse-kernel viewpoint systematically.

## Constructing the one-dimensional Green kernel

There is also a direct ODE construction. Consider

$$
L_\zeta y=-(p y')'+q y-\zeta w y.
$$

Let $u_L$ solve the homogeneous equation $L_\zeta u_L=0$ and satisfy the left boundary condition. Let $u_R$ solve the homogeneous equation and satisfy the right boundary condition. Define the weighted Wronskian-like quantity

$$
W_p[u_L,u_R](x)
=p(x)\left(u_L(x)u_R'(x)-u_L'(x)u_R(x)\right).
$$

For homogeneous solutions it is independent of $x$. If $W_p\ne 0$, the Green kernel satisfying both boundary conditions is

$$
K_\zeta(x,y)
=-\frac{u_L(x_<)u_R(x_>)}{W_p[u_L,u_R]},
$$

where

$$
x_<=\min(x,y),
\qquad
x_>=\max(x,y).
$$

The minus sign comes from the convention $L=-(p\partial_x)'+\cdots$. Across $x=y$, the kernel is continuous, but its derivative has a jump:

$$
p(y)\left[\partial_xK_\zeta(x,y)\right]_{x=y^-}^{x=y^+}=1,
$$

or equivalently

$$
p(y)\partial_xK_\zeta(y^+,y)-p(y)\partial_xK_\zeta(y^-,y)=-1.
$$

Both statements are the same sign convention written with opposite jump orientation. Write your jump convention once, and your future self will buy you coffee.

## Oscillation and node counting

Regular Sturm–Liouville theory also gives a powerful qualitative fact: eigenfunctions are ordered by their zeros. In a standard separated problem, the $n$th eigenfunction has $n$ interior zeros if indexed from $n=0$. This is the Sturm oscillation theorem.

For the Dirichlet Laplacian on $[0,L]$,

$$
u_n(x)=\sqrt{\frac{2}{L}}\sin\frac{n\pi x}{L},
\qquad n=1,2,\ldots,
$$

has $n-1$ interior zeros. If one reindexes by $k=n-1$, the $k$th mode has $k$ nodes.

In quantum mechanics this is the familiar statement that excited bound-state wavefunctions have more nodes. In QFT fluctuation problems it helps identify negative modes and zero modes. Around a tunneling bounce, for example, the existence of a single negative mode is not a detail; it is what turns a Euclidean saddle into a decay rate rather than an ordinary stable correction.

## Singular Sturm–Liouville problems

Many QFT examples are not regular. Radial equations often have singular endpoints. Infinite intervals have endpoints at infinity. Bessel equations have singular behavior at the origin. Schrödinger operators may have continuous spectra.

A typical radial equation contains terms like

$$
-\frac{1}{r^{d-1}}\frac{d}{dr}\left(r^{d-1}\frac{dR}{dr}\right)
+rac{\ell(\ell+d-2)}{r^2}R
=
\lambda R.
$$

This is Sturm–Liouville form with

$$
p(r)=r^{d-1},
\qquad
w(r)=r^{d-1},
$$

and an effective singular potential. The endpoint $r=0$ requires a regularity condition, but what “regularity” means depends on dimension, angular momentum, and the chosen Hilbert space.

For singular endpoints one encounters the limit-point and limit-circle classification. Roughly:

- a limit-point endpoint supplies its own self-adjoint behavior, so no extra boundary condition is needed there;
- a limit-circle endpoint requires a boundary condition to choose a self-adjoint extension.

This is the same domain issue from [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), now with the boundary hiding inside a singular point or at infinity.

## Sturm–Liouville theory in QFT

Here are common places where this machinery enters.

### Finite volume and compactification

On a compact spatial direction, the field decomposes into modes. For a circle of length $L$,

$$
u_n(x)=\frac{1}{\sqrt L}e^{2\pi i n x/L},
\qquad
\lambda_n=\left(\frac{2\pi n}{L}\right)^2.
$$

The $n=0$ mode is often special. It controls infrared behavior, dimensional reduction, finite-temperature zero Matsubara modes, and spontaneous-symmetry subtleties.

### Casimir and boundary problems

Between plates or on an interval, boundary conditions change the eigenvalues. A one-loop vacuum energy often starts formally as

$$
E_0=\frac12\sum_n\omega_n.
$$

This expression is divergent and must be regulated, but the input spectrum comes from a boundary-value problem. Change the boundary condition and the spectrum changes; so does the finite part after a physically meaningful subtraction.

### Solitons and instantons

A fluctuation operator around a one-dimensional kink often has the form

$$
L=-\frac{d^2}{dx^2}+V''(\phi_{\rm kink}(x)).
$$

Its zero mode is typically

$$
\eta_0(x)\propto \frac{d\phi_{\rm kink}}{dx},
$$

because translating the kink costs no energy. The zero mode is not a mistake in the determinant; it is the derivative of a symmetry orbit.

### Partial waves

Rotational symmetry reduces many higher-dimensional problems to radial Sturm–Liouville problems. The angular part supplies quantum numbers, degeneracies, and centrifugal terms. Loop integrals, phase shifts, spectral densities, scattering amplitudes, and determinant ratios can all be computed through partial-wave decompositions.

### Heat kernels and determinants

If $L u_n=\lambda_n u_n$, then the heat trace is

$$
\operatorname{Tr}e^{-sL}=\sum_n e^{-s\lambda_n}.
$$

A zeta-regularized determinant is built from

$$
\zeta_L(s)=\sum_n\lambda_n^{-s},
$$

with zero modes removed when necessary. The one-dimensional theory is often the best classroom for learning how spectra become determinants.

## Common pitfalls

### Treating the weight as optional

If the equation is

$$
-(p y')'+q y=\lambda w y,
$$

then the orthogonality relation uses $w(x)dx$, not necessarily $dx$. Forgetting the weight gives wrong expansion coefficients.

### Forgetting that boundary conditions define the operator

The expression $-d^2/dx^2$ has different spectra with Dirichlet, Neumann, Robin, and periodic boundary conditions. There is no unique “the spectrum of $-d^2/dx^2$ on an interval” until the domain is specified.

### Inverting through zero modes

If $\lambda_0=0$, then the naive Green function

$$
\sum_n\frac{u_n(x)\overline{u_n(y)}}{\lambda_n}
$$

blows up. One must project out the zero mode, impose a solvability condition, add a small regulator, or treat the zero mode as a collective coordinate.

### Confusing pointwise and Hilbert-space convergence

Completeness in $L^2_w$ does not mean every eigenfunction expansion converges pointwise everywhere. Boundary discontinuities and low regularity require care.

### Using the wrong delta function

In a weighted Hilbert space, the identity kernel is not always written the same way. If

$$
f(x)=\int dy\,w(y)\delta_w(x,y)f(y),
$$

then

$$
\delta_w(x,y)=\frac{\delta(x-y)}{w(y)}.
$$

This matters when writing spectral resolutions and Green functions.

## Exercises

### Exercise 1: Orthogonality with a weight

Let $u_m$ and $u_n$ solve

$$
-(p u')'+q u=\lambda w u
$$

with the same self-adjoint boundary conditions. Show that if $\lambda_m\ne\lambda_n$, then

$$
\int_a^b dx\,w(x)\overline{u_m(x)}u_n(x)=0.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
Lu_n=\lambda_n w u_n,
\qquad
Lu_m=\lambda_m w u_m,
$$

with $L=-(p\partial_x)'+q$. Multiply the first equation by $\overline{u_m}$ and integrate. Multiply the conjugate of the second equation by $u_n$ and integrate. Subtract:

$$
\int_a^b dx\,\overline{u_m}Lu_n
-
\int_a^b dx\,\overline{Lu_m}u_n
=
(\lambda_n-\lambda_m)\int_a^b dx\,w\overline{u_m}u_n.
$$

The left-hand side is the boundary form. Self-adjoint boundary conditions make it vanish. Therefore

$$
(\lambda_n-\lambda_m)\langle u_m,u_n\rangle_w=0.
$$

For distinct eigenvalues, the weighted inner product is zero.

</details>

### Exercise 2: Dirichlet modes on an interval

Solve

$$
-y''=\lambda y,
\qquad
0<x<L,
\qquad
y(0)=y(L)=0.
$$

Normalize the eigenfunctions in $L^2([0,L])$.

<details><summary><strong>Solution</strong></summary>

For $\lambda=k^2>0$,

$$
y(x)=A\sin kx+B\cos kx.
$$

The condition $y(0)=0$ gives $B=0$. The condition $y(L)=0$ gives

$$
\sin kL=0,
$$

so

$$
k=\frac{n\pi}{L},
\qquad
n=1,2,3,\ldots.
$$

Thus

$$
\lambda_n=\left(\frac{n\pi}{L}\right)^2.
$$

Since

$$
\int_0^L dx\,\sin^2\frac{n\pi x}{L}=\frac{L}{2},
$$

the normalized modes are

$$
u_n(x)=\sqrt{\frac{2}{L}}\sin\frac{n\pi x}{L}.
$$

</details>

### Exercise 3: Neumann zero mode and solvability

Show that the problem

$$
-u''=f,
\qquad
u'(0)=u'(L)=0
$$

has a solution only if

$$
\int_0^L dx\,f(x)=0.
$$

<details><summary><strong>Solution</strong></summary>

Integrate the equation over the interval:

$$
\int_0^L dx\,f(x)=\int_0^L dx\,(-u'')=-u'(L)+u'(0).
$$

The Neumann boundary conditions give $u'(0)=u'(L)=0$, so

$$
\int_0^L dx\,f(x)=0.
$$

This is exactly the condition that $f$ be orthogonal to the constant zero mode.

</details>

### Exercise 4: The jump condition

Let $K(x,y)$ solve

$$
\left[-\frac{d^2}{dx^2}+m^2\right]K(x,y)=\delta(x-y)
$$

on an interval, away from boundary details. Show that $K$ is continuous at $x=y$ but its derivative satisfies

$$
\partial_xK(y^+,y)-\partial_xK(y^-,y)=-1.
$$

<details><summary><strong>Solution</strong></summary>

Integrate the equation from $y-\epsilon$ to $y+\epsilon$:

$$
\int_{y-\epsilon}^{y+\epsilon}dx\,[-\partial_x^2K(x,y)+m^2K(x,y)]=1.
$$

The mass term vanishes as $\epsilon\to0$ if $K$ is locally bounded. The second-derivative term gives

$$
-\partial_xK(y^+,y)+\partial_xK(y^-,y)=1.
$$

Therefore

$$
\partial_xK(y^+,y)-\partial_xK(y^-,y)=-1.
$$

Continuity follows because a finite jump in $K$ would produce a $\delta'$ term under $-\partial_x^2$, not just a $\delta$ term.

</details>

## References

- R. Courant and D. Hilbert, *Methods of Mathematical Physics*, Vol. 1.
- G. Teschl, *Ordinary Differential Equations and Dynamical Systems* and *Mathematical Methods in Quantum Mechanics*.
- E. Coddington and N. Levinson, *Theory of Ordinary Differential Equations*.
- A. Zettl, *Sturm–Liouville Theory*.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, especially Vols. 1 and 2.
- L. C. Evans, *Partial Differential Equations*.
- P. M. Morse and H. Feshbach, *Methods of Theoretical Physics*.
- M. Srednicki, *Quantum Field Theory*, for mode expansions, determinants, and finite-volume intuition.
- M. Marino, *Instantons and Large N*, for one-dimensional fluctuation operators and determinant methods around saddles.

## Version history

- 2026-06-25: Initial polished draft for the Mathematical Toolkit.
