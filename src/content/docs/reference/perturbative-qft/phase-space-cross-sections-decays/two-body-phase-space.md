---
title: "Two-Body Phase Space"
description: "A derivation and practical guide to the closed-form two-body Lorentz-invariant phase-space measure used in decays and two-body scattering."
sidebar:
  label: "Two-Body Phase Space"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11; Weinberg 1995, Vol. I, ch. 3; Coleman 2019, chs. 11–12; Schwartz 2014, ch. 5"
topics:
  - two-body phase space
  - Källén function
  - decay rates
  - scattering kinematics
  - center-of-momentum frame
canonicalTopics:
  - two-body-phase-space
  - kallen-function
  - two-body-decay-kinematics
  - center-of-momentum-phase-space
researchStatus:
  established:
    - "The two-body phase-space formula is a standard consequence of Lorentz-invariant phase space and relativistic state normalization."
  active:
    - "Finite-width effects, finite-volume spectra, massless infrared boundaries, and detector-level event definitions require extensions of the ideal stable-particle two-body formula."
---

## Summary

Two-body phase space is the simplest nontrivial final-state phase space. It is also the formula that silently powers most first scattering and decay calculations.

For a total timelike momentum $P$ with

$$
P^2=s,
\qquad
P=(\sqrt{s},\mathbf 0)
$$

in its rest frame, the two-body phase-space measure for

$$
P\to p_a+p_b,
\qquad
p_a^2=m_a^2,
\qquad
p_b^2=m_b^2,
$$

is

$$
 d\Pi_2(P;p_a,p_b)
 =
 \frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}\,d\Omega
 =
 \frac{\sqrt{\lambda(s,m_a^2,m_b^2)}}{32\pi^2s}\,d\Omega.
$$

Here $d\Omega$ is the solid-angle element of either final momentum in the $P$ rest frame, and

$$
|\mathbf p_*|
=
\frac{\sqrt{\lambda(s,m_a^2,m_b^2)}}{2\sqrt{s}},
\qquad
\lambda(x,y,z)=x^2+y^2+z^2-2xy-2xz-2yz.
$$

The integrated two-body phase space is

$$
\Phi_2(s;m_a,m_b)
\equiv
\int d\Pi_2
=
\frac{|\mathbf p_*|}{4\pi\sqrt{s}}
=
\frac{\sqrt{\lambda(s,m_a^2,m_b^2)}}{8\pi s}.
$$

For two massless final particles, $d\Pi_2=d\Omega/(32\pi^2)$ and $\Phi_2=1/(8\pi)$.

<figure class="doc-figure" style="--figure-width: 51rem; --caption-width: 53rem;">

![Two-body phase space in the rest frame of the total momentum, with equal and opposite final momenta on a sphere of fixed radius](/figures/perturbative-qft/two-body-phase-space.svg)

<figcaption>

In the rest frame of $P$, the spatial delta function fixes $\mathbf p_b=-\mathbf p_a$, while the energy delta function fixes the magnitude $|\mathbf p_a|=|\mathbf p_*|$. The only continuous freedom left is the direction $\hat{\mathbf n}$, measured by $d\Omega$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/).

## Core idea

The $n$-body phase-space measure usually looks intimidating because it contains many momentum integrals and one four-dimensional delta function. For $n=2$, those constraints almost completely solve the kinematics.

In the rest frame of $P$:

1. momentum conservation forces the two final three-momenta to be equal and opposite;
2. energy conservation fixes their common magnitude;
3. rotational invariance leaves only a direction on a sphere.

That is why the answer is proportional to $d\Omega$. The factor multiplying $d\Omega$ is the Jacobian from the energy delta function. It is the place where most wrong factors of $2$, $\pi$, and $\sqrt{s}$ enter.

## Setup and conventions

We use the qft.org mostly-minus metric and relativistic state normalization. The general two-body phase-space measure is

$$
 d\Pi_2(P;p_a,p_b)
