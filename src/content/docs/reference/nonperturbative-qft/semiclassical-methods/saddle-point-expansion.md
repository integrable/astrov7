---
title: "Saddle-Point Expansion"
description: "Derives the semiclassical expansion of a Euclidean path integral around classical saddles, including fluctuation operators, determinants, zero modes, and validity conditions."
sidebar:
  label: "Saddle-Point Expansion"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman; Zinn-Justin; Mariño; Shifman; Srednicki."
topics:
  - saddle-point expansion
  - semiclassical approximation
  - path integrals
  - fluctuation operators
  - functional determinants
  - zero modes
  - collective coordinates
  - instantons
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - saddle-point-expansion
  - functional-integral-methods
researchStatus:
  established:
    - "The saddle-point expansion is a standard asymptotic expansion of regulated finite-dimensional integrals and Euclidean path integrals around stationary configurations of the action."
  active:
    - "Complex saddles, real-time contours, resurgence, renormalons, and semiclassical claims in strongly coupled theories remain delicate and often research-level."
---

## Summary

The saddle-point expansion is the basic semiclassical approximation to a path integral. For a Euclidean bosonic path integral written with $\hbar$ displayed,

$$
Z=\int \mathcal D\phi\,e^{-S_E[\phi]/\hbar},
$$

one expands around classical Euclidean solutions $\phi_s$ satisfying

$$
\left.\frac{\delta S_E}{\delta\phi}\right|_{\phi_s}=0.
$$

Near such a saddle, write

$$
\phi=\phi_s+\sqrt{\hbar}\,\eta.
$$

Then, schematically,

$$
Z
\sim
\sum_s
 e^{-S_E[\phi_s]/\hbar}
 (\det{}^{\prime}\Delta_s)^{-1/2}
 d\mu_{\text{zero}}
 \left(1+O(\hbar)\right),
$$

where $\Delta_s=S_E''[\phi_s]$ is the quadratic fluctuation operator, the prime means that zero modes are removed from the determinant, and $d\mu_{\text{zero}}$ is the measure on the collective coordinates associated with those zero modes. Normalization constants, determinant ratios, ghosts, counterterms, and fermion determinants depend on the theory and regularization.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic map of the semiclassical saddle-point expansion: the path integral is decomposed into saddles, each contributing a classical weight, determinant, zero-mode measure, and loop corrections.](/figures/nonperturbative-qft/saddle-point-expansion-anatomy.svg)

<figcaption>

The saddle-point expansion decomposes a regulated path integral into neighborhoods of stationary configurations. Around each saddle $\phi_s$, the leading factors are the classical weight, the Gaussian determinant of the Hessian $\Delta_s$, the zero-mode or collective-coordinate measure, and higher-loop corrections.

</figcaption>
</figure>

This method is one of the main ways perturbative technology produces genuinely nonperturbative terms such as $e^{-S_{\text{inst}}/\hbar}$ or $e^{-8\pi^2/g^2}$. The method is powerful precisely because it is not ordinary perturbation theory around the trivial vacuum. The catch is that it is local in field space: every saddle formula must state its boundary conditions, zero modes, negative modes, gauge fixing, and control parameter.

## Prerequisites

You should know [Conventions and Notation](/nonperturbative-qft/conventions/), [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), and [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/).

It is also helpful to have read [Semiclassical Versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/) and [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), since saddle methods are often used to compute gaps, tunneling splittings, and exponentially small amplitudes.

## Core idea

A path integral is an infinite-dimensional analogue of an ordinary integral. If a large parameter suppresses fluctuations, most configurations cancel or are exponentially suppressed, and the dominant contributions come from neighborhoods of stationary points of the action.

The slogan is

$$
\text{path integral}
\approx
\text{sum of local Gaussian integrals around classical saddles}
+
\text{systematic corrections}.
$$

The “nonperturbative” part enters through the classical action of a nontrivial saddle. If the action has the form

$$
S_E[\phi]=\frac{1}{g^2}\,\widetilde S_E[\phi],
$$

then a saddle contributes an exponential factor

$$
\exp\left(-\frac{\widetilde S_E[\phi_s]}{g^2}\right).
$$

No power series in $g^2$ around $g=0$ can reproduce such a term. This is the elementary mathematical reason instantons, bounces, and some soliton effects are invisible to ordinary perturbation theory.

## Setup and conventions

