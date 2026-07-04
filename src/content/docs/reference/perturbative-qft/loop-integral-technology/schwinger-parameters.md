---
title: "Schwinger Parameters"
description: "A practical derivation of Schwinger proper-time representations, their relation to Feynman parameters, and their use in loop integrals and heat-kernel reasoning."
sidebar:
  label: "Schwinger Parameters"
  order: 2
level: Graduate
status: "Polished draft"
source: "Schwinger proper time; Srednicki 2007, §§14–20; Coleman 2019, chs. 15–16; Schwartz 2014, Appendix B and ch. 33; Zinn-Justin 2021, Appendix A8; Zee 2010, Appendix D"
topics:
  - Schwinger parameters
  - proper-time representation
  - loop integrals
  - heat kernel
  - dimensional regularization
canonicalTopics:
  - schwinger-parameterization
  - proper-time-representation
  - heat-kernel-loop-integral
  - feynman-parameter-relation
  - ultraviolet-small-proper-time
researchStatus:
  established:
    - "Schwinger parameterization is a standard representation of inverse operators and propagator denominators by proper-time integrals."
  active:
    - "Modern uses include heat-kernel effective actions, worldline methods, string-inspired integral representations, sector decomposition, and geometric analyses of ultraviolet and infrared limits."
---

## Summary

**Schwinger parameters** represent propagator denominators as integrals over an auxiliary positive variable. In Euclidean signature the basic identity is

$$
\frac{1}{A^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-sA},
\qquad \operatorname{Re} A>0.
$$

The parameter $s$ is often called **proper time**. For a Euclidean scalar denominator,

$$
\frac{1}{(k_E^2+m^2)^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-s(k_E^2+m^2)}.
$$

This turns loop integrals into Gaussian momentum integrals. For example,

$$
\int\frac{d^dk_E}{(2\pi)^d}\frac{1}{(k_E^2+\Delta)^\nu}
=
\frac{1}{(4\pi)^{d/2}}
\frac{\Gamma(\nu-d/2)}{\Gamma(\nu)}
\Delta^{d/2-\nu},
$$

where the formula is understood by analytic continuation when needed.

Schwinger parameters are the proper-time cousin of [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/). Feynman parameters combine denominators by introducing a simplex variable $x$; Schwinger parameters assign a positive length $s_i$ to each denominator, then change variables to the total proper time $T=\sum_i s_i$ and fractions $x_i=s_i/T$.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Schwinger parameterization represents denominators by proper-time integrals and turns loop momentum integrals into Gaussian integrals](/figures/perturbative-qft/schwinger-parameters.svg)

<figcaption>

Schwinger parameters replace each denominator by a proper-time integral. The total proper time $T$ controls the scale of the Gaussian momentum integral: small $T$ probes the ultraviolet, while large $T$ probes infrared thresholds and light degrees of freedom.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/).

It is also useful to know Gaussian integrals and the Gamma function identity

$$
\Gamma(\alpha)=\int_0^\infty dt\,t^{\alpha-1}e^{-t},
\qquad \operatorname{Re}\alpha>0.
$$

## Core idea

A propagator denominator is the inverse of a quadratic operator. Schwinger parameterization rewrites an inverse as an integral over an exponential:

$$
\frac{1}{A}=
\int_0^\infty ds\,e^{-sA}.
$$

In a loop integral, this is powerful because exponentials add:

$$
\frac{1}{A_1A_2}
=
\int_0^\infty ds_1\,ds_2\,
\exp[-s_1A_1-s_2A_2].
$$

If the $A_i$ are quadratic functions of loop momentum, the exponent is a quadratic form. Completing the square turns the loop momentum integral into a Gaussian. The remaining integral over Schwinger parameters records masses, external momenta, thresholds, and divergences.

The conceptual dictionary is

