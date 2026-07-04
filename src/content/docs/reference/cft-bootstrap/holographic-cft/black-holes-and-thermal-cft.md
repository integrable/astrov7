---
title: "Black Holes and Thermal CFT"
description: "How finite-temperature CFT states, heavy operators, thermal correlators, entropy, chaos, and Page curves are encoded by AdS black holes."
sidebar:
  label: "Black Holes and Thermal CFT"
  order: 9
level: Advanced
status: "Polished draft"
source: "Hawking; Bekenstein; Maldacena; Witten; Hawking-Page; Maldacena, Shenker, and Stanford; holographic thermal CFT and black-hole information literature."
topics:
  - black holes
  - thermal CFT
  - holographic CFT
  - AdS/CFT
  - quantum chaos
canonicalTopics:
  - black-holes-and-thermal-cft
  - holographic-thermal-states
  - ads-black-holes
researchStatus:
  established:
    - "Thermal states of holographic CFTs are described by thermal AdS or AdS black-hole saddles depending on the ensemble and temperature."
    - "Black-hole entropy, thermal correlators, quasinormal behavior, and maximal chaos have precise CFT interpretations in large-N holographic regimes."
  active:
    - "Current research studies black-hole microstates, islands, Page curves, finite-N effects, ensemble averaging, wormholes, reconstruction behind horizons, and bootstrap constraints on thermal CFT data."
---

## Summary

In holography, **black holes are thermal states of the CFT**. A CFT placed at finite temperature has a thermal density matrix

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\operatorname{Tr}e^{-\beta H}.
$$

In a holographic CFT, this thermal state can be represented in the bulk by thermal AdS or by an AdS black hole. Which saddle dominates depends on the geometry, temperature, and ensemble.

The key dictionary is:

| CFT object | Bulk interpretation |
|---|---|
| thermal density matrix | Euclidean thermal saddle |
| high-temperature deconfined phase | large AdS black hole |
| free energy | on-shell Euclidean action |
| entropy | horizon area plus quantum corrections |
| heavy operator or heavy state | massive object or black-hole microstate |
| thermal two-point function | propagation in black-hole geometry |
| OTOC growth | shockwave scattering near horizon |
| late-time entropy of radiation | Page curve and quantum extremal surfaces |

The slogan is

$$
\text{black-hole thermodynamics is CFT thermodynamics in disguise}.
$$

This page explains the thermal dictionary, Hawking-Page transitions, black-hole entropy, correlators, chaos, heavy states, and the connection to the information problem.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/), [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/), and [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) first.

You should know thermal density matrices, Euclidean time periodicity, partition functions, entropy, large-$N$ scaling, and the basic AdS/CFT dictionary.

## Thermal CFT basics

A thermal CFT is defined by the partition function

$$
Z(\beta)=\operatorname{Tr}_{\mathcal H}e^{-\beta H},
$$

where the trace is over the Hilbert space on the spatial manifold. On the cylinder,

$$
\mathbb R\times S^{d-1},
$$

the Hamiltonian spectrum is the operator-dimension spectrum by radial quantization:

$$
E_i=\frac{\Delta_i}{R_{S^{d-1}}}.
$$

Therefore the thermal partition function is also a generating function for operator dimensions:

$$
Z(\beta)=\sum_i e^{-\beta \Delta_i/R}.
$$

At low temperature, light states dominate. At high temperature, many heavy states contribute. In holographic theories, those heavy states can organize into black-hole thermodynamics.

## Euclidean thermal circle

Finite temperature is implemented by periodic Euclidean time:

$$
\tau\sim \tau+\beta.
$$

For bosonic operators, thermal correlators are periodic in Euclidean time. For fermionic operators, they are antiperiodic. This is the CFT side of the Euclidean black-hole geometry, where smoothness at the horizon fixes the periodicity of Euclidean time.

The thermal circle is not merely a trick. It encodes the KMS condition:

$$
\langle A(t)B(0)\rangle_\beta
=
\langle B(0)A(t+i\beta)\rangle_\beta.
$$