We use Euclidean signature and write the path-integral weight as $e^{-S_E/\hbar}$. The symbol $\hbar$ is a bookkeeping parameter. In most QFT applications one sets $\hbar=1$, and the small parameter is instead a weak coupling $g$, a large charge, a large volume action, or $1/N$.

To avoid hiding analytic issues, imagine first that the theory has been regulated so the path integral is a finite-dimensional integral over variables $\phi_i$. The continuum expressions are then formal shorthand for the regulated expressions followed by renormalization and continuum limits.

Assume for the moment that:

1. the Euclidean action is real and bounded below in the sector of interest;
2. the saddle is isolated after quotienting exact symmetries;
3. the quadratic fluctuation operator has no negative modes;
4. ultraviolet divergences are regulated;
5. the boundary conditions defining the path integral are fixed.

Every item on this list can fail in important physical examples. Zero modes, gauge redundancy, fermions, bounce negative modes, and complex saddles are not afterthoughts. They are the cases where the schematic formula must be refined.

## Finite-dimensional warm-up

Consider an ordinary integral

$$
I(\hbar)=\int_{\mathbb R^n}d^n x\,e^{-S(x)/\hbar},
$$

where $S(x)$ has an isolated nondegenerate minimum at $x=x_s$. The saddle condition is

$$
\left.\frac{\partial S}{\partial x^i}\right|_{x_s}=0.
$$

Expanding around the saddle gives

$$
S(x_s+y)
=S_s+\frac12H_{ij}y^iy^j+\frac{1}{3!}S_{ijk}y^iy^jy^k+\frac{1}{4!}S_{ijkl}y^iy^jy^ky^l+\cdots,
$$

where

$$
S_s=S(x_s),
\qquad
H_{ij}=\left.\frac{\partial^2S}{\partial x^i\partial x^j}\right|_{x_s}.
$$

At leading order,

$$
I(\hbar)
\approx
 e^{-S_s/\hbar}
\int d^n y\,
\exp\left(-\frac{1}{2\hbar}H_{ij}y^iy^j\right).
$$

If $H$ is positive definite, the Gaussian integral is

$$
I(\hbar)
\approx
 e^{-S_s/\hbar}
\frac{(2\pi\hbar)^{n/2}}{\sqrt{\det H}}
\left(1+O(\hbar)\right).
$$

This is the prototype of every semiclassical formula. The classical action gives the leading exponential; the Hessian gives the one-loop determinant; cubic and higher derivatives give loop corrections.

If there are several isolated saddles, the integral is approximated by a sum over their contributions, provided the integration contour can be deformed to the corresponding steepest-descent cycles and no relevant saddle is missed.

## From ordinary integrals to path integrals

For a field theory, the saddle condition becomes the Euclidean Euler–Lagrange equation

$$
\frac{\delta S_E}{\delta\phi(x)}=0.
$$

Let $\phi_s$ be a solution satisfying the boundary conditions of the problem. Expand

$$
\phi(x)=\phi_s(x)+\sqrt{\hbar}\,\eta(x).
$$

The action expansion has the form

$$
\frac{1}{\hbar}S_E[\phi_s+\sqrt{\hbar}\,\eta]
=
\frac{S_E[\phi_s]}{\hbar}
+\frac12(\eta,\Delta_s\eta)
+\frac{\sqrt{\hbar}}{3!}S_s^{(3)}[\eta^3]
+\frac{\hbar}{4!}S_s^{(4)}[\eta^4]
+\cdots.
$$

Here

$$
(\eta,\Delta_s\eta)
=
\int d^dx\,d^dy\,\eta(x)\Delta_s(x,y)\eta(y),
$$

or, for a local action, a differential-operator expression such as

$$
(\eta,\Delta_s\eta)=\int d^dx\,\eta(x)\Delta_s\eta(x).
$$

The linear term vanishes because $\phi_s$ solves the saddle equation. If the linear term does not vanish, one is not expanding around a saddle.

The leading Gaussian functional integral is formally

$$
\int\mathcal D\eta\,e^{-\frac12(\eta,\Delta_s\eta)}
\propto
(\det\Delta_s)^{-1/2}.
$$

In a continuum QFT, this determinant is divergent until the theory is regulated and renormalized. In practice, meaningful semiclassical answers usually involve determinant ratios, counterterms, or a specified subtraction scheme, for example

$$
\left(\frac{\det\Delta_{\text{ref}}}{\det{}^{\prime}\Delta_s}\right)^{1/2}.
$$

The reference operator $\Delta_{\text{ref}}$ is often the fluctuation operator around the vacuum or another background used to normalize the transition amplitude.

## Loop counting

