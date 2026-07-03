---
title: "Examples of Symmetry TFT"
description: "Concrete examples of symmetry TFTs for ordinary finite symmetries, higher-form symmetries, gauge-theory global forms, anomalies, and non-invertible symmetry."
sidebar:
  label: "Examples of Symmetry TFT"
  order: 9
level: Advanced
status: "Polished draft"
source: "Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; Freed–Teleman; Dijkgraaf–Witten; modern SymTFT literature."
topics:
  - symmetry TFT
  - Dijkgraaf–Witten theory
  - finite symmetry
  - higher-form symmetry
  - anomaly inflow
  - global form
  - non-invertible symmetry
canonicalTopics:
  - symmetry-tft-examples
  - finite-group-symtft
  - higher-form-symtft
  - global-form-symtft
  - anomaly-inflow-example
researchStatus:
  established:
    - "Finite-group gauge theories, Abelian BF theories, Chern–Simons theories, and invertible anomaly theories provide standard examples of topological theories encoding symmetry and anomaly data."
    - "Coupling a QFT to a topological theory can change extended operators and global-form data even when local dynamics on flat space appear unchanged."
  active:
    - "Non-invertible SymTFTs, non-Abelian finite symmetry presentations, categorical boundary conditions, and higher-categorical refinements remain active research areas."
---

## Summary

The SymTFT idea is abstract until it is tested on examples. This page collects the basic models that should sit in your mental toolbox.

The general pattern is:

$$
\text{symmetry data of a }d\text{-dimensional QFT}
\quad
\longleftrightarrow
\quad
(d+1)\text{-dimensional topological bulk}
$$

together with boundary conditions. The physical QFT is one boundary. A topological boundary specifies a global form, a gauging choice, an orbifold, a choice of genuine operators, or a completion of relative data.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A gallery diagram of common SymTFT examples: finite group symmetry, Abelian BF theory, higher-form symmetry, Chern-Simons boundary data, anomaly inflow, and non-invertible defect categories.](/figures/symmetry-anomalies-topology/symtft-examples-gallery.svg)

<figcaption>

Examples of SymTFT should be read as dictionaries. The bulk topological theory is not a replacement for the physical QFT; it packages the symmetry operators, background fields, gauging choices, charged objects, and anomalies that the physical boundary can carry.

</figcaption>
</figure>

A good example has three visible parts:

1. **Bulk topological theory:** the SymTFT.
2. **Physical boundary:** the QFT whose symmetry data are being described.
3. **Topological boundary:** a choice of global form, gauging, background condition, or absolute completion.

The same bulk can often support several topological boundaries. This is the useful feature, not an accident.

## Prerequisites

Read the preceding pages in this chapter, especially [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/), [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/), [Defects from the Bulk](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/defects-from-the-bulk/), and [Relative QFT Preview](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/relative-qft-preview/).

You should also know the basic language of ordinary finite symmetries, higher-form symmetries, Wilson and ’t Hooft lines, background fields, and anomaly inflow.

## Example 1: finite ordinary symmetry and Dijkgraaf–Witten bulk

Let a $d$-dimensional QFT $\mathcal T$ have an ordinary finite global symmetry $G$. Backgrounds for $G$ are flat $G$ bundles, or equivalently Čech cocycles in a triangulated description. Gauging $G$ means summing over those backgrounds.

The associated SymTFT is often a $(d+1)$-dimensional finite gauge theory. In its untwisted version, it is the topological gauge theory with gauge group $G$. In its twisted version, it is a Dijkgraaf–Witten theory specified by a cohomology class

$$
\omega\in H^{d+1}(BG,U(1)).
$$

The physical boundary sees the $G$ symmetry. The topological boundary specifies whether the theory is left ungauged, gauged, or paired with a more general topological sector.

The simplest picture is:

$$
\text{bulk finite }G\text{ gauge theory}
\quad
\text{between}
\quad
\begin{cases}
\text{physical boundary carrying }G,\\
\text{topological boundary choosing gauging data.}
\end{cases}
$$

The Wilson-like bulk defects encode symmetry charges; magnetic or flux-like defects encode twisted sectors. On a boundary, these become symmetry operators, disorder operators, or defect sectors depending on the boundary condition.

:::note[Source note: finite gauge theory]
A finite-group SymTFT is one of the cleanest places where “background field” becomes literally “flat bundle.” The formalism is close to lattice gauge theory: a sum over flat bundles replaces an integral over a continuous connection.
:::

## Example 2: two-dimensional orbifolds

