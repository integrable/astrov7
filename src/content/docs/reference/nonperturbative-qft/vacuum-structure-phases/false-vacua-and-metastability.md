---
title: "False Vacua and Metastability"
description: "Explains false vacua, metastable phases, bubble nucleation, bounce actions, and the limits of semiclassical vacuum-decay estimates."
sidebar:
  label: "False Vacua"
  order: 10
level: Graduate
status: "Polished draft"
source: "Coleman; Callan–Coleman; Coleman–De Luccia; Shifman; Mariño."
topics:
  - false vacuum
  - metastability
  - vacuum decay
  - bounce solution
  - bubble nucleation
  - thin-wall approximation
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - false-vacua
  - metastability
  - semiclassical-methods
researchStatus:
  established:
    - "In a weakly coupled scalar theory with a local but non-global minimum, the leading zero-temperature decay rate is controlled by a Euclidean bounce action."
  active:
    - "Vacuum decay in gauge theories, multifield landscapes, finite-temperature systems, dense matter, curved spacetime, and real-time environments can be model-dependent and technically subtle."
---

## Summary

A **false vacuum** is a long-lived state associated with a local minimum of the energy landscape that is not the true ground state. Perturbation theory around it can look perfectly healthy: it sees particles, propagators, and loop corrections near the local minimum. What it does not see at any finite order is the rare, large fluctuation that carries the system through a barrier and lets a bubble of the true vacuum grow.

The standard semiclassical statement is

$$
\frac{\Gamma}{\mathcal V}
\simeq
A e^{-B},
\qquad
B=S_E[\phi_b]-S_E[\phi_f],
$$

where $\Gamma/\mathcal V$ is the decay probability per unit time per unit spatial volume, $\phi_f$ is the false-vacuum configuration, $\phi_b$ is the Euclidean **bounce**, $S_E$ is the Euclidean action, and $A$ is a one-loop-and-zero-mode prefactor. The exponential is the main event. The false vacuum is metastable because $B$ can be very large.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A tilted two-minimum potential and a Euclidean bounce bubble of true vacuum inside false vacuum.](/figures/nonperturbative-qft/false-vacuum-bounce.svg)

<figcaption>

A false vacuum is a local minimum separated from the true vacuum by a barrier. The leading zero-temperature decay channel is a Euclidean bounce: a critical bubble of true vacuum inside false vacuum whose wall has radius $R_\ast$ in the thin-wall regime.

</figcaption>
</figure>

False-vacuum decay is a prototype nonperturbative phenomenon. It is not merely “large coupling physics.” In weakly coupled theories it can be exponentially small and semiclassically controlled, precisely because it is governed by a classical Euclidean saddle rather than a finite collection of Feynman diagrams.

## Prerequisites

You should know [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/), [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/), [Phase Diagrams](/nonperturbative-qft/vacuum-structure-phases/phase-diagrams/), and [Quantum Phase Transitions](/nonperturbative-qft/vacuum-structure-phases/quantum-phase-transitions/).

This page uses Euclidean signature for the bounce calculation. The Lorentzian interpretation appears afterward: a critical bubble nucleates and then expands in real time.

## Core idea

A local minimum is a good place to do perturbation theory. It is not automatically a true vacuum.

Consider a theory whose effective energy landscape has two local minima. If one minimum has lower energy density, call it $\phi_t$ for “true.” If the other is locally stable but higher, call it $\phi_f$ for “false.” Small fluctuations about $\phi_f$ have positive quadratic energy, so perturbation theory around $\phi_f$ describes ordinary stable-looking quanta. But the state is only metastable. A sufficiently large fluctuation can create a domain of true vacuum inside the false one.

The competition is simple:

- the interior of the bubble gains volume energy because true vacuum has lower energy density;
- the wall of the bubble costs surface energy because the field must interpolate through the barrier;
- subcritical bubbles shrink;
- critical or supercritical bubbles expand.

