---
title: "Moduli Spaces Preview"
description: "Introduces continuous families of vacua, flat directions, gauge quotients, zero modes, singular loci, and the low-energy sigma-model viewpoint."
sidebar:
  label: "Moduli Spaces Preview"
  order: 7
level: Graduate
status: "Polished draft"
source: "Weinberg; Shifman; Nakahara; Frankel; Burgess; Fradkin; Altland–Simons."
topics:
  - moduli spaces
  - flat directions
  - vacuum manifolds
  - gauge quotients
  - zero modes
  - sigma models
  - supersymmetric field theory
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - moduli-spaces
  - flat-directions
  - low-energy-effective-theory
researchStatus:
  established:
    - "A moduli space is a continuous space of physically inequivalent vacua; its tangent directions give zero modes and, at low energy, an effective sigma model on the vacuum manifold."
  active:
    - "Quantum moduli spaces, singular loci, dual descriptions, and nonperturbative lifting or deformation of classical flat directions are central active themes, especially in supersymmetric and strongly coupled gauge theories."
---

## Summary

A **moduli space of vacua** is a continuous space of physically inequivalent vacuum states. Locally, a point on the moduli space labels a vacuum, and moving tangent to the moduli space costs no potential energy density:

$$
V_{\rm eff}(m)=V_{\rm vac}
\qquad
\text{for}\qquad
m\in\mathcal M_{\rm vac}.
$$

The coordinates $m^i$ are called **moduli**. Fluctuations along moduli are zero modes; fluctuations normal to the moduli space are typically massive or lifted. At energies small compared with the normal mass gap, the low-energy dynamics is often a nonlinear sigma model with target $\mathcal M_{\rm vac}$:

$$
S_{\rm low}
=\int d^dx\,\frac12\,g_{ij}(m)\,\partial_\mu m^i\partial^\mu m^j+\cdots.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![A smooth moduli space has tangent zero-mode directions, normal massive directions, and possible singular loci where extra fields become light.](/figures/nonperturbative-qft/moduli-space-local-geometry.svg)

<figcaption>

Near a smooth point of $\mathcal M_{\rm vac}$, tangent directions are massless moduli and normal directions are massive or lifted. At singular loci, the low-energy description can change because extra degrees of freedom become light, gauge symmetry is enhanced, or several branches meet.

</figcaption>
</figure>

This page is a preview. A complete treatment of moduli spaces belongs partly to supersymmetry, duality, algebraic geometry, gauge theory, and low-energy effective field theory. The goal here is more modest: give the vocabulary needed to avoid confusing moduli with Goldstone directions, gauge orbits, accidental classical flat directions, or convexity flat segments.

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/), and [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/). It helps to know the basic difference between global symmetries and gauge redundancy.

This page uses the words “manifold,” “quotient,” and “tangent direction” in their practical physics sense. The mathematical toolkit pages on differential geometry and topology will later make these notions more precise.

## Core idea

A moduli space is not just a set of classical minima drawn on a blackboard. In a quantum field theory, it is the space of physically distinct vacua that remain degenerate after the correct quantum definition is used.

A working hierarchy is:

| Object | Meaning | Warning |
|---|---|---|
| Classical flat direction | A direction in classical field space along which $V_{\rm cl}$ is constant. | It may be lifted by quantum effects. |
| Vacuum manifold | A continuous set of classical or quantum vacua. | It may include gauge copies that must be identified. |
| Symmetry orbit | Vacua related by a broken global symmetry, often $G/H$. | These directions are Goldstone directions under standard assumptions. |
| Gauge orbit | Configurations related by gauge redundancy. | These are not distinct physical vacua. Quotient them out. |
| Moduli space | The space of physically inequivalent vacua after constraints and gauge identifications. | It may have singularities, branches, and quantum deformations. |
| Coexistence flat segment | A flat region in the exact convex effective potential caused by phase mixing. | It is usually not a continuum of pure homogeneous vacua. |

The clean slogan is:

$$
\text{moduli are physical zero-energy directions, not redundant gauge directions.}
$$

A second useful slogan is:

$$
\text{a flat classical potential is a candidate moduli space, not a verdict.}
$$

## Setup and conventions

