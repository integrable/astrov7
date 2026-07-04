---
title: "Quantum Phase Transitions"
description: "Explains zero-temperature phase transitions, gap closing, quantum critical scaling, dynamical exponents, and finite-temperature quantum critical fans."
sidebar:
  label: "Quantum Phase Transitions"
  order: 9
level: Graduate
status: "Polished draft"
source: "Sachdev; Wilson–Kogut; Zinn-Justin; Fradkin; Altland–Simons; Shifman."
topics:
  - quantum phase transitions
  - quantum critical points
  - gap closing
  - dynamical exponent
  - quantum critical fan
  - finite-size scaling
  - universality
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - quantum-phase-transitions
  - critical-phenomena
  - renormalization-group
researchStatus:
  established:
    - "A continuous quantum phase transition is a zero-temperature critical point where the infinite-volume ground-state structure changes and a correlation length, correlation time, or gap scale becomes singular."
  active:
    - "Many strongly coupled quantum critical points, including deconfined criticality, non-Fermi-liquid criticality, and sign-problem regimes, remain active research areas where the correct low-energy theory and scaling data can be subtle."
---

## Summary

A **quantum phase transition** is a phase transition at zero temperature driven by changing a parameter in the Hamiltonian or action, not by thermal fluctuations. The control parameter may be a coupling, mass, pressure, magnetic field, density, theta angle, or lattice ratio. At the critical value, the infinite-volume ground state changes nonanalytically.

For a continuous quantum phase transition, the basic scaling picture is

$$
\xi\sim |g-g_c|^{-\nu},
\qquad
\xi_\tau\sim \xi^z,
\qquad
\Delta\sim \xi_\tau^{-1}\sim |g-g_c|^{z\nu},
$$

where $\xi$ is the spatial correlation length, $\xi_\tau$ is the correlation time, $\Delta$ is the characteristic gap, $z$ is the dynamical critical exponent, and $\nu$ is the correlation-length exponent. For a relativistic critical point, usually $z=1$. For many-body systems, Lifshitz points, metallic criticality, and dissipative systems, $z$ can be different.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic zero-temperature quantum critical point with a finite-temperature quantum critical fan above it.](/figures/nonperturbative-qft/quantum-critical-fan.svg)

<figcaption>

A continuous quantum phase transition at $g=g_c$, $T=0$. Away from the critical point, the low-temperature physics is controlled by the nearby gapped or ordered phases. Above the scale $T\sim |g-g_c|^{z\nu}$, the system enters a quantum critical regime controlled by the zero-temperature fixed point. Dashed curves are crossovers, not necessarily thermodynamic phase boundaries.

</figcaption>
</figure>

The word “quantum” is not ornamental. Thermal transitions are governed by thermal fluctuations in a statistical ensemble. Quantum phase transitions occur even in the ground state. Their Euclidean path integrals look like classical statistical systems in one extra time direction, but the extra direction can scale differently from space.

## Prerequisites

Read [Phase Diagrams](/nonperturbative-qft/vacuum-structure-phases/phase-diagrams/) first. You should also know [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), and [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/).

For this page, a “gap” means the energy difference between the ground state and the lowest state that couples to the relevant long-distance channel. In a finite volume there is always a finite-size spectrum; the question is how the low-energy scales behave as $L\to\infty$.

## Core idea

Let a Hamiltonian depend on a parameter $g$:

$$
H(g)=H_c+(g-g_c)\int d^D x\,\mathcal O_g(x)+\cdots.
$$

The zero-temperature phases on the two sides of $g_c$ may have different symmetry realization, topological order, confinement behavior, gap structure, or low-energy excitations. A quantum phase transition occurs when the infinite-volume ground-state data cannot be continued smoothly through $g_c$.

There are two common mechanisms.

| Type | Ground-state behavior | Low-energy diagnostic |
|---|---|---|
| First-order quantum transition | Competing ground-state energy densities cross. | Discontinuous derivative of $e_0(g)$; finite-volume avoided crossing or exponentially small splitting. |
| Continuous quantum transition | One or more length and time scales diverge. | Gap closes as $\Delta\sim |g-g_c|^{z\nu}$; correlators show scaling. |

