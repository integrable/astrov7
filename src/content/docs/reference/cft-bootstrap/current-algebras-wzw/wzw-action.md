---
title: "WZW Action"
description: "The sigma-model action with a Wess–Zumino term whose quantized level produces affine current algebra, conformal invariance, and Wess–Zumino–Witten models."
sidebar:
  label: "WZW Action"
  order: 5
level: Graduate
status: "Polished draft"
source: "Witten 1984; Knizhnik and Zamolodchikov 1984; Di Francesco, Mathieu, and Senechal chs. 14–15; Ginsparg lectures."
topics:
  - WZW action
  - Wess–Zumino term
  - WZW models
  - current algebra
  - sigma models
canonicalTopics:
  - wzw-action
  - wess-zumino-term
  - wzw-current-algebra
researchStatus:
  established:
    - "The Wess–Zumino–Witten action defines a conformal sigma model on a compact Lie group at quantized level and realizes affine current algebra symmetry."
  active:
    - "Modern applications include boundary WZW models, gauged WZW models, Chern–Simons/WZW correspondence, condensed-matter spin chains, and nonsemisimple or supersymmetric generalizations."
---

## Summary

A **Wess–Zumino–Witten model** is a two-dimensional sigma model whose field is a map

$$
g:\Sigma\to G
$$

from a two-dimensional worldsheet $\Sigma$ into a Lie group $G$. Its action is the sum of an ordinary sigma-model kinetic term and a topological Wess–Zumino term:

$$
S_{\rm WZW}[g]
=\frac{k}{8\pi}\int_\Sigma \operatorname{Tr}(g^{-1}\partial_\mu g\,g^{-1}\partial^\mu g)
+\frac{k}{12\pi}\int_B \operatorname{Tr}(g^{-1}dg)^3,
$$

where $\partial B=\Sigma$. The exact coefficient depends on the trace convention, but the physical integer $k$ is the **level**.

The Wess–Zumino term is the essential ingredient. It makes the theory conformal at a special coupling, forces level quantization for compact groups, and produces independent holomorphic and antiholomorphic currents. These currents generate affine Lie algebras:

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The WZW action is therefore the Lagrangian doorway into current algebra, rational CFT, nonabelian bosonization, cosets, and many exactly solvable models.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/), [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/), and [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) first.

You should be comfortable with differential forms, especially the Maurer–Cartan form $g^{-1}dg$, and with the idea that a two-dimensional sigma model can be written as a path integral over maps into a target manifold.

## Core idea

The ordinary nonlinear sigma model on a group manifold has an action built from the metric on $G$. The WZW model adds a term that cannot be written as a local two-dimensional integral without choosing an extension to a three-dimensional manifold.

That term is

$$
\Gamma[g]=\frac{1}{12\pi}\int_B \operatorname{Tr}(g^{-1}dg)^3.
$$

The full action is schematically

$$
S_{\rm WZW}=k\,S_{\rm kinetic}+k\,\Gamma.
$$

The miracle is that the added topological term changes the current conservation equations into chiral conservation equations:

$$
\bar\partial J=0,
\qquad
\partial \bar J=0.
$$

Thus the model has not just global $G_L\times G_R$ symmetry, but affine symmetry

$$
\widehat{\mathfrak g}_k\times\widehat{\mathfrak g}_k.
$$

The slogan is

$$
\text{group-valued field }g(z,\bar z)
+\text{Wess–Zumino term}
\quad\Longrightarrow\quad
\text{chiral current algebra}.
$$

## Setup and conventions

Let $G$ be compact, simple, and simply connected unless stated otherwise. Let $\Sigma$ be a closed oriented Euclidean two-dimensional surface. The field is

$$
g(z,\bar z)\in G.
$$

Choose a three-manifold $B$ such that

$$
\partial B=\Sigma,
$$

and extend $g$ from $\Sigma$ to $B$. The Wess–Zumino three-form is

$$
\omega_3(g)=\operatorname{Tr}(g^{-1}dg)^3.
$$

A common Euclidean action is

$$
S[g]
=\frac{k}{8\pi}\int_\Sigma d^2x\,\operatorname{Tr}(g^{-1}\partial_\mu g\,g^{-1}\partial_\mu g)
+\frac{i k}{12\pi}\int_B \operatorname{Tr}(g^{-1}dg)^3.
$$