Take a two-dimensional QFT with a finite symmetry $G$. The orbifold by $G$ is obtained by summing over twisted sectors and projecting onto $G$-invariant states. In the SymTFT language, the original theory and the orbifold are different topological boundary choices for a three-dimensional finite gauge theory.

This explains a familiar fact in a more structural way: orbifolding is not just removing non-invariant states. It also adds twisted sectors. A topological boundary condition keeps track of both operations.

For $G=\mathbb Z_2$, the story is visible in the Ising/Kramers–Wannier family. A spin-flip symmetry can be gauged, and at a self-dual point the gauging interface can become a non-invertible duality defect. The SymTFT viewpoint says: do not treat the original theory, the gauged theory, the twisted sectors, and the duality defect as unrelated miracles. They are different boundary and defect data in one topological package.

## Example 3: Abelian one-form symmetry and BF theory

Let a $d$-dimensional QFT have an Abelian $q$-form symmetry $A$. The charged objects are $q$-dimensional operators, and the symmetry operators are supported on codimension-$q+1$ manifolds. A finite Abelian example is often encoded by a topological BF-type bulk.

For a $\mathbb Z_N$ one-form symmetry in four dimensions, a natural five-dimensional topological action has the schematic form

$$
S_{\mathrm{bulk}}
=
\frac{2\pi i}{N}\int B\cup dC
$$

in cochain notation, or a continuum shorthand

$$
S_{\mathrm{bulk}}
=
\frac{iN}{2\pi}\int B\wedge dC
$$

when that notation is appropriate. Here $B$ and $C$ are higher-form gauge fields of complementary degrees.

The linking pairing in the bulk encodes the phase picked up when a symmetry surface links a charged line:

$$
U(\Sigma)\,L(\gamma)
=
\chi(\operatorname{Link}(\Sigma,\gamma))\,L(\gamma).
$$

Different topological boundary conditions decide which lines are genuine, which are confined to end on surfaces, and which symmetry has been gauged. This is exactly the kind of data that is difficult to see from the local Lagrangian alone.

:::caution[Continuum notation is shorthand]
For finite higher-form symmetries, continuum BF notation is often a mnemonic for differential cohomology, Deligne–Beilinson, or cochain data. It is excellent for intuition but should not be mistaken for a globally complete definition on arbitrary manifolds.
:::

## Example 4: Maxwell theory and electric-magnetic one-form symmetry

In four-dimensional free Maxwell theory without dynamical electric or magnetic charges, Wilson and ’t Hooft lines are charged under electric and magnetic one-form symmetries. The symmetry operators are surfaces measuring electric or magnetic flux.

The SymTFT remembers the mutual linking of these surface and line operators. In a schematic Abelian continuum presentation, electric and magnetic background two-form fields $B_e$ and $B_m$ can have a mixed bulk term

$$
S_{\mathrm{bulk}}
\sim
\frac{i}{2\pi}\int B_e\wedge dB_m.
$$

This term records the fact that electric and magnetic one-form symmetry backgrounds are not independent in every global form or duality frame.

Adding dynamical electrically charged matter breaks or screens the electric one-form symmetry. Adding magnetic monopoles does the same to the magnetic one-form symmetry. In SymTFT language, charged lines that were once genuine may become endable on boundary operators or surfaces. Screening is therefore a statement about the allowed endpoints of bulk/boundary defects.

## Example 5: global form of non-Abelian gauge theory

A four-dimensional Yang–Mills theory with local Lie algebra $\mathfrak{su}(N)$ is not fully specified by the Lie algebra. One must choose a global form such as

$$
SU(N),\qquad PSU(N)=SU(N)/\mathbb Z_N,
$$

and possibly a discrete theta angle. These choices determine the allowed Wilson, ’t Hooft, and dyonic line operators.

The SymTFT packages this line-operator information. The bulk knows the electric and magnetic one-form symmetry data; the topological boundary chooses a maximal mutually local set of genuine lines. Switching the topological boundary can change the global form of the boundary gauge theory without changing the local Yang–Mills equations.

This is the point of saying that SymTFT packages **global** QFT data. On $\mathbb R^4$ with no line insertions, two global forms may look locally identical. On general manifolds, with background fields or line operators, they are different theories.

## Example 6: Chern–Simons theory as a symmetry bulk

Three-dimensional Chern–Simons theory is itself a TQFT. It can also serve as a SymTFT for two-dimensional chiral, rational, or defect-rich boundary theories.

A compact way to say the relation is:

$$
\text{bulk Wilson lines}
\quad\longleftrightarrow\quad
\text{boundary topological defects or chiral sectors}.
$$

