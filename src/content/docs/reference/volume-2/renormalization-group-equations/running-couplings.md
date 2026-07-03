---
title: "Running Couplings"
description: "Explains running couplings as solutions of beta-function equations, including one-loop running, scale choice, large logarithms, thresholds, EFT running, and RG-invariant scales."
sidebar:
  label: "Running Couplings"
  order: 4
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations and Asymptotic Freedom; Wilson and Kogut 1974; Srednicki §§27–29; Schwartz ch. 23; Weinberg Vol. II ch. 18; Burgess 2020, chs. 2–3."
topics:
  - running couplings
  - beta functions
  - RG flow
  - large logarithms
  - scale choice
  - thresholds
  - EFT running
canonicalTopics:
  - running-coupling
  - rg-flow
  - large-logarithms
  - threshold-matching
  - dimensional-transmutation
researchStatus:
  established:
    - "Running couplings are the standard solutions of beta-function equations and are used to resum logarithmic scale dependence in renormalized perturbation theory and EFT."
  active:
    - "Precision running across thresholds, high-loop evolution, nonperturbative running, scheme conversions, and RG evolution in large EFT operator bases remain active research and phenomenology topics."
---

## Summary

A **running coupling** is a solution of a renormalization group equation. If a renormalized coupling $g(\mu)$ has beta function

$$
\beta(g)=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare}},
$$

then its running is determined by

$$
\frac{dg}{d\log\mu}=\beta(g).
$$

The simplest one-loop marginal example is

$$
\beta(g)=b g^3.
$$

Its solution is

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}-2b\log\frac{\mu}{\mu_0}.
$$

If $b>0$, the coupling grows toward the ultraviolet in this approximation. If $b<0$, the coupling weakens toward the ultraviolet and the theory is asymptotically free along that direction.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![One-loop running coupling trajectories showing an asymptotically free coupling that decreases toward the ultraviolet and an infrared-free coupling that grows toward a Landau pole](/figures/renormalization-rg-eft/running-coupling-trajectories.svg)

<figcaption>

Running couplings are trajectories obtained by solving beta-function equations. The renormalization scale $\mu$ is a bookkeeping scale; one often chooses $\mu$ near a physical scale $Q$ to keep logarithms small, but the RG trajectory is defined by holding the bare theory fixed.

</figcaption>
</figure>

Running couplings are not a claim that nature changes because we renamed a parameter. They express the fact that different subtraction scales use different renormalized coordinates to describe the same underlying physics.

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), and [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/). It is also useful to have read [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/) and [MSbar Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/msbar-scheme/).

This page focuses on the conceptual and practical use of running couplings. Detailed examples in QED, QCD, EFT matching, and critical phenomena are developed later.

## Core idea

A perturbative calculation often produces logarithms such as

$$
\log\frac{Q^2}{\mu^2},
\qquad
\log\frac{M^2}{\mu^2},
\qquad
\log(\mu^2 x^2),
$$

where $Q$ is a physical momentum, $M$ is a mass threshold, and $\mu$ is the arbitrary renormalization scale. If the ratio of scales is large, fixed-order perturbation theory can become badly organized even when the coupling is small.

The RG solves this organizational problem. The explicit logarithms of $\mu$ in amplitudes are tied to implicit $\mu$ dependence in renormalized couplings, masses, fields, and Wilson coefficients. Running couplings move the logarithmic dependence into the parameters used at the scale where the calculation is being performed.

The practical rule is

$$
\text{measure or match at one scale, run to another scale, compute with }\mu\text{ chosen near the process scale.}
$$

This rule is powerful, but it is easy to say it badly. The process scale $Q$ is physical. The subtraction scale $\mu$ is a convention. Choosing $\mu\sim Q$ is a good convention, not a law of nature.

## Setup and conventions

Let

$$
t=\log\mu.
$$

For one coupling,

$$
\frac{dg}{dt}=\beta(g).
$$

For many couplings,

$$
\frac{dg^i}{dt}=\beta^i(g^1,g^2,\ldots).
$$

A running coupling is the solution with an initial condition:

$$
g(\mu_0)=g_0^{\text{ren}}.
$$

Here $g_0^{\text{ren}}$ means the renormalized coupling at the reference scale $\mu_0$, not a bare coupling. To avoid notation collision, this page avoids using $g_0$ for both a bare coupling and an initial value.

For a single coupling, the implicit solution is