Here

$$
e_0(g)=\lim_{L\to\infty}\frac{E_0(g,L)}{L^D}
$$

is the ground-state energy density. A first-order transition may have a finite correlation length on both sides. A continuous transition is controlled by a scale-invariant long-distance theory.

The nonperturbative content is that the transition is not determined by a small fluctuation calculation around one vacuum. The light degrees of freedom at the critical point may be collective modes, defects, gauge fields, emergent fractionalized particles, or operators of a CFT.

## Setup and conventions

We use $D$ for spatial dimension and $d=D+1$ for Lorentzian spacetime dimension. A zero-temperature quantum problem can be written as the $\beta\to\infty$ limit of

$$
Z(\beta,g)=\operatorname{Tr}e^{-\beta H(g)}.
$$

In a Euclidean path integral, $\beta$ is the size of the imaginary-time circle. A quantum critical point is therefore a critical point in spacetime, not merely in space. When the low-energy theory is local and scale invariant with dynamical exponent $z$, the scaling transformation is

$$
\mathbf x\mapsto b\mathbf x,
\qquad
\tau\mapsto b^z\tau.
$$

A tuning parameter $r=g-g_c$ has RG eigenvalue $y_r=1/\nu$, so

$$
r\mapsto b^{1/\nu}r.
$$

Temperature has scaling dimension $z$ because it is inverse Euclidean time:

$$
T\mapsto b^z T.
$$

We set $k_B=1$. Additive constants in the ground-state energy are physically irrelevant unless derivatives, defects, or gravity-like couplings are under discussion.

## Gap closing and correlation time

For a continuous quantum phase transition, the gap scale vanishes. The intuitive reason is simple: a finite gap defines a finite correlation time. If all excitations stay gapped and no topological or symmetry-protected obstruction appears, the ground state is usually stable under small local perturbations.

Let $\Delta(g)$ be the lowest characteristic energy scale in the critical channel. Then

$$
\xi_\tau\sim \Delta^{-1}.
$$

Anisotropic scaling gives

$$
\xi_\tau\sim \xi^z,
$$

so

$$
\Delta\sim \xi^{-z}
\sim |g-g_c|^{z\nu}.
$$

At a relativistic fixed point, $z=1$ and energy scales like inverse length. At a Lifshitz point with dispersion $\omega\sim k^z$, $z$ is the power relating frequency and momentum. In metallic or dissipative systems, the relation can be more subtle because low-energy modes may live on a Fermi surface or couple to a bath.

The finite-size version at criticality is

$$
\Delta_L(g_c)\sim L^{-z}.
$$

This is one of the most practical diagnostics in numerical Hamiltonian studies: tune $g$ until spectra at different $L$ show the scaling expected from one value of $z$.

## Euclidean quantum-to-classical mapping

A $D$-dimensional quantum system at zero temperature maps to a Euclidean statistical problem with $D$ spatial directions and one imaginary-time direction. If the critical scaling is relativistic, the Euclidean critical theory is effectively isotropic in $D+1$ dimensions after rescaling the velocity.

This gives the useful but dangerous slogan:

$$
D\text{-dimensional quantum criticality}
\quad\leftrightarrow\quad
(D+1)\text{-dimensional classical criticality}.
$$

The dangerous part is that the extra dimension is imaginary time, not an ordinary microscopic spatial direction. Its extent is finite at nonzero temperature, its boundary conditions depend on statistics and traces, and its scaling may be anisotropic:

$$
D+z
$$

is often the effective scaling dimension for hyperscaling estimates, not literally $D+1$ unless $z=1$.

For example, the singular part of the zero-temperature free-energy density often scales as

$$
f_s(r)\sim \xi^{-(D+z)}
\sim |r|^{\nu(D+z)},
$$

when hyperscaling holds. Hyperscaling can fail above the upper critical dimension, in systems with dangerously irrelevant couplings, or in systems with hyperscaling violation.

## Scaling of correlation functions

Let $\mathcal O$ be a scaling operator at the quantum critical point with scaling dimension $\Delta_{\mathcal O}$. Its Euclidean two-point function obeys

