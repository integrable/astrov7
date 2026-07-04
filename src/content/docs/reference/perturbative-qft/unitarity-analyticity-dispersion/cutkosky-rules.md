---
title: "Cutkosky Rules"
description: "How perturbative unitarity turns discontinuities of Feynman diagrams into sums over on-shell cuts and physical intermediate-state phase space."
sidebar:
  label: "Cutkosky Rules"
  order: 2
level: Graduate
status: "Polished draft"
source: "Cutkosky 1960; Weinberg Vol. I; Coleman ch. 12; Srednicki §§20 and 25–26; Schwartz ch. 24"
topics:
  - unitarity
  - cutkosky rules
  - cutting rules
  - discontinuities
  - loop integrals
  - phase space
canonicalTopics:
  - cutkosky-rules
  - cutting-rules
  - perturbative-unitarity
  - discontinuity-of-amplitudes
researchStatus:
  established:
    - "Cutkosky rules are the standard perturbative implementation of S-matrix unitarity for Feynman diagrams and loop integrals."
  active:
    - "Modern variants include generalized unitarity, multi-loop integrand reconstruction, finite-temperature cutting rules, unstable-particle subtleties, and gauge-invariant formulations of cuts."
---

## Summary

The **Cutkosky rules** compute the discontinuity of a Feynman diagram across a physical branch cut by replacing selected internal propagators with on-shell delta functions. They are the diagrammatic version of the optical theorem.

For a scalar line carrying momentum $q$, the replacement at the level of a cut QFT propagator is

$$
\frac{i}{q^2-m^2+i0}
\quad\longrightarrow\quad
2\pi\theta(q^0)\delta(q^2-m^2).
$$

Equivalently, if one strips off the numerator $i$ and writes scalar denominators as $(q^2-m^2+i0)^{-1}$, the corresponding discontinuity replacement is often written

$$
\frac{1}{q^2-m^2+i0}
\quad\longrightarrow\quad
-2\pi i\,\delta_+(q^2-m^2),
\qquad
\delta_+(q^2-m^2)\equiv \theta(q^0)\delta(q^2-m^2).
$$

These two forms are the same rule expressed at different levels of bookkeeping. The first is closest to the unitarity phase-space formula. The second is closest to the discontinuity of a scalar denominator. When in doubt, track whether the graph is being called $I_\Gamma$, $i\mathcal M_\Gamma$, or $\mathcal M_\Gamma$.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 54rem;">

![Cutkosky rules turn a discontinuity into a sum over on-shell intermediate states](/figures/perturbative-qft/cutkosky-rules.svg)

<figcaption>

A cut separates a diagram into an amplitude and a conjugate amplitude with physical on-shell states crossing the cut. Each cut scalar line is replaced by an on-shell delta function. The result is an integral over the phase space of the intermediate state $X$.

</figcaption>
</figure>

The rule is powerful because it converts analytic information into physical information: discontinuities of loop amplitudes know about real intermediate states. It is also a warning label. A cut is not a picture of virtual particles becoming real inside a detector. It is a precise way to insert a complete set of on-shell states into the unitarity relation.

## Prerequisites

You should know [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/), [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/).

For later applications, it helps to know [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/).

## Core idea

The optical theorem says

$$
-i(T-T^\dagger)=T^\dagger T.
$$

The left side is a difference between an amplitude and its conjugate. In analytic language, it is a discontinuity. The right side inserts a complete set of physical intermediate states. In diagrammatic language, that insertion is a cut.

So the slogan is:

$$
\text{discontinuity of a diagram}
\quad\Longleftrightarrow\quad
\text{sum over its on-shell cuts}
\quad\Longleftrightarrow\quad
\text{phase space for intermediate states}.
$$

The word “cut” means that we draw a line through internal propagators so that the diagram splits into two pieces. The lines crossed by the cut are placed on shell and interpreted as the intermediate state summed over by unitarity.