The factor of $i$ appears in Euclidean signature so that the Wess–Zumino term contributes a phase to the path integral. In Lorentzian signature, equivalent conventions often put both terms inside a real action.

The precise numerical coefficient depends on the trace normalization. The invariant statement is that the coefficient multiplying the properly normalized integral is an integer level $k$.

## Why the level is quantized

The Wess–Zumino term depends on a choice of extension $B$. For the path integral

$$
e^{-S_E[g]}
$$

to be well defined, the phase contributed by the Wess–Zumino term must be independent of this choice.

Take two different extensions $B$ and $B'$. Gluing them along their common boundary gives a closed three-manifold

$$
M=B\cup(-B').
$$

The difference between the two Wess–Zumino terms is an integral over $M$:

$$
\Delta\Gamma=\frac{1}{12\pi}\int_M\operatorname{Tr}(g^{-1}dg)^3.
$$

For compact simply connected simple $G$, the normalized integral is tied to

$$
\pi_3(G)=\mathbb Z.
$$

With the standard normalization, changing the extension shifts the action by an integer multiple of $2\pi i k$ in Euclidean signature. The path-integral phase is unchanged only if

$$
k\in\mathbb Z.
$$

For a unitary compact WZW model, one takes

$$
k\in\mathbb Z_{\ge0}.
$$

This is the same integer that appears as the affine level in the current algebra.

## Symmetries

The WZW action has a global

$$
G_L\times G_R
$$

symmetry acting by

$$
g(z,
\bar z)\mapsto h_L\,g(z,\bar z)\,h_R^{-1},
\qquad
h_L,h_R\in G.
$$

At the conformal point this symmetry becomes chiral. The equations of motion imply holomorphic and antiholomorphic currents.

A common convention is

$$
J(z)=-k\,\partial g\,g^{-1},
\qquad
\bar J(\bar z)=k\,g^{-1}\bar\partial g,
$$

up to factors of $i$ and trace-normalization conventions. These satisfy

$$
\bar\partial J=0,
\qquad
\partial\bar J=0.
$$

The left current generates one affine copy, while the right current generates the other. The full chiral algebra contains

$$
\widehat{\mathfrak g}_k\times\widehat{\mathfrak g}_k.
$$

This chiral enhancement is the decisive difference between the WZW model and an ordinary sigma model on $G$.

## Equations of motion

In complex coordinates, the kinetic term alone would produce a sigma-model equation with both $\partial$ and $\bar\partial$ acting on $g$. The Wess–Zumino term modifies the coefficient of the torsion term. At the WZW point, the equations simplify to chiral current conservation.

Schematically,

$$
\bar\partial(\partial g\,g^{-1})=0,
$$

or equivalently

$$
\partial(g^{-1}\bar\partial g)=0,
$$

depending on whether one writes the left or right current. This is why the current can be expanded in Laurent modes:

$$
J^a(z)=\sum_{n\in\mathbb Z}J^a_nz^{-n-1}.
$$

The chiral conservation law is classical. Quantum mechanically, the current algebra acquires the central term whose coefficient is $k$.

## Current algebra from the action

Quantizing the WZW model gives the current OPE

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The simple pole comes from the finite Lie algebra of $G$. The double pole comes from the symplectic structure induced by the Wess–Zumino term and is fixed by the level.

The right-moving currents obey an antiholomorphic copy:

$$
\bar J^a(\bar z)\bar J^b(\bar w)
\sim
\frac{k\kappa^{ab}}{(\bar z-\bar w)^2}
+\frac{i f^{ab}{}_c\bar J^c(\bar w)}{\bar z-\bar w}.
$$

The left and right currents have nonsingular mutual OPE in the bulk:

$$
J^a(z)\bar J^b(\bar w)\sim\text{regular}.
$$

This is the local algebraic content of the WZW model.

## Polyakov–Wiegmann identity

The WZW action satisfies a fundamental identity under multiplication of group-valued fields. In one common convention,

$$
S[g_1g_2]
=S[g_1]+S[g_2]
-\frac{k}{2\pi}\int d^2z\,\operatorname{Tr}(g_1^{-1}\bar\partial g_1\,\partial g_2 g_2^{-1}),
$$

up to Euclidean-signature and trace conventions.

This is the **Polyakov–Wiegmann identity**. It is the computational heart of many WZW manipulations. It explains how currents transform, how gauged WZW actions are built, and why nonabelian bosonization works so cleanly.

In particular, it shows that the WZW functional is almost additive under group multiplication, but not quite. The cross term is exactly what one needs for current algebra and anomaly-related applications.

## Stress tensor and central charge

The WZW stress tensor is the Sugawara stress tensor built from the currents:

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z).
$$