This is why false-vacuum decay resembles nucleation in a superheated fluid or supersaturated solution. The QFT version replaces thermal fluctuations by quantum tunneling, and the tunneling path is most cleanly described by a Euclidean saddle.

## Setup and conventions

For concreteness, take one real scalar field in $d$ Euclidean spacetime dimensions with action

$$
S_E[\phi]=\int d^d x\left[\frac12(\partial_\mu\phi)^2+V(\phi)\right].
$$

Let

$$
V(\phi_f)>V(\phi_t),
\qquad
\epsilon\equiv V(\phi_f)-V(\phi_t)>0.
$$

The additive constant in $V$ is convention-dependent. It is often convenient to set $V(\phi_f)=0$, in which case the true vacuum has $V(\phi_t)=-\epsilon$. The physical decay exponent depends on the action difference between the bounce and the false-vacuum background, not on the arbitrary zero of energy.

The quantity $\mathcal V$ denotes spatial volume. This avoids a notational collision with the potential $V(\phi)$.

## False vacuum versus true ground state

A true vacuum is a lowest-energy state, after specifying the theory, boundary conditions, sector, and limiting procedure. A false vacuum is not another exact ground state. It is a metastable state or resonance: it behaves like a vacuum over a long time interval, but it has a nonzero decay rate.

There are two reasons this distinction is easy to miss.

First, perturbation theory is local in field space. A loop expansion around $\phi_f$ computes small oscillations near $\phi_f$. Barrier penetration is controlled by effects of order $e^{-B}$, which have vanishing Taylor expansion in the loop-counting parameter. A finite-order loop calculation can correct the mass, couplings, and energy density near $\phi_f$, but it cannot by itself show the instability.

Second, the exact effective potential is convex in the infinite-volume Legendre-transform sense. Metastability is not erased by convexity; it is encoded in how one prepares a long-lived state, in analytic continuations, in local effective potentials, and in semiclassical saddles. The exact thermodynamic envelope answers the question “what is the lowest energy density at fixed expectation value?” The false vacuum answers a different dynamical question: “how long can a locally stable state persist before nucleating a lower-energy phase?”

## The bounce equation

The leading zero-temperature decay exponent comes from a Euclidean saddle $\phi_b$ satisfying

$$
\frac{\delta S_E}{\delta\phi}=0.
$$

For a single scalar field this is

$$
-\partial^2\phi_b+V'(\phi_b)=0.
$$

The bounce approaches the false vacuum far away in Euclidean spacetime,

$$
\phi_b(x)\to \phi_f
\qquad
\text{as } |x|\to\infty,
$$

but it explores the true-vacuum side near its center. For the leading single-bounce saddle in a scalar theory, one usually takes the $O(d)$-symmetric ansatz

$$
\phi_b(x)=\phi_b(\rho),
\qquad
\rho=\sqrt{x_\mu x_\mu},
$$

which gives

$$
\frac{d^2\phi_b}{d\rho^2}
+\frac{d-1}{\rho}\frac{d\phi_b}{d\rho}
=V'(\phi_b),
$$

with boundary conditions

$$
\left.\frac{d\phi_b}{d\rho}\right|_{\rho=0}=0,
\qquad
\phi_b(\rho\to\infty)=\phi_f.
$$

The term $(d-1)\phi_b'/\rho$ is often described as friction in the mechanical analogy where $\rho$ plays the role of time and the particle moves in the inverted potential $-V(\phi)$. The bounce starts near the true-vacuum side, rolls through the inverted potential, and asymptotically comes to rest at the false vacuum.

The decay exponent is

$$
B=S_E[\phi_b]-S_E[\phi_f].
$$

The prefactor $A$ comes from Gaussian fluctuations around the bounce, zero modes, and the single negative mode. The negative mode is not a bug: it is the sign that the bounce is a saddle describing decay rather than a stable Euclidean minimum.

## Thin-wall approximation

