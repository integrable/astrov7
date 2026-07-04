---
title: "Thermal States and KMS"
description: "The thermal density matrix, partition function, Euclidean thermal circle, KMS condition, and first consequences for finite-temperature CFT correlators."
sidebar:
  label: "Thermal States and KMS"
  order: 1
level: Advanced
status: "Polished draft"
source: "Kubo; Martin and Schwinger; Haag, Hugenholtz, and Winnink; Le Bellac; Kapusta and Gale; thermal QFT and CFT literature."
topics:
  - thermal CFT
  - KMS condition
  - thermal density matrix
  - Euclidean thermal circle
  - real-time correlators
canonicalTopics:
  - thermal-states-and-kms
  - kms-condition
  - finite-temperature-cft
researchStatus:
  established:
    - "The KMS condition characterizes thermal equilibrium in quantum statistical mechanics and underlies the Euclidean thermal circle, Matsubara formalism, and fluctuation-dissipation relations."
  active:
    - "Current work applies KMS and thermal analyticity to thermal bootstrap, real-time CFT data, OTOCs, modular flow, hydrodynamics, holography, and non-equilibrium generalizations."
---

## Summary

A **thermal state** is an equilibrium mixed state defined by the density matrix

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\operatorname{Tr}e^{-\beta H},
$$

where

$$
\beta=\frac{1}{T}.
$$

Thermal expectation values are traces:

$$
\langle A\rangle_\beta=\operatorname{Tr}(\rho_\beta A).
$$

The central structural statement is the **Kubo-Martin-Schwinger condition**, or **KMS condition**. For bosonic operators in equilibrium,

$$
\langle A(t)B(0)\rangle_\beta
=
\langle B(0)A(t+i\beta)\rangle_\beta,
$$

with fermionic signs when appropriate.

The KMS condition is the operator-algebraic form of thermal equilibrium. It explains why Euclidean time is periodic with period $\beta$, why thermal correlators have special analyticity strips, and why real-time response functions obey fluctuation-dissipation relations.

The slogan is

$$
\text{thermal equilibrium}=\text{imaginary-time periodicity plus operator ordering}.
$$

This page builds the foundation for real-time correlators, spectral functions, thermal bootstrap, hydrodynamics, and chaos.

## Prerequisites

Read [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) and [Euclidean and Lorentzian CFT](/cft-bootstrap/what-is-a-cft/euclidean-and-lorentzian-cft/) first.

You should know density matrices, traces, Heisenberg time evolution, basic complex analysis, and CFT on the cylinder. Familiarity with statistical mechanics helps, but the key formulas are reviewed here.

## Core idea

Thermal equilibrium is encoded by time evolution under the Hamiltonian and a trace over the Hilbert space. The trace is cyclic:

$$
\operatorname{Tr}(XY)=\operatorname{Tr}(YX).
$$

The Boltzmann factor is an imaginary-time evolution operator:

$$
e^{-\beta H}=e^{i(i\beta)H}.
$$

Combining these two facts gives the KMS relation. That relation is much more than a clever identity. It determines the analytic continuation between Euclidean thermal correlators and Lorentzian thermal correlators.

The conceptual chain is

$$
\rho_\beta=Z^{-1}e^{-\beta H}
\quad\to\quad
\text{cyclicity of trace}
\quad\to\quad
\text{KMS condition}
\quad\to\quad
\text{thermal circle and real-time analyticity}.
$$

Everything in finite-temperature QFT is hiding in this chain like a very well-organized raccoon.

## Thermal density matrix

For a quantum system with Hamiltonian $H$, the canonical ensemble is

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)}.
$$

The partition function is

$$
Z(\beta)=\operatorname{Tr}e^{-\beta H}.
$$

The free energy is

$$
F(\beta)=-\frac{1}{\beta}\log Z(\beta).
$$

The thermal entropy is

$$
S=-\operatorname{Tr}\rho_\beta\log\rho_\beta.
$$

