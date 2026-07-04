---
title: "Soft Limits"
description: "How scattering amplitudes simplify when an external particle momentum becomes soft, including leading soft factors for photons, gluons, and gravitons and their relation to gauge invariance and asymptotic structure."
sidebar:
  label: "Soft Limits"
  order: 8
level: Advanced
status: "Polished draft"
source: "Low; Weinberg; Bern, Dixon, and Kosower; Cachazo and Strominger; Elvang and Huang; Strominger lectures."
topics:
  - soft limits
  - soft theorems
  - infrared physics
  - gauge invariance
  - spinor helicity
canonicalTopics:
  - soft-limits
  - soft-photon-theorem
  - soft-gluon-theorem
  - soft-graviton-theorem
  - asymptotic-symmetry-preview
researchStatus:
  established:
    - "Leading soft photon, gluon, and graviton factors are standard universal limits of perturbative scattering amplitudes, with gauge invariance tied to charge, color, and momentum conservation."
  active:
    - "Subleading soft behavior, loop corrections, asymptotic symmetries, celestial amplitudes, memory effects, and nonperturbative formulations remain active research areas."
---

## Summary

A soft limit studies a scattering amplitude when one external momentum becomes small compared with the hard momenta. If the soft particle has momentum $q$ and the hard particles have momenta $p_a$, the limit is schematically

$$
q\to \tau q,
\qquad
\tau\to 0.
$$

For photons, gluons, and gravitons, the leading singular term is universal: the amplitude with the extra soft particle factorizes into a soft factor multiplying an amplitude without that particle,

$$
\mathcal A_{n+1}(1,\ldots,n,q)
\sim
S(q;1,\ldots,n)\,\mathcal A_n(1,\ldots,n).
$$

The word “universal” is doing real work. The leading soft factor depends on charges, color generators, momenta, helicities, and polarizations, but not on the detailed short-distance dynamics of the hard interaction. That is why soft limits sit simultaneously in perturbative amplitudes, infrared physics, asymptotic symmetry, and factorization.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Soft limit factorization of an amplitude into a universal soft factor times a hard amplitude](/figures/perturbative-qft/soft-limits.svg)

<figcaption>

In a soft limit, an amplitude with one low-energy external particle factorizes into a universal soft factor multiplying the hard amplitude. The soft factor is controlled by the long-distance coupling of the soft particle to the external hard lines.

</figcaption>
</figure>

This page explains the common logic behind soft photon, soft gluon, and soft graviton limits, then translates it into spinor-helicity language for color-ordered amplitudes. The goal is not to replace the detailed infrared chapter. The goal is to show why soft behavior is a structural property of amplitudes, not a computational accident.

## Prerequisites

You should know [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/), [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/), [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/), [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/), and [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/).

## Core idea

Soft particles have long wavelengths. A particle with momentum $q$ probes distances of order $1/|q|$, so as $q\to0$ it cannot resolve the microscopic details of the hard scattering process. It mostly sees the external hard particles as classical sources of charge, color, momentum, and angular momentum.

That is the reason soft limits are universal. The hard amplitude can be complicated; the leading soft attachment is simple.

For a photon, the soft particle couples to electric charge. For a gluon, it couples to color charge and remembers color ordering. For a graviton, it couples to energy-momentum. The replacement pattern is roughly

| Soft particle | Long-distance source | Leading factor controlled by |
|---|---|---|
| photon | electric charge | $Q_a p_a\cdot\varepsilon/(p_a\cdot q)$ |
| gluon | color charge | $T_a^A p_a\cdot\varepsilon/(p_a\cdot q)$ |
| graviton | energy-momentum | $p_a^\mu p_a^\nu\varepsilon_{\mu\nu}/(p_a\cdot q)$ |

The denominator $p_a\cdot q$ is the near-on-shell propagator of the hard external line after it emits the soft particle. The numerator is the corresponding eikonal coupling. This is why soft limits are the on-shell amplitude version of the eikonal approximation.

## Setup and conventions

We use the scattering and spinor-helicity conventions fixed elsewhere in this volume. Unless stated otherwise, all hard external momenta are outgoing. A soft momentum is introduced by replacing

