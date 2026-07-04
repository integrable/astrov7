---
title: "Integration-by-Parts Identities"
description: "A practical introduction to IBP identities for loop integrals: total derivatives, integral families, sectors, master integrals, Laporta reduction, and basic recurrence examples."
sidebar:
  label: "IBP Identities"
  order: 5
level: Graduate
status: "Polished draft"
source: "Tkachov 1981; Chetyrkin–Tkachov 1981; Laporta 2000; Smirnov, Feynman Integral Calculus; Srednicki 2007, sections 19–20; Schwartz 2014, Appendix B"
topics:
  - integration by parts identities
  - loop integrals
  - master integrals
  - Laporta algorithm
  - dimensional regularization
canonicalTopics:
  - integration-by-parts-identities
  - ibp-reduction
  - master-integrals
  - laporta-algorithm
  - integral-families
researchStatus:
  established:
    - "IBP identities are standard exact linear relations among dimensionally regularized loop integrals and are the main reduction technology for modern multi-loop calculations."
  active:
    - "Efficient IBP reduction remains an active computational frontier, involving finite fields, syzygy methods, intersection theory, canonical differential equations, numerical unitarity, and large-scale symbolic reconstruction."
---

## Summary

**Integration-by-parts identities**, usually called **IBP identities**, are linear relations among loop integrals obtained from total derivatives in loop-momentum space. In dimensional regularization, the basic statement is

$$
0=
\int \prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}\,
\frac{\partial}{\partial \ell_i^\mu}
\left[
\frac{v^\mu}{D_1^{\nu_1}\cdots D_N^{\nu_N}}
\right].
$$

Here $\ell_i$ is one of the loop momenta, $v^\mu$ is chosen from loop and external momenta, and the $D_a$ are propagator denominators. Expanding the derivative relates integrals whose propagator powers differ by integers.

The result is a huge linear system. Solving it reduces complicated integrals to a finite set of **master integrals**:

$$
I(\nu_1,\ldots,\nu_N)
=
\sum_{k} c_k(d,\{s\},\{m^2\})\,M_k.
$$

The coefficients $c_k$ are rational functions of the dimension, masses, and kinematic invariants. The master integrals $M_k$ must then be evaluated by other methods: Feynman parameters, Schwinger parameters, differential equations, Mellin–Barnes methods, expansion by regions, direct numerical integration, or known analytic formulas.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Integration-by-parts identities turn total derivatives into linear relations among integral families and reduce them to master integrals](/figures/perturbative-qft/integration-by-parts-identities.svg)

<figcaption>

IBP reduction starts with an integral family, generates total-derivative identities, solves the resulting linear system, and expresses all integrals in the family through master integrals. The master integrals still have to be evaluated, usually with differential equations, boundary conditions, cuts, limits, or direct parameter integration.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/), [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/), and [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/).

You should also be comfortable with differentiating rational functions and with the idea that dimensional regularization discards scaleless integrals.

## Core idea

Ordinary integration by parts says

$$
\int dx\,\frac{d}{dx}f(x)=f(\infty)-f(-\infty).
$$

If the boundary term vanishes, the integral of the total derivative is zero. IBP identities apply this idea to loop-momentum integrals. In dimensional regularization, total derivatives of the form used in loop-integral reduction are taken to have vanishing surface terms, provided the integral family is treated consistently.

For a one-loop integral, a simple identity is

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\partial}{\partial\ell^\mu}
\left(\frac{\ell^\mu}{D^\nu}\right),
\qquad
D=\ell^2-m^2+i\epsilon.
$$

Expanding gives

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\left[
\frac{d}{D^\nu}
-
\frac{2\nu\ell^2}{D^{\nu+1}}
\right].
$$

Using $\ell^2=D+m^2-i\epsilon$, this becomes a recurrence relation:

$$
(d-2\nu)T_\nu-2\nu m^2T_{\nu+1}=0,
$$

where

$$
T_\nu\equiv
\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2-m^2+i\epsilon)^\nu}.
$$

That is the whole idea in miniature: total derivatives produce identities that shift denominator powers.

## Setup and conventions

We work in qft.org mostly-minus conventions and use dimensional regularization. A general $L$-loop integral family is written