We use the conventions of [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). Suppose a theory has scalar fields $\phi^I$ and a classical potential $V(\phi)$. A classical vacuum set is

$$
\mathcal Z_{\rm cl}
=\left\{\phi_0^I\mid V(\phi_0)=V_{\rm min},\quad
\frac{\partial V}{\partial \phi^I}(\phi_0)=0\right\}.
$$

If the theory has gauge redundancy with gauge group $\mathcal G$, the classical physical vacuum space is not $\mathcal Z_{\rm cl}$ but the quotient

$$
\mathcal M_{\rm cl}=\mathcal Z_{\rm cl}/\mathcal G.
$$

This quotient is schematic. In real gauge theories one often uses gauge-invariant coordinates, moment-map constraints, BRST language, or algebraic quotients rather than literally dividing a set by a group. The point is simple: gauge-equivalent configurations describe the same physical state.

The **quantum** moduli space is the corresponding space after renormalization and nonperturbative effects are included. It may equal the classical quotient, be lifted, be deformed, split into branches, or acquire singular loci where new degrees of freedom are needed.

## Definition

A QFT has a moduli space of vacua $\mathcal M_{\rm vac}$ if there is a continuous family of physically inequivalent pure vacua

$$
\{\Omega_m\}_{m\in\mathcal M_{\rm vac}}
$$

with the same vacuum energy density and with no potential energy cost for slowly varying $m$ at zero momentum.

Equivalently, in a description using gauge-invariant coordinates $\mathcal O_a$, the vacua have expectation values

$$
u_a(m)=\langle\Omega_m|\mathcal O_a|\Omega_m\rangle
$$

satisfying some relations

$$
F_\alpha(u)=0.
$$

The solution space of these relations, with appropriate identifications and singular loci, is the moduli space.

This definition intentionally avoids saying “solutions of $\partial V=0$” as the final answer. Classical equations are useful, but nonperturbative QFT cares about states, sources, gauge-invariant observables, and long-distance dynamics.

## Symmetry orbits versus moduli

The most familiar continuous vacuum spaces come from spontaneous symmetry breaking. If a global internal symmetry $G$ is broken to $H$, then the symmetry-related vacua form

$$
\mathcal M_{\rm sym}\simeq G/H.
$$

For example, an $O(N)$ vector order parameter with

$$
\langle\phi^a\rangle=vn^a,
\qquad n^an^a=1,
$$

has symmetry orbit

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

Under the usual relativistic assumptions, tangent directions along this orbit give Goldstone bosons.

Moduli spaces can include such symmetry orbits, but the term is often used for a broader phenomenon: continuous degeneracies not generated solely by a broken ordinary global symmetry. Supersymmetric theories, for example, often have flat directions constrained by F-term and D-term equations. Their moduli can be charged under global symmetries, but the entire moduli space is not necessarily a single symmetry orbit.

The distinction matters because Goldstone bosons and moduli are protected in different ways.

| Direction | Why it is flat | Typical protection |
|---|---|---|
| Goldstone direction | Exact broken continuous global symmetry. | Ward identities and symmetry realization. |
| Supersymmetric modulus | F-term and D-term flatness, often holomorphy or nonrenormalization. | Supersymmetry and holomorphic constraints. |
| Accidental classical flat direction | Special form of the classical potential. | Usually none; quantum corrections may lift it. |
| Gauge direction | Redundancy of description. | Not physical; quotient it out. |
| Coexistence direction | Mixture of phases in infinite volume. | Thermodynamic convexity, not a pure homogeneous branch. |

Not every massless scalar is a Goldstone boson. Not every flat direction is an exact modulus. Not every coordinate appearing in a Lagrangian labels a physical vacuum. These three non-statements prevent a remarkable amount of pain.

## Local geometry and low-energy fields

At a smooth point $m\in\mathcal M_{\rm vac}$, choose local coordinates $m^i$. A slowly varying field configuration near the vacuum can often be written as

$$
\phi^I(x)=\phi_0^I(m(x))+\eta^A(x)n_A^I(m(x)),
$$

where $\partial_i\phi_0^I$ span tangent directions to the moduli space and $n_A^I$ span normal directions.

The potential is flat along the tangent directions,

