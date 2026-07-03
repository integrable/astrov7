---
title: "Gauging Finite Symmetries: Preview"
description: "Explains finite-group gauging as a sum over flat symmetry backgrounds, including orbifold sectors, projection, discrete torsion, Dijkgraaf–Witten weights, anomaly obstructions, and quantum symmetries."
sidebar:
  label: "Finite Symmetries (Preview)"
  order: 6
level: Advanced
status: "Polished draft"
source: "Dijkgraaf–Witten on finite gauge theory; Dixon–Harvey–Vafa–Witten and Vafa on orbifolds and discrete torsion; Gaiotto–Kapustin–Seiberg–Willett on gauging global symmetries by summing over backgrounds."
topics:
  - finite symmetries
  - gauging
  - orbifolds
  - flat bundles
  - twisted sectors
  - discrete torsion
  - Dijkgraaf–Witten theory
  - anomalies
canonicalTopics:
  - finite-group-gauging
  - orbifold-qft
  - flat-g-bundle
  - twisted-sector
  - discrete-torsion
  - dijkgraaf-witten-theory
  - anomaly-obstruction-to-gauging
researchStatus:
  established:
    - "Gauging a finite internal symmetry means summing over flat finite-group background fields, with possible local topological weights and with anomaly-free background gauge invariance."
  active:
    - "Modern extensions include higher-form finite symmetries, higher groups, categorical gauging, non-invertible symmetries, symmetry TFT, and stacky formulations of defects and orbifolds."
---

## Summary

A finite global symmetry has no infinitesimal current and no Lie-algebra-valued gauge field. Nevertheless, it can be coupled to background fields and, if anomaly-free, it can be gauged.

For a finite group $G$, a background field on spacetime $M$ is a flat $G$-bundle. The gauged theory is schematically

$$
Z_{\mathcal T/G}(M)
=
\sum_{[P\to M]}
\frac{1}{|\operatorname{Aut}(P)|}
Z_{\mathcal T}[M;P]\,e^{iS_{\omega}[P]}.
$$

Here $[P\to M]$ runs over isomorphism classes of flat principal $G$-bundles, $\operatorname{Aut}(P)$ is the group of bundle automorphisms, and $S_{\omega}$ is an optional finite topological action. In bosonic oriented theories, such actions are often described by group-cohomology data $\omega\in H^d(BG,U(1))$, with important refinements for spin, reflection, higher-form, and fermionic symmetries.

<figure class="doc-figure" style="--figure-width: 53rem;">

![A diagram showing finite symmetry gauging as: a finite group action on a QFT, coupling to flat G-bundles, summing over sectors with automorphism weights and possible topological phases, then obtaining a gauged theory with projected local operators, twisted sectors, and possible dual symmetries.](/figures/symmetry-anomalies-topology/finite-gauging-flat-bundles.svg)

<figcaption>

Finite gauging has two inseparable pieces: project to gauge-invariant data and sum over flat $G$-backgrounds. In two-dimensional orbifold language these are the untwisted projection and the twisted sectors. In any dimension, the invariant language is the groupoid of flat $G$-bundles.

</figcaption>
</figure>

The slogan is:

$$
\text{finite gauging} = \text{projection} + \text{twisted sectors} + \text{topological weights}.
$$

The first term alone is not enough. Projecting to $G$-invariant local operators gives only part of the gauged theory. The sum over nontrivial flat bundles supplies the sectors that make locality, modular invariance, duality, and topological defect algebra work.

## Prerequisites

Read [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) first. You should also know [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/), [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/), and [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/).

This is a preview page. It gives the basic QFT operation and the formulas that recur later. Detailed two-dimensional orbifolds, Dijkgraaf–Witten theory, finite higher-form symmetries, and symmetry TFT appear in later chapters.

## Core idea

For a continuous symmetry, gauging introduces a dynamical connection and usually a kinetic term. For a finite symmetry, there is no small local fluctuation of the gauge field. The gauge field is topological: it records holonomy data around noncontractible cycles and around defects.

