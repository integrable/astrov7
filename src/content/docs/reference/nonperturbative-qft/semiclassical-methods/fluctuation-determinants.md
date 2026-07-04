---
title: "Fluctuation Determinants"
description: "Explains one-loop fluctuation determinants around semiclassical saddles, including determinant ratios, zero-mode exclusions, regularization, fermions, and gauge fixing."
sidebar:
  label: "Fluctuation Determinants"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman; Zinn-Justin; Mariño; Shifman; Srednicki."
topics:
  - fluctuation determinants
  - one-loop approximation
  - Gaussian functional integrals
  - determinant ratios
  - heat kernel
  - zeta regularization
  - Gelfand–Yaglom method
  - instantons
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - fluctuation-determinants
  - one-loop-determinants
researchStatus:
  established:
    - "Gaussian integration around a regulated nonzero fluctuation spectrum gives the one-loop determinant factor in a semiclassical saddle expansion."
  active:
    - "Determinants in gauge theories, theories with fermion zero modes, curved backgrounds, real-time contours, and complex saddles often require model-specific regularization and interpretation."
---

## Summary

A **fluctuation determinant** is the Gaussian prefactor obtained by expanding a path integral to quadratic order around a saddle. If a Euclidean saddle $\phi_s$ has quadratic fluctuation operator $\Delta_s$, then the bosonic one-loop contribution is schematically

$$
Z_s^{\text{1-loop}}
\sim
 e^{-S_E[\phi_s]/\hbar}
 \left(\det{}^{\prime}\Delta_s\right)^{-1/2},
$$

where the prime means that zero modes are omitted. In practice one usually computes a **determinant ratio**, for example

$$
\mathcal K_s
\sim
\left(\frac{\det\Delta_{\mathrm{ref}}}{\det{}^{\prime}\Delta_s}\right)^{1/2},
$$

because absolute functional determinants contain normalization conventions, ultraviolet divergences, and infinite-volume factors. The zero modes removed from $\det{}^{\prime}\Delta_s$ reappear as [collective-coordinate](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) integrals.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic pipeline from a semiclassical saddle to its quadratic operator, spectrum, regulated determinant, and one-loop prefactor.](/figures/nonperturbative-qft/fluctuation-determinant-pipeline.svg)

<figcaption>

The one-loop factor is built from the nonzero spectrum of the quadratic fluctuation operator. Zero modes, negative modes, gauge redundancies, ultraviolet divergences, and normalization choices must be handled before $(\det{}^{\prime}\Delta_s)^{-1/2}$ becomes a physical prefactor.

</figcaption>
</figure>

Fluctuation determinants are where the phrase “one-loop correction around an instanton” becomes literal. The classical saddle gives the exponential $e^{-S_E[\phi_s]/\hbar}$. The determinant says how the neighboring configurations breathe around that saddle.

## Prerequisites

You should know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), and [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/).

This page assumes Euclidean signature and the path-integral weight $e^{-S_E/\hbar}$. It treats determinant formulas as regulated finite-volume formulas first, then explains what survives in the continuum and infinite-volume limits.

## Core idea

A semiclassical saddle is not a single field configuration floating alone in field space. It has a neighborhood. To leading order, that neighborhood is controlled by the second variation of the action.

For a bosonic field $\phi$, expand around a saddle $\phi_s$ as

$$
\phi=\phi_s+\sqrt{\hbar}\,\eta.
$$

Since $\phi_s$ obeys the Euclidean equation of motion, the linear term vanishes and

$$
S_E[\phi_s+\sqrt{\hbar}\,\eta]
=S_E[\phi_s]+\frac{\hbar}{2}(\eta,\Delta_s\eta)+O(\hbar^{3/2}).
$$

Thus the local path integral contains the Gaussian

$$
\int \mathcal D\eta\,
\exp\left[-\frac12(\eta,\Delta_s\eta)\right].
$$

If $\Delta_s$ has eigenvalues $\lambda_n$, this Gaussian is morally the product

$$
\prod_n \lambda_n^{-1/2}.
$$

That product is the determinant factor

$$
(\det\Delta_s)^{-1/2}.
$$

