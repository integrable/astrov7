---
title: "Quantum Error Correction and Entanglement Wedges"
description: "How holographic bulk reconstruction is organized by quantum error correction, code subspaces, entanglement wedges, complementary recovery, and operator-algebra quantum error correction."
sidebar:
  label: "Quantum Error Correction and Entanglement Wedges"
  order: 10
level: Advanced
status: "Polished draft"
source: "Almheiri, Dong, and Harlow; Harlow; Jafferis, Lewkowycz, Maldacena, and Suh; Dong, Harlow, and Wall; quantum error correction and entanglement wedge reconstruction literature."
topics:
  - quantum error correction
  - entanglement wedge
  - holographic CFT
  - bulk reconstruction
  - AdS/CFT
canonicalTopics:
  - quantum-error-correction-and-entanglement-wedges
  - holographic-qec
  - entanglement-wedge-reconstruction
researchStatus:
  established:
    - "Bulk reconstruction in holographic CFT is naturally described by quantum error-correcting codes, with boundary subregions reconstructing operators in their entanglement wedges."
    - "JLMS-type relations and operator-algebra quantum error correction connect boundary relative entropy to bulk relative entropy plus area terms."
  active:
    - "Current research studies reconstruction behind horizons, islands, finite-N corrections, approximate codes, modular flow, operator algebras, tensor networks, and the emergence of spacetime from quantum information."
---

## Summary

Holography has a strange feature: the same bulk operator can often be represented on many different boundary regions. This redundancy is not a bug. It is the signature of **quantum error correction**.

The modern slogan is

$$
\text{AdS/CFT is a quantum error-correcting code}.
$$

A low-energy bulk effective theory is encoded in the exact boundary CFT in a redundant way. Boundary subregions can reconstruct bulk operators in their **entanglement wedges**. If part of the boundary is erased, some bulk information can still be recovered from the remaining region.

The basic dictionary is:

| Quantum-information idea | Holographic meaning |
|---|---|
| logical Hilbert space | bulk code subspace |
| physical Hilbert space | boundary CFT Hilbert space |
| logical operator | bulk operator in EFT |
| physical representation | boundary operator representing it |
| erasure correction | recovery from a boundary subregion |
| correctable region | bulk region outside the relevant entanglement wedge |
| complementary recovery | different boundary regions reconstruct complementary bulk algebras |
| center of algebra | area operator or edge-mode-like data |

This page explains code subspaces, entanglement wedge reconstruction, why RT surfaces mark reconstruction boundaries, and how quantum error correction clarifies bulk locality.

## Prerequisites

Read [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) and [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/) first.

You should know density matrices, entanglement entropy, RT/HRT surfaces, generalized entropy, large-$N$ bulk EFT, and the basic AdS/CFT dictionary.

## Core idea

The exact CFT Hilbert space is the fundamental description. A semiclassical bulk description is valid only in a restricted set of states, called a **code subspace**:

$$
\mathcal H_{\rm code}\subset \mathcal H_{\rm CFT}.
$$

Inside this code subspace, bulk effective field theory makes sense. Bulk operators act as logical operators on $\mathcal H_{\rm code}$. Their boundary representations are physical operators on the CFT Hilbert space.

The same logical bulk operator may have multiple boundary representations:

$$
\phi_{\rm bulk}(x)
\quad\leftrightarrow\quad
\mathcal O_A
\quad\leftrightarrow\quad
\mathcal O_B
\quad\leftrightarrow\quad
\mathcal O_{\rm full}.
$$

These representations agree only within the code subspace. Outside it, they need not be the same operator.

That is exactly how quantum error-correcting codes work.

## Why redundancy is necessary

In ordinary local field theory, an operator at a point belongs to a definite spatial region. In gravity, this is more subtle because diffeomorphism-invariant observables must be gravitationally dressed. A bulk operator is not sharply local in a gauge-invariant microscopic sense.

Holography adds another twist: the bulk has one more spatial dimension than the boundary. A single bulk region can be encoded nonlocally across boundary degrees of freedom.

This makes redundancy natural. If a central bulk operator can be reconstructed from different boundary regions, then no one boundary site or small region literally contains it by itself.

