---
title: "Master Integrals"
description: "A practical explanation of master integrals in loop calculations: integral families, IBP reduction, basis choice, boundary data, and evaluation strategies."
sidebar:
  label: "Master Integrals"
  order: 6
level: Graduate
status: "Polished draft"
source: "Tkachov 1981; Chetyrkin–Tkachov 1981; Laporta 2000; Smirnov, Feynman Integral Calculus; Henn 2013; Kotikov 2021 review"
topics:
  - master integrals
  - loop integrals
  - integration by parts
  - integral families
  - differential equations
canonicalTopics:
  - master-integrals
  - ibp-reduction
  - loop-integral-basis
  - integral-families
  - boundary-conditions
researchStatus:
  established:
    - "For fixed integral families in dimensional regularization, IBP identities reduce large classes of loop integrals to finite sets of master integrals in standard perturbative calculations."
  active:
    - "Finding optimal master bases, especially for multi-scale, elliptic, hyperelliptic, and high-loop families, remains an active part of precision amplitude research."
---

## Summary

**Master integrals** are the irreducible loop integrals left after algebraic reduction. A typical loop calculation first produces many integrals with different propagator powers and numerator insertions. Integration-by-parts identities, Lorentz-invariance identities, graph symmetries, and dimension-shift relations then express most of them in terms of a much smaller set:

$$
I_{\boldsymbol\nu}
=
\sum_{a=1}^{N_{\mathrm{MI}}}
 c_a(d,\{s\},\{m^2\})\,M_a.
$$

The $M_a$ are the master integrals. The coefficients $c_a$ are rational functions of the spacetime dimension $d=4-2\epsilon$, kinematic invariants, and masses. The master integrals themselves still have to be evaluated.

This distinction is the main workflow separation in modern loop technology: the **reduction problem** expresses every integral through masters, while the **evaluation problem** computes the masters themselves.

A master basis is not unique. A poor basis can make the answer enormous; a good basis can make singularities, limits, branch cuts, and differential equations transparent. So “find the masters” really means two things: identify a spanning set after reduction, and choose a basis adapted to the physics and functions of the problem.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Master integrals arise by reducing an integral family through IBP identities to a finite basis, then evaluating that basis with boundary data and analytic or numerical methods](/figures/perturbative-qft/master-integrals.svg)

<figcaption>

Loop-integral reduction separates a large integral family into algebraic coefficients and a finite master basis. The basis is not unique. Good masters are chosen to make differential equations, boundary conditions, singularities, limits, and transcendental structure as simple as possible.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/), [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/), [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/), and [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/).

The page assumes dimensional regularization and the mostly-minus qft.org convention. We keep factors of $(2\pi)^d$ explicit unless a normalized loop measure is introduced for convenience.

## Core idea

A Feynman diagram rarely gives one integral. It gives an **integral family**: the same denominator structure with different propagator powers and numerator powers. IBP identities relate these integrals. After solving all available linear relations, only finitely many independent representatives remain. These representatives are the master integrals.

The slogan is:

$$
\text{many diagram integrals}
\quad\xrightarrow{\text{IBP reduction}}\quad
\text{few master integrals}.
$$

This is not merely bookkeeping. Master integrals are where analytic structure lives: thresholds, branch cuts, logarithms, polylogarithms, elliptic periods, asymptotic expansions, and boundary constants. Reduction tells you **which functions** you need. Evaluation tells you **what those functions are**.

## Setup and conventions

Consider an $L$-loop integral family with denominators

$$
D_a=D_a(\ell_1,\ldots,\ell_L;p_1,\ldots,p_E;m_a^2),
\qquad a=1,\ldots,N.
$$

A convenient notation is

$$
I(\nu_1,\ldots,\nu_N)
=
\mu^{2L\epsilon}
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}},
\qquad d=4-2\epsilon.
$$

The exponents $\nu_a$ may be positive, zero, or negative. Positive exponents are propagator powers. Zero means the corresponding denominator is absent. Negative exponents represent irreducible numerator factors.

An IBP identity has the form

$$
0=
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\frac{\partial}{\partial \ell_i^\mu}
\left[
\frac{v^\mu}{D_1^{\nu_1}\cdots D_N^{\nu_N}}
\right],
$$

where $v^\mu$ is built from loop and external momenta. Expanding the derivative produces a linear relation among integrals with shifted indices. Repeating this for many choices of $i$, $v^\mu$, and $\boldsymbol\nu$ gives a large linear system.

A master integral is an integral that is not eliminated by the chosen reduction system. More invariantly, master integrals form a basis for the vector space of integrals in a family after quotienting by IBP identities and other accepted relations.

