---
title: "Minimal Models and the Ising CFT"
description: "Rational Virasoro CFTs, Kac tables, null vectors, BPZ equations, fusion rules, and the two-dimensional Ising model as the basic exact CFT laboratory."
sidebar:
  order: 1
---

## Goal

Minimal models are the cleanest nontrivial examples of exact conformal field theories. They are interacting, unitary in an important infinite subseries, completely solvable, and rigid enough that one can see the full CFT logic without handwaving:

$$
\begin{aligned}
&\text{Virasoro symmetry}
\quad\Longrightarrow\quad
\text{degenerate representations}
\\
&\quad\Longrightarrow\quad
\text{finite primary spectrum}
\quad\Longrightarrow\quad
\text{fusion rules and exact correlators}.
\end{aligned}
$$

For AdS/CFT preparation, minimal models are not useful because they are semiclassical holographic CFTs. They are not. Their central charges are small, and the unitary Virasoro minimal models have $c<1$. Rather, they are useful because they are the simplest place where the slogan

$$
\text{CFT} = \text{consistent operator algebra}
$$

becomes mathematically explicit. Minimal models teach three habits that are essential later: classify operators by representations, use null states as dynamical constraints, and regard crossing symmetry as associativity of the OPE.

This page is therefore a bridge between the previous Virasoro module discussion and the next topics: modular invariance, WZW models, Liouville theory, and AdS$_3$/CFT$_2$.

## The basic idea

A generic two-dimensional CFT with Virasoro symmetry has infinitely many primary fields. A **minimal model** is a special Virasoro CFT in which only finitely many irreducible highest-weight representations appear in the spectrum.

The word “minimal” should be understood in a precise representation-theoretic sense. A Virasoro highest-weight representation is generated from a highest-weight state $|h\rangle$ obeying

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

The descendants are obtained by acting with lowering operators:

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad n_i>0.
$$

For generic $c$ and $h$, this Verma module is irreducible after quotienting only by zero-norm states if the theory is unitary. But at special values of $c$ and $h$, some descendant states become new highest-weight states. These are **null states**. A null state is simultaneously a descendant and a highest-weight state. Its descendants form a submodule that must be quotiented out in an irreducible representation.

This is the key mechanism. Null states remove many descendants and impose differential equations on correlation functions. If enough null states are present, the theory becomes exactly solvable.

## Degenerate Virasoro representations

The Virasoro algebra is

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The central charge $c$ labels the algebra. The weight $h$ labels a highest-weight representation. For a fixed $c$, the possible reducible Verma modules occur at special values of $h$ arranged in the **Kac table**.

A convenient parametrization of the minimal models uses two coprime integers

$$
2\leq p<q,
\qquad
(p,q)=1.
$$

The central charge is

$$
\boxed{
 c_{p,q}=1-\frac{6(p-q)^2}{pq}
}
$$

and the degenerate weights are

$$
\boxed{
 h_{r,s}^{(p,q)}
 =
 \frac{(qr-ps)^2-(q-p)^2}{4pq}
}
$$

with

$$
1\leq r\leq p-1,
\qquad
1\leq s\leq q-1.
$$

There is a field identification

$$
(r,s)\sim(p-r,q-s),
$$

so the number of distinct Virasoro primary fields is

$$
\boxed{
N_{p,q}=\frac{(p-1)(q-1)}{2}.
}
$$

This is the first miracle: a nontrivial interacting CFT has finitely many primary fields under the Virasoro algebra.

## The Kac determinant viewpoint

At each descendant level $N$, the Verma module has a Gram matrix of inner products. Its determinant is the **Kac determinant**. Schematically,

$$
\det M_N(c,h)
\propto
\prod_{\substack{r,s\geq 1\\rs\leq N}}
\left(h-h_{r,s}(c)\right)^{P(N-rs)},
$$

where $P(n)$ is the number of integer partitions of $n$.

This formula says that a null vector appears at level $rs$ when

$$
h=h_{r,s}(c).
$$

For the minimal model $\mathcal M(p,q)$, the primary labeled by $(r,s)$ has null states at levels

