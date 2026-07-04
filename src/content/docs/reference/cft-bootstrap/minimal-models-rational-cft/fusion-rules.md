---
title: "Fusion Rules"
description: "How fusion rules organize the allowed operator families in minimal and rational conformal field theories, and how they differ from OPE coefficients."
sidebar:
  label: "Fusion Rules"
  order: 6
level: Graduate
status: "Polished draft"
source: "Belavin, Polyakov, and Zamolodchikov 1984; Verlinde 1988; Di Francesco, Mathieu, and Senechal chs. 7–10."
topics:
  - fusion rules
  - minimal models
  - rational CFT
  - Verlinde formula
  - operator product expansion
canonicalTopics:
  - fusion-rules
  - minimal-model-fusion
  - verlinde-formula
researchStatus:
  established:
    - "Fusion rules give the finite algebra of allowed primary families in rational CFT and are exactly computable in Virasoro minimal models."
  active:
    - "Fusion remains central in logarithmic CFT, boundary CFT, defect theory, non-invertible symmetries, and topological phases, where semisimplicity assumptions require care."
---

## Summary

**Fusion rules** say which primary families may appear when two primary fields approach each other. They are the representation-theoretic skeleton of the operator product expansion.

If $i,j,k$ label primary families, the fusion rule is written

$$
\mathcal V_i\times \mathcal V_j
=\sum_k N_{ij}{}^k\,\mathcal V_k,
\qquad
N_{ij}{}^k\in\mathbb Z_{\ge0}.
$$

Fusion coefficients are not OPE coefficients. The integer $N_{ij}{}^k$ tells you whether a channel is allowed and how many independent chiral channels exist. The OPE coefficient $C_{ij}{}^k$ is a normalization-dependent number multiplying the corresponding primary family.

For Virasoro minimal models, fusion rules are finite and explicit. They are one of the first places where the phrase “operator algebra” becomes concrete rather than poetic.

## Prerequisites

Read [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), [Null-Vector Differential Equations](/cft-bootstrap/minimal-models-rational-cft/null-vector-differential-equations/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) first.

You should know that a primary field represents a whole Virasoro family: the primary plus its non-null descendants.

## Core idea

The local OPE has the schematic form

$$
\phi_i(z,\bar z)\phi_j(0)
\sim
\sum_k C_{ij}{}^k
z^{h_k-h_i-h_j}\bar z^{\bar h_k-\bar h_i-\bar h_j}
\left(\phi_k(0)+\text{descendants}\right).
$$

The fusion rule keeps only the allowed families:

$$
\phi_i\times\phi_j=\sum_k N_{ij}{}^k\phi_k.
$$

Thus

$$
N_{ij}{}^k\ne0
\quad\Longleftrightarrow\quad
\text{family }k\text{ is allowed in the }i\times j\text{ channel}.
$$

In rational CFT, there are finitely many primary families, and the fusion rules form a finite associative algebra. This is the small algebraic core behind many exact computations in two-dimensional CFT.

## Fusion coefficients versus OPE coefficients

There are three layers of data.

| Layer | Symbol | Meaning |
|---|---:|---|
| Fusion coefficient | $N_{ij}{}^k$ | Integer count of allowed primary-family channels. |
| OPE coefficient | $C_{ij}{}^k$ | Normalization-dependent structure constant. |
| Descendant coefficients | fixed by symmetry | Coefficients of Virasoro descendants once $C_{ij}{}^k$ is fixed. |

For example, in the Ising CFT,

$$
\sigma\times\sigma=\mathbf 1+\epsilon.
$$

With unit-normalized two-point functions, the leading OPE is

$$
\sigma(z,\bar z)\sigma(0)
\sim
\frac{1}{|z|^{1/4}}
\left(\mathbf 1+\frac12 |z|\,\epsilon(0)+\cdots\right).
$$

So $N_{\sigma\sigma}{}^\epsilon=1$, while $C_{\sigma\sigma\epsilon}=1/2$ in this convention.

## Minimal-model formula

