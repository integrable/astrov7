---
title: "Epsilon Expansion"
description: "Explains the epsilon expansion as a controlled perturbative method for critical fixed points near their upper critical dimension."
sidebar:
  label: "Epsilon Expansion"
  order: 8
level: Graduate
status: "Polished draft"
source: "Wilson and Fisher 1972; Wilson and Kogut 1974; Coleman 1985, Dilatations; Weinberg 1996, ch. 18; Zinn-Justin 2021; Cardy 1996; Goldenfeld 1992."
topics:
  - epsilon expansion
  - Wilson–Fisher fixed point
  - critical exponents
  - O(N) model
  - dimensional continuation
  - universality
canonicalTopics:
  - epsilon-expansion
  - critical-exponents
  - wilson-fisher-fixed-point
  - o-n-model
researchStatus:
  established:
    - "The epsilon expansion is the standard perturbative expansion of critical fixed points around their upper critical dimension, with universal exponents extracted from RG eigenvalues at the fixed point."
  active:
    - "High-order epsilon expansions, resummation methods, conformal bootstrap comparisons, and mixed epsilon/large-N expansions remain active tools for precision critical phenomena."
---

## Summary

The **epsilon expansion** is a controlled way to study an interacting critical point by moving the spacetime or statistical dimension close to a dimension where the interaction is weak.

For the short-range $O(N)$ model, the upper critical dimension is four. One writes

$$
\varepsilon\equiv 4-d,
$$

and studies the theory in $d=4-\varepsilon$. The quartic coupling is then slightly relevant at the Gaussian fixed point, and the one-loop beta function has the form

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

The two terms compete and produce the Wilson–Fisher fixed point

$$
g_* = \frac{6\varepsilon}{N+8}+O(\varepsilon^2).
$$

Since $g_*=O(\varepsilon)$, critical exponents and scaling dimensions can be computed as power series in $\varepsilon$. One then extrapolates, usually with resummation, to physical dimensions such as $d=3$, where $\varepsilon=1$.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Map of the epsilon expansion from the upper critical dimension to physical three dimensions](/figures/renormalization-rg-eft/epsilon-expansion-bridge.svg)

<figcaption>

The epsilon expansion begins at the upper critical dimension, where the interaction is marginal, then moves to $d=4-\varepsilon$. The fixed point is weakly coupled for $\varepsilon\ll1$; physical three-dimensional estimates require extrapolation and, in precision work, resummation at $\varepsilon=1$.

</figcaption>
</figure>

:::note[One sentence to remember]
The epsilon expansion turns a strongly interacting critical point in $d=3$ into a weakly interacting fixed point in $d=4-\varepsilon$, computes universal data as series in $\varepsilon$, and then carefully returns to the physical dimension.
:::

## Prerequisites

You should know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), and [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/).

The technical input is ordinary perturbative renormalization. The conceptual input is more important: the universal data of a critical point are read from RG flow near a fixed point, not from the microscopic lattice Hamiltonian.

## Core idea

The hard problem is to understand an interacting fixed point in a physical dimension such as $d=3$. The trick is to embed the problem in a continuous family of dimensions and expand around a point where the fixed point becomes weakly coupled.

For the $O(N)$ model, the scalar field has Gaussian engineering dimension

$$
[\phi]_{\mathrm G}=\frac{d-2}{2}.
$$

The quartic operator has Gaussian dimension

$$
[(\phi^a\phi^a)^2]_{\mathrm G}=2(d-2),
$$

so its coupling has engineering dimension

$$
[u]=d-2(d-2)=4-d.
$$

Thus the quartic interaction is marginal at $d=4$, irrelevant above $d=4$, and relevant below $d=4$. If $d=4-\varepsilon$ with small positive $\varepsilon$, the interaction is only slightly relevant. The flow has enough time to be seen perturbatively before it reaches the interacting fixed point.

The philosophy is compact:

$$
\text{upper critical dimension}
\quad +\quad
\text{small departure}
\quad =\quad
\text{weakly interacting critical point}.
$$

This is a very Wilsonian move. Instead of treating the physical dimension as sacred, one changes the dimension to reveal the organizing structure of the fixed point.

## Setup and conventions

This page uses the critical-phenomena convention

$$
\varepsilon\equiv4-d.
$$

This is not the same symbol as the dimensional-regularization parameter $\epsilon_{\mathrm{DR}}$ often used in loop calculations with $d=4-2\epsilon_{\mathrm{DR}}$. Here $\varepsilon$ measures distance below the upper critical dimension.

