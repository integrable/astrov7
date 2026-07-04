---
title: "Stationary Phase and Saddle Points"
description: "A QFT-oriented guide to stationary phase, steepest descent, saddle-point expansions, fluctuation determinants, zero modes, collective coordinates, negative modes, and semiclassical path integrals."
sidebar:
  label: "Stationary Phase and Saddle Points"
  order: 9
level: Graduate
status: "Polished draft"
source: "Standard asymptotic analysis and semiclassical path-integral treatments in Coleman, Srednicki, Weinberg, Schwartz, Zee, Zinn-Justin, and localization references."
topics:
  - stationary phase
  - saddle points
  - semiclassical expansion
  - fluctuation determinants
  - zero modes
canonicalTopics:
  - stationary-phase
  - saddle-point-expansion
  - semiclassical-path-integrals
  - fluctuation-determinants
researchStatus:
  established:
    - "Nondegenerate stationary-phase and steepest-descent expansions are standard asymptotic tools; in QFT they organize the semiclassical expansion around classical solutions."
  active:
    - "Complex saddles, integration cycles, Stokes phenomena, resurgence, gauge zero modes, determinant phases, and nonperturbative definitions remain subtle in advanced QFT applications."
---

## Summary

Stationary phase is the mathematical reason classical solutions dominate semiclassical path integrals. In finite dimension, consider an oscillatory integral

$$
I(\hbar)=\int d^n x\,a(x)\exp\left[\frac{i}{\hbar}S(x)\right],
\qquad \hbar\to0^+.
$$

Away from points where $\nabla S=0$, the phase oscillates rapidly and neighboring contributions cancel. The leading contributions come from stationary points

$$
\partial_iS(x_\ast)=0.
$$

If the Hessian

$$
H_{ij}=\partial_i\partial_jS(x_\ast)
$$

is nondegenerate, the leading stationary-phase formula is

$$
I(\hbar)
\sim
\sum_{x_\ast}
a(x_\ast)
\exp\left[\frac{i}{\hbar}S(x_\ast)\right]
\frac{(2\pi\hbar)^{n/2}e^{i\pi\sigma(H)/4}}{|\det H|^{1/2}}
\left[1+O(\hbar)\right],
$$

where $\sigma(H)$ is the number of positive eigenvalues minus the number of negative eigenvalues. The Euclidean version, usually called Laplace's method or steepest descent, replaces $e^{iS/\hbar}$ by $e^{-S_E/g}$ and is dominated by minima or appropriate steepest-descent contours.

In QFT the same structure becomes

$$
Z
\sim
\sum_{\phi_\ast}
\exp\left[-\frac{1}{\hbar}S_E[\phi_\ast]\right]
\left(\det{}' K_{\phi_\ast}\right)^{-1/2}
\int_{\mathcal M_\ast}d\mu_{\rm zero}\,
\left[1+O(\hbar)\right],
$$

where

$$
K_{\phi_\ast}(x,y)=
\left.\frac{\delta^2 S_E}{\delta\phi(x)\delta\phi(y)}\right|_{\phi=\phi_\ast}
$$

is the fluctuation operator. The prime means that zero modes have been removed and treated separately as collective coordinates.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram from an integral and saddle equation to quadratic fluctuations, determinants, zero modes, and higher-loop corrections.](/figures/math-toolkit/stationary-phase-saddle-flow.svg)

<figcaption>

A saddle-point expansion has three layers: solve the classical equation, integrate Gaussian fluctuations, then include interaction vertices around the saddle. Zero modes, negative modes, and integration contours are not optional bookkeeping; they decide what the formula means.

</figcaption>
</figure>

The practical slogan is:

$$
\text{saddle point} + \text{quadratic fluctuations} + \text{vertices}
=
\text{semiclassical expansion}.
$$

## Prerequisites

