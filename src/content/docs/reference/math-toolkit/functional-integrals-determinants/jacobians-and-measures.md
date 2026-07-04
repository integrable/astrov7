---
title: "Jacobians and Measures"
description: "A QFT-oriented guide to changes of variables in functional integrals, bosonic and fermionic Jacobians, field redefinitions, collective-coordinate measures, Faddeev–Popov-type factors, and anomaly-producing measure transformations."
sidebar:
  label: "Jacobians and Measures"
  order: 10
level: Graduate
status: "Polished draft"
source: "Standard finite-dimensional change-of-variables theory and QFT path-integral measure treatments in Coleman, Srednicki, Weinberg, Schwartz, Zee, Zinn-Justin, Fujikawa-style anomaly references, and localization literature."
topics:
  - path-integral measures
  - Jacobians
  - field redefinitions
  - anomalies
  - collective coordinates
canonicalTopics:
  - path-integral-measure
  - functional-jacobians
  - field-redefinitions
  - fujikawa-jacobian
researchStatus:
  established:
    - "Finite-dimensional Jacobians are exact change-of-variables factors; regulated functional Jacobians are standard tools for field redefinitions, collective coordinates, gauge fixing, and anomaly calculations."
  active:
    - "Global measure choices, determinant-line phases, anomaly inflow, gauge-fixing on nontrivial field spaces, boundaries, and nonperturbative definitions remain subtle in modern QFT."
---

## Summary

A Jacobian is the factor that tells an integral how the volume element changes under a change of variables. In finite dimension, if

$$
x^i=f^i(y),
$$

then

$$
d^n x
=
\left|\det\frac{\partial x^i}{\partial y^j}\right|d^n y.
$$

For ordinary integrals this is freshman calculus with determinants. In QFT, the same idea becomes one of the most dangerous pieces of notation in the subject. A formal statement such as

$$
\mathcal D\phi=\mathcal D\chi\,\det\left(\frac{\delta\phi}{\delta\chi}\right)
$$

contains at least four hidden choices:

1. which field space is being integrated over;
2. which regulator defines the product of differentials;
3. which inner product or basis defines the measure;
4. how determinant phases, zero modes, boundaries, and gauge redundancies are treated.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram showing finite-dimensional Jacobians, regulated field measures, trace-log Jacobians, and possible QFT outcomes such as local counterterms, anomalies, ghosts, and collective-coordinate volumes.](/figures/math-toolkit/jacobian-measure-flow.svg)

<figcaption>

A functional Jacobian is a regulated determinant. Depending on the transformation and regulator, it can be a harmless normalization, a local counterterm, a collective-coordinate volume, a ghost determinant, or an anomaly.

</figcaption>
</figure>

The central lesson is:

$$
\text{``the measure is invariant'' is a claim, not a default law}.
$$

In finite dimension the claim can be checked by a determinant. In QFT it must be checked after choosing a regulator.

## Prerequisites

You should know [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), where determinant factors first appear as ordinary matrix Jacobians. [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/) and [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) are essential for fermionic measures, because Grassmann variables transform with inverse determinants.

You should also know [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) for the meaning of regulated determinant-like expressions. [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) explains why collective-coordinate Jacobians appear when zero modes are separated.

## Core idea

In a regulated theory, a field is replaced by finitely many coordinates. For example, on a lattice or in a mode cutoff,

$$
\phi(x)\quad\leadsto\quad (q_1,\ldots,q_N),
$$

and the regulated measure is something like

$$
\mathcal D_N\phi=\prod_{n=1}^N dq_n.
$$

A change of field variables becomes an ordinary change of finite-dimensional variables:

$$
q_n=q_n(r_1,\ldots,r_N).
$$

Therefore

$$
\mathcal D_N\phi
=
\left|\det\frac{\partial q_n}{\partial r_m}\right|
\mathcal D_N\chi.
$$

Only after this finite-dimensional statement is clear should one try to take $N\to\infty$. In that limit, the determinant may diverge, vanish, become a local counterterm, encode an anomaly, or require a phase convention.

For an infinitesimal transformation