$$
I(\nu_1,\ldots,\nu_N)
=
\mu^{2L\epsilon}
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}},
$$

with

$$
d=4-2\epsilon.
$$

The denominators $D_a$ are quadratic forms in loop and external momenta, usually of the form

$$
D_a=q_a^2-m_a^2+i\epsilon.
$$

The exponents $\nu_a$ are integers. Positive $\nu_a$ denote denominator powers. Zero $\nu_a$ means the corresponding denominator is absent. Negative $\nu_a$ represents numerator factors:

$$
D_a^{-(-n)}=D_a^n
\qquad
(n>0).
$$

In a realistic family, the $D_a$ are chosen not only to include physical propagators, but also enough auxiliary denominators to represent irreducible scalar products in the numerator.

:::note[Integral family]
An integral family is a coordinate system on a set of loop integrals. It contains physical propagators, possible subtopologies, and numerator structures. A good family makes all scalar products expressible in terms of denominators and external invariants.
:::

## The general IBP identity

Let

$$
F(\ell_1,\ldots,\ell_L)
=
\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}}.
$$

For any loop momentum $\ell_i$ and any vector $v^\mu$ built from loop and external momenta,

$$
0=
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}\,
\frac{\partial}{\partial \ell_i^\mu}\left(v^\mu F\right).
$$

Expanding the derivative gives

$$
0=
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\left[
(\partial_{\ell_i}\cdot v)F
+v^\mu\frac{\partial F}{\partial \ell_i^\mu}
\right].
$$

Since

$$
\frac{\partial F}{\partial \ell_i^\mu}
=
-F\sum_{a=1}^{N}\nu_a
\frac{\partial_{\ell_i^\mu}D_a}{D_a},
$$

we obtain

$$
0=
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}}
\left[
\partial_{\ell_i}\cdot v
-
\sum_{a=1}^{N}\nu_a\frac{v\cdot\partial_{\ell_i}D_a}{D_a}
\right].
$$

The numerator factors $v\cdot\partial_{\ell_i}D_a$ are scalar products. Once they are rewritten in terms of denominators and irreducible scalar products, the identity becomes a linear relation among integrals with shifted powers.

A typical term looks like

$$
\frac{D_b}{D_a}\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}}
=
I(\nu_1,\ldots,\nu_a+1,\ldots,\nu_b-1,\ldots,\nu_N).
$$

The bookkeeping can look fussy, but the operation is purely algebraic.

## Why dimensional regularization makes this work

The statement that total derivatives integrate to zero is delicate in divergent integrals. Dimensional regularization supplies a consistent analytic continuation in $d$ where the formal manipulations can be interpreted algebraically.

The same logic underlies the familiar statement that scaleless integrals vanish:

$$
\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2+i\epsilon)^a}=0.
$$

An IBP proof is short. Define

$$
J_a=
\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2+i\epsilon)^a}.
$$

Then

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\partial}{\partial\ell^\mu}
\left(\frac{\ell^\mu}{(\ell^2+i\epsilon)^a}\right)
=(d-2a)J_a.
$$

For generic $d$ and $a$, this implies $J_a=0$ after analytic continuation. This does not mean the integral was convergent in the ordinary sense. It means dimensional regularization assigns zero to a scale-free object because there is no mass or momentum scale from which to build a nonzero answer.

:::caution[Cutoffs change surface terms]
With a hard momentum cutoff, total derivatives can produce boundary terms at $|\ell|=\Lambda$. IBP identities in their standard algebraic form are statements in dimensional regularization, or in regulators that preserve the needed shift and surface-term properties.
:::

## A clean example: massive tadpole recurrence

Let

$$
T_\nu(m^2)
=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{(\ell^2-m^2+i\epsilon)^\nu}.
$$

Use

$$
0=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{\partial}{\partial\ell^\mu}
\left[
\frac{\ell^\mu}{(\ell^2-m^2+i\epsilon)^\nu}
\right].
$$

Expanding,

$$
0=
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\left[
\frac{d}{D^\nu}
-
\frac{2\nu\ell^2}{D^{\nu+1}}
\right],
\qquad
D=\ell^2-m^2+i\epsilon.
$$

Since

$$
\ell^2=D+m^2-i\epsilon,
$$

we get

