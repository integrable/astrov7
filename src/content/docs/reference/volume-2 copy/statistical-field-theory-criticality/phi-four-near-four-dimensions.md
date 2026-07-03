---
title: "Phi-Four Near Four Dimensions"
description: "How scalar phi-four theory near its upper critical dimension produces the Wilson–Fisher fixed point and the epsilon expansion."
sidebar:
  label: "Phi-Four Near Four Dimensions"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974, §§4–10; Zinn-Justin 2021, critical phenomena and epsilon-expansion chapters; Schwartz 2014, ch. 23; Altland and Simons 2023, ch. 6."
topics:
  - phi-four theory
  - Wilson–Fisher fixed point
  - epsilon expansion
  - upper critical dimension
  - critical phenomena
  - scalar field theory
canonicalTopics:
  - phi-four-theory
  - wilson-fisher-fixed-point
  - epsilon-expansion
  - upper-critical-dimension
researchStatus:
  established:
    - "Scalar phi-four theory near four dimensions is the standard perturbative route to the Wilson–Fisher fixed point and universal critical exponents."
  active:
    - "High-order resummation, conformal bootstrap, Monte Carlo, functional RG, disorder, boundaries, defects, and long-range variants continue to refine and extend the scalar-universality-class story."
---

## Summary

The scalar $\phi^4$ theory is the local continuum field theory behind the Ising and $O(N)$ universality classes. In Euclidean statistical notation, the $O(N)$ version is

$$
S[\boldsymbol\phi]
=
\int d^d x\left[
\frac12 (\nabla\boldsymbol\phi)^2
+\frac12 r\boldsymbol\phi^2
+\frac{u}{4!}(\boldsymbol\phi^2)^2
-h_a\phi^a
\right],
\qquad a=1,\ldots,N.
$$

For $N=1$ this is the continuum field theory for Ising criticality. Its most important engineering fact is

$$
[u]=4-d.
$$

Thus four dimensions is the **upper critical dimension**: at $d=4$, the quartic interaction is marginal at the Gaussian fixed point; below four dimensions, it is relevant. Writing

$$
\epsilon=4-d,
$$

one can find the nearby interacting critical point perturbatively. In a common dimensionless-coupling convention,

$$
\beta_g\equiv \mu\frac{dg}{d\mu}
=-\epsilon g+\frac{N+8}{6}g^2+O(g^3),
$$

so the nonzero fixed point is

$$
g_* = \frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

This is the **Wilson–Fisher fixed point**. It is the first controlled perturbative model of a nontrivial continuous phase transition.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 54rem;">

![The Gaussian fixed point and Wilson–Fisher fixed point in the r-g plane near four dimensions.](/figures/renormalization-rg-eft/phi-four-near-four-dimensions-flow.svg)

<figcaption>

Near $d=4-\epsilon$, the quartic coupling is weakly relevant at the Gaussian fixed point and flows along the critical surface toward the Wilson–Fisher fixed point. The mass or temperature direction $r-r_c$ is relevant and must be tuned to remain critical.

</figcaption>
</figure>

:::note[The epsilon convention on this page]
In this statistical-field-theory chapter, $\epsilon=4-d$. This differs from the high-energy dimensional-regularization convention $d=4-2\epsilon$ used on some perturbative pages. The symbol is the same because the literature uses it both ways; the definition on the page wins.
:::

## Prerequisites

You should know [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/), [Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/). The companion page [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) explains the saddle-point approximation that this page systematically improves.

## Core idea

The $\phi^4$ model near four dimensions is useful because it is simple enough to calculate and nontrivial enough to teach real critical phenomena.

It is simple because the Gaussian fixed point controls the starting point. At $d=4$, the quartic interaction is marginal. At $d=4-\epsilon$ with $\epsilon\ll1$, the same interaction is only weakly relevant, so the interacting fixed point lies at weak coupling:

$$
g_* = O(\epsilon).
$$

It is nontrivial because the infrared critical point is not a free theory. Correlation functions acquire anomalous scaling, the temperature direction has a shifted RG eigenvalue, and microscopic lattice details disappear into irrelevant couplings. The calculation therefore explains why many short-range systems share the same exponents.