$$
\frac{\partial V_{\rm eff}}{\partial m^i}=0,
\qquad
\frac{\partial^2V_{\rm eff}}{\partial m^i\partial m^j}=0,
$$

while normal fluctuations usually have a positive mass matrix,

$$
M_{AB}^2>0.
$$

If the normal modes are heavy compared with the energy scale of interest, they can be integrated out. The leading low-energy action for $m^i(x)$ is then a sigma model,

$$
S_{\rm low}
=\int d^dx\,\left[
\frac12 g_{ij}(m)\partial_\mu m^i\partial^\mu m^j
+\cdots
\right].
$$

The metric $g_{ij}$ is not decorative. It determines scattering of the massless moduli, geodesic motion in adiabatic problems, normalization of zero modes, and the strength of derivative interactions. If the moduli space has nontrivial topology, the low-energy action may also contain theta terms, Wess–Zumino terms, Berry phases, or couplings to background fields.

This is the first hint that “the vacuum manifold” is not just a picture. Its geometry is part of the low-energy physics.

## Gauge quotients

Gauge redundancy is the easiest way to overcount moduli. Consider a complex scalar $\phi$ with potential

$$
V(\phi)=\lambda(|\phi|^2-v^2)^2.
$$

If the $U(1)$ acting on $\phi$ is a **global** symmetry, then the classical vacuum manifold is

$$
|\phi|=v\simeq S^1,
$$

and the phase of $\phi$ is a physical Goldstone direction.

If the same $U(1)$ is a **gauge** redundancy, then points on the circle are gauge-equivalent. The physical quotient is

$$
S^1/U(1)=\text{one point}.
$$

The gauge theory may still have important Higgs physics, massive vector bosons, vortices, and nontrivial line-operator behavior. But the phase of $\phi$ is not a physical modulus.

Gauge-invariant coordinates make this clear. The operator

$$
|\phi|^2
$$

has the same value $v^2$ everywhere on the gauge orbit. It labels one physical vacuum, not a circle of vacua.

In nonabelian gauge theories the quotient can be much richer. Different points can have different unbroken gauge groups, and the quotient can develop singularities where the gauge orbit changes dimension. These singularities are often where extra fields become massless and the naive low-energy sigma model breaks down.

## Branches and singular loci

Moduli spaces are often not single smooth manifolds. They may have branches:

$$
\mathcal M_{\rm vac}
=\mathcal M_1\cup\mathcal M_2\cup\cdots,
$$

with different low-energy descriptions on different components. A point where branches meet can be physically special.

Typical events at singular loci include:

- additional particles becoming massless;
- an unbroken gauge group being enhanced;
- solitons or monopoles becoming light;
- the effective sigma-model metric becoming singular;
- a dual description becoming more natural than the original variables;
- topological sectors changing their low-energy interpretation.

A singularity in coordinates is not automatically a singularity in the theory. Sometimes it only says that the coordinates are bad. Other times it says that the low-energy spectrum really changes. The difference is physical and must be diagnosed by correlation functions, spectra, symmetries, and effective field theory.

## Quantum lifting and quantum deformation

Classical flat directions are fragile unless protected. Quantum effects can generate an effective potential along a classically flat direction:

$$
V_{\rm cl}(m)=0
\qquad\longrightarrow\qquad
V_{\rm eff}(m)\ne0.
$$

This is called **lifting** the moduli. Lifting can happen perturbatively through loop effects or nonperturbatively through instantons, strong dynamics, anomalies, or boundary conditions.

Quantum effects can also **deform** a moduli space without lifting it. Instead of preserving the classical algebraic relation

$$
F(u)=0,
$$

the exact theory may obey

$$
F(u)=\Lambda^b,
$$

where $\Lambda$ is a dynamically generated scale. This schematic form is common in supersymmetric gauge theory, where holomorphy and symmetries strongly constrain quantum corrections.

In nonsupersymmetric QFT, exact moduli spaces are less generic. A flat scalar potential normally requires a symmetry, a fine tuning, or an emergent mechanism. Without protection, the natural expectation is that quantum corrections generate a potential for any scalar not protected by symmetry.

## Infrared subtleties

