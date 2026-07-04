---
title: "Residues and Contours"
description: "Explains contour integration and the residue theorem for QFT, including orientations, contour deformation, residues at poles, residues at infinity, Fourier-transform contours, propagator prescriptions, Matsubara sums, and common sign mistakes."
sidebar:
  label: "Residues and Contours"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard references on complex analysis, contour integration, distributional boundary values, thermal sums, propagators, and scattering theory, including Ahlfors, Stein–Shakarchi, Titchmarsh, Whittaker–Watson, Arfken–Weber–Harris, Bender–Orszag, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Kapusta–Gale, Le Bellac, and mathematical-physics treatments of Cauchy integrals."
topics:
  - contour integration
  - residues
  - residue theorem
  - contour deformation
  - pole prescriptions
  - Fourier transforms
  - propagators
  - Wick rotation
  - Matsubara sums
  - residues at infinity
  - Jordan lemma
  - QFT contour methods
canonicalTopics:
  - contour-integration
  - residue
  - residue-theorem
  - contour-deformation
  - pole-prescription
  - fourier-transform
  - propagator
  - wick-rotation
  - matsubara-sum
  - residue-at-infinity
  - jordan-lemma
  - qft-contour-method
researchStatus:
  established:
    - "Contour deformation and the residue theorem are standard tools for evaluating meromorphic integrals, inverse Fourier transforms, propagators, thermal sums, and many elementary loop-integral reductions."
  active:
    - "Modern applications continue in amplitudes, generalized unitarity, Landau singularities, resurgence, complex saddles, Lefschetz thimbles, real-time thermal field theory, and analytic bootstrap methods."
---

## Summary

Contour integration is the technology that turns analytic structure into numbers. The residue theorem says that if $f$ is meromorphic inside a positively oriented contour $C$, then

$$
\oint_C dz\,f(z)=2\pi i\sum_{a\in\operatorname{Int}(C)}\operatorname{Res}_{z=a}f.
$$

The theorem is compact, but its QFT consequences are enormous. It computes inverse Fourier transforms, picks out causal prescriptions, evaluates Matsubara sums, relates discontinuities to spectral densities, and turns pole data into propagating degrees of freedom.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Contour diagram showing deformation of a contour around poles, a cut, and a large arc, with the residue theorem relating the contour integral to enclosed singularities.](/figures/math-toolkit/residue-contour-deformation.svg)

<figcaption>

A contour may be deformed freely through holomorphic regions. The integral changes only when the deformation crosses singularities or when arcs at infinity contribute. Residues are the local data carried by isolated poles.

</figcaption>
</figure>

The short practical rule is

$$
\text{choose a contour} \;\longrightarrow\; \text{check decay} \;\longrightarrow\; \text{count enclosed singularities} \;\longrightarrow\; \text{include orientation signs}.
$$

That last arrow is where half the wrong signs in the universe appear. Possibly more. The universe has poor bookkeeping.

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/).

We use the site Fourier convention

$$
f(t)=\int\frac{d\omega}{2\pi}\,e^{-i\omega t}\,\widetilde f(\omega),
\qquad
\widetilde f(\omega)=\int dt\,e^{i\omega t}f(t).
$$

This convention decides which half-plane to close in when $t$ has a sign.

## Contours and orientation

A contour is an oriented path in the complex plane. If $\gamma:[a,b]\to\mathbb C$ is piecewise smooth, then

$$
\int_\gamma dz\,f(z)=\int_a^b ds\,\gamma'(s)f(\gamma(s)).
$$

A simple closed contour is **positively oriented** if it runs counterclockwise. With positive orientation, the residue theorem has the sign

$$
\oint_C dz\,f(z)=2\pi i\sum \operatorname{Res}f.
$$

If a closed contour is clockwise, the sign flips:

$$
\oint_C dz\,f(z)=-2\pi i\sum \operatorname{Res}f.
$$

This matters for Fourier transforms. With $e^{-i\omega t}$, for $t>0$ one closes in the lower half-plane, and the resulting large semicircle is clockwise. Therefore the real-axis integral equals minus $2\pi i$ times the residues in the lower half-plane, assuming the arc vanishes.

## Cauchy’s theorem as contour deformation

