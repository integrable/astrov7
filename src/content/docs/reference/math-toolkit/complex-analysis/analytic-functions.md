---
title: "Analytic Functions"
description: "Explains holomorphic functions as rigid complex functions, including complex differentiability, Cauchy–Riemann equations, Wirtinger derivatives, contour independence, Cauchy formulas, power series, analytic continuation, singularities, and QFT uses."
sidebar:
  label: "Analytic Functions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard references on complex analysis and mathematical physics, including Ahlfors, Stein–Shakarchi, Conway, Titchmarsh, Whittaker–Watson, Bender–Orszag, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, Di Francesco–Mathieu–Sénéchal, and mathematical-physics treatments of analytic continuation and boundary values."
topics:
  - analytic functions
  - holomorphic functions
  - complex differentiability
  - Cauchy–Riemann equations
  - Wirtinger derivatives
  - Cauchy integral formula
  - power series
  - identity theorem
  - maximum modulus principle
  - analytic continuation
  - singularities
  - boundary values
canonicalTopics:
  - analytic-function
  - holomorphic-function
  - complex-differentiability
  - cauchy-riemann-equations
  - wirtinger-derivative
  - cauchy-integral-formula
  - power-series
  - identity-theorem
  - maximum-modulus-principle
  - analytic-continuation
  - singularity
  - boundary-value
researchStatus:
  established:
    - "Holomorphicity, Cauchy’s theorem, Cauchy’s integral formula, power-series expansions, analytic continuation, and the classification of isolated singularities are standard pillars of complex analysis and mathematical physics."
  active:
    - "Modern QFT and mathematical physics continue to use analytic-function ideas in Lorentzian CFT, scattering amplitudes, resurgence, thermal correlators, nonperturbative saddle analysis, and rigorous boundary-value formulations of propagators and response functions."
---

## Summary

An analytic, or holomorphic, function is a complex function $f(z)$ that is complex differentiable in an open region. That short definition is dangerously modest. Holomorphic functions are not merely smooth functions with complex notation; they are rigid objects whose local behavior determines their global behavior as far as singularities allow.

The basic derivative is

$$
f'(z_0)=\lim_{h\to 0}\frac{f(z_0+h)-f(z_0)}{h},
$$

where $h$ approaches zero from every complex direction. Requiring the same limit from all directions is the little trapdoor through which a whole cathedral falls out: Cauchy’s theorem, contour deformation, power series, residues, analytic continuation, branch cuts, dispersion relations, and the $i\epsilon$ prescriptions of QFT.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Flow diagram showing complex differentiability leading to Cauchy–Riemann equations, Cauchy integral formula, power series, analytic continuation, and singularities.](/figures/math-toolkit/analytic-function-rigidity.svg)

<figcaption>

Holomorphicity is rigid. Complex differentiability on an open set implies Cauchy–Riemann equations, contour deformation, Cauchy integral formulas, local power series, and analytic continuation. QFT uses this rigidity to turn singularities into physical information.

</figcaption>
</figure>

The operational slogan is

$$
\bar\partial f=0
\quad\Longrightarrow\quad
\text{contours move, local data propagate, singularities matter}.
$$

This page builds the vocabulary needed for [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), branch cuts, analytic continuation, dispersion relations, conformal maps, and Riemann surfaces.

## Prerequisites

You should know ordinary real calculus, line integrals, elementary topology of open sets, Fourier transforms, and the distributional boundary-value notation introduced in [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/). It also helps to know [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/) and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/), because many QFT examples below are resolvents or propagators viewed as complex functions.

Throughout this page, $z=x+iy$, and a complex function is written

$$
f(z)=u(x,y)+iv(x,y).
$$

## What complex differentiability demands

A function of one complex variable is also a function of two real variables. If $f=u+iv$ is merely differentiable as a real map $\mathbb R^2\to\mathbb R^2$, its derivative at a point is a real linear map

$$
Df=\begin{pmatrix}
\partial_xu & \partial_yu\\
\partial_xv & \partial_yv
\end{pmatrix}.
$$

Complex differentiability asks for more. Multiplication by a complex number $a+ib$ is represented as the special real matrix

$$
\begin{pmatrix}
a & -b\\
b & a
\end{pmatrix}.
$$

