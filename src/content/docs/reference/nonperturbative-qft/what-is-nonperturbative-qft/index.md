---
title: "What Is Nonperturbative QFT?"
description: "Chapter overview for the conceptual entrance to the Nonperturbative QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman; Polyakov; Mariño; Shifman; Wilson–Kogut; Zinn-Justin."
topics:
  - nonperturbative QFT
  - perturbation theory
  - asymptotic series
  - semiclassical effects
  - strong coupling
  - observables
canonicalTopics:
  - nonperturbative-qft
  - perturbation-theory
  - asymptotic-series
  - semiclassical-methods
  - nonperturbative-observables
researchStatus:
  established:
    - "Nonperturbative QFT studies phenomena and definitions not captured by finite-order expansion around one weakly coupled saddle or Gaussian fixed point."
  active:
    - "How far perturbative data determine nonperturbative sectors is active research, especially in realistic four-dimensional gauge theories."
---

What Is Nonperturbative QFT? is the conceptual entrance to the Nonperturbative QFT volume. It explains what the word “nonperturbative” means before the volume turns to specific methods such as lattice definitions, instantons, large-N limits, Schwinger–Dyson equations, Hamiltonian truncation, and resurgence.

The chapter exists because “nonperturbative” is often used too loosely. It can mean exponentially small effects at weak coupling, strong coupling in a chosen set of variables, multiple saddles, topological sectors, mass gaps, confinement, or simply the need for a definition that is not a formal power series. Those meanings are related, but not identical.

The main problem solved here is orientation. After this chapter, the reader should be able to look at a QFT question and say whether it is perturbative, semiclassical but nonperturbative, strongly coupled, definition-level, observable-level, or a mixture of several of these.

A useful slogan is

$$
\text{perturbation theory is local data; nonperturbative QFT asks for the global object.}
$$

## Prerequisites

You should know the basic path-integral expansion around a Gaussian theory, the idea of a coupling expansion, and the meaning of correlation functions. The sign and normalization choices used throughout this volume are fixed in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

No prior lattice gauge theory, instanton calculus, confinement theory, or resurgence background is assumed. The point of this chapter is to build the vocabulary needed before those subjects appear.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/) | The broad distinction between local perturbative expansions and global nonperturbative physics. |
| 2 | [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/) | The precise meaning of asymptotic expansion, optimal truncation, Borel summation, and exponentially small corrections. |
| 3 | [Semiclassical versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/) | Why instantons can be weakly coupled and nonperturbative, while strongly coupled theories may require different variables or definitions. |
| 4 | [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) | Why Wilson loops, disorder operators, gaps, spectra, and topological sectors often diagnose physics better than elementary fields. |
| 5 | Nonperturbative Scales | How RG running and dimensional transmutation generate scales such as $\Lambda$ that are nonanalytic in a weak coupling. |
| 6 | When Perturbation Theory Fails | A diagnostic page for infrared problems, phase transitions, degenerate vacua, bad variables, and uncontrolled expansions. |
| 7 | Common Confusions | A repair page for the most common graduate-level misunderstandings about this subject. |

After this path, you should be able to tell the difference between a hard perturbative calculation, a controlled semiclassical calculation, and a genuinely nonperturbative definition or observable.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Local expansion around a saddle | Perturbation theory describes fluctuations near a chosen vacuum, classical solution, fixed point, or large-N saddle. | Semiclassical methods, instantons, large-N methods. |
| Asymptotic expansion | A divergent series can still approximate a function for small coupling when truncated before its least term. | Resurgence, transseries, large-order behavior. |
| Beyond all orders | Terms such as $e^{-A/g^2}$ have zero Taylor expansion at $g=0$ but can be physically measurable. | Tunneling, instantons, false-vacuum decay. |
| Multiple saddles and sectors | The full path integral may sum over vacua, topological sectors, flux sectors, or complex saddles. | Theta vacua, instanton gas, line operators. |
| Nonperturbative scale | An RG-invariant scale like $\Lambda=\mu e^{-1/(2b_0g^2)}$ is nonanalytic in the microscopic coupling. | Mass gap, confinement, dimensional transmutation. |
| Correct observable | The phenomenon may be visible in an extended operator, spectrum, or boundary condition rather than in a local elementary field. | Wilson loops, ’t Hooft loops, Polyakov loops, disorder operators. |
| Nonperturbative definition | A formal path integral becomes a theory only after specifying a regulator, Hilbert space, continuum limit, and global data. | Euclidean path integral, lattice regularization, reflection positivity. |

