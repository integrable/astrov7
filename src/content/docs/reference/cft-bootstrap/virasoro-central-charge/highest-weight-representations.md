---
title: "Highest-Weight Representations"
description: "Defines highest-weight representations of the Virasoro algebra and explains how primary states generate descendant towers in two-dimensional CFT."
sidebar:
  label: "Highest-Weight Representations"
  order: 5
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Ginsparg 1988; Belavin, Polyakov, and Zamolodchikov 1984; Cardy 1984"
topics:
  - Virasoro representations
  - highest-weight states
  - primary states
  - descendants
  - radial quantization
canonicalTopics:
  - virasoro-highest-weight-representations
  - primary-states-and-descendants
  - radial-quantization-in-two-dimensional-cft
researchStatus:
  established:
    - "Highest-weight representations are the standard representation-theoretic language for local operator families in two-dimensional CFT."
  active:
    - "Nonunitary, logarithmic, boundary, defect, and extended-chiral-algebra theories can require indecomposable modules, relaxed modules, or additional representation data beyond the simple highest-weight picture."
---

## Summary

A highest-weight representation of the Virasoro algebra begins with a state $|h\rangle$ obeying

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

The state $|h\rangle$ is the chiral state created by a Virasoro-primary field at the origin. Acting with the lowering modes $L_{-n}$ generates descendants:

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad n_i>0.
$$

The level of this descendant is

$$
N=n_1+n_2+\cdots+n_k,
$$

and its $L_0$ eigenvalue is $h+N$.

This page explains how primary fields, highest-weight states, descendants, quasi-primaries, vacuum states, and unitarity constraints fit together. The next page, [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/), treats the freely generated module built from such a state.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/), [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Stress-Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/), and [Virasoro Generators](/cft-bootstrap/virasoro-central-charge/virasoro-generators/).

## Core idea

Radial quantization turns a local operator inserted at the origin into a state on a circle. In a two-dimensional CFT, the holomorphic stress tensor has modes

$$
L_n=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z),
$$

and these modes measure and change the scaling behavior of states. The commutator

$$
[L_0,L_n]=-nL_n
$$

says that $L_{-n}$ raises the $L_0$ eigenvalue by $n$, while $L_n$ lowers it by $n$.

A primary state is therefore a lowest-energy state in radial quantization: no positive mode can lower it further. The rest of the conformal family is obtained by acting with negative modes. This is the representation-theoretic version of the OPE statement that derivatives and stress-tensor descendants are fixed once a primary operator is known.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A highest-weight state at level zero generates descendant states by acting with negative Virasoro modes.](/figures/cft-bootstrap/highest-weight-descendant-tower.svg)

<figcaption>

A Virasoro highest-weight representation is graded by $L_0$. The primary state $|h\rangle$ sits at level $0$; descendants at level $N$ have eigenvalue $h+N$.

</figcaption>
</figure>

## Setup and conventions

We use the Virasoro algebra

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The antiholomorphic copy is

$$
[\bar L_m,\bar L_n]
=
(m-n)\bar L_{m+n}
+
\frac{\bar c}{12}m(m^2-1)\delta_{m+n,0},
$$

and in ordinary local CFTs the two copies commute:

$$
[L_m,\bar L_n]=0.
$$

This page first discusses the holomorphic sector. A full local state is usually labeled by two weights,

$$
(h,\bar h),
\qquad
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

Here $\Delta$ is the scaling dimension and $s$ is the Euclidean spin. In a bosonic local CFT, locality usually requires integer spin for mutually local local operators, though spin fields and fermionic theories require more careful sector language.

## From primary fields to highest-weight states

A holomorphic Virasoro-primary field $\phi_h(w)$ is defined by its stress-tensor OPE

$$
T(z)\phi_h(w)
\sim
\frac{h\phi_h(w)}{(z-w)^2}
+
\frac{\partial\phi_h(w)}{z-w}.
$$

Equivalently, the mode action is

$$
[L_n,\phi_h(w)]
=
\left(w^{n+1}\partial_w+(n+1)h w^n\right)\phi_h(w).
$$

Insert the field at the origin and let it act on the radial-quantization vacuum:

$$
|h\rangle=\phi_h(0)|0\rangle.
$$

For $n>0$, the commutator contains positive powers of $w$ and vanishes at $w=0$. Therefore

$$
L_n|h\rangle=0,
\qquad n>0.
$$

For $n=0$,

$$
L_0|h\rangle=h|h\rangle.
$$

This is the highest-weight condition. The phrase “highest weight” comes from representation theory: the positive modes annihilate the top state, and the negative modes generate the module. In radial quantization, it is more intuitive to think of $|h\rangle$ as the lowest-energy state in its chiral family, because negative modes increase $L_0$.

## Descendants and levels

A descendant is obtained by applying negative modes:

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad n_i>0.
$$

Using

$$
[L_0,L_{-n}]=nL_{-n},
$$

one finds

$$
L_0L_{-n_1}\cdots L_{-n_k}|h\rangle
=
(h+n_1+\cdots+n_k)L_{-n_1}\cdots L_{-n_k}|h\rangle.
$$

