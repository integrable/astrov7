---
title: "Dimensional Regularization"
description: "A derivation-focused guide to analytic continuation in spacetime dimension, epsilon poles, the renormalization scale, scaleless integrals, and minimal subtraction."
sidebar:
  label: "Dimensional Regularization"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§14–29; Schwartz app. B and chs. 18–23; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Coleman, renormalization lectures; Zinn-Justin, dimensional regularization and RG chapters."
topics:
  - dimensional regularization
  - epsilon expansion
  - minimal subtraction
  - MS scheme
  - MSbar scheme
  - scaleless integrals
canonicalTopics:
  - dimensional-regularization
  - epsilon-pole
  - minimal-subtraction
  - msbar-scheme
  - scaleless-integral
researchStatus:
  established:
    - "Dimensional regularization is the standard analytic regulator for many continuum perturbative calculations because it preserves Lorentz covariance, momentum-shift invariance, and usually gauge symmetry."
  active:
    - "Subtleties remain important for chiral gauge theories, gamma-five prescriptions, evanescent operators, dimensional reduction, infrared factorization, and multi-loop scheme conversions."
---

## Summary

**Dimensional regularization** regulates divergent integrals by treating the number of spacetime dimensions as a complex parameter. Near four dimensions we write

$$
d=4-2\epsilon.
$$

A logarithmically divergent integral in four dimensions becomes a meromorphic function of $\epsilon$, with a pole at $\epsilon=0$. The canonical Euclidean formula is

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^\alpha}
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
\Delta^{d/2-\alpha}.
$$

For the logarithmic case $\alpha=2$,

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\bar\epsilon}
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right],
$$

where

$$
\frac{1}{\bar\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

Dimensional regularization is not a physical cutoff. It does not say that spacetime is secretly $4-2\epsilon$ dimensional. It is an analytic regulator that keeps symmetries and algebraic manipulations under unusually good control.

:::note[What dimensional regularization is best at]
Dimensional regularization turns UV logarithms into $1/\epsilon$ poles, keeps momentum shifts legal, and works beautifully with minimal subtraction. Its main conceptual cost is that power-law cutoff sensitivity is not displayed as powers of a cutoff.
:::

## Prerequisites

You should know [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/) and the distinction between a cutoff $\Lambda$, a renormalization scale $\mu$, and a physical scale $Q$. You should also know the basic Gaussian integral and the Euclidean form of scalar propagators.

This page uses Euclidean loop integrals after Wick rotation. Lorentzian factors of $i$ and $i\epsilon$ are handled by the scattering conventions in the Perturbative QFT and Scattering volume.

## Core idea

A divergent integral may converge in a different range of dimensions. Dimensional regularization evaluates the integral where it converges, expresses the answer as an analytic function of $d$, and then continues the result back near the desired dimension.

The method is powerful because it does not carve out a boundary in momentum space. Therefore it preserves translation invariance in loop momentum:

$$
\int d^d k\,f(k)=\int d^d k\,f(k+a),
$$

provided the integral is understood dimensionally. This is one reason tensor reduction, Ward identities, and gauge-theory calculations are usually cleaner in dimensional regularization than with a naive hard cutoff.

The slogan is

$$
\text{dimensional regularization replaces divergent cutoff dependence by poles and logarithms.}
$$

The word "replaces" is doing work. A $1/\epsilon$ pole is not literally a large momentum cutoff. It is the analytic-regulator signal that a local counterterm is required.

## Setup and conventions

Near four dimensions we use

$$
d=4-2\epsilon.
$$

The factor $\mu^{2\epsilon}$ is inserted so that four-dimensional couplings can remain dimensionless. For example, in $\phi^4$ theory one writes

$$
\mathcal L
\supset
-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4
$$

in Lorentzian notation, or the corresponding positive Euclidean interaction in $S_E$. For gauge and Yukawa couplings, the corresponding factor is usually $\mu^\epsilon$.

We define

$$
\frac{1}{\bar\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

MS subtracts pole terms in $1/\epsilon$. The $\overline{\mathrm{MS}}$ scheme subtracts pole terms in the common combination $1/\bar\epsilon$. Equivalently, one may absorb the constants into a modified scale

$$
\bar\mu^2=4\pi e^{-\gamma_E}\mu^2.
$$

Different books distribute the factors of $4\pi$, $e^{-\gamma_E}$, and $\mu$ differently. Before comparing formulas, identify which scale is called $\mu$.

## The Schwinger-parameter derivation

Consider the Euclidean integral

$$
J_\alpha(\Delta)
\equiv
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^\alpha},
\qquad
\Delta>0.
$$

Use the Schwinger representation

$$
\frac{1}{(k_E^2+\Delta)^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s(k_E^2+\Delta)}.
$$

The $d$-dimensional Gaussian integral is

$$
\int\frac{d^d k_E}{(2\pi)^d}e^{-s k_E^2}
=
\frac{1}{(4\pi s)^{d/2}}.
$$

Therefore

$$
J_\alpha(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1-d/2}e^{-s\Delta}.
$$

The remaining integral is a gamma-function integral:

$$
\int_0^\infty ds\,s^{\alpha-d/2-1}e^{-s\Delta}
=
\Gamma(\alpha-d/2)\Delta^{d/2-\alpha}.
$$

Thus

$$
J_\alpha(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
\Delta^{d/2-\alpha}.
$$

This formula is the workhorse. The ultraviolet singularity is now the pole of $\Gamma(\alpha-d/2)$.

## The logarithmic integral

Set $\alpha=2$ and $d=4-2\epsilon$. Then

$$
J_2(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}
\Gamma(\epsilon)\Delta^{-\epsilon}.
$$

Use

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon),
$$

and

$$
\mu^{2\epsilon}(4\pi)^\epsilon\Delta^{-\epsilon}
=1+
\epsilon\left(\log(4\pi)+\log\frac{\mu^2}{\Delta}\right)
+O(\epsilon^2).
$$

Therefore

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\epsilon}-\gamma_E+\log(4\pi)
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