The redundancy protects bulk information against erasure:

$$
\text{lose some boundary degrees of freedom}
\quad\not\Rightarrow\quad
\text{lose all bulk information}.
$$

Bulk locality is therefore an emergent, protected property of an encoded subspace.

## Entanglement wedge reconstruction

Given a boundary region $A$, its entanglement wedge is the bulk domain of dependence of a region bounded by $A$ and its RT/HRT or quantum extremal surface.

The reconstruction claim is:

$$
\text{bulk operators in }EW(A)
\quad\text{can be represented on boundary region }A.
$$

Here $EW(A)$ denotes the entanglement wedge of $A$.

This is stronger than causal wedge reconstruction. The causal wedge is the bulk region that can send signals to and receive signals from $A$. The entanglement wedge can be larger.

Thus the RT surface is not merely an entropy-computing surface. It is also a boundary of reconstructability.

## Code subspaces

A code subspace is the set of CFT states that share a semiclassical bulk background plus a controlled number of low-energy excitations:

$$
\mathcal H_{\rm code}
=\operatorname{span}\{\text{low-energy bulk excitations around one background}\}.
$$

The code subspace should be small compared with the full CFT Hilbert space. If one includes too many states, especially black-hole microstates with wildly different geometries, a single semiclassical bulk EFT may no longer apply.

Within a code subspace, one can talk about approximate local bulk fields, entanglement wedges, and reconstruction maps. The approximation improves at large $N$ and large gap.

The phrase “bulk operator” almost always secretly means:

$$
\text{bulk operator acting within a chosen code subspace}.
$$

Forgetting this is how one accidentally asks the boundary CFT to perform illegal magic.

## Erasure correction

Quantum error correction often studies erasure: some known subset of physical degrees of freedom is lost. The code corrects the erasure if the logical information can still be recovered from the remaining degrees of freedom.

In holography, suppose the boundary is split into $A$ and its complement $\bar A$. If a bulk operator lies in the entanglement wedge of $A$, then it can be reconstructed on $A$.

Equivalently, losing $\bar A$ does not destroy that operator's logical information.

The reconstruction condition is geometric:

$$
\phi(x)\in EW(A)
\quad\Rightarrow\quad
\exists\,\mathcal O_A\text{ acting only on }A
\text{ such that }\mathcal O_A\simeq\phi(x)
\text{ on }\mathcal H_{\rm code}.
$$

The symbol $\simeq$ means equality of action on the code subspace, not equality as exact operators on the full CFT Hilbert space.

## Complementary recovery

A striking feature of holographic codes is **complementary recovery**. Operators in $EW(A)$ can be reconstructed on $A$, while operators in $EW(\bar A)$ can be reconstructed on $\bar A$.

This matches the geometry: the RT surface divides the bulk into regions associated with complementary boundary regions.

Complementary recovery is subtle when the RT surface area is an operator or when the relevant algebra has a center. Then the correct language is operator-algebra quantum error correction.

The rough picture is:

| Bulk location | Boundary reconstruction |
|---|---|
| inside $EW(A)$ | reconstruct on $A$ |
| inside $EW(\bar A)$ | reconstruct on $\bar A$ |
| on or near the RT surface | center/edge-mode subtleties |
| outside both semiclassical wedges | not reconstructible in the chosen simple way |

This is the information-theoretic meaning of entanglement wedge geometry.

## JLMS relation

A central result relates boundary and bulk relative entropy. For states in a suitable code subspace,

$$
S_{\rm rel}^{\rm CFT}(\rho_A||\sigma_A)
=
S_{\rm rel}^{\rm bulk}(\rho_{a}||\sigma_{a})+\text{area-sector terms},
$$

schematically. Here $a$ is the bulk entanglement wedge region associated with $A$.

In a fixed-area or suitable semiclassical sector, this is often summarized as equality of boundary relative entropy and bulk relative entropy plus the appropriate geometric contribution.

This relation is powerful because relative entropy controls distinguishability of states. If boundary region $A$ can distinguish two code states exactly as well as the bulk wedge can, then the information in that wedge is reconstructible from $A$.

The conceptual chain is

