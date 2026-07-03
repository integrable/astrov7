---
title: "Homotopy Classification"
description: "Explains how finite-energy fields, defects, and instantons are classified by homotopy classes, and where that classification must be refined in gauge theory and quantum theory."
sidebar:
  label: "Homotopy Classification"
  order: 2
level: Advanced
status: "Polished draft"
source: "Srednicki §§92–94; Polyakov Chs. 4 and 6; Nakahara Ch. 4; Frankel on forms and bundles; Altland–Simons Ch. 8; Manton–Sutcliffe; Tong TASI soliton notes."
topics:
  - homotopy classification
  - topological sectors
  - solitons
  - defects
  - vacuum manifolds
  - gauge bundles
  - exact homotopy sequence
canonicalTopics:
  - homotopy-classification
  - topological-defect-classification
  - vacuum-manifold-homotopy
  - finite-energy-boundary-conditions
  - solitonic-charge
researchStatus:
  established:
    - "For fixed boundary conditions and allowed deformations, many classical topological sectors are labeled by homotopy classes of maps from compactified space or linking spheres into a target or vacuum manifold."
    - "In gauge theory, the same physical classification is often better stated in terms of bundles, fluxes, transition functions, or characteristic classes rather than a gauge-dependent winding of a field."
  active:
    - "Modern QFT refines the naive homotopy classification using generalized symmetries, dynamical defects, anomalies, bordism, non-invertible solitonic symmetries, and quantum tunneling effects."
---

## Summary

Homotopy classification is the first reliable language for topological sectors. The idea is simple: finite energy, finite action, defect boundary conditions, or gauge-bundle regularity turn a field configuration into a continuous map from a compact space into a target space. Smooth deformations of the field become homotopies of that map. If two maps are not homotopic, the corresponding configurations cannot be smoothly deformed into each other without leaving the allowed configuration space.

In its most familiar scalar-field form,

$$
\text{finite-energy boundary data}
\quad\leadsto\quad
f:S^n\to \mathcal M_{\mathrm{vac}},
\qquad
[f]\in \pi_n(\mathcal M_{\mathrm{vac}})
$$

or, more carefully, a based or unbased homotopy class of maps into the vacuum manifold. The sphere $S^n$ may be compactified space, a sphere at spatial infinity, a small sphere linking a defect, or the boundary of Euclidean spacetime.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Flowchart from physical boundary conditions to compactification or linking spheres, then to maps into the vacuum manifold or bundle data, and finally to homotopy labels.](/figures/symmetry-anomalies-topology/homotopy-classification-flow.svg)

<figcaption>

Homotopy classification is a workflow, not a slogan. First specify the allowed configurations and deformations. Then identify the compact domain that records the boundary or defect data. Only after this do homotopy groups, bundle classes, winding numbers, or characteristic classes become meaningful labels.

</figcaption>
</figure>

The classic dictionary in three spatial dimensions is

$$
\begin{array}{c|c|c}
\text{object} & \text{sphere that sees it} & \text{typical label} \\
\hline
\text{domain wall} & S^0 & \pi_0(\mathcal M_{\mathrm{vac}}) \\
\text{vortex or string} & S^1 & \pi_1(\mathcal M_{\mathrm{vac}}) \\
\text{monopole} & S^2 & \pi_2(\mathcal M_{\mathrm{vac}}) \\
\text{texture or Skyrmion} & S^3 & \pi_3(\mathcal M_{\mathrm{vac}})
\end{array}
$$

This dictionary is powerful, but not automatic. It must be applied to the actual configuration space after boundary conditions, singularities, gauge redundancy, global form, and allowed charged objects have been fixed.

## Prerequisites

You should already know the configuration-space viewpoint from [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/). You should also know how order parameters and vacuum manifolds appear in [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) and [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/).

