---
title: "Entanglement and the Ryu-Takayanagi Formula"
description: "How boundary entanglement entropy is computed by bulk extremal surfaces, including RT, HRT, quantum corrections, generalized entropy, entanglement wedges, and CFT consistency checks."
sidebar:
  label: "Entanglement and RT"
  order: 8
level: Advanced
status: "Polished draft"
source: "Ryu and Takayanagi; Hubeny, Rangamani, and Takayanagi; Lewkowycz and Maldacena; Faulkner, Lewkowycz, and Maldacena; Engelhardt and Wall; holographic entanglement literature."
topics:
  - holographic entanglement entropy
  - Ryu-Takayanagi formula
  - entanglement wedge
  - AdS/CFT
  - quantum extremal surfaces
canonicalTopics:
  - entanglement-and-rt
  - holographic-entanglement-entropy
  - ryu-takayanagi-formula
researchStatus:
  established:
    - "The Ryu-Takayanagi and Hubeny-Rangamani-Takayanagi prescriptions compute leading holographic entanglement entropy from bulk extremal surface areas, with quantum corrections given by generalized entropy."
  active:
    - "Current research studies quantum extremal surfaces, islands, entanglement wedge reconstruction, finite-N corrections, modular flow, black-hole information, and bootstrap constraints from entanglement."
---

## Summary

The **Ryu-Takayanagi formula** is one of the most striking entries in the holographic dictionary. It says that the entanglement entropy of a boundary region $A$ is computed by the area of a bulk surface:

$$
S_A=\frac{\operatorname{Area}(\gamma_A)}{4G_N}
$$

at leading classical order.

Here $\gamma_A$ is a codimension-two minimal surface in a static bulk geometry, anchored on the boundary of $A$:

$$
\partial \gamma_A=\partial A.
$$

For time-dependent geometries, the surface is extremal rather than simply minimal. This covariant version is the Hubeny-Rangamani-Takayanagi prescription.

Quantum corrections replace area alone by **generalized entropy**:

$$
S_A=\underset{X\sim A}{\operatorname{ext}}\left[
\frac{\operatorname{Area}(X)}{4G_N}+S_{\rm bulk}(\Sigma_X)+\cdots
\right].
$$

The slogan is

$$
\text{boundary entanglement builds bulk geometry}.
$$

This page explains the RT formula, its quantum corrections, and why entanglement is central to modern holography.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/), and [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/) first.

You should know density matrices, von Neumann entropy, path integrals, boundary regions, basic AdS geometry, and the large-$N$ expansion. For QFT background on entanglement entropy, see free-field and thermal-Lorentzian QFT pages when available.

## Entanglement entropy in QFT

Given a quantum state $|\Psi\rangle$ and a spatial region $A$, the reduced density matrix is

$$
\rho_A=\operatorname{Tr}_{\bar A}|\Psi\rangle\langle\Psi|.
$$

The entanglement entropy is

$$
S_A=-\operatorname{Tr}\rho_A\log\rho_A.
$$

In continuum QFT, this entropy is UV divergent because modes near the entangling surface are strongly entangled. The leading divergence often follows an area law:

$$
S_A\sim \frac{\operatorname{Area}(\partial A)}{\epsilon^{d-2}}+\cdots,
$$

where $\epsilon$ is a UV cutoff.

Holography geometrizes this area law. The boundary divergence is reproduced by the fact that the RT surface extends to the AdS boundary, where its area diverges.

This matching is not decorative. It is one of the first signs that the radial direction of AdS encodes scale.

## The static RT formula

For a static holographic state with a time-reflection-symmetric bulk slice, the RT prescription says:

$$
S_A=\frac{\operatorname{Area}(\gamma_A)}{4G_N}.
$$

The surface $\gamma_A$ must satisfy three conditions.

| Condition | Meaning |
|---|---|
| anchored | $\partial\gamma_A=\partial A$ |
| homologous | there is a bulk region $\Sigma_A$ with $\partial\Sigma_A=A\cup\gamma_A$ |
| minimal | among allowed surfaces, choose the one with smallest area |

The homology condition matters. It tells the surface which boundary region it belongs to and becomes crucial for black holes and disconnected regions.

The formula looks like black-hole entropy:

$$
S_{\rm BH}=\frac{\operatorname{Area}}{4G_N}.
$$

RT says black-hole area entropy was only the most dramatic member of a larger family: areas of bulk surfaces compute boundary entanglement.

## Covariant HRT formula

For time-dependent states, there may be no preferred static slice. The covariant prescription replaces the minimal surface by an extremal surface:

$$
S_A=\frac{\operatorname{Area}(X_A)}{4G_N},
$$

where $X_A$ is codimension two, anchored on $\partial A$, homologous to $A$, and extremal in the Lorentzian bulk geometry.

Extremal means first variation of area vanishes:

$$
\delta\operatorname{Area}(X_A)=0.
$$

One then chooses the appropriate extremal surface with minimal generalized entropy when multiple candidates exist.

This is the Hubeny-Rangamani-Takayanagi formula. It is essential for quenches, collapsing geometries, black-hole evaporation models, and time-dependent entanglement dynamics.

The static RT formula is the peaceful pond. HRT is the same fish during a thunderstorm.

## Quantum corrections

At finite $N$, the bulk is quantum. The leading classical area term is not enough. The first quantum correction includes the bulk entanglement entropy across the RT surface:

$$
S_A=\frac{\operatorname{Area}(\gamma_A)}{4G_N}+S_{\rm bulk}(\Sigma_A)+\cdots .
$$

More generally, one extremizes the **generalized entropy**:

$$
S_{\rm gen}(X)=\frac{\operatorname{Area}(X)}{4G_N}+S_{\rm bulk}(\Sigma_X)+S_{\rm counterterms}+\cdots .
$$

The relevant surface is a **quantum extremal surface**:

$$
\delta S_{\rm gen}(X)=0.
$$

This refinement is crucial for black-hole information and island formulas. It says that the surface itself shifts when bulk quantum entanglement is included.

The hierarchy is:

| Regime | Formula |
|---|---|
| classical static | RT minimal area |
| classical time-dependent | HRT extremal area |
| semiclassical quantum bulk | quantum extremal generalized entropy |
| evaporating black holes | islands from competing quantum extremal surfaces |

## Entanglement wedge

Given a boundary region $A$ and its RT or HRT surface $X_A$, the **entanglement wedge** is the bulk domain of dependence of a region bounded by

$$
A\cup X_A.
$$

Roughly, it is the bulk region encoded by the boundary density matrix $\rho_A$.

The dictionary is:

$$
\rho_A
\quad\Longleftrightarrow\quad
\text{bulk physics in the entanglement wedge of }A.
$$

This is one of the bridges from geometry to quantum information. It leads to entanglement wedge reconstruction: bulk operators inside the wedge can be represented on boundary region $A$, at least within an appropriate code subspace.

This topic becomes central on the next quantum-error-correction page. For now, the key point is that RT surfaces do more than compute a number. They divide the bulk into reconstructible regions.

## Entanglement first law

For a density matrix perturbation around a reference state, the first law of entanglement says

$$
\delta S_A=\delta\langle K_A\rangle,
$$

where the modular Hamiltonian $K_A$ is defined by

$$
\rho_A=\frac{e^{-K_A}}{\operatorname{Tr}e^{-K_A}}.
$$

In holography, applying the entanglement first law to ball-shaped regions in the CFT vacuum leads to the linearized Einstein equations in the bulk.

The rough chain is

$$
\delta S_A=\delta\langle K_A\rangle
\quad\Longleftrightarrow\quad
\text{linearized gravitational constraints in AdS}.
$$

This is one of the sharpest versions of the idea that spacetime dynamics emerge from entanglement consistency.

It is not just that geometry computes entropy. Entanglement identities constrain the geometry's equations of motion.

## Example: interval in AdS3/CFT2

In a two-dimensional holographic CFT vacuum, the entanglement entropy of an interval of length $L$ is

$$
S_A=\frac{c}{3}\log\frac{L}{\epsilon}.
$$

In AdS$_3$, the RT surface is a geodesic connecting the endpoints of the interval. Its regulated length gives

$$
S_A=\frac{\operatorname{Length}(\gamma_A)}{4G_N^{(3)}}.
$$

Using the Brown-Henneaux relation

$$
 c\sim \frac{R_{\rm AdS}}{G_N^{(3)}},