| Schwinger parameter region | Physical or analytic role |
|---|---|
| small total proper time $T$ | large loop momentum, ultraviolet behavior |
| large total proper time $T$ | infrared behavior, light particles, thresholds |
| ratios $x_i=s_i/T$ | Feynman parameters, momentum routing fractions |
| Gaussian determinant | loop momentum integration |
| lower cutoff on $T$ | proper-time UV regulator |

This is one reason Schwinger parameters appear both in perturbative QFT and in heat-kernel methods. The same exponential that represents $1/A$ also represents the heat kernel $e^{-sA}$ of an operator.

## Setup and conventions

We use qft.org mostly-minus Lorentzian conventions, but this page often works in Euclidean momentum space because Schwinger parameter integrals converge most transparently there. The Wick rotation convention is the one in [Conventions and Notation](/perturbative-qft/conventions/) and [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/).

The Euclidean scalar denominator is written

$$
k_E^2+\Delta,
\qquad \Delta>0
$$

in the simplest region. The corresponding Lorentzian denominator after Feynman parameterization is usually

$$
k^2-\Delta+i\epsilon.
$$

For one Lorentzian denominator,

$$
\frac{i}{A+i\epsilon}
=
\int_0^\infty ds\,e^{is(A+i\epsilon)}.
$$

Indeed, the factor $e^{-\epsilon s}$ makes the upper limit convergent. More generally,

$$
\frac{i}{(A+i\epsilon)^\alpha}
=
\frac{i^{1-\alpha}}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{is(A+i\epsilon)}.
$$

For most practical loop calculations, it is safer to derive the integral in Euclidean signature and analytically continue back to Lorentzian kinematics with the $i\epsilon$ prescription intact.

We use the dimensionally regulated loop measure

$$
\int_{k_E}
\equiv
\mu^{2\epsilon}\int\frac{d^dk_E}{(2\pi)^d},
\qquad d=4-2\epsilon
$$

when a mass scale is needed. In purely Euclidean formulas below, factors of $\mu^{2\epsilon}$ can be inserted directly in the loop measure.

## Derivation from the Gamma function

Start from the Gamma function integral

$$
\Gamma(\alpha)
=
\int_0^\infty dt\,t^{\alpha-1}e^{-t}.
$$

For $\operatorname{Re}A>0$, set

$$
t=sA,
\qquad dt=A\,ds.
$$

Then

$$
\Gamma(\alpha)
=
\int_0^\infty ds\,(sA)^{\alpha-1}A e^{-sA}
=
A^\alpha\int_0^\infty ds\,s^{\alpha-1}e^{-sA}.
$$

Therefore

$$
\frac{1}{A^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-sA}.
$$

For a single denominator, $\alpha=1$, this is just

$$
\frac{1}{A}=\int_0^\infty ds\,e^{-sA}.
$$

For a squared denominator,

$$
\frac{1}{A^2}=\int_0^\infty ds\,s e^{-sA}.
$$

This is why extra powers of a denominator correspond to extra powers of proper time.

## Standard Euclidean loop integral

Consider

$$
I_\nu(\Delta)
=
\mu^{2\epsilon}\int\frac{d^dk_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^\nu}.
$$

Schwinger parameterization gives

$$
I_\nu(\Delta)
=
\frac{\mu^{2\epsilon}}{\Gamma(\nu)}
\int_0^\infty ds\,s^{\nu-1}e^{-s\Delta}
\int\frac{d^dk_E}{(2\pi)^d}e^{-sk_E^2}.
$$

The Gaussian integral is

$$
\int\frac{d^dk_E}{(2\pi)^d}e^{-sk_E^2}
=
\frac{1}{(4\pi s)^{d/2}}.
$$

Therefore

$$
I_\nu(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}\Gamma(\nu)}
\int_0^\infty ds\,s^{\nu-1-d/2}e^{-s\Delta}.
$$

Using the Gamma function again,

$$
\int_0^\infty ds\,s^{\nu-1-d/2}e^{-s\Delta}
=
\Gamma(\nu-d/2)\Delta^{d/2-\nu},
$$

so