A flat finite $G$-bundle can be described, after choosing a base point on connected $M$, by a homomorphism

$$
\rho:\pi_1(M)\to G,
$$

up to conjugation by $G$. This is only a convenient description; the coordinate-free object is the flat principal $G$-bundle $P\to M$.

The theory $\mathcal T$ with $G$ symmetry assigns a partition function to each finite background:

$$
P\longmapsto Z_{\mathcal T}[M;P].
$$

Gauging $G$ means summing these background partition functions. The automorphism factor is the finite-group analog of dividing by gauge redundancy. It prevents overcounting backgrounds with stabilizers.

This is why finite gauging is sometimes called an **orbifold**, especially in two-dimensional QFT and string worldsheet theory. But the word “orbifold” can also mean a geometric quotient target space. The QFT operation is more precise:

$$
\mathcal T\quad\longmapsto\quad \mathcal T/G.
$$

It is a new quantum field theory, not just the old theory with the charged operators deleted.

## Setup and conventions

Let $G$ be a finite internal zero-form symmetry of a $d$-dimensional QFT $\mathcal T$ on a closed spacetime $M$.

A background finite $G$-field is a principal $G$-bundle $P\to M$ with flat transition data. Since $G$ is discrete, every connection is locally trivial and all information is in the gluing. On a triangulation, one may assign group elements $g_{ij}\in G$ to oriented edges and impose flatness on each face:

$$
g_{ij}g_{jk}g_{ki}=1.
$$

A gauge transformation assigns $h_i\in G$ to vertices and acts by

$$
g_{ij}\mapsto h_i g_{ij} h_j^{-1}.
$$

The triangulated expression is a lattice-friendly representative of the same groupoid of flat $G$-bundles. It should not be mistaken for a preferred regulator unless the page is explicitly constructing a lattice model.

:::note[Convention-sensitive source note]
There are two common normalizations for finite gauge sums. A triangulated gauge-fixed expression often carries a factor such as $|G|^{-|V|}$, where $|V|$ is the number of vertices. A coordinate-free continuum expression instead sums over isomorphism classes with weight $1/|\operatorname{Aut}(P)|$. These are the same groupoid-counting principle written in two languages.
:::

## Projection is only the untwisted piece

Suppose first that space is simply connected and we quantize on a spatial slice $\Sigma$ with no nontrivial $G$-bundle sectors. The finite group acts unitarily on the Hilbert space $\mathcal H_{\mathcal T}(\Sigma)$. The gauge-invariant subspace is obtained by the projector

$$
\Pi_G=\frac{1}{|G|}\sum_{g\in G}U_g,
$$

so that

$$
\mathcal H_{\text{untwisted}}^G(\Sigma)=\Pi_G\mathcal H_{\mathcal T}(\Sigma).
$$

This projection is real and important. It removes charged states from the local gauge-invariant spectrum. For a local operator $\mathcal O$ transforming in a nontrivial representation of $G$, the gauged theory does not contain $\mathcal O$ as an ordinary local operator.

But the full gauged theory contains more than $\Pi_G\mathcal H$. On a spatial manifold $\Sigma$ with nontrivial cycles, one must include Hilbert spaces in nontrivial flat $G$-backgrounds:

$$
\mathcal H_{\mathcal T/G}(\Sigma)
\simeq
\bigoplus_{[P\to\Sigma]}
\mathcal H_{\mathcal T}[\Sigma;P]^{\operatorname{Aut}(P)}.
$$

This formula is schematic because one must specify defects, spin structures when relevant, and possible topological twists. It captures the main point: gauging includes sectors with nontrivial holonomy.

In two-dimensional orbifold language, quantizing on a circle gives

$$
\mathcal H_{\mathcal T/G}(S^1)
\simeq
\bigoplus_{[g]}
\mathcal H_g^{C(g)},
$$

where $\mathcal H_g$ is the Hilbert space with $g$-twisted boundary condition around the spatial circle, $[g]$ runs over conjugacy classes, and $C(g)$ is the centralizer of $g$.