=
(2\pi)^4\delta^{(4)}(P-p_a-p_b)
\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}
\frac{d^3\mathbf p_b}{(2\pi)^3 2E_b}.
$$

The energies are positive on-shell energies,

$$
E_a=\sqrt{\mathbf p_a^2+m_a^2},
\qquad
E_b=\sqrt{\mathbf p_b^2+m_b^2}.
$$

The total momentum is timelike,

$$
P^2=s,
\qquad
\sqrt{s}\ge m_a+m_b,
$$

so there is a rest frame of $P$. The formula below is written in that frame. The measure itself is Lorentz invariant, but $d\Omega$ and $|\mathbf p_*|$ are coordinates adapted to the center-of-momentum frame.

## Rest-frame kinematics

In the $P$ rest frame,

$$
P^\mu=(\sqrt{s},\mathbf 0).
$$

The spatial delta function in $d\Pi_2$ sets

$$
\mathbf p_b=-\mathbf p_a.
$$

Write

$$
\mathbf p_a=\mathbf p_* = |\mathbf p_*|\hat{\mathbf n},
\qquad
\mathbf p_b=-\mathbf p_*.
$$

The two final energies at the physical point are

$$
E_a^*=
\frac{s+m_a^2-m_b^2}{2\sqrt{s}},
\qquad
E_b^*=
\frac{s+m_b^2-m_a^2}{2\sqrt{s}}.
$$

Their common momentum magnitude is

$$
|\mathbf p_*|^2
=
\frac{\lambda(s,m_a^2,m_b^2)}{4s}.
$$

The Källén function factorizes as

$$
\lambda(s,m_a^2,m_b^2)
=
\big[s-(m_a+m_b)^2\big]
\big[s-(m_a-m_b)^2\big].
$$

This factorization makes the physical threshold visible. At threshold, $\sqrt{s}=m_a+m_b$, the available momentum vanishes.

## Derivation of the measure

Start from

$$
 d\Pi_2
=(2\pi)^4\delta^{(4)}(P-p_a-p_b)
\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}
\frac{d^3\mathbf p_b}{(2\pi)^3 2E_b}.
$$

In the rest frame of $P$, the spatial delta function removes the $\mathbf p_b$ integral:

$$
 d\Pi_2
=
\frac{1}{(2\pi)^2}
\frac{d^3\mathbf p}{4E_aE_b}
\delta(\sqrt{s}-E_a(\mathbf p)-E_b(\mathbf p)),
$$

where $\mathbf p\equiv\mathbf p_a$ and $\mathbf p_b=-\mathbf p$. Writing $p=|\mathbf p|$ and $d^3\mathbf p=p^2dp\,d\Omega$, this becomes

$$
 d\Pi_2
=
\frac{1}{16\pi^2}
\frac{p^2dp\,d\Omega}{E_aE_b}
\delta(\sqrt{s}-E_a(p)-E_b(p)).
$$

The delta function fixes $p=|\mathbf p_*|$. The needed Jacobian is

$$
\frac{d}{dp}\big(E_a(p)+E_b(p)\big)
=
\frac{p}{E_a}+\frac{p}{E_b}
=
\frac{p(E_a+E_b)}{E_aE_b}.
$$

At the root, $E_a+E_b=\sqrt{s}$, so

$$
\left|\frac{d}{dp}\big(\sqrt{s}-E_a(p)-E_b(p)\big)\right|_{p=|\mathbf p_*|}
=
\frac{|\mathbf p_*|\sqrt{s}}{E_a^*E_b^*}.
$$

Therefore

$$
\begin{aligned}
 d\Pi_2
&=
\frac{1}{16\pi^2}
\frac{|\mathbf p_*|^2d\Omega}{E_a^*E_b^*}
\frac{E_a^*E_b^*}{|\mathbf p_*|\sqrt{s}} \\
&=
\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}\,d\Omega.
\end{aligned}
$$

