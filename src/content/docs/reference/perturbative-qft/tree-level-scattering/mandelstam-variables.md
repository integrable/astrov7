---
title: "Mandelstam Variables"
description: "A convention-safe guide to the Lorentz-invariant variables s, t, and u for two-to-two scattering, their physical regions, center-of-mass formulas, and channel interpretation."
sidebar:
  label: "Mandelstam Variables"
  order: 1
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, ch. 3; Coleman 2019, ch. 11; Srednicki 2007, §§10–11; Schwartz 2014, chs. 5–7"
topics:
  - Mandelstam variables
  - two-to-two kinematics
  - scattering amplitudes
  - crossing symmetry
  - tree-level scattering
canonicalTopics:
  - mandelstam-variables
  - two-to-two-kinematics
  - scattering-channels
  - center-of-mass-kinematics
researchStatus:
  established:
    - "The Mandelstam variables and their physical-region constraints are standard Lorentz-invariant kinematics for two-to-two scattering."
  active:
    - "Analytic continuation between physical regions, massless infrared subtleties, unstable particles, and finite-volume scattering require more careful treatments than the stable-particle kinematic formulas collected here."
---

## Summary

**Mandelstam variables** are Lorentz-invariant coordinates for $2\to2$ scattering. For the physical process

$$
1(p_1)+2(p_2)\to3(p_3)+4(p_4),
$$

with all $p_i$ positive-energy physical momenta, qft.org uses

$$
 s=(p_1+p_2)^2,
 \qquad
 t=(p_1-p_3)^2,
 \qquad
 u=(p_1-p_4)^2.
$$

Here $s$ is the squared center-of-mass energy, $t$ is the squared momentum transfer from particle $1$ to particle $3$, and $u$ is the crossed momentum transfer from particle $1$ to particle $4$. For external masses $p_i^2=m_i^2$, the variables obey

$$
{s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.}
$$

Thus, at fixed masses, only two of $s,t,u$ are independent. They are the natural language for tree-level amplitudes because internal propagator denominators become $s-M^2$, $t-M^2$, or $u-M^2$ depending on the exchange channel.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![The three Mandelstam pairings for two-to-two scattering](/figures/perturbative-qft/mandelstam-variables-map.svg)

<figcaption>

For $1+2\to3+4$, the variables $s,t,u$ are the three inequivalent pairings of four external momenta. The $s$ channel groups the two incoming particles, while $t$ and $u$ measure the two possible momentum transfers. Momentum conservation and on-shell conditions impose $s+t+u=\sum_i m_i^2$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/), and [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/).

## Core idea

A scattering amplitude should not depend on how we orient the laboratory axes. For a $2\to2$ process, Lorentz invariance says that the scalar kinematics can be expressed in terms of invariant dot products of the external four-momenta. Momentum conservation and on-shell conditions reduce these dot products to two independent variables. The traditional symmetric choice is $s,t,u$.

The mnemonic is:

| Variable | Pairing | Physical role in the $s$-channel process |
|---|---|---|
| $s$ | $(p_1+p_2)^2$ | total incoming energy squared |
| $t$ | $(p_1-p_3)^2$ | momentum transfer $1\to3$ |
| $u$ | $(p_1-p_4)^2$ | momentum transfer $1\to4$ |

The same symbols also organize crossing. In the ordinary $s$-channel physical region, $s$ is the energy squared. In a crossed process, $t$ or $u$ can become the physical energy squared instead. That is why scattering theory keeps all three variables visible even though only two are independent.

## Setup and conventions

We use the qft.org mostly-minus metric,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
p^2=(p^0)^2-\mathbf p^2.
$$

The physical process is

$$
1(p_1)+2(p_2)\to3(p_3)+4(p_4),
$$

with

$$
p_i^2=m_i^2,
\qquad
p_1+p_2=p_3+p_4.
$$

All $p_i$ in this page are physical positive-energy momenta unless stated otherwise. This is different from all-incoming notation, where outgoing particles are assigned reversed four-momenta.

The total incoming four-momentum is

$$
P=p_1+p_2=p_3+p_4,
$$

so

$$
s=P^2.
$$

In the center-of-mass frame of the incoming pair,

$$
P=(\sqrt{s},\mathbf 0),
$$

so $s$ really is the square of the total center-of-mass energy.

## Definitions and equivalent forms

The Mandelstam variables are

$$
s=(p_1+p_2)^2=(p_3+p_4)^2,
$$

$$
t=(p_1-p_3)^2=(p_2-p_4)^2,
$$

$$
u=(p_1-p_4)^2=(p_2-p_3)^2.
$$

The equalities on the right follow from momentum conservation. For example,