In a CFT on a spatial sphere $S^{d-1}$, the Hamiltonian is the cylinder Hamiltonian. Energy eigenvalues are related to operator dimensions:

$$
E_i=\frac{\Delta_i}{R}
$$

up to the vacuum or Casimir-energy convention. Therefore thermal traces on the sphere are spectral sums over CFT states, equivalently over local operators by the state-operator correspondence.

## Thermal expectation values

A thermal expectation value is

$$
\langle A\rangle_\beta
=\frac{1}{Z}\operatorname{Tr}(e^{-\beta H}A).
$$

For a time-dependent Heisenberg operator,

$$
A(t)=e^{iHt}A(0)e^{-iHt}.
$$

Thermal correlation functions are then

$$
\langle A(t_1)B(t_2)\rangle_\beta
=\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}A(t_1)B(t_2)\right).
$$

Because the thermal state is stationary,

$$
[\rho_\beta,H]=0,
$$

correlators in equilibrium depend only on time differences:

$$
\langle A(t_1)B(t_2)\rangle_\beta
=\langle A(t_1-t_2)B(0)\rangle_\beta
$$

for time-translation-invariant operators and states.

In a CFT on flat space at finite temperature, the thermal rest frame matters. The state preserves spatial translations and rotations, but not Lorentz boosts or scale transformations.

## Deriving KMS

Let

$$
G_{AB}^{>}(t)=\langle A(t)B(0)\rangle_\beta.
$$

Using the thermal trace,

$$
G_{AB}^{>}(t)=\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}e^{iHt}A(0)e^{-iHt}B(0)\right).
$$

Cyclicity lets us move $B(0)$ to the front:

$$
G_{AB}^{>}(t)=\frac{1}{Z}\operatorname{Tr}\left(B(0)e^{-\beta H}e^{iHt}A(0)e^{-iHt}\right).
$$

Because $e^{-\beta H}$ shifts time by $i\beta$, this becomes

$$
G_{AB}^{>}(t)=\langle B(0)A(t+i\beta)\rangle_\beta.
$$

This is the KMS condition for bosonic operators:

$$
\boxed{
\langle A(t)B(0)\rangle_\beta
=
\langle B(0)A(t+i\beta)\rangle_\beta
}.
$$

For fermionic operators, moving operators through the trace introduces the appropriate minus sign:

$$
\langle A(t)B(0)\rangle_\beta
=-\langle B(0)A(t+i\beta)\rangle_\beta
$$

when both operators are fermionic and the usual antiperiodic thermal boundary condition applies.

## Euclidean thermal circle

Set

$$
t=-i\tau.
$$

The KMS relation becomes periodicity in Euclidean time. For bosonic operators,

$$
G_E(\tau+\beta)=G_E(\tau),
$$

while for fermionic operators,

$$
G_E(\tau+\beta)=-G_E(\tau).
$$

Thus the Euclidean thermal path integral lives on a space with imaginary time compactified:

$$
\tau\sim\tau+\beta.
$$

This is the **thermal circle**. The geometry is often written as

$$
S^1_\beta\times \Sigma,
$$

where $\Sigma$ is the spatial manifold.

For a CFT on flat space at temperature $T$, the Euclidean background is

$$
S^1_\beta\times \mathbb R^{d-1}.
$$

For a CFT on the cylinder, it is

$$
S^1_\beta\times S^{d-1}.
$$

The thermal circle is not a mnemonic. It is KMS made geometric.

## Matsubara frequencies

Periodic or antiperiodic Euclidean time implies discrete Euclidean frequencies. For bosonic operators,

$$
\omega_n=\frac{2\pi n}{\beta},
\qquad
n\in\mathbb Z.
$$

For fermionic operators,

$$
\omega_n=\frac{(2n+1)\pi}{\beta},
\qquad
n\in\mathbb Z.
$$

These are **Matsubara frequencies**. Euclidean thermal correlators are naturally expanded as

$$
G_E(\tau)=\frac{1}{\beta}\sum_n e^{-i\omega_n\tau}G_E(i\omega_n).
$$

