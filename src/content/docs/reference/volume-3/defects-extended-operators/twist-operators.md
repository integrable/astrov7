---
title: "Twist Operators"
description: "Twist operators and twist defects as symmetry monodromies, branch cuts, orbifold sectors, and replica insertions."
sidebar:
  label: "Twist Operators"
  order: 6
level: Advanced
status: "Polished draft"
source: "Kadanoff–Ceva and orbifold twist fields; branch-point twist fields for Rényi entropy; generalized-symmetry defect viewpoint."
topics:
  - twist operators
  - branch cuts
  - symmetry defects
  - orbifolds
  - replica trick
  - entanglement entropy
canonicalTopics:
  - twist-operators
  - twist-defects
  - branch-point-twist-fields
  - orbifold-twisted-sectors
researchStatus:
  established:
    - "A symmetry twist operator is a codimension-two defect around which fields return transformed by a symmetry element."
    - "Replica twist operators implement cyclic permutation monodromy among replicated copies and compute Rényi entropies."
  active:
    - "Twist defects in higher-dimensional, anomalous, fermionic, non-invertible, or categorical symmetry settings remain an active research interface."
---

## Summary

A **twist operator** is a disorder operator whose singularity is a symmetry monodromy. Around the insertion, fields are allowed to come back transformed by a symmetry element rather than exactly equal to themselves. In local transverse polar coordinates,

$$
\Phi(r,\theta+2\pi,y)=g\cdot \Phi(r,\theta,y),
$$

where $g$ is an exact symmetry of the theory and $y$ are coordinates along the support of the defect.

In two dimensions, a twist operator is often a local field: it is the endpoint of a symmetry line. In higher dimensions, the natural symmetry-twist defect has codimension two: it is the boundary of a codimension-one symmetry wall. Replica twist operators, used to compute Rényi and entanglement entropies, are the most widely encountered modern example. They implement the cyclic permutation symmetry of $n$ replicated QFTs.

Twist operators are the meeting point of several languages:

$$
\text{symmetry defects}
\quad\Longleftrightarrow\quad
\text{branch cuts}
\quad\Longleftrightarrow\quad
\text{twisted sectors}
\quad\Longleftrightarrow\quad
\text{replica geometry}.
$$

The unifying idea is simple: the branch cut is auxiliary, but the monodromy around its endpoint is physical.

## Prerequisites

You should know the previous pages on local and extended operators, disorder operators, and surface operators. It also helps to know ordinary global symmetries, background fields, finite gauging, and the basic idea of the replica trick.

## From a symmetry wall to a twist operator

Let $G$ be an internal global symmetry. For each $g\in G$, an ordinary invertible symmetry in $d$ dimensions can be represented by a codimension-one topological defect $U_g(M_{d-1})$. Crossing the wall acts on local operators by

$$
\mathcal O(x)\longmapsto g\cdot\mathcal O(x).
$$

If the wall has no boundary, it implements a global symmetry transformation on one side. If the wall is allowed to end on a codimension-two submanifold $\Sigma$, the boundary is a twist defect. A small circle linking $\Sigma$ crosses the wall once, so fields have monodromy $g$ around $\Sigma$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A twist operator is the endpoint of a symmetry branch cut, so a loop around it applies the symmetry action.](/figures/symmetry-anomalies-topology/twist-operator-monodromy.svg)

<figcaption>

A symmetry wall $U_g$ may be drawn as a branch cut ending on a twist defect $\tau_g$. A small linking loop around $\tau_g$ crosses the cut once, so fields return transformed by $g$. The cut can move; the monodromy and endpoint data are physical.

</figcaption>
</figure>

This picture is deceptively powerful. It explains why twist operators are disorder operators, why they create twisted sectors, and why crossing relations are controlled by the group law.

:::note[Source note]
The same object appears under several names: symmetry twist field, branch-point twist field, orbifold twist field, twist defect, or defect endpoint. The precise meaning depends on dimension and context. This page uses “twist operator” broadly, and says “twist defect” when the support has positive dimension.
:::