$$
p_1-p_3=p_4-p_2=-(p_2-p_4),
$$

and squaring removes the sign.

Expanded in dot products,

$$
s=m_1^2+m_2^2+2p_1\cdot p_2,
$$

$$
t=m_1^2+m_3^2-2p_1\cdot p_3,
$$

$$
u=m_1^2+m_4^2-2p_1\cdot p_4.
$$

These formulas are often the fastest way to translate between invariant notation and a chosen frame.

## All-incoming notation

For analytic amplitudes and Feynman rules, it is common to treat every external momentum as incoming. For the physical process above, define

$$
q_1=p_1,
\qquad
q_2=p_2,
\qquad
q_3=-p_3,
\qquad
q_4=-p_4.
$$

Then

$$
q_1+q_2+q_3+q_4=0,
$$

and the same invariants can be written as

$$
s=(q_1+q_2)^2=(q_3+q_4)^2,
$$

$$
t=(q_1+q_3)^2=(q_2+q_4)^2,
$$

$$
u=(q_1+q_4)^2=(q_2+q_3)^2.
$$

This is a common source of sign mistakes. In physical in/out notation, $t=(p_1-p_3)^2$. In all-incoming notation, the same invariant is $(q_1+q_3)^2$ because $q_3=-p_3$.

## The sum rule

The variables obey

$$
{s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.}
$$

One derivation is short. Using the expanded formulas,

$$
\begin{aligned}
s+t+u
&=3m_1^2+m_2^2+m_3^2+m_4^2
+2p_1\cdot(p_2-p_3-p_4).
\end{aligned}
$$

Momentum conservation gives

$$
p_2-p_3-p_4=-p_1,
$$

so

$$
2p_1\cdot(p_2-p_3-p_4)=-2p_1^2=-2m_1^2.
$$

Therefore

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

For identical particles of mass $m$,

$$
s+t+u=4m^2.
$$

For massless external particles,

$$
s+t+u=0.
$$

## Center-of-mass kinematics

Work in the center-of-mass frame of the incoming particles. Choose

$$
p_1=(E_1,0,0,p),
\qquad
p_2=(E_2,0,0,-p),
$$

and let the outgoing particle $3$ make scattering angle $\theta$ with particle $1$:

$$
p_3=(E_3,p'\sin\theta,0,p'\cos\theta),
\qquad
p_4=(E_4,-p'\sin\theta,0,-p'\cos\theta).
$$

The energies are fixed by $s$ and the masses:

$$
E_1=\frac{s+m_1^2-m_2^2}{2\sqrt{s}},
\qquad
E_2=\frac{s+m_2^2-m_1^2}{2\sqrt{s}},
$$

$$
E_3=\frac{s+m_3^2-m_4^2}{2\sqrt{s}},
\qquad
E_4=\frac{s+m_4^2-m_3^2}{2\sqrt{s}}.
$$

The momentum magnitudes are

$$
p=\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}},
\qquad
p'=\frac{\sqrt{\lambda(s,m_3^2,m_4^2)}}{2\sqrt{s}},
$$

where the Källén function is

$$
\lambda(x,y,z)=x^2+y^2+z^2-2xy-2xz-2yz.
$$

Then

$$
 t=m_1^2+m_3^2-2E_1E_3+2pp'\cos\theta,
$$

and

$$
 u=m_1^2+m_4^2-2E_1E_4-2pp'\cos\theta.
$$

Equivalently,

$$
\cos\theta
=
\frac{2s(t-m_1^2-m_3^2)+(s+m_1^2-m_2^2)(s+m_3^2-m_4^2)}
{\sqrt{\lambda(s,m_1^2,m_2^2)\lambda(s,m_3^2,m_4^2)}}.
$$

This formula is useful when an amplitude is written as $\mathcal M(s,t)$ but an observable is differential in the scattering angle.

## Equal-mass simplification

For elastic scattering of identical particles of mass $m$,

$$
m_1=m_2=m_3=m_4=m,
$$

and in the center-of-mass frame

$$
E_1=E_2=E_3=E_4=\frac{\sqrt{s}}{2},
\qquad
p^2=\frac{s}{4}-m^2.
$$

The momentum transfers become

$$
 t=-2p^2(1-\cos\theta)
 =-\frac{s-4m^2}{2}(1-\cos\theta),
$$

$$
 u=-2p^2(1+\cos\theta)
 =-\frac{s-4m^2}{2}(1+\cos\theta).
$$

Thus, in the physical $s$-channel region above threshold,

$$
s\ge4m^2,
\qquad
-(s-4m^2)\le t\le0,
\qquad
-(s-4m^2)\le u\le0.
$$

