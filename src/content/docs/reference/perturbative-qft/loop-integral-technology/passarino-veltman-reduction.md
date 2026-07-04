---
title: "Passarino–Veltman Reduction"
description: "A practical derivation of one-loop Passarino–Veltman reduction: scalar functions, tensor decompositions, Gram matrices, coefficient solving, and stability caveats."
sidebar:
  label: "Passarino–Veltman Reduction"
  order: 4
level: Graduate
status: "Polished draft"
source: "Passarino–Veltman 1979; Srednicki 2007, sections 14–20, 45–48, and 62–66; Weinberg 1995, Vol. I, chs. 6, 8, and 12; Schwartz 2014, chs. 16–20 and Appendix B"
topics:
  - Passarino–Veltman reduction
  - one-loop integrals
  - tensor reduction
  - scalar integrals
  - Gram determinants
canonicalTopics:
  - passarino-veltman-reduction
  - one-loop-tensor-integrals
  - scalar-one-loop-functions
  - gram-determinant
  - loop-integral-basis
researchStatus:
  established:
    - "Passarino–Veltman reduction is a standard algebraic method for reducing one-loop tensor integrals to scalar one-loop functions in dimensional regularization."
  active:
    - "Modern multi-leg and precision calculations supplement or replace direct Passarino–Veltman reduction with integrand reduction, generalized unitarity, finite-field reconstruction, IBP reduction, and numerically stable treatments of small Gram determinants."
---

## Summary

**Passarino–Veltman reduction** is the standard one-loop algorithm that turns tensor loop integrals into scalar loop functions. Instead of trying to integrate numerator tensors such as $\ell^\mu\ell^\nu$ directly, one first uses Lorentz covariance to write them in a basis made from external momenta and the metric, then solves for scalar coefficient functions.

For example, a two-point vector integral with one external momentum $p$ has the form

$$
\mathcal B^\mu(p;m_0^2,m_1^2)
=
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\ell^\mu}{D_0D_1}
=
p^\mu \mathcal B_1(p^2;m_0^2,m_1^2),
$$

where

$$
D_0=\ell^2-m_0^2+i\epsilon,
\qquad
D_1=(\ell+p)^2-m_1^2+i\epsilon.
$$

Contracting with $p_\mu$ and using the denominator identity

$$
2\ell\cdot p=D_1-D_0+m_1^2-m_0^2-p^2
$$

gives

$$
\mathcal B_1
=
\frac{\mathcal A_0(m_0^2)-\mathcal A_0(m_1^2)
+(m_1^2-m_0^2-p^2)\mathcal B_0(p^2;m_0^2,m_1^2)}{2p^2}.
$$

The same logic applies to higher-rank two-point, three-point, and four-point one-loop integrals. The final answer is expressed through scalar functions such as $A_0$, $B_0$, $C_0$, and $D_0$, together with rational functions of external invariants and masses.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Passarino–Veltman reduction maps one-loop tensor integrals to Lorentz tensor bases, projection equations, coefficient functions, and scalar one-loop functions](/figures/perturbative-qft/passarino-veltman-reduction.svg)

<figcaption>

Passarino–Veltman reduction is one-loop tensor reduction by covariance. Tensor numerators are decomposed into external momenta and metrics. Projection equations then solve for scalar coefficients, ultimately reducing the result to scalar one-loop functions. The Gram matrix $G_{ij}=r_i\cdot r_j$ controls the algebraic inversion and is the usual source of exceptional-kinematics warnings.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), and [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/).

This page assumes you are comfortable with Lorentz-index contractions and with solving small linear systems. No knowledge of automated one-loop packages is required.

## Core idea

A loop momentum is an integration variable. After integration, a one-loop tensor integral can depend only on the external momenta, the metric, masses, and the regulator. Therefore covariance strongly restricts its form.

For one external momentum $p$, a vector integral must be proportional to $p^\mu$:

$$
\mathcal B^\mu=p^\mu\mathcal B_1.
$$

A rank-two tensor integral must have the form

$$
\mathcal B^{\mu\nu}
=
\eta^{\mu\nu}\mathcal B_{00}
+p^\mu p^\nu\mathcal B_{11}.
$$

