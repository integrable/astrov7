---
title: "Particle Creation"
description: "A derivation-focused introduction to particle creation in time-dependent backgrounds, using Bogoliubov coefficients, in/out vacua, adiabaticity, and cosmological mode equations."
sidebar:
  label: "Particle Creation"
  order: 60
level: Graduate
status: "Polished draft"
source: "Birrell and Davies 1982, chs. 3–5; Parker and Toms 2009; Fulling 1989; Wald 1994; Mukhanov and Winitzki 2007"
topics:
  - particle creation
  - curved spacetime
  - Bogoliubov transformations
  - in and out vacua
  - cosmological particle production
canonicalTopics:
  - particle-creation
  - in-out-vacua
  - time-dependent-background
  - adiabatic-vacuum
  - cosmological-particle-creation
researchStatus:
  established:
    - "Time-dependent backgrounds can mix positive- and negative-frequency modes of free fields, producing particles relative to an out-basis even when the state begins as an in-vacuum."
  active:
    - "Particle number is basis-dependent; robust physical statements often require detector models, asymptotic regions, or renormalized local observables such as the stress tensor."
---

## Summary

**Particle creation** in curved spacetime is the statement that a state which is empty with respect to one natural set of modes need not be empty with respect to another. The cleanest setup has an early-time positive-frequency basis $u_k^{\mathrm{in}}$ and a late-time positive-frequency basis $u_k^{\mathrm{out}}$. The same exact solution can be expanded as

$$
u_k^{\mathrm{in}}
=\alpha_k u_k^{\mathrm{out}}
+\beta_k u_k^{\mathrm{out}*}.
$$

If $\beta_k\neq0$, the in-vacuum contains out-particles:

$$
\langle0_{\mathrm{in}}|N_k^{\mathrm{out}}|0_{\mathrm{in}}\rangle
=|\beta_k|^2.
$$

The mechanism is not mysterious: a time-dependent background turns each field mode into a parametric oscillator. Positive frequency at early time evolves into a mixture of positive and negative frequency at late time.

The caveat is equally important. Particle number is not a local invariant of QFT. It is a useful observable when a spacetime has preferred asymptotic regions, preferred timelike symmetries, or a detector prescription. In a generic time-dependent spacetime, the local field algebra and renormalized stress tensor are more invariant than any one particle count.

## Prerequisites

Read [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/), [Mode Expansions in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/mode-expansions-in-curved-spacetime/), and [Bogoliubov Transformations](/spacetime-gravity-holography/qft-in-curved-spacetime/bogoliubov-transformations/) first.

You should know the Klein–Gordon inner product, positive-frequency mode bases, and the formula that a nonzero Bogoliubov coefficient $\beta$ gives particle occupation $|\beta|^2$.

## Core idea

In ordinary flat-space QFT, time-translation symmetry lets us define positive frequency once and for all. In a time-dependent geometry, the mode equation changes with time, so the notion of positive frequency can change.

The essential chain is

$$
\text{time-dependent geometry}
\Longrightarrow
\text{time-dependent oscillator frequency}
\Longrightarrow
\text{positive/negative frequency mixing}
\Longrightarrow
\text{particle creation}.
$$

The same logic appears in several settings:

| Setting | What changes | Natural particle comparison |
|---|---|---|
| Expanding universe | Scale factor $a(t)$ | Early-time versus late-time modes. |
| External electric field | Gauge potential or electric background | Past versus future charged-particle modes. |
| Moving mirror or boundary | Boundary condition | Incoming versus outgoing radiation. |
| Black-hole collapse | Null-coordinate relation near horizon | Past-null-infinity versus future-null-infinity modes. |

The details differ, but the algebra is the same: compute $\alpha$ and $\beta$ by matching exact solutions or their asymptotics.

## Setup and conventions

Take a real scalar field obeying

$$
P\phi=0,
\qquad
P=\Box_g+m^2+\xi R.
$$

Assume the spacetime has sufficiently simple early and late regions that one can define positive-frequency bases

$$
\{u_i^{\mathrm{in}}\},
\qquad
\{u_j^{\mathrm{out}}\}.
$$

The field has two expansions:

$$
\widehat\phi
=\sum_i\left(a_i^{\mathrm{in}}u_i^{\mathrm{in}}
+a_i^{\mathrm{in}\dagger}u_i^{\mathrm{in}*}\right)
=\sum_j\left(a_j^{\mathrm{out}}u_j^{\mathrm{out}}
+a_j^{\mathrm{out}\dagger}u_j^{\mathrm{out}*}\right).
$$

The vacua are

$$
a_i^{\mathrm{in}}|0_{\mathrm{in}}\rangle=0,
\qquad
a_j^{\mathrm{out}}|0_{\mathrm{out}}\rangle=0.
$$