Real-time correlators are obtained by analytic continuation, but the continuation depends on which Lorentzian correlator one wants. Retarded, advanced, time-ordered, and Wightman functions are not the same analytic continuation.

That last sentence prevents a lot of thermal-field-theory heartbreak.

## KMS in frequency space

Define Wightman functions

$$
G^{>}_{AB}(t)=\langle A(t)B(0)\rangle_\beta,
\qquad
G^{<}_{AB}(t)=\langle B(0)A(t)\rangle_\beta.
$$

The KMS relation implies, in frequency space,

$$
G^{>}_{AB}(\omega)=e^{\beta\omega}G^{<}_{AB}(\omega)
$$

for bosonic operators, up to conventions for Fourier transforms and operator ordering.

The spectral density is often defined as

$$
\rho_{AB}(\omega)=G^{>}_{AB}(\omega)-G^{<}_{AB}(\omega).
$$

Then KMS relates Wightman functions to the spectral density:

$$
G^{>}(\omega)=\frac{1}{1-e^{-\beta\omega}}\rho(\omega),
\qquad
G^{<}(\omega)=\frac{1}{e^{\beta\omega}-1}\rho(\omega)
$$

for bosonic conventions.

These relations are the seed of fluctuation-dissipation theorems. Thermal fluctuations and dissipative response are two faces of the same spectral data.

## Retarded correlators

The retarded correlator is

$$
G_R(t)=-i\theta(t)\langle[A(t),B(0)]\rangle_\beta
$$

for bosonic operators.

It computes causal linear response. If the Hamiltonian is perturbed by

$$
\delta H(t)=-f(t)B(t),
$$

then the first-order response of $A$ is controlled by