With two independent external momenta, a vector integral can involve both:

$$
\mathcal C^\mu=p_1^\mu\mathcal C_1+p_2^\mu\mathcal C_2.
$$

A rank-two triangle integral has the decomposition

$$
\mathcal C^{\mu\nu}
=
\eta^{\mu\nu}\mathcal C_{00}
+p_1^\mu p_1^\nu\mathcal C_{11}
+p_2^\mu p_2^\nu\mathcal C_{22}
+(p_1^\mu p_2^\nu+p_2^\mu p_1^\nu)\mathcal C_{12}.
$$

Passarino–Veltman reduction is the algorithmic version of these statements. Write the most general covariant decomposition, contract with external momenta and metrics, use denominator identities to remove scalar products of $\ell$, and solve for the coefficient functions.

The trick is not mystical. It is just linear algebra plus the identity

$$
2\ell\cdot r_i
=
D_i-D_0+m_i^2-m_0^2-r_i^2.
$$

This identity trades numerator scalar products for differences of denominators. Denominators cancel. An $N$-point tensor integral becomes a combination of scalar $N$-point and lower-point integrals.

## Setup and conventions

We use qft.org mostly-minus conventions and dimensional regularization. Unless explicitly stated otherwise,

$$
d=4-2\epsilon,
\qquad
\int_\ell\equiv \mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}.
$$

Consider a one-loop family with denominators

$$
D_i=(\ell+r_i)^2-m_i^2+i\epsilon,
\qquad
r_0=0.
$$

Thus

$$
D_0=\ell^2-m_0^2+i\epsilon.
$$

The rank-$R$ $N$-point tensor integral is

$$
\mathcal I_N^{\mu_1\cdots\mu_R}
=
\int_\ell
\frac{\ell^{\mu_1}\cdots\ell^{\mu_R}}{D_0D_1\cdots D_{N-1}}.
$$

The independent external momenta are the shifts $r_1,\ldots,r_{N-1}$, or convenient linear combinations of them. Their Gram matrix is

$$
G_{ij}=r_i\cdot r_j,
\qquad i,j=1,\ldots,N-1.
$$

When $G$ is invertible, vector coefficients can be found by contracting with $r_i$ and multiplying by $G^{-1}$. When $\det G$ is small or zero, the naive coefficient formulas can become singular even if the physical amplitude is finite. This is a numerical and algebraic issue, not necessarily a physical singularity.

:::caution[Reduce in $d$ dimensions]
Do not reduce divergent tensor integrals by using four-dimensional tensor identities too early. In dimensional regularization, terms proportional to $d-4$ can multiply $1/\epsilon$ poles and leave finite rational contributions. The safe default is to reduce in $d=4-2\epsilon$ until all regulator-sensitive pieces are under control.
:::

## Scalar one-loop functions

The scalar functions are the building blocks left after tensor reduction. In the normalization used on this page,

$$
\mathcal A_0(m_0^2)
=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{D_0},
$$

$$
\mathcal B_0(p^2;m_0^2,m_1^2)
=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{D_0D_1},
$$

$$
\mathcal C_0
=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{D_0D_1D_2},
\qquad
\mathcal D_0
=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{D_0D_1D_2D_3}.
$$

Many references and packages instead define dimensionless Passarino–Veltman functions by factoring out $i/(16\pi^2)$:

$$
\mathcal A_0=\frac{i}{16\pi^2}A_0,
\qquad
\mathcal B_0=\frac{i}{16\pi^2}B_0,
\qquad
\mathcal C_0=\frac{i}{16\pi^2}C_0,
\qquad
\mathcal D_0=\frac{i}{16\pi^2}D_0.
$$

This page keeps calligraphic symbols for the integrals that appear directly from qft.org Feynman rules and reserves non-calligraphic symbols for the common $i/(16\pi^2)$-stripped convention.

With

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\log 4\pi,
$$

the standard stripped tadpole is

$$
A_0(m^2)
=
m^2\left[
\frac{1}{\overline\epsilon}+1-\log\frac{m^2}{\mu^2}
\right]+O(\epsilon).
$$