Substituting $|\mathbf p_*|=\sqrt{\lambda(s,m_a^2,m_b^2)}/(2\sqrt{s})$ gives

$$
 d\Pi_2
=
\frac{\sqrt{\lambda(s,m_a^2,m_b^2)}}{32\pi^2s}\,d\Omega.
$$

## Integrated two-body phase space

If the squared amplitude is independent of angle, or if one only needs the total kinematic phase-space volume, integrate over the full solid angle:

$$
\int d\Omega=4\pi.
$$

Then

$$
\Phi_2(s;m_a,m_b)
=
\int d\Pi_2
=
\frac{|\mathbf p_*|}{4\pi\sqrt{s}}
=
\frac{\sqrt{\lambda(s,m_a^2,m_b^2)}}{8\pi s}.
$$

Two special cases are worth memorizing.

For massless final particles,

$$
m_a=m_b=0,
\qquad
|\mathbf p_*|=\frac{\sqrt{s}}{2},
$$

so

$$
 d\Pi_2=\frac{1}{32\pi^2}d\Omega,
\qquad
\Phi_2=\frac{1}{8\pi}.
$$

For equal final masses $m_a=m_b=m$, define

$$
\beta_f=\sqrt{1-\frac{4m^2}{s}}.
$$

Then

$$
 d\Pi_2=\frac{\beta_f}{32\pi^2}d\Omega,
\qquad
\Phi_2=\frac{\beta_f}{8\pi}.
$$

The factor $\beta_f$ is a kinematic threshold suppression. It does not know anything about the interaction.

## Two-body decays

For a decay

$$
A(P)\to a(p_a)+b(p_b),
\qquad
P^2=M_A^2,
$$

the differential decay rate in the rest frame of $A$ is

$$
 d\Gamma
=
\frac{1}{2M_A}
\overline{|\mathcal M|^2}
 d\Pi_2(P;p_a,p_b).
$$

Using the two-body measure with $s=M_A^2$ gives

$$
\frac{d\Gamma}{d\Omega}
=
\frac{|\mathbf p_*|}{32\pi^2M_A^2}
\overline{|\mathcal M|^2}.
$$

If $\overline{|\mathcal M|^2}$ is angle independent and the final particles are distinguishable, then

$$
\Gamma
=
\frac{|\mathbf p_*|}{8\pi M_A^2}
\overline{|\mathcal M|^2}.
$$

If the two final particles are identical and the integration covers the full labeled sphere, include an additional factor $1/2!$:

$$
\Gamma_{A\to aa}
=
\frac{1}{2!}
\frac{|\mathbf p_*|}{8\pi M_A^2}
\overline{|\mathcal M|^2}
$$

for an angle-independent amplitude.

## Two-body final states in scattering

For a scattering process

$$
1(p_1)+2(p_2)\to a(p_a)+b(p_b),
$$

the same two-body phase space appears with

$$
P=p_1+p_2,
\qquad
s=P^2.
$$

The incoming flux factor is separate from final-state phase space:

$$
 d\sigma
=
\frac{1}{F_{12}}\overline{|\mathcal M|^2}d\Pi_2(P;p_a,p_b).
$$

In the center-of-momentum frame, this becomes

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2},
$$

where $|\mathbf p_f^*|$ is the two-body momentum of the final pair and $|\mathbf p_i^*|$ comes from the initial-state flux. The derivation and use of this formula are the subject of [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/).

## Angular variables and invariant variables

The expression

$$
 d\Pi_2=\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}d\Omega
$$

is a coordinate expression on an invariant measure. The angle $\Omega$ is defined in the rest frame of $P$.

For $2\to2$ scattering, it is often useful to trade the polar angle for the Mandelstam variable $t$. With incoming momentum magnitude $|\mathbf p_i^*|$ and final momentum magnitude $|\mathbf p_f^*|$,

$$
t=m_1^2+m_a^2-2E_1^*E_a^*
+2|\mathbf p_i^*||\mathbf p_f^*|\cos\theta.
$$

