---
title: "Anomalies and Symmetry-Protected Phases"
description: "Explains how ’t Hooft anomalies are encoded by one-higher-dimensional symmetry-protected phases and what this means for boundaries and RG flow."
sidebar:
  label: "Anomalies and SPT Phases"
  order: 7
level: Advanced
status: "Polished draft"
source: "’t Hooft anomalies, anomaly inflow, SPT phases, group cohomology, and cobordism literature."
topics:
  - ’t Hooft anomalies
  - symmetry-protected topological phases
  - anomaly inflow
  - invertible field theories
  - boundary constraints
canonicalTopics:
  - thooft-anomalies
  - anomaly-inflow
  - symmetry-protected-topological-phases
  - invertible-topological-field-theory
researchStatus:
  established:
    - "A d-dimensional ’t Hooft anomaly can be represented by a (d+1)-dimensional invertible anomaly theory whose boundary variation cancels the anomalous variation of the d-dimensional theory."
  active:
    - "The most general classification of interacting bosonic, fermionic, crystalline, and higher-symmetry SPT phases uses refined generalized-cohomology, bordism, and categorical tools; this page explains the QFT-facing anomaly logic rather than attempting a full classification."
---

## Summary

A **symmetry-protected topological phase**, or **SPT phase**, is a gapped phase with no intrinsic topological order that becomes deformable to a trivial product-like phase once the protecting symmetry is forgotten. The word *protected* is doing real work: the phase is invisible to ordinary local order parameters, but the symmetry prevents it from being trivialized.

A **’t Hooft anomaly** in a $d$-dimensional QFT is an obstruction to gauging a global symmetry. Modern language packages that obstruction as a $(d+1)$-dimensional **invertible topological theory** depending on background fields. The anomalous $d$-dimensional theory can consistently live as the boundary of that $(d+1)$-dimensional theory. The bulk variation cancels the boundary variation.

The bridge is:

$$
\text{SPT bulk in }d+1\text{ dimensions}
\quad\Longleftrightarrow\quad
\text{’t Hooft anomaly of a }d\text{-dimensional boundary}.
$$

This page explains that bridge. It is not a full classification of SPT phases. It is the QFT lesson: anomalies, boundary obstructions, and protected bulk phases are three faces of the same structure.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Anomaly inflow between an SPT bulk and an anomalous boundary](/figures/symmetry-anomalies-topology/spt-anomaly-boundary-dictionary.svg)

<figcaption>

A $d$-dimensional anomalous boundary theory can be a boundary condition for a $(d+1)$-dimensional invertible SPT/anomaly theory. The anomalous boundary variation is canceled by the bulk inflow variation.

</figcaption>
</figure>

## Prerequisites

You should already know the distinction between gauge redundancy and global symmetry, the background-field definition of a ’t Hooft anomaly, and the anomaly-inflow picture from the previous pages in this chapter. It is also useful to have seen finite-group gauging from the Background Fields and Gauging chapter and spin/Pin caveats from the Discrete, Spacetime, and Antiunitary Symmetries chapter.

## Core idea

A non-anomalous $d$-dimensional QFT with global symmetry $G$ has a partition function $Z_d[M_d,A]$ that is invariant under background gauge transformations of $A$, possibly after choosing a convention for local counterterms.

An anomalous theory fails this test:

$$
Z_d[M_d,A^g]
=
\exp\!\bigl(i\alpha_g[M_d,A]\bigr)
Z_d[M_d,A].
$$

The phase $\alpha_g$ is not an arbitrary defect of notation. If it cannot be removed by a local $d$-dimensional counterterm, it is the anomaly. The inflow statement says that there exists a $(d+1)$-dimensional invertible theory with partition function

$$
Z_{d+1}^{\mathrm{anom}}[X_{d+1},A]
=
\exp\!\bigl(iS_{d+1}^{\mathrm{top}}[X_{d+1},A]\bigr)
$$

such that, when $\partial X_{d+1}=M_d$,

$$
Z_{d+1}^{\mathrm{anom}}[X_{d+1},A^g]Z_d[M_d,A^g]
=
Z_{d+1}^{\mathrm{anom}}[X_{d+1},A]Z_d[M_d,A].
$$

The boundary is not gauge invariant by itself. The bulk is not gauge invariant on a manifold with boundary by itself. The combined bulk–boundary system is gauge invariant.

This is the most important point of the page: **an anomaly is not a failure of the combined system. It is the statement that the boundary theory is not an autonomous symmetric theory unless the inflow bulk is included or the IR realizes the anomaly in some other way.**

## Setup and conventions

Throughout this page, $d$ denotes the spacetime dimension of the boundary QFT. The inflow or anomaly theory lives in spacetime dimension $d+1$.