$$
\delta\langle A(t)\rangle
=\int dt'\,G_R(t-t')f(t')
$$

up to sign and convention choices.

The spectral function is related to the imaginary part of the retarded function:

$$
\rho(\omega)=-2\operatorname{Im}G_R(\omega)
$$

in one common convention.

The important distinction is:

| Correlator | Meaning |
|---|---|
| Wightman | unordered thermal fluctuation |
| Euclidean | imaginary-time thermal correlator |
| time-ordered | perturbative ordering object |
| retarded | causal response |
| advanced | response with opposite support |
| spectral density | commutator data and dissipative content |

KMS relates these objects, but it does not make them identical.

## Chemical potentials

If the theory has a conserved charge $Q$, one can introduce a chemical potential $\mu$:

$$
\rho_{\beta,\mu}=\frac{e^{-\beta(H-\mu Q)}}{Z(\beta,\mu)}.
$$

The partition function is

$$
Z(\beta,\mu)=\operatorname{Tr}e^{-\beta(H-\mu Q)}.
$$

The KMS condition is modified for charged operators. If

$$
[Q,A]=q_A A,
$$

then the imaginary-time shift can include a fugacity factor:

$$
A(t+i\beta)\sim e^{-\beta\mu q_A}A(t)
$$

inside thermal correlators, with convention-dependent signs depending on where the operator is moved.

Equivalently, chemical potentials can be viewed as background gauge fields around the thermal circle.

This is important for charged CFTs, current correlators, hydrodynamics, and finite-density holography.

## Thermal CFT on flat space

A CFT vacuum has no intrinsic scale. A thermal state introduces one:

$$
T=\frac{1}{\beta}.
$$

Therefore thermal expectation values can be nonzero when symmetries permit. For a scalar primary $\mathcal O$ of dimension $\Delta$, dimensional analysis gives

$$
\langle \mathcal O\rangle_\beta=b_{\mathcal O}T^\Delta
$$

if the operator is neutral under all unbroken symmetries and has the right tensor structure.

For the stress tensor in a homogeneous thermal state,

$$
\langle T_{\mu\nu}\rangle_\beta
=\operatorname{diag}(\varepsilon,p,p,\ldots,p)
$$

in the rest frame, with conformal invariance implying

$$
\varepsilon=(d-1)p
$$

for a flat-space CFT without anomalies or additional scales.

Thus thermal CFT is still conformal as an operator algebra, but the state breaks boosts and dilatations.

## Thermal CFT on the cylinder

On the cylinder

$$
\mathbb R\times S^{d-1},
$$

the Hamiltonian spectrum is related to operator dimensions. The thermal partition function is

$$
Z(\beta)=\sum_i e^{-\beta E_i}
\sim \sum_i e^{-\beta \Delta_i/R}
$$

up to vacuum-energy conventions.

This makes thermal physics a probe of the CFT spectrum. At low temperature, light operators dominate. At high temperature, many states contribute.

In two-dimensional CFT, modular invariance gives powerful constraints on this high-temperature behavior. In higher dimensions, thermal and Tauberian methods still relate singular limits of $Z(\beta)$ to averaged high-energy spectral data, but with fewer exact symmetries.

Thermal traces are therefore another way the CFT data become physics.

## Thermal OPE intuition

At finite temperature, the local OPE still exists:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim \sum_k C_{ijk}(x,\partial)\mathcal O_k(0).
$$

Taking a thermal expectation value gives

$$
\langle\mathcal O_i(x)\mathcal O_j(0)\rangle_\beta
\sim
\sum_k C_{ijk}(x,\partial)\langle \mathcal O_k\rangle_\beta.
$$

The OPE coefficients are vacuum CFT data. The thermal one-point functions are state data.

This is the basis of thermal bootstrap approaches: use the OPE and KMS or crossing-like consistency on the thermal cylinder to constrain thermal one-point coefficients and correlators.

The OPE remains local. The state changes which operators have nonzero expectation values.

## Common pitfalls

**Do not confuse thermal periodicity with ordinary time periodicity.** Real time is not periodic. Imaginary time is periodic in equilibrium.

**Do not drop operator ordering from KMS.** KMS relates different orderings shifted by $i\beta$; it is not simply $G(t+i\beta)=G(t)$ for every Lorentzian correlator.

**Do not use the same analytic continuation for every correlator.** Retarded, advanced, time-ordered, and Wightman correlators require different prescriptions.

**Do not forget fermion signs.** Fermionic thermal correlators are antiperiodic around the Euclidean thermal circle.

**Do not assume finite temperature destroys the CFT.** The operator algebra remains conformal; the thermal state breaks some spacetime symmetries.

**Do not identify a thermal mixed state with a pure energy eigenstate without assumptions.** Heavy eigenstates may approximate thermal behavior in chaotic systems, but that is an additional statement.

**Do not ignore chemical-potential twists.** Charged operators can acquire fugacity factors around the thermal circle.

## Relations to other pages

This page starts the [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) chapter and prepares [Euclidean Thermal Circle and Matsubara Modes](/cft-bootstrap/thermal-lorentzian-cft/euclidean-thermal-circle-and-matsubara-modes/), [Real-Time Correlators](/cft-bootstrap/thermal-lorentzian-cft/real-time-correlators/), and [Spectral Functions and Sum Rules](/cft-bootstrap/thermal-lorentzian-cft/spectral-functions-and-sum-rules/).

It connects to [Tauberian and Asymptotic Methods](/cft-bootstrap/analytic-bootstrap/tauberian-and-asymptotic-methods/) because thermal partition functions encode high-energy spectral growth.

It connects to [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/) because holographic thermal states are often dual to thermal AdS or AdS black holes.

For two-dimensional modular constraints, see [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) when expanded.

## Research status

Thermal density matrices, KMS relations, Euclidean thermal circles, Matsubara modes, spectral representations, and retarded response are established foundations of finite-temperature QFT.

Active research uses these tools in thermal bootstrap, real-time conformal dynamics, OTOCs and chaos, hydrodynamic effective theory, modular flow, finite-density CFT, holographic black-hole physics, and non-equilibrium generalizations.

## Exercises

### Exercise 1

Derive the bosonic KMS relation

$$
\langle A(t)B(0)\rangle_\beta
=
\langle B(0)A(t+i\beta)\rangle_\beta.
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
\langle A(t)B(0)\rangle_\beta
=\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}A(t)B(0)\right).
$$