This rule is local in a graph but global in its meaning. A single cut line is replaced by an on-shell delta function, but the cut as a whole must separate the diagram into a left amplitude and a right conjugate amplitude with consistent momentum flow.

## Setup and conventions

We use the scattering and phase-space conventions fixed in [Conventions and Notation](/perturbative-qft/conventions/). The page keeps the overall $i$ and sign bookkeeping explicit because different books attach the name “amplitude” to slightly different objects.

For a complex function of an invariant $s$, define the discontinuity across the $s$-channel cut by

$$
\operatorname{Disc}_s F(s)
\equiv
F(s+i0)-F(s-i0).
$$

For scalar propagator denominators, the distribution identity is

$$
\frac{1}{x+i0}-\frac{1}{x-i0}
=-2\pi i\delta(x).
$$

Multiplying by $i$ gives

$$
\frac{i}{x+i0}-\frac{i}{x-i0}
=2\pi\delta(x).
$$

This is the algebraic seed of the cutting rule. The extra $\theta(q^0)$ is not visible in the one-variable identity; it enters when the cut is oriented so that positive-energy intermediate particles flow across the cut.

For compact notation, write

$$
\delta_+(q^2-m^2)
\equiv
\theta(q^0)\delta(q^2-m^2).
$$

## The scalar cutting rule

Consider a scalar Feynman integral associated with a diagram $\Gamma$. Suppose the graph has internal lines $a$ with momenta $q_a$ and masses $m_a$. A cut $C$ is a set of internal lines such that slicing those lines separates the graph into a left part and a right part.

At the level of a stripped scalar integral, the cut contribution is obtained by the replacement

$$
\prod_{a\in C}\frac{1}{q_a^2-m_a^2+i0}
\quad\longrightarrow\quad
\prod_{a\in C}\big[-2\pi i\delta_+(q_a^2-m_a^2)\big],
$$

while uncut propagators remain Feynman propagators. Schematically,

$$
\operatorname{Disc}_s I_\Gamma
=
\sum_{C\in s\text{-channel cuts}} I_{\Gamma,C},
$$

where $I_{\Gamma,C}$ is the integral with the cut replacements applied.

At the level of a physical amplitude written with propagators $i/(q^2-m^2+i0)$, the same cut line contributes

$$
2\pi\delta_+(q^2-m^2).
$$

The resulting cut diagram has the form

$$
\int d\Pi_X\,\mathcal M_L\mathcal M_R^*,
$$

where $X$ is the on-shell intermediate state crossing the cut. The left and right pieces are lower-order amplitudes, with the right side complex-conjugated because it comes from $T^\dagger$.

:::note[The safest convention check]
A cut line always means an on-shell positive-energy phase-space factor. The overall sign and factor of $i$ depend on whether you are taking the discontinuity of an integral $I$, of $iI$, of $i\mathcal M$, or of $\mathcal M$. The physical unitarity statement is convention-independent.
:::

## Which cuts are allowed

A useful cut must satisfy several conditions.

First, the cut should separate the graph into two pieces. This is what allows the result to be interpreted as an amplitude times a conjugate amplitude.

Second, the cut momenta must be compatible with positive-energy flow across the cut. This is why each cut line carries $\delta_+(q^2-m^2)$, not merely $\delta(q^2-m^2)$.

Third, the cut should be in the channel whose discontinuity is being computed. An $s$-channel cut separates the incoming $s$-channel particles from the outgoing side. A $t$-channel cut computes a different analytic discontinuity.

Fourth, the cut should be kinematically possible. If no real on-shell momenta can satisfy the cut equations and total momentum conservation, the cut has no support. This is how thresholds enter.

For example, a two-particle cut with masses $m_1$ and $m_2$ in a channel with total momentum $P$ exists only when

$$
P^2\ge (m_1+m_2)^2.
$$

Below that threshold, the same loop integral may still contribute to the real part of the amplitude, but the corresponding two-particle discontinuity vanishes.

## Relation to order-by-order unitarity

Expand the transition operator in powers of the interaction,

