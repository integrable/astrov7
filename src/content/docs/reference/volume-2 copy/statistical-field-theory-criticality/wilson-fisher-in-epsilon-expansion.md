---
title: "Wilson-Fisher in Epsilon Expansion"
description: "A derivation-focused page on the Wilson–Fisher fixed point in d equals four minus epsilon, including the one-loop beta function and leading critical exponents."
sidebar:
  label: "Wilson-Fisher in Epsilon Expansion"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974, §§4–10; Zinn-Justin 2021, critical phenomena and epsilon-expansion chapters; Coleman 1985, Dilatations; Schwartz 2014, ch. 23; Altland and Simons 2023, ch. 6."
topics:
  - Wilson–Fisher fixed point
  - epsilon expansion
  - phi-four theory
  - critical exponents
  - anomalous dimensions
  - O(N) model
canonicalTopics:
  - wilson-fisher-fixed-point
  - epsilon-expansion
  - critical-exponents
  - o-n-model
researchStatus:
  established:
    - "The Wilson–Fisher fixed point in $d=4-\epsilon$ is the standard perturbatively controlled interacting fixed point for short-range scalar universality classes."
  active:
    - "High-order resummation, conformal bootstrap, Monte Carlo, functional RG, nonperturbative RG, defects, boundaries, disorder, and long-range variants continue to refine the numerical and structural understanding of Wilson–Fisher CFTs."
---

## Summary

The **Wilson–Fisher fixed point** is the interacting critical point of scalar $\phi^4$ theory below four dimensions. In the $O(N)$ model,

$$
S=\int d^d x\left[
\frac12(\nabla\boldsymbol\phi)^2
+\frac12 r\boldsymbol\phi^2
+\frac{u}{4!}(\boldsymbol\phi^2)^2
\right],
\qquad
\epsilon=4-d.
$$

At the Gaussian fixed point, the quartic interaction has engineering eigenvalue

$$
y_u=4-d=\epsilon.
$$

For $0<\epsilon\ll1$, it is weakly relevant. The beta function for a convenient dimensionless coupling $g$ has the form

$$
\beta_g\equiv \mu\frac{dg}{d\mu}
=-\epsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

Therefore the nonzero fixed point is

$$
g_* = \frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

Because $g_*=O(\epsilon)$, universal quantities at this interacting fixed point can be computed perturbatively. This is the epsilon expansion.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 54rem;">

![The one-loop beta function for the Wilson–Fisher fixed point near four dimensions.](/figures/renormalization-rg-eft/wilson-fisher-beta-function-near-four-dimensions.svg)

<figcaption>

At $d=4-\epsilon$, the Gaussian fixed point and the Wilson–Fisher fixed point are separated by a distance of order $\epsilon$ in coupling space. The one-loop zero of $\beta_g$ is enough to compute leading universal data. The sign of arrows depends on whether one uses UV time $\log\mu$ or IR coarse-graining time; the fixed-point locations do not.

</figcaption>
</figure>

:::note[The epsilon convention on this page]
Here $\epsilon=4-d$. This is the statistical-physics epsilon expansion convention. It is not the high-energy dimensional-regularization convention $d=4-2\epsilon$.
:::

## Prerequisites

You should know [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/), [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/), and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/).

## Core idea

The Wilson–Fisher fixed point is born from a competition between two effects.

First, below four dimensions the quartic interaction is relevant by classical dimensional analysis:

$$
\mu\frac{dg}{d\mu}\supset -\epsilon g.
$$

Second, fluctuations generate a quadratic term in the beta function:

$$
\mu\frac{dg}{d\mu}\supset \frac{N+8}{6}g^2.
$$

The fixed point occurs where these two terms balance:

$$
-\epsilon g_*+\frac{N+8}{6}g_*^2=0.
$$

The nonzero solution is

$$
g_* = \frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

This is why the fixed point is perturbative near four dimensions. The interaction is not assumed small because we are wishful; it is small because the fixed point itself approaches the Gaussian point as $\epsilon\to0$.

The result is profound: a nontrivial continuous phase transition can be studied by expanding around a free theory in a nearby dimension.

## Setup and conventions

Use the Euclidean $O(N)$ action

$$
S=\int d^d x\left[
\frac12 Z_\phi(\nabla\boldsymbol\phi)^2
+\frac12 Z_r r\boldsymbol\phi^2
+\frac{\mu^\epsilon Z_g g}{4!}(\boldsymbol\phi^2)^2
\right].
$$

