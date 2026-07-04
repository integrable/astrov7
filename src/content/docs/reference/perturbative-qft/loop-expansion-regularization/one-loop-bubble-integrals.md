---
title: "One-Loop Bubble Integrals"
description: "A derivation and practical guide to the scalar one-loop bubble integral, its Feynman-parameter form, ultraviolet pole, threshold branch cut, and role in one-loop amplitudes."
sidebar:
  label: "One-Loop Bubbles"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20; Coleman 2019, chs. 15–16; Weinberg 1995, Vol. I, chs. 6 and 12; Schwartz 2014, chs. 16–20; Zinn-Justin 2021, chs. 8–10"
topics:
  - one-loop integrals
  - bubble diagrams
  - Feynman parameters
  - dimensional regularization
  - branch cuts
canonicalTopics:
  - one-loop-bubble-integral
  - scalar-bubble-integral
  - feynman-parameterization
  - threshold-branch-cut
  - one-loop-four-point-amplitude
researchStatus:
  established:
    - "The scalar one-loop bubble integral, its Feynman-parameter representation, ultraviolet pole, and threshold discontinuity are standard textbook material in perturbative QFT."
  active:
    - "Modern precision calculations generalize this elementary integral to tensor bubbles, multi-scale master integrals, unitarity cuts, infrared-subtracted integrals, and automated loop-integral reduction."
---

## Summary

The **one-loop bubble integral** is the first loop integral where external momentum flows through two propagators. It appears in one-loop corrections to four-point scattering, in self-energy diagrams of cubic theories, in vacuum polarization, and as the simplest example of a loop integral with both ultraviolet structure and a physical threshold.

This page uses the following stripped scalar bubble convention. The product of two scalar Feynman propagators is written as

$$
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m_1^2+i\epsilon}
\frac{i}{(\ell+P)^2-m_2^2+i\epsilon}
\equiv
-i\,B(P^2;m_1^2,m_2^2),
$$

with $d=4-2\epsilon$. Then

$$
B(P^2;m_1^2,m_2^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\int_0^1 dx\,
\ln\frac{\Delta(x)-i\epsilon}{\mu^2}
\right]
+O(\epsilon),
$$

where

$$
\Delta(x)=x m_1^2+(1-x)m_2^2-x(1-x)P^2.
$$

The ultraviolet pole is independent of $P^2$ and the masses; the finite logarithm contains the physical scale dependence and the threshold branch cut.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A scalar one-loop bubble with external momentum P and internal momenta ell and ell plus P, mapped to a Feynman-parameter integral](/figures/perturbative-qft/one-loop-bubble-integrals.svg)

<figcaption>

The scalar bubble is the canonical two-propagator one-loop integral. Feynman parameterization combines the denominators, shifts the loop momentum, and reduces the integral to the master logarithmic integral with $\Delta(x)=x m_1^2+(1-x)m_2^2-x(1-x)P^2$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), and [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/).

For scattering applications, review [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) and [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/).

## Core idea

A loop bubble is what remains after a loop has two internal propagators and one independent momentum. The external momentum $P$ flows through the pair, so the integral knows about the invariant $P^2$.

The workflow is always the same:

1. combine the two denominators with a Feynman parameter;
2. shift the loop momentum so the denominator is rotationally invariant;
3. evaluate the standard dimensionally regulated integral;
4. interpret the answer as a UV pole plus a finite logarithm;
5. analytically continue in $P^2$ to see thresholds and imaginary parts.

The bubble is therefore a small laboratory for several themes that recur in higher-loop QFT: Feynman parameters, regulator dependence, branch cuts, discontinuities, and local counterterms.

## Setup and conventions

We use qft.org mostly-minus conventions and plane waves $e^{-ip\cdot x}$. The scalar propagator is

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

The dimensionally regulated loop dimension is

$$
d=4-2\epsilon,
$$

and $1/\overline\epsilon$ denotes

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

The scalar bubble function on this page is stripped of the overall $-i$ carried by the product of two Feynman propagators:

$$
\int_\ell
\frac{i}{\ell^2-m_1^2+i\epsilon}
\frac{i}{(\ell+P)^2-m_2^2+i\epsilon}
=
-iB(P^2;m_1^2,m_2^2),
$$

