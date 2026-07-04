---
title: "False-Vacuum Decay"
description: "Explains the semiclassical bounce calculation of metastable vacuum decay, including the Euclidean bounce equation, negative mode, determinant factor, and thin-wall limit."
sidebar:
  label: "False-Vacuum Decay"
  order: 7
level: Graduate
status: "Polished draft"
source: "Coleman; Callan–Coleman; Weinberg; Zinn-Justin; Mariño; Shifman."
topics:
  - false-vacuum decay
  - bounce solutions
  - metastability
  - negative modes
  - semiclassical approximation
  - thin-wall approximation
  - vacuum decay rate
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - false-vacuum-decay
  - bounce-saddles
researchStatus:
  established:
    - "The leading semiclassical decay rate of a metastable vacuum is controlled by a Euclidean bounce saddle with one negative fluctuation mode."
  active:
    - "Gauge dependence of effective-potential calculations, gravitational corrections, multifield tunneling, thermal transitions, and real-time nonequilibrium decay remain subtle and often model-dependent."
---

## Summary

A **false vacuum** is a local minimum of the quantum effective energy landscape that is not the true ground state. It can be long-lived, but it is not stable. Quantum mechanically it decays by nucleating a bubble of the lower-energy phase. The semiclassical calculation of this decay is controlled by a Euclidean saddle called a **bounce**.

For a metastable vacuum in $D$ Euclidean spacetime dimensions, the leading decay rate per spatial volume has the schematic form

$$
\frac{\Gamma}{V_{D-1}}
=
A e^{-B/\hbar}
\left(1+O(\hbar)\right),
$$

where

$$
B=S_E[\phi_b]-S_E[\phi_f]
$$

is the difference between the Euclidean action of the bounce $\phi_b$ and the homogeneous false-vacuum configuration $\phi_f$. The prefactor $A$ contains determinant ratios, zero-mode Jacobians, renormalization, and the treatment of one negative fluctuation mode.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic false-vacuum decay calculation: a tilted double-well potential leads to a Euclidean bounce bubble whose action is a competition between wall tension and volume energy gain.](/figures/nonperturbative-qft/false-vacuum-decay-bounce.svg)

<figcaption>

False-vacuum decay is controlled by a Euclidean critical bubble. The bounce action is a competition between wall cost and volume gain. In the thin-wall limit, $B(R)=\Omega_{D-1}\sigma R^{D-1}-(\Omega_{D-1}/D)\epsilon R^D$, so the critical radius is $R_\ast=(D-1)\sigma/\epsilon$.

</figcaption>
</figure>

The bounce is the canonical example where a saddle-point expansion does not compute a real correction to the vacuum energy. Because the fluctuation operator has one negative mode, the contour prescription produces an imaginary part of the false-vacuum energy. That imaginary part is the decay rate. This is where “a negative eigenvalue” stops being a nuisance and becomes the physics.

## Prerequisites

You should know [False Vacua and Metastability](/nonperturbative-qft/vacuum-structure-phases/false-vacua-and-metastability/) for the phase-structure interpretation, and [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), and [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/) for the semiclassical machinery.

It is also useful to know [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/), because the phrase “potential barrier” can mean different things depending on whether one is using a classical potential, a perturbative effective potential, or the exact convex effective potential.

## Core idea

A metastable state is not an eigenstate of the full Hamiltonian. It is a long-lived resonance. Its survival probability behaves approximately as

$$
P(t)\approx e^{-\Gamma t}
$$

for times long compared with microscopic relaxation scales but short compared with any ultimate finite-volume recurrence time. In Euclidean language, the decay appears as an imaginary part of the false-vacuum energy density:

$$
\Gamma
=
-2\,\operatorname{Im}E_f
$$

for a single metastable state, or

$$
\frac{\Gamma}{V_{D-1}}
=
2\,\operatorname{Im}\mathcal E_f
$$

up to the sign convention used for $\operatorname{Im}\mathcal E_f$.

The bounce is a Euclidean solution that starts near the false vacuum, makes an excursion toward the true-vacuum side, and returns to the false vacuum. In field theory, it is a finite-size bubble in Euclidean spacetime. After analytic continuation back to Lorentzian time, the bubble expands.

The shortest conceptual chain is

$$
\text{local minimum}
\rightarrow
\text{Euclidean bounce}
\rightarrow
\text{one negative mode}
\rightarrow
\operatorname{Im}E_f
\rightarrow
\text{decay rate}.
$$