$$
0=dT_\nu-2\nu T_\nu-2\nu m^2T_{\nu+1}.
$$

Thus

$$
T_{\nu+1}(m^2)
=
\frac{d-2\nu}{2\nu m^2}T_\nu(m^2).
$$

For $\nu=1$,

$$
T_2(m^2)=\frac{d-2}{2m^2}T_1(m^2).
$$

So every higher-power tadpole reduces to the master tadpole $T_1$, as long as $m^2\ne 0$. The massless case is scaleless and vanishes in dimensional regularization.

## Integral families and irreducible scalar products

At one loop, Passarino–Veltman reduction can usually eliminate tensor numerators directly. At two loops and beyond, numerator algebra becomes more complicated because not every scalar product can be expressed as a linear combination of propagator denominators and external invariants.

An **irreducible scalar product** is a loop-momentum scalar product that cannot be rewritten using the chosen propagator denominators. For example, in a two-loop family with loop momenta $\ell_1,\ell_2$ and external momentum $p$, possible scalar products include

$$
\ell_1^2,
\qquad
\ell_2^2,
\qquad
\ell_1\cdot\ell_2,
\qquad
\ell_1\cdot p,
\qquad
\ell_2\cdot p.
$$

If the physical denominators do not span all of these scalar products, one introduces auxiliary denominators so that every numerator can be encoded as an integer index in the family.

For example, an auxiliary denominator might be

$$
D_{\mathrm{aux}}=\ell_1\cdot p
$$

or, more commonly, a quadratic expression chosen so that all $D_a$ resemble propagators. Negative powers of auxiliary denominators then represent numerator factors.

This is not a physical change in the theory. It is bookkeeping.

## Sectors and subtopologies

Given an integral family

$$
I(\nu_1,\ldots,\nu_N),
$$

the **sector** records which denominators are present with positive power. For example,

$$
\nu_a>0
$$

means line $a$ belongs to the sector, while $\nu_a\le 0$ means it is absent or appears as a numerator factor.

A sector can be represented by a binary vector

$$
\theta_a=
\begin{cases}
1,& \nu_a>0,\\
0,& \nu_a\le 0.
\end{cases}
$$

Lower sectors correspond to subtopologies obtained by deleting propagators. IBP identities mix integrals within a sector and often relate them to lower sectors. This triangular structure is what makes systematic elimination possible.

For a simple diagram, one can reduce by hand. For realistic multi-loop diagrams, there may be thousands or millions of integrals in many sectors. Then one needs an ordering principle.

## The Laporta idea

The **Laporta algorithm** is the systematic reduction strategy behind many practical IBP calculations. The idea is simple:

1. Generate many IBP identities for many integer index choices.
2. Assign an ordering that says which integrals are more complicated.
3. Solve the linear equations for more complicated integrals in terms of simpler ones.
4. Continue until no further reduction is possible.
5. Declare the remaining unreduced integrals to be master integrals.

A common complexity ordering penalizes:

- more positive propagator powers;
- more numerator powers;
- higher sectors;
- more dots on propagators;
- integrals further from the target physical integrals.

Here a **dot** means a propagator with power greater than one, such as $D_a^{-2}$ in the denominator notation.

The output has the form

$$
I_j=
\sum_k c_{jk}(d,\{s\},\{m^2\})M_k,
$$

where $M_k$ are master integrals. The coefficients can be large rational functions. Their size is often the computational bottleneck.

## Master integrals are not optional mysteries

A master integral is not necessarily physically special. It is an integral not reducible by the chosen IBP system within the chosen family and ordering. A different basis of master integrals can be more convenient.

For example, a basis might be chosen to:

- make differential equations simple;
- make singularities manifest;
- have uniform transcendental weight;
- avoid spurious denominators;
- behave well in certain kinematic limits;
- make numerical evaluation stable.

IBP reduction answers one question: which integrals do I really need to evaluate? It does not automatically answer a second question: what are those master integrals equal to? That second question is the subject of differential equations for integrals, boundary conditions, unitarity cuts, analytic continuation, asymptotic expansions, and numerical methods.

## Differential equations after IBP

A standard use of IBP is to derive differential equations for master integrals. Suppose the masters depend on a kinematic variable $x$, such as

