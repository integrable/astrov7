---
title: "Feynman Parameters"
description: "A practical derivation of Feynman parameter identities, loop-momentum shifts, and the standard denominator-combining workflow for one-loop integrals."
sidebar:
  label: "Feynman Parameters"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20; Coleman 2019, chs. 15–16; Weinberg 1995, Vol. I, chs. 6 and 12; Schwartz 2014, Appendix B and chs. 16–20; Zinn-Justin 2021, Appendix A10 and ch. 10"
topics:
  - Feynman parameters
  - loop integrals
  - dimensional regularization
  - one-loop integrals
  - analytic structure
canonicalTopics:
  - feynman-parameterization
  - denominator-combining
  - loop-momentum-shift
  - simplex-parameter-integral
  - one-loop-master-integral
researchStatus:
  established:
    - "Feynman parameterization is a standard algebraic method for combining propagator denominators and reducing one-loop integrals to parameter integrals."
  active:
    - "Modern multi-loop applications use Feynman parameters together with Symanzik polynomials, sector decomposition, Landau analysis, differential equations, elliptic integrals, and automated reduction methods."
---

## Summary

**Feynman parameters** turn products of propagator denominators into a single denominator raised to a higher power. The basic two-denominator identity is

$$
\frac{1}{AB}
=
\int_0^1 dx\,\frac{1}{\left[xA+(1-x)B\right]^2},
$$

provided the denominator prescription is carried along consistently. More generally,

$$
\frac{1}{A_1^{\alpha_1}\cdots A_n^{\alpha_n}}
=
\frac{\Gamma(\alpha)}{\Gamma(\alpha_1)\cdots\Gamma(\alpha_n)}
\int_0^1\left[\prod_{j=1}^n dx_j\,x_j^{\alpha_j-1}\right]
\delta\!\left(1-\sum_{j=1}^n x_j\right)
\frac{1}{\left(\sum_{j=1}^n x_jA_j\right)^\alpha},
$$

where

$$
\alpha=\sum_{j=1}^n\alpha_j.
$$

For the scalar bubble with denominators

$$
A=\ell^2-m_1^2+i\epsilon,
\qquad
B=(\ell+P)^2-m_2^2+i\epsilon,
$$

Feynman parameterization gives

$$
xA+(1-x)B
=
\left[\ell+(1-x)P\right]^2-\Delta(x)+i\epsilon,
$$

with

$$
\Delta(x)=xm_1^2+(1-x)m_2^2-x(1-x)P^2.
$$

This is the denominator-combining move behind almost every elementary one-loop calculation.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Feynman parameterization combines two propagator denominators into one denominator, followed by a loop-momentum shift and a standard integral](/figures/perturbative-qft/feynman-parameters.svg)

<figcaption>

Feynman parameters combine denominators, convert products of propagators into a single quadratic form, and expose the standard loop integral. For a bubble, the parameter $x$ interpolates between the two propagators and produces $\Delta(x)=xm_1^2+(1-x)m_2^2-x(1-x)P^2$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/).

You should also be comfortable with Gamma and Beta functions and with the idea of analytic continuation in a complex parameter.

## Core idea

A loop integral is hard because several propagators depend on the same loop momentum in shifted ways:

$$
\frac{1}{\ell^2-m_1^2+i\epsilon}
\frac{1}{(\ell+P)^2-m_2^2+i\epsilon}.
$$

Feynman parameters replace the product by one denominator:

$$
\frac{1}{AB}
\quad\longrightarrow\quad
\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

The linear combination $xA+(1-x)B$ is a quadratic polynomial in $\ell$. Completing the square shifts the loop momentum and produces a rotationally invariant standard integral. The external kinematics and masses are packaged into a parameter-dependent effective mass $\Delta(x)$.

The workflow is

$$
\text{many denominators}
\to
\text{one denominator}
\to
\text{shift loop momentum}
\to
\text{standard integral}
\to
\text{parameter integral}.
$$

That final parameter integral is often where the analytic structure lives: thresholds, branch cuts, endpoint singularities, and logarithms all become visible in the geometry of the $x_j$-simplex.

## Setup and conventions

We use qft.org mostly-minus conventions, with scalar propagator

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

A typical one-loop denominator is

