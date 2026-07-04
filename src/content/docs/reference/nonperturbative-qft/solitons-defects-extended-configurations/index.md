---
title: "Solitons, Defects, and Extended Field Configurations"
description: "Chapter overview for solitons, defects, finite-energy boundary conditions, and extended nonperturbative configurations in QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Rajaraman; Manton and Sutcliffe; Coleman; Srednicki; Shifman; Nakahara; Polyakov."
topics:
  - solitons
  - topological defects
  - finite-energy boundary conditions
  - domain walls
  - vortices
  - monopoles
  - skyrmions
  - Q-balls
  - nontopological solitons
  - moduli spaces
  - extended operators
  - defect Hilbert spaces
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - topological-defects
  - finite-energy-boundary-conditions
  - nontopological-solitons
  - extended-operators
researchStatus:
  established:
    - "Finite-energy or finite-tension boundary conditions organize many classical solitons and defects into homotopy classes, with quantum states obtained by semiclassical quantization when a control parameter exists."
  active:
    - "Defects in strongly coupled theories, gauge-theory phase structure, noninvertible defects, and defect operator algebras require tools beyond classical topology and elementary semiclassics."
---

Solitons, Defects, and Extended Field Configurations is the chapter in the Nonperturbative QFT volume where nontrivial field configurations become physical objects. The central question is not merely “what are the classical solutions?” but “when does a field configuration define a stable sector, a charged excitation, an interface, a flux tube, or an operator insertion in the quantum theory?”

The chapter begins with the most important constraint: finite energy. A finite-energy condition is a boundary condition in disguise. It forces fields at spatial infinity to approach vacuum data, and that boundary data can carry topology. This is the bridge from local differential equations to global statements such as winding number, magnetic charge, domain-wall number, and Skyrmion number.

This chapter is deliberately concrete. Topology supplies the classification language, but the emphasis is on field configurations, actions, tensions, spectra, zero modes, moduli, and the quantum roles of defects. The same homotopy group can look like elegant mathematics on one page and like a measurable flux tube or domain wall on the next.

$$
\text{finite energy}
\quad\Longrightarrow\quad
\text{vacuum data at infinity}
\quad\Longrightarrow\quad
\text{possible topological sectors}.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![A schematic classification of domain walls, vortices, monopoles, and textures by their boundary spheres and homotopy groups.](/figures/nonperturbative-qft/solitons-defects-classification.svg)

<figcaption>

Many finite-energy sectors are classified by the boundary sphere in the directions transverse to the object. If a defect has spatial dimension $p$ inside $n$ spatial dimensions, the transverse dimension is $m=n-p$, and finite energy often gives boundary data $\phi_\infty:S^{m-1}_\infty\to\mathcal M_{\rm vac}$. The relevant homotopy group is then $\pi_{m-1}(\mathcal M_{\rm vac})$, with important gauge-theory qualifications.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/nonperturbative-qft/conventions/), [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

For the geometric language, it helps to know the basic idea of homotopy groups. The chapter uses homotopy as a classification tool, but it will state the needed maps explicitly rather than assuming a topology course.

## Reading path

Read the chapter in this order on a first pass. Only the first page is needed before the named examples; everything else is a specialization or refinement.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/) | Why finite energy forces fields to approach vacuum data at infinity, and how topology enters through maps from boundary spheres. |
| 2 | [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/) | The simplest localized solitons: static finite-energy solutions in one spatial dimension interpolating between vacua. |
| 3 | [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/) | Codimension-one defects separating distinct vacua, with tension rather than finite total energy in infinite volume. |
| 4 | [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/) | Codimension-two winding defects, including global vortices and gauge vortices with quantized flux. |
| 5 | [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/) | Codimension-three magnetic defects, smooth gauge cores, and the role of the vacuum manifold at spatial infinity. |
| 6 | [Skyrmions](/nonperturbative-qft/solitons-defects-extended-configurations/skyrmions/) | Solitons classified by maps from compactified space into a target or order-parameter manifold. |
| 7 | [Q-Balls](/nonperturbative-qft/solitons-defects-extended-configurations/q-balls/) | Nontopological solitons stabilized by a conserved charge rather than a homotopy class. |
| 8 | [BPS Bounds](/nonperturbative-qft/solitons-defects-extended-configurations/bps-bounds-preview/) | First-order equations and energy bounds that protect special solitons. |
| 9 | [Moduli-Space Dynamics](/nonperturbative-qft/solitons-defects-extended-configurations/moduli-space-dynamics-preview/) | The low-energy dynamics of slowly moving solitons as geodesic motion on moduli space. |
| 10 | [Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/) | The relation between classical defect configurations, extended operator insertions, disorder boundary conditions, and defect Hilbert spaces. |

