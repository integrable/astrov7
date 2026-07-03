---
title: "Wilson–Fisher Fixed Point"
description: "Derives the Wilson–Fisher fixed point of the O(N) scalar model near four dimensions and explains its role as the prototype interacting critical point."
sidebar:
  label: "Wilson–Fisher Fixed Point"
  order: 7
level: Graduate
status: "Polished draft"
source: "Wilson and Fisher 1972; Wilson and Kogut 1974; Coleman 1985, Dilatations; Weinberg 1996, ch. 18; Zinn-Justin 2021; Cardy 1996; Goldenfeld 1992."
topics:
  - Wilson–Fisher fixed point
  - epsilon expansion
  - O(N) model
  - phi-four theory
  - critical exponents
  - universality
canonicalTopics:
  - wilson-fisher-fixed-point
  - epsilon-expansion
  - o-n-model
  - scalar-criticality
researchStatus:
  established:
    - "The Wilson–Fisher fixed point is the standard perturbatively accessible interacting fixed point of scalar O(N) models below four dimensions."
  active:
    - "High-precision properties of Wilson–Fisher CFTs remain active in conformal bootstrap, Monte Carlo, high-order epsilon expansion, large-N methods, functional RG, and applications to real critical systems."
---

## Summary

The **Wilson–Fisher fixed point** is the canonical example of an interacting RG fixed point. It appears in the $O(N)$ scalar model below four dimensions and controls the ordinary critical behavior of many short-range systems with an $N$-component order parameter.

The Euclidean action is

$$
S=\int d^d x\left[
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
+\frac12 r\phi^a\phi^a
+\frac{u}{4!}(\phi^a\phi^a)^2
\right],
\qquad a=1,\ldots,N.
$$

Near four dimensions, define

$$
\varepsilon\equiv 4-d.
$$

In a standard dimensionless coupling convention, the one-loop beta function has the form

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

It has two fixed points:

$$
g_*=0,
\qquad
 g_*^{\mathrm{WF}}=\frac{6\varepsilon}{N+8}+O(\varepsilon^2).
$$

For $\varepsilon>0$, the second fixed point is weakly coupled when $\varepsilon\ll1$. This is the Wilson–Fisher fixed point. It is perturbative near $d=4$, but it teaches a nonperturbative lesson: a continuum QFT can be interacting at long distances even when the Gaussian fixed point is nearby.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![RG flow near the Gaussian and Wilson–Fisher fixed points in the O(N) scalar model below four dimensions](/figures/renormalization-rg-eft/wilson-fisher-fixed-point-flow.svg)

<figcaption>

For $d=4-\varepsilon$ with $\varepsilon>0$, the quartic coupling is relevant at the Gaussian fixed point but flows to the interacting Wilson–Fisher fixed point. The thermal perturbation is relevant at the Wilson–Fisher point and must be tuned to reach criticality; the quartic direction is irrelevant there.

</figcaption>
</figure>

:::note[One sentence to remember]
The Wilson–Fisher fixed point is what becomes of scalar $\phi^4$ theory when the quartic interaction is slightly relevant below four dimensions and then stabilizes at a nonzero fixed-point value.
:::

## Prerequisites

You should know [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), and [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/).

The one technical input is the one-loop renormalization of scalar $\phi^4$ theory. The conceptual input is more important: a fixed point is a scale-invariant theory, and its relevant directions determine what must be tuned to observe criticality.

## Core idea

In four dimensions, the scalar quartic coupling is classically marginal. Below four dimensions, it becomes relevant at the Gaussian fixed point. If it only grew forever, the Gaussian theory would merely tell us that perturbation theory fails in the infrared. The crucial Wilson–Fisher discovery is that loop effects push back.

The beta function has two competing terms:

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2+\cdots
$$

when written in the UV-time convention $\beta_g=\mu\,dg/d\mu$. The first term is classical engineering dimension: below four dimensions the coupling has positive mass dimension, so the dimensionless coupling grows toward the infrared. The second term is the quantum correction. Their competition produces a nonzero fixed point.

Equivalently, in IR coarse-graining time $\ell=\log b$, the flow of $g$ begins

$$
\frac{dg}{d\ell}=\varepsilon g-\frac{N+8}{6}g^2+\cdots,
$$

so small positive $g$ grows, but only until it reaches

$$
g_*^{\mathrm{WF}}=\frac{6\varepsilon}{N+8}+O(\varepsilon^2).
$$

This is the simplest perturbative laboratory for an interacting critical theory.

## Setup and conventions

This page uses the critical-phenomena epsilon convention