For gauge-theory examples, the relevant background is [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), [Local Versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/), [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/), and [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

No theorem-level algebraic topology is assumed. The page uses homotopy groups as QFT tools: a loop that cannot be contracted, a sphere map that cannot be filled in, and a winding number that cannot change under smooth deformation.

## Core idea

A topological classification begins with a space of allowed configurations

$$
\mathcal C
=\{\text{fields satisfying the chosen rules}\}/\mathcal G_{\rm allowed}.
$$

Two configurations are in the same topological sector if there exists a continuous path in $\mathcal C$ connecting them. Written as fields, such a path is a one-parameter family

$$
\Phi_s,
\qquad 0\le s\le 1,
$$

where every intermediate configuration satisfies the same finite-energy, boundary, regularity, and gauge-equivalence rules.

Homotopy enters because many QFT boundary conditions reduce a configuration to a map

$$
f:X\to Y.
$$

Here $X$ is the compact space that records spatial infinity, a defect-linking sphere, or Euclidean boundary data. The target $Y$ is often the vacuum manifold $\mathcal M_{\mathrm{vac}}$, but it can also be a gauge group, a classifying space, a quotient, or a space of boundary conditions.

A deformation $\Phi_s$ induces a homotopy

$$
f_s:X\to Y.
$$

If $f_0$ and $f_1$ are not homotopic, then $\Phi_0$ and $\Phi_1$ cannot be connected without violating the rules. That is the mathematical reason topological sectors are stable under smooth time evolution.

The mantra is

$$
\text{topological sectors}
=\text{homotopy classes of the relevant boundary or bulk maps},
$$

but the word **relevant** is carrying half the physics.

## Setup and conventions

Let $\Sigma$ be a spatial slice of dimension $d$. A static scalar-field configuration is a map

$$
\phi:\Sigma\to \mathcal T,
$$

where $\mathcal T$ is the field target. If the potential has vacuum manifold

$$
\mathcal M_{\mathrm{vac}}\subset \mathcal T,
$$

finite energy often requires $\phi$ to approach $\mathcal M_{\mathrm{vac}}$ at spatial infinity. For a defect of spatial dimension $p$, the normal space has dimension

$$
r=d-p.
$$

A small sphere linking the defect has dimension

$$
S^{r-1}=S^{d-p-1}.
$$

The defect is then detected by a boundary map

$$
\phi_{\rm link}:S^{d-p-1}\to \mathcal M_{\mathrm{vac}},
$$

and the first-pass classification is

$$
[\phi_{\rm link}]\in \pi_{d-p-1}(\mathcal M_{\mathrm{vac}}).
$$

For a nonsingular texture filling all of space, one often compactifies

$$
\mathbb R^d\cup\{\infty\}\simeq S^d
$$

and classifies maps

$$
\phi:S^d\to\mathcal M_{\mathrm{vac}}
$$

by $\pi_d(\mathcal M_{\mathrm{vac}})$.

This page uses the term “homotopy group” in the standard based sense. Many QFT applications are actually unbased classifications, because the value at infinity may be allowed to move by a global symmetry. That distinction matters and is discussed below.

:::note[Convention-sensitive source note]
Some soliton texts classify maps by fixing a vacuum at infinity; others quotient by the global symmetry that moves that vacuum. The first gives based homotopy groups $\pi_n(\mathcal M_{\mathrm{vac}},m_0)$, while the second gives unbased homotopy classes modulo a group action. Both are useful. Always ask whether the vacuum at infinity is a fixed boundary condition, a chosen superselection sector, or a point on a moduli space to be quotiented.
:::

## From boundary conditions to spheres

The appearance of spheres is not magic. It is the geometry of infinity and linking.

For a localized finite-energy configuration in $d$ spatial dimensions, the outside region is approximately radial. If the field tends to a single vacuum independent of direction, one may add the point at infinity:

$$
\mathbb R^d\cup\{\infty\}\simeq S^d.
$$

This gives textures and Skyrmions. The field itself defines the map from the compactified space.

For a defect, the field does not approach the same vacuum in all directions around the defect. Instead, the defect is measured by going around it. The transverse directions form $\mathbb R^r$, and a small sphere around the defect is

$$
S^{r-1}\subset \mathbb R^r.
$$

A vortex line in three spatial dimensions has $p=1$, so $r=2$ and the linking sphere is $S^1$. A point monopole has $p=0$, so $r=3$ and the linking sphere is $S^2$. A domain wall has $p=d-1$, so $r=1$ and the linking “sphere” is $S^0$, two points on opposite sides of the wall.

For Euclidean instantons, the same logic applies to spacetime rather than space. Finite action on $\mathbb R^D$ often makes the field approach a pure gauge or vacuum at infinity, so the boundary is

$$
S^{D-1}_\infty.
$$

For four-dimensional Yang–Mills instantons, the boundary map at infinity is a map

$$
S^3_\infty\to G,
$$

and its winding is related to the second Chern number

$$
\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F).
$$

