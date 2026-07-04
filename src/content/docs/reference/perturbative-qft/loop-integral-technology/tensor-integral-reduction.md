---
title: "Tensor Integral Reduction"
description: "A practical explanation of reducing loop integrals with tensor numerators to scalar integrals using Lorentz covariance, projectors, denominator identities, and one-loop Passarino–Veltman logic."
sidebar:
  label: "Tensor Integral Reduction"
  order: 3
level: Graduate
status: "Polished draft"
source: "Passarino–Veltman 1979; Srednicki 2007, sections 14–20 and 48; Weinberg 1995, Vol. I, ch. 6; Schwartz 2014, chs. 16–20 and Appendix B"
topics:
  - tensor integral reduction
  - loop integrals
  - Passarino–Veltman reduction
  - dimensional regularization
  - scalar master integrals
canonicalTopics:
  - tensor-integral-reduction
  - covariant-tensor-decomposition
  - passarino-veltman-reduction
  - scalar-integral-basis
  - gram-determinant
researchStatus:
  established:
    - "One-loop tensor integrals can be reduced systematically to scalar integrals by Lorentz-covariant decomposition and algebraic projection."
  active:
    - "Modern amplitude calculations use tensor reduction together with integrand reduction, integration-by-parts identities, finite-field reconstruction, numerical unitarity, and stable treatments of exceptional kinematics."
---

## Summary

Loop diagrams in gauge theories, Yukawa theories, and derivative interactions often contain numerator factors of the loop momentum:

$$
\ell^\mu,
\qquad
\ell^\mu \ell^\nu,
\qquad
\ell^\mu \ell^\nu \ell^\rho,
\qquad\ldots
$$

A **tensor integral reduction** rewrites such integrals in terms of scalar loop integrals and tensors built from the metric and external momenta. The simplest symmetric-integration identities are

$$
\int_k k^\mu F(k^2)=0,
\qquad
\int_k k^\mu k^\nu F(k^2)
=
\frac{\eta^{\mu\nu}}{d}
\int_k k^2 F(k^2).
$$

At one loop, the general idea is

$$
\text{tensor numerator}
\quad\longrightarrow\quad
\text{covariant tensor basis}
\quad\longrightarrow\quad
\text{scalar coefficients}
\quad\longrightarrow\quad
\text{scalar integrals}.
$$

For a two-point integral with one external momentum $p$, covariance implies

$$
B^\mu=p^\mu B_1,
\qquad
B^{\mu\nu}=\eta^{\mu\nu}B_{00}+p^\mu p^\nu B_{11}.
$$

The scalar coefficients are found by contracting with $p_\mu$ and $\eta_{\mu\nu}$. This page explains the reduction logic, gives the basic projector formulas, and highlights the convention and stability checks that matter in real calculations.

<figure class="doc-figure" style="--figure-width: 60rem; --caption-width: 55rem;">

![Tensor integral reduction maps loop-momentum numerator tensors to covariant tensor bases, then to scalar coefficients and scalar loop integrals](/figures/perturbative-qft/tensor-integral-reduction.svg)

<figcaption>

Tensor reduction uses Lorentz covariance before doing scalar integrations. After denominator combination and a loop-momentum shift, odd powers vanish and even powers reduce to metric tensors. For external momenta, coefficients are obtained by contractions, with Gram determinants controlling possible numerical instabilities.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), and [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/).

You should also be comfortable with Lorentz-index contractions and with solving small linear systems.

## Core idea

The loop momentum is integrated over. After regularization, the integral cannot remember a preferred direction except those supplied by external momenta and the metric. Therefore a tensor integral has to be a linear combination of all tensors allowed by Lorentz covariance.

For an integral with no external momentum, the only rank-two tensor available is the metric:

$$
\int_k k^\mu k^\nu F(k^2)
=
C\eta^{\mu\nu}.
$$

Contracting both sides with $\eta_{\mu\nu}$ gives

$$
\int_k k^2F(k^2)=Cd,
$$

so

$$
C=\frac1d\int_k k^2F(k^2).
$$

With external momenta, the basis grows: $p_i^\mu$, $p_i^\mu p_j^\nu$, $\eta^{\mu\nu}$, and higher-rank products. The coefficients are scalar functions of invariants such as $p_i\cdot p_j$ and masses. Tensor reduction is the disciplined way to find those coefficients.

## Setup and conventions

We work in qft.org mostly-minus conventions and use dimensional regularization unless otherwise stated. A generic one-loop tensor integral is written

$$
I_N^{\mu_1\cdots \mu_R}
=
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\ell^{\mu_1}\cdots \ell^{\mu_R}}
{D_0D_1\cdots D_{N-1}},
$$