$$
q^\mu\mapsto \tau q^\mu,
\qquad
\tau\to0^+.
$$

The polarization vector of a soft gauge boson is denoted $\varepsilon_\mu(q)$, and the polarization tensor of a graviton is denoted $\varepsilon_{\mu\nu}(q)$. For a graviton built from two gauge-theory-like polarizations, one may think schematically of

$$
\varepsilon_{\mu\nu}\sim \varepsilon_\mu\widetilde\varepsilon_\nu,
$$

with the transverse, symmetric, traceless conditions imposed as appropriate.

Soft theorems are often written for stripped amplitudes without the overall momentum-conserving delta function. That is convenient, but it can hide small deformations needed to preserve momentum conservation. When subleading terms matter, the precise definition of the soft limit should be stated.

## The soft photon factor

For an amplitude with one additional soft photon of polarization $\varepsilon_\mu(q)$, the leading soft theorem is

$$
\mathcal M_{n+1}^{\gamma}(q;1,\ldots,n)
=
\left[
 e\sum_{a=1}^n \eta_a Q_a\,
 \frac{p_a\cdot\varepsilon(q)}{p_a\cdot q}
\right]
\mathcal M_n(1,\ldots,n)
+O(\tau^0).
$$

Here $Q_a$ is the electric charge of hard particle $a$ in units of $e$, and $\eta_a$ is a sign that distinguishes outgoing and incoming hard particles. With the all-outgoing convention, incoming particles are represented by their crossed outgoing antiparticles, so the charge signs are already encoded in the external states. In mixed incoming/outgoing notation it is safer to keep $\eta_a$ explicit.

The soft factor is singular as $\tau^{-1}$ because

$$
p_a\cdot q \mapsto \tau\,p_a\cdot q.
$$

The numerator does not vanish generically. Physically, the hard charged particle can emit a photon of arbitrarily low energy at little kinematic cost.

### Gauge invariance check

Replace the soft polarization by a pure gauge polarization,

$$
\varepsilon_\mu(q)\mapsto q_\mu.
$$

The leading soft factor changes to

$$
e\sum_{a=1}^n \eta_a Q_a.
$$

Gauge invariance therefore requires

$$
\sum_{a=1}^n \eta_a Q_a=0,
$$

which is simply charge conservation for the hard process. This is the first lesson of soft theorems: gauge invariance of the soft factor is not an extra miracle. It is the conservation law associated with the long-distance gauge field.

## The soft gluon factor

For a soft gluon with adjoint color index $A$, the non-Abelian analogue is

$$
\mathcal M_{n+1}^{A}(q;1,\ldots,n)
=
\left[
 g\sum_{a=1}^n \eta_a T_a^A\,
 \frac{p_a\cdot\varepsilon(q)}{p_a\cdot q}
\right]
\mathcal M_n(1,\ldots,n)
+O(\tau^0),
$$

where $T_a^A$ acts on the color index of hard particle $a$. The formula is operator-valued in color space. It multiplies the hard amplitude as a color vector, not just as a scalar number.

In a color-ordered tree amplitude, the leading soft factor simplifies. If the soft gluon $s$ lies between adjacent legs $a$ and $b$ in the color ordering, then

$$
A_{n+1}^{\rm tree}(\ldots,a,s^+,b,\ldots)
\to
S^{(0)}(a,s^+,b)
A_n^{\rm tree}(\ldots,a,b,\ldots),
$$

with

$$
S^{(0)}(a,s^+,b)
=
\frac{\langle ab\rangle}{\langle as\rangle\langle sb\rangle},
\qquad
S^{(0)}(a,s^-,b)
=
\frac{[ab]}{[as][sb]}.
$$

This is one of the cleanest places where color ordering pays rent. The full color-space soft factor sums over all hard color charges. A color-ordered partial amplitude localizes the leading soft pole to the two hard legs adjacent to the soft gluon in the cyclic ordering.

### Color conservation and Ward identities

Gauge invariance now requires color conservation,

$$
\sum_{a=1}^n \eta_a T_a^A\,\mathcal M_n=0.
$$

This is the non-Abelian Ward identity for the hard amplitude. In a color-ordered amplitude the corresponding statement is more hidden: the soft factor depends on neighboring legs, and the cyclic sum of ordered pieces reconstructs the full gauge-invariant color-dressed answer.