The integer

$$
N=n_1+\cdots+n_k
$$

is called the level. The first few levels are

| Level | Typical holomorphic descendants |
|---:|---|
| $0$ | $|h\rangle$ |
| $1$ | $L_{-1}|h\rangle$ |
| $2$ | $L_{-2}|h\rangle$, $L_{-1}^2|h\rangle$ |
| $3$ | $L_{-3}|h\rangle$, $L_{-2}L_{-1}|h\rangle$, $L_{-1}^3|h\rangle$ |

The order of the modes is not arbitrary. Because the Virasoro generators do not commute, one normally chooses an ordered basis with nonincreasing mode numbers:

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad
n_1\ge n_2\ge\cdots\ge n_k\ge 1.
$$

For a generic freely generated module, the number of states at level $N$ is the partition number $p(N)$.

## Primary, descendant, and quasi-primary

There are three closely related words that should not be blurred.

A Virasoro primary is annihilated by all positive Virasoro modes:

$$
L_n|h\rangle=0,
\qquad n>0.
$$

A descendant is obtained by applying negative modes to a primary. Descendants are usually not primary.

A global primary, or quasi-primary, is annihilated only by $L_1$ in the holomorphic global algebra. For fields, quasi-primary means the field transforms covariantly under global Möbius transformations but not necessarily under all local conformal transformations.

The distinction matters because the Virasoro algebra is much larger than the global algebra. A state can be quasi-primary but still be a Virasoro descendant. For example, at level $2$ the combination

$$
\left(L_{-2}-\frac{3}{2(2h+1)}L_{-1}^2\right)|h\rangle
$$

is annihilated by $L_1$, provided $2h+1\ne 0$. It is therefore a quasi-primary descendant, not a new Virasoro primary.

## Full local fields and two chiral modules

A local field $\mathcal O(z,\bar z)$ in a two-dimensional CFT usually carries both holomorphic and antiholomorphic weights:

$$
\mathcal O(z,\bar z):\qquad (h,\bar h).
$$

The state created at the origin obeys

$$
L_0|\mathcal O\rangle=h|\mathcal O\rangle,
\qquad
\bar L_0|\mathcal O\rangle=\bar h|\mathcal O\rangle,
$$

and, if $\mathcal O$ is a Virasoro primary in both sectors,

$$
L_n|\mathcal O\rangle=\bar L_n|\mathcal O\rangle=0,
\qquad n>0.
$$

Descendants are generated independently in the two sectors:

$$
L_{-n_1}\cdots L_{-n_k}\bar L_{-m_1}\cdots \bar L_{-m_\ell}|\mathcal O\rangle.
$$

Their total scaling dimension is

$$
\Delta+N+\bar N,
\qquad
\Delta=h+\bar h.
$$

Their spin is

$$
s+N-\bar N,
\qquad
s=h-\bar h.
$$

This bookkeeping is why two-dimensional conformal families are so powerful: once the primary data are known, the descendants are fixed by symmetry.

## The vacuum representation

The vacuum is special. On the plane, the vacuum is invariant under the global conformal group. In the holomorphic sector this means

$$
L_{-1}|0\rangle=L_0|0\rangle=L_1|0\rangle=0.
$$

It is not merely an ordinary highest-weight state with $h=0$. In an ordinary $h=0$ Verma module, $L_{-1}|0\rangle$ would be a level-one descendant. For the physical plane vacuum, that state vanishes because translations leave the identity operator fixed:

$$
\partial \mathbf 1=0.
$$

The first nontrivial holomorphic descendant of the vacuum is therefore

$$
L_{-2}|0\rangle,
$$

which corresponds to the stress tensor $T(0)$. This is the vacuum-module origin of the familiar fact that the stress tensor has weight $2$.

This detail is small but lethal if ignored. The vacuum character is not the generic $h=0$ Verma character; after quotienting the level-one null state, its generic form begins with descendants made from $L_{-n}$ for $n\ge 2$.

## Inner products and unitarity

In a unitary Euclidean CFT, radial reflection gives the adjoint

$$
L_n^\dagger=L_{-n}.
$$

Normalize a highest-weight state by

$$
\langle h|h\rangle=1.
$$

Then the norm of the level-one descendant is

$$
\|L_{-1}|h\rangle\|^2
=
\langle h|L_1L_{-1}|h\rangle
=
\langle h|[L_1,L_{-1}]|h\rangle
=2h.
$$

Thus unitarity requires

$$
h\ge 0.
$$

At level $2$, in the ordered basis

$$
L_{-2}|h\rangle,
\qquad L_{-1}^2|h\rangle,
$$

the Gram matrix is

$$
G_2=
\begin{pmatrix}
4h+\frac{c}{2} & 6h \\
6h & 4h(2h+1)
\end{pmatrix}.
$$

Positivity of this matrix gives stronger restrictions. At higher levels, positivity becomes the Kac determinant story, which leads to the unitary minimal models for $c<1$ and to broad allowed families for $c\ge 1$.

