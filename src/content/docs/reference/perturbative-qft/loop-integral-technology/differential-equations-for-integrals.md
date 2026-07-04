---
title: "Differential Equations for Integrals"
description: "A practical derivation of differential equations for master integrals, including IBP closure, boundary data, canonical dlog form, alphabets, and analytic-continuation caveats."
sidebar:
  label: "Differential Equations"
  order: 7
level: Graduate
status: "Polished draft"
source: "Kotikov 1990s and 2021 review; Remiddi 1997; Gehrmann–Remiddi 1999; Henn 2013; Smirnov, Feynman Integral Calculus"
topics:
  - differential equations for Feynman integrals
  - master integrals
  - canonical form
  - iterated integrals
  - boundary conditions
canonicalTopics:
  - differential-equations-for-integrals
  - canonical-dlog-form
  - master-integral-systems
  - iterated-integrals
  - boundary-data
researchStatus:
  established:
    - "Differential equations for master integrals are a standard method for evaluating loop integrals after IBP reduction."
  active:
    - "Finding canonical or otherwise optimal systems for multi-scale, elliptic, and more general non-polylogarithmic integral families remains an active research area."
---

## Summary

The **differential-equation method** evaluates master integrals by treating them as functions of masses and kinematic invariants. After IBP reduction, derivatives of the masters can be expressed back in the master basis:

$$
\frac{\partial}{\partial x} \mathbf M(x,\epsilon)
= A_x(x,\epsilon)\,\mathbf M(x,\epsilon).
$$

Here $\mathbf M$ is a vector of master integrals, $x$ is a kinematic variable, and $A_x$ is a matrix of rational functions. With several variables,

$$
d\mathbf M=A\,\mathbf M,
\qquad
A=\sum_i A_i(\mathbf x,\epsilon)\,dx_i.
$$

The calculation has three parts: choose a master basis, derive and simplify the differential system, and fix the boundary constants.

A particularly powerful situation occurs when a basis $\mathbf F$ brings the system to **canonical dlog form**,

$$
d\mathbf F(\mathbf x,\epsilon)
=\epsilon\left(\sum_{a} A_a\,d\log W_a(\mathbf x)\right)\mathbf F(\mathbf x,\epsilon),
$$

where the $A_a$ are constant matrices and the $W_a$ are algebraic or rational functions called **letters**. In this form, the $\epsilon$ expansion is naturally organized by iterated integrals. Not every integral family admits a polylogarithmic canonical form, but the method remains useful far beyond that ideal case.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Differential equations for master integrals follow by differentiating masters with respect to invariants, reducing the derivatives by IBP, choosing a convenient basis, and fixing boundary data](/figures/perturbative-qft/differential-equations-for-integrals.svg)

<figcaption>

The differential-equation method turns master integrals into a first-order system in kinematic variables. IBP reduction closes derivatives back onto the master basis. A good basis may expose canonical $d\log$ form, but every system still needs boundary data and careful analytic continuation.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/), and [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/).

It is useful, but not required, to have seen ordinary differential equations with regular singular points and the basic idea of analytic continuation around branch cuts.

## Core idea

A loop integral is a function. If it depends on a variable $x$, then differentiating it with respect to $x$ gives another integral in the same general family. The derivative may raise propagator powers or insert numerator factors, but IBP reduction can express the result back in the master basis.

For a master integral

$$
M_i(x,
\epsilon)
=
\mu^{2L\epsilon}
\int \prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\mathcal I_i(\ell_r,p_a,m_a;x),
$$

the derivative has the schematic form

$$
\partial_x M_i
=
\int \partial_x \mathcal I_i.
$$

The differentiated integrand is usually not one of the chosen masters. But it is an integral in the same family, so reduction gives

$$
\partial_x M_i
=\sum_j (A_x)_{ij}M_j.
$$

This is the essential move. Instead of evaluating each master integral directly, solve a coupled differential system and fix constants from limits or boundary values.

## Setup and conventions

We work in dimensional regularization with

$$
d=4-2\epsilon.
$$

Let

