---
title: "Kac Determinant Preview"
description: "Introduces the Virasoro Gram determinant, how its zeros detect singular vectors, and why it leads to the Kac table and minimal-model unitarity constraints."
sidebar:
  label: "Kac Determinant Preview"
  order: 8
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997, Chs. 7–8; Kac 1979; Friedan–Qiu–Shenker 1984; Ginsparg 1988"
topics:
  - two-dimensional CFT
  - Virasoro algebra
  - Kac determinant
  - Verma modules
  - singular vectors
  - minimal models
canonicalTopics:
  - kac-determinant
  - virasoro-gram-matrix
  - kac-table
  - minimal-model-unitarity
researchStatus:
  established:
    - "The Kac determinant formula is the standard tool for locating reducible Virasoro Verma modules and singular vectors."
    - "Together with positivity and embedding-structure arguments, it underlies the classification of unitary Virasoro minimal-model representations."
  active:
    - "Extensions to logarithmic, nonsemisimple, superconformal, W-algebra, affine, and deformed Virasoro settings require modified determinant and module-structure technology."
---

## Summary

The **Kac determinant** is the determinant of the Virasoro Gram matrix at fixed descendant level. It answers a brutally practical question:

> At which values of $c$ and $h$ does a Verma module contain a singular vector?

For the Verma module $V(c,h)$, let $M_N(c,h)$ be the Gram matrix of inner products among all level-$N$ descendants. The Kac determinant formula says, up to a nonzero normalization constant,

$$
\det M_N(c,h)=A_N
\prod_{\substack{r,s\ge 1\\ rs\le N}}
\bigl(h-h_{r,s}(c)\bigr)^{p(N-rs)}.
$$

Here $p(n)$ is the partition number, with $p(0)=1$. A zero of this determinant means that some linear combination of descendants at level $N$ has zero norm. When the first zero occurs at level $rs$, the corresponding state is a singular vector and generates a null submodule.

This page is a preview. It explains what the determinant says and why it matters, without proving the full formula. The complete minimal-model story comes later, where the Kac determinant becomes the entrance to Kac tables, null-vector equations, fusion rules, and modular-invariant spectra.

## Prerequisites

You should know [Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/), [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/), and [Null States](/cft-bootstrap/virasoro-central-charge/null-states/). You should also be comfortable using $L_n^\dagger=L_{-n}$ in radial quantization.

The Virasoro convention is

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

## Core idea

A Verma module is generated freely, but a physical irreducible module may not be. The difference is measured by the Gram matrix.

At level $N$, choose a partition basis

$$
|\lambda\rangle=L_{-\lambda_1}\cdots L_{-\lambda_k}|h\rangle,
\qquad
\lambda_1+\cdots+\lambda_k=N.
$$

The Gram matrix is

$$
(M_N)_{\lambda\mu}=\langle \lambda|\mu\rangle.
$$

If $\det M_N(c,h)\ne 0$, then no nonzero level-$N$ descendant has zero inner product with all level-$N$ descendants. If $\det M_N(c,h)=0$, the level-$N$ Gram form is degenerate. This is the first signal that the Verma module may have a singular vector.

<figure class="doc-figure" style="--figure-width: 42rem;">

![The Kac determinant turns level-by-level Gram matrices into a map of singular vectors and representation constraints.](/figures/cft-bootstrap/kac-determinant-flow.svg)

<figcaption>

The Kac determinant organizes Virasoro representation theory level by level. A vanishing Gram determinant detects degenerate directions; primitive zeros correspond to singular vectors; quotienting their submodules produces irreducible representations; positivity of all level Gram matrices imposes unitarity constraints.

</figcaption>
</figure>

The determinant is useful because it factorizes completely. Instead of computing infinitely many Gram matrices by hand, the Kac formula tells us where reducibility can occur.

## Setup and conventions

The highest-weight state obeys

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0,
\qquad
\langle h|h\rangle=1.
$$

A level-$N$ descendant basis is indexed by integer partitions of $N$. The first few levels are

| Level | Partition basis |
|---:|---|
| 0 | $|h\rangle$ |
| 1 | $L_{-1}|h\rangle$ |
| 2 | $L_{-2}|h\rangle$, $L_{-1}^2|h\rangle$ |
| 3 | $L_{-3}|h\rangle$, $L_{-2}L_{-1}|h\rangle$, $L_{-1}^3|h\rangle$ |

The level-$N$ Gram matrix is a $p(N)\times p(N)$ matrix. Its determinant is a polynomial in $h$ and $c$.