The relation between mode bases is

$$
u_j^{\mathrm{out}}
=\sum_i\left(
\alpha_{ji}u_i^{\mathrm{in}}+
\beta_{ji}u_i^{\mathrm{in}*}
\right),
$$

and therefore

$$
a_j^{\mathrm{out}}
=\sum_i\left(
\alpha_{ji}^*a_i^{\mathrm{in}}
-\beta_{ji}^*a_i^{\mathrm{in}\dagger}
\right).
$$

The out-particle number in the in-vacuum is

$$
\langle0_{\mathrm{in}}|
 a_j^{\mathrm{out}\dagger}a_j^{\mathrm{out}}
|0_{\mathrm{in}}\rangle
=\sum_i|\beta_{ji}|^2.
$$

This is the invariant calculation once the two positive-frequency bases have been specified.

## Time-dependent oscillator analogy

Many particle-creation calculations reduce to the oscillator equation

$$
\chi_k''+\Omega_k(\eta)^2\chi_k=0,
$$

where primes denote derivatives with respect to a convenient time coordinate, often conformal time $\eta$.

If

$$
\Omega_k(\eta)\to \omega_{\mathrm{in}}
\quad\text{as }\eta\to-\infty,
\qquad
\Omega_k(\eta)\to \omega_{\mathrm{out}}
\quad\text{as }\eta\to+\infty,
$$

then natural asymptotic modes are

$$
\chi_k^{\mathrm{in}}\sim
\frac{e^{-i\omega_{\mathrm{in}}\eta}}{\sqrt{2\omega_{\mathrm{in}}}},
\qquad
\chi_k^{\mathrm{out}}\sim
\frac{e^{-i\omega_{\mathrm{out}}\eta}}{\sqrt{2\omega_{\mathrm{out}}}}.
$$

An exact solution chosen to be positive frequency in the past will generally behave in the future as

$$
\chi_k^{\mathrm{in}}\sim
\alpha_k\frac{e^{-i\omega_{\mathrm{out}}\eta}}{\sqrt{2\omega_{\mathrm{out}}}}
+\beta_k\frac{e^{+i\omega_{\mathrm{out}}\eta}}{\sqrt{2\omega_{\mathrm{out}}}}.
$$

The Wronskian normalization gives

$$
|\alpha_k|^2-|\beta_k|^2=1.
$$

Thus $|\beta_k|^2$ is not an arbitrary decoration. It is fixed by matching a normalized solution through the time-dependent region.

## Adiabatic evolution

Particle creation is small when the background changes slowly compared with the instantaneous frequency. A rough adiabaticity parameter is

$$
\epsilon_k(\eta)=\left|\frac{\Omega_k'}{\Omega_k^2}\right|.
$$

When

$$
\epsilon_k\ll1,
$$

one can approximate a positive-frequency solution by a WKB form

$$
\chi_k(\eta)
\simeq
\frac{1}{\sqrt{2\Omega_k(\eta)}}
\exp\left(-i\int^\eta d\eta'\,\Omega_k(\eta')\right).
$$

This approximation carries little positive/negative frequency mixing. Particle creation becomes significant when adiabaticity fails, for example near rapid changes of the background, near turning points where $\Omega_k^2$ becomes small, or for long-wavelength modes in an expanding universe.

The phrase “adiabatic vacuum” refers to a state chosen by matching to a high-order WKB prescription. It is useful, but it is a prescription, not a universal law of nature.

## Cosmological scalar modes

For a spatially flat Robertson–Walker metric in conformal time,

$$
ds^2=a(\eta)^2(d\eta^2-d\mathbf x^2),
$$

a scalar field can be expanded as

$$
\widehat\phi(\eta,\mathbf x)
=\int \frac{d^{3}\mathbf k}{(2\pi)^3}
\left(
 a_{\mathbf k}u_k(\eta)e^{i\mathbf k\cdot\mathbf x}
+a_{\mathbf k}^\dagger u_k^*(\eta)e^{-i\mathbf k\cdot\mathbf x}
\right).
$$

In four spacetime dimensions define

$$
\chi_k=a u_k.
$$

Then the mode equation is

$$
\chi_k''+\Omega_k(\eta)^2\chi_k=0,
$$

with

$$
\Omega_k^2
=k^2+a^2m^2+(\xi-1/6)a^2R.
$$

For a massless conformally coupled scalar, $m=0$ and $\xi=1/6$, this becomes

$$
\chi_k''+k^2\chi_k=0.
$$

There is no particle creation in conformally flat cosmology for this special field, because the problem reduces exactly to the flat-space oscillator. This is a useful check: expansion alone is not enough; expansion must affect the relevant mode equation.

