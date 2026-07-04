---
title: "Spectral Methods"
description: "A QFT-oriented guide to Fourier, Chebyshev, Galerkin, and pseudospectral methods, including convergence, differentiation matrices, quadrature, aliasing, boundary conditions, and spectral regulators."
sidebar:
  label: "Spectral Methods"
  order: 2
level: Graduate
status: "Polished draft"
source: "Spectral numerical analysis, Fourier and Chebyshev methods, Galerkin and pseudospectral discretization, numerical PDEs, and QFT applications to modes, spectra, Green functions, and truncated bases."
topics:
  - spectral methods
  - Fourier methods
  - Chebyshev methods
  - Galerkin methods
  - pseudospectral collocation
  - aliasing
  - spectral convergence
canonicalTopics:
  - spectral-methods
  - fourier-spectral-method
  - chebyshev-collocation
  - galerkin-method
  - pseudospectral-methods
researchStatus:
  established:
    - "Fourier and Chebyshev spectral methods, Galerkin projection, collocation, differentiation matrices, spectral convergence, and aliasing analysis are standard parts of high-accuracy numerical analysis."
  active:
    - "QFT-adjacent applications include high-precision spectral solvers, conformal-block numerics, Hamiltonian truncation, matrix models, tensor-network basis choices, and spectral treatments of real-time or curved-background field equations."
---

## Summary

Spectral methods approximate a function by a finite expansion in global basis functions. Instead of storing only nearby differences on a grid, one writes

$$
f(x)\approx \sum_{n=0}^N c_n\psi_n(x),
$$

where the basis $\psi_n$ is chosen to match the domain and boundary conditions. For a periodic interval, the natural basis is Fourier modes:

$$
f(x)\approx \sum_{|n|\le N/2} \tilde f_n e^{2\pi i n x/L}.
$$

For a finite interval, a common basis is Chebyshev polynomials:

$$
f(x)\approx \sum_{n=0}^N c_n T_n(x).
$$

The payoff can be dramatic: for analytic functions on simple domains, spectral errors often decrease faster than any power of $1/N$. The price is equally real: spectral methods are global, dense, sensitive to nonsmoothness, and vulnerable to aliasing in nonlinear problems.

The slogan is:

$$
\text{finite differences use locality; spectral methods use smoothness}.
$$

## Prerequisites

You should know Fourier series, orthogonal polynomials at a basic level, linear algebra, and the difference between boundary-value and initial-value problems. Familiarity with Green functions, eigenvalue problems, and finite-volume QFT helps.

This page complements [Finite-Difference Methods](/math-toolkit/numerical-mathematics/finite-difference-methods/). The two methods solve many of the same continuum problems but make almost opposite bargains.

## Core idea

A spectral method chooses a finite-dimensional trial space

$$
V_N=\operatorname{span}\{\psi_0,\ldots,\psi_N\}
$$

and replaces a continuum problem by a projected problem inside $V_N$.

For a differential equation

$$
Lu=f,
$$

one seeks

$$
u_N(x)=\sum_{n=0}^N c_n\psi_n(x)
$$

and determines the coefficients $c_n$ by one of two broad strategies:

| Strategy | Condition imposed |
|---|---|
| Galerkin | the residual $Lu_N-f$ is orthogonal to test functions |
| Collocation or pseudospectral | the equation holds at chosen grid points |

Both turn a differential equation into linear algebra. The difference is how the continuum residual is forced to vanish.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A spectral-method workflow from basis choice to coefficients, differentiation, aliasing control, and QFT interpretation.](/figures/math-toolkit/spectral-method-basis-flow.svg)

<figcaption>

A spectral method replaces a field by coefficients in a global basis. Derivatives are exact within the truncated basis, but truncation, aliasing, nonsmoothness, and boundary treatment control the actual error.

</figcaption>
</figure>

## Fourier spectral methods

For a periodic function on $[0,L]$, write

$$
f(x)=\sum_{n\in\mathbb Z}\tilde f_n e^{ik_nx},
\qquad
k_n=\frac{2\pi n}{L}.
$$

The derivative is diagonal in Fourier space:

$$
\partial_x f(x)=\sum_{n\in\mathbb Z} ik_n\tilde f_n e^{ik_nx}.
$$

A Fourier spectral method truncates to finitely many modes:

$$
f_N(x)=\sum_{|n|\le N/2}\tilde f_n e^{ik_nx}.
$$

Then

$$
\partial_x f_N(x)=\sum_{|n|\le N/2} ik_n\tilde f_n e^{ik_nx}
$$

is the exact derivative of the truncated function.

