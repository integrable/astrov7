---
title: "Bessel Functions"
description: "Explains Bessel, Hankel, and modified Bessel functions for QFT: radial wave equations, Euclidean Green functions, asymptotics, Wronskians, orthogonality, and boundary-condition choices."
sidebar:
  label: "Bessel Functions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard references on Bessel functions, radial differential equations, Green functions, special functions, asymptotics, and QFT applications, including Watson, Whittaker–Watson, Abramowitz–Stegun, NIST DLMF, Olver, Temme, Bender–Orszag, Morse–Feshbach, Titchmarsh, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, Di Francesco–Mathieu–Sénéchal, and references on AdS/CFT, heat kernels, and scattering theory."
topics:
  - Bessel functions
  - Hankel functions
  - modified Bessel functions
  - radial equation
  - Helmholtz equation
  - Euclidean Green function
  - spherical Bessel functions
  - asymptotic expansion
  - Wronskian
  - boundary conditions
canonicalTopics:
  - bessel-function
  - hankel-function
  - modified-bessel-function
  - radial-equation
  - helmholtz-equation
  - euclidean-green-function
  - spherical-bessel-function
  - asymptotic-expansion
  - wronskian
  - boundary-condition
researchStatus:
  established:
    - "Bessel, Hankel, and modified Bessel functions are classical special functions that solve radial wave, heat, Helmholtz, Klein–Gordon, Schrödinger, and AdS mode equations after separation of variables."
    - "Their power series, Wronskians, recurrence relations, integral representations, asymptotics, and orthogonality/completeness relations are standard and convention-stable."
  active:
    - "Modern QFT uses Bessel technology in AdS/CFT, thermal field theory, heat kernels, spectral densities, conformal blocks in special kinematics, scattering theory, large-order asymptotics, and exact/nonperturbative calculations."
---

## Summary

Bessel functions are the functions forced on you by radial problems. Whenever a wave equation, heat equation, Helmholtz equation, Klein–Gordon equation, or Schrödinger equation is separated in a rotationally symmetric setting, the radial mode usually satisfies a Bessel equation or one of its close relatives.

The standard Bessel equation is

$$
z^2 y''+z y'+(z^2-\nu^2)y=0.
$$

Its main solutions are

$$
J_\nu(z),\qquad Y_\nu(z),\qquad
H_\nu^{(1)}(z)=J_\nu(z)+iY_\nu(z),\qquad
H_\nu^{(2)}(z)=J_\nu(z)-iY_\nu(z).
$$

The modified Bessel equation is

$$
z^2 y''+z y'-(z^2+\nu^2)y=0,
$$

with standard solutions

$$
I_\nu(z),
\qquad
K_\nu(z).
$$

In QFT, these names are not decorative. They encode boundary conditions: regular at the origin, singular at the origin, outgoing, incoming, growing in Euclidean distance, or decaying in Euclidean distance.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing how radial separation leads to Bessel, Hankel, and modified Bessel functions, with boundary conditions and QFT applications.](/figures/math-toolkit/bessel-function-radial-flow.svg)

<figcaption>

Bessel functions are a boundary-condition dictionary for radial equations. $J_\nu$ is the regular oscillatory solution near the origin, $Y_\nu$ is the independent singular oscillatory solution, $H_\nu^{(1,2)}$ are outgoing/incoming oscillatory solutions, and $K_\nu$ is the Euclidean-decaying solution. The same dictionary appears in Green functions, partial waves, heat kernels, AdS radial modes, and threshold analysis.

</figcaption>
</figure>

## Prerequisites

You should know [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Partial Differential Equations](/math-toolkit/differential-equations-green-functions/partial-differential-equations/), [Elliptic, Hyperbolic, and Parabolic Equations](/math-toolkit/differential-equations-green-functions/elliptic-hyperbolic-parabolic/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Heat Equation and Heat Kernel](/math-toolkit/differential-equations-green-functions/heat-equation-and-heat-kernel/), [Wave Equation](/math-toolkit/differential-equations-green-functions/wave-equation/), [Schrödinger Operators](/math-toolkit/differential-equations-green-functions/schrodinger-operators/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), and [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/).