The KMS condition is the analytic signature of thermal equilibrium. In holography, it is mirrored by the analytic structure of fields on black-hole backgrounds.

## Thermal AdS and AdS black holes

For a CFT on

$$
S^{d-1}\times S^1_\beta,
$$

the bulk Euclidean path integral can have multiple saddles with the same boundary geometry. Two basic saddles are:

| Saddle | Interpretation |
|---|---|
| thermal AdS | gas of particles in AdS |
| Euclidean AdS black hole | thermal black-hole geometry |

At low temperature, thermal AdS may dominate. At high temperature, a large AdS black hole may dominate. The transition between them is the Hawking-Page transition.

On the CFT side, this is interpreted as a confinement/deconfinement-like transition in suitable large-$N$ gauge theories. The free energy changes scaling:

$$
F\sim O(1)
\quad\text{to}\quad
F\sim O(N^2)
$$

in matrix-like examples.

The bulk saddle tells you which class of CFT states dominates the thermal ensemble.

## Black-hole entropy

A classical AdS black hole has Bekenstein-Hawking entropy

$$
S_{\rm BH}=\frac{\operatorname{Area}(\mathcal H)}{4G_N}.
$$

Using the holographic relation

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N},
$$

one sees that black-hole entropy is large in a large-$C_T$ CFT.

In CFT language, this entropy counts the logarithm of the number of states in the corresponding energy window:

$$
S(E)=\log \rho(E)
$$

in a microcanonical approximation.

The black-hole area is therefore not extra microscopic data. It is a coarse-grained count of CFT states.

## Heavy states and black-hole microstates

A heavy CFT state has dimension

$$
\Delta_H\gg1.
$$

In a holographic CFT, sufficiently heavy states can correspond to black-hole microstates. The precise threshold depends on the spacetime dimension, angular momentum, charges, and ensemble.

The rough picture is:

| CFT state | Bulk picture |
|---|---|
| vacuum | empty AdS |
| light primary | one-particle state |
| multi-trace state | multi-particle state |
| very heavy state | star, gas, or black-hole microstate |
| typical high-energy state | black-hole-like geometry in coarse observables |

A single exact microstate is pure. The black-hole geometry is a coarse-grained or effective description of many microstates. This distinction is crucial for the information problem.

## Thermal correlators

Thermal correlators probe how operators propagate in a thermal state:

$$
G_\beta(t,\mathbf x)=\operatorname{Tr}\left(\rho_\beta\mathcal O(t,\mathbf x)\mathcal O(0)\right).
$$

In a holographic black-hole phase, these correlators are computed by fields propagating on a black-hole background.

At late Lorentzian times, thermal correlators often decay, reflecting absorption by the horizon and quasinormal modes. In the exact finite-volume CFT, however, the spectrum is discrete, so correlators cannot decay forever. There must be late-time recurrences and nonperturbative effects.

Thus black-hole geometry is an excellent approximation in a regime, but the exact CFT knows about unitarity.

## Quasinormal modes

Perturbations of an AdS black hole ring down through quasinormal modes. These are solutions with ingoing boundary conditions at the horizon and normalizable or sourced behavior near the boundary.

In the CFT, quasinormal frequencies appear as poles of retarded thermal Green's functions:

$$
G_R(\omega,\mathbf k).
$$

The imaginary parts of the frequencies give decay rates. The real parts give oscillation frequencies.

This gives a direct bridge:

$$
\text{black-hole ringdown}
\quad\Longleftrightarrow\quad
\text{thermal CFT response}.
$$

Quasinormal modes are not new operators in the zero-temperature CFT spectrum. They are thermal response features of a state or ensemble.

## Hydrodynamics

At long wavelengths and late times, conserved quantities obey hydrodynamics. In a thermal CFT, the stress tensor and conserved currents have hydrodynamic modes such as sound and diffusion.

Holographically, these modes arise from long-wavelength perturbations of black branes. Transport coefficients are extracted from retarded correlators using Kubo formulas.

Examples include:

| CFT transport | Bulk computation |
|---|---|
| shear viscosity | metric perturbation absorption |
| conductivity | gauge-field perturbation |
| diffusion constant | charge or momentum diffusion mode |
| sound attenuation | coupled gravitational perturbations |

This is one of the practical successes of holography: strongly coupled real-time thermal response can be computed from classical gravity.

## Chaos and OTOCs

Thermal quantum chaos is diagnosed by out-of-time-order correlators, such as

$$
F(t)=\langle V(t)W(0)V(t)W(0)\rangle_\beta.
$$

In large-$N$ chaotic systems, an intermediate-time regime can have

$$
F(t)\approx F_0-\frac{1}{N^2}e^{\lambda_L t}+\cdots .
$$

Einstein gravity gives maximal Lyapunov growth:

$$
\lambda_L=\frac{2\pi}{\beta}.
$$

The bulk mechanism is shockwave scattering near a black-hole horizon. The CFT mechanism is Lorentzian Regge growth on an out-of-time-order sheet.

Stringy corrections or a finite higher-spin gap can soften the Regge behavior and reduce the effective chaos exponent.

## Page curve and information

The black-hole information problem asks how apparently thermal Hawking radiation can be compatible with unitary quantum mechanics.

For an evaporating black hole, the entropy of radiation is expected to follow a Page curve: it rises at early times and falls after the Page time if the total state is pure.

In modern holographic calculations, the Page curve is obtained using quantum extremal surfaces and islands. The entropy is computed by extremizing generalized entropy:

$$
S_{\rm gen}(X)=\frac{\operatorname{Area}(X)}{4G_N}+S_{\rm bulk}(\Sigma_X)+\cdots .
$$

At early times, a no-island saddle dominates. At late times, an island saddle dominates. This changes the entanglement wedge of the radiation and gives a unitary Page curve.

The key CFT lesson is that unitarity was never lost. The semiclassical bulk description had to be refined.

## Eternal black holes and thermofield double states

An eternal two-sided AdS black hole is dual to a thermofield double state of two copies of the CFT:

$$
|\operatorname{TFD}\rangle
=\frac{1}{\sqrt{Z(\beta)}}\sum_n e^{-\beta E_n/2}|n\rangle_L|n\rangle_R.
$$

Each side separately looks thermal. The full two-CFT state is pure.

The two exterior regions of the eternal black hole are connected by an Einstein-Rosen bridge. This is a geometric representation of entanglement between the two CFTs.

The thermofield double is a clean laboratory for studying horizons, wormholes, thermalization, chaos, and reconstruction behind horizons.

## Ensemble versus microstate

A thermal density matrix is mixed:

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)}.
$$

A black-hole microstate is pure. Many semiclassical observables cannot distinguish a typical microstate from the thermal ensemble over accessible times and simple probes.

This is why black-hole geometry often describes coarse-grained physics. But exact questions about unitarity, recurrences, and fine-grained entropy require the microscopic CFT description.

A useful distinction is:

$$
\text{geometry}=\text{coarse effective description},
\qquad
\text{CFT}=\text{exact quantum definition}.
$$

The information problem lives precisely in the gap between these statements.

## Common pitfalls

**Do not say every thermal CFT state is a black hole.** Low-temperature saddles or small systems may be better described by thermal AdS or a gas of particles.

**Do not confuse the thermal ensemble with a pure microstate.** The ensemble is mixed; a microstate is pure.

**Do not treat semiclassical decay as exact forever.** Finite-volume unitary CFT correlators have discrete spectra and late-time effects.

**Do not ignore the ensemble and boundary geometry.** The Hawking-Page transition depends on the setup.

**Do not quote black-hole entropy without specifying coarse graining.** Area entropy is a thermodynamic or generalized entropy, not a list of microstates on the page.

**Do not assume maximal chaos in every holographic regime.** Stringy and finite-coupling corrections can reduce the exponent.

**Do not separate islands from RT/HRT.** Islands are quantum extremal surface saddles in the generalized entropy prescription.