The **thin-wall approximation** applies when the energy-density splitting $\epsilon$ between the two minima is small compared with the barrier scale. Then the bubble radius is much larger than the wall thickness. The bounce can be approximated by a ball of true vacuum inside false vacuum, separated by a thin wall.

Let $\sigma$ be the wall tension computed in the nearly degenerate potential. For a single scalar, a useful expression in the degenerate limit is

$$
\sigma
=\int_{\phi_t}^{\phi_f} d\phi\,
\sqrt{2\left[V_0(\phi)-V_0(\phi_t)\right]},
$$

where $V_0$ is the potential with degenerate minima. The Euclidean action of a spherical bubble of radius $R$ is approximately

$$
B(R)=\Omega_{d-1}\sigma R^{d-1}
-\frac{\Omega_{d-1}}{d}\epsilon R^d,
$$

where

$$
\Omega_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}
$$

is the area of the unit $(d-1)$-sphere. The first term is the wall cost. The second is the volume gain.

Extremizing gives

$$
R_\ast=\frac{(d-1)\sigma}{\epsilon}
$$

and

$$
B_\ast
=\frac{\Omega_{d-1}}{d}(d-1)^{d-1}
\frac{\sigma^d}{\epsilon^{d-1}}.
$$

In $3+1$ Lorentzian dimensions, the Euclidean bounce has $d=4$, so

$$
R_\ast=\frac{3\sigma}{\epsilon},
\qquad
B_\ast=\frac{27\pi^2\sigma^4}{2\epsilon^3}.
$$

The scaling is worth remembering: as $\epsilon\to0$, the critical bubble becomes huge and the decay exponent becomes enormous. Nearly degenerate vacua can be fantastically long-lived.

## Lorentzian bubble interpretation

The Euclidean bounce describes tunneling under the barrier. After analytic continuation back to real time, the critical bubble appears at the classical turning point. In $3+1$ dimensions, its wall is a two-sphere of radius $R_\ast$ at nucleation. The total energy relative to the false vacuum is zero: positive wall energy is balanced by negative volume energy.

After nucleation, the bubble expands. In the thin-wall relativistic approximation, the wall accelerates outward and approaches the speed of light. Locally, the bubble wall is a domain wall separating two phases. Globally, it converts the metastable false vacuum into the lower-energy phase.

This interpretation also explains why one computes a decay probability per unit volume. In a large spatial region, the question is not whether the entire region tunnels at once. The question is whether a critical bubble nucleates somewhere.

## Metastability as a physical phase question

A metastable state can be physically meaningful even though it is not the exact ground state. The relevant dimensionless quantity is roughly

$$
\frac{\Gamma}{\mathcal V}\,\mathcal V_{\rm exp}\,T_{\rm exp},
$$

where $\mathcal V_{\rm exp}$ and $T_{\rm exp}$ are the spatial volume and time scale of the experiment or cosmological region under discussion. If this number is much smaller than one, the false vacuum is operationally stable on those scales. If it is order one or larger, decay is likely.

This is why metastability appears throughout QFT and statistical physics: superheated phases, false scalar vacua, metastable strings, false domain-wall configurations, first-order transitions, and cosmological vacuum questions all share the same nucleation logic.

## Common mistakes

**Calling every local minimum a vacuum.** A local minimum is a candidate saddle for expansion. The true vacuum is the lowest-energy state in the specified sector and limit. A false vacuum is a long-lived state, not another exact ground state.

**Expecting a finite loop calculation to show the decay.** Perturbation theory around the false minimum is blind to $e^{-B}$ effects. It can compute local properties of the metastable state, but tunneling requires a nontrivial saddle.

**Confusing a nonconvex loop potential with the exact effective potential.** The loop-expanded potential is a local semiclassical tool. The exact Legendre-transform potential is convex. Metastability lives in the relation between local saddles, state preparation, and decay, not in a naive reading of a single plotted curve.

**Using the thin-wall approximation without checking its regime.** Thin-wall formulas require $R_\ast$ much larger than the wall thickness. If the vacua are not nearly degenerate, the qualitative bounce picture may survive but the simple formulas for $R_\ast$ and $B_\ast$ need not.