Using $1/\bar\epsilon$, this is

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\bar\epsilon}
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

This is the direct analogue of the logarithmic cutoff integral

$$
\frac{1}{16\pi^2}\log\frac{\Lambda^2}{\Delta}
+\text{scheme-dependent constant}.
$$

The dictionary is not $1/\epsilon=\log\Lambda^2$. The correct statement is subtler: both represent the local UV divergence that must be subtracted, and both leave finite logarithms of physical scales after renormalization.

## Minimal subtraction and modified minimal subtraction

In a subtraction scheme one splits a bare parameter into a renormalized parameter plus counterterms. For a dimensionless coupling in four dimensions, the dimensional continuation has the schematic form

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g(\mu),
$$

where $\kappa$ depends on the engineering dimension of the interaction in $d=4-2\epsilon$. For example, $\kappa=2$ for a scalar quartic coupling and $\kappa=1$ for many gauge or Yukawa couplings.

In MS, the counterterm $Z_g$ contains only poles in $1/\epsilon$:

$$
Z_g(g,\epsilon)=1+\frac{a_1(g)}{\epsilon}+\frac{a_2(g)}{\epsilon^2}+\cdots.
$$

In $\overline{\mathrm{MS}}$, one subtracts the corresponding poles in $1/\bar\epsilon$, or equivalently uses the modified scale $\bar\mu$.

The great advantage is bookkeeping. The beta function can be read from the pole structure because the bare parameter $g_0$ is independent of $\mu$:

$$
0=\mu\frac{d g_0}{d\mu}.
$$

The resulting running of $g(\mu)$ is not a new physical force. It is the compensation needed to keep predictions independent of the arbitrary subtraction scale.

## Why scaleless integrals vanish

Dimensional regularization sets scaleless integrals to zero:

$$
\int\frac{d^d k}{(2\pi)^d}\frac{1}{(k^2)^\alpha}=0.
$$

The quick scaling argument is that the integral has no dimensionful scale. If it were nonzero, it would have to be proportional to a scale with dimension $d-2\alpha$, but no such scale exists.

This rule is useful but dangerous. A scaleless integral may contain both UV and IR divergences. Dimensional regularization can make these cancel in the combined expression. For example,

$$
\int\frac{d^d k}{k^4}
$$

is UV divergent at large $k$ and IR divergent at small $k$ in four dimensions. Setting it to zero does not mean there were no singularities; it means the dimensionally regulated scaleless integral contains no scale with which to report them separately.

