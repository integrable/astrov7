---
title: "Asymptotic Freedom"
description: "Explains why some non-Abelian gauge theories become weakly coupled at short distances, how the one-loop running works, and what asymptotic freedom does and does not imply."
sidebar:
  label: "Asymptotic Freedom"
  order: 10
level: Graduate
status: "Polished draft"
source: "Gross and Wilczek 1973; Politzer 1973; Coleman, Asymptotic Freedom; Polyakov, Gauge Fields and Strings ch. 2; Srednicki gauge-theory beta-function sections; Schwartz chs. 23 and 26; Weinberg Vol. II ch. 18; Wilson and Kogut 1974."
topics:
  - asymptotic freedom
  - non-Abelian gauge theory
  - beta functions
  - QCD
  - dimensional transmutation
  - ultraviolet fixed points
canonicalTopics:
  - asymptotic-freedom
  - non-abelian-beta-function
  - qcd-running-coupling
  - gaussian-uv-fixed-point
  - dimensional-transmutation
researchStatus:
  established:
    - "The one-loop negative beta function of non-Abelian gauge theories with sufficiently little matter is a standard perturbative result and underlies the short-distance success of QCD."
  active:
    - "The infrared fate of asymptotically free theories is theory dependent: confinement, chiral symmetry breaking, conformal windows, mass gaps, and dual descriptions require nonperturbative methods."
---

## Summary

A theory is **asymptotically free** if its interactions become weak at short distances, or equivalently at large renormalization scale $\mu$.

For a single dimensionless coupling $g$, the canonical weak-coupling form is

$$
\beta_g\equiv\mu\frac{dg}{d\mu}
=-b_0g^3+O(g^5),
\qquad b_0>0.
$$

The one-loop solution is

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}.
$$

Thus

$$
g(\mu)\longrightarrow 0
\qquad \text{as}\qquad
\mu\longrightarrow\infty.
$$

The point $g=0$ is a UV fixed point. The theory is not free at all scales; it is free in the ultraviolet limit. At lower scales the same running coupling grows, and perturbation theory eventually breaks down.

For an $SU(N)$ gauge theory with $n_f$ Dirac fermions in the fundamental representation,

$$
\beta_g
=
-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}N-\frac{2}{3}n_f\right)
+O(g^5).
$$

The theory is asymptotically free at one loop if

$$
n_f<\frac{11}{2}N.
$$

For QCD with $N=3$, this gives asymptotic freedom for $n_f\le 16$ Dirac flavors.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Asymptotic freedom sign balance showing gauge-field anti-screening competing with matter screening to determine the one-loop beta-function coefficient](/figures/renormalization-rg-eft/asymptotic-freedom-balance.svg)

<figcaption>

At one loop, non-Abelian gauge fields contribute an anti-screening term proportional to $C_A$, while matter fields screen color charge. If the gauge contribution wins, $b_0>0$ in $\beta_g=-b_0g^3+\cdots$, and the theory is asymptotically free.

</figcaption>
</figure>

The physical importance is enormous: asymptotic freedom explains why quarks and gluons behave almost like weakly interacting partons in sufficiently high-energy scattering, while the same theory can become strongly coupled at hadronic scales.

## Prerequisites

You should know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/), and [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/).

For the gauge-theory examples, it helps to know the basic distinction between Abelian and non-Abelian gauge fields. Full derivations of gauge-theory beta functions belong in [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/) and the Gauge Theories and Standard Model volume.

## Core idea

The simplest intuition is this:

$$
\text{asymptotic freedom} = \text{interactions fade at short distance.}
$$

In ordinary quantum mechanics one often expects short distances to be harder because wavefunctions oscillate faster and high momentum probes microscopic structure. In asymptotically free QFTs, the high-momentum limit becomes simpler in a different sense: the effective coupling becomes small.

The RG reason is the sign of the beta function near $g=0$. If

$$
\beta_g=-b_0g^3+O(g^5),
\qquad b_0>0,
$$

then increasing $\mu$ decreases $g$. The Gaussian theory $g=0$ is approached in the ultraviolet.

This does not mean the full theory is just the free theory. The RG trajectory carries an integration constant, usually written $\Lambda$, and physics at scales comparable to $\Lambda$ can be strongly coupled. Asymptotic freedom is a statement about the ultraviolet endpoint of the flow, not a complete solution of the infrared theory.

:::note[The ultraviolet is weak; the infrared is not promised]
Asymptotic freedom controls the short-distance limit. It does not by itself prove confinement, a mass gap, chiral symmetry breaking, or the spectrum of bound states. Those are nonperturbative infrared questions.
:::

## Setup and conventions

This volume uses