Therefore

$$
\frac{dt}{d\cos\theta}=2|\mathbf p_i^*||\mathbf p_f^*|.
$$

This identity is what converts $d\sigma/d\Omega$ into $d\sigma/dt$ on the next page.

## Threshold behavior

Near threshold,

$$
\sqrt{s}\to m_a+m_b,
$$

the final momentum behaves as

$$
|\mathbf p_*|
\propto
\sqrt{\sqrt{s}-(m_a+m_b)}.
$$

Thus ordinary two-body phase space closes with a square-root law. In many reactions, the amplitude itself also has angular-momentum suppression near threshold. For example, a final state in orbital angular momentum $\ell$ often has an additional factor $|\mathbf p_*|^{2\ell}$ in $|\mathcal M|^2$, making the rate scale as

$$
\Gamma_\ell\sim |\mathbf p_*|^{2\ell+1}
$$

near threshold. The $+1$ comes from phase space; the $2\ell$ comes from dynamics and angular momentum.

## Common pitfalls

**Using $d\Omega$ without naming the frame.** The compact two-body formula uses the solid angle in the rest frame of the total momentum $P$. The phase-space measure is invariant, but $d\Omega$ is a frame-specific coordinate.

**Forgetting the energy-delta-function Jacobian.** After the spatial delta function sets $\mathbf p_b=-\mathbf p_a$, the remaining delta function is $\delta(\sqrt{s}-E_a-E_b)$. Its derivative produces the factor $E_aE_b/(|\mathbf p_*|\sqrt{s})$.

**Confusing threshold suppression with dynamics.** The factor $|\mathbf p_*|$ in $d\Pi_2$ is kinematic. Spin, parity, selection rules, and resonances enter through $\mathcal M$.

**Counting identical final particles twice.** The measure $d\Pi_2(P;p_a,p_b)$ treats the two final momenta as labeled. If $a$ and $b$ are identical and the integration covers both labelings, divide the final-state integral by $2!$.

**Using the massless formula with massive particles.** The famous $d\Pi_2=d\Omega/(32\pi^2)$ assumes both final masses vanish. Massive final states carry the factor $\sqrt{\lambda}/s$.

## Relations to other pages

- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) derives the general $n$-body measure that this page specializes to $n=2$.
- [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/) supplies the initial-state denominator needed to turn two-body phase space into a scattering cross section.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) combines this page with the flux factor to obtain $d\sigma/d\Omega$ and $d\sigma/dt$.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) explains the invariant variables $s$, $t$, and $u$ used to parametrize two-body scattering.
- [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) explains when to divide phase space by final-state factorials and when to add exchange amplitudes before squaring.

## Research status

The two-body formula on this page is textbook-standard for stable asymptotic particles in infinite-volume relativistic QFT. Its convention dependence is limited to the overall state and amplitude normalization; the physical decay rates and cross sections are unchanged under consistent convention changes.

The main extensions appear when one or both final particles are unstable, when finite-volume spectra replace continuum phase space, when massless particles produce soft or collinear boundaries, or when detector-level observables require cuts and inclusive sums. Those refinements build on the stable two-body formula rather than changing its basic kinematic content.

## Exercises

### Exercise 1: Energies in the two-body rest frame

Derive

$$
E_a^*=
\frac{s+m_a^2-m_b^2}{2\sqrt{s}},
\qquad
E_b^*=
\frac{s+m_b^2-m_a^2}{2\sqrt{s}}.
$$

<details>
<summary><strong>Solution</strong></summary>

In the rest frame of $P$,

$$
E_a^*+E_b^*=\sqrt{s}.
$$

Also

$$
P-p_a=p_b,
$$

so

$$
(P-p_a)^2=m_b^2.
$$

Expanding gives

$$
P^2+p_a^2-2P\cdot p_a=m_b^2.
$$

Using $P^2=s$, $p_a^2=m_a^2$, and $P\cdot p_a=\sqrt{s}E_a^*$ gives