If $f$ is holomorphic in the region swept between two contours $C_1$ and $C_2$, and the endpoints agree or the contours are closed and homologous, then

$$
\int_{C_1}dz\,f(z)=\int_{C_2}dz\,f(z).
$$

This is the practical form of Cauchy’s theorem. You may slide a contour around, stretch it, shrink it, and bend it, as long as it does not cross a singularity and boundary terms at infinity are under control.

The words “under control” are doing real work. A contour deformation can fail because:

| Obstruction | What goes wrong |
|---|---|
| pole | crossing picks up a residue |
| branch cut | contour must track a discontinuity |
| essential singularity | local behavior may be wild |
| large arc | integral at infinity may not vanish |
| pinch | singularities trap the contour |
| Stokes line | saddle contributions jump across sectors |

In perturbative QFT, a pinch singularity is especially important. If singularities approach a contour from opposite sides, no small deformation avoids both. This is the analytic mechanism behind thresholds and on-shell intermediate states.

## Residues at poles

If $f$ has a simple pole at $z=a$, then

$$
f(z)=\frac{c_{-1}}{z-a}+c_0+c_1(z-a)+\cdots,
$$

and

$$
\operatorname{Res}_{z=a}f=c_{-1}.
$$

For a simple pole written as a quotient,

$$
f(z)=\frac{g(z)}{h(z)},
\qquad h(a)=0,
\qquad h'(a)\neq0,
$$

with $g$ holomorphic at $a$, the residue is

$$
\operatorname{Res}_{z=a}\frac{g(z)}{h(z)}=\frac{g(a)}{h'(a)}.
$$

For a pole of order $m$,

$$
\operatorname{Res}_{z=a}f
=\frac{1}{(m-1)!}\lim_{z\to a}\frac{d^{m-1}}{dz^{m-1}}\left[(z-a)^m f(z)\right].
$$

In practice, most first-pass QFT residues are simple poles. Higher-order poles appear in differentiated propagators, repeated denominators, degenerate limits, and some contour representations.

## The residue at infinity

Sometimes the easiest singularity is the one at infinity. Define

$$
\operatorname{Res}_{z=\infty}f(z)
=-\operatorname{Res}_{w=0}\left[\frac{1}{w^2}f\left(\frac1w\right)\right].
$$

Equivalently, if the Laurent expansion at large $z$ is

$$
f(z)=\cdots+\frac{a_{-1}}{z}+\frac{a_{-2}}{z^2}+\cdots,
$$

then

$$
\operatorname{Res}_{z=\infty}f=-a_{-1}.
$$

On the Riemann sphere, the sum of all residues vanishes:

$$
\sum_{a\in\mathbb C}\operatorname{Res}_{z=a}f+
\operatorname{Res}_{z=\infty}f=0.
$$

This is useful for rational functions and for checking signs. If your finite residues do not match the behavior at infinity, something is off.

## Real integrals from contours

A standard contour computation begins with a real integral

$$
I=\int_{-\infty}^{\infty}dx\,R(x),
$$

where $R(z)$ is rational and decays sufficiently fast at infinity. If $R$ has no poles on the real axis and decays faster than $1/z$, then closing the contour in the upper half-plane gives

$$
I=2\pi i\sum_{\operatorname{Im}a>0}\operatorname{Res}_{z=a}R(z).
$$

For example,

$$
\int_{-\infty}^{\infty}\frac{dx}{x^2+a^2}
=2\pi i\operatorname{Res}_{z=ia}\frac{1}{z^2+a^2}
=2\pi i\frac{1}{2ia}
=\frac{\pi}{a},
$$

for $a>0$.

This example is simple enough to do in freshman calculus. The point is the method: real integrals become algebraic sums over complex singularities. Loop integrals and inverse transforms are elaborate descendants of this trick.

## Fourier contours and causal prescriptions

With the site convention

$$
f(t)=\int\frac{d\omega}{2\pi}\,e^{-i\omega t}\,\widetilde f(\omega),
$$

the exponential decides where to close:

$$
e^{-i(x+iy)t}=e^{-ixt}e^{yt}.
$$

For $t>0$, the lower half-plane $y<0$ gives decay. For $t<0$, the upper half-plane gives decay.

Consider

$$
I(t)=\int_{-\infty}^{\infty}\frac{d\omega}{2\pi}\,\frac{e^{-i\omega t}}{\omega-\omega_0+i0}.
$$

The pole is at

$$
\omega=\omega_0-i0,
$$

just below the real axis. For $t>0$, close below. The contour is clockwise, so

$$
I(t)=-i e^{-i\omega_0t}.
$$

For $t<0$, close above and enclose no pole. Therefore

$$
\int\frac{d\omega}{2\pi}\,\frac{e^{-i\omega t}}{\omega-\omega_0+i0}
=-i\theta(t)e^{-i\omega_0t}.
$$

This is the retarded-looking boundary-value identity in contour form. The infinitesimal $+i0$ in the denominator moved the pole below the contour and produced the step function.

Similarly,

$$
\int\frac{d\omega}{2\pi}\,\frac{e^{-i\omega t}}{\omega-\omega_0-i0}
=i\theta(-t)e^{-i\omega_0t}.
$$

The sign of $i0$ is not cosmetic. It is time ordering encoded as analytic geometry.

## Scalar Feynman propagator in one line

For fixed spatial momentum, define

$$
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The momentum-space scalar Feynman propagator is

$$
\frac{i}{(p^0)^2-E_{\mathbf p}^2+i\epsilon}.
$$

The poles are placed as

$$
p^0=E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}+i0.
$$

