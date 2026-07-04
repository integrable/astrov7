---
title: "One-Loop Determinants Around Saddles"
description: "Explains how renormalized one-loop determinant ratios are computed around nontrivial semiclassical backgrounds."
sidebar:
  label: "One-Loop Determinants"
  order: 9
level: Graduate
status: "Polished draft"
source: "Coleman; Callan–Coleman; Zinn-Justin; Mariño; Shifman; Weinberg; heat-kernel and phase-shift literature."
topics:
  - one-loop determinants
  - fluctuation operators
  - determinant ratios
  - renormalization
  - heat kernel
  - phase shifts
  - gauge fixing
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - one-loop-determinants
  - fluctuation-determinants
researchStatus:
  established:
    - "Renormalized determinant ratios around semiclassical saddles are a standard one-loop ingredient in instanton, bounce, soliton, and large-field calculations."
  active:
    - "Complex phases, chiral determinants, noncompact moduli, real-time contours, and determinant calculations in strongly coupled backgrounds can be scheme- or regulator-sensitive."
---

## Summary

A **one-loop determinant around a saddle** is the Gaussian quantum correction to a nontrivial classical background. If $\phi_s$ is a Euclidean saddle and $\Delta_s$ is the quadratic fluctuation operator around it, the local saddle contribution has the schematic form

$$
Z_s^{(1)}
=
e^{-S_E[\phi_s]/\hbar}
\,\mathcal J_{\text{zm}}\,
\left(
\frac{\det \Delta_{\text{ref}}}{\det{}'\Delta_s}
\right)^{1/2}
\left(1+O(\hbar)\right),
$$

for a purely bosonic field with positive nonzero modes. The prime means that zero modes have been removed and replaced by the collective-coordinate Jacobian $\mathcal J_{\text{zm}}$. The reference operator $\Delta_{\text{ref}}$ is usually the fluctuation operator in the vacuum or in a nearby trivial background.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic workflow for one-loop determinants: choose a saddle and reference background, form fluctuation operators, remove zero and negative modes, include ghosts and fermions when needed, regulate spectra, add counterterms, and obtain a finite one-loop saddle weight.](/figures/nonperturbative-qft/one-loop-determinants-renormalization.svg)

<figcaption>

A useful one-loop determinant is not an isolated infinite product. It is a regulated and renormalized comparison between a saddle background and a reference background, with zero modes, negative modes, gauge ghosts, fermions, and counterterms treated consistently.

</figcaption>
</figure>

The determinant itself is not usually an observable. What matters is the **renormalized determinant ratio** that multiplies the leading exponential $e^{-S_E[\phi_s]/\hbar}$, or the associated one-loop correction to a soliton mass, instanton measure, bounce rate, or effective action.

This page is more practical than [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/). That page explains why determinants appear. This page explains how they enter actual semiclassical formulas without sweeping ultraviolet divergences, zero modes, gauge redundancies, or scheme dependence under the rug.

## Prerequisites

You should know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

You should also be comfortable with ordinary one-loop renormalization in perturbative QFT. The new ingredient here is not that loops exist; it is that the loop is computed around a nontrivial background.

## Core idea

Around a saddle $\phi_s$, write

$$
\phi=\phi_s+\sqrt{\hbar}\,\eta.
$$

The action expands as

$$
S_E[\phi_s+\sqrt{\hbar}\eta]
=
S_E[\phi_s]
+\frac{\hbar}{2}(\eta,\Delta_s\eta)
+O(\hbar^{3/2}),
$$

so the Gaussian integral gives

$$
\int \mathcal D\eta\,
e^{-(\eta,\Delta_s\eta)/2}
\sim
(\det\Delta_s)^{-1/2}.
$$

In a finite-dimensional problem this is just linear algebra. In QFT it is a product over infinitely many eigenvalues of a differential operator, so it is ultraviolet divergent. It may also have zero eigenvalues from symmetries, negative eigenvalues from instabilities, gauge redundancies from gauge symmetry, and fermionic signs or phases from Grassmann fields.

