---
title: "Wess–Zumino–Witten Terms"
description: "Explains Wess–Zumino–Witten terms as quantized Wess–Zumino terms for group-valued fields, with current algebra, anomaly matching, and Chern–Simons boundary interpretations."
sidebar:
  label: "Wess–Zumino–Witten Terms"
  order: 4
level: Advanced
status: "Polished draft"
source: "Wess–Zumino; Witten, Global Aspects of Current Algebra; Witten, Non-Abelian Bosonization; Coleman, Aspects of Symmetry; Di Francesco–Mathieu–Sénéchal; standard anomaly and CFT references."
topics:
  - Wess Zumino Witten terms
  - current algebra
  - affine Lie algebra
  - chiral Lagrangians
  - anomaly matching
  - Chern Simons boundary theory
  - nonabelian bosonization
canonicalTopics:
  - wess-zumino-witten-terms
  - affine-current-algebra
  - anomaly-matching
  - chiral-lagrangian
  - cft-wzw-model
researchStatus:
  established:
    - "The Wess–Zumino–Witten functional is a quantized Wess–Zumino term for a group-valued field and is well defined only after the level and global form of the group are specified."
    - "In two dimensions the WZW action gives a conformal field theory with affine current algebra; in four-dimensional chiral dynamics the WZW term matches flavor anomalies."
  active:
    - "Modern refinements track global forms, spin structures, boundary conditions, gauged WZW models, categorical symmetry, and the precise relation between Chern–Simons theory and chiral edge modes."
---

## Summary

A Wess–Zumino–Witten term is the most important special case of a Wess–Zumino term. The field is group-valued,

$$
g:\Sigma_2\longrightarrow G,
$$

and the topological part of the action is defined by extending $g$ to a three-manifold $B_3$ with boundary $\partial B_3=\Sigma_2$:

$$
\widetilde g:B_3\longrightarrow G.
$$

For a compact simple group, the basic closed three-form on $G$ represents a generator of $H^3(G,\mathbb Z)$. With a normalized representative $H_3$ satisfying

$$
\int_{S^3} H_3=2\pi
$$

on a unit winding map $S^3\to G$, the Wess–Zumino part is

$$
S_{\mathrm{WZ}}[g]=k\int_{B_3}\widetilde g^{*}H_3,
\qquad k\in\mathbb Z.
$$

The integer $k$ is the **level**. In two-dimensional conformal field theory it becomes the level of an affine current algebra. In four-dimensional chiral dynamics, the analogous WZW functional on spacetime is defined using a five-dimensional extension and matches the UV flavor anomaly of quarks.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing a group-valued field on a two-dimensional worldsheet, its three-dimensional extension, a level-k current algebra, and a Chern–Simons bulk-boundary relation.](/figures/symmetry-anomalies-topology/wzw-current-algebra-map.svg)

<figcaption>

The Wess–Zumino–Witten term starts as an extension integral, but its most visible two-dimensional signature is a level-$k$ current algebra. The same structure appears at the boundary of three-dimensional Chern–Simons theory.

</figcaption>
</figure>

The name “Wess–Zumino–Witten” is used in two closely related ways. In two-dimensional CFT, it usually means the full sigma-model action on $G$ with a quantized Wess–Zumino term and a specially tuned kinetic coefficient. In chiral perturbation theory, it often means the higher-dimensional topological functional that reproduces anomalous Ward identities. Both uses are the same idea: a locally meaningful quantum theory whose action knows about global topology.

## Prerequisites

Read [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/) first. You should also be comfortable with [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/), [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/), and [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/).

For the CFT part, it helps to know complex coordinates and the basic operator product expansion. For the chiral-Lagrangian part, it helps to know that QCD with light quarks has approximate

$$
SU(N_f)_L\times SU(N_f)_R
$$

flavor symmetry, spontaneously broken to the diagonal subgroup.

## Core idea

The ordinary Wess–Zumino construction says that an action can be defined by integrating a closed form on a filling manifold. The WZW construction adds a powerful extra ingredient: the target space is a Lie group, so the closed form is controlled by group multiplication.

For a compact simple group $G$, there is a canonical closed three-form

$$
H_3\propto \operatorname{tr}(g^{-1}dg)^3.
$$

The Maurer–Cartan equation

$$
d(g^{-1}dg)+(g^{-1}dg)\wedge(g^{-1}dg)=0
$$

