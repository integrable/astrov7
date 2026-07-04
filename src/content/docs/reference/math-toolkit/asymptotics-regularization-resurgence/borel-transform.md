---
title: "Borel Transform"
description: "Explains the Borel transform of divergent perturbation series, Borel–Laplace summation, singularities in the Borel plane, lateral sums, Stokes phenomena, large-order behavior, and the QFT interpretation in terms of instantons, renormalons, and transseries sectors."
sidebar:
  label: "Borel Transform"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard references on asymptotic analysis, nonperturbative QFT, instantons, large-order behavior, renormalons, and resurgence, including Zinn-Justin, Coleman, Marino, Shifman, Polyakov, Weinberg, Srednicki, Schwartz, Zee, and modern resurgence literature."
topics:
  - Borel transform
  - Borel summation
  - Borel plane
  - divergent series
  - large-order behavior
  - Stokes phenomenon
  - nonperturbative effects
  - instantons
  - renormalons
  - transseries
canonicalTopics:
  - borel-transform
  - borel-summation
  - borel-plane
  - divergent-series
  - large-order-behavior
  - stokes-phenomenon
  - nonperturbative-effect
  - instanton
  - renormalon
  - transseries
researchStatus:
  established:
    - "Borel transforms and Borel–Laplace summation are standard tools for assigning meaning to many factorially divergent asymptotic series."
    - "Singularities of the Borel transform control large-order growth and produce exponentially small ambiguities when they lie on the summation ray."
  active:
    - "The full resurgent structure of general quantum field theories, especially gauge theories with renormalons, massless modes, complex saddles, and nontrivial operator-product expansions, remains an active research area."
---

## Summary

Perturbation theory in QFT usually diverges. That is not a bug in the typesetting. It is a mathematical signal. A typical formal expansion

$$
F(g)\sim\sum_{n=0}^{\infty}a_n g^n
$$

has coefficients growing like

$$
a_n\sim C A^{-n}\Gamma(n+\beta)
$$

rather than like the coefficients of a convergent Taylor series. The Borel transform divides out the dangerous $n!$-type growth:

$$
\widehat F(t)=\sum_{n=0}^{\infty}{a_n\over n!}t^n.
$$

If $\widehat F(t)$ can be analytically continued and does not grow too quickly, one tries to reconstruct a function by the Borel–Laplace integral

$$
\mathcal S_\theta F(g)
=
{1\over g}
\int_0^{e^{i\theta}\infty}dt\,e^{-t/g}\widehat F(t).
$$

This operation turns a divergent series into an analytic object — unless singularities in the Borel plane block the integration contour. When they do, the obstruction is not just a technical nuisance. Its size is typically

$$
\sim e^{-A/g},
$$

which is exactly the scale of instantons, tunneling, bounces, renormalons, and other nonperturbative effects.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram from formal perturbation series to Borel transform, analytic continuation in the Borel plane, lateral Laplace sums, Stokes ambiguity, and nonperturbative sectors.](/figures/math-toolkit/borel-transform-singularity-flow.svg)

<figcaption>

The Borel transform turns late perturbative growth into singularities in the Borel plane. Singularities on the Laplace ray force lateral sums and produce ambiguities of order $e^{-A/g}$, which must be cancelled or completed by nonperturbative sectors in a full answer.

</figcaption>
</figure>

This page explains the Borel transform as a practical bridge between divergent perturbation theory and nonperturbative physics. It is deliberately honest about the limits: Borel summation is powerful, but not automatic magic.

## Prerequisites and conventions

You should be comfortable with asymptotic series, contour deformation, analytic continuation, and gamma functions. Useful nearby pages are [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/), [Saddle Points](/math-toolkit/complex-analysis/saddle-points/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/), and [Dimensional Regularization Identities](/math-toolkit/asymptotics-regularization-resurgence/dimensional-regularization-identities/).

The coupling parameter is called $g$. In semiclassical QFT one also sees $g^2$, $\hbar$, $1/N$, inverse volume, or inverse spin as the small parameter. The formulas below adapt by renaming the expansion variable.

When $g>0$ is real, the most common Borel sum is along the positive real $t$ axis:

$$
\mathcal S_0 F(g)
=
{1\over g}\int_0^\infty dt\,e^{-t/g}\widehat F(t).
$$

The direction matters. For complex $g$, the Laplace ray is chosen so that $t/g$ has positive real part and the exponential damps the integral.

## Why factorial growth appears

A convergent power series has coefficients that grow at most exponentially:

