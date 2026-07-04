---
title: "Schrödinger Operators"
description: "Explains Schrödinger operators as self-adjoint differential operators with potentials, including domains, quadratic forms, bound states, scattering states, resolvents, spectral density, zero modes, negative modes, and QFT fluctuation operators."
sidebar:
  label: "Schrödinger Operators"
  order: 9
level: Graduate
status: "Polished draft"
source: "Standard references on Schrödinger operators, spectral theory, scattering theory, solitons, semiclassical analysis, and QFT fluctuation determinants, including Reed–Simon, Teschl, Simon, Yafaev, Newton, Taylor, Coleman, Rajaraman, Dashen–Hasslacher–Neveu, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, and mathematical-physics treatments of resolvents and heat kernels."
topics:
  - Schrödinger operators
  - self-adjointness
  - quadratic forms
  - bound states
  - scattering states
  - continuous spectrum
  - resolvents
  - spectral density
  - zero modes
  - negative modes
  - fluctuation operators
  - phase shifts
  - determinant ratios
canonicalTopics:
  - schrodinger-operator
  - self-adjointness
  - quadratic-form
  - bound-state
  - scattering-state
  - continuous-spectrum
  - resolvent
  - spectral-density
  - zero-mode
  - negative-mode
  - fluctuation-operator
  - phase-shift
  - determinant-ratio
researchStatus:
  established:
    - "Schrödinger operators are the standard spectral operators behind bound states, scattering theory, stability analysis, heat kernels, and one-loop determinant ratios."
  active:
    - "Schrödinger operators with singular potentials, rough backgrounds, magnetic fields, matrix-valued potentials, resonances, non-self-adjoint deformations, random media, and soliton or instanton backgrounds remain active in mathematical physics and QFT."
---

## Summary

A Schrödinger operator is a differential operator of the form

$$
H=-\Delta+V
$$

or, with physical nonrelativistic normalization,

$$
H_{\mathrm{phys}}=-\frac{1}{2m}\Delta+V.
$$

In this page the default mathematical normalization is $H=-\Delta+V$. Factors of $2m$ and $\hbar$ can be restored by dimensional analysis; throughout the site $\hbar=c=1$ unless stated otherwise.

Schrödinger operators are where local differential equations meet spectra. They encode bound states, scattering states, resonances, zero modes, negative modes, density of states, determinant ratios, and stability of saddle points in field theory. In QFT they appear in at least three recurring ways:

1. as ordinary quantum-mechanical Hamiltonians in nonrelativistic limits and effective field theories;
2. as spatial mode operators for free fields and fields in backgrounds;
3. as quadratic fluctuation operators around solitons, instantons, bounces, monopoles, vortices, and other classical configurations.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing potential and measure defining a differential expression, then a domain and self-adjoint operator, whose discrete spectrum, continuous spectrum, zero modes, negative modes, resolvent, and Green function feed into QFT applications.](/figures/math-toolkit/schrodinger-operator-spectral-map.svg)

<figcaption>

A Schrödinger operator is not only the expression $-\Delta+V$. The potential, measure, domain, and boundary conditions define the operator. Once self-adjointness is fixed, the spectrum controls bound states, scattering states, Green functions, heat kernels, determinant ratios, and the stability of QFT backgrounds.

</figcaption>
</figure>

The slogan is

$$
\text{potential} + \text{domain}
\quad\Longrightarrow\quad
\text{self-adjoint operator}
\quad\Longrightarrow\quad
\text{spectrum and Green functions}.
$$

The middle arrow is the one people skip. That is usually where the mistakes live.

## Prerequisites

You should know [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/), [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), and [Heat Equation and Heat Kernel](/math-toolkit/differential-equations-green-functions/heat-equation-and-heat-kernel/).

The default spacetime convention is mostly-minus metric, but this page is mostly Euclidean or spatial. A Lorentzian Klein–Gordon operator becomes a family of Schrödinger-type spatial operators after mode decomposition; a Euclidean quadratic fluctuation operator is often elliptic from the start.