is what makes this form closed. The integrality of its periods is what quantizes the coefficient. Group multiplication is what produces the Polyakov–Wiegmann identity, current algebra, nonabelian bosonization, and the Chern–Simons boundary relation.

The compact slogan is

$$
\text{WZW} = \text{Wess–Zumino topology} + \text{group-valued fields} + \text{level }k.
$$

That one extra word, “group,” is doing a ridiculous amount of work.

## Setup and conventions

Let $\Sigma_2$ be a closed oriented two-dimensional spacetime or Euclidean worldsheet. Let $G$ be a compact connected Lie group, often taken to be simple and simply connected on a first pass. A WZW field is

$$
g:\Sigma_2\to G.
$$

Let $B_3$ be an oriented three-manifold with

$$
\partial B_3=\Sigma_2,
$$

and let $\widetilde g:B_3\to G$ extend $g$. For compact simple $G$, choose an invariant bilinear form on $\mathfrak g$ normalized so that

$$
\Omega_3(g)=\frac{1}{24\pi^2}\operatorname{Tr}(g^{-1}dg)^3
$$

has integral periods, up to the standard factor of $i$ that depends on whether one writes Lie-algebra generators as Hermitian or anti-Hermitian matrices.

Then the topological part can be written schematically as

$$
S_{\mathrm{WZ}}[g]=2\pi k\int_{B_3}\widetilde g^{*}\Omega_3.
$$

The exponentiated action is independent of the extension if

$$
k\in\mathbb Z.
$$

The two-dimensional WZW model also contains a kinetic term. In a common Euclidean normalization,

$$
S_k[g]
=\frac{k}{8\pi}\int_{\Sigma_2}d^2x\,\operatorname{Tr}\left(g^{-1}\partial_\mu g\,g^{-1}\partial^\mu g\right)
+2\pi k\int_{B_3}\widetilde g^{*}\Omega_3.
$$

Depending on whether one uses Lorentzian or Euclidean signature and Hermitian or anti-Hermitian generators, the Wess–Zumino term may be displayed with an explicit factor of $i$. The physical invariant is the phase $e^{-S_E}$ in Euclidean signature or $e^{iS_L}$ in Lorentzian signature.

:::note[Convention-sensitive source note]
The coefficient of the matrix formula for the WZW term is notoriously convention-dependent. Some references write $k/(12\pi)$, some write $k/(24\pi)$, and some include an explicit $i$. These are often the same convention written with different choices of trace, generator hermiticity, and Euclidean continuation. In this page the quantization statement is the definition: the normalized three-form has integral periods, and the exponentiated action is independent of the extension.
:::

## Why the level is quantized

Suppose $B_3$ and $B_3'$ are two extensions of the same boundary field $g$. Gluing them with opposite orientations gives a closed three-manifold

