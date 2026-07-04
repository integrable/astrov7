---
title: "Superselection Sectors"
description: "Explain superselection sectors in algebraic QFT, with the DHR criterion, localized endomorphisms, fusion, and the gauge-group reconstruction idea."
sidebar:
  label: "Superselection Sectors"
  order: 6
level: Advanced
status: "Polished draft"
source: "Doplicher–Haag–Roberts superselection theory; Haag, Local Quantum Physics; Fewster–Rejzner AQFT introduction; Halvorson AQFT review."
topics:
  - algebraic QFT
  - superselection sectors
  - DHR theory
canonicalTopics:
  - superselection-sectors
  - dhr-theory
  - localized-endomorphisms
researchStatus:
  established:
    - "DHR superselection theory gives a rigorous description of localized charges and their tensor-category structure under standard assumptions."
  active:
    - "Gauge theories with long-range forces, low-dimensional braid statistics, topological sectors, and generalized symmetries require extensions beyond the simplest DHR setting."
---

## Summary

A **superselection sector** is a class of states or representations that cannot be coherently connected by the observable algebra. In the simplest Hilbert-space picture, observables are block diagonal,

$$
\mathcal H=\bigoplus_\alpha \mathcal H_\alpha,
\qquad
A=\bigoplus_\alpha A_\alpha,
$$

so no observable has matrix elements between different blocks. The labels $\alpha$ are superselection labels: charge, statistics type, boundary condition, topological sector, or phase data, depending on the theory.

In algebraic QFT the sharper language is representation-theoretic. A sector is often an equivalence class of irreducible or factorial representations of the quasi-local observable algebra $\mathcal A$. The vacuum sector is the GNS representation of the vacuum state. Charged sectors are inequivalent representations that look locally like possible charged states but cannot be obtained by applying observable operators to the vacuum.

The most famous rigorous selection criterion is the **Doplicher–Haag–Roberts criterion**. A DHR charge is localized in a bounded region $\mathcal O$ if, outside $\mathcal O$, it is indistinguishable from the vacuum representation. Under Haag duality, such sectors can be described by localized, transportable endomorphisms