The central charge is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

The current remains a Virasoro primary of weight one:

$$
T(z)J^a(w)
\sim
\frac{J^a(w)}{(z-w)^2}
+\frac{\partial J^a(w)}{z-w}.
$$

Thus the WZW action produces both the affine current algebra and the Virasoro algebra needed for conformal field theory.

For $SU(2)_k$,

$$
c=\frac{3k}{k+2}.
$$

For $SU(N)_k$,

$$
c=\frac{k(N^2-1)}{k+N}.
$$

These formulas are among the simplest checks that the action, current normalization, and Sugawara conventions agree.

## Primary fields

The basic WZW field $g(z,\bar z)$ transforms under $G_L\times G_R$ by left and right multiplication. More generally, WZW primary fields are labeled by integrable highest weights $\lambda$ of the affine algebra at level $k$.

For compact simple $G$, integrability means

$$
(\lambda,\theta)\le k,
$$

where $\theta$ is the highest root. The conformal weight is

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}.
$$

The full diagonal WZW model contains local fields with left and right labels paired as

$$
\mathcal V_\lambda\otimes\overline{\mathcal V}_\lambda.
$$

Other modular invariants can pair sectors differently. As always in rational CFT, the chiral algebra alone does not specify every local theory.

## Example: SU(2) WZW models

For $G=SU(2)$,

$$
h^\vee=2,
\qquad
\dim G=3.
$$

The central charge is

$$
c=\frac{3k}{k+2}.
$$

The integrable primaries are labeled by spin

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

Their conformal weights are

$$
h_j=\frac{j(j+1)}{k+2}.
$$

At level one,

$$
j=0,\frac12,
\qquad
c=1,
\qquad
h_{1/2}=\frac14.
$$

The $SU(2)_1$ WZW model is equivalent, after appropriate identification of chiral algebras and radii, to a compact boson at a special radius. This makes it a key bridge between free bosons, spin chains, nonabelian bosonization, and rational CFT.

## Gauged WZW preview

One can gauge a subgroup of $G_L\times G_R$ by coupling gauge fields to the currents. The resulting **gauged WZW models** are the Lagrangian route to many coset CFTs.

The GKO coset central charge

$$
c_{\mathfrak g/\mathfrak h}=c_{\mathfrak g}-c_{\mathfrak h}
$$

has a gauged-WZW interpretation: degrees of freedom associated with the gauged subgroup are removed, leaving a quotient chiral algebra.

This is only a preview. Gauged WZW models require careful treatment of anomalies, gauge choices, and global issues. The coset chapter will develop the conformal-field-theory side first.

## Relation to Chern–Simons theory

The WZW model appears naturally on the boundary of three-dimensional Chern–Simons theory. Roughly,

$$
\text{Chern–Simons on a 3-manifold with boundary}
\quad\Longrightarrow\quad
\text{WZW degrees of freedom on the boundary}.
$$

This relation is one reason the same modular data appear in rational CFT and three-dimensional topological quantum field theory. It also explains why WZW models are central in the physics of quantum Hall edges and in the mathematical theory of modular tensor categories.

This page does not need the Chern–Simons derivation, but it is useful to know that the Wess–Zumino term is not an isolated trick. It is part of a larger topological story.

## Common pitfalls

**Do not treat the Wess–Zumino term as optional.** Without it, a generic sigma model on $G$ does not have the same chiral current algebra or exact conformal structure.

**Do not forget that $B$ is auxiliary.** The Wess–Zumino term is written using an extension to $B$, but the path integral must be independent of the choice of extension. That requirement quantizes $k$.