$$
\mathbf M(\mathbf x,
\epsilon)=
\begin{pmatrix}
M_1(\mathbf x,
\epsilon)\\
\vdots\\
M_N(\mathbf x,
\epsilon)
\end{pmatrix}
$$

be a chosen vector of master integrals depending on dimensionless variables $\mathbf x=(x_1,\ldots,x_k)$. Dimensionless variables are preferred because they separate scaling from shape. For example, a two-scale integral may be written in terms of a ratio

$$
x=\frac{s}{m^2}
$$

and an overall power of $m^2$ fixed by dimensional analysis.

The differential system is

$$
\partial_{x_i}\mathbf M=A_i(\mathbf x,
\epsilon)\mathbf M.
$$

Equivalently,

$$
d\mathbf M=A\mathbf M,
\qquad
A=\sum_i A_i dx_i.
$$

The compatibility condition

$$
dA-A\wedge A=0
$$

is the flatness condition for the system. It follows when the derivatives commute and the reduction is consistent. In practice, checking compatibility is a strong diagnostic for algebra mistakes.

## Deriving the system

Start with an integral family

$$
I(\boldsymbol\nu)=
\mu^{2L\epsilon}
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}}.
$$

Suppose a denominator depends on $x$. Then

$$
\frac{\partial}{\partial x}\frac{1}{D_a^{\nu_a}}
=
-\nu_a\frac{\partial_x D_a}{D_a^{\nu_a+1}}.
$$

Thus differentiating with respect to $x$ usually produces integrals with raised propagator powers or numerator insertions. These are exactly the objects IBP reduction is designed to handle.

The workflow is:

1. choose masters $M_i$;
2. differentiate each $M_i$ with respect to $x$;
3. express the differentiated integrals in the same integral family;
4. IBP-reduce them back to the master basis;
5. assemble the matrix $A_x$.

If there are several variables, repeat this for each one.

## A one-master example: the massless bubble

Consider the massless one-loop bubble with external momentum $p$ and $s=p^2$:

$$
B(s)=
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{(\ell^2+i\epsilon)((\ell+p)^2+i\epsilon)}.
$$

The integral has mass dimension

$$
[B]=d-4=-2\epsilon.
$$

Since $s$ is the only kinematic scale, dimensional analysis gives

$$
B(s)=C(\epsilon)\,\mu^{2\epsilon}(-s-i\epsilon)^{-\epsilon},
$$

up to a normalization convention for the loop measure. Therefore

$$
s\frac{d}{ds}B(s)=-\epsilon B(s).
$$

Equivalently,

$$
dB=-\epsilon\,d\log(-s-i\epsilon)\,B.
$$

This is the simplest possible canonical differential equation: there is one master, one letter, and one boundary constant $C(\epsilon)$. The example is too simple to need IBP reduction, but it shows the general pattern. A loop integral's scale dependence can be easier to determine than the integral itself.

## Matrix systems

Most interesting families have several masters. Then the system is matrix-valued:

$$
\frac{d}{dx}
\begin{pmatrix}
M_1\\M_2\\\vdots\\M_N
\end{pmatrix}
=
\begin{pmatrix}
(A_x)_{11} & (A_x)_{12} & \cdots & (A_x)_{1N}\\
(A_x)_{21} & (A_x)_{22} & \cdots & (A_x)_{2N}\\
\vdots & \vdots & \ddots & \vdots\\
(A_x)_{N1} & (A_x)_{N2} & \cdots & (A_x)_{NN}
\end{pmatrix}
\begin{pmatrix}
M_1\\M_2\\\vdots\\M_N
\end{pmatrix}.
$$

The matrix entries are usually rational functions of $x$ and $\epsilon$. Singular points of the matrix often correspond to physical thresholds, pseudo-thresholds, massless limits, or artifacts of the chosen basis.

The solution of a matrix system requires path ordering unless the matrices commute. Perturbatively in $\epsilon$, canonical form makes this manageable.

## Basis transformations

A change of master basis changes the differential system. Suppose

$$
\mathbf M=T(\mathbf x,
\epsilon)\mathbf F.
$$

If

$$
d\mathbf M=A\mathbf M,
$$

