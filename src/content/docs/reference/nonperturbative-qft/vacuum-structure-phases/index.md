---
title: "Vacuum Structure and Phases"
description: "Chapter overview for vacua, phases, expectation values, symmetry realization, superselection sectors, moduli, and metastability in nonperturbative QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman; Srednicki; Schwartz; Weinberg; Zinn-Justin; Shifman; Fradkin; Altland–Simons."
topics:
  - vacuum structure
  - phases of quantum field theory
  - vacuum expectation values
  - spontaneous symmetry breaking
  - superselection sectors
  - effective potential
  - phase diagrams
  - false vacua
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - phases-of-qft
  - spontaneous-symmetry-breaking
  - effective-potential
  - superselection
researchStatus:
  established:
    - "Vacuum structure is part of the nonperturbative definition of a QFT: phases, order parameters, long-distance correlations, and superselection sectors cannot be inferred from a local Lagrangian alone."
  active:
    - "For gauge theories, strongly coupled systems, topological phases, and theories without weakly coupled order parameters, the right phase diagnostics can be subtle and remain an active organizing problem."
---

Vacuum Structure and Phases is the chapter in the Nonperturbative QFT volume where the phrase “the vacuum” stops meaning “the field value that minimizes the classical potential.” A vacuum is a state, or a Euclidean infinite-volume limit defining a state. Its structure is detected by expectation values, correlation functions, spectra, line operators, boundary conditions, and the response to small sources.

The chapter exists because many nonperturbative phenomena are really statements about vacua. Spontaneous symmetry breaking, confinement, screening, topological order, theta vacua, moduli spaces, false-vacuum decay, and phase transitions all depend on which state or sector is being studied. Perturbation theory around one saddle often sees only a local neighborhood of this story.

The practical goal is to teach the reader how to ask phase questions cleanly: which operator is being measured, which state is selected, which limits are taken, which symmetries are preserved, and which long-distance observable distinguishes one phase from another.

A useful slogan is

$$
\text{a phase is not a Lagrangian; it is a long-distance pattern of states and observables.}
$$

## Prerequisites

You should know the basic language of correlation functions, sources, path integrals, and global symmetries. The pages [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) are especially useful.

It also helps to have read [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/). This chapter repeatedly uses the lesson that different phases may require different observables: local operators, extended operators, spectra, susceptibilities, and response functions.

## Reading path

Read the first six pages in order on a first pass. The later pages are more specialized and can be read when needed.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) | How one-point functions depend on the chosen vacuum, sources, limits, renormalization, and symmetries. |
| 2 | [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/) | Why several vacua can represent the same Hamiltonian but different infinite-volume sectors. |
| 3 | [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/) | Why local finite-energy operations may fail to connect states that look like different vacua. |
| 4 | [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) | How a symmetry of the dynamics can fail to be a symmetry of a pure vacuum state. |
| 5 | [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) | The simplest clean setting for tunneling, domain walls, source selection, and finite-volume subtleties. |
| 6 | [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/) | Why the exact effective potential is convex, and why the loop-expanded potential is still useful. |
| 7 | [Moduli Spaces Preview](/nonperturbative-qft/vacuum-structure-phases/moduli-spaces-preview/) | A handoff to families of vacua, flat directions, zero modes, and low-energy sigma models. |
| 8 | [Phase Diagrams](/nonperturbative-qft/vacuum-structure-phases/phase-diagrams/) | How couplings, masses, theta angles, temperature, and density organize the space of phases. |
| 9 | [Quantum Phase Transitions](/nonperturbative-qft/vacuum-structure-phases/quantum-phase-transitions/) | How zero-temperature transitions are detected by gap closing, scaling, and universality. |
| 10 | [False Vacua and Metastability](/nonperturbative-qft/vacuum-structure-phases/false-vacua-and-metastability/) | How long-lived non-ground-state vacua decay by tunneling or bubble nucleation. |

The central page is [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/). It fixes the basic warning label for the whole chapter: a nonzero expectation value is meaningful only after specifying the operator, the state, the regulator, the renormalization convention, and the limiting procedure.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Vacuum state | A lowest-energy state, or a state obtained by a Euclidean large-time projection. | Vacua are quantum states, not points in classical field space. |
| Pure vacuum | An extremal infinite-volume state satisfying cluster decomposition. | Pure phases are the states in which long-distance observables factorize. |
| Mixed symmetric state | A statistical or Euclidean mixture of several pure vacua. | It can preserve the symmetry while failing cluster decomposition. |
| Vacuum expectation value | A one-point function $\langle\Omega|\mathcal O|\Omega\rangle$ in a specified state. | It is the simplest diagnostic of symmetry realization, but only for suitable operators. |
| Source selection | The use of a small source $h\mathcal O$ to select a vacuum before sending $h\to0$. | It resolves the finite-volume paradox that symmetry-breaking expectation values vanish. |
| Order parameter | An observable whose long-distance value distinguishes phases. | Some phases have no local order parameter, so this concept must be used carefully. |
| Superselection sector | A sector not connected to another by local finite-energy operators. | It explains why infinite-volume broken vacua can coexist without quantum mixing. |
| Effective potential | The constant-field part of the quantum effective action. | It links sources, expectation values, metastable saddles, and convexity. |
| Moduli space | A continuous family of physically inequivalent vacua. | It produces zero modes and low-energy dynamics along the vacuum manifold. |
| Phase transition | A nonanalytic change in infinite-volume observables as parameters vary. | Finite regulated systems are analytic; transitions appear only after limits. |

