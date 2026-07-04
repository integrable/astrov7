---
title: "WKB Method"
description: "Explains the WKB approximation as a semiclassical expansion for differential equations, with turning points, Airy matching, Bohr–Sommerfeld quantization, tunneling exponents, Stokes phenomena, and QFT applications."
sidebar:
  label: "WKB Method"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard references on asymptotic analysis, semiclassical quantum mechanics, exact WKB, instantons, and QFT tunneling, including Jeffreys, Wentzel, Kramers, Brillouin, Olver, Bender–Orszag, Dingle, Berry, Coleman, Zinn-Justin, Mariño, Shifman, Srednicki, Weinberg, Schwartz, and Zee."
topics:
  - WKB approximation
  - semiclassical approximation
  - turning points
  - Airy matching
  - Bohr-Sommerfeld quantization
  - tunneling
  - Stokes phenomenon
  - exact WKB
  - instantons
  - asymptotic series
canonicalTopics:
  - wkb-method
  - semiclassical-approximation
  - turning-point
  - airy-matching
  - bohr-sommerfeld-quantization
  - tunneling
  - stokes-phenomenon
  - exact-wkb
  - instanton
  - asymptotic-expansion
researchStatus:
  established:
    - "The leading WKB approximation, Airy connection formulae near simple turning points, Bohr–Sommerfeld quantization, and barrier tunneling exponents are standard parts of asymptotic analysis and semiclassical quantum mechanics."
    - "In QFT, WKB logic reappears in saddle-point path integrals, instanton and bounce exponents, fluctuation determinants, and semiclassical mode equations in background fields."
  active:
    - "Exact WKB, resurgence, Stokes automorphisms, complex saddles, and their field-theoretic generalizations remain active research areas, especially in gauge theory, quantum mechanics with degenerate vacua, and nonperturbative definitions of path integrals."
---

## Summary

The WKB method is the semiclassical asymptotic expansion for differential equations with a small parameter multiplying the highest derivative. In one-dimensional quantum mechanics, write the stationary Schrödinger equation as

$$
-{\\hbar^2\over 2m}{d^2\psi\over dx^2}+V(x)\psi=E\psi.
$$

Equivalently,

$$
{d^2\psi\over dx^2}+{p(x)^2\over\hbar^2}\psi=0,
\qquad
p(x)=\sqrt{2m(E-V(x))}
$$

in a classically allowed region. WKB says that when $p(x)$ changes slowly on the local wavelength scale, solutions look locally like plane waves with position-dependent momentum:

$$
\psi_\pm(x)\sim {C_\pm\over\sqrt{p(x)}}
\exp\left(\pm {i\over\hbar}\int^x p(y)\,dy\right).
$$

In a forbidden region, where $V(x)>E$, define

$$
\kappa(x)=\sqrt{2m(V(x)-E)}.
$$

Then the WKB solutions become growing and decaying exponentials:

$$
\psi_\pm(x)\sim {C_\pm\over\sqrt{\kappa(x)}}
\exp\left(\pm {1\over\hbar}\int^x \kappa(y)\,dy\right).
$$

The most important warning is also the most important feature: these formulae fail at turning points, where $p(x)=0$. Turning points are not minor details. They decide quantization conditions, reflection phases, tunneling amplitudes, and Stokes jumps.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing WKB regions separated by turning points: oscillatory waves in classically allowed regions, exponential decay through a barrier, Airy matching near turning points, and Stokes curves in the complex plane.](/figures/math-toolkit/wkb-turning-point-stokes.svg)

<figcaption>

WKB converts a differential equation into local momentum data plus global matching data. Away from turning points, solutions are oscillatory or exponential. Near a simple turning point, the equation reduces to the Airy equation. In the complex plane, Stokes curves determine which exponentially small sectors turn on or off.

</figcaption>
</figure>

This page uses explicit $\hbar$ as a semiclassical book-keeping parameter, even though the site usually sets $\hbar=1$. The physics convention is recovered by setting $\hbar=1$ after the small-parameter structure has done its job.

## Prerequisites

