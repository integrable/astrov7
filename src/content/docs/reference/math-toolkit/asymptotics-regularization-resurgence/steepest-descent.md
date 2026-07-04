---
title: "Steepest Descent"
description: "Derives the steepest-descent method for asymptotic integrals, explains thimbles, saddle contributions, Stokes walls, Hessian factors, zero modes, negative modes, and QFT path-integral applications."
sidebar:
  label: "Steepest Descent"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard references on asymptotic analysis, complex saddle methods, stationary phase, Picard–Lefschetz theory, WKB, instantons, and functional integrals, including Olver, Bender–Orszag, Dingle, Berry, Coleman, Zinn-Justin, Mariño, Shifman, Srednicki, Weinberg, Schwartz, and Zee."
topics:
  - steepest descent
  - saddle-point method
  - stationary phase
  - Picard-Lefschetz theory
  - thimbles
  - Stokes phenomenon
  - Gaussian approximation
  - functional determinants
  - instantons
canonicalTopics:
  - steepest-descent
  - saddle-point-method
  - stationary-phase
  - picard-lefschetz-theory
  - thimble
  - stokes-phenomenon
  - gaussian-approximation
  - functional-determinant
  - instanton
researchStatus:
  established:
    - "Steepest descent and stationary phase are standard asymptotic methods for finite-dimensional integrals with nondegenerate critical points."
    - "In semiclassical path integrals, the same local Gaussian logic produces classical actions, fluctuation determinants, zero-mode measures, and loop expansions around saddles."
  active:
    - "The global contour decomposition of full QFT path integrals, especially in gauge theories and real-time problems, remains subtle and is often treated by a mixture of rigorous finite-dimensional analogies and physical prescriptions."
---

## Summary

Steepest descent is the method for extracting the small-parameter behavior of integrals of the form

$$
I(g)=\int_\Gamma dz\,a(z)e^{-S(z)/g},
\qquad g\to0,
$$

by deforming the contour $\Gamma$ to paths through critical points of $S$:

$$
S'(z_\alpha)=0.
$$

Near a nondegenerate saddle $z_\alpha$,

$$
S(z)=S(z_\alpha)+{1\over2}S''(z_\alpha)(z-z_\alpha)^2+\cdots,
$$

so the leading contribution is Gaussian:

$$
I_\alpha(g)
\sim
n_\alpha e^{-S(z_\alpha)/g}
 a(z_\alpha)
\sqrt{2\pi g\over S''(z_\alpha)}
\left(1+O(g)\right).
$$

The integer or signed coefficient $n_\alpha$ is global: it says whether the original contour actually passes through the saddle after allowed deformations. The exponential and determinant are local: they come from expanding the integrand near the saddle.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Complex-plane diagram showing an original contour, saddles, steepest descent thimbles, upward cycles, and the workflow from critical points to local Gaussian data and global contour coefficients.](/figures/math-toolkit/steepest-descent-thimble-flow.svg)

<figcaption>

Steepest descent separates local data from global data. Critical points and Hessians give local asymptotic sectors, while the contour decomposition $\Gamma\sim\sum_\alpha n_\alpha\mathcal J_\alpha$ tells which sectors appear in the answer. Stokes phenomena occur when this decomposition changes as parameters vary.

</figcaption>
</figure>

This page treats steepest descent as the finite-dimensional prototype for semiclassical QFT. In path integrals, $z_\alpha$ becomes a classical field configuration, $S''$ becomes a differential operator, the Gaussian determinant becomes a functional determinant, and zero modes become collective coordinates.

## Prerequisites

You should know Gaussian integrals, Taylor expansion, complex contour deformation, and basic asymptotic notation. Helpful nearby pages are [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Borel Transform](/math-toolkit/asymptotics-regularization-resurgence/borel-transform/), and [Transseries](/math-toolkit/asymptotics-regularization-resurgence/transseries/).

## Core idea

For small $g$, the factor $e^{-S(z)/g}$ is extremely sensitive to $S(z)$. Regions where $\operatorname{Re}S$ is large are exponentially suppressed. Regions where $S$ is stationary can dominate because the phase or exponential no longer changes linearly.

The saddle condition is

$$
S'(z_\alpha)=0.
$$

The local expansion around $z_\alpha$ is

$$
S(z)=S_\alpha+{1\over2}H_\alpha\xi^2+{1\over6}S^{(3)}_\alpha\xi^3+\cdots,
\qquad
\xi=z-z_\alpha,
$$

