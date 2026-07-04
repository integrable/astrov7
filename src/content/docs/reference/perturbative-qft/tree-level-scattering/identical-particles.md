---
title: "Identical Particles"
description: "A calculation-oriented guide to identical-particle symmetrization, exchange interference, final-state phase-space factors, and identical-fermion signs in tree-level scattering."
sidebar:
  label: "Identical Particles"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§4, 10–11, 45, and 48; Weinberg 1995, Vol. I, chs. 3–4 and 6; Coleman 2019, chs. 11–12 and 21; Schwartz 2014, chs. 5, 7, and 12–13"
topics:
  - identical particles
  - symmetrization
  - exchange interference
  - phase space
  - spin statistics
  - tree-level scattering
canonicalTopics:
  - identical-particle-scattering
  - final-state-symmetry-factor
  - exchange-interference
  - identical-fermion-minus-sign
  - fock-space-symmetrization
researchStatus:
  established:
    - "The symmetrization of identical-particle states, exchange signs for fermions, and final-state phase-space factors are standard consequences of Fock-space normalization and spin–statistics."
  active:
    - "In collider and many-body applications, identical-particle bookkeeping is embedded in jet algorithms, inclusive measurements, parton showers, thermal rates, and density-matrix descriptions; those refinements belong to later pages."
---

## Summary

Identical particles create two related but distinct bookkeeping issues in scattering.

First, if two alternatives differ only by exchanging identical external particles, they are not separate physical histories. Their amplitudes must be combined before squaring. Schematically,

$$
\mathcal M_{\rm identical\ bosons}
=\mathcal M_{\rm direct}+\mathcal M_{\rm exchange},
\qquad
\mathcal M_{\rm identical\ fermions}
=\mathcal M_{\rm direct}-\mathcal M_{\rm exchange}.
$$

Second, if a phase-space integral labels two identical final particles as particle 3 and particle 4, it counts each physical final state twice. More generally, for $n_a$ identical final particles of species $a$,

$$
 d\Pi_{\rm final}^{\rm physical}
=\frac{1}{\prod_a n_a!}
 d\Pi_{\rm final}^{\rm labeled}.
$$

These are easy rules to state and surprisingly easy rules to misuse. The amplitude-level exchange rule concerns quantum interference. The phase-space factor concerns overcounting of final states. They are both needed, but they do different jobs.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Identical-particle scattering requires exchange amplitudes before squaring and a final-state phase-space factor after squaring](/figures/perturbative-qft/identical-particles-scattering.svg)

<figcaption>

For identical particles, exchanged final labels describe the same physical final state. Exchange-related amplitudes interfere before squaring, while the labeled phase-space integral must be divided by $2!$ for two identical final particles.

</figcaption>
</figure>

## Prerequisites

