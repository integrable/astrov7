---
title: "Major Effective Field Theories"
description: "Chapter overview for the main effective field theories used across particle physics, nuclear physics, gravity, hydrodynamics, and nonrelativistic systems in the Renormalization, RG, and EFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Burgess 2020; Weinberg Vol. II; Schwartz 2014; Coleman 1985; Manohar EFT lectures; standard reviews on chiral perturbation theory, HQET, NRQED/NRQCD, SCET, SMEFT, gravitational EFT, hydrodynamic EFT, and worldline EFT."
topics:
  - effective field theory examples
  - Fermi theory
  - chiral perturbation theory
  - heavy-quark effective theory
  - nonrelativistic EFT
  - SMEFT
  - gravitational EFT
  - hydrodynamic EFT
canonicalTopics:
  - major-effective-field-theories
  - eft-examples
  - fermi-theory
  - chiral-perturbation-theory
  - smeft
researchStatus:
  established:
    - "The EFTs in this chapter are standard examples of the same scale-separation logic applied to different light degrees of freedom, symmetries, and power countings."
  active:
    - "Several of these EFTs have active frontiers in higher-order matching, resummation, nonperturbative matrix elements, automated bases, finite-density systems, dissipative dynamics, and precision phenomenology."
---

## Summary

Major Effective Field Theories is the chapter in the Renormalization, RG, and EFT volume where the general EFT architecture becomes recognizable physics. Earlier chapters explained locality, power counting, matching, running, decoupling, operator bases, and naturalness. This chapter shows those ideas in the EFTs people actually use.

The theme is not that every EFT looks alike. It is almost the opposite. Fermi theory, chiral perturbation theory, HQET, SCET, SMEFT, gravitational EFT, hydrodynamic EFT, and worldline EFT use different degrees of freedom and different small parameters. What they share is the same disciplined separation of scales:

$$
\text{choose light variables}
\quad\longrightarrow\quad
\text{write all local terms allowed by symmetry}
\quad\longrightarrow\quad
\text{organize by power counting}
\quad\longrightarrow\quad
\text{match, run, and compute}.
$$

Read this chapter when you want examples that are concrete enough to calculate with, but still broad enough to teach the general EFT habit of mind.

## Prerequisites

You should know the [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) chapter, especially [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/).

You should also be comfortable with [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/), especially the distinction between Wilson coefficients and matrix elements. For chiral and gauge examples, familiarity with spontaneous symmetry breaking and gauge theory is useful, but the pages flag the extra ingredients when they first appear.

## Reading path

Read these pages in order on a first pass if your goal is to learn the EFT pattern rather than one specialized application.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Fermi Theory](/renormalization-rg-eft/major-efts/fermi-theory/) | The cleanest historical and conceptual example: a heavy mediator becomes a local four-fermion interaction. |
| 2 | [Chiral Perturbation Theory](/renormalization-rg-eft/major-efts/chiral-perturbation-theory/) | EFT with Goldstone bosons, nonlinear symmetry realization, and derivative power counting. |
| 3 | [Nonlinear Sigma Models](/renormalization-rg-eft/major-efts/nonlinear-sigma-models/) | The geometric language behind Goldstone fields, target spaces, and derivative interactions. |
| 4 | [Heavy-Quark Effective Theory](/renormalization-rg-eft/major-efts/heavy-quark-effective-theory/) | EFT organized by a heavy mass, velocity labels, heavy-quark symmetry, and $1/m_Q$ corrections. |
| 5 | [Nonrelativistic QED](/renormalization-rg-eft/major-efts/nonrelativistic-qed/) | EFT for slowly moving charged particles, multipole expansions, spin interactions, and bound-state scales. |
| 6 | [Nonrelativistic QCD](/renormalization-rg-eft/major-efts/nonrelativistic-qcd/) | Heavy quarkonium and nonrelativistic colored particles, with several dynamical scales. |
| 7 | [Soft-Collinear Effective Theory](/renormalization-rg-eft/major-efts/soft-collinear-effective-theory/) | EFT for energetic particles, jets, soft/collinear modes, factorization, and resummation. |
| 8 | [Standard Model Effective Field Theory](/renormalization-rg-eft/major-efts/standard-model-effective-field-theory/) | The Standard Model plus higher-dimension operators as a systematic language for heavy new physics. |
| 9 | [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/) | General relativity as a low-energy EFT with curvature expansions and quantum corrections. |
| 10 | [Hydrodynamic Effective Field Theory](/renormalization-rg-eft/major-efts/hydrodynamic-effective-field-theory/) | EFT for long-wavelength conserved densities, dissipation, noise, and symmetry constraints. |
| 11 | [Worldline Effective Field Theory](/renormalization-rg-eft/major-efts/worldline-effective-field-theory/) | EFT for compact objects, multipoles, radiation, and gravitational two-body dynamics. |

After this path, you should be able to identify the light fields, symmetries, small parameter, operator basis, matching data, and breakdown scale for a new EFT.

## Landmarks

