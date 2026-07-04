---
title: "Faddeev–Popov Determinants Preview"
description: "A QFT-oriented preview of the Faddeev–Popov determinant as the Jacobian for slicing gauge orbits in a functional integral."
sidebar:
  label: "Faddeev–Popov Preview"
  order: 11
level: Graduate
status: "Polished draft"
source: "Standard treatments of gauge fixing and ghosts in Faddeev–Popov, Coleman, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, and geometric accounts of gauge-field configuration spaces."
topics:
  - Faddeev–Popov determinant
  - gauge fixing
  - ghosts
  - path-integral measures
  - gauge orbits
canonicalTopics:
  - faddeev-popov-determinant
  - gauge-fixing
  - ghost-determinants
  - gauge-orbit-jacobian
researchStatus:
  established:
    - "The local Faddeev–Popov determinant is the standard perturbative Jacobian for imposing a gauge condition in continuum gauge theory."
  active:
    - "Global gauge fixing, Gribov copies, determinant phases, boundaries, zero modes, and nonperturbative gauge-field spaces remain subtle and theory-dependent."
---

## Summary

The Faddeev–Popov determinant is the Jacobian that appears when a functional integral over gauge fields is replaced by an integral over one representative from each gauge orbit. The slogan is

$$
\int_{\mathcal A/\mathcal G}\cdots
\quad\leadsto\quad
\frac{1}{\operatorname{Vol}\mathcal G}
\int_{\mathcal A}\mathcal D A\,\delta(G[A])\,\Delta_{\rm FP}[A]\cdots,
$$

where $\mathcal A$ is the space of gauge fields, $\mathcal G$ is the gauge group, $G[A]=0$ is a gauge condition, and

$$
\Delta_{\rm FP}[A]=\det M[A]
$$

is the determinant of the infinitesimal change of the gauge condition along a gauge orbit.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Gauge-fixing slice crossing gauge orbits, with the Faddeev–Popov determinant shown as the transverse Jacobian between orbit directions and gauge-condition variations.](/figures/math-toolkit/faddeev-popov-slice.svg)

<figcaption>

The Faddeev–Popov determinant is the local transverse Jacobian between motion along the gauge orbit and change in the gauge condition. The picture is reliable only where the slice intersects each orbit cleanly and without zero modes.

</figcaption>
</figure>

In Abelian Lorenz gauge this determinant is field-independent and usually disappears into normalization. In non-Abelian gauge theory it depends on the background gauge field and is represented by anticommuting ghost fields. That is the modest miracle: ghost fields are not extra physical particles at this stage; they are a compact way to write a determinant.

This page is a preview. The full physical story belongs to gauge theory, BRST symmetry, anomalies, and nonperturbative QFT. Here the goal is narrower: understand the Faddeev–Popov determinant as a functional Jacobian.

## Prerequisites

You should know [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/), because the Faddeev–Popov factor is a special functional Jacobian. You should also know [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/), and [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/), since ghost fields are Grassmann variables whose integral gives a determinant.

The relevant distributional background is [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/), especially the idea that kernels, delta functions, and coincident-point expressions need regularization.

The sign conventions for compact-group generators and covariant derivatives follow [Mathematical Conventions](/math-toolkit/conventions/) unless the formula explicitly says otherwise. For Faddeev–Popov determinants, the invariant definition is always the linearization $M=\delta G[A^\alpha]/\delta\alpha$; signs can be translated from that anchor.

## Core idea

Gauge symmetry in a path integral is redundancy. If the action $S[A]$ and the observable $\mathcal O[A]$ are gauge-invariant, then every point on the same gauge orbit contributes the same physical information. Formally integrating over all gauge-related fields therefore overcounts by the volume of the gauge group:

$$
\int_{\mathcal A}\mathcal D A\,e^{-S[A]}\mathcal O[A]
\sim
\operatorname{Vol}\mathcal G
\int_{\mathcal A/\mathcal G}\mathcal D[A]_{\rm phys}\,e^{-S[A]}\mathcal O[A].
$$

A gauge condition $G[A]=0$ tries to choose one representative per orbit. But inserting a delta function $\delta(G[A])$ is not enough. The slice can cut the orbit at an angle, and the delta function measures distance in the gauge-condition coordinates, not physical distance along the orbit. The missing conversion factor is the Faddeev–Popov determinant.

The defining identity is

$$
1=
\Delta_{\rm FP}[A]
\int \mathcal D g\,\delta(G[A^g]),
$$

at least locally, where $A^g$ is the gauge transform of $A$. Equivalently,

