---
title: "Self-Energy Diagrams"
description: "A convention-aware explanation of one-particle-irreducible two-point insertions, Dyson resummation, pole masses, residues, and the first scalar self-energy examples."
sidebar:
  label: "Self-Energy Diagrams"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§13–16; Coleman 2019, chs. 10 and 15–16; Weinberg 1995, Vol. I, chs. 6 and 10; Schwartz 2014, chs. 16 and 18–19; Zinn-Justin 2021, chs. 7–10"
topics:
  - self-energy
  - propagator corrections
  - Dyson resummation
  - pole mass
  - wavefunction renormalization
canonicalTopics:
  - self-energy-diagram
  - two-point-1pi-function
  - dyson-resummed-propagator
  - pole-mass
  - wavefunction-renormalization
researchStatus:
  established:
    - "Self-energy diagrams are the standard one-particle-irreducible two-point insertions that correct propagators, shift pole masses, determine residues, and generate widths when intermediate states can go on shell."
  active:
    - "Precision applications require gauge-invariant definitions of masses and widths, careful treatment of unstable particles, infrared effects, scheme dependence, and resummation beyond the elementary scalar examples on this page."
---

## Summary

A **self-energy diagram** is a one-particle-irreducible two-point insertion. It corrects the propagator rather than directly adding a new external scattering process.

For a scalar field, this page defines the amputated 1PI two-point insertion as

$$
\text{1PI two-point insertion}=-i\Sigma(p^2).
$$

With this convention, the Dyson-resummed scalar propagator is

$$
G(p)
=
\frac{i}{p^2-m^2-\Sigma(p^2)+i\epsilon}
$$

up to the usual caveat that the exact propagator can also contain multiparticle cuts and possible isolated poles. The physical pole mass $M$ is determined by

$$
M^2-m^2-\operatorname{Re}\Sigma(M^2)=0,
$$

and the residue near a stable one-particle pole is

$$
Z^{-1}=1-\operatorname{Re}\Sigma'(M^2).
$$

Self-energies are where perturbation theory first teaches that the parameters in a Lagrangian are not automatically physical observables. The mass and field normalization must be fixed by renormalization conditions or by a chosen subtraction scheme.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Dyson resummation expresses the full propagator as free propagation plus repeated one-particle-irreducible self-energy insertions; scalar examples include the tadpole, bubble, and counterterm insertion](/figures/perturbative-qft/self-energy-diagrams.svg)

<figcaption>

Self-energy diagrams are 1PI two-point insertions. Repeating the insertion inside a propagator gives the Dyson-resummed denominator $p^2-m^2-\Sigma(p^2)$. Tadpoles shift masses, momentum-dependent bubbles also affect residues, and counterterm insertions absorb local ultraviolet divergences according to the chosen renormalization scheme.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), and [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/).

For the exact-propagator viewpoint, review [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) and [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/).

## Core idea

A propagator describes how a field creates an excitation, lets it propagate, and annihilates it. Interactions modify this propagation. The modification is not just one diagram: a particle can propagate, receive a self-energy insertion, propagate again, receive another insertion, and so on.

The useful object is therefore not the full collection of repeated insertions. It is the irreducible kernel that cannot be split into two pieces by cutting one internal line. That kernel is the self-energy.

The practical slogan is

$$
\text{self-energy} = \text{the 1PI correction to the inverse propagator}.
$$

This slogan is more reliable than the phrase “a particle emits and reabsorbs a virtual particle.” The diagrammatic picture is helpful, but the precise object is the two-point 1PI function and its contribution to the pole structure of the propagator.

## Setup and conventions

We work with a real scalar field unless stated otherwise. The free propagator is