This is the cleanest possible derivative operator for periodic smooth data. Unlike the finite-difference derivative, it uses the continuum symbol $ik_n$ for retained modes. The regulator is not a modified momentum; it is the truncation of high modes.

## Fourier collocation and the discrete transform

In practice one stores values on $N$ grid points

$$
x_j=\frac{Lj}{N},
\qquad
j=0,1,\ldots,N-1.
$$

The discrete Fourier coefficients are conventionally

$$
\tilde f_n=\frac1N\sum_{j=0}^{N-1} f_j e^{-2\pi i n j/N},
$$

with inverse

$$
f_j=\sum_n \tilde f_n e^{2\pi i n j/N},
$$

where $n$ runs over the chosen discrete frequency set. Different software packages place the factors of $N$ differently; the invariant fact is the forward-inverse pair.

The spectral derivative at grid points is computed by:

```txt
values f_j
  → discrete Fourier coefficients f̃_n
  → multiply by ik_n
  → inverse transform
```

This is why fast Fourier transforms make Fourier spectral methods powerful.

## Spectral versus finite-difference symbols

For a retained Fourier mode, the Fourier spectral derivative acts as

$$
\partial_x\quad\leadsto\quad ik.
$$

The centered finite-difference derivative acts as

$$
D_0\quad\leadsto\quad \frac{i\sin(ka)}{a}.
$$

Thus a spectral method has no low-order dispersion error for retained linear modes. But it has a hard truncation: modes beyond the maximum resolved wavenumber do not exist.

For the Laplacian,

$$
-\partial_x^2\quad\leadsto\quad k^2
$$

in a Fourier spectral method, while the nearest-neighbor finite-difference Laplacian gives

$$
-\Delta_a\quad\leadsto\quad \frac{4}{a^2}\sin^2\!\left(\frac{ka}{2}\right).
$$

This is the basic trade:

| Method | Derivative error for resolved smooth modes | UV behavior |
|---|---|---|
| finite difference | local modified symbol | Brillouin-zone dispersion |
| Fourier spectral | exact symbol on retained modes | global truncation |

## Chebyshev polynomials

Fourier methods are natural for periodic domains. On a finite interval, one often uses Chebyshev polynomials

$$
T_n(x)=\cos(n\arccos x),
\qquad
x\in[-1,1].
$$

A smooth function is approximated by

$$
f_N(x)=\sum_{n=0}^N c_nT_n(x).
$$

Chebyshev methods typically use clustered points

$$
x_j=\cos\!\left(\frac{\pi j}{N}\right),
\qquad
j=0,1,\ldots,N.
$$

These points cluster near the endpoints. That clustering suppresses the Runge phenomenon and helps resolve boundary layers.

For a general interval $[a,b]$, map to $[-1,1]$ by

$$
x=\frac{2r-(a+b)}{b-a}.
$$

Derivatives transform by the chain rule:

$$
\frac{d}{dr}=\frac{2}{b-a}\frac{d}{dx}.
$$

## Collocation and differentiation matrices

In a Chebyshev collocation method, one stores values

$$
u_j=u(x_j)
$$

at the Chebyshev points and uses a differentiation matrix $D$ such that

$$
(Du)_j\approx u'(x_j).
$$

The matrix $D$ is dense. This is not a flaw. Spectral differentiation is global: changing one value generally changes the interpolating polynomial everywhere.

A boundary-value problem such as

$$
-u''(x)+V(x)u(x)=\lambda u(x)
$$

becomes a matrix eigenvalue problem

$$
\left(-D^2+V\right)u=\lambda u,
$$

with rows modified or unknowns eliminated to impose boundary conditions.

This method is popular for high-precision eigenvalue problems, radial equations, soliton fluctuation spectra, and mode problems on simple domains.

## Galerkin projection

In a Galerkin method, one chooses trial and test functions and requires the residual to be orthogonal to the test space. For

$$
Lu=f,
$$

with

$$
u_N=\sum_n c_n\psi_n,
$$

one imposes

$$
\langle \psi_m,Lu_N-f\rangle=0
$$

for each $m$. This gives a linear system

$$
\sum_n \langle \psi_m,L\psi_n\rangle c_n
=\langle\psi_m,f\rangle.
$$

This is close in spirit to variational calculus. If $L$ is self-adjoint and positive, the Galerkin system often preserves those properties. This matters for eigenvalues, stability, and conserved structures.

Collocation asks the equation to hold at points. Galerkin asks it to hold after testing against basis functions. Both are useful; neither is morally superior.

## Spectral convergence

For analytic periodic functions, Fourier coefficients often decay exponentially:

$$
|\tilde f_n|\lesssim e^{-\alpha |n|}.
$$