$$
rs,
\qquad
(p-r)(q-s).
$$

This double degeneracy is why the representation truncates so strongly. Minimal models are not solved by guessing a Lagrangian. They are solved by understanding the representation theory of the symmetry algebra.

## Unitary minimal models

Not every minimal model is unitary. The unitary Virasoro minimal models are exactly the series

$$
\boxed{
\mathcal M(m,m+1),
\qquad m=3,4,5,\ldots
}
$$

with central charge

$$
\boxed{
 c_m=1-\frac{6}{m(m+1)}.
}
$$

The allowed labels are

$$
1\leq r\leq m-1,
\qquad
1\leq s\leq m,
\qquad
(r,s)\sim(m-r,m+1-s),
$$

and the conformal weights are

$$
\boxed{
 h_{r,s}^{(m)}
 =
 \frac{\left((m+1)r-ms\right)^2-1}{4m(m+1)}.
}
$$

The first few unitary minimal models are:

| Model | $c$ | Common statistical interpretation |
|---|---:|---|
| $\mathcal M(3,4)$ | $1/2$ | critical Ising model |
| $\mathcal M(4,5)$ | $7/10$ | tricritical Ising model |
| $\mathcal M(5,6)$ | $4/5$ | three-state Potts model, with an extended symmetry description |

As $m\to\infty$, the central charges approach $1$ from below:

$$
\lim_{m\to\infty}c_m=1.
$$

Thus the unitary minimal models form a discrete sequence accumulating at $c=1$.

## The Ising model as $\mathcal M(3,4)$

The most important minimal model is

$$
\mathcal M(3,4),
\qquad
c=1-\frac{6}{3\cdot 4}=\frac12.
$$

The allowed Kac labels are

$$
1\leq r\leq 2,
\qquad
1\leq s\leq 3,
$$

with identification

$$
(r,s)\sim(3-r,4-s).
$$

So the six raw Kac labels reduce to three independent primaries.

<figure class="doc-figure" style="--figure-width: 34rem; --caption-width: 48rem;">

![The Kac table of the Ising minimal model.](/figures/cft/minimal-models-ising-kac-table.svg)

<figcaption>

The Kac table of $\mathcal M(3,4)$, the critical Ising CFT. The dashed arrows implement the field identification $(r,s)\sim(3-r,4-s)$, leaving three independent Virasoro primaries: $\mathbf 1$, $\sigma$, and $\epsilon$.

</figcaption>
</figure>

The three chiral Virasoro representations have weights

$$
\begin{array}{c|c|c}
\text{label} & \text{name} & h \\
\hline
(1,1)\sim(2,3) & \mathbf 1 & 0 \\
(1,2)\sim(2,2) & \sigma & \frac{1}{16} \\
(1,3)\sim(2,1) & \epsilon & \frac{1}{2}
\end{array}
$$

For the diagonal bosonic Ising CFT, the local scalar primaries pair the same left and right representation:

$$
(h,\bar h)
=
(0,0),
\qquad
\left(\frac{1}{16},\frac{1}{16}\right),
\qquad
\left(\frac{1}{2},\frac{1}{2}\right).
$$

Their scaling dimensions are

$$
\Delta_{\mathbf 1}=0,
\qquad
\Delta_\sigma=h_\sigma+\bar h_\sigma=\frac18,
\qquad
\Delta_\epsilon=h_\epsilon+\bar h_\epsilon=1.
$$

The operator $\sigma$ is the spin operator. The operator $\epsilon$ is the energy operator, or thermal perturbation. The two relevant deformations of the critical Ising CFT are therefore

$$
S_{\rm CFT}
\longrightarrow
S_{\rm CFT}
+
\lambda_\epsilon\int d^2x\,\epsilon(x)
+
\lambda_\sigma\int d^2x\,\sigma(x).
$$

The first moves the system away from the critical temperature. The second turns on a magnetic field.

## Fusion rules

The OPE of primary fields has the general form