The stripped bubble can be written as a Feynman-parameter integral,

$$
B_0(p^2;m_0^2,m_1^2)
=
\frac{1}{\overline\epsilon}
-
\int_0^1 dx\,
\log\frac{(1-x)m_0^2+xm_1^2-x(1-x)p^2-i\epsilon}{\mu^2}
+O(\epsilon).
$$

The scalar triangle and box functions are finite in many massive off-shell kinematic regions, but they can develop infrared poles, threshold branch cuts, and endpoint singularities in massless or on-shell limits. Passarino–Veltman reduction does not remove those singularities; it only expresses tensor integrals in terms of scalar integrals where the analytic structure is easier to study.

## The denominator identity

The algebraic engine is the difference of two denominators:

$$
\begin{aligned}
D_i-D_0
&=(\ell+r_i)^2-m_i^2-(\ell^2-m_0^2)\\
&=2\ell\cdot r_i+r_i^2+m_0^2-m_i^2.
\end{aligned}
$$

Therefore

$$
2\ell\cdot r_i
=D_i-D_0+m_i^2-m_0^2-r_i^2.
$$

This turns scalar products involving $\ell$ into denominator differences. For an integral with unit propagator powers,

$$
\int_\ell\frac{D_i}{D_0D_1\cdots D_i\cdots D_{N-1}}
=
\int_\ell\frac{1}{D_0D_1\cdots \widehat{D_i}\cdots D_{N-1}},
$$

where the hat means that the denominator is omitted. In words: one denominator cancels. This is why a tensor $N$-point integral reduces to scalar $N$-point integrals and lower-point scalar integrals.

For vector integrals, this identity is usually enough. For rank-two and higher tensors, one also contracts with $\eta_{\mu\nu}$, reducing $\ell^2$ by

$$
\ell^2=D_0+m_0^2-i\epsilon.
$$

The infinitesimal $i\epsilon$ is usually suppressed in purely algebraic numerator reduction, but the pole prescription still belongs to the scalar integrals.

## Vector reduction for a general one-loop integral

Let

$$
\mathcal I_N^\mu
=
\int_\ell \frac{\ell^\mu}{D_0D_1\cdots D_{N-1}}.
$$

By covariance,

$$
\mathcal I_N^\mu
=
\sum_{i=1}^{N-1}r_i^\mu\mathcal I_{N,i},
$$

assuming the $r_i$ span the relevant external momentum space. Contract with $r_j$:

$$
r_j\cdot \mathcal I_N
=
\sum_{i=1}^{N-1}G_{ji}\mathcal I_{N,i}.
$$

The denominator identity gives

$$
r_j\cdot \mathcal I_N
=
\frac12
\left[
\mathcal I_{N-1}^{[j]}
-
\mathcal I_{N-1}^{[0]}
+
(m_j^2-m_0^2-r_j^2)\mathcal I_N
\right],
$$

where $\mathcal I_{N-1}^{[j]}$ is the scalar integral obtained by deleting denominator $D_j$. Hence

$$
\mathcal I_{N,i}
=
\frac12\sum_{j=1}^{N-1}(G^{-1})_{ij}
\left[
\mathcal I_{N-1}^{[j]}
-
\mathcal I_{N-1}^{[0]}
+
(m_j^2-m_0^2-r_j^2)\mathcal I_N
\right].
$$

This formula captures the heart of one-loop vector Passarino–Veltman reduction. The price of solving for coefficients is the inverse Gram matrix.

## Two-point reduction in detail

For the two-point integral, take

$$
r_1=p,
\qquad
D_0=\ell^2-m_0^2+i\epsilon,
\qquad
D_1=(\ell+p)^2-m_1^2+i\epsilon.
$$

The scalar integral is

$$
\mathcal B_0(p^2;m_0^2,m_1^2)
=
\int_\ell\frac{1}{D_0D_1}.
$$

The vector integral is

$$
\mathcal B^\mu
=
\int_\ell\frac{\ell^\mu}{D_0D_1}
=p^\mu\mathcal B_1.
$$