:::note[Master status is basis-dependent]
An integral is not sacred because it is called a master. A different basis can replace it by a linear combination of other integrals. The number of masters for a sector is meaningful once the family and relation set are fixed; the individual representatives are a choice.
:::

## Integral families and sectors

The same graph topology usually contains several **sectors**. A sector records which propagators are present:

$$
S=\{a\mid \nu_a>0\}.
$$

For example, a two-loop family might contain a top sector with all denominators present, and lower sectors obtained by pinching one or more propagators. In diagrams, pinching a propagator means shrinking that line to a point or deleting it from the denominator structure.

IBP reduction generally relates integrals in a sector to integrals in the same sector and lower sectors. This is why reductions are often triangular: one reduces complicated top-sector integrals first, then recursively reduces the lower sectors.

A useful mental picture is that top-sector integrals reduce to masters in the top sector plus lower-sector integrals; the lower sectors are then reduced recursively; and the final master list contains masters from all relevant sectors.

The final answer to a diagram often contains masters from many sectors, not only from the graph that first appeared on paper.

## A first recurrence: the massive tadpole

The simplest example shows the logic without a computer. Define

$$
T_n(m^2)
=
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{D^n},
\qquad
D=\ell^2-m^2+i\epsilon.
$$

Use the total derivative

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\partial}{\partial\ell^\mu}
\left(\frac{\ell^\mu}{D^n}\right).
$$

Expanding gives

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\left[
\frac{d}{D^n}
-
\frac{2n\ell^2}{D^{n+1}}
\right].
$$

Since $\ell^2=D+m^2-i\epsilon$, the $i\epsilon$ part only tracks the pole prescription and does not affect the algebraic recurrence. We obtain

$$
0=(d-2n)T_n-2n m^2 T_{n+1},
$$

or

$$
T_{n+1}=\frac{d-2n}{2n m^2}\,T_n.
$$

Thus all $T_n$ with $n\ge2$ reduce to $T_1$. For this one-propagator family, $T_1$ is the natural master integral. The whole tower of higher powers was never a tower of new functions.

This example is tiny, but it captures the philosophy of IBP reduction: total derivatives turn nearby integrals into recurrence relations, and recurrence relations leave a small irreducible basis.

## Masters are not necessarily hard integrals

A master integral is not necessarily difficult. It is simply not reducible to simpler members of the chosen family using the chosen identities.

At one loop, the familiar scalar functions

$$
A_0(m^2),\qquad
B_0(p^2;m_0^2,m_1^2),\qquad
C_0,\qquad
D_0
$$

can be viewed as master integrals for tadpole, bubble, triangle, and box families. Passarino–Veltman reduction expresses tensor one-loop integrals in terms of these scalar masters.

At higher loops, the master integrals may involve multiple scales and new classes of functions. Some evaluate to logarithms and polylogarithms. Some require elliptic integrals or more general periods. Some are best represented by numerical integration, series expansions, or differential-equation systems.

So the word “master” says **irreducible under reduction**, not **simple in closed form**.

## Choosing a basis

Once a reduction has identified the number of masters, one still has to choose representatives. This choice can dramatically affect the calculation.

A useful basis tries to optimize several goals.

| Goal | What it helps with |
|---|---|
| Simple sectors | Makes reductions and boundary values easier to interpret. |
| Good mass dimension | Keeps equations homogeneous and transparent. |
| Finite normalization | Removes unnecessary $1/\epsilon$ artifacts. |
| Uniform transcendental weight | Simplifies canonical differential equations when available. |
| Simple leading singularities | Often indicates a pure or near-pure basis. |
| Regular limits | Avoids spurious singularities at special kinematics. |
| Physical thresholds visible | Makes analytic continuation and branch cuts easier to track. |

There is no universal best basis. A basis that is excellent for analytic polylogarithmic differential equations may be inconvenient for numerical sector decomposition. A basis that is stable in one physical region may be poor near a threshold or small Gram determinant.

## Boundary data

Master integrals are often computed from differential equations. A differential equation determines a function only up to boundary constants. Therefore a master-integral calculation always needs boundary data.

Common sources of boundary data include:

1. a Euclidean point where the integral is finite and numerically accessible;
2. a soft, collinear, threshold, or large-mass limit;
3. a point where the integral degenerates into lower-loop or lower-point integrals;
4. regularity conditions at pseudo-thresholds;
5. known values of tadpoles, bubbles, or vacuum integrals;
6. unitarity cuts or discontinuities that fix imaginary parts.

Boundary constants are not decoration. They are part of the answer. A beautiful differential equation with no boundary data is a locked door with a polished handle.

## Evaluation strategies

After reduction, the masters may be evaluated in several complementary ways.

### Direct parameter integration

