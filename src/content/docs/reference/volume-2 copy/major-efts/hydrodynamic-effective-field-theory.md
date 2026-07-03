---
title: "Hydrodynamic Effective Field Theory"
description: "Hydrodynamics as the long-wavelength effective field theory of conserved densities, local equilibrium, constitutive relations, noise, and Schwinger–Keldysh constraints."
sidebar:
  label: "Hydrodynamic Effective Field Theory"
  order: 100
level: Advanced
status: "Polished draft"
source: "Landau and Lifshitz, Fluid Mechanics; Forster 1975; Kovtun 2012; Crossley, Glorioso, and Liu 2017; Haehl, Loganayagam, and Rangamani; Burgess 2020; Altland and Simons 2023."
topics:
  - hydrodynamic EFT
  - conserved densities
  - Schwinger–Keldysh effective action
  - transport coefficients
  - diffusion
  - sound modes
canonicalTopics:
  - hydrodynamic-effective-field-theory
  - hydrodynamic-modes
  - schwinger-keldysh-hydrodynamics
researchStatus:
  established:
    - "Hydrodynamics is the universal long-wavelength EFT of conserved quantities and spontaneously broken continuous symmetries near local thermal equilibrium."
  active:
    - "Modern hydrodynamic EFT, fluctuating hydrodynamics, anomalous transport, higher-form hydrodynamics, fracton hydrodynamics, and far-from-equilibrium extensions remain active research areas."
---

## Summary

**Hydrodynamic effective field theory** is the long-wavelength EFT of the slow variables that cannot relax quickly because conservation laws or broken symmetries protect them. Ordinary hydrodynamics is not merely a set of nineteenth-century fluid equations. It is a universal EFT whose degrees of freedom are local temperature, local chemical potentials, velocity fields, and sometimes Goldstone-like fields.

The basic hierarchy is

$$
\omega\tau_{\text{micro}}\ll 1,
\qquad
|\mathbf k|\ell_{\text{micro}}\ll 1,
$$

where $\tau_{\text{micro}}$ and $\ell_{\text{micro}}$ are microscopic relaxation scales. In this regime, most microscopic variables have already relaxed. The remaining long-lived variables are controlled by conservation laws such as

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
\partial_\mu J_a^\mu=0,
$$

together with constitutive relations that express currents in terms of hydrodynamic fields and their gradients.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![Hydrodynamic EFT workflow from microscopic theory to local equilibrium, conservation laws, Schwinger–Keldysh constraints, constitutive relations, and universal modes.](/figures/renormalization-rg-eft/hydrodynamic-effective-field-theory-map.svg)

<figcaption>

Hydrodynamic EFT integrates out fast microscopic relaxation and keeps only protected slow variables. Conservation laws fix the equations of motion, the derivative expansion fixes constitutive relations, and Schwinger–Keldysh plus KMS structure organizes dissipation, noise, and response functions.

</figcaption>
</figure>

The most important lesson is simple:

$$
\text{hydrodynamics is EFT, with derivatives as the expansion parameter.}
$$

The coefficients in this expansion are transport coefficients such as viscosity, conductivity, diffusion constants, sound attenuation, and thermal conductivity. They are not fixed by symmetry alone. They are Wilson coefficients of the hydrodynamic EFT, to be matched from microscopic theory, experiment, lattice simulation, kinetic theory, or holography.

## Prerequisites

You should know the logic of [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/), especially [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) and [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/). You should also know basic thermodynamics, conservation laws, and linear response.

This page uses mostly-minus Lorentzian conventions. The fluid four-velocity is normalized as

$$
u^\mu u_\mu=1.
$$

To avoid sign confusion with spatial projectors in mostly-minus signature, define

$$
P^{\mu\nu}\equiv u^\mu u^\nu-\eta^{\mu\nu}.
$$

In the local rest frame, $u^\mu=(1,\mathbf 0)$ and $P^{ij}=\delta^{ij}$.

## Core idea

Hydrodynamics starts from a brutal observation: most microscopic details are irrelevant at late times and long distances. A system may be made of quarks and gluons, electrons and phonons, atoms in a trap, spins on a lattice, or a strongly coupled plasma with a holographic dual. If it locally equilibrates and has the same conserved quantities and symmetries, its longest-wavelength behavior is described by the same hydrodynamic structure.

The slow variables are the densities of conserved quantities. For a relativistic fluid with one conserved $U(1)$ charge, a convenient set is

