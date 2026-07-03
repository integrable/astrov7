---
title: "Relative QFT Preview"
description: "Introduces relative quantum field theories as boundary theories whose partition functions live in state spaces of a one-higher-dimensional topological theory."
sidebar:
  label: "Relative QFT Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Freed–Teleman; Freed; Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; modern SymTFT and relative-QFT references."
topics:
  - relative QFT
  - absolute QFT
  - anomaly theory
  - symmetry TFT
  - partition functions
  - boundary conditions
canonicalTopics:
  - relative-qft
  - absolute-qft
  - anomaly-theory
  - partition-function-line
  - symtft-boundary-pairing
researchStatus:
  established:
    - "An anomalous or symmetry-relative theory may assign a vector, line, or state in a bulk topological theory rather than a standalone number-valued partition function."
    - "Pairing a relative theory with an appropriate topological boundary condition can produce an absolute theory."
  active:
    - "Intrinsic relativeness, relative non-invertible symmetry, relative chiral algebras, and the classification of boundary completions are active research areas."
---

## Summary

An ordinary standalone QFT assigns a number to a closed spacetime, after all couplings, backgrounds, and spin/orientation structures have been specified:

$$
M_d
\quad\longmapsto\quad
Z_{\mathcal T}[M_d]\in\mathbb C.
$$

A **relative QFT** is different. It naturally lives as a boundary condition for a topological theory in one higher dimension. On a closed $d$-manifold $M_d$, it may assign not a number, but a vector or line in the state space of the bulk topological theory:

$$
M_d
\quad\longmapsto\quad
|Z_X[M_d]\rangle\in\mathcal H_{\mathcal Z}(M_d).
$$

To get a number, one must pair it with another state, often supplied by a topological boundary condition:

$$
Z_{X,\mathcal B}[M_d]
=
\langle \mathcal B[M_d]\,|\,Z_X[M_d]\rangle.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![A diagram comparing an absolute QFT that assigns a number to a closed spacetime with a relative QFT that assigns a vector in a SymTFT state space and becomes a number after pairing with a topological boundary state.](/figures/symmetry-anomalies-topology/relative-qft-pairing.svg)

<figcaption>

An absolute QFT produces a number-valued partition function on a closed spacetime. A relative QFT produces a state in the Hilbert space of a one-higher-dimensional topological theory. A topological boundary condition supplies a dual state, and the pairing gives an absolute partition function.

</figcaption>
</figure>

Relative QFT is the natural language for anomaly theories, self-dual fields, chiral theories, some global-form choices, and modern SymTFT descriptions. This page is a preview: it gives the idea, the notation, and the common pitfalls before the full machinery appears later.

## Prerequisites

Read [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/), [Bulk-Boundary Viewpoint](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/bulk-boundary-viewpoint/), [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/), [Invertible Field Theories](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/invertible-field-theories/), and [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/).

You should also know the basic idea of a topological field theory assigning state spaces to closed manifolds and linear maps to bordisms.

## Core idea

A $d$-dimensional QFT is **absolute** if it can be evaluated on a closed $d$-manifold by itself. It may depend on background fields, spin structure, orientation, or other geometric data, but after those data are chosen it returns a number.

A $d$-dimensional QFT is **relative to** a $(d+1)$-dimensional topological theory $\mathcal Z$ if it is naturally a boundary condition or boundary state for $\mathcal Z$. On a closed $M_d$, the relative theory returns an element of the bulk state space:

$$
|Z_X[M_d]\rangle\in\mathcal H_{\mathcal Z}(M_d).
$$

This is not a defect in the construction. It is the construction. The relative theory is not trying and failing to be absolute; it is defined relative to $\mathcal Z$.

To obtain an ordinary partition function, choose a dual vector

$$
\langle B[M_d]|\in\mathcal H_{\mathcal Z}(M_d)^*
$$

and pair:

$$
Z_{B,X}[M_d]=\langle B[M_d]|Z_X[M_d]\rangle.
$$

In the SymTFT slab, $X$ is the physical boundary and $B$ is the topological boundary.

## Absolute, anomalous, and relative

The words “absolute,” “anomalous,” and “relative” overlap, but they are not identical.

