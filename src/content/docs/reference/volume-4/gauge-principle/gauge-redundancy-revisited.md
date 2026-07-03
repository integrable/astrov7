---
title: "Gauge Redundancy Revisited"
description: "A careful conceptual explanation of why gauge symmetry is redundancy, how gauge equivalence classes define physical configurations, and where global or boundary symmetries enter."
sidebar:
  label: "Gauge Redundancy"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§54–58, 69, 71, 74; Weinberg Vol. II Ch. 15; Coleman, Aspects of Symmetry, Secret Symmetry; Schwartz Chs. 8, 25, 30."
topics:
  - gauge redundancy
  - gauge transformations
  - gauge-invariant observables
  - Gauss law
canonicalTopics:
  - gauge-redundancy
  - gauge-equivalence
  - gauge-invariant-observable
researchStatus:
  established:
    - "The local distinction between gauge redundancy and physical global symmetry is textbook-standard and essential for quantizing gauge theories."
  active:
    - "Boundary symmetries, generalized global symmetries, and global forms of gauge groups are active organizing tools in modern QFT and are only previewed here."
---

## Summary

Gauge symmetry is not an ordinary physical symmetry. It is a redundancy in the variables used to describe a physical configuration.

For a gauge theory with fields collectively denoted by $\Phi$, a gauge transformation $g(x)$ produces another field configuration $\Phi^g$. The central statement is

$$
\Phi\sim \Phi^g,
\qquad
\text{physical configurations}=\{\text{field configurations}\}/\{\text{gauge transformations}\}.
$$

An observable $\mathcal O$ must be well defined on gauge-equivalence classes:

$$
\mathcal O[\Phi^g]=\mathcal O[\Phi]
$$

for gauge transformations that are treated as redundancies. Gauge fixing does not choose a new physics; it chooses coordinates on the space of redundant descriptions.

The subtle caveat is that not every transformation written with the same local formula is necessarily pure redundancy in every physical setting. Transformations with nontrivial behavior at boundaries, at infinity, or in disconnected topological sectors can generate charges, superselection sectors, or genuine global symmetries. The clean rule is: **proper gauge transformations are redundancy; improper, boundary, or topologically nontrivial transformations require separate physical analysis.**

## Prerequisites

You should know the gauge conventions fixed in [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), the basics of Maxwell theory, and the idea of Noether currents and charges from the Foundations of QFT volume. No BRST or Faddeev–Popov quantization is assumed.

## Core idea

A physical symmetry maps a physical state to a different physical state with the same dynamics. A gauge redundancy maps a description to another description of the same physical state.

| Transformation type | What it does | Typical diagnostic |
|---|---|---|
| Ordinary global symmetry | Relates distinct physical states or operators. | Has charges, selection rules, and multiplets. |
| Proper gauge transformation | Changes only the representative of a physical configuration. | Gauge-invariant observables are unchanged. |
| Gauge fixing | Picks one representative per gauge orbit, at least locally. | Intermediate formulas change; physical results do not. |
| Boundary or large transformation | May act physically on sectors or charged operators. | Can carry asymptotic charge, topology, or anomaly data. |

This distinction is not philosophical hair-splitting. It determines which degrees of freedom are physical, what counts as an observable, how the path integral is defined, why ghosts appear, and why the Standard Model is not just a theory with a very large ordinary symmetry group.

## Setup and conventions

We use the conventions of this volume. For an Abelian gauge theory,

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

For a non-Abelian gauge theory,

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
\psi\mapsto U^{-1}\psi,
\qquad
A_\mu\mapsto A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

Let $\mathcal C$ denote the space of field configurations and let $\mathcal G_0$ denote the group of **proper** gauge transformations: transformations that are continuously connected to the identity and obey the boundary conditions required to be treated as redundancy. Then the physical configuration space is locally modeled by the quotient

