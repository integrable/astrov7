---
title: "Anomaly Inflow: Preview"
description: "Introduces anomaly inflow as the bulk–boundary mechanism that cancels the background variation of an anomalous theory by a one-higher-dimensional invertible field theory."
sidebar:
  label: "Anomaly Inflow: Preview"
  order: 5
level: Advanced
status: "Polished draft"
source: "Callan–Harvey anomaly inflow; descent equations; Chern–Simons terms; Wess–Zumino–Witten terms; invertible phases; Gaiotto–Kapustin–Seiberg–Willett; Freed–Hopkins."
topics:
  - anomaly inflow
  - thooft anomalies
  - invertible field theories
  - background fields
  - descent equations
  - boundary anomalies
  - symmetry protected phases
canonicalTopics:
  - anomaly-inflow
  - bulk-boundary-anomaly-cancellation
  - invertible-anomaly-theory
  - relative-qft
  - descent-and-inflow
researchStatus:
  established:
    - "Perturbative local anomalies can be cancelled by inflow from one-higher-dimensional Chern–Simons-type actions whose variations are fixed by descent."
    - "A modern ’t Hooft anomaly can often be represented as an invertible one-higher-dimensional anomaly theory whose boundary variation cancels the anomalous boundary response."
  active:
    - "For fermionic, crystalline, non-invertible, subsystem, and fully extended generalized symmetries, the precise inflow object may require spin/Pin, bordism, categorical, or symmetry-TFT data beyond ordinary anomaly polynomials."
---

## Summary

**Anomaly inflow** is the mechanism by which an anomalous $d$-dimensional theory becomes consistent as the boundary of a $(d+1)$-dimensional bulk theory. The boundary theory still has a ’t Hooft anomaly as a standalone theory. The combined bulk–boundary system is gauge invariant because the bulk variation cancels the boundary variation.

Schematically, let $M_d=\partial X_{d+1}$ and let $A$ denote background fields for an exact symmetry $G$. If the boundary partition function transforms as

$$
Z_{\partial}[M_d,A^g]
=
\exp\!\left(2\pi i\,\mathcal A_g[M_d,A]\right)
Z_{\partial}[M_d,A],
$$

then inflow supplies a bulk functional $Z_{\rm bulk}[X_{d+1},A]$ with the opposite variation:

$$
Z_{\rm bulk}[X_{d+1},A^g]
=
\exp\!\left(-2\pi i\,\mathcal A_g[M_d,A|_{M_d}]\right)
Z_{\rm bulk}[X_{d+1},A].
$$

The product

$$
Z_{\rm bulk}[X_{d+1},A]Z_{\partial}[M_d,A|_{M_d}]
$$

is then gauge invariant.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram of anomaly inflow. A boundary partition function transforms by an anomalous phase, while a one-higher-dimensional bulk transforms by the inverse phase, so the bulk-boundary product is invariant.](/figures/symmetry-anomalies-topology/anomaly-inflow-bulk-boundary.svg)

<figcaption>

Anomaly inflow turns an anomalous boundary response into a consistent bulk–boundary system. The boundary anomaly is not erased; it is cancelled by the opposite variation of the bulk anomaly theory.

</figcaption>
</figure>

## Prerequisites

Read [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/), [Obstruction to Gauging](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/obstruction-to-gauging/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) first.

