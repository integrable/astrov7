---
title: "Kac Table"
description: "How the Kac table organizes degenerate Virasoro highest weights, field identifications, minimal-model primary spectra, and the first checks of rational CFT data."
sidebar:
  label: "Kac Table"
  order: 4
level: Graduate
status: "Polished draft"
source: "Belavin, Polyakov, and Zamolodchikov 1984; Friedan, Qiu, and Shenker; Di Francesco, Mathieu, and Senechal chs. 7–8; standard Virasoro representation theory."
topics:
  - Kac table
  - minimal models
  - Virasoro representations
  - degenerate fields
  - rational CFT
canonicalTopics:
  - kac-table
  - minimal-model-primary-spectrum
  - degenerate-virasoro-representations
researchStatus:
  established:
    - "The Kac table gives the degenerate Virasoro highest weights and, for minimal models, the finite set of primary fields after field identification."
  active:
    - "Kac-table logic remains a standard organizing tool in rational, logarithmic, boundary, and nonunitary two-dimensional CFTs, where additional identifications and module subtleties may appear."
---

## Summary

The **Kac table** is the finite array of degenerate Virasoro highest weights that appears in a minimal model. For the minimal model $\mathcal M(p,p')$, with coprime integers

$$
2\le p<p',
$$

the central charge and Kac weights are

$$
c_{p,p'}=1-\frac{6(p'-p)^2}{pp'},
$$

and

$$
h_{r,s}^{(p,p')}
=\frac{(p'r-ps)^2-(p'-p)^2}{4pp'},
\qquad
1\le r\le p-1,
\qquad
1\le s\le p'-1.
$$

The labels obey the field identification

$$
(r,s)\sim(p-r,p'-s),
$$

so the number of distinct primary families in the diagonal minimal model is

$$
\frac{(p-1)(p'-1)}{2}.
$$

The Kac table is not just a decorative table of numbers. It packages which Virasoro modules are degenerate, which null states must be quotiented out, which differential equations correlators satisfy, and which primary families can appear in a rational CFT.

## Prerequisites

Read [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/), [Tricritical Ising CFT](/cft-bootstrap/minimal-models-rational-cft/tricritical-ising-cft/), [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/), and [Kac Determinant Preview](/cft-bootstrap/virasoro-central-charge/kac-determinant-preview/) first.

The page uses the Virasoro convention

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

A highest-weight state satisfies

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

## Core idea

A Virasoro Verma module is usually large: it is generated freely by acting with all ordered products of negative modes $L_{-n}$ on a highest-weight state. At level $N$, the number of descendant states is the partition number $p(N)$.

At special values of $c$ and $h$, the module contains null states. These null states generate submodules, and the physical irreducible representation is obtained by quotienting them out. The Kac determinant tells us exactly where these null states appear.

The Kac table is the organized list of these special weights. In a minimal model, two infinite null-state patterns line up so efficiently that only finitely many irreducible primary families are needed for a closed local CFT.

A good way to remember the hierarchy is

$$
\text{Kac determinant zeros}
\longrightarrow
\text{degenerate modules}
\longrightarrow
\text{Kac table}
\longrightarrow
\text{finite minimal-model spectrum}.
$$

## Setup and conventions

There are several equivalent parametrizations of the Virasoro central charge. For minimal models, the most concrete one uses coprime positive integers $p,p'$ with $2\le p<p'$:

$$
c_{p,p'}=1-\frac{6(p'-p)^2}{pp'}.
$$

The corresponding Kac weights are

$$
h_{r,s}^{(p,p')}
=\frac{(p'r-ps)^2-(p'-p)^2}{4pp'}.
$$

The labels $r$ and $s$ are positive integers. In the finite Kac table of the minimal model, one restricts to

$$
1\le r\le p-1,
\qquad
1\le s\le p'-1.
$$

The field identification follows immediately from the square in the weight formula:

$$
h_{p-r,p'-s}^{(p,p')}=h_{r,s}^{(p,p')}.
$$

Thus the two labels represent the same irreducible primary family in the minimal model:

$$
\phi_{r,s}\equiv\phi_{p-r,p'-s}.
$$

The diagonal bosonic minimal model pairs the same chiral representation with the same antiholomorphic representation. A diagonal scalar primary has weights

$$
(h_{r,s},h_{r,s})
$$

and scaling dimension

$$
\Delta_{r,s}=2h_{r,s}.
$$

## Degenerate labels before minimization

The formula $h_{r,s}$ makes sense for all positive integers $r,s$. In a general Virasoro theory with the corresponding central charge, a highest-weight representation with weight $h_{r,s}$ has a null vector at level

$$
N=rs.
$$

For example:

| Label | First null level | Meaning |
|---:|---:|---|
| $(1,1)$ | $1$ | Vacuum-type degeneracy; $L_{-1}|0\rangle$ is null in a vacuum module. |
| $(2,1)$ | $2$ | Level-two degenerate field. |
| $(1,2)$ | $2$ | Another level-two degenerate field. |
| $(3,1)$ | $3$ | Level-three degenerate field. |
| $(1,3)$ | $3$ | Another level-three degenerate field. |
| $(2,2)$ | $4$ | Level-four degenerate field. |

The minimal-model Kac table is a finite window in this infinite grid. The finite window is special because it is closed under the field identification and leads to finitely many primary families.

## The finite table

For $\mathcal M(p,p')$, draw a rectangle with rows

$$
r=1,2,\ldots,p-1
$$

and columns

$$
s=1,2,\ldots,p'-1.
$$

Each box contains the weight $h_{r,s}$. Opposite boxes under

$$
(r,s)\mapsto(p-r,p'-s)
$$

are identified. The rectangle has $(p-1)(p'-1)$ boxes, and the identification halves this number.

The finite table is therefore a quotient of a rectangle, not merely a set of low-lying dimensions. The quotient matters. It is what prevents double-counting fields.

## Example: Ising model

The Ising CFT is

$$
\mathcal M(3,4),
\qquad
c=\frac12.
$$

The Kac weights are

$$
h_{r,s}=\frac{(4r-3s)^2-1}{48},
\qquad
r=1,2,
\qquad
s=1,2,3.
$$

The full rectangle is

|  | $s=1$ | $s=2$ | $s=3$ |
|---:|---:|---:|---:|
| $r=1$ | $0$ | $1/16$ | $1/2$ |
| $r=2$ | $1/2$ | $1/16$ | $0$ |

The identification is

$$
(r,s)\sim(3-r,4-s).
$$

Thus there are three distinct primaries:

| Field | Representative | Weight | Diagonal dimension |
|---|---:|---:|---:|
| $\mathbf 1$ | $(1,1)$ | $0$ | $0$ |
| $\sigma$ | $(1,2)$ | $1/16$ | $1/8$ |
| $\epsilon$ | $(2,1)$ | $1/2$ | $1$ |

The reflected entries $(2,3)$, $(2,2)$, and $(1,3)$ are not new fields. They are the same primary families written with the identified labels.

## Example: tricritical Ising model

The tricritical Ising CFT is

$$
\mathcal M(4,5),
\qquad
c=\frac{7}{10}.
$$

The Kac weights are

$$
h_{r,s}=\frac{(5r-4s)^2-1}{80},
\qquad
r=1,2,3,
\qquad
s=1,2,3,4.
$$

The full rectangle is

|  | $s=1$ | $s=2$ | $s=3$ | $s=4$ |
|---:|---:|---:|---:|---:|
| $r=1$ | $0$ | $1/10$ | $3/5$ | $3/2$ |
| $r=2$ | $7/16$ | $3/80$ | $3/80$ | $7/16$ |
| $r=3$ | $3/2$ | $3/5$ | $1/10$ | $0$ |

The identification is

$$
(r,s)\sim(4-r,5-s).
$$

A convenient representative set is

| Field | Representative | Weight | Diagonal dimension |
|---|---:|---:|---:|
| $\mathbf 1$ | $(1,1)$ | $0$ | $0$ |
| $\epsilon$ | $(1,2)$ | $1/10$ | $1/5$ |
| $\epsilon'$ | $(1,3)$ | $3/5$ | $6/5$ |
| $\epsilon''$ | $(1,4)$ | $3/2$ | $3$ |
| $\sigma$ | $(2,2)$ | $3/80$ | $3/40$ |
| $\sigma'$ | $(2,1)$ | $7/16$ | $7/8$ |

The diagonal dimensions immediately identify the relevant scalar primaries: $\sigma$, $\sigma'$, $\epsilon$, and $\epsilon'$ have $\Delta<2$, while $\epsilon''$ is irrelevant.

## The unitary series

The unitary minimal models are the special series

$$
\mathcal M(m,m+1),
\qquad
m=3,4,5,\ldots .
$$

Their central charges are

$$
c_m=1-\frac{6}{m(m+1)}.
$$

The first few are

| $m$ | Model | $c$ | Number of primaries |
|---:|---|---:|---:|
| $3$ | Ising | $1/2$ | $3$ |
| $4$ | Tricritical Ising | $7/10$ | $6$ |
| $5$ | Three-state Potts / tetracritical Ising family, depending on modular invariant | $4/5$ | $10$ in the diagonal minimal model |
| $6$ | Next unitary minimal model | $6/7$ | $15$ |

The number of diagonal primary families is

$$
\frac{(m-1)m}{2}.
$$

The phrase “unitary minimal model” means more than $c<1$. It means the minimal model belongs to this adjacent-integer series. Nonunitary minimal models also have Kac tables, but their Hilbert spaces are not positive definite.

## Nonunitary examples

The Yang–Lee minimal model is

$$
\mathcal M(2,5),
\qquad
c=-\frac{22}{5}.
$$

The Kac rectangle has

$$
r=1,
\qquad
s=1,2,3,4,
$$

with identification

$$
(1,s)\sim(1,5-s).
$$

There are two primaries:

| Field | Representative | Weight |
|---|---:|---:|
| $\mathbf 1$ | $(1,1)$ | $0$ |
| $\phi$ | $(1,2)$ | $-1/5$ |

The negative conformal weight is not a typo. It is a sign of nonunitarity. The Yang–Lee model is still a consistent nonunitary CFT and is one of the cleanest examples where the Kac table remains powerful outside unitary statistical mechanics.

## Why field identification is not optional

Because the weight formula only depends on $(p'r-ps)^2$, the labels $(r,s)$ and $(p-r,p'-s)$ have the same conformal weight. But equality of weights alone does not always imply equality of fields in a generic CFT. In minimal models, the representation-theoretic structure identifies the corresponding irreducible modules.

The identification is therefore part of the minimal-model definition:

$$
\phi_{r,s}\equiv\phi_{p-r,p'-s}.
$$

Ignoring it doubles the spectrum and ruins modular and fusion consistency.

This is a useful warning for later generalizations. In logarithmic CFTs, extended chiral algebras, orbifolds, and non-diagonal modular invariants, labels can behave differently. One should not infer all field identifications from equal conformal weights alone.

## The table and null states

The label $(r,s)$ predicts a null state at level $rs$. In a minimal model, there is also another null state related to the identified label. The two null directions are what make the representation finite enough to support rational CFT structure.

For a primary $\phi_{r,s}$, the first null level is

$$
N_1=rs.
$$

The identified partner gives another null level

$$
N_2=(p-r)(p'-s).
$$

For example, in the Ising model:

| Field | Label | Null levels |
|---|---:|---:|
| $\mathbf 1$ | $(1,1)$ | $1$ and $6$ |
| $\sigma$ | $(1,2)$ | $2$ and $2$ |
| $\epsilon$ | $(2,1)$ | $2$ and $3$ |

These null states are not just representation-theory curiosities. They produce differential equations for correlation functions and truncate fusion rules.

## Reading the table physically

A Kac table gives a compact physical summary:

| Table datum | Physical meaning |
|---|---|
| $c$ | Number of stress-tensor degrees of freedom in the CFT-normalized sense. |
| $h_{r,s}$ | Chiral scaling weight of the primary family. |
| $\Delta=2h$ in diagonal models | Scaling dimension of the scalar local operator. |
| $rs$ | Level of the first null state. |
| Field identification | Removes duplicate labels and fixes the finite spectrum. |
| Relevant entries with $2h<2$ | Scalar perturbations that can drive RG flows away from the fixed point. |

This makes the Kac table a bridge between algebra and physics. From a small array of rational numbers one reads off critical exponents, relevant deformations, fusion constraints, and possible exact correlator equations.

## Common pitfalls

**Do not confuse Kac labels with unique fields before quotienting.** In minimal models, $(r,s)$ and $(p-r,p'-s)$ label the same primary family.

**Do not confuse chiral weight with scaling dimension.** In a diagonal scalar theory, $\Delta=2h$. In a chiral theory, a field may have weights $(h,0)$ instead.

**Do not assume every table with repeated weights has field identification.** Equal weights can arise accidentally. Minimal-model field identification is a specific representation-theoretic statement.

**Do not forget nonunitary models.** The Kac table applies beyond the unitary series. Negative weights and non-positive norms are allowed in nonunitary theories.

**Do not treat the Kac table as the full OPE.** It gives allowed primary families and degenerate representations. OPE coefficients, modular invariants, and locality choices require more data.

**Do not ignore the modular invariant.** The Kac table gives chiral data. A full local CFT must pair left and right chiral sectors consistently.

## Relations to other pages

This page makes the tabular structure behind [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) explicit. It explains the spectra used in [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/) and [Tricritical Ising CFT](/cft-bootstrap/minimal-models-rational-cft/tricritical-ising-cft/).

The representation-theoretic origin belongs to [Kac Determinant Preview](/cft-bootstrap/virasoro-central-charge/kac-determinant-preview/) and [Null States](/cft-bootstrap/virasoro-central-charge/null-states/). The next page, [Null-Vector Differential Equations](/cft-bootstrap/minimal-models-rational-cft/null-vector-differential-equations/), explains how entries in the table become differential equations for correlators.

Later pages on [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/) add the algebraic and modular structures that turn the table into a full local CFT.

## Research status

The Kac table and its role in Virasoro minimal models are established. The unitary $c<1$ minimal series is a classic theorem-level result in two-dimensional CFT representation theory.

Active research uses Kac-table ideas in broader contexts: logarithmic CFT, nonsemisimple tensor categories, boundary and defect conditions, nonunitary statistical systems, supersymmetric minimal models, and rational theories with extended chiral algebras.

## Exercises

### Exercise 1

Show that the Kac weights obey

$$
h_{p-r,p'-s}^{(p,p')}=h_{r,s}^{(p,p')}.
$$

<details><summary><strong>Solution</strong></summary>

Compute the numerator for the identified label:

$$
p'(p-r)-p(p'-s)=pp'-p'r-pp'+ps=-(p'r-ps).
$$

Squaring removes the sign:

$$
[p'(p-r)-p(p'-s)]^2=(p'r-ps)^2.
$$

The subtraction term $(p'-p)^2$ and denominator $4pp'$ are unchanged, so

$$
h_{p-r,p'-s}^{(p,p')}=h_{r,s}^{(p,p')}.
$$

</details>

### Exercise 2

Use the Kac formula for $\mathcal M(3,4)$ to fill the Ising Kac table.

<details><summary><strong>Solution</strong></summary>

For $p=3$, $p'=4$,

$$
h_{r,s}=\frac{(4r-3s)^2-1}{48}.
$$

The allowed labels are $r=1,2$ and $s=1,2,3$.

For $r=1$:

$$
h_{1,1}=0,
\qquad
h_{1,2}=\frac{1}{16},
\qquad
h_{1,3}=\frac12.
$$

For $r=2$:

$$
h_{2,1}=\frac12,
\qquad
h_{2,2}=\frac{1}{16},
\qquad
h_{2,3}=0.
$$

Thus the table is

|  | $s=1$ | $s=2$ | $s=3$ |
|---:|---:|---:|---:|
| $r=1$ | $0$ | $1/16$ | $1/2$ |
| $r=2$ | $1/2$ | $1/16$ | $0$ |

The field identification leaves three distinct primary families.

</details>

### Exercise 3

How many primary families does $\mathcal M(5,6)$ have after field identification?

<details><summary><strong>Solution</strong></summary>

The finite Kac rectangle has

$$
(p-1)(p'-1)=(5-1)(6-1)=20
$$

entries. The field identification pairs entries, so the number of primary families is

$$
\frac{20}{2}=10.
$$

</details>

### Exercise 4

For $\mathcal M(4,5)$, compute the weights $h_{1,2}$, $h_{1,3}$, and $h_{2,2}$.

<details><summary><strong>Solution</strong></summary>

For $p=4$, $p'=5$,

$$
h_{r,s}=\frac{(5r-4s)^2-1}{80}.
$$

Then

$$
h_{1,2}=\frac{(5-8)^2-1}{80}=\frac{8}{80}=\frac{1}{10},
$$

$$
h_{1,3}=\frac{(5-12)^2-1}{80}=\frac{48}{80}=\frac35,
$$

and

$$
h_{2,2}=\frac{(10-8)^2-1}{80}=\frac{3}{80}.
$$

For the diagonal scalar fields, the corresponding dimensions are $1/5$, $6/5$, and $3/40$.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- D. Friedan, Z. Qiu, and S. Shenker, “Conformal invariance, unitarity, and critical exponents in two dimensions,” *Physical Review Letters* **52** (1984).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- P. Goddard, A. Kent, and D. Olive, “Unitary representations of the Virasoro and super-Virasoro algebras,” *Communications in Mathematical Physics* **103** (1986).

## Version history

- 2026-06-28: First polished draft. Added Kac-weight conventions, field identification, Ising and tricritical Ising tables, unitary and nonunitary examples, exercises, and references.