The rescaling $\phi=\phi_s+\sqrt{\hbar}\,\eta$ makes loop counting visible. The quadratic term is order $\hbar^0$ in the exponent, while higher interaction vertices carry powers of $\sqrt{\hbar}$.

The expansion around a saddle is therefore a perturbation theory in the fluctuation field $\eta$, but not necessarily around the trivial vacuum. Its propagator is the inverse of the background operator,

$$
G_s=\Delta_s^{-1},
$$

with zero modes removed when present. Its vertices are functional derivatives of the action evaluated on the saddle.

If the action is written as

$$
S_E[\phi]=\frac{1}{g^2}\widetilde S_E[\phi],
$$

then the more natural fluctuation variable is

$$
\phi=\phi_s+g\eta.
$$

The expansion becomes

$$
Z_s
\sim
\exp\left(-\frac{\widetilde S_E[\phi_s]}{g^2}\right)
(\det{}^{\prime}\widetilde\Delta_s)^{-1/2}
\left(1+c_1g^2+c_2g^4+\cdots\right),
$$

again suppressing zero-mode measures and normalization factors. This is the common gauge-theory instanton pattern: a nonanalytic exponential times an ordinary asymptotic series.

## Anatomy of the semiclassical contribution

A more honest schematic contribution of one bosonic saddle is

$$
Z_s
=
 e^{-S_E[\phi_s]/\hbar}
\times
\mathcal N_s
\times
(\det{}^{\prime}\Delta_s)^{-1/2}
\times
\int_{\mathcal M_s}d\mu_s
\times
\bigl(1+\hbar c_1+\hbar^2c_2+\cdots\bigr).
$$

The pieces are:

| Factor | Meaning |
|---|---|
| $e^{-S_E[\phi_s]/\hbar}$ | Classical saddle weight. This is often the source of nonperturbative exponential dependence. |
| $\mathcal N_s$ | Normalization, counterterms, and possible determinant ratios relative to a reference background. |
| $(\det{}^{\prime}\Delta_s)^{-1/2}$ | Gaussian integral over nonzero bosonic fluctuations. |
| $\int_{\mathcal M_s}d\mu_s$ | Integral over exact collective coordinates or moduli of the saddle. |
| $1+\hbar c_1+\cdots$ | Higher-loop fluctuation corrections around the saddle. |

For fermions, Gaussian Grassmann integration gives determinants in the numerator rather than denominator. If the fermion quadratic operator is $D_s$, then schematically

$$
\int\mathcal D\bar\psi\mathcal D\psi\,e^{-\bar\psi D_s\psi}
=\det D_s.
$$

Fermion zero modes require insertions or external sources to soak them up. Otherwise the corresponding path integral contribution can vanish.

## Zero modes and collective coordinates

Suppose $\Delta_s$ has a zero mode $Z_a(x)$:

$$
\Delta_s Z_a=0.
$$

A common reason is that the saddle comes in a continuous family $\phi_s(x;q)$ labeled by collective coordinates $q^a$, such as a center position, global orientation, size parameter, or gauge orientation. Then

$$
Z_a(x)=\frac{\partial\phi_s(x;q)}{\partial q^a}
$$

is tangent to the family of saddles.

The Gaussian integral over a zero eigenvalue is not defined. The correct procedure is to remove the zero modes from the determinant and integrate over the collective coordinates. The induced metric on the moduli space is

$$
G_{ab}(q)=\int d^dx\,Z_a(x;q)Z_b(x;q),
$$

for a single real scalar with the simplest field-space metric. More generally, $G_{ab}$ uses the theory’s kinetic metric and includes gauge constraints.

Schematically, the zero-mode factor is

$$
d\mu_{\text{zero}}(q)
\propto
\frac{d^k q}{(2\pi\hbar)^{k/2}}\sqrt{\det G(q)},
$$

up to measure conventions and normalization factors. In instanton calculations, these factors are not decoration: they produce powers of the instanton action, spacetime volume factors, and group-volume factors.

## Negative modes and bounces

If $\Delta_s$ has a negative eigenvalue, the saddle is not a local minimum of the Euclidean action. The ordinary real Gaussian integral diverges along that direction. This does not automatically mean the saddle is useless.

The most important example is a false-vacuum bounce. A bounce has one negative mode. Its contribution is interpreted by analytic continuation of the steepest-descent contour and produces an imaginary part in the false-vacuum energy. That imaginary part determines the decay rate.

The rough lesson is:

| Number of negative modes | Usual interpretation |
|---:|---|
| 0 | Stable saddle contributing to a partition function or transition amplitude. |
| 1 | Possible bounce contribution to metastable decay, with a special contour prescription. |
| More than 1 | Usually not the dominant decay saddle for the standard false-vacuum problem, though context matters. |

Negative modes are therefore a diagnostic of what the saddle computes. A minimum and a bounce do not answer the same physical question.

## Gauge theories and ghosts

In a gauge theory, the field space contains gauge orbits: many configurations represent the same physical point. Expanding naively around a gauge-field saddle produces zero modes along gauge directions. These are not physical collective coordinates.

One must fix a gauge and include the corresponding Faddeev–Popov determinant. Around a background gauge field $A_s$, a typical background gauge condition has the form

$$
D_s^\mu a_\mu=0,
$$

where $a_\mu$ is the fluctuation and $D_s$ is the covariant derivative in the background. The one-loop factor then includes both a gauge-field determinant and a ghost determinant. Schematically,

$$
Z_s^{\text{1-loop}}
\sim
\frac{\det\Delta_{\text{ghost},s}}{(\det{}^{\prime}\Delta_{\text{gauge},s})^{1/2}},
$$

with physical zero modes treated separately.

This is why instanton measures in Yang–Mills theory are more than “classical action plus determinant.” They also encode gauge orientations, translations, scale modes when present, ghost factors, and renormalization of the coupling.

## Boundary conditions and sectors

A saddle is always a saddle of a particular problem. The same differential equation may have different relevant solutions depending on boundary conditions.

Examples:

| Problem | Relevant saddle data |
|---|---|
| Vacuum partition function | Periodic Euclidean time, sector sum, vacuum boundary conditions. |
| Tunneling amplitude | Initial and final wavefunction support or boundary field values. |
| Finite-temperature gauge theory | Periodic bosons, antiperiodic fermions, thermal holonomy. |
| False-vacuum decay | Bounce approaching the false vacuum at Euclidean infinity. |
| Topological-sector sum | Integer charge, winding, or bundle data fixed or summed. |

A field configuration that solves the equations but violates the boundary conditions does not contribute to the path integral being computed.

## What makes the approximation controlled?

The saddle expansion is controlled when the local fluctuation expansion is parametrically small and the relevant saddle set is understood. Common control parameters include:

| Control parameter | Example |
|---|---|
| Small $\hbar$ | Quantum mechanics in the WKB regime. |
| Small coupling $g$ with $S_E=\widetilde S_E/g^2$ | Yang–Mills instantons at weak coupling. |
| Large action | Soliton or domain-wall configurations with large classical action. |
| Large $N$ | Vector models, matrix models, and some gauge theories. |
| Dilute density | Rare instantons or defects with weak interactions. |
| Large charge or spin | Semiclassical sectors in some CFTs and many-body systems. |

The warning label is equally important. A saddle calculation is not controlled just because it produces an appealing exponential. One must check that fluctuations are small, collective coordinates are correctly integrated, competing saddles are not equally important, and renormalization has not destroyed the claimed hierarchy.

## A minimal scalar-field example

Take a single real scalar field in Euclidean space with action

$$
S_E[\phi]=\int d^dx\left[\frac12(\partial_\mu\phi)^2+V(\phi)\right].
$$

The saddle equation is

$$
-\partial^2\phi_s+V'(\phi_s)=0.
$$

Let

$$
\phi=\phi_s+\sqrt{\hbar}\,\eta.
$$

Expanding the action gives

$$
S_E[\phi_s+\sqrt{\hbar}\,\eta]
=
S_E[\phi_s]
+\frac{\hbar}{2}\int d^dx\,\eta\left[-\partial^2+V''(\phi_s)\right]\eta
+O(\hbar^{3/2}).
$$

Thus the fluctuation operator is

$$
\Delta_s=-\partial^2+V''(\phi_s(x)).
$$

The one-loop contribution is formally

$$
Z_s^{\text{1-loop}}
\propto
 e^{-S_E[\phi_s]/\hbar}
\left(\det{}^{\prime}\left[-\partial^2+V''(\phi_s)\right]\right)^{-1/2},
$$

with zero modes removed if the saddle has translation or internal moduli. For the vacuum saddle $\phi_s=\phi_0$ constant, this reduces to the familiar Gaussian fluctuation operator

$$
\Delta_0=-\partial^2+m^2,
\qquad
m^2=V''(\phi_0).
$$