then

$$
d\mathbf F=A_F\mathbf F,
$$

with

$$
A_F=T^{-1}AT-T^{-1}dT.
$$

Thus basis choice is not cosmetic. A clever $T$ can remove spurious singularities, factor out dimensions, isolate $\epsilon$, and expose simple logarithmic differential forms. A poor $T$ can hide simple structure behind large rational expressions.

## Canonical dlog form

The ideal polylogarithmic form is

$$
d\mathbf F
=
\epsilon\left(\sum_a A_a\,d\log W_a(\mathbf x)\right)\mathbf F,
$$

where the $A_a$ are constant matrices. The functions $W_a(\mathbf x)$ are called **letters**, and the set of all letters is the **alphabet**.

In one variable, this often looks like

$$
\frac{d\mathbf F}{dx}
=
\epsilon\left(\sum_a\frac{A_a}{x-a}\right)\mathbf F.
$$

Expanding

$$
\mathbf F=\sum_{n=0}^{\infty}\epsilon^n\mathbf F^{(n)},
$$

one gets the recursive equations

$$
d\mathbf F^{(0)}=0,
$$

and

$$
d\mathbf F^{(n)}=
\left(\sum_a A_a\,d\log W_a\right)\mathbf F^{(n-1)}.
$$

Therefore each order is obtained by integrating logarithmic forms against the previous order. This is why canonical systems naturally produce iterated integrals.

:::note[Canonical does not mean automatic]
Canonical $d\log$ form is a target, not a theorem for every family. Some sectors are elliptic or more complicated. In those cases the differential-equation method still works, but the solution space is larger than ordinary multiple polylogarithms.
:::

## Boundary conditions

A first-order system determines the masters only after boundary constants are supplied. Good boundary points are chosen to simplify the integrals or impose physical regularity.

Common choices include:

| Boundary source | Typical use |
|---|---|
| Euclidean point | Real, nonsingular numerical evaluation. |
| Zero momentum | Reduces to tadpoles or vacuum integrals. |
| Large-mass limit | Enables expansion by regions. |
| Threshold regularity | Removes unphysical singular solutions. |
| Pseudo-threshold regularity | Fixes constants not determined by cuts. |
| Soft or collinear limit | Matches factorization behavior. |
| Known cut | Fixes a discontinuity or imaginary part. |

Boundary data must be in the same normalization and branch convention as the differential system. A mismatch here can produce a result that solves the equation but describes the wrong physical sheet.

## Singularities, letters, and branch cuts

The singularities of the differential system organize the analytic structure of the integrals. In a canonical form, singular hypersurfaces appear as letters:

$$
W_a(\mathbf x)=0.
$$

These may correspond to physical thresholds, massless singularities, or pseudo-thresholds. Physical branch cuts depend on the $i\epsilon$ prescription and the chosen kinematic region.

For example, the massless bubble has the letter

$$
W=-s-i\epsilon.
$$

The logarithm knows where the branch cut lies. In multi-scale problems the alphabet can include many letters, and analytic continuation becomes a serious part of the calculation.

A useful rule of thumb is that the differential equation shows possible singularities, while the boundary condition and $i\epsilon$ prescription choose the physical branch.

## Solving order by order

In canonical form, the formal solution from a base point $\mathbf x_0$ to $\mathbf x$ is

$$
\mathbf F(\mathbf x,
\epsilon)
=
\mathcal P\exp\left[
\epsilon\int_{\mathbf x_0}^{\mathbf x}
\sum_a A_a\,d\log W_a
\right]
\mathbf F(\mathbf x_0,
\epsilon),
$$

where $\mathcal P$ denotes path ordering. Expanding gives

$$
\mathbf F(\mathbf x,
\epsilon)
=
\mathbf F(\mathbf x_0,
\epsilon)
+
\epsilon\int_{\mathbf x_0}^{\mathbf x}dA\,\mathbf F(\mathbf x_0,
\epsilon)
+
O(\epsilon^2),
$$

where

$$
dA=\sum_a A_a\,d\log W_a.
$$