$$
\varepsilon\equiv4-d.
$$

This is not the same notation as the dimensional-regularization convention $d=4-2\epsilon$ used elsewhere in perturbative amplitudes. Here $\varepsilon$ measures distance below the upper critical dimension.

The Euclidean $O(N)$ model is

$$
S=\int d^d x\left[
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
+\frac12 r\phi^a\phi^a
+\frac{u}{4!}(\phi^a\phi^a)^2
\right].
$$

The symmetry is

$$
\phi^a\longmapsto R^a{}_b\phi^b,
\qquad R\in O(N).
$$

The parameter $r$ is the thermal perturbation. In statistical mechanics, tuning $r$ corresponds to tuning the temperature through the critical temperature. The coupling $u$ is the quartic self-interaction. A dimensionless renormalized coupling $g$ is obtained by absorbing conventional factors of $4\pi$, gamma functions, and powers of the renormalization scale. We choose the common normalization in which

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

Different books normalize $g$ differently. The fixed-point value changes under such redefinitions; critical exponents and scaling dimensions do not.

## Why four dimensions are special

The engineering dimension of a scalar field at the Gaussian fixed point is

$$
[\phi]_{\mathrm{G}}=\frac{d-2}{2}.
$$

The operator $(\phi^a\phi^a)^2$ has Gaussian engineering dimension

$$
[(\phi^a\phi^a)^2]_{\mathrm{G}}=2(d-2).
$$

Therefore the quartic coupling has engineering dimension

$$
[u]=d-2(d-2)=4-d=\varepsilon.
$$

Thus:

| Dimension | Gaussian status of quartic coupling |
|---|---|
| $d>4$ | irrelevant |
| $d=4$ | marginal |
| $d<4$ | relevant |

This is why $d=4$ is the upper critical dimension for short-range $O(N)$ criticality. Above four dimensions, the Gaussian fixed point gives mean-field exponents at leading order. Below four dimensions, the quartic coupling cannot be ignored.

The phrase “upper critical dimension” does not mean that physics stops above four dimensions. It means that above that dimension the interaction is irrelevant at the Gaussian fixed point, so leading critical exponents are mean-field, with caveats from dangerous irrelevant variables.

## One-loop beta function and fixed points

With the normalization stated above, the beta function is

$$
\beta_g\equiv \mu\frac{dg}{d\mu}
=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

The fixed points solve

$$
\beta_g(g_*)=0.
$$

At this order,

$$
g_*=0
$$

and

$$
g_*^{\mathrm{WF}}=\frac{6\varepsilon}{N+8}+O(\varepsilon^2).
$$

The Gaussian fixed point exists in every dimension. The Wilson–Fisher fixed point is perturbatively visible for small positive $\varepsilon$.

The sign interpretation depends on RG time. With $\mu$ increasing toward the ultraviolet, the beta function above says that $g=0$ is UV-attractive for $d<4$. With IR coarse-graining time $\ell=\log b$, the sign reverses:

$$
\frac{dg}{d\ell}=\varepsilon g-\frac{N+8}{6}g^2+O(g^3).
$$

Thus $g$ flows toward $g_*^{\mathrm{WF}}$ in the infrared.

This sign flip is a common source of confusion. The physics is simple: below four dimensions, the quartic interaction grows as one goes to longer distances until nonlinear RG effects stabilize it at an interacting fixed point.

## Thermal direction and tuning

A critical point is not reached by choosing $g=g_*^{\mathrm{WF}}$ alone. One must also tune the relevant thermal perturbation. In the scalar model this is the mass operator

$$
\mathcal O_t=\phi^a\phi^a.
$$

The corresponding coupling is $r-r_c$, where $r_c$ is the critical value. In continuum minimal-subtraction formulas one often writes the critical point at $r=0$, but in a cutoff or lattice theory additive renormalization shifts the physical critical value.

Near the Wilson–Fisher fixed point, the thermal scaling eigenvalue is

$$
y_t=\frac{1}{\nu}
=2-\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2).
$$

Since $y_t>0$ for small $\varepsilon$, the thermal perturbation is relevant. Reaching the fixed point requires tuning it to zero. In a magnet, that tuning is temperature. In a scalar QFT, it is the renormalized mass parameter.

The quartic direction at the Wilson–Fisher fixed point is irrelevant. Its leading correction-to-scaling exponent is

$$
\omega=\left.\frac{d\beta_g}{dg}\right|_{g_*}^{\mathrm{IR}}
=\varepsilon+O(\varepsilon^2),
$$

