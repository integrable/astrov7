---
title: "Analytic Continuation"
description: "Explains analytic continuation for QFT, including germs, identity theorem, overlapping domains, monodromy, boundary values, Euclidean-to-Lorentzian continuation, Matsubara continuation, Wick rotation, and common failure modes."
sidebar:
  label: "Analytic Continuation"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard references on complex analysis, analytic continuation, QFT propagators, spectral representations, thermal field theory, and Wick rotation, including Ahlfors, Stein–Shakarchi, Conway, Titchmarsh, Whittaker–Watson, Osterwalder–Schrader, Streater–Wightman, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Kapusta–Gale, Le Bellac, and mathematical-physics treatments of boundary values."
topics:
  - analytic continuation
  - identity theorem
  - germs
  - monodromy
  - boundary values
  - Wick rotation
  - Euclidean correlators
  - Lorentzian correlators
  - Matsubara frequencies
  - retarded Green functions
  - spectral representations
canonicalTopics:
  - analytic-continuation
  - identity-theorem
  - germ
  - monodromy
  - boundary-value
  - wick-rotation
  - euclidean-correlator
  - lorentzian-correlator
  - matsubara-frequency
  - retarded-green-function
  - spectral-representation
researchStatus:
  established:
    - "Analytic continuation, identity theorems, monodromy, boundary values, Wick rotation, and spectral representations are standard tools in complex analysis and QFT."
    - "Euclidean-to-Lorentzian continuation is well understood under appropriate axioms or spectral/causality assumptions, but requires care with domains, singularities, and boundary values."
  active:
    - "Analytic continuation remains an active issue in real-time thermal QFT, finite-density systems, Lorentzian CFT, numerical analytic continuation, resurgence, complex saddles, and nonperturbative definitions of QFT."
---

## Summary

Analytic continuation is the process of extending a holomorphic function beyond the region where it was first defined. Locally, it is almost magical: if two holomorphic functions agree on a set with an accumulation point inside a connected domain, they agree everywhere in that domain. Globally, it is less magical and more bureaucratic: singularities, cuts, sheets, growth conditions, and boundary values must all be recorded.

In QFT, analytic continuation is the bridge behind several familiar moves:

$$
\text{Euclidean correlator}\quad\longleftrightarrow\quad\text{Lorentzian correlator},
$$

$$
\text{Matsubara data}\quad\longrightarrow\quad\text{retarded response},
$$

$$
\text{Feynman integral in Minkowski space}\quad\longleftrightarrow\quad\text{Euclidean integral},
$$

and

$$
\text{one branch of an amplitude}\quad\longrightarrow\quad\text{another Riemann sheet}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![Diagram showing analytic continuation by overlapping germs and path dependence around a branch point.](/figures/math-toolkit/analytic-continuation-paths.svg)

<figcaption>

Analytic continuation is local: a power series is re-expanded through overlapping domains. It is also global: different paths around a branch point can land on different sheets. This is why continuation is not just substitution of complex variables.

</figcaption>
</figure>

The main lesson is simple but easy to forget:

$$
\text{analytic continuation is unique only after the domain and path data are fixed.}
$$

A formula such as $i\omega_n\to\omega+i0$ or $t\to-i\tau$ is a shorthand for a statement about analytic functions and their boundary values. It is not a license to rotate every variable through every singularity. Complex analysis has rules; it is not vibes with $i$’s.

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/).

We use the site Fourier convention

$$
f(t)=\int\frac{d\omega}{2\pi}\,e^{-i\omega t}\widetilde f(\omega).
$$

With this convention, retarded functions are naturally analytic in the upper half of the complex $\omega$-plane, under suitable decay assumptions.

## Germs and the identity theorem

A **germ** of a holomorphic function at $z_0$ is the local function near $z_0$, with two local functions identified if they agree in some neighborhood of $z_0$. In less fancy language, a germ is “the analytic function as seen by a sufficiently small microscope.”

If $f$ is holomorphic near $z_0$, then it has a power series

$$
f(z)=\sum_{n=0}^{\infty}a_n(z-z_0)^n
$$

inside its disk of convergence. If this disk overlaps another disk centered at $z_1$, and if $z_1$ lies in the first disk, then the same function can be re-expanded as

