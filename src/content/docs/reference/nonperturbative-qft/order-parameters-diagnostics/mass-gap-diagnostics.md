---
title: "Mass-Gap Diagnostics"
description: "Explains how Euclidean correlators, finite-volume spectra, spectral densities, and transfer matrices diagnose a mass gap in nonperturbative QFT."
sidebar:
  label: "Mass-Gap Diagnostics"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki; Schwartz; Di Francesco–Mathieu–Sénéchal; Zinn-Justin; Fradkin; Shifman; Clay Mathematics Institute."
topics:
  - mass gap
  - spectral gap
  - Euclidean correlators
  - transfer matrix
  - spectral density
  - lattice spectroscopy
canonicalTopics:
  - nonperturbative-qft
  - mass-gap
  - spectral-representation
  - lattice-field-theory
  - phase-diagnostics
researchStatus:
  established:
    - "Euclidean time correlators, transfer-matrix spectra, and spectral representations provide standard diagnostics for energy gaps in specified operator channels."
  active:
    - "The four-dimensional pure Yang–Mills mass gap is strongly supported by physics evidence but remains an open rigorous continuum construction problem."
---

## Summary

A **mass gap** means that the vacuum is separated from the lowest physical excitation by a positive energy. In a finite spatial volume, one can write

$$
\Delta(L)=E_1(L)-E_0(L),
$$

but the nonperturbative question is about the infinite-volume and continuum limits. A relativistic QFT is said to have a mass gap $\Delta>0$ when the vacuum is isolated from the rest of the physical spectrum and there are no states with arbitrarily small invariant mass above it.

The most practical diagnostic is Euclidean time decay. For an operator $\mathcal O$ with the vacuum contribution subtracted,

$$
C_{\mathcal O}(\tau)
=\langle\mathcal O(\tau)\mathcal O^\dagger(0)\rangle_c
=\sum_{n>0}|\langle n|\mathcal O|0\rangle|^2e^{-(E_n-E_0)\tau}.
$$

At large Euclidean time, the lightest state with the same quantum numbers and nonzero overlap dominates:

$$
C_{\mathcal O}(\tau)\sim Ae^{-\Delta_{\mathcal O}\tau}.
$$

Thus mass-gap diagnostics are spectral diagnostics expressed through correlator measurements. This expression is useful: it turns Hilbert-space information into something computable in Euclidean path integrals and lattice simulations.

The caveat is crucial. A correlator measures the lightest state **visible to that operator**. A gapped channel is not automatically a fully gapped theory, and a mass gap is not the same thing as confinement. A massive scalar theory is gapped. Pure Yang–Mills is expected to be both gapped and confining. QED in four dimensions has no mass gap because of the photon. Same word, very different physics.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Spectral extraction of a mass gap from Euclidean time correlators.](/figures/nonperturbative-qft/mass-gap-spectral-extraction.svg)

<figcaption>

A Euclidean correlator projects onto energy eigenstates. After subtracting the vacuum contribution, the lowest state with nonzero overlap controls the large-$\tau$ slope of $\log C_{\mathcal O}(\tau)$. The slope gives the channel gap $\Delta_{\mathcal O}$.

</figcaption>
</figure>

## Prerequisites

You should know [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/), [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/).

It also helps to know the spectral representation of two-point functions, the transfer-matrix interpretation of Euclidean evolution, and the difference between local gauge-invariant operators and gauge-variant fields.

## Core idea

A mass gap is not first a diagram. It is a statement about the spectrum.

Let $H$ be the Hamiltonian in a spatial box, and let $|0\rangle$ be the vacuum. The finite-volume energy gaps are

$$
\Delta_n(L)=E_n(L)-E_0(L).
$$

An operator $\mathcal O$ detects the subset of states for which

$$
\langle n|\mathcal O|0\rangle\neq0.
$$

That is why the Euclidean correlator

$$
C_{\mathcal O}(\tau)=\langle0|\mathcal O(\tau)\mathcal O^\dagger(0)|0\rangle_c
$$

has a sum-of-exponentials expansion. Large Euclidean time is a filter: heavy states die quickly, light states die slowly, and the slowest surviving exponential determines the observed gap.

A theory has a mass gap only if every physical channel above the vacuum is bounded away from zero energy in the infinite-volume limit, with appropriate qualifications for superselection sectors, topological degeneracies, finite-temperature states, and boundary conditions.

## Setup and conventions

We use Hamiltonian language for spectra and Euclidean language for correlators. Euclidean time evolution is

$$
\mathcal O(\tau)=e^{H\tau}\mathcal O(0)e^{-H\tau}.
$$

For a vacuum correlator with $\tau>0$,

$$
\langle0|\mathcal O(\tau)\mathcal O^\dagger(0)|0\rangle
=\sum_n \langle0|\mathcal O|n\rangle
\langle n|\mathcal O^\dagger|0\rangle e^{-(E_n-E_0)\tau}.
$$