$$
\phi_a(z,\bar z)\phi_b(0)
\sim
\sum_c C_{ab}^{\phantom{ab}c}\,
|z|^{\Delta_c-\Delta_a-\Delta_b}
\left(\phi_c(0)+\text{descendants}\right).
$$

In a rational CFT, the first piece of information is not the numerical OPE coefficient $C_{ab}^{\phantom{ab}c}$, but whether a given primary family $c$ is allowed at all. This selection rule is encoded by the fusion algebra

$$
\phi_a\times\phi_b
=
\sum_c N_{ab}^{\phantom{ab}c}\phi_c,
\qquad
N_{ab}^{\phantom{ab}c}\in\mathbb Z_{\geq 0}.
$$

For minimal models, the fusion rules are a truncated version of $SU(2)$ tensor-product rules in the $r$ and $s$ directions. For $\mathcal M(p,q)$,

$$
(r_1,s_1)\times(r_2,s_2)
=
\sum_{r_3}\sum_{s_3}(r_3,s_3),
$$

where $r_3$ runs by steps of $2$ through

$$
|r_1-r_2|+1
\leq r_3\leq
\min(r_1+r_2-1,2p-r_1-r_2-1),
$$

and $s_3$ runs by steps of $2$ through

$$
|s_1-s_2|+1
\leq s_3\leq
\min(s_1+s_2-1,2q-s_1-s_2-1).
$$

After applying the field identification, this gives the fusion algebra of the model.

For the Ising CFT the result is especially simple:

$$
\boxed{
\sigma\times\sigma=\mathbf 1+\epsilon,
\qquad
\sigma\times\epsilon=\sigma,
\qquad
\epsilon\times\epsilon=\mathbf 1.
}
$$

This already encodes a lot of physics. For example, the spin four-point function has two Virasoro conformal-block channels in the $\sigma\times\sigma$ OPE:

$$
\langle\sigma\sigma\sigma\sigma\rangle
\quad\text{contains the intermediate families}\quad
\mathbf 1,\epsilon.
$$

Crossing symmetry then fixes the relative combination of the corresponding conformal blocks up to normalization.

## Null states and BPZ equations

Null vectors do not merely reduce the number of states. They impose differential equations on correlation functions. This is the BPZ mechanism.

Suppose $\phi(z)$ is a holomorphic primary of weight $h$ whose Verma module has a null vector at level $2$:

$$
\left(
L_{-2}
-
\frac{3}{2(2h+1)}L_{-1}^2
\right)|\phi\rangle=0.
$$

Let

$$
F(z;z_1,\ldots,z_n)
=
\left\langle
\phi(z)\prod_{i=1}^n\phi_i(z_i)
\right\rangle
$$

be a holomorphic chiral correlator. The Virasoro Ward identity gives

$$
\left\langle
(L_{-2}\phi)(z)\prod_i\phi_i(z_i)
\right\rangle
=
\sum_i
\left(
\frac{h_i}{(z-z_i)^2}
+
\frac{1}{z-z_i}\partial_{z_i}
\right)F.
$$

Since $L_{-1}$ acts as $\partial_z$, the null-state condition becomes the second-order BPZ equation

$$
\boxed{
\left[
\sum_i
\left(
\frac{h_i}{(z-z_i)^2}
+
\frac{1}{z-z_i}\partial_{z_i}
\right)
-
\frac{3}{2(2h+1)}\partial_z^2
\right]F=0.
}
$$

This is extraordinary. A representation-theoretic statement inside the Hilbert space becomes a differential equation for correlation functions.

In the Ising model, the spin field has

$$
h_\sigma=\frac{1}{16},
$$

so the coefficient is

$$
\frac{3}{2(2h_\sigma+1)}
=
\frac{3}{2(1+1/8)}
=
\frac43.
$$

Thus the chiral Ising spin field obeys the null relation

$$
\left(L_{-2}-\frac43L_{-1}^2\right)|\sigma\rangle=0.
$$

The corresponding BPZ equation determines the chiral conformal blocks of the spin four-point function. The two independent solutions correspond to the two fusion channels

$$
\sigma\times\sigma\to\mathbf 1,
\qquad
\sigma\times\sigma\to\epsilon.
$$

