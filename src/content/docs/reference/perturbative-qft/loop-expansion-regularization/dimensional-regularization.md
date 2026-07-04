---
title: "Dimensional Regularization"
description: "A derivation-focused guide to analytic continuation in spacetime dimension, epsilon poles, the renormalization scale, scaleless integrals, and minimal subtraction."
sidebar:
  label: "Dimensional Regularization"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20 and 27; Schwartz 2014, appendix B and chs. 15–20; Weinberg 1995, Vol. I, ch. 12; Coleman 2019, chs. 25 and 32; Zinn-Justin 2021, ch. 10"
topics:
  - dimensional regularization
  - epsilon expansion
  - minimal subtraction
  - loop integrals
  - renormalization scale
canonicalTopics:
  - dimensional-regularization
  - epsilon-pole
  - minimal-subtraction
  - msbar-scheme
  - scaleless-integral
researchStatus:
  established:
    - "Dimensional regularization is the standard analytic regulator for perturbative loop calculations because it preserves translational and Lorentz covariance and is especially compatible with gauge symmetry."
  active:
    - "Subtleties remain important in chiral gauge theories, gamma-five prescriptions, evanescent operators, dimensional reduction, infrared factorization, and multi-loop scheme conversions."
---

## Summary

**Dimensional regularization** regulates loop integrals by analytically continuing the number of spacetime dimensions away from the physical value. Near four dimensions one writes

$$
{d=4-2\epsilon.}
$$

A logarithmically divergent four-dimensional integral becomes a meromorphic function of $\epsilon$ with a pole at $\epsilon=0$. The basic Euclidean master formula is

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^\alpha}
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
\Delta^{d/2-\alpha}.
$$

For the most common logarithmic case, $\alpha=2$ and $d=4-2\epsilon$,

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{\Delta}{\mu^2}
+O(\epsilon)
\right],
$$

where

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\ln 4\pi.
$$

Minimal subtraction removes the pole part; $\overline{\mathrm{MS}}$ removes $1/\overline\epsilon$. The arbitrary scale $\mu$ remains in renormalized parameters, and the renormalization group describes how those parameters change so that physical predictions do not depend on the arbitrary bookkeeping scale.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Dimensional regularization map from continuing d equals 4 minus 2 epsilon through the gamma-function master integral to epsilon poles, logarithms, subtraction, and renormalized scale dependence](/figures/perturbative-qft/dimensional-regularization-map.svg)

<figcaption>

Dimensional regularization replaces divergent integrals by analytic functions of $d$. Ultraviolet divergences appear as poles in $\epsilon$, while finite logarithms remember the ratio of physical scales to the arbitrary renormalization scale $\mu$. Minimal subtraction removes pole pieces; renormalization group equations track the remaining $\mu$ dependence.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/), [Cutoff Regularization](/perturbative-qft/loop-expansion-regularization/cutoff-regularization/), and [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/). For the Euclidean formulas, review [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/).

## Core idea

A divergent integral is often well defined in a range of dimensions different from the physical dimension. Dimensional regularization evaluates the integral where it converges, writes the answer as a function of $d$, and analytically continues back near the desired value.

The method is powerful because it keeps many symmetries manifest. It does not impose a hard boundary in momentum space, so it preserves momentum-shift invariance. It treats tensor integrals covariantly in $d$ dimensions. In gauge theories, this is a huge advantage: Ward and Slavnov–Taylor identities are far easier to preserve than with a naive hard cutoff.

The price is conceptual. Dimensional regularization hides power divergences that are obvious in cutoff regularization, and it requires care with objects that exist only in integer dimension, such as $\gamma^5$, Levi-Civita tensors, helicity states, and some Fierz identities.

The practical slogan is

$$
\text{dimensional regularization turns UV divergences into poles and scale dependence into logarithms.}
$$

## Setup and conventions

We use mostly-minus Lorentzian conventions for amplitudes, but the master integrals are written in Euclidean form after Wick rotation. Let

$$
d=4-2\epsilon.
$$