For a modular tensor category $\mathcal C$, the bulk three-dimensional TQFT built from $\mathcal C$ can encode the topological lines and fusion data of a two-dimensional rational CFT or topological boundary theory. Boundary conditions select module categories; boundary-changing operators and defect junctions carry additional categorical data.

This example is historically important because it connects Chern–Simons theory, knot invariants, WZW models, rational CFT, and modern categorical symmetry. It also warns against a naive view of symmetry as only a group action: many boundary defect systems are controlled by fusion categories rather than groups.

## Example 7: invertible anomaly theory

Suppose a $d$-dimensional theory has an anomaly for a global symmetry. Its partition function is not an ordinary invariant function of the background fields. It transforms by a phase. That phase can be cancelled by a $(d+1)$-dimensional invertible topological theory.

Schematically,

$$
\delta_\lambda W_{\mathrm{boundary}}[A]
+
\delta_\lambda S_{\mathrm{bulk}}[A]
=0.
$$

Here the SymTFT is invertible: it has no nontrivial topological order in the bulk, but its partition function is a phase depending on background fields and geometry.

A familiar perturbative example is anomaly inflow from a Chern–Simons-like bulk term. A global example may require eta invariants, spin structure, or bordism data. The lesson is the same: the anomalous $d$-dimensional theory is naturally relative to the $(d+1)$-dimensional anomaly theory.

## Example 8: SPT bulk and anomalous boundary

An SPT phase protected by symmetry $G$ is an invertible bulk phase that becomes trivial if $G$ is forgotten, but has a protected boundary if $G$ is preserved. In the SymTFT language, the SPT bulk can be viewed as an anomaly theory for the boundary.

For a finite group in bosonic group-cohomology models, one often writes an action classified by

$$
\omega\in H^{d+1}(BG,U(1)).
$$

The boundary cannot be trivially gapped while preserving all assumptions unless it develops topological order, breaks the symmetry, becomes gapless, or is otherwise anomalous. This is the anomaly/SPT correspondence in its most practical form.

The SymTFT viewpoint emphasizes that the bulk is not merely a response action. It also organizes possible symmetry defects, boundary completions, and gauging operations.

## Example 9: non-invertible SymTFT

Non-invertible symmetry cannot generally be encoded by an ordinary gauge theory with group $G$. The bulk topological theory must remember a category of defects rather than just a group of invertible symmetry operators.

In a two-dimensional boundary theory, a three-dimensional SymTFT may have bulk anyons whose boundary images are topological defect lines with fusion

$$
\mathcal N_a\mathcal N_b
\simeq
\bigoplus_c N_{ab}{}^c\mathcal N_c.
$$

For an Ising-like example,

$$
\mathcal N^2\simeq 1+\eta,
$$

where $\eta$ is an invertible $\mathbb Z_2$ defect. This fusion rule is not group multiplication because the product is a sum.

The SymTFT point of view is especially useful here. It turns non-invertible symmetry from “a strange operator identity” into ordinary topological data in one higher dimension: bulk lines, fusion, boundary conditions, and junction spaces.

## Example 10: symmetry extension and anomaly cancellation

Sometimes an anomaly for a symmetry $G$ becomes trivial after extending the symmetry to a larger group $\widetilde G$,

$$
1\to K\to \widetilde G\to G\to 1.
$$

The SymTFT describes this as a change of bulk/topological boundary data. Rather than cancelling the anomaly by adding arbitrary degrees of freedom, one chooses a boundary condition or extension that changes which background fields are allowed and how they are lifted.

This idea appears in finite-group anomaly matching, SPT boundary constructions, and some gapped boundary classifications. It is conceptually close to the statement that anomaly cancellation may require extra topological degrees of freedom, not just extra local particles.

## How to read examples

When someone says “the SymTFT of this theory is …,” ask the following questions:

| Question | Why it matters |
|---|---|
| What is the physical boundary? | It identifies the actual QFT whose symmetry data are being described. |
| What is the topological boundary? | It specifies gauging, global form, or absolute completion. |
| What are the bulk defects? | They encode symmetry operators, charged objects, and dual defects. |
| Which defects can end on which boundary? | This determines genuine operators and screening. |
| Is the bulk invertible? | If yes, it is anomaly/SPT-like; if no, it carries richer topological order. |
| Is the notation continuum or cochain-level? | Finite symmetries and torsion data need global definitions. |
| Is the symmetry group-like? | If not, expect categorical fusion rather than group multiplication. |

