---
title: "Stress Tensor and the Virasoro Algebra"
description: "The holomorphic stress tensor, conformal Ward identities, the central charge, and the Virasoro algebra in two-dimensional CFT."
sidebar:
  order: 2
---

## Goal

The previous page explained why two-dimensional conformal transformations split into holomorphic and antiholomorphic maps,

$$
z\mapsto f(z),
\qquad
\bar z\mapsto \bar f(\bar z).
$$

This page explains how this local symmetry is represented in a quantum CFT. The central object is the stress tensor. In two dimensions, its holomorphic component is not just one conserved current. It packages infinitely many conserved charges:

$$
L_n=\frac{1}{2\pi i}\oint dz\,z^{n+1}T(z),
\qquad
\bar L_n=\frac{1}{2\pi i}\oint d\bar z\,\bar z^{n+1}\bar T(\bar z).
$$

These charges satisfy the Virasoro algebra,

$$
[L_n,L_m]
=
(n-m)L_{n+m}
+
\frac{c}{12}n(n^2-1)\delta_{n+m,0},
$$

and similarly for the barred sector. The number $c$ is the central charge. It measures the quantum central extension of the classical local conformal algebra.

For AdS/CFT, this page is especially important in two places. In AdS$_3$/CFT$_2$, the Virasoro algebra is the asymptotic symmetry algebra of gravity in AdS$_3$. In string theory, the worldsheet theory is a two-dimensional CFT, and the Virasoro constraints are the local conformal constraints of the string.

## Stress tensor in complex coordinates

Let the Euclidean plane have complex coordinates

$$
z=x^1+i x^2,
\qquad
\bar z=x^1-i x^2,
$$

with derivatives

$$
\partial=\partial_z,
\qquad
\bar\partial=\partial_{\bar z}.
$$

In a two-dimensional conformal field theory, the stress tensor is conserved and, after possible improvement, traceless. In complex coordinates this means, away from operator insertions,

$$
T_{z\bar z}=0,
$$

and conservation becomes

$$
\bar\partial T_{zz}=0,
\qquad
\partial T_{\bar z\bar z}=0.
$$

Thus the two nonzero components split into a holomorphic and an antiholomorphic part. We choose the standard CFT normalization

$$
T(z)=-2\pi T_{zz}(z),
\qquad
\bar T(\bar z)=-2\pi T_{\bar z\bar z}(\bar z).
$$

With this convention,

$$
\bar\partial T(z)=0,
\qquad
\partial \bar T(\bar z)=0,
$$

away from insertions. The phrase “away from insertions” matters. In correlation functions, $T(z)$ has poles when $z$ approaches other operator insertions. Those poles encode the conformal transformation laws of the inserted operators.

A useful way to remember the logic is

$$
\boxed{
\text{conservation} + \text{tracelessness}
\quad\Longrightarrow\quad
T(z)\text{ holomorphic},\quad \bar T(\bar z)\text{ antiholomorphic}.
}
$$

This is the two-dimensional enhancement. In higher dimensions the stress tensor generates finitely many conformal charges. In two dimensions, a holomorphic current has infinitely many Laurent modes.

## The conformal Ward identity

Let

$$
X=\prod_{i=1}^N \phi_i(z_i,\bar z_i)
$$

be a product of primary fields with weights $(h_i,\bar h_i)$. The holomorphic conformal Ward identity is

$$
\boxed{
\left\langle T(z)\prod_{i=1}^N \phi_i(z_i,\bar z_i)\right\rangle
=
\sum_{i=1}^N
\left[
\frac{h_i}{(z-z_i)^2}
+
\frac{1}{z-z_i}\partial_{z_i}
\right]
\left\langle \prod_{i=1}^N \phi_i(z_i,\bar z_i)\right\rangle.
}
$$

Similarly,

$$
\boxed{
\left\langle \bar T(\bar z)\prod_{i=1}^N \phi_i(z_i,\bar z_i)\right\rangle
=
\sum_{i=1}^N
\left[
\frac{\bar h_i}{(\bar z-\bar z_i)^2}
+
\frac{1}{\bar z-\bar z_i}\partial_{\bar z_i}
\right]
\left\langle \prod_{i=1}^N \phi_i(z_i,\bar z_i)\right\rangle.
}
$$