$$
T=T^{(1)}+T^{(2)}+T^{(3)}+\cdots.
$$

The unitarity identity

$$
-i(T-T^\dagger)=T^\dagger T
$$

at order $n$ gives

$$
-i\left(T^{(n)}-T^{(n)\dagger}\right)
=
\sum_{r=1}^{n-1}T^{(r)\dagger}T^{(n-r)}.
$$

The left side is the imaginary or discontinuous part of an $n$th-order contribution. The right side is a sum over products of lower-order contributions with intermediate physical states inserted.

This equation is the conceptual reason cutting rules work. A loop graph on the left can be cut into lower-order pieces on the right. The internal cut lines are the particles in the complete set of states.

A formal diagrammatic proof is often phrased through the largest-time equation. For practical perturbative work, the message is enough: if an internal set of propagators can simultaneously go on shell and separate the graph, that cut contributes to the discontinuity.

## One-loop bubble example

Take a scalar bubble with external momentum $P$ and $s=P^2$:

$$
B(s)=
\mu^{4-d}\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m_1^2+i0}
\frac{i}{(P-\ell)^2-m_2^2+i0}.
$$

The two-particle cut replaces both propagators by on-shell delta functions:

$$
\operatorname{Cut}B(s)
=
\mu^{4-d}\int\frac{d^d\ell}{(2\pi)^d}
(2\pi)\delta_+(\ell^2-m_1^2)
(2\pi)\delta_+((P-\ell)^2-m_2^2),
$$

up to the overall $i$ convention used for the discontinuity of $B$. The right-hand side is exactly the two-body phase-space measure in disguise.

In four dimensions, the fully integrated two-body phase space is

$$
\int d\Phi_2(P;m_1,m_2)
=
\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{8\pi s}
\theta\!\big(s-(m_1+m_2)^2\big),
$$

where

$$
\lambda(s,m_1^2,m_2^2)
=
\big(s-(m_1+m_2)^2\big)\big(s-(m_1-m_2)^2\big).
$$

This formula exhibits two key facts. The cut vanishes below threshold, and near the normal threshold it has square-root behavior. That square root is the local signature of a branch point.

For equal internal masses $m_1=m_2=m$,

$$
\int d\Phi_2(P;m,m)
=
\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{s}}\,\theta(s-4m^2).
$$

That square root is why the bubble integral has a branch cut starting at $s=4m^2$.

## Numerators, spin, and polarizations

Real theories are not just scalar denominators. Fermions, gauge bosons, derivative interactions, and tensor particles bring numerators and sums over quantum numbers.

The rule is simple in principle: evaluate the two sides of the cut as physical amplitudes and sum over the internal on-shell states crossing the cut. For a fermion crossing the cut, the spin sum supplies factors such as

$$
\sum_s u_s(p)\overline u_s(p)=\gamma^\mu p_\mu+m.
$$

For gauge bosons, one must use a consistent polarization sum or a gauge-fixed calculation in which unphysical contributions cancel in gauge-invariant quantities.

The numerator is not an optional decoration. In many gauge-theory amplitudes, wrong numerator or polarization bookkeeping destroys Ward identities and produces nonsense cuts.

## Gauge theories and ghosts

In a covariant gauge, intermediate lines in diagrams can include ghosts and unphysical polarizations. This does not mean ghosts are physical particles in the unitarity sum. It means the gauge-fixed diagrammatic bookkeeping has introduced auxiliary fields whose contributions cancel unphysical gauge modes.

There are two safe ways to proceed.

One is to use a manifestly physical-state formulation when possible. Then the cut sum contains only physical polarizations and physical particles.

The other is to use the gauge-fixed Feynman rules consistently, including ghost cuts where required, and rely on Ward identities or BRST symmetry to guarantee cancellation of unphysical states in gauge-invariant observables.

The moral is not “ghosts go on shell as particles.” The moral is that gauge-fixed perturbation theory must implement the same physical unitarity as the gauge-invariant theory.

## Relation to generalized unitarity