$$
I_\nu(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\nu-d/2)}{\Gamma(\nu)}
\Delta^{d/2-\nu}.
$$

This is the same standard integral reached from Feynman parameterization. The pole of $\Gamma(\nu-d/2)$ is the ultraviolet divergence in dimensional regularization.

### Reading the divergence from proper time

The proper-time integrand behaves at small $s$ as

$$
s^{\nu-1-d/2}.
$$

The lower endpoint $s=0$ is divergent when

$$
\nu-1-d/2\le -1,
$$

or

$$
{d\ge 2\nu.}
$$

This is the proper-time version of power counting. For example,

$$
\int\frac{d^4k_E}{(2\pi)^4}\frac{1}{(k_E^2+\Delta)^2}
$$

is logarithmically divergent because $d=4$ and $2\nu=4$. The divergence sits at small proper time.

## Relation to Feynman parameters

Schwinger parameters imply Feynman parameters almost for free. Start with

$$
\frac{1}{A_1^{\alpha_1}\cdots A_n^{\alpha_n}}
=
\prod_{j=1}^n
\frac{1}{\Gamma(\alpha_j)}
\int_0^\infty ds_j\,s_j^{\alpha_j-1}
\exp\left[-\sum_{j=1}^n s_jA_j\right].
$$

Define

$$
T=\sum_{j=1}^n s_j,
\qquad
x_j=\frac{s_j}{T},
\qquad
\sum_{j=1}^n x_j=1.
$$

Then

$$
\sum_{j=1}^n s_jA_j
=
T\sum_{j=1}^n x_jA_j.
$$

The measure becomes

$$
\prod_{j=1}^n ds_j\,s_j^{\alpha_j-1}
=
 dT\,T^{\alpha-1}
\left[\prod_{j=1}^n dx_j\,x_j^{\alpha_j-1}\right]
\delta\!\left(1-\sum_{j=1}^n x_j\right),
$$

where

$$
\alpha=\sum_{j=1}^n\alpha_j.
$$

The $T$ integral is

$$
\int_0^\infty dT\,T^{\alpha-1}
\exp\left[-T\sum_jx_jA_j\right]
=
\Gamma(\alpha)
\left(\sum_jx_jA_j\right)^{-\alpha}.
$$

Thus

$$
\frac{1}{A_1^{\alpha_1}\cdots A_n^{\alpha_n}}
=
\frac{\Gamma(\alpha)}{\Gamma(\alpha_1)\cdots\Gamma(\alpha_n)}
\int_0^1\left[\prod_{j=1}^n dx_j\,x_j^{\alpha_j-1}\right]
\delta\!\left(1-\sum_{j=1}^n x_j\right)
\frac{1}{\left(\sum_jx_jA_j\right)^\alpha}.
$$

So Feynman parameters are ratios of Schwinger proper times. The total proper time $T$ has already been integrated out in the Feynman-parameter formula.

## Bubble integral in Schwinger form

Consider the Euclidean bubble

$$
I(P_E^2)
=
\int\frac{d^dk_E}{(2\pi)^d}
\frac{1}{(k_E^2+m_1^2)[(k_E+P_E)^2+m_2^2]}.
$$

Introduce two Schwinger parameters:

$$
I(P_E^2)
=
\int_0^\infty ds\,dt
\int\frac{d^dk_E}{(2\pi)^d}
\exp\left[-s(k_E^2+m_1^2)-t((k_E+P_E)^2+m_2^2)\right].
$$

The exponent containing $k_E$ is

$$
s k_E^2+t(k_E+P_E)^2
=
(s+t)\left(k_E+\frac{t}{s+t}P_E\right)^2
+\frac{st}{s+t}P_E^2.
$$

Therefore

$$
I(P_E^2)
=
\frac{1}{(4\pi)^{d/2}}
\int_0^\infty ds\,dt\,
(s+t)^{-d/2}
\exp\left[-s m_1^2-tm_2^2-\frac{st}{s+t}P_E^2\right].
$$

Now set