## Operator expression versus operator

The expression

$$
-\Delta+V(x)
$$

is not yet an operator. To make it an operator one must specify a Hilbert space and a domain. On $\mathbb R^d$ the natural Hilbert space is often

$$
L^2(\mathbb R^d,d^dx),
$$

and one starts with smooth compactly supported functions

$$
C_c^\infty(\mathbb R^d).
$$

But the physical operator is usually a closed self-adjoint extension of this initial symmetric operator.

On a bounded region $\Omega$, the same expression gives different operators depending on the boundary condition:

$$
\psi|_{\partial\Omega}=0
\qquad\text{Dirichlet},
$$

$$
\partial_n\psi|_{\partial\Omega}=0
\qquad\text{Neumann},
$$

or more generally

$$
\partial_n\psi+\alpha\psi=0
\qquad\text{Robin}.
$$

These choices change the spectrum, the heat kernel, the Green function, and the determinant. So the notation $H=-\Delta+V$ is a shorthand, not a complete definition.

A useful distinction is:

| Object | What it means |
|---|---|
| differential expression | the local formula $-\Delta+V$ |
| minimal operator | expression acting on a small domain such as $C_c^\infty$ |
| closed extension | operator obtained by completing or extending the domain |
| self-adjoint realization | the operator whose spectral theorem, unitary evolution, and real spectrum are available |
| resolvent | $(H-z)^{-1}$, defined away from the spectrum |

In physics notation this distinction is often hidden. In serious calculations, especially with boundaries, singular potentials, gauge backgrounds, zero modes, or solitons, hiding it is how gremlins get tenure.

## The quadratic form viewpoint

For many Schrödinger operators the safest definition begins with the quadratic form

$$
q[\psi]=\int d^dx\,\left(|\nabla\psi|^2+V(x)|\psi|^2\right).
$$

If $q$ is densely defined, closed, and bounded below, it determines a self-adjoint operator $H$ by

$$
q[\phi,\psi]=\langle \phi,H\psi\rangle
$$

for $\psi$ in the operator domain. This is often more stable than trying to specify $H\psi=-\Delta\psi+V\psi$ pointwise.

The form viewpoint is especially useful when $V$ is not smooth. For example, singular attractive potentials, delta-function interactions, Coulomb potentials, and inverse-square potentials may still define good operators, but the domain is no longer “all twice differentiable functions.” The domain carries the boundary or matching condition produced by the singularity.

For a real potential $V$, the formal expression $-\Delta+V$ is symmetric:

$$
\langle\phi,H\psi\rangle=\langle H\phi,\psi\rangle
$$

if boundary terms vanish. Self-adjointness is stronger: the operator must equal its adjoint as an operator, including the domain. This stronger condition is what gives real spectral measures and unitary time evolution.

## Spectrum: bound, continuous, threshold, resonance

The spectral equation is

$$
H\psi=E\psi.
$$

If $\psi\in L^2$ and $E$ is isolated with finite multiplicity, $E$ is a discrete eigenvalue. In quantum mechanics this is a bound state. If the generalized eigenfunctions are not square-integrable but describe oscillatory asymptotic states, the corresponding energies belong to the continuous spectrum.

For short-range potentials on $\mathbb R^d$, a common picture is

$$
\sigma_{\mathrm{ess}}(H)=[0,\infty),
$$

with possible negative discrete eigenvalues

$$
E_0<E_1<\cdots<0.
$$

The exact statement depends on the decay and singularity of $V$, but the picture is robust enough for many QFT applications: negative eigenvalues are bound states; positive energies are scattering states; $E=0$ is a threshold.

A **zero mode** is an eigenfunction or generalized eigenfunction with $E=0$. It often signals a symmetry or collective coordinate. A **negative mode** has $E<0$ and usually signals instability of a saddle. A **resonance** is not an ordinary $L^2$ eigenfunction; it is a pole of the analytically continued resolvent or scattering matrix on an unphysical sheet. Resonances behave like unstable states, not honest normalizable states.

