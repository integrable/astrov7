---
title: "Zeta Regularization"
description: "A spectral definition of determinant-like products using analytic continuation of zeta functions, with QFT conventions, scale dependence, heat-kernel links, zero modes, and common caveats."
sidebar:
  label: "Zeta Regularization"
  order: 7
level: Graduate
status: "Polished draft"
source: "Hawking's zeta-function method; standard functional-determinant treatments in Coleman, Srednicki, Schwartz, Weinberg, Zinn-Justin, and spectral-geometry references."
topics:
  - zeta regularization
  - functional determinants
  - spectral zeta functions
  - one-loop effective actions
  - analytic continuation
canonicalTopics:
  - zeta-regularization
  - spectral-regularization
  - functional-determinants
  - one-loop-determinants
researchStatus:
  established:
    - "For suitable positive elliptic operators on compact Euclidean spaces, spectral zeta functions provide a precise determinant scheme through analytic continuation."
  active:
    - "Phases, multiplicative anomalies, determinant-line signs, noncompact spectra, gauge zero modes, and regulator comparisons remain important in anomalies, curved-space QFT, localization, and nonperturbative calculations."
---

## Summary

Zeta regularization is a way to give meaning to divergent spectral products such as

$$
\prod_n \lambda_n,
$$

where $\lambda_n$ are eigenvalues of a differential operator. Instead of multiplying the eigenvalues directly, define a spectral zeta function

$$
\zeta_{K/\mu^2}(s)=\sum_n\left(\frac{\lambda_n}{\mu^2}\right)^{-s},
$$

continue it analytically to $s=0$, and set

$$
\log\det_{\zeta}\left(\frac{K}{\mu^2}\right)
=-\zeta'_{K/\mu^2}(0).
$$

The definition is motivated by the elementary identity

$$
\left. -\frac{d}{ds}\lambda^{-s}\right|_{s=0}=\log\lambda.
$$

So, in finite dimension,

$$
-\zeta'_K(0)=\sum_n\log\lambda_n=\log\det K.
$$

In infinite dimension, the original sum usually converges only for large $\operatorname{Re}(s)$. The determinant is obtained by analytic continuation, not by pretending the divergent product was secretly convergent.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow from a positive operator and its spectrum to the zeta-regularized determinant.](/figures/math-toolkit/zeta-regularization-flow.svg)

<figcaption>

Zeta regularization replaces the formal product $\prod_n\lambda_n$ by the analytic continuation of a spectral zeta function. The scale $\mu$, zero modes, boundary conditions, and phase choices are part of the data.

</figcaption>
</figure>

The method is elegant because it packages a divergent product into a well-defined spectral invariant. It is also easy to misuse. Zeta regularization is a **scheme**, not a law of nature. Its finite answer can differ from other regulators by local terms, and it does not automatically solve zero modes, phases, gauge redundancy, or infrared problems.

## Prerequisites

You should know [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), especially the idea that $\det K$ is a regulated spectral object rather than an ordinary infinite product. The finite-dimensional determinant identities in [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) explain why determinants appear in one-loop path integrals.

You should also be comfortable with the spectral viewpoint previewed in [Sobolev Spaces Preview](/math-toolkit/analysis-distributions-fourier/sobolev-spaces-preview/). The next page, [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/), explains the local short-time expansion that controls the poles and scale dependence of zeta functions.

## Core idea

For a finite positive matrix $K$ with eigenvalues $\lambda_1,\ldots,\lambda_N$, define

$$
\zeta_K(s)=\sum_{n=1}^N \lambda_n^{-s}.
$$

This is an entire function of $s$, and

$$
\zeta_K'(s)=\sum_{n=1}^N \frac{d}{ds}\lambda_n^{-s}
=-\sum_{n=1}^N(\log\lambda_n)\lambda_n^{-s}.
$$

At $s=0$,

$$
-\zeta_K'(0)=\sum_{n=1}^N\log\lambda_n
=\log\prod_{n=1}^N\lambda_n
=\log\det K.
$$

The zeta prescription keeps this formula but changes the order of operations for infinitely many eigenvalues:

1. define $\zeta_K(s)$ where the sum converges;
2. analytically continue $\zeta_K(s)$ to a neighborhood of $s=0$;
3. define the determinant by differentiating at $s=0$.

