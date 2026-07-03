---
title: "Spontaneous Symmetry Breaking"
description: "Chapter overview for spontaneous symmetry breaking, order parameters, degenerate vacua, Goldstone physics, explicit breaking, low-dimensional caveats, and the Higgs-mechanism preview in the Symmetry, Anomalies, and Topology volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman on secret symmetry, Goldstone bosons, soft pions, and lumps; Srednicki §§30–32; Schwartz Ch. 28; Weinberg Vol. II on symmetries and effective actions; Altland–Simons on broken symmetry and collective phenomena."
topics:
  - spontaneous symmetry breaking
  - order parameters
  - degenerate vacua
  - Goldstone theorem
  - Goldstone modes
  - cosets
  - explicit breaking
  - pseudo-Goldstone bosons
  - Higgs mechanism
canonicalTopics:
  - spontaneous-symmetry-breaking
  - order-parameter
  - degenerate-vacua
  - goldstone-theorem
  - goldstone-mode
  - vacuum-manifold
  - explicit-symmetry-breaking
  - pseudo-goldstone-boson
researchStatus:
  established:
    - "For relativistic QFT with an exact continuous internal symmetry, locality and a nonzero order-parameter commutator imply massless Goldstone excitations, subject to standard assumptions."
    - "Spontaneous symmetry breaking is a property of a state or phase, not literally a failure of the microscopic symmetry of the theory."
  active:
    - "Modern refinements involve generalized symmetries, non-invertible symmetries, phases without local order parameters, symmetry-enriched topological phases, finite-density Goldstone counting, and gauge-invariant diagnostics of Higgs phases."
---

Spontaneous Symmetry Breaking is the chapter in the Symmetry, Anomalies, and Topology volume where an exact symmetry of the theory stops being a symmetry of the chosen state. The Lagrangian, Hamiltonian, path integral, or operator algebra may still have the symmetry; a vacuum or thermal phase may not.

This chapter explains how that can happen without contradiction. The core mechanism is that an infinite quantum system can have several macroscopically distinct phases, each related by a symmetry transformation, while local experiments inside one phase see only the subgroup that preserves it.

The slogan is:

$$
\text{exact symmetry of the theory} \ne \text{symmetry of every state}.
$$

For an internal symmetry $G$, a typical broken phase has a nonzero order parameter whose expectation value is invariant only under a subgroup $H\subset G$. The space of symmetry-related vacua is then locally modeled by $G/H$, and continuous directions in this space produce Goldstone physics.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A roadmap diagram showing exact symmetry data leading to order parameters, degenerate vacua, unbroken subgroup H, and then to discrete broken phases, continuous Goldstone modes, explicit breaking, and the Higgs-mechanism preview.](/figures/symmetry-anomalies-topology/spontaneous-symmetry-breaking-roadmap.svg)

<figcaption>

Spontaneous symmetry breaking is detected by the action of the symmetry on states and observables. A tiny source selects a phase, the infinite-volume limit makes different phases orthogonal, and the remaining symmetry is the stabilizer $H$ of the order parameter. Continuous internal breaking gives Goldstone modes; discrete breaking gives degenerate vacua and domain walls; gauged presentations require extra care.

</figcaption>
</figure>

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), the ordinary symmetry chapter through [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), and the Noether chapter through [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/).

The most useful previous pages are [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/), [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/), and [Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/). Background-field language is helpful but not required; it becomes important when discussing explicit breaking, anomalies, and gauging.

Mathematically, you should be comfortable with group actions, stabilizer subgroups, correlation functions, the idea of an infinite-volume limit, and the basic path-integral meaning of a source coupled to an operator.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) | The diagnostic language: expectation values, sources, long-distance correlators, gauge-invariant caveats, and nonlocal order parameters. |
| 2 | Degenerate Vacua | Why symmetry-related phases become distinct only after the thermodynamic or infinite-volume limit. |
| 3 | Goldstone Theorem | The operator and spectral argument that continuous internal breaking produces massless excitations. |
| 4 | Goldstone Modes | How the massless fields transform, couple to currents, and dominate long-distance physics. |
| 5 | Coset Construction: Preview | The geometry of $G/H$ and the first form of the nonlinear symmetry action. |
| 6 | Nonlinear Sigma Models: Preview | The universal effective field theory of slowly varying order-parameter directions. |
| 7 | Explicit versus Spontaneous Breaking | How small symmetry-violating terms differ from a symmetric theory choosing a nonsymmetric state. |
| 8 | Pseudo-Goldstone Bosons | Why approximate symmetries give light, not massless, modes. |
| 9 | Coleman–Mermin–Wagner Theorem: Preview | Why low-dimensional fluctuations can forbid continuous symmetry breaking under standard assumptions. |
| 10 | Higgs Mechanism: Preview | How the Goldstone story changes when the symmetry is gauged or when the broken symmetry is only a redundancy of a description. |