$$
D_j=(\ell+r_j)^2-m_j^2+i\epsilon,
$$

where $\ell$ is the loop momentum and $r_j$ is a fixed combination of external momenta.

The dimensionally regulated loop measure is

$$
\int_\ell
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}.
$$

For most one-loop four-dimensional examples,

$$
d=4-2\epsilon.
$$

The $i\epsilon$ prescription must remain attached to the combined denominator. Dropping it too early hides branch cuts and can produce the wrong imaginary part after analytic continuation.

## The two-denominator identity

The basic identity is

$$
\frac{1}{AB}
=
\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

To verify it, set

$$
C(x)=xA+(1-x)B=B+x(A-B).
$$

Then

$$
\frac{d}{dx}\left(\frac{1}{C(x)}\right)
=
-\frac{A-B}{C(x)^2}.
$$

Therefore

$$
\int_0^1 dx\,\frac{1}{C(x)^2}
=
\frac{1}{A-B}\left[\frac{1}{B}-\frac{1}{A}\right]
=
\frac{1}{AB}.
$$

This derivation assumes $A\ne B$; the equal case follows by continuity.

A useful generalization is

$$
\frac{1}{A^aB^b}
=
\frac{\Gamma(a+b)}{\Gamma(a)\Gamma(b)}
\int_0^1 dx\,
\frac{x^{a-1}(1-x)^{b-1}}{[xA+(1-x)B]^{a+b}}.
$$

For $a=b=1$ this reduces to the basic identity.

## Bubble integral: completing the square

Consider the scalar bubble denominators

$$
A=\ell^2-m_1^2+i\epsilon,
\qquad
B=(\ell+P)^2-m_2^2+i\epsilon.
$$

The Feynman-parameter combination is

$$
\begin{aligned}
xA+(1-x)B
&=x(\ell^2-m_1^2)+(1-x)[(\ell+P)^2-m_2^2]+i\epsilon\\
&=\ell^2+2(1-x)\ell\cdot P+(1-x)P^2
-xm_1^2-(1-x)m_2^2+i\epsilon.
\end{aligned}
$$

Now define

$$
k=\ell+(1-x)P.
$$

Then

$$
\ell^2+2(1-x)\ell\cdot P
=
k^2-(1-x)^2P^2.
$$

Substituting gives

$$
xA+(1-x)B
=
k^2+x(1-x)P^2-xm_1^2-(1-x)m_2^2+i\epsilon.
$$

Therefore

$$
xA+(1-x)B=k^2-\Delta(x)+i\epsilon,
$$

where

$$
\Delta(x)=xm_1^2+(1-x)m_2^2-x(1-x)P^2.
$$

The original bubble integral becomes

$$
\int_\ell\frac{1}{AB}
=
\int_0^1 dx\int_k
\frac{1}{[k^2-\Delta(x)+i\epsilon]^2},
$$

where the shift from $\ell$ to $k$ is allowed in dimensional regularization.

## Standard dimensionally regulated integral

The basic Lorentzian integral is

$$
\mu^{2\epsilon}\int\frac{d^dk}{(2\pi)^d}
\frac{1}{(k^2-\Delta+i\epsilon)^\nu}
=
\frac{i(-1)^\nu}{(4\pi)^{d/2}}
\frac{\Gamma(\nu-d/2)}{\Gamma(\nu)}
\mu^{2\epsilon}(\Delta-i\epsilon)^{d/2-\nu}.
$$

For the bubble denominator, $\nu=2$ and $d=4-2\epsilon$. Thus

$$
\mu^{2\epsilon}\int\frac{d^dk}{(2\pi)^d}
\frac{1}{(k^2-\Delta+i\epsilon)^2}
=
\frac{i}{(4\pi)^{2-\epsilon}}
\Gamma(\epsilon)
\mu^{2\epsilon}(\Delta-i\epsilon)^{-\epsilon}.
$$

Expanding around $\epsilon=0$ gives

$$
\frac{i}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{\Delta-i\epsilon}{\mu^2}
\right]
+O(\epsilon).
$$

If the original integral contains the two scalar propagator numerators $i^2=-1$, the final bubble convention may differ by an overall factor of $-i$. Always check whether the page defines the integral with or without the propagator factors of $i$.