The determinant depends on the normalization of the basis, but its zero locus does not. This is why the Kac determinant is usually stated only up to a nonzero factor $A_N$.

## Low-level checks

The first levels show the mechanism before the general formula appears.

At level one,

$$
M_1=(2h),
\qquad
\det M_1=2h.
$$

The determinant vanishes at $h=0$, giving the singular vector $L_{-1}|0\rangle$.

At level two, in the basis

$$
L_{-2}|h\rangle,
\qquad
L_{-1}^2|h\rangle,
$$

the Gram matrix is

$$
M_2=
\begin{pmatrix}
4h+\frac c2 & 6h\\
6h & 4h(2h+1)
\end{pmatrix}.
$$

Therefore

$$
\det M_2
=4h\left(8h^2+(c-5)h+\frac c2\right).
$$

Up to an overall nonzero factor, the zeros are

$$
h=0,
\qquad
16h^2+2(c-5)h+c=0.
$$

The first zero is the descendant of the level-one null state in the $h=0$ module. The quadratic factor gives the two primitive level-two singular vectors, usually labeled $h_{1,2}(c)$ and $h_{2,1}(c)$.

This is the local logic of the whole determinant formula: lower-level singular vectors contribute descendants at higher levels, while new primitive singular vectors first appear when $N=rs$ for some positive integers $r,s$.

## The Kac parameterization

A convenient way to write the determinant zeros is to introduce a parameter $t$ such that

$$
c(t)=13-6\left(t+\frac{1}{t}\right).
$$

Then

$$
h_{r,s}(t)=\frac{(rt-s)^2-(t-1)^2}{4t},
\qquad
r,s=1,2,3,\ldots.
$$

The symmetry $t\leftrightarrow t^{-1}$ exchanges $r$ and $s$. The same value of $c$ can therefore be described in two equivalent ways.

With this notation, the determinant formula is

$$
\det M_N(c,h)=A_N
\prod_{\substack{r,s\ge1\\rs\le N}}
\left(h-h_{r,s}(c)\right)^{p(N-rs)}.
$$

The exponent $p(N-rs)$ has a simple representation-theoretic meaning. If a singular vector first appears at level $rs$, then its descendants at level $N$ are obtained by acting with all negative-mode monomials of total level $N-rs$. The number of those monomials is $p(N-rs)$.

So the determinant does not merely say where something goes wrong. It also counts how many descendant null directions are forced at each higher level.

## How to read the determinant

The factor $h-h_{r,s}(c)$ tells you that a primitive singular vector may appear at level

$$
N=rs.
$$

For example:

| Root | First possible singular level | Interpretation |
|---|---:|---|
| $h_{1,1}(c)=0$ | 1 | The identity-type level-one null. |
| $h_{1,2}(c)$ | 2 | One family of level-two degenerate fields. |
| $h_{2,1}(c)$ | 2 | The other family of level-two degenerate fields. |
| $h_{1,3}(c)$ | 3 | A level-three degenerate family. |
| $h_{3,1}(c)$ | 3 | The reflected level-three family. |
| $h_{2,2}(c)$ | 4 | A level-four degenerate family. |

When multiple roots coincide, the module can contain a more intricate pattern of nested singular vectors. Minimal models are built precisely in this non-generic world.

:::caution[Primitive zero versus inherited zero]
A zero of $\det M_N$ does not automatically mean that a new singular vector first appears at level $N$. It may be a descendant of a lower-level singular vector. The first appearance is controlled by the smallest $rs$ for which $h=h_{r,s}(c)$.
:::

## The Kac table

For rational values of $t$, many Kac weights repeat. Write

