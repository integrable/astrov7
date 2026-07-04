---
title: "Rational CFT"
description: "What it means for a two-dimensional conformal field theory to be rational, and how chiral algebras, characters, fusion rules, modular data, and local operator spectra fit together."
sidebar:
  label: "Rational CFT"
  order: 7
level: Graduate
status: "Polished draft"
source: "Moore and Seiberg; Verlinde 1988; Di Francesco, Mathieu, and Senechal chs. 10–11; standard rational CFT literature."
topics:
  - rational CFT
  - chiral algebra
  - characters
  - modular invariance
  - fusion rules
  - minimal models
canonicalTopics:
  - rational-cft
  - chiral-algebra
  - modular-data
researchStatus:
  established:
    - "A rational CFT has finitely many irreducible representations with respect to a chosen chiral algebra, leading to finite fusion rules and finite-dimensional modular transformation data."
  active:
    - "Modern work extends rational-CFT ideas to logarithmic, nonsemisimple, categorical, boundary, defect, and topological-phase settings."
---

## Summary

A **rational conformal field theory** is a two-dimensional CFT whose local operator content is finite when organized by a chosen chiral algebra. More precisely, the chiral algebra has finitely many irreducible representations, and the torus characters span a finite-dimensional representation of the modular group.

The basic data are

$$
\text{chiral algebra}
\quad+
\text{finite set of representations}
\quad+
\text{fusion rules}
\quad+
\text{modular data}
\quad+
\text{consistent left-right pairing}.
$$

Minimal models are rational with respect to the Virasoro algebra. WZW models are rational with respect to affine Lie algebras at positive integer level. Compact bosons are rational only at special radii after choosing the appropriate extended chiral algebra.

The most common trap is to say “finite number of local fields.” That is not quite right. There are infinitely many descendant fields. Rationality means finitely many **primary families** with respect to the chosen chiral algebra.

## Prerequisites

Read [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) alongside this page. If [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/) has not been written yet, you can still read this page as a conceptual preview.

You should also know the torus modular parameter $\tau$ and the two generators

$$
S:\tau\mapsto -\frac1\tau,
\qquad
T:\tau\mapsto \tau+1.
$$

## Core idea

A generic two-dimensional CFT can have infinitely many primary families, or even a continuous spectrum. Rational CFT is the opposite extreme: symmetry is strong enough that the chiral sector decomposes into finitely many irreducible modules.

Let $\mathcal A$ be the chosen chiral algebra. It may be the Virasoro algebra, an affine current algebra, a $W$-algebra, a superconformal algebra, or a larger vertex operator algebra. Rationality is always rationality **with respect to this choice**.

The Hilbert space of a full local CFT has the schematic form

$$
\mathcal H
=\bigoplus_{i,j} M_{ij}\,\mathcal V_i\otimes\overline{\mathcal V}_j,
$$

where $\mathcal V_i$ are irreducible chiral representations and

$$
M_{ij}\in\mathbb Z_{\ge0}.
$$

The matrix $M$ is not arbitrary. It must make the torus partition function modular invariant and must be compatible with locality and crossing.

## Chiral algebra dependence

Rationality depends on the chiral algebra used to organize the theory.

The same CFT can look non-rational with respect to a small algebra and rational with respect to a larger algebra. This is not a contradiction. Enlarging the chiral algebra groups several smaller conformal families into fewer larger families.

For example, the compact free boson at a generic radius has infinitely many Virasoro primary fields. At special rational radii, there is an extended chiral algebra under which the theory becomes rational.

This is why one should not define rational CFT as “a CFT with finitely many Virasoro primaries” unless the Virasoro algebra is explicitly the chosen chiral algebra. Virasoro minimal models satisfy that stronger condition, but many important rational CFTs do not.

## Characters

For each irreducible chiral representation $\mathcal V_i$, the character is

$$
\chi_i(\tau)
=\operatorname{Tr}_{\mathcal V_i}
q^{L_0-c/24},
\qquad
q=e^{2\pi i\tau}.
$$

The character counts states in a chiral module, weighted by conformal energy. In rational CFT, the finite vector of characters transforms among itself under modular transformations:

$$
\chi_i(-1/\tau)=\sum_j S_{ij}\chi_j(\tau),
$$

and

$$
\chi_i(\tau+1)=\sum_j T_{ij}\chi_j(\tau).
$$

The matrices $S$ and $T$ are called modular data. They are not decorative. Together with fusion rules, they encode much of the algebraic content of the theory.

## Modular invariant partition functions

A full local CFT on the torus has partition function