These identities are among the most important formulas in two-dimensional CFT. They say that inserting $T(z)$ into a correlator is equivalent to making an infinitesimal holomorphic conformal transformation of all other insertions.

To see the contour form, take a holomorphic vector field $\epsilon(z)$ and define

$$
Q_\epsilon
=
\frac{1}{2\pi i}\oint_C dz\,\epsilon(z)T(z).
$$

If the contour $C$ surrounds all insertions, then by contour deformation the charge is the sum of residues at the insertion points:

$$
\frac{1}{2\pi i}\oint_C dz\,\epsilon(z)
\left\langle T(z)X\right\rangle
=
\sum_i
\left[
\epsilon(z_i)\partial_{z_i}
+h_i\partial\epsilon(z_i)
\right]
\langle X\rangle.
$$

The local action on one primary field is therefore

$$
\frac{1}{2\pi i}\oint_{z_i} dz\,\epsilon(z)T(z)\phi_i(z_i,\bar z_i)
=
\left[
\epsilon(z_i)\partial_{z_i}+h_i\partial\epsilon(z_i)\right]
\phi_i(z_i,\bar z_i).
$$

This is the same transformation law as on the previous page, up to the usual sign convention between an active variation of the operator and the generator acting on the insertion.

<figure class="doc-figure" style="--figure-width: 43rem; --caption-width: 55rem;">

![Stress-tensor contours and Virasoro modes.](/figures/cft/stress-tensor-virasoro-contour-modes.svg)

<figcaption>

The stress tensor generates conformal transformations by contour integrals. A contour enclosing several insertions can be deformed into small contours around each insertion, so the Ward identity is a residue theorem. Choosing $\epsilon(z)=z^{n+1}$ gives the Virasoro mode $L_n$.

</figcaption>
</figure>

## The OPE of $T$ with a primary field

The Ward identity is equivalently encoded in the operator product expansion

$$
\boxed{
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w}.
}
$$

The symbol $\sim$ means equality up to terms regular as $z\to w$. The antiholomorphic counterpart is

$$
\boxed{
\bar T(\bar z)\phi(w,\bar w)
\sim
\frac{\bar h\phi(w,\bar w)}{(\bar z-\bar w)^2}
+
\frac{\bar\partial\phi(w,\bar w)}{\bar z-\bar w}.
}
$$

This OPE is often the most efficient definition of a primary field in two-dimensional CFT.

The double pole knows the conformal weight. The simple pole knows the derivative descendant. Said differently,

$$
\text{weight} \longleftrightarrow \frac{1}{(z-w)^2},
\qquad
\text{translation} \longleftrightarrow \frac{1}{z-w}.
$$

This simple local formula is the reason two-dimensional CFT computations are so contour-friendly. Once the singular part of an OPE is known, the corresponding charge action follows by residues.

## Virasoro modes

Because $T(z)$ is holomorphic away from insertions, it admits a Laurent expansion on a punctured plane:

$$
\boxed{
T(z)=\sum_{n\in\mathbb Z}L_n z^{-n-2}.
}
$$

The inverse formula is

$$
\boxed{
L_n=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z).
}
$$

Similarly,

$$
\bar T(\bar z)=\sum_{n\in\mathbb Z}\bar L_n\bar z^{-n-2},
$$

with

$$
\bar L_n=\frac{1}{2\pi i}\oint_0 d\bar z\,\bar z^{n+1}\bar T(\bar z).
$$

The power $z^{-n-2}$ appears because $T$ has holomorphic weight $2$. Equivalently, the vector-field mode $\epsilon(z)=z^{n+1}$ pairs naturally with $T(z)$ in the contour charge.

From the $T\phi$ OPE,

$$
[L_n,\phi(w,\bar w)]
=
\frac{1}{2\pi i}\oint_w dz\,z^{n+1}T(z)\phi(w,\bar w),
$$