## How highest-weight data appear in correlators

The state $|h\rangle$ is not just an abstract vector. It corresponds to a local primary operator. Its descendants appear in the OPE. Schematically,

$$
\mathcal O_i(z)\mathcal O_j(0)
\sim
\sum_p C_{ijp}z^{h_p-h_i-h_j}\left(
\phi_p(0)+a_1z\,L_{-1}\phi_p(0)+a_2z^2\,L_{-2}\phi_p(0)+\cdots
\right),
$$

with analogous antiholomorphic factors. The coefficient $C_{ijp}$ is dynamical CFT data, while the descendant coefficients are fixed by conformal symmetry once the normalization convention is chosen.

This is the bridge from representation theory to conformal blocks. A Virasoro block is the contribution of a full Virasoro family, not just one primary operator.

## Common pitfalls

Do not confuse a Virasoro primary with a global primary. Every Virasoro primary is global primary, but many global primaries are Virasoro descendants.

Do not call every operator with a scaling dimension “primary.” Descendant operators also have definite scaling dimensions in a CFT.

Do not treat the vacuum as a generic $h=0$ Verma module. The identity has a level-one null descendant because $\partial\mathbf 1=0$.

Do not forget the antiholomorphic sector. A local CFT state usually carries two modules, one for Virasoro and one for anti-Virasoro.

Do not assume that highest-weight modules are always Hilbert spaces. A Verma module is an algebraic representation. A physical Hilbert space may require quotienting null states, imposing locality, summing sectors, and ensuring positive norm.

## Relations to other pages

- [Virasoro Generators](/cft-bootstrap/virasoro-central-charge/virasoro-generators/) defines the modes whose representation theory is used here.
- [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/) builds the freely generated descendant module from a highest-weight state.
- [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) explains when a descendant becomes highest-weight and must be quotient out.
- [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/) uses these descendant towers to decompose four-point functions.
- [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) uses special highest-weight representations with null states to obtain finite operator spectra.

## Research status

The highest-weight representation theory of the Virasoro algebra is established material and is part of the standard foundation of two-dimensional CFT.

The phrase “highest-weight representation” still hides choices. One must specify whether the module is Verma, irreducible, unitary, logarithmic, extended by a larger chiral algebra, or part of a boundary/defect sector. These choices are not pedantic; they change the spectrum, characters, modular properties, and allowed correlators.

## Exercises

### Exercise: Level-one norm

Assume $L_n^\dagger=L_{-n}$ and $L_n|h\rangle=0$ for $n>0$. Show that

$$
\|L_{-1}|h\rangle\|^2=2h\langle h|h\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Using the adjoint relation,

$$
\|L_{-1}|h\rangle\|^2
=
\langle h|L_1L_{-1}|h\rangle.
$$

Since $L_1|h\rangle=0$,

$$
\langle h|L_1L_{-1}|h\rangle
=
\langle h|[L_1,L_{-1}]|h\rangle.
$$

The Virasoro commutator gives

$$
[L_1,L_{-1}]=2L_0,
$$

so

$$
\|L_{-1}|h\rangle\|^2=2h\langle h|h\rangle.
$$

</details>

### Exercise: Level-two quasi-primary descendant

Find a coefficient $a$ such that

$$
\left(L_{-2}+aL_{-1}^2\right)|h\rangle
$$

is annihilated by $L_1$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
[L_1,L_{-2}]=3L_{-1},
\qquad
[L_1,L_{-1}]=2L_0.
$$

First,

$$
L_1L_{-2}|h\rangle=3L_{-1}|h\rangle.
$$

Next,

$$
L_1L_{-1}^2|h\rangle
=2(2h+1)L_{-1}|h\rangle.
$$

Therefore

$$
L_1\left(L_{-2}+aL_{-1}^2\right)|h\rangle
=
\left(3+2a(2h+1)\right)L_{-1}|h\rangle.
$$

The coefficient is

$$
a=-\frac{3}{2(2h+1)},
$$

provided $2h+1\ne 0$.

</details>

### Exercise: Vacuum descendant

Explain why $L_{-1}|0\rangle=0$ in the plane vacuum module.

<details>
<summary><strong>Solution</strong></summary>

The plane vacuum corresponds to the identity operator:

$$
|0\rangle=\mathbf 1(0)|0\rangle.
$$

The mode $L_{-1}$ generates translations, so acting on a local field it gives a derivative:

$$
[L_{-1},\mathcal O(0)]=\partial\mathcal O(0).
$$

For the identity,

$$
\partial\mathbf 1=0.
$$

Therefore the level-one vacuum descendant vanishes:

$$
L_{-1}|0\rangle=0.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, *Applied Conformal Field Theory*, Les Houches lectures, 1988.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* 241, 333–380, 1984.
- J. L. Cardy, “Conformal invariance and surface critical behavior,” *Nuclear Physics B* 240, 514–532, 1984.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996.

## Version history

- 2026-06-28: First polished draft. Defines Virasoro highest-weight states, descendants, quasi-primaries, vacuum module subtleties, and basic unitarity checks.