Therefore $f$ is complex differentiable only if its real derivative has this form. This gives the Cauchy–Riemann equations

$$
\partial_x u=\partial_y v,
\qquad
\partial_y u=-\partial_x v.
$$

Equivalently,

$$
Df\circ J=J\circ Df,
$$

where $J$ is rotation by $90^\circ$. This geometric form says that infinitesimal complex structure is preserved. Holomorphic maps are the maps whose first-order behavior is multiplication by a complex number, not an arbitrary linear distortion.

A useful sanity check is $f(z)=\bar z$. Here $u=x$ and $v=-y$, so

$$
\partial_xu=1,
\qquad
\partial_yv=-1,
$$

and the Cauchy–Riemann equations fail. The map $z\mapsto \bar z$ is perfectly smooth as a real map, but it is not holomorphic. It reverses orientation and angles.

## Wirtinger derivatives

The cleanest notation treats $z$ and $\bar z$ as formally independent variables. Define

$$
\partial_z=\frac12\left(\partial_x-i\partial_y\right),
\qquad
\partial_{\bar z}=\frac12\left(\partial_x+i\partial_y\right).
$$

Then

$$
dz=dx+i\,dy,
\qquad
 d\bar z=dx-i\,dy,
$$

and for a smooth function

$$
df=(\partial_z f)\,dz+(\partial_{\bar z}f)\,d\bar z.
$$

The Cauchy–Riemann equations are simply

$$
\partial_{\bar z}f=0.
$$

This notation is everywhere in two-dimensional QFT and string theory. A “chiral” field depending only on $z$ is holomorphic, while an anti-chiral field depending only on $\bar z$ is antiholomorphic. In Euclidean two-dimensional CFT, one often writes correlators as functions of $z_i$ and $\bar z_i$ separately; holomorphic factorization, when it holds, is the statement that a sector is controlled by $\bar\partial=0$.

A tiny warning: in physics notation, $\partial$ and $\bar\partial$ are sometimes used both for differential operators and for exterior operators on forms. Context decides whether $\partial f$ means $(\partial_z f)dz$ or just $\partial_z f$. When sign trouble appears, write the $dz$ and $d\bar z$ explicitly. It is cheaper than regret.

## Holomorphic functions preserve angles

If $f'(z_0)\neq0$, then near $z_0$ one has

$$
f(z_0+h)=f(z_0)+f'(z_0)h+O(h^2).
$$

Multiplication by $f'(z_0)=|f'(z_0)|e^{i\theta}$ scales lengths by $|f'(z_0)|$ and rotates angles by $\theta$. Hence noncritical holomorphic maps are conformal: they preserve oriented angles.

This is why complex analysis is the natural language of two-dimensional conformal field theory. Locally, any holomorphic coordinate change with nonzero derivative is an angle-preserving change of coordinates. Globally, singularities, boundary conditions, and topology decide which conformal maps exist.

At a critical point, $f'(z_0)=0$, the map need not be locally one-to-one. If

$$
f(z)-f(z_0)=a_n(z-z_0)^n+O((z-z_0)^{n+1}),
\qquad a_n\neq0,
$$

then angles are multiplied by $n$ and the map locally looks like an $n$-fold covering. This is the local model behind branch points and ramification.

## Cauchy’s theorem in its simplest form

Let $D$ be a simply connected domain, and let $f$ be holomorphic on $D$. Then for any closed contour $C$ in $D$,

$$
\oint_C dz\,f(z)=0.
$$

This is Cauchy’s theorem. It implies that if two paths from $a$ to $b$ can be continuously deformed into one another while staying inside $D$, then

$$
\int_{\gamma_1} dz\,f(z)=\int_{\gamma_2} dz\,f(z).
$$

The integral depends only on the homotopy class of the path in the region where the integrand is holomorphic.

The QFT translation is immediate: contours can move until they hit singularities. A propagator prescription, a pole, a branch cut, or a saddle is not decoration on a drawing. It is the obstruction that prevents a contour move from being trivial.

A common example is the inverse Fourier transform of a frequency-space Green function. The exponential $e^{-i\omega t}$ tells you which half-plane gives decay on the closing arc. The pole prescription tells you which singularities are inside the contour. The answer is causal or anti-causal because the contour knows where the poles are.