Moduli produce massless fields. Massless fields produce infrared subtleties. The sharper the statement, the more one must say about dimension, volume, boundary conditions, and the class of observables.

At finite volume, motion along a compact moduli space often becomes quantum mechanics of a zero mode. The exact finite-volume ground state may be spread over the moduli space rather than localized at one point. A localized vacuum is recovered only after the infinite-volume limit, boundary conditions, or small sources select a point.

In low spacetime dimension, long-distance fluctuations can prevent the existence of sharp vacua labeled by a continuous compact order parameter under the usual assumptions. This is the same physics behind the Coleman–Mermin–Wagner warning for continuous symmetry breaking in $1+1$ dimensions. Noncompact moduli bring their own issues: states may fail to be normalizable, and correlation functions can depend sensitively on infrared regulators.

The practical rule is:

$$
\text{a moduli-space approximation is reliable only after checking the infrared.}
$$

That check includes the dimension, the metric on the moduli space, possible compactness, finite-volume effects, and whether additional light fields appear.

## Relation to effective potential and convexity

If a theory has an exact moduli space, the effective potential is flat along it. But this statement is local and coordinate-dependent enough to require care.

For an honest smooth branch of pure vacua, flatness means that a local coordinate $m^i$ labels distinct pure vacua with the same energy density. Slowly varying $m^i(x)$ costs gradient energy but no potential energy.

For a coexistence flat segment in the convex effective potential, the flatness usually has a different meaning. The point in the middle of the segment is a mixed or phase-separated state, not a pure homogeneous vacuum. That is not a moduli space of pure vacua.

The embedding variables can also mislead. A curved moduli space embedded in a larger linear field space may have a convex hull much larger than the actual vacuum manifold. The exact potential as a function of averaged linear fields can flatten over the convex hull, while the pure-vacuum moduli space remains the curved locus itself.

This is why moduli spaces are often described using gauge-invariant coordinates, effective sigma models, or algebraic relations rather than only a plotted potential.

## Common pitfalls

**Confusing gauge orbits with physical moduli.** Gauge-related configurations are the same physical state. Quotient them out or use gauge-invariant coordinates.

**Calling a classical flat direction exact.** A classical flat direction is only a candidate. Quantum corrections can lift or deform it.

**Assuming all moduli are Goldstone bosons.** Goldstone directions are generated by broken global symmetries. Moduli can arise for other reasons, especially in supersymmetric theories.

**Ignoring singular loci.** A smooth sigma model on $\mathcal M_{\rm vac}$ can fail near points where extra fields become light. Singular points often contain the interesting physics.

**Using the potential alone.** The metric, topology, discrete identifications, line operators, defects, and background couplings can all be part of the low-energy physics on a moduli space.

**Mistaking convexity flatness for a moduli space.** A flat segment in the exact convex potential may represent phase coexistence, not continuously many pure vacua.

**Forgetting infrared fluctuations.** In low dimensions or finite volume, massless moduli can prevent the naive picture of sharply selected vacua.

## Relations to other pages

- [Effective Potential and Convexity](/nonperturbative-qft/vacuum-structure-phases/effective-potential-and-convexity/) distinguishes genuine flat directions from coexistence flat regions.
- [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) explains the special case where the vacuum manifold is a symmetry orbit $G/H$.
- [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/) explains why different infinite-volume vacua may not be connected by local finite-energy operations.
- [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) contrasts isolated vacua with continuous vacuum spaces.
- Later chapters on solitons, instantons, gauge theory, large-N methods, and exact models will reuse moduli-space language for zero modes, collective coordinates, and branch structure.

## Research status

The local picture of moduli—flat directions, zero modes, quotient by gauge redundancy, and low-energy sigma-model dynamics—is standard. It is one of the basic languages of solitons, supersymmetric theories, string compactifications, and low-energy effective field theory.

The hard part is determining the exact quantum moduli space in strongly coupled theories. Supersymmetry, holomorphy, anomalies, dualities, localization, and index methods can make this possible in special cases. In nonsupersymmetric theories, exact moduli are rarer and less protected, and apparent flat directions often require careful checks against quantum lifting.

## Exercises

### Exercise 1: Global circle versus gauge circle

Consider a complex scalar with

