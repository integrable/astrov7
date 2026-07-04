---
title: "Quantum Error Correction"
description: "How semiclassical bulk effective theory is encoded redundantly in the CFT as an approximate operator-algebra quantum error-correcting code."
sidebar:
  order: 40
---

## Why this matters

Bulk reconstruction has a strange feature: the same bulk operator can often be represented on different boundary regions. A field in the center of AdS may be reconstructable from the left half of the boundary, from the right half, or from many overlapping large regions. At first this sounds impossible. If the same quantum information can be recovered from different places, have we cloned it?

No. The correct language is **quantum error correction**. The bulk effective theory is not embedded in the CFT as ordinary localized data. It is encoded redundantly in boundary degrees of freedom, much as a logical qubit is encoded into many physical qubits. Different boundary regions can reconstruct the same logical operator because they are different recovery regions for the same encoded information.

In AdS/CFT, the slogan is

$$
\text{bulk effective field theory}
\quad
\longleftrightarrow
\quad
\text{logical degrees of freedom in a CFT quantum code}.
$$

This page explains that slogan carefully.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Quantum error correction in AdS/CFT](/figures/course/holographic-quantum-error-correction.svg)

<figcaption>

In the quantum-error-correction view, the semiclassical bulk Hilbert space is a code subspace embedded into the full CFT Hilbert space. Bulk operators are logical operators. Boundary operators are physical representatives. A bulk operator in the entanglement wedge of $A$ can be reconstructed on $A$ even if the complement $\bar A$ is erased.

</figcaption>
</figure>

## Ordinary error correction in one paragraph

In a standard quantum error-correcting code, one embeds a small logical Hilbert space into a larger physical Hilbert space:

$$
V:\mathcal H_{\rm logical}\to \mathcal H_{\rm physical}.
$$

The physical system may suffer errors. A set of errors $\{E_i\}$ is correctable if there exists a recovery operation that restores the logical state. For an ordinary subspace code with projector $P_{\rm code}$, the Knill–Laflamme condition is

$$
P_{\rm code} E_i^\dagger E_j P_{\rm code}
=
\lambda_{ij}P_{\rm code}.
$$

This means that, inside the code subspace, the errors do not learn anything about the logical state. If the environment cannot distinguish logical states, the logical information can be recovered.

The holographic situation is richer because the logical operators form local bulk algebras, and gravity introduces gauge constraints and area operators. Still, the elementary intuition survives: boundary erasures can be correctable because bulk information is redundantly encoded.

## The CFT as the physical Hilbert space

In AdS/CFT, the physical Hilbert space is the Hilbert space of the boundary CFT. A semiclassical bulk effective theory around a chosen background is a code subspace:

$$
\mathcal H_{\rm code}\subset \mathcal H_{\rm CFT}.
$$

The embedding map is not usually written explicitly, but conceptually it is

$$
V:\mathcal H_{\rm bulk, EFT}\to \mathcal H_{\rm CFT}.
$$

A bulk operator $\phi(X)$ is a logical operator. A boundary representation $\Phi_A(X)$ supported on a boundary region $A$ is a physical representative. The reconstruction condition is

$$
\Phi_A(X)V|\psi\rangle
=
V\phi(X)|\psi\rangle,
\qquad
|\psi\rangle\in \mathcal H_{\rm bulk, EFT}.
$$

Equivalently, after identifying the code subspace with its image in the CFT,

$$
\Phi_A(X)|\psi\rangle
=
\phi(X)|\psi\rangle,
\qquad
|\psi\rangle\in \mathcal H_{\rm code}.
$$

The equality is code-subspace equality, not equality on the full CFT Hilbert space.

## Erasure correction and subregion duality

The most relevant error model for holography is **erasure**. Suppose the boundary is divided into a region $A$ and its complement $\bar A$. If $\bar A$ is erased, can we still reconstruct a bulk operator using only $A$?

The holographic answer is:

$$
\text{operators in }\mathcal W_E[A]
\quad
\text{are reconstructable on }A.
$$

Here $\mathcal W_E[A]$ is the entanglement wedge of $A$. Thus boundary subregion duality becomes a quantum-error-correction statement:

$$
\mathcal A_{\rm bulk}(\mathcal W_E[A])
\quad
\longleftrightarrow
\quad
\mathcal A_{\rm CFT}(A)
\quad
\text{on }\mathcal H_{\rm code}.
$$

If a bulk operator lies in $\mathcal W_E[A]$, erasing $\bar A$ does not destroy the logical information needed to represent that operator. If it lies outside $\mathcal W_E[A]$, region $A$ generally cannot reconstruct it.

## The commutant criterion

For erasure of $\bar A$, a useful operator-algebra criterion is:

$$
O_L\text{ is reconstructable on }A
\quad\Longleftrightarrow\quad
[O_L,X_{\bar A}]P_{\rm code}=0
\quad
\text{for all }X_{\bar A}\text{ supported on }\bar A.
$$

Here $O_L$ is a logical operator and $P_{\rm code}$ projects onto the code subspace. The criterion says: if every operator on the erased region $\bar A$ is unable to detect or disturb the logical action of $O_L$ inside the code subspace, then $O_L$ has a representative on the unerased region $A$.

In holography, this matches entanglement wedge nesting and complementarity. Operators in $\mathcal W_E[A]$ commute, within the code subspace, with operators reconstructable on the complementary wedge.

## Why multiple reconstructions do not clone information

Suppose a bulk operator $\phi(X)$ lies in both $\mathcal W_E[A]$ and $\mathcal W_E[B]$. Then there may be two boundary representatives:

$$
\Phi_A(X),
\qquad
\Phi_B(X),
$$

with

$$
\Phi_A(X)|\psi\rangle
=
\Phi_B(X)|\psi\rangle
=
\phi(X)|\psi\rangle
$$

for all $|\psi\rangle\in\mathcal H_{\rm code}$. This does not produce two independently measurable copies of the same quantum state. The two operators are different representatives of the same logical operator. They agree only after projection to the code subspace:

$$
P_{\rm code}\Phi_A(X)P_{\rm code}
=
P_{\rm code}\Phi_B(X)P_{\rm code}.
$$

Outside the code subspace, they can be completely different CFT operators. The no-cloning theorem is not violated because there is no operation that takes an arbitrary unknown quantum state and produces independent copies. There is only redundant encoding of a restricted logical subspace.

## Entanglement wedges as recovery regions

The entanglement wedge gives the recovery region for a boundary subsystem. For a boundary region $A$, the wedge $\mathcal W_E[A]$ is bounded by $A$ and the HRT surface $\chi_A$. In the quantum theory, the corresponding wedge is defined using quantum extremal surfaces.

The reconstruction statement is algebraic:

$$
O_a\in \mathcal A_{\rm bulk}(a)
\quad
\Rightarrow
\quad
\exists\,O_A\in\mathcal A_{\rm CFT}(A)
\text{ such that }
O_A|\psi\rangle=O_a|\psi\rangle.
$$

Here $a$ is the bulk entanglement-wedge region. The geometric statement “$a$ is inside $\mathcal W_E[A]$” becomes the information-theoretic statement “$A$ can recover the logical algebra of $a$.”

This also explains why deeper bulk points require larger boundary regions. A bulk point near the boundary may lie in the entanglement wedge of a small boundary region. A point near the center usually requires a larger region. A point behind a black-hole horizon may require a boundary system that includes the correct purifying degrees of freedom or radiation system.

## The area term as the center of the code

Holographic quantum error correction is not just ordinary subspace error correction. The RT/HRT area term behaves like an operator associated with the center of an operator algebra.

The quantum-corrected entropy formula is schematically

$$
S(\rho_A)
=
\left\langle
\frac{\widehat{\mathrm{Area}}(\chi_A)}{4G_N}
\right\rangle_\rho
+
S_{\rm bulk}(\rho_a)
+
\cdots.
$$

The area operator is not generally a simple boundary entropy by itself. It is part of the algebraic encoding. In an operator-algebra code, the logical algebra may have a center: operators that commute with all operators in the algebra. The area term is naturally associated with such central data, at least in a fixed semiclassical approximation.

This is one reason the holographic code is subtler than the simplest textbook quantum code.

## JLMS and modular Hamiltonians

A central relation in the modern story is the JLMS formula, schematically

$$
K_A^{\rm CFT}
=
\frac{\widehat{\mathrm{Area}}(\chi_A)}{4G_N}
+K_a^{\rm bulk}
+\cdots.
$$

Here $K_A^{\rm CFT}$ is the modular Hamiltonian of boundary region $A$, and $K_a^{\rm bulk}$ is the modular Hamiltonian of the bulk fields in the entanglement wedge. The same physics can be stated as equality of relative entropies:

$$
S_{\rm CFT}(\rho_A\|\sigma_A)
=
S_{\rm bulk}(\rho_a\|\sigma_a)
+\text{controlled corrections}.
$$

Relative entropy measures distinguishability. If boundary region $A$ has exactly the same distinguishability as the bulk region $a$, then $A$ contains the information needed to reconstruct the bulk algebra in $a$. This is why JLMS is more than an entropy identity: it is a reconstruction theorem in disguise.

## Tensor-network toy models

The HaPPY code is a famous toy model that makes the QEC structure visible. It builds a hyperbolic tensor network out of perfect tensors. Bulk legs are logical degrees of freedom, and boundary legs are physical degrees of freedom. The network map is an encoding map:

$$
V:\mathcal H_{\rm bulk}\to\mathcal H_{\rm boundary}.
$$

In such models, a bulk operator can be pushed through the tensor network to different boundary regions. The minimal cut through the network mimics the RT surface, and the number of cut legs mimics area.

These models are extremely useful pedagogically, but they are not full AdS/CFT. They usually lack realistic dynamics, gravitons, a continuum large-$N$ limit, and the full structure of gravitational constraints. Their value is that they isolate the information-theoretic mechanism.

## A small example: secret sharing intuition

Quantum secret sharing is a simple analogy. Imagine a logical qubit encoded into several physical subsystems so that any sufficiently large subset can reconstruct it, but smaller subsets cannot. Then the logical qubit is protected against erasure of a small number of subsystems.

Holography behaves similarly, but geometrically. The ability of a boundary region to reconstruct a bulk point depends on whether the region's entanglement wedge contains that point. The “access structure” is not arbitrary; it is determined by bulk geometry.

Thus geometry dictates who can recover which logical information.

## Approximate error correction

Real AdS/CFT is not an exact finite-dimensional tensor-network code. Reconstruction is usually approximate. The approximation is controlled by parameters such as

$$
\frac{1}{N},
\qquad
\frac{1}{\Delta_{\rm gap}},
\qquad
G_N,
\qquad
\alpha'.
$$

Even the code subspace itself is approximate. If one includes too many bulk excitations, their backreaction changes the geometry and the entanglement wedges. If one includes a number of states comparable to $e^{A/4G_N}$, black-hole entropy and finite-$N$ constraints become unavoidable.

A safe statement is:

$$
\text{semiclassical AdS/CFT realizes approximate operator-algebra quantum error correction on suitable code subspaces.}
$$

The adjectives matter.

## Black holes and state dependence

For black holes, the code-subspace qualification becomes urgent. Interior reconstruction may be possible for a code subspace of perturbations around a particular black-hole microstate or ensemble. But a single, state-independent operator that reconstructs the interior across an exponentially large set of black-hole microstates is generally too much to ask.

This is not a failure of the QEC picture. It is exactly what one expects from a code with finite capacity. A code can protect a logical subspace only up to some size. In gravity, that size is controlled by entropy and area.

The island formula is a late-stage expression of the same idea. After the Page time, the entanglement wedge of the Hawking radiation may include an island inside the black hole. Then radiation degrees of freedom can reconstruct certain interior operators. The recovery region changes because the quantum extremal surface changes.

## What the QEC picture explains

The quantum-error-correction viewpoint explains several facts that otherwise look mysterious:

| Holographic fact | QEC interpretation |
|---|---|
| bulk operators have multiple boundary representations | logical operators have multiple physical representatives |
| subregion duality uses entanglement wedges | recovery regions are determined by the encoded algebra |
| radial depth controls boundary nonlocality | deeper logical data require larger recovery regions |
| RT/HRT area terms appear in entropy | area behaves like central/geometric code data |
| bulk locality is approximate | logical locality holds only in a code subspace |
| black-hole interior reconstruction is subtle | code capacity and state dependence matter |

## What the QEC picture does not explain by itself

It is tempting to say that “gravity is just quantum error correction.” That is too quick. QEC explains the **encoding structure** of semiclassical bulk operators, but by itself it does not derive:

- the full CFT dynamics;
- Einstein's equations;
- the emergence of a smooth Lorentzian geometry;
- the detailed string spectrum;
- the value of Newton's constant;
- which CFTs have weakly curved gravity duals;
- the nonperturbative definition of all bulk observables.

QEC is a structural principle inside holography. It is not a standalone replacement for the duality.

## Dictionary checkpoint

| Bulk/gravity language | Quantum-information language |
|---|---|
| semiclassical bulk EFT | code subspace |
| full CFT Hilbert space | physical Hilbert space |
| bulk operator | logical operator |
| boundary representative | physical operator |
| boundary erasure | loss of a physical subsystem |
| entanglement wedge | recoverable logical algebra |
| RT/HRT area | central/geometric entropy term |
| multiple reconstructions | redundant encoding |
| finite-$N$ limitations | finite code capacity |

## Common confusions

### “Quantum error correction means the CFT is literally a tensor network.”

No. Tensor networks are toy models and calculational inspirations. The actual CFT is a continuum quantum field theory with dynamics, symmetries, stress tensor, operator product expansion, and large-$N$ structure. The QEC statement is about the encoding of bulk effective degrees of freedom, not about replacing the CFT by a simple network.

### “If $A$ reconstructs a bulk operator, $\bar A$ cannot know anything about it.”

Not exactly. Complementary regions reconstruct complementary algebras, and the area/center degrees of freedom complicate the statement. In ordinary error correction, correctability of erasure means the erased region has no access to the protected logical information. In holography, the operator-algebra version is the right language because of centers and gauge constraints.