The early examples should be read as templates. Kinks teach boundary conditions and zero modes; vortices teach winding and flux; monopoles teach gauge-covariant topology; Skyrmions teach compactified-space maps; Q-balls teach fixed-charge stabilization; BPS examples teach when second-order field equations reduce to first-order equations.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Vacuum manifold $\mathcal M_{\text{vac}}$ | The set of field values or gauge-inequivalent vacuum data minimizing the energy density. | Boundary conditions at infinity usually land in $\mathcal M_{\text{vac}}$. |
| Codimension | The number $c$ of spatial directions transverse to an extended object. | Boundary data lives on a sphere $S^{c-1}$ surrounding the defect. |
| Topological sector | A connected component of finite-energy configuration space with fixed boundary rules. | Sectors cannot be continuously deformed into one another without leaving the allowed configuration space. |
| Topological charge | A discrete label, often an integer, computed from boundary data or a conserved density. | It can protect a soliton against decay into the vacuum. |
| Core | The region where fields leave the vacuum manifold. | The core regularizes winding or flux and determines the soliton size and tension. |
| Tension | Energy per unit length, area, or higher-dimensional volume of an extended object. | Infinite total energy can still mean finite physical tension. |
| Moduli | Continuous parameters of a family of solutions, such as position, phase, size, or orientation. | Moduli become collective coordinates in semiclassical quantization. |
| Zero modes | Normalizable fluctuations tangent to moduli or symmetry orbits. | They must be removed from determinants and integrated as collective coordinates. |
| Gauge quotient | The removal of pure gauge redundancy from boundary data and moduli. | Naively using the vacuum manifold before quotienting can overcount sectors. |
| Nontopological soliton | A localized configuration stabilized by conserved charge and energetics rather than a homotopy class. | Q-balls show that soliton stability need not come from topology. |

## Common confusions

**A soliton is not just any classical lump.** A soliton is a localized or extended configuration whose stability, lifetime, or quantum role survives more than a casual deformation. Some are topologically protected, some are stabilized dynamically, and some are only semiclassical resonances.

**Finite total energy and finite tension are different.** A pointlike soliton in infinite space can have finite total energy. A domain wall or string has infinite total energy in infinite volume, but finite energy per unit area or length.

**Topology at infinity is not optional decoration.** For most familiar topological solitons, the charge is visible only after imposing the finite-energy boundary condition. Without the boundary condition, many “topological” labels evaporate.

**The vacuum manifold is not always the physical configuration space.** In gauge theories, field values related by gauge transformations are physically equivalent. The correct classification may involve gauge-invariant data, bundles, holonomies, or boundary gauge transformations, not just the set of scalar minima.

**Topological stability is not the same as absolute stability.** A topological charge can prevent decay to the vacuum inside a sector, but soliton–antisoliton pairs can annihilate, defects can end on other defects in enlarged theories, and quantum tunneling can change sectors when the assumed boundary conditions are changed.

**Euclidean instantons are cousins, not identical twins.** Solitons and defects in this chapter are usually finite-energy or finite-tension configurations in space. Instantons are finite-action configurations in Euclidean spacetime and belong to the next chapter.

## Boundaries