If $\langle\mathcal O\rangle\neq0$, the $n=0$ term must be subtracted to obtain the connected correlator:

$$
C_{\mathcal O}(\tau)
=\langle\mathcal O(\tau)\mathcal O^\dagger(0)\rangle
-|\langle\mathcal O\rangle|^2.
$$

Then

$$
C_{\mathcal O}(\tau)
=\sum_{n>0}Z_n^{(\mathcal O)}e^{-\Delta_n\tau},
\qquad
Z_n^{(\mathcal O)}=|\langle n|\mathcal O^\dagger|0\rangle|^2.
$$

The channel gap extracted from $\mathcal O$ is

$$
\Delta_{\mathcal O}=\min\{\Delta_n:Z_n^{(\mathcal O)}\neq0\}.
$$

This is not necessarily the absolute mass gap of the whole theory. It is the gap in the sector that $\mathcal O$ can see.

## Channel gaps and the physical mass gap

The phrase “the mass gap” is often used in three related ways.

| Object | Meaning | Typical diagnostic |
|---|---|---|
| Channel gap $\Delta_{\mathcal O}$ | Lightest state that couples to a chosen operator. | Large-$\tau$ decay of $C_{\mathcal O}(\tau)$. |
| Spectral gap in finite volume | Difference $E_1(L)-E_0(L)$ in a finite box. | Hamiltonian diagonalization or transfer matrix. |
| Infinite-volume mass gap | Positive lower edge of the physical spectrum above the vacuum. | Continuum limit of spectra and correlators. |

A page, paper, or simulation should say which one it means. The distinction matters in all the interesting cases.

For example, in a theory with a conserved global charge, a neutral local operator may see only neutral states, while the lightest charged excitation belongs to a different superselection sector. In a gauge theory, a gauge-variant elementary field is not a physical operator, so the physical mass gap is probed by gauge-invariant operators such as glueball operators, meson operators, baryon operators, or line-operator observables.

In a broken continuous symmetry phase, Goldstone modes make the theory gapless even if radial modes are massive. In a topological phase, local correlators can be gapped while nonlocal probes and ground-state structure carry essential information.

## Euclidean effective masses

On a lattice with Euclidean time spacing $a_t$, a standard estimator is the effective mass

$$
m_{\text{eff}}(\tau)
=\frac{1}{a_t}\log\frac{C(\tau)}{C(\tau+a_t)}.
$$

If

$$
C(\tau)=Ae^{-\Delta\tau},
$$

then

$$
m_{\text{eff}}(\tau)=\Delta.
$$

If several states contribute,

$$
C(\tau)=A_1e^{-\Delta_1\tau}+A_2e^{-\Delta_2\tau}+\cdots,
\qquad
\Delta_1<\Delta_2<\cdots,
$$

then

$$
m_{\text{eff}}(\tau)\to\Delta_1
\qquad \tau\to\infty,
$$

provided $A_1\neq0$. In practice, large $\tau$ is noisy, so spectroscopy uses improved operators and correlation matrices.

A common variational method builds several operators $\mathcal O_i$ with the same quantum numbers and studies

$$
C_{ij}(\tau)=\langle\mathcal O_i(\tau)\mathcal O_j^\dagger(0)\rangle_c.
$$

Diagonalizing this matrix in a generalized eigenvalue problem isolates states more effectively than a single operator. Conceptually, though, the principle is still just Euclidean filtering.

## Spectral representation

In a relativistic QFT, the two-point function of a scalar operator has a spectral representation of the schematic form

$$
G_E(p_E^2)
=\int_0^\infty d\mu^2\,
\frac{\rho_{\mathcal O}(\mu^2)}{p_E^2+\mu^2},
$$

where $\rho_{\mathcal O}(\mu^2)\ge0$ under standard positivity assumptions for a Hermitian operator in a unitary theory.

A gap in the $\mathcal O$ channel means

$$
\rho_{\mathcal O}(\mu^2)=0
\qquad
0<\mu<m_{\mathcal O}.
$$

A stable particle produces a delta-function contribution,

$$
\rho_{\mathcal O}(\mu^2)\supset Z\delta(\mu^2-m^2),
$$

while multiparticle states produce continua beginning at thresholds. The Euclidean long-distance behavior is governed by the lowest point in the support of $\rho_{\mathcal O}$.

This is why the mass gap is visible both in momentum space and in position space:

$$
\text{spectral threshold }m_*
\quad\Longleftrightarrow\quad
G_E(r)\sim e^{-m_*r}\times(\text{power}).
$$

Analytic continuation from Euclidean data to a detailed real-time spectral density is difficult and often ill-conditioned. Extracting the lowest gap is usually easier than reconstructing the whole spectrum, but it still requires careful control of excited-state contamination and finite-size effects.