You should know the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), the phase-space normalization introduced in [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), the $2\to2$ kinematics in [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and the scalar and QED examples in [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) and [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/).

## Core idea

Identical-particle scattering is not obtained by pretending identical particles secretly carry invisible labels. Labels such as “particle 3” and “particle 4” are integration variables, not physical names. The physical final state is the occupation-number state with one particle in each occupied momentum, spin, color, or flavor mode.

The safe workflow is:

1. write the amplitude for the physical process, including all exchange-related diagrams and signs;
2. square the total amplitude, keeping exchange interference terms;
3. sum over unresolved spins, polarizations, colors, and flavors;
4. divide the labeled final-state phase space by the factorials for identical final particles;
5. integrate over the chosen physical region.

## Setup and conventions

We use the qft.org scattering normalization

$$
S_{fi}=\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

The Lorentz-invariant $n$-body phase-space measure is

$$
 d\Pi_n(P)
=(2\pi)^4\delta^{(4)}
\!\left(P-
\sum_{r=1}^n p_r\right)
\prod_{r=1}^n
\frac{d^3\mathbf p_r}{(2\pi)^3 2E_r}.
$$

This expression treats the momenta as labeled integration variables. If some final particles are identical, the physical phase space is obtained by dividing by the factorials that remove label overcounting.

We discuss ordinary relativistic scattering in infinite volume. In finite volume, the same facts appear as normalization factors for symmetrized or antisymmetrized multiparticle states.

## Identical states in Fock space

Fock space builds identical-particle statistics in from the start. For a real scalar field,

$$
|\mathbf p_1,\mathbf p_2\rangle
=a^\dagger(\mathbf p_1)a^\dagger(\mathbf p_2)|0\rangle
=a^\dagger(\mathbf p_2)a^\dagger(\mathbf p_1)|0\rangle,
$$

because scalar creation operators commute.

For identical fermions,

$$
|\mathbf p_1,s_1;\mathbf p_2,s_2\rangle
=b^\dagger_{s_1}(\mathbf p_1)b^\dagger_{s_2}(\mathbf p_2)|0\rangle,
$$

and exchanging the two creation operators gives a minus sign:

$$
b^\dagger_{s_1}(\mathbf p_1)b^\dagger_{s_2}(\mathbf p_2)
=-b^\dagger_{s_2}(\mathbf p_2)b^\dagger_{s_1}(\mathbf p_1).
$$

This is not an extra rule added to diagrams. It is the Fock-space origin of the exchange sign that appears when identical external fermions are put into a standard order.

## Add amplitudes before squaring

Suppose two diagrams lead to the same final state but differ by exchanging identical final particles. For identical bosons, the exchange-related contributions add:

$$
\mathcal M=\mathcal M_A+\mathcal M_B.
$$

The probability contains interference:

$$
|\mathcal M|^2
=|\mathcal M_A|^2+|\mathcal M_B|^2
+2\operatorname{Re}(\mathcal M_A\mathcal M_B^*).
$$

For identical fermions, the exchange contribution has the opposite sign:

$$
\mathcal M=\mathcal M_A-\mathcal M_B,
$$

so the interference term changes sign.

A canonical QED example is Møller scattering,

$$
e^-e^-\to e^-e^-.
$$

There are $t$- and $u$-channel photon-exchange contributions. The physical amplitude is schematically

$$
\mathcal M_{ee\to ee}=\mathcal M_t-\mathcal M_u,
$$

where the minus sign is the exchange sign for identical external fermions. The exact sign of each individual diagram depends on the global convention for ordering external spinors, but the relative exchange minus is physical within a fixed convention.

## Divide final-state phase space, not the amplitude

The factorial for identical final particles is not an amplitude factor. It appears in the phase-space integral because the labeled variables overcount physical states.

For a process with two identical final particles, a labeled two-body integral counts both

$$
(\mathbf p_3,\mathbf p_4)
\qquad\text{and}\qquad
(\mathbf p_4,\mathbf p_3)
$$

as separate points, even though they describe the same physical state. Therefore the full solid-angle integral must include

$$
 d\Pi_2^{\rm physical}=\frac{1}{2!}d\Pi_2^{\rm labeled}.
$$

Equivalently, one may integrate over only half of the labeled phase space and omit the factor $1/2!$. Do not do both.

For a $2\to2$ process in the center-of-mass frame, the labeled differential formula is

$$
\frac{d\sigma_{\rm labeled}}{d\Omega}
=\frac{1}{64\pi^2s}
\frac{|\mathbf p_f|}{|\mathbf p_i|}
\overline{|\mathcal M|^2}.
$$

If the two final particles are identical and the integration is over the full sphere, use

$$
\frac{d\sigma_{\rm physical}}{d\Omega}
=\frac{1}{2!}
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f|}{|\mathbf p_i|}
\overline{|\mathcal M|^2}.
$$

Strictly speaking, this differential expression is a density on labeled solid angle. The physical total cross section is unambiguous after either dividing by $2!$ over the full labeled sphere or integrating over one representative half of the final-state configurations.

## Example: real scalar contact scattering

Consider real scalar $\phi^4$ theory,

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4.
$$