$$
\beta_g(g)=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

Let

$$
t=\log\mu.
$$

At weak coupling, assume

$$
\frac{dg}{dt}=-b_0g^3,
\qquad b_0>0.
$$

Then

$$
\frac{d}{dt}\left(\frac{1}{g^2}\right)=2b_0.
$$

Integrating gives

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}+2b_0\log\frac{\mu}{\mu_0}.
$$

Define $\Lambda$ by

$$
\frac{1}{g^2(\mu)}=2b_0\log\frac{\mu}{\Lambda}.
$$

Then

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}.
$$

The formula is valid only when $g^2(\mu)\ll 1$, which requires $\mu\gg\Lambda$ in the one-loop approximation.

## The Gaussian UV fixed point

A fixed point is a value of the coupling where the beta function vanishes. Since

$$
\beta_g=-b_0g^3+O(g^5),
$$

the origin $g=0$ is a fixed point. It is UV-attractive because for $b_0>0$ the coupling flows toward zero as $\mu$ is increased.

Linearizing ordinary RG flow around a Gaussian fixed point can be slightly subtle because the leading term is cubic, not linear. The coupling is marginal at engineering level, and the quantum beta function makes it **marginally irrelevant toward the UV**.

Equivalently, toward the IR the same coupling is marginally relevant: it grows logarithmically as $\mu$ is lowered.

This logarithmic behavior is slower than any power law. That is why high-energy QCD corrections often involve logarithms rather than simple powers:

$$
g^2(Q)\sim \frac{1}{\log(Q/\Lambda)}.
$$

## Why non-Abelian gauge theories can do this

In Abelian gauge theory with charged matter, vacuum polarization screens electric charge. The effective charge grows at shorter distances, giving a positive beta function in QED.

Non-Abelian gauge theory has an extra ingredient: the gauge bosons themselves carry gauge charge. Their self-interactions contribute to the running. In four-dimensional Yang–Mills theory, the gauge and ghost contributions dominate over matter when the matter content is small enough. The result is **anti-screening**: the effective color charge becomes weaker at short distances.

The standard one-loop result for a gauge theory with gauge group $G$ and $n_f$ Dirac fermions in representation $R$ is

$$
\beta_g
=
-\frac{g^3}{16\pi^2}
\left[\frac{11}{3}C_A-\frac{4}{3}T(R)n_f\right]
+O(g^5),
$$

where

$$
f^{acd}f^{bcd}=C_A\delta^{ab},
\qquad
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab}.
$$

For $SU(N)$,

$$
C_A=N,
\qquad
T(\text{fund})=\frac12.
$$

Therefore for $n_f$ fundamental Dirac fermions,

$$
\beta_g
=
-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}N-\frac{2}{3}n_f\right)
+O(g^5).
$$

The gauge-field term $11N/3$ drives asymptotic freedom. The matter term $2n_f/3$ opposes it.

:::tip[The sign is the miracle]
The existence of a negative gauge beta function is not a generic property of interactions. It is a special dynamical feature of non-Abelian gauge theories. This is why asymptotic freedom was historically decisive for QCD.
:::

## QCD running at one loop

For QCD with gauge group $SU(3)$ and $n_f$ active quark flavors,

$$
\beta_g
=
-\frac{g^3}{16\pi^2}
\left(11-\frac{2}{3}n_f\right)+O(g^5).
$$

Define

$$
\alpha_s=\frac{g^2}{4\pi}.
$$

Then at one loop,

$$
\alpha_s(\mu)
=
\frac{4\pi}{\left(11-\frac{2}{3}n_f\right)\log(\mu^2/\Lambda^2)}.
$$

This formula should be used with care:

- $n_f$ changes when $\mu$ crosses quark mass thresholds;
- $\Lambda$ depends on the renormalization scheme and on the number of active flavors;
- the one-loop formula is reliable only when $\mu\gg\Lambda$;
- near hadronic scales, perturbation theory is not the right tool.

Nevertheless, the qualitative message is robust. At large momentum transfer, $\alpha_s$ becomes small. This is the basis for perturbative QCD in high-energy scattering.

## Dimensional transmutation

A massless asymptotically free gauge theory has no mass scale in the classical Lagrangian. Quantum mechanically, the RG trajectory introduces a scale

$$
\Lambda
=
\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]
$$

at leading order.

Thus a dimensionless coupling at one reference scale is traded for a dimensionful scale. This is dimensional transmutation.

For QCD-like theories, physical quantities such as hadron masses, string tensions, condensates, and finite-temperature transition scales are expected to be proportional to powers of $\Lambda$, up to dimensionless numbers. Those numbers are not usually computable by weak-coupling perturbation theory.