Contracting with $p_\mu$ gives

$$
p^2\mathcal B_1
=
\int_\ell\frac{\ell\cdot p}{D_0D_1}.
$$

Using

$$
2\ell\cdot p=D_1-D_0+m_1^2-m_0^2-p^2,
$$

we get

$$
\begin{aligned}
2p^2\mathcal B_1
&=
\int_\ell\frac{D_1-D_0+m_1^2-m_0^2-p^2}{D_0D_1}\\
&=
\int_\ell\frac{1}{D_0}
-
\int_\ell\frac{1}{D_1}
+(m_1^2-m_0^2-p^2)\int_\ell\frac{1}{D_0D_1}.
\end{aligned}
$$

A shift-invariant regulator gives

$$
\int_\ell\frac{1}{D_1}=\mathcal A_0(m_1^2),
\qquad
\int_\ell\frac{1}{D_0}=\mathcal A_0(m_0^2),
$$

so

$$
\mathcal B_1
=
\frac{\mathcal A_0(m_0^2)-\mathcal A_0(m_1^2)
+(m_1^2-m_0^2-p^2)\mathcal B_0}{2p^2}.
$$

For equal internal masses,

$$
m_0=m_1=m,
$$

the tadpoles cancel and

$$
\mathcal B_1(p^2;m^2,m^2)
=-\frac12\mathcal B_0(p^2;m^2,m^2).
$$

This minus sign is a useful convention check. It follows from using $D_1=(\ell+p)^2-m^2+i\epsilon$. If a source uses $D_1=(\ell-p)^2-m^2+i\epsilon$, the sign of $\mathcal B_1$ changes accordingly.

## Rank-two two-point reduction

The rank-two two-point integral is

$$
\mathcal B^{\mu\nu}
=
\int_\ell\frac{\ell^\mu\ell^\nu}{D_0D_1}.
$$

Covariance gives

$$
\mathcal B^{\mu\nu}
=
\eta^{\mu\nu}\mathcal B_{00}
+p^\mu p^\nu\mathcal B_{11}.
$$

Contract with $\eta_{\mu\nu}$ and with $p_\mu p_\nu$:

$$
\eta_{\mu\nu}\mathcal B^{\mu\nu}
=d\mathcal B_{00}+p^2\mathcal B_{11},
$$

$$
p_\mu p_\nu\mathcal B^{\mu\nu}
=p^2\mathcal B_{00}+(p^2)^2\mathcal B_{11}.
$$

Define

$$
X\equiv \int_\ell\frac{\ell^2}{D_0D_1},
\qquad
Y\equiv \int_\ell\frac{(\ell\cdot p)^2}{D_0D_1}.
$$

Then

$$
X=d\mathcal B_{00}+p^2\mathcal B_{11},
\qquad
Y=p^2\mathcal B_{00}+(p^2)^2\mathcal B_{11}.
$$

Solving the two-by-two system gives

$$
\mathcal B_{00}
=
\frac{p^2X-Y}{(d-1)p^2},
\qquad
\mathcal B_{11}
=
\frac{dY-p^2X}{(d-1)(p^2)^2}.
$$

The remaining work is scalar numerator reduction. Since

$$
\ell^2=D_0+m_0^2-i\epsilon,
$$

we have, suppressing the infinitesimal in numerator algebra,

$$
X=\mathcal A_0(m_1^2)+m_0^2\mathcal B_0.
$$

Similarly, $Y$ is reduced by inserting

$$
\ell\cdot p=\frac12(D_1-D_0+m_1^2-m_0^2-p^2)
$$

and expanding. This illustrates a practical point: rank-two reduction is conceptually the same as vector reduction, but algebraically messier. In real calculations, the setup is mechanical enough that automation is sensible.

## Triangle and box reductions

For a triangle integral with denominators $D_0,D_1,D_2$, choose two independent external shifts $r_1,r_2$. The vector integral has the form

$$
\mathcal C^\mu
=
r_1^\mu\mathcal C_1+r_2^\mu\mathcal C_2.
$$

The coefficients solve