$$
\text{RT/generalized entropy}
\quad\to\quad
\text{relative entropy equality}
\quad\to\quad
\text{entanglement wedge reconstruction}.
$$

## Area as an operator

At leading order, the RT area looks like a classical number. At finite $N$, the area can fluctuate between states. In quantum error-correction language, the area term behaves like a central operator associated with the decomposition of the code subspace into sectors.

This explains why the entropy formula resembles an operator-algebra code rather than the simplest textbook code:

$$
S_A
=\left\langle\frac{\operatorname{Area}}{4G_N}\right\rangle
+S_{\rm bulk}+\cdots .
$$

The area term is not ordinary bulk matter entropy. It is the geometric part of the encoding.

This is one reason holographic entropy is richer than a naive tensor-factorization story. Gravity does not factorize Hilbert spaces across surfaces in the simplest way.

## Tensor-network intuition

Tensor networks such as perfect tensors and random tensor networks provide toy models of holographic error correction. They show how a bulk logical index can be encoded redundantly into boundary indices.

These models make several ideas visual:

- reconstruction from different boundary regions;
- minimal cuts resembling RT surfaces;
- entanglement wedges;
- erasure correction;
- code subspaces;
- limitations of exact toy-model locality.

But tensor networks are models, not the full CFT. They capture useful structural features while missing many dynamical ingredients: gravitons, locality constraints, operator dimensions, chaos, and black-hole dynamics.

Use tensor networks as cartoons with teeth, not as the whole animal.

## HKLL reconstruction

Before the quantum-error-correction viewpoint, bulk reconstruction was often discussed through HKLL reconstruction. In a fixed semiclassical background, a free bulk field can be expressed as a smeared boundary operator:

$$
\phi(z,x)=\int d^d x'\,K(z,x|x')\mathcal O(x')+\text{interactions}.
$$

This reconstructs bulk fields from boundary operators using bulk equations of motion.

Quantum error correction refines the story. It explains why the reconstruction is not unique and how subregion reconstruction works. HKLL gives explicit formulas in favorable regimes; QEC explains the redundancy and limitations.

The two viewpoints are complementary:

$$
\text{HKLL}=\text{constructive bulk field reconstruction},
$$

$$
\text{QEC}=\text{information-theoretic structure of reconstruction}.
$$

## Islands and reconstruction

Islands extend the entanglement wedge of a boundary region or radiation system. In black-hole evaporation models, the radiation's entanglement wedge can include an island inside the black hole after the Page time.

This means that operators in the island can be reconstructed from the radiation degrees of freedom, within the appropriate gravitational path-integral and code-subspace setup.

That sounds wild because it is wild. But it is the same principle:

$$
\text{reconstruct from the region whose entanglement wedge contains the operator}.
$$

The island formula is not a separate reconstruction rule. It is entanglement wedge reconstruction applied after quantum extremal surfaces are included.

## Finite-N and approximate codes

Real holographic codes are approximate. At finite $N$, reconstruction is not exact, and errors are controlled by powers of $1/N$, nonperturbative effects, or the limits of the code subspace.

Sources of imperfection include:

| Source | Effect |
|---|---|
| finite $C_T$ | quantum gravity corrections |
| finite gap | stringy or higher-spin corrections |
| large backreaction | code subspace changes geometry |
| black-hole microstate complexity | simple reconstruction can fail |
| nonperturbative effects | exponentially small corrections become important |
| edge modes and constraints | Hilbert-space factorization subtleties |

Approximate error correction is not a weakness. It is exactly what one expects from semiclassical gravity.

## Common pitfalls

**Do not say a bulk operator equals one boundary operator globally.** Boundary representations agree within a code subspace.

**Do not confuse causal wedge and entanglement wedge.** Entanglement wedge reconstruction is generally stronger.

**Do not forget the code subspace.** Reconstruction depends on the class of states being encoded.

**Do not treat the RT area as ordinary matter entropy.** It is the geometric part of the encoding and can behave like a central operator.

**Do not take tensor networks too literally.** They are useful toy models, not full holographic CFTs.

**Do not assume exact locality at finite $N$.** Bulk locality is approximate and gravitationally dressed.

**Do not separate islands from entanglement wedges.** Islands are included by quantum extremal surface prescriptions.

## Relations to other pages

This page follows [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/) and [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/).

It prepares [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/) and [Bootstrap Constraints on Holography](/cft-bootstrap/holographic-cft/bootstrap-constraints-on-holography/).

It also connects to [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), because quantum error correction explains why approximate locality can be redundantly encoded in the boundary.

## Research status

The quantum-error-correction interpretation of AdS/CFT is established as a central organizing principle. Entanglement wedge reconstruction, complementary recovery, and relative-entropy arguments are standard tools in modern holography.

Active research studies approximate recovery, finite-$N$ corrections, islands, black-hole interiors, modular flow, operator-algebra codes, tensor-network models, state dependence, and the precise emergence of local bulk spacetime from exact CFT data.

## Exercises

### Exercise 1

What is a code subspace in holography?

<details><summary><strong>Solution</strong></summary>

A code subspace is a restricted subspace of the full CFT Hilbert space in which a semiclassical bulk effective field theory is valid:

$$
\mathcal H_{\rm code}\subset\mathcal H_{\rm CFT}.
$$

It usually contains low-energy bulk excitations around a chosen semiclassical background.

</details>

### Exercise 2

State the entanglement wedge reconstruction principle.

<details><summary><strong>Solution</strong></summary>

If a bulk operator lies in the entanglement wedge of a boundary region $A$, then there exists a boundary operator supported on $A$ that acts the same way on the code subspace:

$$
\phi(x)\in EW(A)
\quad\Rightarrow\quad
\exists\,\mathcal O_A\text{ with }\mathcal O_A\simeq\phi(x)
\text{ on }\mathcal H_{\rm code}.
$$

</details>

### Exercise 3

Why can the same bulk operator have multiple boundary reconstructions?

<details><summary><strong>Solution</strong></summary>

Because the bulk information is redundantly encoded in the boundary CFT, like logical information in a quantum error-correcting code. Different boundary regions can reconstruct the operator if their entanglement wedges contain it. The different boundary operators agree only within the code subspace.

</details>

### Exercise 4

What is complementary recovery?

<details><summary><strong>Solution</strong></summary>

Complementary recovery means that operators in the entanglement wedge of $A$ can be reconstructed on $A$, while operators in the entanglement wedge of $\bar A$ can be reconstructed on $\bar A$. This matches the geometric division of the bulk by the RT or quantum extremal surface.

</details>

### Exercise 5

How do islands fit into entanglement wedge reconstruction?

<details><summary><strong>Solution</strong></summary>

Islands arise when quantum extremal surfaces make a disconnected bulk region part of the entanglement wedge of a boundary or radiation system. Operators in the island can then be reconstructed from that system, within the appropriate code subspace and semiclassical approximation.

</details>

## References

- A. Almheiri, X. Dong, and D. Harlow, “Bulk locality and quantum error correction in AdS/CFT,” *Journal of High Energy Physics* **2015**.
- D. Harlow, “The Ryu-Takayanagi formula from quantum error correction,” *Communications in Mathematical Physics* **354** (2017).
- D. L. Jafferis, A. Lewkowycz, J. Maldacena, and S. J. Suh, “Relative entropy equals bulk relative entropy,” *Journal of High Energy Physics* **2016**.
- X. Dong, D. Harlow, and A. C. Wall, “Reconstruction of bulk operators within the entanglement wedge in gauge-gravity duality,” *Physical Review Letters* **117** (2016).
- F. Pastawski, B. Yoshida, D. Harlow, and J. Preskill, “Holographic quantum error-correcting codes: Toy models for the bulk/boundary correspondence,” *Journal of High Energy Physics* **2015**.
- A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, “The entropy of bulk quantum fields and the entanglement wedge of an evaporating black hole,” *Journal of High Energy Physics* **2019**.

## Version history

- 2026-07-01: First polished draft. Added code subspaces, erasure correction, entanglement wedge reconstruction, complementary recovery, JLMS relation, area-operator discussion, tensor-network intuition, HKLL comparison, islands and finite-$N$ caveats, exercises, and references.