## Setup and conventions

Consider one real scalar field in $D$ Euclidean spacetime dimensions with action

$$
S_E[\phi]
=
\int d^Dx\left[
\frac12(\partial_\mu\phi)(\partial_\mu\phi)+V(\phi)
\right].
$$

The symbol $\partial_\mu\phi\partial_\mu\phi$ means contraction with the Euclidean metric. We assume the potential has a false vacuum $\phi_f$ and a true vacuum $\phi_t$, with

$$
V(\phi_f)>V(\phi_t).
$$

It is convenient to subtract a constant so that

$$
V(\phi_f)=0,
\qquad
V(\phi_t)<0.
$$

This constant does not change the equations of motion. It only makes the action difference easy to read.

The bounce $\phi_b$ is a nontrivial stationary point of $S_E$ satisfying

$$
-\partial^2\phi_b+V'(\phi_b)=0,
$$

with boundary condition

$$
\phi_b(x)\to\phi_f
\quad
\text{as } |x|\to\infty.
$$

For a single scalar field with canonical kinetic term and no explicit spacetime dependence, the dominant bounce is usually $O(D)$-symmetric. Then $\phi_b(x)=\phi_b(r)$ with

$$
r=\sqrt{x_\mu x_\mu},
$$

and the bounce equation becomes

$$
\frac{d^2\phi}{dr^2}
+
\frac{D-1}{r}\frac{d\phi}{dr}
=
V'(\phi).
$$

The boundary conditions are

$$
\left.\frac{d\phi}{dr}\right|_{r=0}=0,
\qquad
\phi(r\to\infty)=\phi_f.
$$

The first condition avoids a cusp at the center. The second ensures finite action relative to the false vacuum.

## Mechanical analogy

The radial bounce equation can be read as a particle moving in the inverted potential $-V(\phi)$ with a time-dependent friction term:

$$
\ddot\phi+
\frac{D-1}{r}\dot\phi
=V'(\phi).
$$

Here $r$ plays the role of time. The particle starts at rest near the true-vacuum side and rolls in the inverted potential, losing energy to friction, eventually approaching the false vacuum as $r\to\infty$.

This analogy is useful for existence arguments. If the initial value is too close to the true vacuum, friction prevents the particle from reaching the false vacuum. If it starts too far over the barrier, it overshoots. A bounce corresponds to the boundary between undershoot and overshoot.

The analogy should not be pushed too far. The physical tunneling process is not a classical particle rolling in real time. The rolling picture is a way to solve the Euclidean boundary-value problem.

## The bounce action

The quantity controlling the leading exponential is

$$
B=S_E[\phi_b]-S_E[\phi_f].
$$

With $V(\phi_f)=0$ and the false vacuum homogeneous, $S_E[\phi_f]=0$ relative to the false vacuum, so

$$
B=S_E[\phi_b].
$$

For an $O(D)$-symmetric bounce,

$$
B
=
\Omega_{D-1}
\int_0^\infty dr\,r^{D-1}
\left[
\frac12\left(\frac{d\phi}{dr}\right)^2
+V(\phi)
\right],
$$

where

$$
\Omega_{D-1}=\frac{2\pi^{D/2}}{\Gamma(D/2)}
$$

is the area of the unit $(D-1)$-sphere.

The leading decay rate is exponentially small when

$$
B/\hbar\gg1.
$$

This is the bounce version of semiclassical control.

## Why a negative mode is required

The bounce is not a local minimum of the Euclidean action. It is a saddle with one negative mode. Physically, that mode changes the bubble radius. If the bubble is slightly smaller than the critical size, wall tension wins and it collapses. If it is slightly larger, volume energy wins and it expands. The critical bubble sits at the top of this one-dimensional instability.

Mathematically, expand around the bounce:

$$
\phi=\phi_b+\eta.
$$

The quadratic operator is

$$
\Delta_b
=
-\partial^2+V''(\phi_b).
$$

Its spectrum contains:

| Mode type | Origin | Treatment |
|---|---|---|
| one negative mode | instability of the critical bubble radius | contour gives imaginary part |
| $D$ zero modes | translations of the bounce center in Euclidean spacetime | collective-coordinate integral |
| positive modes | ordinary fluctuations | determinant factor |

If there were no negative mode, the saddle would produce a real correction to the false-vacuum energy, not a decay rate. If there were more than one negative mode, the saddle would usually not be the leading tunneling saddle for a single decay channel.