$$
T(x),
\qquad
\mu(x),
\qquad
u^\mu(x),
$$

where $T$ is local temperature, $\mu$ is local chemical potential, and $u^\mu$ is the local velocity. The stress tensor and current are then expanded in gradients:

$$
T^{\mu\nu}=T^{\mu\nu}_{(0)}+T^{\mu\nu}_{(1)}+T^{\mu\nu}_{(2)}+\cdots,
\qquad
J^\mu=J^\mu_{(0)}+J^\mu_{(1)}+J^\mu_{(2)}+\cdots.
$$

Here the subscript counts derivatives. Conservation laws are the equations of motion. The constitutive relations are the EFT expansion. Transport coefficients are Wilson coefficients.

This is why hydrodynamic equations are universal but not completely predictive from symmetry alone. Symmetry tells us the possible terms. Matching tells us the coefficients.

## Ideal hydrodynamics

At zeroth derivative order, the stress tensor and current are

$$
T^{\mu\nu}_{(0)}
=\epsilon u^\mu u^\nu+p P^{\mu\nu},
\qquad
J^\mu_{(0)}=n u^\mu.
$$

Here $\epsilon$ is energy density, $p$ is pressure, and $n$ is charge density. The equation of state gives

$$
p=p(T,\mu),
\qquad
\epsilon=\epsilon(T,\mu),
\qquad
n=n(T,\mu).
$$

The thermodynamic identity is

$$
dp=s\,dT+n\,d\mu,
\qquad
\epsilon+p=Ts+\mu n,
$$

where $s$ is entropy density. Conservation then gives nonlinear equations for $T$, $\mu$, and $u^\mu$.

In the absence of conserved charge, the ideal stress tensor reduces to

$$
T^{\mu\nu}_{(0)}=(\epsilon+p)u^\mu u^\nu-p\eta^{\mu\nu}.
$$

For a conformal fluid in $d$ spacetime dimensions, tracelessness gives

$$
T^\mu{}_\mu=0
\quad\Longrightarrow\quad
\epsilon=(d-1)p.
$$

This is not a statement about all fluids. It is a statement about fluids whose microscopic theory is conformal and whose state does not introduce explicit scale-breaking parameters beyond $T$ and $\mu$.

## First derivative corrections

At first derivative order, dissipative transport appears. For a neutral relativistic fluid, the stress tensor may be written schematically as

$$
T^{\mu\nu}
=\epsilon u^\mu u^\nu+pP^{\mu\nu}
-\eta\,\sigma^{\mu\nu}
-\zeta\,P^{\mu\nu}\theta
+O(\partial^2),
$$

where

$$
\theta\equiv \partial_\mu u^\mu
$$

is the expansion and $\sigma^{\mu\nu}$ is the shear tensor, the symmetric traceless part of the velocity gradient transverse to $u^\mu$.

The constants

$$
\eta,
\qquad
\zeta
$$

are the shear and bulk viscosities. They measure how momentum currents respond to gradients in velocity. They are not arbitrary if the fluid has extra symmetries. For example, conformal invariance forbids bulk viscosity in flat space:

$$
\zeta=0
\qquad
\text{for a conformal fluid.}
$$

For a charged fluid, a first-derivative charge current includes a conductivity term. In a common frame convention,

$$
J^\mu
=n u^\mu
-\sigma_Q P^{\mu\nu}\partial_\nu\left(\frac{\mu}{T}\right)
+O(\partial^2),
$$

up to terms involving external electromagnetic fields if the symmetry is coupled to a background gauge field.

The frame convention matters. One may define $u^\mu$ so that the energy flux vanishes in the local rest frame, or choose another convention. A frame choice is not new physics; it is a field redefinition inside the hydrodynamic EFT.

:::note[Hydrodynamic frames are EFT bases]
The Landau frame, Eckart frame, entropy frame, and related choices are like operator bases in EFT. They change the definition of variables such as $T$, $\mu$, and $u^\mu$ at derivative order. Physical retarded correlators and dispersion relations do not depend on the frame when computed consistently.
:::

## Diffusion as the simplest example

The cleanest hydrodynamic mode is diffusion. Suppose a conserved density $n(t,\mathbf x)$ has current

$$
\mathbf j=-D\nabla n
$$

near equilibrium, where $D$ is the diffusion constant. Conservation gives

$$
\partial_t n+\nabla\cdot\mathbf j=0,
$$

so

$$
\partial_t n-D\nabla^2 n=0.
$$

