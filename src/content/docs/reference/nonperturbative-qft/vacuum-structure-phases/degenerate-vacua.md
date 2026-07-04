---
title: "Degenerate Vacua"
description: "Explains how multiple infinite-volume vacua arise, why finite volume often hides them, and how sources, tunneling, clustering, and domain walls diagnose vacuum degeneracy."
sidebar:
  label: "Degenerate Vacua"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman, Aspects of Symmetry; Srednicki §§30–31; Schwartz §28; Shifman Chs. 1–2; Zinn-Justin."
topics:
  - degenerate vacua
  - spontaneous symmetry breaking
  - finite volume
  - source selection
  - domain walls
  - cluster decomposition
  - phase coexistence
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - degenerate-vacua
  - spontaneous-symmetry-breaking
  - superselection-sectors
  - domain-walls
researchStatus:
  established:
    - "In local QFT, physically distinct vacua are most sharply defined as infinite-volume pure ground states or phases, not merely as minima of a classical potential."
  active:
    - "In strongly coupled gauge theories and topological phases, deciding which apparent degeneracies are physical can require gauge-invariant observables, line operators, anomaly constraints, and finite-volume scaling rather than a local field VEV alone."
---

## Summary

Degenerate vacua are distinct ground states of the same infinite-volume quantum field theory with the same energy density. They are not merely different classical field configurations. A physical vacuum is a state, and two vacua are physically distinct only if they give different expectation values, correlation functions, boundary responses, spectra of defects, or other gauge-invariant long-distance data.

The basic pattern is already visible in a scalar theory with a $\mathbb Z_2$-symmetric double-well potential. Classically there are two minima, $\phi=+v$ and $\phi=-v$. In finite volume, however, the exact ground state of the quantum theory is usually a symmetric state with $\langle\phi\rangle=0$. The two broken vacua appear only after the thermodynamic limit is taken in a way that selects a phase:

$$
\langle\phi\rangle_+
=\lim_{h\to0^+}\lim_{L\to\infty}\langle\phi\rangle_{L,h},
\qquad
\langle\phi\rangle_-
=\lim_{h\to0^-}\lim_{L\to\infty}\langle\phi\rangle_{L,h}.
$$

Here $h$ is a small source, $L$ is the linear spatial size, and the order of limits is part of the definition. If $h\to0$ is taken first at finite $L$, symmetry usually forces $\langle\phi\rangle_{L,0}=0$.

The important nonperturbative lesson is that vacuum degeneracy is a statement about the global organization of the Hilbert space. Perturbation theory around one minimum can compute local fluctuations in one phase, but it does not by itself decide whether another minimum is a distinct vacuum, a gauge copy, a metastable state, a finite-volume tunneling partner, or a point on a continuous vacuum manifold.

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), especially the source-selected definition of an order parameter. You should also know [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) and [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), because most confusion about degenerate vacua is really confusion about limits.

This page assumes basic familiarity with global symmetries, Euclidean path integrals, and the idea of spontaneous symmetry breaking. It does not assume a detailed study of Goldstone's theorem, instantons, or the effective potential.

## Core idea

A classical potential can have several minima. A quantum field theory can have several vacua. Those are related ideas, but they are not the same idea.

A classical minimum is a configuration. A vacuum is a state. To decide whether there are several vacua, ask what happens to physical observables and finite-energy operations in the infinite-volume theory. If two candidate states differ only by a gauge redundancy, they are not distinct physical vacua. If they differ by a global symmetry that is spontaneously broken, by boundary data at infinity, or by a topological sector that local operators cannot change, they may be distinct vacua or distinct superselection sectors.

For discrete symmetry breaking, the standard mental picture is:

| Regime | What the Hilbert space sees | What a local observer sees |
|---|---|---|
| Finite volume, no source | Often a unique symmetric ground state. | The one-point order parameter vanishes. |
| Finite volume, tiny source | A preferred side of the would-be broken pair. | The order parameter follows the source. |
| Infinite volume, source removed last | Distinct pure phases. | Local correlators cluster around one chosen vacuum. |
| Infinite volume, symmetric mixture | Not a pure broken phase. | One-point functions may vanish while long-range order remains. |

The whole subject is a stern little reminder that limits are physics, not housekeeping.

## Setup and conventions