For abelian $G$, this simplifies to

$$
\mathcal H_{\mathcal T/G}(S^1)
\simeq
\bigoplus_{g\in G}\mathcal H_g^G.
$$

The untwisted sector is $g=1$. The other sectors are not optional decorations; they are part of the gauged theory.

## Torus orbifold formula

On a two-dimensional Euclidean torus $T^2$, a flat $G$-bundle is described by a commuting pair $(g,h)$, the holonomies around the two cycles, modulo simultaneous conjugation. A common orbifold formula is

$$
Z_{\mathcal T/G}(T^2)
=
\frac{1}{|G|}
\sum_{\substack{g,h\in G\\ gh=hg}}
Z_{\mathcal T}\!\begin{bmatrix}g\\ h\end{bmatrix}.
$$

Here $g$ is often called the spatial twist and $h$ the temporal insertion, though the formula itself is symmetric under changes of torus cycles. For nonabelian $G$, the condition $gh=hg$ is the flatness condition on the torus.

This formula makes visible why projection alone fails. The term with $g=1$ and sum over $h$ performs the projection in the untwisted Hilbert space:

$$
\frac{1}{|G|}\sum_{h\in G}\operatorname{Tr}_{\mathcal H_1}(U_h q^{L_0-c/24}\bar q^{\bar L_0-c/24}).
$$

The terms with $g\ne 1$ are twisted sectors. Modular transformations exchange the two cycles of the torus, so they mix projection data with twisted-sector data. A modular-invariant orbifold cannot usually keep one and discard the other.

:::note[Source note]
This torus expression is the standard physics normalization for a closed two-dimensional orbifold. The invariant version is the groupoid sum over flat $G$-bundles. On connected $T^2$, groupoid counting turns into the commuting-pair sum divided by $|G|$.
:::

## Discrete torsion and finite topological terms

Finite gauging can include a topological phase depending only on the flat bundle:

$$
e^{iS_\omega[P]}.
$$

In $d$ spacetime dimensions, a bosonic oriented finite-group topological action is often represented by

$$
\omega\in H^d(BG,U(1)).
$$

For $d=2$, this is the familiar **discrete torsion** data. It modifies the orbifold sum by phases. For commuting torus holonomies, one writes schematically

$$
Z_{\mathcal T/G,\omega}(T^2)
=
\frac{1}{|G|}
\sum_{gh=hg}
\epsilon_\omega(g,h)
Z_{\mathcal T}\!\begin{bmatrix}g\\ h\end{bmatrix},
$$

where $\epsilon_\omega(g,h)$ is determined by a group two-cocycle representative. Different cocycle representatives related by a coboundary give equivalent theories after rephasing twisted sectors.

In $d=3$, finite gauge theories with such topological actions are Dijkgraaf–Witten theories. In general dimensions, the same idea supplies finite gauge theory topological terms.

Do not confuse these topological terms with anomalies. A $d$-dimensional cocycle can be a legitimate action term in the gauged theory. An anomaly for gauging a $d$-dimensional finite symmetry is instead represented, in a simple bosonic oriented setting, by one dimension higher:

$$
\alpha\in H^{d+1}(BG,U(1)).
$$

The previous sentence has caveats: fermion parity, spin structures, orientation reversal, antiunitary symmetries, higher-form symmetries, and gravitational backgrounds require refined cohomology or bordism-type classifications. The guiding distinction remains: action terms live in the theory; anomalies obstruct gauging unless supplied by inflow.

## Anomaly obstruction

A finite symmetry can fail to be gaugeable even though it acts perfectly well on local operators. The failure appears when the background partition function cannot be made invariant under background gauge transformations.

One way to state the obstruction is that $Z_{\mathcal T}[M;P]$ is not an honest number depending only on the isomorphism class of $P$. Instead, it transforms by a phase under changes of background trivialization or must be understood as the boundary value of a $(d+1)$-dimensional invertible theory.