where the sign is quoted as a positive correction-to-scaling exponent. Equivalently, deviations of $g$ from $g_*^{\mathrm{WF}}$ die as a power under IR coarse graining.

## Critical exponents to first order

The epsilon expansion converts perturbative RG data into critical exponents.

At leading orders,

$$
\nu=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2),
$$

$$
\eta=\frac{N+2}{2(N+8)^2}\varepsilon^2+O(\varepsilon^3),
$$

and, using scaling relations,

$$
\alpha=\frac{4-N}{2(N+8)}\varepsilon+O(\varepsilon^2),
$$

$$
\beta_{\mathrm{mag}}
=\frac12-\frac{3}{2(N+8)}\varepsilon+O(\varepsilon^2),
$$

$$
\gamma
=1+\frac{N+2}{2(N+8)}\varepsilon+O(\varepsilon^2),
$$

$$
\delta=3+\varepsilon+O(\varepsilon^2).
$$

The anomalous dimension $\eta$ begins only at order $\varepsilon^2$. This does not mean anomalous dimensions are unimportant. It means that the first nontrivial correction to the field dimension happens one loop later than the fixed-point coupling itself.

For $N=1$ and $\varepsilon=1$, the first-order estimates are already qualitatively useful but not precision numbers. Modern high-order expansions, Borel resummation, Monte Carlo, conformal bootstrap, and experiment are needed for precise three-dimensional exponents.

## Physical interpretation

The Wilson–Fisher fixed point answers a famous question: can there be a scale-invariant interacting QFT that is neither free nor defined by a small parameter in physical dimension? Yes.

Near four dimensions it has a small parameter, $\varepsilon$. In three dimensions, $\varepsilon=1$, so the fixed point is not really weakly coupled. Nevertheless the epsilon expansion can be analytically continued and resummed, giving accurate results when treated carefully.

For $N=1$, the three-dimensional Wilson–Fisher CFT describes the Ising universality class. For $N=2$, it describes the ordinary three-dimensional XY universality class, relevant to superfluid transitions and planar magnets. For $N=3$, it describes the Heisenberg universality class for isotropic magnets.

The same fixed point can be approached from many microscopic systems:

$$
\text{lattice spins}
\quad\longrightarrow\quad
\text{coarse graining}
\quad\longrightarrow\quad
O(N)\text{ Wilson–Fisher CFT}.
$$

That is why this fixed point is the prototype of universality.

## Diagrammatic origin of the one-loop coefficient

The coefficient $N+8$ in the beta function is combinatorial. It comes from the one-loop four-point diagrams of the $O(N)$ model.

The interaction is

$$
\frac{u}{4!}(\phi^a\phi^a)^2.
$$

At one loop, the four-point vertex is corrected by bubble diagrams in the $s$, $t$, and $u$ channels. The internal index sums produce the $N$-dependent part; the different contractions of external indices produce the remaining numerical terms.

In the chosen normalization, the result is

$$
\delta g\sim \frac{N+8}{6}\frac{g^2}{\varepsilon}
$$

in minimal subtraction. Requiring the bare coupling to be independent of $\mu$ gives

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

The point of this page is not the integral technology. The point is what the coefficient does: it balances the engineering relevance of $g$ below four dimensions and creates a nonzero fixed point.

## Why the fixed point is infrared-stable in the coupling direction

Using IR time $\ell=\log b$, define

$$
\frac{dg}{d\ell}=\varepsilon g-A g^2,
\qquad
A=\frac{N+8}{6}.
$$

The fixed point is

$$
g_*=\frac{\varepsilon}{A}.
$$

Linearize:

$$
g=g_*+\delta g.
$$

Then

$$
\frac{d\delta g}{d\ell}
=\left(\varepsilon-2Ag_*\right)\delta g+O(\delta g^2)
=-\varepsilon\delta g+O(\delta g^2).
$$

Thus deviations in the quartic coupling shrink under coarse graining:

$$
\delta g(\ell)\sim e^{-\varepsilon\ell}\delta g(0).
$$

This is the RG meaning of irrelevance at the Wilson–Fisher fixed point. The same coupling that was relevant at the Gaussian fixed point becomes irrelevant at the interacting fixed point.

## Relation to conformal field theory

At the critical point, the Wilson–Fisher fixed point is scale invariant and, in the standard local unitary examples, conformally invariant. The three-dimensional Ising CFT is the $N=1$ Wilson–Fisher fixed point in $d=3$.

From the CFT viewpoint, the universality class is specified by conformal data:

$$
\{\Delta_i,\ell_i,C_{ijk}\},
$$