## The basic defect dictionary

Let $\mathcal M=\mathcal M_{\mathrm{vac}}$. The first-pass homotopy dictionary is:

| Spatial dimension $d$ | Object | Normal sphere | First-pass label | Example |
|---:|---|---|---|---|
| any $d$ | domain wall | $S^0$ | $\pi_0(\mathcal M)$ | Ising wall between disconnected vacua |
| $d\ge2$ | vortex, string, line defect | $S^1$ | $\pi_1(\mathcal M)$ | global $U(1)$ vortex |
| $d\ge3$ | monopole, point defect | $S^2$ | $\pi_2(\mathcal M)$ | $O(3)$ hedgehog or ’t Hooft–Polyakov monopole data |
| $d\ge3$ | texture, Skyrmion | compactified $S^3$ | $\pi_3(\mathcal M)$ | Skyrmion in an $SU(2)$ chiral field |
| Euclidean $D=4$ | instanton sector | $S^3_\infty$ or bundle on $S^4$ | $\pi_3(G)$ or $c_2$ | Yang–Mills instanton |

This table is not a theorem about all QFTs. It is the simplest output of a specific recipe:

1. take a classical field with vacuum manifold $\mathcal M$;
2. demand finite energy or fixed defect behavior;
3. prohibit singular deformations;
4. ignore dynamical processes that can end or screen defects;
5. ignore gauge identifications beyond the stated quotient.

In simple global-symmetry models, that recipe is often enough. In gauge theories and quantum theories, it is the beginning of the story.

## Domain walls and zeroth homotopy

The homotopy set $\pi_0(\mathcal M)$ is the set of connected components of $\mathcal M$. If $\mathcal M$ has more than one component, a field can approach one vacuum component on the left and a different one on the right. A domain wall interpolates between them.

For a real scalar theory with

$$
V(\phi)=\frac\lambda4(\phi^2-v^2)^2,
$$

the vacuum manifold is

$$
\mathcal M=\{-v,+v\}.
$$

Thus

$$
\pi_0(\mathcal M)=\mathbb Z_2
$$

as a set of two components. A kink in one spatial dimension is a field with

$$
\phi(-\infty)=-v,
\qquad
\phi(+\infty)=+v.
$$

The topological datum is not a loop or a sphere map. It is simply the fact that the two ends of space land in different components of the vacuum manifold.

This example also shows why $\pi_0$ is slightly different from higher homotopy groups. It is naturally a set. It may have a group structure if $\mathcal M$ is itself a group or has extra structure, but topology alone gives connected components, not addition.

## Vortices and fundamental groups

If

$$
\mathcal M=S^1,
$$

then

$$
\pi_1(S^1)\simeq\mathbb Z.
$$

A vortex in two spatial dimensions is detected by a phase map at infinity,

$$
\phi(r,\varphi)\simeq v e^{i\alpha(\varphi)},
\qquad
\varphi\in S^1_\infty.
$$

Single-valuedness gives

$$
\alpha(2\pi)-\alpha(0)=2\pi n,
\qquad n\in\mathbb Z.
$$

The integer $n$ is the winding number. It is developed in detail in [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/).