## The general n-denominator formula

For $n$ denominators, the Feynman-parameter formula integrates over an $(n-1)$-simplex:

$$
x_j\ge0,
\qquad
\sum_{j=1}^n x_j=1.
$$

The general identity is

$$
\frac{1}{A_1^{\alpha_1}\cdots A_n^{\alpha_n}}
=
\frac{\Gamma(\alpha)}{\prod_{j=1}^n\Gamma(\alpha_j)}
\int_0^1\left[\prod_{j=1}^n dx_j\,x_j^{\alpha_j-1}\right]
\delta\!\left(1-\sum_{j=1}^n x_j\right)
\frac{1}{\left(\sum_{j=1}^n x_jA_j\right)^\alpha},
$$

with

$$
\alpha=\sum_{j=1}^n\alpha_j.
$$

For simple propagators, $\alpha_j=1$, this becomes

$$
\frac{1}{A_1A_2\cdots A_n}
=
(n-1)!
\int_0^1\left[\prod_{j=1}^n dx_j\right]
\delta\!\left(1-\sum_{j=1}^n x_j\right)
\frac{1}{\left(\sum_{j=1}^n x_jA_j\right)^n}.
$$

For $n=3$,

$$
\frac{1}{ABC}
=
2\int_0^1 dx\,dy\,dz\,\delta(1-x-y-z)
\frac{1}{(xA+yB+zC)^3}.
$$

This is the starting point for triangle integrals.

## One-loop n-point denominators

Let

$$
D_j=(\ell+r_j)^2-m_j^2+i\epsilon.
$$

After Feynman parameterization,

$$
\sum_{j=1}^n x_jD_j
=
\ell^2+2\ell\cdot R+
\sum_{j=1}^n x_j(r_j^2-m_j^2)+i\epsilon,
$$

where

$$
R=\sum_{j=1}^n x_jr_j.
$$

Completing the square with

$$
k=\ell+R
$$

gives

$$
\sum_{j=1}^n x_jD_j
=
k^2-\Delta(x)+i\epsilon,
$$

where

$$
\Delta(x)
=
\sum_{j=1}^n x_jm_j^2
-
\sum_{i<j}x_ix_j(r_i-r_j)^2.
$$

This compact expression is worth memorizing. It is the one-loop version of a much more general graphical-polynomial structure at higher loops.

## Numerators and tensor integrals

Feynman parameters also help with numerator factors. Suppose the numerator contains $\ell^\mu$. After the shift

$$
k=\ell+R,
$$

we have

$$
\ell^\mu=k^\mu-R^\mu.
$$

The odd term integrates to zero in a Lorentz-invariant regulator:

$$
\int_k\frac{k^\mu}{(k^2-\Delta+i\epsilon)^\nu}=0.
$$

Thus the numerator becomes a polynomial in external momenta through $R^\mu$.

For two powers,

$$
\ell^\mu\ell^\nu
=
(k^\mu-R^\mu)(k^\nu-R^\nu).
$$

The mixed terms vanish after integration, and the symmetric tensor integral reduces to

$$
\int_k\frac{k^\mu k^\nu}{(k^2-\Delta+i\epsilon)^\nu}
=
\frac{\eta^{\mu\nu}}{d}
\int_k\frac{k^2}{(k^2-\Delta+i\epsilon)^\nu},
$$

with the usual caveat that Lorentzian tensor integrals are defined by the regulated prescription. This is the elementary ancestor of tensor-integral reduction.

## Analytic structure from parameter space

The Feynman-parameter expression makes thresholds geometric. For the bubble, the logarithm contains

$$
\ln[\Delta(x)-i\epsilon].
$$

When $\Delta(x)>0$ for all $x\in[0,1]$, the integral is real below threshold. When $\Delta(x)$ vanishes inside the integration region, the logarithm crosses a branch cut and the integral develops an imaginary part.

For equal internal masses,

$$
\Delta(x)=m^2-x(1-x)P^2.
$$

The maximum of $x(1-x)$ on $[0,1]$ is $1/4$. Thus $\Delta(x)$ can vanish inside the interval when

$$
P^2\ge4m^2.
$$