$$
\begin{pmatrix}
G_{11} & G_{12}\\
G_{21} & G_{22}
\end{pmatrix}
\begin{pmatrix}
\mathcal C_1\\
\mathcal C_2
\end{pmatrix}
=
\begin{pmatrix}
r_1\cdot\mathcal C\\
r_2\cdot\mathcal C
\end{pmatrix},
$$

where each $r_i\cdot\mathcal C$ is reduced to scalar triangles and scalar bubbles by denominator cancellation.

At rank two,

$$
\begin{aligned}
\mathcal C^{\mu\nu}
&=
\eta^{\mu\nu}\mathcal C_{00}
+r_1^\mu r_1^\nu\mathcal C_{11}
+r_2^\mu r_2^\nu\mathcal C_{22}\\
&\quad+(r_1^\mu r_2^\nu+r_2^\mu r_1^\nu)\mathcal C_{12}.
\end{aligned}
$$

The coefficients follow from contractions with $\eta_{\mu\nu}$ and $r_{i\mu}r_{j\nu}$. Again the Gram matrix and its inverse appear.

For a box integral, the corresponding basis uses three independent shifts $r_1,r_2,r_3$. A rank-one box vector decomposes as

$$
\mathcal D^\mu
=
r_1^\mu\mathcal D_1+r_2^\mu\mathcal D_2+r_3^\mu\mathcal D_3.
$$

A rank-two box tensor includes $\eta^{\mu\nu}$ and all symmetric products $r_i^\mu r_j^\nu+r_j^\mu r_i^\nu$.

In four dimensions, one-loop scalar integrals with five or more external legs can often be reduced further to boxes, up to regulator-dependent subtleties. In practical modern calculations, the reduction of high-multiplicity one-loop amplitudes is usually handled by integrand-reduction or unitarity-based methods rather than by writing enormous Passarino–Veltman coefficient formulas by hand.

## A practical Passarino–Veltman workflow

A reliable one-loop reduction workflow looks like this.

1. **Choose denominators and momentum routing.** State $D_i=(\ell+r_i)^2-m_i^2+i\epsilon$ and keep the routing fixed. A changed routing changes the signs of coefficient functions.

2. **Define the tensor integral.** Write numerator powers of $\ell^\mu$ explicitly. Keep spinor, polarization, and color algebra separate until the loop-momentum dependence is clear.

3. **Decompose covariantly.** Use every independent external momentum and the metric. Symmetrize tensor structures when the integral is symmetric in Lorentz indices.

4. **Project.** Contract with external momenta and $\eta_{\mu\nu}$. This produces scalar products such as $\ell\cdot r_i$ and $\ell^2$.

5. **Cancel denominators.** Use

$$
2\ell\cdot r_i=D_i-D_0+m_i^2-m_0^2-r_i^2,
\qquad
\ell^2=D_0+m_0^2.
$$

6. **Solve for coefficients.** Invert the Gram matrix, unless the kinematics are exceptional.

7. **Evaluate scalar functions.** Use known analytic formulas, Feynman-parameter integrals, numerical scalar-integral libraries, or differential equations.

8. **Check the amplitude.** Verify Ward identities, gauge-parameter cancellation, symmetry under identical external particles, ultraviolet poles, infrared poles, and known kinematic limits.

This workflow is simple enough to do by hand for two-point and low-rank three-point integrals. For realistic Standard Model amplitudes, it is better viewed as the conceptual basis of automated one-loop reduction.

## Gram determinants and exceptional kinematics

The Gram determinant measures the linear independence of the external momenta used in the tensor basis. For two vectors $p_1,p_2$,

$$
\det G
=
\begin{vmatrix}
p_1^2 & p_1\cdot p_2\\
p_1\cdot p_2 & p_2^2
\end{vmatrix}
=p_1^2p_2^2-(p_1\cdot p_2)^2.
$$

If $\det G=0$, the two vectors are linearly dependent in the relevant Lorentzian subspace. The naive basis is redundant, so the coefficient-solving equations are singular. If $\det G$ is tiny but nonzero, coefficient formulas can contain large cancellations.