The Euclidean $O(N)$ scalar model is

$$
S=\int d^d x\left[
\frac12\partial_\mu\phi^a\partial^\mu\phi^a
+\frac12 r\,\phi^a\phi^a
+\frac{u}{4!}(\phi^a\phi^a)^2
\right],
\qquad a=1,\ldots,N.
$$

The $O(N)$ symmetry acts by

$$
\phi^a\mapsto R^a{}_b\phi^b,
\qquad R\in O(N).
$$

The parameter $r$ is the thermal perturbation. To reach criticality, it must be tuned to a critical value $r_c$. The coupling $u$ controls the quartic interaction. A dimensionless renormalized coupling $g$ is obtained by absorbing powers of the renormalization scale and conventional factors such as $4\pi$.

We use the common normalization in which

$$
\beta_g\equiv\mu\frac{dg}{d\mu}
=-\varepsilon g+\frac{N+8}{6}g^2+O(g^3).
$$

The beta function is written in UV RG time $t=\log\mu$. If one uses IR coarse-graining time $\ell=\log b$, the sign of the flow is reversed:

$$
\frac{dg}{d\ell}=\varepsilon g-\frac{N+8}{6}g^2+O(g^3).
$$

Both equations describe the same physics.

## The fixed point as a series

The fixed point is defined by

$$
\beta_g(g_*)=0.
$$

At one loop,

$$
0=-\varepsilon g_*+\frac{N+8}{6}g_*^2+O(g_*^3),
$$

so the nonzero fixed point is

$$
g_* = \frac{6\varepsilon}{N+8}+O(\varepsilon^2).
$$

This single equation explains why the epsilon expansion is possible. Loop corrections are powers of $g$, but at the fixed point $g$ is itself a power of $\varepsilon$. Therefore perturbation theory at the fixed point becomes an expansion in $\varepsilon$.

If the beta function is known to two loops in the convention

$$
\beta_g=-\varepsilon g+\frac{N+8}{6}g^2
-\frac{3N+14}{12}g^3+O(g^4),
$$

then solving order by order gives

$$
g_*=\frac{6\varepsilon}{N+8}
+\frac{18(3N+14)}{(N+8)^3}\varepsilon^2
+O(\varepsilon^3).
$$

The fixed-point coordinate $g_*$ is scheme dependent beyond its existence and qualitative role. Critical exponents and scaling dimensions are the universal quantities.

## Critical exponents from RG eigenvalues

The epsilon expansion becomes physically useful when one computes RG eigenvalues at the fixed point. Let $t_r$ denote the thermal scaling field, the perturbation that moves the system away from the critical temperature. Near the Wilson–Fisher fixed point,

$$
\frac{dt_r}{d\ell}=y_t\,t_r+\cdots.
$$

The correlation length exponent is

$$
\nu=\frac{1}{y_t}.
$$

For the $O(N)$ model, the one-loop result is

$$
y_t=2-\frac{N+2}{N+8}\varepsilon+O(\varepsilon^2),
$$

and therefore

$$
\nu
=\frac12+\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2).
$$

The anomalous dimension of the fundamental field begins at two loops:

$$
\eta=\frac{N+2}{2(N+8)^2}\varepsilon^2+O(\varepsilon^3).
$$

This is why the first-order epsilon expansion improves some exponents but leaves $\eta$ at its mean-field value. The leading one-loop tadpole corrects the mass term but is momentum independent; field anomalous dimension requires momentum-dependent self-energy corrections, which first contribute at the next order in this model.

The leading correction-to-scaling exponent associated with the quartic direction is

$$
\omega=\left.\frac{d\beta_g}{dg}\right|_{g_*}
=\varepsilon+O(\varepsilon^2),
$$

up to the sign convention for RG time. It measures how fast perturbations along the leading irrelevant direction die away near the fixed point.

## What is actually expanded

The epsilon expansion is not only an expansion of a coupling. It gives formal series for universal data:

$$
\Delta_i(\varepsilon)=\Delta_i^{(0)}+\Delta_i^{(1)}\varepsilon+\Delta_i^{(2)}\varepsilon^2+\cdots,
$$

where $\Delta_i$ is a scaling dimension, and

$$
\nu(\varepsilon)=\nu_0+\nu_1\varepsilon+\nu_2\varepsilon^2+\cdots,
\qquad
\eta(\varepsilon)=\eta_0+\eta_1\varepsilon+\eta_2\varepsilon^2+\cdots.
$$

