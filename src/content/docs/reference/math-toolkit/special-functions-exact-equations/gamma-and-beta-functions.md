---
title: "Gamma and Beta Functions"
description: "Explains the gamma and beta functions for QFT: analytic continuation of factorials, Mellin and Schwinger parameters, beta integrals, Feynman parameters, dimensional regularization, pole expansions, and CFT star-triangle-type integrals."
sidebar:
  label: "Gamma and Beta Functions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard references on gamma and beta functions, Mellin transforms, dimensional regularization, Feynman parameters, CFT integrals, and special functions, including Whittaker–Watson, Abramowitz–Stegun, NIST DLMF, Olver, Temme, Bender–Orszag, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, Di Francesco–Mathieu–Sénéchal, and standard perturbative QFT references."
topics:
  - gamma function
  - beta function
  - Mellin transform
  - Schwinger parameters
  - Feynman parameters
  - dimensional regularization
  - Euler beta function
  - pole expansion
  - digamma function
  - star-triangle integral
canonicalTopics:
  - gamma-function
  - beta-function
  - mellin-transform
  - schwinger-parameter
  - feynman-parameter
  - dimensional-regularization
  - euler-beta-function
  - pole-expansion
  - digamma-function
  - star-triangle-integral
researchStatus:
  established:
    - "Gamma and beta functions are standard analytic continuations of factorials and simplex integrals, and they control many QFT calculations through Schwinger parameters, Feynman parameters, dimensional regularization, and conformal integrals."
    - "Their poles, residues, reflection formulae, Stirling expansions, and logarithmic derivatives are classical and convention-stable."
  active:
    - "Modern loop-integral, bootstrap, and nonperturbative calculations use gamma-function technology inside Mellin–Barnes representations, conformal integrals, asymptotic expansions, dimensional recurrence relations, and exact determinant formulae."
---

## Summary

The gamma function is the analytic continuation of the factorial:

$$
\Gamma(n+1)=n!,
\qquad n=0,1,2,\dots.
$$

For $\operatorname{Re}z>0$ it is defined by the convergent integral

$$
\Gamma(z)=\int_0^\infty dt\,t^{z-1}e^{-t}.
$$

The beta function is the simplex integral

$$
B(x,y)=\int_0^1 dt\,t^{x-1}(1-t)^{y-1}
=\frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)},
\qquad \operatorname{Re}x,\operatorname{Re}y>0.
$$

These two functions are everywhere in QFT because they are the algebra of powers. They turn denominators into Schwinger parameters, combine propagators with Feynman parameters, analytically continue dimension-dependent integrals, and expose poles in dimensional regularization.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing the gamma function from Mellin and Schwinger parameters, the beta function from simplex integrals, and their flow into dimensional regularization, Feynman parameters, and CFT integrals.](/figures/math-toolkit/gamma-beta-functions-flow.svg)

<figcaption>

Gamma and beta functions are the backbone of power-law integrals. The gamma function is a Mellin transform and Schwinger-parameter normalization; the beta function is a one-simplex integral and the two-denominator Feynman-parameter identity. In QFT their poles and ratios encode UV divergences, IR divergences, normalization constants, and conformal integral coefficients.

</figcaption>
</figure>

A warning about names: the Euler beta function $B(x,y)$ is unrelated to the renormalization-group beta function $\beta(g)=\mu\,dg/d\mu$, except that both show up in the same calculations and gleefully cause notation mayhem.

## Prerequisites

You should know [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), and [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/).

This page uses Euclidean momentum integrals for the cleanest formulas. Lorentzian formulas follow by Wick rotation and the inherited $i0$ prescription.

## The gamma function

The gamma function satisfies the recursion relation

$$
\Gamma(z+1)=z\Gamma(z).
$$

For positive integers, this gives

$$
\Gamma(n+1)=n\Gamma(n)=n!.
$$

The integral definition is valid only for $\operatorname{Re}z>0$, but the recursion extends $\Gamma(z)$ meromorphically to the whole complex plane. It has simple poles at

$$
z=0,-1,-2,\dots,
$$

with residues

$$
\operatorname{Res}_{z=-n}\Gamma(z)=\frac{(-1)^n}{n!},
\qquad n=0,1,2,\dots.
$$

There are no zeros. This matters because ratios of gamma functions often have cancellations of poles but never cancellations by gamma zeros.

Some indispensable identities are

$$
\Gamma(z)\Gamma(1-z)=\frac{\pi}{\sin \pi z},
$$

and