For a minimal first pass, read steps 1–4. Then read Explicit versus Spontaneous Breaking before studying anomalies or low-energy effective theories. Return to the coset and nonlinear-sigma-model previews when you need the effective field theory of broken phases.

## Landmarks

**Spontaneous breaking is a state property.** A symmetry $G$ of the theory is spontaneously broken in a state $|\Omega\rangle$ if some symmetry transformation does not leave the state invariant in the physical sense. Operationally, one detects this through observables. A local operator $\mathcal O_i$ may transform nontrivially,

$$
\delta_a\mathcal O_i=i[Q_a,\mathcal O_i],
$$

and have an expectation value whose variation is nonzero:

$$
\langle\delta_a\mathcal O_i\rangle\ne 0.
$$

The theory still has the symmetry; the selected phase does not.

**The stabilizer is the unbroken symmetry.** If an order parameter takes a value $v$, the unbroken subgroup is

$$
H=\{g\in G\mid g\cdot v=v\}.
$$

The broken directions are the directions in $G/H$. This sentence is the seed of the coset construction.

**Infinite volume matters.** In a finite system with a unique symmetric ground state, the exact expectation value of a symmetry-odd order parameter often vanishes. A broken phase is obtained by adding a small symmetry-breaking source, taking the infinite-volume limit, and only then removing the source:

$$
\langle\mathcal O\rangle_{\text{broken}}
=
\lim_{h\to0}\lim_{V\to\infty}\langle\mathcal O\rangle_{h,V}.
$$

Reversing the two limits usually gives the symmetric answer.

**Discrete breaking gives degeneracy but no Goldstone theorem.** If a discrete symmetry such as $\mathbb Z_2$ is broken, there can be two or more phases related by the symmetry. There is no continuous flat direction, hence no Goldstone boson forced by symmetry. Domain walls may appear instead.

**Continuous internal breaking gives Goldstone modes.** In relativistic QFT, if an exact continuous internal symmetry is spontaneously broken and the usual assumptions hold, then the spectrum contains massless excitations. More precisely, a nonzero vacuum matrix element of a current commutator forces spectral weight at $p^2=0$.

**The number of Goldstone modes can be subtle outside relativistic vacua.** In Lorentz-invariant relativistic QFT with internal symmetry breaking, the common result is one Goldstone boson per broken generator. At finite density or in nonrelativistic systems, two broken generators can pair into one type-B Goldstone mode with quadratic dispersion. For spacetime symmetry breaking, inverse-Higgs constraints and redundancy among generators can reduce the number of independent gapless fields.

**Explicit breaking is not spontaneous breaking.** If the action contains a term that is not invariant under $G$, then $G$ is not a symmetry of the theory. If that term is small, the theory may have an approximate symmetry and pseudo-Goldstone modes. But an exact Ward identity has been replaced by a partially conserved or explicitly violated one.

**Gauge symmetry is not broken like global symmetry.** A gauge symmetry is a redundancy of description. Local gauge-variant fields are not physical order parameters in an unfixed gauge. The Higgs mechanism is real physics, but the clean diagnostics are gauge-invariant: spectra, screening, global remnant symmetries, line operators, boundary behavior, and response to background fields.

**Anomalies and SSB talk to each other.** A broken phase can match an ’t Hooft anomaly through Goldstone fields, Wess–Zumino terms, edge modes, or topological order. Thus anomaly matching does not require the infrared theory to be symmetric in the same linear way as the ultraviolet theory.

## Common confusions

**“The symmetry of the Lagrangian is broken.”** Usually the Lagrangian is not broken. The state is. Better wording is: the symmetry is exact but spontaneously broken by the vacuum or phase.

**“The finite-volume ground state proves there is no SSB.”** Finite volume often restores the symmetry by tunneling between would-be vacua. SSB is diagnosed after the infinite-volume limit or by long-distance clustering, not by one finite box.

**“Any nonzero expectation value is an order parameter.”** A useful order parameter must distinguish phases or transform in a way that detects symmetry realization. The vacuum energy density is nonzero in many theories; it is not automatically an order parameter.

**“The order parameter must be a fundamental field.”** It may be composite, such as $\bar\psi\psi$ in chiral symmetry breaking; nonlocal, such as a Wilson loop for a higher-form symmetry; or absent if the phase has topological order rather than ordinary Landau order.

**“Goldstone’s theorem is only a Mexican-hat potential calculation.”** The potential picture is useful but not the theorem. The theorem is an operator and spectral statement about currents, charges, locality, and a nonzero commutator with an order parameter.