The time-dependent propagator is

$$
D_F(t,\mathbf p)=\int\frac{dp^0}{2\pi}\,
\frac{i e^{-ip^0 t}}{(p^0)^2-E_{\mathbf p}^2+i\epsilon}.
$$

For $t>0$, close below and enclose $p^0=E_{\mathbf p}-i0$. Because the contour is clockwise,

$$
D_F(t,\mathbf p)=\frac{1}{2E_{\mathbf p}}e^{-iE_{\mathbf p}t}.
$$

For $t<0$, close above and enclose $p^0=-E_{\mathbf p}+i0$, giving

$$
D_F(t,\mathbf p)=\frac{1}{2E_{\mathbf p}}e^{iE_{\mathbf p}t}.
$$

Thus

$$
D_F(t,\mathbf p)=\frac{1}{2E_{\mathbf p}}
\left[\theta(t)e^{-iE_{\mathbf p}t}+\theta(-t)e^{iE_{\mathbf p}t}\right].
$$

This is a perfect example of the analytic story. Positive-frequency propagation forward in time and negative-frequency propagation backward in time are not added by hand; they follow from the pole placement.

## Poles on the contour and principal values

If a pole lies on the integration contour, the contour prescription must say how to avoid it. The distribution identities are

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x),
$$

and

$$
\frac{1}{x-i0}=\operatorname{PV}\frac{1}{x}+i\pi\delta(x).
$$

Graphically, the $i0$ tells the contour whether to pass above or below the pole. Algebraically, it splits the answer into a principal-value part and a delta-function part.

For a smooth test function $\varphi$, this means

$$
\int dx\,\frac{\varphi(x)}{x+i0}
=\operatorname{PV}\int dx\,\frac{\varphi(x)}{x}-i\pi\varphi(0).
$$

This is the clean bridge between complex analysis and distributions.

## Branch cuts and keyhole contours

Not all singularities are isolated poles. A function such as

$$
\log z
$$

or

$$
\sqrt{z-a}
$$

requires a branch choice. A contour surrounding a branch cut usually converts an integral into a discontinuity integral. If $F$ has a cut along the real interval $[a,\infty)$, then a contour that wraps the cut gives schematically

$$
\oint dz\,F(z)
=\int_a^\infty dx\,\left[F(x+i0)-F(x-i0)\right]
=\int_a^\infty dx\,\operatorname{Disc}F(x),
$$

up to orientation conventions and possible endpoint circles.

This is the contour picture behind spectral representations. Poles give discrete residues; cuts give integrals over discontinuities. Bound states are isolated singularities, continua are cuts. This is why the analytic structure of a propagator often reads like a particle spectrum.

## Wick rotation as contour rotation