## Common confusions

**A classical minimum is not automatically a quantum vacuum.** Classical minima are saddle points used for semiclassical expansion. Quantum effects can shift, remove, split, or connect them through tunneling, anomalies, finite-volume effects, or strong dynamics.

**A vacuum expectation value is not meaningful without a state.** In a theory with several vacua, $\langle\mathcal O\rangle$ is incomplete notation. One should write $\langle\Omega_\alpha|\mathcal O|\Omega_\alpha\rangle$, or specify the Euclidean boundary condition or source limit selecting $\Omega_\alpha$.

**Spontaneous symmetry breaking is an infinite-volume statement.** At finite volume, a Hamiltonian with an exact global symmetry usually has symmetry eigenstates. Broken vacua appear when the thermodynamic limit is taken before the symmetry-breaking source is removed.

**A gauge-variant VEV is not a physical order parameter.** Gauge fixing can make quantities such as a Higgs-field expectation value convenient, but local gauge redundancy is not a physical symmetry that breaks in the same sense as a global symmetry. Gauge-invariant diagnostics carry the actual physics.

**The exact effective potential is not the same as the tree-level picture.** The exact Legendre-transform effective potential is convex. The familiar nonconvex loop-expanded potential is a local or semiclassical tool, not the full infinite-volume convex object.

**No local order parameter does not mean no phase structure.** Topological phases, confinement, Coulomb phases, Higgs phases, and spin liquids may require extended operators, spectra, response functions, or boundary sensitivity rather than a local VEV.

## Boundaries

This chapter does:

- explain VEVs, order parameters, source limits, and cluster decomposition;
- separate classical minima from quantum vacua;
- treat degenerate vacua and spontaneous symmetry breaking as nonperturbative state structure;
- explain why finite volume hides some infinite-volume physics;
- prepare the reader for solitons, domain walls, tunneling, confinement, and theta vacua;
- give a careful warning about gauge-dependent language in Higgs and gauge phases.

This chapter does not try to do:

- a full Standard Model treatment of the Higgs sector;
- a full proof of Goldstone’s theorem or the Coleman–Mermin–Wagner theorem;
- a complete classification of topological phases;
- a full lattice Monte Carlo treatment of phase diagrams;
- a theorem-level account of KMS states, algebraic phases, or constructive infinite-volume limits;
- a complete treatment of finite-temperature transitions.

Those topics belong to later chapters in this volume or to neighboring volumes on Gauge Theories, CFT and Bootstrap, Topological QFT, Condensed Matter QFT, Thermal and Real-Time QFT, and Mathematical and Rigorous QFT.

## Where to go next

Start with [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/). It gives the minimal vocabulary needed for everything else in the chapter.

After that, read [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), and [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/). Together they explain why the words “many vacua” mean something different in finite volume, infinite volume, Euclidean path integrals, Hilbert space, and defect sectors. Then read [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/) and [Moduli Spaces Preview](/nonperturbative-qft/vacuum-structure-phases/moduli-spaces-preview/) to separate local potentials, convex thermodynamic envelopes, coexistence regions, and genuine continuous families of vacua. Finally, read [Phase Diagrams](/nonperturbative-qft/vacuum-structure-phases/phase-diagrams/), [Quantum Phase Transitions](/nonperturbative-qft/vacuum-structure-phases/quantum-phase-transitions/), and [False Vacua and Metastability](/nonperturbative-qft/vacuum-structure-phases/false-vacua-and-metastability/) to organize vacuum diagnostics into parameter-space maps, zero-temperature critical behavior, and long-lived non-ground-state phases.

If your goal is confinement or gauge theory, continue from this chapter to [Order Parameters and Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/), then to Confinement, Screening, and Mass Gap. If your goal is semiclassics, continue to Semiclassical Methods and then Instantons, Tunneling, and Theta Vacua.

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially the lectures on secret symmetry, the effective potential, and false-vacuum decay.
- M. Srednicki, *Quantum Field Theory*, chapters on the quantum action, spontaneous symmetry breaking, chiral symmetry breaking, solitons, instantons, and theta vacua.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on vacuum expectation values, spontaneous symmetry breaking, Yang–Mills theory, and anomalies.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for sources, order parameters, Euclidean field integrals, renormalization, critical phenomena, and convexity.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for symmetry realization, effective actions, and vacuum structure in relativistic QFT.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on phases of gauge theories, solitons, false-vacuum decay, anomalies, and confinement.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for phases, order parameters, gauge-theory phases, topological fluids, and condensed-matter examples.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for broken symmetry, collective modes, renormalization group, topological field theory, and gauge theory in many-body systems.

## Version history

- **2026-06-26:** Linked the False Vacua and Metastability page and handed off to the Order Parameters and Diagnostics chapter.
- **2026-06-26:** Linked the Phase Diagrams and Quantum Phase Transitions pages in the reading path.
- **2026-06-26:** Linked the Effective Potential and Convexity and Moduli Spaces Preview pages in the reading path.
- **2026-06-26:** Linked the Spontaneous Symmetry Breaking and Discrete Vacua pages in the reading path.
- **2026-06-26:** Linked the Degenerate Vacua and Superselection Sectors pages in the reading path.
- **2026-06-26:** Initial polished chapter overview.