Cutkosky rules compute discontinuities of already-defined loop diagrams. Modern generalized unitarity uses the same logic more aggressively: instead of first constructing the loop integral and then cutting it, one reconstructs the loop integrand or amplitude from many cuts.

A two-particle cut may determine only part of an amplitude. Multi-particle cuts, multiple cuts, and cuts in complexified kinematics can isolate more detailed integral coefficients. At one loop, quadruple cuts can freeze loop momenta in four dimensions and directly read off box coefficients in many theories.

So Cutkosky rules are not outdated. They are the conservative ancestor of much of modern amplitudes technology.

## Common pitfalls

**Cutting the wrong object.** The discontinuity of an integral, the imaginary part of an amplitude, and the optical-theorem right-hand side differ by conventional factors of $i$ and signs. Decide what object you are cutting before comparing formulas.

**Forgetting positive energy.** A physical cut uses $\delta_+(q^2-m^2)$, not just $\delta(q^2-m^2)$. The $\theta(q^0)$ selects the direction of intermediate-state propagation across the cut.

**Ignoring thresholds.** A cut contributes only when the cut on-shell equations have real solutions compatible with momentum conservation.

**Treating every imaginary part as a chosen cut.** A diagram can have several branch cuts in different channels. The discontinuity in one channel is not the same as the full imaginary part in all kinematic regions.

**Dropping numerator information.** For spinor and gauge theories, cut numerators encode spin sums, polarization sums, and Ward identities.

**Interpreting gauge-fixed cuts too literally.** Ghost and longitudinal contributions can appear in intermediate diagrammatic calculations, but the physical unitarity relation sums over physical states.

**Confusing Cutkosky cuts with arbitrary graph slicing.** A useful cut must separate the graph into two pieces and correspond to the channel discontinuity under study.

## Relations to other pages

- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) gives the unitarity identity whose diagrammatic implementation is the cutting rule.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) explains the analytic language of discontinuities and physical cuts.
- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) introduces cuts as a loop-integral technology.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) gives the simplest integral where the cut produces two-body phase space.
- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) defines the on-shell measures that appear on cut lines.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) and [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/) provide the gauge-theory ingredients needed for gauge-fixed cuts.

## Research status

Cutkosky rules are a standard consequence of perturbative unitarity and correctly reproduce physical discontinuities when applied within their assumptions. For ordinary stable-particle amplitudes in flat spacetime, they are settled textbook technology.

Cutting methods remain central in multi-loop amplitude reconstruction, collider calculations, finite-temperature rates, unstable-particle effective theories, and bootstrap-style constraints. Gauge theories, massless particles, overlapping infrared singularities, unstable particles, confined degrees of freedom, and finite-density or real-time systems require extra care in identifying the correct physical state sum and analytic continuation.

## Exercises

### Exercise 1: Distribution identity

Show that