$$
\int_{g(\mu_0)}^{g(\mu)}\frac{dg}{\beta(g)}
=\log\frac{\mu}{\mu_0}.
$$

For several couplings, the RG equations form a coupled system of ordinary differential equations. In perturbation theory one usually solves them order by order, numerically, or by finding useful approximate invariants.

## Linearized running near a fixed point

Let $g_*$ be a fixed point:

$$
\beta(g_*)=0.
$$

Close to the fixed point,

$$
g(\mu)=g_*+\delta g(\mu),
$$

and

$$
\frac{d\delta g}{d\log\mu}
=\beta'(g_*)\delta g+O(\delta g^2).
$$

The linearized solution is

$$
\delta g(\mu)
=\delta g(\mu_0)
\left(\frac{\mu}{\mu_0}\right)^{\beta'(g_*)}.
$$

Thus, with the convention $t=\log\mu$, the fixed point is attractive toward the ultraviolet if $\beta'(g_*)<0$ and attractive toward the infrared if $\beta'(g_*)>0$.

For multiple couplings,

$$
\frac{d\delta g^i}{d\log\mu}=B^i{}_j\delta g^j,
\qquad
B^i{}_j=\left.\frac{\partial\beta^i}{\partial g^j}\right|_{g_*}.
$$

The eigenvectors of $B$ are the linearized scaling directions. The signs of the eigenvalues must always be interpreted together with the direction of RG time.

## One-loop marginal running

The most common one-coupling example is

$$
\beta(g)=b g^3+O(g^5).
$$

Keeping only the one-loop term gives

$$
\frac{dg}{d\log\mu}=b g^3.
$$

Separating variables,

$$
\int_{g(\mu_0)}^{g(\mu)}\frac{dg}{g^3}
=b\log\frac{\mu}{\mu_0},
$$

so

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}-2b\log\frac{\mu}{\mu_0}.
$$

This single formula contains two famous behaviors.

If $b>0$, then $g(\mu)$ grows as $\mu$ increases. The one-loop solution has a formal ultraviolet singularity at

$$
\mu_L=\mu_0\exp\left[\frac{1}{2b g^2(\mu_0)}\right].
$$

This is Landau-pole behavior in the one-loop approximation.

If $b<0$, write $b=-b_0$ with $b_0>0$. Then

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}+2b_0\log\frac{\mu}{\mu_0},
$$

so $g(\mu)$ decreases toward the ultraviolet. This is asymptotic freedom.

## Running in terms of alpha

Gauge couplings are often written as

$$
\alpha=\frac{g^2}{4\pi}.
$$

If

$$
\mu\frac{dg}{d\mu}=b g^3,
$$

then

$$
\mu\frac{d\alpha}{d\mu}=8\pi b\,\alpha^2.
$$

For QED with one Dirac fermion,

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5),
$$

so

$$
\mu\frac{d\alpha}{d\mu}
=\frac{2}{3\pi}\alpha^2+O(\alpha^3).
$$

For a non-Abelian gauge theory with

$$
\beta_g=-\frac{\beta_0}{16\pi^2}g^3+O(g^5),
$$

where

$$
\beta_0=\frac{11}{3}C_A-\frac{4}{3}T_R N_f,
$$

one gets

$$
\mu\frac{d\alpha}{d\mu}
=-\frac{\beta_0}{2\pi}\alpha^2+O(\alpha^3).
$$

The one-loop solution is

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}
{1+\frac{\beta_0\alpha(\mu_0)}{2\pi}\log\frac{\mu}{\mu_0}}.
$$

When $\beta_0>0$, the coupling decreases at large $\mu$.

:::caution[Translate variables before comparing coefficients]
The beta function for $g$, $g^2$, $\alpha=g^2/(4\pi)$, and $a=g^2/(16\pi^2)$ has different numerical coefficients. Many apparent disagreements between books are only variable changes.
:::

## RG-invariant scales

For an asymptotically free one-loop coupling,

$$
\frac{dg}{d\log\mu}=-b_0g^3,
\qquad b_0>0,
$$

the solution can be written

$$
\frac{1}{g^2(\mu)}=2b_0\log\frac{\mu}{\Lambda}.
$$

The constant $\Lambda$ is defined by

$$
\Lambda
=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

At one loop, $\Lambda$ is independent of $\mu$. A dimensionless coupling has been exchanged for a dimensionful integration constant. This is the first appearance of **dimensional transmutation**.