When UV and IR physics both matter, one must introduce separate regulators, keep external momenta off shell, add masses, or use factorization methods appropriate to the observable.

## Tensor integrals and momentum shifts

Dimensional regularization respects rotational symmetry in $d$ Euclidean dimensions. Therefore

$$
\int d^d k_E\,k_{E\mu}k_{E\nu}f(k_E^2)
=
\frac{\delta_{\mu\nu}}{d}
\int d^d k_E\,k_E^2 f(k_E^2).
$$

Similarly,

$$
\int d^d k_E\,k_{E\mu}k_{E\nu}k_{E\rho}k_{E\sigma}f(k_E^2)
=
\frac{\delta_{\mu\nu}\delta_{\rho\sigma}
+\delta_{\mu\rho}\delta_{\nu\sigma}
+\delta_{\mu\sigma}\delta_{\nu\rho}}{d(d+2)}
\int d^d k_E\,(k_E^2)^2 f(k_E^2).
$$

These identities are one reason loop calculations simplify in dimensional regularization. Momentum shifts are also allowed in dimensionally regulated integrals. This avoids the surface-term ambiguities that appear with hard cutoffs.

In gauge theory this matters enormously. Ward identities often rely on shifting loop momenta and reducing tensor integrals in a symmetry-preserving way.

## Comparison with cutoff regularization

Cutoff regularization and dimensional regularization answer the same local question in different languages.

| Issue | Cutoff regularization | Dimensional regularization |
|---|---|---|
| Regulator | High-momentum scale $\Lambda$ | Dimension $d=4-2\epsilon$ |
| Log divergence | $\log\Lambda^2$ | $1/\epsilon$ pole |
| Power divergence | Explicit powers such as $\Lambda^2$ | Usually absent as powers of a cutoff |
| Momentum shifts | Can produce cutoff-surface terms | Preserved by analytic continuation |
| Gauge symmetry | Naive cutoffs can break it | Usually preserved, with known caveats |
| Best use | Wilsonian intuition, EFT sensitivity, lattice previews | Continuum perturbation theory and MS-style RG |

Neither regulator is "more physical" in all contexts. A cutoff is more intuitive and more Wilsonian. Dimensional regularization is cleaner for continuum perturbative calculations. A good physicist should understand both and know what each is hiding.

## Power divergences and heavy thresholds

Because dimensional regularization does not display power divergences as powers of $\Lambda$, it can tempt readers into saying that quadratic sensitivity is fake. That is too fast.

Suppose a light scalar couples to a heavy field of mass $M$. A one-loop threshold correction can produce a contribution to the light scalar mass of the form

$$
\delta m_{\text{light}}^2\sim \frac{g^2}{16\pi^2}M^2,
$$

up to scheme-dependent constants and logarithms. This is a physical heavy-mass sensitivity in a matching calculation. Dimensional regularization does not eliminate it. It simply does not report it as a bare $\Lambda^2$ divergence.

Thus dimensional regularization is excellent for computing logarithmic running in mass-independent schemes, but decoupling of heavy particles is not automatic in MS or $\overline{\mathrm{MS}}$. One often integrates out heavy fields at $\mu\sim M$, matches onto an EFT, and then runs the EFT coefficients below $M$.

## Gamma-five, evanescent operators, and other caveats

Some objects are intrinsically tied to integer dimension. Examples include

$$
\gamma^5,
\qquad
\epsilon_{\mu\nu\rho\sigma},
\qquad
\text{four-dimensional helicity states},
\qquad
\text{dimension-specific Fierz identities}.
$$

In theories where these objects matter, dimensional regularization requires additional prescriptions. Chiral gauge theories and anomalies are the classic warning signs.

Another subtlety is the appearance of **evanescent operators**: operators that vanish algebraically in the physical integer dimension but are nonzero in $d=4-2\epsilon$. In multi-loop calculations and operator mixing problems, evanescent operators can affect finite physical results after multiplying $1/\epsilon$ poles.

Supersymmetric theories have their own issue: ordinary dimensional regularization changes the number of gauge-field components without changing the number of fermion components in a supersymmetric way. Dimensional reduction is often used instead, but it has its own consistency requirements.