At tree level, identical scalar scattering

$$
\phi\phi\to\phi\phi
$$

has the contact amplitude

$$
\mathcal M=-\lambda.
$$

For equal masses in the center-of-mass frame, elastic kinematics gives $|\mathbf p_f|=|\mathbf p_i|$. With no spin average,

$$
\frac{d\sigma_{\rm physical}}{d\Omega}
=\frac12\frac{\lambda^2}{64\pi^2s}.
$$

Integrating over the full sphere gives

$$
\sigma_{\rm physical}
=\frac{\lambda^2}{32\pi s}
$$

for this pure contact example. If one instead integrates over only one hemisphere of final directions, the factor $1/2$ is not inserted, and the same total cross section is obtained.

## What counts as distinguishable?

Particles are distinguishable if the final states carry different measured or intrinsic labels: different species, different charges, different flavors, or different external tags. For example,

$$
e^-\mu^-\to e^-\mu^-
$$

has distinguishable final particles because the electron and muon are different species.

Particles of the same species but different momenta are still identical particles. The momentum labels specify occupied modes, not particle names. Similarly, if two photons have different polarizations, the final states with one photon in each polarization mode are orthogonal components to be summed over if the polarizations are unresolved; the particles are not converted into different species.

Internal quantum numbers require care. If two final quarks have different flavors, they are distinguishable. If they have the same flavor but different colors and color is unobserved, the calculation should be performed with explicit color labels and then summed over final colors. The identical-particle issue applies to final states with the same species and the same unresolved quantum-number content.

## Identical particles in the initial state

The final-state $1/n!$ is a phase-space overcounting factor. There is no universal matching rule that says “divide by $2!$ for identical particles in the initial state” in an $S$-matrix cross section. The incoming state is part of the preparation.

For a specified two-particle incoming state, the flux factor and state normalization already define the scattering probability. In a gas, plasma, beam luminosity calculation, or Boltzmann equation, one may include statistical factors to avoid double-counting unordered initial pairs. That is a rate-counting issue in the ensemble, not a new Feynman-rule factor.

This distinction is one of the most common sources of factor-of-two errors.

## Common pitfalls

**Dividing the amplitude by $2!$.** Identical final-state factorials divide the phase-space integral, not the amplitude. Exchange-related amplitudes must first be added or subtracted coherently.

**Both dividing by $2!$ and integrating over half the angles.** These are two equivalent ways to avoid overcounting. Using both undercounts the physical final states by a factor of two.

**Forgetting exchange interference.** Identical-particle effects are not only global factors. If direct and exchanged contributions lead to the same physical state, their interference can be numerically important.

**Adding an initial-state factorial automatically.** Cross sections are defined for prepared incoming states. Initial-state combinatorics enters when converting cross sections into rates for unordered pairs in an ensemble.

**Calling particles distinguishable because their momenta differ.** Different momenta label different modes of the same identical-particle Fock space. They do not make the particles different species.

## Relations to other pages

- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) gives the $\phi^4$ contact amplitude used in the example.
- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) contains the Bhabha and Møller-style diagrammatic patterns where exchange terms matter.
- [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explains the spin sums that are performed after the identical-particle amplitude has been assembled.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) explains how exchanging identical final particles often corresponds to interchanging $t$ and $u$.
- [Connected Correlators and Scattering](/perturbative-qft/from-correlators-to-s-matrix/connected-correlators-and-scattering/) explains why disconnected products and independently occurring processes are separated from the connected scattering amplitude.

## Research status

This page is textbook-standard for ordinary relativistic scattering. The subtleties are practical rather than conceptual: realistic measurements may use jets, inclusive bins, detector tags, density matrices, thermal ensembles, or many-body occupation factors, and each context has its own counting convention.

## Exercises

### Exercise 1: Why the two-body phase space has a half

Let $F(p_3,p_4)$ be symmetric under $p_3\leftrightarrow p_4$. Show that the labeled integral