$$
x=\frac{s}{m^2}.
$$

Differentiate a master integral:

$$
\frac{d}{dx}M_i(x).
$$

The derivative acts on denominators and produces integrals in the same family with shifted powers and numerator factors. IBP reduction then expresses those derivatives back in the master basis:

$$
\frac{d}{dx}\vec M(x,\epsilon)
=
A(x,\epsilon)\vec M(x,\epsilon).
$$

This converts integral evaluation into solving a system of differential equations. Boundary conditions come from simple limits, regularity, thresholds, direct integration at special points, or physical constraints.

In especially nice bases, the system can be brought to a canonical form

$$
d\vec M(\epsilon)=
\epsilon\,d\mathbb A\,\vec M(\epsilon),
$$

where $d\mathbb A$ has logarithmic singularities. Such a form makes the transcendental structure of the answer far more transparent. Not every integral family admits a simple canonical form in ordinary polylogarithms; elliptic and more general structures occur in important examples.

## IBP versus Passarino–Veltman reduction

Passarino–Veltman reduction and IBP reduction both simplify loop integrals, but they solve different problems.

| Feature | Passarino–Veltman reduction | IBP reduction |
|---|---|---|
| Natural domain | One loop | Any loop order |
| Basic input | Tensor numerator | Integral family |
| Main identity | Lorentz covariance and denominator differences | Total derivatives in loop momentum |
| Output | Scalar one-loop functions | Master integrals |
| Main algebraic object | Gram matrix | Large linear system |
| Common issue | Small Gram determinants | Equation swell and large rational functions |

At one loop, the methods overlap. IBP can reduce many one-loop integrals too. But Passarino–Veltman reduction is usually the cleaner conceptual route for low-rank one-loop tensor integrals, while IBP is the dominant organizing language for multi-loop calculations.

## Boundary terms and doubled propagators

When the derivative hits a denominator,

$$
\partial_{\ell_i^\mu}\frac{1}{D_a^{\nu_a}}
=-\nu_a\frac{\partial_{\ell_i^\mu}D_a}{D_a^{\nu_a+1}},
$$

it raises that denominator power by one. This is how **dotted propagators** appear. For example,

$$
\frac{1}{D_a}
\quad\longrightarrow\quad
\frac{1}{D_a^2}.
$$

This can look like the algebra is making the problem worse before it gets better. That is normal. IBP identities create a web of relations among ordinary propagators, dotted propagators, and numerator integrals. The reduction algorithm then solves the web in a chosen direction.

A good complexity ordering ensures that dotted or numerator-heavy integrals are eliminated in favor of simpler targets and master integrals.

## Symmetries of integral families

Before launching a large IBP reduction, one should use graph and family symmetries. Examples include:

- exchange of equal-mass internal lines;
- reversal of loop momentum;
- permutations of identical external legs;
- shifts and relabelings of loop momenta;
- crossing symmetries of the amplitude.

These symmetries identify integrals that look different in index notation but are actually the same. Using them early can dramatically reduce the size of the linear system.

For a simple example, the equal-mass bubble integral satisfies

$$
\int_\ell\frac{1}{(\ell^2-m^2)((\ell+p)^2-m^2)}
=
\int_\ell\frac{1}{(\ell^2-m^2)((\ell-p)^2-m^2)}
$$

by the loop-momentum change $\ell\mapsto -\ell$. Such relabelings are trivial by hand and precious in automation.

## Common pitfalls

**Thinking IBP evaluates integrals.** IBP reduction expresses many integrals in terms of master integrals. The masters still require evaluation.

**Choosing a poor integral family.** If scalar products cannot be represented cleanly, the reduction becomes awkward or incomplete.

**Ignoring scaleless sectors.** Many sectors vanish in dimensional regularization. Removing them early simplifies the system.

**Forgetting numerator integrals.** Negative indices are not exotic; they are how irreducible scalar products are represented.

**Overcounting equivalent integrals.** Family symmetries can identify many integrals. Missing them makes the system larger than necessary.

**Trusting surface-term arguments outside their regulator.** Standard IBP identities rely on dimensional-regularization logic. A hard cutoff requires boundary care.

**Calling the master basis unique.** Master integrals are basis-dependent. A good master basis can make the difference between a readable answer and algebraic soup.