$$
\Gamma\!\left(z+\frac12\right)\Gamma(z)
=2^{1-2z}\sqrt\pi\,\Gamma(2z).
$$

The first is Euler’s reflection formula. The second is the duplication formula. Together they are enough to tame many normalization fights involving $\sqrt\pi$, half-integers, and spherical integrals.

For half-integers,

$$
\Gamma\!\left(\frac12\right)=\sqrt\pi,
$$

and

$$
\Gamma\!\left(n+\frac12\right)
=\frac{(2n)!}{4^n n!}\sqrt\pi
=\frac{(2n-1)!!}{2^n}\sqrt\pi.
$$

## Mellin and Schwinger representations

The defining gamma integral immediately implies, for $\operatorname{Re}A>0$ and $\operatorname{Re}\alpha>0$,

$$
\int_0^\infty ds\,s^{\alpha-1}e^{-sA}
=\frac{\Gamma(\alpha)}{A^\alpha}.
$$

Equivalently,

$$
\frac{1}{A^\alpha}
=\frac{1}{\Gamma(\alpha)}\int_0^\infty ds\,s^{\alpha-1}e^{-sA}.
$$

This is the Schwinger-parameter representation. It is one of the main reasons the gamma function belongs in a QFT toolkit. It turns denominators into exponentials, and exponentials combine beautifully with Gaussian momentum integrals.

For a positive operator $L$, the formal identity

$$
L^{-\alpha}=\frac{1}{\Gamma(\alpha)}\int_0^\infty ds\,s^{\alpha-1}e^{-sL}
$$

connects resolvents, heat kernels, determinants, and zeta functions. In Lorentzian QFT, $A$ is replaced by the appropriate $A-i0$ or $A+i0$ boundary value before the parameter integral is interpreted.

## The beta function

The Euler beta function is

$$
B(x,y)=\int_0^1 dt\,t^{x-1}(1-t)^{y-1}.
$$

It obeys

$$
B(x,y)=B(y,x),
$$

and

$$
B(x,y)=\frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}.
$$

A useful special case is

$$
B(x,1-x)=\frac{\pi}{\sin\pi x},
$$

which follows from the reflection formula.

The beta function is a one-dimensional simplex integral. Its higher-dimensional cousin is the Dirichlet integral:

$$
\int_{x_i\ge0}\left(\prod_{i=1}^n dx_i\,x_i^{\alpha_i-1}\right)
\delta\!\left(1-\sum_{i=1}^n x_i\right)
=\frac{\prod_{i=1}^n\Gamma(\alpha_i)}{\Gamma\!\left(\sum_{i=1}^n\alpha_i\right)},
$$

for $\operatorname{Re}\alpha_i>0$. This is the mathematical heart of Feynman parameters.

## Feynman parameters

For $\operatorname{Re}\alpha,\operatorname{Re}\beta>0$, one has

$$
\frac{1}{A^\alpha B^\beta}
=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}
\int_0^1 dx\,
\frac{x^{\alpha-1}(1-x)^{\beta-1}}
{\big[xA+(1-x)B\big]^{\alpha+\beta}}.
$$

This identity is usually the first place the beta function becomes unavoidable in perturbative QFT.

For $n$ denominators,

$$
\prod_{i=1}^n\frac{1}{A_i^{\alpha_i}}
=\frac{\Gamma(\alpha)}{\prod_{i=1}^n\Gamma(\alpha_i)}
\int_{x_i\ge0}\left(\prod_{i=1}^n dx_i\,x_i^{\alpha_i-1}\right)
\frac{\delta\!\left(1-\sum_i x_i\right)}
{\left(\sum_i x_i A_i\right)^\alpha},
$$

where

$$
\alpha=\sum_{i=1}^n\alpha_i.
$$

In Lorentzian loop integrals, the $i0$ prescriptions are part of $A_i$. Combining denominators combines those prescriptions as well. Dropping them is one of the fastest ways to get the wrong branch cut.

## Dimensional regularization integral

The basic Euclidean momentum integral is

$$
\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2+\Delta)^\alpha}
=\frac{1}{(4\pi)^{d/2}}
\frac{\Gamma\!\left(\alpha-\frac d2\right)}{\Gamma(\alpha)}
\Delta^{\frac d2-\alpha},
$$

for $\Delta>0$ and initially $\operatorname{Re}\alpha>d/2$. Dimensional regularization defines the answer elsewhere by analytic continuation.

A quick derivation uses Schwinger parameters:

$$
\frac{1}{(\ell^2+\Delta)^\alpha}
=\frac{1}{\Gamma(\alpha)}\int_0^\infty ds\,s^{\alpha-1}e^{-s(\ell^2+\Delta)}.
$$

