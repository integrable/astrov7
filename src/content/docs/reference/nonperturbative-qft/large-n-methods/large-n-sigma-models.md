---
title: "Large-N Sigma Models"
description: "Derives the large-N saddle-point treatment of nonlinear sigma models, including mass generation in the O(N) model and the CP N minus one model."
sidebar:
  label: "Large-N Sigma Models"
  order: 2
level: Advanced
status: "Polished draft"
source: "Polyakov; Shifman; Mariño; Zinn-Justin; Coleman; standard nonlinear sigma-model literature."
topics:
  - large-N sigma models
  - nonlinear sigma model
  - O(N) model
  - CP N minus one model
  - gap equation
  - mass generation
  - asymptotic freedom
  - Lagrange multiplier
  - induced gauge field
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - large-n-sigma-models
  - o-n-sigma-model
  - cp-n-minus-one-model
  - mass-gap
researchStatus:
  established:
    - "Two-dimensional O(N) and CP N minus one sigma models are standard large-N laboratories for dynamical mass generation, gap equations, and constrained-field path integrals."
  active:
    - "Finite-N behavior, theta dependence, resurgence, and the relation of large-N saddles to exact or numerical results remain model-dependent and are often research-level."
---

## Summary

Large-N sigma models are nonlinear field theories in which the microscopic fields are constrained to live on a target space whose size grows with $N$. The simplest example is the $O(N)$ nonlinear sigma model, whose fields obey

$$
\phi_i(x)\phi_i(x)=\frac{N}{g_0},
\qquad i=1,\dots,N.
$$

The large-$N$ method replaces the constraint by a Lagrange multiplier, integrates out the $N$ fields, and obtains an effective action proportional to $N$:

$$
S_{\rm eff}[\sigma]
=N\left[\frac12\operatorname{Tr}\log(-\partial^2+\sigma)
-\frac{1}{2g_0}\int d^dx\,\sigma\right].
$$

A constant saddle $\sigma=M^2$ then obeys a gap equation,

$$
\frac1{g_0}
=\int^\Lambda\frac{d^dp}{(2\pi)^d}\frac1{p^2+M^2}.
$$

In two dimensions this produces a dynamically generated scale. The perturbative picture of $N-1$ massless Goldstone fields is replaced, at large $N$, by a massive theory. This is the main nonperturbative lesson: the constraint and the measure know more than the naive classical vacuum.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Large-N sigma-model workflow: constrained fields, auxiliary variables, integration over N fields, large-N saddle, gap equation, generated scale, O(N) and CP N minus one outputs, and 1/N corrections.](/figures/nonperturbative-qft/large-n-sigma-model-pipeline.svg)

<figcaption>

The large-$N$ sigma-model saddle. The constraint is imposed by a Lagrange multiplier $\sigma$; integrating out $N$ constrained components produces $N\operatorname{Tr}\log(-\partial^2+\sigma)$. The constant saddle $\sigma=M^2$ fixes the correlation length $\xi=M^{-1}$ and can generate a nonperturbative mass scale in two dimensions.

</figcaption>
</figure>

## Prerequisites

Read [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) first. You should also know [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/), [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), and [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/).

The main technical input is the Gaussian determinant

$$
\int\mathcal D\phi\,\exp\left[-\frac12\int \phi K\phi\right]
\propto (\det K)^{-1/2},
$$

and the main physical input is the difference between spontaneous symmetry breaking in a classical saddle and the quantum realization of symmetry in low dimensions.

## Core idea

A nonlinear sigma model has two kinds of data. There is a base spacetime, where the quantum field lives, and there is a target space, where the field takes its values. In the $O(N)$ model the target is a sphere $S^{N-1}$. In the $CP^{N-1}$ model the target is complex projective space.

The large-$N$ trick is that the number of target-space components is large. Even though the field is constrained, the $N$ components can still be integrated out after introducing auxiliary fields. The result is a collective effective action multiplied by $N$, so the path integral is controlled by a saddle.

The essential chain is

$$
\text{constraint}
\quad\Longrightarrow\quad
\text{Lagrange multiplier}
\quad\Longrightarrow\quad
N\text{ identical Gaussian fields}
\quad\Longrightarrow\quad
N\operatorname{Tr}\log
\quad\Longrightarrow\quad
\text{gap equation}.
$$

This is a sharper version of the vector-model story. Instead of using an auxiliary field to rewrite a quartic interaction, we use it to enforce a nonlinear target-space constraint.

## Setup and conventions

We work in Euclidean signature. The $O(N)$ nonlinear sigma model may be written as