## The soft graviton factor

Gravity is even more universal because every particle carries energy-momentum. The leading soft graviton theorem is

$$
\mathcal M_{n+1}^{h}(q;1,\ldots,n)
=
\left[
\frac{\kappa}{2}
\sum_{a=1}^n \eta_a
\frac{p_a^\mu p_a^\nu\varepsilon_{\mu\nu}(q)}{p_a\cdot q}
\right]
\mathcal M_n(1,\ldots,n)
+O(\tau^0).
$$

The numerator has two powers of hard momentum because a graviton couples to the stress tensor. The soft pole is again the nearly on-shell external propagator.

Gauge invariance is now invariance under the linearized diffeomorphism shift

$$
\varepsilon_{\mu\nu}\mapsto \varepsilon_{\mu\nu}+q_\mu\xi_\nu+q_\nu\xi_\mu.
$$

The variation of the leading soft factor is proportional to

$$
\sum_{a=1}^n \eta_a p_a^\mu,
$$

which vanishes by momentum conservation. The gravitational soft theorem therefore ties together three ideas that often appear separately:

```txt
soft gravitons ↔ long-distance gravity ↔ momentum conservation.
```

At tree level in four-dimensional gravity, more is true. With a suitable definition of the soft limit, graviton amplitudes have universal subleading and sub-subleading soft operators involving the angular momentum generators acting on the hard legs. These terms are central in the modern connection between soft theorems, memory effects, and asymptotic symmetries. Beyond tree level, loop corrections and infrared subtleties require care.

## Spinor-helicity form of gauge-theory soft limits

For massless color-ordered amplitudes in four dimensions, the leading soft factors become especially compact. The positive-helicity soft gluon factor

$$
S^{(0)}(a,s^+,b)
=
\frac{\langle ab\rangle}{\langle as\rangle\langle sb\rangle}
$$

has little-group weight $t_s^{-2}$ under

$$
|s\rangle\mapsto t_s|s\rangle,
\qquad
|s]\mapsto t_s^{-1}|s].
$$

That is the correct weight for a positive-helicity gluon amplitude as a function of the soft leg. Similarly,

$$
S^{(0)}(a,s^-,b)
=
\frac{[ab]}{[as][sb]}
$$

has weight $t_s^{+2}$, appropriate for a negative-helicity gluon.

The formulas also show why soft limits are singular. If $q_s\to\tau q_s$ with both spinors scaled as $|s\rangle,|s]\sim \sqrt\tau$, then

$$
\langle as\rangle\langle sb\rangle\sim \tau,
\qquad
[as][sb]\sim \tau.
$$

The leading soft factors therefore scale as $\tau^{-1}$.

## Soft limits versus collinear limits

Soft and collinear limits are often discussed together, but they are not the same limit.

In a soft limit, one momentum becomes small:

$$
q_s\to0.
$$

In a collinear limit, two finite-energy massless momenta become parallel:

$$
p_i\parallel p_j,
\qquad
s_{ij}=2p_i\cdot p_j\to0.
$$

A soft limit can also be collinear to a hard leg, but it need not be. This distinction matters in factorization formulas, parton showers, jet observables, and infrared subtraction. Soft singularities are tied to long wavelengths. Collinear singularities are tied to unresolved small angles for massless particles.

## Subleading soft behavior

The leading soft factors are the most universal and the least fragile. Subleading soft behavior contains more information and more caveats.

For photons, Low's theorem constrains the next term in the soft expansion under assumptions about isolated external particles and analyticity. For gravitons, the subleading tree-level soft factor involves total angular momentum of the hard particles. Schematically,

$$
S_{\rm grav}^{(1)}
\sim
\sum_a
\frac{\varepsilon_{\mu\nu}p_a^\mu q_\rho J_a^{\rho\nu}}{p_a\cdot q}.
$$

Here $J_a^{\rho\nu}$ acts on the momentum and spin or helicity data of hard particle $a$. Gauge invariance of this term is tied to angular momentum conservation.

Subleading soft theorems are a meeting point for several subjects:

| Viewpoint | What the subleading term knows |
|---|---|
| amplitude theory | differential operators acting on hard amplitudes |
| infrared physics | next-to-eikonal corrections |
| asymptotic symmetry | Ward identities at null infinity |
| classical radiation | memory and angular momentum flux |
| celestial amplitudes | current algebra and conformal-soft limits |

A good rule of thumb: leading soft factors are robust; subleading soft statements should always come with their assumptions.

## Relation to factorization and recursion

Soft limits are one member of a larger family of factorization limits. On-shell amplitudes simplify when kinematics approach special boundaries:

| Limit | Boundary | Universal object |
|---|---|---|
| multiparticle factorization | $P^2\to0$ | lower-point amplitudes joined by propagator |
| collinear factorization | $p_i\parallel p_j$ | splitting amplitude |
| soft factorization | $q\to0$ | soft factor times hard amplitude |

BCFW recursion uses factorization at complex poles. Soft recursion and inverse-soft constructions use soft behavior more directly. In modern amplitude theory, the guiding idea is that amplitudes are constrained by their singularities and behavior at infinity. Soft limits are among the simplest and most physical singular boundaries.

## Common pitfalls

**Confusing soft with zero.** A soft particle has small momentum, but the amplitude can diverge as the momentum goes to zero. The soft particle is not simply absent; it leaves a universal long-distance imprint.

**Forgetting the hard momentum deformation.** A stripped amplitude can be evaluated at momenta that do not explicitly display the overall delta function. For subleading terms, momentum conservation and the chosen deformation matter.

**Treating all soft theorems as equally universal.** Leading soft photon, gluon, and graviton factors are very robust. Subleading and loop-level statements have more assumptions.

**Ignoring color space.** The full soft gluon factor is an operator in color space. The simple adjacent-leg formula applies to color-ordered partial amplitudes.

**Mixing soft and collinear singularities.** They often overlap in massless gauge theory, but they are physically and mathematically distinct limits.

**Assuming soft factors are observables by themselves.** Infrared-safe observables require combining virtual and real radiation with a measurement function. Soft factors are ingredients, not full detector predictions.

## Relations to other pages

- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) explains how soft singularities appear in real and virtual corrections.
- [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) derives the long-distance approximation behind leading soft factors.
- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) and [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) give more detailed infrared versions.
- [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/) explains why the ordered soft gluon factor only sees adjacent legs.
- [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) uses complex factorization and can prove many tree-level soft statements.
- [Double Copy](/perturbative-qft/modern-on-shell-amplitudes/double-copy/) explains how gravity soft behavior is related to gauge-theory structures.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) places soft limits inside the broader structure of factorized observables.

## Research status

- **Established:** Leading soft photon, gluon, and graviton theorems are textbook-standard perturbative results. Color-ordered tree-level soft gluon factors and leading gravitational soft factors are central tools in amplitude calculations.
- **Active:** Subleading soft theorems, loop corrections, asymptotic symmetries, celestial formulations, memory effects, and soft behavior in curved backgrounds or nonperturbative settings remain active research areas.
- **Speculative:** Some proposed links between soft structures, complete S-matrix organization, and quantum gravity constraints are promising but not settled as general theorems.

## Exercises

### Exercise 1: Gauge invariance of the soft photon factor

Starting from

$$
S_\gamma^{(0)}=e\sum_{a=1}^n \eta_a Q_a\frac{p_a\cdot\varepsilon}{p_a\cdot q},
$$

show that the replacement $\varepsilon\mapsto q$ gives charge conservation.

<details>
<summary><strong>Solution</strong></summary>

Under $\varepsilon\mapsto q$,

$$
S_\gamma^{(0)}\mapsto
e\sum_{a=1}^n \eta_a Q_a\frac{p_a\cdot q}{p_a\cdot q}
=
e\sum_{a=1}^n\eta_a Q_a.
$$

Gauge invariance requires this variation to vanish when acting on the hard amplitude. Hence

$$
\sum_{a=1}^n\eta_a Q_a=0,
$$

which is electric charge conservation for the process.

</details>

### Exercise 2: Little-group weight of the positive-helicity soft gluon factor

Check that

$$
S^{(0)}(a,s^+,b)=\frac{\langle ab\rangle}{\langle as\rangle\langle sb\rangle}
$$

