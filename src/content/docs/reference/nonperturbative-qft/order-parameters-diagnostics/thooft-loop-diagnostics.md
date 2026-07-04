---
title: "’t Hooft-Loop Diagnostics"
description: "Explains how ’t Hooft loops define magnetic disorder probes and diagnose dual confinement, Higgs phases, oblique confinement, and magnetic one-form symmetry."
sidebar:
  label: "’t Hooft-Loop Diagnostics"
  order: 8
level: Graduate
status: "Polished draft"
source: "’t Hooft; Polyakov; Gaiotto–Kapustin–Seiberg–Willett; Fradkin; Shifman; Pestun et al."
topics:
  - ’t Hooft loops
  - disorder operators
  - magnetic flux
  - confinement
  - Higgs phase
  - oblique confinement
  - one-form symmetry
canonicalTopics:
  - nonperturbative-qft
  - thooft-loops
  - disorder-operators
  - magnetic-one-form-symmetry
  - confinement-diagnostics
researchStatus:
  established:
    - "’t Hooft loops are standard magnetic disorder line operators, defined by prescribed magnetic singularities or equivalent bundle modifications around a loop."
  active:
    - "In non-Abelian theories, the complete interpretation of ’t Hooft loops depends on the global form of the gauge group, allowed line operators, discrete theta angles, duality frame, and possible mixed anomalies."
---

## Summary

An **’t Hooft loop** is the magnetic counterpart of a Wilson loop. A Wilson loop measures the holonomy of the gauge field around a curve. An ’t Hooft loop instead inserts a prescribed magnetic singularity along a curve, or equivalently modifies the gauge bundle around that curve.

In a four-dimensional gauge theory, an ’t Hooft line $T_B(C)$ supported on a closed curve $C$ is labeled, roughly, by a magnetic charge $B$. Near a small two-sphere $S^2$ linking the line,

$$
\frac{1}{2\pi}\int_{S^2}F\sim B,
$$

where $B$ lies in an appropriate coweight lattice, modulo identifications by the Weyl group and by the global form of the gauge group. This formula is schematic but captures the key point: the operator is defined by a singular boundary condition, not by tracing a local field around $C$.

The diagnostic power of ’t Hooft loops comes from their algebra with Wilson loops. In the simplest center-valued case,