where

$$
\int_\ell
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}.
$$

This sign convention keeps the scalar function $B$ equal to the positive Euclidean master integral after Feynman parameterization. Other books may put the factor of $i$ elsewhere. Always compare the full diagram, not just the symbol $B$.

## Feynman parameterization

Start from the denominator product

$$
A=\ell^2-m_1^2+i\epsilon,
\qquad
B_2=(\ell+P)^2-m_2^2+i\epsilon.
$$

Use

$$
\frac{1}{AB_2}
=
\int_0^1 dx\,\frac{1}{[xA+(1-x)B_2]^2}.
$$

The combined denominator is

$$
\begin{aligned}
xA+(1-x)B_2
&=x(\ell^2-m_1^2+i\epsilon)
+(1-x)((\ell+P)^2-m_2^2+i\epsilon)\\
&=(\ell+(1-x)P)^2
-\Delta(x)+i\epsilon,
\end{aligned}
$$

with

$$
\Delta(x)=x m_1^2+(1-x)m_2^2-x(1-x)P^2.
$$

After the shift

$$
k=\ell+(1-x)P,
$$

the product of propagators becomes

$$
\int_\ell
\frac{i}{\ell^2-m_1^2+i\epsilon}
\frac{i}{(\ell+P)^2-m_2^2+i\epsilon}
=
-
\int_0^1 dx\,
\mu^{2\epsilon}\int\frac{d^d k}{(2\pi)^d}
\frac{1}{(k^2-\Delta(x)+i\epsilon)^2}.
$$

Wick rotation gives the Euclidean logarithmic master integral. With the stripped definition above, the final result is

$$
B(P^2;m_1^2,m_2^2)
=
\int_0^1 dx\,
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta(x)-i\epsilon)^2}.
$$

The momentum integral is precisely the $\alpha=2$ master integral from dimensional regularization.

## Dimensional-regularization result

Using

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

we get

$$
B(P^2;m_1^2,m_2^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\int_0^1 dx\,
\ln\frac{x m_1^2+(1-x)m_2^2-x(1-x)P^2-i\epsilon}{\mu^2}
\right]
+O(\epsilon).
$$

The UV divergence is local: it does not depend on $P^2$. That is why a local counterterm can remove it. The nonlocal information sits in the finite logarithm and its analytic continuation.

For spacelike momentum $P^2=-Q^2<0$ and positive masses, the denominator becomes

$$
xm_1^2+(1-x)m_2^2+x(1-x)Q^2,
$$

which is positive for $0\le x\le1$. The integral is real and has no threshold singularity. Timelike momentum is more interesting because the logarithm can cross its branch cut.

## Equal masses and threshold behavior

For equal internal masses,

$$
B(s;m^2,m^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\int_0^1 dx\,
\ln\frac{m^2-x(1-x)s-i\epsilon}{\mu^2}
\right],
$$

where $s=P^2$. Below the two-particle threshold, $0<s<4m^2$, the integral is real and can be written as

$$
B(s;m^2,m^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{m^2}{\mu^2}
+2
-2\sqrt{\frac{4m^2}{s}-1}\,
\arctan\!\left(\frac{1}{\sqrt{4m^2/s-1}}\right)
\right].
$$

At $s=0$, the last two terms cancel, giving

$$
B(0;m^2,m^2)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{m^2}{\mu^2}
\right].
$$

Above threshold, $s>4m^2$, the interval where

$$
m^2-x(1-x)s<0
$$

has length

$$
\beta(s)=\sqrt{1-\frac{4m^2}{s}}.
$$

Using $\ln(-|a|-i\epsilon)=\ln|a|-i\pi$, the imaginary part is

$$
\operatorname{Im} B(s;m^2,m^2)
=
\frac{\beta(s)}{16\pi}\,\theta(s-4m^2).
$$

This is the simplest sign of unitarity inside a loop integral: once the external momentum can create the two internal particles on shell, the amplitude develops an absorptive part.

## Role in scalar four-point scattering

In $\lambda\phi^4/4!$ theory, the one-loop four-point amplitude receives three bubble contributions, corresponding to the $s$, $t$, and $u$ channels. With the conventions of this page,

