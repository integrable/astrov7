---
title: "Instanton Measure"
description: "Explains the collective-coordinate measure, determinant ratio, size integration, and renormalization factors that turn an instanton saddle into a semiclassical contribution."
sidebar:
  label: "Instanton Measure"
  order: 9
level: Advanced
status: "Polished draft"
source: "Coleman; Srednicki ch. 93; Shifman ch. 5; Mariño ch. 4; ’t Hooft."
topics:
  - instanton measure
  - instanton calculus
  - collective coordinates
  - fluctuation determinants
  - size modulus
  - Yang–Mills instantons
  - renormalization
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - semiclassical-methods
  - collective-coordinates
  - yang-mills
researchStatus:
  established:
    - "The one-instanton measure is the semiclassical weight obtained by replacing bosonic zero modes with collective-coordinate integrals and integrating nonzero fluctuations at one loop."
  active:
    - "In strongly coupled gauge theories, the large-size region, interactions among instantons, and relation to renormalons and dense ensembles are not controlled by the one-instanton measure alone."
---

## Summary

The instanton measure is the answer to a deceptively small question: after finding an instanton solution, what exactly do we integrate over? The saddle gives the leading exponential $e^{-S_I}$, but the path integral also contains ordinary integrals over zero modes, determinant ratios from nonzero fluctuations, normalization factors, renormalization-scale dependence, and possible fermion zero-mode insertions.

For a one-instanton sector, the schematic rule is

$$
\langle\mathcal O\rangle_{I}
\sim
\int_{\mathcal M_1}d\mu_I(m)\,\mathcal O[\Phi_I(m)]\,e^{-S_I},
$$

where $m$ denotes the collective coordinates of the instanton and $\mathcal M_1$ is the one-instanton moduli space. For a Yang–Mills instanton, these coordinates include the center $x_0$, the size $\rho$, and the gauge orientation $U$.

In pure $SU(N)$ Yang–Mills theory, a common one-loop form of the one-instanton measure is

$$
d\mu_I
=
C_N\,d^4x_0\,\frac{d\rho}{\rho^5}\,d\Omega\,
\left(\frac{8\pi^2}{g^2(\mu)}\right)^{2N}
(\mu\rho)^{b_0}
\exp\left[-\frac{8\pi^2}{g^2(\mu)}\right],
$$

where $b_0=11N/3$ for pure Yang–Mills, $d\Omega$ is the normalized measure over gauge orientations, and $C_N$ is a convention-dependent numerical constant. With $N_f$ Dirac fermions in the fundamental representation, the one-loop coefficient becomes

$$
b_0=\frac{11}{3}N-\frac{2}{3}N_f,
$$

and massless fermion zero modes must be saturated by external fields or mass insertions.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A schematic decomposition of the one-instanton measure into zero-mode, nonzero-mode, renormalization, and fermion factors.](/figures/nonperturbative-qft/instanton-measure-anatomy.svg)

<figcaption>

The one-instanton measure has several logically distinct pieces: bosonic zero modes become collective-coordinate integrals, nonzero modes give determinant ratios, renormalization produces the running-coupling and $(\mu\rho)^{b_0}$ factors, and fermion zero modes require insertions or mass factors.

</figcaption>
</figure>

This page is a physics-facing preview of instanton calculus. It explains what the measure means and how to use it; it does not attempt a full ADHM construction of multi-instanton moduli spaces or a complete derivation of every numerical normalization constant.

## Prerequisites

You should know [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/), [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/), and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/).

You should also know the general machinery of [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), and [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/).

We work in Euclidean signature and use the instanton-number convention of [Conventions and Notation](/nonperturbative-qft/conventions/):

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu},
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}
$$

for the fundamental representation of $SU(N)$.

## Core idea

A saddle point with no zero modes gives the familiar Gaussian approximation

$$
Z_{\rm saddle}
\sim
\exp[-S_E[\Phi_{\rm cl}]]\,
\left(\det\Delta_{\rm cl}\right)^{-1/2},
$$

with the right powers and signs adjusted for bosons, ghosts, and fermions. Instantons are more interesting because they come in continuous families. If $\Phi_I(x;m)$ is a family of instantons, then changing $m$ does not change the classical action. The quadratic fluctuation operator therefore has zero modes.

The correct procedure is not to include those zero eigenvalues in the determinant. Instead, one changes variables from zero-mode fluctuation coefficients to collective coordinates:

$$
\prod_{a\in\text{zero modes}} dc_a
\quad\longrightarrow\quad
J(m)\,\prod_i dm^i.
$$

