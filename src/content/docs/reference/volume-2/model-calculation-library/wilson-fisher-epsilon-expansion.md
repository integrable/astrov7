---
title: "Wilson–Fisher Epsilon Expansion"
description: "A worked one-loop derivation of the Wilson–Fisher fixed point in O(N) phi-four theory near four dimensions, including the fixed-point coupling, relevant eigenvalue, and leading critical exponents."
sidebar:
  label: "Wilson–Fisher Epsilon Expansion"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Srednicki 2007, §§27–29; Schwartz 2014, ch. 23; Coleman 1985, Dilatations."
topics:
  - Wilson–Fisher fixed point
  - epsilon expansion
  - critical exponents
  - O(N) model
  - phi-four theory
  - fixed points
canonicalTopics:
  - wilson-fisher-fixed-point
  - epsilon-expansion
  - critical-exponents
  - o-n-model
researchStatus:
  established:
    - "The one-loop epsilon-expansion derivation of the Wilson–Fisher fixed point is a standard bridge between perturbative QFT and critical phenomena."
  active:
    - "Precision critical exponents use high-loop series, resummation, conformal bootstrap, Monte Carlo, functional RG, and exact or numerical methods beyond the one-loop calculation shown here."
---

## Summary

The Wilson–Fisher epsilon expansion turns the statement "$\phi^4$ is marginal in four dimensions" into a controlled calculation of an interacting critical point below four dimensions. In the $O(N)$ scalar theory,

$$
\mathcal L_E
=
\frac12 \partial_\mu\phi^a\partial_\mu\phi^a
+\frac12 r\,\phi^a\phi^a
+\frac{g}{4!}(\phi^a\phi^a)^2,
\qquad a=1,\ldots,N,
$$

write

$$
\varepsilon\equiv 4-d.
$$

The one-loop beta function for the dimensionless quartic coupling is

$$
\beta_g
=
\left.\mu\frac{dg}{d\mu}\right|_{\text{bare fixed}}
=
-\varepsilon g+\frac{N+8}{48\pi^2}g^2+O(g^3).
$$

It has a nonzero perturbative fixed point

$$
\boxed{
g_*=\frac{48\pi^2}{N+8}\,\varepsilon+O(\varepsilon^2)
}
$$

for small positive $\varepsilon$. This is the Wilson–Fisher fixed point. The Gaussian fixed point controls mean-field behavior near $d=4$; the Wilson–Fisher fixed point controls the universal long-distance behavior of the interacting critical theory for $d<4$.

At one loop, the most important output is the relevant thermal eigenvalue

$$
y_t=\frac{1}{\nu}=2-\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2),
$$

or equivalently

$$
\boxed{
\nu=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2)
}
$$

while the field anomalous exponent begins only at two loops,

$$
\eta=O(\varepsilon^2).
$$

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Workflow for the Wilson-Fisher epsilon expansion: marginal quartic coupling in four dimensions, beta function in four minus epsilon dimensions, fixed point, linearized eigenvalues, and universal exponents.](/figures/renormalization-rg-eft/wilson-fisher-epsilon-expansion-map.svg)

<figcaption>

The epsilon expansion converts marginality of $(\phi^a\phi^a)^2$ at $d=4$ into a weakly coupled fixed point at $d=4-\varepsilon$. The fixed point $g_*=O(\varepsilon)$ makes critical exponents computable as series in $\varepsilon$.

</figcaption>
</figure>

:::note[One epsilon, two conventions]
This page uses the critical-phenomena convention $\varepsilon=4-d$. Many dimensional-regularization pages in this volume write $d=4-2\epsilon$. The relation is

$$
\varepsilon=2\epsilon.
$$

The physics is the same; only the symbol differs.
:::

## Prerequisites

You should know [Phi-Four Beta Function](/renormalization-rg-eft/model-calculation-library/phi-four-beta-function/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/).

The calculation is Euclidean because critical phenomena are most naturally written in terms of a partition function. The same counterterm algebra is the analytic continuation of the Lorentzian scalar-field calculation.

## What the epsilon expansion is doing

At the Gaussian fixed point in $d$ spacetime or statistical dimensions, the engineering dimension of a scalar field is

$$
[\phi]_{\text{eng}}=\frac{d-2}{2}.
$$

Therefore

$$
[(\phi^a\phi^a)^2]_{\text{eng}}=2(d-2),
$$

and the quartic coupling has dimension

$$
[g]=d-2(d-2)=4-d=\varepsilon.
$$

Thus $g$ is exactly marginal by engineering dimension at $d=4$, relevant for $d<4$, and irrelevant for $d>4$. Perturbation theory near $d=4$ is possible because the departure from marginality is small.

The competition is simple:

$$
\text{engineering scaling drives }g\text{ away from zero for }d<4,
$$

while one-loop fluctuations produce a positive $g^2$ term in the ultraviolet beta function. The balance creates a nonzero fixed point at $g_*=O(\varepsilon)$.

This is the core Wilson–Fisher move. One does not try to solve the strongly coupled three-dimensional Ising model directly. One solves a nearby problem where the fixed point is weakly coupled, then extrapolates and improves the expansion.

## The O(N) model and normalization

We use the Euclidean action

$$
S_E=\int d^d x\left[
\frac12 \partial_\mu\phi^a\partial_\mu\phi^a
+\frac12 r\,\phi^a\phi^a
+\frac{g}{4!}(\phi^a\phi^a)^2
\right].
$$

The index $a$ is summed from $1$ to $N$. The interaction is invariant under

$$
\phi^a\longrightarrow R^a{}_b\phi^b,
\qquad R\in O(N).
$$

Different books put factors of $4!$, $N$, $8\pi^2$, or $16\pi^2$ in different places. This page uses the normalization in which the one-loop quartic beta function is

$$
\beta_g=-\varepsilon g+\frac{N+8}{48\pi^2}g^2+O(g^3).
$$

For $N=1$, this reduces to

$$
\beta_g=-\varepsilon g+\frac{3g^2}{16\pi^2}+O(g^3),
$$

matching the previous $\phi^4$ beta-function page after identifying $\varepsilon=4-d$.

## The quartic beta function

The one-loop correction to the four-point vertex has the same local short-distance structure as in the one-component theory, but the internal $O(N)$ index contractions add a group-theory factor. The result is

$$
\delta g
=
\frac{N+8}{48\pi^2}\frac{g^2}{\varepsilon}+O(g^3)
$$

in a minimal-subtraction convention, up to the sign convention implicit in writing the counterterm Lagrangian. The bare coupling has the form

$$
g_0
=
\mu^{\varepsilon}
\left[
 g+\frac{N+8}{48\pi^2}\frac{g^2}{\varepsilon}+O(g^3)
\right].
$$

Since $g_0$ does not depend on $\mu$,

$$
0=\mu\frac{d g_0}{d\mu}.
$$

Writing

$$
\beta_g=-\varepsilon g+b g^2+O(g^3),
$$

and differentiating the pole term at fixed bare coupling gives

$$
b=\frac{N+8}{48\pi^2}.
$$

Thus

$$
\boxed{
\beta_g=-\varepsilon g+\frac{N+8}{48\pi^2}g^2+O(g^3)
}
$$

as announced.

:::tip[Why $N+8$ appears]
The $N$ counts internal field components that can circulate through the loop. The extra $8$ comes from the crossed index contractions among the external fields. In $N=1$ language these are the $s$, $t$, and $u$ one-loop fish diagrams; in $O(N)$ language the same contractions reorganize into the invariant tensor structures of $(\phi^a\phi^a)^2$.
:::

## Fixed points and their linearized flow

The zeros of the one-loop beta function are

$$
g_{\mathrm G}^*=0
$$

and

$$
g_*=\frac{48\pi^2}{N+8}\varepsilon+O(\varepsilon^2).
$$

The Gaussian fixed point is perturbatively exact at $g=0$. The Wilson–Fisher fixed point exists perturbatively for $\varepsilon>0$ and small.

The linearized eigenvalue in the quartic direction is

$$
\omega
=
\left.\frac{d\beta_g}{dg}\right|_{g_*}
=
-\varepsilon+2\frac{N+8}{48\pi^2}g_*+O(\varepsilon^2)
=
\varepsilon+O(\varepsilon^2).
$$

With the ultraviolet RG time $t=\log\mu$, this positive derivative means that $g-g_*$ grows toward the UV and shrinks toward the IR. In statistical-physics language, $\omega$ is the leading correction-to-scaling exponent associated with the least irrelevant scalar perturbation at the Wilson–Fisher fixed point.

The mass parameter is different. It is the relevant perturbation that must be tuned to reach criticality.

## Thermal eigenvalue and the exponent nu

The temperature-like perturbation is represented by the $O(N)$ singlet operator

$$
\phi^a\phi^a.
$$

Equivalently, one studies the running of the mass parameter $r$. To one loop, the dimensionless mass perturbation has RG eigenvalue

$$
y_t=2-\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2).
$$

This number is the inverse correlation-length exponent:

$$
y_t=\frac{1}{\nu}.
$$

Expanding gives

$$
\nu
=\frac{1}{2-\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2)}
=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2).
$$

For the Ising universality class, $N=1$, so

$$
\nu
=\frac12+\frac{1}{12}\varepsilon+O(\varepsilon^2).
$$