The formula should not be overinterpreted. In QCD, higher-loop terms, thresholds, scheme conventions, and nonperturbative physics refine the definition of $\Lambda$. The main lesson survives: logarithmic running can generate a scale even when the classical Lagrangian contains only dimensionless couplings.

## Running and large logarithms

Suppose a dimensionless observable has a perturbative expansion

$$
F(Q,\mu,g(\mu))
=A_0+A_1g^2(\mu)
+B_1g^2(\mu)\log\frac{Q^2}{\mu^2}+O(g^4).
$$

If $\mu$ is very different from $Q$, the logarithm can be large. Fixed-order perturbation theory then becomes a poor expansion in practice, because the real expansion parameter is not just $g^2$ but also $g^2\log(Q^2/\mu^2)$.

Choosing

$$
\mu\sim Q
$$

makes the explicit logarithm small. The dependence on scales far from $Q$ is then hidden in the running coupling $g(\mu)$, which was evolved from a reference scale.

The same idea works when several scales are present, but not with one magical choice of $\mu$. If a problem contains $M\gg Q$, then a single fixed-order calculation may contain

$$
\log\frac{M^2}{Q^2}.
$$

Effective field theory handles this by matching near $M$, running down, and computing near $Q$.

## Thresholds and matching

Beta functions depend on the degrees of freedom present in the theory. When the scale crosses a particle mass threshold, the appropriate low-energy description changes.

The standard EFT workflow is

$$
\text{full theory above }M
\quad\longrightarrow\quad
\text{match at }\mu\sim M
\quad\longrightarrow\quad
\text{run in EFT}
\quad\longrightarrow\quad
\text{compute at }\mu\sim Q.
$$

At matching, one chooses Wilson coefficients so that the full theory and EFT agree for low-energy observables:

$$
\mathcal A_{\text{full}}(Q\ll M)
=
\mathcal A_{\text{EFT}}(Q;C_i(M),M)
+O\left(\frac{Q^{n+1}}{M^{n+1}}\right).
$$

Then the EFT coefficients run:

$$
\mu\frac{dC_i}{d\mu}=\gamma_i{}^j C_j+\cdots,
$$

with signs and transposes determined by the operator-basis convention. The point is to resum logarithms of $M/Q$ by evolving the coefficient from $M$ to $Q$ rather than leaving a large logarithm in a fixed-order expression.

:::tip[Run only with the right theory]
Do not run a coupling through a threshold as if nothing happened. Above and below the threshold, the field content and beta functions can differ. Matching is the seam between the two descriptions.
:::

## Running masses

Masses can run just like dimensionless couplings. A common convention for a multiplicatively renormalized fermion mass is

$$
\mu\frac{dm}{d\mu}=-\gamma_m(g)m.
$$

The solution is

$$
m(\mu)=m(\mu_0)
\exp\left[-\int_{\log\mu_0}^{\log\mu}dt\,\gamma_m(g(t))\right].
$$

For a scalar squared mass, one may write

$$
\mu\frac{dm^2}{d\mu}=\beta_{m^2}(g,m^2).
$$

In many perturbative examples,

$$
\beta_{m^2}=\gamma_{m^2}(g)m^2+\text{additive terms allowed by the scheme and theory}.
$$

Mass running is more delicate than coupling running because masses are relevant parameters. They are not merely logarithmic deformations of a fixed point; they can drive the theory away from criticality. This is why mass terms are central in discussions of naturalness, critical surfaces, and EFT power counting.

## Multiple couplings

In a theory with several couplings, running is a trajectory in coupling space:

$$
\frac{d}{d\log\mu}
\begin{pmatrix}
 g^1\\
 g^2\\
 \vdots
\end{pmatrix}
=
\begin{pmatrix}
 \beta^1(g)\\
 \beta^2(g)\\
 \vdots
\end{pmatrix}.
$$

The couplings generally cannot be run independently. A Yukawa coupling can feed into a scalar quartic beta function; a gauge coupling can feed into a Yukawa beta function; an EFT coefficient can mix into another coefficient. The RG trajectory is obtained by solving the coupled system.

In matrix form, Wilson-coefficient running often takes the form

$$
\mu\frac{dC}{d\mu}=\gamma^T(g(\mu))C.
$$

The solution is