where $\Delta_i$ are scaling dimensions, $\ell_i$ are spins, and $C_{ijk}$ are OPE coefficients. The epsilon expansion computes this data perturbatively near $d=4$. The conformal bootstrap computes or constrains the same data using crossing symmetry and unitarity.

The lowest $O(N)$ singlet scalar is the energy operator, often denoted $\epsilon$ in CFT literature. To avoid collision with $\varepsilon=4-d$, call it $\mathcal E$ here. Its dimension is related to $\nu$ by

$$
\Delta_{\mathcal E}=d-y_t=d-\frac1\nu.
$$

The order parameter field $\phi^a$ has dimension

$$
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

These are not merely statistical exponents in disguise; they are operator dimensions in the critical QFT.

## Limits and special cases

### N equals 1

For $N=1$, the model has a single real scalar and $\mathbb Z_2$ symmetry. In $d=3$, this is the Ising universality class. The fixed point is strongly coupled by the naive epsilon-counting standard, but it is very precisely known by modern bootstrap and numerical methods.

### N equals 2

For $N=2$, the order parameter is a two-component vector or complex scalar. In $d=3$, this describes the XY universality class. It is relevant to superfluid helium and systems with a broken $U(1)$ order parameter. In $d=2$, the ordinary Wilson–Fisher description gives way to BKT physics, where vortices and a line of fixed points become central.

### N equals 3

For $N=3$, the model describes the Heisenberg universality class of isotropic magnets. Real materials can have anisotropies; whether those anisotropies are relevant decides the true asymptotic class.

### Large N

At large $N$, the $O(N)$ model can be studied by auxiliary-field methods. The large-$N$ expansion and the epsilon expansion are different approximations to the same family of fixed points where their regimes overlap.

### d equals 4

At $d=4$, $\varepsilon=0$ and the Wilson–Fisher fixed point merges with the Gaussian fixed point. The quartic coupling is marginally irrelevant for positive coupling. The leading behavior is mean-field with logarithmic corrections.

### d greater than 4

For $d>4$, the quartic coupling is irrelevant at the Gaussian fixed point. The leading critical exponents are mean-field, but the quartic coupling is dangerously irrelevant for some observables. This is the classic caveat to naive hyperscaling above the upper critical dimension.

## What the epsilon expansion really means

The epsilon expansion is not a Taylor expansion in a physical laboratory knob. Three-dimensional magnets do not come with a dial that changes spacetime dimension from $4$ to $3$. The expansion is an analytic continuation strategy: compute near four dimensions where the fixed point is weakly coupled, then resum or extrapolate to the dimension of interest.

This is both audacious and justified by success. It becomes reliable when combined with:

- high-loop calculations;
- Borel or conformal-Borel resummation;
- fixed-dimension perturbative expansions;
- large-$N$ checks;
- Monte Carlo simulations;
- conformal bootstrap constraints;
- experimental data.

The first-order formulas on this page are for understanding. They are not the final numerical word on the three-dimensional Ising model.

## Common pitfalls

**Confusing the two epsilons.** This page uses $\varepsilon=4-d$. Dimensional-regularization pages often use $d=4-2\epsilon$. The meanings are related but not identical conventions.

**Thinking the fixed-point coupling is physical.** The number $g_*^{\mathrm{WF}}=6\varepsilon/(N+8)+\cdots$ depends on how $g$ is normalized. Exponents and operator dimensions are physical universal data.

**Forgetting the mass tuning.** The Wilson–Fisher fixed point controls criticality only after the thermal perturbation is tuned. Generic nearby points flow to massive phases.

**Plugging $\varepsilon=1$ and calling it precision.** First-order epsilon expansion is a conceptual map. Precision requires higher orders and resummation or independent nonperturbative methods.

**Assuming all $O(N)$-looking systems are asymptotically $O(N)$.** Anisotropies, disorder, gauge fields, long-range interactions, and topological terms can be relevant and change the true universality class.

**Thinking $d=4$ is just another point.** At the upper critical dimension, marginality produces logarithmic corrections. Power laws alone do not tell the whole story.

## Relations to other pages

[Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) explains why the Wilson–Fisher fixed point describes many different microscopic systems. [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) and [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) translate fixed-point eigenvalues into observable power laws.

[Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) explains beta functions abstractly. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) and [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/) show different ways beta functions create scale dependence. [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) explains why $d=4$ is special for scalar quartic interactions.

The next page, [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/), develops the computational method systematically.

## Research status

The existence and role of the Wilson–Fisher fixed point are established. It is one of the central examples connecting renormalization, statistical mechanics, critical phenomena, and conformal field theory.

