---
title: "Conformal Ward Identities"
description: "Local and integrated Ward identities for conformal transformations, contact terms, primary operators, and the CFT constraints that become bulk constraints in AdS/CFT."
sidebar:
  order: 4
---

The previous pages introduced operators, sources, the stress tensor, and conserved currents. We now put these ingredients together into one of the most useful tools in conformal field theory: **Ward identities**.

A Ward identity is symmetry written as an equation for correlation functions. In a CFT, the conformal Ward identities say that inserting the stress tensor and integrating it over a surface implements an infinitesimal spacetime transformation on all operator insertions inside the surface.

This page has two goals. First, it gives the local and integrated forms of the Ward identities in a form that is usable in arbitrary dimension. Second, it explains why conformal symmetry fixes the kinematic structure of CFT correlators. The formulas here are the bridge between the geometric conformal group and the concrete correlators studied in the next module.

The AdS/CFT reason to care is sharp:

$$
\boxed{
\text{CFT Ward identities}
\quad\longleftrightarrow\quad
\text{bulk constraint equations.}
}
$$

Boundary stress-tensor conservation becomes the bulk momentum constraint. The trace Ward identity becomes the radial Hamiltonian/Weyl constraint, including the holographic Weyl anomaly in even boundary dimensions.

## The basic idea

Let

$$
X=
\mathcal O_1^{A_1}(x_1)
\mathcal O_2^{A_2}(x_2)
\cdots
\mathcal O_n^{A_n}(x_n)
$$

be a product of local operators. The superscripts $A_i$ denote possible spin or internal indices. In this page we work mostly in flat Euclidean space. Lorentzian formulas are obtained by replacing $\delta_{\mu\nu}$ with $\eta_{\mu\nu}$ and by choosing the appropriate real-time ordering prescription.

The stress tensor generates spacetime transformations. If $\xi^\mu(x)$ is an infinitesimal vector field, define the current

$$
j_\xi^\mu(x)=T^{\mu\nu}(x)\xi_\nu(x).
$$

At separated points, if $\xi^\mu$ is a conformal Killing vector and the theory is a CFT, this current is conserved:

$$
\partial_\mu j_\xi^\mu(x)=0,
\qquad x\neq x_i.
$$

But inside a correlation function this statement is incomplete. When $x$ collides with an operator insertion $x_i$, there are contact terms. These contact terms are not technical clutter; they are exactly the statement that $T_{\mu\nu}$ generates the conformal transformation of the operator at $x_i$.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Conformal Ward identity as stress-tensor flux through a surface enclosing operator insertions](/figures/cft/conformal-ward-identities-contours.svg)

<figcaption>

The conformal current $j_\xi^\mu=T^{\mu\nu}\xi_\nu$ is conserved away from insertions. Its flux through a surface depends only on which operators are enclosed. When the surface crosses an insertion, the Ward identity produces the infinitesimal conformal variation of that operator.

</figcaption>
</figure>

## Conformal Killing vectors

A vector field $\xi^\mu(x)$ generates an infinitesimal conformal transformation if it obeys the conformal Killing equation

$$
\partial_\mu \xi_\nu+
\partial_\nu \xi_\mu
=
2\sigma_\xi(x)\delta_{\mu\nu},
$$

where

$$
\sigma_\xi(x)=\frac{1}{d}\partial_\rho\xi^\rho(x).
$$

Equivalently, the infinitesimal coordinate transformation

$$
x^\mu\mapsto x^\mu+\xi^\mu(x)
$$

changes the flat metric by a local Weyl rescaling:

$$
\delta_\xi \delta_{\mu\nu}
=
\partial_\mu\xi_\nu+
\partial_\nu\xi_\mu
=
2\sigma_\xi\delta_{\mu\nu}.
$$

For $d\ge 3$, the most general solution is

$$
\xi^\mu(x)
=
a^\mu
+
\omega^\mu{}_{\nu}x^\nu
+
\lambda x^\mu
+
2(b\cdot x)x^\mu-b^\mu x^2,
$$

with

$$
\omega_{\mu\nu}=-\omega_{\nu\mu}.
$$

