---
title: "Sugawara Construction"
description: "How the stress tensor of a WZW model is built from affine currents, and how this determines the central charge and conformal weights of affine primaries."
sidebar:
  label: "Sugawara Construction"
  order: 4
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Senechal ch. 14; Ginsparg lectures; Knizhnik and Zamolodchikov 1984; standard affine CFT literature."
topics:
  - Sugawara construction
  - affine Lie algebras
  - WZW models
  - central charge
  - current algebra
canonicalTopics:
  - sugawara-construction
  - affine-stress-tensor
  - wzw-central-charge
researchStatus:
  established:
    - "The Sugawara construction gives the stress tensor of a compact simple WZW model as a normal-ordered quadratic expression in affine currents."
  active:
    - "Generalizations with constraints, cosets, superalgebras, logarithmic theories, and nonsemisimple current algebras require additional care beyond the compact simple case."
---

## Summary

The **Sugawara construction** builds a Virasoro stress tensor from affine currents. For a compact simple current algebra with OPE

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w},
$$

the WZW stress tensor is

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z),
$$

in the standard long-root normalization. Here $k$ is the level, $h^\vee$ is the dual Coxeter number, and $\kappa_{ab}$ is the inverse current metric.

This stress tensor makes the currents primary fields of weight one:

$$
T(z)J^a(w)
\sim
\frac{J^a(w)}{(z-w)^2}
+\frac{\partial J^a(w)}{z-w},
$$

and gives the central charge

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

For an affine primary of finite highest weight $\lambda$, the conformal weight is

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}
=\frac{(\lambda,\lambda+2\rho)}{2(k+h^\vee)}.
$$

The construction is one of the main reasons WZW models are exactly solvable: the Virasoro symmetry is not independent data, but is built from the current algebra.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/), and [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/) first.

You should know the current OPE, the meaning of the level $k$, and the convention that long roots have length squared $2$ when using root and weight formulas.

## Core idea

A holomorphic stress tensor should generate conformal transformations. A holomorphic current $J^a(z)$ has weight one, so the product $:J^aJ^b:$ has weight two. The only invariant quadratic expression in the currents is therefore a natural candidate for the stress tensor:

$$
T(z)=A\,\kappa_{ab}:J^aJ^b:(z).
$$

The coefficient $A$ is fixed by demanding that the currents transform as Virasoro primaries of weight one. The answer is not simply $A=1/(2k)$. Quantum normal ordering and the nonabelian current-current singularity shift the denominator from $k$ to

$$
k+h^\vee.
$$

That shift is the main content of the nonabelian Sugawara construction.

The short slogan is

$$
\text{affine currents}
\quad\Longrightarrow\quad
\text{quadratic stress tensor}
\quad\Longrightarrow\quad
\text{Virasoro algebra}.
$$

## Setup and conventions

Let $\mathfrak g$ be compact and simple. We use Hermitian generators and current OPE

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The dual Coxeter number $h^\vee$ is defined by the adjoint quadratic identity

$$
f^{ac}{}_d f^{bd}{}_c=2h^\vee\kappa^{ab}
$$

up to the sign convention for Hermitian versus anti-Hermitian generators. The formulas below assume the convention that produces the standard WZW central charge

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

Normal ordering means subtracting singular terms in the coincident-current product. A useful point-splitting definition is

$$
:J^aJ^b:(w)
=\lim_{z\to w}\left[J^a(z)J^b(w)-\frac{k\kappa^{ab}}{(z-w)^2}\right]
$$

with the understanding that nonabelian composite-operator conventions can differ by total derivatives or contact terms. The stress tensor itself is unambiguous in the WZW model once the current normalization is fixed.

## Determining the coefficient

Start with

$$
T(z)=A\kappa_{ab}:J^aJ^b:(z).
$$

Demand that $T$ generate conformal transformations of the current:

$$
T(z)J^c(w)
\sim
\frac{J^c(w)}{(z-w)^2}
+\frac{\partial J^c(w)}{z-w}.
$$

At a classical or abelian level, contracting one current in $:J^aJ^b:$ with $J^c$ gives a factor proportional to $2Ak$. This would suggest $A=1/(2k)$.

In the nonabelian quantum theory, the simple-pole part of the current-current OPE produces an additional contribution. The adjoint contraction is proportional to the dual Coxeter number $h^\vee$. The net denominator is shifted:

$$
2Ak\quad\longrightarrow\quad 2A(k+h^\vee).
$$

Therefore

$$
A=\frac{1}{2(k+h^\vee)}.
$$

This gives the Sugawara stress tensor

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z).
$$

The same result follows cleanly in modes by defining Virasoro generators

$$
L_n=\frac{1}{2(k+h^\vee)}\sum_m \kappa_{ab}:J^a_{n-m}J^b_m:.
$$

The coefficient is fixed by requiring

$$
[L_m,J^a_n]=-nJ^a_{m+n}.
$$

## Currents have weight one

With the Sugawara stress tensor,

$$
T(z)J^a(w)
\sim
\frac{J^a(w)}{(z-w)^2}
+\frac{\partial J^a(w)}{z-w}.
$$

This is exactly the OPE of a Virasoro primary of weight one. Equivalently, the modes obey

$$
[L_m,J^a_n]=-nJ^a_{m+n}.
$$

In particular,

$$
[L_0,J^a_{-n}]=nJ^a_{-n}.
$$

Thus a negative current mode $J^a_{-n}$ raises the conformal level by $n$. This is why affine descendants are organized naturally by conformal weight.

For the zero modes,

$$
[L_m,J^a_0]=0
\qquad m=0,
$$

and $J^a_0$ acts as the finite Lie algebra on states at the same conformal level.

## Central charge

The stress-tensor OPE has the standard Virasoro form

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w}.
$$

For the Sugawara tensor of a compact simple algebra, the central charge is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

This formula is a useful sanity check in examples.

For $SU(2)_k$,

$$
\dim\mathfrak{su}(2)=3,
\qquad
h^\vee=2,
$$

so

$$
c=\frac{3k}{k+2}.
$$

For $SU(N)_k$,

$$
\dim\mathfrak{su}(N)=N^2-1,
\qquad
h^\vee=N,
$$

so

$$
c=\frac{k(N^2-1)}{k+N}.
$$

For large level,

$$
c\to\dim\mathfrak g.
$$

This matches the intuition that the WZW model becomes weakly curved and resembles $\dim G$ free bosonic degrees of freedom at large $k$.

## Conformal weights of affine primaries

Let $|\lambda\rangle$ be an affine highest-weight state. It is annihilated by positive current modes,

$$
J^a_n|\lambda\rangle=0,
\qquad n>0,
$$

and transforms under the zero modes in a finite-dimensional representation of highest weight $\lambda$.

The Sugawara $L_0$ mode is

$$
L_0=\frac{1}{2(k+h^\vee)}\left(\kappa_{ab}J^a_0J^b_0+2\sum_{n>0}\kappa_{ab}J^a_{-n}J^b_n\right).
$$

On an affine primary state, the positive modes kill the state, so only the finite quadratic Casimir remains:

$$
L_0|\lambda\rangle
=\frac{C_2(\lambda)}{2(k+h^\vee)}|\lambda\rangle.
$$

Therefore

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}.
$$

In long-root normalization,

$$
C_2(\lambda)=(\lambda,\lambda+2\rho),
$$

so

$$
h_\lambda=\frac{(\lambda,\lambda+2\rho)}{2(k+h^\vee)}.
$$

For $SU(2)_k$, a representation of spin $j$ has

$$
C_2(j)=2j(j+1)
$$

in this convention, so

$$
h_j=\frac{j(j+1)}{k+2}.
$$

At level $k=1$, the allowed $SU(2)$ spins are $j=0$ and $j=1/2$, giving