$$
Z(\tau,
\bar\tau)=\sum_{i,j}M_{ij}\chi_i(\tau)\overline{\chi_j(\tau)}.
$$

Modular invariance requires

$$
S M S^\dagger=M,
\qquad
T M T^\dagger=M.
$$

The simplest possibility is the diagonal invariant

$$
Z_{\rm diag}(\tau,\bar\tau)=\sum_i |\chi_i(\tau)|^2.
$$

But diagonal invariants are not the only possibilities. Non-diagonal modular invariants appear in important models, including Potts-type theories, simple-current extensions, and exceptional cases.

The chiral representation theory is therefore only one half of the story. A local CFT requires a consistent left-right pairing.

## Fusion and the Verlinde formula

The chiral fusion rules are

$$
\mathcal V_i\times\mathcal V_j
=\sum_k N_{ij}{}^k\mathcal V_k.
$$

For a semisimple rational CFT, the Verlinde formula computes these integers from the modular $S$ matrix:

$$
N_{ij}{}^k
=\sum_\ell
\frac{S_{i\ell}S_{j\ell}S^*_{k\ell}}{S_{0\ell}}.
$$

This is one of the deepest bridges in the subject:

$$
\text{modular transformations on the torus}
\quad\Longleftrightarrow\quad
\text{operator algebra on the sphere}.
$$

Here $0$ labels the vacuum representation. The same $S$ matrix also gives quantum dimensions:

$$
d_i=\frac{S_{i0}}{S_{00}}.
$$

For the Ising CFT, this gives

$$
d_{\mathbf 1}=1,
\qquad
d_\sigma=\sqrt2,
\qquad
d_\epsilon=1.
$$

## Examples