| Term | Meaning |
|---|---|
| Absolute QFT | A standalone theory with number-valued partition functions on closed spacetimes. |
| Anomalous QFT | A theory whose symmetry cannot be gauged or whose partition function transforms nontrivially under background gauge transformations. |
| Relative QFT | A theory whose partition function naturally lives in a state space or line of a higher-dimensional topological theory. |

An anomalous QFT is often relative to its anomaly theory. The anomaly theory may be invertible, in which case the state space is one-dimensional and the partition function is best viewed as a section of a line. For non-invertible or nontrivial SymTFTs, the state space can have dimension greater than one, and the relative nature is more visible.

The slogan is:

$$
\text{anomaly}
\quad
\Rightarrow
\quad
\text{partition function is not just a function}.
$$

It may be a section, a vector, or an object requiring pairing with bulk/topological data.

:::note[Source note: anomaly line]
In geometric anomaly theory, an anomalous partition function is often a section of a determinant or anomaly line bundle. The SymTFT generalizes this idea: the “line” may become a higher-dimensional state space of a topological theory.
:::

## The SymTFT slab interpretation

Let $\mathcal Z_{\mathrm{sym}}$ be the SymTFT. Place it on a slab

$$
M_d\times I.
$$

Let $X_{\mathrm{phys}}$ be the physical boundary and $\mathcal B_{\mathrm{top}}$ a topological boundary. The full slab partition function is a number:

$$
Z_{\mathcal Z_{\mathrm{sym}}}
\bigl[M_d\times I;\mathcal B_{\mathrm{top}},X_{\mathrm{phys}}\bigr]\in\mathbb C.
$$

But if we remove $\mathcal B_{\mathrm{top}}$, the physical boundary alone gives a state:

$$
|X_{\mathrm{phys}}[M_d]\rangle\in
\mathcal H_{\mathcal Z_{\mathrm{sym}}}(M_d).
$$

The topological boundary supplies the dual state

$$
\langle \mathcal B_{\mathrm{top}}[M_d]|.
$$

Thus

$$
Z_{\mathcal T_{\mathcal B}}[M_d]
=
\langle \mathcal B_{\mathrm{top}}[M_d]\,|\,X_{\mathrm{phys}}[M_d]\rangle.
$$

Different choices of $\mathcal B_{\mathrm{top}}$ produce different absolute theories from the same relative boundary. These choices can correspond to gauging, orbifolding, choosing a global form, adding discrete theta terms, or selecting a genuine-operator spectrum.

## Why relative theories appear

Relative theories appear whenever the data of a $d$-dimensional theory cannot be consistently made into a number without extra topological choices.

Common sources include:

1. **Anomalies.** A theory with an anomaly is naturally a boundary of an anomaly theory.
2. **Self-dual fields.** Chiral or self-dual $p$-form fields often have partition functions that require a polarization or higher-dimensional topological input.
3. **Chiral CFT.** A chiral half of a two-dimensional CFT often gives conformal blocks rather than a single modular-invariant partition function.
4. **Gauge group global form.** A Lie algebra may not specify a unique absolute gauge theory; additional electric/magnetic and discrete theta data are needed.
5. **Non-invertible symmetry.** A physical boundary may carry a categorical symmetry whose absolute completions correspond to different topological boundaries.
6. **Six-dimensional theories.** Some higher-dimensional theories are naturally described as relative because their partition functions depend on a choice of duality frame or polarization.

The shared feature is that the QFT wants to produce something more structured than a complex number.

## Polarization and basis choices

If $\mathcal H_{\mathcal Z}(M)$ has dimension greater than one, obtaining a number requires more than a phase convention. One must choose a state or basis. In many examples this is called a **polarization**.

A polarization is a choice of which mutually compatible observables are diagonalized. For finite abelian higher-form symmetry, it can look like choosing electric variables versus magnetic variables. In gauge theory, this is related to choosing a global form and line-operator spectrum. In chiral CFT, it is related to choosing how conformal blocks are combined into a modular-invariant full CFT.

This is one reason relative QFT is not merely “an anomalous theory with a phase ambiguity.” It can involve a genuine vector space of possibilities.

## Example: chiral conformal blocks