The slogan is

$$
\text{Gaussian fixed point}
+\text{slightly relevant quartic coupling}
\longrightarrow
\text{Wilson–Fisher fixed point}.
$$

## Setup and conventions

This page uses Euclidean statistical conventions:

$$
Z=\int \mathcal D\boldsymbol\phi\,e^{-S[\boldsymbol\phi]}.
$$

For the $O(N)$ model,

$$
\boldsymbol\phi=(\phi^1,\ldots,\phi^N),
\qquad
\boldsymbol\phi^2=\phi^a\phi^a.
$$

The $N=1$ case has $Z_2$ symmetry, $\phi\mapsto -\phi$, and describes the Ising universality class. The $N=2$ and $N=3$ cases describe XY-like and Heisenberg-like universality classes when no extra anisotropies become relevant.

The action is written with a canonical gradient term. A more general Landau–Ginzburg functional begins with

$$
\frac12 Z(\nabla\boldsymbol\phi)^2.
$$

For local power counting one can rescale the field to set $Z=1$. At an interacting fixed point, however, the field has an anomalous scaling dimension; that is real critical data, not a removable normalization.

## Engineering dimensions

At the Gaussian fixed point, the gradient term fixes

$$
[\boldsymbol\phi]=\frac{d-2}{2}.
$$

The mass parameter has engineering dimension

$$
[r]=2,
$$

and the quartic coupling has

$$
[u]=d-4[\boldsymbol\phi]=4-d.
$$

Therefore:

| Dimension | Quartic coupling at the Gaussian fixed point | Consequence |
|---:|---|---|
| $d>4$ | irrelevant | Gaussian fixed point controls leading exponents; mean field works asymptotically. |
| $d=4$ | marginal | logarithmic corrections appear. |
| $d<4$ | relevant | fluctuations drive the critical point to an interacting fixed point. |

This is the first signal that four dimensions is special.

## The one-loop beta function

Define a dimensionless coupling $g$ by absorbing the appropriate power of the renormalization scale and a conventional loop factor. In a common normalization,

$$
\beta_g\equiv \mu\frac{dg}{d\mu}
=-\epsilon g+\frac{N+8}{6}g^2+O(g^3),
\qquad
\epsilon=4-d.
$$

This is the ultraviolet-time convention: increasing $\mu$ moves toward shorter distances. In an infrared Wilsonian convention with

$$
\ell=\log b,
$$

where $b$ is the coarse-graining factor, the flow is

$$
\frac{dg}{d\ell}
=\epsilon g-\frac{N+8}{6}g^2+O(g^3).
$$

The two signs describe the same physics with opposite flow parameters.

At leading order, the fixed points are

$$
g=0,
\qquad
 g_* = \frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

For $\epsilon>0$, the Gaussian fixed point is unstable in the quartic direction under infrared flow, while $g_*$ is stable along the critical surface.

## Where the one-loop structure comes from

The coefficient $N+8$ is not magic; it is the combinatorics of short-distance contractions in the four-point function. At one loop, two quartic vertices can approach each other. The loop momentum becomes large compared with the external momenta, so the diagram cannot resolve the detailed external configuration. Its divergent or cutoff-sensitive part therefore has the same local form as the original quartic interaction,

$$
(\boldsymbol\phi^2)^2.
$$

For $N=1$, the familiar three channels of the one-loop bubble give the coefficient proportional to $3$. For general $O(N)$ symmetry, the index contractions add the extra $N+5$ pieces, producing $N+8$ in this normalization. The exact numerical coefficient depends on how $g$ is normalized, but the existence of the $O(g^2)$ term and the resulting $O(\epsilon)$ fixed point do not.

The linear term $-\epsilon g$ in the ultraviolet beta function is classical dimensional analysis. The quadratic term is the first quantum or fluctuation correction. The Wilson–Fisher fixed point is the balance point between these two effects:

$$
\text{engineering relevance}\quad\leftrightarrow\quad\text{fluctuation screening of the quartic coupling}.
$$