Work on a spatial torus of linear size $L$ with Hamiltonian $H_L$. Suppose a scalar operator $\mathcal O$ is a candidate order parameter. Add a source $h$ by

$$
H_L(h)=H_L-h\int_{L^{d-1}}d^{d-1}\mathbf x\,\mathcal O(t,\mathbf x),
$$

or, in Euclidean signature,

$$
S_E(h)=S_E-h\int d^dx\,\mathcal O(x).
$$

The finite-volume ground-state energy is $E_0(L,h)$. The vacuum energy density is defined by

$$
\epsilon(h)=\lim_{L\to\infty}\frac{E_0(L,h)}{L^{d-1}},
$$

when the limit exists. A source-selected order parameter is

$$
m(h)=\lim_{L\to\infty}\frac{1}{L^{d-1}}
\left\langle\int_{L^{d-1}}d^{d-1}\mathbf x\,\mathcal O(t,\mathbf x)\right\rangle_{L,h}.
$$

The broken vacua, when they exist, are obtained by approaching $h=0$ from different sides or directions:

$$
m_+=\lim_{h\to0^+}m(h),
\qquad
m_-=\lim_{h\to0^-}m(h).
$$

For a continuous symmetry, $h$ is a vector source in order-parameter space, and the limiting direction of $h$ selects a point on the vacuum manifold.

:::caution[Gauge warning]
A family of classical configurations related by a gauge transformation is not a family of distinct physical vacua. Gauge fixing can make a redundant family look like degeneracy. Physical vacuum structure must be stated in terms of gauge-invariant observables, boundary conditions, spectra, line operators, or symmetry realization.
:::

## Thermodynamic degeneracy versus finite-volume degeneracy

At finite volume, a Hamiltonian with a symmetry usually has energy eigenstates that transform in representations of the symmetry. If the lowest state is unique, it must be invariant under the symmetry. Therefore a symmetry-odd operator has vanishing expectation value:

$$
\langle\Omega_L|\mathcal O|\Omega_L\rangle=0.
$$

This does not rule out spontaneous symmetry breaking. It only says that a finite box cannot contain the full infinite-volume phase structure in a single exact ground-state vector.

For a discrete broken symmetry, one often has two approximate localized states, $|+\rangle_L$ and $|-\rangle_L$, with

$$
{}_L\langle +|\mathcal O|+\rangle_L\simeq +v,
\qquad
{}_L\langle -|\mathcal O|-\rangle_L\simeq -v.
$$

But the exact low-energy eigenstates are closer to symmetric and antisymmetric combinations,

$$
|0\rangle_L\simeq \frac{|+\rangle_L+|-\rangle_L}{\sqrt2},
\qquad
|1\rangle_L\simeq \frac{|+\rangle_L-|-\rangle_L}{\sqrt2},
$$

with a small splitting

$$
\Delta E(L)=E_1(L)-E_0(L).
$$

In quantum mechanics, the analogous splitting is small but nonzero. In QFT with a broken discrete symmetry in spatial volume $L^{d-1}$, the tunneling process has to reorganize a macroscopic region. Semiclassically, the relevant Euclidean configuration contains a domain wall spanning the spatial box, so a typical large-$L$ scaling is

$$
\Delta E(L)\sim A(L)\exp[-\sigma L^{d-1}],
$$

where $\sigma$ is the domain-wall tension and $A(L)$ is a prefactor. The exact scaling is model-dependent, but the physical point is robust: the splitting vanishes in the thermodynamic limit. The two pure broken phases then behave as different vacua.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Finite-volume symmetric and antisymmetric states split into two infinite-volume broken vacua](/figures/nonperturbative-qft/degenerate-vacua-finite-infinite.svg)

<figcaption>

Finite volume often replaces two would-be broken vacua by symmetric and antisymmetric combinations with exponentially small splitting. In the infinite-volume limit the splitting vanishes, a small source selects one side, and the two pure phases become physically distinct vacua.

</figcaption>
</figure>

This is why the phrase “degenerate vacua” usually means **thermodynamic degeneracy**, not necessarily exact degeneracy at finite $L$.

## Pure phases, mixtures, and clustering

A pure vacuum should satisfy cluster decomposition for local observables. Roughly, for widely separated local operators $A(x)$ and $B(y)$,