$$
S_E[\phi]
=\frac12\int d^dx\, (\partial_\mu\phi_i)(\partial_\mu\phi_i),
\qquad
\phi_i\phi_i=\frac{N}{g_0}.
$$

The coupling $g_0$ is chosen so that the radius squared of the target sphere scales as $N/g_0$. With this normalization, the action is $O(N)$ at large $N$ and has a smooth saddle-point limit.

To impose the constraint, introduce a Lagrange multiplier field $\sigma(x)$:

$$
S_E[\phi,\sigma]
=\frac12\int d^dx\left[
(\partial_\mu\phi_i)^2
+\sigma\left(\phi_i\phi_i-\frac{N}{g_0}\right)
\right].
$$

The precise contour for $\sigma$ is a functional-integral subtlety. For saddle-point physics, the useful stationary value is real and positive in the massive phase,

$$
\sigma=M^2.
$$

## The O(N) saddle and the gap equation

The $N$ fields $\phi_i$ appear quadratically:

$$
S_E[\phi,\sigma]
=\frac12\int d^dx\,\phi_i(-\partial^2+\sigma)\phi_i
-\frac{N}{2g_0}\int d^dx\,\sigma.
$$

Integrating out all $N$ components gives

$$
Z=\int\mathcal D\sigma\,e^{-S_{\rm eff}[\sigma]},
$$

where

$$
S_{\rm eff}[\sigma]
=N\left[\frac12\operatorname{Tr}\log(-\partial^2+\sigma)
-\frac{1}{2g_0}\int d^dx\,\sigma\right].
$$

The saddle equation is

$$
0=\frac{\delta S_{\rm eff}}{\delta\sigma(x)}
=\frac{N}{2}\left[\langle x|(-\partial^2+\sigma)^{-1}|x\rangle-\frac1{g_0}\right].
$$

For a translation-invariant saddle $\sigma=M^2$ this becomes

$$
\frac1{g_0}
=\int^\Lambda\frac{d^dp}{(2\pi)^d}\frac1{p^2+M^2}.
$$

This equation fixes the mass gap $M$ in terms of the bare coupling and cutoff. It is nonperturbative because, in two dimensions, the solution is exponentially small in the weak bare coupling.

## Dimensional transmutation in two dimensions

In $d=2$, the regulated integral is

$$
I_2(M)
=\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}
=\frac1{4\pi}\log\frac{\Lambda^2+M^2}{M^2}.
$$

For $M\ll\Lambda$,

$$
I_2(M)\simeq \frac1{2\pi}\log\frac{\Lambda}{M}.
$$

The gap equation gives

$$
\frac1{g_0}\simeq \frac1{2\pi}\log\frac{\Lambda}{M},
$$

and therefore

$$
M\simeq \Lambda\exp\left(-\frac{2\pi}{g_0}\right).
$$

The numerical coefficient in the exponent depends on the precise normalization of $g_0$, but the structure is robust:

$$
M\sim \Lambda e^{-\text{const}/g_0}.
$$

This mass scale is invisible in perturbation theory around $g_0=0$. Every Taylor coefficient in $g_0$ misses the exponential. Yet the large-$N$ saddle sees it directly.

## What happened to the Goldstone bosons?

Classically, choosing a point on $S^{N-1}$ seems to break

$$
O(N)\to O(N-1),
$$

which would suggest $N-1$ massless Goldstone modes. In two dimensions that conclusion is not correct for the quantum theory. The large-$N$ saddle restores the symmetry and produces a massive spectrum.

The diagnosis is visible in the two-point function. At leading large $N$,

$$
\langle \phi_i(p)\phi_j(-p)\rangle
=\delta_{ij}\frac1{p^2+M^2}.
$$

At large separation,

$$
\langle \phi_i(x)\phi_j(0)\rangle
\sim \delta_{ij}\,e^{-M|x|}
\times \text{power law prefactor}.
$$

There is no long-range order. The correlation length is finite:

$$
\xi=M^{-1}.
$$

This is one of the cleanest examples of a nonperturbative mechanism overriding naive classical symmetry-breaking intuition.

## CP N minus one model

The $CP^{N-1}$ model is the complex cousin of the $O(N)$ sigma model and is closer in spirit to gauge theory. It uses $N$ complex fields $z_i$ with a local phase redundancy,

$$
z_i(x)\sim e^{i\alpha(x)}z_i(x),
\qquad
z_i^*(x)z_i(x)=\frac{N}{g_0}.
$$

A convenient Euclidean action is