For the Wilson–Fisher fixed point, the zeroth-order values are Gaussian or mean-field values. The corrections encode the interacting critical theory.

A typical workflow is:

| Step | Operation | Output |
|---:|---|---|
| 1 | Continue the theory to $d=4-\varepsilon$ | couplings acquire small engineering dimensions |
| 2 | Renormalize in dimensional regularization and MS | beta functions and anomalous dimensions |
| 3 | Solve $\beta_i(g_*)=0$ | fixed-point coordinates as series in $\varepsilon$ |
| 4 | Linearize the RG near $g_*$ | universal RG eigenvalues |
| 5 | Evaluate or resum at $\varepsilon=1$ | estimates for three-dimensional universality classes |

Only the last step is uncontrolled by small $\varepsilon$ alone. That is why serious numerical use of the epsilon expansion relies on resummation and comparison with other methods.

## Why analytic continuation in dimension is allowed

A first encounter with the epsilon expansion can feel illicit. What does it mean to study a magnet in $3.7$ dimensions?

The answer is that the continuum field theory is first treated as a set of analytically continued integrals and RG equations. Feynman integrals, scaling equations, and renormalization constants can be defined for complex $d$ in dimensional regularization. The universal quantities obtained near a fixed point can then be analytically continued as formal series.

This does not mean that a microscopic lattice magnet literally lives in noninteger dimension. It means that universal continuum data can be embedded in a family of local field theories whose perturbative expansion is well defined near the upper critical dimension.

This is no stranger than using complex angular momentum, analytic continuation of spin, or zeta-function regularization. The continued object is a calculational and conceptual bridge. The physical interpretation returns when one evaluates the universal data at the desired physical dimension.

## From epsilon series to three dimensions

For three-dimensional critical phenomena,

$$
\varepsilon=1.
$$

A formal series in $\varepsilon$ is then being used at a value that is not small. A first-order estimate may be qualitatively helpful, but precision requires more.

There are three increasingly serious levels of use:

| Use | What one does | Reliability |
|---|---|---|
| qualitative | keep one or two leading terms | good for structure and signs |
| semi-quantitative | evaluate a short truncated series | useful but often rough |
| precision | use high-order series plus Borel-type resummation | competitive for many exponents |

The reason resummation is needed is that perturbative QFT series are typically asymptotic rather than convergent. Coefficients eventually grow factorially. A divergent asymptotic series can still contain excellent numerical information if it is truncated and resummed correctly.

For example, the one-loop Ising estimate $N=1$ gives

$$
\nu=\frac12+\frac{1}{12}\varepsilon+O(\varepsilon^2),
$$

so at $\varepsilon=1$ it gives $\nu\approx0.583$. This is not a precision value, but it moves in the right direction from the mean-field value $1/2$. Higher orders and resummation bring the estimate much closer to the observed and simulated three-dimensional Ising value.

The lesson is not that the first term is magic. The lesson is that a controlled expansion near $d=4$ can be systematically improved and cross-checked.

## The upper critical dimension viewpoint

The epsilon expansion is part of a broader pattern. A critical theory often has an **upper critical dimension** $d_c$ where a key interaction is marginal. One then writes

$$
\varepsilon=d_c-d
$$

and expands below $d_c$.

Examples include:

| Problem | Upper critical dimension | Small parameter |
|---|---:|---|
| short-range $O(N)$ criticality | $4$ | $4-d$ |
| tricritical scalar theory with $\phi^6$ interaction | $3$ | $3-d$ |
| percolation and related cubic theories | $6$ | $6-d$ |
| certain long-range models | depends on the long-range exponent | distance from marginality |

The specific fields and interactions change, but the method is the same: identify a dimension where the important coupling is marginal, then perturb away from it.

## Epsilon expansion and universality

The epsilon expansion is powerful because it computes universal data without caring about most microscopic details. The lattice Hamiltonian, short-distance cutoff, and detailed shape of local interactions affect nonuniversal quantities. They do not affect the fixed-point scaling dimensions and critical exponents, once the universality class is fixed.

For an $O(N)$ model with short-range interactions, the inputs that matter are essentially:

| Input | Role |
|---|---|
| dimension $d$ | controls engineering dimensions and phase space |
| symmetry $O(N)$ | controls allowed operators and combinatorics |
| locality and short-range interactions | justify local continuum action |
| number of relevant perturbations | determines how many tunings are needed |

