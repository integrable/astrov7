---
title: "Instantons, Tunneling, and Theta Vacua"
description: "Chapter overview for Euclidean instantons, tunneling, topological sectors, theta vacua, and fermion zero modes in nonperturbative QFT."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Coleman; Rajaraman; Srednicki; Weinberg; Shifman; Polyakov; Mariño; Nakahara."
topics:
  - instantons
  - tunneling
  - theta vacua
  - topological sectors
  - Yang–Mills instantons
  - fermion zero modes
  - anomalies
  - instanton measure
  - instanton gas
  - sphalerons
  - semiclassical methods
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - theta-vacua
  - topological-charge
  - semiclassical-methods
researchStatus:
  established:
    - "Instantons are finite-action Euclidean saddle configurations that compute tunneling and topology-sensitive effects when the semiclassical expansion is controlled."
  active:
    - "Instantons in strongly coupled gauge theories, dense instanton ensembles, renormalons, complex saddles, and resurgence require additional tools and remain active research areas."
---

Instantons, Tunneling, and Theta Vacua is the chapter in the Nonperturbative QFT volume where Euclidean topology becomes quantum dynamics. The central objects are finite-action Euclidean saddle configurations that connect classically distinct sectors, generate effects proportional to $e^{-S_E}$, and force us to take the global structure of configuration space seriously.

The chapter starts with ordinary quantum mechanics because the double-well and periodic-potential problems teach the right lesson with minimal technology: perturbation theory around one minimum cannot see tunneling. QFT then adds topology, gauge fields, fermion zero modes, anomalies, theta angles, and sector sums.

The basic path-integral slogan is

$$
Z(\theta)
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q,
\qquad
Z_Q
=
\int_{\text{topological charge }Q}\mathcal D\Phi\,e^{-S_E[\Phi]}.
$$

In Yang–Mills theory, the most famous saddles obey self-duality or anti-self-duality,

$$
F=\pm \widetilde F,
$$

and saturate the Euclidean action bound

$$
S_E\ge \frac{8\pi^2}{g^2}|Q|.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic roadmap from topological sectors and Euclidean saddles to theta sums, zero modes, and physical observables.](/figures/nonperturbative-qft/instantons-theta-vacua-roadmap.svg)

<figcaption>

Instanton physics ties together topological sectors, finite-action Euclidean saddles, tunneling amplitudes, theta-dependent sector sums, collective-coordinate measures, and observables such as $E(\theta)$, $\chi_{\rm top}$, and anomaly-induced selection rules.

</figcaption>
</figure>

The warning label is just as important as the formulas: instantons are not generic magic nonperturbative corrections. They are specific semiclassical saddles, useful when their action is large enough and their zero modes, negative modes, measure, and interactions are under control.

## Prerequisites

You should know [Conventions and Notation](/nonperturbative-qft/conventions/), [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/), [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/), [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/), and the whole [Semiclassical Methods](/nonperturbative-qft/semiclassical-methods/) chapter through [One-Loop Determinants Around Saddles](/nonperturbative-qft/semiclassical-methods/one-loop-determinants-around-saddles/).

For the topological language, it helps to know the idea of compactifying space or Euclidean spacetime and classifying maps by homotopy classes. For the gauge-theory pages, you should be comfortable with Yang–Mills fields, the field strength $F_{\mu\nu}$, the dual field strength $\widetilde F_{\mu\nu}$, and the basic relation between topology and total derivatives.

For the later fermion pages, you should know chiral symmetry, the axial anomaly, and the difference between bosonic and fermionic zero modes.

## Reading path

Read this chapter in three passes. The first pass learns tunneling. The second pass learns gauge topology. The third pass learns zero modes, anomalies, measures, and thermal extensions.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Instantons in Quantum Mechanics](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-quantum-mechanics/) | The double-well and periodic-potential prototypes: tunneling amplitudes, energy splittings, theta-like labels, and dilute instanton gases. |
| 2 | [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/) | The definition of a finite-action Euclidean saddle in QFT, plus boundary data, topological sectors, and the difference between instantons, bounces, and solitons. |
| 3 | [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/) | Self-dual gauge fields, BPST instantons, action bounds, and why Yang–Mills instantons are localized in four Euclidean dimensions. |
| 4 | [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) | Integer topological charge, Chern–Simons number, $F\widetilde F$, and normalization conventions. |
| 5 | [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) | Superpositions of winding sectors, the theta angle, theta-dependent energy, and CP questions. |
| 6 | [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/) | How Euclidean finite-action saddles mediate transitions between sectors and generate exponentially small effects. |
| 7 | [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) | The index-theorem logic, Grassmann zero modes, selection rules, and why instantons often vanish unless operators saturate zero modes. |
| 8 | [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) | Chiral charge violation, anomaly matching, and the relation between instantons and anomalous symmetry transformations. |
| 9 | [Instanton Measure](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-measure-preview/) | The collective-coordinate measure, determinant ratios, gauge orientation, size moduli, fermion saturation, and renormalization. |
| 10 | [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/) | When instantons can be summed as a dilute ensemble, how grand-canonical exponentiation works, and what physics the gas produces. |
| 11 | [Sphalerons](/nonperturbative-qft/instantons-tunneling-theta-vacua/sphalerons-preview/) | Thermal transitions over barriers rather than tunneling through them, including Chern–Simons diffusion and anomalous $B+L$ violation. |