The physical interpretation depends on whether the $U(1)$ is global or gauged. A global vortex has long-range gradient energy and in two spatial dimensions usually has logarithmically divergent energy with system size. A local, or Abrikosov–Nielsen–Olesen, vortex can have finite tension because the gauge field cancels the angular gradient at infinity. The homotopy label survives, but the energy and long-distance physics change.

## Monopoles and second homotopy

A pointlike defect in three spatial dimensions is detected by a sphere surrounding the point:

$$
S^2_{\rm link}\to\mathcal M.
$$

If $\mathcal M=S^2$, then

$$
\pi_2(S^2)\simeq\mathbb Z.
$$

The simplest representative is the hedgehog map

$$
\hat n(\mathbf x)=\frac{\mathbf x}{|\mathbf x|},
\qquad
\hat n:S^2_\infty\to S^2.
$$

In the ’t Hooft–Polyakov monopole, the Higgs field in the adjoint representation approaches a vacuum value at infinity. Its direction defines a map

$$
\hat\Phi:S^2_\infty\to G/H.
$$

For the familiar breaking $SU(2)\to U(1)$,

$$
G/H\simeq S^2,
$$

so the asymptotic Higgs field has an integer degree. Physically the same integer is magnetic charge. But the gauge-invariant statement is not merely “the scalar winds.” The gauge field and Higgs field together define an unbroken $U(1)$ bundle over $S^2_\infty$, whose first Chern class is the magnetic charge.

This distinction is the first lesson of gauge theory topology: a winding visible in one gauge may become a transition function or bundle class in another.

## Textures and compactified space

A texture is not detected by a sphere linking a singular core. It is a nonsingular configuration spread through space. If $\Sigma=\mathbb R^3$ and the field approaches a fixed vacuum at infinity, then

$$
\Sigma\cup\{\infty\}\simeq S^3.
$$

For a target with

$$
\pi_3(\mathcal M)\ne0,
$$

there can be nontrivial maps

$$
S^3\to\mathcal M.
$$

The Skyrme model uses the fact that

$$
SU(2)\simeq S^3,
\qquad
\pi_3(SU(2))\simeq\mathbb Z.
$$

A field

$$
U(\mathbf x):S^3\to SU(2)
$$

has an integer degree. In the Skyrme model this integer is interpreted as baryon number. Topology gives the conserved integer, but topology alone does not guarantee a stable finite-size classical solution. In the simplest two-derivative sigma model, Derrick scaling tends to shrink or spread configurations; the Skyrme term or other dynamics is needed to stabilize a soliton size.

## Instantons and maps at Euclidean infinity

Instantons are finite-action Euclidean field configurations. In four-dimensional Yang–Mills theory, finite action implies that at Euclidean infinity the field strength vanishes sufficiently fast, so the connection approaches a pure gauge:

$$
A\sim i\,g^{-1}dg
$$

with the precise factor depending on whether generators are Hermitian or anti-Hermitian. Thus one obtains a map

$$
g:S^3_\infty\to G.
$$

For $G=SU(N)$,

$$
\pi_3(SU(N))\simeq\mathbb Z
$$

for $N\ge2$. The integer can also be written as the Chern number

$$
k=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F)
$$

with the trace and orientation conventions fixed in the Topological Terms chapter.

:::note[Convention-sensitive source note]
The relation between the winding of $g:S^3\to G$ and $k=(8\pi^2)^{-1}\int\operatorname{tr}(F\wedge F)$ depends on whether $A$ is Hermitian or anti-Hermitian and on the sign used in $D=d-iA$. This volume uses Hermitian generators and $F=dA-iA\wedge A$. When comparing to instanton references, compare the phase $e^{i\theta k}$ and the integrality of $k$, not only the sign of a displayed Chern–Simons form.
:::

## Based maps, unbased maps, and global symmetry

The based homotopy group $\pi_n(Y,y_0)$ classifies maps

$$
f:S^n\to Y
$$

that send a chosen basepoint of $S^n$ to a chosen point $y_0\in Y$, with homotopies preserving that condition.

Many field-theory boundary conditions are based. For example, if a scalar field is required to approach a particular vacuum $\phi_0$ at infinity, then compactified space has a distinguished point at infinity, and maps are based:

$$
(S^d,\infty)\to(\mathcal M,\phi_0).
$$

But sometimes the value at infinity is not physically fixed. It may be moved by a global symmetry. Then sectors are better described by unbased homotopy classes, possibly modulo the action of the symmetry group on $\mathcal M$.

This is not pedantry. If $\mathcal M$ is not simply connected or if $\pi_1(\mathcal M)$ acts nontrivially on higher homotopy groups, based and unbased classifications can differ. For most first examples, such as $S^1$, $S^2$, and $S^3$, the distinction is mild. For quotient spaces, nematic order parameters, gauge-Higgs systems, and theories with discrete identifications, it can be decisive.

A safe workflow is:

$$
\text{fix boundary condition first}
\quad\longrightarrow\quad
\text{choose based or unbased maps}
\quad\longrightarrow\quad
\text{only then compute }\pi_n.
$$

## Gauge theories and the exact-sequence lesson

In a gauge theory with Higgs field, one often says that symmetry breaking

$$
G\to H
$$

has vacuum manifold

$$
\mathcal M_{\mathrm{vac}}=G/H.
$$

That slogan is useful, but gauge redundancy changes the interpretation. Points in $G/H$ related by local gauge transformations are not distinct physical vacua in the same way as vacua of a global symmetry. Nevertheless, asymptotic Higgs data can define gauge-invariant bundle topology.

The long exact sequence of the fibration

$$
H\to G\to G/H
$$

contains the piece

$$
\pi_2(G)\to\pi_2(G/H)\to\pi_1(H)\to\pi_1(G).
$$

For compact simple simply connected $G$, one has

$$
\pi_1(G)=0,
\qquad
\pi_2(G)=0,
$$

so

$$
\pi_2(G/H)\simeq\pi_1(H).
$$

This is the clean mathematical reason monopoles in $G\to H$ breaking are tied to magnetic fluxes of the unbroken gauge group $H$.

For $SU(2)\to U(1)$,

$$
\pi_2(SU(2)/U(1))
\simeq
\pi_1(U(1))
\simeq
\mathbb Z.
$$

The same integer can be seen as the degree of the Higgs direction map or as the first Chern class of the unbroken $U(1)$ bundle at infinity.

## Homotopy is not the same as a stable soliton

A nontrivial homotopy class says a configuration cannot be continuously deformed to the trivial one while staying inside the allowed class. It does **not** by itself say that the classical equations have a smooth, finite-energy, stable, localized solution.

There are several separate questions:

| Question | Topology answers it? | Comment |
|---|---:|---|
| Are there disconnected sectors of configuration space? | often yes | This is the homotopy classification. |
| Is there a finite-energy representative? | not always | The boundary data may force divergent energy, as for some global vortices. |
| Is there a stationary solution of the equations? | not automatically | Dynamics determines existence. |
| Is the solution stable against shrinking or spreading? | not automatically | Derrick-type scaling can destabilize textures. |
| Is the charge conserved quantum mechanically? | sometimes | Anomalies, instantons, boundaries, and dynamical defects can change the answer. |

This distinction prevents a common misunderstanding: topology protects against certain deformations, but it does not write the Lagrangian for you.

## Characteristic classes and bundle refinements

Homotopy groups classify many boundary maps, but gauge fields often require bundle language. A connection $A$ is not merely a map into a group. It is a connection on a principal bundle, possibly described locally by forms $A_i$ patched by transition functions $g_{ij}$.

The topology of the bundle is measured by characteristic classes. Standard examples are:

$$
\frac{1}{2\pi}\int_{S^2}F\in\mathbb Z
$$

for a compact $U(1)$ bundle over $S^2$, and

$$
\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F)\in\mathbb Z
$$

for an $SU(N)$ bundle over a closed oriented four-manifold with standard normalization.

These expressions are not merely integrals of local functions. They know about patching. A local potential $A$ may be smooth on each patch, but the global class is stored in how patches are glued.