$$
C_3=B_3\cup_{\Sigma_2}(-B_3').
$$

The difference between the two Wess–Zumino actions is

$$
\Delta S_{\mathrm{WZ}}
=2\pi k\int_{C_3}\widehat g^{*}\Omega_3.
$$

If $\Omega_3$ has integral periods, then

$$
\int_{C_3}\widehat g^{*}\Omega_3\in\mathbb Z.
$$

Therefore

$$
e^{i\Delta S_{\mathrm{WZ}}}=1
$$

when $k\in\mathbb Z$. This is the same logic as for ordinary Wess–Zumino terms, but for compact simple groups it is especially concrete because

$$
\pi_3(G)\cong\mathbb Z
$$

for many of the groups used in QFT, such as $SU(N)$.

The first global caveat is immediate: if $G$ is not simply connected, or if fields are allowed to live on nontrivial bundles, the allowed levels can change. A page that says only “$k$ is an integer” is giving the first-pass answer, not the full global answer.

## Equations of motion and chiral currents

The WZW model is not merely a topological theory. Its kinetic term matters. The miracle is that at the WZW coefficient the equations of motion factorize into left- and right-moving current conservation laws.

In complex coordinates

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2,
$$

the classical equations of motion can be written as

$$
\partial_{\bar z}J(z)=0,
\qquad
\partial_z\bar J(\bar z)=0,
$$

where, in a common normalization,

$$
J(z)=-k\,\partial_z g\,g^{-1},
\qquad
\bar J(\bar z)=k\,g^{-1}\partial_{\bar z}g.
$$

The precise signs and factors of two depend on the normalization of the kinetic term and complex coordinates. The structural statement is invariant:

$$
\text{the left and right currents become holomorphic and antiholomorphic.}
$$

This is why the two-dimensional WZW model is a conformal field theory, not just a sigma model with a topological decoration.

## The Polyakov–Wiegmann identity

The workhorse identity of WZW theory is the Polyakov–Wiegmann identity. It describes what happens when two group-valued fields are multiplied.

Schematically,

$$
S_k[gh]
=S_k[g]+S_k[h]+\text{a local bilinear term in }g^{-1}dg\text{ and }dh\,h^{-1}.
$$

In one common Euclidean convention,

$$
S_k[gh]
=S_k[g]+S_k[h]
+\frac{k}{2\pi}\int_{\Sigma_2}d^2z\,
\operatorname{Tr}\left(g^{-1}\partial_{\bar z}g\,\partial_z h\,h^{-1}\right).
$$

The identity follows from the group-cohomological behavior of

$$
\operatorname{Tr}(g^{-1}dg)^3.
$$

It implies, for example, that the action is invariant under

$$
g(z,\bar z)\longmapsto \Omega_L(z)\,g(z,\bar z)\,\Omega_R(\bar z)^{-1},
$$

where $\Omega_L$ is holomorphic and $\Omega_R$ is antiholomorphic. This is much larger than the ordinary global $G_L\times G_R$ symmetry.

:::note[Convention-sensitive source note]
Different references place the Polyakov–Wiegmann bilinear term as $\operatorname{Tr}(g^{-1}\partial g\,\bar\partial h h^{-1})$, $\operatorname{Tr}(g^{-1}\bar\partial g\,\partial h h^{-1})$, or with the opposite sign. This depends on whether the product is written as $gh$, $gh^{-1}$, or $h^{-1}g$, and on the Euclidean coordinate convention. The identity’s invariant content is that multiplication of fields changes the WZW functional by a local two-dimensional term.
:::

## Current algebra and the meaning of the level

Quantization promotes the holomorphic currents to operators satisfying an affine Lie algebra. In OPE form,

$$
J^a(z)J^b(0)
\sim
\frac{k\,\kappa^{ab}}{z^2}
+\frac{i f^{ab}{}_c J^c(0)}{z},
$$

with an analogous antiholomorphic algebra for $\bar J^a(\bar z)$. Here $\kappa^{ab}$ is the inverse invariant metric on the Lie algebra.

Equivalently, the current modes

$$
J^a(z)=\sum_{n\in\mathbb Z}J^a_n z^{-n-1}
$$

obey

$$
[J^a_m,J^b_n]
=i f^{ab}{}_c J^c_{m+n}+k\,m\,\kappa^{ab}\delta_{m+n,0}.
$$

The integer $k$ that made $e^{iS}$ well defined is exactly the central extension level of the current algebra. This is one of the prettiest normalization checks in QFT: a global topological integer reappears as a local short-distance singularity.

For compact simple $G$, the stress tensor is given by the Sugawara construction,

$$
T(z)=\frac{1}{2(k+h^\vee)}\,\kappa_{ab}:J^aJ^b:(z),
$$

where $h^\vee$ is the dual Coxeter number. The corresponding central charge is

$$
c=\frac{k\,\dim G}{k+h^\vee}.
$$

For example, for $G=SU(2)$,

$$
h^\vee=2,
\qquad
\dim G=3,
\qquad
c=\frac{3k}{k+2}.
$$

## The WZW term in chiral Lagrangians

The WZW term is not only a two-dimensional CFT object. It is also the low-energy memory of anomalies in four-dimensional gauge theories.

Consider massless QCD with $N_f$ light quark flavors. Classically, the flavor symmetry contains

$$
SU(N_f)_L\times SU(N_f)_R.
$$

The chiral condensate breaks this symmetry to the diagonal subgroup,

$$
SU(N_f)_L\times SU(N_f)_R\longrightarrow SU(N_f)_V.
$$

The Goldstone field is usually written

$$
U(x)\in SU(N_f).
$$

The ordinary chiral Lagrangian contains derivative terms such as

$$
\frac{f_\pi^2}{4}\operatorname{Tr}(\partial_\mu U^\dagger\partial^\mu U).
$$

But that is not enough. The UV quarks have anomalous flavor Ward identities. The IR pion theory must reproduce them. The WZW functional does exactly this. In four spacetime dimensions it is defined using a five-dimensional extension,

$$
U:X_4\to SU(N_f),
\qquad
\widetilde U:B_5\to SU(N_f),
\qquad
\partial B_5=X_4,
$$

with a normalized five-form built from

$$
U^{-1}dU.
$$

The coefficient is fixed by the number of colors,

$$
k=N_c.
$$

This term is responsible for anomalous pion interactions, including the famous neutral-pion decay amplitude into two photons when electromagnetic background fields are included. The deep point is not a particular decay rate. It is that anomaly matching forces a topological term in the IR effective action.

## Gauged WZW terms

To compare anomalous Ward identities, one couples the left and right flavor symmetries to background gauge fields

$$
A_L,
\qquad
A_R.
$$

The gauged WZW functional is a background-dependent extension of the ungauged WZW term. It is built so that its variation under background gauge transformations reproduces the anomaly polynomial or descent representative of the UV theory.

Symbolically,

$$
\delta_\alpha S_{\mathrm{WZW}}[U,A_L,A_R]
=\int_{X_4}\alpha\,\mathcal A(A_L,A_R).
$$

This is why the WZW term belongs in a chapter on topological terms rather than only in a chapter on pion phenomenology. It is a topological representative of anomaly matching.

There is a practical warning: gauged WZW formulas are long. Their length is not conceptual depth. The compact object is the anomaly polynomial and its descent. The gauged WZW functional is one convenient local representative.

## Relation to Chern–Simons theory

WZW theory appears naturally on the boundary of Chern–Simons theory. If $M_3$ has boundary $\Sigma_2$, the Chern–Simons action is not gauge invariant without boundary data. One way to restore gauge invariance is to add boundary degrees of freedom described by a WZW model.

At the classical level, a flat connection on $M_3$ is locally pure gauge,

$$
A=g^{-1}dg,
$$

and substituting a pure gauge connection into the Chern–Simons functional produces the Wess–Zumino term. With a boundary, the remaining boundary piece becomes the WZW kinetic term after imposing suitable boundary conditions.

The rough correspondence is

$$
\text{Chern–Simons level }k
\quad\longleftrightarrow\quad
\text{WZW current-algebra level }k.
$$

This is one of the main reasons Chern–Simons theory computes knot and three-manifold invariants through conformal blocks of WZW models.

## Nonabelian bosonization

In two dimensions, free fermions with nonabelian flavor symmetry can be rewritten in bosonic variables. The resulting bosonic theory contains a WZW model.

A standard schematic statement is

$$
N\text{ free complex fermions}
\quad\leftrightarrow\quad
U(N)_1\text{ WZW data, with appropriate }U(1)\text{ factors}.
$$

For fermions transforming under color and flavor groups, the bosonized description splits the current algebra into corresponding affine factors. This is not a decorative reformulation. It turns strongly interacting fermionic problems in two dimensions into sigma-model and current-algebra problems.

The lesson for this volume is that WZW terms are not rare. They are the natural bosonic language for fermion anomalies and current algebras in low dimensions.

## A local term cannot replace the WZW term

A tempting mistake is to ask for an ordinary local two-dimensional Lagrangian that reproduces the WZW term. Locally one can write the three-form as an exterior derivative,

$$
H_3=dB_2,
$$

and then write

$$
\int_{\Sigma_2}g^*B_2.
$$

But $B_2$ is not globally defined on $G$ when $H_3$ represents a nontrivial cohomology class. The obstruction is exactly the point. If the WZW term were globally the integral of an ordinary two-form, it would not carry the same quantized topological data.

The same logic reappears for Berry phases, magnetic monopoles, Chern–Simons forms, and anomaly inflow. Locally exact is not globally trivial.

## Common pitfalls

The most common pitfall is treating the level $k$ as a tunable real coupling. For compact WZW models, $k$ is quantized by global consistency. The kinetic coefficient is also tied to $k$ at the conformal point.

A second pitfall is confusing the two-dimensional WZW model with the four-dimensional chiral WZW functional. The former is a two-dimensional CFT. The latter is a topological term in a four-dimensional effective field theory, defined using a five-dimensional extension. They share the same Wess–Zumino logic but live in different dimensions.

A third pitfall is forgetting global-form restrictions. The algebra $\mathfrak g$ and level $k$ do not fully specify all global versions of a WZW model. The group $G$, allowed bundles, spin structure, and possible quotient by a center can matter.

A fourth pitfall is saying that the WZW term “causes” an anomaly. In an IR effective theory, the WZW term usually **matches** a UV anomaly. It is the cure, not the disease.

A fifth pitfall is using the current-algebra OPE without specifying trace normalization. If $\kappa^{ab}$ is rescaled, the displayed value of $k$ changes unless the generator normalization is rescaled in tandem.

## Relations to other pages

This page refines [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/) by specializing to group-valued fields and current algebra. It prepares for [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/), where the same level $k$ controls a three-dimensional topological gauge theory.

It also connects to [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/), [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/), and [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/). Later CFT pages develop affine algebras, conformal blocks, modular invariance, and rational WZW models in more detail.

## Research status

The local and perturbative structure of WZW models is established textbook material. Their role in two-dimensional CFT, bosonization, anomaly matching, chiral Lagrangians, and Chern–Simons boundary theory is standard.

The active refinements are global. Modern work asks which levels are allowed for non-simply connected groups, how spin and Pin structures modify quantization, how gauged WZW models encode global anomalies, and how WZW-like terms appear in generalized-symmetry and symmetry-TFT language. These are not corrections to the basic story; they are the global audit trail.

## Exercises

### Exercise 1: Extension independence

Let $H_3$ be normalized so that $\int_C H_3\in 2\pi\mathbb Z$ for every closed three-cycle $C$ arising from allowed maps into $G$. Show that

$$
S_{\mathrm{WZ}}=k\int_{B_3}\widetilde g^*H_3
$$

defines an unambiguous phase if $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

Two choices of extension differ by a closed three-cycle $C_3$. The action difference is

$$
\Delta S_{\mathrm{WZ}}=k\int_{C_3}\widehat g^*H_3.
$$

By the period assumption, this lies in $2\pi k\mathbb Z$. If $k\in\mathbb Z$, then $e^{i\Delta S_{\mathrm{WZ}}}=1$. Therefore $e^{iS_{\mathrm{WZ}}}$ is independent of the extension.

</details>

### Exercise 2: SU(2) central charge

Use the Sugawara formula

$$
c=\frac{k\dim G}{k+h^\vee}
$$

for $G=SU(2)$ to compute $c$ at levels $k=1$ and $k=2$.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
\dim G=3,
\qquad
h^\vee=2.
$$

Thus

$$
c=\frac{3k}{k+2}.
$$

At $k=1$,

$$
c=\frac{3}{3}=1.
$$

At $k=2$,

$$
c=\frac{6}{4}=\frac32.
$$

</details>

### Exercise 3: Why a WZW term can match an anomaly

Explain why a WZW term in an IR effective action is compatible with locality even though it is defined using a higher-dimensional extension.

<details><summary><strong>Solution</strong></summary>

The extension is used to define the action phase globally. The variation of the Wess–Zumino functional depends only on the boundary field because the higher-dimensional form is closed. For a variation generated by a vector field $V$ on the target,

$$
\delta\int_{B}H=\int_B d(i_VH)=\int_{\partial B}i_VH.
$$

Thus the equations of motion and anomalous Ward variations are local on spacetime. This is why the WZW term can appear in a local IR effective theory and reproduce a UV anomaly.

</details>

### Exercise 4: Level as topology and as OPE data

The same integer $k$ appears in the quantization condition for the Wess–Zumino term and in the current OPE

$$
J^a(z)J^b(0)\sim\frac{k\kappa^{ab}}{z^2}+\cdots.
$$

What does this tell you about the relation between global and local data in a WZW model?

<details><summary><strong>Solution</strong></summary>

It shows that the local operator algebra remembers the global topological normalization of the action. The integer $k$ is fixed by the requirement that the exponentiated Wess–Zumino term be globally well defined. After quantization, the same $k$ controls the central extension of the affine current algebra. Thus a global period condition becomes a local short-distance singularity.

</details>

## References

- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities.”
- E. Witten, “Global Aspects of Current Algebra.”
- E. Witten, “Non-Abelian Bosonization in Two Dimensions.”
- E. Witten, “Quantum Field Theory and the Jones Polynomial.”
- Sidney Coleman, *Aspects of Symmetry*, especially lectures on soft pions, current algebra, and anomalies.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters on affine Lie algebras and WZW models.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, topological field theory chapters on theta, Wess–Zumino, and Chern–Simons terms.
- K. Gawedzki, “Lectures on Conformal Field Theory,” for global and geometric aspects of WZW models.

## Version history

- 2026-06-18: First polished draft. Added extension definition, level quantization, current algebra, Polyakov–Wiegmann identity, chiral-Lagrangian anomaly matching, Chern–Simons boundary relation, pitfalls, and exercises.