The default convention is the site convention: mostly-minus Lorentzian metric when spacetime is Lorentzian, $c=\hbar=1$, and plane waves $e^{-ip\cdot x}$. On this page, the cleanest formulae are written for Euclidean radial distance or for time dependence $e^{-i\omega t}$ when discussing incoming and outgoing waves.

## The radial origin of the Bessel equation

The fastest way to recognize Bessel functions is to separate a rotationally invariant equation. In $d$ Euclidean dimensions,

$$
\nabla^2
=\frac{\partial^2}{\partial r^2}
+\frac{d-1}{r}\frac{\partial}{\partial r}
+\frac{1}{r^2}\Delta_{S^{d-1}}.
$$

Hyperspherical harmonics obey

$$
\Delta_{S^{d-1}}Y_{\ell a}(\Omega)
=-\ell(\ell+d-2)Y_{\ell a}(\Omega),
\qquad \ell=0,1,2,\dots.
$$

For a Helmholtz mode

$$
(\nabla^2+k^2)\psi=0,
\qquad
\psi(r,\Omega)=R_\ell(r)Y_{\ell a}(\Omega),
$$

the radial function satisfies

$$
R_\ell''+\frac{d-1}{r}R_\ell'
+\left(k^2-\frac{\ell(\ell+d-2)}{r^2}\right)R_\ell=0.
$$

Set

$$
R_\ell(r)=r^{-\frac{d-2}{2}}u_\ell(kr),
\qquad
z=kr.
$$

Then $u_\ell(z)$ obeys

$$
z^2u_\ell''+zu_\ell'
+\left(z^2-\nu^2\right)u_\ell=0,
\qquad
\nu=\ell+\frac{d-2}{2}.
$$

Thus the order $\nu$ is not mysterious. It is the angular momentum shifted by the radial measure.

For a Euclidean massive equation

$$
(-\nabla^2+m^2)G(x)=\delta^{(d)}(x),
$$

the radial solutions away from the source are modified Bessel functions, because the equation contains $m^2$ rather than $-k^2$ after analytic continuation.

## The main solutions

The solution regular at the origin is $J_\nu(z)$. Its series normalization is

$$
J_\nu(z)
=\sum_{n=0}^{\infty}
\frac{(-1)^n}{n!\,\Gamma(n+\nu+1)}
\left(\frac z2\right)^{2n+\nu}.
$$

For $\operatorname{Re}\nu>-1$, this gives

$$
J_\nu(z)\sim \frac{1}{\Gamma(\nu+1)}\left(\frac z2\right)^\nu,
\qquad z\to0.
$$

For noninteger $\nu$, a second independent solution is $J_{-\nu}(z)$. The conventional second solution is instead

$$
Y_\nu(z)=\frac{J_\nu(z)\cos\pi\nu-J_{-\nu}(z)}{\sin\pi\nu},
\qquad \nu\notin\mathbb Z,
$$

continued to integer $\nu$ by a limit. For integer order, $Y_n$ contains logarithms near $z=0$. This logarithm is not a bug. It is the usual repeated-exponent phenomenon from the Frobenius method.

The Hankel functions are

$$
H_\nu^{(1)}(z)=J_\nu(z)+iY_\nu(z),
\qquad
H_\nu^{(2)}(z)=J_\nu(z)-iY_\nu(z).
$$

For large positive real $z$,

$$
H_\nu^{(1)}(z)
\sim
\sqrt{\frac{2}{\pi z}}
\exp\!\left[i\left(z-\frac{\pi\nu}{2}-\frac\pi4\right)\right],
$$

and

$$
H_\nu^{(2)}(z)
\sim
\sqrt{\frac{2}{\pi z}}
\exp\!\left[-i\left(z-\frac{\pi\nu}{2}-\frac\pi4\right)\right].
$$

With time dependence $e^{-i\omega t}$, $H_\nu^{(1)}(kr)$ is the outgoing radial-wave choice and $H_\nu^{(2)}(kr)$ is the incoming choice. If you use $e^{+i\omega t}$, these words swap. Physics did not change; your convention did.

## Modified Bessel functions

The modified Bessel functions solve

$$
z^2y''+zy'-(z^2+\nu^2)y=0.
$$