The hierarchy is exponential:

$$
\Lambda\ll\mu
\quad\text{when}\quad
 g^2(\mu)\ll 1.
$$

This is one of the most important ways a small coupling can generate a much lower physical scale without inserting a small mass parameter by hand.

## What asymptotic freedom explains

Asymptotic freedom explains why short-distance QCD can be studied with quarks and gluons as weakly coupled degrees of freedom. It supports:

- perturbative calculations at large momentum transfer;
- RG-improved treatment of large logarithms;
- the parton model at high energies;
- operator product expansions in deep Euclidean regimes;
- scaling violations in high-energy processes;
- the emergence of a strong scale through dimensional transmutation.

The phenomenon also explains why a local non-Abelian gauge theory can be both weakly coupled in the UV and strongly coupled in the IR. That combination is rare and precious.

## What asymptotic freedom does not prove

Asymptotic freedom does not prove confinement. A theory can be asymptotically free in the ultraviolet and have different possible infrared behaviors depending on matter content and global structure. Possibilities include confinement, chiral symmetry breaking, Coulomb-like phases, conformal windows, mass gaps, or more exotic dynamics.

Asymptotic freedom also does not mean all high-energy observables are easy. Infrared and collinear effects can still complicate scattering. Factorization, jets, parton distributions, and infrared-safe observables are required to connect short-distance calculations to measured hadrons.

Finally, asymptotic freedom is not the same as asymptotic safety. In asymptotic freedom, the UV fixed point is the Gaussian point $g=0$. In asymptotic safety, the UV fixed point may occur at nonzero coupling.

## Relation to Landau poles

Landau poles and asymptotic freedom are opposites in the simplest one-loop sense.

If

$$
\beta(g)=+b g^3,
\qquad b>0,
$$

then the coupling grows toward the UV and has a formal UV Landau pole.

If

$$
\beta(g)=-b_0g^3,
\qquad b_0>0,
$$

then the coupling decreases toward the UV and the one-loop formula has a formal infrared strong-coupling scale.

The first behavior suggests a possible obstruction to a standalone continuum UV completion. The second behavior gives a controlled UV limit but leaves a difficult infrared problem.

This is why asymptotic freedom changed the status of non-Abelian gauge theories: they could be fundamental short-distance theories while still producing strong long-distance phenomena.

## Scheme dependence and universal data

For a single gauge coupling,

$$
\beta_g=-b_0g^3-b_1g^5+O(g^7).
$$

The first coefficient $b_0$ is universal under ordinary analytic coupling redefinitions. In common mass-independent schemes, $b_1$ is also universal for gauge theories. Higher coefficients depend on the scheme.

The statement that a weakly coupled theory is asymptotically free depends on the sign of $b_0$, so it is robust. The precise definition of $\Lambda$ is scheme dependent, but ratios of physical quantities are not once the same theory and scheme-conversion rules are used consistently.

The slogan is:

$$
\text{the sign of the UV flow is universal; the coordinate labels are not.}
$$

## Common pitfalls

**Saying asymptotically free means free.** The theory becomes weakly coupled only in the ultraviolet limit. It can be strongly coupled at ordinary or infrared scales.

**Using the one-loop formula at $\mu\sim\Lambda$.** The formula itself says the coupling is large there. That is where the formula stops being reliable.

**Treating asymptotic freedom as a proof of confinement.** It is not. Confinement is an infrared nonperturbative property.

**Forgetting matter screening.** Too many matter fields can destroy asymptotic freedom.

**Confusing asymptotic freedom with asymptotic safety.** The former has a Gaussian UV fixed point; the latter has an interacting UV fixed point.

**Ignoring thresholds.** In QCD, the number of active quark flavors changes with scale, and matching across thresholds matters.

## Relations to other pages

[Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/) explains the opposite sign of one-loop running. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) explains the RG-invariant scale generated by asymptotic freedom. [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/) explains why high-energy logarithms are organized by running couplings. [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/) explains which parts of the beta function are convention dependent.

Later chapters connect this page to the Wilsonian picture of the Gaussian fixed point, the classification of relevant and marginal operators, gauge-theory beta functions, QCD, the operator product expansion, and nonperturbative confinement.

## Research status

The perturbative discovery and one-loop derivation of asymptotic freedom are settled. The short-distance success of QCD is one of the central achievements of quantum field theory.

The infrared fate of asymptotically free theories is much richer. Pure Yang–Mills theory is expected to confine and have a mass gap. QCD with light quarks also involves chiral symmetry breaking and hadronization. Gauge theories with many fermions may enter conformal windows rather than confining in the same way. Supersymmetric examples, lattice calculations, large-$N$ limits, semiclassical compactifications, and dualities provide complementary windows into these questions.