The one-loop calculation therefore has four jobs:

1. identify the correct fluctuation operators;
2. remove or separately treat zero and negative modes;
3. regulate the determinant and compare it to a reference background;
4. add the counterterms that define the renormalized theory.

A formula that skips any of these steps may still look impressive. That is precisely why it is dangerous.

## Setup and conventions

Let $\phi_s$ be a saddle of the Euclidean action,

$$
\left.\frac{\delta S_E}{\delta\phi}\right|_{\phi_s}=0.
$$

The quadratic fluctuation operator is

$$
\Delta_s
=
S_E''[\phi_s],
$$

understood as an operator with specified boundary conditions and inner product. The reference background $\phi_{\text{ref}}$ has operator $\Delta_{\text{ref}}$.

For a single bosonic field with no gauge symmetry and no negative modes, the formal one-loop effective action difference is

$$
\Gamma^{(1)}[\phi_s;\phi_{\text{ref}}]
=
\frac{\hbar}{2}\operatorname{Tr}'\log\Delta_s
-\frac{\hbar}{2}\operatorname{Tr}\log\Delta_{\text{ref}}.
$$

The prime removes zero modes. In a renormalized QFT, the actual quantity is

$$
\Gamma_{\text{ren}}^{(1)}[\phi_s;\phi_{\text{ref}}]
=
\frac{\hbar}{2}\operatorname{Tr}'\log\frac{\Delta_s}{\mu^2}
-\frac{\hbar}{2}\operatorname{Tr}\log\frac{\Delta_{\text{ref}}}{\mu^2}
+\Gamma_{\text{ct}}^{(1)}[\phi_s]
-\Gamma_{\text{ct}}^{(1)}[\phi_{\text{ref}}],
$$

where $\mu$ is the renormalization scale and $\Gamma_{\text{ct}}^{(1)}$ contains the one-loop counterterms in the same scheme used to define the couplings and masses.

The one-loop saddle factor is then

$$
\mathcal K_s
=
\mathcal J_{\text{zm}}\,
\exp\left[-\Gamma_{\text{ren}}^{(1)}[\phi_s;\phi_{\text{ref}}]/\hbar\right],
$$

up to conventional normalization factors, possible negative-mode factors, and higher-loop corrections.

## Determinant ratios and reference backgrounds

The determinant of a fluctuation operator by itself depends on the normalization of the functional measure. The ratio

$$
\frac{\det \Delta_s}{\det\Delta_{\text{ref}}}
$$

has a clearer meaning: it compares the spectrum of fluctuations near the saddle to the spectrum in a reference background.

For an instanton in quantum mechanics, the reference is often the harmonic oscillator around one vacuum. For a soliton mass, the reference is the perturbative vacuum in the same spatial volume. For a bounce rate, the reference is the false-vacuum background. For a gauge instanton, the reference is the vacuum gauge field plus the same gauge-fixing convention.

This comparison does not automatically remove all divergences. It removes many extensive or measure-dependent constants, but local ultraviolet divergences remain. Those are exactly the divergences canceled by counterterms. The final answer is finite only after the determinant ratio and counterterm contribution are combined.

A good practical expression is therefore not

$$
\det{}'\Delta_s,
$$

but