For a continuous internal symmetry, $A$ is an ordinary background connection. For a finite internal symmetry, $A$ should be thought of as a flat $G$ bundle, equivalently a map

$$
A:M\to BG,
$$

where $BG$ is the classifying space of $G$. For spacetime symmetries, time reversal, reflection, or fermionic systems, the background data may also include metric, orientation, spin, Pin, or related tangential structures.

:::note[Source and convention note]
The words *SPT phase*, *invertible phase*, and *anomaly theory* are not always used identically across high-energy, condensed-matter, and mathematical literature. Here an **SPT bulk** is a physical gapped invertible phase protected by symmetry, while an **anomaly theory** is the one-higher-dimensional invertible field theory that records the anomaly of a boundary QFT. Often they are the same mathematical object, but their physical roles are different.
:::

## SPT phases as invertible bulk theories

A topologically ordered phase may have long-range entanglement, anyons, degenerate ground states on closed spatial manifolds, and a non-invertible low-energy TQFT. An SPT phase is subtler. It has no intrinsic topological order. On a closed spatial manifold, its ground state is unique in the simplest cases, and its bulk excitations are not fractionalized in the same way as in a topologically ordered phase.

Yet it is not trivial as a symmetric phase. The distinction appears in how the theory responds to background symmetry fields.

For an SPT bulk in spacetime dimension $d+1$, the low-energy partition function on a closed manifold $X_{d+1}$ has the schematic form

$$
Z_{\mathrm{SPT}}[X_{d+1},A]
=\exp\!\bigl(iS_{\mathrm{top}}[X_{d+1},A]\bigr),
$$

where $S_{\mathrm{top}}$ depends only on topology, background fields, and possible spin/Pin/geometric structures. Since the theory is **invertible**, stacking it with its inverse gives a trivial phase:

$$
Z_{\mathrm{SPT}}Z_{\mathrm{SPT}}^{-1}=1.
$$

This invertibility is why SPT phases are perfect anomaly carriers. They supply phases, not sums over internal topological sectors.

## Finite internal symmetry and group cohomology

For a bosonic finite internal symmetry $G$, many SPT phases are described by group-cohomology classes

$$
\omega\in H^{d+1}(BG,U(1)).
$$

Given a flat $G$ background $A:X_{d+1}\to BG$, the bulk action is the evaluation of $\omega$ on $X_{d+1}$:

$$
Z_{\omega}[X_{d+1},A]
=\exp\!\left(2\pi i\int_{X_{d+1}}A^*\omega\right).
$$

On a closed manifold, this is gauge invariant. On a manifold with boundary, changing the cocycle representative or applying a background gauge transformation can leave a boundary phase. That boundary phase is precisely the finite-group ’t Hooft anomaly of the boundary theory.

This is the finite-group version of descent. Instead of differential forms and Chern–Simons forms, one uses cochains, cocycles, and coboundaries.

Group cohomology is not the final word. It misses some bosonic phases involving gravitational response, and it is not the natural language for fermionic phases or antiunitary/spacetime symmetries. A more robust classification uses bordism or generalized-cohomology data of the relevant background structure.

The practical QFT lesson is independent of the full classification technology:

$$
\text{anomaly class}
=
\text{invertible bulk response class}.
$$

The details of the cohomology theory tell you **which** invertible responses exist. The anomaly logic tells you **how** they constrain the boundary.

## Boundary anomaly as protected nontriviality

Imagine a symmetric gapped bulk with boundary. If the bulk is trivial, the boundary can be trivially gapped without degeneracy, without breaking symmetry, and without topological order. If the bulk is a nontrivial SPT, a completely trivial symmetric boundary is forbidden.

The boundary must do at least one of the following:

| Boundary behavior | How it matches the anomaly |
|---|---|
| Gapless degrees of freedom | The anomalous Ward identities are realized by massless boundary modes. |
| Symmetry breaking | The protecting symmetry is not preserved in the boundary state. |
| Intrinsic topological order | Fractionalized boundary anyons or defects carry the anomaly. |
| Relative theory | The boundary is not standalone and is defined only with the bulk. |

This table is the SPT version of anomaly matching. The anomaly does not say which row must occur. It says that the row “trivial symmetric gapped boundary with no topological order” is not allowed.

### A one-dimensional boundary diagnostic

The simplest finite-group example is a $0+1$-dimensional boundary of a $1+1$-dimensional bosonic SPT. A projective representation of $G$ on the boundary Hilbert space satisfies

$$
U_gU_h=\omega(g,h)U_{gh},
$$