This is the prototype of a controlled interacting fixed point. The interaction is not assumed small forever; it is small because the fixed point itself moves close to the Gaussian point when $\epsilon$ is small.

## The temperature direction

The parameter $r$ is the field-theory version of the temperature-like perturbation. The critical point is not generally at $r=0$ after fluctuations are included; rather one tunes

$$
r-r_c.
$$

Near the Wilson–Fisher fixed point, the temperature-like perturbation has RG eigenvalue

$$
y_t=\frac{1}{\nu}.
$$

At one loop,

$$
\frac{1}{\nu}
=2-\frac{N+2}{N+8}\epsilon+O(\epsilon^2),
$$

or

$$
\nu
=\frac12+\frac{N+2}{4(N+8)}\epsilon+O(\epsilon^2).
$$

For the Ising case $N=1$,

$$
\nu=\frac12+\frac{\epsilon}{12}+O(\epsilon^2).
$$

This is the first correction to the mean-field value $\nu_{\text{MF}}=1/2$.

## Field anomalous dimension

At the Gaussian fixed point, the critical two-point function scales as

$$
G(x)=\langle \phi^a(x)\phi^a(0)\rangle
\sim
\frac{1}{|x|^{d-2}}.
$$

At an interacting critical point,

$$
G(x)\sim \frac{1}{|x|^{d-2+\eta}},
$$

so

$$
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

For the $O(N)$ Wilson–Fisher fixed point,

$$
\eta
=
\frac{N+2}{2(N+8)^2}\epsilon^2+O(\epsilon^3).
$$

The absence of an $O(\epsilon)$ term is worth remembering. At first order in the epsilon expansion, the main changes to the standard thermodynamic exponents come from the temperature eigenvalue, not from a large anomalous dimension of the fundamental field.

## Why this fixed point is universal

The local scalar action contains infinitely many additional operators:

$$
\phi^6,
\quad
\phi^8,
\quad
(\nabla\phi)^4,
\quad
\phi^2(\nabla\phi)^2,
\quad
\cdots.
$$

Near four dimensions, these are more irrelevant than the terms displayed in the $\phi^4$ action. They can affect nonuniversal amplitudes and subleading corrections to scaling, but they do not change the leading universal exponents unless one tunes to a different multicritical point or adds a genuinely relevant perturbation.

This is why the $\phi^4$ model is not merely one model among many. It is the local normal form of a large basin of attraction.

## Upper critical dimension and dangerous irrelevance

For short-range scalar $\phi^4$ theory,

$$
d_c=4.
$$

For $d>4$, the quartic coupling is irrelevant at the Gaussian fixed point, and the leading exponents are mean-field exponents. But one must still keep $u>0$ to stabilize the ordered phase. The quartic coupling is therefore **dangerously irrelevant**: irrelevant for the fixed-point classification, but essential for some observables.

At $d=4$, the quartic coupling is marginally irrelevant in the ordinary Ising/$O(N)$ case. Mean-field powers are then multiplied by logarithmic corrections.

For $d<4$, the Wilson–Fisher fixed point replaces the Gaussian fixed point as the infrared critical theory.

## The Ising case

For $N=1$,

$$
\beta_g=-\epsilon g+\frac32 g^2+O(g^3),
$$

and

$$
g_* = \frac{2\epsilon}{3}+O(\epsilon^2).
$$

The leading exponent corrections are

$$
\nu=\frac12+\frac{\epsilon}{12}+O(\epsilon^2),
\qquad
\eta=\frac{\epsilon^2}{54}+O(\epsilon^3),
$$

and the susceptibility exponent is

$$
\gamma=1+\frac{\epsilon}{6}+O(\epsilon^2).
$$

At $\epsilon=1$, these one-loop expressions are not precision numbers for the three-dimensional Ising model. Precision comes from high-order series, resummation, fixed-dimension methods, Monte Carlo, and bootstrap. One loop is the conceptual skeleton.

## Common pitfalls

**Using the wrong epsilon.** Here $\epsilon=4-d$. Some perturbative pages use $d=4-2\epsilon$. Never compare coefficients before checking this convention.