$$
s+m_a^2-2\sqrt{s}E_a^*=m_b^2.
$$

Therefore

$$
E_a^*=\frac{s+m_a^2-m_b^2}{2\sqrt{s}}.
$$

The expression for $E_b^*$ follows by exchanging $a\leftrightarrow b$.

</details>

### Exercise 2: Momentum from the Källén function

Show that

$$
|\mathbf p_*|^2=\frac{\lambda(s,m_a^2,m_b^2)}{4s}.
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
|\mathbf p_*|^2=(E_a^*)^2-m_a^2
$$

and substitute

$$
E_a^*=\frac{s+m_a^2-m_b^2}{2\sqrt{s}}.
$$

Then

$$
|\mathbf p_*|^2
=
\frac{(s+m_a^2-m_b^2)^2}{4s}-m_a^2.
$$

Putting this over a common denominator gives

$$
|\mathbf p_*|^2
=
\frac{s^2+m_a^4+m_b^4-2sm_a^2-2sm_b^2-2m_a^2m_b^2}{4s}
=
\frac{\lambda(s,m_a^2,m_b^2)}{4s}.
$$

</details>

### Exercise 3: Integrated massless phase space

For $m_a=m_b=0$, show that

$$
\int d\Pi_2=\frac{1}{8\pi}.
$$

<details>
<summary><strong>Solution</strong></summary>

For massless final particles,

$$
|\mathbf p_*|=\frac{\sqrt{s}}{2}.
$$

Thus

$$
 d\Pi_2
=
\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}d\Omega
=
\frac{1}{32\pi^2}d\Omega.
$$

Integrating over the full sphere,

$$
\int d\Pi_2
=
\frac{1}{32\pi^2}\int d\Omega
=
\frac{4\pi}{32\pi^2}
=
\frac{1}{8\pi}.
$$

</details>

### Exercise 4: Constant-amplitude two-body decay

A scalar particle of mass $M$ decays to two distinguishable scalars with an angle-independent amplitude $\mathcal M=g$. Derive the total decay rate.

<details>
<summary><strong>Solution</strong></summary>

The decay formula is

$$
 d\Gamma=\frac{1}{2M}|\mathcal M|^2d\Pi_2.
$$

For an angle-independent amplitude and distinguishable final particles,

$$
\Gamma
=\frac{1}{2M}|g|^2\int d\Pi_2
=\frac{1}{2M}|g|^2\frac{|\mathbf p_*|}{4\pi M}.
$$

Therefore

$$
\Gamma
=\frac{|\mathbf p_*|}{8\pi M^2}|g|^2.
$$

If the two final scalars are identical and the full labeled phase space is integrated, multiply by $1/2!$.

</details>

### Exercise 5: Equal-mass threshold behavior

For $m_a=m_b=m$, show that

$$
\Phi_2=\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{s}}.
$$

What happens as $s\to4m^2$ from above?

<details>
<summary><strong>Solution</strong></summary>

For equal masses,

$$
\lambda(s,m^2,m^2)=s^2-4sm^2=s^2\left(1-\frac{4m^2}{s}\right).
$$

Therefore

$$
\Phi_2
=\frac{\sqrt{\lambda(s,m^2,m^2)}}{8\pi s}
=\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{s}}.
$$

As $s\to4m^2$ from above, the square root vanishes. The two-particle final state closes at threshold.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§10–11, for amplitudes, phase space, decay rates, and cross sections.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering theory, Lorentz-invariant phase space, rates, and cross sections.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 11–12, for Mandelstam variables, phase space, decays, and differential cross sections.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 5, for a practical treatment of phase space, cross sections, and decay rates.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 4–5, for standard perturbative-QFT applications of two-body phase space.

## Version history

- **2026-06-12:** Initial polished draft for qft.org. Derives the two-body phase-space measure, integrated formulas, decay-rate specialization, threshold behavior, and relation to $2\to2$ scattering in qft.org conventions.