A rational chiral algebra often produces a finite-dimensional space of conformal blocks on a Riemann surface. A chiral theory by itself does not necessarily produce a single modular-invariant number. Instead, it produces a vector in the space of blocks.

A full two-dimensional CFT is obtained by pairing left-moving and right-moving data, or by choosing a modular-invariant combination. Schematically,

$$
Z_{\mathrm{full}}
=
\sum_{i,j} M_{ij}\,\chi_i(\tau)\,\overline{\chi_j(\tau)}.
$$

The matrix $M_{ij}$ is extra absolute-completion data. In topological language, it is related to choosing boundary or condensation data in a three-dimensional topological theory.

This example is pedagogically useful because it is familiar: the chiral piece is meaningful and powerful, but it is not always a standalone full local QFT.

## Example: Chern–Simons boundary theories

Chern–Simons theory on a three-manifold with boundary naturally assigns a state to the boundary. A boundary WZW or chiral algebra is relative to the bulk Chern–Simons theory.

If the three-manifold is a bordism from one Riemann surface to another, Chern–Simons theory gives a linear map between spaces of conformal blocks. The boundary theory inherits anomaly and modular properties from the bulk.

This is one of the historical roots of the relative viewpoint: a boundary theory can be perfectly meaningful while requiring a bulk topological theory to define its partition function unambiguously.

## Example: global form of gauge theory

A four-dimensional gauge theory specified only by a Lie algebra may not be absolute. To define the theory fully, one must specify the global form of the gauge group, allowed bundles, line operators, and sometimes discrete theta terms.

The SymTFT for the relevant one-form symmetry packages these choices. The physical boundary may be thought of as relative to the topological theory controlling the line-operator lattice. Choosing a topological boundary gives an absolute gauge theory such as an $SU(N)$ or $PSU(N)$ variant with a particular discrete theta angle.

The lesson is:

$$
\text{same local Lie algebra}
\quad \not\Rightarrow \quad
\text{same absolute QFT}.
$$

Relative language makes the missing topological data explicit.

## Intrinsically relative theories

Sometimes relativeness is a presentation choice: after selecting a boundary condition, polarization, or gauging convention, one obtains an ordinary absolute theory.

Sometimes the theory appears to be **intrinsically relative**: no standalone absolute version with the desired properties exists without coupling to the higher-dimensional topological theory. This situation is especially important in modern discussions of higher-dimensional theories, non-invertible symmetries, and chiral sectors.

The phrase “intrinsically relative” should be used with care. It depends on which structures one insists on preserving, which backgrounds are allowed, and what counts as a valid completion. The research literature is still refining this language.

:::caution[Preview caveat]
This page uses “relative” in the physics sense of Freed–Teleman, anomaly theory, and SymTFT. It is not claiming that every relative presentation is intrinsically relative, nor that every anomaly requires a non-invertible SymTFT. Later pages should state the precise category of theories and background structures under discussion.
:::

## Relative theories and gauging

Gauging can turn one absolute theory into another, but in the SymTFT picture both can arise from the same relative boundary paired with different topological boundaries.

Suppose $\mathcal B_1$ and $\mathcal B_2$ are two topological boundary conditions. Then

$$
Z_1[M]=\langle\mathcal B_1[M]|X[M]\rangle,
$$

and

$$
Z_2[M]=\langle\mathcal B_2[M]|X[M]\rangle.
$$

The two theories may be related by gauging a finite symmetry, gauging a higher-form symmetry, changing global form, or adding a discrete topological term. Instead of seeing gauging as an operation performed inside $d$ dimensions, the SymTFT sees it as changing which topological state pairs with the relative boundary.

This viewpoint is especially powerful when the symmetry is non-invertible and there is no ordinary group of backgrounds to sum over.

## Common pitfalls

**Thinking relative means inconsistent.** A relative QFT can be perfectly well-defined. It is defined as a boundary or state relative to a bulk topological theory.

**Thinking every anomalous theory has a fatal gauge anomaly.** ’t Hooft anomalies of global symmetries are allowed. They often mean the theory is relative to an anomaly theory when backgrounds are turned on.

**Forgetting the topological boundary.** In the SymTFT slab, the physical boundary alone may not produce a number. The topological boundary is part of the absolute completion.