where $\omega(g,h)$ is a $U(1)$ two-cocycle. Rephasing $U_g\mapsto \lambda(g)U_g$ changes $\omega$ by a coboundary, so only the class

$$
[\omega]\in H^2(G,U(1))
$$

is invariant. This projective edge action is the boundary shadow of a $1+1$-dimensional SPT response. A lone boundary carrying a nontrivial projective representation cannot be realized as a unique symmetric short-range-entangled $0+1$-dimensional system by itself.

## Difference between an SPT bulk and an anomalous QFT

It is tempting to say “the anomaly is the SPT.” That slogan is useful but a little too fast.

An SPT phase is a bulk quantum system. It has a Hilbert space, boundary conditions, possible microscopic realizations, and a gapped bulk. An anomaly of a $d$-dimensional QFT is an obstruction class attached to its symmetry action. The two are related because the anomaly class can be represented by the partition function of a $(d+1)$-dimensional invertible theory.

A good dictionary is:

| Boundary/QFT language | Bulk/SPT language |
|---|---|
| Background variation of $Z_d[M_d,A]$ | Boundary variation of $S_{d+1}^{\mathrm{top}}$ |
| Obstruction to gauging $G$ | Nontrivial response to $G$ background |
| Anomaly matching along RG | Invariance of the bulk response under boundary deformations |
| Boundary cannot be trivially symmetric and gapped | Nontrivial SPT has protected boundary behavior |
| Local counterterm ambiguity | Choice of representative of the bulk response class |

The dictionary is powerful because it moves an obstruction in $d$ dimensions into an ordinary topological action in $d+1$ dimensions.

## Continuous examples and Chern–Simons inflow

For continuous symmetries, the inflow action often resembles a Chern–Simons term. A two-dimensional chiral boundary current anomaly for a background $U(1)$ field can be canceled by a three-dimensional bulk term

$$
S_{\mathrm{bulk}}[A]
=\frac{k}{4\pi}\int_{X_3} A\wedge dA.
$$

Under $A\mapsto A+d\lambda$, this changes by a boundary term:

$$
\delta_\lambda S_{\mathrm{bulk}}
=\frac{k}{4\pi}\int_{\partial X_3}\lambda\,dA,
$$

up to convention-dependent orientation signs. The boundary theory has the opposite anomalous variation.

:::note[Source and convention note]
For Chern–Simons inflow, orientation and background-field normalization affect signs and factors of $2$. This volume uses $D_\mu=\partial_\mu-iA_\mu$ for a unit-charge field and writes the abelian Chern–Simons level as $\frac{k}{4\pi}\int A\wedge dA$ when $A$ has standard $2\pi$ flux quantization. Some condensed-matter references absorb electric charge or Hall conductivity factors into $A$.
:::

## Fermionic and antiunitary refinements

Fermionic SPT phases require fermion parity $(-1)^F$ and usually a choice of spin structure. Time reversal and reflection may require Pin structures. This matters because some response terms are not defined on arbitrary oriented manifolds.

For example, a fermionic invertible phase may have a partition function depending on a spin structure $\eta$:

$$
Z[X,\eta].
$$

A theory with such dependence cannot be faithfully described by bosonic group cohomology alone. Its boundary anomaly is a **fermionic anomaly**, not merely a finite-group cocycle for an ordinary bosonic symmetry.

## Gauging and the SPT response

If a standalone boundary theory has a ’t Hooft anomaly, one cannot gauge its global symmetry by summing over background fields in $d$ dimensions. But a combined bulk–boundary system may be gaugeable, because the bulk cancels the boundary anomaly.

For a finite group $G$, gauging the bulk SPT can produce a Dijkgraaf–Witten-type topological gauge theory in the bulk. Its boundary inherits a consistent gauged description only together with the bulk. This is a crisp way to remember the difference between:

$$
\text{gauging an anomalous boundary alone}
\quad\text{and}\quad
\text{gauging the anomaly-free bulk–boundary pair}.
$$

The first operation is obstructed. The second can be well-defined.

## Common pitfalls

**Pitfall 1: Calling every topological phase an SPT phase.**

An SPT phase is short-range entangled and invertible. Intrinsic topological order is not an SPT phase, although it can appear on the anomalous boundary of an SPT.

**Pitfall 2: Forgetting that the symmetry is part of the definition.**

A nontrivial SPT can become trivial when the protecting symmetry is ignored or explicitly broken.

**Pitfall 3: Treating anomaly inflow as optional decoration.**

Inflow is not just a picture. It is the precise statement that a non-invariant boundary partition function can be completed by a one-higher-dimensional invertible response.

**Pitfall 4: Confusing gauge anomalies with ’t Hooft anomalies.**