with denominators

$$
D_j=(\ell+r_j)^2-m_j^2+i\epsilon.
$$

We usually set $r_0=0$, so

$$
D_0=\ell^2-m_0^2+i\epsilon.
$$

The dimension is

$$
d=4-2\epsilon
$$

in common four-dimensional calculations. The reduction should be done in $d$ dimensions when divergent integrals are present. Reducing tensors in four dimensions too early can lose rational terms or violate identities after renormalization.

:::caution[Regulator matters]
The identities in this page assume a shift-invariant regulator such as dimensional regularization. With a hard cutoff, loop-momentum shifts and symmetric integration can generate boundary terms unless the regulator is defined carefully.
:::

## Symmetric integration with no external momentum

Suppose the only vector being integrated is $k^\mu$ and the scalar function depends on $k$ only through $k^2$. Then the integral of an odd tensor vanishes:

$$
\int_k k^\mu F(k^2)=0.
$$

For rank two,

$$
\int_k k^\mu k^\nu F(k^2)
=
\frac{\eta^{\mu\nu}}{d}
\int_k k^2F(k^2).
$$

For rank four,

$$
\int_k k^\mu k^\nu k^\rho k^\sigma F(k^2)
=
\frac{\eta^{\mu\nu}\eta^{\rho\sigma}
+\eta^{\mu\rho}\eta^{\nu\sigma}
+\eta^{\mu\sigma}\eta^{\nu\rho}}
{d(d+2)}
\int_k (k^2)^2F(k^2).
$$

These formulas are the tensor analog of ordinary rotational averaging. In Euclidean space, replace $\eta^{\mu\nu}$ by $\delta^{\mu\nu}$; after analytic continuation, the covariant Lorentzian form is written with $\eta^{\mu\nu}$.

A very common scalarization step is

$$
k^2=(k^2-\Delta+i\epsilon)+\Delta-i\epsilon,
$$

so, inside an integral,

$$
\frac{k^2}{(k^2-\Delta+i\epsilon)^n}
=
\frac{1}{(k^2-\Delta+i\epsilon)^{n-1}}
+\frac{\Delta}{(k^2-\Delta+i\epsilon)^n}
$$

up to the infinitesimal prescription. This reduces numerator powers to simpler scalar denominator powers.

## Two-point vector and tensor decompositions

For two-point functions there is one independent external momentum $p$. Define

$$
B^\mu
=
\int_\ell
\frac{\ell^\mu}{D_0D_1},
\qquad
D_0=\ell^2-m_0^2+i\epsilon,
\qquad
D_1=(\ell+p)^2-m_1^2+i\epsilon.
$$

Lorentz covariance implies

$$
{B^\mu=p^\mu B_1.}
$$

Contracting with $p_\mu$ gives

$$
B_1=\frac{p_\mu B^\mu}{p^2},
$$

as long as $p^2\ne0$. If $p^2=0$, this projector degenerates and one should use a different basis, take a limit, or avoid the projection formula in this form.

For rank two,

$$
B^{\mu\nu}
=
\int_\ell
\frac{\ell^\mu\ell^\nu}{D_0D_1}.
$$

The most general covariant decomposition is

$$
B^{\mu\nu}
=
\eta^{\mu\nu}B_{00}+p^\mu p^\nu B_{11}.
$$

Define the contractions

$$
T_g=\eta_{\mu\nu}B^{\mu\nu},
\qquad
T_p=p_\mu p_\nu B^{\mu\nu},
\qquad
s=p^2.
$$

Then

$$
T_g=dB_{00}+sB_{11},
\qquad
T_p=sB_{00}+s^2B_{11}.
$$

Solving,

$$
B_{00}=\frac{sT_g-T_p}{(d-1)s},
\qquad
B_{11}=\frac{dT_p-sT_g}{(d-1)s^2}.
$$

These formulas are simple, but they already show the main numerical issue: denominators contain powers of the Gram invariant $s=p^2$. If $s$ is small, a naive projected representation can be unstable even when the original tensor integral is perfectly finite.

## Denominator identities

A useful algebraic relation expresses loop-momentum dot products in terms of denominators. With

$$
D_i=(\ell+r_i)^2-m_i^2+i\epsilon,
\qquad
D_0=\ell^2-m_0^2+i\epsilon,
$$

we have

$$
D_i-D_0
=
2\ell\cdot r_i+r_i^2-m_i^2+m_0^2.
$$

Therefore

$$
2\ell\cdot r_i
=
D_i-D_0-r_i^2+m_i^2-m_0^2.
$$