The word “morally” is doing work. In QFT the product is infinite, often divergent, and sometimes includes zero or negative eigenvalues. A trustworthy calculation says exactly which spectrum is being multiplied, how it is regulated, and what it is being compared to.

## Setup and conventions

Let the quadratic fluctuation operator be defined by

$$
(\eta,\Delta_s\eta)
=
\int d^dx\,d^dy\,
\eta_i(x)\Delta_{s,ij}(x,y)\eta_j(y),
$$

or, for a local action,

$$
(\eta,\Delta_s\eta)
=
\int d^dx\,\eta_i(x)(\Delta_s\eta)_i(x).
$$

The inner product fixes the normalization of eigenmodes. For real scalar fields in flat Euclidean space the default is

$$
(\eta_1,\eta_2)=\int d^dx\,\eta_1(x)\eta_2(x),
$$

with obvious generalizations for multiplets, gauge indices, curved backgrounds, and fermions.

For the moment suppose the theory is in a finite box and the ultraviolet has been regulated, so $\Delta_s$ has a discrete spectrum. Choose orthonormal eigenfunctions

$$
\Delta_s u_n=\lambda_n u_n,
\qquad
(u_m,u_n)=\delta_{mn},
$$

and expand

$$
\eta(x)=\sum_n c_nu_n(x).
$$

Then

$$
(\eta,\Delta_s\eta)=\sum_n\lambda_n c_n^2.
$$

With the normalized Gaussian measure

$$
\prod_n\frac{dc_n}{\sqrt{2\pi}},
$$

each positive eigenvalue contributes

$$
\int_{-\infty}^{\infty}\frac{dc_n}{\sqrt{2\pi}}\,
\exp\left(-\frac12\lambda_n c_n^2\right)
=\lambda_n^{-1/2}.
$$

Therefore

$$
\int \mathcal D\eta\,e^{-(\eta,\Delta_s\eta)/2}
=(\det\Delta_s)^{-1/2}
$$

for a finite-dimensional positive operator. This is the clean core hidden inside every one-loop determinant.

## Why determinant ratios are physical

The absolute determinant depends on the path-integral measure. Multiplying every mode coefficient by a fixed normalization changes every determinant by a constant. In a finite-dimensional integral this is harmless. In QFT it is an infinite constant.

Physical semiclassical formulas usually compare a saddle to a reference configuration. For example, in one-dimensional Euclidean quantum mechanics around an instanton $q_{\mathrm{inst}}(\tau)$ one encounters

$$
\Delta_{\mathrm{inst}}
= -\frac{d^2}{d\tau^2}+V''(q_{\mathrm{inst}}(\tau)),
$$

and compares it with the harmonic operator in the perturbative vacuum,

$$
\Delta_0
= -\frac{d^2}{d\tau^2}+\omega^2.
$$

The determinant factor appears as

$$
\left(\frac{\det\Delta_0}{\det{}^{\prime}\Delta_{\mathrm{inst}}}\right)^{1/2},
$$

up to the zero-mode measure and conventional constants. The ratio has a direct meaning: it measures how the fluctuation spectrum near the instanton differs from the fluctuation spectrum near the vacuum.

In field theory the same logic applies. For a soliton, bounce, monopole, or instanton, the determinant ratio measures the change in the density of small oscillations caused by the nontrivial background.

## The primed determinant

Zero modes are eigenfunctions with

$$
\Delta_s Z_a=0.
$$

If one included them in the determinant, then

$$
\det\Delta_s=0,
\qquad
(\det\Delta_s)^{-1/2}=\infty.
$$

This infinity is not a physical blow-up. It means that the saddle is not isolated. For example, translating an instanton center or a kink center produces another solution with the same action. The Gaussian approximation is flat along that direction, so it should be integrated as a coordinate on the family of saddles, not as an oscillator.

The primed determinant means

$$
\det{}^{\prime}\Delta_s
=\prod_{\lambda_n\ne0}\lambda_n.
$$

A more honest phrase is: “the determinant over the fluctuation directions normal to the moduli space of saddles.” The zero-mode directions are treated by collective coordinates.