The exact normalization of $g$ is conventional. This page uses the common normalization in which

$$
\beta_g=-\epsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

Changing the finite definition of $g$ changes higher-order coefficients, but it does not change the universal critical exponents computed consistently.

The mass parameter $r$ is the temperature-like perturbation. The critical surface is obtained by tuning

$$
r=r_c(g,\mu),
$$

so that the correlation length diverges. In minimal subtraction, $r_c$ is often zero for the massless renormalized theory, but in a cutoff or lattice description it includes additive short-distance shifts.

## The beta function and the fixed point

At one loop, the four-point function receives bubble corrections. At short distance, two quartic vertices collide and renormalize the local operator $(\boldsymbol\phi^2)^2$. The combinatorics of the $O(N)$ index contractions gives the coefficient $N+8$ in the chosen normalization.

Thus

$$
\beta_g=-\epsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

The fixed points through this order are

$$
g_0=0,
\qquad
g_* = \frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

The stability exponent for the leading irrelevant direction at the Wilson–Fisher fixed point is

$$
\omega=\left.\frac{\partial\beta_g}{\partial g}\right|_{g_*}
=\epsilon+O(\epsilon^2),
$$

up to the sign convention for RG time. This exponent controls the leading correction to scaling from the quartic coupling direction.

In infrared language, the Gaussian fixed point is unstable along the quartic direction for $\epsilon>0$, while the Wilson–Fisher point is stable along the critical surface.

## Temperature eigenvalue and nu

The mass operator $\boldsymbol\phi^2$ controls the temperature-like perturbation. At the Gaussian fixed point its RG eigenvalue is

$$
y_t^{(0)}=2.
$$

At the Wilson–Fisher fixed point, operator renormalization shifts this value. To first order in $\epsilon$,

$$
y_t=\frac{1}{\nu}
=2-\frac{N+2}{N+8}\epsilon+O(\epsilon^2).
$$

Therefore

$$
\nu=\frac12+\frac{N+2}{4(N+8)}\epsilon+O(\epsilon^2).
$$

For the Ising case $N=1$,

$$
\nu=\frac12+\frac{1}{12}\epsilon+O(\epsilon^2).
$$

Setting $\epsilon=1$ gives $\nu\approx0.583$ at first order, while the three-dimensional Ising value is about $0.63$. The point is not that first order is numerically perfect. The point is that the expansion gives a controlled analytic route to a non-Gaussian fixed point.

## Field anomalous dimension and eta

The field anomalous dimension starts at two loops in ordinary $\phi^4$ theory. Thus

$$
\eta=O(\epsilon^2)
$$

at leading one-loop order. The first nonzero term is

$$
\eta=\frac{N+2}{2(N+8)^2}\epsilon^2+O(\epsilon^3)
$$

in the standard normalization.

The scaling dimension of the field is therefore

$$
\Delta_\phi=\frac{d-2+\eta}{2}
=1-\frac{\epsilon}{2}+\frac{\eta}{2}.
$$

This is the first place where the interacting critical theory differs sharply from the Gaussian fixed point as a theory of local operators. The field dimension is no longer purely engineering; it includes an anomalous part determined by fluctuations.

## Other critical exponents at leading order

Once $\nu$ and $\eta$ are known, the standard scaling relations give the remaining thermodynamic exponents, assuming ordinary hyperscaling below the upper critical dimension.

To first order in $\epsilon$,

$$
\gamma=\nu(2-\eta)
=1+\frac{N+2}{2(N+8)}\epsilon+O(\epsilon^2),
$$

$$
\beta_{\text{mag}}
=\frac{\nu}{2}(d-2+\eta)
=\frac12-\frac{3}{2(N+8)}\epsilon+O(\epsilon^2),
$$

$$
\delta=\frac{d+2-\eta}{d-2+\eta}
=3+\epsilon+O(\epsilon^2),
$$

and

$$
\alpha=2-d\nu
=\frac{4-N}{2(N+8)}\epsilon+O(\epsilon^2).
$$

The magnetization exponent is written as $\beta_{\text{mag}}$ to avoid confusion with the beta function $\beta_g$.

For $N=1$ these become

$$
\nu=\frac12+\frac{\epsilon}{12}+O(\epsilon^2),
\qquad
\eta=\frac{\epsilon^2}{54}+O(\epsilon^3),
$$