The loop measure is analytically continued to $d$ dimensions. To keep the action dimensionless and couplings conventionally normalized, one introduces a renormalization scale $\mu$. For example, a scalar quartic coupling has dimension $2\epsilon$ in $d=4-2\epsilon$, so one often writes

$$
\lambda_B=\mu^{2\epsilon}Z_\lambda\lambda(\mu)
$$

or uses the $\overline{\mathrm{MS}}$ scale $\overline\mu$ defined by

$$
\overline\mu^2=4\pi e^{-\gamma_E}\mu^2.
$$

The precise placement of $4\pi$ and $e^{-\gamma_E}$ is a convention. The important point is that $\mu$ is arbitrary. It is not a physical cutoff. It is a scale introduced so that dimensionally continued couplings can be compared at different energies.

For compactness, this page uses

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

Then $\overline{\mathrm{MS}}$ subtraction means subtracting the $1/\overline\epsilon$ pole part, not merely $1/\epsilon$.

## The Euclidean master integral

Consider

$$
J_\alpha(\Delta)
\equiv
\mu^{2\epsilon}
\int\frac{d^d k}{(2\pi)^d}
\frac{1}{(k^2+\Delta)^\alpha},
\qquad
\Delta>0.
$$

Use the Schwinger representation

$$
\frac{1}{(k^2+\Delta)^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s(k^2+\Delta)}.
$$

The Gaussian momentum integral is

$$
\int\frac{d^d k}{(2\pi)^d}e^{-sk^2}
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

The divergence structure is now encoded in poles of $\Gamma(\alpha-d/2)$.

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
=
1+
\epsilon\left(\ln4\pi+\ln\frac{\mu^2}{\Delta}\right)
+O(\epsilon^2).
$$

Therefore

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\epsilon}-\gamma_E+\ln4\pi-
\ln\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

Equivalently,

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

This formula is the workhorse behind one-loop bubble integrals after Feynman parameterization. The $1/\overline\epsilon$ term is the UV pole. The logarithm is the finite memory of the scale $\Delta$ relative to the arbitrary scale $\mu$.

## The tadpole integral

For $\alpha=1$ and $d=4-2\epsilon$,

$$
J_1(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}
\Gamma(-1+\epsilon)\Delta^{1-\epsilon}.
$$

Expanding around $\epsilon=0$ gives

$$
J_1(\Delta)
=
\frac{\Delta}{16\pi^2}
\left[
-\frac{1}{\overline\epsilon}
+
\ln\frac{\Delta}{\mu^2}
-1
+O(\epsilon)
\right].
$$

The sign of the pole is not a mistake. It follows from the pole of $\Gamma(-1+\epsilon)$.

This formula is the dimensional-regularization counterpart of the cutoff tadpole. In cutoff language the same integral contains a quadratic divergence and a logarithmic divergence. In dimensional regularization with minimal subtraction, the power-divergent part is not represented as a $\Lambda^2$ term. The remaining pole is tied to the logarithmic scale dependence.

A useful derivative check survives:

$$
J_2(\Delta)=-\frac{\partial J_1(\Delta)}{\partial \Delta}
$$

up to terms that vanish after the consistent $\epsilon$ expansion is performed.

## Minimal subtraction and MS-bar

Dimensional regularization by itself only regulates. A subtraction prescription turns it into a renormalization scheme.

The most common schemes are:

| Scheme | What is subtracted |
|---|---|
| MS | the pure pole terms $1/\epsilon^n$ |
| $\overline{\mathrm{MS}}$ | the combination $1/\overline\epsilon^n$ and associated higher-pole generalizations |

At one loop, $\overline{\mathrm{MS}}$ removes

$$
\frac{1}{\overline\epsilon}
=
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

For the logarithmic master integral, the $\overline{\mathrm{MS}}$-subtracted result is simply

$$
J_2^{\overline{\mathrm{MS}}}(\Delta)
=
-\frac{1}{16\pi^2}
\ln\frac{\Delta}{\mu^2}
$$

up to finite constants fixed by the exact integral being evaluated. Different finite subtractions define different schemes. Physical predictions agree once renormalized parameters are translated between schemes.