A Wick rotation is a contour deformation in a complex energy plane. In a typical loop integral, one rotates

$$
p^0=i p_E^0
$$

or an equivalent convention, depending on the metric and Fourier choices. The legitimacy of this move depends on whether the contour can be rotated without crossing poles and whether the arcs at infinity vanish.

For a Feynman denominator

$$
(p^0)^2-E_{\mathbf p}^2+i\epsilon,
$$

the pole placement is exactly what makes the rotation possible in the standard vacuum contour. If singularities pinch the contour, Wick rotation fails or must be modified. At finite temperature, finite density, in real-time nonequilibrium settings, or around nontrivial backgrounds, this caveat stops being academic.

The safe phrasing is: Wick rotation is allowed when the relevant contour deformation is allowed. The slogan “set $t=-i\tau$” is convenient only after the analytic work has been done.

## Matsubara sums by residues

Thermal sums are another place residues earn their keep. For bosonic Matsubara frequencies

$$
\omega_n=2\pi nT,
$$

one often needs sums of the form

$$
T\sum_{n\in\mathbb Z} f(i\omega_n).
$$

The Bose–Einstein function

$$
n_B(z)=\frac{1}{e^{\beta z}-1}
$$

has simple poles at

$$
z=i\omega_n
$$

with residue $T$. Therefore an appropriate contour integral of $f(z)n_B(z)$ converts the Matsubara sum into residues of $f$ weighted by thermal occupation factors. The precise sign depends on the contour convention, but the mechanism is simple:

$$
\text{Matsubara poles of } n_B
\quad\Longleftrightarrow\quad
\text{thermal frequency sum}.
$$

For fermions, one uses

$$
n_F(z)=\frac{1}{e^{\beta z}+1},
$$

whose poles sit at

$$
z=i(2n+1)\pi T.
$$

This residue viewpoint is often the fastest way to understand why thermal correlators have different analytic structures from zero-temperature correlators.

## Arc estimates and Jordan’s lemma

Contour methods often say “the arc at infinity vanishes.” Do not let that sentence become ceremonial. A large semicircle $z=Re^{i\theta}$ contributes roughly

$$
\int_{\text{arc}} dz\, f(z)e^{-izt}.
$$

For $t>0$, the lower half-plane gives exponential decay because $e^{-izt}=e^{-ixt}e^{yt}$ and $y<0$. But the rest of the integrand must not grow too quickly. Jordan’s lemma is one standard sufficient condition for integrals of this type.

In QFT, arc estimates are the difference between a valid contour argument and a vibes-based sign convention. Dispersion relations, Wick rotations, and retarded/advanced transforms all require assumptions about large complex energies.

## Common pitfalls

**Forgetting clockwise signs.** Closing below for $t>0$ with $e^{-i\omega t}$ gives a clockwise contour. The real-axis integral is then $-2\pi i$ times lower-half-plane residues if the arc vanishes.

**Ignoring the Fourier convention.** If the transform uses $e^{+i\omega t}$ instead, the closing rules reverse. Always check the exponential.

**Treating $i\epsilon$ as infinitesimal algebra.** The $i\epsilon$ is a boundary-value prescription. It tells you which singularities are above or below the contour.

**Crossing a branch cut as if nothing happened.** Cuts encode discontinuities. A deformed contour crossing a cut must include the jump between sheets.

**Dropping arcs without checking decay.** Large arcs vanish under conditions. Those conditions can fail in dispersion relations, thermal problems, and nonlocal effective actions.

**Confusing Euclidean poles with Lorentzian poles.** Euclidean denominators and Lorentzian Feynman denominators live on different contours. Translate by contour deformation, not by blind sign replacement.

## Worked example: a causal pole

Evaluate

$$
I(t)=\int\frac{d\omega}{2\pi}\,
\frac{e^{-i\omega t}}{\omega+i0}.
$$

The pole is just below the origin. For $t>0$, close the contour in the lower half-plane. The contour is clockwise and encloses the pole, whose residue is $1$. Therefore

$$
I(t)=-i.
$$

For $t<0$, close in the upper half-plane and enclose no pole, so $I(t)=0$. Thus

$$
I(t)=-i\theta(t).
$$

This is the transform version of