## The local monodromy condition

Near a codimension-two twist defect $\Sigma$, choose local coordinates

$$
(r,\theta,y^1,\ldots,y^{d-2}),
$$

where $(r,\theta)$ are polar coordinates in the transverse plane and $y$ coordinates run along $\Sigma$. A $g$-twist imposes

$$
\Phi(r,\theta+2\pi,y)=g\cdot\Phi(r,\theta,y).
$$

For an operator $\mathcal O$ of charge or representation $R$, the corresponding monodromy is

$$
\mathcal O(r,\theta+2\pi,y)=R(g)\mathcal O(r,\theta,y).
$$

In a path-integral definition, this means one integrates over fields on the punctured neighborhood of $\Sigma$ with this boundary condition. Equivalently, one cuts the transverse plane along a ray, imposes a discontinuity $g$ across the cut, and then declares the endpoint of the cut to be the twist insertion.

The cut is a presentation. The endpoint, or more generally the codimension-two defect $\Sigma$, is the operator.

## Twist operators are special disorder operators

A general disorder operator can impose arbitrary singular boundary data compatible with the theory. A twist operator imposes boundary data coming from a symmetry. That special origin gives extra structure.

First, the singularity is mild: the fields need not blow up; they can be multivalued up to a symmetry. Second, if the symmetry wall is topological, the branch cut can be moved freely unless it crosses charged operators or other defects. Third, the group law controls fusion:

$$
\tau_g\times \tau_h\sim \tau_{gh}+\text{defect-local excitations},
$$

at least in a simple invertible-symmetry setting. In nonabelian groups, conjugacy and ordering matter. In anomalous, gauged, or non-invertible settings, this schematic fusion rule must be refined.

A twist operator is therefore not just a singular insertion. It is the local endpoint of a symmetry action.

## Two-dimensional symmetry twist fields

In two-dimensional QFT, a codimension-one symmetry defect is a line, and its endpoint is a local operator. This makes two dimensions the natural laboratory for twist fields.

Suppose the theory has a $\mathbb Z_2$ symmetry acting as

$$
\phi\mapsto -\phi.
$$

A $\mathbb Z_2$ twist field $\tau$ at the origin imposes

$$
\phi(e^{2\pi i}z,e^{-2\pi i}\bar z)=-\phi(z,\bar z).
$$

Equivalently, one draws a branch cut ending at the origin. Crossing the cut sends $\phi$ to $-\phi$. Correlation functions with $\tau$ are then defined by evaluating the original path integral on fields with this monodromy.

This is why twist fields in two-dimensional CFT often have fractional conformal dimensions. The local geometry around the insertion is not the ordinary single-valued geometry of the original field; modes can become fractionally moded. In free-field examples, this can be computed explicitly. In rational CFT, twist fields are organized by the defect and orbifold data.

## Ising order and disorder as twist fields

The Ising disorder field $\mu$ is a twist field for the $\mathbb Z_2$ spin-flip structure in an appropriate description. A branch cut ending on $\mu$ flips the sign of spin operators crossing the cut. Therefore taking a spin field $\sigma$ around $\mu$ produces a sign:

$$
\sigma(e^{2\pi i}z)=-\sigma(z).
$$

At the critical point, $\sigma$ and $\mu$ have the same scaling dimension,

$$
(h,\bar h)=\left(\frac{1}{16},\frac{1}{16}\right),
$$

but they are not mutually local in the naive sense. Correlators containing both fields remember branch choices. This is not a bug in the CFT; it is precisely the point. The order and disorder fields expose the nontrivial symmetry-defect algebra.

A useful mental model is that $\sigma$ measures the ordered spin variable, while $\mu$ creates a branch cut for it. Kramers–Wannier duality exchanges the roles of the two.

## Orbifold twist sectors

Now let a theory $\mathcal T$ have a finite symmetry group $G$, and form the orbifold or gauged theory $\mathcal T/G$. The path integral of the gauged theory sums over $G$ bundles. On a circle, this means there are sectors in which fields obey