**Forgetting that $r_c$ is shifted.** The critical value of the quadratic parameter is not generally zero after interactions and regulator-dependent terms are included.

**Treating the one-loop answer at $\epsilon=1$ as a final prediction.** The one-loop epsilon expansion is a controlled expansion near four dimensions, not a high-precision three-dimensional calculation by itself.

**Confusing Gaussian and Wilson–Fisher criticality.** In $d<4$, the interacting short-range Ising transition is governed by the Wilson–Fisher fixed point, not the Gaussian fixed point.

**Ignoring dangerous irrelevance above four dimensions.** The quartic coupling is irrelevant for the Gaussian fixed point when $d>4$, but setting it to zero in the broken phase destroys stability.

## Relations to other pages

This page is the statistical-field-theory companion to [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/). It sits after [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/) and [Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/) because those pages explain where the scalar field theory comes from. It prepares [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) by showing why mean field is the Gaussian approximation and how it is corrected below four dimensions.

For the Wilsonian geometry, see [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

## Research status

The Wilson–Fisher fixed point and epsilon expansion are standard pillars of modern critical phenomena. The high-order epsilon expansion, when combined with resummation, remains a practical precision tool. Modern conformal bootstrap and Monte Carlo computations have made the three-dimensional Ising and $O(N)$ universality classes among the best-understood interacting QFTs.

Active directions include boundary and defect criticality, long-range interactions, quenched disorder, multicritical points, cubic and anisotropic perturbations, nonunitary continuations, dynamic critical phenomena, and transitions where a single scalar order parameter is not the whole story.

## Exercises

### Exercise 1: Engineering dimension of the quartic coupling

For the Gaussian scalar action

$$
S_0=\int d^d x\,\frac12(\nabla\phi)^2,
$$

show that $[\phi]=(d-2)/2$ and $[u]=4-d$ for the interaction $u\phi^4/4!$.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless. Since $[d^d x]=-d$, the integrand must have dimension $d$. The gradient term has dimension

$$
[(\nabla\phi)^2]=2+2[\phi].
$$

Therefore

$$
2+2[\phi]=d,
$$

so

$$
[\phi]=\frac{d-2}{2}.
$$

The operator $\phi^4$ has dimension $2(d-2)$, so the coefficient has dimension

$$
[u]=d-2(d-2)=4-d.
$$

</details>

### Exercise 2: One-loop fixed point

Given

$$
\beta_g=-\epsilon g+\frac{N+8}{6}g^2+O(g^3),
$$

find the nonzero fixed point to leading order.

<details><summary><strong>Solution</strong></summary>

To leading order, solve

$$
0=-\epsilon g+\frac{N+8}{6}g^2.
$$

The solutions are

$$
g=0,
\qquad
 g_* = \frac{6\epsilon}{N+8}.
$$

For fixed $N$ and $\epsilon\ll1$, the nonzero fixed point is weakly coupled.

</details>

### Exercise 3: First correction to nu

Use

$$
\frac{1}{\nu}=2-A\epsilon+O(\epsilon^2),
\qquad
A=\frac{N+2}{N+8},
$$

to derive

$$
\nu=\frac12+\frac{A}{4}\epsilon+O(\epsilon^2).
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
\nu=\frac{1}{2-A\epsilon}
=\frac12\frac{1}{1-A\epsilon/2}.
$$

Expanding the denominator gives

$$
\frac{1}{1-A\epsilon/2}=1+\frac{A\epsilon}{2}+O(\epsilon^2).
$$

Therefore

$$
\nu=\frac12+\frac{A}{4}\epsilon+O(\epsilon^2).
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for systematic renormalization and high-order critical-exponent technology.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, scalar masses, and RG flows.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the renormalization-group analysis of ferromagnetic transitions.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for a physics-first treatment of mean field, scaling, and the Ginzburg criterion.

## Version history

- 2026-06-18: First polished draft. Added near-four-dimensional scalar $\phi^4$ setup, one-loop Wilson–Fisher beta function, critical-exponent corrections, upper-critical-dimension discussion, and RG-flow figure.