For a minimally coupled scalar, $\xi=0$, long-wavelength modes can be strongly affected by expansion. In inflationary applications, the same mathematics underlies the amplification of quantum fluctuations into classical-looking perturbations.

## Energy, number, and what is actually measured

The number $|\beta_k|^2$ answers a precise question: how many out-quanta are present in the in-vacuum, relative to a specified out-mode basis. It does not by itself answer every physical question.

Three related observables should be distinguished:

| Quantity | What it means | Main caveat |
|---|---|---|
| Particle number | Occupation of a chosen out-basis. | Basis-dependent. |
| Detector response | Excitation probability of a localized physical detector. | Detector- and trajectory-dependent. |
| Stress tensor | Local energy, pressure, and flux after renormalization. | Composite operator requiring subtraction. |

In asymptotically static spacetimes, particle number can be operationally sharp: detectors in the far future can count the out-quanta. In a general time-dependent region, particle language may be approximate, while detector response and $\langle T_{\mu\nu}\rangle_{\mathrm{ren}}$ may be the safer objects.

## Example: sudden frequency change

The simplest solvable model is a harmonic oscillator whose frequency jumps from $\omega_i$ to $\omega_f$ at $t=0$. A positive-frequency solution before the jump is

$$
\chi_{\mathrm{in}}(t<0)=\frac{e^{-i\omega_i t}}{\sqrt{2\omega_i}}.
$$

After the jump, write

$$
\chi_{\mathrm{in}}(t>0)
=\alpha\frac{e^{-i\omega_f t}}{\sqrt{2\omega_f}}
+\beta\frac{e^{+i\omega_f t}}{\sqrt{2\omega_f}}.
$$

Continuity of $\chi$ and $\dot\chi$ at $t=0$ gives

$$
\alpha=\frac12\left(\sqrt{\omega_f/\omega_i}
+\sqrt{\omega_i/\omega_f}\right),
\qquad
\beta=\frac12\left(\sqrt{\omega_f/\omega_i}
-\sqrt{\omega_i/\omega_f}\right).
$$

Thus

$$
|\beta|^2=
\frac{(\omega_f-\omega_i)^2}{4\omega_i\omega_f}.
$$

This toy model is deliberately abrupt, so it overproduces high-frequency quanta. Smooth backgrounds suppress high-frequency production when adiabaticity holds.

## Common pitfalls

**Treating particle creation as invariant without specifying the modes.** The statement “particles are created” becomes precise only after defining the in/out particle notions or a detector observable.

**Forgetting the normalization condition.** For bosons, $|\alpha|^2-|\beta|^2=1$ in a single mode. If a calculation violates this, the mode normalization or complex conjugation is wrong.

**Confusing expansion with particle creation.** A massless conformally coupled scalar in a conformally flat spacetime has no particle creation in the conformal vacuum.

**Using instantaneous diagonalization too literally.** Defining particles at every instant by diagonalizing a time-dependent Hamiltonian can produce a rapidly varying, nonunique particle number.

**Ignoring renormalization of energy.** Summing particle energies is not the same as computing the renormalized stress tensor. Vacuum subtraction and curvature counterterms matter.

**Forgetting that beta may describe a density.** In continuum normalization, $|\beta_k|^2$ often appears with delta functions. Use finite volume, wave packets, or densities.

## Relations to other pages

This page applies [Bogoliubov Transformations](/spacetime-gravity-holography/qft-in-curved-spacetime/bogoliubov-transformations/) to time-dependent backgrounds. It prepares the [Unruh Effect](/spacetime-gravity-holography/qft-in-curved-spacetime/unruh-effect/) and Hawking radiation pages, where horizons supply different natural frequency notions.

The discussion of conformally coupled scalars connects to the later stress-tensor and trace-anomaly pages. The distinction between particle number and local energy anticipates renormalized $\langle T_{\mu\nu}\rangle$ in the Stress Tensor and Curved-Space Renormalization chapter.

## Research status

Particle creation for free fields on fixed backgrounds is standard. The in/out Bogoliubov calculation is a mature tool in cosmology, external-field QFT, moving-boundary problems, and black-hole physics.

The subtle issues are interpretive and dynamical: which state is physically prepared, what an actual detector measures, how particle creation backreacts through $\langle T_{\mu\nu}\rangle$, and how the story changes for interacting fields or dynamical quantum gravity.

## Exercises

### Exercise 1: Sudden frequency jump

Derive

$$
|\beta|^2=
\frac{(\omega_f-\omega_i)^2}{4\omega_i\omega_f}
$$

for an oscillator whose frequency jumps suddenly from $\omega_i$ to $\omega_f$.

<details><summary><strong>Solution</strong></summary>

Before the jump,

$$
\chi(t<0)=\frac{e^{-i\omega_i t}}{\sqrt{2\omega_i}}.
$$