## Spatial correlation length versus energy gap

At zero temperature in a Lorentz-invariant theory, a mass gap also controls spatial decay:

$$
G_c(r)\sim e^{-mr},
\qquad
\xi=\frac{1}{m}.
$$

In a quantum many-body system with dynamical exponent $z$, the relation becomes a scaling statement near criticality:

$$
\Delta\sim \xi^{-z}.
$$

For relativistic QFT, $z=1$. For nonrelativistic quantum critical points, finite-density systems, and condensed-matter field theories, $z$ may differ from one.

At finite temperature, spatial screening lengths and real-time pole masses need not agree. A Euclidean spatial correlator may define a screening mass,

$$
G(\mathbf r)\sim e^{-m_{\text{scr}}|\mathbf r|},
$$

while the real-time spectral function has transport peaks, quasiparticle widths, or branch cuts. This is one reason thermal nonperturbative QFT requires separate diagnostic tools.

## Finite-volume diagnostics

Finite volume is both a regulator and a source of possible misidentification. In a finite box, the spectrum is usually discrete. A nonzero finite-volume gap does not by itself prove an infinite-volume mass gap.

The limiting behavior is diagnostic:

| Infinite-volume behavior | Typical finite-size pattern |
|---|---|
| Gapped phase | Energy gaps approach nonzero limits, with corrections often $\sim e^{-mL}$. |
| Critical or conformal phase | Gaps scale as powers, often $\Delta E\sim L^{-z}$. |
| Broken discrete symmetry | Vacuum splitting may vanish as $e^{-cL^{d-1}}$, while excitations remain gapped. |
| Broken continuous symmetry | Anderson tower and Goldstone modes create gaps that vanish with $L$. |
| Topological order | Ground-state splittings may vanish exponentially, while local excitations remain gapped. |

A common mistake is confusing vacuum-sector splittings with particle gaps. In a broken discrete symmetry phase, the symmetric and antisymmetric finite-volume combinations of two vacua can be split by an exponentially tiny amount. That does not mean the infinite-volume theory has a massless particle. It means finite volume is tunneling between vacua that become superselected at infinite volume.

## Gauge theories and the mass gap

Gauge theory makes the phrase “mass gap” sharper and subtler at the same time.

In pure nonabelian Yang–Mills theory, the expected physical spectrum consists of gauge-invariant massive glueballs. A mass gap means there are no physical excitations with arbitrarily small mass above the vacuum. In lattice calculations, one studies correlators of gauge-invariant operators such as

$$
\mathcal O(x)=\operatorname{tr}F_{\mu\nu}(x)F^{\mu\nu}(x),
$$

or improved lattice versions built from Wilson loops, and extracts glueball masses from Euclidean decay.

But confinement and mass gap are distinct statements.

| Statement | What it says |
|---|---|
| Mass gap | Physical excitations above the vacuum have positive minimum mass. |
| Confinement | Certain probe charges are not isolated asymptotic states, often diagnosed by Wilson loops, string tension, or one-form symmetry realization. |

A pure Yang–Mills theory is expected to have both. A massive gauge-Higgs theory may be gapped without having confinement in the same sense. QED in four dimensions has charged matter and a massless photon, so it is not gapped. A topological field theory can have no local propagating particles but still have nontrivial global Hilbert-space structure.

The rigorous continuum construction of four-dimensional pure Yang–Mills theory with a positive mass gap remains a major open mathematical problem. The physics evidence from confinement, lattice gauge theory, and phenomenology is strong; the theorem-level construction is a different standard of knowledge.

## Stating a mass-gap claim

A mass gap claim should specify four things:

| Ingredient | Question |
|---|---|
| Hilbert space | Which physical states and superselection sectors are included? |
| Limit | Is the statement finite-volume, infinite-volume, continuum, zero-temperature, or thermodynamic? |
| Channel | Is the gap absolute, or only in the operator channel being measured? |
| Diagnostic | Is the evidence from Euclidean correlators, transfer matrices, spectral density, Hamiltonian truncation, lattice spectroscopy, or analytic control? |

With those ingredients, “the theory is gapped” becomes precise. Without them, it is usually under-specified.

## Common pitfalls

**Confusing finite-volume gaps with infinite-volume gaps.** A finite box discretizes the spectrum. The question is how the low-lying energies behave as $L\to\infty$.

**Forgetting vacuum subtraction.** If $\langle\mathcal O\rangle\neq0$, the unsubtracted correlator contains a constant vacuum contribution. Use the connected correlator to extract excited-state gaps.

**Assuming one operator sees the whole spectrum.** A poorly chosen operator can miss the lightest state. Symmetry, gauge invariance, spin, parity, charge, and topology all restrict overlaps.

**Equating a mass gap with confinement.** They often appear together in pure nonabelian gauge theory, but they are logically distinct.