Setting $\varepsilon=1$ naively gives $\nu\approx0.583$. The actual three-dimensional Ising exponent is larger. This is not a failure of the idea; it is a reminder that precision requires higher orders and resummation, or nonperturbative methods such as bootstrap and Monte Carlo.

## The field exponent eta

The anomalous dimension of the elementary field begins at two loops in the $O(N)$ model:

$$
\eta=2\gamma_\phi(g_*)=O(\varepsilon^2).
$$

More explicitly,

$$
\eta=\frac{N+2}{2(N+8)^2}\varepsilon^2+O(\varepsilon^3)
$$

in the standard normalization. Since this is beyond the one-loop calculation, it should not be mixed into one-loop-only derivations unless the order is stated clearly.

At leading nontrivial order in this page,

$$
\Delta_\phi=\frac{d-2+\eta}{2}
=1-\frac{\varepsilon}{2}+O(\varepsilon^2).
$$

The smallness of $\eta$ near four dimensions is one reason mean-field theory starts as a reasonable first approximation.

## Leading critical exponents

Using scaling relations, the one-loop epsilon expansion gives the following leading exponents for the $O(N)$ model:

| Exponent | Meaning | Leading epsilon expansion |
|---|---|---|
| $\nu$ | correlation length, $\xi\sim |t|^{-\nu}$ | $\displaystyle \frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2)$ |
| $\eta$ | two-point anomalous exponent | $\displaystyle O(\varepsilon^2)$ |
| $\gamma$ | susceptibility, $\chi\sim |t|^{-\gamma}$ | $\displaystyle 1+\frac{N+2}{2(N+8)}\varepsilon+O(\varepsilon^2)$ |
| $\alpha$ | heat capacity, $C\sim |t|^{-\alpha}$ | $\displaystyle \frac{4-N}{2(N+8)}\varepsilon+O(\varepsilon^2)$ |
| $\beta_{\text{mag}}$ | order parameter, $M\sim (-t)^{\beta_{\text{mag}}}$ | $\displaystyle \frac12-\frac{3}{2(N+8)}\varepsilon+O(\varepsilon^2)$ |
| $\delta_{\text{mag}}$ | critical isotherm, $M\sim h^{1/\delta_{\text{mag}}}$ | $\displaystyle 3+\varepsilon+O(\varepsilon^2)$ |
| $\omega$ | leading correction to scaling | $\displaystyle \varepsilon+O(\varepsilon^2)$ |

Here $t$ is the reduced temperature-like scaling field, not the RG time. The symbol $\beta_{\text{mag}}$ is the magnetization exponent, not a beta function. The symbol $\delta_{\text{mag}}$ is the critical-isotherm exponent, not a counterterm.

## The Ising example

For $N=1$ and $d=3$, one sets $\varepsilon=1$. The leading formulas give

$$
\nu=\frac12+\frac{1}{12}=\frac{7}{12}\approx0.583,
$$

$$
\eta=O(\varepsilon^2),
$$

$$
\gamma=1+\frac{1}{6}=\frac76\approx1.167,
$$

and

$$
\beta_{\text{mag}}=\frac12-\frac16=\frac13.
$$

These numbers are not precision estimates. They are a controlled first deformation away from mean-field theory. The great achievement of the epsilon expansion is not that the one-loop value at $\varepsilon=1$ is numerically perfect. It is that the calculation identifies the fixed point, organizes corrections systematically, and explains why universal exponents are computable from local RG data.

## Why this is a model calculation

This page belongs in the model calculation library because it shows how several abstract ideas meet in one calculation:

| Abstract concept | Concrete realization here |
|---|---|
| marginal operator | $(\phi^a\phi^a)^2$ at $d=4$ |
| beta function | $\beta_g=-\varepsilon g+(N+8)g^2/(48\pi^2)+\cdots$ |
| fixed point | $g_*=48\pi^2\varepsilon/(N+8)+\cdots$ |
| relevant direction | the mass or temperature perturbation |
| irrelevant direction | the deviation of $g$ from $g_*$ |
| universal exponent | $\nu^{-1}=2-(N+2)\varepsilon/(N+8)+\cdots$ |
| scheme independence | critical exponents, not the coordinate value of $g_*$ |

The fixed-point coordinate $g_*$ is scheme-dependent beyond the leading statement that it is $O(\varepsilon)$. The critical exponents are physical universal data.

## Common pitfalls

**Confusing the two epsilons.** Dimensional regularization in particle-physics pages often uses $d=4-2\epsilon$. Critical phenomena usually uses $d=4-\varepsilon$. Translate before comparing coefficients.

**Thinking the fixed-point coupling is an observable.** The numerical value of $g_*$ depends on how the coupling is defined. Critical exponents and properly normalized CFT data are the universal outputs.

