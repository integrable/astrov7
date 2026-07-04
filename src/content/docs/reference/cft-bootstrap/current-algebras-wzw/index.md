---
title: "Current Algebras and WZW Models"
description: "Chapter overview for affine current algebras, Wess–Zumino–Witten models, Sugawara stress tensors, integrable representations, fusion, and coset constructions in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Senechal chs. 14–16; Ginsparg lectures; Witten 1984; Knizhnik and Zamolodchikov 1984; standard WZW literature."
topics:
  - current algebras
  - affine Lie algebras
  - WZW models
  - Kac–Moody symmetry
  - Sugawara construction
  - rational CFT
canonicalTopics:
  - affine-current-algebras
  - wzw-models
  - kac-moody-symmetry
researchStatus:
  established:
    - "Affine current algebras and WZW models are standard exactly solvable two-dimensional CFTs with finite rational spectra at positive integer level for compact simple groups."
  active:
    - "Modern uses include boundary CFT, defects, non-invertible symmetries, condensed-matter edge theories, cosets, dualities, and higher-categorical formulations."
---

Current Algebras and WZW Models is the chapter where two-dimensional CFT stops being only Virasoro theory and starts using larger chiral symmetry. The basic new object is a holomorphic conserved current $J^a(z)$ whose modes form an affine Lie algebra.

The chapter exists because many of the most important rational CFTs are not most naturally organized by Virasoro symmetry alone. Wess–Zumino–Witten models, coset CFTs, parafermions, nonabelian bosonization, quantum Hall edges, and many string worldsheet theories all use current algebra as their working language.

The central pipeline is

$$
\text{finite Lie algebra }\mathfrak g
\longrightarrow
\text{affine algebra }\widehat{\mathfrak g}_k
\longrightarrow
\text{WZW model }G_k
\longrightarrow
\text{rational CFT data}.
$$

The chapter is not a full course on Lie theory or vertex operator algebras. It gives the current-algebra toolkit needed to understand WZW models as CFTs and to use them in the rest of the volume.

## Prerequisites

You should know the [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) chapter through stress tensors, radial quantization, OPEs, and the cylinder–plane map. You should also know [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) and [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/), especially characters, fusion rules, and modular invariance.

For the Lie-algebra side, you should be comfortable with generators, structure constants, roots, weights, highest-weight representations, and compact simple Lie groups. The chapter reviews what it needs, but it is not the canonical home for finite-dimensional representation theory.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/) | The central extension of loop algebras, current modes, level, and the basic current OPE. |
| 2 | [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/) | The local CFT form of current algebra, including Ward identities and charge contours. |
| 3 | [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/) | How $k$, Killing-form conventions, Dynkin index, and current normalization fit together. |
| 4 | [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) | How the stress tensor is built from currents and why $c=k\dim\mathfrak g/(k+h^\vee)$. |
| 5 | [WZW Action](/cft-bootstrap/current-algebras-wzw/wzw-action/) | The sigma-model action with Wess–Zumino term and why the level is quantized. |
| 6 | [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) | Affine primaries, left-right transformation laws, conformal weights, and examples. |
| 7 | [Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/) | The finite set of allowed affine primaries at positive integer level. |
| 8 | [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) | Truncated tensor products, Verlinde formula, and simple examples such as $SU(2)_k$. |
| 9 | [Knizhnik–Zamolodchikov Equations](/cft-bootstrap/current-algebras-wzw/knizhnik-zamolodchikov-equations/) | The current-algebra differential equations for WZW correlators. |
| 10 | [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) | How subtracting current algebras produces new CFTs, including parafermion and minimal-model examples. |
| 11 | [Nonabelian Bosonization Preview](/cft-bootstrap/current-algebras-wzw/nonabelian-bosonization-preview/) | How free fermions reorganize into WZW current algebras and why this matters in matter systems. |

After this path, you should be able to recognize the current OPE, compute the Sugawara central charge, identify integrable affine primaries, and understand why WZW models are exact rational CFTs.

## Landmarks

The basic holomorphic current OPE is

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_c J^c(w)}{z-w}.
$$

Equivalently, the current modes obey

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}
+k m\kappa^{ab}\delta_{m+n,0}.
$$

The integer $k$ is the level. In compact WZW models it is quantized by the Wess–Zumino term and becomes part of the definition of the CFT.

The Sugawara construction expresses the stress tensor in terms of currents:

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z),
$$

in the common normalization where long roots have length squared $2$. The central charge is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

For $SU(2)_k$, this gives

$$
c=\frac{3k}{k+2},
$$

and the integrable affine primaries are labeled by spins

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

The WZW action has the schematic form

$$
S_{\rm WZW}[g]
=\frac{k}{8\pi}\int_\Sigma \operatorname{Tr}(g^{-1}\partial_\mu g\,g^{-1}\partial^\mu g)
+\frac{k}{12\pi}\int_B \operatorname{Tr}(g^{-1}dg)^3,
$$

where $\partial B=\Sigma$. The second term is topological and forces the quantization of $k$ when $G$ is compact and simply connected.

## Common confusions

**Current algebra is more than a global symmetry.** A global Lie algebra has finitely many charges. An affine current algebra has infinitely many modes and controls local holomorphic singularities.

**The level is not the central charge.** The level $k$ is the coefficient of the current-current central term. The Virasoro central charge $c$ follows from the Sugawara construction and depends on $k$ and $\mathfrak g$.

**Affine primaries are not just finite-dimensional Lie-algebra primaries.** They are highest-weight states for the affine algebra. At positive integer level, only integrable highest weights are allowed in the compact unitary WZW model.

**A WZW model is not merely a free sigma model on a group.** The Wess–Zumino term is essential. At the conformal point, it changes both the equations and the quantum consistency conditions.

**Do not ignore normalization.** Factors of $2$, $i$, root length, trace convention, and Dynkin index shift the visible form of the OPE. This chapter states its conventions on each page when normalization matters.

**Cosets are not quotients of spacetime.** A GKO coset is a quotient of chiral algebras or stress tensors, not a geometric quotient of the worldsheet.

## Boundaries

This chapter focuses on current algebra as two-dimensional CFT structure. It does not try to become a complete Lie-algebra textbook. Root systems, Weyl groups, weights, and representation theory are used only as needed for affine CFT.

The chapter also does not replace the full Current Algebras and WZW treatment in mathematical physics, vertex operator algebras, or modular tensor categories. It gives the physics-facing toolkit needed for CFT, bootstrap, and related QFT applications.

Supersymmetric WZW models, gauged WZW models, anomaly inflow, Chern–Simons/WZW correspondence, and boundary current algebra are touched as previews unless a later page explicitly develops them.

## Where to go next

After this chapter, the natural continuation is [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/) if you want to return to finite-dimensional conformal symmetry, or [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) if you want to use characters and modular invariance more systematically.

For applications, go to Boundary, Defect, and Interface CFT for Cardy states and current-preserving boundaries; to CFT in Statistical Physics and Matter for WZW descriptions of spin chains and edge theories; and to Supersymmetric CFT for supersymmetric current algebras and protected sectors.

## References

- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).
- V. G. Knizhnik and A. B. Zamolodchikov, “Current algebra and Wess–Zumino model in two dimensions,” *Nuclear Physics B* **247** (1984).
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- P. Goddard, A. Kent, and D. Olive, “Virasoro algebras and coset space models,” *Physics Letters B* **152** (1985).

## Version history

- 2026-06-30: Replaced scaffold with a polished chapter overview. Added prerequisites, reading path, landmarks, confusions, boundaries, next routes, references, and version history.