$$
\phi\mapsto \phi+\epsilon R[\phi],
$$

the regulated Jacobian has the schematic form

$$
\log J
=\epsilon\operatorname{Tr}_{\rm reg}\left(\frac{\delta R}{\delta\phi}\right)+O(\epsilon^2).
$$

The trace is the dangerous object. In finite dimension it is an ordinary trace. In field theory it contains coincident kernels such as $\delta(x-x)$ and must be regulated.

## Setup and conventions

This page distinguishes four related objects.

A **coordinate volume element** is the finite-dimensional object

$$
d^n x=dx^1\cdots dx^n.
$$

A **regulated field measure** is a finite product of coordinate differentials, such as

$$
\mathcal D_N\phi=\prod_{n=1}^N dq_n,
$$

where $q_n$ are lattice variables or mode coefficients.

A **formal functional measure** is the shorthand

$$
\mathcal D\phi,
$$

which is meaningful only after the class of regulators or Gaussian measures being used has been specified.

A **measure convention** is the normalization choice that fixes factors such as $2\pi$, $\hbar$, metric factors, and inner products on the field space. Different conventions can shift finite local terms but should not change physical observables when the theory is treated consistently.

For a real bosonic field on a Euclidean background, a common mode expansion is

$$
\phi(x)=\sum_n q_n f_n(x),
$$

where the basis is orthonormal with respect to

$$
\langle f_m,f_n\rangle
=\int d^d x\sqrt g\, f_m(x)f_n(x)=\delta_{mn}.
$$

Then the regulated measure is

$$
\mathcal D_N\phi=\prod_{n=1}^N dq_n.
$$

Changing the inner product or cutoff changes the measure definition. That is not a contradiction; it is part of the regularization data.

## Ordinary bosonic Jacobians

Let

$$
x=Ay
$$

for an invertible real $n\times n$ matrix $A$. Then

$$
d^n x=|\det A|\,d^n y.
$$

For an affine transformation

$$
x=Ay+b,
$$

the translation $b$ does not affect the measure, so the Jacobian is still $|\det A|$.

For a nonlinear transformation $x=f(y)$, the Jacobian is local in $y$:

$$
J(y)=\left|\det\frac{\partial f^i(y)}{\partial y^j}\right|.
$$

The change-of-variables theorem says

$$
\int d^n x\,F(x)
=
\int d^n y\,
\left|\det\frac{\partial f}{\partial y}\right|F(f(y)),
$$

provided the map is appropriately invertible on the integration domain. If the map is many-to-one, singular, or changes the domain in a nontrivial way, the formula must be refined.

This finite-dimensional warning already matters in QFT. Gauge transformations, polar decompositions, collective-coordinate maps, and field redefinitions are often not globally one-to-one.

## Grassmann Jacobians

Grassmann integration transforms oppositely from ordinary bosonic integration. Let

$$
\theta_i=A_i{}^j\eta_j
$$

for $n$ Grassmann generators. Then

$$
d\theta_n\cdots d\theta_1
=(\det A)^{-1}d\eta_n\cdots d\eta_1.
$$

The inverse determinant is not a typo. It is forced by the rule that Berezin integration extracts the coefficient of the top monomial.

Check the one-variable case. If

$$
\theta=a\eta,
$$

then

$$
\int d\theta\,\theta=1.
$$

To preserve the value after changing variables,

$$
1=\int d\theta\,a\eta.
$$

Therefore

$$
d\theta=a^{-1}d\eta.
$$

For a complex fermionic pair, if

$$
\psi=A\chi,
\qquad
\overline\psi=\overline\chi B,
$$

then schematically

$$
\mathcal D\overline\psi\,\mathcal D\psi
=(\det B)^{-1}(\det A)^{-1}
\mathcal D\overline\chi\,\mathcal D\chi.
$$

This inverse behavior is the measure-level reason fermionic Gaussian integrals produce determinants in the numerator rather than denominator.

## Functional Jacobians as trace logs

For a linear field transformation

$$
\phi=M\chi,
$$

where $M$ is an operator, a finite-dimensional regulator gives