| Theory | Chiral algebra | Rational? | Comment |
|---|---|---:|---|
| Virasoro minimal model $\mathcal M(p,p')$ | Virasoro | yes | Finite Kac table after field identification. |
| Ising CFT | Virasoro | yes | Three Virasoro primary families. |
| Tricritical Ising CFT | Virasoro | yes | Six Virasoro primary families. |
| WZW model at positive integer level | affine Lie algebra | yes | Primary fields are integrable highest-weight representations. |
| Compact boson at generic radius | Virasoro | no | Infinitely many Virasoro primaries. |
| Compact boson at rational radius | extended chiral algebra | yes | Rational after extending the current algebra. |
| Liouville theory | Virasoro | no | Continuous spectrum. |

The lesson is that rationality is not simply a statement about central charge. It is a statement about representation theory and the chosen chiral algebra.

## Minimal models as rational CFTs

Virasoro minimal models are the most accessible rational CFTs. For $\mathcal M(p,p')$,

$$
c=1-\frac{6(p'-p)^2}{pp'},
$$

and the finite Kac table gives

$$
\frac{(p-1)(p'-1)}{2}
$$

distinct primary families.

The Ising model has three:

$$
\mathbf 1,\quad \sigma,\quad \epsilon.
$$

The tricritical Ising model has six:

$$
\mathbf 1,\quad \epsilon,\quad \epsilon',\quad \epsilon'',\quad \sigma,\quad \sigma'.
$$

Their rationality follows from degenerate Virasoro representations, null-state quotienting, finite fusion rules, and modularly closed characters.

## Rational does not mean solvable without choices

Rational CFT is highly constrained, but a full theory still requires choices.

One must specify:

| Choice | Why it matters |
|---|---|
| Chiral algebra | Determines what counts as a primary family. |
| Representation set | Determines the finite chiral spectrum. |
| Fusion rules | Determines allowed chiral OPE channels. |
| Modular invariant | Determines left-right pairing in the full local theory. |
| OPE coefficients and fusing data | Determine local correlators and crossing. |
| Reality and locality conditions | Determine which chiral data make a physical local CFT. |

A set of characters and fusion rules is not automatically a complete local CFT. Rational CFT is a tightly constrained construction problem, not merely a finite table.

## Boundary and defect preview

Rational CFT becomes especially powerful on surfaces with boundaries and defects. Boundary conditions, boundary fields, and topological defects can often be classified using the same fusion and modular data.

For example, Cardy boundary states in diagonal rational CFTs are labeled by the same set of primaries as the bulk chiral representations. Fusion rules then control boundary operator spectra.

This is a preview, not a replacement for the Boundary, Defect, and Interface CFT chapter. The important point here is that rationality makes boundary and defect problems finite enough to solve exactly.

## Common pitfalls

**Do not say rational means finitely many fields.** Descendants are still infinite. Rationality means finitely many primary families with respect to a chosen chiral algebra.

**Do not forget the phrase “with respect to a chiral algebra.”** Enlarging the chiral algebra can turn an infinite Virasoro decomposition into a finite extended-algebra decomposition.

**Do not confuse chiral data with a full local CFT.** A local CFT must pair left and right sectors consistently and satisfy modular invariance, locality, and crossing.

**Do not assume diagonal modular invariance.** It is common and simple, but non-diagonal invariants are essential in many rational CFTs.

**Do not assume rational means unitary.** There are nonunitary rational CFTs, such as the Yang–Lee minimal model.

**Do not apply semisimple formulas blindly to logarithmic CFT.** Logarithmic theories can have indecomposable modules and nonsemisimple fusion, so the standard rational-CFT package must be modified.

## Relations to other pages

This page synthesizes [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), and the model pages [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/) and [Tricritical Ising CFT](/cft-bootstrap/minimal-models-rational-cft/tricritical-ising-cft/).

It prepares [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), modular-invariance pages, and the later Current Algebras and WZW Models chapter. It also connects to [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/) and [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/).

## Research status

The rational-CFT framework of chiral algebras, characters, modular invariance, fusion rules, and Verlinde formula is established. It is one of the best-understood nonperturbative sectors of quantum field theory.

Active research extends and exports the framework: logarithmic CFT, nonsemisimple tensor categories, topological phases, non-invertible symmetries, boundary and defect classification, generalized orbifolds, and moonshine-type structures. The classical rational-CFT toolkit remains the reference point even when its assumptions are deliberately relaxed.

## Exercises

### Exercise 1

Why is it misleading to define rational CFT as a theory with finitely many local fields?

<details><summary><strong>Solution</strong></summary>

Even a rational CFT has infinitely many descendant fields. For example, once a primary $\phi$ is present, its Virasoro descendants

$$
L_{-n_1}\cdots L_{-n_k}\phi
$$

produce infinitely many fields as the level increases. Rationality means that there are finitely many irreducible primary families with respect to the chosen chiral algebra, not finitely many fields total.

</details>

### Exercise 2

For a diagonal rational CFT, show that the partition function

$$
Z=\sum_i |\chi_i|^2
$$

is invariant under $S$ if the modular $S$ matrix is unitary.

<details><summary><strong>Solution</strong></summary>

Under $S$,

$$
\chi_i\mapsto \sum_j S_{ij}\chi_j.
$$

Therefore

$$
Z\mapsto
\sum_i\left(\sum_j S_{ij}\chi_j\right)
\left(\sum_k S_{ik}\chi_k\right)^*.
$$

This equals

$$
\sum_{j,k}\left(\sum_i S_{ij}S^*_{ik}\right)\chi_j\overline{\chi_k}.
$$

Unitarity gives

$$
\sum_i S_{ij}S^*_{ik}=\delta_{jk},
$$

so

$$
Z\mapsto\sum_j |\chi_j|^2=Z.
$$

</details>

### Exercise 3

Why can the compact boson be non-rational at a generic radius but rational at special radii?

<details><summary><strong>Solution</strong></summary>

At a generic radius, the compact boson has infinitely many Virasoro primary fields associated with momentum and winding sectors. At special rational radii, the chiral algebra can be extended by additional currents or vertex operators. With respect to the enlarged algebra, infinitely many Virasoro families are grouped into finitely many extended-algebra representations. Rationality is therefore a statement about the chosen chiral algebra.

</details>

### Exercise 4

What extra ingredient is needed to pass from a finite set of chiral representations to a full local rational CFT?

<details><summary><strong>Solution</strong></summary>

One must specify how left-moving and right-moving representations are paired in the full Hilbert space:

$$
\mathcal H=\bigoplus_{i,j}M_{ij}\mathcal V_i\otimes\overline{\mathcal V}_j.
$$

The nonnegative integer matrix $M$ must give a modular-invariant partition function and be compatible with locality and crossing. Thus a finite chiral representation category alone is not the whole local CFT.

</details>

## References

- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989).
- E. Verlinde, “Fusion rules and modular transformations in 2D conformal field theory,” *Nuclear Physics B* **300** (1988).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- G. Segal, “The definition of conformal field theory,” in *Topology, Geometry and Quantum Field Theory*, Cambridge University Press.
- Y.-Z. Huang, *Two-Dimensional Conformal Geometry and Vertex Operator Algebras*, Birkhauser, 1997.

## Version history

- 2026-06-30: First polished draft. Added definition, chiral-algebra dependence, characters, modular invariants, Verlinde formula, examples, pitfalls, exercises, and references.