The four pieces are translations, rotations, dilatations, and special conformal transformations. Their corresponding values of $\sigma_\xi$ are:

| transformation | $\xi^\mu(x)$ | $\sigma_\xi(x)$ |
|---|---:|---:|
| translation | $a^\mu$ | $0$ |
| rotation | $\omega^\mu{}_{\nu}x^\nu$ | $0$ |
| dilatation | $\lambda x^\mu$ | $\lambda$ |
| special conformal | $2(b\cdot x)x^\mu-b^\mu x^2$ | $2b\cdot x$ |

The fact that $\sigma_\xi$ appears in the Ward identity is why scaling dimensions enter conformal transformations.

## Primary operators and the differential generator

A scalar primary operator of dimension $\Delta$ transforms infinitesimally as

$$
\delta_\xi \mathcal O(x)
=
-
\left[
\xi^\mu(x)\partial_\mu+
\Delta\sigma_\xi(x)
\right]
\mathcal O(x).
$$

For a spinning primary, there is also a local rotation of the spin indices. Define

$$
\varpi_{\mu\nu}(x)
=
\frac12\left(\partial_\mu\xi_\nu-\partial_\nu\xi_\mu\right).
$$

If $S^{\mu\nu}$ are the spin generators in the representation of $\mathcal O^A$, then

$$
\delta_\xi \mathcal O^A(x)
=
-
\left[
\xi^\mu\partial_\mu+
\Delta\sigma_\xi
\right]
\mathcal O^A(x)
-
\frac12\varpi_{\mu\nu}
(S^{\mu\nu})^A{}_{B}\mathcal O^B(x).
$$

It is convenient to define the positive differential operator $\mathcal D_{\xi}$ by

$$
\delta_\xi\mathcal O^A(x)=-\mathcal D_\xi\mathcal O^A(x),
$$

so that

$$
\boxed{
\mathcal D_\xi
=
\xi^\mu\partial_\mu+
\Delta\sigma_\xi
+
\frac12\varpi_{\mu\nu}S^{\mu\nu}.
}
$$

For a product of operators, $\mathcal D_{\xi,i}$ means that the operator acts on the $i$-th insertion, including its coordinate, dimension, and spin indices.

## The local conformal Ward identity

With the convention above, the local conformal Ward identity is

$$
\boxed{
\partial_\mu
\left\langle
T^{\mu\nu}(x)\xi_\nu(x)\,X
\right\rangle
=
-
\sum_{i=1}^n
\delta^{(d)}(x-x_i)\,
\mathcal D_{\xi,i}
\left\langle X\right\rangle.
}
$$

This equation should be read as a distributional identity. Away from the points $x=x_i$, the right-hand side vanishes. At the insertion points, the delta functions tell us how the inserted operators transform.

Integrating over a region $R$ gives

$$
\int_{\partial R}dS_\mu\,
\left\langle
T^{\mu\nu}\xi_\nu X
\right\rangle
=
-
\sum_{x_i\in R}
\mathcal D_{\xi,i}
\left\langle X\right\rangle.
$$

If $R$ is all of flat space and the surface term at infinity vanishes, we obtain the global Ward identity

$$
\boxed{
\sum_{i=1}^n
\mathcal D_{\xi,i}
\left\langle
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle
=0.
}
$$

This is the form most often used to constrain CFT correlators.

The sign convention is not sacred. Some authors define the infinitesimal operator variation with the opposite sign. Then both the definition of $\mathcal D_\xi$ and the local Ward identity change sign, while the global constraint is the same.

## Why the current is conserved away from insertions

At separated points, use the symmetry of the stress tensor and the conformal Killing equation:

$$
\partial_\mu j_\xi^\mu
=
\partial_\mu(T^{\mu\nu}\xi_\nu)
=
(\partial_\mu T^{\mu\nu})\xi_\nu
+
T^{\mu\nu}\partial_\mu\xi_\nu.
$$

In a flat-space CFT at separated points,

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

Also,