:::note[Minimal subtraction is not a physical renormalization condition]
MS and $\overline{\mathrm{MS}}$ remove pole parts. They do not directly say that a mass equals a pole mass or that a coupling equals a measured scattering amplitude at a chosen momentum. Such physical statements require matching or a separate renormalization condition.
:::

## Scaleless integrals vanish

A defining feature of dimensional regularization is that scaleless integrals vanish:

$$
\int\frac{d^d k}{(2\pi)^d}(k^2)^\nu=0
$$

whenever no mass, external momentum, or other scale is present.

A quick argument uses scaling. Let

$$
I=\int d^d k\,(k^2)^\nu.
$$

Under $k\mapsto ak$,

$$
I=a^{d+2\nu}I.
$$

If no scale exists to compensate this factor, analytic regularization sets $I=0$ except at singular cases. More carefully, scaleless integrals often contain canceling UV and IR poles. Dimensional regularization records only the combined scaleless integral, which is zero.

This rule is useful but dangerous if misread. For example,

$$
\int\frac{d^d k}{(2\pi)^d}\frac{1}{k^2}
=0
$$

in dimensional regularization because it has no scale. It is not “finite” in a physical sense; it is both UV and IR singular in ordinary terms. The zero reflects the regulator and analytic continuation.

## Relation to cutoff logarithms

Dimensional regularization and cutoff regularization encode logarithmic divergences differently. A cutoff bubble integral has

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[
\ln\frac{\Lambda^2}{m^2}-1+\cdots
\right].
$$

Dimensional regularization gives

$$
J_2(m^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{m^2}{\mu^2}
+\cdots
\right].
$$

The rough dictionary is

$$
\ln\Lambda^2
\quad\leftrightarrow\quad
\frac{1}{\overline\epsilon}+\ln\mu^2
$$

up to finite scheme-dependent constants. This is not an equality of regulators. It is a way to recognize that both descriptions require a local counterterm and leave behind logarithmic scale dependence.

Power divergences do not translate this way. In minimal-subtraction dimensional regularization, scaleless power divergences vanish. This is convenient for many calculations, but it can hide Wilsonian threshold sensitivity. When a heavy mass $M$ is present, dimensionally regularized amplitudes still know about $M$ through logarithms and finite threshold corrections after matching.

## Tensor integrals

Dimensional regularization treats rotationally invariant Euclidean tensor integrals cleanly. For any function $F(k^2)$,

$$
\int d^d k\,k_\mu k_\nu F(k^2)
=
\frac{\delta_{\mu\nu}}{d}
\int d^d k\,k^2F(k^2).
$$

Similarly,

$$
\int d^d k\,k_\mu k_\nu k_\rho k_\sigma F(k^2)
=
\frac{
\delta_{\mu\nu}\delta_{\rho\sigma}
+\delta_{\mu\rho}\delta_{\nu\sigma}
+\delta_{\mu\sigma}\delta_{\nu\rho}
}{d(d+2)}
\int d^d k\,(k^2)^2F(k^2).
$$

In Lorentzian form, replace Euclidean $\delta_{\mu\nu}$ with the appropriate metric after Wick rotation and sign bookkeeping. The power of dimensional regularization is that these algebraic reductions are compatible with momentum shifts and covariance in $d$ dimensions.

## Gauge theories and chiral subtleties

Dimensional regularization is popular partly because it preserves the identities one most wants to keep in gauge theories. Momentum shifts are allowed, tensor reduction is covariant, and gauge-invariant counterterm structure is easier to maintain.

However, not every four-dimensional object has a harmless continuation to $d$ dimensions. The main warning signs are:

| Object | Subtlety |
|---|---|
| $\gamma^5$ | defined using four-dimensional gamma matrices and the four-dimensional Levi-Civita tensor |
| $\epsilon^{\mu\nu\rho\sigma}$ | intrinsically four-dimensional |
| helicity states | tied to integer-dimensional little-group structure |
| Fierz identities | can change away from four dimensions |
| evanescent operators | vanish in four dimensions but affect finite terms through poles |