**Reducing gauge-dependent pieces blindly.** It is often better to reduce a gauge-invariant amplitude or a carefully organized set of diagrams, because cancellations can be hidden at the level of individual integrals.

## Relations to other pages

- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains why scaleless integrals vanish and why shift-invariant manipulations are reliable.
- [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/) and [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/) are the one-loop tensor-reduction relatives of IBP.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) and [Schwinger Parameters](/perturbative-qft/loop-integral-technology/schwinger-parameters/) give direct integral representations useful for evaluating master integrals.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) gives a concrete scalar integral that can also be studied through IBP recurrence relations.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how local counterterms combine with loop integrals after reduction.
- Later pages on master integrals, differential equations, unitarity cuts, and Landau singularities develop the evaluation side of the story.

## Research status

- **Established:** IBP identities are exact algebraic consequences of total derivatives in dimensionally regularized loop integrals and are central to modern multi-loop calculations.
- **Convention-dependent:** Integral-family definitions, numerator conventions, normalization factors, and master-basis choices vary between papers and software packages.
- **Technically delicate:** Intermediate expressions can become enormous, contain spurious singularities, or obscure cancellations until a good basis or ordering is chosen.
- **Active:** Efficient IBP reduction is an active computational area, with modern work using finite-field methods, syzygy and module techniques, intersection theory, numerical unitarity, and optimized master-integral bases.

## Exercises

### Exercise 1: Massive tadpole recurrence

Derive

$$
T_{\nu+1}(m^2)=\frac{d-2\nu}{2\nu m^2}T_\nu(m^2)
$$

from

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\partial}{\partial\ell^\mu}\left(\frac{\ell^\mu}{(\ell^2-m^2+i\epsilon)^\nu}\right).
$$

<details>
<summary><strong>Solution</strong></summary>

Let

$$
D=\ell^2-m^2+i\epsilon.
$$

Then

$$
\frac{\partial}{\partial\ell^\mu}\ell^\mu=d,
\qquad
\frac{\partial}{\partial\ell^\mu}D=2\ell_\mu.
$$

Therefore

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\left[
\frac{d}{D^\nu}-\nu\frac{\ell^\mu 2\ell_\mu}{D^{\nu+1}}
\right]
=
\int\frac{d^d\ell}{(2\pi)^d}
\left[
\frac{d}{D^\nu}-\frac{2\nu\ell^2}{D^{\nu+1}}
\right].
$$

Use

$$
\ell^2=D+m^2-i\epsilon.
$$

Suppressing the infinitesimal in numerator algebra,

$$
\frac{\ell^2}{D^{\nu+1}}
=
\frac{1}{D^\nu}+m^2\frac{1}{D^{\nu+1}}.
$$

Thus

$$
0=dT_\nu-2\nu T_\nu-2\nu m^2T_{\nu+1}.
$$

Rearranging gives

$$
T_{\nu+1}=\frac{d-2\nu}{2\nu m^2}T_\nu.
$$

</details>

### Exercise 2: Scaleless integral from IBP

Use an IBP identity to show that

$$
J_a=\int\frac{d^d\ell}{(2\pi)^d}\frac{1}{(\ell^2+i\epsilon)^a}
$$

vanishes in dimensional regularization for generic $a$ and $d$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
0=
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\partial}{\partial\ell^\mu}\left(\frac{\ell^\mu}{(\ell^2+i\epsilon)^a}\right).
$$

Expanding gives

$$
0=\int\frac{d^d\ell}{(2\pi)^d}
\left[
\frac{d}{(\ell^2+i\epsilon)^a}
-
\frac{2a\ell^2}{(\ell^2+i\epsilon)^{a+1}}
\right].
$$

Ignoring the infinitesimal in numerator algebra,

$$
\frac{\ell^2}{(\ell^2+i\epsilon)^{a+1}}
=
\frac{1}{(\ell^2+i\epsilon)^a}.
$$

Therefore

$$
0=(d-2a)J_a.
$$

For generic $d$ and $a$, $d-2a\ne0$, so

$$
J_a=0.
$$

This is the dimensional-regularization statement that scaleless integrals vanish.

</details>

### Exercise 3: General derivative formula

Let