$$
|a_n|\lesssim C R^{-n}.
$$

Perturbation theory in QFT often grows factorially. There are several reasons.

First, the number of Feynman diagrams usually grows like $n!$ at high order. Second, path integrals expanded around one saddle often remember other saddles through large-order behavior. Third, in renormalizable QFTs, loop-momentum regions tied to running couplings can generate renormalon growth. Fourth, expansions of differential equations near irregular singular points naturally produce divergent WKB-type series.

The exact mechanism depends on the problem, but the mathematical consequence is similar: the power series does not define $F(g)$ by ordinary summation.

For a model factorial series,

$$
F(g)\sim\sum_{n=0}^{\infty} n!\,g^n,
$$

the terms do not even tend to zero for fixed $g\ne0$. The Borel transform is

$$
\widehat F(t)=\sum_{n=0}^{\infty}t^n={1\over1-t},
$$

inside $|t|<1$. The factorial divergence has become a simple pole at $t=1$. That pole is the new problem — and also the new information.

## The formal Borel transform

Given a formal series

$$
F(g)\sim\sum_{n=0}^{\infty}a_n g^n,
$$

define its Borel transform by

$$
\mathcal B F(t)=\widehat F(t)=\sum_{n=0}^{\infty}{a_n\over n!}t^n.
$$

If the original coefficients behave like $a_n\sim n!A^{-n}$, then the Borel coefficients behave like $A^{-n}$, so the Borel series can have a nonzero radius of convergence. Singularities of $\widehat F(t)$ typically occur at values of $t$ associated with actions or action differences between saddles.

There is also a generalized Borel transform for series with shifted factorial growth,

$$
a_n\sim A^{-n}\Gamma(n+\beta).
$$

One may divide by $\Gamma(n+\beta)$ rather than $n!$. This changes powers in the Laplace kernel but not the central idea: remove the universal factorial growth, study the singularities of the transformed function, and reconstruct by an integral.

For most introductory QFT use, the ordinary $n!$ transform is enough.

## Borel–Laplace reconstruction

The Laplace step uses the identity

$$
\int_0^\infty dt\,e^{-t/g}t^n
=g^{n+1}n!,
\qquad
\operatorname{Re}g>0.
$$

Therefore, if

$$
\widehat F(t)=\sum_{n=0}^{\infty}{a_n\over n!}t^n,
$$

then formally

$$
{1\over g}\int_0^\infty dt\,e^{-t/g}\widehat F(t)
=
{1\over g}\sum_{n=0}^{\infty}{a_n\over n!}
\int_0^\infty dt\,e^{-t/g}t^n
=
\sum_{n=0}^{\infty}a_n g^n.
$$

The right-hand side may diverge, but the left-hand side may exist. When it exists and has the given asymptotic expansion, it is a candidate nonperturbative definition of the series.

A series is **Borel summable along a direction** if the Borel transform can be analytically continued along that direction and the Laplace integral converges. It is **not Borel summable along a direction** if singularities lie on the integration ray or if the growth is too large for the Laplace integral.

## Two toy examples

Consider the alternating factorial series

$$
F_-(g)\sim\sum_{n=0}^{\infty}(-1)^n n!\,g^n.
$$

Its Borel transform is

$$
\widehat F_-(t)=\sum_{n=0}^{\infty}(-t)^n={1\over1+t}.
$$

For $g>0$, the positive real Borel ray has no singularity. The Borel sum is

$$
\mathcal S_0F_-(g)=
{1\over g}\int_0^\infty dt\,{e^{-t/g}\over1+t}.
$$

This integral is well-defined for positive $g$ and has the original divergent series as its asymptotic expansion.

Now consider the non-alternating series

$$
F_+(g)\sim\sum_{n=0}^{\infty} n!\,g^n.
$$

Its Borel transform is

$$
\widehat F_+(t)={1\over1-t}.
$$

The pole at $t=1$ lies directly on the positive integration contour. The Borel integral is ambiguous. One may pass above or below the pole, producing two lateral sums

$$
\mathcal S_{0^+}F_+(g),
\qquad
\mathcal S_{0^-}F_+(g),
$$

whose difference is proportional to

$$
e^{-1/g}.
$$

That exponential is invisible to the original power series. This tiny example contains the whole plot.

## Borel-plane singularities and large order

Suppose the Borel transform has a singularity near $t=A$ of the form

$$
\widehat F(t)\sim {C\over(1-t/A)^\beta}.
$$

Expanding around $t=0$ gives coefficients with large-order behavior