**Ignoring finite temperature, density, or gravity.** Thermal transitions can proceed by sphaleron-like activation over a barrier rather than zero-temperature tunneling. Curved spacetime changes both the bounce and the interpretation of vacuum energy. Dense matter and real-time environments can invalidate the simplest Euclidean story.

**Trusting gauge-dependent tunneling paths too literally.** In gauge theories and multifield systems, field-space coordinates are often redundant or convention-dependent. The decay rate is physical; a plotted path through gauge-dependent variables is not automatically physical.

## Research status

- **Established:** In weakly coupled scalar QFT, false-vacuum decay is computed semiclassically by Euclidean bounce methods. The leading exponential is the bounce action difference, and the prefactor comes from fluctuations, zero modes, and the negative mode.
- **Controlled but technical:** One-loop corrections, multi-field bounces, constrained instantons, finite-temperature transitions, and gravitational corrections can be systematically treated in favorable regimes, but they require care.
- **Active:** Vacuum decay in complicated gauge theories, cosmological landscapes, dense matter, real-time environments, and theories with strong coupling or sign problems is often a research problem rather than a solved exercise.

## Relation to other topics

- [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/) explains why the exact effective potential is convex and how this coexists with local semiclassical minima.
- [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) explains the symmetric limit where the two minima are degenerate and domain walls are stable.
- [Phase Diagrams](/nonperturbative-qft/vacuum-structure-phases/phase-diagrams/) explains how first-order lines and coexistence regions organize metastable phases.
- [Quantum Phase Transitions](/nonperturbative-qft/vacuum-structure-phases/quantum-phase-transitions/) contrasts first-order metastability with continuous gap-closing transitions.
- [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) gives the path-integral language used by the bounce calculation.
- [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains why exact finite-volume spectra and infinite-volume metastability are not the same problem.

## Exercises

### Exercise 1: Extremize the thin-wall action

Start from

$$
B(R)=\Omega_{d-1}\sigma R^{d-1}
-\frac{\Omega_{d-1}}{d}\epsilon R^d.
$$

Show that the stationary radius is

$$
R_\ast=\frac{(d-1)\sigma}{\epsilon}.
$$

Is this stationary point a minimum or a maximum of $B(R)$?

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dB}{dR}
=\Omega_{d-1}(d-1)\sigma R^{d-2}
-\Omega_{d-1}\epsilon R^{d-1}.
$$

For $R\neq0$, the stationary condition is

$$
(d-1)\sigma-\epsilon R=0,
$$

so

$$
R_\ast=\frac{(d-1)\sigma}{\epsilon}.
$$

The second derivative is

$$
\frac{d^2B}{dR^2}
=\Omega_{d-1}(d-1)(d-2)\sigma R^{d-3}
-\Omega_{d-1}(d-1)\epsilon R^{d-2}.
$$

At $R=R_\ast$ this becomes

$$
\left.\frac{d^2B}{dR^2}\right|_{R_\ast}
=-\Omega_{d-1}(d-1)\sigma R_\ast^{d-3}<0.
$$

Thus the bounce is a saddle direction, not a Euclidean minimum. This is the thin-wall manifestation of the negative mode.

</details>

### Exercise 2: The four-dimensional bounce exponent

Use

$$
B_\ast
=\frac{\Omega_{d-1}}{d}(d-1)^{d-1}
\frac{\sigma^d}{\epsilon^{d-1}}
$$

and $\Omega_3=2\pi^2$ to derive the thin-wall exponent in $3+1$ Lorentzian dimensions.

<details>
<summary><strong>Solution</strong></summary>

For $3+1$ Lorentzian dimensions, the Euclidean bounce lives in $d=4$ dimensions. Therefore

$$
B_\ast
=\frac{\Omega_3}{4}3^3\frac{\sigma^4}{\epsilon^3}.
$$

Since $\Omega_3=2\pi^2$,