**Mistaking Goldstone phases for gapped phases.** Continuous symmetry breaking usually produces gapless modes under the usual assumptions, even when some fields are massive.

**Using gauge-variant fields as physical probes.** In gauge theory, the physical spectrum is probed by gauge-invariant operators or properly defined charged sectors, not by an elementary gauge-variant field alone.

**Overinterpreting screening masses.** Finite-temperature spatial screening lengths are useful, but they are not automatically real-time particle masses.

**Ignoring excited-state contamination.** A correlator at moderate Euclidean time may not yet be dominated by the lightest state.

## Relations to other pages

[Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/) explains the real-space version of the same diagnostic. [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains why the order of limits matters. [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) explains why Euclidean correlators can reconstruct a unitary Lorentzian Hilbert space when the required positivity conditions hold.

This page prepares for later diagnostics based on spectral density, Wilson loops, confinement, lattice field theory, Hamiltonian truncation, and large-$N$ gap equations. The confinement chapter will use the mass gap as one ingredient, but not as a synonym for confinement.

## Research status

The spectral interpretation of Euclidean correlators, the transfer-matrix extraction of gaps, and the channel dependence of operator overlaps are established. These are standard tools in lattice QFT, statistical mechanics, constructive approaches, and Hamiltonian methods.

The frontier lies in hard systems: strongly coupled four-dimensional gauge theories, real-time spectral reconstruction, theories with sign problems, finite-density QFT, conformal-window questions, topological phases, and rigorous continuum construction. Four-dimensional pure Yang–Mills mass gap is the famous example where physics evidence is compelling but proof at the level of mathematical construction remains open.

## Exercises

### Exercise 1: Effective mass plateau

Assume a Euclidean correlator has a single exponential form

$$
C(\tau)=Ae^{-\Delta\tau}
$$

on a lattice with time spacing $a_t$. Show that

$$
m_{\mathrm{eff}}(\tau)=\frac{1}{a_t}\log\frac{C(\tau)}{C(\tau+a_t)}
$$

is independent of $\tau$ and equal to $\Delta$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the single exponential:

$$
\frac{C(\tau)}{C(\tau+a_t)}
=\frac{Ae^{-\Delta\tau}}{Ae^{-\Delta(\tau+a_t)}}
=e^{\Delta a_t}.
$$

Therefore

$$
m_{\mathrm{eff}}(\tau)
=\frac{1}{a_t}\log e^{\Delta a_t}
=\Delta.
$$

</details>

### Exercise 2: Excited-state contamination

Let

$$
C(\tau)=A_1e^{-\Delta_1\tau}+A_2e^{-\Delta_2\tau},
\qquad
0<\Delta_1<\Delta_2.
$$

Show that the correction to the leading exponential is controlled by $e^{-(\Delta_2-\Delta_1)\tau}$.

<details>
<summary><strong>Solution</strong></summary>

Factor out the lightest exponential:

$$
C(\tau)=A_1e^{-\Delta_1\tau}
\left[1+\frac{A_2}{A_1}e^{-(\Delta_2-\Delta_1)\tau}\right].
$$

The bracket approaches one at large $\tau$, and the excited-state contamination is suppressed by

$$
e^{-(\Delta_2-\Delta_1)\tau}.
$$

Thus the larger the separation between the first two contributing levels, the faster the plateau appears.

</details>

### Exercise 3: Gap versus correlation length at a quantum critical point

Assume a quantum critical point has spatial correlation length $\xi\sim |g-g_c|^{-\nu}$ and dynamical exponent $z$. Use scaling to find how the gap closes near the transition.

<details>
<summary><strong>Solution</strong></summary>

The correlation time scales as

$$
\xi_\tau\sim \xi^z.
$$

The gap is the inverse correlation time,

$$
\Delta\sim \xi_\tau^{-1}\sim \xi^{-z}.
$$

Since $\xi\sim |g-g_c|^{-\nu}$,

$$
\Delta\sim |g-g_c|^{z\nu}.
$$

For a relativistic critical point, $z=1$, so $\Delta\sim |g-g_c|^\nu$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, for the Lehmann–Källén representation, exact propagators, poles, thresholds, and physical mass extraction.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for spectral decomposition, unitarity, locality, and modern QFT diagnostics.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for transfer matrices, correlation lengths, and the relation between Euclidean mass and the inverse correlation length.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field theory, correlation functions, criticality, and mass scales.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for mass gaps, correlation lengths, topological phases, and quantum critical examples.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for nonperturbative gauge-theory phases, solitons, confinement, and lower-dimensional mass-gap examples.
- Clay Mathematics Institute, “Yang–Mills and Mass Gap,” for the mathematical status of the four-dimensional Yang–Mills existence and mass-gap problem.

## Version history

- **2026-06-26:** Initial polished page.
