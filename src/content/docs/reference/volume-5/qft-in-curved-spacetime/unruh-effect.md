---
title: "Unruh Effect"
description: "A QFT-oriented derivation and interpretation of the Unruh effect: why the Minkowski vacuum appears thermal to uniformly accelerated observers."
sidebar:
  label: "Unruh Effect"
  order: 70
level: Graduate
status: "Polished draft"
source: "Fulling 1973; Davies 1975; Unruh 1976; Birrell and Davies 1982, ch. 4; Wald 1994; Crispino, Higuchi, and Matsas 2008"
topics:
  - Unruh effect
  - Rindler quantization
  - accelerated observers
  - thermal field theory
  - horizons
canonicalTopics:
  - unruh-effect
  - rindler-wedge
  - accelerated-detector
  - minkowski-vacuum
  - kms-state
researchStatus:
  established:
    - "The Minkowski vacuum restricted to a Rindler wedge is thermal with respect to boost time, with temperature T=a/(2π) for a uniformly accelerated detector of proper acceleration a."
  active:
    - "The effect is conceptually settled in QFT, while experimental realization, detector modeling, and extensions to interacting theories and gravity-adjacent settings remain active topics."
---

## Summary

The **Unruh effect** says that the Minkowski vacuum is not empty for a uniformly accelerated observer. A detector with constant proper acceleration $a$ in the Minkowski vacuum responds as if immersed in a thermal bath with temperature

$$
T_U=\frac{a}{2\pi}.
$$

In units with $\hbar=c=k_B=1$, acceleration has units of energy. Restoring constants gives

$$
T_U=\frac{\hbar a}{2\pi c k_B}.
$$

The geometry behind the effect is the Rindler wedge. In two displayed dimensions, Minkowski spacetime has

$$
ds^2=dt^2-dx^2,
$$

and the right Rindler wedge is

$$
\mathcal R=\{(t,x):x>|t|\}.
$$

A uniformly accelerated observer remains inside this wedge and has a horizon at $x=\pm t$. The Minkowski vacuum, when restricted to observables in the right wedge, is a thermal state with respect to Rindler time. The effect is therefore not “particles appearing from nowhere.” It is the mismatch between two notions of time evolution: inertial time and boost time.

## Prerequisites

Read [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/), [Mode Expansions in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/mode-expansions-in-curved-spacetime/), [Bogoliubov Transformations](/spacetime-gravity-holography/qft-in-curved-spacetime/bogoliubov-transformations/), and [Particle Creation](/spacetime-gravity-holography/qft-in-curved-spacetime/particle-creation/).

You should know that a positive-frequency split defines particles and that different time flows can define different annihilation operators.

## Core idea

The Unruh effect has three equivalent faces:

| Viewpoint | Main statement |
|---|---|
| Rindler modes | Minkowski positive frequency mixes Rindler positive and negative frequency. |
| Density matrix | The Minkowski vacuum restricted to one wedge is thermal. |
| Detector response | A uniformly accelerated detector clicks thermally in the Minkowski vacuum. |

The same physics is summarized by

$$
\text{Minkowski vacuum restricted to a wedge}
=\text{thermal state for boost time}.
$$

The word restricted is crucial. The full Minkowski vacuum is pure and Poincare invariant. The right-wedge observer has access only to a subalgebra of observables. Tracing over the causally inaccessible left wedge turns the pure state into a thermal density matrix.

## Rindler coordinates

In the right wedge, introduce Rindler coordinates $(\eta,\rho)$ by

$$
t=\rho\sinh\eta,
\qquad
x=\rho\cosh\eta,
\qquad
\rho>0.
$$

Then

$$
ds^2=\rho^2d\eta^2-d\rho^2.
$$

The vector $\partial_\eta$ generates Lorentz boosts. It is timelike inside the right wedge and becomes null on the horizon $\rho=0$.

A worldline at fixed $\rho=\rho_0$ has proper time

$$
d\tau=\rho_0 d\eta.
$$

Its proper acceleration is

$$
a=1/\rho_0.
$$

Thus the Rindler time $\eta$ is related to the observer's proper time by

$$
\eta=a\tau.
$$

If one instead writes

$$
t=a^{-1}e^{a\xi}\sinh(a\tau),
\qquad
x=a^{-1}e^{a\xi}\cosh(a\tau),
$$