$$
\mathcal C_{\mathrm{phys}}=\mathcal C/\mathcal G_0.
$$

The word “locally” matters. Global issues such as Gribov copies, topological sectors, and boundary charges mean that this quotient is often more complicated than the slogan suggests.

## Gauge orbits and gauge slices

A gauge orbit is the set of all configurations that describe the same physical configuration:

$$
\operatorname{Orb}(\Phi)=\{\Phi^g\mid g\in\mathcal G_0\}.
$$

The physical configuration is the orbit, not a particular representative on it. Gauge fixing attempts to choose one representative from each orbit by imposing a condition such as

$$
F[A]=0.
$$

Examples include Lorenz gauge $\partial_\mu A^\mu=0$, Coulomb gauge $\nabla\cdot\mathbf A=0$, axial gauges, and background-field gauges. A gauge condition is a coordinate choice on configuration space, not an extra law of nature.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Gauge orbits in configuration space intersected by a gauge-fixing slice.](/figures/gauge-theories-standard-model/gauge-orbits-and-gauge-fixing.svg)

<figcaption>

Gauge-related configurations lie on the same orbit in the redundant configuration space $\mathcal C$. A gauge-fixing condition $F[A]=0$ tries to choose one representative on each orbit, thereby giving local coordinates on the quotient $\mathcal C/\mathcal G_0$.

</figcaption>
</figure>

This picture is deliberately local. In non-Abelian gauge theory, some gauge-fixing conditions intersect a gauge orbit more than once. These extra intersections are called Gribov copies. They are not usually visible in first perturbation theory around $A_\mu=0$, but they become important in nonperturbative discussions of gauge fixing.

## Maxwell theory as the first example

In electromagnetism, the gauge potential is not unique:

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

The field strength is unchanged:

$$
F_{\mu\nu}\mapsto
\partial_\mu(A_\nu+\partial_\nu\alpha)-\partial_\nu(A_\mu+\partial_\mu\alpha)
=F_{\mu\nu}.
$$

Thus the electric and magnetic fields are insensitive to the gauge representative. The same electromagnetic field can be described by infinitely many potentials.

This is not merely a cute fact about Maxwell's equations. In quantum theory, using a manifestly Lorentz-covariant vector potential $A_\mu$ introduces four components, while a massless photon has only two physical helicities. Gauge redundancy is the mechanism that lets us keep locality and Lorentz covariance without turning the unphysical polarizations into observable particles.

A quick one-particle version of the same idea is the polarization shift

$$
\varepsilon_\mu(p)\mapsto \varepsilon_\mu(p)+\lambda p_\mu.
$$

For a conserved current $J^\mu$ with $p_\mu J^\mu=0$, the amplitude contribution from the shifted part vanishes. Longitudinal polarization data are therefore not physical photon data.

## Non-Abelian gauge redundancy

In Yang–Mills theory the field strength is not invariant as a matrix. It transforms covariantly:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

This is exactly what is needed for gauge-invariant local expressions such as

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

to be well defined on gauge orbits. Matter kinetic terms are gauge invariant for the same reason:

$$
\bar\psi i\gamma^\mu D_\mu\psi
\mapsto
\bar\psi U i\gamma^\mu U^{-1}D_\mu\psi
=\bar\psi i\gamma^\mu D_\mu\psi,
$$

because $U$ acts on internal indices and commutes with the gamma matrices.

The non-Abelian potential itself is not observable. Even the components $A_\mu^a$ are basis-dependent coordinates in field space. Gauge-invariant information is carried by objects such as local traces of curvature, Wilson loops, correlation functions of gauge-invariant operators, and appropriately dressed or boundary-defined charged operators.

## What is observable?

The slogan “observables must be gauge invariant” is correct but needs interpretation.

For local gauge-invariant operators, the rule is straightforward. In pure Yang–Mills theory, examples include

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}),
\qquad
\operatorname{tr}(F_{\mu\nu}\widetilde F^{\mu\nu}),
$$