You should also know the distinction between a [Background Field Versus Dynamical Gauge Field](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) and the role of boundary terms in [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

## Core idea

A $d$-dimensional ’t Hooft anomaly says that the partition function cannot be made into an honest gauge-invariant function of background fields. Inflow says that this failure can itself be the boundary variation of a $(d+1)$-dimensional invertible theory.

The slogan is

$$
\text{anomaly} = \text{boundary variation of an invertible bulk}.
$$

This slogan should be read carefully. Inflow does **not** mean that the boundary theory has secretly become anomaly-free. It means that the boundary theory is not being asked to stand alone. The combined object is the honest gauge-invariant object.

A good mental picture is a bookkeeping ledger. The boundary has an anomalous variation. The bulk carries the opposite entry. The total balance is zero:

$$
\delta_g W_{\partial}[A]
+
\delta_g S_{\rm bulk}[A]
=0.
$$

This is why anomaly inflow is the natural language for boundaries of symmetry-protected topological phases, chiral edge modes of quantum Hall systems, topological-insulator surfaces, Wess–Zumino–Witten terms, domain-wall fermions, and modern symmetry TFT.

## Setup and conventions

Let $X_{d+1}$ be a manifold with boundary

$$
\partial X_{d+1}=M_d.
$$

Let $A$ denote background fields for a global symmetry $G$. This may mean an ordinary connection, a flat finite-group bundle, a higher-form background, a spin or Pin structure, or a package of several pieces of geometric data.

The boundary theory has a background-field partition function

$$
Z_{\partial}[M_d,A|_{M_d}].
$$

If $G$ has an anomaly, then under a background gauge transformation $g$,

$$
Z_{\partial}[M_d,A^g]
=
\exp\!\left(2\pi i\mathcal A_g[M_d,A]\right)
Z_{\partial}[M_d,A].
$$

An inflow theory is a $(d+1)$-dimensional bulk theory whose partition function has the inverse boundary variation:

$$
Z_{\rm bulk}[X_{d+1},A^g]
=
\exp\!\left(-2\pi i\mathcal A_g[M_d,A|_{M_d}]\right)
Z_{\rm bulk}[X_{d+1},A].
$$

Then

$$
Z_{\rm total}[X_{d+1},M_d,A]
=
Z_{\rm bulk}[X_{d+1},A]
Z_{\partial}[M_d,A|_{M_d}]
$$

is gauge invariant.

:::note[Convention-sensitive source note]
Some sources define the anomaly as $\delta W$, others as the phase multiplying $Z=e^{iW}$, and still others work in Euclidean signature with $Z=e^{-W_E}$. This page fixes the sign of the inflow action by the cancellation condition

$$
\delta_g W_{\partial}+\delta_g S_{\rm bulk}=0.
$$

If a reference defines the anomaly with the opposite sign, the displayed bulk action is reversed. The physics is unchanged.
:::

## The descent picture for local anomalies

For perturbative local anomalies, inflow is beautifully organized by descent equations. Suppose a $d$-dimensional anomaly is encoded by a closed characteristic form

$$
I_{d+2}.
$$

Locally one writes

$$
I_{d+2}=dI_{d+1}^{(0)},
$$

where $I_{d+1}^{(0)}$ is a Chern–Simons-like form. Under an infinitesimal background gauge transformation with parameter $\lambda$,

$$
\delta_\lambda I_{d+1}^{(0)}=dI_d^{(1)}(\lambda).
$$

A boundary anomaly of the form

$$
\delta_\lambda W_{\partial}
=
-2\pi\int_{M_d}I_d^{(1)}(\lambda)
$$

is cancelled by the bulk inflow action

$$
S_{\rm inflow}=2\pi\int_{X_{d+1}}I_{d+1}^{(0)}.
$$

Indeed,

$$
\delta_\lambda S_{\rm inflow}
=
2\pi\int_{X_{d+1}}dI_d^{(1)}(\lambda)
=
2\pi\int_{M_d}I_d^{(1)}(\lambda),
$$

so that

$$
\delta_\lambda\left(W_{\partial}+S_{\rm inflow}\right)=0.
$$

This is the local-anomaly version of the bulk–boundary cancellation. It is the same descent tower that appeared in the anomaly-polynomial chapter, now interpreted as a physical inflow mechanism.

## Example: Chern–Simons inflow onto a chiral edge

The simplest model to keep in your bones is a three-dimensional Abelian Chern–Simons term on a manifold $X_3$ with boundary $M_2$:

$$
S_{\rm CS}[A]
=
\frac{k}{4\pi}\int_{X_3} A\wedge dA.
$$

Under $A\mapsto A+d\lambda$,

$$
\delta_\lambda S_{\rm CS}
=
\frac{k}{4\pi}\int_{X_3}d\lambda\wedge dA
=
\frac{k}{4\pi}\int_{M_2}\lambda\,dA.
$$

This boundary variation is not a bug. It is exactly the inflow that can cancel the anomaly of chiral edge degrees of freedom on $M_2$.

The same idea underlies the edge of an integer quantum Hall state. The two-dimensional edge theory by itself has a chiral anomaly in the background electromagnetic field. The three-dimensional bulk Chern–Simons response varies by the opposite amount. The combined bulk plus edge is gauge invariant.

:::note[Normalization warning]
The coefficient $k/4\pi$ assumes a standard Abelian Chern–Simons normalization. Large gauge invariance quantizes $k$ under appropriate assumptions on the background and spacetime topology. With spin structures, fermionic systems can allow refinements such as half-integer effective levels after the spin/eta-invariant data are included. Those refinements belong to the topological-terms and symmetry-TFT chapters.
:::

## Example: four-dimensional chiral anomalies from five dimensions

A four-dimensional chiral fermion with global symmetry $G$ can have a perturbative ’t Hooft anomaly encoded by a six-form anomaly polynomial $I_6$. Locally,

$$
I_6=dI_5^{(0)},
\qquad
\delta_\lambda I_5^{(0)}=dI_4^{(1)}(\lambda).
$$

The four-dimensional anomaly is represented by

$$
\delta_\lambda W_{4d}
=-2\pi\int_{M_4}I_4^{(1)}(\lambda),
$$

and the five-dimensional inflow action is

$$
S_{5d}=2\pi\int_{X_5}I_5^{(0)}.
$$

The combined variation vanishes. This is often the cleanest way to understand why anomaly matching works: the same five-dimensional inflow theory must be attachable to the UV and to any symmetry-preserving IR description.

Do not confuse this five-dimensional action with a new propagating fifth dimension in the original four-dimensional theory. It is a representation of the anomaly class. In condensed-matter applications, it can be a physical bulk. In purely relativistic QFT applications, it may be an auxiliary anomaly theory used to package the obstruction.

## Domain-wall fermions and the Callan–Harvey mechanism

Historically, anomaly inflow became concrete in systems where fermions are localized on a defect. Imagine a massive fermion in an odd-dimensional spacetime whose mass changes sign across a domain wall. The wall can support lower-dimensional chiral zero modes.

The chiral wall modes have an anomaly if viewed alone. But the massive bulk fermions generate a Chern–Simons-like effective action whose gauge variation flows into the wall and cancels the wall anomaly. This is the Callan–Harvey mechanism.

The lesson is broad:

$$
\text{anomalous defect modes}
+
\text{bulk topological response}
=
\text{consistent total system}.
$$

That same logic reappears in topological insulators, quantum Hall systems, domain walls in gauge theories, fermion lattice constructions, and modern defect field theory.

## Invertible bulk theories

The bulk theory used for inflow is often **invertible**. Informally, an invertible theory has no intrinsic topological order: its Hilbert spaces are one-dimensional on closed spatial manifolds, and it has an inverse under stacking.

Invertibility matters because an anomaly is not supposed to introduce arbitrary new long-distance degrees of freedom. It is obstruction data. A non-invertible topological order can also live in a bulk, but the minimal object that represents a pure anomaly is invertible.

This gives a modern formulation:

$$
\text{’t Hooft anomaly in }d\text{ dimensions}
=
\text{invertible field theory in }d+1\text{ dimensions}.
$$

This statement is a preview, not a replacement for the detailed symmetry-TFT chapter. For local perturbative anomalies, the invertible theory is often represented by a Chern–Simons form. For global and fermionic anomalies, it may be represented by eta invariants, spin/Pin bordism invariants, or other global topological data.

## Relative theories and anomaly lines

There is a slightly more precise way to say what inflow does.

For an anomalous boundary theory, $Z_{\partial}[A]$ may fail to be a number. Instead, it behaves like a vector in a one-dimensional complex line that depends on the background:

$$
Z_{\partial}[M_d,A]\in \mathcal L_{M_d,A}.
$$

The bulk inflow theory supplies an element of the dual line,

$$
Z_{\rm bulk}[X_{d+1},A]\in \mathcal L_{M_d,A}^{-1},
$$

so their product is an honest number.

This is why anomalous QFTs are sometimes called **relative** QFTs: they are defined relative to an anomaly theory in one higher dimension. In ordinary textbook cases, one can ignore this language and just compute the anomalous Ward identity. In modern generalized-symmetry problems, the relative viewpoint is often the cleanest one.

## Inflow versus cancellation by another boundary sector

There are two common ways to cancel an anomaly:

1. Add another $d$-dimensional sector with the opposite anomaly.
2. Attach the anomalous theory to a $(d+1)$-dimensional inflow theory.

The first makes a standalone $d$-dimensional theory anomaly-free. If

$$
[\mathcal A_1]+[\mathcal A_2]=0,
$$

then $\mathcal T_1\times\mathcal T_2$ can be gaugeable as a $d$-dimensional system.

The second makes a **bulk–boundary pair** gauge invariant. The boundary by itself remains anomalous. The distinction is essential:

$$
\begin{aligned}
\text{boundary + opposite boundary} &\Rightarrow \text{standalone anomaly-free theory},\\
\text{boundary + inflow bulk} &\Rightarrow \text{relative boundary of a bulk theory}.
\end{aligned}
$$

Both are important. They answer different questions.

## Inflow and symmetry-protected phases

A symmetry-protected topological phase is a gapped phase that looks trivial if the symmetry is ignored, but has protected boundary behavior when the symmetry is imposed. In field-theory language, the bulk is often an invertible topological response theory for background fields.

If the bulk has a nontrivial response

$$
Z_{\rm SPT}[X_{d+1},A],
$$

then a boundary $M_d$ must supply degrees of freedom or boundary conditions whose anomaly cancels the bulk variation. Equivalently, the boundary realizes the ’t Hooft anomaly determined by the bulk.

This is the anomaly-based version of the bulk–boundary correspondence:

$$
\text{SPT bulk response}
\quad\Longleftrightarrow\quad
\text{boundary ’t Hooft anomaly}.
$$

The boundary may be gapless, symmetry-breaking, or topologically ordered. What it cannot be, when the anomaly is nontrivial, is a completely trivial symmetric gapped system.

## Inflow for defects and generalized symmetries

Anomaly inflow is not restricted to spacetime boundaries. A defect can carry its own anomalous degrees of freedom, with inflow from the surrounding bulk or from a topological operator inserted on the defect.

Examples include:

- chiral modes localized on domain walls;
- Wilson and ’t Hooft lines with projective symmetry action;
- surface defects carrying lower-dimensional anomalies;
- boundaries of higher-form SPT phases;
- non-invertible or duality defects with anomaly-like obstruction data.

For a $q$-form symmetry, the charged operators are $q$-dimensional, and the topological symmetry operators have codimension $q+1$. Their anomalies can produce inflow onto defects of many codimensions, not just onto ordinary spacetime boundaries.

## What inflow proves and what it does not prove

Inflow proves that a boundary anomaly can be consistently paired with a bulk whose variation is opposite. It also gives a robust way to match anomaly classes across RG flows, boundaries, interfaces, and defects.

It does **not** automatically prove that a particular microscopic boundary Hamiltonian exists, that a chosen boundary condition is stable, or that the boundary must be gapless. A nontrivial anomaly forbids a trivial symmetric gapped boundary, but it can often be matched by symmetry breaking or topological order.

The logically precise chain is

$$
\text{nontrivial anomaly}
\Rightarrow
\text{no trivially gapped symmetric standalone realization}
\not\Rightarrow
\text{must be gapless}.
$$

Gaplessness is one allowed matching mechanism, not the only one.

## Common pitfalls

**Pitfall 1: Saying inflow removes the anomaly.**

Inflow cancels the variation of the combined bulk–boundary system. The boundary theory alone remains anomalous.

**Pitfall 2: Forgetting that signs are conventional.**

The sign of the inflow action depends on whether the boundary anomaly is defined as $\delta W$, $\delta\log Z$, or the phase multiplying $Z$. Always check the cancellation equation.

**Pitfall 3: Treating every bulk as an ordinary dynamical gauge theory.**

The inflow bulk may be an invertible topological theory for background fields, not a new dynamical sector with local propagating particles.

**Pitfall 4: Assuming anomaly means inconsistency.**

A global anomaly is consistent as long as the symmetry remains global. It becomes an obstruction only when one tries to gauge the symmetry or define the anomalous theory without its inflow partner.

**Pitfall 5: Equating anomaly with gaplessness.**

Anomaly matching constrains the IR. It does not demand a gapless IR in every case. Symmetry breaking and topological order can also match anomalies.

## Relations to other pages

- [Obstruction to Gauging](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/obstruction-to-gauging/) gives the gauging test that inflow repairs only after adding a bulk.
- [Anomalies as RG Invariants](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-as-rg-invariants/) explains why the same inflow theory must be visible in the UV and IR.
- [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) derives the local formulas used in perturbative inflow.
- [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) develops the bulk topological response used in many examples.
- [Anomalies and Boundaries](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-boundaries/) explains the possible boundary fates forced by anomaly inflow.
- [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/) develops the modern topological bulk viewpoint beyond this preview.

## Research status

The inflow mechanism for perturbative local anomalies is established textbook material. The descent construction and Chern–Simons inflow are standard tools in gauge theory, string theory, condensed matter, and anomaly matching.

The modern formulation of anomalies as invertible field theories is also well established, though its most compact mathematical forms use bordism, differential cohomology, spin/Pin structures, eta invariants, and extended field theory. The frontier is not whether inflow exists; it is how best to encode inflow for generalized, non-invertible, crystalline, subsystem, and categorical symmetry structures.

## Exercises

### 1. Abelian Chern–Simons variation

Let

$$
S_{\rm CS}[A]=\frac{k}{4\pi}\int_{X_3}A\wedge dA
$$

on a three-manifold with boundary $M_2=\partial X_3$. Compute the variation under $A\mapsto A+d\lambda$.

<details><summary><strong>Solution</strong></summary>

Using $d^2\lambda=0$,

$$
\delta_\lambda S_{\rm CS}
=
\frac{k}{4\pi}\int_{X_3}d\lambda\wedge dA
=
\frac{k}{4\pi}\int_{X_3}d(\lambda dA)
=
\frac{k}{4\pi}\int_{M_2}\lambda dA.
$$

Thus the Chern–Simons action is gauge invariant on a closed manifold, but on a manifold with boundary it has a boundary variation. This boundary variation is precisely what can cancel a two-dimensional chiral anomaly of the opposite sign.

</details>

### 2. Inflow does not make the boundary standalone

Suppose

$$
Z_{\partial}[A^g]=e^{2\pi i\mathcal A_g[A]}Z_{\partial}[A]
$$

and

$$
Z_{\rm bulk}[A^g]=e^{-2\pi i\mathcal A_g[A]}Z_{\rm bulk}[A].
$$

Show that the product is invariant. Does this imply that $Z_{\partial}$ is gauge invariant by itself?

<details><summary><strong>Solution</strong></summary>

The product transforms as

$$
Z_{\rm bulk}[A^g]Z_{\partial}[A^g]
=
e^{-2\pi i\mathcal A_g[A]}Z_{\rm bulk}[A]
\,e^{2\pi i\mathcal A_g[A]}Z_{\partial}[A]
=
Z_{\rm bulk}[A]Z_{\partial}[A].
$$

The boundary partition function still transforms anomalously. Only the combined bulk–boundary object is invariant.

</details>

### 3. Descent and Stokes’ theorem

Given

$$
I_{d+2}=dI_{d+1}^{(0)},
\qquad
\delta_\lambda I_{d+1}^{(0)}=dI_d^{(1)}(\lambda),
$$

show that $S_{\rm inflow}=2\pi\int_{X_{d+1}}I_{d+1}^{(0)}$ has a boundary variation.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta_\lambda S_{\rm inflow}
=
2\pi\int_{X_{d+1}}\delta_\lambda I_{d+1}^{(0)}
=
2\pi\int_{X_{d+1}}dI_d^{(1)}(\lambda)
=
2\pi\int_{\partial X_{d+1}}I_d^{(1)}(\lambda).
$$

If $\partial X_{d+1}=M_d$, this is exactly a $d$-dimensional anomalous variation. It cancels a boundary anomaly with the opposite sign.

</details>

### 4. Two ways to cancel an anomaly

A theory $\mathcal T$ has anomaly class $[\mathcal A]$. Compare cancellation by a second $d$-dimensional theory $\mathcal T'$ with anomaly $-[\mathcal A]$ and cancellation by a $(d+1)$-dimensional inflow bulk.

<details><summary><strong>Solution</strong></summary>

The product $\mathcal T\times\mathcal T'$ is a standalone $d$-dimensional theory whose total anomaly class is zero. It can be gaugeable in $d$ dimensions.

By contrast, attaching $\mathcal T$ to a bulk inflow theory gives a gauge-invariant bulk–boundary system. The boundary theory $\mathcal T$ by itself remains anomalous and should be regarded as a boundary condition, or relative theory, for the bulk anomaly theory.

</details>

## References

- C. G. Callan and J. A. Harvey, “Anomalies and Fermion Zero Modes on Strings and Domain Walls,” *Nuclear Physics B* 250 (1985) 427.
- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities,” *Physics Letters B* 37 (1971) 95.
- E. Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* 223 (1983) 422.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* 234 (1984) 269.
- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology,” *Communications in Mathematical Physics* 129 (1990) 393.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- A. Kapustin, “Symmetry Protected Topological Phases, Anomalies, and Cobordisms,” arXiv:1403.1467.
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” arXiv:1604.06527.
- E. Witten and K. Yonekura, “Anomaly Inflow and the eta-Invariant,” arXiv:1909.08775.
- M. Srednicki, *Quantum Field Theory*, §§75–77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30.

## Version history

- 2026-06-18: First polished draft. Added descent-based inflow, Chern–Simons and chiral-edge examples, domain-wall mechanism, invertible-bulk interpretation, relative-theory language, and exercises.