At forward scattering, $\theta=0$, so $t=0$. At backward scattering, $\theta=\pi$, so $u=0$.

For massless $2\to2$ scattering, the formulas reduce to

$$
t=-\frac{s}{2}(1-\cos\theta),
\qquad
u=-\frac{s}{2}(1+\cos\theta),
\qquad
s+t+u=0.
$$

## Physical region

For a real $s$-channel scattering experiment, the incoming and outgoing center-of-mass momenta must be real:

$$
\lambda(s,m_1^2,m_2^2)\ge0,
\qquad
\lambda(s,m_3^2,m_4^2)\ge0.
$$

For ordinary positive-energy scattering, this means

$$
s\ge(m_1+m_2)^2,
\qquad
s\ge(m_3+m_4)^2.
$$

At fixed $s$, the allowed range of $t$ comes from $-1\le\cos\theta\le1$:

$$
 t_\pm
 =m_1^2+m_3^2
 -\frac{(s+m_1^2-m_2^2)(s+m_3^2-m_4^2)}{2s}
 \pm
 \frac{\sqrt{\lambda(s,m_1^2,m_2^2)\lambda(s,m_3^2,m_4^2)}}{2s}.
$$

Here $t_+$ is the forward endpoint and $t_-$ is the backward endpoint. The corresponding $u$ range follows from the sum rule.

These inequalities describe the physical $s$-channel region. Crossing symmetry relates this region to different physical regions in which $t$ or $u$ becomes the energy squared. Those regions are not usually reached by keeping all real momenta fixed and merely renaming variables; they are reached by analytic continuation.

## Channel denominators

The Mandelstam variables appear directly in propagator denominators. Suppose a tree diagram contains a scalar internal line of mass $M$. Then

| Exchange channel | Internal momentum | Propagator denominator |
|---|---:|---:|
| $s$ channel | $p_1+p_2$ | $s-M^2+i\epsilon$ |
| $t$ channel | $p_1-p_3$ | $t-M^2+i\epsilon$ |
| $u$ channel | $p_1-p_4$ | $u-M^2+i\epsilon$ |

This is why a four-point tree amplitude in a scalar theory often looks like

$$
\mathcal M(s,t,u)
=\text{contact terms}
+\frac{\text{residue}}{s-M^2}
+\frac{\text{residue}}{t-M^2}
+\frac{\text{residue}}{u-M^2}.
$$

The poles are not decorative. They encode possible intermediate one-particle states in the corresponding channel. At loop level, thresholds also generate branch cuts in $s,t,u$.

## Common pitfalls

**Treating $s,t,u$ as independent.** At fixed external masses they obey one linear relation. A four-point amplitude may be written as $\mathcal M(s,t,u)$ for symmetry, but only two variables are independent.

**Forgetting the metric convention.** With mostly-minus signature, physical elastic $s$-channel scattering has $s>0$ and, for equal masses, $t\le0$ and $u\le0$. A mostly-plus source will write invariant squares with the opposite sign unless it has redefined the variables.

**Mixing physical and all-incoming momenta.** In physical notation $t=(p_1-p_3)^2$. In all-incoming notation it is $(q_1+q_3)^2$ because $q_3=-p_3$.

**Confusing the Mandelstam variable $u$ with a Dirac spinor $u(p,s)$.** The notation collision is standard and unfortunate. Context is the cure.

**Calling every pole an on-shell internal particle.** A propagator pole signals that the analytic amplitude has a one-particle singularity in that channel. In a generic physical region, the internal momentum in a tree diagram is usually off shell.

**Ignoring physical regions.** Crossing exchanges channel variables analytically. It is not equality of different experiments at the same real momenta.

## Relations to other pages

- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains why the same analytic amplitude has different $s$-, $t$-, and $u$-channel physical interpretations.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) explains how momentum conservation at vertices produces channel denominators.
- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) uses $s,t,u$ to write the first explicit four-point amplitudes.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) uses forward kinematics, where $t=0$ for elastic scattering.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the amplitude normalization into which these kinematic variables are inserted.

## Research status

- **Established:** The definitions, sum rule, center-of-mass formulas, and physical-region bounds on this page are standard kinematics for stable $2\to2$ scattering.
- **Convention-dependent:** Signs of invariant squares depend on metric convention, and factors of $i\epsilon$ depend on the propagator and amplitude convention.
- **More delicate:** Massless gauge theories, unstable external particles, finite-volume extraction of amplitudes, and rigorous analytic continuation require refinements beyond the elementary stable-particle formulas given here.

## Exercises

### Exercise 1: Derive the sum rule

Starting from

$$
s=(p_1+p_2)^2,
\qquad
 t=(p_1-p_3)^2,
\qquad
 u=(p_1-p_4)^2,