where

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

For extended operators, the most important example is the Wilson loop

$$
W_R(C)=\operatorname{tr}_R\,\mathcal P\exp\left(-ig\oint_C A_\mu dx^\mu\right),
$$

with the sign chosen to match $D_\mu=\partial_\mu+igA_\mu$. Under a gauge transformation, the parallel transporter along an open path transforms at its endpoints. The trace around a closed loop cancels the endpoint factors and gives a gauge-invariant operator.

For charged fields the statement is subtler. The electron field $\psi_e(x)$ is not gauge invariant by itself, but QED certainly has charged states. The resolution is that a physical charged excitation includes its electromagnetic field and is tied to boundary flux data. In a compact space without boundary, Gauss law forces the total gauge charge to vanish. In an asymptotically flat setting, electric charge is measured at infinity.

This is why “not gauge invariant” does not mean “useless.” Gauge-variant fields are often the most efficient variables for calculations. They simply are not, by themselves, physical observables.

## Gauge fixing and Gauss law

In the path integral, integrating over all gauge potentials naively counts every physical configuration infinitely many times, once for every point on its gauge orbit. Gauge fixing removes this overcounting locally by imposing a condition such as $F[A]=0$ and including the corresponding Faddeev–Popov determinant.

In canonical language, the same structure appears as a constraint. In electrodynamics, Gauss law is

$$
\nabla\cdot\mathbf E-\rho=0.
$$

In Yang–Mills theory the schematic form is

$$
G^a(x)=(D_iE^i)^a-\rho^a\approx 0,
$$

where $G^a(x)$ generates infinitesimal proper gauge transformations. Physical states satisfy

$$
G^a(x)|\mathrm{phys}\rangle=0
$$

for transformations treated as redundancy.

This is one of the cleanest ways to see that gauge symmetry is not an optional symmetry assumption. It is a constraint on the physical Hilbert space. Gauge fixing chooses a way to solve or manage the constraint; it does not remove the need for the constraint.

## Local, global, large, and boundary transformations

The phrase “gauge transformation” hides an important boundary convention. Transformations that vanish sufficiently fast at the boundary, or are trivial at infinity, are normally treated as redundancy. Transformations that do not vanish at the boundary can act nontrivially on the physical Hilbert space.

For example, in electrodynamics, the total electric charge can be written as a boundary flux:

$$
Q_{\mathrm{electric}}=\int_\Sigma d^3x\,\rho
=\oint_{\partial\Sigma} dS_i\,E^i.
$$

A transformation with nonzero limiting value at infinity is related to the global electric charge. It is not erased in the same way as a compactly supported gauge wiggle.

There are also large gauge transformations not continuously connected to the identity. These can label topological sectors, affect theta angles, or act nontrivially on line operators. Later pages on Wilson loops, global form, center symmetry, anomalies, and instantons refine this basic statement.

A safe working dictionary is therefore:

| Transformation | Usually treated as | Physical role |
|---|---|---|
| Infinitesimal gauge transformation with compact support | Redundancy | Generated by local constraints. |
| Gauge transformation trivial at the boundary | Redundancy | Does not change physical charges. |
| Transformation with nontrivial boundary value | Possible physical symmetry | Can measure or generate asymptotic charges. |
| Large transformation | Topological operation | Can affect sectors, theta vacua, or line operators. |

This nuance matters especially in modern QFT, where generalized global symmetries and boundary symmetries often reveal physical structure invisible in the local Lagrangian alone.

## The Standard Model viewpoint

The Standard Model gauge group is not a giant ordinary symmetry group acting on an oversized multiplet of particles. It is a redundancy structure that dictates which local interactions are allowed, which degrees of freedom are physical, and which quantum theories are consistent.

This viewpoint clarifies several otherwise puzzling facts.