## Cauchy’s integral formula

Cauchy’s theorem says integrals around holomorphic regions vanish. Cauchy’s integral formula says values inside a contour are determined by values on the contour. If $f$ is holomorphic on and inside a positively oriented simple contour $C$, and $z_0$ lies inside $C$, then

$$
f(z_0)=\frac{1}{2\pi i}\oint_C dz\,\frac{f(z)}{z-z_0}.
$$

Even better,

$$
f^{(n)}(z_0)=\frac{n!}{2\pi i}\oint_C dz\,\frac{f(z)}{(z-z_0)^{n+1}}.
$$

This is one of the central surprises of complex analysis. The entire tower of derivatives at $z_0$ is determined by boundary data. In QFT language, this is the seed of many reconstruction formulas: analyticity plus singularity data can determine an amplitude or correlator far away from the region where it was first computed.

For example, dispersion relations are Cauchy integral formulas adapted to functions with cuts. The contour is enlarged until it runs around the cut; the function is then reconstructed from its discontinuity across that cut, up to possible subtraction constants.

## Power series and radius of convergence

If $f$ is holomorphic in a disk centered at $z_0$, then it has a convergent Taylor series

$$
f(z)=\sum_{n=0}^{\infty}a_n(z-z_0)^n,
\qquad
a_n=\frac{f^{(n)}(z_0)}{n!}.
$$

The radius of convergence is the distance from $z_0$ to the nearest singularity of the analytic continuation of $f$. This innocent statement is wildly useful.

Suppose a perturbative expansion or conformal-block expansion is naturally a power series in a complex variable. Its radius of convergence is not set by where your algebra gets bored; it is set by singularities in the complex plane. That is why mapping a domain to a unit disk, changing variables to expose the nearest singularity, or using radial coordinates can dramatically improve convergence.

A simple example is

$$
\frac{1}{1-z}=\sum_{n=0}^{\infty}z^n,
\qquad |z|<1.
$$

The series fails at $|z|=1$ not because the function is singular everywhere on the unit circle, but because the nearest singularity to $0$ is the pole at $z=1$. Around a different center, the disk of convergence changes accordingly.

This principle reappears in the operator product expansion. The convergence domain is controlled by the closest operator insertion or singular configuration in complexified position space. Geometry of singularities becomes convergence data.

## Identity theorem and analytic continuation

The identity theorem says: if two holomorphic functions on a connected domain agree on a set with an accumulation point in that domain, then they agree everywhere in the domain.

Equivalently, if a holomorphic function has zeros accumulating inside its domain, it is identically zero. This is absurdly unlike real smooth functions, where one can build bump functions vanishing on large sets and nonzero elsewhere.

Analytic continuation is the corresponding propagation principle. If $f$ is known near one point and can be extended holomorphically along a path, then its extension is unique along that path. Different paths can give different values only if the domain has nontrivial monodromy or singularities. That is the beginning of Riemann surfaces.

In physics, analytic continuation is powerful but not magic. A Euclidean correlator can determine a Lorentzian correlator only when one knows the relevant analytic domain and boundary-value prescription. “Replace $\tau$ by $it$” is the final line of an argument, not the argument. The singularities are the bouncers at the club.

## Maximum principle and Liouville’s theorem

If $f$ is holomorphic on a connected domain $D$, then $|f|$ cannot have a strict local maximum inside $D$ unless $f$ is constant. This is the maximum modulus principle.

One consequence is Liouville’s theorem: a bounded entire function is constant. An entire function is holomorphic on all of $\mathbb C$. Thus, if

$$
|f(z)|\leq M
\qquad\text{for all }z\in\mathbb C,
$$

then $f$ is constant.

This is not only a cute theorem. It underlies many uniqueness arguments. For instance, if two candidate analytic functions have the same singularity structure and their difference is entire and suitably bounded, then the difference may be forced to be a polynomial or constant. In S-matrix and dispersion problems, growth at infinity is not a boring technicality; it determines the number of subtraction constants and the uniqueness of reconstruction.

## Singularities

Analytic functions are best understood by their failures to be analytic. An isolated singularity at $z_0$ is classified by the Laurent expansion

$$
f(z)=\sum_{n=-\infty}^{\infty}a_n(z-z_0)^n.
$$

There are three basic cases.