You should know ordinary differential equations, asymptotic series, complex contour deformation, and the basic stationary-phase idea. Helpful nearby pages are [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/), [Steepest Descent](/math-toolkit/asymptotics-regularization-resurgence/steepest-descent/), [Borel Transform](/math-toolkit/asymptotics-regularization-resurgence/borel-transform/), [Transseries](/math-toolkit/asymptotics-regularization-resurgence/transseries/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), and Airy-type special-function pages later in this volume.

The last item is not needed to read this page: the only special-function fact used below is that the Airy equation supplies the universal local model near a simple turning point.

## Core idea

WKB is the differential-equation sibling of steepest descent. Steepest descent starts with an integral and asks which saddle points dominate. WKB starts with a differential equation and asks how a rapidly oscillating or rapidly decaying solution changes when its local wave number varies slowly.

Use the ansatz

$$
\psi(x)=A(x)e^{iS(x)/\hbar}.
$$

Substitute into

$$
\psi''+{p(x)^2\over\hbar^2}\psi=0.
$$

After collecting powers of $\hbar$, one obtains

$$
\left(S'\right)^2-p^2
-i\hbar S''
-2i\hbar {A'\over A}S'
-\hbar^2 {A''\over A}=0.
$$

A convenient way to organize the expansion is to absorb the amplitude into a complex phase,

$$
\psi(x)=\exp\left({i\over\hbar}W(x)\right),
$$

which gives the Riccati equation

$$
\left(W'\right)^2-i\hbar W''=p(x)^2.
$$

Expand

$$
W(x)=W_0(x)+\hbar W_1(x)+\hbar^2W_2(x)+\cdots.
$$

At leading order,

$$
\left(W_0'\right)^2=p^2,
\qquad
W_0'=\pm p.
$$

At the next order,

$$
2W_0'W_1'-iW_0''=0,
$$

so

$$
W_1'={i\over2}{p'\over p}
$$

for the $+$ branch. Hence

$$
e^{iW_1}=p^{-1/2}
$$

up to a constant. This is the origin of the familiar WKB amplitude $p^{-1/2}$.

The leading result is therefore

$$
\psi_\pm(x)
\sim
{C_\pm\over\sqrt{p(x)}}
e^{\pm i\int^x p(y)dy/\hbar}.
$$

The same logic works for many second-order equations after putting them into a Schrödinger-like normal form.

## Validity condition

The leading WKB approximation assumes that the momentum changes little over one local wavelength. A useful condition is

$$
\left|\hbar {p'(x)\over p(x)^2}\right|\ll 1.
$$

There are equivalent higher-order conditions involving $p''/p^3$ and higher derivatives. The simplest message is:

$$
\text{WKB is local if the wavelength varies slowly.}
$$

Since the local wavelength is

$$
\lambda(x)={2\pi\hbar\over |p(x)|},
$$

WKB fails when $p(x)$ becomes small, even if $V(x)$ is perfectly smooth. This is why turning points are special.

A **simple turning point** $x=a$ is a point where

$$
E=V(a),
\qquad
V'(a)\neq0.
$$

Near such a point,

$$
p(x)^2=2m(E-V(x))\approx -2mV'(a)(x-a),
$$

so the differential equation reduces, after rescaling, to the Airy equation. Airy functions are the universal bridge between oscillatory and exponential WKB regions.

## Allowed and forbidden regions

In a classically allowed region $E>V(x)$, $p(x)$ is real. A real solution can be written as

$$
\psi(x)
\sim
{2C\over\sqrt{p(x)}}
\cos\left({1\over\hbar}\int^x p(y)dy+\varphi\right).
$$

In a forbidden region $E<V(x)$, $p=i\kappa$ and the same expression becomes exponential:

$$
\psi(x)
\sim
{C_+\over\sqrt{\kappa(x)}}
\exp\left({1\over\hbar}\int^x \kappa(y)dy\right)
+
{C_-\over\sqrt{\kappa(x)}}
\exp\left(-{1\over\hbar}\int^x \kappa(y)dy\right).
$$

The decaying exponential is often the physically acceptable branch far inside a forbidden region. But near a barrier or finite interval, both branches can matter because matching at two turning points mixes them.

## Airy matching at a simple turning point

Suppose $a$ is a simple turning point, with the allowed region on the left and the forbidden region on the right:

$$
V(x)<E\quad (x<a),
\qquad
V(x)>E\quad (x>a).
$$

Define

$$
p(x)=\sqrt{2m(E-V(x))}\quad (x<a),
\qquad
\kappa(x)=\sqrt{2m(V(x)-E)}\quad (x>a).
$$

The decaying solution on the forbidden side,

$$
{C\over\sqrt{\kappa(x)}}
\exp\left(-{1\over\hbar}\int_a^x \kappa(y)dy\right),
\qquad x>a,
$$

matches to the oscillatory solution

$$
{2C\over\sqrt{p(x)}}
\sin\left({1\over\hbar}\int_x^a p(y)dy+{\pi\over4}\right),
\qquad x<a.
$$

Equivalently, up to harmless phase conventions, one often writes a cosine with a $-\pi/4$ phase. The important piece is the universal Maslov phase $\pi/4$ per simple turning point.

This phase is easy to lose and hard to fake. It is the reason the harmonic oscillator quantization condition gives $n+1/2$ rather than $n$.

## Bohr–Sommerfeld quantization

Consider a bound state between two simple turning points $x_1$ and $x_2$, with $V(x)<E$ in between. Matching to decaying solutions outside the interval gives the quantization condition

$$
\int_{x_1}^{x_2}p(x)\,dx
=\pi\hbar\left(n+{1\over2}\right),
\qquad n=0,1,2,\ldots.
$$

Equivalently,

$$
\oint p(x)\,dx=2\pi\hbar\left(n+{1\over2}\right).
$$

The $1/2$ is the total Maslov contribution from two simple turning points. For more general systems, the condition becomes

$$
\oint p\,dq=2\pi\hbar\left(n+{\mu\over4}\right),
$$

where $\mu$ is the Maslov index of the closed classical orbit.

### Example: harmonic oscillator

For

$$
V(x)={1\over2}m\omega^2x^2,
$$

the turning points are

$$
x_\pm=\pm\sqrt{2E\over m\omega^2}.
$$

The action integral is the area enclosed by the classical orbit in phase space:

$$
\oint p\,dx={2\pi E\over\omega}.
$$

Bohr–Sommerfeld gives

$$
{2\pi E\over\omega}=2\pi\hbar\left(n+{1\over2}\right),
$$

so

$$
E_n=\hbar\omega\left(n+{1\over2}\right).
$$

For the harmonic oscillator this leading WKB result is exact. Do not overgeneralize that miracle; most potentials receive higher WKB corrections.

## Barrier tunneling

Suppose a particle with energy $E$ crosses a barrier with two turning points $x_1<x_2$ and $V(x)>E$ for $x_1<x<x_2$. The leading exponential suppression is

$$
T\sim
\exp\left[-{2\over\hbar}\int_{x_1}^{x_2}\kappa(x)\,dx\right],
\qquad
\kappa(x)=\sqrt{2m(V(x)-E)}.
$$

The exponent

$$
S_\text{barrier}=\int_{x_1}^{x_2}\kappa(x)\,dx
$$

is the imaginary classical action accumulated through the forbidden region. This is the one-dimensional ancestor of instanton and bounce actions in field theory. The prefactor multiplying the exponential depends on matching, boundary conditions, and sometimes resonant structure; the exponential is usually the first thing one trusts.

## Relation to path integrals and instantons

In ordinary quantum mechanics, the transition amplitude has the schematic path-integral form

$$
K(x_f,t_f;x_i,t_i)=\int_{x_i}^{x_f}\mathcal D x\,e^{iS[x]/\hbar}.
$$

The semiclassical limit $\hbar\to0$ is controlled by classical paths satisfying

$$
{\delta S\over\delta x(t)}=0.
$$

WKB and saddle-point path integrals are two descriptions of the same semiclassical physics. WKB solves the Schrödinger equation directly; the path integral expands around classical trajectories. In forbidden regions, one often continues to Euclidean time,

$$
t=-i\tau,
$$

so that the weight becomes

$$
e^{-S_E[x]/\hbar}.
$$

A tunneling solution in Euclidean time is an instanton or bounce, depending on the boundary conditions and physical context. The leading tunneling amplitude has the form

$$
\text{amplitude}\sim A e^{-S_E[x_\text{cl}]/\hbar},
$$

where the prefactor $A$ comes from Gaussian fluctuations, zero modes, and determinant ratios.

Thus WKB is not merely a first-year quantum-mechanics trick. It is the finite-dimensional face of the semiclassical method used throughout QFT.

## Higher WKB corrections

The leading WKB expression can be systematically corrected. Using

$$
\psi(x)=\exp\left({i\over\hbar}W(x)\right),
$$

the Riccati equation

$$
(W')^2-i\hbar W''=p^2
$$

generates a formal expansion

$$
W(x)=\sum_{n=0}^{\infty}\hbar^n W_n(x).
$$

The first two terms are

$$
W_0'=\pm p,
\qquad
W_1'={i\over2}{p'\over p}.
$$

The next term is

$$
W_2'
=\pm\left({p''\over4p^2}-{3(p')^2\over8p^3}\right)
$$

up to the branch convention used for $W_0'$. Higher terms are rational expressions built from $p$ and its derivatives.

This expansion is usually asymptotic, not convergent. Its late terms know about other saddles, turning points, and Stokes phenomena. That is why exact WKB naturally connects to Borel transforms and transseries.

## Stokes phenomena

The two local WKB branches are

$$
\psi_\pm\sim p^{-1/2}e^{\pm i\int^x p dx/\hbar}.
$$

In the complex $x$-plane, their relative size depends on

$$
\operatorname{Re}\left({i\over\hbar}\int^x p(y)dy\right).
$$

A **Stokes curve** is a curve along which the phase difference between two branches is purely imaginary or purely real, depending on convention, so that dominance can change. Crossing such a curve can add an exponentially small multiple of one branch to another. This is not a contradiction in the differential equation; it is how a single analytic solution is represented by different asymptotic expansions in different sectors.

In practical physics language, Stokes phenomena explain why exponentially small reflected waves, tunneling contributions, or instanton sectors can be absent in one asymptotic region and present in another.

## WKB in QFT

QFT uses WKB in several overlapping ways.

First, a field theory can reduce to an effective quantum-mechanical tunneling coordinate. False-vacuum decay, bubble nucleation, and collective-coordinate tunneling often have an exponent of the form

$$
\Gamma\sim e^{-B/\hbar},
$$

where $B$ is a Euclidean bounce action.

Second, fluctuations around a background field obey mode equations. A time-dependent electric field, expanding cosmological background, soliton background, or curved spacetime can lead to equations of the form

$$
\ddot u_k(t)+\omega_k(t)^2u_k(t)=0.
$$

The WKB approximation reads

$$
u_k(t)\sim {1\over\sqrt{2W_k(t)}}
\exp\left(-i\int^t W_k(t')dt'\right),
$$

with $W_k$ determined iteratively. Particle production occurs when the adiabatic approximation fails, usually near complex turning points where $\omega_k(t)=0$.

Third, WKB organizes one-loop determinants in semiclassical backgrounds. The determinant is spectral data, and spectral data are often approximated by phase integrals.

Fourth, exact WKB and resurgence make precise the relationship between perturbative fluctuations around a vacuum and nonperturbative tunneling sectors.

## Common confusions

**WKB is not the same as setting $\hbar=0$.** The leading Hamilton–Jacobi equation is classical, but the amplitude, connection formulae, Maslov phases, tunneling exponents, and Stokes jumps are quantum asymptotic data.

**The WKB wavefunction is not valid at a turning point.** The factor $p^{-1/2}$ diverges when $p=0$. One must use Airy matching or a uniform approximation.

**A decaying exponential is not always the whole forbidden-region solution.** In a finite barrier, the growing branch may be needed to satisfy matching at the other side. Throwing it away too early breaks the calculation.

**The $1/2$ in Bohr–Sommerfeld quantization is not arbitrary.** It is the Maslov contribution from turning points. Different boundary conditions or singular endpoints can change it.

**The tunneling exponent is not the full tunneling probability.** It gives the leading exponential scale. Prefactors can matter for quantitative decay rates.

**Exact WKB is not merely “higher-order WKB.”** It studies Borel summation, Stokes automorphisms, and global analytic continuation of WKB series. That is a much sharper object than writing two extra correction terms.

## Exercises

### Exercise 1: Derive the WKB amplitude

Starting from

$$
\psi(x)=A(x)e^{iS(x)/\hbar},
\qquad
\psi''+{p(x)^2\over\hbar^2}\psi=0,
$$

show that the leading transport equation gives $A\propto p^{-1/2}$ when $S'=p$.

<details><summary><strong>Solution</strong></summary>

Substitute the ansatz. The coefficient of $\hbar^{-2}$ gives

$$
(S')^2=p^2.
$$

Choose $S'=p$. The coefficient of $\hbar^{-1}$ gives

$$
2A'S'+AS''=0.
$$

Using $S'=p$ and $S''=p'$,

$$
2A'p+Ap'=0.
$$

Divide by $2Ap$:

$$
{A'\over A}=-{1\over2}{p'\over p}.
$$

Therefore

$$
\log A=-{1\over2}\log p+\text{constant},
$$

so

$$
A={C\over\sqrt p}.
$$

</details>

### Exercise 2: Bohr–Sommerfeld for the harmonic oscillator

Use

$$
\oint p\,dx=2\pi\hbar\left(n+{1\over2}\right)
$$

for the harmonic oscillator $V(x)=m\omega^2x^2/2$ to derive $E_n=\hbar\omega(n+1/2)$.

<details><summary><strong>Solution</strong></summary>

The classical phase-space orbit is an ellipse,

$$
{p^2\over2m}+{1\over2}m\omega^2x^2=E.
$$

Its semiaxes are

$$
p_\text{max}=\sqrt{2mE},
\qquad
x_\text{max}=\sqrt{2E\over m\omega^2}.
$$

The area is

$$
\oint p\,dx=\pi p_\text{max}x_\text{max}
={2\pi E\over\omega}.
$$

Bohr–Sommerfeld gives

$$
{2\pi E\over\omega}=2\pi\hbar\left(n+{1\over2}\right),
$$

so

$$
E_n=\hbar\omega\left(n+{1\over2}\right).
$$

</details>

### Exercise 3: Rectangular barrier exponent

A particle of energy $E$ encounters a rectangular barrier of height $V_0>E$ and width $L$. Use WKB to find the leading tunneling exponent.

<details><summary><strong>Solution</strong></summary>

Inside the barrier,

$$
\kappa=\sqrt{2m(V_0-E)}
$$

is constant. The WKB transmission exponent is

$$
T\sim\exp\left[-{2\over\hbar}\int_0^L \kappa\,dx\right].
$$

Therefore

$$
T\sim\exp\left[-{2L\over\hbar}\sqrt{2m(V_0-E)}\right].
$$

This is only the leading exponential. The exact rectangular-barrier answer has a prefactor that depends on $E$ and $V_0$.

</details>

### Exercise 4: Why WKB fails at a turning point

Let $p(x)^2\approx c(x-a)$ near a simple turning point. Show that the leading validity parameter $\hbar |p'|/|p|^2$ diverges as $x\to a$.

<details><summary><strong>Solution</strong></summary>

If

$$
p(x)^2\approx c(x-a),
$$

then

$$
p(x)\approx c^{1/2}(x-a)^{1/2},
\qquad
p'(x)\approx {1\over2}c^{1/2}(x-a)^{-1/2}.
$$

Thus

$$
\hbar {|p'|\over |p|^2}
\approx
\hbar { {1\over2}|c|^{1/2}|x-a|^{-1/2}\over |c||x-a|}
=
{\hbar\over2|c|^{1/2}}|x-a|^{-3/2}.
$$

This diverges as $x\to a$. The local WKB approximation must be replaced by Airy matching or a uniform approximation near the turning point.

</details>

## References

- C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*.
- F. W. J. Olver, *Asymptotics and Special Functions*.
- R. B. Dingle, *Asymptotic Expansions: Their Derivation and Interpretation*.
- M. V. Berry, work on Stokes phenomena and semiclassical asymptotics.
- S. Coleman, *Aspects of Symmetry*.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- M. Mariño, *Instantons and Large N*.
- M. Shifman, *Advanced Topics in Quantum Field Theory*.
- M. Srednicki, *Quantum Field Theory*.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II.
- M. Schwartz, *Quantum Field Theory and the Standard Model*.

## Version history

- 2026-06-26: First polished draft for the Mathematical Toolkit volume.