Feynman or Schwinger parameters can combine denominators and expose the Symanzik polynomials. This is often the cleanest route for simple one-loop and two-loop examples, and it is also the starting point for sector decomposition.

### Differential equations

Differentiate master integrals with respect to masses or kinematic invariants. IBP reduction expresses the derivatives back in the master basis, giving a first-order system. This is now one of the central analytic methods for multi-loop integrals.

### Mellin–Barnes representations

Mellin–Barnes integrals separate sums in denominators and are useful for asymptotic expansions and some multi-scale integrals.

### Expansion by regions

In limits with separated scales, the integral is expanded into hard, soft, collinear, potential, or ultrasoft regions. Each region gives a simpler integral, and the sum reproduces the asymptotic expansion.

### Sector decomposition

Parameter space is decomposed so that overlapping singularities factorize. This gives systematic numerical evaluation and is also useful for checking analytic results.

### Difference equations and dimensional recurrences

Some master integrals are efficiently computed through recurrence relations in propagator powers or spacetime dimension.

None of these methods is morally superior. A trustworthy calculation often uses several of them: one method to compute, another to check, and a third to understand limits.

## What the reduction coefficients know

The reduction formula

$$
I_{\boldsymbol\nu}
=
\sum_a c_a(d,\{s\},\{m^2\})M_a
$$

contains only rational coefficients. These coefficients know about algebraic singularities of the chosen basis: Gram determinants, threshold factors, and spurious denominators introduced by the reduction.

They do not by themselves contain the logarithms, branch cuts, or special functions of the final answer. Those live in the master integrals.

This separation is why master integrals are so useful. Once a family's masters are known, many amplitudes can reuse them. The diagram-specific information sits mostly in rational coefficients and numerator algebra; the analytic function space sits in the master basis.

## Checks on a master-integral calculation

Good loop calculations are checked from several directions.

### Dimensional analysis

Every master integral has a mass dimension. If an integral has $L$ loops, $N_+$ positive propagator powers, and numerator dimension $r$, then its dimension is schematically

$$
[I]=Ld-2N_+ + r.
$$

The reduction coefficients must compensate dimensions so that each term has the same total dimension.

### Pole structure

The $\epsilon$ poles should match the expected UV and IR behavior. Unexpected higher-order poles may indicate a bad basis, but they can also signal genuine overlapping divergences.

### Limits

Soft, collinear, threshold, equal-mass, massless, and large-mass limits should agree with simpler calculations or known expansions.

### Cuts

Discontinuities across physical branch cuts should agree with unitarity cuts when the relevant cut is available.

### Numerical comparison

Sector decomposition, direct numerical integration in Euclidean regions, or high-precision differential-equation evolution can check analytic expressions.

A master-integral result that passes only algebraic reduction has not yet earned your trust. The integral still has to behave correctly as a function.

## Common pitfalls

**Confusing master integrals with diagrams.** A master integral is a basis element in an integral family. A Feynman diagram can reduce to many masters, and the same master can appear in many diagrams.

**Thinking the master basis is unique.** The number of masters is meaningful for a fixed family and relation set. The individual representatives are not unique.

**Ignoring lower sectors.** A top-sector diagram often reduces to masters in lower sectors. Pinched propagators are part of the calculation, not garbage.

**Trusting a bad basis too much.** Spurious Gram-determinant poles or artificial $1/\epsilon$ singularities may appear because of a basis choice. They should cancel in physical results, but they can make intermediate expressions unstable.

**Forgetting boundary constants.** Differential equations reduce evaluation to integration plus constants. The constants are physics and analysis, not administrative details.

**Assuming all masters are polylogarithmic.** Many important integrals are elliptic or more complicated. The canonical $d\log$ dream is powerful, but it is not universal.

## Relations to other pages

- [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/) explains the total-derivative relations that reduce integral families.
- [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) explains one of the main methods for evaluating master integrals.
- [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/) is the one-loop tensor-reduction precursor to modern integral-basis methods.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) and [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/) give parameter-space representations often used to evaluate or check masters.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains why total derivatives and scaleless integrals are handled cleanly in the regulator used here.
- Renormalized perturbation theory uses reduced loop integrals after counterterms are included and then combines them into finite physical amplitudes.

## Research status

- **Established:** IBP reduction to master integrals is a standard part of modern perturbative QFT. At one loop and for many two-loop and multi-loop families, master bases and analytic results are known.
- **Active:** Efficient reduction and optimal basis choice are active research areas, especially for multi-scale collider integrals, elliptic sectors, finite-field reconstruction, numerical unitarity, and high-loop amplitudes.
- **Convention-dependent:** The normalization of the master integrals, the choice of basis, and the placement of factors such as $i\pi^{d/2}$ or $(4\pi)^\epsilon e^{-\gamma_E\epsilon}$ vary across the literature. The physical amplitude is independent of these choices when coefficients and masters are transformed consistently.