$$
\langle\mathcal O(\mathbf x,\tau)\mathcal O(0,0)\rangle
=b^{-2\Delta_{\mathcal O}}
\langle\mathcal O(\mathbf x/b,\tau/b^z)\mathcal O(0,0)\rangle
$$

at criticality. Choosing $b=|\mathbf x|$ gives the equal-time power law

$$
\langle\mathcal O(\mathbf x,0)\mathcal O(0,0)\rangle
\sim \frac{1}{|\mathbf x|^{2\Delta_{\mathcal O}}}.
$$

Away from criticality, the scaling form becomes

$$
\langle\mathcal O(\mathbf x,\tau)\mathcal O(0,0)\rangle_c
=b^{-2\Delta_{\mathcal O}}
F_{\mathcal O}\left(
\frac{\mathbf x}{b},\frac{\tau}{b^z},rb^{1/\nu},Tb^z
\right).
$$

This formula contains the three main regimes:

- at $r=0,T=0$, scale-invariant quantum critical behavior;
- at $r\neq0,T=0$, massive or ordered behavior controlled by $\xi$ and $\Delta$;
- at $T\neq0$, finite-temperature crossover controlled by the thermal time $\beta=1/T$.

## The quantum critical fan

At nonzero temperature, imaginary time is compact:

$$
0\le\tau<\beta=1/T.
$$

The system can no longer probe correlation times much longer than $\beta$. Near a continuous quantum critical point, compare the thermal scale $T$ with the zero-temperature gap scale

$$
\Delta(g)\sim |g-g_c|^{z\nu}.
$$

The crossover into the quantum critical regime occurs when

$$
T\gtrsim \Delta(g),
$$

or equivalently

$$
T\sim |g-g_c|^{z\nu}.
$$

This creates the fan-shaped region in the figure. Inside the fan, observables are controlled by the critical fixed point, but with $T$ acting as the infrared cutoff. For example, a correlation length at $g=g_c$ scales as

$$
\xi_T\sim T^{-1/z}.
$$

The fan boundaries are usually crossovers, not true thermodynamic transitions. A separate finite-temperature transition may occur in the ordered phase when the symmetry and dimension allow it, but it is not automatic. This is a classic place where a pretty drawing can accidentally lie. Draw the fan with dashed crossover curves unless there is a genuine finite-temperature critical line.

## First-order quantum transitions

Not every quantum phase transition is continuous. At a first-order quantum transition, the ground-state energy density has a kink:

$$
\left.\frac{\partial e_0}{\partial g}\right|_{g_c^-}
\neq
\left.\frac{\partial e_0}{\partial g}\right|_{g_c^+}.
$$

If $g$ couples to $\mathcal O_g$, then the derivative is the ground-state expectation value of $\mathcal O_g$ up to sign and normalization. The discontinuity signals that the two ground states have different local or extended observable data.

In finite volume, exact level crossings may be forbidden when the states have the same quantum numbers, so the transition appears as an avoided crossing. The minimum splitting often becomes exponentially small in volume for a first-order transition:

$$
\Delta_L^{\rm min}\sim e^{-cL^D}
$$

in many simple cases. This should not be confused with critical scaling $L^{-z}$.

First-order quantum transitions can have domain walls, hysteresis, metastability, and tunneling. Their finite-temperature continuations can become first-order surfaces or terminate at critical endpoints, depending on the theory.

## Examples and universality classes

The following examples are meant as orientation, not as complete model pages.

| Example | Tuning parameter | Critical data |
|---|---|---|
| Transverse-field Ising chain | ratio of transverse field to exchange coupling | $D=1$, $z=1$, critical theory is the two-dimensional Ising CFT. |
| Relativistic scalar theory | renormalized mass parameter | Wilson–Fisher or Gaussian criticality, depending on dimension and interactions. |
| Bose–Hubbard model | hopping to repulsion ratio, chemical potential | Mott–superfluid transitions, with relativistic tips and density-driven nonrelativistic transitions. |
| Antiferromagnets | pressure, coupling ratio, field, frustration | O($N$) criticality in some regimes; more exotic criticality in others. |
| Topological band transitions | mass parameter in a Dirac Hamiltonian | gap closing changes topological response; interacting versions can be subtler. |
| Gauge-theory transitions | matter content, temperature, theta angle, compactification scale | confinement, screening, center realization, line operators, and anomaly constraints may be central. |