$$
C(\mu)=U(\mu,\mu_0)C(\mu_0),
$$

where

$$
U(\mu,\mu_0)
=P\exp\left[
\int_{\log\mu_0}^{\log\mu}dt\,\gamma^T(g(t))
\right].
$$

Here $P$ denotes ordering along the RG trajectory. In simple one-operator cases, this reduces to an ordinary exponential.

## Running versus Wilsonian flow

Running couplings in renormalized perturbation theory and Wilsonian couplings in a cutoff action are closely related but not identical objects.

A renormalized coupling $g(\mu)$ changes with $\mu$ while the bare regulated theory is held fixed. The scale $\mu$ is a subtraction convention.

A Wilsonian coupling $g_i(\Lambda)$ changes when modes above or below a cutoff are integrated out. The scale $\Lambda$ labels which degrees of freedom remain explicit.

Both descriptions lead to RG equations. Both describe scale dependence. But their operational meanings differ:

| Object | What changes | What is being held fixed |
|---|---|---|
| Renormalized running $g(\mu)$ | subtraction scale and renormalized coordinates | bare theory and regulator definition |
| Wilsonian flow $g_i(\Lambda)$ | effective action and explicit degrees of freedom | long-distance physics |

In weakly coupled regimes, the two languages often give the same beta-function coefficients for universal quantities. Conceptually, it is still worth keeping them distinct.

## What running means physically

A running coupling is not itself an observable. It becomes physically useful after one specifies a measurement convention.

For example, the electromagnetic charge can be defined through a scattering process or a static potential. Vacuum polarization then makes the effective charge depend on the momentum transfer used to probe it. In a convenient scheme, this physical scale dependence is captured by a running coupling.

In QCD, the running coupling is small at high momentum transfer, making perturbative calculations possible. At low momentum, the perturbative running coupling grows, warning us that confinement and other nonperturbative phenomena are taking over.

In EFT, Wilson coefficients run even when the low-energy process is far below the heavy masses that generated them. The running encodes the influence of quantum fluctuations between the matching scale and the measurement scale.

Thus the safe statement is:

$$
\text{running couplings are scheme-dependent coordinates that efficiently encode physical scale dependence.}
$$

## Common pitfalls

**Saying that $\mu$ is the energy.** The physical energy scale is set by external momenta, masses, temperature, density, or geometry. The scale $\mu$ is a renormalization convention. Choosing $\mu\sim Q$ is a strategy.

**Running through thresholds without matching.** The beta function changes when degrees of freedom are removed or added. Matching near the threshold is part of the calculation.

**Treating a Landau pole as automatically fundamental.** A perturbative singularity can indicate a real obstruction, a finite cutoff, a missing UV completion, a threshold, or breakdown of the approximation.

**Comparing couplings in different schemes as if they were the same variable.** Running couplings are coordinates. Scheme changes are coordinate transformations.

**Forgetting that multiple couplings run together.** Coupled beta functions can qualitatively change the flow. Solving one equation while freezing the others is an approximation that must be justified.

**Using fixed-order perturbation theory with large logarithms.** If $g^2\log(M/Q)$ is not small, running and matching are not aesthetic refinements. They are necessary for a controlled expansion.

**Confusing renormalized running with Wilsonian coarse graining.** Both are RG ideas, but the first changes subtraction coordinates while the second changes the effective action.

## Relations to other pages

[Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) defines the differential equations that running couplings solve. [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) explains the running of fields, operators, masses, and Wilson coefficients. [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/) shows why running is required by independence of the arbitrary scale $\mu$.

[Running Masses](/renormalization-rg-eft/renormalization-group-equations/running-masses/) develops mass parameters more carefully. [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/) explains systematic logarithm resummation. [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/) explains how running changes under finite redefinitions.

[Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) develops the RG-invariant scale $\Lambda$. [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/) and [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/) study the two most familiar one-loop endpoints. [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/) gives the full EFT workflow.

## Research status

Running couplings are standard tools in perturbative QFT, critical phenomena, and EFT. Their one-loop and multi-loop use in weakly coupled theories is well established.

Active work includes high-precision running across many thresholds, scheme conversion in multi-loop QCD and electroweak calculations, nonperturbative determinations of running couplings on the lattice, RG evolution in large EFT operator bases, functional RG approximations, conformal-window studies, and running in theories without simple weakly coupled Lagrangians.

## Exercises

### Exercise 1: QED-like one-loop running