The Jacobian $J(m)$ is part of the measure. The nonzero modes give determinant ratios. Gauge theories also require gauge fixing and ghost determinants. Fermions add a separate Grassmann story: bosonic zero modes become ordinary integrals, while fermion zero modes become Grassmann integrations that must be saturated.

This is why the phrase “the instanton contribution is $e^{-8\pi^2/g^2}$” is incomplete. That is only the action. The actual one-instanton contribution is an integral over the instanton’s position, size, orientation, and zero-mode data, weighted by a fluctuation determinant and by whatever operator insertions are needed.

## Setup and conventions

Consider pure Euclidean Yang–Mills theory with gauge group $SU(N)$,

$$
S_E[A]
=
\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}.
$$

A charge-one self-dual instanton has

$$
Q=1,
\qquad
S_I=\frac{8\pi^2}{g^2}.
$$

For $SU(2)$, the BPST instanton has eight bosonic collective coordinates:

| Coordinate type | Number | Meaning |
|---|---:|---|
| translations | $4$ | the Euclidean center $x_0^\mu$ |
| scale | $1$ | the size $\rho$ |
| gauge orientation | $3$ | global $SU(2)$ orientation modulo redundancies |

For $SU(N)$, the instanton still lives in an embedded $SU(2)$ subgroup, but its embedding can be rotated inside $SU(N)$. The number of bosonic collective coordinates becomes

$$
4N.
$$

Equivalently, one has $4$ translations, $1$ scale, and $4N-5$ orientation parameters. The orientation space can be described, up to finite identifications and normalization conventions, as the quotient

$$
\frac{SU(N)}{SU(N-2)\times U(1)}.
$$

The exact normalization of $d\Omega$ depends on how one normalizes the group volume and the generators. The physically robust ingredients are the existence of the orientation integral, the $\rho$ dependence, the action factor, and the way renormalization turns the bare coupling into a running coupling.

## Anatomy of the one-instanton density

It is often useful to write

$$
d\mu_I=d^4x_0\,d\rho\,d\Omega\,D(\rho),
$$

where $D(\rho)$ is the instanton size density. At one loop in pure $SU(N)$ Yang–Mills theory,

$$
D(\rho)
=
C_N\,\rho^{-5}
\left(\frac{8\pi^2}{g^2(\mu)}\right)^{2N}
(\mu\rho)^{b_0}
\exp\left[-\frac{8\pi^2}{g^2(\mu)}\right]
\left[1+O(g^2)\right].
$$

Each factor has a job.

| Factor | Origin | Meaning |
|---|---|---|
| $d^4x_0$ | translation zero modes | the instanton can occur anywhere in Euclidean spacetime |
| $d\rho$ | scale zero mode | classical Yang–Mills instantons have arbitrary size |
| $d\Omega$ | gauge-orientation zero modes | the instanton can be embedded in different color directions |
| $\rho^{-5}$ | dimensional and zero-mode Jacobian factors | makes $D(\rho)d\rho d^4x_0$ dimensionless before RG factors |
| $e^{-8\pi^2/g^2}$ | classical action | the leading nonperturbative suppression |
| $(8\pi^2/g^2)^{2N}$ | zero-mode normalization | one factor roughly from each bosonic collective coordinate pair |
| $(\mu\rho)^{b_0}$ | one-loop determinant and renormalization | cancels the explicit scale dependence of $g(\mu)$ at this order |

The formula is not meant to be memorized as decoration. It tells you what scales dominate the instanton integral. Observables often contain integrals of the form

$$
\int_0^\infty d\rho\,D(\rho)\,\mathcal F(\rho),
$$

where $\mathcal F(\rho)$ comes from the operator insertion, fermion zero modes, external momenta, masses, finite volume, temperature, or Higgs expectation values.

## Running coupling and the size modulus

The scale modulus is the troublemaker and the teacher. Classically, Yang–Mills theory in four dimensions is scale invariant, so instantons of all sizes have the same action. Quantum mechanically, the coupling runs. The measure knows this.

At one loop,

$$
\frac{8\pi^2}{g^2(\mu)}=b_0\log\frac{\mu}{\Lambda}+\cdots.
$$

Therefore

$$
(\mu\rho)^{b_0}\exp\left[-\frac{8\pi^2}{g^2(\mu)}\right]
=
(\rho\Lambda)^{b_0}
$$

at leading-log order. Equivalently, one often writes the instanton density as if the coupling were evaluated at the inverse instanton size,