$$
B_\ast
=\frac{2\pi^2}{4}27\frac{\sigma^4}{\epsilon^3}
=\frac{27\pi^2\sigma^4}{2\epsilon^3}.
$$

</details>

### Exercise 3: Why no finite perturbative order sees the decay

Suppose the decay rate contains a factor

$$
e^{-B/g^2}
$$

with $B>0$. Show that this contribution has zero Taylor series around $g=0$ even though it is nonzero for $g>0$.

<details>
<summary><strong>Solution</strong></summary>

For every positive integer $n$,

$$
\lim_{g\to0^+}\frac{e^{-B/g^2}}{g^n}=0.
$$

The exponential vanishes faster than any power. Equivalently, all derivatives at $g=0$ obtained by extending the function smoothly from $g>0$ vanish. Thus the Taylor series around $g=0$ is identically zero, while the function is nonzero at any finite positive $g$. This is the standard sense in which the bounce contribution is nonperturbative in $g$.

</details>

### Exercise 4: Critical radius versus energy barrier

In $3+1$ dimensions, approximate the energy of a static spherical bubble of true vacuum of radius $r$ inside false vacuum by

$$
E(r)=4\pi\sigma r^2-\frac{4\pi}{3}\epsilon r^3.
$$

Find the radius where $E(r)$ is maximal and the nonzero radius where $E(r)=0$. Explain why these radii are different.

<details>
<summary><strong>Solution</strong></summary>

The maximum is found from

$$
\frac{dE}{dr}=8\pi\sigma r-4\pi\epsilon r^2
=4\pi r(2\sigma-\epsilon r).
$$

Thus

$$
r_{\rm max}=\frac{2\sigma}{\epsilon}.
$$

The nonzero solution of $E(r)=0$ is

$$
4\pi\sigma r^2-\frac{4\pi}{3}\epsilon r^3=0
\quad\Rightarrow\quad
r=\frac{3\sigma}{\epsilon}.
$$

The first radius is the top of the static energy barrier for a bubble at rest. The second is the classical turning-point radius of a spontaneously nucleated bubble with total energy equal to that of the original false-vacuum state. The Euclidean bounce lands at the turning point, not at the top of the static energy curve.

</details>

### Exercise 5: Lifetime criterion

Assume the decay rate per unit spatial volume is $\Gamma/\mathcal V$. For an experiment probing volume $\mathcal V_{\rm exp}$ for time $T_{\rm exp}$, estimate the probability of at least one bubble nucleation event when the rate is small.

<details>
<summary><strong>Solution</strong></summary>

For a small rate, bubble nucleation events are approximately Poisson distributed. The expected number of events is

$$
N_{\rm exp}\simeq \frac{\Gamma}{\mathcal V}\,\mathcal V_{\rm exp}T_{\rm exp}.
$$

When $N_{\rm exp}\ll1$, the probability of one or more events is approximately

$$
P\simeq N_{\rm exp}
=\frac{\Gamma}{\mathcal V}\,\mathcal V_{\rm exp}T_{\rm exp}.
$$

Thus metastability is scale-dependent: a false vacuum can be effectively stable in a laboratory volume and time while still having a nonzero decay rate in principle.

</details>

## References

- S. Coleman, “The Fate of the False Vacuum: Semiclassical Theory,” *Physical Review D* **15** (1977), 2929–2936.
- C. G. Callan and S. Coleman, “The Fate of the False Vacuum. II. First Quantum Corrections,” *Physical Review D* **16** (1977), 1762–1768.
- S. Coleman and F. De Luccia, “Gravitational Effects on and of Vacuum Decay,” *Physical Review D* **21** (1980), 3305–3315.
- S. Coleman, *Aspects of Symmetry*, especially the lecture “The Uses of Instantons.”
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 7.
- M. Mariño, *Instantons and Large N*, especially the chapters on unstable vacua and large-order behavior.

## Version history

- **2026-06-26:** Initial polished page.