$$
S_E[z,A,\sigma]
=\int d^2x\left[
(D_\mu z_i)^*(D_\mu z_i)
+\sigma\left(z_i^*z_i-\frac{N}{g_0}\right)
+i\frac{\theta}{2\pi}\epsilon_{\mu\nu}\partial_\mu A_\nu
\right],
$$

where

$$
D_\mu=\partial_\mu-iA_\mu.
$$

The field $A_\mu$ is auxiliary at the classical level in this formulation. At large $N$, integrating out the $z_i$ fields induces dynamics for both $\sigma$ and $A_\mu$. The same determinant logic gives an effective action proportional to $N$:

$$
S_{\rm eff}[A,\sigma]
=N\operatorname{Tr}\log(-D^2+\sigma)
-\frac{N}{g_0}\int d^2x\,\sigma
+i\frac{\theta}{2\pi}\int F.
$$

The constant saddle again generates a mass scale. The induced gauge field produces confinement-like physics in two dimensions: charged $z_i$ quanta are not gauge-invariant asymptotic particles, while gauge-invariant composites are the physical observables.

The $CP^{N-1}$ model is valuable because it shares several qualitative features with four-dimensional Yang–Mills theory: asymptotic freedom, dimensional transmutation, theta dependence, instantons at finite $N$, and a useful large-$N$ saddle. It is not a toy in the insulting sense; it is a smaller arena where hard gauge-theory lessons can be made explicit.

## Corrections and fluctuations

At $N=\infty$, $\sigma$ is frozen at its saddle value. At finite large $N$, write

$$
\sigma(x)=M^2+\frac1{\sqrt N}s(x).
$$

Expanding the effective action gives

$$
S_{\rm eff}[\sigma]
=N s_0+\frac12\int s\,K_s\,s+O(N^{-1/2}).
$$

The $s$ propagator is order $N^0$ after the $1/\sqrt N$ normalization, but its coupling to the original fields carries powers of $1/\sqrt N$. Therefore connected corrections to many singlet observables are organized in powers of $1/N$.

In $CP^{N-1}$, the gauge field also becomes dynamical through the same expansion. The induced Maxwell-like term is generated by the one-loop determinant of the $N$ charged fields. This is a useful warning: auxiliary fields at the microscopic level can become real low-energy collective fields after integrating out many components.

## Checks and diagnostics

**Check the $N$ scaling.** The constraint radius is $N/g_0$, the determinant is multiplied by $N$, and the effective action is $N$ times an $N$-independent functional. Without that scaling, the saddle would not be controlled.

**Check the mass dimensions.** In $d=2$, $g_0$ is dimensionless, so the generated mass must involve the cutoff or renormalization scale multiplied by an exponential. In $d>2$, the coupling has dimension and the gap equation must be interpreted differently.

**Check symmetry restoration.** The leading propagator is diagonal in $O(N)$ indices, so the large-$N$ saddle does not select a permanent direction in target space in two dimensions.

**Check gauge invariance in $CP^{N-1}$.** The fields $z_i$ are not gauge-invariant observables. Physical correlation functions must be built from gauge-invariant composites or dressed objects.

## Common pitfalls

**Treating the Lagrange multiplier as an arbitrary mass parameter.** The mass $M$ is not inserted by hand. It is determined self-consistently by the gap equation.

**Forgetting the UV regulator.** The gap equation contains a divergent integral. The physical result is obtained only after relating the bare coupling to a renormalized scale.

**Confusing the finite-N sigma model with its large-N saddle.** The saddle is controlled as $N\to\infty$. Some effects, especially instanton-like effects and theta dependence, can be subtle or exponentially small in $N$.

**Calling the $CP^{N-1}$ gauge field fundamental without qualification.** In the gauged formulation, $A_\mu$ starts as an auxiliary field implementing a redundancy. At large $N$, it acquires induced dynamics.

**Applying spontaneous-symmetry-breaking intuition too quickly.** A classical target-space vacuum does not automatically imply a quantum broken phase, especially in two dimensions.

## Relations to other pages

[Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) introduces the auxiliary-field determinant in the unconstrained quartic model. This page shows how the same determinant logic enforces a nonlinear constraint.

[Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) explains how exponential correlation decay diagnoses a gap. The large-$N$ $O(N)$ model gives a controlled example where the gap is generated dynamically.

[Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/) and [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) provide background for the theta dependence and instanton sectors that become especially interesting in $CP^{N-1}$.

Continue next to [CP N-Minus-One Model](/nonperturbative-qft/large-n-methods/cp-n-minus-one-model/) for the dedicated complex-projective model page, and then to [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) for the general steepest-descent anatomy. [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) then replaces the Lagrange-multiplier saddle by an eigenvalue density.