Negative modes require a different warning. If $\Delta_s$ has an eigenvalue $\lambda_-<0$, the saddle is not a local minimum of the Euclidean action. For a false-vacuum bounce, exactly one negative mode is expected and is essential: it gives the imaginary part of the false-vacuum energy from which the decay rate is extracted. One should not simply put $|\lambda_-|$ into a determinant and pretend the saddle is stable.

## Regularization

A functional determinant is often written as

$$
\log\det\Delta=\operatorname{Tr}\log\Delta.
$$

Using the heat kernel, this becomes formally

$$
\log\det\Delta
=-\int_0^\infty\frac{ds}{s}\,\operatorname{Tr}e^{-s\Delta}
$$

up to additive conventions. The small-$s$ region probes ultraviolet modes and typically diverges. Those divergences are local: they are absorbed into the same counterterms that renormalize the original QFT.

Several regularizations are common.

| Method | Basic idea | Good for |
|---|---|---|
| Mode cutoff | Multiply a finite number of eigenvalues, then subtract divergences. | Pedagogical finite-volume calculations. |
| Heat kernel | Use $\operatorname{Tr}e^{-s\Delta}$ and isolate small-$s$ divergences. | Local counterterms, curved backgrounds, anomaly-related calculations. |
| Zeta function | Define $\zeta_\Delta(s)=\sum_n\lambda_n^{-s}$ and $\log\det_\zeta\Delta=-\zeta_\Delta'(0)$. | Spectral problems with analytic continuation. |
| Pauli–Villars | Divide by determinants of massive regulator fields. | Instanton calculations and explicit ultraviolet bookkeeping. |
| Dimensional regularization | Continue spacetime dimension. | Perturbative matching and determinant expansions. |
| Lattice regulator | Make the spectrum finite at finite lattice spacing and volume. | Nonperturbative numerical definitions. |

Different regulators can assign different intermediate finite pieces. A physical answer is obtained only after the couplings and operators are renormalized in a specified scheme.

## A one-dimensional shortcut

In one-dimensional quantum mechanics, determinant ratios of Schrödinger-type operators can often be computed without finding the full spectrum. For Dirichlet boundary conditions on an interval, consider

$$
L=-\frac{d^2}{d\tau^2}+U(\tau).
$$

Let $y(\tau)$ solve

$$
Ly=0,
\qquad
 y(\tau_i)=0,
\qquad
 y'(\tau_i)=1.
$$

For another operator $L_0$ with solution $y_0$ satisfying the same initial conditions, the Gelfand–Yaglom result gives, schematically,

$$
\frac{\det L}{\det L_0}
=\frac{y(\tau_f)}{y_0(\tau_f)}.
$$

The boundary conditions matter, and zero modes require a modified formula. But the lesson is beautiful: in one dimension, a functional determinant can be reduced to an initial-value problem for an ordinary differential equation. This is one reason quantum-mechanical instantons are the best training ground for field-theory instantons.

## Phase shifts and density of states

For solitons or instantons on an infinite line, the fluctuation operator may have both bound states and continuum scattering states. Then determinant ratios are often computed by comparing densities of states. A background changes the scattering phase shift $\delta(k)$, and the density of continuum modes changes by

$$
\rho(k)-\rho_0(k)=\frac{1}{\pi}\frac{d\delta(k)}{dk}
$$

in a typical one-dimensional problem, up to conventions and boundary-condition details.

Then a determinant ratio is built from bound-state eigenvalues plus an integral over the changed continuum density. This method gives a useful physical picture: the determinant counts how the saddle rearranges the small-oscillation spectrum.

## Fermions, ghosts, and signs

Bosonic Gaussian integrals give inverse square roots of determinants. Fermionic Gaussian integrals give determinants or Pfaffians.

For complex Grassmann fields,

$$
\int D\bar\psi D\psi\,
\exp(-\bar\psi D\psi)=\det D.
$$

For Majorana fermions the corresponding object is a Pfaffian,

$$
\operatorname{Pf}(\mathcal D)^2=\det\mathcal D.
$$

Fermion zero modes are especially important. If $D$ has exact zero modes, the fermion determinant vanishes unless the path integral includes operator insertions that soak up the corresponding Grassmann integrations. This is the origin of many instanton selection rules and effective vertices.