The epsilon expansion makes this universality concrete. The coefficients in the exponent series come from continuum diagrams and group factors, not from microscopic lattice chemistry.

## Relation to minimal subtraction

In minimal subtraction, the beta functions are extracted from pole terms in dimensional regularization. This is especially clean for epsilon expansions because the same formalism both regulates diagrams and keeps the dimension variable.

For a coupling with engineering dimension $\varepsilon$, one writes schematically

$$
g_0=\mu^{\varepsilon}Z_g(g,\varepsilon)g.
$$

Holding the bare coupling fixed gives

$$
0=\mu\frac{dg_0}{d\mu}
=\mu^{\varepsilon}\left[
\varepsilon Z_g g+\beta_g\frac{\partial}{\partial g}(Z_g g)
\right].
$$

The pole part of $Z_g$ determines the loop terms in $\beta_g$. The classical $-\varepsilon g$ term comes from the explicit factor of $\mu^\varepsilon$, with sign depending on whether one writes the beta function in UV or IR time.

This is why the epsilon expansion naturally belongs at the intersection of renormalized perturbation theory and Wilsonian scaling.

## What the epsilon expansion does not do

The epsilon expansion does not prove that the physical three-dimensional fixed point exists by itself. It gives a controlled fixed point for small $\varepsilon$ and a powerful extrapolation tool. Existence and precise numerical data in $d=3$ are supported by many additional methods: Monte Carlo, conformal bootstrap, high-temperature expansions, functional RG, large-$N$ expansions, and experiments.

It also does not compute nonuniversal amplitudes without extra microscopic input. Critical exponents are universal. Critical temperatures, lattice-scale amplitudes, and detailed crossover functions depend on normalization choices and microscopic details.

Finally, it does not make the theory weakly coupled in $d=3$. At $\varepsilon=1$, the Wilson–Fisher fixed point is not parametrically weak. The epsilon expansion is a controlled path to the theory, not a proof that every truncated expression is accurate.

## Common pitfalls

**Confusing the two epsilons.** In critical phenomena, $\varepsilon=4-d$. In many perturbative amplitude calculations, dimensional regularization uses $d=4-2\epsilon_{\mathrm{DR}}$. They are related only by convention, not by a universal identity.

**Plugging in $\varepsilon=1$ too casually.** A first-order epsilon expansion is a guide, not a precision estimate. For precision, use higher orders, resummation, and cross-checks.

**Thinking noninteger dimension is a literal lattice dimension.** The continuation is a field-theoretic analytic device. The physical interpretation returns when universal quantities are evaluated in the target dimension.

**Treating $g_*$ as observable.** The fixed-point coordinate depends on coupling normalization and scheme. Critical exponents and scaling dimensions are the observable universal data.

**Forgetting relevant directions.** Finding $g_*$ is not enough. The thermal perturbation must be tuned to reach criticality.

**Calling mean-field theory wrong above four dimensions without caveats.** Above the upper critical dimension, the Gaussian fixed point controls leading exponents, but dangerous irrelevant variables can affect scaling forms and finite-size scaling.

## Relations to other pages

This page is the method page following [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/). That page derives the prototype fixed point; this page explains the expansion method built around it.

It prepares for [Large-N Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/large-n-expansion/), which provides a different controlled limit: large number of field components at fixed dimension. The two methods overlap and cross-check each other in the $O(N)$ model.

For the RG infrastructure, see [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/). For the statistical interpretation, see [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) and [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/).

## Research status

The conceptual framework of the epsilon expansion is established. It is one of the standard pillars of modern critical phenomena and perturbative RG.

The active frontier is not whether the method exists, but how best to extract high-precision and structurally meaningful information from it. Modern work uses high-loop series, Borel and conformal-map resummation, conformal bootstrap constraints, large-$N$ comparisons, and numerical simulations. In some problems, epsilon expansions are also used away from simple scalar models, including gauge-Yukawa theories, multicritical points, disorder problems, long-range interactions, and nonequilibrium universality classes.

The honest status is: the epsilon expansion is rigorous as a formal perturbative construction near the upper critical dimension, extremely useful as a resummed approximation in physical dimensions, and not by itself a substitute for nonperturbative existence or precision methods.

## Exercises

### Exercise 1: Fixed point and correction-to-scaling exponent

Suppose

$$
\beta_g=-\varepsilon g+A g^2+O(g^3),
\qquad A>0.
$$

Find the nonzero fixed point to leading order in $\varepsilon$ and compute $\omega=d\beta_g/dg|_{g_*}$.