For a Fourier mode $n\sim e^{-i\omega t+i\mathbf k\cdot\mathbf x}$,

$$
-i\omega+D\mathbf k^2=0,
$$

or

$$
\omega=-iD\mathbf k^2+O(k^4).
$$

This pole is not a particle. It is a collective relaxation mode. Its location is fixed by conservation and the derivative expansion.

In linear response, if $\chi$ is the static susceptibility, the retarded density correlator has the universal hydrodynamic form

$$
G^R_{nn}(\omega,\mathbf k)
=\frac{\chi D\mathbf k^2}{-i\omega+D\mathbf k^2}
+\text{contact and analytic terms}.
$$

The pole location is universal. The values of $D$ and $\chi$ are microscopic data.

## Sound and shear modes

Energy-momentum conservation gives propagating sound modes. For a neutral fluid linearized around equilibrium, the sound dispersion has the form

$$
\omega_\pm(k)=\pm c_s k-\frac{i}{2}\Gamma_s k^2+O(k^3),
$$

where

$$
c_s^2=\left.\frac{\partial p}{\partial\epsilon}\right|_{s/n}
$$

is the speed of sound and $\Gamma_s$ is the sound attenuation constant. In a relativistic fluid in $d$ spacetime dimensions, the attenuation contains viscosities schematically as

$$
\Gamma_s\sim \frac{1}{\epsilon+p}
\left[\frac{2(d-2)}{d-1}\eta+\zeta+\cdots\right],
$$

with charge and heat transport adding further terms when present.

There are also shear diffusion modes with dispersion

$$
\omega=-i\frac{\eta}{\epsilon+p}k^2+O(k^4).
$$

Again, the form is universal and the coefficient is physical data.

## Effective action viewpoint

Hydrodynamics looks strange from the usual Lagrangian viewpoint because dissipation is essential. A single ordinary action in real time gives time-reversal-symmetric equations unless one adds nonlocality, boundary conditions, or extra variables. The modern EFT answer is to use a closed-time-path, or Schwinger–Keldysh, description.

The Schwinger–Keldysh generating functional doubles the sources:

$$
Z[g_1,A_1;g_2,A_2]
=\operatorname{Tr}\left(
U[g_1,A_1]\rho_0 U[g_2,A_2]^\dagger
\right).
$$

It is often useful to write

$$
Z=e^{iW}.
$$

Hydrodynamic EFT then constructs a local effective action for doubled hydrodynamic variables and doubled sources. The resulting theory must obey several structural constraints:

| Constraint | Meaning |
|---|---|
| Unitarity | $Z[A,g;A,g]=1$ for identical sources on the two contours. |
| Reality | Complex conjugation exchanges the two Schwinger–Keldysh legs. |
| Positivity | Noise and dissipation are constrained by a positive imaginary part. |
| KMS structure | Thermal equilibrium imposes fluctuation–dissipation relations. |
| Symmetries | Spacetime, internal, gauge, and sometimes higher-form symmetries constrain allowed terms. |

This is the EFT origin of the fluctuation–dissipation theorem. Dissipation and noise are not optional add-ons. They are linked by thermal consistency.

## The derivative expansion

Hydrodynamic power counting assigns one derivative to quantities such as

$$
\partial_\mu T,
\qquad
\partial_\mu\mu,
\qquad
\partial_\mu u^\nu,
\qquad
F_{\mu\nu},
\qquad
\partial_\mu g_{\nu\rho},
$$

where external fields are counted according to the physical regime. The expansion parameter is not simply $E/M$. It is a gradient expansion:

$$
\partial\sim \omega,|\mathbf k|\ll \tau_{\text{micro}}^{-1},\ell_{\text{micro}}^{-1}.
$$

Higher derivative terms correct constitutive relations, response functions, and dispersion relations. For example,

$$
\omega=-iD k^2-iD_2 k^4+O(k^6)
$$

for diffusion. The coefficient $D_2$ is a higher-order transport coefficient. It is analogous to a higher-dimension Wilson coefficient in ordinary EFT.

The expansion can fail even at small $k$ if there are additional long-lived degrees of freedom not included in the hydrodynamic variables. Examples include weakly broken symmetries, quasihydrodynamic modes, order-parameter relaxation near a critical point, Goldstone modes, and gauge-field constraints in plasmas.

## Matching transport coefficients

Hydrodynamic EFT does not predict numerical values of all transport coefficients. It organizes them and relates them to microscopic correlation functions. For example, the shear viscosity is given by the Kubo formula