Gauge theories introduce another layer. One cannot take a determinant over gauge copies. After gauge fixing, the quadratic gauge-field operator is accompanied by a ghost operator. A schematic one-loop gauge prefactor has the form

$$
\mathcal K_s^{\mathrm{gauge}}
\sim
\frac{\det \Delta_{\mathrm{gh}}}{(\det{}^{\prime}\Delta_{\mathrm{vec}})^{1/2}},
$$

again with zero modes, regulator factors, counterterms, group volumes, and gauge choices treated carefully. This formula is schematic, not a substitute for an actual instanton-measure calculation.

## Interpretation

A fluctuation determinant is a quantum correction to the weight of a classical saddle. It is not merely a technical decoration.

If the saddle has many soft modes, the determinant can enhance its contribution. If the background strongly repels modes, it can suppress it. If the determinant contains a negative mode, the saddle may describe decay rather than a stable energy shift. If the determinant contains fermion zero modes, the saddle may contribute only to correlation functions with the right operator insertions.

For this reason, a semiclassical statement such as

$$
\text{amplitude}\sim e^{-S_{\mathrm{inst}}}
$$

is incomplete. A trustworthy statement says

$$
\text{amplitude}
\sim
 e^{-S_{\mathrm{inst}}}
\times
\text{determinant ratio}
\times
\text{zero-mode measure}
\times
\text{operator factors}
\times
\cdots.
$$

The exponential often dominates parametrically, but the prefactor decides dimensions, selection rules, renormalization-scale dependence, and sometimes whether the contribution exists at all.

## Common mistakes

**Mistaking an absolute determinant for an observable.** Most functional determinants are meaningful only after specifying a regulator, scheme, normalization, and reference operator.

**Forgetting the prime.** Zero modes are not ordinary Gaussian directions. Leaving them inside $\det\Delta_s$ gives a meaningless infinity.

**Treating a negative mode as a harmless sign.** A negative mode changes the interpretation of the saddle. For bounces it is tied to decay.

**Ignoring boundary conditions.** Determinants depend on whether the interval is periodic, Dirichlet, thermal, finite-volume, or infinite-volume with scattering boundary conditions.

**Multiplying over gauge copies.** Gauge redundancies must be fixed or quotiented. Ghost determinants and collective coordinates are part of the calculation, not optional decorations.

**Forgetting fermion zero-mode saturation.** A fermion determinant with zero modes vanishes unless the correlation function supplies the needed Grassmann factors.

## Limitations and caveats

Fluctuation determinants are controlled only when the saddle expansion is controlled. They do not rescue a semiclassical expansion with no large action, no stable contour, or no separation between collective coordinates and heavy modes.

In strongly coupled theories, determinant language may still be formally useful, but the one-loop approximation around a guessed saddle need not be reliable. In real-time problems, the relevant fluctuation operators need not be positive Euclidean operators. In complex-saddle problems, determinants require a choice of contour and phase. In gauge theories, determinant phases and global anomalies can carry physics that is not visible in a naive eigenvalue product.

The safe rule is boring and excellent: define the regulated problem first, identify the saddle and its fluctuation spectrum, separate zero and negative modes, fix gauge redundancies, renormalize, and only then take limits.

## Research status

- **Established:** One-loop determinants are a standard part of semiclassical instanton, soliton, bounce, and large-saddle calculations. In regulated finite-dimensional problems, their derivation is ordinary Gaussian integration.
- **Established:** In continuum QFT, determinant divergences are local and must be treated with the same renormalization discipline as loop diagrams.
- **Active:** Determinant phases, fermion Pfaffians, gauge-field zero modes, complex saddles, real-time contours, and finite-density sign problems remain subtle in many modern applications.
- **Model-dependent:** A semiclassical determinant computed around a classical configuration is useful only if that configuration is a relevant saddle of the path integral being studied.

## Relation to other topics

Fluctuation determinants are the bridge from [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) to [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/). They also feed directly into false-vacuum decay, instanton measures, soliton quantization, fermion zero modes, anomalies, and large-N saddle calculations.

Later pages on instantons and solitons will specialize this page. The present page tells you what the symbol $\det{}^{\prime}\Delta_s$ means; later pages compute it in concrete models.