$$
\Phi(x+2\pi)=g\cdot\Phi(x),
\qquad g\in G.
$$

These are **twisted sectors**. In two-dimensional orbifold CFT, local twist fields create the corresponding twisted-sector states under radial quantization.

For nonabelian $G$, twisted sectors are labeled not by individual group elements in an invariant way, but by conjugacy classes $[g]$. Additional local data can transform under the centralizer

$$
C_g=\{h\in G\mid hg=gh\}.
$$

This is the first place where the innocent-looking phrase “the $g$-twist field” becomes too simple. The full orbifold spectrum depends on conjugacy classes, centralizer representations, possible discrete torsion, and anomaly data.

## Replica twist operators

Replica twist operators arise when computing Rényi entropies. Given a density matrix $\rho_A$ for a spatial region $A$, the $n$th Rényi entropy is

$$
S_n(A)=\frac{1}{1-n}\log \operatorname{Tr}\rho_A^n.
$$

The replica method writes $\operatorname{Tr}\rho_A^n$ as a path integral on an $n$-sheeted geometry. Equivalently, one can work in the $n$-fold product theory

$$
\mathcal T^{\otimes n}
$$

and insert a twist defect for the cyclic permutation symmetry

$$
(1\;2\;\cdots\;n)\in S_n.
$$

Around the entangling surface $\partial A$, the replicated fields obey

$$
\Phi_k(r,\theta+2\pi,y)=\Phi_{k+1}(r,\theta,y),
\qquad k=1,
\ldots,n,
$$

with $k+n\equiv k$. Thus the branch-point twist defect is a symmetry twist defect for replica symmetry.

In two-dimensional CFT, for a single interval $A=[u,v]$, this becomes a two-point function of local twist fields,

$$
\operatorname{Tr}\rho_A^n
\propto
\langle \tau_n(u)\,\tilde \tau_n(v)\rangle.
$$

For a CFT with central charge $c$, the cyclic replica twist field has conformal weights

$$
h_n=\bar h_n=\frac{c}{24}\left(n-\frac{1}{n}\right).
$$

This formula is one of the most useful sanity checks in the subject. It reproduces the familiar vacuum interval result

$$
\operatorname{Tr}\rho_A^n\propto |u-v|^{-\frac{c}{6}(n-1/n)}.
$$

:::warning[Replica caveat]
Replica twist operators are first defined for positive integers $n$. Entanglement entropy requires analytic continuation in $n$ and the limit $n\to 1$. That continuation is often physically correct and enormously useful, but it is not automatically guaranteed by the integer-$n$ construction alone.
:::

## Twist defects in higher dimensions

In $d>2$, the endpoint of a codimension-one symmetry wall is not local. It has codimension two. For an ordinary internal symmetry, a twist defect is supported on a $(d-2)$-dimensional submanifold $\Sigma$.

For example:

- in three dimensions, a symmetry twist defect is a line,
- in four dimensions, a symmetry twist defect is a surface,
- a replica twist defect is supported on the entangling surface,
- a codimension-two monodromy defect for a gauge or flavor symmetry is a surface operator.

Higher-dimensional twist defects have their own local dynamics. There can be defect-local operators living on $\Sigma$, displacement operators measuring broken transverse translations, and defect RG flows. The twist condition tells us the monodromy, but not necessarily the entire defect theory.

This is a recurring theme: a singularity label is not always a complete quantum definition. Renormalization may require choosing local counterterms and defect-local degrees of freedom.

## Fusion and crossing

For an invertible finite symmetry, symmetry walls obey

$$
U_g\,U_h=U_{gh}.
$$

The corresponding twist defects inherit a version of this multiplication. Bringing two twist endpoints together can produce a twist endpoint for the product symmetry element, together with defect-local operators:

$$
\tau_g(x)\,\tau_h(0)
\sim
\sum_{a} C_{gh}^{a}(x)\,\mathcal D_{gh,a}(0).
$$