## Minimal models as exact bootstrap solutions

It is tempting to describe minimal models as “special Lagrangians.” That is not the best viewpoint. The deeper description is algebraic.

A minimal model is specified by:

$$
\boxed{
\text{central charge } c,
\quad
\text{finite set of Virasoro primaries},
\quad
\text{fusion rules},
\quad
\text{OPE coefficients consistent with crossing}.
}
$$

The finite set of primaries comes from the Kac table. The allowed intermediate families come from fusion. The conformal blocks obey BPZ equations whenever degenerate fields appear. Crossing symmetry then fixes the remaining constants.

This is the exact version of the modern bootstrap philosophy. In higher-dimensional CFTs, we usually do not have enough symmetry to solve the crossing equations analytically. In minimal models, Virasoro symmetry and null states make the bootstrap finite-dimensional enough to solve exactly.

## Characters and rationality

A chiral Virasoro representation has a character

$$
\chi(\tau)
=
\operatorname{Tr}_{\mathcal H_h}
Q^{L_0-c/24},
\qquad
Q=e^{2\pi i\tau}.
$$

For a minimal model, the irreducible characters are finite in number. One convenient formula is

$$
\chi_{r,s}^{(p,q)}(\tau)
=
\frac{1}{\eta(\tau)}
\sum_{n\in\mathbb Z}
\left[
Q^{\frac{(2pqn+qr-ps)^2}{4pq}}
-
Q^{\frac{(2pqn+qr+ps)^2}{4pq}}
\right],
$$

where $\eta(\tau)$ is the Dedekind eta function.

The torus partition function is built by pairing holomorphic and antiholomorphic characters. The simplest diagonal invariant is

$$
Z_{p,q}^{\rm diag}(\tau,\bar\tau)
=
\sum_{(r,s)\in\mathcal K_{p,q}/\sim}
\chi_{r,s}^{(p,q)}(\tau)\,
\overline{\chi_{r,s}^{(p,q)}(\tau)}.
$$

Here $\mathcal K_{p,q}/\sim$ means the Kac table after the identification $(r,s)\sim(p-r,q-s)$.

This is where minimal models connect directly to modular invariance, the next major topic. Rationality means that the characters transform among themselves under modular transformations:

$$
\tau\mapsto -\frac{1}{\tau},
\qquad
\tau\mapsto \tau+1.
$$

Thus modular invariance becomes a finite-dimensional matrix problem. This is one reason minimal models are so powerful.

## The Ising CFT data package

For quick reference, the diagonal critical Ising CFT has:

$$
\boxed{c=\bar c=\frac12.}
$$

The local scalar primary spectrum is

$$
\begin{array}{c|c|c|c}
\text{field} & (h,\bar h) & \Delta & \text{physical role} \\
\hline
\mathbf 1 & (0,0) & 0 & \text{identity} \\
\sigma & \left(\frac{1}{16},\frac{1}{16}\right) & \frac18 & \text{spin operator} \\
\epsilon & \left(\frac12,\frac12\right) & 1 & \text{energy operator}
\end{array}
$$

The fusion algebra is

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
\qquad
\sigma\times\epsilon=\sigma,
\qquad
\epsilon\times\epsilon=\mathbf 1.
$$

The relevant scalar deformations are

$$
\Delta_\sigma=\frac18<2,
\qquad
\Delta_\epsilon=1<2.
$$

The thermal exponent follows from the RG eigenvalue

$$
y_t=2-\Delta_\epsilon=1,
$$

so

$$
\nu=\frac{1}{y_t}=1.
$$

The magnetic exponent follows from

$$
y_h=2-\Delta_\sigma=\frac{15}{8}.
$$

The spin two-point function at criticality is

$$
\langle\sigma(z,\bar z)\sigma(0)\rangle
\propto
\frac{1}{|z|^{2\Delta_\sigma}}
=
\frac{1}{|z|^{1/4}}.
$$

This reproduces the classic Ising exponent $\eta=1/4$.

## Why this matters for strings and AdS$_3$

Minimal models enter string theory in several ways.