Thus asymptotic freedom is the beginning of the story, not the end. It gives a controlled ultraviolet definition; the infrared dynamics still has to be solved.

## Exercises

### Exercise 1: Solve the asymptotically free one-loop equation

Let

$$
\frac{dg}{d\log\mu}=-b_0g^3,
\qquad b_0>0.
$$

Show that

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}.
$$

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{dg}{g^3}=-b_0\,d\log\mu.
$$

Integrating gives

$$
-\frac{1}{2g^2}= -b_0\log\mu+\text{constant}.
$$

Equivalently,

$$
\frac{1}{g^2(\mu)}=2b_0\log\frac{\mu}{\Lambda},
$$

where $\Lambda$ is the integration constant written as a scale. Therefore

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}.
$$

As $\mu\to\infty$, the denominator grows and $g(\mu)\to 0$.

</details>

### Exercise 2: Flavor bound for QCD-like theories

For $SU(N)$ gauge theory with $n_f$ fundamental Dirac fermions,

$$
\beta_g
=
-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}N-\frac{2}{3}n_f\right)+O(g^5).
$$

Find the condition for asymptotic freedom. Specialize to $SU(3)$.

<details><summary><strong>Solution</strong></summary>

Asymptotic freedom requires the coefficient inside the parentheses to be positive:

$$
\frac{11}{3}N-\frac{2}{3}n_f>0.
$$

Multiplying by $3$ gives

$$
11N-2n_f>0,
$$

so

$$
n_f<\frac{11}{2}N.
$$

For $SU(3)$,

$$
n_f<\frac{33}{2}=16.5.
$$

Since $n_f$ is an integer, the one-loop condition is

$$
n_f\le 16.
$$

</details>

### Exercise 3: Running of αs

Using

$$
\beta_g=-\frac{B_0}{16\pi^2}g^3,
\qquad
\alpha=\frac{g^2}{4\pi},
$$

show that

$$
\alpha(\mu)=\frac{4\pi}{B_0\log(\mu^2/\Lambda^2)}.
$$

<details><summary><strong>Solution</strong></summary>

Here

$$
b_0=\frac{B_0}{16\pi^2}
$$

in the notation $\beta_g=-b_0g^3$. The one-loop solution is

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}
=
\frac{16\pi^2}{2B_0\log(\mu/\Lambda)}.
$$

Thus

$$
\alpha(\mu)=\frac{g^2(\mu)}{4\pi}
=
\frac{2\pi}{B_0\log(\mu/\Lambda)}.
$$

Since

$$
\log(\mu^2/\Lambda^2)=2\log(\mu/\Lambda),
$$

this is equivalently

$$
\alpha(\mu)=\frac{4\pi}{B_0\log(\mu^2/\Lambda^2)}.
$$

</details>

### Exercise 4: Marginally irrelevant toward the UV

Let $g$ obey

$$
\frac{dg}{d\log\mu}=-b_0g^3,
\qquad b_0>0.
$$

Explain why $g$ is called marginally irrelevant toward the UV.

<details><summary><strong>Solution</strong></summary>

At engineering level, a four-dimensional gauge coupling is dimensionless, so it is marginal at the Gaussian fixed point. If the beta function had no quantum term, it would remain exactly marginal at this order.

The leading quantum correction is cubic:

$$
\beta_g=-b_0g^3.
$$

For $g>0$, increasing $\mu$ gives $dg/d\log\mu<0$, so $g$ flows toward zero in the ultraviolet. A perturbation that dies away under RG flow toward a fixed point is irrelevant in that direction. Since the irrelevance appears only logarithmically through a cubic beta function rather than through a linear scaling exponent, it is called marginally irrelevant toward the UV.

</details>

## References

- D. J. Gross and F. Wilczek, “Ultraviolet Behavior of Non-Abelian Gauge Theories,” *Physical Review Letters* **30** (1973) 1343–1346.
- H. D. Politzer, “Reliable Perturbative Results for Strong Interactions?” *Physical Review Letters* **30** (1973) 1346–1349.
- Sidney Coleman, *Aspects of Symmetry*, especially “Dilatations” and “Asymptotic Freedom.”
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapter on asymptotic freedom and the renormalization group.
- Mark Srednicki, *Quantum Field Theory*, especially the gauge-theory beta-function sections.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on the renormalization group and QCD running.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18.
- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for RG fixed-point language and the statistical-field-theory perspective.

## Version history

- 2026-06-17: First polished draft. Added one-loop solution, non-Abelian beta-function sign, QCD running, dimensional-transmutation connection, limitations, exercises, and screening versus anti-screening figure.