Then

$$
\int\frac{d^d\ell}{(2\pi)^d}e^{-s\ell^2}
=\frac{1}{(4\pi s)^{d/2}}.
$$

The remaining integral is

$$
\frac{1}{(4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1-d/2}e^{-s\Delta}
=\frac{1}{(4\pi)^{d/2}}
\frac{\Gamma\!\left(\alpha-\frac d2\right)}{\Gamma(\alpha)}
\Delta^{\frac d2-\alpha}.
$$

This formula is the origin of countless $\Gamma(\epsilon)$ poles.

For example, in $d=4-2\epsilon$,

$$
\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2+\Delta)^2}
=\frac{1}{(4\pi)^{2-\epsilon}}\Gamma(\epsilon)\Delta^{-\epsilon}.
$$

The pole is visible because

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon).
$$

## Expansions near small epsilon

The most common small-$\epsilon$ expansions are

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E
+\left(\frac{\gamma_E^2}{2}+\frac{\pi^2}{12}\right)\epsilon
+O(\epsilon^2),
$$

$$
\Gamma(1+\epsilon)=1-\gamma_E\epsilon
+\left(\frac{\gamma_E^2}{2}+\frac{\pi^2}{12}\right)\epsilon^2
+O(\epsilon^3),
$$

and

$$
\Gamma(1-\epsilon)=1+\gamma_E\epsilon
+\left(\frac{\gamma_E^2}{2}+\frac{\pi^2}{12}\right)\epsilon^2
+O(\epsilon^3).
$$

Also,

$$
\Delta^{-\epsilon}=1-\epsilon\log\Delta+O(\epsilon^2),
$$

and

$$
(4\pi)^\epsilon=1+\epsilon\log(4\pi)+O(\epsilon^2).
$$

Thus gamma-function poles rarely appear alone. They travel with logarithms, $4\pi$, and Euler’s constant $\gamma_E$. The modified minimal subtraction convention packages some of these into the usual $\overline{\mathrm{MS}}$ normalization.

## Digamma and logarithmic derivatives

The digamma function is