$$
\lim_{|x-y|\to\infty}
\langle A(x)B(y)\rangle_\Omega
=\langle A(x)\rangle_\Omega\langle B(y)\rangle_\Omega,
$$

when the vacuum is translation invariant and the operators are neutral enough for the limit to exist.

For two broken vacua $|\Omega_+\rangle$ and $|\Omega_-\rangle$ of a $\mathbb Z_2$ theory,

$$
\langle\phi\rangle_+=+v,
\qquad
\langle\phi\rangle_-=-v.
$$

A symmetric mixture can have

$$
\langle\phi\rangle_{\mathrm{mix}}=0,
$$

but still

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_{\mathrm{mix}}=v^2.
$$

The vanishing one-point function in the mixture does not mean the phase is symmetric in the same way as a unique symmetric vacuum. It means the state is not an extremal pure phase. This distinction matters in lattice simulations, finite-temperature statistical mechanics, and any path integral that samples several symmetry-related sectors without a source or boundary condition selecting one.

A useful operational test is this: a pure phase is stable under small local perturbations and has clustering. A mixture can be decomposed into pure phases and typically retains long-distance memory of which phase was chosen.

## Classical minima and quantum vacua

Consider a real scalar field with classical potential

$$
U(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2.
$$

The classical minima are $\phi=\pm v$. Perturbation theory around either minimum gives a massive scalar fluctuation. This is a good local description of either broken phase when the semiclassical approximation is reliable.

But the classical picture can fail or require refinement in several ways.

First, quantum corrections can shift the location of the order parameter. The physical VEV is not exactly the tree-level minimum unless protected by a limit or symmetry.

Second, the exact effective potential is a Legendre transform and is convex in infinite volume. A perturbative double-well effective potential is often best interpreted as a local or branch-wise approximation to the response of pure phases, not as the final global graph of the exact Legendre-transformed potential.

Third, a minimum can be metastable rather than degenerate. A false vacuum is a local minimum with higher energy density than the true vacuum. It can be long-lived, and in practice very important, but it is not a degenerate vacuum.

Fourth, a flat direction can be lifted by quantum effects. Conversely, in supersymmetric or constrained systems, a classical family of vacua may survive as a genuine moduli space. That requires separate analysis.

Finally, in gauge theory, a set of minima related by gauge transformations is a redundancy. The Higgs mechanism is not the spontaneous breaking of a local gauge symmetry as an ordinary physical symmetry. The physical phase must be described by gauge-invariant operators and the spectrum.

## Discrete and continuous degeneracy

Degenerate vacua can be isolated or continuous.

For a broken discrete global symmetry, the vacua are isolated. A $\mathbb Z_2$ theory may have two vacua; a theory with a broken $\mathbb Z_N$ symmetry may have $N$ vacua. Interfaces between isolated vacua are domain walls. If $\Omega_a$ and $\Omega_b$ are two discrete vacua, a field configuration that approaches $\Omega_a$ at one end of space and $\Omega_b$ at the other contains a wall with tension

$$
T_{ab}=\frac{\text{energy}}{\text{area}}.
$$

The existence, tension, and junctions of such walls are physical data of the theory.

For a broken continuous global symmetry $G\to H$, the classical vacuum manifold is often described by

$$
\mathcal M_{\mathrm{vac}}\simeq G/H.
$$

The corresponding QFT has massless Goldstone modes under the usual assumptions. The continuous family is subtler than the discrete case because nearby vacua are connected by long-wavelength Goldstone fluctuations rather than by isolated domain walls. In low spacetime dimensions, infrared fluctuations can prevent continuous spontaneous symmetry breaking; in particular, continuous internal symmetries cannot be spontaneously broken in relativistic $1+1$-dimensional QFT under the standard assumptions of Coleman's theorem.

The practical lesson is that the phrase “many vacua” compresses several different phenomena:

| Type | Typical diagnostic | Typical excitation |
|---|---|---|
| Discrete broken vacua | Nonzero discrete order parameter, domain walls | Kinks or domain walls |
| Continuous broken vacua | Order-parameter direction, Goldstone correlations | Goldstone bosons |
| Topological degeneracy | Extended operators, boundary-condition dependence | Anyons, fluxes, defects, or topological sectors |
| Gauge-copy degeneracy | Gauge-fixed variables only | Not physical degeneracy |
| Metastable minima | Decay rate rather than equal energy | Bounce-mediated decay |

## Degeneracy and superselection

In infinite volume, distinct broken vacua are often superselection sectors for the local observable algebra. A compactly supported local operator can create particles, defects, and finite-energy disturbances in a chosen vacuum, but it cannot flip the order parameter throughout all of space.

For a discrete broken symmetry, the overlap between finite-volume approximations to two different pure phases typically behaves as

$$
{}_L\langle\Omega_+|\Omega_-\rangle_L\to0
\qquad
(L\to\infty),
$$

and matrix elements of local operators between the two phases vanish in the same limit:

$$
\langle\Omega_+|A_{\mathrm{local}}|\Omega_-\rangle=0.
$$

This does not mean no operator exists that relates the phases. A global symmetry operator may map one vacuum to another. A boundary condition can select a different phase. A domain wall operator can create an interface. But these are not ordinary compactly supported local observables acting within a single phase.

The next page makes this statement precise using superselection sectors.

## Common pitfalls

**Confusing minima with vacua.** A minimum of a classical or perturbative potential is not automatically a nonperturbative vacuum. Check the state, the volume limit, the source prescription, and gauge invariance.

**Taking the symmetric finite-volume state as the whole story.** At $h=0$ and finite $L$, the exact ground state may respect the symmetry. The broken vacua can still exist as infinite-volume pure phases.

**Declaring gauge copies to be degenerate vacua.** Gauge-related field configurations are different descriptions of the same physical configuration. Distinct vacua must be distinguished by physical observables or boundary data.

**Forgetting mixtures.** A state with zero one-point order parameter can still have long-range order if it is a mixture of broken phases. Inspect two-point functions and clustering.

**Calling metastability degeneracy.** A long-lived false vacuum is not a degenerate vacuum unless its energy density equals that of the true vacuum in the limit under discussion.

**Assuming continuous symmetry breaking always works.** In low dimensions, infrared fluctuations can destroy continuous long-range order even when the classical potential has a continuous family of minima.

## Relations to other pages

[Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) explains how sources and order-of-limits define one-point functions in a chosen phase. Degenerate vacua are the main reason that care is needed.

[Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains why a finite regulated system is often too small to display the final phase structure directly.

[Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) explains another limit that can fail to commute with the thermodynamic or source-selection limits.

[Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/) sharpens the statement that different infinite-volume vacua may be disconnected by local physical operators.

Later pages on spontaneous symmetry breaking, effective potentials, discrete vacua, domain walls, instantons, and false-vacuum decay will develop the main mechanisms and calculations.

## Research status

**Established.** The distinction between finite-volume symmetric states and infinite-volume pure broken phases is standard in QFT and statistical mechanics. The source prescription for selecting phases is the clean practical definition of a broken vacuum.

**Established.** Gauge redundancy is not physical degeneracy. Statements about vacuum structure in gauge theories must be made using gauge-invariant observables, spectra, line operators, boundary conditions, or other physical data.

**Active.** In strongly coupled gauge theories, determining the full phase structure can be difficult. Different diagnostics may agree only after careful limits are taken, and phases can be distinguished by nonlocal or topological data rather than by a simple local VEV.

**Caveat.** The notation $|\Omega_a\rangle$ for different infinite-volume vacua is convenient but formal. In algebraic language, different phases may be inequivalent representations of the local observable algebra rather than normalizable vectors in one separable Hilbert space.

## Exercises

### Exercise 1: Symmetric and broken expectations

Suppose $|+\rangle$ and $|-\rangle$ are approximately orthonormal states with

$$
\langle +|\mathcal O|+\rangle=+v,
\qquad
\langle -|\mathcal O|-\rangle=-v,
\qquad
\langle +|\mathcal O|-\rangle\simeq0.
$$

Define

$$
|S\rangle=\frac{|+\rangle+|-\rangle}{\sqrt2},
\qquad
|A\rangle=\frac{|+\rangle-|-\rangle}{\sqrt2}.
$$

Compute $\langle S|\mathcal O|S\rangle$ and explain why this does not rule out broken vacua.

<details>
<summary><strong>Solution</strong></summary>

Using the assumptions,

$$
\langle S|\mathcal O|S\rangle
=\frac12\left(v-v+\langle+|\mathcal O|-\rangle+
\langle-|\mathcal O|+\rangle\right)\simeq0.
$$

The symmetric combination has zero one-point function. But the states $|+\rangle$ and $|-\rangle$ still have opposite order parameter. In finite volume, the symmetric and antisymmetric combinations are often closer to exact energy eigenstates. In infinite volume the tunneling splitting vanishes, and source-selected pure phases recover $\langle\mathcal O\rangle=\pm v$.

</details>

### Exercise 2: A two-state model for source selection

Model the two nearly degenerate finite-volume states by

$$
H_{\mathrm{eff}}=-\Delta\sigma_x-hVv\,\sigma_z,
$$

where $V=L^{d-1}$, $\Delta>0$ is a tunneling matrix element, and $h$ is a source. Find the ground-state expectation value of $\sigma_z$ and take the limits $V\to\infty$ and $h\to0$ in both orders, assuming $\Delta$ stays finite or decreases with $V$.

<details>
<summary><strong>Solution</strong></summary>

The effective magnetic field in Pauli-matrix space is

$$
\mathbf B=(\Delta,0,hVv),
$$

so the ground state aligns with $\mathbf B$. Thus

$$
\langle\sigma_z\rangle
=\frac{hVv}{\sqrt{\Delta^2+h^2V^2v^2}}.
$$

If $h\to0$ first at fixed $V$, then $\langle\sigma_z\rangle\to0$. If $V\to\infty$ first at fixed nonzero $h$, then

$$
\langle\sigma_z\rangle\to \operatorname{sgn}(h),
$$

and the subsequent $h\to0^\pm$ limit gives the two broken phases. If $\Delta$ decreases with $V$, the selection becomes even sharper.

</details>

### Exercise 3: Domain-wall scaling of tunneling

Give a dimensional argument for why tunneling between two discrete broken vacua in a spatial box of size $L$ is suppressed like $\exp[-\sigma L^{d-1}]$ rather than like $\exp[-\sigma L]$ in $d$ spacetime dimensions.

<details>
<summary><strong>Solution</strong></summary>

A tunneling event that flips the order parameter of the whole spatial box must pass through a configuration containing an interface between the two phases. In Euclidean spacetime, the interface spans the spatial volume at some Euclidean time. Its area is proportional to the spatial volume, $L^{d-1}$. If $\sigma$ is the tension, the Euclidean action cost is of order

$$
S_{\mathrm{wall}}\sim \sigma L^{d-1}.
$$

Therefore the transition amplitude is suppressed as

$$
\exp[-S_{\mathrm{wall}}]\sim \exp[-\sigma L^{d-1}],
$$

up to prefactors and model-dependent corrections.

</details>

### Exercise 4: Mixture versus pure phase

Let a symmetric mixed state be

$$
\rho=\frac12|\Omega_+\rangle\langle\Omega_+|
+\frac12|\Omega_-\rangle\langle\Omega_-|,
$$

where $\langle\phi\rangle_+=v$ and $\langle\phi\rangle_-=-v$. Assuming clustering in each pure phase, compute $\operatorname{Tr}(\rho\phi)$ and the large-distance limit of $\operatorname{Tr}(\rho\phi(x)\phi(0))$.

<details>
<summary><strong>Solution</strong></summary>

The one-point function is

$$
\operatorname{Tr}(\rho\phi)=\frac12v+\frac12(-v)=0.
$$

In each pure phase, clustering gives

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_\pm
=\langle\phi\rangle_\pm^2=v^2.
$$

Therefore

$$
\lim_{|x|\to\infty}\operatorname{Tr}(\rho\phi(x)\phi(0))=v^2.
$$

The mixed state has zero one-point function but retains long-range order in the two-point function.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially the lectures on spontaneous symmetry breaking, functional methods, and the effective potential.
- M. Srednicki, *Quantum Field Theory*, sections on the quantum action, spontaneous symmetry breaking, and broken symmetry with loop corrections.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter on spontaneous symmetry breaking.

### Deeper references

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the field-integral and statistical-mechanics view of phases, thermodynamic limits, and effective potentials.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters on phases of gauge theories, kinks, domain walls, and related nonperturbative phenomena.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for the many-body and statistical-field-theory perspective on broken symmetry, collective phenomena, and phase structure.

## Version history

- **2026-06-26:** Initial standardized page.