For $\mathcal M(p,p')$, primary fields are labeled by

$$
(r,s),
\qquad
1\le r\le p-1,
\qquad
1\le s\le p'-1,
$$

with identification

$$
(r,s)\sim(p-r,p'-s).
$$

The fusion rule is

$$
(r,s)\times(r',s')=\sum_{r''}\sum_{s''}(r'',s''),
$$

where $r''$ runs in steps of two through

$$
|r-r'|+1,\ |r-r'|+3,\ldots,
\min(r+r'-1,2p-r-r'-1),
$$

and $s''$ runs in steps of two through

$$
|s-s'|+1,\ |s-s'|+3,\ldots,
\min(s+s'-1,2p'-s-s'-1).
$$

This is a truncated $SU(2)$-type tensor-product rule in the $r$ direction times the same kind of rule in the $s$ direction. Labels are then reduced using the field identification.

## Ising fusion rules

The Ising CFT is $\mathcal M(3,4)$, with primaries

$$
\mathbf 1,\qquad \sigma,\qquad \epsilon.
$$

The fusion algebra is

$$
\mathbf 1\times\mathcal O=\mathcal O,
$$

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
$$

$$
\sigma\times\epsilon=\sigma,
$$

and

$$
\epsilon\times\epsilon=\mathbf 1.
$$

The energy field $\epsilon$ is a simple current: fusing with it permutes primary families. The spin field $\sigma$ is not a simple current, because $\sigma\times\sigma$ branches into two channels.

In the basis $(\mathbf 1,\sigma,\epsilon)$, the fusion matrix for $\sigma$ is

$$
N_\sigma=
\begin{pmatrix}
0&1&0\\
1&0&1\\
0&1&0
\end{pmatrix},
$$

and

$$
N_\sigma^2=N_{\mathbf 1}+N_\epsilon.
$$

The largest positive eigenvalue of $N_\sigma$ is $\sqrt2$, the quantum dimension of $\sigma$.

## Tricritical Ising examples

The tricritical Ising CFT is $\mathcal M(4,5)$. A convenient representative set is

$$
\mathbf 1,\quad \epsilon,\quad \epsilon',\quad \epsilon'',\quad \sigma,\quad \sigma'.
$$

Selected fusion rules are

$$
\epsilon\times\epsilon=\mathbf 1+\epsilon',
$$

$$
\epsilon\times\epsilon'=\epsilon+\epsilon'',
$$

$$
\sigma\times\sigma=\mathbf 1+\epsilon+\epsilon'+\epsilon'',
$$

and

$$
\sigma'\times\sigma'=\mathbf 1+\epsilon''.
$$

The four channels in $\sigma\times\sigma$ explain why tricritical Ising spin correlators are richer than ordinary Ising spin correlators.

## Associativity and crossing

Fusion is associative:

$$
(\mathcal V_i\times\mathcal V_j)\times\mathcal V_k
=\mathcal V_i\times(\mathcal V_j\times\mathcal V_k).
$$

Equivalently, if $(N_i)_j{}^k=N_{ij}{}^k$, then

$$
N_iN_j=\sum_k N_{ij}{}^kN_k.
$$

This is the algebraic shadow of crossing symmetry. The full crossing problem also needs fusing matrices, conformal blocks, and OPE coefficients, but fusion rules give the channel-counting backbone.

For a four-point function, if $i\times j$ contains only certain families, then the $ij$ OPE channel may contain only the corresponding blocks. Crossing demands agreement with the allowed channels in another pairing.

## Verlinde formula preview

In a rational CFT, torus characters transform under the modular $S$ transformation as

$$
\chi_i(-1/\tau)=\sum_j S_{ij}\chi_j(\tau).
$$

For a semisimple rational CFT, the fusion coefficients are given by the Verlinde formula

$$
N_{ij}{}^k
=\sum_\ell
\frac{S_{i\ell}S_{j\ell}S^*_{k\ell}}{S_{0\ell}},
$$

where $0$ labels the vacuum representation. The remarkable message is

$$
\text{modular transformations of characters}
\quad\Longrightarrow\quad
\text{fusion rules}.
$$

This formula is developed later from the character and modular-invariance point of view.

## Common pitfalls

**Do not call $N_{ij}{}^k$ an OPE coefficient.** It is an integer channel count, not a normalization-dependent structure constant.

**Do not forget descendants.** Fusion rules list primary families. Each allowed family includes descendants.

**Do not double-count identified Kac labels.** In $\mathcal M(p,p')$, the labels $(r,s)$ and $(p-r,p'-s)$ describe the same primary family.

**Do not assume every CFT has finite fusion.** Rational CFTs do. Generic CFTs may have infinitely many primaries or continuous spectra.

**Do not confuse chiral fusion with a full local CFT.** A full CFT must pair left and right sectors consistently and satisfy locality and modular invariance.

## Relations to other pages

This page follows [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/) and [Null-Vector Differential Equations](/cft-bootstrap/minimal-models-rational-cft/null-vector-differential-equations/). It prepares [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and later modular-invariance pages.

Fusion rules also connect back to [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/) and [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/).

## Research status

Fusion rules for Virasoro minimal models and standard rational CFTs are established. The Verlinde formula is a cornerstone of rational CFT and modular tensor category theory.

Active work extends fusion ideas to logarithmic CFT, nonunitary models, non-invertible symmetries, generalized orbifolds, categorical defects, and topological phases. In those settings, one must be careful about semisimplicity, indecomposable modules, and the difference between fusion rings and full operator algebras.

## Exercises

### Exercise 1

Use the minimal-model formula to compute $\sigma\times\sigma$ in the Ising model, with $\sigma=(1,2)$ in $\mathcal M(3,4)$.

<details><summary><strong>Solution</strong></summary>

For the $r$ labels, only $r''=1$ occurs. For the $s$ labels,

$$
s''=1,3.
$$

Thus

$$
(1,2)\times(1,2)=(1,1)+(1,3).
$$

In Ising, $(1,1)=\mathbf 1$ and $(1,3)\sim(2,1)=\epsilon$, so

$$
\sigma\times\sigma=\mathbf 1+\epsilon.
$$

</details>

### Exercise 2

Explain why $\sigma\times\sigma=\mathbf 1+\epsilon$ does not mean $C_{\sigma\sigma\epsilon}=1$.

<details><summary><strong>Solution</strong></summary>

The fusion rule says the $\epsilon$ family is allowed. It does not fix the OPE coefficient. With unit-normalized two-point functions in the usual Ising convention,

$$
C_{\sigma\sigma\epsilon}=\frac12.
$$

Fusion coefficients are integer selection data; OPE coefficients are numerical CFT data.

</details>

### Exercise 3

What is the quantum dimension of the Ising spin field $\sigma$?

<details><summary><strong>Solution</strong></summary>

The fusion matrix

$$
N_\sigma=
\begin{pmatrix}
0&1&0\\
1&0&1\\
0&1&0
\end{pmatrix}
$$

has characteristic polynomial

$$
\lambda(\lambda^2-2).
$$

The largest positive eigenvalue is

$$
d_\sigma=\sqrt2.
$$

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- E. Verlinde, “Fusion rules and modular transformations in 2D conformal field theory,” *Nuclear Physics B* **300** (1988).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989).
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.

## Version history

- 2026-06-30: First polished draft. Added definitions, minimal-model fusion formula, Ising and tricritical examples, Verlinde preview, pitfalls, exercises, and references.
