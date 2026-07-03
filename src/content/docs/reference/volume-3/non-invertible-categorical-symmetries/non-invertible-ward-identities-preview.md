---
title: "Non-Invertible Ward Identities: Preview"
description: "Preview of how non-invertible topological defects impose Ward identities, selection rules, sector relations, and defect-network constraints without ordinary Noether currents."
sidebar:
  label: "Non-Invertible Ward Identities: Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Shao TASI lectures; Schäfer-Nameki ICTP lectures; Fröhlich–Fuchs–Runkel–Schweigert; Ising defect and SymTFT literature."
topics:
  - non-invertible Ward identities
  - topological defects
  - categorical symmetry
  - selection rules
  - defect networks
canonicalTopics:
  - noninvertible-ward-identity
  - topological-defect-ward-identity
  - defect-network-identity
  - categorical-selection-rule
researchStatus:
  established:
    - "Ward identities from topological defect deformation are standard in two-dimensional topological-defect and rational-CFT examples."
    - "Non-invertible symmetry constraints are naturally formulated as identities among correlators with defect networks, rather than as ordinary current-conservation equations."
  active:
    - "A general higher-dimensional theory of non-invertible Ward identities, generalized charges, and their SymTFT interpretation remains an active research area."
---

## Summary

An ordinary Ward identity says: move a topological symmetry operator without changing the correlator, and record what happens when it crosses charged insertions.

A **non-invertible Ward identity** says the same thing, but with a crucial upgrade. When the topological defect crosses operators or fuses with other defects, the result may be a sum over channels, a defect endpoint, a disorder operator, or a relation between different sectors. There may be no current, no infinitesimal parameter, no inverse operator, and no simple phase charge.

For an invertible ordinary symmetry,

$$
U_g(\Sigma)\mathcal O_i
\quad\leadsto\quad
(g\cdot\mathcal O_i)U_g(\Sigma).
$$

For a non-invertible defect $\mathcal N$,

$$
\mathcal N\text{ crossing }\mathcal O
\quad\leadsto\quad
\sum_\alpha c_\alpha\,\mathcal O_\alpha\text{ with possible attached defects}.
$$

The Ward identity is not lost. It has become a **defect-network identity**.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic of a non-invertible Ward identity: a topological defect is deformed through operator insertions, crossing produces a sum of channels, and fusion resolves the network into correlated sectors.](/figures/symmetry-anomalies-topology/noninvertible-ward-identity-network.svg)

<figcaption>

Non-invertible Ward identities come from the same topological sliding principle as ordinary Ward identities. The difference is what happens at crossings and fusions: the defect action may produce sums of channels, attached lines, or sector-changing operators rather than a single transformed operator.

</figcaption>
</figure>

This is a preview page. It explains the logic and the first examples, while the full technical machinery belongs to later pages on gauging, orbifolding, Tambara–Yamagami examples, and symmetry TFT.

## Prerequisites

You should know [Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/), [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/), and [Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/).

It also helps to remember the ordinary topological-operator version of Ward identities: inserting a closed topological symmetry defect and deforming it gives identities among correlation functions.

## Core idea

The usual Noether-current Ward identity is not the most general form of a symmetry constraint. It is the infinitesimal, current-based version of a deeper topological statement.

For an ordinary zero-form symmetry with defect $U_g(\Sigma)$, deformation invariance says

$$
\langle U_g(\Sigma)\,\mathcal O_1\cdots\mathcal O_n\rangle
$$

depends only on which insertions $\Sigma$ encloses or crosses. If the vacuum is symmetric, moving $U_g$ across all insertions gives

$$
\langle\mathcal O_1\cdots\mathcal O_n\rangle
=
\langle(g\cdot\mathcal O_1)\cdots(g\cdot\mathcal O_n)\rangle.
$$

If each $\mathcal O_i$ has $U(1)$ charge $q_i$, this reduces to charge conservation.

For a non-invertible defect $\mathcal D_a$, the same deformation principle holds, but the crossing rule is not a group action. It is a categorical action:

$$
\mathcal D_a\triangleright \mathcal O
=
\bigoplus_{\alpha} \mathcal O_\alpha,
$$

possibly with attached topological lines or junctions. The Ward identity becomes a relation in the category of defect networks.

## Setup and notation

Let $\mathcal D_a$ be a topological codimension-one defect. A correlator with a closed defect insertion is written schematically as

$$
\left\langle \mathcal D_a(\Sigma)\,\prod_i\mathcal O_i(x_i)\right\rangle.
$$