They arise from analytic continuation $z\mapsto iz$, or directly from Euclidean equations. A useful convention is

$$
I_\nu(z)=i^{-\nu}J_\nu(iz),
$$

with a branch choice for $i^{-\nu}$. The function $I_\nu$ is regular at $z=0$:

$$
I_\nu(z)
=\sum_{n=0}^{\infty}
\frac{1}{n!\,\Gamma(n+\nu+1)}
\left(\frac z2\right)^{2n+\nu}.
$$

For large positive $z$,

$$
I_\nu(z)\sim \frac{e^z}{\sqrt{2\pi z}},
\qquad
K_\nu(z)\sim \sqrt{\frac{\pi}{2z}}e^{-z}.
$$

Thus $K_\nu$ is the decaying Euclidean solution. This is why it appears in massive Euclidean propagators. Near $z=0$, for $\operatorname{Re}\nu>0$,

$$
K_\nu(z)\sim \frac12\Gamma(\nu)\left(\frac z2\right)^{-\nu}.
$$

So $K_\nu$ is usually singular at the origin. It is selected by decay at infinity, not by regularity at the origin.

## Boundary-condition dictionary

A radial second-order equation has two local solutions. The notation tells you which two are convenient for the physical problem.

| Function | Equation type | Useful behavior | Typical QFT role |
|---|---|---|---|
| $J_\nu(z)$ | Oscillatory | Regular at $z=0$ for $\operatorname{Re}\nu>-1$ | Regular radial modes, partial-wave bases |
| $Y_\nu(z)$ | Oscillatory | Singular at $z=0$ | Independent solution, irregular radial modes |
| $H_\nu^{(1)}(z)$ | Oscillatory | Outgoing for $e^{-i\omega t}$ | Retarded/outgoing Green functions, scattering |
| $H_\nu^{(2)}(z)$ | Oscillatory | Incoming for $e^{-i\omega t}$ | Incoming waves, advanced-type choices |
| $I_\nu(z)$ | Euclidean/modified | Regular near $0$, grows as $e^z$ | Interior Euclidean modes |
| $K_\nu(z)$ | Euclidean/modified | Decays as $e^{-z}$, usually singular near $0$ | Massive Euclidean propagators, exterior modes |

The same equation may be written with $J_\nu$, $H_\nu^{(1)}$, or $K_\nu$ depending on whether you are imposing regularity, radiation, or Euclidean decay. Never choose a named Bessel function without also knowing the boundary condition it encodes.

## Wronskians and Green functions

The Wronskian is what fixes Green-function normalization. For two solutions of the Bessel equation,

$$
W[f,g](z)=f(z)g'(z)-f'(z)g(z)
$$

obeys

$$
W'(z)+\frac1z W(z)=0,
$$

so

$$
W(z)=\frac{C}{z}.
$$

The standard normalizations are

$$
W[J_\nu,Y_\nu]=\frac{2}{\pi z},
$$

and

$$
W[H_\nu^{(1)},H_\nu^{(2)}]=-\frac{4i}{\pi z}.
$$

For modified Bessel functions,

$$
W[I_\nu,K_\nu]=-\frac1z.
$$

These identities are tiny but mighty. They turn matching conditions across a delta-function source into the coefficient of a propagator.

## Euclidean massive Green function

The standard Euclidean massive scalar Green function in $d$ dimensions is

$$
G_m(x)
=\int\frac{d^d p}{(2\pi)^d}
\frac{e^{ip\cdot x}}{p^2+m^2}.
$$

For $r=|x|>0$,

$$
G_m(r)
=\frac{m^\nu}{(2\pi)^{d/2}r^\nu}K_\nu(mr),
\qquad
\nu=\frac d2-1.
$$

For $d=3$, using

$$
K_{1/2}(z)=\sqrt{\frac{\pi}{2z}}e^{-z},
$$

this becomes the familiar Yukawa kernel

$$
G_m(r)=\frac{e^{-mr}}{4\pi r}.
$$

For $d=4$,

$$
G_m(r)=\frac{m}{4\pi^2r}K_1(mr).
$$

At small distance, the singularity of $K_\nu$ reproduces the short-distance singularity of the massless Green function. For $d>2$,