$$

one recovers the CFT logarithm.

This example is the cleanest classroom version of the formula. Boundary logarithmic entanglement becomes a geodesic length in hyperbolic space.

## Phase transitions of RT surfaces

When the boundary region has multiple components, there can be several candidate RT surfaces. The correct one is the surface with smallest area among homologous candidates.

For two separated boundary regions $A$ and $B$, the entropy of $A\cup B$ may be computed either by disconnected surfaces or by a connected configuration. As the separation changes, the preferred surface can jump.

This produces a sharp transition in the leading large-$N$ mutual information:

$$
I(A:B)=S_A+S_B-S_{A\cup B}.
$$

At leading classical order, the mutual information can vanish over a range of separations. At subleading order, bulk fields can produce nonzero corrections.

These RT phase transitions are geometric shadows of large-$N$ factorization and competing OPE channels.

## Entropy inequalities

Entanglement entropy obeys general inequalities such as subadditivity and strong subadditivity:

$$
S_A+S_B\ge S_{A\cup B},
$$

and

$$
S_{AB}+S_{BC}\ge S_B+S_{ABC}.
$$

The RT formula gives geometric proofs of some of these inequalities in holographic states. Because areas can be cut and recombined, entropy inequalities become geometric inequalities.

Holographic entropies also obey additional constraints not satisfied by arbitrary quantum states, such as monogamy of mutual information at leading classical order:

$$
I(A:B)+I(A:C)\le I(A:BC).
$$

This means classical holographic states form a special subset of all quantum states. Geometry is picky. Delightfully picky, but picky.

## Modular Hamiltonians

The modular Hamiltonian $K_A$ is usually nonlocal and hard to write. A major exception is a ball-shaped region in the CFT vacuum. By a conformal transformation, its reduced density matrix is related to a thermal state on hyperbolic space.

This makes $K_A$ local and expressible as an integral of the stress tensor:

$$
K_A=\int_A d^{d-1}x\,f_A(x)T_{00}(x)
$$

for a known weight $f_A(x)$.

This special case is central because it lets one relate entanglement variations to stress-tensor expectation values and bulk gravitational equations.

For generic regions and states, modular Hamiltonians are much harder. That difficulty is not a bug; it is the entire quantum-information dragon guarding the cave.

## Replica trick and cosmic branes

Entanglement entropy can be computed from Renyi entropies:

$$
S_n(A)=\frac{1}{1-n}\log\operatorname{Tr}\rho_A^n,
$$

then analytically continued to

$$
S_A=\lim_{n\to1}S_n(A).
$$

In holography, the replica trick leads to bulk geometries with replica symmetry. The fixed locus of the replica symmetry becomes a cosmic brane. Taking the limit $n\to1$ produces the RT surface.

This gives a derivation of the RT formula from gravitational path integrals. It also explains why the area term appears with coefficient

$$
\frac{1}{4G_N}.
$$

The replica derivation is subtle, but conceptually powerful: the extremal surface emerges from demanding smoothness and consistency of replicated bulk geometries.

## Islands and black-hole information

Quantum extremal surfaces can produce **islands**: bulk regions disconnected from the naive boundary region but included in the entanglement wedge.

In black-hole evaporation models, the entropy of Hawking radiation is computed by extremizing generalized entropy over candidate surfaces. At early times, the no-island saddle dominates. At late times, an island saddle can dominate, producing a Page curve compatible with unitarity.

This is a major modern development, but it deserves its own later page. Here the key point is that islands are not a separate rule. They are a consequence of the quantum extremal surface prescription applied carefully.

The RT formula grew up, went to quantum gravity school, and came back carrying islands.

## Common pitfalls

**Do not say RT computes all entropy.** It computes spatial entanglement entropy in holographic states under specific assumptions, with refinements for time dependence and quantum corrections.

**Do not forget UV divergences.** Boundary entanglement entropy and bulk surface area are both divergent and require matching regulators.

**Do not omit the homology condition.** It is essential for black holes, mixed states, and disconnected regions.

**Do not use minimal surfaces in time-dependent spacetimes.** Use extremal HRT surfaces.

**Do not treat the area term as exact at finite $N$.** Bulk entropy and quantum extremal surfaces matter.