$$
i\mathcal M_{s}^{(1)}
=
\frac{i\lambda^2}{2}B(s;m^2,m^2),
$$

and similarly for $t$ and $u$. Therefore

$$
\mathcal M_{2\to2}
=
-\lambda
+
\frac{\lambda^2}{2}
\left[B(s;m^2,m^2)+B(t;m^2,m^2)+B(u;m^2,m^2)\right]
+O(\lambda^3),
$$

before adding the coupling counterterm and before imposing a renormalization condition. The divergent part is

$$
\mathcal M_{\rm div}^{(1)}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon},
$$

because the three channels have the same UV pole. This is the local divergence that the $\phi^4$ coupling counterterm cancels.

The finite logarithms are not all removable. They encode the dependence of the scattering amplitude on the external invariants and on the renormalization scale.

## Checks and limits

**Large loop momentum.** For large $\ell$, the integrand behaves as

$$
\frac{d^4\ell}{\ell^4},
$$

so the four-dimensional bubble is logarithmically divergent. This matches the single $1/\overline\epsilon$ pole.

**Zero external momentum.** At $P=0$ and equal masses,

$$
B(0;m^2,m^2)
=
\mu^{2\epsilon}\int\frac{d^d k_E}{(2\pi)^d}\frac{1}{(k_E^2+m^2)^2},
$$

which is exactly the logarithmic master integral $J_2(m^2)$.

**Derivative with respect to mass.** Since

$$
\frac{\partial}{\partial m^2}\frac{1}{k_E^2+m^2}
=-\frac{1}{(k_E^2+m^2)^2},
$$

one has, at $P=0$,

$$
B(0;m^2,m^2)=-\frac{\partial A(m^2)}{\partial m^2},
$$

where $A(m^2)$ is the one-propagator tadpole integral.

**Threshold.** The imaginary part turns on at exactly the two-particle threshold $s=4m^2$. Below threshold the internal particles cannot both go on shell with total momentum $P$.

## Common pitfalls

**Losing the overall factor of $i$.** The scalar function $B$ on this page is stripped so that the product of two Feynman propagators gives $-iB$. Some books define the loop function with a different overall phase. Compare a full diagram such as $i\mathcal M_s^{(1)}$, not an isolated symbol.

**Shifting loop momentum inside a hard cutoff.** The shift $\ell\mapsto \ell+(1-x)P$ is harmless in dimensional regularization, but not automatically harmless with a hard momentum cutoff. A cutoff changes the integration region, so momentum-routing choices can move finite local terms.

**Confusing the UV pole with the branch cut.** The $1/\overline\epsilon$ pole is a short-distance divergence. The threshold imaginary part is an infrared or on-shell analytic feature of the finite logarithm. They have different physical meanings and are handled by different parts of the calculation.

**Forgetting the channel.** In $2\to2$ scattering, the same bubble function appears with $P^2=s$, $t$, or $u$. A channel that is timelike and above threshold can have an imaginary part even if another channel is spacelike and real.

**Treating finite constants as universal.** The coefficient of the UV pole is universal in a fixed normalization, but additive finite constants depend on the subtraction convention. The logarithmic dependence on physical ratios is the more durable information.

## Relations to other pages

- [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) explains why the bubble has one independent loop momentum.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) derives the master integral used after Feynman parameterization.
- [Cutoff Regularization](/perturbative-qft/loop-expansion-regularization/cutoff-regularization/) explains how the same logarithmic divergence appears with a momentum cutoff.
- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) gives the tree-level amplitudes corrected by these one-loop bubbles.
- [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/) explains how imaginary parts of amplitudes are tied to sums over physical intermediate states.

## Research status

The scalar one-loop bubble is completely standard. Its evaluation, UV pole, and threshold discontinuity are textbook material.

The active frontier is not this integral by itself. The same ideas scale into modern calculations involving tensor numerator reduction, unstable thresholds, infrared subtraction, multi-loop master integrals, differential equations, generalized unitarity, and numerical evaluation in difficult kinematic regions.

## Exercises

### Exercise 1: Derive the combined denominator

Starting from

$$
A=\ell^2-m_1^2+i\epsilon,
\qquad
B_2=(\ell+P)^2-m_2^2+i\epsilon,
$$

show that