$$
f(z)=\sum_{n=0}^{\infty}b_n(z-z_1)^n.
$$

Repeating this process along a path gives analytic continuation.

The reason continuation is rigid is the identity theorem:

:::note[Identity theorem]
If $f$ and $g$ are holomorphic on a connected open set $D$, and if the set of points where $f=g$ has an accumulation point inside $D$, then

$$
f=g
$$

on all of $D$.
:::

This is the theorem behind the physicist’s phrase “the analytic continuation.” Once the holomorphic function and the connected domain are fixed, there is no freedom to adjust it elsewhere without changing it everywhere.

## Continuation along paths

Let $f_0$ be holomorphic in a disk $U_0$ around $z_0$. Choose a path

$$
\gamma:[0,1]\to\mathbb C,
\qquad \gamma(0)=z_0.
$$

An analytic continuation of $f_0$ along $\gamma$ is a chain of overlapping open sets

$$
U_0,U_1,\ldots,U_N
$$

covering the path, together with holomorphic functions $f_j$ on $U_j$, such that

$$
f_j=f_{j+1}
$$

on every connected overlap $U_j\cap U_{j+1}$. The identity theorem then guarantees that each handoff is unique where it is possible.

This local uniqueness does not automatically imply global path independence. If two different paths from $z_0$ to $z_1$ wind around different singularities, the continued values may land on different branches. This is exactly what happens for $\log z$ and $\sqrt z$ around the origin.

A useful theorem packages the safe case:

:::note[Monodromy theorem]
If a germ can be analytically continued along every path in a simply connected domain $D$, and if continuation around closed loops returns to the original germ, then the germ defines a single-valued holomorphic function on all of $D$.
:::

The hypotheses matter. If the domain is not simply connected, or if closed loops produce nontrivial monodromy, there may be no single-valued function on $D$.

## Singularities are the map

Analytic continuation is controlled by obstructions. The most common ones are:

| Obstruction | What it does |
|---|---|
| removable singularity | can be filled in after redefining the value |
| pole | blocks continuation through the point and gives residues |
| branch point | continuation around it changes branch |
| cut | chosen seam used to define a branch |
| essential singularity | produces wild local behavior |
| natural boundary | prevents continuation beyond a curve |
| pinch singularity | traps a contour between approaching singularities |

In QFT, singularity locations are often more physical than closed-form answers. A two-point function knows the mass gap by the first threshold. A scattering amplitude knows allowed intermediate states by its cuts. A resonance is not merely a bump in a plot; it is a pole on a particular sheet. Thermal correlators know causality and dissipation through analyticity domains.

The right question is rarely “Can I substitute a complex number?” The right question is:

$$
\text{From which domain, along which path, to which boundary value?}
$$

## Boundary values are part of the data

Many QFT objects are not values of analytic functions on a cut. They are boundary values from one side of a cut. For an analytic function $F(z)$ defined off the real axis, define

$$
F_+(x)=F(x+i0),
\qquad
F_-(x)=F(x-i0).
$$

The discontinuity is

$$
\operatorname{Disc}F(x)=F_+(x)-F_-(x).
$$

The formula

$$
\frac{1}{x+i0}=\operatorname{PV}\frac1x-i\pi\delta(x)
$$

is a boundary-value statement. The analytic function is $1/z$ away from $z=0$; the QFT distribution is obtained by approaching the real axis from above.

Similarly, the logarithm has different boundary values. With the principal logarithm,

$$
\operatorname{Log}(-s-i0)=\log s-i\pi,
\qquad
\operatorname{Log}(-s+i0)=\log s+i\pi,
$$

for $s>0$. The imaginary part is not optional. It is fixed by the continuation path.

## Retarded functions and analyticity

For a bosonic operator $O$, define the retarded two-point function

$$
G_R(t)=-i\theta(t)\langle[O(t),O(0)]\rangle.
$$

Its Fourier transform is

$$
G_R(\omega)=\int_{-\infty}^{\infty}dt\,e^{i\omega t}G_R(t).
$$

Because $G_R(t)$ vanishes for $t<0$, the factor