First, the electroweak gauge bosons are introduced as gauge fields, but only after symmetry breaking do the familiar photon, $W^\pm$, and $Z$ variables become the most useful particle variables.

Second, the Higgs mechanism does not literally break a gauge redundancy as if it were an ordinary global symmetry. Gauge-invariant statements are instead about the spectrum, the realization of the theory, and the screening of charges. The slogan “the gauge symmetry is broken” is useful shorthand only after a gauge choice has made it look that way.

Third, anomaly cancellation is not optional. A gauge anomaly would make the redundancy inconsistent in the quantum theory, destroying the ability to define a physical Hilbert space or a gauge-independent path integral. This is why the pattern of Standard Model fermion representations is a consistency condition, not just a decorative classification.

## Checks and examples

The fastest tests of gauge redundancy are simple.

**Abelian field strength.** If $A_\mu\mapsto A_\mu+\partial_\mu\alpha$, then $F_{\mu\nu}$ is unchanged because mixed partial derivatives commute.

**Pure gauge potentials.** In Abelian theory, $A_\mu=\partial_\mu\alpha$ has $F_{\mu\nu}=0$. In non-Abelian theory, a transformed zero potential

$$
A_\mu=-\frac{i}{g}U^{-1}\partial_\mu U
$$

also has $F_{\mu\nu}=0$ locally.

**Mass terms.** A Proca mass term $\frac12m^2A_\mu A^\mu$ is not invariant under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$. A gauge-boson mass in a consistent gauge theory must therefore arise through a gauge-invariant mechanism, such as the Higgs mechanism, or through an effective description with a carefully stated domain of validity.

**Closed Wilson loops.** The parallel transporter along an open curve transforms at its endpoints. Taking a trace around a closed curve removes the endpoint dependence and produces a gauge-invariant extended operator.

## Common pitfalls

**Saying gauge symmetry is “just a symmetry.”** A physical symmetry relates distinct physical states. A proper gauge transformation relates two descriptions of the same physical state.

**Thinking gauge fixing changes the theory.** Gauge fixing changes the coordinates used in the calculation. Correctly defined gauge-invariant observables do not depend on the gauge parameter or the chosen slice.

**Forgetting boundary transformations.** Transformations that look like gauge transformations locally can carry physical charges at boundaries or infinity. The boundary conditions are part of the definition of the physical problem.

**Treating gauge-variant fields as meaningless.** Gauge-variant fields are not observables by themselves, but they are indispensable variables. The point is not to ban them; the point is to know what must cancel or be dressed before a physical question is answered.

**Saying the Higgs mechanism breaks a redundancy.** A redundancy cannot be physically broken in the same sense as a global symmetry. In a fixed gauge, the Higgs mechanism may look like symmetry breaking; gauge-invariantly, it reorganizes the spectrum and screens gauge charges.

## Relations to other pages

- [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/) fixes the transformation laws and sign conventions used in this page.
- [Conventions and Normalizations](/foundations/conventions-and-normalizations/) gives the site-wide metric, spinor, Fourier, path-integral, and propagator conventions assumed here.

## Research status

The local statement that proper gauge transformations are redundancy is settled textbook material. It underlies canonical constraints, path-integral gauge fixing, BRST quantization, and the construction of the Standard Model.

The boundary and global refinements are active and important in modern QFT. Higher-form symmetries, non-invertible symmetries, global forms of gauge groups, edge modes, and anomaly inflow all sharpen the question “which transformations are redundancy and which are physical?” This page gives the local foundation; later pages develop those refinements.

## Exercises

### Exercise 1: Field strength is gauge invariant in QED

Show that the Abelian field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is unchanged by $A_\mu\mapsto A_\mu+\partial_\mu\alpha$.

<details>
<summary><strong>Solution</strong></summary>

Under the transformation,

$$
F_{\mu\nu}\mapsto
\partial_\mu(A_\nu+\partial_\nu\alpha)-\partial_\nu(A_\mu+\partial_\mu\alpha).
$$