$$
\psi(z)=\frac{d}{dz}\log\Gamma(z)=\frac{\Gamma'(z)}{\Gamma(z)}.
$$

It appears whenever a gamma-function ratio is expanded in a parameter. The recursion relation gives

$$
\psi(z+1)=\psi(z)+\frac{1}{z}.
$$

At positive integers,

$$
\psi(n+1)=H_n-\gamma_E,
$$

where

$$
H_n=\sum_{k=1}^n\frac{1}{k}
$$

is the harmonic number. Harmonic numbers in loop integrals and conformal-block expansions are often digamma functions in integer clothing.

For small $\epsilon$,

$$
\log\Gamma(z+\epsilon)
=\log\Gamma(z)+\epsilon\psi(z)+O(\epsilon^2).
$$

This is usually the cleanest way to expand products and ratios.

## Sphere volumes and angular integrals

The gamma function controls sphere volumes:

$$
\operatorname{Vol}(S^{d-1})=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

This follows from comparing the $d$-dimensional Gaussian integral

$$
\int_{\mathbb R^d}d^d x\,e^{-x^2}=\pi^{d/2}
$$

with polar coordinates,

$$
\int_{\mathbb R^d}d^d x\,e^{-x^2}
=\operatorname{Vol}(S^{d-1})\int_0^\infty dr\,r^{d-1}e^{-r^2}.
$$

Since

$$
\int_0^\infty dr\,r^{d-1}e^{-r^2}
=\frac12\Gamma(d/2),
$$

one obtains the stated volume.

This formula is why gamma functions appear before any loop integral has even become complicated: dimensional regularization analytically continues the angular volume itself.

## CFT and conformal integrals

A standard conformal integral in $d$ Euclidean dimensions is

$$
\int d^d x\,\frac{1}{(x^2)^\alpha((x-y)^2)^\beta}
=\pi^{d/2}
\frac{\Gamma\!\left(\frac d2-\alpha\right)
\Gamma\!\left(\frac d2-\beta\right)
\Gamma\!\left(\alpha+\beta-\frac d2\right)}
{\Gamma(\alpha)\Gamma(\beta)\Gamma(d-\alpha-\beta)}
\frac{1}{(y^2)^{\alpha+\beta-d/2}},
$$

where the formula is first derived in its convergence domain and then analytically continued. It is just Feynman parameters plus the dimensional integral, rewritten in position space.

The star-triangle identity is another central example. If

$$
\alpha_1+\alpha_2+\alpha_3=d,
$$

then

$$
\int d^d x_0\,
\prod_{i=1}^3\frac{1}{(x_{i0}^2)^{\alpha_i}}
=\pi^{d/2}
\prod_{i=1}^3\frac{\Gamma\!\left(\frac d2-\alpha_i\right)}{\Gamma(\alpha_i)}
\prod_{i=1}^3\frac{1}{(x_{jk}^2)^{\frac d2-\alpha_i}},
$$

where in the last product $(i,j,k)$ cycles through $(1,2,3)$, so the factor associated with $\alpha_1$ is $(x_{23}^2)^{-(d/2-\alpha_1)}$, and similarly for the others.

This identity is a gamma-function statement with conformal covariance doing the bookkeeping.

## Poles and what they mean

A gamma-function pole in a regulated expression can signal several different things.

A UV divergence often appears as

$$
\Gamma\!\left(\alpha-\frac d2\right)
$$

when the large-momentum region fails to converge.

An IR divergence can produce a similar pole after masses or external scales are sent to zero. Dimensional regularization does not label the pole for you. The integral, scales, and region analysis do.

A physical threshold can appear through gamma functions only after analytic continuation in kinematic invariants. In that case the discontinuity and branch prescription matter more than the pole expansion alone.

A normalization pole may cancel against another factor. In CFT and representation theory, gamma-function ratios can have apparent poles that cancel after imposing selection rules or summing contributions.

So the rule is: do not interpret a gamma pole until you know which variable is being analytically continued and which physical region created the nonconvergence.

## Common pitfalls

**Forgetting the convergence domain.** The integral definition of $\Gamma(z)$ requires $\operatorname{Re}z>0$. A formula outside its convergence domain is an analytically continued identity, not an ordinary convergent integral.

**Dropping $i0$ in Feynman parameters.** In Lorentzian integrals, the branch of $[xA+(1-x)B]^{-\alpha-\beta}$ is fixed by the inherited prescription.

**Confusing Euler beta with RG beta.** Write $B(x,y)$ for Euler’s beta function whenever possible. Save $\beta(g)$ for renormalization-group flow.

**Missing angular factors.** The difference between $\pi^{d/2}$ and $(4\pi)^{d/2}$ is usually a Fourier-transform or $(2\pi)^d$ measure issue, not a profound mystery.

**Expanding gamma ratios term by term in a bad form.** Use logarithms and digamma functions. Ratios are often safer than products.

**Treating every $1/\epsilon$ as UV.** In dimensional regularization, UV and IR divergences can look identical algebraically. The momentum region decides.

## Exercises

### Exercise 1: Recursion relation

Show directly from the integral definition that

$$
\Gamma(z+1)=z\Gamma(z)
$$

for $\operatorname{Re}z>0$.

<details><summary><strong>Solution</strong></summary>

Use integration by parts:

$$
\Gamma(z+1)=\int_0^\infty dt\,t^z e^{-t}.
$$

Let $u=t^z$ and $dv=e^{-t}dt$. Then $du=zt^{z-1}dt$ and $v=-e^{-t}$. The boundary term

$$
[-t^z e^{-t}]_0^\infty
$$

vanishes for $\operatorname{Re}z>0$. Therefore

$$
\Gamma(z+1)=z\int_0^\infty dt\,t^{z-1}e^{-t}=z\Gamma(z).
$$

</details>

### Exercise 2: Beta-gamma identity

Derive

$$
B(x,y)=\frac{\Gamma(x)\Gamma(y)}{\Gamma(x+y)}.
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
\Gamma(x)\Gamma(y)
=\int_0^\infty du\int_0^\infty dv\,u^{x-1}v^{y-1}e^{-u-v}.
$$

Set

$$
s=u+v,
\qquad t=\frac{u}{u+v}.
$$

Then

$$
u=st,
\qquad v=s(1-t),
\qquad du\,dv=s\,ds\,dt.
$$

Thus

$$
\Gamma(x)\Gamma(y)
=\int_0^\infty ds\,s^{x+y-1}e^{-s}
\int_0^1 dt\,t^{x-1}(1-t)^{y-1}.
$$

The first integral is $\Gamma(x+y)$ and the second is $B(x,y)$, so

$$
\Gamma(x)\Gamma(y)=\Gamma(x+y)B(x,y).
$$

</details>

### Exercise 3: Feynman parameter for two denominators

Use the beta function to show that

$$
\frac{1}{AB}
=\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

<details><summary><strong>Solution</strong></summary>

Set $\alpha=\beta=1$ in the general Feynman-parameter identity:

$$
\frac{1}{A^\alpha B^\beta}
=\frac{\Gamma(\alpha+\beta)}{\Gamma(\alpha)\Gamma(\beta)}
\int_0^1 dx\,
\frac{x^{\alpha-1}(1-x)^{\beta-1}}
{[xA+(1-x)B]^{\alpha+\beta}}.
$$

Since $\Gamma(2)=1$ and $\Gamma(1)=1$, this gives

$$
\frac{1}{AB}
=\int_0^1 dx\,\frac{1}{[xA+(1-x)B]^2}.
$$

One may also check directly by doing the integral:

$$
\int_0^1 dx\,\frac{1}{[B+x(A-B)]^2}
=\frac{1}{A-B}\left(\frac{1}{B}-\frac{1}{A}\right)
=\frac{1}{AB}.
$$

</details>

### Exercise 4: Basic dimensional integral

Derive

$$
\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2+\Delta)^\alpha}
=\frac{1}{(4\pi)^{d/2}}
\frac{\Gamma\!\left(\alpha-\frac d2\right)}{\Gamma(\alpha)}
\Delta^{\frac d2-\alpha}.
$$