**Calling the Gaussian and Wilson–Fisher fixed points the same theory.** They collide at $\varepsilon=0$, but for $\varepsilon>0$ the Wilson–Fisher fixed point is interacting.

**Setting $\varepsilon=1$ too literally.** The three-dimensional theory is reached by extrapolation. Precision requires higher-loop information and resummation, or independent nonperturbative methods.

**Forgetting the mass tuning.** The Wilson–Fisher fixed point has at least one relevant direction. Reaching criticality requires tuning the temperature-like parameter.

**Assuming $\eta$ appears at one loop.** In the $O(N)$ $\phi^4$ model, $\eta$ starts at two loops. The exponent $\nu$ already receives a one-loop correction.

## Relations to other pages

This page builds directly on [Phi-Four Beta Function](/renormalization-rg-eft/model-calculation-library/phi-four-beta-function/) and gives the model-calculation version of [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/).

It also prepares for [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/), [Wilson–Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/), [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/), and [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/).

## Research status

The one-loop epsilon expansion is established textbook physics. The frontier begins when one asks for precision and for nonperturbative definitions: high-order perturbative series are divergent and require resummation; the three-dimensional fixed point is strongly coupled from the viewpoint of $\varepsilon=1$; and modern determinations combine perturbative RG, conformal bootstrap, Monte Carlo, functional RG, large-$N$ methods, and rigorous constraints.

The conceptual status is firmer than the one-loop numerics: the Wilson–Fisher fixed point is the organizing critical theory for short-range $O(N)$ models below four dimensions, and the epsilon expansion remains one of the cleanest ways to see why.

## Exercises

### Exercise 1: Fixed point and correction exponent

Starting from

$$
\beta_g=-\varepsilon g+A g^2,
\qquad
A=\frac{N+8}{48\pi^2},
$$

find the nonzero fixed point and the linearized eigenvalue $\omega=d\beta_g/dg|_{g_*}$.

<details><summary><strong>Solution</strong></summary>

The fixed points solve

$$
g(-\varepsilon+Ag)=0.
$$

Thus

$$
g_{\mathrm G}^*=0,
\qquad
g_* = \frac{\varepsilon}{A}=\frac{48\pi^2}{N+8}\varepsilon.
$$

The derivative is

$$
\frac{d\beta_g}{dg}=-\varepsilon+2Ag.
$$

At the nonzero fixed point,

$$
\omega=-\varepsilon+2A\frac{\varepsilon}{A}=\varepsilon.
$$

So the leading correction-to-scaling exponent is $\omega=\varepsilon+O(\varepsilon^2)$.

</details>

### Exercise 2: Inverting the thermal eigenvalue

Given

$$
\frac{1}{\nu}=2-a\varepsilon+O(\varepsilon^2),
\qquad
 a=\frac{N+2}{N+8},
$$

show that

$$
\nu=\frac12+\frac{a}{4}\varepsilon+O(\varepsilon^2).
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
\nu=\frac{1}{2-a\varepsilon}
=\frac12\frac{1}{1-a\varepsilon/2}.
$$

Expanding $1/(1-x)=1+x+O(x^2)$ gives

$$
\nu=\frac12\left(1+\frac{a\varepsilon}{2}+O(\varepsilon^2)\right)
=\frac12+\frac{a}{4}\varepsilon+O(\varepsilon^2).
$$

Substituting $a=(N+2)/(N+8)$ gives the result on the page.

</details>

### Exercise 3: Susceptibility exponent from scaling

Use the scaling relation

$$
\gamma=(2-\eta)\nu
$$

and the facts

$$
\eta=O(\varepsilon^2),
\qquad
\nu=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2)
$$

to derive the one-loop expression for $\gamma$.

<details><summary><strong>Solution</strong></summary>

To first order in $\varepsilon$, $\eta$ can be set to zero because it starts at $O(\varepsilon^2)$. Therefore

$$
\gamma=(2+O(\varepsilon^2))\left[\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2)\right].
$$

Multiplying gives

$$
\gamma=1+\frac{N+2}{2(N+8)}\varepsilon+O(\varepsilon^2).
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\varepsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on $O(N)$ models, dimensional regularization, the epsilon expansion, and critical exponents.
- Mark Srednicki, *Quantum Field Theory*, especially sections on renormalization, beta functions, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23 for RG methods and scalar RG flows.
- Sidney Coleman, "Dilatations," in *Aspects of Symmetry*, for anomalous dimensions, Callan–Symanzik equations, and the return of scaling.

## Version history

- 2026-06-19: First polished draft. Added one-loop $O(N)$ beta function, Wilson–Fisher fixed point, leading exponents, exercises, and figure.