## Exercises

### Exercise 1: finite Gaussian determinant

Let $H$ be a positive $n\times n$ real symmetric matrix. Show that

$$
\int_{\mathbb R^n}\frac{d^n c}{(2\pi)^{n/2}}
\exp\left(-\frac12c^THc\right)
=(\det H)^{-1/2}.
$$

<details><summary><strong>Solution</strong></summary>

Since $H$ is real symmetric and positive, it can be diagonalized by an orthogonal matrix,

$$
H=O^T\Lambda O,
\qquad
\Lambda=\operatorname{diag}(\lambda_1,\ldots,\lambda_n),
\qquad
\lambda_i>0.
$$

The change of variables $c'=Oc$ has unit Jacobian. Therefore the integral factorizes:

$$
\prod_{i=1}^n
\int_{-\infty}^{\infty}\frac{dc_i}{\sqrt{2\pi}}
\exp\left(-\frac12\lambda_i c_i^2\right)
=
\prod_{i=1}^n\lambda_i^{-1/2}
=(\det H)^{-1/2}.
$$

</details>

### Exercise 2: why ratios cancel measure constants

Suppose a finite-dimensional Gaussian measure is rescaled so that every mode integral acquires an extra constant factor $C$. Show that the ratio of two determinants with the same number of modes is unchanged.

<details><summary><strong>Solution</strong></summary>

For an operator $H$, the Gaussian integral changes as

$$
I_H=C^n(\det H)^{-1/2}.
$$

For a reference operator $H_0$ with the same number of modes,

$$
I_{H_0}=C^n(\det H_0)^{-1/2}.
$$

Thus

$$
\frac{I_H}{I_{H_0}}
=
\left(\frac{\det H_0}{\det H}\right)^{1/2},
$$

and the factor $C^n$ cancels. In QFT this cancellation is one reason determinant ratios are better-defined than absolute determinants, although ultraviolet renormalization is still required.

</details>

### Exercise 3: zero mode and primed determinant

Let $H$ have eigenvalues $0,\lambda_2,\ldots,\lambda_n$ with $\lambda_i>0$ for $i\ge2$. Explain why the ordinary Gaussian integral diverges and define the primed determinant.

<details><summary><strong>Solution</strong></summary>

In the eigenbasis the Gaussian contains

$$
\int_{-\infty}^{\infty}\frac{dc_1}{\sqrt{2\pi}}\,e^{-0\cdot c_1^2/2},
$$

which is an integral over a constant and therefore diverges. The zero direction is not confined by the quadratic action.

The primed determinant omits this direction:

$$
\det{}'H=\prod_{i=2}^n\lambda_i.
$$

The missing integral must be replaced by an integral over the corresponding collective coordinate or symmetry parameter.

</details>

### Exercise 4: derivative of a determinant

For a finite positive operator $H(m^2)=H_0+m^2 I$, show that

$$
\frac{\partial}{\partial m^2}\log\det H(m^2)=\operatorname{Tr}\,H(m^2)^{-1}.
$$

<details><summary><strong>Solution</strong></summary>

Using $\log\det H=\operatorname{Tr}\log H$,

$$
\frac{\partial}{\partial m^2}\log\det H
=\operatorname{Tr}\left(H^{-1}\frac{\partial H}{\partial m^2}\right).
$$

Since $\partial H/\partial m^2=I$,

$$
\frac{\partial}{\partial m^2}\log\det H
=\operatorname{Tr}H^{-1}.
$$

This identity is often useful because traces of Green functions can be easier to regulate or compare than determinants themselves.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on functional integration, instantons, and false-vacuum decay.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean functional integrals, determinants, heat-kernel logic, and renormalization.
- M. Mariño, *Instantons and Large N*, especially the sections on instanton path integrals, functional determinants, the Gelfand–Yaglom method, large-order behavior, and Yang–Mills instantons.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for soliton quantization, instanton measures, zero modes, and gauge-theory examples.
- M. Srednicki, *Quantum Field Theory*, especially the material on path integrals, functional determinants, solitons, monopoles, instantons, and theta vacua.

## Version history

- **2026-06-26:** Initial polished page.