$$
a_n\sim
{C\over\Gamma(\beta)}A^{-n}\Gamma(n+\beta)
\qquad
(n\to\infty),
$$

up to corrections from subleading terms near the same singularity and from more distant singularities.

Thus the nearest Borel singularities control the late perturbative coefficients. This is the sharp version of the slogan:

> Large order knows about nonperturbative physics.

The location $A$ determines the exponential scale $e^{-A/g}$; the nature of the singularity determines powers of $g$ and logarithms multiplying that exponential; the discontinuity across the associated cut determines Stokes data.

## Lateral sums and Stokes jumps

If a Borel singularity lies on the desired ray, the integral must be defined by avoiding the singularity above or below. For $g>0$ and a singularity on $t>0$, define

$$
\mathcal S_{0^\pm}F(g)=
{1\over g}\int_{0}^{\infty e^{\pm i0}}dt\,e^{-t/g}\widehat F(t).
$$

The two answers generally differ:

$$
\mathcal S_{0^+}F(g)-\mathcal S_{0^-}F(g)
\ne0.
$$

For a simple pole

$$
\widehat F(t)\sim {R\over t-A},
\qquad A>0,
$$

the discontinuity has magnitude

$$
\left|\mathcal S_{0^+}F(g)-\mathcal S_{0^-}F(g)\right|
\sim
{2\pi |R|\over g}e^{-A/g},
$$

with the phase depending on contour orientation and residue convention.

This is called a **Stokes jump**. The underlying exact function, when it exists, is not usually jumping. What jumps is the asymptotic decomposition into sectors. Crossing a Stokes ray changes which exponentially small terms are active in the representation.

## What Borel summation can and cannot do

Borel summation can assign a canonical value to many divergent series, especially alternating factorial series and series whose Borel singularities avoid the summation direction.

But Borel summation is not guaranteed. It can fail because:

1. the Borel transform has zero radius of convergence after division by $n!$;
2. the Borel transform cannot be analytically continued far enough;
3. the Borel transform grows too fast at infinity;
4. the summation ray hits singularities;
5. the perturbative series is only one sector of a larger transseries.

In QFT, failure is often informative. A Borel ambiguity of order $e^{-A/g}$ usually says: “you are missing something of this size.” Sometimes that something is an instanton sector. Sometimes it is a renormalon ambiguity that must cancel against an operator-product-expansion matrix element or a definition of a condensate. Sometimes it indicates a false vacuum or an instability.

So the Borel transform is less like a calculator and more like a diagnostic machine. A slightly judgmental diagnostic machine, but a very good one.

## Relation to saddle points

Consider a finite-dimensional integral

$$
Z(g)=\int_\Gamma dx\,e^{-S(x)/g},
\qquad g\to0^+.
$$

Expanding around one saddle $x_0$ produces a perturbative series

$$
Z_{x_0}(g)\sim e^{-S(x_0)/g}\sum_{n=0}^{\infty}a_n g^n.
$$

Other saddles $x_1,x_2,\ldots$ produce sectors

$$
e^{-S(x_i)/g}\sum_{n=0}^{\infty}a_{i,n}g^n.
$$

The Borel singularities of the expansion around $x_0$ often appear at

$$
A_i=S(x_i)-S(x_0).
$$

Thus the perturbative coefficients around one saddle know about action differences to other saddles. This is one of the simplest faces of resurgence.

In path integrals, the same idea becomes subtler because the space of fields is infinite-dimensional, gauge redundancies must be divided out, zero modes must be handled, and renormalization enters. Still, the saddle-point intuition remains indispensable.

## Instantons, bounces, and signs

Instantons often produce contributions like

$$
e^{-S_{\rm inst}/g^2}
$$

rather than $e^{-S/g}$. This just means the natural expansion variable is $g^2$. A perturbative series

$$
F(g)\sim\sum_{n=0}^{\infty}a_n g^{2n}
$$

has a Borel variable conjugate to $g^2$, and singularities at $t=S_{\rm inst}$ produce exponentials $e^{-S_{\rm inst}/g^2}$.

For stable potentials, the perturbative series may be Borel summable along the physical direction. For unstable potentials or false vacua, the Borel ambiguity is related to an imaginary part describing decay. Coleman's bounce physics is the grown-up version of this story: a nonperturbative saddle controls the instability of a metastable state.

The sign pattern of perturbative coefficients matters. Alternating factorial growth often places singularities away from the positive ray and permits Borel summation for positive coupling. Same-sign factorial growth often places singularities on the positive ray and creates an ambiguity.