## The prefactor

The leading exponential is robust; the prefactor is more technical. Schematically,

$$
\frac{\Gamma}{V_{D-1}}
\simeq
\mathcal C
\left(\frac{B}{2\pi\hbar}\right)^{D/2}
\left|
\frac{\det{}'\Delta_b}{\det\Delta_f}
\right|^{-1/2}
 e^{-B/\hbar}.
$$

Here

$$
\Delta_f=-\partial^2+V''(\phi_f)
$$

is the fluctuation operator in the false vacuum. The prime removes the $D$ translational zero modes and the single negative mode from the determinant. The factor $(B/2\pi\hbar)^{D/2}$ is the translational collective-coordinate Jacobian in the simplest single-field normalization. The constant $\mathcal C$ includes the conventional factor arising from the negative-mode contour and from converting the total Euclidean spacetime volume factor into a decay rate per spatial volume.

For most conceptual uses, the essential formula is

$$
\frac{\Gamma}{V_{D-1}}=A e^{-B/\hbar}.
$$

The page-worthy warning is that $A$ is not just decoration. In precision applications, such as electroweak vacuum metastability or nucleation in finite-temperature field theory, the prefactor, renormalization scale, gauge dependence, and loop-improved effective action can matter.

## Multi-bounce exponentiation

A single bounce gives the elementary decay event. The full decay law comes from summing over any number of well-separated bounces, just as in the [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/).

If the one-bounce contribution to the false-vacuum amplitude is proportional to

$$
i K \,\mathcal V_D e^{-B/\hbar},
$$

where the factor of $i$ comes from the negative mode, then the $N$-bounce contribution is approximately

$$
\frac{1}{N!}
\left(i K\mathcal V_D e^{-B/\hbar}\right)^N.
$$

Summing over $N$ exponentiates:

$$
\sum_{N=0}^{\infty}
\frac{1}{N!}
\left(i K\mathcal V_D e^{-B/\hbar}\right)^N
=
\exp\left(iK\mathcal V_D e^{-B/\hbar}\right).
$$

The imaginary contribution to the false-vacuum energy density is then proportional to $K e^{-B/\hbar}$, which gives the decay rate. This is why the bounce calculation is both a saddle-point problem and a dilute-gas problem.

## Thin-wall approximation

The thin-wall approximation applies when the false and true vacua are nearly degenerate. Let

$$
\epsilon=V(\phi_f)-V(\phi_t)>0
$$

be small compared with the barrier height. The bubble wall is then thin compared with its radius. Let $\sigma$ be the wall tension computed in the nearly degenerate potential. The bounce action as a function of bubble radius is approximated by

$$
B(R)
=
\underbrace{\Omega_{D-1}\sigma R^{D-1}}_{\text{wall cost}}
-
\underbrace{\frac{\Omega_{D-1}}{D}\epsilon R^D}_{\text{volume gain}}.
$$

Extremizing gives

$$
\frac{dB}{dR}=0
\quad\Longrightarrow\quad
R_\ast=\frac{(D-1)\sigma}{\epsilon}.
$$

At the critical radius,

$$
B_{\text{tw}}
=
\frac{\Omega_{D-1}}{D}
(D-1)^{D-1}
\frac{\sigma^D}{\epsilon^{D-1}}.
$$

In four Euclidean dimensions,

$$
D=4,
\qquad
\Omega_3=2\pi^2,
$$

so

$$
B_{\text{tw}}
=
\frac{27\pi^2\sigma^4}{2\epsilon^3}.
$$

This formula is famous because it cleanly displays the physics: as the vacua become degenerate, $\epsilon\to0$, the critical bubble becomes large and the decay is exponentially suppressed.

## From Euclidean bubble to Lorentzian expansion

The Euclidean bounce is a sphere in $D$ Euclidean dimensions. To obtain the Lorentzian interpretation, slice the bounce at its time-reflection-symmetric surface and continue Euclidean time to real time. The critical bubble appears at rest at the nucleation time. Then it expands because the lower-energy interior gains volume energy while the wall cost grows more slowly.

In $3+1$ Lorentzian dimensions, the Euclidean bounce is approximately an $S^3$ wall in four-dimensional Euclidean spacetime. The nucleated bubble wall is an $S^2$ in ordinary space. This is one of the easiest places to accidentally confuse Euclidean dimension with spatial dimension, so keep the notation straight:

$$
D=\text{Euclidean spacetime dimension},
\qquad
D-1=\text{Lorentzian spatial dimension}.
$$

## Gauge theories and effective potentials

Many practical vacuum-decay calculations use an effective potential rather than a tree-level potential. This introduces subtleties.

The exact effective potential is convex and does not literally show a barrier in the naive way. Perturbative or coarse-grained effective potentials can display a useful barrier, but they may depend on gauge and renormalization scheme. A physical decay rate cannot depend on gauge choice, but intermediate quantities such as $\phi_b(r)$, $V_{\text{eff}}(\phi)$, and even pieces of $A$ can.

The safe statement is:

$$
\text{The decay rate is physical; the field-space picture used to compute it may be gauge- and scheme-dependent.}
$$

For this introductory page, we treat the single-scalar problem as the clean model. Gauge fields, gravity, finite temperature, and multifield tunneling require additional pages.

## Finite temperature

At finite temperature, Euclidean time is compact with period

$$
\beta=1/T.
$$

If the bounce radius is large compared with $\beta$, the dominant configuration may become approximately independent of Euclidean time. In $3+1$ dimensions, the leading thermal transition is then controlled by a three-dimensional $O(3)$ saddle, often written as a sphaleron-like or thermal-bounce contribution:

$$
\Gamma/V
\sim
A_T e^{-S_3/T}.
$$

This is conceptually related to false-vacuum decay, but it is not the same as the zero-temperature $O(4)$ bounce. The crossover between quantum tunneling and thermal activation is an important topic in finite-temperature field theory.

## Common pitfalls

**Calling the false vacuum a stable vacuum.** A false vacuum is at best metastable. In infinite volume, the total decay probability eventually becomes large even when the decay rate per unit volume is tiny.

**Forgetting the negative mode.** The bounce is not just another instanton contributing to $Z$. Its single negative mode is what turns the saddle contribution into an imaginary energy and hence a decay rate.

**Confusing the bounce with the expanding bubble.** The bounce is Euclidean. The expanding bubble is the Lorentzian continuation of a time-symmetric slice of the bounce.

**Using the exact convex effective potential as a literal tunneling barrier.** Bounce calculations often use a classical, perturbative, or coarse-grained potential. One must know which object is being used.

**Mixing up dimensions.** A zero-temperature decay in $3+1$ Lorentzian dimensions uses a four-dimensional Euclidean bounce. The wall is an $S^3$ in Euclidean spacetime but an $S^2$ bubble wall at nucleation in space.

**Overtrusting the thin-wall formula.** The thin-wall approximation requires small energy splitting relative to the barrier. Away from that limit, one must solve the bounce equation directly.

## Limitations and caveats

The bounce method is a controlled semiclassical method when $B/\hbar\gg1$ and the fluctuation analysis is under control. It does not by itself prove that a given field theory is nonperturbatively well-defined. It assumes a Euclidean formulation, a metastable state, and a meaningful saddle-point approximation.

Multifield potentials can have tunneling paths that are not obvious from one-dimensional intuition. Gravity changes the problem dramatically: the Coleman–De Luccia bounce includes the metric, and the existence or interpretation of decay can depend on spacetime boundary conditions. Real-time nonequilibrium decay, strong fields, and finite density introduce additional obstacles.

For gauge theories, the semiclassical exponent is physical, but naive potential plots can be misleading. A robust calculation must track gauge dependence, renormalization, and the derivative expansion.

## Research status

- **Established:** In ordinary quantum mechanics and weakly coupled scalar field theory, false-vacuum decay is controlled by a Euclidean bounce with one negative mode.
- **Established:** In the thin-wall regime, the critical radius and leading bounce action follow from wall-cost versus volume-gain competition.
- **Established:** The multi-bounce dilute-gas sum exponentiates and produces an imaginary false-vacuum energy, interpreted as a decay rate.
- **Active:** Gauge-invariant formulations of perturbative vacuum-decay calculations, multifield tunneling algorithms, gravitational decay, thermal transitions, and real-time nucleation remain active technical areas.
- **Model-dependent:** Claims about the metastability of a specific fundamental vacuum require the full theory, its cutoff or UV completion, gravitational assumptions, and properly matched effective action.

## Relations to other pages

- [False Vacua and Metastability](/nonperturbative-qft/vacuum-structure-phases/false-vacua-and-metastability/) gives the phase-structure interpretation.
- [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/) explains why $e^{-B/\hbar}$ is a saddle contribution.
- [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/) explains the determinant ratio in the prefactor.
- [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) explains translational zero modes and the special role of negative modes.
- [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/) explains the multi-bounce exponentiation.
- Later finite-temperature pages will revisit thermal activation and sphaleron-like rates.

## Exercises

### Exercise 1: Thin-wall critical radius

Starting from

$$
B(R)=\Omega_{D-1}\sigma R^{D-1}
-\frac{\Omega_{D-1}}{D}\epsilon R^D,
$$

show that the critical radius is

$$
R_\ast=\frac{(D-1)\sigma}{\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dB}{dR}
=
\Omega_{D-1}(D-1)\sigma R^{D-2}
-\Omega_{D-1}\epsilon R^{D-1}.
$$

For a nonzero-radius extremum,

$$
(D-1)\sigma-\epsilon R=0.
$$

Therefore

$$
R_\ast=\frac{(D-1)\sigma}{\epsilon}.
$$

</details>

### Exercise 2: Thin-wall action

Using the result of Exercise 1, show that

$$
B_{\text{tw}}
=
\frac{\Omega_{D-1}}{D}
(D-1)^{D-1}
\frac{\sigma^D}{\epsilon^{D-1}}.
$$

<details>
<summary><strong>Solution</strong></summary>

At the extremum,

$$
\epsilon R_\ast=(D-1)\sigma.
$$

Substitute this into

$$
B(R_\ast)=\Omega_{D-1}\sigma R_\ast^{D-1}
-\frac{\Omega_{D-1}}{D}\epsilon R_\ast^D.
$$

The second term becomes

$$
\frac{\Omega_{D-1}}{D}\epsilon R_\ast^D
=
\frac{\Omega_{D-1}}{D}(D-1)\sigma R_\ast^{D-1}.
$$

Thus

$$
B(R_\ast)
=\Omega_{D-1}\sigma R_\ast^{D-1}
\left(1-\frac{D-1}{D}\right)
=\frac{\Omega_{D-1}}{D}\sigma R_\ast^{D-1}.
$$

Now insert

$$
R_\ast=\frac{(D-1)\sigma}{\epsilon}.
$$

This gives

$$
B_{\text{tw}}
=
\frac{\Omega_{D-1}}{D}
(D-1)^{D-1}
\frac{\sigma^D}{\epsilon^{D-1}}.
$$

</details>

### Exercise 3: Why the bounce has a negative mode

Use the thin-wall action $B(R)$ to show that the critical bubble is unstable under changing $R$.

<details>
<summary><strong>Solution</strong></summary>

Compute the second derivative:

$$
\frac{d^2B}{dR^2}
=
\Omega_{D-1}(D-1)(D-2)\sigma R^{D-3}
-\Omega_{D-1}(D-1)\epsilon R^{D-2}.
$$

At $R=R_\ast$, use $\epsilon R_\ast=(D-1)\sigma$:

$$
\left.\frac{d^2B}{dR^2}\right|_{R_\ast}
=
\Omega_{D-1}(D-1)\sigma R_\ast^{D-3}
\left[(D-2)-(D-1)\right]
<0.
$$

Thus the critical bubble is a maximum along the radius direction. This is the thin-wall version of the bounce's one negative mode.

</details>

### Exercise 4: Four-dimensional thin-wall exponent

Set $D=4$ and $\Omega_3=2\pi^2$ in the general thin-wall formula. Show that

$$
B_{\text{tw}}=\frac{27\pi^2\sigma^4}{2\epsilon^3}.
$$

<details>
<summary><strong>Solution</strong></summary>

The formula gives

$$
B_{\text{tw}}
=
\frac{\Omega_3}{4}3^3\frac{\sigma^4}{\epsilon^3}.
$$

Since $\Omega_3=2\pi^2$,

$$
B_{\text{tw}}
=\frac{2\pi^2}{4}27\frac{\sigma^4}{\epsilon^3}
=\frac{27\pi^2\sigma^4}{2\epsilon^3}.
$$

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially “The Fate of the False Vacuum.”
- C. Callan and S. Coleman, “Fate of the False Vacuum II,” for the one-loop prefactor and negative-mode treatment.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, section on vacuum decay.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean saddle methods and metastability.
- M. Mariño, *Instantons and Large N*, for instantons in unstable vacua and thin-wall methods.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter on false-vacuum decay and related applications.

## Version history

- **2026-06-26:** Initial polished page.