Suppose

$$
\mu\frac{d\alpha}{d\mu}=B\alpha^2,
\qquad B>0.
$$

Solve for $\alpha(\mu)$ in terms of $\alpha(\mu_0)$ and find the formal Landau scale.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\int_{\alpha(\mu_0)}^{\alpha(\mu)}\frac{d\alpha}{\alpha^2}
=B\log\frac{\mu}{\mu_0}.
$$

This gives

$$
-\frac{1}{\alpha(\mu)}+\frac{1}{\alpha(\mu_0)}
=B\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}
{1-B\alpha(\mu_0)\log(\mu/\mu_0)}.
$$

The denominator vanishes at

$$
\mu_L=\mu_0\exp\left[\frac{1}{B\alpha(\mu_0)}\right].
$$

This is the formal one-loop Landau scale.

</details>

### Exercise 2: RG-invariant scale for asymptotic freedom

Let

$$
\frac{dg}{d\log\mu}=-b_0g^3,
\qquad b_0>0.
$$

Show that

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]
$$

is independent of $\mu$ at one loop.

<details><summary><strong>Solution</strong></summary>

Take the logarithm:

$$
\log\Lambda=\log\mu-\frac{1}{2b_0g^2(\mu)}.
$$

Differentiate with respect to $t=\log\mu$:

$$
\frac{d\log\Lambda}{dt}
=1-\frac{d}{dt}\left(\frac{1}{2b_0g^2}\right).
$$

Since

$$
\frac{d}{dt}\left(\frac{1}{g^2}\right)
=-\frac{2}{g^3}\frac{dg}{dt}
=-\frac{2}{g^3}(-b_0g^3)=2b_0,
$$

we get

$$
\frac{d}{dt}\left(\frac{1}{2b_0g^2}\right)=1.
$$

Therefore

$$
\frac{d\log\Lambda}{dt}=0.
$$

</details>

### Exercise 3: Choosing the scale

A fixed-order expression contains

$$
F(Q,\mu)=1+A g^2(\mu)+B g^2(\mu)\log\frac{Q^2}{\mu^2}+O(g^4).
$$

What choice of $\mu$ removes the explicit logarithm at this order, and why does this not mean $\mu$ is a physical energy?

<details><summary><strong>Solution</strong></summary>

Choosing

$$
\mu=Q
$$

removes the explicit logarithm because

$$
\log\frac{Q^2}{\mu^2}=0.
$$

This is a convention that improves the perturbative expansion by avoiding large logarithms. The physical scale $Q$ is set by external kinematics. The scale $\mu$ is the arbitrary subtraction scale at which the renormalized coupling is defined. We choose $\mu$ near $Q$ for convenience, not because the theory requires them to be identical.

</details>

### Exercise 4: Simple threshold matching

Suppose a full theory above a heavy mass $M$ matches onto an EFT coefficient at $\mu=M$:

$$
C(M)=C_0.
$$

Below $M$, assume

$$
\mu\frac{dC}{d\mu}=\gamma C,
$$

with constant $\gamma$. Find $C(Q)$ for $Q<M$.

<details><summary><strong>Solution</strong></summary>

The RG equation is

$$
\frac{dC}{d\log\mu}=\gamma C.
$$

Integrating from $M$ to $Q$ gives

$$
\log\frac{C(Q)}{C(M)}
=\gamma\log\frac{Q}{M}.
$$

Using $C(M)=C_0$,

$$
C(Q)=C_0\left(\frac{Q}{M}\right)^\gamma.
$$

If $\gamma$ itself depends on running couplings, the constant-power formula is replaced by an exponential of the integral of $\gamma(g(\mu))$.

</details>

## References

- Sidney Coleman, "Dilatations" and "Asymptotic Freedom" in *Aspects of Symmetry*, for classic explanations of running, scaling, and asymptotic freedom.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200, for RG flow, fixed points, scaling, and the connection between field theory and critical phenomena.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on the renormalization group, running couplings, and nonrenormalizable theories.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for sliding scales, varieties of asymptotic behavior, multiple couplings, mass effects, and minimal subtraction.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, power counting, matching, and running.

## Version history

- 2026-06-17: First polished draft. Explained running couplings as beta-function solutions, derived one-loop running, clarified scale choice and large logarithms, introduced thresholds, Wilson-coefficient running, running masses, and RG-invariant scales.