$$
\left[
\frac{\det\Delta_{\text{ref}}}{\det{}'\Delta_s}
\right]_{\text{ren}}
$$

together with the zero-mode measure and any special treatment of unstable directions.

## Spectral method and phase shifts

For static solitons, one-loop corrections are often computed from fluctuation frequencies. Suppose the fluctuation operator separates as

$$
\Delta_s=-\partial_t^2+\mathcal H_s,
$$

where $\mathcal H_s$ is a spatial Schrödinger-type operator. If

$$
\mathcal H_s u_n=\omega_n^2u_n,
$$

then the formal zero-point correction is

$$
\Delta M^{(1)}
=
\frac{\hbar}{2}\sum_n^{\text{saddle}}\omega_n
-\frac{\hbar}{2}\sum_n^{\text{vacuum}}\omega_n
+\Delta M_{\text{ct}}.
$$

When the spectrum contains continuum modes, one puts the system in a large box. In one spatial dimension, the quantization condition often has the form

$$
kL+\delta(k)=2\pi n,
$$

where $\delta(k)$ is a scattering phase shift caused by the soliton background. Differentiating gives the density-of-states shift

$$
\Delta\rho(k)
=
\rho_s(k)-\rho_0(k)
=
\frac{1}{2\pi}\frac{d\delta(k)}{dk}
$$

for a single channel on the full line with this convention. With multiple parity channels or partial waves, one sums the corresponding phase shifts.

The one-loop mass shift can then be written schematically as

$$
\Delta M^{(1)}
=
\frac{\hbar}{2}\sum_b\omega_b
+\frac{\hbar}{2}\int dk\,\Delta\rho(k)\,\omega(k)
+\Delta M_{\text{ct}},
$$

where the sum is over bound fluctuation modes, excluding zero modes. The integral still needs a regulator and counterterms. The phase-shift form is powerful because it expresses the continuum difference directly, rather than subtracting two huge boxes of nearly identical modes one by one.

## Heat-kernel and zeta-function method

For elliptic Euclidean operators, a compact way to define determinants is through the heat kernel. Let the positive nonzero eigenvalues of $\Delta$ be $\lambda_n$. Formally,

$$
\operatorname{Tr}e^{-t\Delta}
=
\sum_n e^{-t\lambda_n}.
$$

The zeta function is

$$
\zeta_\Delta(s)
=
\sum_n \lambda_n^{-s},
$$

or equivalently

$$
\zeta_\Delta(s)
=
\frac{1}{\Gamma(s)}
\int_0^\infty dt\,t^{s-1}\operatorname{Tr}e^{-t\Delta}
$$

after analytic continuation. The zeta-regularized determinant is

$$
\log\det\Delta
=
-\zeta_\Delta'(0).
$$

The ultraviolet behavior comes from small $t$. For a local elliptic operator in $d$ Euclidean dimensions,

$$
\operatorname{Tr}e^{-t\Delta}
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{k\ge 0} a_k(\Delta)t^k
\qquad
(t\to 0^+).
$$

The coefficients $a_k$ are local integrals built from the background fields, masses, curvature, and boundary data. This is the key reason counterterms are local: the UV divergences of the determinant are controlled by local heat-kernel coefficients.

The heat-kernel method is especially useful when the background is smooth and the operator is geometrically natural. It also makes anomalies, scale dependence, and curvature dependence visible.

## Gelfand–Yaglom and partial waves

In one-dimensional determinant problems, the Gelfand–Yaglom method replaces an eigenvalue product by an ordinary differential equation with specified boundary conditions. The slogan is

$$
\frac{\det L_1}{\det L_0}
=
\frac{\text{solution data for }L_1}{\text{solution data for }L_0},
$$

with the exact form depending on the boundary conditions and on whether zero modes are present.

This method is particularly useful in quantum mechanics, radial fluctuation problems, and backgrounds reducible to one-dimensional channels.

In higher-dimensional radially symmetric backgrounds, one often decomposes into partial waves,

$$
\Delta_s
=
\bigoplus_{\ell}\Delta_{\ell}.
$$

Then

$$
\log\det\Delta_s
=
\sum_{\ell} d_\ell\log\det\Delta_{\ell},
$$

where $d_\ell$ is the degeneracy. The individual one-dimensional determinants may be accessible by Gelfand–Yaglom, but the sum over $\ell$ is ultraviolet divergent. A correct calculation subtracts the large-$\ell$ asymptotics and restores the corresponding local counterterms. The partial-wave method is therefore not a loophole around renormalization; it is a way to organize it.

## Gauge theories

For gauge fields, the fluctuation operator has zero directions along gauge orbits. One must choose a gauge, usually a background-field gauge, and include the Faddeev–Popov determinant.

For a Yang–Mills background $A_s$, a schematic one-loop factor has the form

$$
\mathcal K_s
\sim
\left(\det{}'\Delta_{\text{gauge}}\right)^{-1/2}
\det \Delta_{\text{gh}}
\times
\mathcal J_{\text{zm}},
$$

where $\Delta_{\text{gh}}$ is the ghost operator and $\mathcal J_{\text{zm}}$ is the collective-coordinate measure for physical zero modes. The prime on the gauge determinant removes zero modes that correspond to genuine moduli or residual symmetries treated separately.

Gauge-fixing dependence cancels in gauge-invariant quantities when all pieces are treated consistently. But intermediate determinants can look gauge dependent, and a sloppy zero-mode quotient can produce wrong powers of couplings, volumes, or instanton sizes.

Gauge instantons illustrate the point. The one-loop determinant does not merely produce a number; it contributes to a measure on instanton moduli space, with factors depending on the instanton position, size, gauge orientation, renormalization scale, and running coupling. The compact formula is beautiful only after much bookkeeping.

## Fermions and phases

Grassmann Gaussian integrals produce determinants in the numerator rather than the denominator. If the quadratic fermion action is

$$
S_F=\int d^dx\,\bar\psi\,\mathcal D_s\psi,
$$

then

$$
\int D\bar\psi D\psi\,e^{-S_F}
=
\det\mathcal D_s.
$$

For a Dirac fermion in a real positive setup, one often rewrites the magnitude using

$$
\log|\det\mathcal D_s|
=
\frac12\operatorname{Tr}\log(\mathcal D_s^\dagger\mathcal D_s).
$$

But this can hide phases. In chiral theories, topological backgrounds, and theories with anomalies, the phase of the fermion determinant can carry physical information. It may encode anomaly inflow, theta-angle dependence, parity anomalies, or sign problems.

Fermion zero modes require special handling. If $\mathcal D_s$ has zero modes, then

$$
\det\mathcal D_s=0
$$

unless the path integral contains insertions or mass terms that soak up the corresponding Grassmann integrals. This is not a small correction. It is a selection rule.

## Negative modes and decay rates

If $\Delta_s$ has one negative mode, the saddle is not a stable local minimum of the Euclidean action. The most important example is a false-vacuum bounce. In that case the determinant is often written as an absolute value,

$$
|\det{}'\Delta_b|^{-1/2},
$$

while the integration contour through the negative direction supplies an imaginary part. That imaginary part is what becomes the decay rate.

Thus the same determinant machinery appears in two physically different settings:

| Background | Spectrum | Interpretation |
|---|---:|---|
| stable soliton | zero modes plus positive modes | quantum particle states and mass shifts |
| instanton | zero modes plus positive modes | tunneling amplitude or topological-sector weight |
| bounce | one negative mode, zero modes, positive modes | imaginary part of false-vacuum energy and decay rate |
| sphaleron-like saddle | unstable direction in real time or finite temperature | transition rate over or near a barrier |

The determinant alone does not tell you which case you are in. The boundary conditions and fluctuation spectrum do.

## Practical checklist

A clean one-loop determinant calculation should answer the following questions.

| Question | Why it matters |
|---|---|
| What is the saddle $\phi_s$? | The Hessian and boundary conditions depend on it. |
| What is the reference background? | Determinants are usually meaningful as ratios. |
| What is the fluctuation operator? | Field-space metric, gauge choice, and constraints enter here. |
| Which modes are zero modes? | They must be removed and replaced by collective coordinates. |
| Are there negative modes? | They change the interpretation from energy shift to instability. |
| Are there gauge redundancies? | Gauge modes are not physical moduli. Ghosts and gauge fixing are required. |
| Are there fermion zero modes or phases? | They produce selection rules and possible anomalies. |
| What regulator is being used? | Infinite products need definition. |
| What counterterms are included? | The determinant ratio alone is generally divergent. |
| What renormalization scheme defines the answer? | The finite part is scheme-dependent unless expressed in physical parameters. |

This checklist is not bureaucracy. It is how one avoids turning a semiclassical calculation into numerology wearing a lab coat.

## Common pitfalls

**Computing an absolute determinant and calling it physical.** In QFT, useful determinant factors are usually ratios plus counterterms.

**Dropping zero modes without adding the Jacobian.** Removing a zero eigenvalue from $\det{}'\Delta_s$ is only half the job. The missing integration is the collective-coordinate measure.

**Treating a negative mode as an ordinary absolute value.** For bounces, the negative mode supplies an imaginary part. Taking an absolute determinant is only part of the contour prescription.

**Forgetting ghosts in gauge theory.** Gauge-field determinants without the ghost determinant and gauge-mode quotient are not physical.

**Using different regulators for the saddle and reference.** The cancellation of divergences depends on comparing like with like.

**Mistaking zeta regularization for renormalization.** Zeta methods define products elegantly, but the answer still corresponds to a choice of scheme and local counterterms.

**Ignoring continuum density shifts.** A soliton changes the density of scattering states. Bound states alone do not give the one-loop mass shift.

**Hiding fermion phases.** Squaring a Dirac operator may compute a magnitude while losing physically important phase information.

## Relations to other pages

This page refines the determinant factor introduced in [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) and [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/). It uses the zero-mode logic of [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) and the collective-coordinate measure of [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/).

For stable solitons, combine this page with [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/). For metastable vacua, combine it with [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/). For instantons, later pages on instanton measures, fermion zero modes, and theta vacua will use this machinery again with gauge and topological structure added.

## Research status

**Established.** One-loop determinant ratios are standard in instanton calculus, bounce calculations, soliton mass shifts, semiclassical quantization, finite-temperature saddle estimates, and effective actions in background fields.

**Scheme-dependent.** The finite part of a one-loop determinant is not meaningful until the renormalization scheme, reference background, and physical input parameters are specified.

**Active.** Determinants in chiral gauge theories, complex saddles, real-time contours, finite-density backgrounds, noncompact moduli spaces, and strongly coupled systems remain subtle. The right answer may depend on global phases, anomaly inflow, contour choices, or nonperturbative definitions beyond the elementary Gaussian expansion.

## Exercises

### Exercise 1: Determinant from a finite Gaussian

Let $A$ be a positive $N\times N$ matrix. Show that

$$
\int \frac{d^N x}{(2\pi)^{N/2}}
\exp\left(-\frac12 x^T A x\right)
=
(\det A)^{-1/2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $A$ is real symmetric and positive, it can be diagonalized by an orthogonal matrix,

$$
A=O^T\operatorname{diag}(\lambda_1,\ldots,\lambda_N)O,
\qquad
\lambda_i>0.
$$

The change of variables $y=Ox$ has unit Jacobian. Therefore

$$
\int \frac{d^N x}{(2\pi)^{N/2}}
e^{-x^TAx/2}
=
\prod_{i=1}^N
\int_{-\infty}^{\infty}
\frac{dy_i}{\sqrt{2\pi}}
e^{-\lambda_i y_i^2/2}.
$$

Each integral is $\lambda_i^{-1/2}$, so the product is

$$
\prod_{i=1}^N\lambda_i^{-1/2}
=
(\det A)^{-1/2}.
$$

</details>

### Exercise 2: Density of states from a phase shift

Suppose modes in a large one-dimensional box obey

$$
kL+\delta(k)=2\pi n.
$$

Derive the shift in the density of states.

<details>
<summary><strong>Solution</strong></summary>

Treat $n$ as a smooth function of $k$:

$$
n(k)=\frac{1}{2\pi}\left(kL+\delta(k)\right).
$$

The density of states is

$$
\rho(k)=\frac{dn}{dk}
=
\frac{L}{2\pi}
+\frac{1}{2\pi}\frac{d\delta(k)}{dk}.
$$

The free density is $\rho_0(k)=L/(2\pi)$, so

$$
\Delta\rho(k)
=
\rho(k)-\rho_0(k)
=
\frac{1}{2\pi}\frac{d\delta(k)}{dk}.
$$

With multiple channels, the total shift is the sum over channel phase shifts.

</details>

### Exercise 3: Scaling a determinant

Let $\Delta$ have nonzero eigenvalues $\lambda_n$. Formally define

$$
\zeta_\Delta(s)=\sum_n\lambda_n^{-s}.
$$

Show that zeta regularization gives

$$
\log\det\left(\frac{\Delta}{\mu^2}\right)
=
-\zeta_\Delta'(0)-\zeta_\Delta(0)\log\mu^2.
$$

<details>
<summary><strong>Solution</strong></summary>

The zeta function of $\Delta/\mu^2$ is

$$
\zeta_{\Delta/\mu^2}(s)
=
\sum_n\left(\frac{\lambda_n}{\mu^2}\right)^{-s}
=
\mu^{2s}\zeta_\Delta(s).
$$

The zeta-regularized determinant is

$$
\log\det\left(\frac{\Delta}{\mu^2}\right)
=
-\left.\frac{d}{ds}\zeta_{\Delta/\mu^2}(s)\right|_{s=0}.
$$

Differentiating,

$$
\frac{d}{ds}\left(\mu^{2s}\zeta_\Delta(s)\right)
=
\mu^{2s}\left(2\log\mu\,\zeta_\Delta(s)+\zeta_\Delta'(s)\right).
$$

At $s=0$ this gives

$$
\log\det\left(\frac{\Delta}{\mu^2}\right)
=
-\zeta_\Delta'(0)-2\log\mu\,\zeta_\Delta(0).
$$

Since $2\log\mu=\log\mu^2$, the result is

$$
\log\det\left(\frac{\Delta}{\mu^2}\right)
=
-\zeta_\Delta'(0)-\zeta_\Delta(0)\log\mu^2.
$$

</details>

### Exercise 4: Why the counterterm cannot be skipped

Suppose a regulated determinant ratio has the divergent form

$$
\frac12\operatorname{Tr}\log\Delta_s
-\frac12\operatorname{Tr}\log\Delta_0
=
A\log\Lambda+B+O(\Lambda^{-1}),
$$

where $A$ is a local functional of the saddle background. Explain why a local counterterm can cancel the divergence and why the finite number $B$ alone is not a scheme-independent observable.

<details>
<summary><strong>Solution</strong></summary>

The divergent coefficient $A$ is local in the background. Therefore it has the same form as a local term already allowed in the action, such as a mass, coupling, wavefunction, boundary, or curvature counterterm. A one-loop counterterm contribution can contain

$$
\Gamma_{\text{ct}}^{(1)}=-A\log\Lambda+\text{finite local part},
$$

which cancels the regulator dependence.

The remaining finite answer is

$$
B+\text{finite local part}.
$$

Changing the renormalization scheme changes the finite local part. Therefore $B$ by itself is not an observable. A physical prediction is obtained only after expressing the result in terms of renormalized or measured parameters in a specified scheme.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on functional methods, instantons, and false-vacuum decay.
- C. Callan and S. Coleman, classic work on false-vacuum decay and determinant prefactors.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional determinants, saddle expansions, and renormalization.
- M. Mariño, *Instantons and Large N*, especially the discussion of functional determinants, Gelfand–Yaglom methods, large-order behavior, and instanton calculus.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for solitons, instantons, fermion zero modes, and nonperturbative examples.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for background-field methods, one-loop effective actions, and solitons.
- Standard heat-kernel references for zeta determinants, Seeley–DeWitt coefficients, and spectral asymptotics.

## Version history

- **2026-06-26:** Initial polished draft.