At higher orders, one obtains iterated integrals of the letters. When the letters are rational functions of one variable, these are often harmonic polylogarithms or generalized polylogarithms. With algebraic letters or elliptic sectors, more general functions appear.

## Practical workflow

A practical differential-equation calculation usually looks like this:

1. choose an integral family and reduce it to masters;
2. pick dimensionless variables and factor out overall mass dimensions;
3. derive $\partial_{x_i}\mathbf M=A_i\mathbf M$ by differentiating under the integral sign and reducing by IBP;
4. look for a better basis $\mathbf F$;
5. identify singular points and possible letters;
6. fix boundary data in a safe kinematic region or limit;
7. solve in the desired region;
8. analytically continue to the physical region;
9. check limits, cuts, pole structure, and numerical values.

The method is powerful because steps 1–4 are mostly algebraic, while steps 5–9 expose the analytic content.

## Common pitfalls

**Differentiating the answer you wish you had.** The method differentiates integral representations or reduced masters, not guessed final expressions.

**Forgetting to reduce derivatives.** Derivatives produce integrals with shifted powers or numerators. The system closes only after IBP reduction.

**Ignoring boundary constants.** A differential equation without boundary data is not an evaluated integral.

**Confusing singular points with physical cuts.** The matrix may have singularities that are spurious or pseudo-thresholds. The physical sheet is fixed by boundary data and the $i\epsilon$ prescription.

**Assuming canonical form always exists.** Many important systems are not expressible in ordinary polylogarithmic canonical $d\log$ form.

**Expanding in ε too early.** Sometimes the all-$\epsilon$ structure is needed to see cancellations, choose a good basis, or fix boundary behavior.

**Trusting a numerical path through a singularity.** Numerical integration of the system must respect branch cuts, thresholds, and regularity conditions.

## Relations to other pages

- [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explains the basis objects whose differential equations are solved here.
- [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/) supplies the reduction step that closes derivatives on the master basis.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) and [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/) provide representations useful for deriving boundary values and seeing singularities.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) gives simple examples where the differential-equation logic reduces to dimensional analysis and elementary logarithms.
- Unitarity cuts for integrals connect discontinuities of master integrals to cut phase-space integrals.
- Landau singularities explain how possible singularities arise from pinch conditions in parameter space.

## Research status

- **Established:** Differential equations for master integrals are a standard tool in multi-loop perturbative QFT and precision collider calculations.
- **Active:** Modern work focuses on choosing canonical or otherwise optimal bases, handling elliptic and more general periods, constructing alphabets, improving numerical evolution, using finite fields and algebraic geometry, and connecting differential systems to intersection theory and $D$-modules.
- **Convention-dependent:** The matrices $A_i$, the letters, and even the number and appearance of singularities can change under basis transformations. Physical amplitudes must be basis-independent after all masters and coefficients are combined.

## Exercises

### Exercise 1: Massless bubble differential equation

Let

$$
B(s)=C(\epsilon)\mu^{2\epsilon}(-s-i\epsilon)^{-\epsilon}.
$$

Show that

$$
s\frac{d}{ds}B(s)=-\epsilon B(s).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate directly:

$$
\frac{d}{ds}(-s-i\epsilon)^{-\epsilon}
= -\epsilon(-s-i\epsilon)^{-\epsilon-1}(-1)
=\epsilon(-s-i\epsilon)^{-\epsilon-1}.
$$

Multiplying by $s$ gives

$$
s\frac{dB}{ds}
= C(\epsilon)\mu^{2\epsilon}\epsilon s(-s-i\epsilon)^{-\epsilon-1}.
$$

For the differential equation in the physical variable, this is equivalently

$$
\frac{dB}{d\log(-s-i\epsilon)}=-\epsilon B.
$$

Since $d\log(-s-i\epsilon)=ds/s$ away from the infinitesimal prescription, we write

$$
{s\frac{dB}{ds}=-\epsilon B.}
$$

</details>

### Exercise 2: Basis transformation

Suppose $d\mathbf M=A\mathbf M$ and $\mathbf M=T\mathbf F$. Derive the transformed connection