## Relations to other pages

This page follows [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) and prepares [Quantum Error Correction and Entanglement Wedges](/cft-bootstrap/holographic-cft/quantum-error-correction-and-entanglement-wedges/) and [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/).

It connects to [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/), and [Tauberian and Asymptotic Methods](/cft-bootstrap/analytic-bootstrap/tauberian-and-asymptotic-methods/).

## Research status

The thermal-CFT/AdS-black-hole dictionary is established. Hawking-Page transitions, black-hole entropy, thermal correlators, hydrodynamic response, quasinormal modes, and chaos are standard parts of holographic CFT.

Active research studies microscopic black-hole states, quantum extremal surfaces, islands, replica wormholes, late-time correlators, ensemble averaging, interior reconstruction, finite-$N$ corrections, and bootstrap constraints on thermal spectra and OPE data.

## Exercises

### Exercise 1

What is the CFT partition function at temperature $1/\beta$?

<details><summary><strong>Solution</strong></summary>

The thermal partition function is

$$
Z(\beta)=\operatorname{Tr}_{\mathcal H}e^{-\beta H}.
$$

It sums over states in the CFT Hilbert space on the chosen spatial manifold.

</details>

### Exercise 2

What is the Hawking-Page transition in CFT language?

<details><summary><strong>Solution</strong></summary>

It is a transition between dominance of the thermal AdS saddle and dominance of the AdS black-hole saddle. In suitable large-$N$ gauge-theory CFTs, it is interpreted as a confinement/deconfinement-like transition, with the free energy changing from order one to order $N^2$.

</details>

### Exercise 3

Why does black-hole entropy scale like the number of CFT degrees of freedom?

<details><summary><strong>Solution</strong></summary>

The black-hole entropy is

$$
S_{\rm BH}=\frac{\operatorname{Area}}{4G_N}.
$$

Since

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N},
$$

large central charge means small $G_N$ and therefore a large area entropy in AdS units. This entropy is the coarse-grained logarithm of the number of CFT states in the corresponding energy range.

</details>

### Exercise 4

What is the thermofield double state dual to?

<details><summary><strong>Solution</strong></summary>

The thermofield double state

$$
|\operatorname{TFD}\rangle
=\frac{1}{\sqrt{Z(\beta)}}\sum_n e^{-\beta E_n/2}|n\rangle_L|n\rangle_R
$$

is dual to an eternal two-sided AdS black hole in suitable holographic CFTs.

</details>

### Exercise 5

How do islands modify the semiclassical entropy calculation?

<details><summary><strong>Solution</strong></summary>

Islands arise as quantum extremal surface saddles in the generalized entropy prescription. At late times in evaporating black-hole models, an island saddle can dominate over the no-island saddle. This changes the entanglement wedge of the radiation and produces a Page curve compatible with unitarity.

</details>

## References

- J. D. Bekenstein, “Black holes and entropy,” *Physical Review D* **7** (1973).
- S. W. Hawking, “Particle creation by black holes,” *Communications in Mathematical Physics* **43** (1975).
- E. Witten, “Anti de Sitter space, thermal phase transition, and confinement in gauge theories,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- J. Maldacena, “Eternal black holes in anti-de Sitter,” *Journal of High Energy Physics* **2003**.
- P. K. Kovtun, D. T. Son, and A. O. Starinets, “Viscosity in strongly interacting quantum field theories from black hole physics,” *Physical Review Letters* **94** (2005).
- J. Maldacena, S. H. Shenker, and D. Stanford, “A bound on chaos,” *Journal of High Energy Physics* **2016**.
- A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, “The entropy of bulk quantum fields and the entanglement wedge of an evaporating black hole,” *Journal of High Energy Physics* **2019**.

## Version history

- 2026-07-01: First polished draft. Added thermal-CFT setup, thermal AdS and black-hole saddles, Hawking-Page transition, entropy, heavy states, thermal correlators, quasinormal modes, hydrodynamics, chaos, Page curve, TFD state, microstate/ensemble caveats, exercises, and references.