This does not automatically mean the original integral is singular. It means the chosen tensor basis is a bad coordinate system on the space of integrals. The situation is like using polar coordinates at the origin: the coordinate chart is singular, not necessarily the physical object.

Common remedies include:

- expanding around the small Gram determinant;
- choosing a different tensor basis;
- using special kinematic formulas;
- using integrand-level reduction;
- using numerical methods designed for exceptional phase-space points;
- reducing the whole gauge-invariant amplitude rather than isolated diagrams.

The last point matters. Gauge invariance and other symmetries often produce cancellations only after summing diagrams. A numerically ugly coefficient in one diagram may disappear from the physical amplitude.

## What Passarino–Veltman reduction does not do

Passarino–Veltman reduction is a reduction method, not a full calculation pipeline.

It does **not** by itself choose a renormalization scheme. Ultraviolet poles in $A_0$ and $B_0$ still need counterterms or subtractions.

It does **not** make infrared divergences disappear. Massless on-shell bubbles, triangles, and boxes can contain soft and collinear poles. Physical cancellation requires inclusive observables, factorization, or subtraction methods.

It does **not** guarantee numerical stability. Gram determinants and threshold regions need care.

It does **not** prove gauge invariance diagram by diagram. Individual tensor integrals are usually gauge-dependent pieces of a larger gauge-invariant answer.

It does **not** replace integration-by-parts reduction at higher loops. Passarino–Veltman reduction is fundamentally a one-loop tensor-reduction method. Multi-loop calculations require a broader integral-family technology.

## A small worked example: equal-mass bubble vector

Consider

$$
\mathcal B^\mu
=
\int_\ell
\frac{\ell^\mu}{(\ell^2-m^2+i\epsilon)((\ell+p)^2-m^2+i\epsilon)}.
$$

By covariance,

$$
\mathcal B^\mu=p^\mu\mathcal B_1.
$$

Contract with $p_\mu$:

$$
p^2\mathcal B_1
=
\int_\ell
\frac{\ell\cdot p}{D_0D_1}.
$$

For equal masses,

$$
2\ell\cdot p=D_1-D_0-p^2.
$$

Thus

$$
2p^2\mathcal B_1
=
\int_\ell\frac{1}{D_0}
-
\int_\ell\frac{1}{D_1}
-p^2\int_\ell\frac{1}{D_0D_1}.
$$

By shift invariance,

$$
\int_\ell\frac{1}{D_0}
=
\int_\ell\frac{1}{D_1},
$$

so

$$
2p^2\mathcal B_1=-p^2\mathcal B_0.
$$

Therefore

$$
\mathcal B^\mu
=-\frac12p^\mu\mathcal B_0(p^2;m^2,m^2).
$$

The result is also intuitive after shifting to the symmetric loop momentum $k=\ell+p/2$. The denominator becomes symmetric under $k\mapsto -k$, while

$$
\ell^\mu=k^\mu-\frac12p^\mu.
$$

The odd $k^\mu$ integral vanishes, leaving the same $-p^\mu/2$ factor.

## Common pitfalls

**Mixing scalar-function normalizations.** Some authors include $i/(16\pi^2)$ in $A_0,B_0,C_0,D_0$; others do not. Check before comparing formulas.

**Changing momentum routing without changing coefficients.** If $D_1=(\ell+p)^2-m^2$ is replaced by $D_1=(\ell-p)^2-m^2$, vector coefficients change sign.

**Forgetting the Gram determinant.** Coefficient formulas can become singular when external momenta are linearly dependent. This can be a basis problem rather than a physical pole.

**Reducing in four dimensions too early.** Terms proportional to $d-4$ can multiply ultraviolet poles and leave finite pieces.

**Confusing reduction with renormalization.** Passarino–Veltman reduction expresses tensor integrals in terms of scalar functions. It does not decide which counterterms to add or which finite subtraction scheme to use.

**Expecting diagram-by-diagram stability.** Physical amplitudes often become simple only after summing all diagrams required by symmetry.

## Relations to other pages