A gauge anomaly makes a gauge theory inconsistent unless canceled. A ’t Hooft anomaly for a global symmetry is allowed and constrains the IR.

**Pitfall 5: Assuming group cohomology is always enough.**

It is an excellent first model for finite internal bosonic symmetries. It is not the universal classification language for fermions, time reversal, reflection, higher symmetries, or gravitational responses.

## Relations to other pages

This page refines the anomaly-inflow preview by explaining why the inflow bulk is often interpreted as an SPT or invertible topological phase. It prepares the Examples of Anomaly Matching page, where SPT-style anomaly constraints appear in concrete systems. It also links forward to Topological Terms, Symmetry TFT and Anomaly Inflow, and Symmetry in Phases of Matter.

## Research status

The equivalence between ’t Hooft anomaly classes and one-higher-dimensional invertible anomaly theories is a standard organizing principle in modern QFT. The broad classification of interacting SPT phases, especially with fermions, crystalline symmetry, higher-form symmetry, subsystem symmetry, or non-invertible symmetry, remains an active research area.

For this volume, the key stable result is not a final classification table. It is the conceptual mechanism:

$$
\text{boundary anomaly} + \text{bulk SPT response} = \text{gauge-invariant combined system}.
$$

## Exercises

### Exercise 1: Projective edge representation

Let a quantum-mechanical boundary Hilbert space carry operators $U_g$ satisfying

$$
U_gU_h=\omega(g,h)U_{gh}.
$$

Show that associativity implies the two-cocycle condition for $\omega$.

<details><summary><strong>Solution</strong></summary>

Associativity requires

$$
(U_gU_h)U_k=U_g(U_hU_k).
$$

Using the projective multiplication law, the left side is

$$
(U_gU_h)U_k
=\omega(g,h)U_{gh}U_k
=\omega(g,h)\omega(gh,k)U_{ghk}.
$$

The right side is

$$
U_g(U_hU_k)
=\omega(h,k)U_gU_{hk}
=\omega(h,k)\omega(g,hk)U_{ghk}.
$$

Thus

$$
\omega(g,h)\omega(gh,k)=\omega(h,k)\omega(g,hk),
$$

which is precisely the two-cocycle condition.

</details>

### Exercise 2: Rephasing and coboundaries

Under $U_g\mapsto \lambda(g)U_g$, find the transformation of $\omega(g,h)$.

<details><summary><strong>Solution</strong></summary>

Define $U'_g=\lambda(g)U_g$. Then

$$
U'_gU'_h
=\lambda(g)\lambda(h)\omega(g,h)U_{gh}
=\frac{\lambda(g)\lambda(h)}{\lambda(gh)}\omega(g,h)U'_{gh}.
$$

Therefore

$$
\omega'(g,h)=\frac{\lambda(g)\lambda(h)}{\lambda(gh)}\omega(g,h).
$$

This is multiplication by a coboundary. The cohomology class $[\omega]\in H^2(G,U(1))$ is invariant.

</details>

### Exercise 3: Boundary fates

Suppose a $d$-dimensional boundary has a nonzero ’t Hooft anomaly for an unbroken symmetry $G$. Explain why a unique symmetric gapped boundary with no intrinsic topological order cannot be the full IR description.

<details><summary><strong>Solution</strong></summary>

A unique symmetric gapped boundary with no intrinsic topological order is, at long distance, a trivial theory. A trivial theory has a gauge-invariant partition function for background $G$ fields and therefore has zero anomaly. But anomaly matching says the UV anomaly class is invariant under symmetry-preserving RG flow. If the UV boundary anomaly is nonzero, the IR cannot be the trivial symmetric gapped theory. The IR must instead be gapless, break $G$, contain intrinsic topological order, or remain a relative theory attached to an inflow bulk.

</details>

## References

- G. ’t Hooft, “Naturalness, chiral symmetry, and spontaneous chiral symmetry breaking,” in *Recent Developments in Gauge Theories*.
- X. Chen, Z.-C. Gu, Z.-X. Liu, and X.-G. Wen, “Symmetry protected topological orders and the group cohomology of their symmetry group.”
- A. Kapustin, “Symmetry protected topological phases, anomalies, and cobordisms: beyond group cohomology.”
- A. Kapustin, R. Thorngren, A. Turzillo, and Z. Wang, “Fermionic symmetry protected topological phases and cobordisms.”
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized global symmetries.”
- E. Witten, “Fermion path integrals and topological phases.”
- D. S. Freed and M. J. Hopkins, “Reflection positivity and invertible topological phases.”

## Version history

- 2026-06-18: First polished draft. Introduced the SPT/anomaly dictionary, finite-group and continuous examples, fermionic refinements, boundary constraints, and exercises.