This chapter does:

- explain how finite-energy boundary conditions produce maps to vacuum data;
- classify the basic solitons and defects by codimension and homotopy;
- connect classical solutions to semiclassical quantization, moduli, zero modes, and fluctuation spectra;
- distinguish global and gauge defects;
- prepare the later instanton, confinement, lattice, and large-N chapters.

This chapter does not try to do:

- replace a topology text on homotopy, cohomology, characteristic classes, or cobordism;
- give the full mathematical theory of defects in algebraic QFT or extended TQFT;
- classify all conformal, topological, or noninvertible defects;
- prove existence and stability theorems for every nonlinear field equation;
- give numerical soliton methods or lattice defect simulations.

Those topics belong to the Mathematical Toolkit, Symmetry and Topology, CFT and Bootstrap, Mathematical and Rigorous QFT, or Computational QFT volumes. Here the center of gravity is nonperturbative field configurations and their quantum use.

## Where to go next

Start with [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/). It gives the boundary-at-infinity logic used by the rest of the chapter.

After that, the natural sequence is [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), [Skyrmions](/nonperturbative-qft/solitons-defects-extended-configurations/skyrmions/), and [Q-Balls](/nonperturbative-qft/solitons-defects-extended-configurations/q-balls/). Those examples build up the codimension ladder

$$
S^0,
\quad S^1,
\quad S^2,
\quad S^d,
$$

and show how boundary and topological data become mass, tension, flux, or winding charge. Q-balls then add the complementary lesson that a soliton can be stabilized by Noether charge rather than topology. After these examples, read [BPS Bounds](/nonperturbative-qft/solitons-defects-extended-configurations/bps-bounds-preview/) and [Moduli-Space Dynamics](/nonperturbative-qft/solitons-defects-extended-configurations/moduli-space-dynamics-preview/) to see how first-order equations, no-force conditions, zero modes, and collective-coordinate metrics organize special solitons. Then return to [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/) and [One-Loop Determinants Around Saddles](/nonperturbative-qft/semiclassical-methods/one-loop-determinants-around-saddles/) to see how classical objects become quantum states.

Before leaving this chapter, read [Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/) to separate dynamical solitons, external defect insertions, and Hilbert-space sectors. The next major chapter, [Instantons, Tunneling, and Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/), uses many of the same global ideas with space replaced by Euclidean spacetime.

## References

### Standard first pass

- R. Rajaraman, *Solitons and Instantons*, for a classic introduction to kinks, solitons, collective coordinates, and instantons.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for the modern geometric and dynamical treatment of solitons.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on kinks and domain walls, vortices, monopoles and Skyrmions, and phases of gauge theories.
- S. Coleman, “Q-balls,” and T. D. Lee and Y. Pang, “Nontopological Solitons,” for the charge-stabilized side of soliton physics.

### Broader context

- M. Srednicki, *Quantum Field Theory*, for solitons, monopoles, instantons, theta vacua, gauge theory, and spontaneous symmetry breaking.
- S. Coleman, *Aspects of Symmetry*, for spontaneous symmetry breaking, semiclassics, false-vacuum decay, and the physics style that underlies much of this subject.
- M. Nakahara, *Geometry, Topology and Physics*, for homotopy groups, defects in ordered media, monopoles, instantons, and the geometry used in topological classification.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling, instanton, confinement, loop, and gauge-string perspectives.

## Version history

- **2026-06-27:** Linked Defects Versus Operators and the new Instantons, Tunneling, and Theta Vacua chapter.
- **2026-06-27:** Linked BPS Bounds and Moduli-Space Dynamics in the reading path.
- **2026-06-26:** Linked Skyrmions and Q-Balls in the reading path.
- **2026-06-26:** Linked Vortices and Monopoles in the reading path.
- **2026-06-26:** Linked Kinks and Domain Walls in the reading path.
- **2026-06-26:** Initial polished chapter overview, added together with Finite-Energy Boundary Conditions.