**Do not confuse the entanglement wedge with the causal wedge.** They are related but generally different.

**Do not assume every quantum state has a smooth geometric entropy picture.** Classical RT geometry is special to holographic large-$N$ states.

## Relations to other pages

This page follows [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/) and prepares [Quantum Error Correction and Entanglement Wedges](/cft-bootstrap/holographic-cft/quantum-error-correction-and-entanglement-wedges/) and [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/).

It connects back to [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), and [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/).

For QFT entanglement methods outside holography, see [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) and later entanglement pages when expanded.

## Research status

The RT and HRT prescriptions are established central results in holography. Quantum corrections through bulk entropy, generalized entropy, and quantum extremal surfaces are also standard in modern semiclassical holography.

Active research studies islands, black-hole information, entanglement wedge reconstruction, modular flow, finite-$N$ corrections, bulk locality from entanglement, tensor-network models, and constraints on which quantum states can have semiclassical geometric duals.

## Exercises

### Exercise 1

State the RT formula for a static holographic state.

<details><summary><strong>Solution</strong></summary>

For a boundary region $A$, the RT formula is

$$
S_A=\frac{\operatorname{Area}(\gamma_A)}{4G_N},
$$

where $\gamma_A$ is the minimal codimension-two bulk surface anchored on $\partial A$ and homologous to $A$.

</details>

### Exercise 2

What changes in the covariant HRT prescription?

<details><summary><strong>Solution</strong></summary>

In time-dependent geometries, the surface is not restricted to a static time slice. One uses a codimension-two extremal surface $X_A$ anchored on $\partial A$ and homologous to $A$:

$$
S_A=\frac{\operatorname{Area}(X_A)}{4G_N}.
$$

The surface extremizes area in the Lorentzian bulk.

</details>

### Exercise 3

What is the generalized entropy of a candidate quantum extremal surface?

<details><summary><strong>Solution</strong></summary>

The generalized entropy is

$$
S_{\rm gen}(X)=\frac{\operatorname{Area}(X)}{4G_N}+S_{\rm bulk}(\Sigma_X)+S_{\rm counterterms}+\cdots .
$$

A quantum extremal surface extremizes $S_{\rm gen}$ rather than area alone.

</details>

### Exercise 4

Why is the homology condition important?

<details><summary><strong>Solution</strong></summary>

The homology condition requires that the RT or HRT surface and the boundary region $A$ together bound a bulk region. This assigns the surface to the correct boundary subsystem and is essential in black-hole geometries, mixed states, and disconnected regions.

</details>

### Exercise 5

What is the entanglement wedge of a boundary region?

<details><summary><strong>Solution</strong></summary>

The entanglement wedge of $A$ is the bulk domain of dependence of the region bounded by $A$ and its RT/HRT or quantum extremal surface. It is the bulk region encoded by the boundary density matrix $\rho_A$ within the appropriate holographic regime.

</details>

## References

- S. Ryu and T. Takayanagi, “Holographic derivation of entanglement entropy from AdS/CFT,” *Physical Review Letters* **96** (2006).
- V. E. Hubeny, M. Rangamani, and T. Takayanagi, “A covariant holographic entanglement entropy proposal,” *Journal of High Energy Physics* **2007**.
- A. Lewkowycz and J. Maldacena, “Generalized gravitational entropy,” *Journal of High Energy Physics* **2013**.
- T. Faulkner, A. Lewkowycz, and J. Maldacena, “Quantum corrections to holographic entanglement entropy,” *Journal of High Energy Physics* **2013**.
- N. Engelhardt and A. C. Wall, “Quantum extremal surfaces: Holographic entanglement entropy beyond the classical regime,” *Journal of High Energy Physics* **2015**.
- M. Van Raamsdonk, “Building up spacetime with quantum entanglement,” *General Relativity and Gravitation* **42** (2010).
- A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, “The entropy of bulk quantum fields and the entanglement wedge of an evaporating black hole,” *Journal of High Energy Physics* **2019**.

## Version history

- 2026-07-01: First polished draft. Added RT and HRT prescriptions, quantum corrections, generalized entropy, entanglement wedge, entanglement first law, AdS3 interval example, RT phase transitions, entropy inequalities, modular Hamiltonians, replica/cosmic-brane derivation, island preview, exercises, and references.