| Type | Local form | Meaning |
|---|---|---|
| removable | no negative powers after redefining $f(z_0)$ | the singularity was fake |
| pole of order $m$ | finitely many negative powers down to $(z-z_0)^{-m}$ | meromorphic singularity with algebraic blowup |
| essential | infinitely many negative powers | genuinely wild local behavior |

In QFT, simple poles often represent one-particle states, bound states, or normal modes. Branch points and cuts usually represent continua or thresholds. Essential singularities appear in nonperturbative and asymptotic contexts, for example through expressions like $e^{-1/g^2}$ near $g=0$.

A meromorphic function is holomorphic except for poles. Meromorphic functions are the friendliest singular functions: contour integrals reduce to sums of residues, and isolated poles have finite algebraic data. Many first QFT contour computations are meromorphic for precisely this reason.

## Harmonic functions and potentials

If $f=u+iv$ is holomorphic, then the Cauchy–Riemann equations imply

$$
\Delta u=0,
\qquad
\Delta v=0,
$$

where $\Delta=\partial_x^2+\partial_y^2$. Thus the real and imaginary parts of a holomorphic function are harmonic.

Locally, $u$ and $v$ are harmonic conjugates. The level curves of $u$ and $v$ intersect orthogonally where $f'\neq0$. This is the classical link between complex analysis, electrostatics, fluid flow, and two-dimensional potential theory.

In field theory this viewpoint is useful in two dimensions. Logarithmic Green functions, Coulomb-gas representations, vertex operators, conformal maps, and vortex configurations all exploit the fact that

$$
\Delta\log|z|=2\pi\delta^{(2)}(z)
$$

as a distribution. The function $\log z$ is multivalued, but its derivative $1/z$ is meromorphic on the punctured plane. Physics frequently lives in this compromise: a multivalued potential with single-valued local fields.

## Boundary values and distributions

A function may be holomorphic away from the real axis and still have a distributional boundary value on it. The most important example is

$$
\frac{1}{x\pm i0}=\operatorname{PV}\frac{1}{x}\mp i\pi\delta(x).
$$

Here $1/(z)$ is analytic off the origin, but approaching the real axis from above or below gives different distributions. This is how analytic functions talk to causal Green functions.

More generally, if $F(z)$ is holomorphic in the upper and lower half-planes and has boundary values $F(x+i0)$ and $F(x-i0)$, then the discontinuity

$$
\operatorname{Disc}F(x)=F(x+i0)-F(x-i0)
$$

records the jump across the real axis. In spectral representations, this jump is often proportional to a spectral density. In scattering, it is related to absorptive parts and thresholds. In thermal field theory, analytic strips and boundary values encode retarded, advanced, Euclidean, and Matsubara correlators.

This is the conceptual reason complex analysis belongs near distributions in the Mathematical Toolkit. The function in the complex plane is honest and smooth away from singularities; the physical real-axis object may be a distribution obtained as a boundary value.

## Examples from QFT

### Propagator denominators

With mostly-minus convention, the scalar Feynman propagator in momentum space has denominator

$$
p^2-m^2+i\epsilon.
$$

For fixed spatial momentum, write

$$
p^2-m^2+i\epsilon=(p^0)^2-E_{\mathbf p}^2+i\epsilon,
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

As a function of complex $p^0$, the singularities are displaced poles:

$$
p^0=E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}+i0.
$$

The whole causal structure of the Feynman propagator is encoded in this analytic statement. The algebraic denominator is not enough; the side of the pole matters.

### Resolvents and spectral density

For a self-adjoint operator $H$, the resolvent

$$
R(z)=(H-z)^{-1}
$$

is analytic for $z$ off the spectrum. Its boundary values near the real axis define spectral information. Formally,

$$
\rho(\lambda)=\frac{1}{2\pi i}\operatorname{Tr}\left[R(\lambda+i0)-R(\lambda-i0)\right].
$$

This is complex analysis in operator clothing. Poles correspond to discrete eigenvalues; cuts correspond to continuous spectrum.

### Euclidean and Lorentzian correlators

Euclidean correlators are often easier to define and compute. Lorentzian correlators carry causal information. They are not related by a casual substitution unless the analytic domain is known. The correct statement is about holomorphic functions in complexified time variables and their boundary values on different real slices.