For ordinary scalar theories, QED without chiral complications, and many Yang–Mills calculations, dimensional regularization is straightforward. For chiral gauge theories, anomalies, and multi-loop operator mixing, the prescription must be stated carefully.

## Common pitfalls

**Forgetting the scale $\mu$.** The measure $d^d k$ changes dimension when $d$ changes. The scale $\mu$ is needed so that couplings keep their conventional dimensions and logarithms have dimensionless arguments.

**Thinking $1/\epsilon$ is literally a cutoff.** An epsilon pole plays the role of a UV divergence, but it is not the same object as $\Lambda^2$ or $\ln\Lambda$. The relation is clearest for logarithmic divergences; power divergences are scheme-dependent.

**Calling a scaleless integral finite.** Dimensional regularization sets scaleless integrals to zero by analytic continuation. Many such integrals contain both UV and IR singular behavior, so the zero should not be interpreted as ordinary convergence.

**Dropping $O(\epsilon)$ terms too early.** At multi-loop order or in products of counterterms, an $O(\epsilon)$ term can multiply a $1/\epsilon$ pole and contribute to the finite answer. Keep enough terms for the order being computed.

**Using four-dimensional identities inside $d$-dimensional algebra.** Identities involving $\gamma^5$, Levi-Civita tensors, helicity, or dimension-specific trace relations require a stated prescription. This is not optional in chiral or high-loop calculations.

## Relations to other pages

- [Cutoff Regularization](/perturbative-qft/loop-expansion-regularization/cutoff-regularization/) explains the regulator where UV power sensitivity is most visible.
- [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/) predicts which loop integrals produce UV poles in dimensional regularization.
- [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) explains why each independent loop momentum receives a $d$-dimensional integration measure.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) shows how pole subtractions enter diagrammatic perturbation theory.
- [Conventions and Notation](/perturbative-qft/conventions/) fixes the scattering normalization and loop-measure conventions used in this volume.

## Research status

Dimensional regularization and minimal subtraction are textbook-standard and central to modern perturbative QFT. The basic scalar master integrals, epsilon expansion, and MS or $\overline{\mathrm{MS}}$ subtraction rules are settled.

The active subtleties are not about whether the method works. They concern how to implement it in dimension-specific settings: chiral gauge theories, $\gamma^5$, evanescent operators, helicity schemes, supersymmetry-preserving dimensional reduction, infrared factorization, and high-loop scheme conversions. Precision calculations often devote serious effort to these bookkeeping issues because tiny convention differences can move finite terms between amplitudes, counterterms, and operator definitions.

## Exercises

### Exercise 1: Derive the master integral

Use the Schwinger representation to derive

$$
\mu^{2\epsilon}
\int\frac{d^d k}{(2\pi)^d}
\frac{1}{(k^2+\Delta)^\alpha}
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
\Delta^{d/2-\alpha}.
$$

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
\frac{1}{(k^2+\Delta)^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s(k^2+\Delta)}.
$$

Then

$$
\int\frac{d^d k}{(2\pi)^d}e^{-sk^2}
=
\frac{1}{(4\pi s)^{d/2}}.
$$

Therefore

$$
J_\alpha(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-d/2-1}e^{-s\Delta}.
$$

Using

$$
\int_0^\infty ds\,s^{a-1}e^{-s\Delta}
=
\Gamma(a)\Delta^{-a},
$$

with $a=\alpha-d/2$, gives the result.

</details>

### Exercise 2: Expand the logarithmic integral

Starting from

$$
J_2(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}
\Gamma(\epsilon)\Delta^{-\epsilon},
$$

show that

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon),
$$

and

$$
\mu^{2\epsilon}(4\pi)^\epsilon\Delta^{-\epsilon}
=
1+
\epsilon\left(\ln4\pi+\ln\frac{\mu^2}{\Delta}\right)+O(\epsilon^2).
$$

Multiplying gives

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\epsilon}-\gamma_E+\ln4\pi+
\ln\frac{\mu^2}{\Delta}+O(\epsilon)
\right].
$$