For a kink, bounce, or instanton-like solution, $V''(\phi_s(x))$ is position-dependent, so the determinant is a genuine spectral problem in a nontrivial background.

## Checks

A proposed saddle calculation should pass at least these checks.

| Check | What can go wrong |
|---|---|
| Saddle equation | A missed boundary term or source leaves a nonzero linear term. |
| Quadratic operator | Wrong signs can turn a stable mode into a fake negative mode. |
| Zero-mode count | Symmetry modes accidentally included in the determinant make the answer vanish or diverge. |
| Gauge fixing | Gauge copies are counted as physical configurations. |
| Dimensional analysis | The determinant and collective-coordinate measure have the wrong dimensions. |
| Renormalization | UV-divergent determinant factors are treated as finite numbers. |
| Competing saddles | Another saddle of comparable action is omitted. |
| Physical interpretation | A bounce contribution is interpreted as an ordinary energy correction rather than a decay rate. |

A good semiclassical calculation is less like evaluating one formula and more like auditing a whole approximation scheme. This is where many beautiful blackboard derivations quietly lose a factor, a volume, or a zero mode.

## Common pitfalls

**Expanding around a non-saddle.** If $\delta S_E/\delta\phi\ne0$, the linear fluctuation term survives. The Gaussian approximation is then centered at the wrong point.

**Forgetting the sector.** Instantons, vortices, and winding configurations often belong to distinct topological sectors. The path integral may fix the sector, sum over sectors, or weight sectors by a theta angle.

**Putting zero modes inside the determinant.** A zero eigenvalue makes $\det\Delta_s=0$. The correct object is $\det{}^{\prime}\Delta_s$ together with a collective-coordinate measure.

**Calling every exponentially small term an instanton.** Instantons are particular Euclidean saddles. Renormalons, finite-volume effects, tunneling through different saddles, and large-N eigenvalue effects can produce other nonperturbative exponentials.

**Ignoring the contour.** In complex or Lorentzian integrals, the relevant saddles depend on the integration contour and steepest-descent cycles. The real Euclidean saddle story is the cleanest case, not the universal case.

**Trusting an uncontrolled saddle at strong coupling.** A formal saddle can exist when fluctuations are large. The existence of a classical solution is not the same thing as a controlled approximation.

## Relations to other pages

This page is the technical bridge between [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/) and later semiclassical calculations. It explains how nonanalytic factors such as $e^{-S_s/\hbar}$ arise from neighborhoods of nontrivial saddles.

It also supports [False Vacua and Metastability](/nonperturbative-qft/vacuum-structure-phases/false-vacua-and-metastability/), where bounce saddles compute decay rates, and [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/), where topological sectors and instanton-like saddles help organize theta dependence in semiclassical regimes.

For a conceptual warning about when this method is not enough, compare [Semiclassical Versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/). For the chapter map, see [Semiclassical Methods](/nonperturbative-qft/semiclassical-methods/).

## Research status

The saddle-point expansion is mathematically standard for finite-dimensional integrals under suitable hypotheses, and it is a core physics tool for regulated Euclidean path integrals. In weakly coupled quantum mechanics, semiclassical soliton quantization, many instanton calculations, false-vacuum decay, and large-N models, it gives reproducible and highly informative results.

The delicate part is not the local Gaussian expansion. The delicate part is knowing which saddles belong to the correct integration cycle, how to renormalize determinant factors, how to treat zero and negative modes, and whether uncontrolled fluctuations or competing saddles spoil the approximation.

Current research-level extensions include complex saddles, Lefschetz thimbles, resurgence, renormalons, real-time semiclassics, finite-density sign problems, and semiclassical regimes engineered by compactification, supersymmetry, large charge, or large $N$.

## Exercises

### Exercise 1: derive the finite-dimensional saddle formula

Let

$$
I(\hbar)=\int_{\mathbb R^n}d^n x\,e^{-S(x)/\hbar},
$$

and suppose $S$ has a nondegenerate minimum at $x_s$ with positive Hessian $H$. Derive

$$
I(\hbar)
\sim
 e^{-S(x_s)/\hbar}\frac{(2\pi\hbar)^{n/2}}{\sqrt{\det H}}
$$

at leading order.

<details><summary><strong>Solution</strong></summary>

Write $x=x_s+y$. Since $x_s$ is a stationary point,

$$
S(x_s+y)=S(x_s)+\frac12H_{ij}y^iy^j+O(y^3).
$$

To leading order in $\hbar$,