$$
T=s+t,
\qquad
x=\frac{s}{s+t},
\qquad
1-x=\frac{t}{s+t}.
$$

Since $ds\,dt=T\,dT\,dx$, the integral becomes

$$
I(P_E^2)
=
\frac{1}{(4\pi)^{d/2}}
\int_0^1 dx\int_0^\infty dT\,
T^{1-d/2}
\exp[-T\Delta_E(x)],
$$

where

$$
\Delta_E(x)=xm_1^2+(1-x)m_2^2+x(1-x)P_E^2.
$$

Integrating over $T$ gives

$$
I(P_E^2)
=
\frac{\Gamma(2-d/2)}{(4\pi)^{d/2}}
\int_0^1 dx\,[\Delta_E(x)]^{d/2-2}.
$$

This is exactly the Feynman-parameter result in Euclidean kinematics.

## Proper-time cutoffs

A proper-time cutoff regulates ultraviolet divergences by excluding very small $s$. For example,

$$
\frac{1}{A}
\longrightarrow
\int_{1/\Lambda^2}^\infty ds\,e^{-sA}.
$$

For the standard Euclidean loop integral,

$$
I_\nu^\Lambda(\Delta)
=
\frac{1}{(4\pi)^{d/2}\Gamma(\nu)}
\int_{1/\Lambda^2}^\infty ds\,s^{\nu-1-d/2}e^{-s\Delta}.
$$

The divergent terms are obtained by expanding the exponential at small $s$:

$$
e^{-s\Delta}=1-s\Delta+\frac{s^2\Delta^2}{2}-\cdots.
$$

For instance, in $d=4$ and $\nu=1$,

$$
I_1^\Lambda(\Delta)
=
\frac{1}{(4\pi)^2}
\int_{1/\Lambda^2}^\infty ds\,s^{-2}e^{-s\Delta}.
$$

The leading small-$s$ terms give

$$
I_1^\Lambda(\Delta)
\sim
\frac{1}{(4\pi)^2}
\left[
\Lambda^2
-\Delta\log\frac{\Lambda^2}{\Delta}
+\cdots
\right],
$$

up to scheme-dependent constants. The precise finite constant depends on how the cutoff is implemented, but the local divergent structure is the point.

A proper-time cutoff is intuitive because it exposes UV divergences geometrically. It is not automatically the best regulator for every theory: gauge invariance, chiral symmetry, and regulator consistency must be checked just as carefully as with a momentum cutoff.

## Heat-kernel viewpoint

Let $\mathcal O$ be a positive Euclidean operator, such as

$$
\mathcal O=-\partial_E^2+m^2.
$$

Then

$$
\mathcal O^{-1}
=
\int_0^\infty ds\,e^{-s\mathcal O}.
$$

The kernel of $e^{-s\mathcal O}$ is the heat kernel. In flat space,

$$
\langle x|e^{-s(-\partial_E^2+m^2)}|y\rangle
=
\frac{1}{(4\pi s)^{d/2}}
\exp\left[-\frac{(x-y)^2}{4s}-sm^2\right].
$$

The one-loop effective action of a bosonic Gaussian integral contains

$$
\Gamma^{(1)}
=
\frac12\operatorname{Tr}\log\mathcal O.
$$

Using

$$
\log\mathcal O
=
-\int_0^\infty\frac{ds}{s}\,e^{-s\mathcal O}
$$

up to regulator-dependent constants, one obtains

$$
\Gamma^{(1)}
=
-\frac12\int_0^\infty\frac{ds}{s}\,
\operatorname{Tr}e^{-s\mathcal O}.
$$

This is the bridge from Schwinger parameters to heat-kernel expansions, background-field effective actions, and curved-spacetime one-loop calculations.

The small-$s$ expansion of the heat kernel has the schematic form

$$
\operatorname{Tr}e^{-s\mathcal O}
\sim
\frac{1}{(4\pi s)^{d/2}}
\sum_{n=0}^\infty s^n a_n(\mathcal O),
$$