## Renormalons in QFT

Renormalons are Borel singularities associated not with a finite-action classical saddle but with special loop-momentum regions and running couplings. Roughly speaking, chains of logarithmic loop corrections can produce coefficients growing like

$$
a_n\sim n!\,b_0^n,
$$

where $b_0$ is related to a beta-function coefficient. The resulting Borel singularities appear at locations tied to power corrections and operator dimensions.

There are two broad types:

- **UV renormalons**, associated with large loop momenta;
- **IR renormalons**, associated with small loop momenta.

In asymptotically free theories such as QCD, IR renormalons are especially important because perturbation theory at short distances can carry ambiguities of order

$$
\left({\Lambda_{\rm QCD}\over Q}\right)^p,
$$

which must cancel against nonperturbative matrix elements in an operator product expansion. The perturbative series alone is not the observable; the correctly combined expansion is.

This is why renormalons are both annoying and profound. They say the separation between “perturbative coefficient” and “nonperturbative matrix element” can be scheme-dependent, while the full physical answer is not.

## Borel summation and analytic continuation

The Borel sum depends on a direction $\theta$. For complex $g$, one often defines

$$
\mathcal S_\theta F(g)
=
{1\over g}\int_0^{e^{i\theta}\infty}dt\,e^{-t/g}\widehat F(t),
$$

with the ray chosen so that the exponential damps. As $\theta$ crosses a direction containing a Borel singularity, the lateral sums change by a Stokes automorphism.

This makes Borel summation part of the same analytic-continuation toolkit as branch cuts, contour deformation, dispersion relations, and Wick rotation. The key questions are always:

- Where are the singularities?
- Which sheet are we on?
- Which contour or ray defines the prescription?
- Which discontinuity or ambiguity must be cancelled by another sector?

A Borel sum without these questions is a vibe, not a definition.

## From Borel transforms to transseries

A pure perturbative series has the form

$$
F^{(0)}(g)\sim\sum_{n=0}^{\infty}a_n^{(0)}g^n.
$$

A transseries enlarges this to include exponentially small sectors:

$$
F(g)\sim
\sum_{k\ge0}\sigma^k e^{-kA/g}g^{\beta_k}
\sum_{n=0}^{\infty}a_n^{(k)}g^n,
$$

possibly with logarithms and multiple actions. The parameter $\sigma$ records boundary conditions, contour choices, or nonperturbative data.

The role of the Borel transform is then not merely to sum the $k=0$ sector. It helps reveal how the sectors talk to one another. The large-order behavior of $a_n^{(0)}$ can encode $A$, $\beta_1$, and the coefficients $a_n^{(1)}$ in the first nonperturbative sector. In favorable problems, the web of such relations is called resurgence.

Transseries are covered in the next page of this chapter. The point here is simpler: if the Borel plane has singularities on important rays, perturbation theory is asking for companions.

## A practical workflow

When given a divergent perturbative expansion:

1. Estimate the large-order behavior of $a_n$.
2. Form the Borel transform by dividing by $n!$ or the expected factorial scale.
3. Determine the radius of convergence of the Borel series.
4. Analytically continue the Borel transform beyond its first disk of convergence.
5. Locate singularities in the Borel plane.
6. Check whether the desired Laplace ray crosses singularities.
7. If the ray is clear, compute the Borel sum.
8. If the ray is obstructed, define lateral sums and identify the ambiguity.
9. Look for nonperturbative sectors whose ambiguity can cancel it.
10. Only then ask whether the resulting object matches boundary conditions, physical input, or a nonperturbative definition.

The workflow is not always easy. In real QFT we often do not know enough coefficients to reconstruct the Borel plane. But even partial information can be powerful: the sign pattern, expected instanton actions, OPE dimensions, and renormalization group already constrain the answer.

## Common pitfalls

**Borel transform does not mean Borel sum.** The transform is the series $\widehat F(t)$. The sum requires analytic continuation and a Laplace integral. Many mistakes happen between those two words.

**A pole on the positive axis is not a disaster; it is data.** It means the perturbative sector alone is ambiguous. The ambiguity should be paired with a nonperturbative prescription or sector.

**Borel summability is direction-dependent.** A series can be summable in one angular sector and obstructed in another. Complex coupling changes the story.

**The nearest singularity controls large order, but not everything.** Subleading singularities, branch structure, logarithms, and multi-instanton sectors contribute corrections that can matter in precision resurgence.