### “The code subspace is the whole Hilbert space.”

No. The code subspace is small compared with the full CFT Hilbert space. It describes perturbative bulk states around a chosen semiclassical background. If the subspace is too large, backreaction changes the geometry, and the reconstruction map must change.

### “Multiple reconstructions violate no-cloning.”

They do not. The representatives agree only after projection to the code subspace. They are not independent copies of an arbitrary state.

### “QEC automatically solves the black-hole information problem.”

It supplies the right language for the encoding and recovery of interior/radiation information. The actual Page curve and islands require the quantum extremal surface prescription and gravitational replica-wormhole physics.

## Exercises

### Exercise 1: Erasure and commutation

Let $P$ be the projector onto a code subspace. Suppose a logical operator $O_L$ has a representative $O_A$ supported on $A$, so

$$
O_A P=O_L P,
\qquad
P O_A=P O_L.
$$

Show that $O_L$ commutes with every operator $X_{\bar A}$ supported on the complementary region $\bar A$, inside the code subspace.

<details>
<summary><strong>Solution</strong></summary>

Because $O_A$ is supported on $A$ and $X_{\bar A}$ is supported on $\bar A$, the two physical operators commute:

$$
[O_A,X_{\bar A}]=0.
$$

Inside the code subspace,

$$
P[O_L,X_{\bar A}]P
=
P[O_A,X_{\bar A}]P
=0.
$$

Thus any operator on the erased region $\bar A$ is unable to detect the logical action of $O_L$ within the code subspace. This is the algebraic signature of erasure correctability.

</details>

### Exercise 2: Why multiple reconstructions are allowed

Suppose $O_A$ and $O_B$ are two boundary representatives of the same logical operator $O_L$ on a code subspace. What equation expresses this, and why does it not imply $O_A=O_B$ as exact CFT operators?

<details>
<summary><strong>Solution</strong></summary>

The correct statement is

$$
P_{\rm code} O_A P_{\rm code}
=
P_{\rm code} O_B P_{\rm code}
=
P_{\rm code} O_L P_{\rm code}.
$$

This equality holds only after projecting to the code subspace. Outside the code subspace, $O_A$ and $O_B$ may act very differently. Therefore they need not be equal as exact operators on the full CFT Hilbert space. They are different physical representatives of the same logical operator.

</details>

### Exercise 3: Entropy decomposition

Explain the meaning of each term in

$$
S(\rho_A)
=
\left\langle
\frac{\widehat{\mathrm{Area}}(\chi_A)}{4G_N}
\right\rangle_\rho
+S_{\rm bulk}(\rho_a)+\cdots.
$$

<details>
<summary><strong>Solution</strong></summary>

The left-hand side is the entropy of the boundary region $A$. The first term on the right is the expectation value of the area of the HRT or quantum extremal surface in Planck units. It is the geometric contribution. The second term is the ordinary bulk entanglement entropy of quantum fields in the entanglement wedge region $a$. The ellipsis denotes higher-order quantum-gravity corrections, counterterm subtleties, and possible corrections to the semiclassical approximation. In the QEC interpretation, the area term is associated with central/geometric data of the encoded algebra.

</details>

### Exercise 4: Code subspace size

Why can one not include all black-hole microstates and all perturbative excitations in one fixed semiclassical code subspace with one fixed reconstruction map?

<details>
<summary><strong>Solution</strong></summary>

A fixed semiclassical code subspace assumes a fixed background geometry and small perturbations around it. Including too many states changes the geometry through backreaction. Including exponentially many black-hole microstates also runs into entropy bounds and finite code capacity. Reconstruction maps, entanglement wedges, and even the meaning of “the same bulk point” can depend on the background and the chosen state family. Therefore a single fixed reconstruction map is reliable only for an appropriately limited code subspace.

</details>

## Further reading

- A. Almheiri, X. Dong, and D. Harlow, [Bulk Locality and Quantum Error Correction in AdS/CFT](https://arxiv.org/abs/1411.7041).
- F. Pastawski, B. Yoshida, D. Harlow, and J. Preskill, [Holographic Quantum Error-Correcting Codes: Toy Models for the Bulk/Boundary Correspondence](https://arxiv.org/abs/1503.06237).
- D. L. Jafferis, A. Lewkowycz, J. Maldacena, and S. J. Suh, [Relative Entropy Equals Bulk Relative Entropy](https://arxiv.org/abs/1512.06431).
- X. Dong, D. Harlow, and A. C. Wall, [Reconstruction of Bulk Operators within the Entanglement Wedge in Gauge-Gravity Duality](https://arxiv.org/abs/1601.05416).
- D. Harlow, [TASI Lectures on the Emergence of Bulk Physics in AdS/CFT](https://arxiv.org/abs/1802.01040).