- [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/) gives the broader covariance and projector logic that Passarino–Veltman reduction specializes at one loop.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) derive the scalar one-loop parameter integrals used after reduction.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains the regulator that makes shift invariance and $d$-dimensional tensor algebra consistent.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) evaluates the basic two-point scalar integral.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) and [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) are common places where one-loop tensor numerators appear.
- [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/) generalize the idea of algebraic integral reduction, especially beyond one loop.

## Research status

- **Established:** The one-loop Passarino–Veltman reduction of tensor integrals to scalar one-loop functions is textbook-standard and underlies many analytic one-loop calculations.
- **Convention-dependent:** Scalar function definitions vary by factors of $i$, $16\pi^2$, powers of $\mu$, and sign conventions for momentum routing and metric signature.
- **Technically delicate:** Exceptional kinematics, small Gram determinants, massless thresholds, and gauge cancellations require more care than the compact formulas suggest.
- **Active:** Modern precision calculations often use integrand reduction, generalized unitarity, finite-field reconstruction, numerical reduction, and IBP-based methods alongside or instead of traditional coefficient-level Passarino–Veltman reduction.

## Exercises

### Exercise 1: Derive the two-point vector coefficient

Starting from

$$
\mathcal B^\mu=p^\mu\mathcal B_1,
$$

and

$$
D_0=\ell^2-m_0^2+i\epsilon,
\qquad
D_1=(\ell+p)^2-m_1^2+i\epsilon,
$$

derive