$$
D_0(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The scalar self-energy convention is

$$
\text{1PI two-point insertion}=-i\Sigma(p^2).
$$

With this choice, repeated insertions give

$$
D_0(p)+D_0(p)(-i\Sigma)D_0(p)
+D_0(p)(-i\Sigma)D_0(p)(-i\Sigma)D_0(p)+\cdots.
$$

For counterterms, write

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2.
$$

The corresponding quadratic counterterm vertex is

$$
i(\delta Z\,p^2-\delta m^2)
=-i(\delta m^2-\delta Z\,p^2).
$$

Therefore, in this convention, the counterterm contribution to the self-energy is

$$
\Sigma_{\rm ct}(p^2)=\delta m^2-\delta Z\,p^2.
$$

This sign bookkeeping is not glamorous, but it is exactly where many incorrect propagator formulas are born.

## Dyson resummation

Using the convention above, the repeated insertion series is

$$
\begin{aligned}
G(p)
&=\frac{i}{p^2-m^2+i\epsilon}
+\frac{i}{p^2-m^2+i\epsilon}(-i\Sigma)
\frac{i}{p^2-m^2+i\epsilon}+\cdots.
\end{aligned}
$$

Let

$$
A=p^2-m^2+i\epsilon.
$$

Then

$$
G(p)
=\frac{i}{A}
\left[1+\frac{\Sigma}{A}+\left(\frac{\Sigma}{A}\right)^2+\cdots\right].
$$

Formally summing the geometric series gives

$$
G(p)=\frac{i}{A-\Sigma(p^2)}
=
\frac{i}{p^2-m^2-\Sigma(p^2)+i\epsilon}.
$$

This formula should be read perturbatively unless a resummation prescription has been justified. Near a pole, resummation is often necessary to identify masses, residues, or widths. Away from a pole, expanding order by order may be the safer organization.

## Pole mass and residue

A stable one-particle pole occurs where the denominator vanishes:

$$
P(p^2)=p^2-m^2-\Sigma(p^2)=0.
$$

Define the physical mass $M$ by

$$
M^2-m^2-\operatorname{Re}\Sigma(M^2)=0.
$$

Near the pole,

$$
P(p^2)
=P(M^2)+(p^2-M^2)P'(M^2)+\cdots
=(p^2-M^2)\left[1-\Sigma'(M^2)\right]+\cdots.
$$

Thus the propagator behaves as

$$
G(p)
\sim
\frac{iZ}{p^2-M^2+i\epsilon}
+\text{less singular terms},
$$

where

$$
Z^{-1}=1-\operatorname{Re}\Sigma'(M^2).
$$

The pole position is physical for a stable particle. The residue depends on the normalization of the interpolating field, but it is exactly the factor that appears in LSZ reduction.

:::note[Mass parameter versus pole mass]
The symbol $m$ in the Lagrangian is a parameter. The physical mass is identified from the pole of the exact propagator. A renormalization condition may choose $m=M$ order by order, but that is a scheme choice, not an identity before renormalization.
:::

## Tadpole self-energy in φ⁴ theory

Consider

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4.
$$

The one-loop tadpole correction to the two-point function has 1PI insertion

$$
-i\Sigma_{\rm tad}^{(1)}
=
\frac{-i\lambda}{2}
A(m^2),
$$

where

$$
A(m^2)
\equiv
\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m^2+i\epsilon}.
$$

Therefore

$$
\Sigma_{\rm tad}^{(1)}
=
\frac{\lambda}{2}A(m^2).
$$

In dimensional regularization,

$$
A(m^2)
=
\frac{m^2}{16\pi^2}
\left[
-\frac{1}{\overline\epsilon}
+
\ln\frac{m^2}{\mu^2}
-1
\right]
+O(\epsilon).
$$

This one-loop self-energy is independent of $p^2$. It shifts the mass but does not produce a one-loop wavefunction renormalization in four-dimensional $\phi^4$ theory. Momentum-dependent two-point corrections first appear at higher loop order in this theory.

## Bubble self-energy in cubic scalar theory

Now consider a cubic interaction

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3.
$$

The one-loop two-point bubble has two cubic vertices and symmetry factor $2$. Using the stripped bubble function from [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/),

$$
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+p)^2-m^2+i\epsilon}
=-iB(p^2;m^2,m^2).
$$

The 1PI insertion is

$$
-i\Sigma_{\rm bub}^{(1)}(p^2)
=
\frac{(-ig)^2}{2}
\left[-iB(p^2;m^2,m^2)\right],
$$

so

$$
\Sigma_{\rm bub}^{(1)}(p^2)
=-\frac{g^2}{2}B(p^2;m^2,m^2).
$$

Unlike the $\phi^4$ tadpole, this self-energy depends on $p^2$. Its divergent part in four dimensions is local and proportional to a constant, but in six-dimensional $\phi^3$ theory the analogous bubble has divergences proportional to both $p^2$ and $m^2$, requiring both field-strength and mass counterterms.

Momentum dependence is the beginning of wavefunction renormalization. Expanding near the physical pole,