This identity is powerful because a numerator factor $\ell\cdot r_i$ can cancel a denominator. For example,

$$
\frac{\ell\cdot r_i}{D_0D_i}
=
\frac12
\left[
\frac{1}{D_0}
-
\frac{1}{D_i}
+
\frac{-r_i^2+m_i^2-m_0^2}{D_0D_i}
\right],
$$

with the sign pattern following from the definition above. The result is a combination of lower-point scalar integrals and the original scalar integral.

This denominator-cancellation method is often the fastest way to reduce scalar products of the loop momentum with external momenta. Metric tensors still arise from irreducible powers such as $k^\mu k^\nu$ after completing the square.

## Reduction after Feynman parameterization

A clean way to avoid mistakes is to combine denominators first. For the two-point rank-two integral,

$$
B^{\mu\nu}
=
\int_\ell
\frac{\ell^\mu\ell^\nu}{D_0D_1},
$$

Feynman parameterization gives

$$
\frac{1}{D_0D_1}
=
\int_0^1 dx\,
\frac{1}{[(\ell+xp)^2-\Delta(x)+i\epsilon]^2},
$$

where

$$
\Delta(x)=xm_1^2+(1-x)m_0^2-x(1-x)p^2.
$$

Shift

$$
k=\ell+xp,
\qquad
\ell=k-xp.
$$

Then

$$
\ell^\mu\ell^\nu
=
k^\mu k^\nu
-x(k^\mu p^\nu+p^\mu k^\nu)
+x^2p^\mu p^\nu.
$$

The odd terms vanish after integration. Therefore

$$
B^{\mu\nu}
=
\int_0^1 dx
\left[
\frac{\eta^{\mu\nu}}{d}
\int_k \frac{k^2}{(k^2-\Delta(x)+i\epsilon)^2}
+x^2p^\mu p^\nu
\int_k \frac{1}{(k^2-\Delta(x)+i\epsilon)^2}
\right].
$$

This is tensor reduction in its most transparent form: after the shift, only metric tensors and external momenta remain. The scalar integrals are the same objects computed on the one-loop scalar-integral pages.

## Passarino–Veltman logic

For one-loop amplitudes, the traditional Passarino–Veltman strategy is:

1. define tensor integrals with $N$ denominators and rank $R$;
2. decompose each tensor integral into a covariant basis built from $\eta^{\mu\nu}$ and independent external momenta;
3. contract with basis tensors to solve for scalar coefficients;
4. express contractions involving $\ell\cdot p_i$ using denominator identities;
5. reduce the result to scalar one-loop integrals such as tadpoles, bubbles, triangles, and boxes.

For example, in a three-point function with independent momenta $p_1$ and $p_2$,

$$
C^\mu=p_1^\mu C_1+p_2^\mu C_2,
$$

and

$$
C^{\mu\nu}
=
\eta^{\mu\nu}C_{00}
+p_1^\mu p_1^\nu C_{11}
+p_2^\mu p_2^\nu C_{22}
+(p_1^\mu p_2^\nu+p_2^\mu p_1^\nu)C_{12}.
$$

The coefficients are determined by contracting with $p_1$, $p_2$, and the metric. The linear systems involve the Gram matrix

$$
G_{ij}=p_i\cdot p_j.
$$

If $\det G$ is small, the algebraic solution can become numerically unstable. Precision calculations therefore often use special expansions, alternative integral bases, or numerical reduction methods in exceptional kinematic regions.

## Tensor reduction versus integral reduction

Tensor reduction is not the end of loop technology. It reduces tensor numerators to scalar integrals, but those scalar integrals may still be related by identities.

| Step | What it reduces |
|---|---|
| Tensor reduction | Lorentz-index numerators to scalar coefficient functions. |
| Denominator cancellation | Scalar products $\ell\cdot p_i$ to lower-point integrals. |
| Passarino–Veltman reduction | One-loop tensor integrals to standard scalar one-loop functions. |
| Integration-by-parts reduction | Large families of scalar integrals to master integrals. |
| Differential equations | Master integrals as functions of kinematic invariants. |

This page focuses on the first three. Multi-loop scalar reduction belongs to later loop-integral technology pages.

## Validation checks

A tensor reduction should pass several quick checks.

| Check | What to verify |
|---|---|
| Index symmetry | The reduced expression has the same symmetries as the original tensor integral. |
| Dimension | Both sides have the same mass dimension in $d$ dimensions. |
| Covariance | Only $\eta^{\mu\nu}$ and external momenta appear. |
| Odd terms | Odd powers of the shifted loop momentum vanish only after a shift-invariant regulator is in place. |
| Ward identities | In gauge theories, reduced amplitudes should satisfy the expected gauge-invariance checks. |
| Smooth limits | Apparent Gram singularities should be checked against the original integral in special kinematics. |