$$
\eta
=\lim_{\omega\to 0}\frac{1}{\omega}\operatorname{Im}G^R_{T^{xy}T^{xy}}(\omega,\mathbf 0),
$$

up to sign conventions for the retarded correlator. Similarly, conductivity may be extracted from the current-current retarded correlator:

$$
\sigma
=\lim_{\omega\to 0}\frac{1}{\omega}\operatorname{Im}G^R_{J^xJ^x}(\omega,\mathbf 0).
$$

The microscopic method used to compute these correlators is separate from hydrodynamics. It might be kinetic theory, perturbation theory, lattice simulation in Euclidean signature with analytic continuation, gauge/gravity duality, experiment, or numerical many-body methods.

The EFT logic is:

$$
\text{symmetry and conservation}
\quad\Longrightarrow\quad
\text{allowed hydrodynamic structures},
$$

and

$$
\text{microscopic input}
\quad\Longrightarrow\quad
\text{transport coefficients}.
$$

## Entropy and positivity

Dissipative coefficients are constrained by the second law. In first-order ordinary hydrodynamics, local entropy production gives conditions such as

$$
\eta\ge 0,
\qquad
\zeta\ge 0,
\qquad
\sigma\ge 0.
$$

This is the hydrodynamic version of unitarity and positivity. In modern Schwinger–Keldysh EFT, these inequalities are encoded in the structure of the effective action: dissipative terms come with noise terms whose coefficients make the statistical weight well behaved.

The entropy-current analysis is not obsolete, but the EFT perspective is cleaner. It treats dissipation, noise, and response as one package rather than three unrelated rules.

## Anomalous and generalized hydrodynamics

If the microscopic theory has anomalies or higher-form symmetries, hydrodynamics changes. For example, anomalous currents can contain terms proportional to vorticity or magnetic fields:

$$
J^\mu
=n u^\mu+\xi_B B^\mu+\xi_\omega\omega^\mu+\cdots,
$$

where $B^\mu$ is the magnetic field in the local fluid frame and $\omega^\mu$ is vorticity. The coefficients are not arbitrary; anomaly matching and thermodynamic consistency constrain them.

Higher-form symmetries lead to hydrodynamics of extended conserved fluxes rather than ordinary particle number. Magnetohydrodynamics, superfluid hydrodynamics, elasticity, and fracton-like systems can all be viewed as generalized hydrodynamic EFTs with extra conservation laws, constraints, or Goldstone fields.

The moral is that hydrodynamics is not one theory. It is a recipe:

$$
\text{slow variables} + \text{symmetries} + \text{locality} + \text{KMS/positivity}
\quad\Longrightarrow\quad
\text{hydrodynamic EFT}.
$$

## Common pitfalls

**Thinking hydrodynamics requires weak coupling.** It does not. Hydrodynamics requires local equilibration and a separation between slow conserved modes and fast nonconserved modes. Strongly coupled systems can be excellent fluids.

**Treating transport coefficients as symmetry data.** Symmetry fixes tensor structures and relations. It does not generally fix $\eta$, $\zeta$, $D$, $\sigma$, or higher-order transport coefficients.

**Confusing hydrodynamic modes with particles.** Diffusion and sound poles are collective response poles. They need not correspond to stable quasiparticles.

**Forgetting noise.** Dissipative hydrodynamics without fluctuations is a classical deterministic approximation. At sufficiently long distances, hydrodynamic fluctuations can renormalize transport and produce long-time tails.

**Ignoring frame dependence.** Variables such as $T$, $\mu$, and $u^\mu$ are not uniquely defined beyond leading order. Frame-dependent coefficients are not directly observable.

**Using hydrodynamics outside its domain.** Hydrodynamics is not a magic approximation for all low energies. It can fail when local equilibrium is absent, when gradients are too large, or when extra slow variables have been omitted.

## Relations to other pages

This page is the hydrodynamic EFT entry in the Major Effective Field Theories chapter. It connects directly to [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Nonlinear Sigma Models](/renormalization-rg-eft/major-efts/nonlinear-sigma-models/), and [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/). It also prepares later pages on finite-temperature QFT, Schwinger–Keldysh methods, linear response, transport, anomalies, and holography.

The conceptual difference from ordinary EFT is that hydrodynamic EFT is intrinsically real-time and dissipative. The conceptual similarity is that it is still organized by symmetries, locality, fields, power counting, and Wilson coefficients.