Universality means that different microscopic systems can share the same critical fixed point. The fixed point determines scaling dimensions, exponents, universal ratios, and finite-size spectra. The nonuniversal data include the microscopic value of $g_c$, the velocity, and the precise shape of crossover lines.

## Beyond the local order parameter picture

Many quantum phase transitions fit the Landau–Ginzburg picture: choose an order parameter, write an effective action, tune its mass term, and study the critical fixed point. But important nonperturbative examples do not fit this template cleanly.

A transition between two gapped topological phases can be driven by a gap closing without a local symmetry-breaking order parameter. A confinement–deconfinement transition may be diagnosed by line operators or center symmetry. A deconfined quantum critical point can have emergent gauge fields and fractionalized degrees of freedom at criticality, while the neighboring phases are described by different order parameters. A transition in a system with a Fermi surface can involve a continuum of gapless modes before the critical point is reached.

The right question is therefore not always “which field condenses?” Sometimes it is:

$$
\text{which low-energy operators, defects, symmetries, and anomalies become visible at criticality?}
$$

That question is exactly why quantum phase transitions belong in Nonperturbative QFT rather than being treated as a decorative add-on to perturbation theory.

## Common pitfalls

**Assuming a finite-size gap means the transition is absent.** Continuous quantum critical points have $\Delta_L\sim L^{-z}$ at criticality. First-order transitions may have exponentially small avoided-crossing gaps. Both require finite-size scaling.

**Forgetting the dynamical exponent.** A $D$-dimensional quantum transition is not automatically the same as a $(D+1)$-dimensional isotropic classical transition. The scaling of time is governed by $z$.

**Confusing the quantum critical fan with a phase.** The fan is often a crossover regime controlled by the quantum critical fixed point. It need not be separated from neighboring finite-temperature regimes by true thermodynamic transitions.

**Assuming every continuous transition has a simple local order parameter.** Topological, gauge-theoretic, and deconfined transitions may require line operators, emergent fields, or anomaly constraints.

**Using perturbation theory around one side as though it controls the critical point.** The critical degrees of freedom may be invisible in weak perturbation theory around either adjacent phase.

**Ignoring dangerously irrelevant couplings.** A coupling can be irrelevant at the critical fixed point but still determine the ordered-phase spectrum, amplitude ratios, or crossover scales.

**Equating zero-temperature and finite-temperature phase diagrams.** A zero-temperature quantum critical point can control finite-temperature crossovers even when no finite-temperature phase transition exists.

## Relations to other pages

This page follows [Phase Diagrams](/nonperturbative-qft/vacuum-structure-phases/phase-diagrams/) and uses its language of phases, boundaries, crossovers, and diagnostics. It also relies on [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) because finite-size scaling is one of the main ways quantum phase transitions are detected.

The pages [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) and [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) explain the simplest broken-symmetry phases adjacent to quantum critical points. Later chapters on [Order Parameters and Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/), Lattice Field Theory, Large-N Methods, Exact and Low-Dimensional Models, and Confinement will return to quantum phase transitions in concrete systems.

## Research status

**Established.** The scaling theory of continuous quantum phase transitions, the role of $z$, the quantum-to-classical Euclidean mapping, finite-size scaling, and the quantum critical fan are standard parts of modern QFT and many-body physics.

**Model-dependent.** Identifying the correct critical theory can be difficult. Some systems are controlled by Wilson–Fisher fixed points, some by Gaussian or large-$N$ fixed points, some by CFTs known from exact methods, and some by strongly coupled fixed points accessible only numerically or indirectly.

**Active.** Current research includes deconfined quantum criticality, conformal windows of gauge theories, critical metals and non-Fermi liquids, real-time quantum critical dynamics, quantum phase transitions with higher-form symmetries or anomalies, and sign-problem-limited phase diagrams.

## Exercises

### Exercise 1: gap exponent from correlation length

Assume a continuous quantum phase transition has