$$
\Sigma(p^2)
=\Sigma(M^2)+(p^2-M^2)\Sigma'(M^2)+\cdots,
$$

shows that the constant part shifts the pole position, while the derivative changes the pole residue.

## Counterterms and renormalized self-energy

A loop self-energy by itself is usually divergent. The renormalized self-energy is the sum of loop diagrams and counterterm insertions:

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Z\,p^2.
$$

The values of $\delta m^2$ and $\delta Z$ depend on the renormalization scheme.

In an on-shell scheme for a stable scalar particle, one often imposes

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

The first condition fixes the pole at $p^2=M^2$. The second fixes the residue to be $Z=1$ for the renormalized field. In minimal subtraction, by contrast, one subtracts only pole terms and leaves finite shifts in the relation between the Lagrangian parameters and pole observables.

Neither scheme is “more physical” by itself. A scheme is a convention for labeling the same predictions by different intermediate parameters.

## Imaginary parts and widths

If the self-energy contains intermediate states that can go on shell, $\Sigma(p^2)$ develops an imaginary part. For an unstable particle, the pole moves off the real axis. Schematically,

$$
p^2_{\rm pole}=M^2-iM\Gamma.
$$

With the convention

$$
G(p)=\frac{i}{p^2-m^2-\Sigma(p^2)},
$$

a narrow width satisfies

$$
\Gamma
= -\frac{1}{M}\operatorname{Im}\Sigma(M^2)
$$

at leading order, after the real part has fixed $M$. The minus sign is convention-dependent, but the physical statement is not: the imaginary part of the self-energy is tied by unitarity to decay probability into on-shell intermediate states.

This is the self-energy version of the optical theorem. The elementary bubble threshold already shows the mechanism: above two-particle threshold, the loop logarithm develops an absorptive part.

## Common pitfalls

**Using the wrong sign for $\Sigma$.** Some authors define the 1PI insertion as $i\Pi$ instead of $-i\Sigma$. Then the denominator is written differently. Before comparing formulas, identify the insertion convention and the resummed denominator.

**Calling every two-point diagram a self-energy.** In this page, self-energy means the 1PI two-point insertion. A reducible chain of insertions is generated by Dyson resummation; it is not the primitive self-energy kernel.

**Equating the Lagrangian mass with the pole mass.** The equality can be imposed order by order in an on-shell scheme, but it is not automatic. In other schemes, the pole mass is a derived quantity.

**Ignoring field normalization.** The residue of the pole depends on the normalization of the interpolating field. LSZ reduction compensates for this through the external-leg residue factors.

**Resumming without a reason.** Dyson resummation near a pole is physically useful. Away from poles, uncontrolled partial resummations can double-count terms or spoil gauge cancellations unless the approximation is organized carefully.

## Relations to other pages

- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) defines the irreducibility condition used by self-energy diagrams.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) evaluates the scalar bubble that appears in momentum-dependent two-point functions.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) introduces the counterterm insertions that cancel local self-energy divergences.
- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains why pole residues and external-leg normalization matter for scattering amplitudes.
- [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) uses the pole structure of unstable propagators in cross-section calculations.

## Research status

The scalar self-energy formalism, Dyson resummation, pole mass, and residue formulas are textbook-standard. The elementary tadpole and bubble examples are settled perturbative calculations.

The subtleties arise in precision and gauge-theory settings. Gauge-dependent intermediate self-energies must be combined into gauge-invariant observables; unstable-particle poles require careful complex-pole definitions; infrared effects can obstruct naive pole expansions for massless particles; and high-order calculations demand consistent scheme, regulator, and resummation choices.

## Exercises

### Exercise 1: Sum the Dyson series

Starting from

$$
D_0(p)=\frac{i}{p^2-m^2+i\epsilon}
$$

and the insertion $-i\Sigma(p^2)$, show that

