---
title: "DHR Theory Preview"
description: "Introduce Doplicher–Haag–Roberts superselection theory: localized endomorphisms, tensor categories of sectors, statistics, and gauge-group reconstruction."
sidebar:
  label: "DHR Theory Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Doplicher–Haag–Roberts superselection theory; Doplicher–Roberts reconstruction; Haag, Local Quantum Physics."
topics:
  - algebraic QFT
  - DHR theory
  - superselection sectors
  - tensor categories
canonicalTopics:
  - dhr-theory
  - localized-endomorphisms
  - doplicher-roberts-reconstruction
researchStatus:
  established:
    - "DHR theory gives a rigorous tensor-categorical description of localized finite-statistics charges under standard AQFT assumptions."
  active:
    - "Long-range gauge charges, low-dimensional braid statistics, topological order, and higher-categorical generalized symmetries require extensions of the original DHR setting."
---

## Summary

Doplicher–Haag–Roberts theory is the part of algebraic QFT where superselection sectors become a precise mathematical structure. Its basic question is:

$$
\text{What can the observable net determine about charges?}
$$

The answer, in the original four-dimensional setting without long-range forces, is strikingly sharp. A charge sector can be described by a localized, transportable endomorphism of the observable algebra,

$$
\rho:\mathcal A\to\mathcal A,
\qquad
\rho(A)=A
\quad (A\in\mathcal A(\mathcal O')),
$$

where $\mathcal O'$ is the spacelike complement of a bounded region $\mathcal O$. The condition says that the charge is invisible to all observables localized outside $\mathcal O$.

The collection of such endomorphisms is not just a set. It is a tensor category. The product of charges is composition,

$$
\rho\otimes\sigma := \rho\circ\sigma,
$$

and charge-changing operators appear as intertwiners. In spacetime dimension at least three spatial dimensions, locality makes the statistics symmetric; in two spatial dimensions, the analogous theory leads to braided statistics rather than ordinary Bose–Fermi alternatives.

The deepest structural result is the Doplicher–Roberts reconstruction theorem: under appropriate hypotheses, the category of finite-statistics DHR sectors reconstructs a compact gauge group $G$ and a field algebra $\mathcal F$ whose gauge-invariant part is the observable algebra,

$$
\mathcal A = \mathcal F^G.
$$

This page is a preview rather than a full proof. Its job is to explain the dictionary: DHR representation, localized endomorphism, transportability, intertwiners, fusion, statistics, conjugates, and gauge-group reconstruction.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A pipeline from a Haag–Kastler observable net and vacuum sector to DHR selection, localized transportable endomorphisms, a tensor C-star category of sectors, statistics and conjugates, and Doplicher–Roberts reconstruction of a field algebra and compact gauge group.](/figures/rigorous-qft/dhr-category-reconstruction.svg)

<figcaption>

The DHR pipeline. Starting from local observables, a localization criterion selects charged representations. Under duality and finite-statistics assumptions, these become localized endomorphisms forming a tensor category. In the symmetric case this category reconstructs a compact gauge group $G$ and a field algebra $\mathcal F$ with $\mathcal A=\mathcal F^G$.

</figcaption>
</figure>

## Prerequisites

You should know [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/), [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/), and [Superselection Sectors](/rigorous-qft/algebraic-qft/superselection-sectors/). The pages [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) and [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) give useful Wightman-side intuition.

## Core idea

The observable algebra of a theory may not contain charged fields. In electrodynamics, for example, a charged electron field is not gauge invariant, whereas electric charge is detected through gauge-invariant observables. DHR theory starts from the observable net alone and asks whether the missing charged-field structure can be recovered from observable data.

The recovery is possible only after imposing a physical selection criterion. Without one, the representation theory of a quasi-local $C^*$-algebra is far too large. DHR theory selects representations that differ from the vacuum only inside bounded regions and can be moved to other bounded regions without changing the sector.

The slogan is:

$$
\text{localized charge}
= \text{vacuum outside a bounded region}.
$$

This criterion is local, operational, and representation-theoretic. It does not require a Lagrangian, a chosen charged field, or a prior internal gauge group. Those structures are recovered later, when the sector category has enough finiteness and symmetry.

## Setup and conventions

Let

$$
\mathcal O\longmapsto \mathcal A(\mathcal O)
$$

be a Haag–Kastler net of observable $C^*$-algebras or von Neumann algebras on Minkowski spacetime. Let $\mathcal A$ be the quasi-local $C^*$-algebra generated by the local algebras. Let

$$
(\mathcal H_0,\pi_0,\Omega)
$$

be the vacuum representation, and, when no confusion can arise, identify $\mathcal A$ with its image $\pi_0(\mathcal A)$.

For a double cone $\mathcal O$, write $\mathcal O'$ for the spacelike complement. The algebra generated by observables in regions contained in $\mathcal O'$ is denoted schematically by

$$
\mathcal A(\mathcal O').
$$

In detailed treatments one must choose whether this means the $C^*$-algebraic causal-complement algebra, the corresponding von Neumann algebra in the vacuum representation, or a dual net. This page suppresses those completions unless they affect the point being made.

Two representations $\pi_1$ and $\pi_2$ are unitarily equivalent, written $\pi_1\simeq\pi_2$, if a unitary $U$ intertwines their actions:

$$
U\pi_1(A)U^{-1}=\pi_2(A)
\qquad (A\in\mathcal A).
$$

A sector is an equivalence class of physically admissible representations. DHR theory supplies one important admissibility criterion.

## The DHR selection criterion

A representation $\pi$ satisfies the DHR localization criterion in a double cone $\mathcal O$ if

$$
\pi|_{\mathcal A(\mathcal O')}
\simeq
\pi_0|_{\mathcal A(\mathcal O')}.
$$

In words: all measurements spacelike to $\mathcal O$ see the representation $\pi$ as the vacuum representation. The charge carried by $\pi$ is localized in $\mathcal O$.

A representation is **transportable** if for every double cone $\widetilde{\mathcal O}$ there is a unitarily equivalent representation localized in $\widetilde{\mathcal O}$. Transportability says that the charge type does not depend on where the charge is placed. A charge can be moved without changing the sector.

A representation satisfying localization and transportability is called a DHR representation. One often adds local normality, positive energy, irreducibility or factoriality, and finite-statistics hypotheses depending on the theorem under discussion.

The DHR criterion is deliberately strong. It is suited to charges that can be localized in bounded spacetime regions. It is not designed to capture electric charges in ordinary four-dimensional QED, where Gauss's law ties charge to flux at infinity. This failure is not a bug; it identifies exactly where long-range gauge fields escape the bounded-localization criterion.

## From representations to endomorphisms

Assume a suitable form of Haag duality in the vacuum representation. Then a DHR representation localized in $\mathcal O$ can be represented by an endomorphism

$$
\rho:\mathcal A\to\mathcal A
$$

such that

$$
\rho(A)=A
\qquad
(A\in\mathcal A(\mathcal O')).
$$

The corresponding representation is

$$
\pi_\rho=\pi_0\circ\rho.
$$

This is one of the conceptual miracles of DHR theory. Instead of studying many Hilbert spaces at once, one can often study endomorphisms of the vacuum observable algebra. Localization becomes the statement that $\rho$ acts trivially on the spacelike complement.

The vacuum sector is the identity endomorphism,

$$
\iota(A)=A.
$$

Two localized endomorphisms $\rho$ and $\sigma$ describe the same sector if they are unitarily equivalent by an observable intertwiner. An operator $T\in\mathcal A$ is an intertwiner from $\rho$ to $\sigma$ if

$$
T\rho(A)=\sigma(A)T
\qquad (A\in\mathcal A).
$$

The space of such intertwiners is written

$$
\operatorname{Hom}(\rho,\sigma).
$$

Thus DHR sectors form a category: objects are localized transportable endomorphisms, and arrows are intertwiners.

## Fusion as composition

The product of two charges is their joint sector. In the endomorphism picture, this product is simply composition:

$$
\rho\otimes\sigma
:=\rho\circ\sigma.
$$

This convention means that the combined representation is

$$
\pi_{\rho\otimes\sigma}
=\pi_0\circ\rho\circ\sigma.
$$

Composition is associative, so fusion is associative up to the standard categorical identifications. Direct sums and subobjects correspond to reducible sectors and their irreducible components.

For example, if a sector $\rho$ decomposes as

$$
\rho\simeq \rho_1\oplus \rho_2,
$$

then the charge type represented by $\rho$ contains the irreducible sector types $\rho_1$ and $\rho_2$. Fusion coefficients are the multiplicities in decompositions such as

$$
\rho\otimes\sigma
\simeq
\bigoplus_\tau N_{\rho\sigma}^{\tau}\,\tau.
$$

In finite-statistics rational situations this resembles the fusion algebra familiar from CFT. DHR theory, however, is not limited to conformal theories; it is a general local-QFT mechanism for deriving fusion from observable localization.

## Statistics from locality

Suppose $\rho$ and $\sigma$ are localized in spacelike separated double cones. Locality implies that their actions commute on observables in a precise categorical sense. Transportability then allows one to compare $\rho\circ\sigma$ with $\sigma\circ\rho$ even when the localization regions are moved.

The result is a statistics operator,

$$
\varepsilon_{\rho,\sigma}
\in
\operatorname{Hom}(\rho\circ\sigma,\sigma\circ\rho).
$$

This operator is the algebraic version of exchanging two charges. It is not inserted by hand. It is extracted from locality and transportability.

In spacetime dimension $d\geq 4$, the relevant configuration-space topology gives ordinary permutation statistics. The statistics is symmetric:

$$
\varepsilon_{\sigma,\rho}\,
\varepsilon_{\rho,\sigma}=1.
$$

Finite-statistics irreducible sectors obey a rigorous version of the Bose–Fermi alternative, with possible parastatistics encoded by higher-dimensional representations of the compact gauge group that is reconstructed later.

In three spacetime dimensions, or in chiral conformal theories on the line or circle, the analogous exchange structure is braided rather than symmetric. Then one should expect braid group statistics, anyonic sectors, modular tensor categories, and related structures. That is an extension of the DHR idea, not the original four-dimensional symmetric case.

## Conjugates and finite statistics

A sector $\rho$ has a conjugate or dual sector $\overline\rho$ if the product of $\rho$ with $\overline\rho$ contains the vacuum in the appropriate categorical sense. Concretely, there are intertwiners

$$
R\in \operatorname{Hom}(\iota,\overline\rho\rho),
\qquad
\overline R\in \operatorname{Hom}(\iota,\rho\overline\rho)
$$

satisfying conjugate equations. These are categorical analogues of particle–antiparticle pairing.

Finite statistics is the condition that the sector has finite statistical dimension. The statistical dimension $d(\rho)$ behaves like an internal multiplicity:

$$
d(\rho\oplus\sigma)=d(\rho)+d(\sigma),
\qquad
d(\rho\otimes\sigma)=d(\rho)d(\sigma).
$$

For sectors that come from ordinary compact group representations, $d(\rho)$ is the dimension of the corresponding representation. In the algebraic construction this number is intrinsic: it is not assumed from a preexisting group representation.

The finite-statistics DHR sectors form a rigid $C^*$-tensor category. In four-dimensional theories satisfying the usual symmetry assumptions, it is symmetric. This is the input for Doplicher–Roberts reconstruction.

## Gauge-group reconstruction

The Doplicher–Roberts theorem says, roughly, that a symmetric rigid $C^*$-tensor category of DHR sectors with finite statistics and simple unit is equivalent to the category of finite-dimensional continuous unitary representations of a compact group $G$:

$$
\mathsf{DHR}_f(\mathcal A)
\simeq
\operatorname{Rep}(G).
$$

More precisely, in the presence of fermionic sectors one keeps track of the usual Bose–Fermi grading, often encoded by a distinguished central element of $G$. The same construction produces a field algebra $\mathcal F$ carrying an action of $G$ such that the observables are the fixed points:

$$
\mathcal A=\mathcal F^G.
$$

This is a theorem-level form of a familiar physical idea: charged fields may be absent from the observable algebra, but their charge structure can be reconstructed from the observable sectors. The gauge group is not assumed first and then imposed on fields. It is recovered from the tensor category of localized charges.

There is a subtle philosophical payoff. In this framework, **global gauge group** means a compact internal group acting on a reconstructed field algebra. It is not a local gauge redundancy in the Lagrangian sense. Local gauge symmetry is usually a presentation-dependent redundancy, while the DHR gauge group is an invariant structure extracted from observables under the stated hypotheses.

## A basic example: a global charge

Imagine a theory with a compact internal symmetry group $G$ and a field algebra $\mathcal F$. The observable algebra is the invariant subalgebra

$$
\mathcal A=\mathcal F^G.
$$

Charged fields transform in representations of $G$ and are not themselves observables. Applying a charged field to the vacuum can create a state in a charged sector. The observable algebra cannot connect different irreducible charge sectors, but it can detect sector labels through how representations restrict to local observables.

For $G=U(1)$, charged sectors are labeled by integer charge in simple examples. Fusion adds charges:

$$
n\otimes m = n+m.
$$

For non-Abelian compact $G$, sectors are labeled by irreducible representations, and fusion follows tensor-product decomposition. DHR reconstruction reverses this logic: from the fusion and statistics category of sectors it recovers $G$.

This example is pedagogically useful but incomplete. In interacting gauge theories, especially with massless gauge bosons or topological sectors, not all physically important charges satisfy the DHR bounded-localization criterion.

## Relation to Gauss law and long-range forces

DHR localization is too strong for electric charge in four-dimensional QED. Gauss's law says that the total charge can be measured by the electric flux through a large sphere,

$$
Q=\lim_{R\to\infty}
\int_{S_R^2} \mathbf E\cdot d\mathbf S,
$$

at least formally and with the usual domain qualifications. No bounded region can screen this information from all far-away observables. Charged sectors in theories with long-range electromagnetic fields are therefore not DHR sectors.

Buchholz–Fredenhagen sectors, cone-localized sectors, infraparticle analysis, and related frameworks address parts of this problem. Low-dimensional topological phases and generalized symmetries also require broader localization notions. The lesson is not that DHR theory is wrong. The lesson is that localization type is part of the physics.

## Common pitfalls

**DHR sectors are not all possible sectors.** They are sectors satisfying a bounded-localization and transportability criterion. Long-range gauge charges, solitonic sectors, thermal representations, boundary sectors, and topological sectors may require other criteria.

**The field algebra is reconstructed, not assumed.** In the DHR–Doplicher–Roberts logic, one starts with observables and reconstructs charged fields and a compact gauge group under hypotheses. This is different from starting with gauge-variant fields and projecting to gauge invariants.

**The DHR gauge group is not local gauge redundancy.** It is a compact global group acting on the reconstructed field algebra. Lagrangian gauge redundancy is a different concept and can be presentation-dependent.

**The tensor product is composition of endomorphisms.** This is initially surprising because one expects tensor products of Hilbert spaces. In the endomorphism picture, composition is precisely what represents putting charges together.

**Four-dimensional statistics and low-dimensional statistics differ.** The original DHR reconstruction is symmetric. In lower-dimensional AQFT and chiral CFT, braid statistics replaces symmetric statistics.

**Haag duality matters.** Passing cleanly from representations to localized endomorphisms usually uses duality assumptions or a dual-net replacement. Without them, the categorical picture needs technical modifications.

**Finite statistics is an assumption in the reconstruction theorem.** Infinite-statistics or infinite-dimensional sector structures can occur in broader contexts. The compact-group reconstruction theorem applies to the finite-statistics symmetric subcategory.

## Relations to other pages

The page [Superselection Sectors](/rigorous-qft/algebraic-qft/superselection-sectors/) gives the conceptual entry point. This page sharpens that discussion into the DHR mechanism: localized representations become endomorphisms, and endomorphisms form a tensor category.

The page [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/) explains why a state naturally produces a representation, while [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/) explains the reference vacuum sector. The page [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) explains why localization data is part of the theory rather than optional decoration.

The next page, [Modular Theory and Tomita–Takesaki](/rigorous-qft/algebraic-qft/modular-theory-and-tomita-takesaki/), develops a different operator-algebraic engine: cyclic separating vectors, modular conjugations, modular flows, and their role in duality, thermal structure, and entanglement.

## Research status

The core DHR theory and Doplicher–Roberts reconstruction are established mathematical physics. They are among the clearest examples where locality, representation theory, and operator algebras produce a structural theorem about QFT.

Several important directions go beyond the original setting. Massless gauge theories require weaker localization criteria because charges are tied to fields at infinity. Low-dimensional QFT and topological phases produce braided rather than symmetric sector categories. Conformal nets, subfactor theory, and rational CFT give highly developed examples of braided sector theory. Modern discussions of generalized and non-invertible symmetries can often be read as descendants or extensions of the same core idea: sectors and defects form algebraic structures richer than ordinary group actions.

For four-dimensional interacting gauge theories, one should be careful. DHR theory is a rigorous framework for localizable charges, not a complete construction of Yang–Mills theory or of the Standard Model as a net of observables.

## Exercises

### Exercise 1: invisible relative phase

Let

$$
\mathcal H=\mathcal H_1\oplus\mathcal H_2,
\qquad
\mathcal A=B(\mathcal H_1)\oplus B(\mathcal H_2).
$$

For normalized vectors $\psi_i\in\mathcal H_i$, set

$$
\Psi_\theta=\frac{1}{\sqrt2}
(\psi_1+e^{i\theta}\psi_2).
$$

Show that all expectations $\langle\Psi_\theta,A\Psi_\theta\rangle$ with $A\in\mathcal A$ are independent of $\theta$.

<details><summary><strong>Solution</strong></summary>

Every observable has the block-diagonal form

$$
A=A_1\oplus A_2.
$$

Therefore

$$
\begin{aligned}
\langle\Psi_\theta,A\Psi_\theta\rangle
&=\frac12\langle\psi_1,A_1\psi_1\rangle
+\frac12\langle e^{i\theta}\psi_2,
A_2e^{i\theta}\psi_2\rangle \\
&=\frac12\langle\psi_1,A_1\psi_1\rangle
+\frac12\langle\psi_2,A_2\psi_2\rangle.
\end{aligned}
$$

There are no off-diagonal observables in $\mathcal A$, so no expectation value can see the relative phase.

</details>

### Exercise 2: composition preserves localization

Suppose $\rho$ and $\sigma$ are both localized in the same double cone $\mathcal O$, meaning

$$
\rho(A)=A,
\qquad
\sigma(A)=A
\quad (A\in\mathcal A(\mathcal O')).
$$

Show that $\rho\circ\sigma$ is also localized in $\mathcal O$.

<details><summary><strong>Solution</strong></summary>

For $A\in\mathcal A(\mathcal O')$,

$$
(\rho\circ\sigma)(A)
=\rho(\sigma(A))
=\rho(A)
=A.
$$

Thus the composed endomorphism acts trivially on the spacelike complement, so it is localized in the same double cone. This is the elementary reason that composition is a natural candidate for fusion of localized charges.

</details>

### Exercise 3: intertwiners as charged-field-like operators

Let $T\in\operatorname{Hom}(\rho,\sigma)$, so

$$
T\rho(A)=\sigma(A)T
\qquad (A\in\mathcal A).
$$

Show that if $T$ is unitary, then $\rho$ and $\sigma$ are equivalent endomorphisms.

<details><summary><strong>Solution</strong></summary>

If $T$ is unitary, multiply the intertwining relation on the right by $T^{-1}$:

$$
T\rho(A)T^{-1}=\sigma(A).
$$

Thus $T$ implements unitary equivalence of the two endomorphisms. In sector language, $\rho$ and $\sigma$ describe the same charge type placed, perhaps, in different localization regions.

</details>

## References

### Original DHR and reconstruction papers

- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local observables and particle statistics I," *Communications in Mathematical Physics* **23** (1971), 199–230. [doi:10.1007/BF01877742](https://doi.org/10.1007/BF01877742).
- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local observables and particle statistics II," *Communications in Mathematical Physics* **35** (1974), 49–85. [doi:10.1007/BF01646454](https://doi.org/10.1007/BF01646454).
- Sergio Doplicher and John E. Roberts, "A new duality theory for compact groups," *Inventiones mathematicae* **98** (1989), 157–218. [doi:10.1007/BF01388849](https://doi.org/10.1007/BF01388849).
- Sergio Doplicher and John E. Roberts, "Why there is a field algebra with a compact gauge group describing the superselection structure in particle physics," *Communications in Mathematical Physics* **131** (1990), 51–107. [doi:10.1007/BF02097680](https://doi.org/10.1007/BF02097680).

### Standard AQFT references

- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).
- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory – an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).
- Detlev Buchholz and Klaus Fredenhagen, "Algebraic Quantum Field Theory: Objectives, Methods, and Results," arXiv: [2305.12923](https://arxiv.org/abs/2305.12923).

### Extensions and low-dimensional sectors

- Klaus Fredenhagen, Karl-Henning Rehren, and Bert Schroer, "Superselection sectors with braid group statistics and exchange algebras I," *Communications in Mathematical Physics* **125** (1989), 201–226. [doi:10.1007/BF01217906](https://doi.org/10.1007/BF01217906).
- Klaus Fredenhagen, Karl-Henning Rehren, and Bert Schroer, "Superselection sectors with braid group statistics and exchange algebras II," *Reviews in Mathematical Physics* **4** (1992), 113–157. [doi:10.1142/S0129055X92000170](https://doi.org/10.1142/S0129055X92000170).
- D. Guido, R. Longo, J. E. Roberts, and R. Verch, "Charged sectors, spin and statistics in quantum field theory on curved spacetimes," arXiv: [math-ph/9906019](https://arxiv.org/abs/math-ph/9906019).

## Version history

- 2026-06-29: First polished draft. Introduced the DHR selection criterion, endomorphism picture, tensor-category structure, statistics, conjugates, Doplicher–Roberts reconstruction, limitations, and exercises.