$$
\xi\sim |g-g_c|^{-\nu},
\qquad
\xi_\tau\sim \xi^z.
$$

Show that the characteristic gap scales as

$$
\Delta\sim |g-g_c|^{z\nu}.
$$

<details><summary><strong>Solution</strong></summary>

The characteristic gap is the inverse correlation time:

$$
\Delta\sim \xi_\tau^{-1}.
$$

Using $\xi_\tau\sim\xi^z$ gives

$$
\Delta\sim \xi^{-z}.
$$

Finally, $\xi\sim |g-g_c|^{-\nu}$ implies

$$
\Delta\sim \left(|g-g_c|^{-\nu}\right)^{-z}
=|g-g_c|^{z\nu}.
$$

</details>

### Exercise 2: finite-size scaling of the gap

At criticality, the only available length scale in a finite box of size $L$ is $L$ itself. Use dynamical scaling to estimate $\Delta_L(g_c)$.

<details><summary><strong>Solution</strong></summary>

At criticality, the infinite-volume correlation length is infinite, but finite volume cuts it off at $L$. Dynamical scaling says energy scales as inverse time and time scales as length to the power $z$. Therefore

$$
\Delta_L(g_c)\sim L^{-z}.
$$

This is a basic diagnostic of a continuous quantum critical point. It differs sharply from the exponentially small avoided-crossing scale often associated with finite-volume first-order transitions.

</details>

### Exercise 3: the shape of the quantum critical fan

Given $\Delta(g)\sim |g-g_c|^{z\nu}$, estimate the crossover curves separating the low-temperature phase-dominated regimes from the quantum critical regime.

<details><summary><strong>Solution</strong></summary>

The crossover occurs when the thermal energy scale $T$ becomes comparable to the zero-temperature gap scale:

$$
T\sim \Delta(g).
$$

Therefore

$$
T\sim |g-g_c|^{z\nu}.
$$

These curves are usually crossovers, not true thermodynamic phase boundaries. Inside them, the temperature is the dominant infrared cutoff and observables are controlled by quantum critical scaling functions.

</details>

### Exercise 4: why $D+1$ is not always the right phrase

Explain why a $D$-dimensional quantum critical point with $z=2$ should not simply be called a $(D+1)$-dimensional isotropic classical critical point.

<details><summary><strong>Solution</strong></summary>

The Euclidean path integral has $D$ spatial directions and one imaginary-time direction, but the scaling is anisotropic:

$$
\mathbf x\mapsto b\mathbf x,
\qquad
\tau\mapsto b^2\tau.
$$

Thus the time direction does not scale like an ordinary spatial direction. In hyperscaling estimates, the effective scaling of spacetime volume is $b^{D+z}=b^{D+2}$, not $b^{D+1}$. Calling the system $(D+1)$-dimensional can be useful as a path-integral mnemonic, but it hides the dynamical exponent.

</details>

### Exercise 5: first-order or continuous?

A sequence of finite-size spectra near $g_c$ has a minimum gap that scales approximately as $e^{-cL^D}$. Another sequence has a minimum gap scaling as $L^{-1}$. Which behavior is more suggestive of a first-order transition, and which is more suggestive of a continuous transition with $z=1$?

<details><summary><strong>Solution</strong></summary>

An exponentially small minimum gap $e^{-cL^D}$ is suggestive of a first-order transition, where two competing extensive states mix weakly in finite volume. A power-law finite-size gap $L^{-z}$ is suggestive of a continuous quantum critical point. If the observed scaling is $L^{-1}$, it is consistent with $z=1$ criticality, though one should still check other observables and finite-size corrections.

</details>

## References

- S. Sachdev, *Quantum Phase Transitions*, for the standard theory of zero-temperature criticality, scaling, and quantum critical regimes.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” for the RG foundation of fixed points, critical surfaces, and universality.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field theory, renormalization, and critical phenomena.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for quantum ordered and disordered phases, gauge-theory phase diagrams, and topological phases.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for many-body path integrals, broken symmetry, RG, topological field theory, and quantum matter examples.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for phases of gauge theories, confinement, anomalies, solitons, and lower-dimensional models.

## Version history

- **2026-06-26:** Initial polished page.