$$
T^{\mu\nu}\partial_\mu\xi_\nu
=
\frac12 T^{\mu\nu}
\left(\partial_\mu\xi_\nu+
\partial_\nu\xi_\mu\right)
=
\sigma_\xi T^\mu{}_{\mu}.
$$

Therefore

$$
\partial_\mu j_\xi^\mu=0
\qquad
(x\neq x_i).
$$

This is the clean local reason conformal transformations have charges: the current $T^{\mu\nu}\xi_\nu$ is conserved whenever $\xi$ is a conformal Killing vector.

## The separate Ward identities

The compact identity above packages several more primitive Ward identities.

### Translations

Take

$$
\xi^\mu=a^\mu.
$$

For scalar insertions,

$$
\mathcal D_{\xi,i}=a^\mu\partial_{i\mu}.
$$

Since $a^\mu$ is arbitrary, the local identity gives

$$
\boxed{
\partial_\mu
\left\langle
T^{\mu\nu}(x)X
\right\rangle
=
-
\sum_{i=1}^n
\delta^{(d)}(x-x_i)
\partial_{i}^{\nu}
\left\langle X\right\rangle
}
$$

for scalar insertions in our sign convention.

The corresponding global identity is

$$
\sum_{i=1}^n\partial_{i}^{\nu}
\left\langle X\right\rangle=0.
$$

Thus a correlator depends only on relative separations, not on the absolute origin.

### Rotations

Take

$$
\xi^\mu=\omega^\mu{}_{\nu}x^\nu,
\qquad
\omega_{\mu\nu}=-\omega_{\nu\mu}.
$$

The global Ward identity becomes

$$
\boxed{
\sum_{i=1}^n
\left[
 x_{i\mu}\partial_{i\nu}
 -x_{i\nu}\partial_{i\mu}
 +S^{(i)}_{\mu\nu}
\right]
\left\langle X\right\rangle
=0.
}
$$

For scalar operators the spin term is absent. For vector, spinor, tensor, or mixed-symmetry operators, the spin term rotates their indices.

### Dilatations

Take

$$
\xi^\mu=\lambda x^\mu.
$$

Then $\sigma_\xi=\lambda$, and the scalar-primary Ward identity is

$$
\boxed{
\sum_{i=1}^n
\left(
 x_i\cdot\partial_i+\Delta_i
\right)
\left\langle
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle
=0.
}
$$

Equivalently, under $x_i\mapsto \Lambda x_i$,

$$
\left\langle
\mathcal O_1(\Lambda x_1)\cdots\mathcal O_n(\Lambda x_n)
\right\rangle
=
\Lambda^{-\sum_i\Delta_i}
\left\langle
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle.
$$

This is the precise statement that local operators have scaling dimensions.

### Special conformal transformations

Take

$$
\xi^\mu=2(b\cdot x)x^\mu-b^\mu x^2.
$$

For scalar primaries,

$$
\mathcal D_{\xi,i}
=
b_\mu
\left[
2x_i^\mu(x_i\cdot\partial_i)
-x_i^2\partial_i^\mu
+2\Delta_i x_i^\mu
\right].
$$

Since $b_\mu$ is arbitrary, the global special conformal Ward identity is

$$
\boxed{
\sum_{i=1}^n
\left[
2x_i^\mu(x_i\cdot\partial_i)
-x_i^2\partial_i^\mu
+2\Delta_i x_i^\mu
\right]
\left\langle X\right\rangle
=0
}
$$

for scalar primaries. For spinning primaries, the full operator is

$$
\boxed{
\sum_{i=1}^n
\left[
2x_i^\mu(x_i\cdot\partial_i)
-x_i^2\partial_i^\mu
+2\Delta_i x_i^\mu
+2x_{i\nu}S_i^{\mu\nu}
\right]
\left\langle X\right\rangle
=0.
}
$$

This identity is the extra constraint that distinguishes conformal invariance from ordinary scale invariance.

## Contact terms are the point, not a nuisance

At separated points, the CFT stress tensor satisfies

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0,
\qquad
T^{\mu\nu}=T^{\nu\mu}.
$$