This is why monopoles, instantons, theta terms, Chern–Simons terms, and anomalies repeatedly force the same lesson: QFT fields are often global geometric objects, not just functions in a coordinate chart.

## Homotopy, generalized symmetry, and modern refinements

A classical soliton number often behaves like a conserved charge. For example, in a sigma model one can define a topological current whose conservation follows from an identity rather than from the equations of motion. This suggests a symmetry associated with soliton number.

Modern QFT refines this idea. Solitonic charges can sometimes be interpreted as charges under higher-form symmetries. But the naive homotopy group is not always the full symmetry. Dynamical defects can end solitons; anomalies can obstruct gauging the solitonic symmetry; and in some systems the correct conserved structure is described by bordism or even by non-invertible topological operators rather than by an ordinary abelian group.

For this chapter, the practical lesson is modest: homotopy classification is the correct first pass, not the final word. The final word depends on the full QFT, not only on the classical target manifold.

## Common pitfalls

**Pitfall 1: Classifying the target instead of the configuration.** The target $\mathcal M$ is not itself the sector label. The sector label is a homotopy class of maps from the relevant domain into $\mathcal M$.

**Pitfall 2: Forgetting the domain sphere.** A line defect, a point defect, a texture, and an instanton can involve the same target but different spheres, hence different homotopy groups.

**Pitfall 3: Treating gauge-related configurations as distinct.** In gauge theory, the physical classification must be gauge-invariant. A winding scalar written in one gauge may be a bundle transition function in another.

**Pitfall 4: Assuming nontrivial homotopy guarantees finite energy.** Global vortices, textures, and scale-invariant sigma-model lumps all teach otherwise. Dynamics matters.

**Pitfall 5: Ignoring singularities and endpoints.** If singular configurations, boundaries, or dynamical charged objects are allowed, a topological charge may cease to be conserved.

**Pitfall 6: Calling every integer a winding number.** Some integers are degrees of maps. Some are fluxes. Some are Chern numbers. Some are indices. They may agree in examples, but they are not the same definition.

## Relations to other pages

[Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/) develops the integer degree formulas that implement the simplest homotopy labels.

[Vortices](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/vortices/) and [Monopoles](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/monopoles/) will turn the $\pi_1$ and $\pi_2$ entries of the dictionary into field-theory solutions.

[Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/) will develop the Euclidean $\pi_3(G)$ and $\int\operatorname{tr}(F\wedge F)$ story.

[Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) explains how topological charges of extended objects become symmetry charges in modern language.

[Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/) explains how a path integral weights sectors by phases $e^{i\theta Q}$.

## Research status

The classical homotopy classification of defects and solitons is established and remains the standard first diagnostic. It is the right language for kinks, global vortices, sigma-model textures, monopole boundary data, Skyrmions, and instanton sectors.

The active frontier is not whether homotopy matters. It is how the homotopy classification embeds into the full quantum theory. Modern work relates solitonic charges to generalized global symmetries, anomaly inflow, bordism invariants, and non-invertible topological operators. In condensed matter and high-energy theory alike, the correct classification can depend on symmetry, gauge structure, fermion parity, spin or Pin data, and which defects are dynamical.

## Exercises

### Exercise 1: Defects in three spatial dimensions

Let a global symmetry-breaking theory in three spatial dimensions have vacuum manifold $\mathcal M$. Fill in the homotopy group that gives the first-pass classification of domain walls, line vortices, point monopoles, and textures.

<details><summary><strong>Solution</strong></summary>

A domain wall has codimension one, so a small normal sphere is $S^0$. The label is $\pi_0(\mathcal M)$.

A line vortex has codimension two, so the linking sphere is $S^1$. The label is $\pi_1(\mathcal M)$.

A point monopole has codimension three, so the linking sphere is $S^2$. The label is $\pi_2(\mathcal M)$.

A nonsingular texture fills space, so compactified space is $S^3$. The label is $\pi_3(\mathcal M)$.

Thus the dictionary is