**“Every broken generator gives one massless scalar in every QFT.”** This is true in the standard relativistic internal-symmetry setting. It is not the general rule for nonrelativistic systems, finite-density systems, spacetime symmetry breaking, systems with long-range interactions, or gauged symmetries.

**“Gauge symmetry breaking means a local gauge-charged field has a physical expectation value.”** In an unfixed gauge, local gauge-variant expectation values are not physical diagnostics. Gauge fixing can be a useful calculation tool, but physical statements must be gauge-invariant.

**“SSB always means long-range order in a local operator.”** Ordinary Landau SSB has such a description. Generalized symmetry breaking, topological order, deconfinement, and fracton-like systems may require line, surface, or more elaborate diagnostics.

## Boundaries

This chapter teaches the symmetry-realization side of broken phases. It does not try to replace full treatments of condensed matter, gauge theory, or effective field theory.

| Topic | Treated here | Continued in |
|---|---|---|
| Order parameters | Definitions, source limits, examples, caveats | Matter, Statistical Physics, and Quantum Information for many-body applications |
| Degenerate vacua | Symmetry-related phases and superselection | Nonperturbative QFT for tunneling, false vacua, and instantons |
| Goldstone theorem | Operator logic and relativistic internal symmetries | Low-dimensional CFT, EFT, and matter chapters for refinements |
| Cosets | Preview of $G/H$ geometry | Renormalization, RG, and EFT; Supersymmetry/Duality for advanced cosets |
| Explicit breaking | Difference from spontaneous breaking | EFT for spurions, pseudo-Goldstone bosons, and chiral perturbation theory |
| Higgs mechanism | Conceptual warning about gauge redundancy | Gauge Redundancy and BRST; Gauge Theories and the Standard Model |
| Low-dimensional no-go results | Preview and assumptions | CFT and Bootstrap; Matter and Statistical Physics |
| Generalized symmetry breaking | Mentioned as a modern extension | Higher-Form and Generalized Symmetries; Defects and Extended Operators |

## Where to go next

After this chapter, continue to Gauge Redundancy and BRST if you want to understand why the Higgs mechanism is not ordinary breaking of a physical local symmetry. Continue to Anomalies if you want to see how exact classical symmetries can fail quantum mechanically and how broken phases can still match anomaly constraints.

For effective field theory, the most important path is Order Parameters → Goldstone Theorem → Goldstone Modes → Coset Construction Preview → Nonlinear Sigma Models Preview. That path leads directly to chiral Lagrangians, pion physics, superfluids, and modern EFT treatments of symmetry realization.

For condensed matter and statistical physics, read Order Parameters and Degenerate Vacua first, then return later for the Coleman–Mermin–Wagner preview, topological order caveats, and generalized-symmetry extensions.

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Secret Symmetry,” “Soft Pions,” and “Classical Lumps and Their Quantum Descendants.” Classic lectures on spontaneous symmetry breaking, Goldstone bosons, gauge fields, current algebra, and topological excitations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters on spacetime symmetries, internal symmetries, and later broken-symmetry material.
- Mark Srednicki, *Quantum Field Theory*, §§30–32. Standard graduate-level treatment of spontaneous symmetry breaking and continuous symmetries.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 28. Clear treatment of discrete and continuous SSB and the Higgs-mechanism entry point.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II. Effective actions, symmetries, Goldstone bosons, and broken gauge theories.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the chapters on broken symmetry, collective phenomena, and topological field theory.
- C. P. Burgess, *Introduction to Effective Field Theory*, Chs. 4 and 14. Effective-theory view of linear versus nonlinear symmetry realization and Goldstone modes.
- J. Goldstone, A. Salam, and S. Weinberg, “Broken Symmetries,” *Physical Review* **127** (1962) 965–970.
- H. B. Nielsen and S. Chadha, “On How to Count Goldstone Bosons,” *Nuclear Physics B* **105** (1976) 445–453.
- H. Watanabe and H. Murayama, “Unified Description of Nambu–Goldstone Bosons without Lorentz Invariance,” *Physical Review Letters* **108** (2012) 251602.
- S. Coleman, “There are no Goldstone bosons in two dimensions,” *Communications in Mathematical Physics* **31** (1973) 259–264.
- N. D. Mermin and H. Wagner, “Absence of Ferromagnetism or Antiferromagnetism in One- or Two-Dimensional Isotropic Heisenberg Models,” *Physical Review Letters* **17** (1966) 1133–1136.
- S. Elitzur, “Impossibility of Spontaneously Breaking Local Symmetries,” *Physical Review D* **12** (1975) 3978–3982.

## Version history

- 2026-06-17: First polished draft. Introduced the chapter reading path, main landmarks, state-versus-theory distinction, order-of-limits warning, gauge-symmetry caveat, and handoffs to anomalies, BRST, EFT, and generalized symmetries.