**Do not compare action coefficients without trace conventions.** The displayed $k/(8\pi)$ and $k/(12\pi)$ coefficients assume a convention. The invariant content is the normalized integer level.

**Do not confuse $G_L\times G_R$ global symmetry with affine symmetry.** The affine modes are the chiral enhancement of the global symmetry at the conformal WZW point.

**Do not assume every group-valued sigma model is a WZW model.** The WZW model requires the Wess–Zumino term at the quantized coefficient and the conformal coupling.

**Do not forget global subtleties.** Non-simply connected groups, quotient groups, spin structures, and discrete theta-like choices can change the allowed levels and line operators.

## Relations to other pages

This page follows [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) by explaining where the currents and level come from in an action principle. It also relies on [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/) for the trace-convention dictionary.

[WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) uses the action’s $G_L\times G_R$ symmetry and the affine representation theory to classify primary fields. [Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/) explains why only finitely many representations appear at positive integer level. [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) later returns to gauged WZW models.

The WZW action also connects to [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/), [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/), and later boundary and topological-field-theory pages.

## Research status

The WZW action, level quantization, affine current algebra, Sugawara stress tensor, and rational CFT data for compact simple groups at positive integer level are established.

Active directions include boundary and defect WZW models, gauged WZW models and dualities, supergroup WZW models, logarithmic current algebras, Chern–Simons/WZW relations, non-invertible symmetries, and condensed-matter realizations of current-algebra critical points.

## Exercises

### Exercise 1

Explain why the Wess–Zumino term is naturally written as a three-dimensional integral even though the CFT is two-dimensional.

<details><summary><strong>Solution</strong></summary>

The Wess–Zumino term uses the closed three-form

$$
\operatorname{Tr}(g^{-1}dg)^3
$$

on the group manifold. Pulling this form back by $g$ gives a three-form, so it must be integrated over a three-manifold $B$ whose boundary is the worldsheet:

$$
\partial B=\Sigma.
$$

The resulting action is still a two-dimensional theory because the physical field lives on $\Sigma$. Consistency requires the path-integral phase to be independent of the extension to $B$, which quantizes the coefficient.

</details>

### Exercise 2

For $SU(2)_k$, compute $c$ and the allowed spins at $k=1$.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
c=\frac{3k}{k+2}.
$$

At $k=1$,

$$
c=\frac{3}{3}=1.
$$

The allowed integrable spins satisfy

$$
0\le j\le \frac{k}{2},
$$

so

$$
j=0,\frac12.
$$

</details>

### Exercise 3

Why is the level of a compact simply connected WZW model quantized?

<details><summary><strong>Solution</strong></summary>

The Wess–Zumino term depends on an extension of $g:\Sigma\to G$ to a three-manifold $B$. Two choices of extension differ by a map from a closed three-manifold to $G$. For compact simply connected simple $G$, the normalized integral of the Wess–Zumino three-form over this closed three-manifold is an integer because $\pi_3(G)=\mathbb Z$.

The Euclidean path-integral phase changes by $e^{2\pi i k n}$. This is independent of the extension only if

$$
k\in\mathbb Z.
$$

</details>

### Exercise 4

What is the main difference between an ordinary sigma model on $G$ and the WZW model on $G$?

<details><summary><strong>Solution</strong></summary>

An ordinary sigma model has only the metric kinetic term. The WZW model adds a quantized Wess–Zumino term. At the WZW point, the equations of motion imply chiral current conservation,

$$
\bar\partial J=0,
\qquad
\partial\bar J=0,
$$

which leads to affine current algebra symmetry. This chiral enhancement is absent in a generic sigma model on the same group manifold.

</details>

## References

- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).
- V. G. Knizhnik and A. B. Zamolodchikov, “Current algebra and Wess–Zumino model in two dimensions,” *Nuclear Physics B* **247** (1984).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- K. Gawedzki, “Non-compact WZW conformal field theories,” in *New Symmetry Principles in Quantum Field Theory*, Springer, 1992.

## Version history

- 2026-06-30: First polished draft. Added WZW action, level quantization, chiral currents, Polyakov–Wiegmann identity, Sugawara stress tensor, $SU(2)_k$ example, gauged-WZW and Chern–Simons previews, exercises, and references.