$$
D(\rho)
\sim
C_N\,\rho^{-5}
\left(\frac{8\pi^2}{g^2(1/\rho)}\right)^{2N}
\exp\left[-\frac{8\pi^2}{g^2(1/\rho)}\right].
$$

This is a useful mnemonic, not a license to forget the scheme dependence of the prefactor.

For an asymptotically free theory, small instantons probe high momenta, where $g(1/\rho)$ is small. The semiclassical calculation can be controlled there. Large instantons probe the infrared. In pure Yang–Mills theory the one-loop density grows toward large $\rho$, and the integral is not controlled by weak-coupling instanton calculus. That is the famous infrared problem of instanton calculus in QCD-like theories.

A Higgs expectation value, finite temperature, compactification, large external momentum, or other physical scale can suppress large instantons and make the measure useful in a controlled way. Without such a cutoff, the one-instanton measure should not be mistaken for a complete calculation of strongly coupled long-distance physics.

## Fermions and zero-mode saturation

Fermions modify the measure in two different ways.

First, nonzero fermion modes contribute determinant factors. These help change $b_0$ from the pure Yang–Mills value to the matter-corrected value. For $N_f$ fundamental Dirac fermions,

$$
b_0=\frac{11}{3}N-\frac{2}{3}N_f.
$$

Second, zero modes impose selection rules. In a charge-one instanton background, each massless fundamental Dirac flavor supplies zero modes. If no operator insertion absorbs them, the massless fermion determinant vanishes. If the fermions have small masses, mass terms can soak up pairs of zero modes, and the measure gets factors schematically of the form

$$
\prod_{f=1}^{N_f}(m_f\rho).
$$

If instead the correlation function contains external fermion fields, the zero modes are represented by explicit wavefunctions. This is how the instanton measure becomes the coefficient of the ’t Hooft vertex rather than merely a contribution to the vacuum energy.

Thus a more honest schematic expression is

$$
d\mu_I\,\mathcal O
\quad\longrightarrow\quad
 d^4x_0\,d\rho\,d\Omega\,D(\rho)
\times
\left(\text{zero-mode wavefunctions, masses, or sources}\right).
$$

The instanton measure is therefore not a single number. It is a rule for integrating over the instanton’s collective coordinates while respecting the zero-mode structure of the theory.

## How the measure is used

A typical one-instanton calculation has the following shape.

1. Choose the instanton background $\Phi_I(m)$.
2. Identify bosonic zero modes and replace them by collective-coordinate integrals.
3. Gauge fix and divide by gauge redundancies.
4. Compute determinant ratios for nonzero fluctuations, including ghosts and matter fields.
5. Treat fermion zero modes by insertions or mass terms.
6. Integrate over $x_0$, $\rho$, and orientation.
7. Check whether the $\rho$ integral is dominated in a controlled regime.

For a local operator $\mathcal O(x)$ in a translation-invariant vacuum, the $x_0$ integral often has a simple interpretation: it integrates over where the instanton event occurred relative to the operator insertion. In a partition function, it produces the spacetime volume $V_4$. In a dilute gas, that volume factor is what later exponentiates.

The $\rho$ integral is more delicate. It decides whether the calculation is ultraviolet dominated, infrared dominated, or controlled by a physical external scale. This is often the most important diagnostic in the entire computation.

## Common pitfalls

**Keeping zero eigenvalues inside the determinant.** Zero modes must be removed from the determinant and replaced by collective-coordinate integrals. A prime on a determinant, as in $\det'\Delta$, is not decorative; it changes the calculation.

**Quoting only $e^{-8\pi^2/g^2}$.** The action factor is only the leading exponential. The position integral, size integral, orientation integral, determinant ratio, and zero-mode insertions decide the actual observable.

**Treating the $\rho$ integral as automatically convergent.** In four-dimensional QCD-like theories, large instantons are not controlled by weak-coupling instanton calculus. A large-$\rho$ divergence is not a small technical problem; it says the approximation has left its domain of validity.

**Forgetting fermion zero modes.** In theories with massless fermions, an instanton contribution to the vacuum functional may vanish while a fermionic correlation function survives. Counting zero modes comes before estimating sizes.

**Overinterpreting the numerical constant.** Constants such as $C_N$ depend on normalization conventions, renormalization scheme, and group-volume choices. Universal statements are usually about scaling, selection rules, and controlled dominance, not the isolated value of $C_N$ copied without conventions.

**Confusing one-instanton and multi-instanton moduli spaces.** The one-instanton measure is already subtle. Multi-instanton spaces are not simply a Cartesian product once instantons overlap or interact, even though the dilute limit often begins with such a product approximation.

## Relations to other pages

[Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) and [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) give the general semiclassical technology that the instanton measure specializes.

[Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/) supplies the classical saddle and the $8\pi^2/g^2$ action. [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) fixes the normalization of $Q$. [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) explains why the measure must be supplemented by Grassmann saturation rules.

The next page, [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/), explains what happens when the one-instanton measure is used as the fugacity of a rare gas of instantons and anti-instantons.

## Research status

**Established.** The one-instanton measure in weakly coupled Yang–Mills theory, including collective coordinates and one-loop determinant structure, is standard instanton calculus.

**Controlled in special regimes.** The measure is useful when the instanton size integral is cut off or dominated where $g(1/\rho)$ is small: for example in certain Higgs regimes, high-energy processes, small compactification radii, or supersymmetric settings with additional protection.

**Subtle in QCD-like infrared physics.** In ordinary four-dimensional QCD, large instantons probe strong coupling. The single-instanton measure by itself does not establish confinement, the hadron spectrum, or the full theta dependence of the vacuum.

## Exercises

### Exercise 1: Count one-instanton collective coordinates in SU(N)

For an $SU(N)$ BPST instanton embedded in an $SU(2)$ subgroup, the orientation space has dimension $4N-5$. Show that the total number of bosonic collective coordinates is $4N$.

<details><summary><strong>Solution</strong></summary>

The collective coordinates are:

$$
4\quad\text{translations},
\qquad
1\quad\text{scale},
\qquad
4N-5\quad\text{orientations}.
$$

Adding them gives

$$
4+1+(4N-5)=4N.
$$

For $N=2$, this gives $8$: four translations, one scale, and three gauge orientations.

</details>

### Exercise 2: RG-improved instanton weight

Assume the one-loop running relation

$$
\frac{8\pi^2}{g^2(\mu)}=b_0\log\frac{\mu}{\Lambda}.
$$

Show that

$$
(\mu\rho)^{b_0}\exp\left[-\frac{8\pi^2}{g^2(\mu)}\right]
=
(\rho\Lambda)^{b_0}.
$$

<details><summary><strong>Solution</strong></summary>

Use the running relation in the exponential:

$$
\exp\left[-\frac{8\pi^2}{g^2(\mu)}\right]
=
\exp\left[-b_0\log\frac{\mu}{\Lambda}\right]
=
\left(\frac{\Lambda}{\mu}\right)^{b_0}.
$$

Multiplying by $(\mu\rho)^{b_0}$ gives

$$
(\mu\rho)^{b_0}\left(\frac{\Lambda}{\mu}\right)^{b_0}
=
(\rho\Lambda)^{b_0}.
$$

Thus the explicit $\mu$ dependence cancels at this order.

</details>

### Exercise 3: Why an unsaturated fermion zero mode kills a vacuum amplitude

Let $c$ and $\overline c$ be Grassmann variables for a zero mode, so the action contains no term proportional to $\overline c c$. Show that

$$
\int d\overline c\,dc\,1=0,
\qquad
\int d\overline c\,dc\,\overline c c=1
$$

up to the convention for the order of the Grassmann measure.

<details><summary><strong>Solution</strong></summary>

Grassmann integration is defined by

$$
\int dc\,1=0,
\qquad
\int dc\,c=1.
$$

Therefore an integral with no factor of $c$ vanishes. Similarly an integral with no factor of $\overline c$ vanishes. Hence

$$
\int d\overline c\,dc\,1=0.
$$

If the integrand contains both variables, then the integration is saturated:

$$
\int d\overline c\,dc\,\overline c c=1
$$

for the measure ordering used here. With the opposite ordering one picks up the corresponding sign. The physical statement is independent of this bookkeeping convention: every Grassmann zero-mode variable must appear exactly once for the integral to be nonzero.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on instantons and the uses of instantons.
- M. Srednicki, *Quantum Field Theory*, chapter on instantons and theta vacua.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters on instantons and supersymmetric instanton calculus.
- M. Mariño, *Instantons and Large N*, chapters on Yang–Mills instantons and instanton calculus.
- G. ’t Hooft, “Computation of the Quantum Effects Due to a Four-Dimensional Pseudoparticle,” for the classic one-loop instanton measure.
- C. Bernard, “Gauge Zero Modes, Instanton Determinants, and QCD Calculations,” for technical details of the determinant and zero-mode normalization.

## Version history

- **2026-06-27:** Initial polished page. Added the one-instanton measure anatomy, $SU(N)$ collective-coordinate counting, running-coupling interpretation, fermion zero-mode factors, caveats about the large-size region, and exercises.