$$
\mathcal B_1
=
\frac{\mathcal A_0(m_0^2)-\mathcal A_0(m_1^2)
+(m_1^2-m_0^2-p^2)\mathcal B_0}{2p^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Contract the decomposition with $p_\mu$:

$$
p^2\mathcal B_1
=
\int_\ell\frac{\ell\cdot p}{D_0D_1}.
$$

The denominator difference gives

$$
2\ell\cdot p=D_1-D_0+m_1^2-m_0^2-p^2.
$$

Therefore

$$
2p^2\mathcal B_1
=
\int_\ell\frac{1}{D_0}
-
\int_\ell\frac{1}{D_1}
+(m_1^2-m_0^2-p^2)\int_\ell\frac{1}{D_0D_1}.
$$

Using shift invariance,

$$
\int_\ell\frac{1}{D_0}=\mathcal A_0(m_0^2),
\qquad
\int_\ell\frac{1}{D_1}=\mathcal A_0(m_1^2),
$$

and the last integral is $\mathcal B_0$. Dividing by $2p^2$ gives the stated formula.

</details>

### Exercise 2: Equal masses

Show that for $m_0=m_1=m$,

$$
\mathcal B^\mu(p;m^2,m^2)
=-\frac12p^\mu\mathcal B_0(p^2;m^2,m^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Set $m_0=m_1=m$ in the result of Exercise 1. The tadpole difference vanishes:

$$
\mathcal A_0(m^2)-\mathcal A_0(m^2)=0.
$$

The remaining term is

$$
\mathcal B_1
=
\frac{-p^2\mathcal B_0}{2p^2}
=-\frac12\mathcal B_0.
$$

Since $\mathcal B^\mu=p^\mu\mathcal B_1$,

$$
\mathcal B^\mu=-\frac12p^\mu\mathcal B_0.
$$

</details>

### Exercise 3: The two-point rank-two projector

Suppose

$$
\mathcal B^{\mu\nu}
=
\eta^{\mu\nu}\mathcal B_{00}+p^\mu p^\nu\mathcal B_{11}.
$$

Let

$$
X=\eta_{\mu\nu}\mathcal B^{\mu\nu},
\qquad
Y=p_\mu p_\nu\mathcal B^{\mu\nu}.
$$

Derive

$$
\mathcal B_{00}
=
\frac{p^2X-Y}{(d-1)p^2},
\qquad
\mathcal B_{11}
=
\frac{dY-p^2X}{(d-1)(p^2)^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The two contractions give

$$
X=d\mathcal B_{00}+p^2\mathcal B_{11},
$$

and

$$
Y=p^2\mathcal B_{00}+(p^2)^2\mathcal B_{11}.
$$

Multiply the first equation by $p^2$ and subtract the second:

$$
p^2X-Y=(d-1)p^2\mathcal B_{00}.
$$

Thus

$$
\mathcal B_{00}=\frac{p^2X-Y}{(d-1)p^2}.
$$

Now solve for $\mathcal B_{11}$. One way is to compute $dY-p^2X$:

$$
dY-p^2X
=d\left[p^2\mathcal B_{00}+(p^2)^2\mathcal B_{11}\right]
-p^2\left[d\mathcal B_{00}+p^2\mathcal B_{11}\right].
$$

The $\mathcal B_{00}$ terms cancel, leaving

$$
dY-p^2X=(d-1)(p^2)^2\mathcal B_{11}.
$$

Therefore

$$
\mathcal B_{11}=\frac{dY-p^2X}{(d-1)(p^2)^2}.
$$

</details>

### Exercise 4: Gram determinant for a triangle

For a triangle with two independent external vectors $p_1,p_2$, compute the Gram determinant and state when the naive vector reduction becomes singular.

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

Therefore

$$
\det G=p_1^2p_2^2-(p_1\cdot p_2)^2.
$$

The naive vector reduction solves

$$
G
\begin{pmatrix}
\mathcal C_1\\
\mathcal C_2
\end{pmatrix}
=
\begin{pmatrix}
p_1\cdot\mathcal C\\
p_2\cdot\mathcal C
\end{pmatrix}.
$$

This requires $G^{-1}$, so the formula becomes singular when

$$
\det G=0.
$$

Geometrically, this means the chosen external vectors are linearly dependent in the relevant kinematic subspace. The integral may still be finite; the chosen tensor basis has become degenerate.

</details>

### Exercise 5: Zero-momentum equal-mass bubble

Using the Feynman-parameter expression for $B_0$, show that

$$
B_0(0;m^2,m^2)
=
\frac{1}{\overline\epsilon}-\log\frac{m^2}{\mu^2}+O(\epsilon).
$$

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
B_0(p^2;m_0^2,m_1^2)
=
\frac{1}{\overline\epsilon}
-
\int_0^1 dx\,
\log\frac{(1-x)m_0^2+xm_1^2-x(1-x)p^2-i\epsilon}{\mu^2}
+O(\epsilon).
$$

Set $p^2=0$ and $m_0=m_1=m$. The argument of the logarithm becomes independent of $x$:

$$
(1-x)m^2+xm^2=m^2.
$$

Therefore

$$
B_0(0;m^2,m^2)
=
\frac{1}{\overline\epsilon}
-
\int_0^1 dx\,\log\frac{m^2}{\mu^2}
+O(\epsilon).
$$

Since $\int_0^1dx=1$,

$$
B_0(0;m^2,m^2)
=
\frac{1}{\overline\epsilon}-\log\frac{m^2}{\mu^2}+O(\epsilon).
$$

</details>

## References

- G. Passarino and M. Veltman, “One-Loop Corrections for $e^+e^-$ Annihilation into $\mu^+\mu^-$ in the Weinberg Model,” *Nuclear Physics B* **160** (1979), 151–207.
- G. ’t Hooft and M. Veltman, “Scalar One-Loop Integrals,” *Nuclear Physics B* **153** (1979), 365–401.
- Mark Srednicki, *Quantum Field Theory*, especially sections 14–20 for scalar-loop examples, sections 45–48 for spinor amplitudes, and sections 62–66 for QED loop corrections.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6, 8, and 12, for Feynman rules, QED examples, and renormalization conventions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 16–20 and Appendix B, for one-loop examples, dimensional regularization, and practical scalar-integral formulas.
- G. Devaraj and R. G. Stuart, “Reduction of One-Loop Tensor Form Factors to Scalar Integrals: A General Scheme,” *Nuclear Physics B* **519** (1998), 483–513, for extensions useful near vanishing Gram determinants.

## Version history

- **2026-06-12:** Initial polished draft. Fixes qft.org normalization for calligraphic scalar integrals, explains the relation to common $i/(16\pi^2)$-stripped Passarino–Veltman functions, and includes the two-point vector coefficient as the main worked example.