$$
\rho:\mathcal A\to\mathcal A,
\qquad
\rho(A)=A
\quad (A\in\mathcal A(\mathcal O')).
$$

Composition of endomorphisms gives fusion of charges. Intertwiners give charged-field-like morphisms. Under additional assumptions, the category of DHR sectors reconstructs a compact gauge group and a field algebra whose gauge-invariant part is the observable algebra.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing the DHR criterion: a charge localized in a region acts trivially on observables in the spacelike complement, then DHR sectors form a tensor category with fusion by composition and intertwiners between sectors.](/figures/rigorous-qft/superselection-dhr-sectors.svg)

<figcaption>

The DHR picture. A localized charge is invisible to observables in the spacelike complement of its localization region. Localized, transportable endomorphisms form a tensor category whose product is composition.

</figcaption>
</figure>

## Prerequisites

You should know [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/), [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/), and [Isotony, Locality, and Covariance](/rigorous-qft/algebraic-qft/isotony-locality-and-covariance/). The Wightman pages [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) and [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) provide useful comparison points.

## Core idea

The observable algebra may not contain all fields one uses to describe charged objects. For example, a charged field can change total charge, but a gauge-invariant observable cannot. If only gauge-invariant observables are admitted, states with different total charge may belong to different superselection sectors.

This is not merely a statement about a particular Hamiltonian. It is a statement about what the observable algebra can and cannot do. If all physical observables commute with a charge operator $Q$, then the spectral subspaces of $Q$ cannot be coherently mixed by observables. An operator that changes $Q$ is not an observable in that algebra.

Algebraic QFT turns this idea into representation theory. Instead of saying “there are charge eigenspaces inside one Hilbert space,” one often says “there are inequivalent representations of the observable algebra.” The second formulation is more flexible in infinite systems and is the natural language of local quantum physics.

## Setup and conventions

Let

$$
\mathcal O\longmapsto \mathcal A(\mathcal O)
$$

be a Haag–Kastler net on Minkowski spacetime, and let $\mathcal A$ be its quasi-local $C^*$-algebra. A representation is a $*$-representation

$$
\pi:\mathcal A\to B(\mathcal H_\pi).
$$

Two representations $\pi_1$ and $\pi_2$ are unitarily equivalent if there is a unitary

$$
U:\mathcal H_{\pi_1}\to\mathcal H_{\pi_2}
$$

such that

$$
U\pi_1(A)U^{-1}=\pi_2(A)
\qquad (A\in\mathcal A).
$$

A first approximation is:

$$
\text{sector} =
\text{unitary equivalence class of physically admissible representations}.
$$

For detailed sector theory one often restricts to irreducible, factorial, locally normal, positive-energy, or localized representations, depending on the selection criterion being used.

## Superselection in the simplest block model

The simplest model of superselection is a Hilbert space split into orthogonal blocks,

$$
\mathcal H=\mathcal H_1\oplus\mathcal H_2,
$$

with observable algebra

$$
\mathcal A
= B(\mathcal H_1)\oplus B(\mathcal H_2)
\subset B(\mathcal H_1\oplus\mathcal H_2).
$$

Every observable has the form

$$
A=\begin{pmatrix}
A_1 & 0\\
0 & A_2
\end{pmatrix}.
$$

There is no observable of the form

$$
\begin{pmatrix}
0 & T\\
T^* & 0
\end{pmatrix},
$$

so no observable can measure a relative phase between vectors in different blocks. If

$$
\Psi=\frac{1}{\sqrt2}(\psi_1+e^{i\theta}\psi_2),
\qquad
\psi_i\in\mathcal H_i,
$$

then for all observables $A\in\mathcal A$,

$$
\langle\Psi,A\Psi\rangle
=\frac12\langle\psi_1,A_1\psi_1\rangle
+\frac12\langle\psi_2,A_2\psi_2\rangle.
$$

The phase $e^{i\theta}$ is invisible. Operationally, the coherent vector and the incoherent mixture give the same expectation values on the observable algebra.

This finite-dimensional picture is useful, but it should not be overinterpreted. In QFT, sectors often appear as inequivalent representations rather than literal blocks in one predetermined Hilbert space.

## Sectors as representations

Let $\pi_0$ be the vacuum representation of $\mathcal A$. The vacuum sector is the equivalence class of $\pi_0$. A charged sector is represented by another representation $\pi$ that is physically admissible but not unitarily equivalent to $\pi_0$.

The question then becomes: **which representations should count as physical sectors of the same theory?** Without a selection criterion, the representation theory of a large $C^*$-algebra can be too big. Algebraic QFT therefore imposes physically motivated criteria.

Common requirements include:

| Requirement | Meaning |
|---|---|
| Local normality | The representation behaves normally on each local von Neumann algebra of the reference representation. |
| Positive energy | Spacetime translations are implemented with spectrum in the forward light cone. |
| Localization | The representation differs from the vacuum only inside some localization region. |
| Transportability | The charge can be moved to other suitable regions without changing the sector. |
| Finite statistics | The sector has a finite statistical dimension, analogous to a finite internal multiplicity. |

The DHR theory focuses on localized and transportable charges in relativistic QFT without long-range gauge fields.

## The DHR selection criterion

Work in the vacuum representation and assume the observable net satisfies suitable versions of locality, covariance, Haag duality, and positive energy. Let $\mathcal O'$ denote the spacelike complement of a double cone $\mathcal O$.

A representation $\pi$ is localized in $\mathcal O$ relative to the vacuum if

$$
\pi|_{\mathcal A(\mathcal O')}
\simeq
\pi_0|_{\mathcal A(\mathcal O')}.
$$

This means that outside $\mathcal O$, the representation is indistinguishable from the vacuum by all observables localized in the spacelike complement. A DHR representation is, roughly, one that can be localized in bounded regions and transported to any other such region by unitary equivalence.

Under Haag duality one may represent a localized sector by an endomorphism

$$
\rho:\mathcal A\to\mathcal A
$$

such that

$$
\rho(A)=A
\qquad
(A\in\mathcal A(\mathcal O')).
$$

This is the localized-endomorphism picture. The representation corresponding to $\rho$ is

$$
\pi_\rho=\pi_0\circ\rho.
$$

The vacuum sector corresponds to the identity endomorphism

$$
\iota(A)=A.
$$

## Fusion and intertwiners

If $\rho$ and $\sigma$ are localized endomorphisms, their composition

$$
\rho\sigma=\rho\circ\sigma
$$

is again an endomorphism. If both are localized in the same region $\mathcal O$, then $\rho\sigma$ is also localized in $\mathcal O$, since for $A\in\mathcal A(\mathcal O')$,

$$
(\rho\sigma)(A)=\rho(A)=A.
$$

This composition is interpreted as **fusion of charges**. The identity endomorphism is the tensor unit.

An intertwiner from $\rho$ to $\sigma$ is an operator $T$ in the observable algebra, or in a suitable represented algebra, satisfying

$$
T\rho(A)=\sigma(A)T
\qquad (A\in\mathcal A).
$$

Intertwiners are the morphisms of the sector category. They encode multiplicities, subobjects, direct sums, and equivalences between sectors.

Thus DHR sectors form a tensor category:

$$
\begin{array}{ccl}
\text{objects} &:& \text{localized transportable endomorphisms},\\
\text{morphisms} &:& \text{intertwiners},\\
\text{tensor product} &:& \text{composition of endomorphisms}.
\end{array}
$$

In spacetime dimension at least $1+3$, locality makes this tensor category symmetric. In lower dimensions, spacelike exchange can carry braid-group information, and braided tensor categories appear instead.

## Statistics and conjugates

The DHR framework does not merely label charges. It also derives statistics structure from locality.

For a sector $\rho$, a conjugate sector $\bar\rho$ behaves like an antiparticle or conjugate charge. The sector $\bar\rho\rho$ should contain the vacuum sector if a charge–anticharge pair can annihilate into observables. Finite-statistics sectors have a statistical dimension $d(\rho)$, which plays the role of an intrinsic size or quantum dimension.

In ordinary four-dimensional relativistic QFT, the resulting statistics are Bose, Fermi, or para-statistics, and the DHR–Doplicher–Roberts analysis shows how para-statistics can be reinterpreted using an ordinary compact gauge group and multiplet fields.

In two-dimensional chiral CFT and low-dimensional topological phases, the corresponding categories can be braided or modular rather than symmetric. Those cases are not failures of the sector idea; they are reminders that the topology of spacelike exchange matters.

## Gauge-group reconstruction

One of the striking outcomes of the Doplicher–Roberts theory is that, under suitable assumptions, the category of sectors determines a compact gauge group $G$ and a field algebra $\mathcal F$ such that

$$
\mathcal A = \mathcal F^G,
$$

where $\mathcal F^G$ denotes the gauge-invariant subalgebra.

This reverses the usual physics presentation. Instead of starting with charged fields and a gauge group and then taking gauge-invariant observables, one starts with the observable algebra and its localized sectors. The charged field algebra and compact gauge group are reconstructed from the category of representations.

The moral is precise and important:

$$
\text{observable locality + sector structure}
\quad\Longrightarrow\quad
\text{charged fields and compact gauge symmetry}
$$

under the hypotheses of the theorem.

This is one reason algebraic QFT treats observables as primary. Gauge symmetry, in this setting, is not merely a redundancy in a Lagrangian presentation; it can appear as a reconstruction from the superselection structure of the observable net.

## What DHR does not cover

The DHR criterion is powerful but not universal.

First, it is designed for charges localizable in bounded regions. Electric charge in QED is not of this type. Gauss law ties electric charge to long-range electromagnetic flux, so a charged state cannot be indistinguishable from the vacuum outside every bounded region. Such sectors require weaker localization, such as spacelike cone localization, and lead to Buchholz–Fredenhagen-type analyses and infraparticle issues.

Second, DHR theory in its simplest form assumes a fixed vacuum representation and good duality properties. Curved spacetime, thermal states, broken phases, boundaries, defects, and topological order may require different reference states or different localization criteria.

Third, low-dimensional theories can have braid statistics. The category of sectors then carries braided rather than symmetric structure, and the reconstruction target is subtler than an ordinary compact group.

Fourth, modern generalized and non-invertible symmetries overlap with the language of sectors and defects, but they are not identical to the original DHR setup. Higher-form charged operators, topological defect lines, and categorical symmetries belong to later pages.

## Examples and non-examples

| Situation | Sector interpretation |
|---|---|
| Observable algebra with global charge superselection | Different total charges label sectors because observables commute with charge. |
| Gauge-invariant observable algebra $\mathcal F^G$ | Charged fields in $\mathcal F$ can transform between sectors, but they are not observables in $\mathcal A$. |
| DHR-localized charge | Charge is invisible outside a bounded region and defines a localized transportable endomorphism. |
| Electric charge in QED | Not DHR-localized because of long-range fields and Gauss-law constraints. |
| Two-dimensional anyonic sectors | Still superselection sectors, but the exchange structure is braided. |
| Different thermodynamic phases | Often inequivalent representations, but not necessarily DHR sectors of one vacuum theory. |

The table also shows why “sector” is a broad word. The DHR sector is a particular mathematically controlled kind of sector, not the only possible one.

## Common pitfalls

**A superselection sector is not just an eigenspace.** In finite examples it may look like an eigenspace of a central charge. In QFT the robust object is often an inequivalent representation or a localized endomorphism.

**A global symmetry representation is not the same as a sector.** A symmetry may act within a Hilbert space, while superselection concerns what the observable algebra can connect or distinguish. The two ideas are related but not identical.

**Charged fields need not be observables.** A charged field can map one sector to another. If it is not gauge invariant, it belongs to a field algebra, not to the observable algebra.

**DHR does not describe ordinary QED charge.** The DHR criterion assumes bounded localization. Long-range gauge fields violate this assumption.

**The reconstructed gauge group is not put in by hand.** In the Doplicher–Roberts result, the compact group is reconstructed from the tensor category of sectors, given the theorem's hypotheses.

## Relations to other pages

[States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/) explains why sectors are naturally representation-theoretic. [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/) supplies the reference vacuum representation used in DHR theory. Haag Duality will explain one of the duality assumptions that makes localized endomorphisms work cleanly.

The later DHR Theory Preview should develop the category-theoretic statements more systematically. The later Defects, Categories, and Extended QFT chapter will connect sector categories with defects, modular tensor categories, and non-invertible symmetry.

## Research status

The DHR analysis is a rigorous theorem-level achievement of algebraic QFT. It gives a precise reconstruction of compact gauge symmetry and charged fields from observable-algebra data under clear assumptions.

The active frontier is the scope of the paradigm. Gauge theories with massless particles, confinement, generalized symmetries, topological order, theories on nontrivial backgrounds, and non-invertible defects all require extensions or reinterpretations. The original DHR theory remains the clean reference point against which these generalizations are measured.

## Exercises

### Exercise 1

Let $\mathcal H=\mathcal H_1\oplus\mathcal H_2$ and let

$$
\mathcal A=B(\mathcal H_1)\oplus B(\mathcal H_2)
$$

act block diagonally. Show that a vector

$$
\Psi=\frac{1}{\sqrt2}(\psi_1+e^{i\theta}\psi_2)
$$

with unit vectors $\psi_i\in\mathcal H_i$ gives the same expectation values on $\mathcal A$ as the mixed state

$$
\omega_{\mathrm{mix}}(A)=
\frac12\langle\psi_1,A_1\psi_1\rangle
+
\frac12\langle\psi_2,A_2\psi_2\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Every observable has the form

$$
A=\begin{pmatrix}
A_1&0\\
0&A_2
\end{pmatrix}.
$$

Therefore

$$
\begin{aligned}
\langle\Psi,A\Psi\rangle
&=\frac12
\left\langle
\psi_1+e^{i\theta}\psi_2,
A_1\psi_1+e^{i\theta}A_2\psi_2
\right\rangle\\
&=\frac12\langle\psi_1,A_1\psi_1\rangle
+\frac12\langle\psi_2,A_2\psi_2\rangle.
\end{aligned}
$$

The cross terms vanish because $\mathcal H_1$ and $\mathcal H_2$ are orthogonal and $A$ has no off-diagonal components. The phase $e^{i\theta}$ is invisible to $\mathcal A$.

</details>

### Exercise 2

Let $\rho$ and $\sigma$ be endomorphisms localized in the same double cone $\mathcal O$, meaning

$$
\rho(A)=A,
\qquad
\sigma(A)=A
\qquad
(A\in\mathcal A(\mathcal O')).
$$

Show that $\rho\sigma$ is also localized in $\mathcal O$.

<details><summary><strong>Solution</strong></summary>

For $A\in\mathcal A(\mathcal O')$,

$$
(\rho\sigma)(A)=\rho(\sigma(A))=\rho(A)=A.
$$

Thus $\rho\sigma$ acts trivially on the algebra of the spacelike complement and is localized in the same region $\mathcal O$.

</details>

### Exercise 3

Let $T$ be an intertwiner from $\rho$ to $\sigma$:

$$
T\rho(A)=\sigma(A)T
\qquad (A\in\mathcal A).
$$

Show that if $T$ is unitary, then $\rho$ and $\sigma$ define unitarily equivalent representations $\pi_0\circ\rho$ and $\pi_0\circ\sigma$ in the vacuum Hilbert space.

<details><summary><strong>Solution</strong></summary>

In the vacuum representation, regard $T$ as represented by $\pi_0(T)$. The intertwining relation gives

$$
\pi_0(T)\pi_0(\rho(A))
=\pi_0(\sigma(A))\pi_0(T).
$$

If $T$ is unitary, then

$$
\pi_0(T)\,\pi_0(\rho(A))\,\pi_0(T)^{-1}
=\pi_0(\sigma(A)).
$$

Thus $\pi_0(T)$ is a unitary equivalence between $\pi_0\circ\rho$ and $\pi_0\circ\sigma$.

</details>

## References

### Standard first pass

- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory – an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).
- Hans Halvorson, "Algebraic Quantum Field Theory," arXiv: [math-ph/0602036](https://arxiv.org/abs/math-ph/0602036).

### DHR and reconstruction

- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local observables and particle statistics I," *Communications in Mathematical Physics* **23** (1971), 199–230. [doi:10.1007/BF01877742](https://doi.org/10.1007/BF01877742).
- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local observables and particle statistics II," *Communications in Mathematical Physics* **35** (1974), 49–85. [doi:10.1007/BF01646454](https://doi.org/10.1007/BF01646454).
- Sergio Doplicher and John E. Roberts, "Why there is a field algebra with a compact gauge group describing the superselection structure in particle physics," *Communications in Mathematical Physics* **131** (1990), 51–107. [doi:10.1007/BF02097680](https://doi.org/10.1007/BF02097680).
- Detlev Buchholz and Klaus Fredenhagen, "Locality and the structure of particle states," *Communications in Mathematical Physics* **84** (1982), 1–54. [doi:10.1007/BF01208370](https://doi.org/10.1007/BF01208370).
- Detlev Buchholz and Klaus Fredenhagen, "Algebraic Quantum Field Theory: Objectives, Methods, and Results," arXiv: [2305.12923](https://arxiv.org/abs/2305.12923).

## Version history

- **2026-06-28:** Initial polished draft.