$$
I_{\rm lab}=\int d\Pi_2^{\rm labeled}\, F(p_3,p_4)
$$

counts each physical final state twice when particles 3 and 4 are identical.

<details>
<summary><strong>Solution</strong></summary>

For every labeled point $(p_3,p_4)$ in the phase-space integral, the exchanged point $(p_4,p_3)$ is also present. If the particles are identical, these two labeled points represent the same occupation-number final state. Since $F$ is symmetric, the two contributions are equal. Therefore the physical integral is

$$
I_{\rm phys}=\frac12 I_{\rm lab}.
$$

This is the origin of the $1/2!$ factor for two identical final particles.

</details>

### Exercise 2: Contact scattering of identical scalars

Using $\mathcal M=-\lambda$ for tree-level real $\phi^4$ scattering, derive

$$
\frac{d\sigma}{d\Omega}
=\frac{\lambda^2}{128\pi^2s}
$$

for identical final particles in the center-of-mass frame with equal masses.

<details>
<summary><strong>Solution</strong></summary>

The labeled two-body formula is

$$
\frac{d\sigma_{\rm labeled}}{d\Omega}
=\frac{1}{64\pi^2s}
\frac{|\mathbf p_f|}{|\mathbf p_i|}
|\mathcal M|^2.
$$

Elastic equal-mass kinematics gives $|\mathbf p_f|=|\mathbf p_i|$, and the contact amplitude gives $|\mathcal M|^2=\lambda^2$. Because the two final scalars are identical and the full labeled solid angle is being used,

$$
\frac{d\sigma}{d\Omega}
=\frac12\frac{\lambda^2}{64\pi^2s}
=\frac{\lambda^2}{128\pi^2s}.
$$

</details>

### Exercise 3: Exchange interference sign

Suppose two diagrams give amplitudes $\mathcal M_A$ and $\mathcal M_B$ for the same final state after exchanging two identical particles. Compute the interference term for identical bosons and for identical fermions.

<details>
<summary><strong>Solution</strong></summary>

For identical bosons,

$$
\mathcal M_B^{\rm total}=\mathcal M_A+\mathcal M_B,
$$

so

$$
|\mathcal M|^2
=|\mathcal M_A|^2+|\mathcal M_B|^2
+2\operatorname{Re}(\mathcal M_A\mathcal M_B^*).
$$

For identical fermions,

$$
\mathcal M_F^{\rm total}=\mathcal M_A-\mathcal M_B,
$$

so

$$
|\mathcal M|^2
=|\mathcal M_A|^2+|\mathcal M_B|^2
-2\operatorname{Re}(\mathcal M_A\mathcal M_B^*).
$$

The sign difference is the exchange sign from anticommuting fermionic creation operators.

</details>

### Exercise 4: Full sphere or half sphere

For two identical final particles in a two-body center-of-mass process, explain why integrating over the full solid angle with a factor $1/2!$ is equivalent to integrating over one representative half of the solid angle with no factor $1/2!$.

<details>
<summary><strong>Solution</strong></summary>

In the center-of-mass frame, the two final momenta are back-to-back. The direction $\hat{\mathbf p}$ and the opposite direction $-\hat{\mathbf p}$ correspond to exchanging the two identical final particles. Thus the full sphere contains two labeled representatives of each physical final state. Dividing the full-sphere integral by $2$ gives the same result as integrating over a hemisphere that chooses one representative of each exchanged pair.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially the sections on spin–statistics, scalar scattering, fermion Feynman rules, and spin-averaged cross sections.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3–4 and 6, for scattering theory, identical-particle normalization, cluster decomposition, and Feynman rules.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5, 7, and 12–13, for cross sections, Feynman rules, identical particles, and QED examples.

### Deeper references

- S. Coleman, *Lectures on Quantum Field Theory*, especially the chapters on scattering, phase space, and fermion Feynman rules.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, for standard applications to scalar scattering and Møller/Bhabha-type QED processes.

## Version history

- **2026-06-12:** Initial standardized page.