$$
h_0=0,
\qquad
h_{1/2}=\frac14.
$$

## Mode algebra and Virasoro generators

The Sugawara modes are

$$
L_n=\frac{1}{2(k+h^\vee)}\sum_{m\in\mathbb Z}\kappa_{ab}:J^a_{n-m}J^b_m:.
$$

They obey the Virasoro algebra

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

with

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

They also act on currents by

$$
[L_m,J^a_n]=-nJ^a_{m+n}.
$$

This pair of commutators is often the most efficient working definition of the Sugawara construction in radial quantization.

The normal-ordering prescription in $L_n$ places annihilation modes to the right. For affine highest-weight modules, the positive current modes are annihilation modes. The zero modes require a finite-dimensional normal-ordering convention, but the final expression for $L_0$ on primaries is the Casimir formula above.

## Abelian Sugawara construction

For a $U(1)$ current with

$$
J(z)J(w)\sim\frac{k}{(z-w)^2},
$$

the Sugawara tensor is

$$
T(z)=\frac{1}{2k}:J J:(z).
$$

There is no dual Coxeter shift because the algebra is abelian. The central charge is

$$
c=1
$$

for one current.

A field of charge $q$ satisfying

$$
J(z)\Phi_q(w)\sim\frac{q\Phi_q(w)}{z-w}
$$

has Sugawara conformal weight

$$
h_q=\frac{q^2}{2k}
$$

for the current-algebra part of the stress tensor.

In a compact boson, this formula is the chiral momentum contribution to the dimension of a vertex operator. At rational radii, the abelian current algebra can be extended by additional vertex operators, producing rational CFTs.

## Product algebras

If the current algebra is a direct sum of simple and abelian factors,

$$
\widehat{\mathfrak g}_{1,k_1}\oplus\widehat{\mathfrak g}_{2,k_2}\oplus\cdots\oplus U(1)^r,
$$

the Sugawara stress tensor is the sum of the stress tensors of the factors:

$$
T=T_1+T_2+\cdots+T_{U(1)^r}.
$$

The central charge is additive:

$$
c=c_1+c_2+\cdots+r.
$$

This additivity is essential in coset constructions. If a subalgebra $\widehat{\mathfrak h}$ is embedded in $\widehat{\mathfrak g}$, then the coset stress tensor is

$$
T_{\mathfrak g/\mathfrak h}=T_{\mathfrak g}-T_{\mathfrak h},
$$

with central charge

$$
c_{\mathfrak g/\mathfrak h}=c_{\mathfrak g}-c_{\mathfrak h}.
$$

The denominator level for $\mathfrak h$ must include the embedding index. Forgetting this is a classic coset normalization error.

## Relation to WZW models

In a WZW model, the conserved currents come from the left and right group symmetries. The Sugawara construction gives the stress tensor in terms of those currents. This has two major consequences.

First, the conformal symmetry follows from current algebra. One does not need to independently guess the stress tensor.

Second, the conformal data become representation-theoretic. The central charge is fixed by $(\mathfrak g,k)$, and the conformal weights of primary fields are fixed by quadratic Casimirs.

For a compact simple group $G$ at positive integer level $k$, the WZW model has a finite set of integrable affine primaries. Thus the Sugawara construction is one input in the rational-CFT package:

$$
\widehat{\mathfrak g}_k
\quad\Longrightarrow\quad
\{h_\lambda,c,\chi_\lambda,S,N_{\lambda\mu}{}^\nu\}.
$$

## Common pitfalls

**Do not use $1/(2k)$ for nonabelian WZW models.** The correct denominator is $2(k+h^\vee)$ in the standard normalization. The $h^\vee$ shift is a quantum normal-ordering effect.

**Do not confuse level and central charge.** The level is $k$ in the current OPE. The central charge is $c=k\dim\mathfrak g/(k+h^\vee)$ for compact simple WZW models.