so

$$
\boxed{
[L_n,\phi(w,\bar w)]
=
\left(w^{n+1}\partial_w+h(n+1)w^n\right)
\phi(w,\bar w).
}
$$

Likewise,

$$
\boxed{
[\bar L_n,\phi(w,\bar w)]
=
\left(\bar w^{n+1}\partial_{\bar w}+\bar h(n+1)\bar w^n\right)
\phi(w,\bar w).
}
$$

For the first few holomorphic modes,

$$
L_{-1}:\quad \partial_w,
$$

$$
L_0:\quad w\partial_w+h,
$$

$$
L_1:\quad w^2\partial_w+2hw.
$$

Thus $L_{-1}$ translates the insertion, $L_0$ measures holomorphic scaling weight, and $L_1$ generates the holomorphic special conformal transformation.

## The $T(z)T(w)$ OPE and the central charge

If $T$ were an ordinary primary field of weight $(2,0)$, its OPE with $T$ would be determined by the primary formula with $h=2$:

$$
T(z)T(w)
\sim
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

Quantum mechanically there is one more allowed singular term proportional to the identity:

$$
\boxed{
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
}
$$

Similarly,

$$
\boxed{
\bar T(\bar z)\bar T(\bar w)
\sim
\frac{\bar c}{2(\bar z-\bar w)^4}
+
\frac{2\bar T(\bar w)}{(\bar z-\bar w)^2}
+
\frac{\bar\partial \bar T(\bar w)}{\bar z-\bar w}.
}
$$

For a parity-invariant unitary CFT one usually has

$$
c=\bar c.
$$

In a theory with a gravitational anomaly, one can have $c\neq \bar c$.

The coefficient $c$ is the central charge. It is not an operator-valued field. It is a number characterizing the CFT. Roughly speaking, it measures the strength of stress-tensor fluctuations and the response of the theory to Weyl transformations. In examples,

| Theory | Holomorphic central charge |
|---|---:|
| one free real boson | $c=1$ |
| one free Majorana fermion | $c=\frac12$ |
| one free Dirac fermion | $c=1$ |
| reparametrization ghosts of the bosonic string | $c=-26$ |

The $T T$ OPE is the local form of the Virasoro algebra. The term $c/2(z-w)^{-4}$ is the local origin of the central extension.

## Deriving the Virasoro algebra

Use

$$
L_n=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z).
$$

The commutator $[L_n,L_m]$ is computed by nesting contours and using the singular part of $T(z)T(w)$. Schematically,

$$
[L_n,L_m]
=
\frac{1}{2\pi i}\oint_0 dw\,w^{m+1}
\operatorname*{Res}_{z=w}
\left[z^{n+1}T(z)T(w)\right].
$$

Now use

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

The $2T(w)/(z-w)^2$ term gives

$$
2(n+1)\frac{1}{2\pi i}\oint_0 dw\,w^{n+m+1}T(w).
$$

The $\partial T(w)/(z-w)$ term gives

$$
\frac{1}{2\pi i}\oint_0 dw\,w^{n+m+2}\partial T(w)
=
-(n+m+2)L_{n+m},
$$

where we integrated by parts. Combining these two noncentral terms gives

$$
\left[2(n+1)-(n+m+2)\right]L_{n+m}
=(n-m)L_{n+m}.
$$

The central term comes from

$$
\frac{c/2}{(z-w)^4}.
$$

The residue of $z^{n+1}/(z-w)^4$ at $z=w$ is

$$
\frac{1}{3!}\partial_w^3 w^{n+1}
=
\frac{(n+1)n(n-1)}{6}w^{n-2}.
$$

Therefore the central contribution is

$$
\frac{c}{2}\frac{n(n^2-1)}{6}
\frac{1}{2\pi i}\oint_0 dw\,w^{n+m-1}
=
\frac{c}{12}n(n^2-1)\delta_{n+m,0}.
$$

Thus

$$
\boxed{
[L_n,L_m]
=
(n-m)L_{n+m}
+
\frac{c}{12}n(n^2-1)\delta_{n+m,0}.
}
$$