This vocabulary is central in semiclassical QFT. Around a classical configuration $\phi_{\mathrm{cl}}$, the quadratic action often has the form

$$
S[\phi_{\mathrm{cl}}+\eta]
=S[\phi_{\mathrm{cl}}]+\frac12\langle\eta,H_{\mathrm{fluc}}\eta\rangle+\cdots.
$$

If $H_{\mathrm{fluc}}$ has a negative mode, the saddle is unstable. If it has zero modes, one must introduce collective coordinates or divide by gauge volume. If it has a continuous spectrum, determinant ratios must be defined with scattering data or heat kernels.

## Free particle and the resolvent

For the free operator on the line,

$$
H_0=-\frac{d^2}{dx^2},
$$

the resolvent is

$$
R_0(z)=(H_0-z)^{-1},
\qquad z\notin[0,\infty).
$$

Its kernel is

$$
G_0(z;x,y)=\frac{i}{2k}e^{ik|x-y|},
\qquad
k^2=z,
\qquad
\operatorname{Im} k>0.
$$

It satisfies

$$
\left(-\frac{d^2}{dx^2}-z\right)G_0(z;x,y)=\delta(x-y).
$$

The condition $\operatorname{Im}k>0$ makes the kernel decay when $z$ is off the spectrum. As $z$ approaches the continuous spectrum from above or below, one gets boundary values

$$
R_0(E\pm i0).
$$

These are not the same distribution. In scattering theory, the outgoing and incoming boundary values are different choices of inverse for an operator that is not invertible on the spectrum.

In higher dimensions the free resolvent has the Fourier representation

$$
G_0(z;\mathbf x,\mathbf y)
=\int\frac{d^dk}{(2\pi)^d}\,
\frac{e^{i\mathbf k\cdot(\mathbf x-\mathbf y)}}{|\mathbf k|^2-z}.
$$

This looks like a Euclidean propagator with an energy parameter. The singularity as $\mathbf x\to\mathbf y$ is local; the boundary value at $z=E\pm i0$ contains scattering information.

## Spectral theorem and Green kernels

For a self-adjoint Schrödinger operator, the spectral theorem gives a projection-valued measure $dP(E)$ such that

$$
H=\int E\,dP(E).
$$

The resolvent is

$$
R(z)=(H-z)^{-1}
=\int\frac{dP(E)}{E-z}.
$$

If this operator has a kernel, write

$$
G_z(x,y)=\langle x|(H-z)^{-1}|y\rangle.
$$

For a purely discrete spectrum with normalized eigenfunctions $\psi_n$,

$$
G_z(x,y)
=\sum_n\frac{\psi_n(x)\overline{\psi_n(y)}}{E_n-z}.
$$

When the spectrum has a continuous part, this becomes a sum plus an integral against a spectral measure:

$$
G_z(x,y)
=\sum_n\frac{\psi_n(x)\overline{\psi_n(y)}}{E_n-z}
+\int_{\sigma_{\mathrm{cont}}}dE\,
\frac{\rho(E;x,y)}{E-z}.
$$

The local spectral density is the discontinuity of the resolvent:

$$
\rho(E;x,y)
=\frac{1}{2\pi i}\left[ G_{E+i0}(x,y)-G_{E-i0}(x,y)\right]
$$

when the boundary values exist in an appropriate weak sense.

This formula is the same analytic idea that appears in QFT propagators: spectra are encoded in discontinuities across cuts. The variables and signatures differ, but the complex-analysis skeleton is the same.

## Scattering states and phase shifts

For short-range potentials, positive-energy states solve

$$
(-\Delta+V)\psi=E\psi,
\qquad
E=k^2>0.
$$

They are not square-integrable on $\mathbb R^d$, so they are not Hilbert-space eigenvectors. They are generalized eigenfunctions. In the simplest incoming-plane-wave setup,