If the anomaly is $\alpha$, then the anomalous theory can often be consistently placed on the boundary of a bulk symmetry-protected phase whose partition function supplies the compensating factor:

$$
Z_{\text{bulk}}[Y;\widetilde P]\,Z_{\partial}[\partial Y;P]
$$

is gauge invariant even when $Z_{\partial}$ alone is not.

Thus the finite gauging test is:

$$
Z_{\mathcal T}[M;P]\text{ must be a gauge-invariant function of finite }G\text{-backgrounds}.
$$

If this fails, the symmetry is anomalous. One may still discuss anomaly matching, symmetry defects, or boundary inflow, but one cannot gauge the symmetry as a standalone $d$-dimensional operation.

## Local operators after finite gauging

Let $\mathcal O_i$ be local operators of $\mathcal T$. Gauging keeps $G$-invariant combinations as local operators. For example, if $G=\mathbb Z_2$ acts by

$$
\phi\mapsto -\phi,
$$

then $\phi$ is not a local operator of $\mathcal T/\mathbb Z_2$, while $\phi^2$ can be.

This does not mean that the information carried by $\phi$ has vanished. In a gauged theory, a charged operator may appear as the endpoint of a topological line or as part of a defect construction, depending on the dimension and the details of the theory. Locality is stricter after gauging: operators must be compatible with the gauge redundancy and the allowed bundles.

The gauged theory also contains local or extended operators from twisted sectors. In two-dimensional orbifolds, twist fields are local operators associated with nontrivial monodromy of fields around their insertion. In higher-dimensional finite gauge theories, twist defects and gauge flux defects are extended objects.

A useful mental picture is:

$$
\text{charged operators before gauging}
\quad\longleftrightarrow\quad
\text{defect endpoints or nonlocal data after gauging}.
$$

The exact dictionary is theory-dependent.

## Quantum symmetries after finite gauging

Gauging can create a new symmetry. For a finite abelian group $G$, the gauged theory often has a dual finite symmetry built from characters

$$
\widehat G=\operatorname{Hom}(G,U(1)).
$$

In two-dimensional orbifolds, this is an ordinary quantum zero-form symmetry acting on twisted sectors. In general $d$ dimensions, gauging a finite abelian zero-form symmetry naturally produces a dual $(d-2)$-form symmetry valued in $\widehat G$; its charged objects and topological symmetry operators are extended rather than ordinary local operators.

This is one reason the phrase “gauging removes the symmetry” is misleading. Gauging changes the symmetry structure. It can remove one global symmetry as an ordinary action on local operators, while producing a dual symmetry acting on defects or topological sectors.

For nonabelian finite $G$, the post-gauging topological data is richer and is naturally described in terms of conjugacy classes, centralizers, representations of quantum doubles, and defect categories. Those details belong later in the Defects, Non-Invertible Symmetries, and TQFT chapters.

## Example: finite gauge theory with no matter

If $\mathcal T$ is the trivial theory and we gauge a finite group $G$, the result is pure finite $G$ gauge theory. Its partition function is

$$
Z_{G\text{ gauge}}(M)=
\sum_{[P\to M]}
\frac{1}{|\operatorname{Aut}(P)|}
 e^{iS_\omega[P]}.
$$

For $\omega=0$, this counts flat $G$-bundles with automorphism weights. On connected $M$, this may be written as

$$
Z_{G\text{ gauge}}(M)=
\frac{1}{|G|}
\#\operatorname{Hom}(\pi_1(M),G)
$$

when one counts homomorphisms before quotienting by conjugation. The two expressions are equivalent groupoid cardinalities.

This theory has no propagating gauge boson. Still, it can have nontrivial line operators, surface defects, topological order, ground-state degeneracy on spatial manifolds with nontrivial cycles, and discrete topological response.

Finite gauge theory is therefore a nice antidote to the student misconception that gauge theory means massless spin-one particles. Gauge theory means redundancy plus a sum over gauge backgrounds. Continuous Yang–Mills gauge bosons are one important realization, not the definition.