## Research status

The existence of hydrodynamics as the universal long-wavelength theory of conserved quantities is established. The derivative expansion, Kubo formulas, and first-order transport are standard. Modern effective-action formulations using Schwinger–Keldysh variables and KMS constraints are now central research tools rather than merely formal reorganizations.

Active directions include fluctuating hydrodynamics, anomalous hydrodynamics, hydrodynamics with higher-form symmetries, hydrodynamics of active matter and open quantum systems, fracton hydrodynamics, far-from-equilibrium attractors, and the interface between hydrodynamics and quantum chaos.

## Exercises

### Exercise 1: The diffusion pole

Starting from

$$
\partial_t n+\nabla\cdot\mathbf j=0,
\qquad
\mathbf j=-D\nabla n,
$$

derive the hydrodynamic dispersion relation for a Fourier mode $n\sim e^{-i\omega t+i\mathbf k\cdot\mathbf x}$.

<details><summary><strong>Solution</strong></summary>

Substitute the constitutive relation into the conservation equation:

$$
\partial_t n-D\nabla^2 n=0.
$$

For $n\sim e^{-i\omega t+i\mathbf k\cdot\mathbf x}$,

$$
\partial_t n=-i\omega n,
\qquad
\nabla^2n=-\mathbf k^2 n.
$$

Therefore

$$
-i\omega n+D\mathbf k^2 n=0.
$$

For a nonzero fluctuation,

$$
\omega=-iD\mathbf k^2.
$$

This is a diffusive pole, not a propagating particle pole.

</details>

### Exercise 2: Entropy production and viscosity

For a neutral nonrelativistic fluid, the viscous stress contains terms proportional to shear and expansion. Explain why negative shear viscosity would contradict the second law.

<details><summary><strong>Solution</strong></summary>

The local entropy production from shear takes the schematic form

$$
\partial_t s+\nabla\cdot\mathbf j_s
\supset
\frac{\eta}{T}\sigma_{ij}\sigma_{ij}.
$$

The quantity $\sigma_{ij}\sigma_{ij}$ is nonnegative. Temperature is positive in equilibrium thermodynamics. Therefore local entropy production is nonnegative for arbitrary shear only if

$$
\eta\ge 0.
$$

A negative shear viscosity would mean that shear gradients systematically decrease entropy and amplify rather than damp velocity gradients, contradicting the ordinary local second law.

</details>

### Exercise 3: Conformal bulk viscosity

Use the flat-space trace condition $T^\mu{}_\mu=0$ to explain why a conformal fluid cannot have a first-order bulk-viscosity term.

<details><summary><strong>Solution</strong></summary>

The first-order bulk-viscosity correction has the form

$$
\Delta T^{\mu\nu}_{\zeta}=-\zeta P^{\mu\nu}\theta.
$$

Taking the trace in $d$ spacetime dimensions gives a contribution proportional to

$$
\Delta T^\mu{}_{\mu,\zeta}
\propto
-\zeta(d-1)\theta.
$$

The expansion $\theta$ is an allowed independent first-derivative scalar. If the microscopic theory is conformal and the state is described by conformal hydrodynamics in flat space, the stress tensor must remain traceless. Therefore the coefficient of this trace-producing term must vanish:

$$
\zeta=0.
$$

</details>

## References

- Landau and Lifshitz, *Fluid Mechanics*, for classical hydrodynamics, viscosity, sound, and thermodynamics.
- D. Forster, *Hydrodynamic Fluctuations, Broken Symmetry, and Correlation Functions*, for hydrodynamic modes and fluctuation physics.
- P. Kovtun, lectures and reviews on relativistic hydrodynamics and Kubo formulas.
- Crossley, Glorioso, and Liu, and Haehl, Loganayagam, and Rangamani, for modern Schwinger–Keldysh effective actions for dissipative hydrodynamics.
- Son and collaborators, for anomalous hydrodynamics and symmetry-based transport.
- Altland and Simons, *Condensed Matter Field Theory*, for many-body field theory, response, and hydrodynamic-adjacent methods.
- Burgess, *Introduction to Effective Field Theory*, for EFT logic, hierarchies of scale, and the interpretation of hydrodynamics among low-energy descriptions.

## Version history

- 2026-06-19: First polished draft. Added hydrodynamic variables, constitutive relations, diffusion and sound examples, Schwinger–Keldysh EFT logic, transport matching, pitfalls, exercises, and a workflow figure.