Topological invariance means that if $\Sigma$ is deformed without crossing insertions, boundaries, or other defects, then the correlator is unchanged.

Fusion is written

$$
\mathcal D_a\otimes\mathcal D_b
\simeq
\bigoplus_c N_{ab}{}^c\,\mathcal D_c.
$$

A crossing rule is the local replacement used when a defect is moved past an operator:

$$
\mathcal D_a\text{ crossing }\mathcal O_i
\quad\rightsquigarrow\quad
\sum_{\alpha}C_{a i}^{\alpha}\,\mathcal O_{\alpha}.
$$

The symbol $\rightsquigarrow$ is deliberately schematic. In many examples, $\mathcal O_\alpha$ is not an ordinary local operator: it may be a defect-local operator, a disorder operator, or a local operator attached to a topological line.

:::note[Terminology]
In this page, “Ward identity” means an exact identity following from topological defect deformation. It need not be the divergence equation of a Noether current.
:::

## Ordinary Ward identities as the special case

For an invertible group-like defect, crossing is simple. If $\mathcal O_i$ transforms in a representation of $G$,

$$
U_g\text{ crossing }\mathcal O_i
\quad\rightsquigarrow\quad
g\cdot\mathcal O_i.
$$

The fusion rule is

$$
U_g\otimes U_h=U_{gh},
$$

and every $U_g$ has an inverse. Wrapping $U_g$ around a set of insertions gives a familiar selection rule.

For a finite Abelian symmetry, if

$$
g\cdot\mathcal O_i=\chi_i(g)\mathcal O_i,
$$

then a nonzero correlator in a symmetric vacuum must satisfy

$$
\prod_i\chi_i(g)=1
$$

for every $g$.

This is the ordinary finite-group Ward identity written topologically.

Non-invertible Ward identities keep the topological wrapping logic but replace characters by categorical action data.

## What changes in the non-invertible case

Three things change.

First, there is usually no inverse. A defect $\mathcal N$ may obey

$$
\mathcal N\otimes\mathcal N=1\oplus\eta
$$

rather than $\mathcal N\otimes\mathcal N=1$.

Second, there may be no one-dimensional charge eigenvalue. A defect can act by mapping one object to several objects:

$$
\mathcal N\triangleright X\simeq X_1\oplus X_2.
$$

Third, the action can leave the category of genuine local operators. A local operator may be mapped to a disorder operator attached to a line. This is exactly what happens in the Ising Kramers–Wannier example: the spin operator can be sent to a disorder operator with an attached spin-flip defect.

Thus non-invertible Ward identities do not usually say “multiply the correlator by a phase.” They say “two defect-network evaluations are equal after applying the allowed crossing, fusion, and junction moves.”

## Defect sliding identity

The fundamental identity is defect sliding.

Suppose $\Sigma$ and $\Sigma'$ are homologous deformations that cross no insertions. Then