$$
\psi_{\mathbf k}^{(+)}(\mathbf x)
=e^{i\mathbf k\cdot\mathbf x}
-R_0(k^2+i0)V\psi_{\mathbf k}^{(+)}(\mathbf x).
$$

This is the Lippmann–Schwinger equation in the convention

$$
R_0(z)=(-\Delta-z)^{-1}.
$$

The superscript $(+)$ indicates outgoing boundary conditions. The opposite boundary value gives incoming conditions.

In one dimension or in a radial partial-wave decomposition, scattering information is often packaged in phase shifts. For a partial wave labeled by $\ell$, the large-$r$ behavior has the schematic form

$$
\psi_{\ell}(r)
\sim
\sin\left(kr-\frac{\ell\pi}{2}+\delta_\ell(k)\right).
$$

The derivative of the phase shift measures the change in spectral density relative to the free problem. Schematically,

$$
\Delta\rho(E)
\sim
\frac{1}{\pi}\frac{d\delta}{dE}
$$

with appropriate sums over channels and bound-state terms. This relation is the workhorse behind many one-loop determinant and Casimir-energy calculations.

## Bound states and zero modes

A bound state is an $L^2$ solution of

$$
H\psi_n=E_n\psi_n.
$$

For a short-range potential with $E_n<0$, the wavefunction decays exponentially at infinity. In one dimension, if

$$
H=-\frac{d^2}{dx^2}+V(x)
$$

and $V(x)\to0$, a bound state with $E=-\kappa^2$ behaves as

$$
\psi(x)\sim e^{-\kappa |x|}
$$

at large $|x|$.

Zero modes require special care. Suppose a soliton solution $\phi_{\mathrm{cl}}(x)$ solves

$$
-\phi_{\mathrm{cl}}''+U'(\phi_{\mathrm{cl}})=0.
$$

The fluctuation operator is

$$
H_{\mathrm{fluc}}=-\frac{d^2}{dx^2}+U''(\phi_{\mathrm{cl}}(x)).
$$

Differentiating the classical equation gives

$$
H_{\mathrm{fluc}}\,\phi_{\mathrm{cl}}'=0.
$$

The zero mode is the derivative of the background because translating the soliton costs no energy. In the path integral, this mode cannot be treated as an ordinary Gaussian direction. It must be replaced by an integral over the collective coordinate, such as the soliton center.

Negative modes are different. A negative eigenvalue of $H_{\mathrm{fluc}}$ means the action decreases in that direction. Bounces describing false-vacuum decay have one negative mode. Stable solitons should not have negative modes once gauge and collective-coordinate redundancies are treated correctly.

## Heat kernels and determinant ratios

For a positive Schrödinger operator, the heat kernel is

$$
K(s;x,y)=\langle x|e^{-sH}|y\rangle.
$$

It solves

$$
(\partial_s+H_x)K(s;x,y)=0,
\qquad
K(0;x,y)=\delta(x-y).
$$

The trace is

$$
\operatorname{Tr}e^{-sH}=\int d^dx\,K(s;x,x).
$$

A regularized determinant can be written formally as

$$
\log\det H
=-\int_0^\infty\frac{ds}{s}\,\operatorname{Tr}e^{-sH},
$$

with ultraviolet and infrared qualifications. More often one computes a determinant ratio,

$$
\log\frac{\det H}{\det H_0}
=-\int_0^\infty\frac{ds}{s}\,
\operatorname{Tr}\left(e^{-sH}-e^{-sH_0}\right),
$$

again after removing zero modes and regulating divergences.

In one-dimensional fluctuation problems there is also the Gel'fand–Yaglom method: determinant ratios for second-order operators can be computed from solutions of initial-value problems rather than from explicit eigenvalue products. In scattering problems, determinant ratios can often be expressed through phase shifts and bound states. These methods are different windows onto the same spectral object.