## Research status

**Established.** The large-$N$ solution of $O(N)$ and $CP^{N-1}$ sigma models is a standard controlled method. It gives a clean path to mass generation, renormalization, induced collective fields, and $1/N$ corrections.

**Established with caveats.** These models are excellent analogues of harder gauge theories, but analogies should be labeled as analogies. The two-dimensional $CP^{N-1}$ model is not four-dimensional QCD.

**Active.** Theta dependence, resurgence, large-order behavior, compactification, boundary conditions, finite-volume effects, and the relation between instantons and large $N$ remain lively topics. The leading saddle is old; the global nonperturbative story still has teeth.

## Exercises

### Exercise 1: Derive the gap equation

Starting from

$$
S_{\rm eff}[\sigma]
=N\left[\frac12\operatorname{Tr}\log(-\partial^2+\sigma)
-\frac{1}{2g_0}\int d^dx\,\sigma\right],
$$

assume $\sigma=M^2$ is constant and derive

$$
\frac1{g_0}
=\int^\Lambda\frac{d^dp}{(2\pi)^d}\frac1{p^2+M^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\delta\operatorname{Tr}\log K=\operatorname{Tr}(K^{-1}\delta K).
$$

Here $K=-\partial^2+\sigma$, so $\delta K=\delta\sigma$. The saddle equation is

$$
0=\frac{\delta S_{\rm eff}}{\delta\sigma(x)}
=\frac{N}{2}\left[\langle x|(-\partial^2+\sigma)^{-1}|x\rangle-\frac1{g_0}\right].
$$

For $\sigma=M^2$, translation invariance gives

$$
\langle x|(-\partial^2+M^2)^{-1}|x\rangle
=\int^\Lambda\frac{d^dp}{(2\pi)^d}\frac1{p^2+M^2}.
$$

</details>

### Exercise 2: Evaluate the two-dimensional integral

Show that

$$
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}
=\frac1{4\pi}\log\frac{\Lambda^2+M^2}{M^2}
$$

for a circular cutoff $|p|\le \Lambda$.

<details>
<summary><strong>Solution</strong></summary>

Use polar coordinates:

$$
\int^\Lambda\frac{d^2p}{(2\pi)^2}\frac1{p^2+M^2}
=\frac{1}{2\pi}\int_0^\Lambda dp\,\frac{p}{p^2+M^2}.
$$

The integral is

$$
\frac{1}{2\pi}\cdot\frac12\log(p^2+M^2)\Big|_0^\Lambda
=\frac1{4\pi}\log\frac{\Lambda^2+M^2}{M^2}.
$$

</details>

### Exercise 3: Why the CP model has a gauge redundancy

Let $z_i(x)$ be $N$ complex fields with $z_i^*z_i=N/g_0$. Explain why the identification

$$
z_i(x)\sim e^{i\alpha(x)}z_i(x)
$$

requires a gauge field in the kinetic term.

<details>
<summary><strong>Solution</strong></summary>

The ordinary derivative transforms as

$$
\partial_\mu z_i\to e^{i\alpha}\left(\partial_\mu z_i+i(\partial_\mu\alpha)z_i\right),
$$

so $|\partial_\mu z_i|^2$ is not invariant under a local phase rotation. Introducing

$$
D_\mu=\partial_\mu-iA_\mu,
\qquad
A_\mu\to A_\mu+\partial_\mu\alpha,
$$

makes $D_\mu z_i\to e^{i\alpha}D_\mu z_i$, so $|D_\mu z_i|^2$ is gauge invariant.

</details>

## References

### Standard first pass

- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the discussion of the $O(3)$ model, $CP(N-1)$ models, and the large-$N$ solutions of $O(N)$ and $CP(N-1)$.
- M. Mariño, *Instantons and Large N*, especially the chapters on sigma models at large $N$ and instantons at large $N$.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the large-$N$ chapter and the sigma-model chapters.

### Deeper references

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for systematic $1/N$ methods in statistical and quantum field theory.
- A. M. Polyakov, “Interaction of Goldstone particles in two dimensions,” for the classic asymptotic-freedom and mass-generation perspective.
- E. Witten, “Instantons, the Quark Model, and the 1/N Expansion,” for large-$N$ thinking about $CP^{N-1}$ and related nonperturbative physics.

## Version history

- **2026-06-27:** Added handoff links to the dedicated CP N-minus-one and saddle-points-at-large-N pages.
- **2026-06-27:** Initial polished page deriving the large-$N$ sigma-model gap equation, mass generation, and the $CP^{N-1}$ bridge.