Then the truncation error decreases exponentially with $N$:

$$
\|f-f_N\|\lesssim e^{-\alpha N}.
$$

For functions with only $p$ derivatives, the decay is algebraic:

$$
|\tilde f_n|\sim |n|^{-p-1},
$$

and spectral convergence is lost.

This is why spectral methods feel miraculous for smooth instanton profiles, bound-state wavefunctions, and analytic background fields, but can become grumpy around shocks, discontinuities, cusps, delta-function sources, and sharp boundaries.

## Gibbs phenomenon

If a periodic function has a jump discontinuity, its truncated Fourier series overshoots near the jump by an amount that does not vanish pointwise as $N\to\infty$. The oscillations become narrower, but the overshoot remains.

This is the Gibbs phenomenon. In QFT-flavored computations, it appears whenever one expands nonsmooth sources, step potentials, sharp regulators, or functions with branch-type singular behavior in a too-smooth basis.

The lesson is not “never use spectral methods.” The lesson is to choose basis functions and domain decompositions that match the regularity of the problem.

## Aliasing

Aliasing occurs because products of truncated functions generate unresolved high modes. Suppose

$$
f_N(x)=\sum_{|n|\le N/2}\tilde f_ne^{ik_nx},
\qquad
 g_N(x)=\sum_{|n|\le N/2}\tilde g_ne^{ik_nx}.
$$

Their product contains modes with frequencies up to roughly $N$. If the product is evaluated on only $N$ grid points, high modes are folded back into lower modes.

This is especially important for nonlinear equations. A cubic interaction $\phi^3$ or nonlinear term $u\partial_xu$ generates higher Fourier modes even if $u$ was initially band-limited.

A common remedy is dealiasing. One version is the two-thirds rule: keep only the lower $2/3$ of modes after nonlinear products. Another is padding: transform to a larger grid, multiply, and truncate back.

Aliasing is not roundoff error. It is a deterministic error caused by representing nonlinear products in an insufficient basis.

## Quadrature

Spectral methods often come with high-order quadrature rules. For Fourier collocation on a periodic grid, the trapezoidal rule

$$
\int_0^L dx\,f(x)
\approx
\frac{L}{N}\sum_{j=0}^{N-1}f(x_j)
$$

is spectrally accurate for smooth periodic functions.

For Chebyshev points, Clenshaw–Curtis quadrature approximates

$$
\int_{-1}^1 dx\,f(x)
$$

using weights adapted to Chebyshev interpolation. Gaussian quadrature is another high-order strategy, exact for polynomials up to a prescribed degree.

In path-integral and spectral-action calculations, quadrature is often as important as differentiation. A high-order derivative paired with a careless integral is a tiny sports car towing a brick wall.

## Boundary conditions

Boundary conditions can be built into the basis or imposed afterward.

For example, Dirichlet conditions on $[-1,1]$ can be built into trial functions of the form

$$
\psi_n(x)=(1-x^2)T_n(x),
$$

so that

$$
\psi_n(\pm1)=0.
$$

Alternatively, one may use Chebyshev collocation and replace the first and last equations by

$$
u(-1)=0,
\qquad
u(1)=0.
$$

The first approach enforces boundary conditions exactly in the trial space. The second is often easier to implement. Both must be checked for conditioning and accuracy.

For periodic fields, Fourier modes automatically satisfy periodicity. For antiperiodic fields, use modes

$$
e^{2\pi i(n+1/2)x/L}.
$$

This is the spectral version of thermal fermion boundary conditions.

## Spectral regulators in QFT

A spectral truncation is a regulator. For example, on a circle of length $L$, retaining modes

$$
|n|\le N
$$

is a momentum cutoff

$$
|k_n|\le \frac{2\pi N}{L}.
$$

In a Hamiltonian truncation, one keeps only basis states below a cutoff energy. In a matrix model, one may truncate a basis of orthogonal polynomials or eigenvalue modes. In a curved background, one might truncate eigenfunctions of a Laplace-type operator:

$$
-\Delta\psi_n=\lambda_n\psi_n,
\qquad
\lambda_n\le \Lambda^2.
$$

Spectral cutoffs preserve some structures and break others. A Laplacian eigenmode cutoff may respect geometric symmetries of the background, while a coordinate grid may not. A Fourier cutoff may preserve translations but complicate locality. As always, a regulator is part of the calculation.

## Green functions and mode sums

If an operator has eigenfunctions

$$
L\psi_n=\lambda_n\psi_n,
$$

with orthonormality

$$
\langle \psi_m,\psi_n\rangle=\delta_{mn},
$$