**Confusing a line with a vector space.** Invertible anomaly theories often give one-dimensional state spaces, so the partition function is a section of a line. Non-invertible and nontrivial SymTFTs can give higher-dimensional state spaces.

**Assuming the word relative is standardized in every subfield.** The core idea is stable, but conventions differ between anomaly theory, condensed matter, chiral CFT, higher-form symmetry, and recent SymTFT literature.

## Relations to other pages

[Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) explains how topological boundary conditions choose absolute theories.

[Defects from the Bulk](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/defects-from-the-bulk/) explains how bulk defects act on physical boundary objects and how endability depends on boundary choice.

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) explains the invertible-anomaly case, where the relative partition function often lives in a line.

[Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/) gives the slab picture used throughout this page.

## Research status

Relative QFT is an established concept in anomaly theory, Chern–Simons/WZW relations, chiral conformal blocks, self-dual fields, and global-form questions. The SymTFT language has made the idea more visible by treating many absolute theories as different pairings of a common relative boundary with different topological boundaries.

Active research includes intrinsic relativeness, relative non-invertible symmetries, relative chiral algebras, boundary SymTFT, generalized charges, and the classification of allowed absolute completions. The broad picture is stable; the most general formalism is still evolving.

## Exercises

### Exercise 1: Number versus vector

Explain the difference between

$$
Z_{\mathcal T}[M]\in\mathbb C
$$

and

$$
|Z_X[M]\rangle\in\mathcal H_{\mathcal Z}(M).
$$

<details><summary><strong>Solution</strong></summary>

The first expression is a number-valued partition function of an absolute QFT. Once the background data are specified, it can be evaluated on the closed manifold $M$ by itself.

The second expression is a state in the Hilbert space assigned to $M$ by a higher-dimensional topological theory $\mathcal Z$. It is not a number until it is paired with a dual state, such as one supplied by a topological boundary condition. This is the hallmark of a relative QFT.

</details>

### Exercise 2: Pairing with a boundary

Suppose $\mathcal H_{\mathcal Z}(M)$ is two-dimensional with basis $|0\rangle,|1\rangle$. A relative theory gives

$$
|Z_X[M]\rangle=a|0\rangle+b|1\rangle.
$$

A topological boundary gives

$$
\langle B|=\alpha\langle 0|+\beta\langle 1|.
$$

Assuming the basis is orthonormal, compute the absolute partition function.

<details><summary><strong>Solution</strong></summary>

The pairing is

$$
Z_{B,X}[M]=\langle B|Z_X[M]\rangle
=
(\alpha\langle 0|+\beta\langle 1|)(a|0\rangle+b|1\rangle).
$$

Using orthonormality,

$$
Z_{B,X}[M]=\alpha a+\beta b.
$$

Different choices of $\alpha,\beta$ give different absolute completions.

</details>

### Exercise 3: Chiral blocks

Why is a chiral conformal block naturally closer to a relative partition function than to an absolute partition function?

<details><summary><strong>Solution</strong></summary>

A chiral conformal block is one vector in a space of blocks. It usually transforms nontrivially under modular transformations and does not by itself define a single modular-invariant full CFT partition function. To get a full two-dimensional CFT partition function, one must choose how to pair chiral and anti-chiral blocks, or more generally choose modular-invariant completion data. This is analogous to pairing a relative state with another state to get a number.

</details>

## References

- Freed and Teleman, “Relative Quantum Field Theory,” for the general notion of QFTs defined relative to one-higher-dimensional topological theories.
- Freed, “Anomalies and Invertible Field Theories,” for anomalous partition functions as objects controlled by invertible anomaly theories.
- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for the QFT–TQFT coupling viewpoint and global-form applications.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for background fields, gauging, anomaly inflow, and generalized symmetry.
- Witten, “Quantum Field Theory and the Jones Polynomial,” for Chern–Simons theory, boundary conformal blocks, and topological state spaces.
- Recent SymTFT literature on boundary SymTFT, defect charges, intrinsic relativeness, and non-invertible symmetry for modern developments.

## Version history

- **2026-06-20:** Initial polished preview. Added absolute/relative distinction, slab pairing formula, anomaly-line viewpoint, chiral block example, Chern–Simons boundary example, global-form example, intrinsic-relativeness caveats, and exercises.