After the jump,

$$
\chi(t>0)=\alpha\frac{e^{-i\omega_f t}}{\sqrt{2\omega_f}}
+\beta\frac{e^{+i\omega_f t}}{\sqrt{2\omega_f}}.
$$

Continuity of $\chi$ and $\dot\chi$ at $t=0$ gives

$$
\frac{1}{\sqrt{2\omega_i}}
=\frac{\alpha+\beta}{\sqrt{2\omega_f}},
$$

and

$$
\frac{-i\omega_i}{\sqrt{2\omega_i}}
=\frac{-i\omega_f\alpha+i\omega_f\beta}{\sqrt{2\omega_f}}.
$$

Thus

$$
\alpha+\beta=\sqrt{\omega_f/\omega_i},
\qquad
\alpha-\beta=\sqrt{\omega_i/\omega_f}.
$$

Solving gives

$$
\beta=\frac12\left(\sqrt{\omega_f/\omega_i}
-\sqrt{\omega_i/\omega_f}\right),
$$

so

$$
|\beta|^2
=\frac14\left(\frac{\omega_f}{\omega_i}
+\frac{\omega_i}{\omega_f}-2\right)
=\frac{(\omega_f-\omega_i)^2}{4\omega_i\omega_f}.
$$

</details>

### Exercise 2: Conformal coupling check

For a massless scalar in four spacetime dimensions with $\xi=1/6$, show that the conformal-time mode equation in a spatially flat Robertson–Walker spacetime reduces to

$$
\chi_k''+k^2\chi_k=0.
$$

<details><summary><strong>Solution</strong></summary>

The general rescaled mode equation is

$$
\chi_k''+\left[k^2+a^2m^2+(\xi-1/6)a^2R\right]\chi_k=0.
$$

Setting $m=0$ and $\xi=1/6$ removes the mass and curvature terms. Therefore

$$
\chi_k''+k^2\chi_k=0.
$$

The modes are ordinary plane waves in conformal time, so the conformal vacuum has no cosmological particle creation for this field.

</details>

### Exercise 3: Number from beta coefficients

Suppose

$$
a_j^{\mathrm{out}}
=\sum_i(\alpha_{ji}^*a_i^{\mathrm{in}}
-\beta_{ji}^*a_i^{\mathrm{in}\dagger}).
$$

Show that

$$
\langle0_{\mathrm{in}}|a_j^{\mathrm{out}\dagger}a_j^{\mathrm{out}}|0_{\mathrm{in}}\rangle
=\sum_i|\beta_{ji}|^2.
$$

<details><summary><strong>Solution</strong></summary>

The adjoint is

$$
a_j^{\mathrm{out}\dagger}
=\sum_i(\alpha_{ji}a_i^{\mathrm{in}\dagger}
-\beta_{ji}a_i^{\mathrm{in}}).
$$

In the product $a_j^{\mathrm{out}\dagger}a_j^{\mathrm{out}}$, the only term with nonzero in-vacuum expectation value is

$$
\sum_{ik}\beta_{ji}\beta_{jk}^*
\langle0_{\mathrm{in}}|a_i^{\mathrm{in}}a_k^{\mathrm{in}\dagger}|0_{\mathrm{in}}\rangle.
$$

Using

$$
\langle0_{\mathrm{in}}|a_i^{\mathrm{in}}a_k^{\mathrm{in}\dagger}|0_{\mathrm{in}}\rangle=\delta_{ik},
$$

we obtain

$$
\sum_i|\beta_{ji}|^2.
$$

</details>

### Exercise 4: Adiabatic suppression

Explain why high-frequency modes are usually weakly produced by a smooth background.

<details><summary><strong>Solution</strong></summary>

For large $\Omega_k$, the adiabaticity parameter

$$
\epsilon_k=|\Omega_k'/\Omega_k^2|
$$

is small when the background changes on a fixed smooth time scale. The WKB solution then remains approximately positive frequency:

$$
\chi_k\simeq(2\Omega_k)^{-1/2}
\exp\left(-i\int^\eta \Omega_k d\eta'\right).
$$

Since positive and negative frequencies mix only when the WKB approximation fails, high-frequency modes are weakly produced by smooth time dependence.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 2009.
- V. Mukhanov and S. Winitzki, *Introduction to Quantum Effects in Gravity*, Cambridge University Press, 2007.
- L. Parker, “Particle creation in expanding universes,” *Physical Review Letters* **21** (1968) 562.
- Ya. B. Zel'dovich and A. A. Starobinsky, “Particle production and vacuum polarization in an anisotropic gravitational field,” *Soviet Physics JETP* **34** (1972) 1159.

## Version history

- 2026-07-01: Added a polished page on particle creation from time-dependent backgrounds and Bogoliubov mixing.