$$
\mathcal D\phi=|\det M_N|\,\mathcal D\chi.
$$

The formal continuum expression is

$$
\log J=\operatorname{Tr}\log M.
$$

If $M$ is a differential or pseudodifferential operator, this trace log is a functional determinant and must be regulated. If $M$ is a multiplication operator,

$$
(M\chi)(x)=m(x)\chi(x),
$$

then the formal trace is

$$
\operatorname{Tr}\log M
=\int d^d x\,\delta^{(d)}(0)\log m(x),
$$

which displays the problem: $\delta^{(d)}(0)$ is not a number. A lattice regulator replaces it by a power of the cutoff. Dimensional regularization often sets such ultra-local power divergences to zero. A heat-kernel regulator may produce local curvature and background-field terms.

Thus the phrase

$$
\mathcal D\phi=\det(M)\mathcal D\chi
$$

is not wrong, but it is incomplete until $\det(M)$ is defined.

## Local field redefinitions

Consider a scalar field redefinition

$$
\phi(x)=f(\chi(x)).
$$

On a lattice with sites $x_i$,

$$
\prod_i d\phi_i
=\prod_i\left|f'(\chi_i)\right|d\chi_i.
$$

Therefore

$$
J[\chi]=\prod_i\left|f'(\chi_i)\right|,
$$

and

$$
\log J[\chi]=\sum_i\log|f'(\chi_i)|.
$$

In continuum notation, this resembles

$$
\log J[\chi]
\sim
\delta^{(d)}(0)\int d^d x\,\log|f'(\chi(x))|.
$$

This is regulator dependent and local. In many perturbative QFT settings, such ultra-local Jacobians can be absorbed into local counterterms or vanish in dimensional regularization. But that is a conclusion in a scheme, not a universal identity.

Local invertible field redefinitions do not change physical S-matrix elements when sources, counterterms, and operator definitions are treated correctly. This is often called the equivalence theorem. The theorem is not the claim that the Jacobian never exists. It is the claim that the properly transformed theory gives the same physics.

A useful practical rule is:

$$
\text{field redefinition} = \text{changed action} + \text{changed measure} + \text{changed operators}.
$$

Dropping two of the three can create fake paradoxes.

## Collective-coordinate measures

Saddle-point expansions often require a change of variables from field fluctuations to zero modes plus nonzero fluctuations. Suppose saddles are parameterized by collective coordinates $a^A$:

$$
\phi_\ast(x;a).
$$

Write a nearby field as

$$
\phi(x)=\phi_\ast(x;a)+\eta_\perp(x),
$$

with orthogonality constraints

$$
\int d^d x\,\eta_\perp(x)\frac{\partial\phi_\ast(x;a)}{\partial a^A}=0.
$$

The measure changes schematically as

$$
\mathcal D\phi
=d^m a\,J(a)\,\mathcal D\eta_\perp.
$$

If the field-space metric is

$$
\|\delta\phi\|^2=\int d^d x\,\delta\phi(x)^2,
$$

then the induced metric on the collective-coordinate space is

$$
G_{AB}(a)=\int d^d x\,
\frac{\partial\phi_\ast(x;a)}{\partial a^A}
\frac{\partial\phi_\ast(x;a)}{\partial a^B}.
$$

The natural volume element contains

$$
J(a)d^m a\propto \sqrt{\det G_{AB}(a)}\,d^m a,
$$

up to normalization conventions. This is the geometric content behind the instanton and soliton phrase "integrate over zero modes."

The determinant with zero modes removed,

$$
\det{}'K,
$$

and the collective-coordinate Jacobian are two pieces of the same change of variables. Keeping one while forgetting the other gives the wrong semiclassical normalization.

## Gauge fixing and Faddeev–Popov-type Jacobians

Gauge redundancy is a change-of-variables problem with overcounting. Schematically, the fields decompose into

$$
\text{field} = \text{gauge slice} + \text{gauge orbit}.
$$

The path integral over all fields overcounts physically equivalent configurations by the volume of the gauge group. A gauge condition

$$
G[A]=0
$$

inserts a functional identity of the form