For abelian $G$, the product $gh$ is independent of ordering. For nonabelian $G$, the order matters, and moving one branch point around another can conjugate monodromy data. In orbifolds, this is why conjugacy classes and centralizers naturally appear.

Crossing an ordinary operator through a $g$-wall acts by $g$. Moving an operator around a $g$-twist defect therefore gives the monodromy

$$
\mathcal O\longmapsto g\cdot \mathcal O.
$$

The twist defect is a machine for making symmetry action geometrical.

## Anomalies and twist defects

An anomaly can obstruct the clean topological manipulation of symmetry defects. If the symmetry $G$ has a ’t Hooft anomaly, one may still discuss $G$ background fields and twisted boundary conditions, but the partition function can pick up phases under changes of background representative. In the defect language, the symmetry wall is not an ordinary standalone topological defect unless it is accompanied by anomaly inflow.

Consequences include:

- a branch cut may require a bulk topological term to be well-defined,
- fusing twist defects may acquire cocycle phases,
- gauging the symmetry may be obstructed,
- twist defects may carry protected boundary degrees of freedom,
- endpoints of symmetry walls may fail to exist as genuine operators in the standalone theory.

This is one of the reasons twist operators are not merely a CFT curiosity. They expose the same obstruction data that later appears as ’t Hooft anomaly, SPT boundary anomaly, or symmetry TFT inflow.

## Fermions and spin structures

Twist operators involving fermions require extra care. A twist by $(-1)^F$ changes fermion boundary conditions. In Euclidean path integrals, the difference between periodic and antiperiodic fermions around a cycle is not decoration; it is spin-structure data.

Replica twist operators in fermionic theories also require spin-structure choices on the replicated geometry. Treating the cyclic permutation symmetry alone may miss signs from transporting fermions around branch points. In many practical computations, these signs are packaged by choosing spin structures on the branched cover or by including appropriate fermion-parity defects.

The practical rule is blunt: whenever a twist involves fermions, ask what happens to $(-1)^F$ around every cycle.

## Common pitfalls

### A twist operator is not the branch cut

The branch cut is a way to draw the monodromy. The twist insertion is the endpoint or boundary of the branch cut. Moving the cut is allowed when the symmetry wall is topological and no charged operator is crossed.

### Twist defects need not be topological

The symmetry wall may be topological, but the boundary of that wall can carry local dynamics. Replica twist defects, for instance, are generally not topological; their correlators depend on geometry and encode entanglement data.

### Orbifold twist fields are not always labeled by group elements

For nonabelian orbifolds, conjugacy classes label twisted sectors. Operators in a sector can also carry representations of the centralizer. Discrete torsion and anomalies further modify the story.

### Replica twist operators are symmetry twist operators, but in a bigger theory

The symmetry is not a symmetry of one copy of $\mathcal T$; it is the permutation symmetry of $\mathcal T^{\otimes n}$. Forgetting this leads to confusion about why a geometric branch point can be represented as an operator insertion.

### Analytic continuation in replica number is an additional step

Integer $n$ defines the replicated theory. The limit $n\to 1$ is a further analytic continuation. It is standard, powerful, and sometimes subtle.

## Relation to nearby pages

- [Disorder Operators](/symmetry-anomalies-topology/defects-extended-operators/disorder-operators/) gives the broader path-integral framework of singular boundary conditions.
- [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) treats codimension-two monodromy defects in gauge theories.
- [Domain Walls as Defects](/symmetry-anomalies-topology/defects-extended-operators/domain-walls-as-defects/) develops the codimension-one wall viewpoint.
- [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) develops the algebraic structure behind fusing walls, lines, and twist defects.
- [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/) explains twisted sectors and orbifold sums from the background-field perspective.
- [Anomalies of Discrete Symmetries: Preview](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/anomalies-of-discrete-symmetries-preview/) explains why some twist constructions require inflow.

## Research status

Symmetry twist operators, orbifold twist fields, and replica branch-point twists are standard tools. Their basic definitions are settled and widely used in statistical mechanics, CFT, entanglement calculations, and gauge theory.