$$
xA+(1-x)B_2
=(\ell+(1-x)P)^2-
\left[xm_1^2+(1-x)m_2^2-x(1-x)P^2\right]+i\epsilon.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the right-hand side of the Feynman-parameter combination:

$$
\begin{aligned}
xA+(1-x)B_2
&=x\ell^2+(1-x)(\ell^2+2\ell\cdot P+P^2)\\
&\quad -xm_1^2-(1-x)m_2^2+i\epsilon\\
&=\ell^2+2(1-x)\ell\cdot P+(1-x)P^2
-xm_1^2-(1-x)m_2^2+i\epsilon.
\end{aligned}
$$

Complete the square:

$$
(\ell+(1-x)P)^2
=\ell^2+2(1-x)\ell\cdot P+(1-x)^2P^2.
$$

The remaining coefficient of $P^2$ is

$$
(1-x)-(1-x)^2=x(1-x),
$$

which gives the stated expression.

</details>

### Exercise 2: Extract the UV pole

Use the dimensional-regularization master integral to show that the pole part of $B(P^2;m_1^2,m_2^2)$ is independent of $P^2$, $m_1$, and $m_2$.

<details>
<summary><strong>Solution</strong></summary>

After Feynman parameterization,

$$
B(P^2;m_1^2,m_2^2)
=
\int_0^1 dx\,
\mu^{2\epsilon}\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta(x)-i\epsilon)^2}.
$$

The master integral gives

$$
\frac{1}{16\pi^2}
\left[\frac{1}{\overline\epsilon}-\ln\frac{\Delta(x)-i\epsilon}{\mu^2}\right]
+O(\epsilon).
$$

The pole term does not depend on $x$, so integrating over $x\in[0,1]$ gives

$$
B_{\rm pole}
=
\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}.
$$

All dependence on $P^2$ and the masses is in the finite logarithmic term.

</details>

### Exercise 3: Imaginary part above threshold

For equal masses, show that

$$
\operatorname{Im}B(s;m^2,m^2)
=
\frac{1}{16\pi}\sqrt{1-\frac{4m^2}{s}}\,\theta(s-4m^2).
$$

<details>
<summary><strong>Solution</strong></summary>

The logarithm develops an imaginary part where

$$
m^2-x(1-x)s<0.
$$

The two roots of $m^2-x(1-x)s=0$ are

$$
x_\pm=\frac12\left(1\pm\sqrt{1-\frac{4m^2}{s}}\right),
$$

which exist only for $s>4m^2$. On the interval $x_-<x<x_+$,

$$
\ln(-|a|-i\epsilon)=\ln|a|-i\pi.
$$

Since $B$ contains minus the logarithm, the imaginary part is

$$
\operatorname{Im}B
=\frac{1}{16\pi^2}\pi(x_+-x_-)
=\frac{1}{16\pi}\sqrt{1-\frac{4m^2}{s}}.
$$

</details>

### Exercise 4: Divergence of the one-loop φ⁴ amplitude

Using the three-channel result for identical scalar $2\to2$ scattering, show that the divergent part of the one-loop amplitude is

$$
\mathcal M_{\rm div}^{(1)}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

Each channel contributes

$$
\frac{\lambda^2}{2}B(P^2;m^2,m^2).
$$

The pole part of each bubble is

$$
B_{\rm pole}=\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}.
$$

There are three channels, $s$, $t$, and $u$, so

$$
\mathcal M_{\rm div}^{(1)}
=3\cdot\frac{\lambda^2}{2}\cdot
\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§14–20, for loop corrections, one-loop scalar diagrams, and perturbation theory to all orders.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 16–20 and appendix B, for one-loop integrals, dimensional regularization, and renormalized perturbation theory.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 15–16, for one-loop scalar integrals and renormalization logic.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 12, for general Feynman rules, loop integrals, and renormalization structure.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for power counting, dimensional regularization, and renormalization in a field-integral framework.
- G. Passarino and M. Veltman, “One-Loop Corrections for $e^+e^-$ Annihilation Into $\mu^+\mu^-$ in the Weinberg Model,” *Nuclear Physics B* **160** (1979), for the classic one-loop reduction notation used in precision calculations.

## Version history

- **2026-06-12:** Initial standardized page.