$$
1=\Delta_{\rm FP}[A]
\int\mathcal D\alpha\,\delta(G[A^\alpha]),
$$

where $A^\alpha$ is the gauge transform of $A$. The Faddeev–Popov determinant is the Jacobian

$$
\Delta_{\rm FP}[A]
=
\det\left(\frac{\delta G[A^\alpha]}{\delta\alpha}\right)_{G[A]=0}.
$$

This formula is only a preview; full gauge fixing belongs to gauge-theory and BRST pages. For this chapter, the important point is that the ghost determinant is not mystical. It is a Jacobian for changing variables from redundant field coordinates to a gauge slice and gauge-orbit coordinates.

Global issues remain. A gauge condition may intersect an orbit more than once or fail to intersect some orbits. These Gribov-type issues are invisible in the most naive local determinant formula.

## Fujikawa's measure idea and anomalies

An anomaly can arise when a classical symmetry of the action is not a symmetry of the regulated quantum measure. Fujikawa's method makes this statement concrete.

For a massless Dirac fermion, consider a local axial rotation

$$
\psi(x)\to e^{i\alpha(x)\gamma^5}\psi(x),
\qquad
\overline\psi(x)\to\overline\psi(x)e^{i\alpha(x)\gamma^5}.
$$

Classically, this is a symmetry when the fermion is massless and no anomaly is present. The fermionic measure, however, transforms by a regulated determinant. Expand the fermion in eigenfunctions of a Dirac operator,

$$
\psi(x)=\sum_n c_n\varphi_n(x),
\qquad
\overline\psi(x)=\sum_n \overline c_n\varphi_n^\dagger(x).
$$

The formal Jacobian involves

$$
\operatorname{Tr}(\alpha\gamma^5)=
\sum_n\int d^4x\,\varphi_n^\dagger(x)\alpha(x)\gamma^5\varphi_n(x),
$$

which is ill-defined without a regulator. A gauge-invariant heat-kernel regulator replaces this by

$$
\operatorname{Tr}_{\rm reg}(\alpha\gamma^5)
=
\lim_{M\to\infty}
\operatorname{Tr}\left(\alpha\gamma^5 e^{-D^2/M^2}\right).
$$

In four-dimensional Abelian gauge theory, this produces the standard axial anomaly, conventionally written in Lorentzian form as

$$
\partial_\mu j_5^\mu
=
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

for one massless Dirac fermion of charge $q$, with the sign tied to the conventions for $\gamma^5$, $\epsilon^{0123}$, and the axial rotation. The site convention is $\epsilon^{0123}=+1$ and $\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3$.

The moral is not that all anomalies are "just Jacobians" in every formulation. The moral is sharper: a regulator can preserve some symmetries while obstructing others, and the obstruction appears as a local term in the regulated measure variation.

## Measures, inner products, and curved backgrounds

On a curved Euclidean background, a scalar field has a natural $L^2$ inner product

$$
\langle\phi_1,\phi_2\rangle
=\int_M d^d x\sqrt g\,\phi_1(x)\phi_2(x).
$$

Choosing an orthonormal basis with respect to this inner product defines mode coefficients and hence a formal measure. If the metric changes, the basis changes, the measure can change, and the variation may contribute to stress-tensor anomalies or curvature counterterms.

Similarly, for gauge fields, spinors, $p$-forms, and constrained fields, the inner product includes bundle metrics, spacetime metrics, and sometimes gauge-fixing choices. There is no context-free object called "the measure" independent of these choices.

This is especially important in determinant problems. The expression

$$
\det K
$$

depends not only on the differential expression $K$, but also on its domain, boundary conditions, zero-mode treatment, spectral cut, and measure normalization.

## A finite-dimensional warning about polar coordinates

The standard two-dimensional example is worth keeping close. In $\mathbb R^2$,

$$
x=r\cos\theta,
\qquad
 y=r\sin\theta.
$$

The Jacobian is

$$
\left|\det\frac{\partial(x,y)}{\partial(r,\theta)}\right|=r,
$$

so

$$
dx\,dy=r\,dr\,d\theta.
$$