The active frontier is the systematic organization of twist defects for anomalous symmetries, higher-form symmetries, non-invertible symmetries, fermionic symmetries, and higher-dimensional defect QFT. In these settings, “draw a branch cut” is only the first line of the story; the full answer includes defect-local degrees of freedom, anomaly inflow, fusion categories, and sometimes symmetry TFT.

## Exercises

### Exercise 1: Monodromy from a branch cut

Let a $\mathbb Z_N$ symmetry act on a complex scalar by

$$
\phi\mapsto e^{2\pi i/N}\phi.
$$

A twist operator $\tau_k$ is defined by a branch cut across which $\phi$ jumps by $e^{2\pi i k/N}$. What is the monodromy of $\phi$ around $\tau_k$?

<details><summary><strong>Solution</strong></summary>

A small loop around $\tau_k$ crosses the branch cut once. Crossing the cut applies the symmetry action $g^k$, so

$$
\phi(r,\theta+2\pi)=e^{2\pi i k/N}\phi(r,\theta).
$$

Thus $\tau_k$ creates a $\mathbb Z_N$ twist sector with monodromy $g^k$.

</details>

### Exercise 2: Fusion of abelian twists

For the same $\mathbb Z_N$ theory, argue that the leading twist label in the fusion of $\tau_k$ and $\tau_\ell$ is $\tau_{k+\ell}$, with the label understood modulo $N$.

<details><summary><strong>Solution</strong></summary>

A loop enclosing both twist insertions crosses both branch cuts, so the total monodromy is the product

$$
g^k g^\ell=g^{k+\ell}.
$$

Because $G=\mathbb Z_N$ is abelian, the ordering does not matter. Therefore the fused defect lies in the $k+\ell$ twisted sector modulo $N$. The full OPE may contain multiple defect-local operators in that sector, but the monodromy label is fixed.

</details>

### Exercise 3: Scaling dimension of the two-dimensional replica twist

In a two-dimensional CFT of central charge $c$, the cyclic replica twist field has

$$
h_n=\bar h_n=\frac{c}{24}\left(n-\frac{1}{n}\right).
$$

Use this to derive the power of the interval length in $\operatorname{Tr}\rho_A^n$ for a single interval $A=[u,v]$ in the vacuum.

<details><summary><strong>Solution</strong></summary>

The two-point function of a primary field with weights $(h_n,\bar h_n)$ scales as

$$
\langle \tau_n(u)\tilde\tau_n(v)\rangle
\propto |u-v|^{-2h_n-2\bar h_n}.
$$

Since $h_n=\bar h_n$, the exponent is

$$
2h_n+2\bar h_n=4h_n
=\frac{c}{6}\left(n-\frac{1}{n}\right).
$$

Therefore

$$
\operatorname{Tr}\rho_A^n
\propto |u-v|^{-\frac{c}{6}(n-1/n)},
$$

up to cutoff-dependent normalization factors. Taking $S_n=(1-n)^{-1}\log\operatorname{Tr}\rho_A^n$ gives the standard logarithmic interval scaling after restoring the UV cutoff.

</details>

## References and further reading

- L. P. Kadanoff and H. Ceva, “Determination of an operator algebra for the two-dimensional Ising model.”
- L. Dixon, J. Harvey, C. Vafa, and E. Witten, “Strings on Orbifolds.”
- J. L. Cardy, O. A. Castro-Alvaredo, and B. Doyon, “Form factors of branch-point twist fields in quantum integrable models and entanglement entropy.”
- P. Calabrese and J. Cardy, “Entanglement entropy and quantum field theory.”
- H. Casini and M. Huerta, “Entanglement entropy in free quantum field theory.”
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- A. M. Polyakov, *Gauge Fields and Strings*, for disorder, duality, loop, and topological-defect perspectives.

## Version history

- 2026-06-19: First polished draft. Defines twist operators as symmetry-monodromy disorder defects, develops two-dimensional, orbifold, replica, higher-dimensional, anomalous, and fermionic cases, and adds exercises with solutions.