$$
D_0+D_0(-i\Sigma)D_0+D_0(-i\Sigma)D_0(-i\Sigma)D_0+\cdots
=
\frac{i}{p^2-m^2-\Sigma(p^2)+i\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

Let

$$
A=p^2-m^2+i\epsilon.
$$

Then $D_0=i/A$. The series becomes

$$
\frac{i}{A}
+\frac{i}{A}(-i\Sigma)\frac{i}{A}
+\frac{i}{A}(-i\Sigma)\frac{i}{A}(-i\Sigma)\frac{i}{A}
+\cdots.
$$

The first correction is

$$
\frac{i\Sigma}{A^2},
$$

so the series is

$$
\frac{i}{A}\left[1+\frac{\Sigma}{A}+\left(\frac{\Sigma}{A}\right)^2+\cdots\right]
=
\frac{i}{A}\frac{1}{1-\Sigma/A}
=
\frac{i}{A-\Sigma}.
$$

</details>

### Exercise 2: Tadpole self-energy in φ⁴ theory

Use the quartic vertex $-i\lambda$ and the tadpole symmetry factor to show that

$$
\Sigma_{\rm tad}^{(1)}=\frac{\lambda}{2}A(m^2).
$$

<details>
<summary><strong>Solution</strong></summary>

The one-loop tadpole insertion has one quartic vertex and one internal propagator whose ends are attached to the same vertex. The contraction counting leaves the factor $1/2$. Thus the 1PI two-point insertion is

$$
-i\Sigma_{\rm tad}^{(1)}
=
\frac{-i\lambda}{2}
\int_\ell\frac{i}{\ell^2-m^2+i\epsilon}
=
\frac{-i\lambda}{2}A(m^2).
$$

Dividing by $-i$ gives

$$
\Sigma_{\rm tad}^{(1)}=\frac{\lambda}{2}A(m^2).
$$

</details>

### Exercise 3: First-order pole-mass shift

Suppose $\Sigma$ is already one-loop order. Show that, to first order in the loop expansion,

$$
M^2=m^2+\operatorname{Re}\Sigma(m^2)+O(\Sigma^2).
$$

<details>
<summary><strong>Solution</strong></summary>

The pole equation is

$$
M^2-m^2-\operatorname{Re}\Sigma(M^2)=0.
$$

Since $\Sigma$ is already first order, the difference between evaluating it at $M^2$ and at $m^2$ is higher order:

$$
\Sigma(M^2)=\Sigma(m^2)+(M^2-m^2)\Sigma'(m^2)+\cdots.
$$

But $M^2-m^2$ is itself first order, so the derivative term is second order. Therefore

$$
M^2-m^2-\operatorname{Re}\Sigma(m^2)=O(\Sigma^2),
$$

which gives the stated result.

</details>

### Exercise 4: Width from the imaginary part

Assume the propagator denominator is

$$
p^2-m^2-\Sigma(p^2)
$$

and the pole is $p^2_{\rm pole}=M^2-iM\Gamma$ with $\Gamma\ll M$. Derive

$$
\Gamma=-\frac{1}{M}\operatorname{Im}\Sigma(M^2)
$$

at leading order.

<details>
<summary><strong>Solution</strong></summary>

Insert

$$
p^2_{\rm pole}=M^2-iM\Gamma
$$

into the pole equation:

$$
M^2-iM\Gamma-m^2-\Sigma(M^2-iM\Gamma)=0.
$$

At leading order in the width and loop expansion, evaluate $\Sigma$ at $M^2$. Separate real and imaginary parts:

$$
M^2-m^2-\operatorname{Re}\Sigma(M^2)
-i\left[M\Gamma+\operatorname{Im}\Sigma(M^2)\right]=0.
$$

The real part fixes the mass. The imaginary part gives

$$
M\Gamma+\operatorname{Im}\Sigma(M^2)=0,
$$

so

$$
\Gamma=-\frac{1}{M}\operatorname{Im}\Sigma(M^2).
$$

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§13–16, for exact propagators, loop corrections to propagators, and one-loop self-energy examples.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 16 and 18–19, for vacuum polarization, mass renormalization, counterterms, and two-point functions.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 10 and 15–16, for Feynman diagrams, mass renormalization, and one-loop scalar self-energies.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 10, for general diagrammatic rules and renormalized perturbation theory.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 7–10, for 1PI functions, loop expansion, and renormalization in the functional framework.
- G. Källén, “On the Definition of the Renormalization Constants in Quantum Electrodynamics,” *Helvetica Physica Acta* **25** (1952), and H. Lehmann, “On the Properties of Propagation Functions and Renormalization Constants of Quantized Fields,” *Nuovo Cimento* **11** (1954), for the spectral representation underlying exact propagator pole and continuum structure.

## Version history

- **2026-06-12:** Initial standardized page.