The barred sector gives

$$
\boxed{
[\bar L_n,\bar L_m]
=
(n-m)\bar L_{n+m}
+
\frac{\bar c}{12}n(n^2-1)\delta_{n+m,0}.
}
$$

The two sectors commute:

$$
\boxed{
[L_n,\bar L_m]=0.
}
$$

The classical Witt algebra is recovered by setting $c=0$ and replacing quantum commutators by classical vector-field commutators.

## The global conformal subalgebra

The modes

$$
L_{-1},\quad L_0,\quad L_1
$$

generate the global holomorphic conformal transformations. They close into $\mathfrak{sl}(2)$:

$$
[L_0,L_{-1}]=L_{-1},
$$

$$
[L_0,L_1]=-L_1,
$$

$$
[L_1,L_{-1}]=2L_0.
$$

The central term vanishes for these modes because

$$
n(n^2-1)=0
\qquad
\text{for } n=-1,0,1.
$$

Thus the central extension affects local conformal transformations but not the global $SL(2)$ subgroup.

On the plane, the conformal vacuum is invariant under global conformal transformations:

$$
L_{-1}|0\rangle=L_0|0\rangle=L_1|0\rangle=0,
$$

and similarly

$$
\bar L_{-1}|0\rangle=\bar L_0|0\rangle=\bar L_1|0\rangle=0.
$$

In fact, regularity of $T(z)|0\rangle$ at $z=0$ gives the stronger condition

$$
L_n|0\rangle=0
\qquad
\text{for } n\ge -1,
$$

with the analogous barred statement.

## Primary states and descendants

Let a primary operator $\phi(0,0)$ create a state by radial quantization:

$$
|h,\bar h\rangle=\phi(0,0)|0\rangle.
$$

The $T\phi$ OPE implies

$$
L_0|h,\bar h\rangle=h|h,\bar h\rangle,
$$

$$
\bar L_0|h,\bar h\rangle=\bar h|h,\bar h\rangle,
$$

and

$$
L_n|h,\bar h\rangle=0,
\qquad
\bar L_n|h,\bar h\rangle=0,
\qquad
n>0.
$$

The negative modes create descendants:

$$
L_{-n}|h,\bar h\rangle,
\qquad
\bar L_{-n}|h,\bar h\rangle,
\qquad
n>0.
$$

For example,

$$
L_{-1}|h,\bar h\rangle
\leftrightarrow
\partial\phi(0,0),
$$

and

$$
\bar L_{-1}|h,\bar h\rangle
\leftrightarrow
\bar\partial\phi(0,0).
$$

This is the beginning of Virasoro representation theory. The next page develops highest-weight modules, Verma modules, null states, and the unitarity constraints that make two-dimensional CFT exactly solvable.

## The Schwarzian derivative and why $T$ is not quite primary

A primary field of holomorphic weight $2$ would transform under $z\mapsto w$ as

$$
\phi_w(w)=\left(\frac{dz}{dw}\right)^2\phi_z(z).
$$

The stress tensor almost does this, but not quite. Its transformation law is

$$
\boxed{
T_w(w)
=
\left(\frac{dz}{dw}\right)^2T_z(z)
+
\frac{c}{12}\{z,w\}.
}
$$

Here