$$
e^{i(x+iy)t}=e^{ixt}e^{-yt}
$$

improves convergence for $y>0$. Under standard boundedness assumptions, $G_R(\omega)$ is analytic for

$$
\operatorname{Im}\omega>0.
$$

The physical real-frequency retarded function is the upper-half-plane boundary value

$$
G_R(\omega+i0).
$$

The spectral density is often defined by

$$
\rho(\omega)=-2\operatorname{Im}G_R(\omega+i0),
$$

though some communities absorb signs or factors of $2\pi$ differently. The analytic domain is not a convention: retarded means causal support, and causal support gives upper-half-plane analyticity with the Fourier phase used here.

## Spectral representation as continuation technology

A common convention writes a frequency-space Euclidean correlator as

$$
G_E(z)=\int_{-\infty}^{\infty}\frac{d\omega'}{2\pi}\,
\frac{\rho(\omega')}{\omega'-z},
$$

where $z$ is initially evaluated at Matsubara points. The retarded function is then the boundary value

$$
G_R(\omega)=G_E(\omega+i0)
$$

in this convention.

The notation compresses several facts:

- $G_E(z)$ is not merely a list of values at discrete Matsubara frequencies.
- The function has a cut where the spectral density has support.
- The retarded correlator is a boundary value from the upper half-plane.
- The imaginary part is controlled by the discontinuity across the cut.

Indeed,

$$
G_E(\omega+i0)-G_E(\omega-i0)
= i\rho(\omega)
$$

with the displayed normalization. Different denominator conventions shift the sign. The lesson is invariant: spectral data live in the discontinuity.

## Matsubara continuation

At finite temperature, bosonic Euclidean correlators are sampled at Matsubara frequencies

$$
\omega_n=2\pi nT,
\qquad n\in\mathbb Z,
$$

while fermionic correlators use

$$
\omega_n=(2n+1)\pi T.
$$

In formulas one often writes

$$
i\omega_n\to \omega+i0.
$$

This shorthand is safe only when the Euclidean data are known to come from the correct analytic function with the correct growth. Values on a discrete set do not determine a holomorphic function by themselves, because the identity theorem requires an accumulation point inside the domain. The Matsubara frequencies accumulate only at infinity.

This is why numerical analytic continuation from imaginary-time data is ill-conditioned. Infinitely many analytic functions can agree nearly perfectly at the sampled Euclidean data while having noticeably different real-time spectral densities. Physics input—positivity, asymptotics, sum rules, smoothness, model space, or Bayesian priors—must supplement the raw data.

For formal continuum QFT calculations, the analytic structure usually supplies the missing input. For numerical data, the missing input becomes the problem. Tiny Euclidean error bars can turn into a whole jazz solo on the real axis.

## Wick rotation

Wick rotation is analytic continuation plus contour deformation. For a scalar Feynman denominator in the mostly-minus convention,

$$
\frac{i}{p^2-m^2+i0}
=\frac{i}{(p^0)^2-\mathbf p^2-m^2+i0},
$$

with

$$
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

the poles are located at

$$
p^0=+E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}+i0.
$$

The $i0$ prescription tells the contour how to pass the poles. Rotating the $p^0$ contour to the imaginary axis is legitimate only if the contour can be deformed without crossing poles and if the arcs at infinity do not contribute.

With

$$
p^0=i p_E^0,
\qquad
p_E^2=(p_E^0)^2+\mathbf p^2,
$$

one obtains schematically

$$
\int\frac{d^4p}{(2\pi)^4}\,\frac{i}{p^2-m^2+i0}
\longrightarrow
\int\frac{d^4p_E}{(2\pi)^4}\,\frac{1}{p_E^2+m^2},
$$

up to regulator and contour assumptions. The arrow is not algebra. It is the residue-free deformation of an integral contour in a complex plane.

Wick rotation can fail or require modification when:

| Situation | Possible obstruction |
|---|---|
| real-time thermal contours | multiple time branches and thermal singularities |
| finite density | poles or cuts can obstruct naive rotation |
| nonzero external energies | singularities may pinch the loop-energy contour |
| unstable backgrounds | Euclidean saddle may not define a stable integral |
| gauge theories | gauge fixing and zero modes require care |
| nonperturbative sectors | different saddles may live on different contours |

The moral is not “avoid Wick rotation.” The moral is “do not pretend the rotation is free.” Most textbook uses are valid because their hypotheses are quietly satisfied.

## Euclidean and Lorentzian correlators

Euclidean correlators are often easier to define nonperturbatively. Lorentzian correlators are what causality, scattering, and real-time response require. Analytic continuation connects them, but only after one specifies operator ordering and domain.

For a simple spectral decomposition with Hamiltonian eigenstates, a Euclidean two-point function for $\tau>0$ has the form

$$
G_E(\tau)=\sum_n |\langle0|O|n\rangle|^2 e^{-(E_n-E_0)\tau}.
$$

The corresponding Wightman function is obtained by

$$
\tau=it+0^+,
$$

or equivalently by approaching the Lorentzian time axis from the correct half-plane:

$$
G^>(t)=\sum_n |\langle0|O|n\rangle|^2 e^{-i(E_n-E_0)t}.
$$

The small positive Euclidean regulator remembers the ordering. Different Lorentzian orderings—Wightman, time-ordered, retarded, advanced—are different boundary values or combinations of boundary values. There is not one Lorentzian correlator hiding behind the Euclidean correlator; there is an analytic object whose different boundary values encode different physical orderings.

## Continuation between sheets

Analytic continuation also relates different Riemann sheets of the same amplitude. Suppose a function contains

$$
k(s)=\sqrt{s-s_0}
$$

with a cut beginning at $s_0$. A continuation around $s_0$ sends

$$
k(s)\mapsto-k(s).
$$

Therefore any amplitude written as

$$
\mathcal A(s)=F(s,k(s))
$$

has an adjacent-sheet continuation

$$
\mathcal A_{\mathrm{II}}(s)=F(s,-k(s)).
$$

Resonance poles are often found on this adjacent sheet. They are invisible if one insists on looking only at the physical sheet as a single-valued function of $s$. The analytic continuation is the operation that reveals them.

## Common pitfalls

**Substitution is not continuation.** Replacing a variable by a complex value is meaningful only when a holomorphic function and continuation path have been specified.

**The identity theorem needs an accumulation point in the domain.** A discrete Matsubara sequence accumulating only at infinity does not, by itself, determine a unique analytic function.

**Euclidean continuation does not choose every Lorentzian ordering at once.** Retarded, advanced, Wightman, and time-ordered correlators are different boundary values or combinations of boundary values.

**Wick rotation can cross singularities.** The deformation must avoid poles and cuts. External kinematics can pinch loop contours and obstruct naive rotation.

**A cut is not a wall of physical reality.** It is a chosen seam. But the boundary values on its sides are real analytic data and cannot be ignored.

**Growth at infinity matters.** Dispersion relations, Carlson-type uniqueness statements, and contour rotations all require assumptions about growth.

**Numerical analytic continuation is ill-conditioned.** Exact analytic structure can determine a continuation; noisy samples usually cannot without additional input.

**The second sheet is not a second function unrelated to the first.** It is the same analytic object continued along a path crossing or circling a branch point.

## Exercises

### Exercise 1: Identity theorem check

Let $f$ be holomorphic on a connected domain $D$. Suppose $f$ vanishes on a sequence of distinct points $z_n\in D$ with $z_n\to z_*$ and $z_*\in D$. Show that $f$ vanishes identically.

<details><summary><strong>Solution</strong></summary>

Because $z_*$ is an accumulation point in $D$, the identity theorem applied to $f$ and the zero function gives

$$
f=0
$$

on all of $D$. Equivalently, the zeros of a nonzero holomorphic function are isolated. A sequence of distinct zeros accumulating inside the domain is possible only for the zero function.

</details>

### Exercise 2: Two continuations of the square root

Start with the branch $\sqrt z=1$ at $z=1$. Continue once around the origin counterclockwise and return to $z=1$. What value do you obtain? What happens after two loops?

<details><summary><strong>Solution</strong></summary>

Write $z=e^{i\theta}$ along the unit circle. Starting at $\theta=0$, the chosen value is

$$
\sqrt z=e^{i\theta/2}.
$$

After one counterclockwise loop, $\theta=2\pi$, so

$$
\sqrt z=e^{i\pi}=-1.
$$

After two loops, $\theta=4\pi$, so

$$
\sqrt z=e^{2\pi i}=1.
$$

Thus the square root has two-sheet monodromy.

</details>

### Exercise 3: Boundary value of a pole

Use the distribution identity

$$
\frac{1}{x+i0}=\operatorname{PV}\frac1x-i\pi\delta(x)
$$

to compute

$$
\frac{1}{x+i0}-\frac{1}{x-i0}.
$$

<details><summary><strong>Solution</strong></summary>

The conjugate boundary value is

$$
\frac{1}{x-i0}=\operatorname{PV}\frac1x+i\pi\delta(x).
$$

Therefore

$$
\frac{1}{x+i0}-\frac{1}{x-i0}
=-2\pi i\delta(x).
$$

The principal-value parts cancel. The discontinuity is entirely supported at the pole.

</details>

### Exercise 4: Why Matsubara samples are not enough

Explain why knowing a holomorphic function at all points $z_n=i2\pi nT$ does not by itself determine the function uniquely on the complex plane cut along the real axis.

<details><summary><strong>Solution</strong></summary>

The identity theorem requires agreement on a set with an accumulation point inside the domain. The Matsubara points

$$
z_n=i2\pi nT
$$

have no finite accumulation point; they accumulate only at infinity. Therefore two different holomorphic functions can agree on all Matsubara points while differing elsewhere, unless additional growth conditions or physical input are imposed. This is the analytic reason numerical continuation from Euclidean thermal data is ill-conditioned.

</details>

### Exercise 5: Wick rotation poles

For the Feynman denominator

$$
(p^0)^2-E_{\mathbf p}^2+i0,
$$

locate the two poles in the complex $p^0$-plane.

<details><summary><strong>Solution</strong></summary>

The poles solve

$$
(p^0)^2-E_{\mathbf p}^2+i0=0.
$$

Factoring with the Feynman prescription gives

$$
(p^0-E_{\mathbf p}+i0)(p^0+E_{\mathbf p}-i0).
$$

Thus the positive-energy pole is slightly below the real axis,

$$
p^0=E_{\mathbf p}-i0,
$$

and the negative-energy pole is slightly above the real axis,

$$
p^0=-E_{\mathbf p}+i0.
$$

This placement is what makes the Feynman contour and Wick rotation well-defined in the standard vacuum case.

</details>

## References

- L. Ahlfors, *Complex Analysis*. Standard reference for analytic continuation, monodromy, and Riemann surfaces.
- E. Stein and R. Shakarchi, *Complex Analysis*. Clear introduction to identity theorems, continuation, and contour deformation.
- J. B. Conway, *Functions of One Complex Variable*. Useful for germs, monodromy, and analytic continuation theorems.
- E. Titchmarsh, *The Theory of Functions*. Classic source for analytic function theory and boundary behavior.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Classic reference for analytic continuation of special functions.
- A. S. Wightman and R. F. Streater, *PCT, Spin and Statistics, and All That*. Standard reference for analytic structure in axiomatic QFT.
- K. Osterwalder and R. Schrader, papers on Euclidean QFT reconstruction. Foundational source for Euclidean-to-Lorentzian reconstruction.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for propagators, $i0$ prescriptions, and analytic structure in scattering.
- M. Srednicki, *Quantum Field Theory*. Useful for Wick rotation, spectral representations, and perturbative examples.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Practical source for propagators, contour methods, and Wick rotation.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for analytic continuation, Euclidean methods, and asymptotics.
- J. I. Kapusta and C. Gale, *Finite-Temperature Field Theory*. Standard reference for Matsubara continuation and real-time response.
- M. Le Bellac, *Thermal Field Theory*. Standard reference for thermal Green functions and analytic continuation.

## Version history

- **2026-06-26:** Initial polished draft. Added germs, identity theorem, path continuation, monodromy theorem, boundary values, retarded analyticity, spectral and Matsubara continuation, Wick rotation, Euclidean-to-Lorentzian continuation, exercises with solutions, and TikZ/SVG figure.