## Common confusions

**Nonperturbative does not mean strongly coupled.** A weakly coupled instanton contribution proportional to $e^{-8\pi^2/g^2}$ is nonperturbative because no finite power series in $g$ sees it. Strong coupling is a statement about the size of a parameter in a chosen description.

**Divergent does not mean useless.** Many perturbative series are asymptotic rather than convergent, but an optimally truncated asymptotic series can be extremely accurate. The danger is treating the infinite formal sum as if convergence were guaranteed.

**A Lagrangian is not always a nonperturbative definition.** A Lagrangian plus a formal measure may define perturbative Feynman rules. A nonperturbative definition also needs a regulator, a space of fields or states, boundary conditions, symmetries, and a continuum limit when appropriate.

**The elementary fields need not be the physical particles.** In a confining theory, the Lagrangian variables may be quarks and gluons while the asymptotic spectrum contains hadrons and glueballs. This is not a high-loop correction to free quarks; it is a reorganization of the physical Hilbert space.

**Not every difficult calculation is nonperturbative.** A five-loop beta function is technically hard but still perturbative. A simple tunneling splitting in a double well is elementary to state but nonperturbative in the expansion around one minimum.

## Boundaries

This chapter does:

- define the main uses of the word “nonperturbative”;
- explain why finite-order perturbation theory can miss real physical effects;
- distinguish asymptotic divergence, exponential corrections, strong coupling, and bad variables;
- prepare the reader for observables such as mass gaps, Wilson loops, theta dependence, and topological sectors.

This chapter does not try to do:

- a full construction of Euclidean or Lorentzian QFT;
- a detailed instanton calculation;
- a proof of confinement or a lattice simulation workflow;
- a complete treatment of resurgence, renormalons, or transseries;
- a survey of every strongly coupled QFT.

Those topics appear later in this volume, or in neighboring volumes on Foundations of QFT, Renormalization and EFT, Gauge Theories, CFT and Bootstrap, Supersymmetry and Duality, and Mathematical and Rigorous QFT.

## Where to go next

For the conceptual route, read [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/) and then [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/).

For the definition route, continue next to [Nonperturbative Definitions of QFT](/nonperturbative-qft/nonperturbative-definitions/) and then [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), which explain how formal path-integral expressions become regulated objects with observables and limits.

For the physics route, continue to [Vacuum Structure and Phases](/nonperturbative-qft/vacuum-structure-phases/), then later to order parameters, instantons, confinement, lattice field theory, and large-N methods.

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, for the classic physical style behind semiclassical effects, instantons, solitons, large N, and symmetry-breaking language.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling expansion, instantons, topology of gauge fields, confinement criteria, loop dynamics, and large N.
- M. Mariño, *Instantons and Large N*, for a pedagogical route through instantons, large-order behavior, Borel summability, Yang–Mills instantons, and large-N methods.

### Deeper references

- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the Wilsonian viewpoint connecting critical phenomena, QFT, and exact RG ideas.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for field integrals, RG, critical phenomena, instantons, large-order behavior, and summation of perturbation theory.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, 2nd ed., for phases of gauge theories, solitons, instantons, false-vacuum decay, anomalies, and confinement in lower-dimensional models.

## Version history

- **2026-06-26:** Added handoff link to Vacuum Structure and Phases.
- **2026-06-25:** Initial polished chapter overview.