$$
\gamma=1+\frac{\epsilon}{6}+O(\epsilon^2),
\qquad
\beta_{\text{mag}}=\frac12-\frac{\epsilon}{6}+O(\epsilon^2).
$$

These first-order values are rough in three dimensions, but the high-order epsilon expansion, when properly resummed, is quantitatively powerful.

## Why epsilon expansion is not ordinary small-coupling perturbation theory

Ordinary perturbation theory expands observables around a weakly coupled theory at fixed dimension. The epsilon expansion is different. It expands both the dimension and the fixed point:

$$
d=4-\epsilon,
\qquad
g_*(\epsilon)=O(\epsilon).
$$

Universal quantities are then evaluated at $g=g_*(\epsilon)$. For an observable $X(g,\epsilon)$,

$$
X_*=X(g_*(\epsilon),\epsilon).
$$

This is why a critical exponent can have a series in $\epsilon$ even though the three-dimensional theory is not weakly coupled in the original microscopic sense.

The expansion is asymptotic, not convergent in a naive elementary sense. Serious numerical use of the epsilon expansion relies on high orders plus resummation. Conceptually, however, even the first orders teach the most important lesson: interacting scale-invariant QFTs can be reached from controlled deformations of Gaussian fixed points.

## Interpretation as a CFT

At the Wilson–Fisher fixed point, the long-distance theory is a conformal field theory in dimensions where scale invariance enhances to conformal invariance under the usual assumptions. The CFT data include operator dimensions and OPE coefficients.

The leading scalar operators are:

| Operator | Meaning | Scaling dimension near $4-\epsilon$ |
|---|---|---|
| $\phi^a$ | order parameter | $(d-2+\eta)/2$ |
| $\boldsymbol\phi^2$ | energy or temperature operator | $d-y_t$ |
| symmetric traceless $\phi^a\phi^b$ | anisotropy-like tensor operator | receives its own anomalous dimension |
| $(\boldsymbol\phi^2)^2$ | leading irrelevant scalar near WF | $d+\omega$ |

This operator viewpoint is often cleaner than thinking only in terms of a Lagrangian. The Lagrangian is a way to reach the fixed point. The fixed point itself is characterized by scaling dimensions, OPE coefficients, global symmetry, and correlation functions.

## Relation to the Gaussian fixed point

The Gaussian fixed point remains visible inside the Wilson–Fisher calculation. At $\epsilon=0$, the two fixed points collide:

$$
g_*(\epsilon)\to0.
$$

For small positive $\epsilon$, the Wilson–Fisher fixed point is nearby. This makes the Gaussian operator basis a useful starting basis. Operators that are nearly marginal at the Gaussian point can acquire small anomalous dimensions and reorganize into interacting scaling operators.

The same story also explains why four dimensions is special. In $d=4$, the quartic interaction is marginally irrelevant, so the infrared critical theory of the ordinary scalar model is Gaussian with logarithmic corrections. In $d=3$, the Wilson–Fisher point is genuinely interacting.

## Common pitfalls

**Plugging in $\epsilon=1$ and expecting precision from one loop.** First-order epsilon expansion is a controlled analytic lesson, not a precision table. Quantitative estimates require higher orders, resummation, Monte Carlo, bootstrap, or other nonperturbative input.

**Forgetting the sign convention for beta functions.** This page uses $\beta_g=\mu dg/d\mu$. Infrared Wilsonian flow uses the opposite direction for RG time. Fixed-point locations are invariant; arrow directions depend on convention.

**Calling $g_*$ universal.** The numerical value of $g_*$ depends on coupling normalization and scheme. Critical exponents and properly defined CFT data are universal.

**Confusing the Ising model with the Ising CFT.** The lattice Ising model is a microscopic system. The Wilson–Fisher fixed point is the continuum long-distance theory reached after tuning to criticality.

**Using Gaussian operator dimensions after reaching the interacting fixed point.** Gaussian dimensions are the zeroth approximation. The Wilson–Fisher point has anomalous dimensions.

## Relations to other pages

This page is the statistical-field-theory counterpart of [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/). It builds on [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/) and [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/), and it prepares the later pages [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/), [Susceptibility and Critical Exponents](/renormalization-rg-eft/statistical-field-theory-criticality/susceptibility-and-critical-exponents/), and [Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/).

The local-operator interpretation connects to [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/).

## Research status