Inside correlators, these equations become distributional. For example, in a correlator of scalar primaries,

$$
\partial_\mu
\left\langle
T^{\mu\nu}(x)X
\right\rangle
$$

has delta-function support at $x=x_i$. Similarly, the trace insertion

$$
\left\langle T^\mu{}_{\mu}(x)X\right\rangle
$$

has contact terms that encode the scaling dimensions of the insertions. Schematically,

$$
\left\langle T^\mu{}_{\mu}(x)X\right\rangle
=
-
\sum_i
\Delta_i\delta^{(d)}(x-x_i)
\left\langle X\right\rangle
+
\text{derivative contact terms},
$$

where the derivative terms depend on the precise definition of the local operators and on possible spin structures.

This is why the phrase “$T^\mu{}_{\mu}=0$ in a CFT” must be read carefully. At separated points it is true. As an operator statement inside correlation functions, it is true only after keeping track of contact terms. Those contact terms are exactly what make the stress tensor generate scale transformations.

## How the Ward identities fix scalar two-point functions

Let

$$
G_{12}(x_1,x_2)
=
\left\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\right\rangle
$$

for scalar primaries of dimensions $\Delta_1$ and $\Delta_2$.

Translation and rotation invariance imply

$$
G_{12}(x_1,x_2)=f(r),
\qquad
r=|x_{12}|,
\qquad
x_{12}=x_1-x_2.
$$

The dilation Ward identity gives

$$
\left(
 r\frac{d}{dr}+\Delta_1+\Delta_2
\right)f(r)=0,
$$

so

$$
f(r)=\frac{C_{12}}{r^{\Delta_1+\Delta_2}}.
$$

The special conformal Ward identity then forces

$$
\Delta_1=\Delta_2
$$

unless $C_{12}=0$. Therefore

$$
\boxed{
\left\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\right\rangle
=
\frac{C_{12}\delta_{\Delta_1,\Delta_2}}{|x_{12}|^{2\Delta_1}}.
}
$$

In a basis of scalar primaries with diagonal two-point functions, this becomes

$$
\left\langle
\mathcal O_i(x)\mathcal O_j(0)
\right\rangle
=
\frac{C_i\delta_{ij}}{|x|^{2\Delta_i}}.
$$

Often one chooses the normalization $C_i=1$ for nonzero-norm scalar primaries.

## How they fix scalar three-point functions

For three scalar primaries, conformal Ward identities imply

$$
\boxed{
\left\langle
\mathcal O_1(x_1)
\mathcal O_2(x_2)
\mathcal O_3(x_3)
\right\rangle
=
\frac{C_{123}}
{|x_{12}|^{\Delta_1+\Delta_2-\Delta_3}
 |x_{23}|^{\Delta_2+\Delta_3-\Delta_1}
 |x_{13}|^{\Delta_1+\Delta_3-\Delta_2}}
.}
$$

The coefficient $C_{123}$ is not fixed by symmetry. It is dynamical CFT data. Together with the spectrum of primary dimensions and spins, these coefficients are the input for the OPE and conformal bootstrap.

This is an important moral: Ward identities are powerful, but they do not solve the whole theory in $d\ge 3$. They fix the form of low-point functions and relate certain coefficients, but they leave genuine dynamical data.

## Four points and beyond

For four scalar operators, conformal invariance leaves nontrivial functions of cross-ratios. Define

$$
u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

A common notation is $u$ and $v$ for these cross-ratios, and we will use it throughout the course.

For identical scalar primaries of dimension $\Delta$,

$$
\left\langle
\mathcal O(x_1)\mathcal O(x_2)
\mathcal O(x_3)\mathcal O(x_4)
\right\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^\Delta}
\mathcal G(u,v).
$$

The function $\mathcal G(u,v)$ is not fixed by conformal symmetry alone. Crossing symmetry and the OPE constrain it further. This is where the conformal bootstrap begins.

## Ward identities with sources

The source formalism from the previous page gives a compact way to write Ward identities on general backgrounds.

Let

$$
W[g,A,\lambda]=-\log Z[g,A,\lambda]
$$