$$
I(\hbar)\approx e^{-S(x_s)/\hbar}
\int d^ny\,\exp\left(-\frac{1}{2\hbar}H_{ij}y^iy^j\right).
$$

Diagonalize $H=O^T\Lambda O$ with $\Lambda_i>0$. Orthogonal transformations have unit Jacobian, so the integral factorizes:

$$
\prod_{i=1}^n\int_{-\infty}^{\infty}dy_i\,e^{-\lambda_i y_i^2/(2\hbar)}
=
\prod_{i=1}^n\sqrt{\frac{2\pi\hbar}{\lambda_i}}
=
\frac{(2\pi\hbar)^{n/2}}{\sqrt{\det H}}.
$$

Higher Taylor coefficients generate corrections in powers of $\hbar$.

</details>

### Exercise 2: show the loop-counting rescaling

For a Euclidean action $S_E[\phi]$, expand around a saddle using $\phi=\phi_s+\sqrt{\hbar}\eta$. Show that the cubic interaction in the exponent is order $\sqrt{\hbar}$ and the quartic interaction is order $\hbar$.

<details><summary><strong>Solution</strong></summary>

Taylor expand the action:

$$
S_E[\phi_s+\sqrt{\hbar}\eta]
=S_E[\phi_s]
+\sqrt{\hbar}\,S_E^{(1)}[\eta]
+\frac{\hbar}{2}S_E^{(2)}[\eta^2]
+\frac{\hbar^{3/2}}{3!}S_E^{(3)}[\eta^3]
+\frac{\hbar^2}{4!}S_E^{(4)}[\eta^4]+\cdots.
$$

The linear term vanishes because $\phi_s$ is a saddle. Dividing by $\hbar$ gives

$$
\frac{S_E[\phi_s+\sqrt{\hbar}\eta]}{\hbar}
=\frac{S_E[\phi_s]}{\hbar}
+\frac12S_E^{(2)}[\eta^2]
+\frac{\sqrt{\hbar}}{3!}S_E^{(3)}[\eta^3]
+\frac{\hbar}{4!}S_E^{(4)}[\eta^4]+\cdots.
$$

Thus cubic vertices carry $\sqrt{\hbar}$ and quartic vertices carry $\hbar$ in the fluctuation expansion.

</details>

### Exercise 3: identify a translational zero mode

Let $\phi_s(x-X)$ be a one-parameter family of one-dimensional Euclidean saddles related by translations. Show that

$$
Z(x)=\frac{\partial\phi_s(x-X)}{\partial X}
$$

is a zero mode of the fluctuation operator.

<details><summary><strong>Solution</strong></summary>

The saddle equation is

$$
\left.\frac{\delta S_E}{\delta\phi(x)}\right|_{\phi_s(x-X)}=0
$$

for every value of $X$. Differentiate this equation with respect to $X$:

$$
0=\frac{\partial}{\partial X}
\left.\frac{\delta S_E}{\delta\phi(x)}\right|_{\phi_s(x-X)}.
$$

By the chain rule this is the second variation of the action acting on $\partial\phi_s/\partial X$:

$$
\int dy\,
\left.\frac{\delta^2S_E}{\delta\phi(x)\delta\phi(y)}\right|_{\phi_s}
\frac{\partial\phi_s(y-X)}{\partial X}=0.
$$

Therefore

$$
\Delta_s Z=0.
$$

The zero mode exists because translating the saddle does not change the action.

</details>

### Exercise 4: why a bounce gives a decay rate

In one sentence, explain why a saddle with one negative Euclidean fluctuation mode should not be interpreted as an ordinary stable correction to the vacuum energy.

<details><summary><strong>Solution</strong></summary>

A negative mode means the Euclidean action decreases along one fluctuation direction, so the real Gaussian integral is not a stable minimum contribution; with the appropriate steepest-descent prescription for a false-vacuum bounce, it instead produces an imaginary part of the false-vacuum energy, and that imaginary part is interpreted as a decay rate.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the functional integration, instanton, and false-vacuum decay lectures.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean functional integrals, saddle expansions, fluctuation determinants, and renormalization.
- M. Mariño, *Instantons and Large N*, especially the chapters on instantons in quantum mechanics, unstable vacua in QFT, large-order behavior, Yang–Mills instantons, and large-N methods.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for solitons, instantons, false-vacuum decay, and gauge-theory applications.
- M. Srednicki, *Quantum Field Theory*, for path integrals, functional determinants, solitons, monopoles, instantons, and theta vacua.

## Version history

- **2026-06-26:** Initial polished page.