The first four pages are the backbone. After them, theta vacua make conceptual sense. Fermion zero modes and anomalies should be read after the gauge-theory topology is clear, not before. The measure page should be read after [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) and [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), because the compact formula hides a lot of important plumbing.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Euclidean action $S_E$ | The action appearing in $e^{-S_E}$ after Wick rotation. | Instanton effects are exponentially weighted by finite Euclidean action. |
| Finite-action boundary condition | Fields approach vacuum or pure-gauge data at Euclidean infinity. | This compactifies spacetime and makes topological sectors possible. |
| Topological charge $Q$ | An integer label for sectors, often written as an integral of a total derivative or density. | Sector sums and theta dependence are organized by $Q$. |
| Instanton | A finite-action Euclidean saddle, often changing $Q$ by $+1$. | Gives tunneling amplitudes and nonperturbative corrections. |
| Anti-instanton | The corresponding saddle with opposite orientation or charge. | Gives the $Q=-1$ sector and restores real/CP-constrained combinations when appropriate. |
| Self-duality | The equation $F=+\widetilde F$ or $F=-\widetilde F$. | In Yang–Mills theory it reduces second-order equations to first-order equations and saturates the action bound. |
| Chern–Simons number | A label for gauge-field vacua on spatial slices. | Tunneling changes Chern–Simons number by an integer. |
| Theta angle | A coefficient multiplying the topological charge. | Weights sectors by $e^{i\theta Q}$ and affects quantum physics despite being a total derivative locally. |
| Bosonic zero modes | Flat directions of the instanton action. | Become collective coordinates such as position, size, and gauge orientation. |
| Fermion zero modes | Normalizable zero eigenfunctions of the Dirac operator in the instanton background. | Force selection rules and generate ’t Hooft vertices. |
| Dilute gas | Approximation in which instantons are rare and weakly interacting. | Turns multi-instanton sums into exponentials or effective potentials. |
| Sphaleron | Static unstable configuration at the top of an energy barrier. | Controls thermal transitions between sectors. |

## Common confusions

**Instantons are Euclidean saddles, not Lorentzian particles.** A soliton is often a finite-energy object in space. An instanton is a finite-action event in Euclidean spacetime. Some equations look similar; the interpretation is not.

**Nonperturbative does not always mean strongly coupled.** Weak-coupling instanton corrections are nonperturbative because they scale like $e^{-\mathrm{const}/g^2}$, invisible to every order in powers of $g$. They can still be semiclassically controlled when $g$ is small at the instanton scale.

**A total derivative can change quantum physics.** The theta term is locally a total derivative in Yang–Mills theory, so it does not change the classical local equations of motion on trivial field histories. It changes the quantum theory because the path integral sums over topological sectors.

**The instanton action is only the leading exponential.** A useful answer also needs the determinant ratio, zero-mode measure, normalization, renormalization scale, integration over sizes and positions, and possible interactions with other instantons.

**Fermion zero modes are not optional decoration.** In a background with fermion zero modes, the fermionic determinant vanishes unless operator insertions or mass terms saturate the Grassmann integrations. This is the source of many instanton-induced selection rules.

**Not every Euclidean saddle is an instanton.** Bounces describe false-vacuum decay and have one negative mode. Instantons often connect degenerate sectors or contribute to tunneling amplitudes. Complex saddles and thimbles belong to the resurgence story.

**Instanton gases are approximations.** They require rare, well-separated events. Dense instanton ensembles, large instantons in strongly coupled regimes, and infrared-divergent size integrals require extra physics.

## Boundaries

This chapter does:

- introduce instantons first in quantum mechanics, where the tunneling interpretation is transparent;
- define finite-action Euclidean saddle configurations in QFT;
- explain topological sectors, instanton number, theta angles, and theta vacua;
- derive the key Yang–Mills action bound and the role of self-duality;
- explain zero modes, determinant exclusions, collective-coordinate measures, and dilute gases;
- connect instantons to fermion zero modes, anomalies, and induced effective interactions;
- prepare later discussions of confinement mechanisms, large-N theta dependence, resurgence, renormalons, and finite-temperature sphalerons.

This chapter does not try to do:

- give a complete numerical theory of strongly coupled gauge dynamics;
- claim that instantons alone explain confinement in four-dimensional QCD;
- replace lattice definitions of Yang–Mills theory;
- develop the full mathematical theory of moduli spaces of anti-self-dual connections;
- cover every supersymmetric exact result from instantons;
- treat complex saddles, Lefschetz thimbles, and resurgence in full depth.

Those topics belong to later chapters on Confinement, Screening, and Mass Gap; Large-N Methods; Lattice Field Theory; Supersymmetry and Duality; and Resurgence and Transseries.

## Where to go next

Start with [Instantons in Quantum Mechanics](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-quantum-mechanics/). It is the small laboratory where the whole story can be seen: degenerate minima, Euclidean classical paths, zero modes, determinants, and tunneling splittings.

Then read [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/), and [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) as a single unit. These pages explain what changes when the tunneling coordinate becomes a field, why finite action imposes pure-gauge boundary conditions at infinity, and how $F\widetilde F$ measures topology.

After that, read [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) and [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/). These are the conceptual center of the chapter. They explain why the physically useful vacuum is often not a single winding sector $|n\rangle$, but a theta superposition,

$$
|\theta\rangle
=\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

Then continue to [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/), which explain why instantons know about chiral symmetry and anomaly-induced selection rules. Finally, use [Instanton Measure](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-measure-preview/) and [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/) as calculation tools, and [Sphalerons](/nonperturbative-qft/instantons-tunneling-theta-vacua/sphalerons-preview/) as the bridge to finite-temperature nonperturbative physics. Then continue to [Confinement, Screening, and Mass Gap](/nonperturbative-qft/confinement-screening-mass-gap/) for Wilson loops, line-operator diagnostics, flux tubes, screening, and spectral gaps.

For background already developed in this volume, revisit [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/), [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/), [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/), and [Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/).

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially the lectures on instantons, tunneling, false-vacuum decay, and functional methods.
- R. Rajaraman, *Solitons and Instantons*, for the classic bridge from solitons to instantons.
- M. Srednicki, *Quantum Field Theory*, especially the chapters on solitons and monopoles, instantons and theta vacua, and quarks and theta vacua.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on instantons, false-vacuum decay, anomalies, and confinement-related models.

### Deeper and broader references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for modern applications, anomalies, instantons, theta terms, and gauge theory.
- M. Mariño, *Instantons and Large N*, for instantons in quantum mechanics, Yang–Mills instantons, large-order behavior, Borel summability, and large-N connections.
- A. M. Polyakov, *Gauge Fields and Strings*, for instantons in Abelian systems, topology of gauge fields, confinement analogies, and loop dynamics.
- M. Nakahara, *Geometry, Topology and Physics*, for the geometric background on homotopy, bundles, monopoles, and instantons.
- G. ’t Hooft, “Symmetry Breaking Through Bell–Jackiw Anomalies,” for instantons, fermion zero modes, and anomaly-induced effects.
- A. Belavin, A. Polyakov, A. Schwartz, and Y. Tyupkin, “Pseudoparticle Solutions of the Yang–Mills Equations,” for the original BPST instanton.

## Version history

- **2026-06-27:** Initial polished chapter overview. Added together with Defects Versus Operators as the transition from the solitons/defects chapter into instanton physics.
- **2026-06-27:** Added links to Instantons in Quantum Mechanics and Instantons in Field Theory after drafting those pages.
- **2026-06-27:** Added links to Yang–Mills Instantons and Instanton Number after drafting those pages.
- **2026-06-27:** Added links to Theta Vacua and Tunneling Between Vacua after drafting those pages.
- **2026-06-27:** Added links to Fermion Zero Modes and Instantons and Anomalies after drafting those pages.
- **2026-06-27:** Added links to Instanton Measure and Instanton Gas after drafting those pages.
- **2026-06-27:** Added link to Sphalerons and handoff to Confinement, Screening, and Mass Gap.