$$
A_F=T^{-1}AT-T^{-1}dT.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate $\mathbf M=T\mathbf F$:

$$
d\mathbf M=dT\,\mathbf F+T\,d\mathbf F.
$$

Using $d\mathbf M=A\mathbf M=AT\mathbf F$, we get

$$
dT\,\mathbf F+T\,d\mathbf F=AT\mathbf F.
$$

Multiplying by $T^{-1}$ gives

$$
d\mathbf F=(T^{-1}AT-T^{-1}dT)\mathbf F.
$$

Thus

$$
{A_F=T^{-1}AT-T^{-1}dT.}
$$

</details>

### Exercise 3: First order in canonical form

Let

$$
dF=\epsilon\,d\log x\,F,
\qquad F(1,
\epsilon)=1.
$$

Solve $F$ through $O(\epsilon^2)$.

<details>
<summary><strong>Solution</strong></summary>

The exact solution is

$$
F(x,
\epsilon)=\exp(\epsilon\log x)=x^\epsilon.
$$

Expanding gives

$$
F(x,
\epsilon)=1+
\epsilon\log x+
\frac{\epsilon^2}{2}\log^2x+O(\epsilon^3).
$$

This is the one-letter, one-master version of iterated-integral solving.

</details>

### Exercise 4: Why derivatives raise propagator powers

For a denominator $D(x)$, show that differentiating $D^{-\nu}$ with respect to $x$ raises the denominator power.

<details>
<summary><strong>Solution</strong></summary>

By the chain rule,

$$
\frac{\partial}{\partial x}D^{-\nu}
=-\nu D^{-\nu-1}\partial_xD.
$$

Thus the differentiated integrand contains $D^{-\nu-1}$, so the power of $D$ in the denominator has increased by one. The numerator factor $\partial_xD$ is then handled by algebra and IBP reduction.

</details>

### Exercise 5: Flatness condition

For two variables $x$ and $y$, suppose

$$
\partial_x\mathbf M=A_x\mathbf M,
\qquad
\partial_y\mathbf M=A_y\mathbf M.
$$

Show that commuting mixed derivatives implies

$$
\partial_xA_y-
\partial_yA_x+[A_y,A_x]=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\partial_x\partial_y\mathbf M
=\partial_x(A_y\mathbf M)
=(\partial_xA_y)\mathbf M+A_yA_x\mathbf M,
$$

and

$$
\partial_y\partial_x\mathbf M
=\partial_y(A_x\mathbf M)
=(\partial_yA_x)\mathbf M+A_xA_y\mathbf M.
$$

Since mixed derivatives commute, the difference must vanish:

$$
(\partial_xA_y-
\partial_yA_x+A_yA_x-A_xA_y)\mathbf M=0.
$$

Therefore

$$
\partial_xA_y-
\partial_yA_x+[A_y,A_x]=0.
$$

This is the component form of $dA-A\wedge A=0$ for the convention $d\mathbf M=A\mathbf M$.

</details>

## References

- A. V. Kotikov, early papers on the differential-equation method for Feynman integrals, and “Differential equations and Feynman integrals,” 2021 review.
- E. Remiddi, “Differential equations for Feynman graph amplitudes,” *Nuovo Cimento A* **110** (1997), 1435–1452.
- T. Gehrmann and E. Remiddi, “Differential equations for two-loop four-point functions,” *Nuclear Physics B* **580** (2000), 485–518.
- J. M. Henn, “Multiloop integrals in dimensional regularization made simple,” *Physical Review Letters* **110** (2013), 251601.
- V. A. Smirnov, *Evaluating Feynman Integrals* and *Feynman Integral Calculus*, for parameter representations, recurrence methods, and differential equations.
- S. Laporta, “High-precision calculation of multi-loop Feynman integrals by difference equations,” *International Journal of Modern Physics A* **15** (2000), 5087–5159.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Appendix B, for practical regularization and one-loop integral conventions.

## Version history

- **2026-06-12:** Initial polished draft. Introduced master-integral differential equations, canonical $d\log$ form, basis transformations, boundary data, singularities, and a massless-bubble example.