The extra terms are

$$
\partial_\mu\partial_\nu\alpha-\partial_\nu\partial_\mu\alpha=0
$$

for a smooth gauge parameter. Therefore $F_{\mu\nu}$ is unchanged.

</details>

### Exercise 2: A Proca mass term is not gauge invariant

Consider

$$
\mathcal L_m=\frac12m^2A_\mu A^\mu.
$$

Show that it is not invariant under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ for a general local $\alpha(x)$.

<details>
<summary><strong>Solution</strong></summary>

The transformed term is

$$
\frac12m^2(A_\mu+\partial_\mu\alpha)(A^\mu+\partial^\mu\alpha).
$$

Expanding gives

$$
\mathcal L_m\mapsto \mathcal L_m
+m^2A^\mu\partial_\mu\alpha
+\frac12m^2\partial_\mu\alpha\partial^\mu\alpha.
$$

The last two terms do not vanish for a general local $\alpha(x)$. Thus a bare vector mass term is incompatible with this gauge redundancy.

</details>

### Exercise 3: Endpoint transformation of a Wilson line

Let

$$
U_C(y,x)=\mathcal P\exp\left(-ig\int_x^y A_\mu dz^\mu\right)
$$

be the parallel transporter along a curve $C$ from $x$ to $y$. Using the transformation law of $A_\mu$, show that

$$
U_C(y,x)\mapsto G^{-1}(y)U_C(y,x)G(x).
$$

Explain why $\operatorname{tr}U_C(x,x)$ is gauge invariant for a closed curve.

<details>
<summary><strong>Solution</strong></summary>

The Wilson line is defined as the solution to parallel transport along the curve. The transformed connection is precisely what is needed so that a transported matter vector transforms covariantly at every point. This gives

$$
U_C(y,x)\mapsto G^{-1}(y)U_C(y,x)G(x).
$$

For a closed curve, $x=y$, so

$$
U_C(x,x)\mapsto G^{-1}(x)U_C(x,x)G(x).
$$

Taking the trace removes the conjugation:

$$
\operatorname{tr}\bigl(G^{-1}U_CG\bigr)=\operatorname{tr}U_C.
$$

Therefore the traced Wilson loop is gauge invariant.

</details>

### Exercise 4: Gauge orbit versus physical point

Let $\mathcal C$ be the space of Abelian gauge potentials on a contractible spacetime region. Show that all potentials of the form $A_\mu=\partial_\mu\alpha$ lie on the same gauge orbit as $A_\mu=0$. What is their field strength?

<details>
<summary><strong>Solution</strong></summary>

Starting from $A_\mu=0$ and performing the gauge transformation with parameter $\alpha$ gives

$$
A_\mu'=0+\partial_\mu\alpha.
$$

Thus $A_\mu=\partial_\mu\alpha$ is gauge-equivalent to zero. Its field strength is

$$
F_{\mu\nu}=\partial_\mu\partial_\nu\alpha-\partial_\nu\partial_\mu\alpha=0
$$

for smooth $\alpha$. Locally, it is a pure gauge configuration.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, sections on Maxwell theory, path integrals for photons, non-Abelian gauge theory, BRST symmetry, and chiral gauge theories.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on gauge invariance, Yang–Mills theory, spontaneous symmetry breaking, and anomalies.
- S. Coleman, *Aspects of Symmetry*, “Secret Symmetry: An Introduction to Spontaneous Symmetry Breakdown and Gauge Fields.”

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, Chapter 15 on non-Abelian gauge theories.
- A. M. Polyakov, *Gauge Fields and Strings*, chapters on local symmetries, gauge systems, Wilson loops, and confinement-oriented reasoning.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern distinction between gauge presentations and intrinsic global symmetry data.

## Version history

- **2026-06-17:** Initial polished draft for the Gauge Principle and Classical Gauge Theory chapter.