$$
\Delta_{\rm FP}[A]^{-1}
=
\int \mathcal D g\,\delta(G[A^g]).
$$

Near the identity of the gauge group, write $g=e^\alpha$ and linearize:

$$
G[A^\alpha]
=
G[A]+M[A]\alpha+O(\alpha^2).
$$

The Faddeev–Popov operator is

$$
M[A]
=
\left.\frac{\delta G[A^\alpha]}{\delta\alpha}\right|_{\alpha=0}.
$$

Therefore the delta function changes variables from $G$ to $\alpha$ with determinant $\det M[A]$:

$$
\delta(G[A^\alpha])
\sim
\frac{\delta(\alpha-\alpha_*)}{|\det M[A]|}.
$$

That is the whole local mechanism.

$$
\Delta_{\rm FP}[A]=\det M[A]
$$

up to sign, phase, and convention choices that must be fixed by the regulator and by the contour of integration.

## Setup and conventions

This page uses Euclidean-looking functional-integral notation when discussing determinants, because it keeps convergence and signs less distracting. Lorentzian formulas have the same Jacobian structure but place the gauge-fixed action inside $e^{iS}$ and require the usual $i\epsilon$ and contour prescriptions.

Let $A_\mu=A_\mu^aT^a$ be a non-Abelian gauge field. With coupling $g_{\rm YM}$ included in the covariant derivative, write the infinitesimal gauge transformation as

$$
\delta_\alpha A_\mu^a
=
D_\mu^{ab}[A]\alpha^b,
\qquad
D_\mu^{ab}[A]
=
\delta^{ab}\partial_\mu+g_{\rm YM}f^{acb}A_\mu^c.
$$

A gauge condition is a functional

$$
G^a[A](x)=0.
$$

The corresponding Faddeev–Popov operator is the kernel

$$
M^{ab}(x,y;A)
=
\left.
\frac{\delta G^a[A^\alpha](x)}{\delta\alpha^b(y)}
\right|_{\alpha=0}.
$$

For the Lorenz-type condition

$$
G^a[A]=\partial^\mu A_\mu^a,
$$

one obtains

$$
M^{ab}(x,y;A)
=
\partial^\mu D_\mu^{ab}[A] \delta^{(d)}(x-y),
$$

or, with a conventional sign absorbed into the ghost action,

$$
\Delta_{\rm FP}[A]
=
\det\bigl(-\partial^\mu D_\mu[A]\bigr).
$$

The sign inside the determinant is usually conventional in perturbation theory. The boundary conditions, zero modes, determinant phase, and regularization are not conventional; they are part of the definition of the problem.

## The finite-dimensional model

The cleanest way to understand the determinant is to forget fields for a moment.

Suppose a finite-dimensional space $X$ has coordinates adapted to a group action:

$$
x=(y,\alpha),
$$

where $y$ labels the chosen slice and $\alpha$ labels the position along the group orbit. The volume element has the form

$$
d^n x=J(y,\alpha)\,d^{n-r}y\,d^r\alpha.
$$

If the gauge condition is $G(x)=0$, then near a good slice

$$
G(y,\alpha)=M(y)\alpha+O(\alpha^2).
$$

Thus

$$
\delta^{(r)}(G(y,\alpha))
=
\frac{\delta^{(r)}(\alpha)}{|\det M(y)|}
$$

and therefore

$$
\int_X d^n x\,\delta(G(x))\,|\det M(x)|\,f(x)
=
\int_{\text{slice}} d^{n-r}y\,J(y,0)f(y,0).
$$

This is the Faddeev–Popov formula without functional analysis. The continuum formula is obtained by replacing $x$ by a field, $\alpha$ by a gauge parameter $\alpha(x)$, and $\det M$ by a regulated functional determinant.

### A rotation toy model

Take $X=\mathbb R^2\setminus\{0\}$ and let $SO(2)$ rotate the point $(x,y)$. A gauge orbit is a circle of radius $r$. The gauge slice $y=0$ intersects each circle twice, so to make a good local slice choose the half-line $y=0$, $x>0$.

The infinitesimal rotation is

$$
\delta_\alpha x=-\alpha y,
\qquad
\delta_\alpha y=\alpha x.
$$

At the slice point $(r,0)$,

$$
\delta_\alpha G=\delta_\alpha y=r\alpha.
$$

Therefore

$$
M=r,
\qquad
\Delta_{\rm FP}=r.
$$

But $dx\,dy=r\,dr\,d\theta$. The Faddeev–Popov determinant is nothing exotic here; it is the polar-coordinate Jacobian in disguise. Tiny determinant, huge career.

## Abelian gauge theory

For Abelian gauge theory,

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