## Magnetic and matrix-valued Schrödinger operators

Gauge fields produce covariant Schrödinger operators. For a charged particle in a background vector potential $A_i$, the operator is

$$
H_A=-(\nabla-iA)^2+V.
$$

For nonabelian backgrounds or fields with internal indices, $A_i$ and $V$ are matrices, and the operator acts on sections of a vector bundle rather than scalar functions. The commutator of covariant derivatives contains curvature:

$$
[D_i,D_j]=-iF_{ij}
$$

in a common physics convention.

This is not just ornamental geometry. In gauge theory, fluctuation operators around classical backgrounds are often matrix-valued Laplace-type or Dirac-type operators. Their heat-kernel coefficients contain gauge curvature, spacetime curvature, and endomorphism terms. Their zero modes are tied to moduli, gauge transformations, and index theorems.

The scalar Schrödinger operator is the training ground. The real calculations often wear matrix boots.

## Relation to relativistic fields

A relativistic free scalar field satisfies

$$
(\partial_t^2+H)\phi=0
$$

when the spatial operator is

$$
H=-\nabla^2+m^2
$$

in flat space. The normal-mode equation is

$$
H u_n=\omega_n^2 u_n.
$$

Thus the spatial Schrödinger-type operator determines the oscillator frequencies of the field. If $H$ has a negative eigenvalue, then $\omega^2<0$, and the mode grows exponentially in time: the background is unstable.

In Euclidean field theory, quadratic fluctuations often look directly like

$$
H_{\mathrm{E}}=-\partial_\tau^2-\nabla^2+m^2+V_{\mathrm{bg}}(x).
$$

This is a Schrödinger-type elliptic operator on spacetime. Its determinant contributes to the one-loop effective action.

In nonrelativistic EFT, the field equation is first order in time:

$$
i\partial_t\psi=H\psi.
$$

The propagator involves

$$
(i\partial_t-H)^{-1},
$$

and its analytic structure is controlled by the same spectral data of $H$.

## A minimal dictionary

| Schrödinger-operator idea | QFT appearance |
|---|---|
| bound state | particle bound state, defect-localized mode, fluctuation trapped by background |
| scattering state | asymptotic mode, continuum contribution, phase shift |
| zero mode | collective coordinate, gauge redundancy, modulus, Goldstone direction |
| negative mode | instability, false-vacuum bounce direction, sphaleron direction |
| resolvent | Green function, spectral density, response kernel |
| heat kernel | determinant, anomaly coefficient, UV expansion |
| phase shift | change in density of states, one-loop energy shift |
| threshold | onset of multiparticle or continuum states |
| resonance | unstable state, pole on an unphysical sheet |
| self-adjoint extension | boundary condition, point interaction, defect condition |

The same formal operator may appear in all these guises. The interpretation depends on which variable is time, which Hilbert space is being used, and which analytic continuation or boundary prescription is chosen.

## Common pitfalls

**Writing $H=-\Delta+V$ does not define the operator.** The Hilbert space, domain, boundary conditions, and behavior at singularities are part of the definition.

**Symmetric is not the same as self-adjoint.** A symmetric operator satisfies the integration-by-parts identity on its domain. A self-adjoint operator equals its adjoint including the domain. The difference is invisible until it matters, which is rude but traditional.

**Continuous-spectrum eigenfunctions are not ordinary Hilbert-space vectors.** Plane waves and scattering states are generalized eigenfunctions. Treating them as normalizable vectors without distributions or boxes leads to wrong normalizations.

**A resonance is not a bound state.** A resonance is usually a pole of an analytically continued resolvent or scattering matrix. It is not an $L^2$ eigenfunction of a self-adjoint operator on the physical sheet.

**A zero mode is not a small positive eigenvalue.** It means the Gaussian integral is degenerate. In a path integral one must project it out, fix a gauge, or introduce collective coordinates.