This is the same lesson again: the analytic function is the central object; the physical correlators are boundary values selected by a prescription.

## Common pitfalls

**Mistaking smooth for holomorphic.** A function can be $C^\infty$ in $x$ and $y$ and fail to be holomorphic. Check $\bar\partial f=0$, not just differentiability.

**Forgetting the domain.** Holomorphicity is always holomorphicity on a domain. The same formula can be analytic on one domain and multivalued or singular on another.

**Treating branch choices as physics.** A branch cut is a convention for making a multivalued function single-valued on a chosen domain. Branch points and monodromy are intrinsic; the drawn cut is not.

**Using Wick rotation as a symbolic rule.** Wick rotation is contour deformation. You must know where the singularities are and whether the arcs at infinity vanish.

**Ignoring growth at infinity.** Cauchy formulas and dispersion relations can pick up contributions from large arcs. Growth assumptions decide whether subtractions are needed.

**Losing orientation.** Holomorphic maps preserve orientation where $f'\neq0$; antiholomorphic maps reverse it. This matters in contour integrals, complex coordinates, and chiral factorization.

## Exercises

### Exercise 1: Cauchy–Riemann equations for powers

Show directly that $f(z)=z^n$ is holomorphic for nonnegative integer $n$, and find $f'(z)$.

<details><summary><strong>Solution</strong></summary>

Write the increment formula:

$$
\frac{(z+h)^n-z^n}{h}
=\sum_{k=1}^{n}\binom{n}{k}z^{n-k}h^{k-1}.
$$

Taking $h\to0$ gives

$$
f'(z)=nz^{n-1}.
$$

The limit is independent of the direction of $h$, so $z^n$ is holomorphic. This also implies the Cauchy–Riemann equations where the real and imaginary parts are expanded as polynomials in $x$ and $y$.

</details>

### Exercise 2: Why conjugation is not holomorphic

Use the definition of complex derivative to show that $f(z)=\bar z$ is not holomorphic anywhere.

<details><summary><strong>Solution</strong></summary>

At any $z_0$,

$$
\frac{\overline{z_0+h}-\bar z_0}{h}=\frac{\bar h}{h}.
$$

If $h$ is real, $\bar h/h=1$. If $h$ is purely imaginary, say $h=i\epsilon$, then $\bar h/h=-1$. The limit depends on the direction of approach, so the complex derivative does not exist anywhere.

</details>

### Exercise 3: Boundary value of a simple pole

Assuming the distribution identity

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x),
$$

compute the discontinuity of $1/(z)$ across the real axis at $x=0$ in the sense of boundary values.

<details><summary><strong>Solution</strong></summary>

The two boundary values are

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x),
$$

and

$$
\frac{1}{x-i0}=\operatorname{PV}\frac{1}{x}+i\pi\delta(x).
$$

Therefore

$$
\operatorname{Disc}\frac{1}{x}
=\frac{1}{x+i0}-\frac{1}{x-i0}
=-2\pi i\delta(x).
$$

The principal-value parts cancel. This is the distributional shadow of approaching the same pole from different sides.

</details>

## References

- L. Ahlfors, *Complex Analysis*. Classic reference for holomorphic functions, conformal maps, and Cauchy theory.
- E. Stein and R. Shakarchi, *Complex Analysis*. Clear modern introduction with good explanations of power series, contour integrals, and analytic continuation.
- J. B. Conway, *Functions of One Complex Variable*. Useful for a mathematically careful treatment of analytic functions and singularities.
- E. Titchmarsh, *The Theory of Functions*. Classic source for analytic function theory and boundary behavior.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Useful for analytic continuation and special functions.
- C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*. Useful for asymptotics and complex saddle methods.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for propagators, analytic structure, and scattering foundations.
- M. Srednicki, *Quantum Field Theory*. Useful for propagator prescriptions and spectral representations.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for practical contour methods and Wick rotation in perturbative QFT.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*. Standard reference for complex coordinates and holomorphic methods in two-dimensional CFT.

## Version history

- **2026-06-26:** Initial polished draft. Added holomorphicity, Wirtinger derivatives, Cauchy theory, power series, analytic continuation, singularities, boundary values, QFT examples, exercises, and a TikZ/SVG figure.