$$
G_0(r)=\frac{\Gamma\!\left(\frac d2-1\right)}{4\pi^{d/2}r^{d-2}}.
$$

This is one of the cleanest examples of how a special function packages both UV behavior and IR decay.

## Outgoing Helmholtz Green function

The outgoing Green function for the Helmholtz operator in $d$ spatial dimensions can be written as

$$
G_k^{(+)}(r)
=\frac{i}{4}\left(\frac{k}{2\pi r}\right)^\nu
H_\nu^{(1)}(kr),
\qquad
\nu=\frac d2-1,
$$

with the convention

$$
(\nabla^2+k^2)G_k^{(+)}(x)=-\delta^{(d)}(x).
$$

In $d=3$, this reduces to

$$
G_k^{(+)}(r)=\frac{e^{ikr}}{4\pi r}.
$$

The superscript $(+)$ is a boundary condition: outgoing radiation. It is not the same thing as a positive-frequency projection, though the two are related once a time convention and an $i0$ prescription are chosen.

## Orthogonality and the radial transform

Bessel functions form the radial analogue of Fourier modes. For $k,k'>0$,

$$
\int_0^\infty dr\,r\,J_\nu(kr)J_\nu(k'r)
=\frac{\delta(k-k')}{k},
$$

and the closure relation is

$$
\int_0^\infty dk\,k\,J_\nu(kr)J_\nu(kr')
=\frac{\delta(r-r')}{r}.
$$

These formulas are best understood distributionally. They say that the Hankel transform

$$
\widetilde f(k)=\int_0^\infty dr\,r\,J_\nu(kr)f(r)
$$

has inverse

$$
f(r)=\int_0^\infty dk\,k\,J_\nu(kr)\widetilde f(k),
$$

under suitable hypotheses. In $d$-dimensional radial Fourier transforms, extra powers of $r$ are absorbed by the shift $\nu=\ell+(d-2)/2$ and by the radial measure $r^{d-1}dr$.

## Recurrence relations

The basic recurrences are

$$
J_{\nu-1}(z)+J_{\nu+1}(z)=\frac{2\nu}{z}J_\nu(z),
$$

and

$$
J_{\nu-1}(z)-J_{\nu+1}(z)=2J_\nu'(z).
$$

Equivalently,

$$
\frac{d}{dz}\left(z^\nu J_\nu(z)\right)=z^\nu J_{\nu-1}(z),
$$

and

$$
\frac{d}{dz}\left(z^{-\nu}J_\nu(z)\right)=-z^{-\nu}J_{\nu+1}(z).
$$

These identities are especially useful when differentiating radial Green functions. The modified functions obey parallel identities with signs adjusted by analytic continuation, for example

$$
K_\nu'(z)=-K_{\nu-1}(z)-\frac{\nu}{z}K_\nu(z)
=-K_{\nu+1}(z)+\frac{\nu}{z}K_\nu(z).
$$

## Spherical Bessel functions

In three spatial dimensions, half-integer Bessel functions are so common that they get their own notation:

$$
j_\ell(z)=\sqrt{\frac{\pi}{2z}}J_{\ell+1/2}(z),
$$

and

$$
y_\ell(z)=\sqrt{\frac{\pi}{2z}}Y_{\ell+1/2}(z).
$$

The spherical Hankel functions are

$$
h_\ell^{(1)}(z)=j_\ell(z)+iy_\ell(z),
\qquad
h_\ell^{(2)}(z)=j_\ell(z)-iy_\ell(z).
$$

The first two spherical Bessel functions are

$$
j_0(z)=\frac{\sin z}{z},
\qquad
j_1(z)=\frac{\sin z}{z^2}-\frac{\cos z}{z}.
$$

They are the radial functions in the three-dimensional partial-wave expansion of a plane wave.

## Large-argument asymptotics

For fixed $\nu$ and large positive real $z$,

$$
J_\nu(z)\sim
\sqrt{\frac{2}{\pi z}}
\cos\!\left(z-\frac{\pi\nu}{2}-\frac\pi4\right),
$$

and

$$
Y_\nu(z)\sim
\sqrt{\frac{2}{\pi z}}
\sin\!\left(z-\frac{\pi\nu}{2}-\frac\pi4\right).
$$

These asymptotics are why $J$ and $Y$ are standing-wave combinations, while $H^{(1)}$ and $H^{(2)}$ are traveling-wave combinations.

For QFT applications, there are two caveats. First, asymptotic formulae depend on the sector of the complex $z$-plane; Stokes phenomena matter when $z$ is complex. Second, large order $\nu$ with $z/\nu$ fixed is a different limit from fixed $\nu$ with large $z$. Partial-wave sums, large angular momentum, and WKB approximations often require uniform asymptotic expansions rather than the elementary large-$z$ formulas above.

## Where Bessel functions appear in QFT

Bessel functions appear in free-field propagators because Fourier transforms of rotationally invariant denominators reduce to radial integrals. They appear in scattering because angular momentum decomposition separates the radial Helmholtz equation. They appear in finite-temperature and finite-volume calculations because cylindrical or spherical geometry imposes radial modes. They appear in AdS/CFT because scalar wave equations in Poincaré AdS reduce near the boundary to modified Bessel equations. They appear in heat kernels and determinants because radial spectral decompositions use Bessel zeros and Bessel completeness.

A useful slogan:

$$
\text{Fourier modes in a box are sines and cosines; radial Fourier modes are Bessel functions.}
$$

That slogan is not a proof, but it keeps the zoo in order.

## Common pitfalls

**Confusing ordinary and modified Bessel functions.** Ordinary Bessel functions are oscillatory for large positive argument. Modified Bessel functions grow or decay exponentially. If your Euclidean massive propagator oscillates at large distance, something has gone sideways.

**Forgetting the radial measure.** The radial measure in $d$ dimensions is $r^{d-1}dr$, not $dr$. The power $r^{-(d-2)/2}$ in the radial solution is not arbitrary; it compensates part of this measure.

**Using $K_\nu$ as if it were regular at the origin.** Except in special cases, $K_\nu$ is singular near zero. It is usually chosen because it decays at infinity.

**Treating outgoing and incoming as convention-free.** With time dependence $e^{-i\omega t}$, $H_\nu^{(1)}$ is outgoing. With $e^{+i\omega t}$, the labels reverse.

**Ignoring integer-order limits.** Formulae involving $J_\nu$ and $J_{-\nu}$ often have apparent singularities at integer $\nu$. The correct $Y_n$ is obtained by taking the limit, and logarithms appear.

**Expanding outside the valid asymptotic regime.** Fixed-order large-$z$ asymptotics are not the same as large-order asymptotics. Partial-wave tails are especially unforgiving here.

## Exercises

### Exercise 1: derive the radial Bessel order

Starting from

$$
R''+\frac{d-1}{r}R'
+\left(k^2-\frac{\ell(\ell+d-2)}{r^2}\right)R=0,
$$

show that $R(r)=r^{-(d-2)/2}u(kr)$ gives the Bessel equation with order

$$
\nu=\ell+\frac{d-2}{2}.
$$

<details><summary><strong>Solution</strong></summary>

Let $a=(d-2)/2$ and $z=kr$, so $R=r^{-a}u(z)$. Differentiate:

$$
R'=r^{-a}\left(ku'-\frac{a}{r}u\right),
$$

and

$$
R''=r^{-a}\left(k^2u''-\frac{2ak}{r}u'+\frac{a(a+1)}{r^2}u\right).
$$

Substitute into the radial equation. The coefficient of $u'$ becomes

$$
-2a+(d-1)=1,
$$

so the $u'$ term is $k u'/r$. Multiplying by $r^2$ and using $z=kr$ gives

$$
z^2u''+zu'+\left[z^2-a(a+1)+(d-1)a-\ell(\ell+d-2)\right]u=0.
$$

Since

$$
-a(a+1)+(d-1)a=a^2,
$$

the coefficient is

$$
z^2-\left[\ell(\ell+d-2)+a^2\right]
=z^2-\left(\ell+a\right)^2.
$$

Thus

$$
\nu=\ell+a=\ell+\frac{d-2}{2}.
$$

</details>

### Exercise 2: fix the Wronskian form

Show that if $f$ and $g$ solve the Bessel equation, then their Wronskian obeys $W=C/z$.

<details><summary><strong>Solution</strong></summary>

Write the Bessel equation in normalized form:

$$
y''+\frac1z y'+\left(1-\frac{\nu^2}{z^2}\right)y=0.
$$

For any second-order equation $y''+p(z)y'+q(z)y=0$, the Wronskian satisfies Abel's identity

$$
W'=-p(z)W.
$$

Here $p(z)=1/z$, so

$$
W'=-\frac1z W.
$$

Therefore

$$
\frac{d}{dz}\log W=-\frac1z,
$$

and hence

$$
W=\frac{C}{z}.
$$

The constant $C$ depends on the normalization of the two chosen solutions. For $J_\nu$ and $Y_\nu$, the standard normalization gives $C=2/\pi$.

</details>

### Exercise 3: recover the three-dimensional Yukawa kernel

Use

$$
G_m(r)
=\frac{m^\nu}{(2\pi)^{d/2}r^\nu}K_\nu(mr),
\qquad
\nu=\frac d2-1,
$$

and

$$
K_{1/2}(z)=\sqrt{\frac{\pi}{2z}}e^{-z}
$$

to show that in $d=3$,

$$
G_m(r)=\frac{e^{-mr}}{4\pi r}.
$$

<details><summary><strong>Solution</strong></summary>

For $d=3$, $\nu=1/2$. Therefore

$$
G_m(r)=\frac{m^{1/2}}{(2\pi)^{3/2}r^{1/2}}K_{1/2}(mr).
$$

Substitute the half-integer formula:

$$
G_m(r)=\frac{m^{1/2}}{(2\pi)^{3/2}r^{1/2}}
\sqrt{\frac{\pi}{2mr}}e^{-mr}.
$$

The factor $m^{1/2}$ cancels $m^{-1/2}$, and

$$
\frac{\sqrt\pi}{\sqrt2(2\pi)^{3/2}}=\frac1{4\pi}.
$$

Thus

$$
G_m(r)=\frac{e^{-mr}}{4\pi r}.
$$

</details>

### Exercise 4: outgoing wave in three dimensions

Using

$$
H_{1/2}^{(1)}(z)=-i\sqrt{\frac{2}{\pi z}}e^{iz},
$$

show that the $d=3$ outgoing Helmholtz Green function is $e^{ikr}/(4\pi r)$.

<details><summary><strong>Solution</strong></summary>

For $d=3$, $\nu=1/2$, so

$$
G_k^{(+)}(r)=\frac{i}{4}\left(\frac{k}{2\pi r}\right)^{1/2}H_{1/2}^{(1)}(kr).
$$

Substitute the half-integer Hankel function:

$$
G_k^{(+)}(r)
=\frac{i}{4}\left(\frac{k}{2\pi r}\right)^{1/2}
\left[-i\sqrt{\frac{2}{\pi kr}}e^{ikr}\right].
$$

The factors $i$ and $-i$ multiply to $1$, and the square roots give $1/(\pi r)$. Therefore

$$
G_k^{(+)}(r)=\frac{e^{ikr}}{4\pi r}.
$$

</details>

## References

- G. N. Watson, *A Treatise on the Theory of Bessel Functions*. Classic deep reference.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Classical source for special-function and asymptotic methods.
- M. Abramowitz and I. A. Stegun, *Handbook of Mathematical Functions*. Useful for identities and normalization checks.
- NIST Digital Library of Mathematical Functions, chapters on Bessel functions and asymptotics. Reliable modern formula reference.
- F. W. J. Olver et al., *NIST Handbook of Mathematical Functions*. Modern handbook version of the DLMF.
- C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*. Excellent for asymptotics and differential equations.
- P. M. Morse and H. Feshbach, *Methods of Theoretical Physics*. Useful for boundary-value and Green-function applications.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for field-theory applications of special functions and asymptotics.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Useful for propagators, analytic continuation, and scattering contexts.
- M. Srednicki, *Quantum Field Theory*. Useful for practical QFT normalization and propagator conventions.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for perturbative-QFT applications and normalization checks.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*. Useful for special functions in CFT and conformal blocks.

## Version history

- 2026-06-26: Initial polished draft.