where the coefficients $a_n$ are local integrals built from background fields, curvature, and their derivatives. Ultraviolet divergences are local because they come from the small-$s$ expansion.

## When Schwinger parameters are better than Feynman parameters

Feynman parameters are usually fastest for elementary one-loop amplitude calculations. Schwinger parameters are especially useful when one of the following is true.

| Situation | Why Schwinger parameters help |
|---|---|
| Heat-kernel or effective-action calculation | $e^{-s\mathcal O}$ is the natural object. |
| Background fields | Proper time keeps operator structure visible. |
| Worldline or string-inspired methods | Proper time becomes a length modulus. |
| UV/IR endpoint analysis | Small and large proper time separate cleanly. |
| Many denominators | Independent $s_i$ variables can be more symmetric before changing to simplex variables. |
| Nonlocal form factors | Exponentials often keep momentum dependence compact. |

The methods are not competitors. They are two coordinate systems on the same calculation. Often one introduces Schwinger parameters, changes to $T$ and $x_i$, integrates over $T$, and lands on Feynman parameters.

## Common pitfalls

**Using the Euclidean formula in Lorentzian signature without the $i\epsilon$ prescription.** The Euclidean identity $1/A=\int_0^\infty ds\,e^{-sA}$ assumes convergence. Lorentzian denominators require oscillatory proper-time integrals and the damping from $i\epsilon$.

**Forgetting where the UV lives.** In proper time, ultraviolet behavior is the small-$s$ or small-$T$ endpoint, not large proper time.

**Forgetting where the IR lives.** Massless particles, thresholds, and long-distance physics usually appear at large proper time or at endpoints of the parameter simplex.

**Treating a proper-time cutoff as automatically symmetry-preserving.** Some symmetries are easy to preserve; others are not. Gauge invariance, chirality, and regulator-dependent anomalies require care.

**Dropping field-independent terms too early.** In flat-space normalized correlators, many vacuum factors cancel. In effective actions, thermal free energies, curved spacetime, and gravity, determinant constants can matter.

**Interchanging divergent integrations casually.** Schwinger parameterization often changes the order of integrations. A regulator or analytic-continuation prescription is part of the definition of the manipulation.

## Relations to other pages

- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) derives the simplex form obtained by integrating out the total Schwinger proper time.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains the analytic continuation that gives meaning to the Gamma-function poles.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) uses the same standard integral after denominator combination.
- [Cutoff Regularization](/perturbative-qft/loop-expansion-regularization/cutoff-regularization/) compares different ways of making UV divergences finite.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how local UV divergences are absorbed into local terms in the Lagrangian.
- [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/) uses the same Gaussian symmetry logic to reduce numerator powers of loop momentum.

## Research status

- **Established:** Schwinger parameterization, proper-time regularization, and heat-kernel representations are standard tools in perturbative QFT, effective actions, and spectral analysis.
- **Convention-dependent:** Lorentzian proper-time formulas depend on the $i\epsilon$ prescription and on how the Wick rotation is implemented.
- **Regulator-dependent:** A proper-time cutoff is a useful regulator, but finite parts and some symmetry properties depend on the precise cutoff prescription.
- **Active:** Worldline methods, heat-kernel resummations, nonlocal effective actions, and string-inspired parameter representations remain active computational frameworks.

## Exercises

### Exercise 1: Derive the squared-denominator formula

Use the Gamma function to show that

$$
\frac{1}{A^2}
=
\int_0^\infty ds\,s e^{-sA}
$$

for $\operatorname{Re}A>0$.

<details>
<summary><strong>Solution</strong></summary>

Set $\alpha=2$ in

$$
\frac{1}{A^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-sA}.
$$

Since $\Gamma(2)=1$, we get

$$
\frac{1}{A^2}
=
\int_0^\infty ds\,s e^{-sA}.
$$

</details>

### Exercise 2: Gaussian proper-time integral

Evaluate