with metric $g_{\mu\nu}$, background gauge field $A_\mu^a$, and scalar sources $\lambda^i$. The expectation values are defined by

$$
\langle T^{\mu\nu}\rangle
=
\frac{2}{\sqrt g}\frac{\delta W}{\delta g_{\mu\nu}},
\qquad
\langle J_a^\mu\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta A_\mu^a},
\qquad
\langle\mathcal O_i\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta\lambda^i}.
$$

Diffeomorphism invariance gives, schematically,

$$
\boxed{
\nabla_\mu\langle T^\mu{}_{\nu}\rangle
=
F_{\nu\mu}^a\langle J_a^\mu\rangle
+
\langle\mathcal O_i\rangle\nabla_\nu\lambda^i
+
\text{anomaly terms}.
}
$$

In flat space with no background sources this reduces to

$$
\partial_\mu\langle T^{\mu}{}_{\nu}\rangle=0.
$$

Weyl invariance gives

$$
\boxed{
\langle T^\mu{}_{\mu}\rangle
=
\sum_i(d-\Delta_i)\lambda^i\langle\mathcal O_i\rangle
+\mathcal A[g,A,\lambda].
}
$$

Here $\mathcal A$ is the Weyl anomaly. In a flat-space CFT with all sources set to zero, the anomaly vanishes and

$$
\langle T^\mu{}_{\mu}\rangle=0.
$$

In even dimensions on curved backgrounds, $\mathcal A$ can be nonzero. This is the curved-space origin of quantities such as the $a$ and $c$ anomaly coefficients in four-dimensional CFTs.

## The AdS/CFT checkpoint

In holography, the generating functional relation is roughly

$$
W_{\mathrm{CFT}}[g_{(0)},A_{(0)},\lambda]
\simeq
S_{\mathrm{bulk,ren}}^{\mathrm{os}}[g_{(0)},A_{(0)},\lambda]
$$

in the classical bulk limit. The Ward identities of the CFT are then not optional constraints imposed after solving the bulk equations. They are already built into the bulk theory:

$$
\begin{array}{ccl}
\text{CFT diffeomorphism Ward identity}
&\longleftrightarrow&
\text{bulk momentum constraint},\\
\text{CFT current Ward identity}
&\longleftrightarrow&
\text{bulk gauge constraint},\\
\text{CFT Weyl Ward identity}
&\longleftrightarrow&
\text{radial Hamiltonian constraint and anomaly}.
\end{array}
$$

This is why the stress tensor is the first operator one should understand before learning the AdS/CFT dictionary. It is the boundary imprint of bulk gravity.

## Common pitfalls

A first common mistake is to say that $\partial_\mu T^{\mu\nu}=0$ and $T^\mu{}_{\mu}=0$ imply that stress-tensor insertions vanish in Ward identities. They do not. They vanish only away from contact terms.

A second common mistake is to confuse scale invariance with conformal invariance. The dilation Ward identity alone fixes homogeneity. The special conformal Ward identity imposes additional constraints. For example, it is the special conformal identity that forces scalar two-point functions of primaries with unequal dimensions to vanish.

A third common mistake is to ignore spin terms. For scalar correlators this is harmless. For currents, stress tensors, fermions, and supersymmetric operators, the spin part of $\mathcal D_\xi$ is essential.

## Summary

The conformal Ward identities can be compressed into the statement

$$
\partial_\mu
\left\langle
T^{\mu\nu}(x)\xi_\nu(x)X
\right\rangle
=
-
\sum_i
\delta^{(d)}(x-x_i)
\mathcal D_{\xi,i}
\left\langle X\right\rangle.
$$

For global conformal transformations, this becomes

$$
\sum_i\mathcal D_{\xi,i}\left\langle X\right\rangle=0.
$$

These identities fix the coordinate dependence of two- and three-point functions, identify the stress tensor as the generator of spacetime symmetries, and provide the boundary form of the gravitational constraints in AdS/CFT.

## Exercises

### Exercise 1 — Conservation of the conformal current