## Example: two-dimensional orbifold sectors

Let a two-dimensional QFT have finite symmetry $G$. On a spatial circle, the $g$-twisted sector obeys a boundary condition of the schematic form

$$
\Phi(x+2\pi)=g\cdot\Phi(x).
$$

The gauged Hilbert space is not merely the $G$-invariant part of the $g=1$ sector. It is the direct sum over twisted sectors, with the appropriate residual projection:

$$
\mathcal H_{\mathcal T/G}
=
\bigoplus_{[g]}
\mathcal H_g^{C(g)}.
$$

This formula gives a practical way to remember orbifolds:

- $g$ labels the bundle around the spatial circle.
- $C(g)$ is the residual gauge group preserving that bundle.
- The trace over each sector includes temporal holonomies.

The same structure is what the torus path integral sees as commuting pairs $(g,h)$.

## Relation to Kramers–Wannier duality

Finite gauging is closely related to duality. In two-dimensional Ising-type systems, coupling to a $\mathbb Z_2$ background and summing over it is a sharp way to express the passage between order and disorder variables. The duality exchanges local charged operators, disorder defects, and twisted-sector data.

This page will not use the slogan “duality is gauging” as a theorem. Dualities require matching local operators, defects, partition functions, anomalies, and boundary conditions. But finite gauging is one of the cleanest operations by which dual theories are constructed.

Later pages on low-dimensional symmetry technology return to Kramers–Wannier duality, orbifolds, fermionization, and gauging finite symmetries in more detail.

## Common pitfalls

**Pitfall 1: “Finite groups have no gauge fields.”**  
They have no Lie-algebra-valued local gauge potential. They do have finite background fields: flat bundles, transition functions, branch cuts, holonomies, and topological defects.

**Pitfall 2: “Gauging equals taking invariant operators.”**  
Taking invariant local operators is only the untwisted projection. The gauged theory also includes nontrivial bundles, twisted sectors, and possible topological weights.

**Pitfall 3: “The factor $1/|G|$ is arbitrary.”**  
It is the gauge-volume factor in a simple presentation. More invariantly, finite gauging uses groupoid cardinality: each background is weighted by $1/|\operatorname{Aut}(P)|$.

**Pitfall 4: “Discrete torsion is an anomaly.”**  
Discrete torsion is a choice of topological action in the gauged theory. An anomaly is an obstruction to performing the gauging as a standalone theory.

**Pitfall 5: “A finite gauge theory is trivial because it has no local waves.”**  
Finite gauge theories are often topological, but topological does not mean empty. Their nonlocal observables, ground-state sectors, and defect categories can be highly nontrivial.

## Relations to other pages

- [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) gives the general background-summing viewpoint.
- [Quotienting by Symmetry](/symmetry-anomalies-topology/background-fields-and-gauging/quotienting-by-symmetry/) explains why “take the quotient” is an overloaded phrase.
- **Higher-Form Symmetries** later generalizes finite gauging to extended charged operators and higher background fields.
- **Dijkgraaf–Witten Theory** later treats pure finite gauge theories as TQFTs.
- **Kramers–Wannier Duality** later makes the two-dimensional duality relation explicit.

## Research status

The core operation of finite gauging is established. In modern language, the most precise formulation is a sum over a groupoid of finite symmetry backgrounds, possibly weighted by topological action terms, and allowed only when the symmetry has no obstruction to gauging.

Several extensions are active research areas. Finite higher-form and higher-group symmetries require higher gauge fields. Non-invertible symmetries can arise from gauging finite subgroups or from duality defects. Symmetry TFT packages finite gauging as a change of boundary condition in a one-dimension-higher topological theory. Categorical orbifolds and gauging operations make the defect algebra, rather than a group action on fields, primary.

For most graduate QFT uses, the safe rule is enough:

$$
\text{to gauge a finite symmetry, sum over flat finite backgrounds with anomaly-free weights.}
$$

## Exercises