## Exercises

### Exercise 1: Tadpole recurrence

Starting from

$$
T_n(m^2)=\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2-m^2+i\epsilon)^n},
$$

use

$$
0=\int\frac{d^d\ell}{(2\pi)^d}\frac{\partial}{\partial\ell^\mu}
\left(\frac{\ell^\mu}{D^n}\right),
\qquad D=\ell^2-m^2+i\epsilon,
$$

to derive a recurrence relating $T_{n+1}$ to $T_n$.

<details>
<summary><strong>Solution</strong></summary>

Expanding the derivative gives

$$
0=\int\frac{d^d\ell}{(2\pi)^d}
\left[\frac{d}{D^n}-\frac{2n\ell^2}{D^{n+1}}\right].
$$

Using $\ell^2=D+m^2-i\epsilon$ gives, algebraically,

$$
0=(d-2n)T_n-2n m^2 T_{n+1}.
$$

Therefore

$$
T_{n+1}=\frac{d-2n}{2n m^2}T_n.
$$

Thus the one-propagator massive tadpole family has one natural master, $T_1$.

</details>

### Exercise 2: Dimension of a scalar integral

Consider an $L$-loop scalar integral in $d$ dimensions with $N$ propagators, each appearing to the first power and no numerator. What is its mass dimension?

<details>
<summary><strong>Solution</strong></summary>

Each loop measure $d^d\ell$ has mass dimension $d$, and each propagator denominator has dimension $2$. Therefore

$$
[I]=Ld-2N.
$$

In dimensional regularization, powers of $\mu$ are inserted so that couplings keep their chosen dimensions, but the kinematic dimension of the integral before those bookkeeping factors is $Ld-2N$.

</details>

### Exercise 3: Basis non-uniqueness

Suppose $M_1$ and $M_2$ are two master integrals in a sector. Show that, if $r(d,s)$ is a nonzero rational function, then

$$
M_1'=M_1+r(d,s)M_2,
\qquad
M_2'=M_2
$$

is also a valid master basis.

<details>
<summary><strong>Solution</strong></summary>

The change of basis is invertible as long as $r(d,s)$ is finite in the region where the basis is used. The inverse is

$$
M_2=M_2',
\qquad
M_1=M_1'-r(d,s)M_2'.
$$

Thus the two sets span the same vector space of reduced integrals. The choice may still be bad if $r$ introduces spurious singularities or poor limits, but it is algebraically a valid basis.

</details>

### Exercise 4: Scalars versus tensors

Why are scalar master integrals enough for one-loop Passarino–Veltman reduction, even when the original diagram contains powers of $\ell^\mu$ in the numerator?

<details>
<summary><strong>Solution</strong></summary>

Lorentz covariance decomposes tensor integrals into external momenta and the metric multiplied by scalar coefficient functions. Contractions with external momenta and metrics rewrite numerator scalar products in terms of propagator denominators, masses, and kinematic invariants. After this algebra, the coefficient functions reduce to scalar one-loop functions such as $A_0$, $B_0$, $C_0$, and $D_0$.

</details>

## References

- F. V. Tkachov, “A theorem on analytical calculability of four-loop renormalization group functions,” *Physics Letters B* **100** (1981), 65–68.
- K. G. Chetyrkin and F. V. Tkachov, “Integration by parts: The algorithm to calculate beta functions in 4 loops,” *Nuclear Physics B* **192** (1981), 159–204.
- S. Laporta, “High-precision calculation of multi-loop Feynman integrals by difference equations,” *International Journal of Modern Physics A* **15** (2000), 5087–5159.
- V. A. Smirnov, *Evaluating Feynman Integrals* and *Feynman Integral Calculus*, for systematic treatments of IBP reduction and master-integral evaluation.
- J. M. Henn, “Multiloop integrals in dimensional regularization made simple,” *Physical Review Letters* **110** (2013), 251601, for canonical differential equations and pure integral bases.
- A. V. Kotikov, “Differential equations and Feynman integrals,” 2021 review, for historical and modern perspectives on the differential-equation method.
- M. Srednicki, *Quantum Field Theory*, sections 19–20, for perturbation theory to all orders and one-loop scattering examples.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Appendix B and chapters 15–20, for regularization, loop examples, and practical integral technology.

## Version history

- **2026-06-12:** Initial polished draft. Introduced master integrals as quotient-basis objects after IBP reduction, with a tadpole recurrence, basis-choice guidance, boundary-data discussion, and links to differential equations.