Use cyclicity of the trace to move $B(0)$ to the front:

$$
=\frac{1}{Z}\operatorname{Tr}\left(B(0)e^{-\beta H}A(t)\right).
$$

Since

$$
e^{-\beta H}A(t)=A(t+i\beta)e^{-\beta H},
$$

this becomes

$$
\frac{1}{Z}\operatorname{Tr}\left(e^{-\beta H}B(0)A(t+i\beta)\right)
=\langle B(0)A(t+i\beta)\rangle_\beta.
$$

</details>

### Exercise 2

Why are bosonic Matsubara frequencies multiples of $2\pi/\beta$?

<details><summary><strong>Solution</strong></summary>

Bosonic Euclidean thermal correlators are periodic:

$$
G_E(\tau+\beta)=G_E(\tau).
$$

A Fourier mode $e^{-i\omega_n\tau}$ must obey

$$
e^{-i\omega_n(\tau+\beta)}=e^{-i\omega_n\tau}.
$$

Therefore

$$
e^{-i\omega_n\beta}=1,
$$

so

$$
\omega_n=\frac{2\pi n}{\beta},
\qquad n\in\mathbb Z.
$$

</details>

### Exercise 3

What changes for fermionic thermal correlators?

<details><summary><strong>Solution</strong></summary>

Fermionic operators anticommute when moved around the thermal trace. This gives antiperiodic Euclidean boundary conditions:

$$
G_E(\tau+\beta)=-G_E(\tau).
$$

The allowed frequencies are therefore

$$
\omega_n=\frac{(2n+1)\pi}{\beta},
\qquad n\in\mathbb Z.
$$

</details>

### Exercise 4

Why does finite temperature break conformal symmetry even in a CFT?

<details><summary><strong>Solution</strong></summary>

The CFT operator algebra remains conformal, but the thermal state introduces a scale $T=1/\beta$ and a preferred rest frame. This breaks boosts and dilatations. Correlators can depend on dimensionless ratios such as $\omega/T$ and $|\mathbf k|/T$, and thermal one-point functions may be nonzero when symmetries allow them.

</details>

### Exercise 5

What is the difference between a Wightman correlator and a retarded correlator?

<details><summary><strong>Solution</strong></summary>

A Wightman correlator is an unordered thermal correlator, such as

$$
G^>(t)=\langle A(t)B(0)\rangle_\beta.
$$

A retarded correlator is a causal commutator:

$$
G_R(t)=-i\theta(t)\langle[A(t),B(0)]\rangle_\beta.
$$

The Wightman function describes fluctuations. The retarded correlator describes causal linear response.

</details>

## References

- R. Kubo, “Statistical-Mechanical Theory of Irreversible Processes. I,” *Journal of the Physical Society of Japan* **12** (1957).
- P. C. Martin and J. Schwinger, “Theory of Many-Particle Systems. I,” *Physical Review* **115** (1959).
- R. Haag, N. M. Hugenholtz, and M. Winnink, “On the equilibrium states in quantum statistical mechanics,” *Communications in Mathematical Physics* **5** (1967).
- A. L. Fetter and J. D. Walecka, *Quantum Theory of Many-Particle Systems*, Dover, 2003.
- M. Le Bellac, *Thermal Field Theory*, Cambridge University Press, 1996.
- J. I. Kapusta and C. Gale, *Finite-Temperature Field Theory: Principles and Applications*, Cambridge University Press, 2006.
- D. T. Son and A. O. Starinets, “Minkowski-space correlators in AdS/CFT correspondence,” *Journal of High Energy Physics* **2002**.

## Version history

- 2026-07-02: First polished draft. Added thermal density matrix, KMS derivation, Euclidean thermal circle, Matsubara frequencies, frequency-space KMS, retarded response, chemical potentials, thermal CFT on flat space and cylinder, thermal OPE intuition, exercises, and references.