$$
F=\frac{1}{D_1^{\nu_1}\cdots D_N^{\nu_N}}.
$$

Show that

$$
\partial_{\ell_i}\cdot(vF)
=F\left[\partial_{\ell_i}\cdot v
-\sum_{a=1}^{N}\nu_a\frac{v\cdot\partial_{\ell_i}D_a}{D_a}\right].
$$

<details>
<summary><strong>Solution</strong></summary>

Use the product rule:

$$
\partial_{\ell_i}\cdot(vF)
=(\partial_{\ell_i}\cdot v)F+v\cdot\partial_{\ell_i}F.
$$

Now differentiate $F$ logarithmically:

$$
\partial_{\ell_i}F
=F\,\partial_{\ell_i}\log F.
$$

Since

$$
\log F=-\sum_{a=1}^{N}\nu_a\log D_a,
$$

we have

$$
\partial_{\ell_i}\log F
=-\sum_{a=1}^{N}\nu_a\frac{\partial_{\ell_i}D_a}{D_a}.
$$

Therefore

$$
v\cdot\partial_{\ell_i}F
=-F\sum_{a=1}^{N}\nu_a\frac{v\cdot\partial_{\ell_i}D_a}{D_a}.
$$

Substituting into the product rule gives the desired identity.

</details>

### Exercise 4: Number of basic IBP vectors

For an $L$-loop integral with $E$ independent external momenta, suppose you choose $v^\mu$ from the set of all loop momenta and independent external momenta. How many basic IBP identities do you get before choosing index values?

<details>
<summary><strong>Solution</strong></summary>

There are $L$ choices for the derivative momentum $\ell_i$:

$$
i=1,\ldots,L.
$$

The vector $v^\mu$ can be chosen from $L$ loop momenta and $E$ independent external momenta, giving

$$
L+E
$$

choices. Thus the number of basic derivative-vector pairs is

$$
{L(L+E).}
$$

Each pair gives a family of identities after substituting different integer values of the indices $\nu_a$.

</details>

### Exercise 5: Dots from differentiation

Show explicitly why differentiating a propagator factor produces a dotted propagator.

<details>
<summary><strong>Solution</strong></summary>

For a denominator $D_a$ with power $\nu_a$,

$$
\frac{\partial}{\partial\ell_i^\mu}\left(D_a^{-\nu_a}\right)
=-\nu_a D_a^{-\nu_a-1}\frac{\partial D_a}{\partial\ell_i^\mu}.
$$

The power has changed from $\nu_a$ to $\nu_a+1$ in the denominator:

$$
D_a^{-\nu_a}
\quad\longrightarrow\quad
D_a^{-\nu_a-1}.
$$

For example, if $\nu_a=1$,

$$
\frac{1}{D_a}
\quad\longrightarrow\quad
\frac{1}{D_a^2}.
$$

This is a dotted propagator. IBP identities often generate dotted integrals even when the original Feynman diagram has only simple propagators.

</details>

## References

- F. V. Tkachov, “A Theorem on Analytical Calculability of Four-Loop Renormalization Group Functions,” *Physics Letters B* **100** (1981), 65–68.
- K. G. Chetyrkin and F. V. Tkachov, “Integration by Parts: The Algorithm to Calculate Beta Functions in Four Loops,” *Nuclear Physics B* **192** (1981), 159–204.
- S. Laporta, “High-Precision Calculation of Multi-Loop Feynman Integrals by Difference Equations,” *International Journal of Modern Physics A* **15** (2000), 5087–5159.
- V. A. Smirnov, *Feynman Integral Calculus*, for systematic integral-family, IBP, and asymptotic-expansion techniques.
- V. A. Smirnov, *Analytic Tools for Feynman Integrals*, for a broader modern treatment of IBP, Mellin–Barnes methods, and master integrals.
- Mark Srednicki, *Quantum Field Theory*, sections 19–20, for perturbation theory to all orders and one-loop scalar scattering examples.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Appendix B, for regularization and parameter-integral technology used in loop calculations.

## Version history

- **2026-06-12:** Initial polished draft. Introduces total-derivative IBP identities, integral families, sectors, dotted propagators, master integrals, Laporta reduction, and the massive tadpole recurrence as the main worked example.