$$
\int\frac{d^dk_E}{(2\pi)^d}e^{-s k_E^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The ordinary $d$-dimensional Gaussian is

$$
\int d^dk_E\,e^{-s k_E^2}
=\left(\frac{\pi}{s}\right)^{d/2}.
$$

Dividing by $(2\pi)^d$ gives

$$
\int\frac{d^dk_E}{(2\pi)^d}e^{-s k_E^2}
=
\frac{1}{(2\pi)^d}\left(\frac{\pi}{s}\right)^{d/2}
=
\frac{1}{(4\pi s)^{d/2}}.
$$

</details>

### Exercise 3: Proper-time power counting

For

$$
I_\nu(\Delta)=\int\frac{d^dk_E}{(2\pi)^d}\frac{1}{(k_E^2+\Delta)^\nu},
$$

show from the Schwinger representation that the UV divergence occurs when $d\ge2\nu$.

<details>
<summary><strong>Solution</strong></summary>

Schwinger parameterization gives

$$
I_\nu(\Delta)
=
\frac{1}{(4\pi)^{d/2}\Gamma(\nu)}
\int_0^\infty ds\,s^{\nu-1-d/2}e^{-s\Delta}.
$$

The ultraviolet region is $s\to0$. Near this endpoint, $e^{-s\Delta}\to1$, so the integral behaves like

$$
\int_0 ds\,s^{\nu-1-d/2}.
$$

An integral $\int_0 ds\,s^a$ diverges at the lower endpoint if $a\le -1$. Thus

$$
\nu-1-d/2\le -1,
$$

which is equivalent to

$$
d\ge2\nu.
$$

</details>

### Exercise 4: Recover one Feynman parameter

Starting from

$$
\frac{1}{AB}
=
\int_0^\infty ds\,dt\,e^{-sA-tB},
$$

use $T=s+t$ and $x=s/(s+t)$ to show that

$$
\frac{1}{AB}
=
\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

With

$$
s=xT,
\qquad
 t=(1-x)T,
$$

we have

$$
ds\,dt=T\,dT\,dx.
$$

The exponent becomes

$$
sA+tB=T[xA+(1-x)B].
$$

Therefore

$$
\frac{1}{AB}
=
\int_0^1 dx\int_0^\infty dT\,T e^{-T[xA+(1-x)B]}.
$$

Using

$$
\int_0^\infty dT\,T e^{-TC}=\frac{1}{C^2},
$$

we obtain

$$
\frac{1}{AB}
=
\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

</details>

### Exercise 5: Proper-time cutoff in four dimensions

Show that

$$
\int_{1/\Lambda^2}^\infty ds\,s^{-1}e^{-s\Delta}
$$

contains a logarithmic divergence as $\Lambda\to\infty$.

<details>
<summary><strong>Solution</strong></summary>

At small $s$,

$$
e^{-s\Delta}=1+O(s).
$$

Therefore the divergent part is

$$
\int_{1/\Lambda^2} ds\,s^{-1}
=
\log s\Big|_{1/\Lambda^2}^{\text{fixed}}
=
\log\Lambda^2+\text{finite}.
$$

The coefficient of this logarithm depends on the prefactors multiplying the proper-time integral, but the logarithmic endpoint divergence is universal.

</details>

## References

- J. Schwinger, “On Gauge Invariance and Vacuum Polarization,” *Physical Review* **82** (1951), for the proper-time method in QED.
- M. Srednicki, *Quantum Field Theory*, §§14–20, for one-loop scalar integrals and early loop-correction examples.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 15–16, for one-loop integrals, Feynman parameters, and renormalization examples.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, Appendix B and ch. 33, for regularization formulas and Schwinger proper-time effective actions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, Appendix A8 and chs. 8–10, for proper-time regularization, dimensional regularization, and renormalization.
- A. Zee, *Quantum Field Theory in a Nutshell*, Appendix D, for compact integral formulas.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume. Figure generated from compact TikZ source in the qft.org black/gray style.