You should know [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), because the leading saddle approximation is a Gaussian integral in disguise. [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains how the determinant of the fluctuation operator enters, while [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explain common ways to regulate that determinant.

The distributional background from [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) is useful when fluctuation operators are written as kernels. The next page, [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/), explains why the change from fields to fluctuations and collective coordinates can itself produce determinant factors.

## Core idea

A rapidly oscillating integral usually cancels itself. The exception occurs near points where the phase varies slowly. If $S'(x_\ast)=0$, then near $x_\ast$,

$$
S(x_\ast+y)=S(x_\ast)+\frac12 y^iH_{ij}y^j+\frac{1}{3!}S_{ijk}y^iy^jy^k+\cdots.
$$

The linear term is absent precisely because $x_\ast$ is stationary. To leading order, the integral near the saddle becomes Gaussian. Higher derivatives of $S$ and derivatives of the prefactor $a(x)$ produce a controlled asymptotic series.

The QFT version is the same statement with more indices. Expand a field around a classical solution:

$$
\phi(x)=\phi_\ast(x)+\eta(x).
$$

If $\phi_\ast$ satisfies the Euler–Lagrange equation, the first variation vanishes,

$$
\left.\frac{\delta S_E}{\delta\phi(x)}\right|_{\phi=\phi_\ast}=0,
$$

and the action expands as

$$
S_E[\phi_\ast+\eta]
=S_E[\phi_\ast]
+\frac12\int d^d x\,d^d y\,\eta(x)K_{\phi_\ast}(x,y)\eta(y)
+S_{\rm int}^{(3+)}[\eta].
$$

The quadratic term gives the one-loop determinant. The cubic and higher terms give loop corrections around the saddle.

Thus perturbation theory around the vacuum and semiclassical instanton calculus are not different species of mathematics. They are saddle-point expansions around different classical solutions.

## Setup and conventions

This page uses two parallel conventions.

For convergent Euclidean integrals, write

$$
I(g)=\int_{\mathbb R^n}d^n x\,a(x)\exp\left[-\frac{1}{g}S(x)\right],
\qquad g\to0^+.
$$

Here $S$ is real, and a nondegenerate local minimum has positive Hessian. This is the cleanest setting for Gaussian determinants.

For oscillatory Lorentzian integrals, write

$$
I(\hbar)=\int d^n x\,a(x)\exp\left[\frac{i}{\hbar}S(x)\right].
$$

The Hessian need not be positive. Its signature contributes a phase, and the integral may require an $i\epsilon$ prescription or a chosen contour. QFT often starts with Lorentzian expressions but evaluates saddles using Euclidean continuation, especially for instantons and tunneling.

For a Euclidean bosonic path integral, use the formal notation

$$
Z=\int\mathcal D\phi\,e^{-S_E[\phi]/\hbar}.
$$

A saddle $\phi_\ast$ is a solution of

$$
\delta S_E[\phi_\ast]=0
$$

with the boundary conditions imposed by the problem. Boundary conditions are part of the saddle data. A field configuration that solves the local differential equation but violates the boundary condition is not a saddle of the variational problem.

For fermions and ghosts, quadratic fluctuation integrals give determinants or Pfaffians rather than inverse square roots of determinants. This page focuses first on bosonic saddle mechanics and then states the fermionic modifications.

## Laplace method in one dimension

Let

$$
I(g)=\int_{-\infty}^{\infty}dx\,a(x)e^{-S(x)/g},
\qquad g\to0^+,
$$

and suppose $S$ has a nondegenerate minimum at $x_\ast$:

$$
S'(x_\ast)=0,
\qquad
S''(x_\ast)>0.
$$

Near the saddle,

$$
S(x)=S_\ast+\frac12S_\ast''(x-x_\ast)^2+O((x-x_\ast)^3),
$$

and

$$
a(x)=a_\ast+O(x-x_\ast).
$$

The integral is dominated by a region of width

$$
|x-x_\ast|\sim \sqrt g.
$$

Keeping only the leading terms gives

$$
I(g)
\sim
a_\ast e^{-S_\ast/g}
\int_{-\infty}^{\infty}dx\,
\exp\left[-\frac{S_\ast''}{2g}(x-x_\ast)^2\right].
$$

Therefore

$$
I(g)
\sim
 a_\ast e^{-S_\ast/g}\sqrt{\frac{2\pi g}{S_\ast''}}.
$$

This formula already contains the whole saddle-point logic:

$$
\text{action at saddle}\quad +\quad
\text{inverse square root of Hessian}\quad +\quad
\text{expansion in }g.
$$

If several minima contribute, the leading answer is the sum of their leading contributions. If one minimum has smaller $S_\ast$, it dominates exponentially. If two saddles have equal action, both must be kept.

## Higher-dimensional steepest descent

For

$$
I(g)=\int d^n x\,a(x)e^{-S(x)/g},
$$

suppose $x_\ast$ is a nondegenerate minimum. Let

$$
H_{ij}=\partial_i\partial_jS(x_\ast),
\qquad H>0.
$$

Then

$$
S(x_\ast+y)=S_\ast+\frac12y^iH_{ij}y^j+O(y^3),
$$

and the leading term is

$$
I(g)
\sim
a(x_\ast)e^{-S_\ast/g}
\int d^n y\,\exp\left[-\frac{1}{2g}y^iH_{ij}y^j\right].
$$

Using the finite-dimensional Gaussian formula,

$$
\int d^n y\,\exp\left[-\frac{1}{2g}y^THy\right]
=(2\pi g)^{n/2}(\det H)^{-1/2},
$$

we find

$$
I(g)
\sim
(2\pi g)^{n/2}
\frac{a(x_\ast)e^{-S_\ast/g}}{\sqrt{\det H}}
\left[1+O(g)\right].
$$

The determinant is basis-independent once the measure $d^n x$ has been fixed. A change of variables can move factors between the Hessian and the measure; it cannot be ignored. This is the first hint that saddle-point expansions and measure Jacobians belong together.

The correction terms are generated by treating the cubic and higher parts of $S$ and the Taylor expansion of $a$ as interaction vertices with Gaussian covariance

$$
\langle y^iy^j\rangle_0=g(H^{-1})^{ij}.
$$

So the saddle expansion is a small Feynman-diagram expansion around a finite-dimensional classical solution. In QFT, this becomes the loop expansion around a background field.

## Stationary phase and the Hessian phase

For an oscillatory integral,

$$
I(\hbar)=\int d^n x\,a(x)e^{iS(x)/\hbar},
$$

a nondegenerate stationary point gives a Gaussian integral with phase. Diagonalize the Hessian. Each positive eigenvalue contributes

$$
\int_{-\infty}^{\infty}dy\,e^{i\lambda y^2/(2\hbar)}
=e^{i\pi/4}\sqrt{\frac{2\pi\hbar}{\lambda}},
\qquad \lambda>0,
$$

with the contour understood by the usual oscillatory prescription. Each negative eigenvalue contributes $e^{-i\pi/4}$ times the corresponding absolute-value determinant factor.

Thus

$$
I(\hbar)
\sim
\sum_{x_\ast}
 a(x_\ast)e^{iS(x_\ast)/\hbar}
\frac{(2\pi\hbar)^{n/2}e^{i\pi\sigma(H)/4}}{|\det H|^{1/2}}
\left[1+O(\hbar)\right],
$$

where

$$
\sigma(H)=n_+(H)-n_-(H).
$$

This phase is the finite-dimensional ancestor of determinant phases, eta invariants, Maslov indices, and related sign data in field theory. One should not reduce a Lorentzian determinant to "just the absolute value" unless the phase is irrelevant for the question.

## From saddle points to loop expansion

A Euclidean scalar path integral has the formal form

$$
Z=\int\mathcal D\phi\,e^{-S_E[\phi]/\hbar}.
$$

Let $\phi_\ast$ solve the Euclidean equation of motion. Write

$$
\phi=\phi_\ast+\sqrt\hbar\,\eta.
$$

The factor $\sqrt\hbar$ is a useful bookkeeping choice. Expanding gives

$$
S_E[\phi_\ast+\sqrt\hbar\eta]
=S_E[\phi_\ast]
+\frac{\hbar}{2}\langle\eta,K\eta\rangle
+\hbar^{3/2}S_3[\eta]
+\hbar^2S_4[\eta]
+\cdots.
$$

Then

$$
Z_\ast
=e^{-S_E[\phi_\ast]/\hbar}
\int\mathcal D\eta\,
\exp\left[-\frac12\langle\eta,K\eta\rangle
-\sqrt\hbar S_3[\eta]
-\hbar S_4[\eta]-\cdots\right].
$$

The leading Gaussian integral gives

$$
Z_\ast^{\text{one-loop}}
\propto
 e^{-S_E[\phi_\ast]/\hbar}(\det K)^{-1/2}.
$$

The interaction terms $S_3,S_4,\ldots$ generate loop corrections around the saddle. The small parameter is $\hbar$ or, in many QFT applications, a coupling that multiplies the action as $S/g^2$.

For example, if

$$
S_E[\phi]=\frac{1}{g^2}\widehat S_E[\phi],
$$

then the semiclassical expansion is an expansion in powers of $g^2$ around saddle points of $\widehat S_E$.

## One-loop effective action

The same expansion gives the standard one-loop effective action around a background field. Suppose

$$
\phi=\varphi+\eta,
$$

and expand the action as

$$
S[\varphi+\eta]
=S[\varphi]
+\int dx\,\frac{\delta S}{\delta\varphi(x)}\eta(x)
+\frac12\int dx\,dy\,\eta(x)S^{(2)}[\varphi](x,y)\eta(y)+\cdots.
$$

If $\varphi$ is chosen as a background in the effective-action construction, the Gaussian integration over $\eta$ gives schematically

$$
\Gamma[\varphi]
=S[\varphi]
+\frac{\hbar}{2}\operatorname{Tr}\log S^{(2)}[\varphi]
+O(\hbar^2)
$$

for a real bosonic field. For fermions, the corresponding Gaussian integral contributes with the opposite determinant power, so a Dirac fermion gives a schematic term

$$
\Gamma_{\rm fermion}^{(1)}[\varphi]
=-\hbar\operatorname{Tr}\log D[\varphi]
$$

for the appropriate Dirac-type operator $D[\varphi]$. For real fermions, Pfaffians and their signs are the natural objects.

This formula is a saddle-point formula, not a magic definition of $\operatorname{Tr}\log$. The trace log must be regulated, zero modes must be separated, and gauge redundancies must be fixed.

## Zero modes and collective coordinates

A zero mode is an eigenvector of the Hessian with eigenvalue zero:

$$
K\psi_0=0.
$$

In finite dimension, if $H$ has a zero eigenvalue, then

$$
\det H=0,
$$

and the Gaussian formula is invalid. In a path integral, zero modes usually indicate that the saddle is not isolated. Instead, it belongs to a family of physically equivalent or physically distinct saddles.

Suppose a family of saddles is parameterized by collective coordinates $a^A$:

$$
\phi_\ast(x;a),
\qquad A=1,\ldots,m.
$$

The tangent vectors

$$
\psi_A(x)=\frac{\partial\phi_\ast(x;a)}{\partial a^A}
$$

are zero modes when changing $a^A$ leaves the action stationary. The correct semiclassical expression separates these directions:

$$
\mathcal D\phi
\quad\leadsto\quad
 d^m a\,J(a)\,\mathcal D\eta_\perp.
$$

Then

$$
Z_\ast
\sim
 e^{-S_E[\phi_\ast]/\hbar}
\int d^m a\,J(a)
\left(\det{}'K\right)^{-1/2}
\left[1+O(\hbar)\right].
$$

The prime on the determinant means that the zero eigenvalues have been omitted. The Jacobian $J(a)$ is the volume element induced on the moduli space of saddles by the field-space metric used in the measure. In the simplest bosonic case, if the zero-mode inner-product matrix is

$$
G_{AB}=\int d^d x\,\psi_A(x)\psi_B(x),
$$

then the collective-coordinate volume element contains

$$
\sqrt{\det G_{AB}}\,d^m a,
$$

up to normalization conventions inherited from the original path-integral measure.

This is why "zero modes are removed from the determinant" is only half a sentence. Removed and replaced by what? By an integral over collective coordinates with the correct Jacobian.

## Gauge zero modes

Gauge theories add a special kind of zero mode. If two field configurations differ by a gauge transformation, they represent the same physical point. The action is constant along gauge orbits, so the quadratic fluctuation operator has gauge zero modes before gauge fixing.

These zero modes should not be integrated as physical moduli. They represent overcounting. The correct procedure is to divide by the gauge-group volume or impose a gauge condition and include the corresponding Faddeev–Popov determinant.

At the level of this chapter, the important structural point is:

$$
\text{physical zero mode} \neq \text{gauge redundancy}.
$$

Both create zero eigenvalues of a naive Hessian. The first becomes a collective coordinate. The second becomes gauge fixing and ghosts. Confusing them is a reliable way to get nonsense determinants.

## Negative modes and unstable saddles

A negative mode is an eigenvector of the Euclidean Hessian with negative eigenvalue. If

$$
K\psi_-=-\lambda\psi_- ,
\qquad \lambda>0,
$$

then the Euclidean Gaussian factor along that direction looks like

$$
\int dc\,\exp\left(+\frac{\lambda c^2}{2\hbar}\right),
$$

which diverges along the real contour.

This does not necessarily mean the saddle is useless. It means the original real integration cycle is not a convergent steepest-descent contour through that saddle. In false-vacuum decay, for example, the bounce has one negative mode; the contour prescription produces an imaginary part of the false-vacuum energy, which is interpreted as a decay rate.

The rule of thumb is:

$$
\text{positive Hessian} \to \text{stable Gaussian},
\qquad
\text{zero mode} \to \text{collective coordinate or redundancy},
\qquad
\text{negative mode} \to \text{contour and instability data}.
$$

A determinant without this eigenvalue bookkeeping is not a semiclassical answer.

## Complex saddles and steepest-descent contours

In many important integrals, the relevant saddles are complex even when the original integration variable is real. The modern language is to complexify the variables and decompose the integration cycle into steepest-descent cycles, often called Lefschetz thimbles.

For a schematic integral

$$
I(g)=\int_C dz\,e^{-S(z)/g},
$$

a complex saddle satisfies

$$
\frac{dS}{dz}=0.
$$

But not every saddle contributes to a given contour $C$. The coefficient of a saddle depends on how $C$ decomposes into steepest-descent cycles. As parameters vary, this decomposition can jump across Stokes walls. That is Stokes phenomenon.

For introductory QFT calculations, this may sound like overkill. But it becomes essential in tunneling, real-time path integrals, finite-density sign problems, resurgence, complex Chern–Simons theory, and many supersymmetric or holographic saddle analyses.

A safe page-level principle is:

$$
\text{saddle equation alone does not define the saddle contribution}.
$$

The integration cycle is part of the problem.

## Relation to asymptotic series and nonperturbative terms

Saddle expansions are usually asymptotic, not convergent. A typical saddle contribution has the form

$$
Z_\ast(g)
\sim
 e^{-S_\ast/g}\sum_{k\ge0}c_k g^k.
$$

Even if every coefficient $c_k$ can be computed, the series often has zero radius of convergence. This is not a defect of the method; it is one way nonperturbative physics enters.

Different saddles can be exponentially separated:

$$
\frac{Z_{\ast,2}}{Z_{\ast,1}}
\sim
\exp\left[-\frac{S_{\ast,2}-S_{\ast,1}}{g}\right].
$$

No ordinary power series in $g$ around saddle 1 can produce this factor. This is the basic reason instantons, bounces, solitons, and other nontrivial saddles are called nonperturbative relative to a vacuum perturbation series.

In resurgence theory, perturbative large-order behavior around one saddle can encode information about other saddles. That subject belongs to a later asymptotics and resurgence chapter, but the entrance door is already here.

## Common pitfalls

**Forgetting that the saddle must obey the boundary conditions.** A classical solution of the local equation is not automatically a saddle of the variational problem. Boundary terms and allowed variations matter.

**Using the Gaussian determinant when the Hessian has zero modes.** A zero eigenvalue invalidates the ordinary determinant formula. Separate the zero modes and replace them by collective coordinates or gauge fixing.

**Treating gauge zero modes as physical moduli.** Gauge directions are overcounting, not physical degeneracy. They require gauge fixing and Faddeev–Popov determinants, not integration over new physical saddles.

**Dropping determinant phases without checking the observable.** In Lorentzian signature and for non-positive operators, determinant phases can carry physical information, including anomalies and eta-invariant data.

**Assuming every solution of the saddle equation contributes.** The integration contour determines which saddles contribute. Complex saddles and Stokes jumps are real issues, not aesthetic decorations.

**Confusing perturbative loop order with powers of the original coupling.** The loop-counting parameter depends on how the action is normalized. In gauge theory, the classical action often carries an overall $1/g^2$, so semiclassical powers and diagrammatic powers must be tracked carefully.

**Calling a divergent Gaussian integral a small correction.** A negative mode is not a harmless sign. It signals instability or a contour problem and must be interpreted before using the saddle.

## Relations to other pages

[Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) gives the exact finite-dimensional formulas that produce the leading saddle determinant. [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains the spectral meaning of $\det K$ in field theory, while [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explains how one-loop UV divergences arise from local short-time coefficients.

[Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/) and [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) give the fermionic analogues of the bosonic determinant factors used here. [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/) explains the measure factors that appear when one changes from fields to fluctuations, collective coordinates, or new variables.

For analytic prerequisites, [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/) explains why operator domains and boundary conditions cannot be swept under the rug. For physics applications, this page later feeds into instantons, false-vacuum decay, solitons, localization, loop expansion, and semiclassical quantization.

## Research status

The finite-dimensional stationary-phase and steepest-descent expansions are established mathematical tools. Their extension to perturbative QFT around a fixed saddle is also standard once a regulator and renormalization scheme are specified.

The frontier is not the leading formula; it is the global and infinite-dimensional meaning of the formula. Which complex saddles contribute? What is the correct integration cycle? How do perturbative expansions around different saddles talk to each other? How are determinant phases and zero-mode measures defined globally? How does gauge fixing interact with moduli spaces and boundaries? These questions remain central in resurgence, localization, gauge theory, quantum gravity, and nonperturbative QFT.

## Exercises

### Exercise 1: Leading Laplace approximation

Let

$$
I(g)=\int_{-\infty}^{\infty}dx\,e^{-(x^2/2+x^4)/g}.
$$

Find the leading small-$g$ asymptotic behavior.

<details><summary><strong>Solution</strong></summary>

The action is

$$
S(x)=\frac12x^2+x^4.
$$

The stationary equation is

$$
S'(x)=x+4x^3=x(1+4x^2)=0.
$$

The only real stationary point is $x_\ast=0$. It is a nondegenerate minimum because

$$
S''(0)=1.
$$

The leading Laplace approximation is therefore

$$
I(g)\sim e^{-S(0)/g}\sqrt{\frac{2\pi g}{S''(0)}}
=\sqrt{2\pi g}.
$$

The quartic term contributes to subleading powers of $g$.

</details>

### Exercise 2: First correction from a quartic vertex

Using Gaussian expectation values, compute the first correction to

$$
I(g)=\int_{-\infty}^{\infty}dx\,e^{-(x^2/2+x^4)/g}.
$$

Write the result through order $g$ relative to the leading term.

<details><summary><strong>Solution</strong></summary>

Write

$$
I(g)=\int dx\,e^{-x^2/(2g)}e^{-x^4/g}.
$$

For small $g$,

$$
e^{-x^4/g}=1-\frac{x^4}{g}+O(g^2)
$$

because typical Gaussian fluctuations have $x\sim\sqrt g$, so $x^4/g\sim g$.

The normalized Gaussian expectation with variance $g$ satisfies

$$
\langle x^4\rangle_0=3g^2.
$$

Thus

$$
I(g)=\sqrt{2\pi g}\left(1-\frac{\langle x^4\rangle_0}{g}+O(g^2)\right)
=\sqrt{2\pi g}\left(1-3g+O(g^2)\right).
$$

So the first relative correction is $-3g$.

</details>

### Exercise 3: Hessian determinant in two dimensions

Let

$$
S(x,y)=\frac12(ax^2+2bxy+cy^2),
$$

with $a>0$ and $ac-b^2>0$. Compute the leading small-$g$ value of

$$
I(g)=\int_{\mathbb R^2}dx\,dy\,e^{-S(x,y)/g}.
$$

<details><summary><strong>Solution</strong></summary>

The Hessian matrix is

$$
H=\begin{pmatrix}a&b\\ b&c\end{pmatrix}.
$$

The conditions $a>0$ and $ac-b^2>0$ make $H$ positive definite. The action is already quadratic, so the Gaussian formula is exact:

$$
I(g)=(2\pi g)^{2/2}(\det H)^{-1/2}
=\frac{2\pi g}{\sqrt{ac-b^2}}.
$$

</details>

### Exercise 4: A finite-dimensional zero mode

Consider

$$
S(x,y)=\frac12x^2
$$

on a rectangular domain $x\in\mathbb R$ and $y\in[0,L]$. Explain why the Hessian determinant vanishes and compute the integral

$$
I(g)=\int_{-\infty}^{\infty}dx\int_0^Ldy\,e^{-x^2/(2g)}.
$$

<details><summary><strong>Solution</strong></summary>

The Hessian is

$$
H=\begin{pmatrix}1&0\\0&0\end{pmatrix},
$$

so $\det H=0$. The $y$ direction is a zero mode because the action is independent of $y$.

The integral separates:

$$
I(g)=\left(\int_{-\infty}^{\infty}dx\,e^{-x^2/(2g)}\right)
\left(\int_0^Ldy\right).
$$

Therefore

$$
I(g)=\sqrt{2\pi g}\,L.
$$

This is the finite-dimensional model for replacing a zero-mode determinant by a collective-coordinate volume.

</details>

### Exercise 5: One-loop determinant from a scalar saddle

Let a Euclidean scalar action have a classical saddle $\phi_\ast$ and expansion

$$
S_E[\phi_\ast+\eta]=S_E[\phi_\ast]+\frac12\langle\eta,K\eta\rangle+O(\eta^3),
$$

with $K$ positive and no zero modes. Show the leading saddle contribution to $Z$ is proportional to

$$
e^{-S_E[\phi_\ast]/\hbar}(\det K)^{-1/2}.
$$

<details><summary><strong>Solution</strong></summary>

Keeping only the quadratic term gives

$$
Z_\ast\approx e^{-S_E[\phi_\ast]/\hbar}
\int\mathcal D\eta\,
\exp\left[-\frac{1}{2\hbar}\langle\eta,K\eta\rangle\right].
$$

In a finite-dimensional regulator, expand $\eta$ in modes so that the quadratic form becomes

$$
\frac12\sum_n\lambda_n c_n^2.
$$

Then

$$
\prod_n\int dc_n\,e^{-\lambda_nc_n^2/(2\hbar)}
\propto
\prod_n\lambda_n^{-1/2}
=(\det K)^{-1/2},
$$

where normalization constants independent of $K$ have been suppressed. Thus

$$
Z_\ast\propto e^{-S_E[\phi_\ast]/\hbar}(\det K)^{-1/2}.
$$

In continuum QFT, the determinant must be regulated.

</details>

## References

- S. Coleman, *Aspects of Symmetry*. Semiclassical functional integration, instantons, false-vacuum decay, collective coordinates, and determinant ratios.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Functional integration, loop expansion, generating functionals, and saddle-point reasoning.
- M. Srednicki, *Quantum Field Theory*. Path integrals, loop expansion, functional determinants, and semiclassical approximations.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Effective action, stationary-phase expansion, external-field methods, gauge fixing, and one-loop determinants.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Path integrals, Schwinger proper time, background-field methods, and effective actions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, steepest descent, saddle-point expansions, instantons, large-order behavior, and renormalization.
- A. Zee, *Quantum Field Theory in a Nutshell*. Physical intuition for saddle points, instantons, determinants, and path-integral methods.
- V. Pestun et al., *Localization Techniques in Quantum Field Theories*. Supersymmetric localization as an exact saddle-point computation with one-loop determinants and zero-mode subtleties.

## Version history

- 2026-06-24: First polished draft. Introduced finite-dimensional stationary phase and steepest descent, path-integral saddle expansions, one-loop determinants, zero modes, collective coordinates, gauge zero modes, negative modes, complex saddles, Stokes phenomena, and exercises.