$$

and using $p_1+p_2=p_3+p_4$, prove that

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand each invariant:

$$
s=m_1^2+m_2^2+2p_1\cdot p_2,
$$

$$
t=m_1^2+m_3^2-2p_1\cdot p_3,
$$

$$
u=m_1^2+m_4^2-2p_1\cdot p_4.
$$

Adding gives

$$
s+t+u
=3m_1^2+m_2^2+m_3^2+m_4^2
+2p_1\cdot(p_2-p_3-p_4).
$$

Momentum conservation implies $p_2-p_3-p_4=-p_1$, so the final dot product is $-2m_1^2$. Therefore

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

</details>

### Exercise 2: Equal-mass scattering angle

For elastic scattering of four identical particles of mass $m$, show that

$$
t=-\frac{s-4m^2}{2}(1-\cos\theta),
\qquad
u=-\frac{s-4m^2}{2}(1+\cos\theta).
$$

<details>
<summary><strong>Solution</strong></summary>

In the center-of-mass frame,

$$
E=\frac{\sqrt{s}}{2},
\qquad
p^2=E^2-m^2=\frac{s}{4}-m^2.
$$

For particle $3$ scattering at angle $\theta$ relative to particle $1$,

$$
p_1\cdot p_3=E^2-p^2\cos\theta.
$$

Thus

$$
t=(p_1-p_3)^2=2m^2-2p_1\cdot p_3
=2m^2-2E^2+2p^2\cos\theta.
$$

Since $E^2=p^2+m^2$,

$$
t=-2p^2(1-\cos\theta)
=-\frac{s-4m^2}{2}(1-\cos\theta).
$$

Similarly, particle $4$ has angle $\pi-\theta$ relative to particle $1$, so the spatial dot product has the opposite sign. Hence

$$
u=-2p^2(1+\cos\theta)
=-\frac{s-4m^2}{2}(1+\cos\theta).
$$

</details>

### Exercise 3: Physical range of t

For equal-mass elastic scattering with $s\ge4m^2$, find the allowed range of $t$.

<details>
<summary><strong>Solution</strong></summary>

From Exercise 2,

$$
t=-\frac{s-4m^2}{2}(1-\cos\theta).
$$

The physical scattering angle satisfies $-1\le\cos\theta\le1$. Therefore

$$
0\le1-\cos\theta\le2.
$$

Since $s-4m^2\ge0$,

$$
-(s-4m^2)\le t\le0.
$$

Forward scattering has $\theta=0$ and $t=0$. Backward scattering has $\theta=\pi$ and $t=-(s-4m^2)$.

</details>

### Exercise 4: Channel denominators

A scalar tree diagram has an exchanged particle of mass $M$. Identify the denominator for an $s$-channel exchange and for a $t$-channel exchange in the process $1+2\to3+4$.

<details>
<summary><strong>Solution</strong></summary>

In the $s$ channel the internal momentum is the total incoming momentum,

$$
k_s=p_1+p_2,
$$

so

$$
k_s^2-M^2+i\epsilon=s-M^2+i\epsilon.
$$

In the $t$ channel the internal momentum can be taken as the momentum transfer from particle $1$ to particle $3$,

$$
k_t=p_1-p_3,
$$

so

$$
k_t^2-M^2+i\epsilon=t-M^2+i\epsilon.
$$

The corresponding scalar propagators are $i/(s-M^2+i\epsilon)$ and $i/(t-M^2+i\epsilon)$.

</details>

### Exercise 5: Massless angular form

For massless $2\to2$ scattering in the center-of-mass frame, show that

$$
\frac{t}{s}=-\frac{1-\cos\theta}{2},
\qquad
\frac{u}{s}=-\frac{1+\cos\theta}{2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Set $m=0$ in the equal-mass formulas:

$$
t=-\frac{s}{2}(1-\cos\theta),
\qquad
u=-\frac{s}{2}(1+\cos\theta).
$$

Dividing by $s$ gives the desired relations. Their sum is

$$
\frac{t+u}{s}=-1,
$$

which is equivalent to $s+t+u=0$.

</details>

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 11–12, for Mandelstam variables, crossing, phase space, and scattering applications.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for relativistic scattering kinematics, rates, cross sections, and unitarity.
- M. Srednicki, *Quantum Field Theory*, §§10–11, for scattering amplitudes, Feynman rules, cross sections, and decay rates.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5–7, for cross sections, the S-matrix, LSZ, and momentum-space Feynman rules.

## Version history

- **2026-06-12:** Initial polished draft for the Tree-Level Scattering chapter. The page fixes the qft.org Mandelstam-variable convention before explicit scalar amplitudes and phase-space formulas are introduced.