then the metric becomes

$$
ds^2=e^{2a\xi}(d\tau^2-d\xi^2),
$$

and the observer at $\xi=0$ has proper acceleration $a$.

## Rindler horizons

The null lines

$$
x=t,
\qquad
x=-t
$$

are the boundaries of the right wedge. A right-Rindler observer can never receive signals from the left wedge $x<-|t|$. This causal restriction is the origin of the thermal density matrix.

No curvature singularity exists at the Rindler horizon. The horizon is observer-dependent. Inertial observers cross it without drama; accelerated observers use coordinates that cover only one wedge.

This is the cleanest possible horizon lesson: horizons can be caused by observer access, not by curvature.

## Euclidean periodicity argument

The fastest derivation of the temperature uses Euclidean continuation. Set

$$
t_E=it.
$$

Near the Rindler wedge, the Euclidean metric becomes

$$
ds_E^2=d\rho^2+\rho^2d\eta_E^2,
$$

where $\eta_E$ is the Euclidean Rindler angle. This is just the plane in polar coordinates. Smoothness at $\rho=0$ requires

$$
\eta_E\sim\eta_E+2\pi.
$$

For an observer with proper time $\tau=\eta/a$, the Euclidean proper time has period

$$
\tau_E\sim \tau_E+\frac{2\pi}{a}.
$$

A Euclidean time circle of period $\beta$ corresponds to temperature $T=1/\beta$. Hence

$$
T_U=\frac{a}{2\pi}.
$$

This derivation is the prototype for the Euclidean derivation of Hawking temperature. Near any smooth nonextremal horizon, the Euclidean geometry looks like a plane in polar coordinates, and smoothness fixes the period.

## Rindler modes and Bogoliubov mixing

A scalar field can be quantized using modes positive frequency with respect to Minkowski time $t$, or using modes positive frequency with respect to Rindler time $\eta$ in the right wedge. These are not the same.

Minkowski modes behave like

$$
e^{-i\omega t+i kx}
$$

with positive frequency relative to $\partial_t$. Rindler modes behave like

$$
e^{-i\Omega\eta}
$$

with positive frequency relative to $\partial_\eta$.

Because $\eta$ is a boost time and covers only a wedge, Minkowski positive-frequency modes analytically continued across the horizon become mixtures of right- and left-Rindler modes. Equivalently, Rindler annihilation operators mix Minkowski annihilation and creation operators. This is the Bogoliubov-transformation origin of the Unruh effect.

The detailed mode functions involve Bessel functions, but the conceptual result is simple: the Minkowski vacuum is an entangled state of left- and right-Rindler excitations.

## Thermofield-double structure

For each Rindler frequency $\Omega$, the Minkowski vacuum has the schematic form

$$
|0_M\rangle
\propto
\prod_\Omega
\sum_{n=0}^\infty
 e^{-\pi\Omega n}
 |n_{\Omega,R}\rangle|n_{\Omega,L}\rangle.
$$

Tracing over the left wedge gives a right-wedge density matrix

$$
\rho_R
\propto
\prod_\Omega
\sum_{n=0}^\infty
 e^{-2\pi\Omega n}
 |n_{\Omega,R}\rangle\langle n_{\Omega,R}|.
$$

This is thermal with respect to the dimensionless Rindler Hamiltonian $K$ generating $\eta$ translations:

$$
\rho_R=Z^{-1}e^{-2\pi K}.
$$

For an observer with proper time $\tau=\eta/a$, the physical Hamiltonian is $H_R=aK$, so

$$
\rho_R=Z^{-1}e^{-H_R/T_U},
\qquad
T_U=a/(2\pi).
$$

This expression also clarifies why the global state can be pure while the wedge state is thermal. The thermal entropy is entanglement entropy across the Rindler horizon.

## Detector response

The operational version uses an Unruh–DeWitt detector: a simple quantum system moving along a worldline $x(\tau)$ and coupled locally to a scalar field. The transition rate depends on the pullback of the Wightman function to the detector trajectory:

$$
\mathcal F(E)
=\int_{-\infty}^{\infty}d\Delta\tau\,
 e^{-iE\Delta\tau}
 G^+(x(\tau),x(\tau')).
$$

For a uniformly accelerated trajectory in the Minkowski vacuum, the Wightman function is periodic in imaginary proper time with period

$$
\beta=2\pi/a.
$$

This is the KMS condition for a thermal state. It implies detailed balance:

$$
\frac{\mathcal F(E)}{\mathcal F(-E)}=e^{-2\pi E/a}.
$$

Thus the detector responds as if it were in a bath at temperature

$$
T_U=a/(2\pi).
$$

This detector statement is often the cleanest answer to “what does the accelerated observer actually measure?”

## Relation to Hawking radiation

Near the horizon of a nonextremal black hole, the metric locally takes Rindler form in the time-radial plane:

$$
ds^2\simeq \kappa^2\rho^2dt^2-d\rho^2+ds_\perp^2,
$$

where $\kappa$ is the surface gravity. Repeating the Euclidean smoothness argument gives

$$
T_H=\frac{\kappa}{2\pi}.
$$

The analogy is deep but not identical. The Unruh effect occurs in flat spacetime and depends on accelerated observers. Hawking radiation involves a black-hole horizon and radiation reaching infinity. Still, the near-horizon Rindler structure is why the same temperature formula appears.

## What is and is not thermal

The Minkowski vacuum is not a thermal state with respect to inertial time translations. It is the ground state of the inertial Hamiltonian. It becomes thermal only after restricting to a wedge and using boost time.

More precisely:

| Statement | True? | Comment |
|---|---:|---|
| The full Minkowski vacuum is thermal for inertial observers. | No | It is the inertial vacuum. |
| A uniformly accelerated detector clicks thermally. | Yes | With $T=a/(2\pi)$. |
| The right-wedge reduced state is thermal for Rindler time. | Yes | $\rho_R=Z^{-1}e^{-2\pi K}$. |
| The Rindler horizon is a curvature singularity. | No | It is a coordinate/observer horizon. |
| The Unruh effect requires gravity. | No | It occurs in flat spacetime. |

This table is a useful antidote to several popular but misleading summaries of the effect.

## Common pitfalls

**Saying acceleration creates particles absolutely.** The accelerated detector response is real, but particle number depends on the time flow and observables used.

**Confusing Rindler and Minkowski Hamiltonians.** The Rindler thermal state is thermal with respect to boost time, not inertial time.

**Forgetting the left wedge.** The right wedge is thermal because the Minkowski vacuum entangles right- and left-wedge degrees of freedom.

**Thinking the Rindler horizon is a physical wall.** It is a causal boundary for a class of observers, not a singular surface in Minkowski spacetime.

**Using $T=a/(2\pi)$ without units.** In ordinary units, $T=\hbar a/(2\pi c k_B)$.

**Assuming the effect is large in everyday accelerations.** The temperature is tiny for ordinary accelerations; direct laboratory observation is difficult.

## Relations to other pages

This page applies [Bogoliubov Transformations](/spacetime-gravity-holography/qft-in-curved-spacetime/bogoliubov-transformations/) and [Particle Creation](/spacetime-gravity-holography/qft-in-curved-spacetime/particle-creation/) to the Rindler wedge. It uses the horizon language of [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/).

The Hawking-radiation page will reuse the near-horizon Rindler argument, replacing acceleration $a$ by black-hole surface gravity $\kappa$. Later holography pages use the same modular-Hamiltonian and wedge-restriction ideas in entanglement wedges and thermal density matrices.

## Research status

The Unruh effect is a standard consequence of relativistic QFT. The Bisognano–Wichmann theorem gives a precise algebraic version: the vacuum restricted to a Rindler wedge is a KMS state for Lorentz boosts.

Active work concerns refinements: detector modeling, finite-time acceleration, interactions, analogue systems, experimental observability, and the role of modular flow in general regions. The core result, however, is not speculative.

## Exercises

### Exercise 1: Rindler metric

Starting with

$$
t=\rho\sinh\eta,
\qquad
x=\rho\cosh\eta,
$$

show that $ds^2=dt^2-dx^2$ becomes

$$
ds^2=\rho^2d\eta^2-d\rho^2.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
dt=\sinh\eta\,d\rho+\rho\cosh\eta\,d\eta,
$$

$$
dx=\cosh\eta\,d\rho+\rho\sinh\eta\,d\eta.
$$

Then

$$
dt^2-dx^2
=(\sinh^2\eta-\cosh^2\eta)d\rho^2
+\rho^2(\cosh^2\eta-\sinh^2\eta)d\eta^2.
$$

The cross terms cancel and $\cosh^2\eta-\sinh^2\eta=1$, so

$$
ds^2=\rho^2d\eta^2-d\rho^2.
$$

</details>

### Exercise 2: Proper acceleration of a Rindler observer

For the worldline

$$
t=\rho_0\sinh\eta,
\qquad
x=\rho_0\cosh\eta,
$$

show that the proper acceleration is $a=1/\rho_0$.

<details><summary><strong>Solution</strong></summary>

Along fixed $\rho=\rho_0$, the line element is

$$
d\tau^2=\rho_0^2d\eta^2,
$$

so $\tau=\rho_0\eta$. Therefore

$$
t=\rho_0\sinh(\tau/\rho_0),
\qquad
x=\rho_0\cosh(\tau/\rho_0).
$$

The four-velocity is

$$
U^\mu=(\cosh(\tau/\rho_0),\sinh(\tau/\rho_0)),
$$

and the four-acceleration is

$$
A^\mu=(\rho_0^{-1}\sinh(\tau/\rho_0),
\rho_0^{-1}\cosh(\tau/\rho_0)).
$$

With mostly-minus signature,

$$
A^\mu A_\mu=-\rho_0^{-2}.
$$

The proper acceleration magnitude is therefore

$$
a=\sqrt{-A^\mu A_\mu}=1/\rho_0.
$$

</details>

### Exercise 3: Euclidean period and temperature

Use the Euclidean Rindler metric

$$
ds_E^2=d\rho^2+\rho^2d\eta_E^2
$$

to derive $T_U=a/(2\pi)$ for an observer with $\eta=a\tau$.

<details><summary><strong>Solution</strong></summary>

The metric is the flat Euclidean plane in polar coordinates. Smoothness at $\rho=0$ requires the angular coordinate to have period

$$
\eta_E\sim\eta_E+2\pi.
$$

Since $\eta=a\tau$, the Euclidean proper time has period

$$
\tau_E\sim\tau_E+2\pi/a.
$$

A thermal Euclidean time circle has period $\beta=1/T$. Therefore

$$
T_U=1/\beta=a/(2\pi).
$$

</details>

### Exercise 4: Thermal density matrix from entanglement

Suppose the Minkowski vacuum has the schematic two-mode form

$$
|0_M\rangle=\sqrt{1-q}\sum_{n=0}^\infty q^{n/2}|n_R\rangle|n_L\rangle,
\qquad
0<q<1.
$$

Trace over the left wedge and show that the right-wedge density matrix is thermal.

<details><summary><strong>Solution</strong></summary>

The density matrix is

$$
|0_M\rangle\langle0_M|
=(1-q)\sum_{n,m}q^{(n+m)/2}
|n_R\rangle|n_L\rangle
\langle m_R|\langle m_L|.
$$

Tracing over left states gives $\langle m_L|n_L\rangle=\delta_{mn}$, hence

$$
\rho_R=(1-q)\sum_{n=0}^\infty q^n|n_R\rangle\langle n_R|.
$$

If $q=e^{-\beta\Omega}$, this is

$$
\rho_R=(1-e^{-\beta\Omega})
\sum_{n=0}^\infty e^{-\beta\Omega n}|n_R\rangle\langle n_R|,
$$

which is the thermal oscillator density matrix at inverse temperature $\beta$.

For Rindler modes, $q=e^{-2\pi\Omega}$ with respect to dimensionless boost time, giving $\beta=2\pi$ for the boost Hamiltonian.

</details>

## References

- S. A. Fulling, “Nonuniqueness of canonical field quantization in Riemannian space-time,” *Physical Review D* **7** (1973) 2850.
- P. C. W. Davies, “Scalar production in Schwarzschild and Rindler metrics,” *Journal of Physics A* **8** (1975) 609.
- W. G. Unruh, “Notes on black-hole evaporation,” *Physical Review D* **14** (1976) 870.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- L. C. B. Crispino, A. Higuchi, and G. E. A. Matsas, “The Unruh effect and its applications,” *Reviews of Modern Physics* **80** (2008) 787.
- R. Haag, *Local Quantum Physics*, 2nd ed., Springer, 1996.

## Version history

- 2026-07-01: Added a polished page on the Unruh effect, Rindler wedges, detector response, and the thermal character of wedge-restricted vacuum states.