$$
\boxed{
\{z,w\}
=
\frac{z'''(w)}{z'(w)}
-
\frac{3}{2}
\left(\frac{z''(w)}{z'(w)}\right)^2
}
$$

is the Schwarzian derivative. The anomalous Schwarzian term is another expression of the central charge.

For Möbius transformations, the Schwarzian vanishes:

$$
\left\{\frac{az+b}{cz+d},z\right\}=0.
$$

Therefore $T$ transforms as a genuine weight-two field under global conformal transformations. It fails to be primary only under general local conformal transformations.

A famous example is the map from the plane to the cylinder:

$$
z=e^w,
\qquad
w=\tau+i\sigma.
$$

For this map,

$$
\{z,w\}=-\frac12.
$$

If the plane vacuum has

$$
\langle T_z(z)\rangle=0,
$$

then on the cylinder

$$
\langle T_w(w)\rangle=-\frac{c}{24}.
$$

This is the Casimir energy of the two-dimensional CFT on the cylinder. It will reappear in modular invariance, the Cardy formula, and AdS$_3$ black-hole physics.

## Physical meaning of the central charge

The central charge $c$ has several equivalent interpretations.

First, it normalizes the stress-tensor two-point function. From the $TT$ OPE,

$$
\langle T(z)T(0)\rangle=\frac{c/2}{z^4}
$$

on the plane, assuming $\langle T\rangle=0$.

Second, it controls the Weyl anomaly. On a curved two-dimensional background,

$$
\langle T^\mu{}_\mu\rangle
=-\frac{c}{12}R
$$

up to conventions for the normalization of $T_{\mu\nu}$ and the curvature. Many references instead write this as $\langle T^\mu{}_\mu\rangle=-\frac{c}{24\pi}R$, depending on whether factors of $2\pi$ are absorbed into $T$.

Third, it controls the universal cylinder Casimir energy:

$$
E_0=-\frac{c}{12}
$$

for a unit-radius spatial circle when both holomorphic and antiholomorphic sectors contribute equally. In holomorphic language this is the shift

$$
L_0\mapsto L_0-\frac{c}{24}.
$$

Fourth, in AdS$_3$/CFT$_2$, the Brown-Henneaux central charge is

$$
c=\frac{3\ell_{\mathrm{AdS}}}{2G_N},
$$

so a large central charge corresponds to weakly coupled semiclassical gravity.

The central charge is therefore not a decorative constant. It is one of the main bridges between symmetry, anomaly, density of states, and holographic gravity.

## Common pitfalls

One common mistake is to say that $T$ is a primary field. It is better to say: $T$ is a quasi-primary field of weight $(2,0)$, but unless $c=0$, it is not primary under arbitrary local conformal maps because of the Schwarzian derivative.

Another mistake is to forget that the Ward identity is a statement about singularities. The formula

$$
\bar\partial T(z)=0
$$

is true away from insertions. In correlators, the singularities at insertion points become contact terms.

A third mistake is to treat the central charge as a property of only one field. The central charge is a property of the full CFT. It adds over decoupled sectors:

$$
c_{\mathrm{total}}=c_1+c_2
$$

for a tensor product of independent CFTs.

A fourth mistake is to ignore barred modes. Many chiral computations use only $T(z)$ and $L_n$, but a full local two-dimensional CFT usually has both holomorphic and antiholomorphic sectors.

## Summary

The holomorphic stress tensor generates local conformal transformations:

$$
Q_\epsilon=\frac{1}{2\pi i}\oint dz\,\epsilon(z)T(z).
$$

Its OPE with a primary field is

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w}.
$$

Its self-OPE is

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

The Virasoro modes are

$$
L_n=\frac{1}{2\pi i}\oint dz\,z^{n+1}T(z),
$$

with algebra

$$
[L_n,L_m]
=
(n-m)L_{n+m}
+
\frac{c}{12}n(n^2-1)\delta_{n+m,0}.
$$

The global subalgebra $L_{-1},L_0,L_1$ has no central term. The central charge appears only in genuinely local conformal transformations and controls stress-tensor fluctuations, Weyl anomaly, cylinder Casimir energy, Cardy growth, and the semiclassical scale of AdS$_3$ gravity.

## Exercises

### Exercise 1: Ward identity from the $T\phi$ OPE

Let $\phi(w,\bar w)$ be a primary field of holomorphic weight $h$. Starting from

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w},
$$

show that

$$
\frac{1}{2\pi i}\oint_w dz\,\epsilon(z)T(z)\phi(w,\bar w)
=
\left[\epsilon(w)\partial+h\partial\epsilon(w)\right]\phi(w,\bar w).
$$

<details><summary><strong>Solution</strong></summary>

Insert the OPE into the contour integral:

$$
\frac{1}{2\pi i}\oint_w dz\,\epsilon(z)T(z)\phi(w,\bar w)
=
\frac{1}{2\pi i}\oint_w dz\,\epsilon(z)
\left[
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w}
\right].
$$

The simple pole gives

$$
\frac{1}{2\pi i}\oint_w dz\,\frac{\epsilon(z)}{z-w}\partial\phi(w,\bar w)
=
\epsilon(w)\partial\phi(w,\bar w).
$$

For the double pole, use Cauchy's derivative formula:

$$
\frac{1}{2\pi i}\oint_w dz\,\frac{\epsilon(z)}{(z-w)^2}
=\partial\epsilon(w).
$$

Thus

$$
\frac{1}{2\pi i}\oint_w dz\,\epsilon(z)T(z)\phi(w,\bar w)
=
\left[\epsilon(w)\partial+h\partial\epsilon(w)\right]\phi(w,\bar w).
$$

</details>

### Exercise 2: Action of $L_n$ on a primary field

Use

$$
L_n=\frac{1}{2\pi i}\oint dz\,z^{n+1}T(z)
$$

and the $T\phi$ OPE to prove

$$
[L_n,\phi(w,\bar w)]
=
\left(w^{n+1}\partial+h(n+1)w^n\right)\phi(w,\bar w).
$$

Then compute the action of $L_{-1}$, $L_0$, and $L_1$.

<details><summary><strong>Solution</strong></summary>

Set

$$
\epsilon(z)=z^{n+1}.
$$

Using the result of Exercise 1,

$$
[L_n,\phi(w,\bar w)]
=
\left[\epsilon(w)\partial+h\partial\epsilon(w)\right]\phi(w,\bar w).
$$

Since

$$
\epsilon(w)=w^{n+1},
\qquad
\partial\epsilon(w)=(n+1)w^n,
$$

we obtain

$$
[L_n,\phi(w,\bar w)]
=
\left(w^{n+1}\partial+h(n+1)w^n\right)\phi(w,\bar w).
$$

For $n=-1$,

$$
[L_{-1},\phi]=\partial\phi.
$$

For $n=0$,

$$
[L_0,\phi]=(w\partial+h)\phi.
$$

For $n=1$,

$$
[L_1,\phi]=(w^2\partial+2hw)\phi.
$$

These are the holomorphic translation, dilatation, and special conformal actions.

</details>

### Exercise 3: The central term in the Virasoro algebra

Starting from

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w},
$$

show that the central contribution to $[L_n,L_m]$ is

$$
\frac{c}{12}n(n^2-1)\delta_{n+m,0}.
$$

<details><summary><strong>Solution</strong></summary>

The central contribution is obtained from

$$
\frac{1}{2\pi i}\oint_0 dw\,w^{m+1}
\operatorname*{Res}_{z=w}
\left[z^{n+1}\frac{c/2}{(z-w)^4}\right].
$$

The residue formula gives

$$
\operatorname*{Res}_{z=w}\frac{z^{n+1}}{(z-w)^4}
=
\frac{1}{3!}\partial_w^3 w^{n+1}.
$$

Now

$$
\partial_w^3 w^{n+1}
=(n+1)n(n-1)w^{n-2}
=n(n^2-1)w^{n-2}.
$$

Therefore the central contribution is

$$
\frac{c}{2}\frac{n(n^2-1)}{6}
\frac{1}{2\pi i}\oint_0 dw\,w^{m+1}w^{n-2}.
$$

The integral is

$$
\frac{1}{2\pi i}\oint_0 dw\,w^{n+m-1}=\delta_{n+m,0}.
$$

Thus the central term is

$$
\frac{c}{12}n(n^2-1)\delta_{n+m,0}.
$$

</details>

### Exercise 4: The noncentral part of the Virasoro algebra

Use the same $TT$ OPE to show that the noncentral part of $[L_n,L_m]$ is

$$
(n-m)L_{n+m}.
$$

<details><summary><strong>Solution</strong></summary>

The noncentral singular terms are

$$
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

The double pole gives

$$
2\frac{1}{2\pi i}\oint_0 dw\,w^{m+1}
\operatorname*{Res}_{z=w}\frac{z^{n+1}T(w)}{(z-w)^2}.
$$

Since

$$
\operatorname*{Res}_{z=w}\frac{z^{n+1}}{(z-w)^2}=(n+1)w^n,
$$

this contribution is

$$
2(n+1)\frac{1}{2\pi i}\oint_0 dw\,w^{n+m+1}T(w)
=2(n+1)L_{n+m}.
$$

The simple pole gives

$$
\frac{1}{2\pi i}\oint_0 dw\,w^{n+m+2}\partial T(w).
$$

Integrating by parts on the contour,

$$
\oint dw\,w^{n+m+2}\partial T(w)
=-(n+m+2)\oint dw\,w^{n+m+1}T(w).
$$

Thus the simple-pole contribution is

$$
-(n+m+2)L_{n+m}.
$$

Combining both pieces,

$$
2(n+1)L_{n+m}-(n+m+2)L_{n+m}
=(n-m)L_{n+m}.
$$

</details>

### Exercise 5: The global subalgebra has no central term

Show that the central term in

$$
[L_n,L_m]
=
(n-m)L_{n+m}
+
\frac{c}{12}n(n^2-1)\delta_{n+m,0}
$$

vanishes for $n,m\in\{-1,0,1\}$. Then verify

$$
[L_0,L_{-1}]=L_{-1},
\qquad
[L_0,L_1]=-L_1,
\qquad
[L_1,L_{-1}]=2L_0.
$$

<details><summary><strong>Solution</strong></summary>

For

$$
n=-1,0,1,
$$

we have

$$
n(n^2-1)=0.
$$

Hence the central term vanishes within the span of $L_{-1},L_0,L_1$.

Now use the noncentral part:

$$
[L_n,L_m]=(n-m)L_{n+m}.
$$

For $[L_0,L_{-1}]$,

$$
[L_0,L_{-1}]=(0-(-1))L_{-1}=L_{-1}.
$$

For $[L_0,L_1]$,

$$
[L_0,L_1]=(0-1)L_1=-L_1.
$$

For $[L_1,L_{-1}]$,

$$
[L_1,L_{-1}]=(1-(-1))L_0=2L_0.
$$

This is the holomorphic $\mathfrak{sl}(2)$ global conformal algebra.

</details>

### Exercise 6: The Schwarzian on the cylinder

Let

$$
z=e^w.
$$

Compute

$$
\{z,w\}
=
\frac{z'''(w)}{z'(w)}
-
\frac{3}{2}\left(\frac{z''(w)}{z'(w)}\right)^2.
$$

Then show that if $\langle T_z(z)\rangle=0$ on the plane, the cylinder expectation value is

$$
\langle T_w(w)\rangle=-\frac{c}{24}.
$$

<details><summary><strong>Solution</strong></summary>

For

$$
z=e^w,
$$

we have

$$
z'=e^w=z,
\qquad
z''=e^w=z,
\qquad
z'''=e^w=z.
$$

Therefore

$$
\frac{z'''}{z'}=1,
\qquad
\frac{z''}{z'}=1.
$$

The Schwarzian is

$$
\{z,w\}
=1-\frac32
=-\frac12.
$$

The stress-tensor transformation law is

$$
T_w(w)
=
\left(\frac{dz}{dw}\right)^2T_z(z)
+
\frac{c}{12}\{z,w\}.
$$

If

$$
\langle T_z(z)\rangle=0,
$$

then

$$
\langle T_w(w)\rangle
=\frac{c}{12}\left(-\frac12\right)
=-\frac{c}{24}.
$$

</details>

## Further reading

For the classic development, see Di Francesco, Mathieu, and Sénéchal, Chapter 5 on Ward identities, central charge, and the stress tensor, and Chapter 6 on radial quantization and the Virasoro algebra. For holography, this page prepares the Brown-Henneaux central charge, the Cardy formula, Virasoro blocks, and worldsheet conformal constraints.