The factor $r$ is not an optional normalization. Dropping it changes the integral. In field theory, decompositions into radial and angular variables, gauge-invariant variables and gauge orbits, eigenvalues and angular matrices, or moduli and fluctuations all have analogous Jacobians.

In matrix models, for example, diagonalizing a Hermitian matrix produces a Vandermonde determinant. In gauge theory, gauge fixing produces a Faddeev–Popov determinant. In instanton calculus, separating collective coordinates produces a moduli-space volume form. These are all higher-powered versions of $r\,dr\,d\theta$.

## Common pitfalls

**Writing a formal determinant and never specifying the regulator.** A functional Jacobian is a determinant. In infinite dimension, determinant means regulator plus convention.

**Assuming local field redefinitions have zero Jacobian in every scheme.** Ultra-local Jacobians often vanish in dimensional regularization or are absorbed into counterterms, but they need not vanish in every regulator.

**Forgetting that operators transform too.** A field redefinition changes not only the action and measure but also source couplings and composite operators.

**Using bosonic Jacobians for Grassmann variables.** Grassmann measures transform with inverse determinants. This is why fermionic Gaussian integrals produce determinants upstairs.

**Treating gauge fixing as an ordinary one-to-one change of variables.** Gauge orbits can have stabilizers, Gribov copies, boundaries, and global topology. The local Faddeev–Popov determinant is only the beginning.

**Dropping collective-coordinate Jacobians.** Removing zero modes from $\det K$ requires replacing them by a measure on the corresponding collective-coordinate space.

**Thinking anomalies are caused by sloppy regularization.** An anomaly is not a mistake; it is an obstruction to preserving all desired symmetries simultaneously in the quantum theory.

## Relations to other pages

[Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) explains the inverse determinant rule for Grassmann measures. [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/) explains the sign-sensitive real-fermion analogue. [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains trace-log notation, determinant ratios, and zero-mode removal.

[Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explain two standard ways of defining determinant-like Jacobians. [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) explains how collective-coordinate measures appear in semiclassical expansions.

The distributional issue behind $\delta^{(d)}(0)$ is introduced in [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/). Later gauge-theory, BRST, anomaly, and topology pages will use this page as the finite-dimensional and regulated-measure backbone.

## Research status

Finite-dimensional Jacobians and regulated perturbative functional Jacobians are established tools. Fujikawa-style anomaly calculations, Faddeev–Popov determinants, collective-coordinate measures, and field-redefinition equivalence arguments are standard parts of QFT.

The subtle parts are global and nonperturbative. Measures may be sections of determinant lines rather than ordinary functions. Fermion signs can depend on topology. Gauge-fixing slices may fail globally. Boundaries can carry anomaly inflow. Noncompact field spaces can create convergence problems. In modern QFT, these issues are not peripheral; they appear in anomalies, dualities, localization, topological phases, and quantum gravity.

## Exercises

### Exercise 1: Bosonic linear Jacobian

Let

$$
\begin{pmatrix}x\\y\end{pmatrix}
=\begin{pmatrix}2&1\\0&3\end{pmatrix}
\begin{pmatrix}u\\v\end{pmatrix}.
$$

Find $dx\,dy$ in terms of $du\,dv$.

<details><summary><strong>Solution</strong></summary>

The Jacobian matrix is

$$
A=\begin{pmatrix}2&1\\0&3\end{pmatrix}.
$$

Its determinant is

$$
\det A=2\cdot3-0\cdot1=6.
$$

Therefore

$$
dx\,dy=6\,du\,dv.
$$

</details>

### Exercise 2: Grassmann linear Jacobian

Let $\theta_1=a\eta_1$ and $\theta_2=b\eta_2$, where $a,b$ are nonzero ordinary numbers. Show that

$$
d\theta_2\,d\theta_1=(ab)^{-1}d\eta_2\,d\eta_1.
$$

<details><summary><strong>Solution</strong></summary>

Berezin integration is normalized by

$$
\int d\theta_2\,d\theta_1\,\theta_1\theta_2=1
$$

with the chosen ordering. Since

$$
\theta_1\theta_2=(a\eta_1)(b\eta_2)=ab\,\eta_1\eta_2,
$$

the measure must transform as

$$
d\theta_2\,d\theta_1=(ab)^{-1}d\eta_2\,d\eta_1
$$

so that the integral remains equal to 1.

</details>

### Exercise 3: Polar-coordinate Jacobian

Derive the Jacobian for

$$
x=r\cos\theta,
\qquad y=r\sin\theta.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
\frac{\partial(x,y)}{\partial(r,\theta)}
=\begin{pmatrix}
\cos\theta&-r\sin\theta\\
\sin\theta&r\cos\theta
\end{pmatrix}.
$$

The determinant is

$$
r\cos^2\theta+r\sin^2\theta=r.
$$

Therefore

$$
dx\,dy=r\,dr\,d\theta.
$$

</details>

### Exercise 4: Infinitesimal Jacobian

Let

$$
x^i=y^i+\epsilon R^i(y),
$$

where $\epsilon$ is infinitesimal. Show that

$$
\det\left(\frac{\partial x^i}{\partial y^j}\right)
=1+\epsilon\partial_iR^i+O(\epsilon^2).
$$

<details><summary><strong>Solution</strong></summary>

The Jacobian matrix is

$$
\frac{\partial x^i}{\partial y^j}
=\delta^i{}_j+
\epsilon\frac{\partial R^i}{\partial y^j}.
$$

For a small matrix perturbation,

$$
\det(I+\epsilon A)=1+\epsilon\operatorname{tr}A+O(\epsilon^2).
$$

Here

$$
\operatorname{tr}A=\frac{\partial R^i}{\partial y^i}.
$$

Thus

$$
\det\left(\frac{\partial x^i}{\partial y^j}\right)
=1+\epsilon\partial_iR^i+O(\epsilon^2).
$$

</details>

### Exercise 5: Lattice field redefinition

On a lattice with $N$ sites, let

$$
\phi_i=e^{\chi_i}.
$$

Find the Jacobian relating $\prod_i d\phi_i$ to $\prod_i d\chi_i$.

<details><summary><strong>Solution</strong></summary>

At each site,

$$
d\phi_i=e^{\chi_i}d\chi_i.
$$

Therefore

$$
\prod_{i=1}^N d\phi_i
=\left(\prod_{i=1}^N e^{\chi_i}\right)
\prod_{i=1}^N d\chi_i.
$$

The Jacobian is

$$
J[\chi]=\exp\left(\sum_{i=1}^N\chi_i\right).
$$

In a continuum limit, this becomes a regulator-dependent local term proportional to a cutoff-dependent density times $\int d^d x\,\chi(x)$.

</details>

## References

- S. Coleman, *Aspects of Symmetry*. Functional integration, Faddeev–Popov gauge fixing, instanton collective coordinates, and measure factors.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Functional integrals, gauge fixing, ghost determinants, and generating functionals.
- M. Srednicki, *Quantum Field Theory*. Bosonic and fermionic path-integral measures, ghosts, determinants, anomalies, and field redefinitions.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Functional methods, gauge fixing, field redefinitions, BRST, and anomaly-related measure issues.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Path-integral measures, Schwinger–Dyson equations, Ward–Takahashi identities, and anomaly calculations.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, changes of variables, renormalization, gauge fixing, and anomalies.
- A. Zee, *Quantum Field Theory in a Nutshell*. Physical discussion of path-integral measures, anomalies, and gauge fixing.
- K. Fujikawa and H. Suzuki, *Path Integrals and Quantum Anomalies*. Standard reference for measure-based anomaly calculations.
- V. Pestun et al., *Localization Techniques in Quantum Field Theories*. One-loop determinants, supersymmetric localization, equivariant measures, and zero-mode factors.

## Version history

- 2026-06-24: First polished draft. Introduced finite-dimensional bosonic and Grassmann Jacobians, regulated field measures, trace-log functional Jacobians, local field redefinitions, collective-coordinate measures, Faddeev–Popov-type factors, Fujikawa anomaly logic, and exercises.