Research remains active because the fixed point is a precision laboratory. Current work computes increasingly accurate scaling dimensions, OPE coefficients, amplitude ratios, finite-size data, and response functions using conformal bootstrap, Monte Carlo, high-order perturbation theory, large-$N$, functional RG, and experiments. The $O(N)$ family also serves as a benchmark for more exotic critical points, including gauge-matter theories and systems with topological terms or disorder.

## Exercises

### Exercise 1: Locate the fixed point

Using

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3),
$$

find the nonzero fixed point to leading order in $\varepsilon$.

<details><summary><strong>Solution</strong></summary>

Set $\beta_g=0$ and keep only the displayed terms:

$$
0=-\varepsilon g+\frac{N+8}{6}g^2
=g\left(-\varepsilon+\frac{N+8}{6}g\right).
$$

The solutions are

$$
g_*=0
$$

and

$$
g_*^{\mathrm{WF}}=\frac{6\varepsilon}{N+8}.
$$

Higher-loop terms correct this by $O(\varepsilon^2)$.

</details>

### Exercise 2: Stability in the coupling direction

Use IR time $\ell=\log b$ and

$$
\frac{dg}{d\ell}=\varepsilon g-\frac{N+8}{6}g^2.
$$

Show that the Wilson–Fisher fixed point is IR-attractive in the $g$ direction.

<details><summary><strong>Solution</strong></summary>

Let

$$
A=\frac{N+8}{6},
\qquad
 g_*=\frac{\varepsilon}{A}.
$$

Linearize $g=g_*+\delta g$. Then

$$
\frac{d\delta g}{d\ell}
=\left(\varepsilon-2Ag_*\right)\delta g+O(\delta g^2)
=\left(\varepsilon-2\varepsilon\right)\delta g+O(\delta g^2).
$$

Thus

$$
\frac{d\delta g}{d\ell}=-\varepsilon\delta g+O(\delta g^2),
$$

so for $\varepsilon>0$,

$$
\delta g(\ell)\sim e^{-\varepsilon\ell}\delta g(0).
$$

The deviation shrinks under coarse graining, so the fixed point is IR-attractive along the coupling direction.

</details>

### Exercise 3: First-order estimate for the Ising exponent ν

Set $N=1$ and $\varepsilon=1$ in

$$
\nu=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2).
$$

What value do you get? Why should it not be treated as a precision result?

<details><summary><strong>Solution</strong></summary>

For $N=1$,

$$
\frac{N+2}{4(N+8)}=\frac{3}{36}=\frac{1}{12}.
$$

For $\varepsilon=1$,

$$
\nu\approx \frac12+\frac{1}{12}=\frac{7}{12}\approx0.583.
$$

This is qualitatively closer to the three-dimensional Ising value than mean-field theory, but it is not a precision result because $\varepsilon=1$ is not small. Higher-loop terms and resummation are needed for accurate estimates.

</details>

### Exercise 4: Operator dimension of the energy operator

Using

$$
\Delta_{\mathcal E}=d-\frac1\nu
$$

and

$$
\frac1\nu=2-\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2),
\qquad d=4-\varepsilon,
$$

find $\Delta_{\mathcal E}$ to first order in $\varepsilon$.

<details><summary><strong>Solution</strong></summary>

Substitute the formulas:

$$
\Delta_{\mathcal E}
=(4-\varepsilon)-\left(2-\frac{N+2}{N+8}\varepsilon\right)+O(\varepsilon^2).
$$

Therefore

$$
\Delta_{\mathcal E}
=2-\varepsilon+\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2)
=2-\frac{6}{N+8}\varepsilon+O(\varepsilon^2).
$$

For $N=1$, this gives $\Delta_{\mathcal E}=2-2\varepsilon/3+O(\varepsilon^2)$.

</details>

## References

- Kenneth G. Wilson and Michael E. Fisher, "Critical Exponents in 3.99 Dimensions," *Physical Review Letters* **28** (1972) 240–243.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Secret Symmetry," for scale invariance, RG equations, and asymptotic freedom in a broader QFT context.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, critical behavior, and the Wilson–Fisher fixed point in QFT language.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., for systematic epsilon expansion, renormalization, and critical exponents.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a concise scaling and RG treatment.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for physical interpretation and worked examples.

## Version history

- 2026-06-17: First polished draft. Introduced the $O(N)$ model, one-loop beta function, Wilson–Fisher fixed point, critical exponents, epsilon-expansion caveats, and relation to universality and CFT data.