### Exercise 1: The four sectors of a $\mathbb Z_2$ torus orbifold

Let $G=\mathbb Z_2=\{1,a\}$. Write the torus orbifold sum in terms of the four pairs of holonomies.

<details><summary><strong>Solution</strong></summary>

Since $\mathbb Z_2$ is abelian, all pairs commute. The torus sum is

$$
Z_{\mathcal T/\mathbb Z_2}(T^2)
=
\frac12\left(
Z\!\begin{bmatrix}1\\1\end{bmatrix}
+Z\!\begin{bmatrix}1\\a\end{bmatrix}
+Z\!\begin{bmatrix}a\\1\end{bmatrix}
+Z\!\begin{bmatrix}a\\a\end{bmatrix}
\right).
$$

The first two terms are traces over the untwisted sector with and without the symmetry insertion. Together they project onto $\mathbb Z_2$-even states. The last two terms come from the $a$-twisted sector and are required in the orbifold theory.

</details>

### Exercise 2: Pure finite gauge theory on a circle

For connected $M=S^1$, compute the untwisted pure finite gauge theory partition function with gauge group $G$ using

$$
Z(S^1)=\sum_{[P\to S^1]}\frac{1}{|\operatorname{Aut}(P)|}.
$$

<details><summary><strong>Solution</strong></summary>

Flat $G$-bundles on $S^1$ are classified by a holonomy $g\in G$ modulo conjugation. The automorphism group of the bundle with holonomy $g$ is the centralizer

$$
C(g)=\{h\in G\mid hg=gh\}.
$$

Thus

$$
Z(S^1)=\sum_{[g]}\frac{1}{|C(g)|}.
$$

Each conjugacy class $[g]$ has size $|G|/|C(g)|$, so

$$
\frac{1}{|C(g)|}=\frac{|[g]|}{|G|}.
$$

Summing over conjugacy classes gives

$$
Z(S^1)=\frac{1}{|G|}\sum_{[g]}|[g]|=1.
$$

Equivalently, count all homomorphisms $\pi_1(S^1)\to G$, which are just elements of $G$, and divide by $|G|$.

</details>

### Exercise 3: Projection operator

Show that

$$
\Pi_G=\frac{1}{|G|}\sum_{g\in G}U_g
$$

is a projector if $U_gU_h=U_{gh}$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\Pi_G^2
=\frac{1}{|G|^2}\sum_{g,h\in G}U_gU_h
=\frac{1}{|G|^2}\sum_{g,h\in G}U_{gh}.
$$

For each fixed $k\in G$, the equation $gh=k$ has exactly $|G|$ solutions: choose $g$ freely and set $h=g^{-1}k$. Therefore

$$
\Pi_G^2
=\frac{1}{|G|^2}\sum_{k\in G}|G|U_k
=\frac{1}{|G|}\sum_{k\in G}U_k
=\Pi_G.
$$

The image of $\Pi_G$ is the subspace invariant under all $U_g$.

</details>

## References

- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology,” 1990. Classic reference for finite gauge theories and group-cohomology topological actions.
- Lance Dixon, Jeffrey Harvey, Cumrun Vafa, and Edward Witten, “Strings on Orbifolds,” 1985–1986. Classic worldsheet orbifold construction and twisted-sector technology.
- Cumrun Vafa, “Modular Invariance and Discrete Torsion on Orbifolds,” 1986. Classic source for discrete torsion in two-dimensional orbifolds.
- Cumrun Vafa and Edward Witten, “On Orbifolds with Discrete Torsion,” 1994. Geometric interpretation and examples of discrete torsion.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” 2015. Modern background-field and gauging perspective for ordinary and generalized symmetries.
- Daniel S. Freed and Frank Quinn, “Chern–Simons Theory with Finite Gauge Group,” 1993. Mathematical finite-gauge-theory construction and finite gauge-field sums.

## Version history

- **2026-06-17:** Initial polished preview page on finite-group gauging, orbifold sectors, automorphism weights, discrete torsion, and anomaly obstruction.