In Lorenz gauge,

$$
G[A]=\partial^\mu A_\mu.
$$

Then

$$
G[A^\alpha]
=
\partial^\mu A_\mu+\partial^\mu\partial_\mu\alpha
=
G[A]+\Box\alpha.
$$

The Faddeev–Popov operator is therefore

$$
M=\Box
$$

in Lorentzian signature, or $M=-\partial^2$ after Euclidean continuation with common positive elliptic-operator conventions. The determinant does not depend on $A$:

$$
\Delta_{\rm FP}[A]=\det\Box.
$$

For many perturbative QED calculations this is absorbed into the normalization of the generating functional. That is why Abelian ghosts often appear to be absent.

They are not conceptually absent. They are just noninteracting in this gauge. Boundaries, zero modes, compact gauge fields, topology, and finite temperature can make even Abelian determinants worth treating carefully.

## Non-Abelian gauge theory

For a non-Abelian gauge field,

$$
\delta_\alpha A_\mu^a
=D_\mu^{ab}[A]\alpha^b.
$$

In Lorenz gauge,

$$
G^a[A]=\partial^\mu A_\mu^a,
$$

so

$$
\delta_\alpha G^a[A]
=
\partial^\mu D_\mu^{ab}[A]\alpha^b.
$$

Thus

$$
M^{ab}[A]=\partial^\mu D_\mu^{ab}[A].
$$

Unlike the Abelian case, this operator depends on $A$. Its determinant cannot be discarded as a constant. Expanding the covariant derivative gives a field-dependent term,

$$
\partial^\mu D_\mu^{ab}[A]
=
\delta^{ab}\partial^2
+g_{\rm YM}f^{acb}\partial^\mu A_\mu^c
+g_{\rm YM}f^{acb}A_\mu^c\partial^\mu,
$$

with the precise distributional placement of derivatives fixed by integration by parts and boundary conditions.

In perturbative gauge theory, the determinant is represented by Grassmann ghost fields $c^a,\bar c^a$:

$$
\det M[A]
=
\int \mathcal D\bar c\,\mathcal D c\,
\exp\left(-\int d^d x\,\bar c^a M^{ab}[A]c^b\right)
$$

in Euclidean conventions.

The ghosts are scalar Grassmann fields in spacetime but transform in the adjoint representation of the gauge algebra. They do not represent physical external particles in the gauge-invariant Hilbert space. Their job in the path integral is to reproduce the Jacobian and maintain the cancellations required by gauge redundancy.

## Gauge-fixing Gaussian and the usual covariant form

The delta-function gauge condition is often softened into a Gaussian average over gauge conditions. Instead of imposing

$$
G^a[A]=0,
$$

one uses a gauge-fixing weight

$$
\exp\left[-\frac{1}{2\xi}\int d^d x\,G^a[A]G^a[A]\right]
$$

in Euclidean signature. For $G^a[A]=\partial^\mu A_\mu^a$, this gives the familiar covariant gauge-fixing term

$$
S_{\rm gf}[A]
=
\frac{1}{2\xi}\int d^d x\, (\partial^\mu A_\mu^a)^2.
$$

The gauge-fixed Euclidean path integral then has the schematic form

$$
Z
=
\frac{1}{\operatorname{Vol}\mathcal G}
\int \mathcal D A\,\mathcal D\bar c\,\mathcal D c\,
\exp\left[-S[A]-S_{\rm gf}[A]-S_{\rm gh}[A,c,\bar c]\right],
$$

with

$$
S_{\rm gh}
=
\int d^d x\,\bar c^a(-\partial^\mu D_\mu^{ab}[A])c^b
$$

up to sign conventions.

That compact formula is useful, but it hides its origin. The ghost action is not an arbitrary interaction; it is the exponentiated determinant of the operator that measures how the gauge condition changes along the gauge orbit.

## Zero modes and residual gauge symmetry

If $M[A]$ has zero modes, then the gauge condition is not transverse to the gauge orbit at $A$. There are several possible meanings:

- the gauge condition has residual gauge transformations;
- the field has a continuous stabilizer subgroup;
- the boundary conditions leave unfixed global transformations;
- the gauge slice is tangent to the orbit;
- the configuration lies on a Gribov horizon.

In all cases, the naive determinant formula fails or needs modification. One must separate zero modes, divide by the remaining gauge volume, add extra conditions, or change the gauge-fixing procedure.

A familiar Abelian example is constant gauge transformations on a compact space without charged boundary data. For $M=-\partial^2$, constants are zero modes. They are not small corrections; they are exactly the leftover global $U(1)$ transformation.