The analytic continuation is the regularization. It discards the divergent part of the naive sum in a specific, reproducible way.

For QFT, the point is not that zeta regularization is the only sensible definition. The point is that it gives a clean spectral scheme for many one-loop determinants, especially on compact Euclidean spaces and for elliptic operators.

## Setup and conventions

Unless stated otherwise, let $K$ be a positive self-adjoint operator with discrete positive eigenvalues

$$
0<\lambda_1\le \lambda_2\le\cdots.
$$

The determinant of a dimensionful operator is not dimensionless. If $K$ has mass dimension $2$, we introduce a reference scale $\mu$ and define

$$
\zeta_{K/\mu^2}(s)
=\sum_n\left(\frac{\lambda_n}{\mu^2}\right)^{-s}.
$$

The zeta-regularized determinant is then

$$
\det_\zeta\left(\frac{K}{\mu^2}\right)
=\exp\left[-\zeta'_{K/\mu^2}(0)\right].
$$

When no confusion is possible, one often writes $\det_\zeta K$ as shorthand. The dimensionless expression is the safer object.

If $K$ has zero modes, omit them from the spectral sum. A prime on $\zeta_K'(s)$ already means derivative with respect to $s$, so this page avoids writing a "primed zeta function" and instead uses

$$
\zeta_{K}^{\mathrm{nz}}(s)=\sum_{\lambda_n\ne0}\lambda_n^{-s}
$$

when the nonzero spectrum is meant. The corresponding determinant is

$$
\det{}'_{\zeta}K
=\exp\left[-\left.\frac{d}{ds}\zeta_K^{\mathrm{nz}}(s)\right|_{s=0}\right].
$$

The symbol $\det{}'$ still does not say how the zero modes are normalized or integrated. It only says that they were removed from the spectral product.

## Convergence and analytic continuation

A differential operator has infinitely many eigenvalues. The zeta sum

$$
\sum_n \lambda_n^{-s}
$$

converges only if $\operatorname{Re}(s)$ is large enough. For a second-order elliptic operator on a compact $d$-dimensional space, Weyl's law gives roughly

$$
\lambda_n\sim C n^{2/d}
$$

at large $n$. Therefore

$$
\sum_n\lambda_n^{-s}
\sim
\sum_n n^{-2s/d},
$$

which converges when

$$
\operatorname{Re}(s)>\frac d2.
$$

The determinant, however, needs the function near $s=0$. That is outside the original convergence region. The nontrivial theorem behind the method is that for many elliptic operators on smooth compact manifolds, $\zeta_K(s)$ has a meromorphic continuation to the complex $s$-plane and is regular at $s=0$.

This statement has hypotheses. The operator, domain, boundary conditions, background geometry, and spectrum matter. A random infinite product is not zeta-regularizable just because one writes the letter $\zeta$ next to it.

## The heat-kernel bridge

For $\operatorname{Re}(s)$ large enough, the identity

$$
\lambda^{-s}
=\frac{1}{\Gamma(s)}\int_0^\infty dt\,t^{s-1}e^{-t\lambda}
$$

gives

$$
\zeta_K(s)
=\frac{1}{\Gamma(s)}
\int_0^\infty dt\,t^{s-1}\operatorname{Tr}(e^{-tK}).
$$

This is the Mellin transform relation between zeta functions and heat kernels. It is one of the main reasons zeta regularization is useful in QFT.

The small-$t$ behavior of

$$
\operatorname{Tr}(e^{-tK})
$$

contains ultraviolet information. For a Laplace-type operator on a compact $d$-dimensional Euclidean space, the heat trace has an asymptotic expansion

$$
\operatorname{Tr}(e^{-tK})
\sim
\frac{1}{(4\pi t)^{d/2}}
\sum_{r\ge0}A_r(K)t^r,
\qquad t\to0^+,
$$

with possible half-integer powers if there is a boundary. The coefficients $A_r(K)$ are integrals of local invariants built from the geometry, background fields, bundle curvature, potential terms, and boundary data.

This expansion explains where the poles of $\zeta_K(s)$ come from. Inserting a term

$$
\frac{A_r}{(4\pi)^{d/2}}t^{r-d/2}
$$

into the Mellin integral produces a pole at

$$
s=\frac d2-r.
$$

Thus zeta regularization and heat-kernel regularization are not separate religions. They are two views of the same spectral data: zeta functions package the analytic continuation, while heat kernels expose locality and ultraviolet structure.

## Scale dependence

Because $K$ has dimensions, the determinant must be compared with a scale. We have

$$
\zeta_{K/\mu^2}(s)
=\mu^{2s}\zeta_K(s),
$$

where $\zeta_K(s)=\sum_n\lambda_n^{-s}$ is written formally with dimensionful eigenvalues. Differentiating at $s=0$ gives

$$
\zeta'_{K/\mu^2}(0)
=2(\log\mu)\zeta_K(0)+\zeta'_K(0).
$$

Therefore

$$
\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-\zeta'_K(0)-2\zeta_K(0)\log\mu.
$$

The scale derivative is

$$
\mu\frac{\partial}{\partial\mu}
\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-2\zeta_K(0).
$$

For a real bosonic one-loop effective action

$$
\Gamma^{(1)}=\frac12\log\det_\zeta\left(\frac{K}{\mu^2}\right),
$$

this gives

$$
\mu\frac{\partial \Gamma^{(1)}}{\partial\mu}
=-\zeta_K(0).
$$

This is not a bug. The scale dependence is the zeta-scheme version of the logarithmic ultraviolet dependence that must be absorbed into renormalized couplings or interpreted as an anomaly.

When $K$ is an elliptic operator on a compact space, $\zeta_K(0)$ is controlled by the coefficient of $t^0$ in the heat-kernel expansion, with a correction if zero modes are omitted. That is why trace anomalies, determinant scales, and heat-kernel coefficients are so closely tied together.

## Sanity check: finite dimension

Let $K$ be a positive $N\times N$ matrix. Then

$$
\zeta_{K/\mu^2}(s)
=\sum_{n=1}^N\left(\frac{\lambda_n}{\mu^2}\right)^{-s}.
$$

Since the sum is finite,

$$
-\zeta'_{K/\mu^2}(0)
=\sum_{n=1}^N\log\left(\frac{\lambda_n}{\mu^2}\right)
=\log\det\left(\frac{K}{\mu^2}\right).
$$

The scale derivative is

$$
\mu\frac{\partial}{\partial\mu}\log\det\left(\frac{K}{\mu^2}\right)
=-2N.
$$

The zeta formula gives the same result because

$$
\zeta_K(0)=N.
$$

In infinite dimension, $\zeta_K(0)$ plays the role of a regularized number of modes. It is generally not a literal count; it is the analytic-continuation value that controls scale dependence.

## Example: the circle Laplacian

Consider

$$
K=-\frac{d^2}{dx^2}
$$

on a circle of circumference $L$, acting on periodic functions. The eigenfunctions are

$$
f_n(x)=e^{2\pi i n x/L},
\qquad n\in\mathbb Z,
$$

with eigenvalues

$$
\lambda_n=\left(\frac{2\pi n}{L}\right)^2.
$$

The $n=0$ mode is a zero mode, so we remove it. The nonzero spectral zeta function is

$$
\zeta_K^{\mathrm{nz}}(s)
=\sum_{n\ne0}\left(\frac{2\pi n}{L}\right)^{-2s}
=2\left(\frac{L}{2\pi}\right)^{2s}\zeta_R(2s),
$$

where $\zeta_R$ is the Riemann zeta function. Using

$$
\zeta_R(0)=-\frac12,
\qquad
\zeta_R'(0)=-\frac12\log(2\pi),
$$

we find

$$
\left.\frac{d}{ds}\zeta_K^{\mathrm{nz}}(s)\right|_{s=0}
= -2\log L.
$$

Therefore

$$
\log\det{}'_{\zeta}K=2\log L,
\qquad
\det{}'_{\zeta}K=L^2.
$$

With the dimensionless operator $K/\mu^2$,

$$
\log\det{}'_{\zeta}\left(\frac{K}{\mu^2}\right)=2\log(\mu L).
$$

This example is small but useful. The answer knows about the size of the circle, the removed zero mode, and the scale needed to make the determinant dimensionless.

## Determinant ratios

Absolute determinants often include normalization choices. Ratios are usually more physical. Suppose $K$ and $K_0$ are positive operators with comparable high-frequency behavior. Define

$$
\log\frac{\det_\zeta K}{\det_\zeta K_0}
=-\left.\frac{d}{ds}\left[\zeta_K(s)-\zeta_{K_0}(s)\right]\right|_{s=0}
$$

when the same scale convention is used for both operators.

In semiclassical QFT, determinant ratios appear as

$$
\left(\frac{\det{}'K_{\mathrm{saddle}}}{\det K_{\mathrm{vac}}}\right)^{-1/2}.
$$

The ratio can cancel leading ultraviolet terms, but not always all of them. If the difference between the backgrounds changes local heat-kernel coefficients, counterterms are still needed. Zeta regularization gives a finite answer in a scheme; renormalization decides how that finite answer is related to physical couplings.

## Zeta regularization versus cutoff regularization

A proper-time cutoff writes, schematically,

$$
\operatorname{Tr}\log K\big|_{\epsilon}
=-\int_{\epsilon}^{\infty}\frac{dt}{t}\operatorname{Tr}(e^{-tK}).
$$

As $\epsilon\to0^+$, the small-$t$ heat-kernel expansion produces power divergences and logarithmic divergences. Zeta regularization corresponds to analytic continuation of the Mellin transform and automatically discards or reshuffles the divergent pieces according to that analytic prescription.

This is useful but not neutral. A cutoff scheme may display power divergences explicitly. Zeta regularization often hides them. Two schemes can differ by local counterterms. In renormalizable QFT, these differences are absorbed into the definition of renormalized parameters. In effective field theory, they are part of the Wilsonian bookkeeping of local operators.

A practical way to remember the difference is:

$$
\text{heat-kernel cutoff shows the ultraviolet terms; zeta regularization assigns them a finite spectral value.}
$$

The physics is not the raw finite number; the physics is the renormalized, convention-specified quantity.

## Nonpositive and first-order operators

The clean definition above assumes a positive spectrum. Many QFT operators are not positive in that simple sense.

For a Dirac-type operator $D$, eigenvalues may come with signs. One often computes the magnitude of the determinant using

$$
D^\dagger D,
$$

because this is positive. Then

$$
\log|\det D|=\frac12\log\det(D^\dagger D)
$$

in favorable cases. But this loses the phase of $\det D$. The phase can encode anomalies, spectral asymmetry, eta invariants, parity-odd terms, or global signs of Pfaffians.

For an operator with complex eigenvalues, one must choose a spectral cut: a branch of the logarithm used to define $\lambda^{-s}=e^{-s\log\lambda}$. Different choices can differ by phases. This is not pedantry. In fermionic theories, signs and phases often carry real physics.

For an operator with negative modes, the Euclidean Gaussian is not a positive Gaussian. A negative mode may signal an instability or a saddle appropriate to tunneling. Zeta regularizing the product of eigenvalues does not decide the integration contour.

## Multiplicative anomaly

In finite dimension,

$$
\det(AB)=\det A\det B.
$$

In infinite dimension, a regularized determinant need not preserve this identity. In zeta regularization, one can find

$$
\log\det_\zeta(AB)
\ne
\log\det_\zeta A+
\log\det_\zeta B
$$

for certain classes of operators, even when the finite-dimensional intuition would suggest equality. The difference is called a multiplicative anomaly.

In many QFT applications the anomaly is a local expression and can be moved by scheme choices. Still, the moral is important: algebraic identities for finite determinants are not automatically identities for regulated functional determinants.

The safer procedure is to define the operator whose determinant is actually needed, choose the spectral prescription for that operator, and only factor it if the regulator respects the factorization or the anomaly has been accounted for.

## Common pitfalls

**“Zeta regularization proves the divergent product was really finite.”** No. It defines a finite number by analytic continuation. That number is useful because it is spectral, systematic, and often symmetry-friendly, but it is a regularized value.

**“The scale $\mu$ is optional.”** Only for dimensionless finite toy problems. In QFT, determinants of differential operators are dimensionful; $\mu$ records how the determinant has been made dimensionless and how the result changes under scale transformations.

**“$\zeta_K(0)$ is the number of eigenvalues.”** In finite dimension, yes. In field theory, $\zeta_K(0)$ is a regularized spectral quantity tied to heat-kernel coefficients and zero-mode subtractions.

**“Zeta regularization removes the need for renormalization.”** It does not. It supplies one scheme for assigning finite values. Counterterms, scale dependence, and scheme comparisons remain.

**“Zero modes are harmless because the zeta sum can omit them.”** Omitting zero modes only defines $\det{}'K$. The removed modes still have to be integrated, gauge-fixed, saturated by fermionic insertions, or converted into collective coordinates.

**“$D^\dagger D$ gives the fermion determinant.”** It gives the magnitude in many cases. It can miss the phase, sign, eta-invariant contribution, or Pfaffian orientation.

**“Zeta determinants multiply like ordinary determinants.”** Sometimes, but not as a universal rule. Check for multiplicative anomalies whenever factorization is used in an infinite-dimensional determinant.

## Relations to other pages

[Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains why determinant-like objects appear in one-loop QFT. This page gives one precise spectral scheme for defining them. [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) explains the local small-$t$ expansion behind the analytic continuation and the ultraviolet counterterms.

The finite-dimensional determinant identities come from [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/). Fermionic determinants and Pfaffian signs are developed in [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) and [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/).

Zeta regularization also connects to spectral theory, Casimir energies, anomalies, curved-space QFT, instanton determinants, localization, and index-theorem technology.

## Research status

Zeta-function regularization is a standard and well-developed method for suitable elliptic operators, especially on compact Euclidean backgrounds. Its relation to heat kernels, local counterterms, and one-loop effective actions is part of the established mathematical physics toolkit.

The subtle issues are mostly global, infrared, or phase-sensitive: noncompact spectra, scattering backgrounds, eta invariants, determinant line bundles, Majorana signs, gauge zero modes, boundary conditions, and compatibility with other regulators. These questions remain active in anomalies, topological phases, lattice fermions, supersymmetric localization, and QFT on curved spaces.

## Exercises

### Exercise 1: Finite-dimensional zeta determinant

Let $K$ be a positive diagonal $N\times N$ matrix with eigenvalues $\lambda_1,
\ldots,\lambda_N$. Define

$$
\zeta_K(s)=\sum_{n=1}^N\lambda_n^{-s}.
$$

Show that

$$
\det K=\exp[-\zeta_K'(0)].
$$

<details><summary><strong>Solution</strong></summary>

Differentiate term by term:

$$
\zeta_K'(s)
=\sum_{n=1}^N\frac{d}{ds}\lambda_n^{-s}
=-\sum_{n=1}^N(\log\lambda_n)\lambda_n^{-s}.
$$

At $s=0$,

$$
-\zeta_K'(0)=\sum_{n=1}^N\log\lambda_n
=\log\prod_{n=1}^N\lambda_n
=\log\det K.
$$

Exponentiating gives

$$
\exp[-\zeta_K'(0)]=\det K.
$$

</details>

### Exercise 2: Scale dependence

Assume

$$
\zeta_{K/\mu^2}(s)=\mu^{2s}\zeta_K(s).
$$

Show that

$$
\mu\frac{\partial}{\partial\mu}
\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-2\zeta_K(0).
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-\zeta'_{K/\mu^2}(0).
$$

Since

$$
\zeta_{K/\mu^2}(s)=\mu^{2s}\zeta_K(s),
$$

we have

$$
\zeta'_{K/\mu^2}(0)
=2(\log\mu)\zeta_K(0)+\zeta_K'(0).
$$

Therefore

$$
\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-2(\log\mu)\zeta_K(0)-\zeta_K'(0).
$$

Taking $\mu\partial_\mu$ gives

$$
\mu\frac{\partial}{\partial\mu}
\log\det_\zeta\left(\frac{K}{\mu^2}\right)
=-2\zeta_K(0).
$$

</details>

### Exercise 3: Circle determinant

For

$$
K=-\frac{d^2}{dx^2}
$$

on a circle of circumference $L$, remove the constant zero mode and use

$$
\zeta_K^{\mathrm{nz}}(s)=2\left(\frac{L}{2\pi}\right)^{2s}\zeta_R(2s).
$$

Given

$$
\zeta_R(0)=-\frac12,
\qquad
\zeta_R'(0)=-\frac12\log(2\pi),
$$

show that

$$
\det{}'_{\zeta}K=L^2.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{d}{ds}\zeta_K^{\mathrm{nz}}(s)
=4\log\left(\frac{L}{2\pi}\right)
\left(\frac{L}{2\pi}\right)^{2s}\zeta_R(2s)
+4\left(\frac{L}{2\pi}\right)^{2s}\zeta_R'(2s).
$$

At $s=0$,

$$
\left(\zeta_K^{\mathrm{nz}}\right)'(0)
=4\log\left(\frac{L}{2\pi}\right)\left(-\frac12\right)
+4\left(-\frac12\log(2\pi)\right).
$$

Thus

$$
\left(\zeta_K^{\mathrm{nz}}\right)'(0)
=-2\log\left(\frac{L}{2\pi}\right)-2\log(2\pi)
=-2\log L.
$$

Therefore

$$
\log\det{}'_{\zeta}K
=-\left(\zeta_K^{\mathrm{nz}}\right)'(0)
=2\log L,
$$

so

$$
\det{}'_{\zeta}K=L^2.
$$

</details>

### Exercise 4: Zeta regularization and ordinary counting

For a finite $N$-dimensional positive operator, show that $\zeta_K(0)=N$. Explain why this statement should not be read literally in infinite-dimensional QFT.

<details><summary><strong>Solution</strong></summary>

In finite dimension,

$$
\zeta_K(0)=\sum_{n=1}^N\lambda_n^0=\sum_{n=1}^N1=N.
$$

In infinite dimension, the original sum

$$
\sum_n1
$$

diverges. The value $\zeta_K(0)$ is obtained by analytic continuation from a region where $\sum_n\lambda_n^{-s}$ converges. It is therefore a regularized spectral quantity, not a literal number of modes.

In QFT, $\zeta_K(0)$ is tied to heat-kernel coefficients, zero-mode subtractions, and scale dependence of the determinant.

</details>

### Exercise 5: Heat-kernel location of poles

Suppose a heat trace has a small-$t$ term

$$
\operatorname{Tr}(e^{-tK})\sim C t^{\alpha}
$$

as $t\to0^+$. Use

$$
\zeta_K(s)=\frac{1}{\Gamma(s)}\int_0^\infty dt\,t^{s-1}\operatorname{Tr}(e^{-tK})
$$

to identify where this term can produce a pole of $\zeta_K(s)$.

<details><summary><strong>Solution</strong></summary>

The small-$t$ contribution behaves like

$$
\frac{C}{\Gamma(s)}\int_0 dt\,t^{s-1+\alpha}.
$$

Near $t=0$, the integral has the form

$$
\int_0 dt\,t^{s+\alpha-1},
$$

which produces a pole when

$$
s+\alpha=0.
$$

Thus the pole is located at

$$
s=-\alpha.
$$

For a heat-kernel coefficient

$$
(4\pi t)^{-d/2}A_r t^r,
$$

we have $\alpha=r-d/2$, so the corresponding pole is at

$$
s=\frac d2-r.
$$

</details>

## References

- S. W. Hawking, “Zeta Function Regularization of Path Integrals in Curved Spacetime.” Classic physics introduction to zeta determinants in curved-space path integrals.
- M. Srednicki, *Quantum Field Theory*. Functional determinants, fermion determinants, and one-loop effective actions.
- S. Coleman, *Aspects of Symmetry*. Instanton determinants, false-vacuum decay, zero modes, and determinant ratios.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Functional integration, generating functionals, and determinant reasoning.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Path integrals, effective actions, Schwinger proper time, and background fields.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. External field methods, effective action, gauge fixing, and one-loop determinants.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, determinant regularization, and saddle-point expansions.
- E. Elizalde et al., *Zeta Regularization Techniques with Applications*. Detailed spectral zeta-function methods and applications.
- D. V. Vassilevich, “Heat Kernel Expansion: User's Manual.” Useful bridge between zeta determinants, heat kernels, and QFT applications.

## Version history

- 2026-06-24: First polished draft. Defined spectral zeta functions and zeta determinants, derived the finite-dimensional identity, explained convergence and analytic continuation, scale dependence, heat-kernel relation, circle determinant example, determinant ratios, comparison with cutoff regularization, nonpositive operators, phases, multiplicative caveats, and exercises with solutions.