where

$$
S_\alpha=S(z_\alpha),
\qquad
H_\alpha=S''(z_\alpha).
$$

The leading term in the integral comes from the Gaussian approximation. Higher terms come from expanding $a(z)$ and the cubic, quartic, and higher terms in $S$.

The global contour decides which saddle expansions appear. A critical point can exist mathematically but contribute zero to a given contour.

## Setup and conventions

We use the exponential convention

$$
I(g)=\int_\Gamma dz\,a(z)e^{-S(z)/g},
\qquad g>0,
\qquad g\to0^+.
$$

For oscillatory integrals one often writes

$$
J(\lambda)=\int dx\,a(x)e^{i\lambda\phi(x)},
\qquad \lambda\to+\infty.
$$

This is related by the formal replacement $g=1/(i\lambda)$ and $S=-i\phi$. The stationary-phase formula contains phases rather than real exponential suppression.

We assume at first that saddles are isolated and nondegenerate:

$$
S'(z_\alpha)=0,
\qquad
S''(z_\alpha)\ne0.
$$

Degenerate saddles, endpoints, branch points, and zero modes require modified formulas.

## The one-dimensional formula

Let $z_\ast$ be a nondegenerate saddle. Locally,

$$
I_\ast(g)=\int_{\mathcal J_\ast}dz\,a(z)e^{-S(z)/g},
$$

where $\mathcal J_\ast$ is a steepest-descent path through $z_\ast$. Write

$$
S(z)=S_\ast+{1\over2}H(z-z_\ast)^2+O\!\left((z-z_\ast)^3\right),
\qquad
H=S''(z_\ast).
$$

Choose the local coordinate along the descent path so that

$$
{1\over2}H(z-z_\ast)^2={1\over2}y^2,
\qquad y\in\mathbb R.
$$

Then

$$
I_\ast(g)
\sim
 e^{-S_\ast/g}a(z_\ast)
\int_{-\infty}^{\infty}{dy\over\sqrt{H}}e^{-y^2/(2g)}.
$$

Thus

$$
I_\ast(g)
\sim
 e^{-S_\ast/g}a(z_\ast)
\sqrt{2\pi g\over H}.
$$

The square root requires a branch choice fixed by the orientation of the contour. In real positive Gaussian integrals this is harmless. In complex saddle problems it is one of the small places where large sign errors like to enter with muddy shoes.

Including higher corrections gives

$$
I_\ast(g)
\sim
 e^{-S_\ast/g}\sqrt{2\pi g\over H}
\sum_{n=0}^{\infty}c_n g^n,
$$

where $c_0=a(z_\ast)$.

## Deriving the first correction

To see what the expansion does, set $z=z_\ast+\sqrt g\,u$ and expand:

$$
S(z)=S_\ast+{g\over2}Hu^2+{g^{3/2}\over6}S_3u^3+{g^2\over24}S_4u^4+\cdots,
$$

with

$$
S_k=S^{(k)}(z_\ast).
$$

Also expand

$$
a(z)=a_0+\sqrt g\,a_1u+{g\over2}a_2u^2+\cdots,
$$

where $a_k=a^{(k)}(z_\ast)$. The integral becomes

$$
I_\ast(g)=e^{-S_\ast/g}\sqrt g
\int du\,e^{-Hu^2/2}
\left[a_0+
\sqrt g\left(a_1u-{a_0S_3\over6}u^3\right)+O(g)\right].
$$

Odd terms integrate to zero on a symmetric steepest descent contour. The first correction comes from the even $O(g)$ terms. The exact expression is not usually memorized; what matters is the method:

1. rescale fluctuations by $\sqrt g$,
2. expand the action and prefactor,
3. evaluate Gaussian moments,
4. obtain an asymptotic series in powers of $g$.

In QFT this is exactly the loop expansion around a classical saddle.

## The multi-dimensional formula

For an $N$-dimensional integral

$$
I(g)=\int_\Gamma d^Nz\,a(z)e^{-S(z)/g},
$$

let $z_\ast$ be a nondegenerate saddle with Hessian matrix

$$
H_{ij}=\left.{\partial^2S\over\partial z^i\partial z^j}\right|_{z=z_\ast}.
$$

The local leading contribution is

$$
I_\ast(g)
\sim
 e^{-S_\ast/g}
(2\pi g)^{N/2}
{a(z_\ast)\over\sqrt{\det H}}
\left(1+O(g)\right),
$$