<details><summary><strong>Solution</strong></summary>

The fixed point solves

$$
0=-\varepsilon g_*+A g_*^2+O(g_*^3).
$$

Besides $g_*=0$, the nonzero solution is

$$
g_* = \frac{\varepsilon}{A}+O(\varepsilon^2).
$$

The linearized eigenvalue in UV RG time is

$$
\left.\frac{d\beta_g}{dg}\right|_{g_*}
=-\varepsilon+2A\frac{\varepsilon}{A}+O(\varepsilon^2)
=\varepsilon+O(\varepsilon^2).
$$

Thus the leading correction-to-scaling exponent is $\omega=\varepsilon+O(\varepsilon^2)$, up to the convention for RG time.

</details>

### Exercise 2: Expanding the inverse exponent

Given

$$
y_t=2-a\varepsilon+O(\varepsilon^2),
$$

show that

$$
\nu=\frac{1}{y_t}
=\frac12+\frac{a}{4}\varepsilon+O(\varepsilon^2).
$$

Apply this to $a=(N+2)/(N+8)$.

<details><summary><strong>Solution</strong></summary>

Factor out the leading value:

$$
y_t=2\left(1-\frac{a}{2}\varepsilon+O(\varepsilon^2)\right).
$$

Then use $(1-x)^{-1}=1+x+O(x^2)$:

$$
\frac{1}{y_t}
=\frac12\left(1+\frac{a}{2}\varepsilon+O(\varepsilon^2)\right)
=\frac12+\frac{a}{4}\varepsilon+O(\varepsilon^2).
$$

For the $O(N)$ model,

$$
\nu=\frac12+
\frac{N+2}{4(N+8)}\varepsilon+O(\varepsilon^2).
$$

</details>

### Exercise 3: Why eta starts at two loops

In scalar $\phi^4$ theory, the one-loop correction to the two-point function is a tadpole independent of external momentum. Explain why this means that $\eta$ begins at $O(\varepsilon^2)$ rather than $O(\varepsilon)$ at the Wilson–Fisher fixed point.

<details><summary><strong>Solution</strong></summary>

The exponent $\eta$ is the anomalous dimension of the field. It is determined by wavefunction renormalization, which renormalizes the coefficient of the kinetic term or, equivalently, the momentum-dependent part of the two-point function.

At one loop in $\phi^4$ theory, the tadpole self-energy is momentum independent. It shifts the mass term, but it does not change the coefficient of $p^2$. Therefore it does not produce field anomalous dimension at one loop.

The first momentum-dependent self-energy correction appears at two loops. Since the fixed-point coupling satisfies $g_*=O(\varepsilon)$, a two-loop field anomalous dimension is $O(g_*^2)=O(\varepsilon^2)$.

</details>

### Exercise 4: Why fixed-point coordinates are not universal

Let $g'=g+c g^2+O(g^3)$ be a finite coupling redefinition. Explain why the numerical value of $g_*$ changes, but the existence of a nearby nonzero fixed point and its RG eigenvalues do not change when computed consistently.

<details><summary><strong>Solution</strong></summary>

A change of scheme is a change of coordinate on coupling space. The beta function transforms as

$$
\beta_{g'}=\frac{dg'}{dg}\beta_g.
$$

If $\beta_g(g_*)=0$, then $\beta_{g'}(g'_*)=0$ with $g'_*=g'(g_*)$. The coordinate value changes because $g'$ is a different coordinate.

The linearized flow eigenvalue at a one-dimensional fixed point is invariant under a smooth redefinition. Differentiating the transformed beta function and evaluating at the fixed point gives the same eigenvalue because the term proportional to $\beta_g$ vanishes at $g_*$. Thus the coordinate location is not universal, but the local scaling exponent is.

</details>

## References

- Kenneth G. Wilson and Michael E. Fisher, "Critical Exponents in 3.99 Dimensions," *Physical Review Letters* **28** (1972) 240–243.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\varepsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Asymptotic Freedom."
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG, and critical exponents.
- John Cardy, *Scaling and Renormalization in Statistical Physics*.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*.
- Hagen Kleinert and Verena Schulte-Frohlinde, *Critical Properties of $\phi^4$-Theories*.

## Version history

- 2026-06-17: First polished draft. Introduced the epsilon expansion as a method page following the Wilson–Fisher fixed point, with fixed-point expansion, leading exponents, practical resummation cautions, and exercises.