Since

$$
\frac{1}{\overline\epsilon}
=
\frac{1}{\epsilon}-\gamma_E+\ln4\pi,
$$

this is

$$
J_2(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{\Delta}{\mu^2}+O(\epsilon)
\right].
$$

</details>

### Exercise 3: Dimension of the quartic coupling

In $d=4-2\epsilon$, show that the scalar quartic coupling has mass dimension $2\epsilon$.

<details>
<summary><strong>Solution</strong></summary>

The scalar field has dimension

$$
[\phi]=\frac{d-2}{2}.
$$

The operator $\phi^4$ has dimension

$$
[\phi^4]=4\cdot\frac{d-2}{2}=2d-4.
$$

Since the Lagrangian density has dimension $d$, the quartic coupling has dimension

$$
[\lambda]=d-(2d-4)=4-d.
$$

For $d=4-2\epsilon$,

$$
[\lambda]=4-(4-2\epsilon)=2\epsilon.
$$

That is why one writes $\lambda_B=\mu^{2\epsilon}Z_\lambda\lambda(\mu)$.

</details>

### Exercise 4: Scaleless integral by scaling

Use a scaling argument to explain why

$$
\int d^d k\,(k^2)^\nu=0
$$

in dimensional regularization.

<details>
<summary><strong>Solution</strong></summary>

Let

$$
I=\int d^d k\,(k^2)^\nu.
$$

Under $k\mapsto ak$, the integral scales as

$$
I=a^{d+2\nu}I.
$$

Since there is no external scale in the problem, the result cannot depend on $a$. For generic $d+2\nu$, the only analytic answer compatible with this scaling is

$$
I=0.
$$

This argument hides the fact that the integral may have both UV and IR singularities. Dimensional regularization defines the scaleless integral by analytic continuation, where those singularities cancel in the combined expression.

</details>

### Exercise 5: Compare a cutoff logarithm with an epsilon pole

Compare the logarithmic structures

$$
I_2^\Lambda(m^2)
=
\frac{1}{16\pi^2}
\left[\ln\frac{\Lambda^2}{m^2}-1+\cdots\right]
$$

and

$$
J_2(m^2)
=
\frac{1}{16\pi^2}
\left[\frac{1}{\overline\epsilon}-\ln\frac{m^2}{\mu^2}+\cdots\right].
$$

What part is regulator-dependent, and what part survives as physical scale dependence after renormalization?

<details>
<summary><strong>Solution</strong></summary>

The divergent objects $\ln\Lambda^2$ and $1/\overline\epsilon$ are regulator-dependent. They are removed by local counterterms in a chosen renormalization scheme.

The logarithmic dependence on physical scales remains. In cutoff language it appears through $-\ln m^2$ together with the subtraction scale implicit in the renormalization condition. In dimensional regularization it appears as

$$
-\ln\frac{m^2}{\mu^2}.
$$

After renormalization, amplitudes depend on ratios of physical scales and on the arbitrary scale $\mu$ only through renormalized parameters whose running cancels the explicit $\mu$ dependence in observables.

</details>

## References

### Standard first pass

- Mark Srednicki, *Quantum Field Theory*, §§14–20 and 27, for scalar loop corrections, all-orders perturbation theory, and other renormalization schemes.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, appendix B and chs. 15–20, for dimensional regularization identities and applications to renormalized perturbation theory and infrared divergences.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 25 and 32, for regularization, renormalization, and generating-functional loop expansion.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, for renormalization, power counting, and the general structure of perturbative QFT.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, ch. 10, for dimensional continuation, dimensional regularization, minimal subtraction, and RG functions.
- G. ’t Hooft and M. Veltman, “Regularization and Renormalization of Gauge Fields,” *Nuclear Physics B* **44** (1972), for the classic gauge-theory development of dimensional regularization.
- C. G. Bollini and J. J. Giambiagi, “Dimensional Renormalization: The Number of Dimensions as a Regularizing Parameter,” *Il Nuovo Cimento B* **12** (1972), for an early formulation of dimensional regularization.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume.