$$
\left\langle \mathcal D_a(\Sigma)\,\mathcal X\right\rangle
=
\left\langle \mathcal D_a(\Sigma')\,\mathcal X\right\rangle,
$$

where $\mathcal X$ denotes all other insertions.

If $\Sigma$ is moved across an operator $\mathcal O$, the identity becomes

$$
\left\langle \mathcal D_a(\Sigma_{\rm before})\,\mathcal O\,\mathcal X\right\rangle
=
\left\langle \mathcal D_a(\Sigma_{\rm after})\,(\mathcal D_a\triangleright\mathcal O)\,\mathcal X\right\rangle.
$$

For a topological defect this is exact. The content lies in the crossing rule.

In a current-based symmetry, the crossing rule comes from integrating a current conservation equation around the insertion. In a non-invertible symmetry, the crossing rule is part of the topological defect data.

## Fusion identity

A second kind of Ward identity comes from fusing parallel defects.

If two topological defects lie close to each other, then

$$
\left\langle \mathcal D_a\mathcal D_b\,\mathcal X\right\rangle
=
\sum_c N_{ab}{}^c
\left\langle \mathcal D_c\,\mathcal X\right\rangle,
$$

with possible sums over junction multiplicity labels when $N_{ab}{}^c>1$.

For the Ising non-invertible defect,

$$
\left\langle \mathcal N\mathcal N\,\mathcal X\right\rangle
=
\left\langle \mathcal X\right\rangle
+
\left\langle \eta\,\mathcal X\right\rangle.
$$

This is a Ward identity: two ways of evaluating the same topological network agree. It is not a probability statement. It is a decomposition into superselection channels.

If $\eta$ acts as $-1$ on an operator, then the second term can cancel or reinforce the first depending on the insertions. This is how ordinary selection-rule information reappears inside non-invertible fusion.

## Ising example

The critical Ising model has topological lines

$$
1,\qquad \eta,\qquad \mathcal N,
$$

with

$$
\eta^2=1,
\qquad
\eta\mathcal N=\mathcal N\eta=\mathcal N,
\qquad
\mathcal N^2=1+\eta.
$$

The spin operator $\sigma$ is odd under $\eta$. The energy operator $\epsilon$ is even. The Kramers–Wannier defect $\mathcal N$ maps order data to disorder data.

Sliding $\eta$ around a correlator gives the usual $\mathbb Z_2$ selection rule: a correlator with an odd number of $\sigma$ insertions vanishes in the symmetric vacuum.

Sliding $\mathcal N$ gives a different kind of statement. It relates correlators of order insertions to correlators involving disorder insertions and possible attached $\eta$ lines. Fusion of two $\mathcal N$ lines gives

$$
\langle \mathcal N^2\,\mathcal X\rangle
=
\langle \mathcal X\rangle+\langle\eta\,\mathcal X\rangle.
$$

If $\mathcal X$ is neutral under $\eta$, then the right side is twice the ordinary correlator. If $\mathcal X$ is odd, the two terms cancel. This is a simple shadow of how the non-invertible line encodes both projection and sector information.

:::note[Source note]
The statement that $\mathcal N$ maps order operators to disorder operators must be interpreted with defect attachments and sector data. On the lattice, boundary conditions and spin structures can affect the exact formulation. The continuum topological-line statement is cleanest at the critical point.
:::

## Hilbert-space viewpoint

Place the theory on a spatial circle and let a topological line wrap the spatial circle. It defines an operator $\widehat{\mathcal D}_a$ on the Hilbert space. Topological invariance implies

$$
[\widehat{\mathcal D}_a,H]=0.
$$

For an invertible symmetry, $\widehat{\mathcal D}_g$ is unitary and the Hilbert space decomposes into charge representations.

For a non-invertible defect, $\widehat{\mathcal D}_a$ need not be unitary and need not have an inverse. Instead, the operators obey a fusion algebra:

$$
\widehat{\mathcal D}_a\,\widehat{\mathcal D}_b
=
\sum_c N_{ab}{}^c\,\widehat{\mathcal D}_c.
$$

Thus the spectrum can be organized by simultaneous action of commuting topological defect operators when such a commuting set exists. But the labels are not ordinary group charges. They are eigenvalues or modules of a fusion algebra, often with degeneracy and sector subtleties.

## Relation to Noether currents

A continuous invertible symmetry usually has a Noether current. Non-invertible symmetries generally do not.

This is not a failure of symmetry. It is a sign that Noether currents are not the universal definition of symmetry. The universal object is the topological operator or defect network.

For finite symmetries, even ordinary invertible ones, there is no local current. Their Ward identities are already topological rather than differential. Non-invertible symmetry takes this one step further: the defect is topological, but its crossing and fusion do not define a group action.

The safe hierarchy is:

$$
\text{Noether current Ward identity}
\subset
\text{topological defect Ward identity}
\subset
\text{categorical defect-network identity}.
$$

## Selection rules and forbidden flows

Non-invertible Ward identities can impose selection rules. They can forbid certain correlators, forbid certain deformations, require degeneracies, or obstruct flows to trivially gapped phases.

The logic is the same as for ordinary symmetry. If a perturbing operator is not compatible with the defect action, adding it breaks the symmetry. If an RG flow preserves the topological defect, the infrared theory must still realize its fusion and action data, possibly in a different form.

However, non-invertible selection rules are often less expressible as “total charge equals zero.” They may instead say that a perturbation must be transparent to a defect, that it must live in a specific module sector, or that a defect endpoint must be allowed.

This is why categorical language is useful: the selection rule is a statement about allowed morphisms and modules.

## Preview of generalized charges

In the modern SymTFT viewpoint, generalized charges of a theory with categorical symmetry are often characterized by topological defects of the associated symmetry TFT. This explains why a non-invertible symmetry can act on extended objects in ways that resemble higher representations rather than ordinary representations.

For this page, the takeaway is modest:

$$
\text{charged object}
\neq
\text{vector in a group representation only}.
$$

A charged object may be a local operator, a line, a boundary condition, a sector, or a defect endpoint. A non-invertible Ward identity is the statement that the topological symmetry defect acts consistently on these objects and that correlators are invariant under the resulting network moves.

## Common pitfalls

**“No current means no Ward identity.”** False. Finite symmetries already show that Ward identities can be topological rather than current-based.

**“Non-invertible Ward identities are just selection rules with strange charges.”** Too narrow. They can relate different sectors, attach defects to operators, and decompose networks into sums of channels.

**“The defect operator must be unitary.”** A non-invertible topological defect need not define a unitary invertible operator on Hilbert space. It can still commute with the Hamiltonian and impose exact constraints.

**“The fusion rule alone gives all identities.”** Fusion rules give some identities. Crossing rules, junction spaces, associators, and module actions are also needed.

**“A sum of defects means a probabilistic mixture.”** No. It is a direct-sum decomposition of topological sectors.

## Relations to other pages

[Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/) explains the defect, junction, and module data needed to formulate these identities. [Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/) gives the canonical example. [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) will explain how gauging produces non-invertible defects and their Ward identities.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter gives the current-based special case. The [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) chapter gives the one-higher-dimensional packaging of generalized charges and defect-network constraints.

## Research status

In two-dimensional rational CFT, lattice Ising-type models, and many semisimple topological-defect examples, non-invertible Ward identities are well established as topological defect-network identities.

In higher dimensions, the general picture is active. Current research studies how non-invertible defects act on extended operators, how such actions are encoded in SymTFT, how anomalies constrain the identities, and how non-invertible symmetry restricts phases and RG flows.

## Exercises

### Exercise 1: Ordinary selection rule as defect sliding

Let $\eta$ be a $\mathbb Z_2$ topological defect and let $\mathcal O_i$ have parity $p_i=\pm1$. Use defect sliding to show that a correlator in a symmetric vacuum vanishes unless $\prod_i p_i=1$.

<details><summary><strong>Solution</strong></summary>

Wrap $\eta$ around all insertions. Since the vacuum is symmetric and the defect is topological, the defect can be removed without changing the correlator. Now shrink the defect across the insertions. Each crossing gives a factor $p_i$. Therefore

$$
\langle\mathcal O_1\cdots\mathcal O_n\rangle
=
\left(\prod_i p_i\right)
\langle\mathcal O_1\cdots\mathcal O_n\rangle.
$$

If $\prod_i p_i\ne1$, the correlator must vanish.

</details>

### Exercise 2: Fusion identity for the Ising duality defect

Use $\mathcal N^2=1+\eta$ to evaluate $\langle \mathcal N^2\,\mathcal X\rangle$ when $\mathcal X$ is even under $\eta$ and when $\mathcal X$ is odd under $\eta$.

<details><summary><strong>Solution</strong></summary>

The fusion rule gives

$$
\langle \mathcal N^2\,\mathcal X\rangle
=
\langle\mathcal X\rangle+\langle\eta\,\mathcal X\rangle.
$$

If $\mathcal X$ is even under $\eta$, then $\langle\eta\,\mathcal X\rangle=\langle\mathcal X\rangle$, so

$$
\langle \mathcal N^2\,\mathcal X\rangle=2\langle\mathcal X\rangle.
$$

If $\mathcal X$ is odd, then $\langle\eta\,\mathcal X\rangle=-\langle\mathcal X\rangle$, so

$$
\langle \mathcal N^2\,\mathcal X\rangle=0.
$$

This is a simple example of a non-invertible fusion identity producing a selection rule.

</details>

### Exercise 3: Why no phase charge?

Explain why a non-invertible defect with $\mathcal N^2=1+\eta$ cannot act on every local operator by multiplication by an ordinary phase.

<details><summary><strong>Solution</strong></summary>

If $\mathcal N$ acted by a phase $\lambda$ on every operator in an ordinary one-dimensional charge sector, then $\mathcal N^2$ would act by $\lambda^2$. But the fusion rule says that $\mathcal N^2$ decomposes into two channels, $1$ and $\eta$. The action depends on how $\eta$ acts and on the relevant sector. This is not equivalent to multiplication by a single group character. The non-invertible defect acts categorically, not as an ordinary group element.

</details>

## References

- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries,” for modern non-invertible Ward-identity intuition.
- S. Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries,” for topological-operator and SymTFT perspectives.
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, papers on topological defects and duality defects in rational CFT.
- L. Bhardwaj and S. Schäfer-Nameki, “Generalized Charges, Part II: Non-Invertible Symmetries and the Symmetry TFT,” for generalized charges and the SymTFT viewpoint.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the higher-form topological-operator framework that this page extends.

## Version history

- **2026-06-20:** Initial polished preview. Introduced non-invertible Ward identities as topological defect-network identities, with sliding, crossing, fusion, Hilbert-space, Ising, and selection-rule examples.