## Minimal worked example

Consider

$$
I^{\mu\nu}
=
\int_k \frac{k^\mu k^\nu}{(k^2-\Delta+i\epsilon)^2}.
$$

There is no external vector, so covariance gives

$$
I^{\mu\nu}=\eta^{\mu\nu}I_g.
$$

Contracting with $\eta_{\mu\nu}$,

$$
\eta_{\mu\nu}I^{\mu\nu}
=
\int_k \frac{k^2}{(k^2-\Delta+i\epsilon)^2}
=dI_g.
$$

Thus

$$
I^{\mu\nu}
=
\frac{\eta^{\mu\nu}}{d}
\int_k \frac{k^2}{(k^2-\Delta+i\epsilon)^2}.
$$

Now rewrite the numerator:

$$
k^2=(k^2-\Delta+i\epsilon)+\Delta-i\epsilon.
$$

Ignoring the infinitesimal in the numerator, the scalar integral becomes

$$
\int_k \frac{k^2}{(k^2-\Delta+i\epsilon)^2}
=
\int_k \frac{1}{k^2-\Delta+i\epsilon}
+\Delta\int_k \frac{1}{(k^2-\Delta+i\epsilon)^2}.
$$

So the rank-two tensor integral is reduced to scalar integrals with denominator powers one and two.

## Common pitfalls

**Reducing in four dimensions too early.** Divergent tensor integrals should be reduced in $d=4-2\epsilon$ dimensions. Four-dimensional identities can miss rational terms or conflict with dimensional regularization.

**Using symmetric integration with a non-shift-invariant cutoff.** The statement that odd shifted integrals vanish assumes the integration domain is symmetric in the regulated theory. A hard cutoff centered before a shift can spoil this.

**Confusing tensor reduction with renormalization.** Tensor reduction rewrites numerator structure. It does not remove UV divergences; the resulting scalar integrals still need regularization, counterterms, and a renormalization prescription.

**Ignoring Gram determinant zeros.** Projector formulas often divide by determinants built from external momenta. These singularities can be artifacts of the reduction basis rather than singularities of the physical amplitude.

**Losing gauge cancellations.** In gauge theories, large numerator expressions often cancel only after diagrams are combined and Ward identities are used. Reducing each diagram independently is allowed, but the final gauge check is non-negotiable.

## Relations to other pages

- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) explains the denominator-combining step used before the clean shifted-momentum reduction.
- [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/) gives the exponential version of the same Gaussian averaging logic.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) supplies the scalar bubble functions that tensor reductions produce.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) and [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) are physical places where tensor numerators first appear.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains why reduction should be performed in $d$ dimensions.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how the UV divergences of the resulting scalar integrals are subtracted.

## Research status

One-loop tensor reduction is textbook-standard, and Passarino–Veltman reduction remains a common language for presenting results. The active frontier is not the basic covariance argument; it is efficient, stable, and automated reduction in complicated amplitudes. Modern precision calculations often combine tensor reduction with integrand reduction, integration-by-parts identities, finite-field reconstruction, numerical unitarity, and special treatments of small Gram determinants.

## Exercises

### Exercise 1: Derive the rank-two symmetric average

Assume

$$
\int_k k^\mu k^\nu F(k^2)=C\eta^{\mu\nu}.
$$

Show that