then the Green function is formally

$$
G(x,y)=\sum_n\frac{\psi_n(x)\psi_n^*(y)}{\lambda_n}.
$$

A spectral method truncates this sum:

$$
G_N(x,y)=\sum_{n=0}^N\frac{\psi_n(x)\psi_n^*(y)}{\lambda_n}.
$$

This is often an excellent way to compute propagators, heat kernels, Casimir energies, and fluctuation determinants. But ultraviolet singularities live precisely in the high-mode tail. Truncating the sum regulates the singularity; renormalization or extrapolation must then account for the cutoff dependence.

## Spectral methods and locality

Finite differences are local in position space. Spectral methods are local in mode space. That distinction matters physically.

A differential operator that is local in $x$ can become diagonal or sparse in a good spectral basis. But a pointwise interaction such as

$$
\lambda \phi(x)^4
$$

becomes a convolution over modes. Conversely, a momentum cutoff is simple spectrally but nonlocal in position space.

This is not a defect. It is a choice of representation. A good numerical method makes the hard part of the problem as small as possible.

## Conditioning

Spectral differentiation matrices can be ill-conditioned, especially at high order. For Chebyshev collocation, entries near endpoints can grow rapidly with $N$. Higher derivatives amplify high modes:

$$
\partial_x^p e^{ikx}=(ik)^p e^{ikx}.
$$

Thus high-frequency noise is magnified by differentiation.

Good spectral computations monitor residuals, convergence with $N$, sensitivity to precision, and stability under changes of basis or mapping. Spectral accuracy does not exempt you from numerical humility. Alas.

## When spectral methods are the right tool

Spectral methods are often excellent when:

| Situation | Why spectral methods help |
|---|---|
| solution is smooth or analytic | coefficients decay rapidly |
| domain is periodic or simple | natural global bases exist |
| high precision is needed | convergence can be exponential |
| linear operator has known eigenbasis | derivatives or inverses diagonalize |
| boundary conditions match basis | constraints become exact or simple |
| mode interpretation is physical | truncation has a clean spectral meaning |

They are less ideal when the solution has discontinuities, complicated local geometry, rough coefficients, strongly localized defects, shocks, or many independent length scales not captured by a single basis.

## Comparison with finite differences

| Question | Finite differences | Spectral methods |
|---|---|---|
| Main approximation | local stencil | global expansion |
| Matrix structure | sparse | often dense |
| Best for | local geometry, rough problems, lattice regulators | smooth functions, simple domains, high precision |
| Derivative symbol | modified, e.g. $i\sin(ka)/a$ | exact $ik$ on retained Fourier modes |
| Boundary handling | modified rows or ghost points | built-in basis or collocation constraints |
| Nonlinear products | local in position | convolutions and aliasing |
| Continuum control | grid spacing $a\to0$ | mode cutoff $N\to\infty$ |

Many serious computations mix them: spectral in periodic directions, finite differences in radial directions; finite elements for geometry, spectral basis for internal modes; finite differences for evolution, spectral analysis for diagnostics.

## Common pitfalls

### Thinking spectral means exact

A spectral derivative is exact for the truncated interpolant, not for the unknown continuum function. Truncation error still controls the calculation.

### Ignoring nonsmoothness

Exponential convergence requires regularity. A cusp, discontinuity, branch point, or delta-function source can reduce spectral convergence to algebraic convergence or produce Gibbs oscillations.

### Forgetting aliasing in nonlinear terms

Products of resolved modes generate unresolved modes. If they are folded back into the resolved range, the low modes are contaminated. Dealiasing is not optional in many nonlinear spectral computations.

### Treating dense matrices as harmless

Spectral matrices can become expensive and ill-conditioned. A beautiful $N=80$ calculation might be better than a doomed $N=8000$ calculation, but only if convergence is checked.

### Imposing boundary conditions inconsistently

Boundary conditions can be built into the basis or imposed by replacing equations. Mixing these carelessly can overconstrain the problem or break self-adjointness.

### Mistaking a spectral cutoff for a local regulator

A mode cutoff is usually nonlocal in position space. That can be fine, but it affects interpretation of UV-sensitive observables.

## Exercises

### Exercise 1: Fourier derivative

Let

$$
f(x)=\sum_{n=-N}^{N}\tilde f_ne^{2\pi i n x/L}.
$$

Show that the derivative is obtained by multiplying each Fourier coefficient by $2\pi i n/L$.

<details><summary><strong>Solution</strong></summary>

Differentiate term by term:

$$
\frac{d}{dx}e^{2\pi i n x/L}
=\frac{2\pi i n}{L}e^{2\pi i n x/L}.
$$