Let $\xi^\mu$ obey the conformal Killing equation

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=2\sigma_\xi\delta_{\mu\nu}.
$$

Assume that at separated points

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
T^{\mu\nu}=T^{\nu\mu},
\qquad
T^\mu{}_{\mu}=0.
$$

Show that $j_\xi^\mu=T^{\mu\nu}\xi_\nu$ is conserved at separated points.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j_\xi^\mu
=
\partial_\mu(T^{\mu\nu}\xi_\nu)
=
(\partial_\mu T^{\mu\nu})\xi_\nu
+T^{\mu\nu}\partial_\mu\xi_\nu.
$$

The first term vanishes by stress-tensor conservation. Because $T^{\mu\nu}$ is symmetric,

$$
T^{\mu\nu}\partial_\mu\xi_\nu
=
\frac12T^{\mu\nu}
(\partial_\mu\xi_\nu+\partial_\nu\xi_\mu).
$$

Use the conformal Killing equation:

$$
T^{\mu\nu}\partial_\mu\xi_\nu
=
\frac12T^{\mu\nu}(2\sigma_\xi\delta_{\mu\nu})
=
\sigma_\xi T^\mu{}_{\mu}=0.
$$

Therefore

$$
\partial_\mu j_\xi^\mu=0
$$

away from operator insertions.

</details>

### Exercise 2 — Dilation Ward identity for an $n$-point function

Let

$$
G(x_1,\ldots,x_n)
=
\left\langle
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle
$$

where the $\mathcal O_i$ are scalar primaries of dimensions $\Delta_i$. Use the dilation Ward identity to show that

$$
G(\Lambda x_1,\ldots,\Lambda x_n)
=
\Lambda^{-\sum_i\Delta_i}G(x_1,\ldots,x_n).
$$

<details><summary><strong>Solution</strong></summary>

For a dilation,

$$
\xi^\mu=x^\mu,
\qquad
\sigma_\xi=1.
$$

The global Ward identity is

$$
\sum_i
\left(x_i\cdot\partial_i+\Delta_i\right)G=0.
$$

Now define

$$
F(\Lambda)=G(\Lambda x_1,\ldots,\Lambda x_n).
$$

Then

$$
\Lambda\frac{dF}{d\Lambda}
=
\sum_i x_i\cdot\partial_i\,G(\Lambda x_1,\ldots,\Lambda x_n).
$$

Applying the Ward identity at the points $\Lambda x_i$ gives

$$
\Lambda\frac{dF}{d\Lambda}
=-\left(\sum_i\Delta_i\right)F.
$$

Solving this differential equation yields

$$
F(\Lambda)=\Lambda^{-\sum_i\Delta_i}F(1),
$$

which is the desired result.

</details>

### Exercise 3 — Scalar two-point function

Assume translation, rotation, and scale invariance. Show that the two-point function of scalar primaries must have the form

$$
G_{12}(x_1,x_2)=\frac{C_{12}}{|x_{12}|^{\Delta_1+\Delta_2}}.
$$

Then use the special conformal Ward identity to show that $C_{12}=0$ unless $\Delta_1=\Delta_2$.

<details><summary><strong>Solution</strong></summary>

Translation invariance implies that the correlator depends only on

$$
x_{12}=x_1-x_2.
$$

Rotation invariance then implies that it depends only on

$$
r=|x_{12}|.
$$

So $G_{12}=f(r)$. The dilation Ward identity gives

$$
\left(r\frac{d}{dr}+\Delta_1+\Delta_2\right)f(r)=0,
$$

whose solution is

$$
f(r)=\frac{C_{12}}{r^{\Delta_1+\Delta_2}}.
$$

Now place one operator at the origin and the other at $x$:

$$
G_{12}(x,0)=\frac{C_{12}}{|x|^{\Delta_1+\Delta_2}}.
$$

The special conformal Ward identity for two scalar primaries is

$$
\sum_{i=1}^2
\left[
2x_i^\mu(x_i\cdot\partial_i)-x_i^2\partial_i^\mu+2\Delta_i x_i^\mu
\right]G_{12}=0.
$$