The existence and perturbative structure of the Wilson–Fisher fixed point near four dimensions are standard. In three dimensions, the Ising, XY, and Heisenberg Wilson–Fisher CFTs are among the best-studied nontrivial QFTs. Their critical data are known with high precision from a combination of resummed perturbation theory, Monte Carlo, conformal bootstrap, high-temperature expansions, and experiments.

Active research includes boundaries, defects, interfaces, disorder, random fields, long-range interactions, multicritical points, noninteger dimension, conformal-bootstrap perturbation theory, nonperturbative RG, and dynamical critical phenomena. The fixed point is old; the ecosystem around it is absolutely not dusty.

## Exercises

### Exercise 1: Locate the fixed point

Starting from

$$
\beta_g=-\epsilon g+\frac{N+8}{6}g^2+O(g^3),
$$

find the nonzero fixed point to leading order in $\epsilon$.

<details><summary><strong>Solution</strong></summary>

At a fixed point,

$$
0=-\epsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

Factoring out $g$ gives

$$
g\left(-\epsilon+\frac{N+8}{6}g+O(g^2)\right)=0.
$$

The nonzero solution is

$$
g_*=\frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

</details>

### Exercise 2: Compute the correction-to-scaling exponent

Using the one-loop beta function above, show that the leading irrelevant exponent at the Wilson–Fisher fixed point is $\omega=\epsilon+O(\epsilon^2)$, up to RG-time sign convention.

<details><summary><strong>Solution</strong></summary>

Linearize the beta function near $g_*$:

$$
\beta_g(g)=\beta_g(g_*)+
\left.\frac{\partial\beta_g}{\partial g}\right|_{g_*}(g-g_*)+
\cdots.
$$

Since $\beta_g(g_*)=0$,

$$
\left.\frac{\partial\beta_g}{\partial g}\right|_{g_*}
=-\epsilon+\frac{N+8}{3}g_*+O(g_*^2).
$$

Substituting

$$
g_*=\frac{6\epsilon}{N+8}+O(\epsilon^2)
$$

gives

$$
\left.\frac{\partial\beta_g}{\partial g}\right|_{g_*}
=-\epsilon+2\epsilon+O(\epsilon^2)
=\epsilon+O(\epsilon^2).
$$

With the ultraviolet-time convention this is the slope of $\beta_g$. In infrared coarse-graining time the sign of the flow is reversed, but the positive correction-to-scaling exponent is conventionally quoted as

$$
\omega=\epsilon+O(\epsilon^2).
$$

</details>

### Exercise 3: Derive beta-mag from scaling

Use

$$
\beta_{\text{mag}}=\frac{\nu}{2}(d-2+\eta),
$$

with

$$
\nu=\frac12+\frac{N+2}{4(N+8)}\epsilon+O(\epsilon^2),
\qquad
\eta=O(\epsilon^2),
\qquad
d=4-\epsilon,
$$

to show that

$$
\beta_{\text{mag}}=\frac12-\frac{3}{2(N+8)}\epsilon+O(\epsilon^2).
$$

<details><summary><strong>Solution</strong></summary>

To first order in $\epsilon$,

$$
\frac{d-2+\eta}{2}=\frac{2-\epsilon}{2}+O(\epsilon^2)
=1-\frac{\epsilon}{2}+O(\epsilon^2).
$$

Therefore

$$
\beta_{\text{mag}}
=\left(\frac12+\frac{N+2}{4(N+8)}\epsilon\right)
\left(1-\frac{\epsilon}{2}\right)+O(\epsilon^2).
$$

Multiplying out,

$$
\beta_{\text{mag}}
=\frac12-\frac{\epsilon}{4}
+\frac{N+2}{4(N+8)}\epsilon
+O(\epsilon^2).
$$

The coefficient of $\epsilon$ is

$$
-\frac14+\frac{N+2}{4(N+8)}
=\frac{-(N+8)+(N+2)}{4(N+8)}
=-\frac{6}{4(N+8)}
=-\frac{3}{2(N+8)}.
$$

Thus

$$
\beta_{\text{mag}}=\frac12-\frac{3}{2(N+8)}\epsilon+O(\epsilon^2).
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on perturbative RG, critical exponents, and resummation.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" for the Callan–Symanzik equation, anomalous dimensions, and scaling.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapter on the renormalization group.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the RG analysis of ferromagnetic transitions.

## Version history

- 2026-06-18: First polished draft. Added one-loop beta function, fixed point, leading exponents, scheme/universality comments, CFT interpretation, figure, and exercises.