That is the two-particle production threshold. The humble parameter $x$ just quietly revealed the cut structure. Respect.

## Euclidean version

After Wick rotation, the standard Euclidean integral is

$$
\int\frac{d^dk_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^\nu}
=
\frac{1}{(4\pi)^{d/2}}
\frac{\Gamma(\nu-d/2)}{\Gamma(\nu)}
\Delta^{d/2-\nu},
$$

for suitable $\Delta$ and analytic continuation elsewhere. This formula is often easier to remember than the Lorentzian one. The price is that one must separately track the Wick rotation, factors of $i$, and the $i\epsilon$ prescription.

For practical perturbative QFT, the safe rule is:

$$
\text{combine denominators before Wick rotation, and keep the }i\epsilon\text{ until the analytic structure is clear.}
$$

## Relation to Schwinger parameters

Feynman parameters are closely related to Schwinger parameters. The identity

$$
\frac{1}{A^\alpha}
=
\frac{1}{\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1}e^{-sA}
$$

combines denominators by introducing one positive parameter per propagator. Rescaling the Schwinger parameters by their total size separates an overall scale from simplex coordinates. Those simplex coordinates are the Feynman parameters.

This relation becomes especially useful at multi-loop order, where graph polynomials and sector decomposition are naturally written in Schwinger or Feynman parameters.

## Common pitfalls

**Dropping the iε.** The $i\epsilon$ is not decorative. It determines how logarithms and powers are analytically continued.

**Using the wrong x convention.** Some sources write $xA+(1-x)B$; others write $(1-x)A+xB$. Both are fine, but $\Delta(x)$ changes by $x\leftrightarrow1-x$.

**Shifting divergent integrals without a regulator.** The shift $\ell\mapsto k$ is safe in dimensional regularization. With a hard cutoff, a shift can change the integration domain and produce extra terms unless the regulator is translation invariant or the shift is handled carefully.

**Forgetting numerator shifts.** After completing the square, $\ell^\mu$ is not $k^\mu$; it is $k^\mu-R^\mu$.

**Confusing UV and threshold behavior.** UV divergences come from large loop momentum and appear through Gamma-function poles. Thresholds arise when $\Delta(x)$ vanishes inside parameter space.

**Blindly Euclideanizing.** Euclidean formulas are clean, but scattering amplitudes live on Lorentzian sheets. Analytic continuation is part of the calculation.

## Relations to other pages

- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) uses the two-denominator identity in its most important first example.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) supplies the standard $d$-dimensional integrals used after completing the square.
- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) uses Feynman parameters for triangle and bubble vertex corrections.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how local divergent pieces of parameter integrals are subtracted.
- Later pages in this chapter develop Schwinger parameters, tensor integral reduction, and Landau singularities from the parameter-space viewpoint.

## Research status

- **Established:** Feynman parameter identities and one-loop denominator combination are standard textbook tools.
- **Convention-dependent:** Overall factors of $i$, signs of $\Delta$, and powers of $4\pi$ depend on whether the integral is defined before or after including propagator numerators and Wick rotation.
- **Active:** Multi-loop parameter integrals remain a major research arena, especially for sector decomposition, elliptic and Calabi–Yau structures, symbol alphabets, differential equations, and numerical integration near physical thresholds.
- **Not a regulator by itself:** Feynman parameterization combines denominators. It does not by itself make divergent integrals finite.

## Exercises

### Exercise 1: Prove the basic identity

Prove that

$$
\frac{1}{AB}
=
\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Set

$$
C(x)=xA+(1-x)B.
$$

Then

$$
\frac{d}{dx}\frac{1}{C(x)}
=
-\frac{A-B}{C(x)^2}.
$$

Therefore

$$
\int_0^1 dx\,\frac{1}{C(x)^2}
=
-\frac{1}{A-B}\left[\frac{1}{C(x)}\right]_{0}^{1}
=
-\frac{1}{A-B}\left(\frac{1}{A}-\frac{1}{B}\right)
=
\frac{1}{AB}.
$$

</details>

### Exercise 2: Derive the bubble Δ function

For

$$
A=\ell^2-m_1^2+i\epsilon,
\qquad
B=(\ell+P)^2-m_2^2+i\epsilon,
$$

show that