**A negative mode is not a harmless sign.** It changes the saddle interpretation. In false-vacuum decay it is essential; in a supposedly stable soliton it signals a problem unless it is removed by a constraint or gauge redundancy.

**The determinant of an infinite-dimensional operator is not a product you can casually multiply.** Determinants require regularization, normalization, and zero-mode treatment. Ratios are usually better behaved than absolute determinants.

**The $i0$ prescription is not optional.** The boundary value of the resolvent determines incoming or outgoing scattering, retarded or advanced response, and physical spectral density.

## Practical checklist

When a Schrödinger operator appears in a calculation, ask:

| Question | Why it matters |
|---|---|
| What is the Hilbert space? | fixes inner product and normalization |
| What is the domain? | fixes boundary conditions and self-adjointness |
| Is the operator bounded below? | determines stability and heat-kernel behavior |
| Are there zero modes? | determines collective coordinates or constraints |
| Are there negative modes? | determines whether the saddle is stable |
| Is the spectrum discrete, continuous, or mixed? | determines sums, integrals, and density of states |
| Which resolvent boundary value is used? | fixes scattering or response prescription |
| Is a determinant being computed absolutely or relatively? | fixes regularization and subtraction |
| Are there singular potentials or boundaries? | domain issues may dominate the calculation |

This checklist looks bureaucratic, but it saves lives. Well, okay, it saves one-loop calculations. Same emotional neighborhood.

## Exercises

### Exercise 1: Free resolvent on the line

Let

$$
H_0=-\frac{d^2}{dx^2}
$$

on $\mathbb R$. Show that

$$
G_0(z;x,y)=\frac{i}{2k}e^{ik|x-y|},
\qquad
k^2=z,
\qquad
\operatorname{Im}k>0,
$$

satisfies

$$
(H_0-z)G_0(z;x,y)=\delta(x-y).
$$

<details><summary><strong>Solution</strong></summary>

For $x\ne y$, the function $e^{ik|x-y|}$ satisfies

$$
-\frac{d^2}{dx^2}e^{ik|x-y|}=k^2e^{ik|x-y|}=z e^{ik|x-y|},
$$

so $(H_0-z)G_0=0$ away from $x=y$.

The delta function comes from the jump in the first derivative. For $x>y$,

$$
\partial_xG_0=-\frac12e^{ik(x-y)},
$$

while for $x<y$,

$$
\partial_xG_0=\frac12e^{ik(y-x)}.
$$

Therefore

$$
\partial_xG_0(y^+,y)-\partial_xG_0(y^-,y)=-1.
$$

A function whose first derivative jumps by $J$ has second derivative containing $J\delta(x-y)$. Hence $-\partial_x^2G_0$ contains $-J\delta(x-y)=\delta(x-y)$. The remaining smooth part cancels $zG_0$.

The condition $\operatorname{Im}k>0$ chooses the decaying branch of the off-spectrum resolvent.

</details>

### Exercise 2: Delta-function attractive well

Consider

$$
H=-\frac{d^2}{dx^2}-\lambda\delta(x),
\qquad
\lambda>0.
$$

Find its bound-state energy.

<details><summary><strong>Solution</strong></summary>

A bound state has energy $E=-\kappa^2$ with $\kappa>0$. Away from $x=0$,

$$
-\psi''=-\kappa^2\psi,
$$

so the normalizable solution is

$$
\psi(x)=Ae^{-\kappa |x|}.
$$

Integrate the eigenvalue equation across a small interval around $0$:

$$
\int_{-\epsilon}^{\epsilon}\left(-\psi''-\lambda\delta(x)\psi\right)dx
=\int_{-\epsilon}^{\epsilon}E\psi\,dx.
$$

The right-hand side vanishes as $\epsilon\to0$, so

$$
-\left[\psi'(0^+)-\psi'(0^-)\right]-\lambda\psi(0)=0.
$$

Thus

$$
\psi'(0^+)-\psi'(0^-)=-\lambda\psi(0).
$$

For $Ae^{-\kappa |x|}$, the jump is