**Renormalons are not instantons.** Both can create Borel singularities and factorial growth, but their origins are different. Instantons are saddle configurations; renormalons arise from classes of perturbative momentum regions and running-coupling effects.

**Non-Borel-summable does not mean meaningless.** It means the perturbative series requires a prescription or completion. Lateral sums and transseries are ways to state the missing data precisely.

**Do not infer a unique function from an asymptotic series alone.** Exponentially small functions such as $e^{-A/g}$ have zero perturbative expansion at $g=0$. Perturbation theory needs boundary conditions or nonperturbative input to select the full function.

## Exercises

### Exercise 1: Borel sum of an alternating factorial series

Let

$$
F(g)\sim\sum_{n=0}^{\infty}(-1)^n n!\,g^n.
$$

Find the Borel transform and write the Borel sum for $g>0$.

<details><summary><strong>Solution</strong></summary>

The Borel transform is

$$
\widehat F(t)=\sum_{n=0}^{\infty}(-1)^n t^n={1\over1+t}.
$$

For $g>0$, there is no pole on the positive $t$ axis, so the Borel sum is

$$
\mathcal S_0F(g)=
{1\over g}\int_0^\infty dt\,{e^{-t/g}\over1+t}.
$$

Expanding $1/(1+t)$ near $t=0$ and integrating term by term reproduces the original asymptotic series.

</details>

### Exercise 2: Pole and ambiguity

Suppose

$$
\widehat F(t)={1\over1-t}.
$$

Explain why the positive-axis Borel sum for $g>0$ is ambiguous and estimate the size of the ambiguity.

<details><summary><strong>Solution</strong></summary>

The Borel–Laplace integral would be

$$
{1\over g}\int_0^\infty dt\,{e^{-t/g}\over1-t}.
$$

The pole at $t=1$ lies on the integration contour. Passing above or below the pole gives two lateral sums. Their difference is proportional to the residue of the integrand at $t=1$, hence has magnitude of order

$$
{2\pi\over g}e^{-1/g},
$$

up to a phase convention. The important scale is $e^{-1/g}$, which is invisible to the original power series.

</details>

### Exercise 3: Singularity and large order

Let

$$
\widehat F(t)=(1-t/A)^{-\beta}.
$$

Show that the coefficients $a_n$ of the original series behave like

$$
a_n\sim {A^{-n}\Gamma(n+\beta)\over\Gamma(\beta)}.
$$

<details><summary><strong>Solution</strong></summary>

Use the binomial expansion

$$
(1-z)^{-\beta}=\sum_{n=0}^{\infty}{\Gamma(n+\beta)\over\Gamma(\beta)\Gamma(n+1)}z^n.
$$

With $z=t/A$,

$$
\widehat F(t)=\sum_{n=0}^{\infty}{\Gamma(n+\beta)\over\Gamma(\beta)n!}A^{-n}t^n.
$$

Since the Borel transform is

$$
\widehat F(t)=\sum_{n=0}^{\infty}{a_n\over n!}t^n,
$$

we identify

$$
a_n={\Gamma(n+\beta)\over\Gamma(\beta)}A^{-n}.
$$

For large $n$, this is factorial growth.

</details>

### Exercise 4: Why perturbation theory cannot see an exponential

Show that the function

$$
f(g)=e^{-A/g}
$$

has zero asymptotic power series as $g\to0^+$ for $A>0$.

<details><summary><strong>Solution</strong></summary>

For every integer $N\ge0$,

$$
{e^{-A/g}\over g^N}\to0
\qquad(g\to0^+).
$$

The exponential decays faster than any power. Therefore all coefficients in its asymptotic expansion in powers of $g$ vanish:

$$
e^{-A/g}\sim0+0g+0g^2+\cdots.
$$

This is why two functions can have the same perturbative expansion but differ by nonperturbative terms.

</details>

## References

For asymptotic expansions and Borel summation, see classic references on asymptotic analysis and the treatments in Zinn-Justin and Marino. For instantons, bounces, and large-order behavior, see Coleman and Marino. For renormalons and nonperturbative QFT applications, see standard advanced QFT references, including Shifman and modern EFT/QCD discussions. For the complex-analysis background, see the pages on analytic continuation, branch cuts, Riemann surfaces, and saddle points in this volume.

## Version history

- 2026-06-26: First polished draft. Added definitions, Borel–Laplace reconstruction, toy examples, Borel-plane singularities, lateral sums, Stokes jumps, instanton and renormalon interpretation, transseries motivation, exercises, and a workflow figure.