$$
\text{walls}:\pi_0(\mathcal M),
\qquad
\text{vortices}:\pi_1(\mathcal M),
\qquad
\text{monopoles}:\pi_2(\mathcal M),
\qquad
\text{textures}:\pi_3(\mathcal M).
$$

</details>

### Exercise 2: Which defects exist for a circle vacuum manifold?

Take $\mathcal M=S^1$ in three spatial dimensions. Which of the first-pass defects in Exercise 1 are topologically classified by nontrivial groups?

<details><summary><strong>Solution</strong></summary>

The relevant homotopy groups are

$$
\pi_0(S^1)=0,
\qquad
\pi_1(S^1)=\mathbb Z,
\qquad
\pi_2(S^1)=0,
\qquad
\pi_3(S^1)=0.
$$

Here $\pi_0(S^1)=0$ means $S^1$ is connected, not that it is a group with one zero element in the same way as higher homotopy groups. The only nontrivial first-pass topological defect in three spatial dimensions is the line vortex, classified by $\pi_1(S^1)=\mathbb Z$.

</details>

### Exercise 3: Monopoles from an exact sequence

Suppose $G$ is compact, simple, and simply connected, and a gauge theory is Higgsed to $H$. Use the long exact sequence of $H\to G\to G/H$ to show that

$$
\pi_2(G/H)\simeq\pi_1(H).
$$

<details><summary><strong>Solution</strong></summary>

The relevant part of the long exact sequence is

$$
\pi_2(G)\to \pi_2(G/H)\to \pi_1(H)\to \pi_1(G).
$$

For compact simple simply connected $G$,

$$
\pi_1(G)=0,
\qquad
\pi_2(G)=0.
$$

Therefore the map

$$
\pi_2(G/H)\to \pi_1(H)
$$

has trivial kernel and is surjective. Hence it is an isomorphism:

$$
\pi_2(G/H)\simeq \pi_1(H).
$$

Physically, monopole Higgs winding at infinity is equivalent to magnetic flux of the unbroken gauge group $H$.

</details>

### Exercise 4: Why topology does not guarantee a stable lump

Consider a scalar sigma model in three spatial dimensions with target $S^3$. Since $\pi_3(S^3)=\mathbb Z$, there are nontrivial texture classes. Explain why this fact alone does not guarantee a stable finite-size soliton in the two-derivative sigma model.

<details><summary><strong>Solution</strong></summary>

The nontrivial homotopy group says that a smooth configuration in a nonzero degree class cannot be deformed to the constant map while staying inside the allowed finite-energy configuration space.

But stability of a finite-size classical solution is a dynamical question. In a two-derivative sigma model, a scaling argument can show that the energy changes monotonically as the configuration is shrunk or expanded, depending on dimension and terms in the Lagrangian. Thus there may be no stationary finite-size solution even though the topological class is nontrivial.

To stabilize a Skyrmion-like soliton, one typically needs additional terms, such as a four-derivative Skyrme term, gauge-field energy, a potential, or other dynamics. Topology protects the sector; it does not by itself supply a stable size.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§92–94. Solitons, monopoles, instantons, and theta vacua.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4 and 6. Compact gauge fields, instantons, and topology of gauge fields.
- S. Coleman, *Aspects of Symmetry*. Monopoles, instantons, spontaneous symmetry breaking, and semiclassical reasoning.
- M. Nakahara, *Geometry, Topology and Physics*, Ch. 4 and later gauge-theory chapters. Homotopy groups, defects, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*. Differential forms, bundles, characteristic classes, and gauge-field topology.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 8. Homotopy, theta terms, Wess–Zumino terms, and topological field theory.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Comprehensive modern reference for solitons, homotopy, and examples.
- R. Rajaraman, *Solitons and Instantons*. Classic detailed introduction to kinks, vortices, monopoles, instantons, and collective coordinates.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Pedagogical lecture notes on solitons and their topology.

## Version history

- 2026-06-18: First polished draft. Added boundary/linking-sphere workflow, defect dictionary, based versus unbased maps, gauge-theory exact-sequence lesson, bundle refinements, modern caveats, exercises, and references.