These caveats do not make dimensional regularization bad. They make it a precision instrument. Precision instruments come with manuals.

## Worked example: a one-loop bubble denominator

A common scalar bubble integral after Feynman parametrization has the form

$$
B(p^2)
=\mu^{2\epsilon}\int_0^1 dx
\int\frac{d^d \ell_E}{(2\pi)^d}
\frac{1}{(\ell_E^2+\Delta(x,p^2))^2},
$$

where

$$
\Delta(x,p^2)=m^2+x(1-x)p_E^2
$$

in Euclidean kinematics for equal masses. Using the logarithmic master integral,

$$
B(p^2)
=
\frac{1}{16\pi^2}\int_0^1 dx
\left[
\frac{1}{\bar\epsilon}
-\log\frac{m^2+x(1-x)p_E^2}{\mu^2}
+O(\epsilon)
\right].
$$

The pole term is independent of $p^2$ in this simple example, so the UV divergence multiplies a local operator with no derivatives in the corresponding four-point vertex. The finite logarithm contains the physical momentum dependence. In Lorentzian kinematics, analytic continuation of the logarithm produces thresholds and branch cuts when the external momentum can put intermediate particles on shell.

This example captures the pattern of many one-loop calculations:

$$
\text{UV pole} + \text{finite logarithms} + \text{analytic finite terms}.
$$

The UV pole is removed by a local counterterm. The finite logarithms encode scale dependence and physical analytic structure.

## Common pitfalls

**Thinking $d=4-2\epsilon$ is a physical spacetime.** It is an analytic regulator, not a claim about microscopic geometry.

**Equating $1/\epsilon$ with $\log\Lambda^2$ too literally.** Both represent logarithmic UV sensitivity, but they live in different schemes and differ by finite conventions.

**Forgetting the scale $\mu$.** In dimensional regularization, $\mu$ is required by dimensional analysis. Running couplings appear because bare quantities do not depend on this arbitrary scale.

**Using scaleless integrals without checking IR divergences.** A scaleless integral vanishing in dimensional regularization may hide a cancellation between UV and IR poles.

**Believing dimensional regularization proves power sensitivity is absent.** Heavy threshold corrections and relevant-operator sensitivity remain physical questions.

**Comparing MS and $\overline{\mathrm{MS}}$ formulas without checking scale conventions.** Constants $\gamma_E$ and $\log 4\pi$ move between the definition of the scale and the counterterm.

**Ignoring dimension-specific algebra.** Objects such as $\gamma^5$, Levi-Civita tensors, helicity projectors, and Fierz identities need prescriptions away from integer dimension.

## Relations to other pages

This page follows [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/). Together they teach the two most important regulator languages: a direct short-distance cutoff and analytic continuation in dimension.

The next regulator page, Pauli–Villars Regularization, will introduce a mass-based subtraction regulator. The Counterterms page will explain how the poles and cutoff dependence found here are absorbed into local terms. Minimal Subtraction and $\overline{\mathrm{MS}}$ return in Renormalized Perturbation Theory, where they become full renormalization schemes rather than only regulator vocabulary.

The beta functions, anomalous dimensions, running couplings, and Callan–Symanzik equations generated by dimensional poles are developed in Renormalization Group Equations. Heavy-threshold matching and decoupling are developed in Effective Field Theory and Matching, Running, and Decoupling.

## Research status

Dimensional regularization and MS-style subtraction are standard technology in perturbative QFT. Their mathematical use as analytic regularization of Feynman integrals is mature, and their compatibility with gauge symmetry is one of the reasons they dominate high-order calculations.

Active subtleties remain in precision contexts: chiral gauge theories, anomaly-sensitive computations, evanescent operators in EFT bases, dimensional reduction in supersymmetry, infrared subtraction in gauge theories with massless particles, multi-loop scheme conversions, and automated amplitude pipelines. In such applications, the regulator is part of the definition of the calculation and must be documented as carefully as the Lagrangian.

## Exercises

### Exercise 1: Derive the master integral

Starting from

$$
J_\alpha(\Delta)
=\mu^{2\epsilon}\int\frac{d^d k_E}{(2\pi)^d}\frac{1}{(k_E^2+\Delta)^\alpha},
$$

use the Schwinger representation to derive