has the correct little-group weight for a positive-helicity soft gluon.

<details>
<summary><strong>Solution</strong></summary>

Under the little-group scaling of leg $s$,

$$
|s\rangle\mapsto t_s|s\rangle,
\qquad
|s]\mapsto t_s^{-1}|s],
$$

the angle brackets involving $s$ scale as

$$
\langle as\rangle\mapsto t_s\langle as\rangle,
\qquad
\langle sb\rangle\mapsto t_s\langle sb\rangle.
$$

The numerator $\langle ab\rangle$ is independent of leg $s$. Therefore

$$
S^{(0)}(a,s^+,b)\mapsto t_s^{-2}S^{(0)}(a,s^+,b).
$$

A positive-helicity gluon amplitude has little-group weight $t_s^{-2}$ in leg $s$, so the soft factor has the correct weight.

</details>

### Exercise 3: Gauge invariance of the leading soft graviton factor

Use

$$
S_h^{(0)}=\frac{\kappa}{2}\sum_{a=1}^n\eta_a
\frac{p_a^\mu p_a^\nu\varepsilon_{\mu\nu}}{p_a\cdot q}
$$

and the shift $\varepsilon_{\mu\nu}\mapsto q_\mu\xi_\nu+q_\nu\xi_\mu$ to show that gauge invariance follows from momentum conservation.

<details>
<summary><strong>Solution</strong></summary>

The variation is

$$
\delta S_h^{(0)}
=
\frac{\kappa}{2}\sum_a\eta_a
\frac{p_a^\mu p_a^\nu(q_\mu\xi_\nu+q_\nu\xi_\mu)}{p_a\cdot q}.
$$

The two terms are equal after relabeling dummy indices, so

$$
\delta S_h^{(0)}
=
\kappa\sum_a\eta_a p_a\cdot\xi
=
\kappa\,\xi_\mu\sum_a\eta_a p_a^\mu.
$$

Momentum conservation gives

$$
\sum_a\eta_a p_a^\mu=0,
$$

so the variation vanishes.

</details>

### Exercise 4: Soft scaling of the color-ordered factor

Let $q_s\to\tau q_s$ with $|s\rangle\to\sqrt\tau |s\rangle$ and $|s]\to\sqrt\tau |s]$. Show that $S^{(0)}(a,s^+,b)$ scales as $\tau^{-1}$.

<details>
<summary><strong>Solution</strong></summary>

The numerator $\langle ab\rangle$ is independent of the soft spinors. Each denominator factor containing $s$ scales as $\sqrt\tau$:

$$
\langle as\rangle\sim\sqrt\tau,
\qquad
\langle sb\rangle\sim\sqrt\tau.
$$

Thus

$$
S^{(0)}(a,s^+,b)
=
\frac{\langle ab\rangle}{\langle as\rangle\langle sb\rangle}
\sim
\frac{1}{\tau}.
$$

This matches the leading soft pole for a gauge boson.

</details>

## References

- F. E. Low, “Bremsstrahlung of Very Low-Energy Quanta in Elementary Particle Collisions,” *Physical Review* **110** (1958), and “Scattering of Light of Very Low Frequency by Systems of Spin 1/2,” *Physical Review* **96** (1954).
- S. Weinberg, “Infrared Photons and Gravitons,” *Physical Review* **140** (1965), for the leading universal soft photon and graviton factors.
- F. Cachazo and A. Strominger, “Evidence for a New Soft Graviton Theorem,” for tree-level subleading and sub-subleading graviton soft behavior.
- A. Strominger, *Lectures on the Infrared Structure of Gravity and Gauge Theory*, for the relation between soft theorems, memory, and asymptotic symmetry.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for spinor-helicity soft factors and amplitude-theory applications.
- L. J. Dixon, “A brief introduction to modern amplitude methods,” for soft and collinear limits in gauge-theory amplitudes.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 27, and 32, for infrared divergences, jets, and spinor-helicity applications.

## Version history

- **2026-06-13:** Initial QFT.org page on soft limits in modern on-shell amplitudes, emphasizing leading universality, gauge invariance, color ordering, gravitational soft factors, and the handoff to infrared factorization.