$$
\frac{1}{\omega+i0}=\operatorname{PV}\frac{1}{\omega}-i\pi\delta(\omega).
$$

Indeed, Fourier transforming the right-hand side gives the same answer with the site convention.

## Exercises

### Exercise 1: A rational integral

Use residues to compute

$$
\int_{-\infty}^{\infty}\frac{dx}{(x^2+a^2)^2}
$$

for $a>0$.

<details><summary><strong>Solution</strong></summary>

The integrand has second-order poles at $z=ia$ and $z=-ia$. Close in the upper half-plane. The residue at $z=ia$ is

$$
\operatorname{Res}_{z=ia}\frac{1}{(z^2+a^2)^2}
=\left.\frac{d}{dz}\frac{1}{(z+ia)^2}\right|_{z=ia}
=-\frac{2}{(2ia)^3}
=\frac{1}{4ia^3}.
$$

Therefore

$$
\int_{-\infty}^{\infty}\frac{dx}{(x^2+a^2)^2}
=2\pi i\frac{1}{4ia^3}
=\frac{\pi}{2a^3}.
$$

</details>

### Exercise 2: Advanced pole prescription

Show that

$$
\int\frac{d\omega}{2\pi}\,
\frac{e^{-i\omega t}}{\omega-\omega_0-i0}
=i\theta(-t)e^{-i\omega_0t}.
$$

<details><summary><strong>Solution</strong></summary>

The pole is at $\omega=\omega_0+i0$, just above the real axis. For $t>0$, close below; no pole is enclosed, so the result is zero. For $t<0$, close above; the contour is counterclockwise and encloses the pole. The residue is $e^{-i\omega_0t}$, so

$$
I(t)=\frac{1}{2\pi}(2\pi i)e^{-i\omega_0t}
=i e^{-i\omega_0t}.
$$

Combining the two cases gives the stated result.

</details>

### Exercise 3: Scalar propagator pole locations

Starting from

$$
(p^0)^2-E^2+i\epsilon,
$$

show that the poles are displaced as

$$
p^0=E-i0,
\qquad
p^0=-E+i0.
$$

<details><summary><strong>Solution</strong></summary>

Factor the denominator approximately as

$$
(p^0)^2-E^2+i\epsilon
=(p^0-E)(p^0+E)+i\epsilon.
$$

Near $p^0=E$, write $p^0=E+\delta$. Then

$$
(p^0)^2-E^2+i\epsilon\approx 2E\delta+i\epsilon,
$$

so the zero is at

$$
\delta=-\frac{i\epsilon}{2E},
$$

just below the real axis. Near $p^0=-E$, write $p^0=-E+\delta$. Then

$$
(p^0)^2-E^2+i\epsilon\approx -2E\delta+i\epsilon,
$$

so

$$
\delta=\frac{i\epsilon}{2E},
$$

just above the real axis.

</details>

## References

- L. Ahlfors, *Complex Analysis*. Classic reference for Cauchy theory and residues.
- E. Stein and R. Shakarchi, *Complex Analysis*. Clear introduction to contour integration and analytic continuation.
- E. Titchmarsh, *The Theory of Functions*. Classic source for boundary behavior and contour arguments.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Useful for contour methods and special functions.
- G. Arfken, H. Weber, and F. Harris, *Mathematical Methods for Physicists*. Useful for applied residue calculations.
- C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*. Useful for contours, asymptotics, and saddle-point methods.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for propagator prescriptions and analytic structure.
- M. Srednicki, *Quantum Field Theory*. Useful for contour derivations of propagators and loop-integral practice.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for practical QFT contour methods, Feynman prescriptions, and Wick rotation.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for analytic continuation and saddle-point methods.
- J. Kapusta and C. Gale, *Finite-Temperature Field Theory*. Useful for Matsubara sums and thermal contour methods.
- M. Le Bellac, *Thermal Field Theory*. Useful for analytic structure of thermal correlators.

## Version history

- **2026-06-26:** Initial polished draft. Added contour orientation, residue formulas, residues at infinity, Fourier contour prescriptions, scalar propagator derivation, branch-cut contours, Wick rotation, Matsubara sums, arc estimates, exercises, and a TikZ/SVG figure.