<details><summary><strong>Solution</strong></summary>

Insert the Schwinger representation:

$$
\frac{1}{(\ell^2+\Delta)^\alpha}
=\frac{1}{\Gamma(\alpha)}\int_0^\infty ds\,s^{\alpha-1}e^{-s(\ell^2+\Delta)}.
$$

Then

$$
\int\frac{d^d\ell}{(2\pi)^d}e^{-s\ell^2}
=\frac{1}{(4\pi s)^{d/2}}.
$$

Therefore

$$
I=\frac{1}{(4\pi)^{d/2}\Gamma(\alpha)}
\int_0^\infty ds\,s^{\alpha-1-d/2}e^{-s\Delta}.
$$

Using

$$
\int_0^\infty ds\,s^{\rho-1}e^{-s\Delta}=\Gamma(\rho)\Delta^{-\rho},
$$

with $\rho=\alpha-d/2$, gives the result.

</details>

### Exercise 5: Small epsilon bubble pole

For $d=4-2\epsilon$, expand

$$
I(\Delta)=\frac{1}{(4\pi)^{d/2}}\Gamma\!\left(2-\frac d2\right)\Delta^{d/2-2}
$$

to order $\epsilon^0$.

<details><summary><strong>Solution</strong></summary>

Since $d/2=2-\epsilon$,

$$
I(\Delta)=\frac{1}{(4\pi)^{2-\epsilon}}\Gamma(\epsilon)\Delta^{-\epsilon}.
$$

Use

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon),
$$

$$
(4\pi)^\epsilon=1+\epsilon\log(4\pi)+O(\epsilon^2),
$$

and

$$
\Delta^{-\epsilon}=1-\epsilon\log\Delta+O(\epsilon^2).
$$

Thus

$$
I(\Delta)=\frac{1}{(4\pi)^2}
\left[\frac{1}{\epsilon}+\log(4\pi)-\gamma_E-\log\Delta+O(\epsilon)\right].
$$

In a dimensionful calculation, $\Delta$ is compared to the renormalization scale; this page suppresses that scale to keep the algebra visible.

</details>

## References

- NIST Digital Library of Mathematical Functions, chapters on gamma, beta, and related functions. Best modern reference for definitions, branches, identities, and numerical details.
- M. Abramowitz and I. Stegun, *Handbook of Mathematical Functions*. Classic tables and identities.
- E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*. Classic treatment of gamma and beta functions in complex analysis.
- F. W. J. Olver, *Asymptotics and Special Functions*. Standard source for asymptotic expansions and uniform methods.
- N. M. Temme, *Special Functions: An Introduction to the Classical Functions of Mathematical Physics*. Clear reference for gamma-function technology.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for dimensional regularization, gamma-function poles, and asymptotic expansions.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Useful for dimensional regularization and perturbative QFT conventions.
- M. Srednicki, *Quantum Field Theory*. Useful for functional determinants, Feynman parameters, and loop integrals.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for practical Feynman-parameter and dimensional-regularization calculations.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*. Useful for gamma functions in conformal integrals and special-function normalizations.

## Version history

- **2026-06-26:** Initial polished draft. Added gamma and beta definitions, analytic continuation, Schwinger and Feynman parameters, dimensional regularization formulae, small-$\epsilon$ expansions, conformal integrals, common pitfalls, exercises with solutions, and TikZ/SVG figure.