$$
J_\alpha(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
\Delta^{d/2-\alpha}.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\frac{1}{(k_E^2+\Delta)^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s(k_E^2+\Delta)}.
$$

Then

$$
J_\alpha
=
\frac{\mu^{2\epsilon}}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s\Delta}
\int\frac{d^d k_E}{(2\pi)^d}e^{-s k_E^2}.
$$

The Gaussian integral is

$$
\int\frac{d^d k_E}{(2\pi)^d}e^{-s k_E^2}
=\frac{1}{(4\pi s)^{d/2}}.
$$

Therefore

$$
J_\alpha
=\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-d/2-1}e^{-s\Delta}.
$$

The last integral equals

$$
\Gamma(\alpha-d/2)\Delta^{d/2-\alpha},
$$

which gives the desired expression.

</details>

### Exercise 2: Expand the logarithmic integral

For $d=4-2\epsilon$, show that

$$
\mu^{2\epsilon}\int\frac{d^d k_E}{(2\pi)^d}\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}\left[\frac{1}{\bar\epsilon}-\log\frac{\Delta}{\mu^2}+O(\epsilon)\right].
$$

<details><summary><strong>Solution</strong></summary>

From the master integral with $\alpha=2$,

$$
J_2(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}\Gamma(\epsilon)\Delta^{-\epsilon}.
$$

Use

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon),
$$

and

$$
\mu^{2\epsilon}(4\pi)^\epsilon\Delta^{-\epsilon}
=1+\epsilon\left(\log(4\pi)+\log\frac{\mu^2}{\Delta}\right)+O(\epsilon^2).
$$

Multiplying gives

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\epsilon}-\gamma_E+\log(4\pi)-\log\frac{\Delta}{\mu^2}+O(\epsilon)
\right].
$$

Using

$$
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log(4\pi)
$$

gives the result.

</details>

### Exercise 3: Why a scaleless integral vanishes

Use dimensional analysis to explain why

$$
\int\frac{d^d k}{(2\pi)^d}\frac{1}{(k^2)^\alpha}=0
$$

in dimensional regularization. What important caveat should accompany this statement?

<details><summary><strong>Solution</strong></summary>

The integral has mass dimension

$$
d-2\alpha.
$$

If it were nonzero, the answer would have to be proportional to some mass scale raised to that power. But the integral contains no mass, external momentum, cutoff, or other scale. Dimensional regularization therefore assigns the scaleless integral the value zero.

The caveat is that the integral may contain both UV and IR divergences. Dimensional regularization can make the UV and IR poles cancel in the scaleless expression. Therefore "zero" does not mean "no singularities." It means that with no scale present, the dimensionally regulated integral has no nonzero value to report. In problems where UV and IR singularities must be separated, one needs an additional scale or regulator.

</details>

### Exercise 4: The dimension of the scalar quartic coupling

In $d=4-2\epsilon$, show that the coefficient of $\phi^4$ has mass dimension $2\epsilon$ if the scalar has canonical dimension $(d-2)/2$.

<details><summary><strong>Solution</strong></summary>

The scalar dimension is

$$
[\phi]=\frac{d-2}{2}=1-\epsilon.
$$

Therefore

$$
[\phi^4]=4(1-\epsilon)=4-4\epsilon.
$$

The Lagrangian density has dimension

$$
[\mathcal L]=d=4-2\epsilon.
$$

Thus the coefficient of $\phi^4$ has dimension

$$
(4-2\epsilon)-(4-4\epsilon)=2\epsilon.
$$

Writing the interaction as $\mu^{2\epsilon}\lambda\phi^4/4!$ keeps $\lambda$ dimensionless.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the sections on loop corrections, renormalizability, renormalization schemes, RG, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially appendix B and chapters 18–23.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Renormalization and Symmetry."
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on dimensional regularization, renormalization, and the RG.
- John Collins, *Renormalization*, for a systematic treatment of dimensional regularization, subtraction, and all-orders renormalization.

## Version history

- 2026-06-17: First polished draft. Added dimensional-continuation setup, Schwinger-parameter derivation, logarithmic master integral, MS and $\overline{\mathrm{MS}}$ conventions, scaleless integral caveats, and comparison with cutoff regularization.