| Landmark | Meaning | Typical EFT |
|---|---|---|
| $G_F$ | Dimension $-2$ coefficient of charged-current weak interactions below the $W$ scale. | Fermi theory. |
| $f_\pi$ | Goldstone decay constant setting the normalization and expansion scale of pion interactions. | Chiral perturbation theory. |
| $U(x)\in G/H$ | Nonlinear Goldstone field valued in a coset manifold. | Chiral EFT, nonlinear sigma models. |
| $v^\mu$ | Heavy-particle velocity label separating a large mass from residual momentum. | HQET. |
| $p\sim mv$ and $E\sim mv^2$ | Nonrelativistic momentum and kinetic-energy scaling. | NRQED, NRQCD. |
| Soft and collinear modes | Distinct low-energy modes with different momentum scalings. | SCET. |
| $C_i/\Lambda^{d_i-4}$ | Wilson coefficient and heavy-scale suppression of higher-dimension operators. | SMEFT and many EFTs. |
| Curvature expansion | Local expansion in $R$, $R_{\mu\nu}$, $R_{\mu\nu\rho\sigma}$, and derivatives. | Gravitational EFT. |
| Conserved densities | Variables fixed by conservation laws rather than microscopic quasiparticles. | Hydrodynamic EFT. |
| Multipole moments | Worldline coefficients encoding finite-size response. | Worldline EFT. |

The point of this chapter is not to memorize a zoo. It is to learn how the same logic mutates when the small parameter changes.

## Common confusions

**There is no universal EFT power counting.** Chiral perturbation theory counts derivatives and quark masses. HQET counts powers of $1/m_Q$. NRQED and NRQCD count nonrelativistic velocity. SCET counts soft and collinear momentum components. SMEFT usually counts operator dimension. Hydrodynamics counts gradients.

**An EFT is not specified by a Lagrangian alone.** You must also state its degrees of freedom, symmetries, power counting, matching conditions, scheme, truncation order, and regime of validity.

**A famous EFT is not automatically the right EFT.** The correct low-energy description depends on the process. For example, heavy-quark physics, quarkonium, jets, hadronic matrix elements, and weak decays can require different EFTs even when QCD is present in all of them.

**The breakdown scale is not always the first heavy mass.** Strong coupling, symmetry restoration, multiparticle thresholds, finite density, collective modes, or nonperturbative physics can set a lower practical breakdown scale.

**Wilson coefficients are not measured in isolation.** Data constrain combinations of coefficients and matrix elements. In strongly coupled EFTs, the matrix elements may require lattice QCD, dispersion theory, symmetry arguments, or phenomenological input.

**Nonrenormalizable does not mean nonpredictive.** The entire chapter is a gallery of useful nonrenormalizable EFTs. Predictivity comes from truncation by a small parameter.

## Boundaries

This chapter does:

- introduce the major EFTs as reusable examples of scale separation;
- identify each EFT's light degrees of freedom, symmetries, power counting, matching logic, and common observables;
- show how the same EFT principles appear in particle physics, nuclear physics, gravity, hydrodynamics, and many-body settings;
- prepare readers to recognize which EFT is appropriate for a calculation.

This chapter does not try to do:

- provide exhaustive phenomenology of weak decays, QCD, collider physics, gravitational waves, nuclear physics, or hydrodynamics;
- replace specialized volumes on gauge theory, the Standard Model, nonperturbative QFT, or matter physics;
- list every operator basis in SMEFT, chiral EFT, SCET, or gravitational EFT;
- teach all loop technology, which belongs in Perturbative QFT and Scattering;
- make all EFTs look artificially identical.

The boundary is simple: this chapter teaches representative EFTs as **scale-separation templates**. Deeper applications belong in their dedicated physics volumes.

## Where to go next

After this chapter, readers interested in methodology should continue to Advanced RG Methods and the Model Calculation Library. Readers interested in weak interactions and Standard Model applications should continue to Gauge Theories and the Standard Model. Readers interested in low-energy QCD should continue to nonperturbative QFT, chiral dynamics, and lattice-oriented material. Readers interested in gravity should continue to Spacetime, Gravity, and Holography.

For a first worked example, start with Fermi theory. It is short enough to compute by hand and deep enough to contain the entire EFT storyline: integrate out a heavy particle, write a local operator, match its coefficient, organize corrections, and state the domain of validity.

## References

- C. P. Burgess, *Introduction to Effective Field Theory*, for the broad EFT viewpoint and examples across particle, nuclear, condensed matter, gravitational, relativistic, and nonrelativistic systems.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, for effective Lagrangians, current algebra, chiral dynamics, and Standard Model applications.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for Fermi theory, nonrenormalizable theories, RG methods, QCD, HQET, SCET, and Standard Model examples.
- Sidney Coleman, *Aspects of Symmetry*, especially the soft-pion and renormalization/symmetry lectures.
- Aneesh V. Manohar, EFT lecture notes and reviews, for practical power counting, matching, and major EFT examples.
- Howard Georgi, *Weak Interactions and Modern Particle Theory*, for Fermi theory, weak currents, and early effective weak-interaction logic.

## Version history

- 2026-06-19: First polished chapter overview for Major Effective Field Theories.