again with the square-root branch and phase fixed by the integration cycle.

For an oscillatory real integral

$$
J(\lambda)=\int_{\mathbb R^N}d^Nx\,a(x)e^{i\lambda\phi(x)},
$$

with a nondegenerate real critical point $x_\ast$, the stationary-phase formula is

$$
J_\ast(\lambda)
\sim
 e^{i\lambda\phi(x_\ast)}
 e^{i\pi\operatorname{sgn}(H)/4}
\left({2\pi\over\lambda}\right)^{N/2}
{a(x_\ast)\over\sqrt{|\det H|}}
\left(1+O(\lambda^{-1})\right),
$$

where $H_{ij}=\partial_i\partial_j\phi(x_\ast)$ and

$$
\operatorname{sgn}(H)=\#(\text{positive eigenvalues})-\#(\text{negative eigenvalues}).
$$

That phase is the finite-dimensional ancestor of many determinant phases in real-time path integrals.

## Steepest descent paths

For the integrand $e^{-S(z)/g}$ with $g>0$, a steepest descent path through a saddle is chosen so that

$$
\operatorname{Im}S(z)=\operatorname{Im}S(z_\ast)
$$

and

$$
\operatorname{Re}S(z)\ge \operatorname{Re}S(z_\ast)
$$

as one moves away from the saddle. Along such a path, the phase of $e^{-S/g}$ is constant and the magnitude decreases away from the saddle. This turns the local integral into a Gaussian-like convergent integral.

The steepest ascent paths are the dual cycles. They determine intersection numbers: if an upward cycle from $z_\alpha$ intersects the original contour $\Gamma$, then the corresponding descent thimble $\mathcal J_\alpha$ appears in the decomposition.

One writes schematically

$$
\Gamma\sim\sum_\alpha n_\alpha\mathcal J_\alpha,
$$

so

$$
I(g)\sim\sum_\alpha n_\alpha e^{-S_\alpha/g}\Phi_\alpha(g).
$$

This is the geometric origin of the transseries expansion.

## Stokes and anti-Stokes walls

Suppose two saddles have actions $S_\alpha$ and $S_\beta$. Their relative exponential is

$$
\exp\!\left[-{S_\beta-S_\alpha\over g}\right].
$$

For fixed complex $g$, Stokes walls occur when the two exponentials have aligned phases:

$$
\operatorname{Im}\!\left({S_\beta-S_\alpha\over g}\right)=0.
$$

Across such a wall, the thimble decomposition can jump. The exact integral is unchanged, but the asymptotic representation changes.

Anti-Stokes walls, or dominance walls, occur when the two exponentials have equal magnitude:

$$
\operatorname{Re}\!\left({S_\beta-S_\alpha\over g}\right)=0.
$$

Across these walls, the dominant saddle can change. In many physics discussions the terminology is used a little loosely, so it is wise to state which condition is meant.

The connection with Borel summation is direct: a Stokes jump in saddle decomposition is mirrored by a jump between lateral Borel sums.

## Degenerate saddles and endpoints

The Gaussian formula assumes $S''(z_\ast)\ne0$. If the saddle is degenerate, the quadratic approximation fails.

For example, if

$$
S(z)=S_\ast+{c\over m}(z-z_\ast)^m+\cdots,
\qquad m>2,
$$

then the natural fluctuation scale is not $\sqrt g$ but

$$
z-z_\ast\sim g^{1/m}.
$$

The leading asymptotics involve gamma functions or special functions rather than ordinary Gaussian factors. When two saddles collide, Airy-type or Pearcey-type uniform approximations often replace separate saddle expansions.

Endpoints and branch points also contribute. If an integration endpoint is not stationary, Watson's lemma gives endpoint asymptotics. In QFT language, analogous effects can arise from boundaries of moduli space, small instantons, infrared regions, or threshold singularities.

## Zero modes

A zero mode is a direction in which the Hessian vanishes because the saddle belongs to a continuous family. If

$$
H v=0,
$$

then the Gaussian determinant has a zero eigenvalue, and the naive formula diverges.

The cure is not to keep the zero eigenvalue in the determinant. One separates collective coordinates $q^a$ along the saddle family and integrates over them:

$$
\int d^Nz\,e^{-S/g}
\quad\leadsto\quad
\int d^r q\,J(q)
\left(\det{}' H\right)^{-1/2}e^{-S_\ast/g}
\left(1+O(g)\right).
$$

Here $\det{}'$ means the determinant over nonzero fluctuation modes. In instanton calculations, translational zero modes produce spacetime volume factors and powers of the coupling. Gauge zero modes require gauge fixing and division by gauge volume.

## Negative modes

A negative mode is a direction in which the quadratic form has the wrong sign for an ordinary convergent Euclidean Gaussian. For a real finite-dimensional integral, a negative eigenvalue means the real contour is not a descent contour. One must specify how the contour is deformed.

In false-vacuum decay, a bounce saddle has one negative mode. The corresponding contour prescription produces an imaginary part in the energy or effective action. That imaginary part is not an error; it encodes the decay rate of a metastable state.

The practical rule is simple: determinants around saddles are not just numbers. Their sign, phase, zero modes, and contour prescription carry physical information.

## Path-integral version

A Euclidean path integral has the schematic form

$$
Z(g)=\int \mathcal D\phi\,e^{-S_E[\phi]/g}.
$$

The saddle condition is the classical equation of motion:

$$
\left.{\delta S_E\over\delta\phi(x)}\right|_{\phi=\phi_\alpha}=0.
$$

Expand

$$
\phi=\phi_\alpha+\sqrt g\,\eta.
$$

Then

$$
S_E[\phi]
=
S_E[\phi_\alpha]
+{g\over2}\int d^dx\,d^dy\,
\eta(x)\,K_\alpha(x,y)\,\eta(y)
+O(g^{3/2}),
$$

where

$$
K_\alpha(x,y)=
\left.{\delta^2S_E\over\delta\phi(x)\delta\phi(y)}\right|_{\phi=\phi_\alpha}.
$$

The Gaussian integral gives

$$
Z_\alpha(g)
\sim
n_\alpha e^{-S_E[\phi_\alpha]/g}
\left(\det{}' K_\alpha\right)^{-1/2}
\times
\left(\text{zero-mode measure}\right)
\times
\left(1+O(g)\right).
$$

In fermionic sectors, the determinant power and sign are changed by Grassmann integration. In gauge theory, one adds gauge fixing, ghosts, and collective-coordinate factors.

The same schematic formula underlies perturbation theory around the trivial vacuum, instanton calculus, soliton quantization, one-loop effective actions, heat-kernel expansions, and semiclassical tunneling.

## A practical workflow

For a finite-dimensional integral or a semiclassical path integral, the steepest-descent workflow is:

1. identify the small parameter and write the exponent as $e^{-S/g}$ or $e^{iS/g}$,
2. solve the saddle equations,
3. compute the action at each saddle,
4. compute the Hessian and identify zero or negative modes,
5. determine which saddles lie in the contour decomposition,
6. compute Gaussian determinants and collective-coordinate measures,
7. expand interactions around each saddle to obtain loop corrections,
8. track Stokes walls if parameters are complex or if analytic continuation is required,
9. organize the result as a transseries.

The local saddle calculation is often the easy part. The contour, zero modes, and physical prescription are where the gremlins live.

## Common pitfalls

**Counting every critical point as contributing.** A saddle contributes only if its thimble appears in the decomposition of the original contour.

**Using the Gaussian formula at a degenerate saddle.** If the Hessian vanishes, the $g^{1/2}$ scaling and determinant formula fail.

**Dropping determinant phases.** Complex saddles and real-time stationary phase carry phases that affect interference and Stokes jumps.

**Confusing Stokes walls with dominance walls.** Phase alignment controls jumps in the asymptotic representation; equal magnitude controls dominance. Some physics texts blur the terminology, so always check the condition.

**Ignoring zero modes.** Zero modes are collective coordinates, not zero determinants to be blindly inserted into a denominator.

**Treating path-integral contour questions as solved by notation.** Writing $\int\mathcal D\phi$ does not specify the nonperturbative contour in complexified field space.

## Relations to other pages

[Transseries](/math-toolkit/asymptotics-regularization-resurgence/transseries/) uses steepest descent to explain where nonperturbative sectors come from. [Borel Transform](/math-toolkit/asymptotics-regularization-resurgence/borel-transform/) explains how the same saddle data appear as Borel-plane singularities. [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/) explains why the fluctuation expansions are usually divergent.

[Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) gives the functional-integral perspective. [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) supplies the finite-dimensional determinant formulas. [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explain how one-loop determinants are regularized in field theory.

## Research status

For ordinary finite-dimensional integrals with isolated nondegenerate saddles, steepest descent is a mature and precise method. Picard–Lefschetz theory gives a powerful language for contour decomposition and Stokes jumps.

For QFT, the local expansion around a saddle is standard physics. The global contour in infinite-dimensional complexified field space is much more delicate. Many calculations are justified by finite-dimensional analogies, lattice regularization, supersymmetric localization, physical boundary conditions, or consistency checks rather than by a fully rigorous thimble decomposition of the continuum path integral.

## Exercises

### Exercise 1: Gaussian saddle

Evaluate the leading steepest-descent approximation to

$$
I(g)=\int_{-\infty}^{\infty}dx\,e^{-(x^2/2+x^4)/g}
$$

as $g\to0^+$.

<details><summary><strong>Solution</strong></summary>

The exponent is $S(x)=x^2/2+x^4$. The only real minimum is at $x=0$, with

$$
S(0)=0,
\qquad
S''(0)=1.
$$

The leading Gaussian approximation is therefore

$$
I(g)\sim e^0\sqrt{2\pi g\over1}=\sqrt{2\pi g}.
$$

The $x^4$ term gives higher corrections. Since $x\sim\sqrt g$ near the saddle, $x^4/g\sim g$, so the first correction is of order $g$.

</details>

### Exercise 2: Stationary-phase sign

Let

$$
J(\lambda)=\int_{-\infty}^{\infty}dx\,a(x)e^{i\lambda x^2/2},
$$

where $a$ is smooth and decays rapidly. Use stationary phase near $x=0$ to find the leading term.

<details><summary><strong>Solution</strong></summary>

Here $\phi(x)=x^2/2$, so $\phi'(0)=0$ and $\phi''(0)=1$. The one-dimensional stationary-phase formula gives

$$
J(\lambda)
\sim
 e^{i\lambda\phi(0)}e^{i\pi/4}
\left({2\pi\over\lambda}\right)^{1/2}a(0).
$$

Since $\phi(0)=0$,

$$
J(\lambda)
\sim
 e^{i\pi/4}\sqrt{2\pi\over\lambda}\,a(0).
$$

</details>

### Exercise 3: Zero-mode scaling

Suppose a saddle has one exact zero mode and $N-1$ nonzero Gaussian modes. Explain why the determinant should be written as $\det{}'H$ and what replaces the missing Gaussian integral.

<details><summary><strong>Solution</strong></summary>

A zero mode means the quadratic approximation has no restoring force in one direction, so the Gaussian integral in that direction is not controlled by $H$. Including the zero eigenvalue in $\det H$ would give zero and make $(\det H)^{-1/2}$ divergent. The correct procedure is to remove the zero eigenvalue and use $\det{}'H$ over the nonzero modes. The missing integration is replaced by an integral over the collective coordinate parametrizing the family of equivalent saddles, together with the appropriate Jacobian.

</details>

### Exercise 4: Relative saddle action

Two saddles have actions $S_0$ and $S_1$ with $\operatorname{Re}(S_1-S_0)>0$. Write the two-saddle approximation in transseries form relative to the first saddle.

<details><summary><strong>Solution</strong></summary>

The two-saddle approximation is

$$
I(g)\sim n_0e^{-S_0/g}\Phi_0(g)+n_1e^{-S_1/g}\Phi_1(g).
$$

Factor out $e^{-S_0/g}$:

$$
I(g)\sim e^{-S_0/g}\left[n_0\Phi_0(g)+n_1e^{-(S_1-S_0)/g}\Phi_1(g)\right].
$$

The relative transseries action is

$$
A=S_1-S_0.
$$

Because $\operatorname{Re}A>0$, the second sector is exponentially suppressed relative to the first for $g\to0^+$.

</details>

## References

- F. W. J. Olver, *Asymptotics and Special Functions*.
- C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*.
- R. B. Dingle, *Asymptotic Expansions: Their Derivation and Interpretation*.
- M. V. Berry, work on Stokes phenomena and hyperasymptotics.
- S. Coleman, *Aspects of Symmetry*.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- M. Mariño, *Instantons and Large N*.
- M. Shifman, *Advanced Topics in Quantum Field Theory*.
- M. Srednicki, *Quantum Field Theory*.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I.
- M. Schwartz, *Quantum Field Theory and the Standard Model*.

## Version history

- 2026-06-26: First polished draft for the Mathematical Toolkit volume.