$$
xA+(1-x)B=[\ell+(1-x)P]^2-\Delta(x)+i\epsilon,
$$

with

$$
\Delta(x)=xm_1^2+(1-x)m_2^2-x(1-x)P^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the left-hand side:

$$
\begin{aligned}
xA+(1-x)B
&=x(\ell^2-m_1^2)+(1-x)[\ell^2+2\ell\cdot P+P^2-m_2^2]+i\epsilon\\
&=\ell^2+2(1-x)\ell\cdot P+(1-x)P^2
-xm_1^2-(1-x)m_2^2+i\epsilon.
\end{aligned}
$$

Complete the square:

$$
[\ell+(1-x)P]^2
=
\ell^2+2(1-x)\ell\cdot P+(1-x)^2P^2.
$$

Thus

$$
\ell^2+2(1-x)\ell\cdot P+(1-x)P^2
=
[\ell+(1-x)P]^2+x(1-x)P^2.
$$

Therefore

$$
xA+(1-x)B
=
[\ell+(1-x)P]^2
-
\left[xm_1^2+(1-x)m_2^2-x(1-x)P^2\right]+i\epsilon.
$$

</details>

### Exercise 3: Equal-mass threshold

For equal internal masses, show that

$$
\Delta(x)=m^2-x(1-x)P^2
$$

can vanish for some $x\in[0,1]$ only if $P^2\ge4m^2$.

<details>
<summary><strong>Solution</strong></summary>

On the interval $0\le x\le1$, the function $x(1-x)$ has maximum $1/4$ at $x=1/2$. Therefore

$$
x(1-x)P^2\le \frac{P^2}{4}
$$

for positive $P^2$. A zero of

$$
\Delta(x)=m^2-x(1-x)P^2
$$

requires

$$
m^2=x(1-x)P^2\le \frac{P^2}{4}.
$$

Hence

$$
P^2\ge4m^2.
$$

This is the two-particle threshold.

</details>

### Exercise 4: Three-denominator simplex

Use the general formula to write $1/(ABC)$ as a two-dimensional parameter integral over $x,y,z\ge0$ with $x+y+z=1$.

<details>
<summary><strong>Solution</strong></summary>

For three denominators with powers $\alpha_1=\alpha_2=\alpha_3=1$, we have

$$
\alpha=3,
\qquad
\frac{\Gamma(3)}{\Gamma(1)^3}=2.
$$

Therefore

$$
\frac{1}{ABC}
=
2\int_0^1 dx\,dy\,dz\,
\delta(1-x-y-z)
\frac{1}{(xA+yB+zC)^3}.
$$

Equivalently, integrate out $z=1-x-y$ over the triangle $x\ge0$, $y\ge0$, $x+y\le1$.

</details>

### Exercise 5: A numerator shift

Let

$$
R=\sum_jx_jr_j,
\qquad
k=\ell+R.
$$

If a numerator contains $\ell^\mu$, show that after integration it contributes as $-R^\mu$ times the scalar integral, assuming the denominator depends only on $k^2$.

<details>
<summary><strong>Solution</strong></summary>

Since

$$
k=\ell+R,
$$

we have

$$
\ell^\mu=k^\mu-R^\mu.
$$

The integral of the odd vector term vanishes in a Lorentz-invariant regulator:

$$
\int_k\frac{k^\mu}{(k^2-\Delta+i\epsilon)^\nu}=0.
$$

Therefore

$$
\int_k\frac{\ell^\mu}{(k^2-\Delta+i\epsilon)^\nu}
=
-R^\mu
\int_k\frac{1}{(k^2-\Delta+i\epsilon)^\nu}.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§14–20, for one-loop scalar integrals and their use in self-energy and vertex corrections.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 15–16, for one-loop integrals and Feynman parameterization in renormalization examples.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 12, for momentum-space Feynman rules and dimensional regularization in perturbation theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, Appendix B and chs. 16–20, for Feynman parameters, regularization, and loop examples.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, Appendix A10 and ch. 10, for Feynman parameterization and dimensional regularization.
- A. Zee, *Quantum Field Theory in a Nutshell*, Appendix D, for a compact integral-technology reference.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume. Figure generated from compact TikZ source in the qft.org black/gray style.