$$
t=\frac{p}{p'},
\qquad
p,p'\text{ coprime positive integers}.
$$

Then

$$
c=1-6\frac{(p-p')^2}{pp'},
$$

and

$$
h_{r,s}
=\frac{(pr-p's)^2-(p-p')^2}{4pp'}.
$$

The **Kac table** is the array of weights $h_{r,s}$ in a chosen finite rectangle. For the minimal model usually denoted $M(p,p')$, one takes

$$
1\le r\le p'-1,
\qquad
1\le s\le p-1,
$$

with the identification

$$
(r,s)\sim(p'-r,p-s).
$$

The unitary minimal series is the special case

$$
p=m+1,
\qquad
p'=m,
\qquad
m=3,4,5,\ldots,
$$

so

$$
c_m=1-\frac{6}{m(m+1)}.
$$

The conformal weights are

$$
h_{r,s}^{(m)}
=\frac{\bigl((m+1)r-ms\bigr)^2-1}{4m(m+1)},
\qquad
1\le r\le m-1,
\qquad
1\le s\le m.
$$

For $m=3$, one gets the Ising central charge

$$
c=\frac12,
$$

and the three inequivalent primary weights

$$
0,
\qquad
\frac{1}{16},
\qquad
\frac12.
$$

These correspond to the identity, spin, and energy fields of the Ising CFT.

## Unitarity information

Unitarity requires the inner product on the physical Hilbert space to be positive semidefinite before quotienting and positive definite after quotienting null states. Therefore every Gram matrix must have nonnegative eigenvalues.

The determinant is not the same as the full positivity condition, but it is an extremely strong diagnostic. As $h$ and $c$ vary, determinants at different levels change sign across Kac zeros. Demanding positivity at every level forces severe restrictions.

The classic result is:

| Central charge range | Unitary highest-weight representations |
|---|---|
| $c\ge 1$ | $h\ge0$, with quotienting of possible nulls. |
| $0<c<1$ | Only the discrete minimal-series values $c_m=1-6/[m(m+1)]$ and Kac-table weights $h_{r,s}^{(m)}$. |

This is one of the great surprises of 2D CFT. Below $c=1$, unitarity and Virasoro symmetry do not allow a continuous landscape of theories. They force a discrete staircase.

The determinant is also why the vacuum module is special. Since $h=0$ gives a level-one null state, the physical vacuum representation is not the generic $h=0$ Verma module. Removing the null descendants is necessary for a sensible identity operator.

## Minimal-model preview

Minimal models arise when the spectrum is made from degenerate Virasoro representations that close under fusion. The Kac determinant supplies the representation-theoretic input:

1. It locates degenerate highest weights $h_{r,s}$.
2. It tells at which level the first singular vector appears.
3. It implies null-state differential equations.
4. These equations restrict fusion rules.
5. Finite Kac-table spectra can then close consistently under OPE and modular invariance.

The minimal-model pipeline is therefore

$$
\det M_N=0
\quad\Longrightarrow\quad
\text{singular vectors}
\quad\Longrightarrow\quad
\text{BPZ equations}
\quad\Longrightarrow\quad
\text{fusion rules}
\quad\Longrightarrow\quad
\text{rational CFT data}.
$$

This page stops before the full proof. The later minimal-model chapter explains how these ingredients assemble into the Ising model, tricritical Ising model, and the unitary series.

## What the determinant does not do

The Kac determinant detects reducibility, but it does not by itself give the complete physical CFT.

It does not choose the spectrum. A consistent CFT needs left and right sectors, locality, modular invariance on the torus, and OPE coefficients satisfying crossing.

It does not automatically prove unitarity. Positivity is a condition on all Gram matrices and all physical sectors. The determinant is a powerful part of the argument, but one must still analyze signs and quotient nulls correctly.

It does not replace fusion rules. It locates null vectors; null vectors then imply differential equations; differential equations then constrain fusion.

It also does not describe every interesting 2D CFT. Liouville theory, logarithmic CFTs, WZW models, cosets, superconformal theories, and theories with extended chiral algebras use related but richer representation-theoretic tools.

## Common pitfalls

**Thinking every determinant zero is a new null state.** A determinant zero at level $N$ may come from descendants of a lower-level singular vector.

**Ignoring the exponent.** The power $p(N-rs)$ counts the descendants of a singular vector that contribute null directions at level $N$.

**Treating $t$ as a physical coupling.** The parameter $t$ is a convenient way to label $c$ and $h_{r,s}$. It is not generally a coupling constant of the CFT.

**Forgetting the field identification.** In minimal models, $(r,s)$ and $(p'-r,p-s)$ label the same conformal weight and ultimately the same primary field.

**Using Verma characters for irreducible modules.** Once null submodules are quotient out, the character changes. Minimal-model characters are not generic Verma characters.

**Assuming the determinant fixes OPE coefficients.** It fixes representation degeneracies. OPE coefficients require additional bootstrap or model-specific input.

## Relations to other pages

- [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) explains what the determinant zeros mean as singular vectors and null submodules.
- [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/) defines the level-by-level descendant spaces whose Gram determinants are being computed.
- [Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/) introduces the highest-weight state $|h\rangle$ and descendant tower.
- [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/) turns null vectors into differential equations for correlators.
- [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) develops the finite Kac-table theories.
- [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/) later gives the table as a practical reference.

## Research status

The Kac determinant formula for Virasoro Verma modules is a classical theorem and a standard tool in 2D CFT. Its role in minimal models, BPZ equations, and unitary representation theory is settled.

The active edge is not the formula itself but its generalizations and contexts: super-Virasoro algebras, affine Kac–Moody algebras, $W$-algebras, logarithmic modules, deformed Virasoro algebras, and vertex-operator-algebra representation categories. In those settings, determinant formulas remain important, but the module categories and quotient procedures can be subtler than the simple Verma-module picture presented here.

For the present volume, this page should be used as the representation-theory bridge from Virasoro modules to minimal models.

## Exercises

### Exercise 1: Level-two Gram matrix

Using the Virasoro algebra, compute the level-two Gram matrix in the basis $L_{-2}|h\rangle$, $L_{-1}^2|h\rangle$.

<details><summary><strong>Solution</strong></summary>

The entries are

$$
\langle h|L_2L_{-2}|h\rangle
=\langle h|[L_2,L_{-2}]|h\rangle
=4h+\frac c2.
$$

Next,

$$
\langle h|L_2L_{-1}^2|h\rangle=6h.
$$

Finally,

$$
\langle h|L_1^2L_{-1}^2|h\rangle=4h(2h+1).
$$

Thus

$$
M_2=
\begin{pmatrix}
4h+\frac c2 & 6h\\
6h & 4h(2h+1)
\end{pmatrix}.
$$

</details>

### Exercise 2: Level-two determinant roots

Show that the level-two determinant vanishes when $h=0$ or

$$
16h^2+2(c-5)h+c=0.
$$

<details><summary><strong>Solution</strong></summary>

From the level-two matrix,

$$
\det M_2
=\left(4h+\frac c2\right)4h(2h+1)-(6h)^2.
$$

Factor out $4h$:

$$
\det M_2
=4h\left[(2h+1)\left(4h+\frac c2\right)-9h\right].
$$

The expression in brackets is

$$
8h^2+(c-5)h+\frac c2.
$$

Multiplying by $2$ gives the quadratic

$$
16h^2+2(c-5)h+c.
$$

</details>

### Exercise 3: Kac weights for the Ising model

Use

$$
c=1-6\frac{(p-p')^2}{pp'},
\qquad
h_{r,s}=\frac{(pr-p's)^2-(p-p')^2}{4pp'}
$$

with $(p,p')=(4,3)$ to find the three inequivalent Ising weights.

<details><summary><strong>Solution</strong></summary>

For $(p,p')=(4,3)$,

$$
c=1-6\frac{1}{12}=\frac12.
$$

Take $r=1$ and $s=1,2,3$:

$$
h_{1,1}=\frac{(4-3)^2-1}{48}=0,
$$

$$
h_{1,2}=\frac{(4-6)^2-1}{48}=\frac{3}{48}=\frac{1}{16},
$$

and

$$
h_{1,3}=\frac{(4-9)^2-1}{48}=\frac{24}{48}=\frac12.
$$

The field identification relates these to the other entries in the finite Kac table. The three inequivalent weights are $0$, $1/16$, and $1/2$.

</details>

### Exercise 4: Why the exponent is a partition number

Explain why the factor $h-h_{r,s}$ appears in $\det M_N$ with exponent $p(N-rs)$.

<details><summary><strong>Solution</strong></summary>

If a singular vector first appears at level $rs$, then it generates a submodule. At total level $N$, the descendants of that singular vector are obtained by acting with negative Virasoro modes whose total level is $N-rs$.

The number of independent monomials in negative modes at total level $N-rs$ in a Verma module is the partition number $p(N-rs)$. Hence this many null directions descend from the level-$rs$ singular vector at level $N$, which explains the exponent.

This argument is the representation-theoretic meaning of the determinant factorization. A full proof must also handle linear dependence and normalization carefully.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Chapters 7–8.
- V. G. Kac, “Contravariant form for infinite-dimensional Lie algebras and superalgebras,” Lecture Notes in Physics **94** (1979).
- D. Friedan, Z. Qiu, and S. Shenker, “Conformal invariance, unitarity, and critical exponents in two dimensions,” *Physical Review Letters* **52** (1984).
- D. Friedan, Z. Qiu, and S. Shenker, “Details of the nonunitarity proof for highest weight representations of the Virasoro algebra,” *Communications in Mathematical Physics* **107** (1986).
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- P. Goddard, A. Kent, and D. Olive, “Unitary representations of the Virasoro and super-Virasoro algebras,” *Communications in Mathematical Physics* **103** (1986).

## Version history

- 2026-06-28: First polished draft. Introduced Gram matrices, low-level determinants, the Kac determinant formula, Kac-table parameterization, and the unitarity/minimal-model preview.
