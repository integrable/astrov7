---
title: "Minimal Models and Rational CFT"
description: "Chapter overview for minimal models, finite Virasoro spectra, fusion rules, characters, and rational conformal field theory in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Belavin, Polyakov, and Zamolodchikov 1984; Di Francesco, Mathieu, and Sénéchal 1997; Ginsparg 1988"
topics:
  - minimal models
  - rational conformal field theory
  - Virasoro representations
  - Kac tables
  - fusion rules
  - characters
canonicalTopics:
  - minimal-models-and-rational-cft
  - virasoro-representation-theory
  - rational-cft-data
researchStatus:
  established:
    - "Virasoro minimal models are exactly solvable two-dimensional CFTs whose finite primary spectra, null states, fusion rules, and characters are standard parts of conformal field theory."
  active:
    - "The broader classification of rational CFTs, modular tensor categories, logarithmic extensions, defects, and non-semisimple generalizations remains an active interface between QFT, mathematics, and statistical physics."
---

Minimal Models and Rational CFT is the chapter where the abstract Virasoro machinery becomes a laboratory of exact solutions. The previous chapter built the algebra, central charge, highest-weight modules, null states, Ward identities, and the conformal anomaly. This chapter turns those ingredients into complete two-dimensional CFTs with finitely many primary families.

The first examples are the Virasoro minimal models. They include the Yang–Lee edge singularity, the Ising CFT, the tricritical Ising CFT, and the unitary minimal series. Their power is not that they are complicated. Their power is that they are small enough to solve and rich enough to teach the general logic of rational CFT.

The slogan is

$$
\text{null states}
\quad\Longrightarrow\quad
\text{finite fusion}
\quad\Longrightarrow\quad
\text{solvable correlators and modular data}.
$$

Read this chapter when you want a concrete bridge from Virasoro representation theory to exact CFT data, lattice criticality, fusion algebras, modular invariance, and the bootstrap solution of two-dimensional models.

## Prerequisites

You should know the [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/), [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/), [Null States](/cft-bootstrap/virasoro-central-charge/null-states/), and [Kac Determinant Preview](/cft-bootstrap/virasoro-central-charge/kac-determinant-preview/). You should also be comfortable with [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) and the [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/).

Readers entering from statistical physics should first skim [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/) and [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/). Readers entering from bootstrap should know [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) and [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) | The definition of $\mathcal M(p,p')$, the Kac table, the finite primary spectrum, and the unitary series. |
| 2 | [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/) | The smallest unitary example: $\mathbf 1$, $\sigma$, $\epsilon$, fusion rules, and critical-Ising data. |
| 3 | [Tricritical Ising CFT](/cft-bootstrap/minimal-models-rational-cft/tricritical-ising-cft/) | The next unitary minimal model and its richer relevant-operator structure. |
| 4 | [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/) | A systematic reference for Kac labels, identifications, null states, conformal weights, and example tables. |
| 5 | [Null-Vector Differential Equations](/cft-bootstrap/minimal-models-rational-cft/null-vector-differential-equations/) | How null-state decoupling turns Virasoro representation theory into differential equations for correlators. |
| 6 | [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/) | The finite operator algebra and the selection rules controlling OPE channels. |
| 7 | [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/) | The graded traces that count states in Virasoro modules and build torus partition functions. |
| 8 | [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/) | The broader framework of finite primary spectra, chiral algebras, modular data, and fusion categories. |

After this path, you should be able to read a Kac table, identify the primary fields of a minimal model, use fusion rules, and understand why rational CFTs are exactly solvable in a way generic CFTs are not.

## Landmarks

The core landmarks are these.

| Landmark | Meaning |
|---|---|
| Minimal central charge | $c=1-6(p-p')^2/(pp')$ for coprime integers $2\leq p<p'$. |
| Kac weights | $h_{r,s}=\big((p'r-ps)^2-(p'-p)^2\big)/(4pp')$. |
| Field identification | $(r,s)\sim(p-r,p'-s)$ in $\mathcal M(p,p')$. |
| Number of Virasoro primaries | $(p-1)(p'-1)/2$. |
| Unitary series | $\mathcal M(m,m+1)$ with $m=3,4,5,\ldots$. |
| Rationality | A finite set of irreducible chiral representations closes under fusion. |
| Modular data | Characters transform under $SL(2,\mathbb Z)$ and constrain torus partition functions. |

<figure class="doc-figure" style="--figure-width: 46rem;">

![A flow diagram from Virasoro representation theory to minimal models and rational CFT data.](/figures/cft-bootstrap/minimal-models-rational-cft-map.svg)

<figcaption>

Minimal models sit at the intersection of Virasoro representation theory and full CFT consistency. Null states truncate Verma modules, the Kac table gives a finite set of primaries, fusion closes on that set, and characters/modular data organize the torus theory.

</figcaption>
</figure>

The important conceptual transition is from a representation of the algebra to a full CFT. A list of allowed highest weights is not yet a full theory. One must also specify OPE coefficients, fusion rules, locality, modular invariants, and the way left- and right-moving sectors are paired.

## Common confusions

A minimal model is not a finite-dimensional Hilbert space. Each primary field has infinitely many descendants before null states are quotiented, and the full Hilbert space still contains infinitely many states on the cylinder.

A finite primary spectrum is not the same thing as a free theory. Minimal models are usually interacting CFTs, even when their data can be solved exactly.

A Kac table is not a list of distinct fields before identifications. The labels $(r,s)$ and $(p-r,p'-s)$ describe the same Virasoro primary in $\mathcal M(p,p')$.

The word “rational” does not mean that every conformal dimension is a rational number in every convention one might write down. It means that the chiral algebra has only finitely many irreducible representations appearing in the theory. In common Virasoro minimal models the conformal weights and central charge are rational, but rationality is really a representation-theoretic property.

A modular invariant partition function is not optional decoration. For a local two-dimensional CFT on closed Riemann surfaces, the left–right pairing of chiral sectors must be compatible with modular transformations.

## Boundaries

This chapter treats Virasoro minimal models and the rational-CFT toolkit that grows naturally from them. It does not try to replace the [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) chapter, where the algebra and its representation theory are developed.

Affine current algebras and WZW models belong in [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/). Modular bootstrap as a constraint method for spectra belongs in [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/). Vertex operator algebras, modular tensor categories, and theorem-first RCFT are important, but their full mathematical development belongs in mathematical and rigorous QFT material.

The chapter also does not treat every two-dimensional critical lattice model. It uses lattice examples only when they clarify CFT data and universality.

## Where to go next

If your goal is exact two-dimensional models, continue through [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/), and [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/).

If your goal is bootstrap logic, pair this chapter with [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) and [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/). Minimal models are the cleanest place to see how crossing, OPE closure, null equations, and exact spectrum data cooperate.

If your goal is modular data, read [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), then continue to [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/).

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- D. Friedan, Z. Qiu, and S. Shenker, “Conformal invariance, unitarity, and critical exponents in two dimensions,” *Physical Review Letters* **52** (1984).
- D. Friedan, Z. Qiu, and S. Shenker, “Details of the non-unitarity proof for highest weight representations of the Virasoro algebra,” *Communications in Mathematical Physics* **107** (1986).
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- J. L. Cardy, “Operator content of two-dimensional conformally invariant theories,” *Nuclear Physics B* **270** (1986).
- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989).

## Version history

- 2026-06-28: First polished draft. Replaced scaffold overview with a chapter doorway, reading path, landmarks, and boundaries for minimal models and rational CFT.