$$
T_m(C)W_e(C')
=\exp\left(2\pi i\,\langle e,m\rangle\operatorname{Lk}(C,C')\right)
W_e(C')T_m(C),
$$

where $\operatorname{Lk}(C,C')$ is the linking number. This algebra says that Wilson and ’t Hooft loops measure mutually nonlocal electric and magnetic charges.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A magnetic ’t Hooft loop linked with an electric Wilson loop, illustrating the Wilson–’t Hooft linking phase.](/figures/nonperturbative-qft/thooft-loop-linking-algebra.svg)

<figcaption>

An ’t Hooft loop inserts magnetic flux. A Wilson loop linked with it detects that flux by a phase. This linking algebra is the line-operator version of electric–magnetic mutual nonlocality.

</figcaption>
</figure>

Together, Wilson and ’t Hooft loops distinguish confinement, Higgs, Coulomb, and oblique-confinement behavior much more sharply than either one alone.

## Prerequisites

Read [Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/) first. You should also know [Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/), [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), [Conventions and Notation](/nonperturbative-qft/conventions/), and [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/).

The page assumes basic gauge theory, Dirac quantization, and the idea that the global form of the gauge group affects which line operators are genuine.

## Core idea

A Wilson loop asks what happens to an external electric charge. An ’t Hooft loop asks what happens to an external magnetic probe.

The most compact slogan is:

$$
\text{Wilson loops insert electric probes; ’t Hooft loops insert magnetic disorder.}
$$

This distinction matters because phases of gauge theory often look different to electric and magnetic probes. In a confining phase, electric flux is squeezed into a string, so suitable Wilson loops have an area law. In a Higgs phase, magnetic flux can be squeezed into a string, so suitable ’t Hooft loops have an area law. In a Coulomb phase, both electric and magnetic probes see long-range fields. In an oblique-confining phase, the condensed object is dyonic, and the simple electric/magnetic labels must be replaced by a dyonic line-operator lattice.

A useful first diagnostic table is:

| Phase language | Wilson loop | ’t Hooft loop | Physical image |
|---|---|---|---|
| Confinement of electric probes | Area law | Perimeter law | Electric flux tube; magnetic probes screened or condensed in a dual description. |
| Higgs phase | Perimeter law | Area law | Electric probes screened; magnetic flux confined. |
| Coulomb phase | Coulomb law | Coulomb law | Massless photon; long-range electric and magnetic fields. |
| Oblique confinement | Depends on electric charge | Depends on magnetic charge | A dyonic combination has perimeter behavior; mutually nonlocal probes may have area laws. |

This table is intentionally schematic. The precise statement depends on the global form of the gauge group and the allowed genuine lines.

## Setup and conventions

An ’t Hooft loop is a disorder operator. Rather than inserting a function of smooth fields, it changes the class of fields included in the path integral. Formally,

$$
\langle T_B(C)\,X\rangle
=
\frac{1}{Z}\int_{\text{fields with magnetic singularity }B\text{ along }C}
\mathcal D\Phi\,X[\Phi]e^{-S_E[\Phi]}.
$$

In an Abelian theory, a line along the Euclidean time direction may be described locally as a Dirac monopole singularity in the three transverse directions. For a small sphere linking the line,

$$
\int_{S^2}F=2\pi m,
$$

where $m$ is the magnetic charge in the normalization appropriate to the electric charges of the theory.

In a non-Abelian theory, one chooses $B$ in the Cartan subalgebra. Single-valuedness of all allowed Wilson lines imposes the Dirac quantization condition

$$
\exp(2\pi i B)=1
$$

as seen by the allowed electric probes. More invariantly, $B$ belongs to the coweight lattice appropriate to the gauge group, modulo Weyl transformations and additional identifications.

The phrase “appropriate to the gauge group” is doing real work. The same local Lie algebra can define different theories with different genuine line operators. For example, theories with local algebra $\mathfrak{su}(N)$ but global group $SU(N)$ or $PSU(N)$ have different electric and magnetic line spectra.

## The lattice definition

On the lattice, an ’t Hooft loop can be defined without singular continuum fields. For a discrete or center-valued magnetic insertion, choose a surface $\Sigma$ whose boundary is the loop:

$$
\partial\Sigma=C.
$$

Then modify the plaquette terms pierced by $\Sigma$ by a center element. In an $SU(N)$-type theory, this means multiplying pierced plaquettes by

$$
z=e^{2\pi i k/N}\in \mathbb Z_N.
$$

Changing the surface $\Sigma$ without moving its boundary should be an unphysical deformation, except when it crosses Wilson lines charged under the center. When such a crossing happens, the correlator picks up precisely the Wilson–’t Hooft linking phase.

This lattice picture is often the clearest way to remember the definition:

$$
\text{an ’t Hooft loop is the boundary of a magnetic twist sheet.}
$$

The sheet itself is auxiliary; the boundary is the operator. If the sheet crosses an electric Wilson loop, the crossing is observable through a phase.

## Wilson–’t Hooft algebra

The defining diagnostic feature of ’t Hooft loops is their mutual nonlocality with Wilson loops. Let $W_e(C')$ be an electric line and $T_m(C)$ a magnetic line. If the two loops are linked, their ordering differs by a phase:

$$
T_m(C)W_e(C')
=\exp\left(2\pi i\,\langle e,m\rangle\operatorname{Lk}(C,C')\right)
W_e(C')T_m(C).
$$

Here $\langle e,m\rangle$ is the electric–magnetic pairing. In the simplest $\mathbb Z_N$ center example, a fundamental Wilson loop and a minimal ’t Hooft loop obey

$$
T(C)W(C')
=e^{2\pi i\operatorname{Lk}(C,C')/N}W(C')T(C).
$$

This algebra is a nonlocal analog of a commutation relation. It tells us that electric and magnetic line operators cannot all be simultaneously ordinary local operators. Choosing the global form of the gauge group and the genuine line operators is therefore part of specifying the theory, not a decorative afterthought.

## Diagnostic laws

Just like Wilson loops, ’t Hooft loops can have area, perimeter, or Coulomb behavior. For a large loop $C$,

$$
\langle T(C)\rangle\sim e^{-\widetilde\sigma A(C)}
$$

means an ’t Hooft-loop area law, with magnetic string tension $\widetilde\sigma$. For a large rectangular ’t Hooft loop, this corresponds to a linearly growing potential between external magnetic probes.

A perimeter law,

$$
\langle T(C)\rangle\sim e^{-\widetilde\mu P(C)},
$$

means no asymptotic magnetic flux tube after local line renormalization. In a Coulomb phase, the magnetic probes interact through a long-range potential.

The classic Wilson–’t Hooft phase diagnostics can then be stated as:

| Electric/magnetic response | Wilson loop | ’t Hooft loop |
|---|---|---|
| Electric confinement | Area | Perimeter |
| Higgs screening of electric charge | Perimeter | Area |
| Coulomb phase | Coulomb | Coulomb |
| Oblique confinement | Area or perimeter depending on dyonic charge | Area or perimeter depending on dyonic charge |

The table is safest for theories where the relevant lines are genuine and where matter content does not explicitly break the corresponding one-form symmetries. With dynamical matter, line operators can end on dynamical particles, and the asymptotic law may cease to be a sharp order parameter.

## Magnetic one-form symmetry

Wilson loops are naturally charged under electric one-form symmetries. ’t Hooft loops are naturally charged under magnetic one-form symmetries, when such symmetries exist.

For example, a theory with gauge group $PSU(N)=SU(N)/\mathbb Z_N$ has a magnetic $\mathbb Z_N$ one-form symmetry. The corresponding charged line is an ’t Hooft line. The large-loop rule is the same generalized-symmetry rule as for Wilson loops:

| Magnetic one-form symmetry realization | Charged ’t Hooft loop behavior |
|---|---|
| Unbroken magnetic one-form symmetry | Area law. |
| Broken magnetic one-form symmetry | Perimeter or Coulomb behavior after local line renormalization. |
| Broken to a subgroup | Lines charged under the unbroken subgroup have area law. |

This language also clarifies why an ’t Hooft loop is not automatically available as a genuine line in every theory. In an $SU(N)$ theory, fundamental Wilson lines are genuine, but minimally charged ’t Hooft lines can require attached surfaces depending on the chosen global form and line spectrum. In a $PSU(N)$ theory, the magnetic line spectrum is different.

The diagnostic statement should therefore specify:

| Required data | Why it matters |
|---|---|
| Local gauge algebra | Determines local gluons and perturbative dynamics. |
| Global gauge group | Determines which electric and magnetic charges are genuine. |
| Discrete theta angle, when present | Changes the allowed dyonic line lattice. |
| Matter content | Determines whether line charges can be screened or explicitly broken. |
| Dimension and boundary conditions | Affect whether loop behavior is area, perimeter, Coulomb, or topological. |

## Confinement, Higgs, and oblique confinement

The ’t Hooft loop was introduced precisely because a Wilson loop alone cannot give a complete phase taxonomy. Consider a gauge theory with both electric and magnetic probes available.

In an electric confining phase, external electric charges are connected by an electric flux tube. A suitable Wilson loop has area law. The magnetic probe is not confined in the same way; a suitable ’t Hooft loop has perimeter behavior.

In a Higgs phase, electric charges can be screened by the condensate. A suitable Wilson loop has perimeter behavior. Magnetic flux, however, is squeezed into vortex tubes, so a suitable ’t Hooft loop has area behavior.

In a Coulomb phase, neither electric nor magnetic flux is squeezed into a string. Both Wilson and ’t Hooft loops show Coulomb behavior, reflecting a massless photon.

In an oblique-confining phase, the condensed object carries both electric and magnetic charge. The line with perimeter behavior is then a dyonic Wilson–’t Hooft line, not a purely electric Wilson line or a purely magnetic ’t Hooft line. This is one reason the full line-operator lattice is more fundamental than the words “electric” and “magnetic” in isolation.

## Relation to dual superconductivity

A common physical picture of confinement is the **dual superconductor**. In an ordinary superconductor, electric charges condense and magnetic flux is confined into Abrikosov vortices. In a dual superconductor, magnetic objects condense and electric flux is confined into strings.

In this picture:

| Condensate picture | Confined flux | Loop diagnostic |
|---|---|---|
| Electric condensate | Magnetic flux | ’t Hooft area law. |
| Magnetic condensate | Electric flux | Wilson area law. |
| Dyonic condensate | Mutually nonlocal dyonic flux | Oblique confinement. |

This language is physically useful but should be handled carefully. A condensate of a gauge-charged object is not by itself a gauge-invariant local order parameter. The gauge-invariant diagnostic is the behavior of line operators, the realization of one-form symmetries, and the spectrum of excitations.

## Supersymmetric and duality contexts

In supersymmetric gauge theories, Wilson and ’t Hooft loops often fit into a larger family of Wilson–’t Hooft line operators labeled by electric and magnetic charges. Electric–magnetic dualities can exchange Wilson and ’t Hooft loops, or map them to dyonic lines.

For example, in many four-dimensional supersymmetric theories, a half-BPS Wilson loop includes scalar couplings in addition to the gauge holonomy, while a half-BPS ’t Hooft loop imposes compatible magnetic singularities and scalar singularities. Localization can sometimes compute their expectation values exactly or reduce them to finite-dimensional integrals.

Those exact supersymmetric results are not needed for the basic diagnostic role of ’t Hooft loops. They are mentioned here because they reinforce the conceptual point: Wilson and ’t Hooft loops are not optional decorations. They are fundamental observables, and in duality frames they transform into one another.

## Common pitfalls

**Pitfall: defining an ’t Hooft loop as a Wilson loop of a dual gauge field.** That can be true in a weakly coupled Abelian dual description, but it is not the general definition. The general definition is a magnetic singularity or bundle modification.

**Pitfall: ignoring the global form of the gauge group.** The local Lie algebra does not determine the genuine magnetic line operators. $SU(N)$ and $PSU(N)$ theories have different line spectra.

**Pitfall: treating the Dirac string as physical.** The auxiliary surface or string used to define the singularity should be unobservable except through its linking with electric operators. If it becomes observable, the definition has changed.

**Pitfall: overusing the confinement/Higgs table.** The simple Wilson–’t Hooft table assumes the relevant lines are genuine and the relevant symmetries are not explicitly broken by dynamical matter.

**Pitfall: forgetting line renormalization.** ’t Hooft loops, like Wilson loops, have UV-sensitive perimeter and cusp divergences. Area-law statements concern the large-distance part after local geometric terms are separated.

**Pitfall: confusing magnetic one-form symmetry with magnetic gauge redundancy.** A one-form symmetry is a physical global symmetry acting on line operators. Gauge redundancy is not a physical symmetry acting on states.

## Relations to other pages

[Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/) is the electric partner of this page. The Wilson–’t Hooft pair is the minimal diagnostic language for many gauge-theory phases.

[Disorder Parameters](/nonperturbative-qft/order-parameters-diagnostics/disorder-parameters/) explains the broader idea of defining operators by twists, singularities, and modified boundary conditions. ’t Hooft loops are among the most important gauge-theory examples.

[Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/) explains why sectors labeled by charges or boundary conditions cannot always be mixed by local operators. Line operators often diagnose exactly this structure.

[Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) distinguishes spectral gaps from confinement diagnostics. A phase can be gapped, Higgsed, topologically ordered, or confining in ways that require line operators to tell apart.

The later confinement chapter will use Wilson and ’t Hooft loops together to discuss confinement, screening, center symmetry, dual superconductivity, oblique confinement, and compact gauge theory.

## Research status

**Established.** ’t Hooft loops are standard magnetic disorder line operators. They are defined by prescribed singularities, by gauge-bundle modifications, or on the lattice by magnetic twist sheets ending on the loop.

**Established.** The Wilson–’t Hooft linking algebra captures electric–magnetic mutual nonlocality and is a central tool for classifying line operators and phases of gauge theories.

**Modern interpretation.** ’t Hooft loops charged under magnetic one-form symmetries act as generalized order parameters. Their area or perimeter behavior diagnoses whether the relevant magnetic one-form symmetry is unbroken or broken.

**Caveat.** A phrase like “the ’t Hooft loop” is incomplete in a non-Abelian theory. One must specify the magnetic charge, the global form of the gauge group, the allowed line lattice, and any discrete theta data.

**Active.** The organization of Wilson–’t Hooft lines using higher-form symmetries, anomalies, duality defects, and non-invertible structures remains an active part of modern nonperturbative QFT.

## Exercises

### Exercise 1: Linking phase in a center-valued theory

Suppose a minimal Wilson loop $W(C')$ and a minimal ’t Hooft loop $T(C)$ in a $\mathbb Z_N$ center-valued setting obey

$$
T(C)W(C')=e^{2\pi i\operatorname{Lk}(C,C')/N}W(C')T(C).
$$

For which linking numbers do the two operators commute?

<details><summary><strong>Solution</strong></summary>

The operators commute when the phase is one:

$$
e^{2\pi i\operatorname{Lk}(C,C')/N}=1.
$$

This holds when

$$
\operatorname{Lk}(C,C')=0\pmod N.
$$

Thus a single linking gives a nontrivial phase unless $N=1$. The noncommutativity is the line-operator expression of electric–magnetic mutual nonlocality.

</details>

### Exercise 2: Reading a phase table

Assume a theory has genuine Wilson and ’t Hooft loops with the following asymptotic behavior:

$$
\langle W(C)\rangle\sim e^{-\mu P(C)},
\qquad
\langle T(C)\rangle\sim e^{-\widetilde\sigma A(C)}.
$$

Which standard phase does this suggest, and what is the physical interpretation?

<details><summary><strong>Solution</strong></summary>

The Wilson loop has perimeter behavior, so electric probe charges are screened rather than confined by an asymptotic electric flux tube. The ’t Hooft loop has area behavior, so magnetic probes are confined by a magnetic flux tube.

This is the standard Higgs-phase pattern. In the superconductor analogy, electric charge condensation screens electric probes and confines magnetic flux into vortex tubes.

</details>

### Exercise 3: Why magnetic charge lies in a coweight lattice

Let an ’t Hooft loop have magnetic charge $B$ in the Cartan subalgebra. A Wilson line of weight $\lambda$ transported around the Dirac string picks up the phase

$$
e^{2\pi i\lambda(B)}.
$$

Explain why $B$ must obey $\lambda(B)\in\mathbb Z$ for all allowed electric weights $\lambda$ if the Dirac string is to be unobservable.

<details><summary><strong>Solution</strong></summary>

The Dirac string is an auxiliary artifact of the singular gauge-field description. If an allowed electric Wilson line detects the string by a nontrivial phase, then the string is physical, which is not acceptable for a genuine ’t Hooft operator.

Therefore every allowed electric probe must acquire phase one around the string:

$$
e^{2\pi i\lambda(B)}=1.
$$

This requires

$$
\lambda(B)\in\mathbb Z
$$

for every allowed electric weight $\lambda$. The set of $B$ satisfying this integrality condition is the coweight lattice appropriate to the chosen global form and allowed electric line spectrum.

</details>

## References

- G. ’t Hooft, “On the Phase Transition Towards Permanent Quark Confinement,” for the classic Wilson–’t Hooft loop classification of gauge-theory phases.
- A. M. Polyakov, *Gauge Fields and Strings*, for compact gauge theory, disorder variables, confinement, vortices, monopoles, and loop dynamics.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for magnetic one-form symmetries, line-operator lattices, and the modern symmetry interpretation of Wilson and ’t Hooft loops.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for lattice gauge theory, magnetic ’t Hooft loops, duality, visons, and topological phases.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for phases of gauge theories, dual superconductivity, oblique confinement, vortices, monopoles, and higher-form symmetry applications.
- V. Pestun et al., “Localization Techniques in Quantum Field Theories,” for supersymmetric Wilson loops, ’t Hooft loops, and exact localization contexts.

## Version history

- **2026-06-26:** Initial polished draft.