$$
-\kappa A-\kappa A=-2\kappa A.
$$

Therefore $2\kappa=\lambda$, and

$$
E=-\kappa^2=-\frac{\lambda^2}{4}.
$$

</details>

### Exercise 3: Translational zero mode

Let $\phi_{\mathrm{cl}}(x)$ solve

$$
-\phi_{\mathrm{cl}}''+U'(\phi_{\mathrm{cl}})=0.
$$

Show that the fluctuation operator

$$
H=-\frac{d^2}{dx^2}+U''(\phi_{\mathrm{cl}}(x))
$$

has a zero mode.

<details><summary><strong>Solution</strong></summary>

Differentiate the classical equation with respect to $x$:

$$
-\phi_{\mathrm{cl}}'''+U''(\phi_{\mathrm{cl}})\phi_{\mathrm{cl}}'=0.
$$

This is exactly

$$
\left(-\frac{d^2}{dx^2}+U''(\phi_{\mathrm{cl}})\right)\phi_{\mathrm{cl}}'=0.
$$

So $\phi_{\mathrm{cl}}'$ is a zero mode. Physically, translating the classical solution changes its center but not its action.

</details>

### Exercise 4: Resolvent discontinuity and spectral density

Let

$$
R(z)=\int\frac{dP(E')}{E'-z}
$$

be the resolvent of a self-adjoint operator. Show formally that

$$
\frac{1}{2\pi i}\left[R(E+i0)-R(E-i0)\right]
$$

is the spectral density at $E$.

<details><summary><strong>Solution</strong></summary>

Use the distribution identity

$$
\frac{1}{x\mp i0}=\operatorname{PV}\frac{1}{x}\pm i\pi\delta(x).
$$

Since

$$
R(E+i0)=\int\frac{dP(E')}{E'-E-i0},
$$

and

$$
R(E-i0)=\int\frac{dP(E')}{E'-E+i0},
$$

the principal-value pieces cancel in the difference and the delta pieces add:

$$
R(E+i0)-R(E-i0)=2\pi i\int dP(E')\delta(E'-E).
$$

Therefore

$$
\frac{1}{2\pi i}\left[R(E+i0)-R(E-i0)\right]
$$

is the operator-valued density $dP/dE$ when such a density exists. As a kernel, it gives the local spectral density.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vols. I–IV. Standard reference for self-adjointness, spectral theory, scattering, and Schrödinger operators.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. Clear modern reference for one-dimensional Schrödinger operators, Sturm–Liouville theory, spectral measures, and scattering.
- B. Simon, *Quantum Mechanics for Hamiltonians Defined as Quadratic Forms*. Classic source for the quadratic-form approach.
- D. R. Yafaev, *Mathematical Scattering Theory*. Detailed reference for scattering theory and spectral analysis.
- R. G. Newton, *Scattering Theory of Waves and Particles*. Physics-oriented reference for phase shifts, scattering amplitudes, and bound states.
- M. E. Taylor, *Partial Differential Equations* and related analysis texts. Useful for elliptic operators, resolvents, and spectral methods.
- S. Coleman, *Aspects of Symmetry*. Classic physics source for semiclassical methods, instantons, and fluctuation operators.
- R. Rajaraman, *Solitons and Instantons*. Pedagogical treatment of soliton fluctuation spectra and zero modes.
- R. Dashen, B. Hasslacher, and A. Neveu, “Nonperturbative Methods and Extended-Hadron Models in Field Theory.” Classic papers on soliton quantization and spectral methods.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Broad reference for path integrals, instantons, determinants, and spectral techniques.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Standard QFT reference for propagators, spectral representations, scattering, and effective actions.
- M. Srednicki, *Quantum Field Theory*. Useful for propagators, spinor and scalar fields, functional determinants, and one-loop calculations.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Pedagogical reference for QFT propagators, Green functions, and perturbative applications.

## Version history

- 2026-06-25: Initial polished draft.