$$
C=\frac1d\int_k k^2F(k^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Contract both sides with $\eta_{\mu\nu}$. The left-hand side becomes

$$
\eta_{\mu\nu}\int_k k^\mu k^\nu F(k^2)
=
\int_k k^2F(k^2).
$$

The right-hand side is

$$
C\eta_{\mu\nu}\eta^{\mu\nu}=Cd.
$$

Therefore

$$
C=\frac1d\int_k k^2F(k^2).
$$

</details>

### Exercise 2: Solve the two-point rank-two projectors

Starting from

$$
T_g=dB_{00}+sB_{11},
\qquad
T_p=sB_{00}+s^2B_{11},
$$

solve for $B_{00}$ and $B_{11}$.

<details>
<summary><strong>Solution</strong></summary>

Multiply the first equation by $s$:

$$
sT_g=dsB_{00}+s^2B_{11}.
$$

Subtract the second equation:

$$
sT_g-T_p=(d-1)sB_{00}.
$$

Thus

$$
B_{00}=\frac{sT_g-T_p}{(d-1)s}.
$$

For $B_{11}$, compute $dT_p-sT_g$:

$$
dT_p-sT_g
=d(sB_{00}+s^2B_{11})-s(dB_{00}+sB_{11})
=(d-1)s^2B_{11}.
$$

Therefore

$$
B_{11}=\frac{dT_p-sT_g}{(d-1)s^2}.
$$

</details>

### Exercise 3: Denominator cancellation

With

$$
D_i=(\ell+r_i)^2-m_i^2+i\epsilon,
\qquad
D_0=\ell^2-m_0^2+i\epsilon,
$$

show that

$$
2\ell\cdot r_i=D_i-D_0-r_i^2+m_i^2-m_0^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand $D_i$:

$$
D_i=\ell^2+2\ell\cdot r_i+r_i^2-m_i^2+i\epsilon.
$$

Subtract $D_0=\ell^2-m_0^2+i\epsilon$:

$$
D_i-D_0
=2\ell\cdot r_i+r_i^2-m_i^2+m_0^2.
$$

Rearranging gives

$$
2\ell\cdot r_i=D_i-D_0-r_i^2+m_i^2-m_0^2.
$$

</details>

### Exercise 4: Reduce a shifted rank-two numerator

Let

$$
I^{\mu\nu}(p)=\int_k \frac{(k-xp)^\mu(k-xp)^\nu}{(k^2-\Delta+i\epsilon)^2}.
$$

Show that odd terms vanish and write the result in terms of scalar integrals.

<details>
<summary><strong>Solution</strong></summary>

Expand the numerator:

$$
(k-xp)^\mu(k-xp)^\nu
=
k^\mu k^\nu
-x(k^\mu p^\nu+p^\mu k^\nu)
+x^2p^\mu p^\nu.
$$

The terms linear in $k$ vanish by symmetric integration. Therefore

$$
I^{\mu\nu}(p)
=
\int_k \frac{k^\mu k^\nu}{(k^2-\Delta+i\epsilon)^2}
+x^2p^\mu p^\nu
\int_k \frac{1}{(k^2-\Delta+i\epsilon)^2}.
$$

Using the rank-two average,

$$
\int_k \frac{k^\mu k^\nu}{(k^2-\Delta+i\epsilon)^2}
=
\frac{\eta^{\mu\nu}}{d}
\int_k \frac{k^2}{(k^2-\Delta+i\epsilon)^2}.
$$

Thus

$$
I^{\mu\nu}(p)
=
\frac{\eta^{\mu\nu}}{d}
\int_k \frac{k^2}{(k^2-\Delta+i\epsilon)^2}
+x^2p^\mu p^\nu
\int_k \frac{1}{(k^2-\Delta+i\epsilon)^2}.
$$

</details>

### Exercise 5: Identify a Gram determinant

For two independent external momenta $p_1$ and $p_2$, write the Gram matrix and explain why its determinant can appear in tensor reduction.

<details>
<summary><strong>Solution</strong></summary>

The Gram matrix is

$$
G=
\begin{pmatrix}
p_1^2 & p_1\cdot p_2\\
p_1\cdot p_2 & p_2^2
\end{pmatrix}.
$$

Its determinant is

$$
\det G=p_1^2p_2^2-(p_1\cdot p_2)^2.
$$

Tensor reduction solves for scalar coefficients by contracting tensor integrals with $p_1$ and $p_2$. This requires inverting the Gram matrix. If $\det G$ is small or zero, the projection formulas become singular or numerically unstable, even if the original loop integral is finite.

</details>

## References

### Standard first pass

- G. Passarino and M. Veltman, “One-Loop Corrections for $e^+e^-$ Annihilation into $\mu^+\mu^-$ in the Weinberg Model,” *Nuclear Physics B* **160** (1979), for the classic one-loop tensor-reduction framework.
- M. Srednicki, *Quantum Field Theory*, sections 14–20 and 48, for one-loop integrals, spin sums, and amplitude calculations where tensor numerators appear.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 16–20 and Appendix B, for loop examples, dimensional regularization, and practical tensor-numerator reduction.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 6, for covariant Feynman rules and loop-momentum organization.
- A. Denner, “Techniques for Calculation of Electroweak Radiative Corrections at the One-Loop Level and Results for W-Physics at LEP200,” *Fortschritte der Physik* **41** (1993), for systematic one-loop reduction conventions.
- T. Hahn and M. Pérez-Victoria, “Automated One-Loop Calculations in Four and D Dimensions,” *Computer Physics Communications* **118** (1999), for computational implementations of one-loop reduction.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume. Figure generated from compact TikZ source in the qft.org black/gray style.