**Do not mix Casimir normalizations.** The formula $h_\lambda=C_2(\lambda)/[2(k+h^\vee)]$ assumes a specific definition of $C_2$. If your source writes $h_j=j(j+1)/(k+2)$ for $SU(2)_k$, match to that convention before translating.

**Do not assume every stress tensor in a current-algebra theory is Sugawara.** The WZW stress tensor is Sugawara. Deformed theories, constrained systems, ghosts, and cosets can involve different or subtracted stress tensors.

**Do not forget the antiholomorphic copy.** A full WZW model also has $\bar T(\bar z)$ built from right-moving currents.

**Do not ignore embedding indices in cosets.** The subalgebra level entering $T_{\mathfrak h}$ may be $x_e k$, not $k$.

## Relations to other pages

This page builds on [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/), and [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/).

The next page, [WZW Action](/cft-bootstrap/current-algebras-wzw/wzw-action/), explains how the same current algebra arises from a sigma model with a Wess–Zumino term. [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) uses the weight formula $h_\lambda=C_2(\lambda)/[2(k+h^\vee)]$. [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) uses the subtraction $T_{\mathfrak g}-T_{\mathfrak h}$.

The page also connects backward to [Central Charge](/cft-bootstrap/virasoro-central-charge/central-charge/) and [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/).

## Research status

The Sugawara construction for compact simple affine current algebras is established and standard. It is a basic theorem-level tool in WZW models and rational CFT.

Active research uses and generalizes it in settings where the assumptions change: supergroups, logarithmic current algebras, nonsemisimple categories, constrained systems, coset dualities, boundary and defect current algebra, and chiral algebras arising from higher-dimensional QFT.

## Exercises

### Exercise 1

For $SU(2)_k$, compute the Sugawara central charge.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
\dim\mathfrak{su}(2)=3,
\qquad
h^\vee=2.
$$

Therefore

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}
=\frac{3k}{k+2}.
$$

</details>

### Exercise 2

For $SU(2)_k$, compute the conformal weight of the spin-$j$ affine primary.

<details><summary><strong>Solution</strong></summary>

In the standard convention,

$$
h_j=\frac{j(j+1)}{k+2}.
$$

This follows from

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)},
$$

with $h^\vee=2$ and $C_2(j)=2j(j+1)$ in the long-root convention used for the general formula.

</details>

### Exercise 3

Show that the abelian Sugawara tensor for $J(z)J(w)\sim k/(z-w)^2$ is $T=(2k)^{-1}:JJ:$.

<details><summary><strong>Solution</strong></summary>

Take

$$
T(z)=A:J J:(z).
$$

Contracting one $J$ in $T(z)$ with $J(w)$ gives two identical contributions from the double pole:

$$
T(z)J(w)\sim 2A\frac{k}{(z-w)^2}J(z).
$$

Expanding $J(z)=J(w)+(z-w)\partial J(w)+\cdots$ gives

$$
T(z)J(w)\sim
\frac{2AkJ(w)}{(z-w)^2}+rac{2Ak\partial J(w)}{z-w}.
$$

For $J$ to have weight one, we need $2Ak=1$, so

$$
A=\frac{1}{2k}.
$$

</details>

### Exercise 4

For $SU(3)_1$, compute the central charge.

<details><summary><strong>Solution</strong></summary>

For $SU(3)$,

$$
\dim\mathfrak{su}(3)=8,
\qquad
h^\vee=3.
$$

At level $k=1$,

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}
=\frac{1\cdot8}{1+3}=2.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- V. G. Knizhnik and A. B. Zamolodchikov, “Current algebra and Wess–Zumino model in two dimensions,” *Nuclear Physics B* **247** (1984).
- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).

## Version history

- 2026-06-30: First polished draft. Added Sugawara tensor, coefficient explanation, central charge, affine-primary weights, abelian and product-algebra cases, examples, pitfalls, exercises, and references.