First, they are exact worldsheet CFTs. A string background is specified, perturbatively, by a two-dimensional CFT on the worldsheet. Minimal models provide exact internal CFT factors in nontrivial string compactifications and in noncritical string constructions.

Second, they teach modular invariance. One-loop string amplitudes are torus partition functions, and modular invariance is a consistency condition. Minimal models give finite character systems where this condition can be studied exactly.

Third, they clarify the role of chiral algebras. In AdS$_3$/CFT$_2$, the Virasoro algebra is not optional; it is the asymptotic symmetry algebra of gravity in AdS$_3$. Minimal models show what it means for Virasoro symmetry to be strong enough to solve a theory.

But there is an important warning:

$$
\text{unitary minimal models are not semiclassical Einstein-gravity duals.}
$$

A semiclassical AdS$_3$ gravity dual requires large central charge and a sparse enough low-dimension spectrum. Minimal models have $c<1$ and finitely many Virasoro primaries. They are exact CFT laboratories, not large-$c$ holographic theories.

The point is not that minimal models are holographic. The point is that minimal models are the best simple example of exact CFT consistency. They show, in an explicit solvable setting, how much physics is contained in the operator algebra.

## AdS/CFT checkpoint

The minimal-model lesson for AdS/CFT is this:

$$
\boxed{
\text{A CFT is not primarily a Lagrangian. It is a spectrum and OPE data obeying consistency.}
}
$$

Minimal models realize this principle in its sharpest elementary form. The data are finite, the representation theory is exact, null states become differential equations, fusion rules organize the OPE, and modular invariance constrains the torus spectrum.

Later, in holographic CFTs, the same structural objects reappear in a very different regime:

$$
\begin{array}{c|c}
\text{minimal models} & \text{holographic CFTs} \\
\hline
c<1\text{ unitary series} & c\gg 1\text{ semiclassical regime} \\
\text{finite Virasoro primary set} & \text{infinite single-trace spectrum} \\
\text{BPZ equations} & \text{bulk equations and Witten diagrams} \\
\text{exact fusion rules} & \text{large-}N\text{ OPE organization} \\
\text{modular invariance} & \text{black-hole/Cardy physics in }d=2
\end{array}
$$

The techniques differ, but the conceptual skeleton is the same.

## Exercises

### Exercise 1: Count the primaries

Show that the minimal model $\mathcal M(p,q)$ has

$$
\frac{(p-1)(q-1)}{2}
$$

distinct primary fields.

<details>
<summary><strong>Solution</strong></summary>

The raw Kac table contains labels

$$
1\leq r\leq p-1,
\qquad
1\leq s\leq q-1,
$$

so it has $(p-1)(q-1)$ entries. The field identification

$$
(r,s)\sim(p-r,q-s)
$$

pairs every entry with another entry. There are no fixed points of this identification because a fixed point would require

$$
r=\frac p2,
\qquad
s=\frac q2,
$$

which would require both $p$ and $q$ to be even. But $p$ and $q$ are coprime. Hence every orbit has two elements, so the number of distinct primary fields is

$$
\frac{(p-1)(q-1)}{2}.
$$

</details>

### Exercise 2: Derive the Ising weights

Use

$$
h_{r,s}^{(p,q)}
=
\frac{(qr-ps)^2-(q-p)^2}{4pq}
$$

for $\mathcal M(3,4)$ to compute the weights of the three independent Ising primaries.

<details>
<summary><strong>Solution</strong></summary>

For $p=3$, $q=4$,

$$
h_{r,s}
=
\frac{(4r-3s)^2-1}{48}.
$$

For $(1,1)$,

$$
h_{1,1}
=
\frac{(4-3)^2-1}{48}=0.
$$

For $(1,2)$,

$$
h_{1,2}
=
\frac{(4-6)^2-1}{48}
=
\frac{3}{48}
=
\frac{1}{16}.
$$

For $(1,3)$,

$$
h_{1,3}
=
\frac{(4-9)^2-1}{48}
=
\frac{24}{48}
=
\frac12.
$$

Using the identification $(r,s)\sim(3-r,4-s)$, these are the three independent weights:

$$
0,
\qquad
\frac{1}{16},
\qquad
\frac12.
$$

</details>

### Exercise 3: Recover the Ising critical exponents $\eta$ and $\nu$

The spin operator has scaling dimension $\Delta_\sigma=1/8$, and the energy operator has scaling dimension $\Delta_\epsilon=1$. Show that the Ising exponents $\eta$ and $\nu$ are

$$
\eta=\frac14,
\qquad
\nu=1.
$$

<details>
<summary><strong>Solution</strong></summary>

In $d=2$, the critical spin two-point function behaves as

$$
\langle\sigma(x)\sigma(0)\rangle
\sim
\frac{1}{|x|^{2\Delta_\sigma}}.
$$

In statistical-mechanics notation,

$$
\langle\sigma(x)\sigma(0)\rangle
\sim
\frac{1}{|x|^{d-2+\eta}}.
$$

For $d=2$, this exponent is just $\eta$. Therefore

$$
\eta=2\Delta_\sigma=2\cdot\frac18=\frac14.
$$

The thermal perturbation has RG eigenvalue

$$
y_t=d-\Delta_\epsilon=2-1=1.
$$

The correlation-length exponent is

$$
\nu=\frac{1}{y_t}=1.
$$

</details>

### Exercise 4: Use Ising fusion to identify four-point channels

Using

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
$$

list the possible intermediate Virasoro families in the $s$-channel decomposition of

$$
\langle\sigma(z_1)\sigma(z_2)\sigma(z_3)\sigma(z_4)\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

The $s$-channel first fuses the pair $\sigma(z_1)\sigma(z_2)$. The fusion rule says

$$
\sigma\times\sigma=\mathbf 1+\epsilon.
$$

Therefore the only possible intermediate Virasoro families are

$$
\mathbf 1,
\qquad
\epsilon.
$$

Thus the four-point function decomposes into two chiral conformal blocks in this channel, one identity block and one energy block. The full single-valued local correlator is obtained by pairing holomorphic and antiholomorphic blocks in a crossing-symmetric way.

</details>

### Exercise 5: From a null vector to a BPZ equation

Suppose a primary $\phi(z)$ obeys the level-two null relation

$$
\left(L_{-2}-aL_{-1}^2\right)|\phi\rangle=0.
$$

Show that a chiral correlator

$$
F(z;z_i)=\left\langle\phi(z)\prod_i\phi_i(z_i)\right\rangle
$$

obeys

$$
\left[
\sum_i
\left(
\frac{h_i}{(z-z_i)^2}
+
\frac{1}{z-z_i}\partial_{z_i}
\right)
-a\partial_z^2
\right]F=0.
$$

<details>
<summary><strong>Solution</strong></summary>

The operator $L_{-1}$ acts as translation on a primary insertion, so

$$
\left\langle
(L_{-1}^2\phi)(z)\prod_i\phi_i(z_i)
\right\rangle
=
\partial_z^2F.
$$

For $L_{-2}$, use the Virasoro Ward identity by inserting a contour integral of the stress tensor around $z$ and then deforming the contour around the other insertions. This gives

$$
\left\langle
(L_{-2}\phi)(z)\prod_i\phi_i(z_i)
\right\rangle
=
\sum_i
\left(
\frac{h_i}{(z-z_i)^2}
+
\frac{1}{z-z_i}\partial_{z_i}
\right)F.
$$

The null state has zero correlators, hence

$$
0=
\left\langle
\left[(L_{-2}-aL_{-1}^2)\phi\right](z)
\prod_i\phi_i(z_i)
\right\rangle.
$$

Substituting the two formulas above gives the BPZ equation.

</details>

## Further reading

For the classic detailed treatment, read Di Francesco, Mathieu, and Sénéchal, Chapters 7 and 8 on minimal models, then Chapter 10 on modular invariance and Chapter 12 on the two-dimensional Ising model. For the logic of this course, the important point is not to memorize every Kac-table formula, but to understand how representation theory, OPE associativity, differential equations, and modular consistency combine into an exact solution.