Therefore

$$
f'(x)=\sum_{n=-N}^{N}\frac{2\pi i n}{L}\tilde f_ne^{2\pi i n x/L}.
$$

Thus the derivative is diagonal in Fourier space with multiplier

$$
ik_n=\frac{2\pi i n}{L}.
$$

</details>

### Exercise 2: spectral Laplacian eigenvalues on a circle

On a circle of length $L$, show that

$$
-\partial_x^2 e^{2\pi i n x/L}
=\left(\frac{2\pi n}{L}\right)^2 e^{2\pi i n x/L}.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate twice:

$$
\partial_x^2 e^{2\pi i n x/L}
=\left(\frac{2\pi i n}{L}\right)^2e^{2\pi i n x/L}
=-\left(\frac{2\pi n}{L}\right)^2e^{2\pi i n x/L}.
$$

Multiplying by $-$ gives

$$
-\partial_x^2 e^{2\pi i n x/L}
=\left(\frac{2\pi n}{L}\right)^2e^{2\pi i n x/L}.
$$

This is why the Fourier basis diagonalizes constant-coefficient operators on periodic domains.

</details>

### Exercise 3: antiperiodic modes

Show that

$$
f_n(x)=e^{2\pi i(n+1/2)x/L}
$$

satisfies $f_n(x+L)=-f_n(x)$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
f_n(x+L)
=e^{2\pi i(n+1/2)(x+L)/L}
=e^{2\pi i(n+1/2)x/L}e^{2\pi i(n+1/2)}.
$$

Since

$$
e^{2\pi i(n+1/2)}=e^{2\pi in}e^{\pi i}=-1,
$$

we get

$$
f_n(x+L)=-f_n(x).
$$

These are the natural Fourier modes for antiperiodic boundary conditions.

</details>

### Exercise 4: aliasing of a product

On a grid with $N$ points, modes differing by multiples of $N$ have the same values at all grid points. Show that

$$
e^{2\pi i(n+N)j/N}=e^{2\pi i n j/N}
$$

for integer grid index $j$.

<details><summary><strong>Solution</strong></summary>

We have

$$
e^{2\pi i(n+N)j/N}
=e^{2\pi i n j/N}e^{2\pi i j}.
$$

Since $j$ is an integer,

$$
e^{2\pi i j}=1.
$$

Therefore

$$
e^{2\pi i(n+N)j/N}=e^{2\pi i n j/N}.
$$

This is aliasing: the grid cannot distinguish modes whose indices differ by $N$.

</details>

### Exercise 5: Chebyshev derivative identity

Using

$$
T_n(x)=\cos(n\arccos x),
$$

show that

$$
\frac{dT_n}{dx}=nU_{n-1}(x),
$$

where $U_{n-1}(\cos\theta)=\sin(n\theta)/\sin\theta$.

<details><summary><strong>Solution</strong></summary>

Let $x=\cos\theta$. Then

$$
T_n(x)=\cos(n\theta).
$$

Differentiate with respect to $\theta$:

$$
\frac{dT_n}{d\theta}=-n\sin(n\theta).
$$

Also

$$
\frac{dx}{d\theta}=-\sin\theta.
$$

Thus

$$
\frac{dT_n}{dx}
=\frac{dT_n/d\theta}{dx/d\theta}
=n\frac{\sin(n\theta)}{\sin\theta}.
$$

By definition,

$$
U_{n-1}(\cos\theta)=\frac{\sin(n\theta)}{\sin\theta}.
$$

Therefore

$$
\frac{dT_n}{dx}=nU_{n-1}(x).
$$

</details>

## References

- Trefethen, *Spectral Methods in MATLAB*.
- Boyd, *Chebyshev and Fourier Spectral Methods*.
- Canuto, Hussaini, Quarteroni, and Zang, *Spectral Methods: Fundamentals in Single Domains*.
- Gottlieb and Orszag, *Numerical Analysis of Spectral Methods*.
- Fornberg, *A Practical Guide to Pseudospectral Methods*.
- Boyd, *Solving Transcendental Equations: The Chebyshev Polynomial Proxy and Other Numerical Rootfinders*.
- Poland, Rychkov, and Vichi, “The conformal bootstrap: theory, numerical techniques, and applications.”
- Rychkov and Su, “New developments in the numerical conformal bootstrap.”

## Version history

- **2026-06-27:** First polished draft. Introduces Fourier and Chebyshev spectral methods, Galerkin projection, collocation, spectral convergence, Gibbs phenomena, aliasing, quadrature, boundary conditions, spectral regulators, Green-function mode sums, and worked exercises.