## Gribov copies and the local nature of the formula

The derivation assumes that every gauge orbit intersects the slice exactly once. In non-Abelian gauge theory this is generally false globally. A gauge condition may intersect the same orbit multiple times. These multiple intersections are called Gribov copies.

The determinant can vanish on a Gribov horizon, where the gauge slice becomes tangent to the gauge orbit. Perturbation theory around $A_\mu=0$ often works inside a local patch where the usual Faddeev–Popov formula is adequate. Nonperturbatively, the global geometry of gauge-field space matters.

This is why the Faddeev–Popov method is both indispensable and limited. It is the right local Jacobian. It is not, by itself, a complete global construction of the quotient $\mathcal A/\mathcal G$.

## Relation to BRST symmetry

Once the determinant is written using ghosts, the gauge-fixed action often has a fermionic symmetry called BRST symmetry. Schematically, BRST symmetry combines an infinitesimal gauge transformation with a ghost parameter.

The conceptual progression is:

$$
\text{gauge redundancy}
\quad\to\quad
\text{gauge condition}
\quad\to\quad
\Delta_{\rm FP}
\quad\to\quad
\text{ghost fields}
\quad\to\quad
\text{BRST symmetry}.
$$

BRST symmetry is not needed to define the local determinant, but it is the organizing principle that makes gauge-fixed perturbation theory systematic. It controls Ward identities, unitarity cancellations, gauge-parameter independence, and the physical-state condition in covariant quantization.

This preview stops before BRST cohomology. The determinant is the entrance; BRST is the hallway system behind the door.

## Common pitfalls

**“Gauge symmetry is an ordinary symmetry, so we should integrate over all its images.”** Gauge symmetry is redundancy. Gauge-related configurations are different descriptions of the same physical configuration, not distinct physical states.

**“The determinant is optional because it is just a normalization.”** It is a normalization only when it is independent of the fields being integrated over, or when it cancels in a specific normalized quantity. In non-Abelian gauge theory it is field-dependent and produces ghost interactions.

**“Ghosts are physical particles with wrong statistics.”** Faddeev–Popov ghosts are Grassmann fields introduced to represent a determinant. They appear in internal lines of covariant perturbation theory but not as physical external states.

**“The gauge condition fixes the gauge globally.”** Usually it does not. Perturbative gauge fixing is local in field space. Global issues include Gribov copies, large gauge transformations, zero modes, boundary conditions, and topological sectors.

**“The absolute value of the determinant is harmless.”** In finite-dimensional real integrals, absolute values appear naturally in delta-function changes of variables. In gauge theory, the sign or phase of determinants can carry important global information. Perturbative Euclidean ghost formulas usually represent $\det M$, not $|\det M|$.

**“Faddeev–Popov is the same thing as choosing coordinates on the quotient.”** It is a way to compute locally as if a good slice exists. A true global coordinate system on the quotient may not exist.

## Relations to other pages

[Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/) explains why functional measures change under field redefinitions and why the phrase “the measure is invariant” needs a regulator.

[Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains determinant expressions such as $\det M[A]$, while [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explain two standard ways determinant-like quantities are regularized.

[Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/) and [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) explain why anticommuting variables produce determinants rather than inverse square roots.

Gauge theory pages will use this determinant to derive ghost propagators, ghost–gluon vertices, BRST symmetry, Slavnov–Taylor identities, and the perturbative rules for Yang–Mills theory.

## Research status

The local Faddeev–Popov construction is standard and settled in perturbative gauge theory. It is one of the basic ingredients of covariant quantization and is built into modern treatments of Yang–Mills theory, the Standard Model, and perturbative quantum gravity.

The global story is more delicate. Non-Abelian gauge fixing can fail globally because of Gribov copies. Boundaries can leave edge modes or residual gauge transformations. Topologically nontrivial sectors can affect determinant phases and zero modes. In rigorous and nonperturbative settings, defining the quotient by gauge transformations is often the real problem, not a decorative technicality.

A safe status label is:

$$
\text{Faddeev–Popov determinant}=\text{settled local perturbative tool, subtle global object}.
$$

## Exercises

### Exercise 1: Rotation gauge fixing

Let $X=\mathbb R^2\setminus\{0\}$ and let $SO(2)$ act by rotations. Use the gauge condition $G(x,y)=y=0$ and restrict to the slice $x>0$. Show that the Faddeev–Popov determinant is $r$ at the point $(r,0)$.

<details><summary><strong>Solution</strong></summary>

An infinitesimal rotation by $\alpha$ gives

$$
\delta_\alpha x=-\alpha y,
\qquad
\delta_\alpha y=\alpha x.
$$

Since $G(x,y)=y$,

$$
\delta_\alpha G=\delta_\alpha y=\alpha x.
$$

At the slice point $(r,0)$ this becomes

$$
\delta_\alpha G=r\alpha.
$$

Therefore

$$
M=\frac{\partial G}{\partial\alpha}=r,
\qquad
\Delta_{\rm FP}=r.
$$

This is exactly the polar-coordinate Jacobian $dx\,dy=r\,dr\,d\theta$.

</details>

### Exercise 2: Abelian Lorenz gauge

For $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ and $G[A]=\partial^\mu A_\mu$, compute the Faddeev–Popov operator. Why does the corresponding ghost field decouple from $A_\mu$?

<details><summary><strong>Solution</strong></summary>

The gauge-transformed condition is

$$
G[A^\alpha]
=\partial^\mu(A_\mu+\partial_\mu\alpha)
=\partial^\mu A_\mu+\Box\alpha.
$$

Thus

$$
M=\Box.
$$

The determinant is

$$
\Delta_{\rm FP}=\det\Box,
$$

which is independent of $A_\mu$. If one writes it using Grassmann variables,

$$
\det\Box
=\int \mathcal D\bar c\,\mathcal D c\,
\exp\left(-\int \bar c\Box c\right),
$$

the ghost action contains no coupling to $A_\mu$. The ghosts are free and normally contribute only an overall normalization, aside from zero-mode and boundary subtleties.

</details>

### Exercise 3: Ghost determinant

Let $M$ be an $N\times N$ matrix. Show that

$$
\int d\bar c_N\,dc_N\cdots d\bar c_1\,dc_1\,
\exp(-\bar c_i M_{ij}c_j)
$$

is proportional to $\det M$, with the overall sign depending on the ordering convention for the Berezin measure.

<details><summary><strong>Solution</strong></summary>

The exponential truncates because the variables are Grassmann. Only the term containing every $\bar c_i$ and every $c_j$ survives the Berezin integral. Expanding,

$$
\exp(-\bar c_iM_{ij}c_j)
=\prod_i \left(1-\bar c_iM_{ij}c_j+\cdots\right),
$$

and collecting the top-degree part gives an antisymmetrized product of matrix entries. That antisymmetrized product is the determinant:

$$
\sum_{\sigma\in S_N}\operatorname{sgn}(\sigma)
M_{1\sigma(1)}\cdots M_{N\sigma(N)}
=\det M.
$$

Depending on whether the measure is ordered as $d\bar c_Ndc_N\cdots d\bar c_1dc_1$, $dc_Nd\bar c_N\cdots dc_1d\bar c_1$, or another convention, an overall sign may appear. The QFT convention is chosen once and then held fixed.

</details>

### Exercise 4: Where the formula can fail

In the rotation example of Exercise 1, what goes wrong if the slice is all of $y=0$ instead of only the half-line $x>0$?

<details><summary><strong>Solution</strong></summary>

Each circle of radius $r$ intersects the full line $y=0$ twice: at $(r,0)$ and $(-r,0)$. These two points are related by a rotation by $\pi$, so they lie on the same gauge orbit. The slice therefore does not choose one representative per orbit.

The local determinant is still $|x|$ at each intersection, but the global gauge fixing overcounts by a factor of two. This finite-dimensional failure is the baby version of a Gribov-copy problem: a gauge condition can be locally transverse and still fail to define a global unique slice.

</details>

## References

- L. D. Faddeev and V. N. Popov, “Feynman diagrams for the Yang–Mills field.” Original gauge-fixing determinant construction.
- S. Coleman, *Aspects of Symmetry* and *Lectures of Sidney Coleman on Quantum Field Theory*. Pedagogical treatments of functional integration, ghosts, and the Faddeev–Popov ansatz.
- M. Srednicki, *Quantum Field Theory*. Compact perturbative treatment of non-Abelian gauge fixing, ghosts, and Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II. Systematic treatment of non-Abelian gauge theories, the Faddeev–Popov method, ghosts, and BRST symmetry.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Practical derivations of gauge fixing, ghost terms, and perturbative Yang–Mills rules.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, gauge fixing, BRST symmetry, and renormalization of gauge theories.
- I. M. Singer, “Some remarks on the Gribov ambiguity.” Classic geometric perspective on global gauge-fixing obstructions.

## Version history

- 2026-06-24: First polished draft. Introduced the Faddeev–Popov determinant as a local gauge-orbit Jacobian, derived the Abelian and non-Abelian forms, explained ghost exponentiation, and flagged zero modes, residual gauge symmetry, and Gribov copies.