At $x_2=0$, the second operator contributes no explicit term. Acting on the power law gives

$$
\left[
2x^\mu(x\cdot\partial)-x^2\partial^\mu+2\Delta_1x^\mu
\right]
|x|^{-\Delta_1-\Delta_2}
=
(\Delta_1-\Delta_2)x^\mu |x|^{-\Delta_1-\Delta_2}.
$$

Therefore the special conformal Ward identity requires

$$
(\Delta_1-\Delta_2)C_{12}=0.
$$

Thus $C_{12}$ can be nonzero only when

$$
\Delta_1=\Delta_2.
$$

</details>

### Exercise 4 — Special conformal generator from the conformal Killing vector

For

$$
\xi^\mu=2(b\cdot x)x^\mu-b^\mu x^2,
$$

show that

$$
\sigma_\xi=2b\cdot x.
$$

Then derive the scalar-primary differential operator

$$
\mathcal D_\xi
=
b_\mu
\left[
2x^\mu(x\cdot\partial)-x^2\partial^\mu+2\Delta x^\mu
\right].
$$

<details><summary><strong>Solution</strong></summary>

First compute the divergence:

$$
\partial_\mu\xi^\mu
=
\partial_\mu\left[2(b\cdot x)x^\mu-b^\mu x^2\right].
$$

The first term gives

$$
\partial_\mu\left[2(b\cdot x)x^\mu\right]
=
2b_\mu x^\mu+2d(b\cdot x)
=2(d+1)b\cdot x.
$$

The second gives

$$
\partial_\mu(b^\mu x^2)=2b\cdot x.
$$

Therefore

$$
\partial_\mu\xi^\mu=2d(b\cdot x),
$$

and hence

$$
\sigma_\xi=\frac1d\partial_\mu\xi^\mu=2b\cdot x.
$$

For a scalar primary,

$$
\mathcal D_\xi=\xi^\mu\partial_\mu+\Delta\sigma_\xi.
$$

Substitute $\xi^\mu$ and $\sigma_\xi$:

$$
\mathcal D_\xi
=\left[2(b\cdot x)x^\mu-b^\mu x^2\right]\partial_\mu
+2\Delta(b\cdot x).
$$

Factoring out $b_\mu$ gives

$$
\mathcal D_\xi
=
b_\mu
\left[
2x^\mu(x\cdot\partial)-x^2\partial^\mu+2\Delta x^\mu
\right].
$$

</details>

### Exercise 5 — Weyl Ward identity with a scalar source

Suppose a CFT is deformed by

$$
S\mapsto S+
\int d^d x\sqrt g\,\lambda(x)\mathcal O(x),
$$

where $\mathcal O$ is a scalar primary of dimension $\Delta$. Under a Weyl transformation,

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu},
\qquad
\delta_\sigma\lambda=-(d-\Delta)\sigma\lambda.
$$

Using

$$
\delta W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}
+
\int d^d x\sqrt g\,\langle\mathcal O\rangle\delta\lambda,
$$

show that Weyl invariance without anomaly implies

$$
\langle T^\mu{}_{\mu}\rangle
=(d-\Delta)\lambda\langle\mathcal O\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the Weyl variations into $\delta W$. The metric term is

$$
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle(2\sigma g_{\mu\nu})
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

The source term is

$$
\int d^d x\sqrt g\,\langle\mathcal O\rangle[-(d-\Delta)\sigma\lambda]
=
-
\int d^d x\sqrt g\,\sigma(d-\Delta)\lambda\langle\mathcal O\rangle.
$$

Thus

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma
\left[
\langle T^\mu{}_{\mu}\rangle
-(d-\Delta)\lambda\langle\mathcal O\rangle
\right].
$$

If the theory is Weyl invariant and there is no anomaly, $\delta_\sigma W=0$ for arbitrary $\sigma(x)$. Therefore

$$
\langle T^\mu{}_{\mu}\rangle
=(d-\Delta)\lambda\langle\mathcal O\rangle.
$$

When $\lambda=0$, this reduces to $\langle T^\mu{}_{\mu}\rangle=0$.

</details>