$$
V(\phi)=\lambda(|\phi|^2-v^2)^2,
\qquad \lambda>0.
$$

First treat the phase rotation $\phi\mapsto e^{i\alpha}\phi$ as a global symmetry. Then treat it as a gauge redundancy. What is the vacuum manifold in each case?

<details>
<summary><strong>Solution</strong></summary>

The classical minima satisfy

$$
|\phi|=v,
$$

so as a set in field space they form a circle $S^1$.

If the $U(1)$ is global, different points on this circle are physically distinct vacua related by spontaneous symmetry breaking. The vacuum manifold is $S^1$, and the phase direction is a Goldstone direction.

If the $U(1)$ is gauged, points on the circle are gauge-equivalent. The physical vacuum space is

$$
S^1/U(1)=\text{one point}.
$$

The phase is not a physical modulus.

</details>

### Exercise 2: A simple lifted flat direction

Suppose a classical theory has two scalar fields and potential

$$
V_{\rm cl}(\phi,\chi)=\frac{\lambda}{4}(\chi^2-v^2)^2,
$$

so $V_{\rm cl}$ is independent of $\phi$. What is the classical vacuum set? What would it mean for quantum corrections to lift the $\phi$ direction?

<details>
<summary><strong>Solution</strong></summary>

The minima satisfy

$$
\chi=\pm v,
$$

while $\phi$ is arbitrary. Thus the classical vacuum set has two branches, each isomorphic to a line:

$$
\mathcal M_{\rm cl}=\mathbb R_\phi\times\{+v,-v\}.
$$

Quantum corrections lift the $\phi$ direction if they generate an effective potential depending on $\phi$, for example

$$
V_{\rm eff}(\phi,\chi=\pm v)=\frac12m_\phi^2\phi^2+\cdots.
$$

Then only the minima of this new potential remain as quantum vacua. The classical flat direction was not an exact moduli space.

</details>

### Exercise 3: Normal and tangent masses

Let a potential near a smooth vacuum branch take the local form

$$
V(m,\eta)=V_0+\frac12M^2\eta^2+O(\eta^3,\eta^2\partial m),
$$

where $m$ is a coordinate along the branch and $\eta$ is a normal coordinate. Identify the massless and massive directions.

<details>
<summary><strong>Solution</strong></summary>

Because $V$ has no dependence on $m$ at $\eta=0$, the tangent direction $m$ is a flat direction. Its potential mass is zero. The normal coordinate $\eta$ has quadratic potential

$$
\frac12M^2\eta^2,
$$

so it is massive when $M^2>0$. At energies much smaller than $M$, the normal mode can be integrated out and the low-energy theory is written in terms of $m(x)$.

</details>

### Exercise 4: Why a convex flat interval is not automatically a moduli space

In a broken $\mathbb Z_2$ theory, the exact convex effective potential is flat for

$$
-v_R\le\bar\phi\le v_R.
$$

Why is this interval not a moduli space of pure homogeneous vacua?

<details>
<summary><strong>Solution</strong></summary>

The endpoints $\bar\phi=\pm v_R$ are the pure broken vacua. A value strictly between them can be obtained in infinite volume by a mixture or phase-separated configuration containing regions of both phases. The wall cost is subextensive, so the energy density is the same, producing a flat convex envelope. But the intermediate points are not new pure homogeneous vacua connected by zero modes. Therefore the flat interval represents coexistence, not a moduli space.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, for spontaneous symmetry breaking, effective potentials, and collective-coordinate intuition.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II for symmetry realization and Vol. III for supersymmetric flat directions and nonperturbative results.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for phases of gauge theories, solitons, supersymmetric gauge dynamics, and strong-coupling examples.
- C. P. Burgess, *Introduction to Effective Field Theory*, for low-energy effective actions and nonlinear realizations.

### Geometry and condensed-matter context

- M. Nakahara, *Geometry, Topology and Physics*, for homotopy, bundles, gauge fields, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*, for manifolds, differential forms, bundles, and gauge-field geometry.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for sigma models, topological terms, spin liquids, gauge descriptions, and topological phases.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for broken symmetry, collective modes, nonlinear sigma models, topology, and gauge-theory examples.

## Version history

- **2026-06-26:** Initial polished draft.