$$
\frac{1}{x+i0}-\frac{1}{x-i0}=-2\pi i\delta(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Use the Sokhotski formula

$$
\frac{1}{x\pm i0}=\operatorname{PV}\frac{1}{x}\mp i\pi\delta(x).
$$

Therefore

$$
\frac{1}{x+i0}-\frac{1}{x-i0}
=
\left(\operatorname{PV}\frac1x-i\pi\delta(x)\right)
-
\left(\operatorname{PV}\frac1x+i\pi\delta(x)\right)
=-2\pi i\delta(x).
$$

</details>

### Exercise 2: Cut line with the propagator numerator included

Using Exercise 1, compute

$$
\frac{i}{x+i0}-\frac{i}{x-i0}.
$$

<details>
<summary><strong>Solution</strong></summary>

Multiply the identity in Exercise 1 by $i$:

$$
\frac{i}{x+i0}-\frac{i}{x-i0}
=i(-2\pi i\delta(x))
=2\pi\delta(x).
$$

This is why a cut scalar propagator written as $i/(q^2-m^2+i0)$ contributes an on-shell factor $2\pi\delta(q^2-m^2)$, with the positive-energy condition added by the physical cut orientation.

</details>

### Exercise 3: Bubble threshold

For a bubble with cut internal masses $m_1$ and $m_2$, show that the cut has support only when

$$
s=P^2\ge (m_1+m_2)^2.
$$

<details>
<summary><strong>Solution</strong></summary>

The cut equations are

$$
\ell^2=m_1^2,
\qquad
(P-\ell)^2=m_2^2,
$$

with both energies positive. In the center-of-mass frame, $P=(\sqrt{s},\mathbf 0)$, so the two on-shell particles have energies

$$
E_1=\sqrt{\mathbf p^2+m_1^2},
\qquad
E_2=\sqrt{\mathbf p^2+m_2^2}.
$$

Energy conservation requires

$$
\sqrt{s}=E_1+E_2.
$$

The minimum possible value of the right-hand side occurs at $\mathbf p=0$, giving

$$
\sqrt{s}\ge m_1+m_2.
$$

Thus

$$
s\ge(m_1+m_2)^2.
$$

</details>

### Exercise 4: Two-body phase-space factor

Use the known four-dimensional two-body phase-space result to show that the equal-mass bubble cut has square-root threshold behavior.

<details>
<summary><strong>Solution</strong></summary>

For two particles with equal mass $m$,

$$
\lambda(s,m^2,m^2)=s(s-4m^2).
$$

The integrated two-body phase space is

$$
\int d\Phi_2(P;m,m)
=
\frac{\lambda^{1/2}(s,m^2,m^2)}{8\pi s}\theta(s-4m^2).
$$

Substituting the equal-mass Källén function gives

$$
\int d\Phi_2(P;m,m)
=
\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{s}}\,\theta(s-4m^2).
$$

Near $s=4m^2$, this is proportional to

$$
\sqrt{s-4m^2}.
$$

This square-root behavior is the branch-point behavior of the bubble discontinuity.

</details>

### Exercise 5: Order-by-order unitarity

Starting from

$$
-i(T-T^\dagger)=T^\dagger T,
$$

and $T=\sum_{n\ge1}T^{(n)}$, derive the order-$n$ relation

$$
-i\left(T^{(n)}-T^{(n)\dagger}\right)
=
\sum_{r=1}^{n-1}T^{(r)\dagger}T^{(n-r)}.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the expansion into both sides. The left-hand side gives

$$
-i\sum_{n\ge1}\left(T^{(n)}-T^{(n)\dagger}\right).
$$

The right-hand side is

$$
T^\dagger T
=
\left(\sum_{r\ge1}T^{(r)\dagger}\right)
\left(\sum_{k\ge1}T^{(k)}\right)
=
\sum_{r,k\ge1}T^{(r)\dagger}T^{(k)}.
$$

Terms of total perturbative order $n$ have $r+k=n$, so $k=n-r$ and $r=1,\dots,n-1$. Matching order by order gives

$$
-i\left(T^{(n)}-T^{(n)\dagger}\right)
=
\sum_{r=1}^{n-1}T^{(r)\dagger}T^{(n-r)}.
$$

Diagrammatically, this is why an $n$th-order discontinuity is represented by products of lower-order amplitudes across cuts.

</details>

## References

### Standard first pass

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3 and 6, for unitarity, scattering theory, and Feynman-rule foundations.
- M. Srednicki, *Quantum Field Theory*, §§20 and 25–26, for loop amplitudes, elastic scattering, and infrared-related discontinuities.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for unitarity, the optical theorem, spectral decomposition, and branch cuts.

### Original and deeper references

- R. E. Cutkosky, “Singularities and discontinuities of Feynman amplitudes,” *Journal of Mathematical Physics* **1** (1960), for the original cutting rules.
- S. Coleman, *Lectures on Quantum Field Theory*, ch. 12, for the optical theorem and scattering interpretation.
- G. 't Hooft and M. Veltman, “Diagrammar,” for diagrammatic cutting and unitarity methods in perturbative field theory.

## Version history

- **2026-06-13:** Initial standardized page.