This checklist prevents the most common error: treating the bulk topological theory as if it were the same object as the physical boundary QFT.

## Common pitfalls

**“The SymTFT is the physical theory.”** Usually no. The SymTFT packages symmetry data. The physical QFT is a boundary condition or boundary sector.

**“Same local Lagrangian means same SymTFT.”** Not necessarily. Different global forms, line-operator spectra, discrete theta angles, or anomaly data can share local equations.

**“Finite group examples are just toy models.”** They are the cleanest laboratory for background bundles, gauging, orbifolding, twisted sectors, and non-invertible duality defects.

**“Invertible bulk means trivial.”** Invertible means it has an inverse under stacking. It can still encode a nontrivial anomaly or SPT response.

**“BF notation is always globally complete.”** For finite groups and torsion classes, a cochain or differential-cohomology formulation may be required.

**“Non-invertible examples are only two-dimensional curiosities.”** Two dimensions are the most explicit laboratory, but non-invertible and categorical symmetry is a broader organizing language.

## Relations to other pages

This page closes the Symmetry TFT and Anomaly Inflow chapter by collecting examples. It connects directly to [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/), [Defects from the Bulk](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/defects-from-the-bulk/), and [Relative QFT Preview](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/relative-qft-preview/).

It also prepares the next chapter, [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/), where topological theories are studied not only as symmetry packages but as QFTs in their own right.

## Research status

Finite-group, BF, Chern–Simons, Dijkgraaf–Witten, and invertible anomaly-theory examples are established. Their modern SymTFT interpretation is now standard in generalized-symmetry work.

The active frontier includes non-invertible SymTFTs, higher-categorical boundary conditions, non-Abelian finite-symmetry presentations, intrinsically relative theories, global forms in higher dimensions, and the interface between SymTFT and mathematical extended TQFT.

## Exercises

### Exercise 1: Orbifold as boundary choice

Explain why orbifolding a finite symmetry is more than projecting onto invariant states.

<details><summary><strong>Solution</strong></summary>

Projection onto invariant states keeps only the untwisted invariant part. A full orbifold also sums over twisted sectors, or equivalently over nontrivial background bundles for the finite symmetry. In the SymTFT description, the topological boundary condition that implements gauging includes both operations: projection and summation over twisted backgrounds. This is why orbifolds can contain operators not present in the original untwisted sector.

</details>

### Exercise 2: Linking in a BF SymTFT

Suppose a finite Abelian one-form symmetry is represented by a BF-type SymTFT. What physical information is encoded by the linking of a bulk symmetry surface with a boundary line operator?

<details><summary><strong>Solution</strong></summary>

The linking computes the charge of the line under the one-form symmetry. If a symmetry surface $U(\Sigma)$ links a charged line $L(\gamma)$, the correlation function is multiplied by a character depending on the linking number and the charge. This is the higher-form analogue of surrounding a local charged operator by an ordinary symmetry surface.

</details>

### Exercise 3: Global form from line operators

Why can two Yang–Mills theories with the same Lie algebra have different SymTFT boundary conditions?

<details><summary><strong>Solution</strong></summary>

The local Lie algebra controls local gauge-boson interactions, but the global form of the gauge group controls allowed Wilson, ’t Hooft, and dyonic lines. A topological boundary condition in the SymTFT selects which bulk line defects can end on the boundary and which boundary line operators are genuine. Different choices can correspond to $SU(N)$, $PSU(N)$, or theories with different discrete theta angles.

</details>

### Exercise 4: Invertible anomaly theory

What does it mean for an anomaly theory to be invertible, and why can it still be physically nontrivial?

<details><summary><strong>Solution</strong></summary>

Invertible means that under stacking there exists an inverse theory whose product is trivial. It does not mean the partition function is identically one. An invertible anomaly theory can assign nontrivial phases depending on background fields and spacetime topology. Those phases cancel the anomalous variation of the boundary theory by inflow.

</details>

## References

- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality.”
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.”
- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology.”
- Daniel S. Freed and Constantin Teleman, “Relative Quantum Field Theory.”
- Daniel S. Freed and Michael J. Hopkins, “Reflection Positivity and Invertible Topological Phases.”
- Edward Witten, “Quantum Field Theory and the Jones Polynomial.”
- Recent reviews and lectures on SymTFT, generalized symmetry, non-invertible symmetry, and categorical symmetry.

## Version history

- 2026-06-22: Initial polished draft. Added finite-group, orbifold, BF, Maxwell, global-form, Chern–Simons, anomaly, SPT, non-invertible, and symmetry-extension examples.
