---
title: "Embedding-Space Formulas"
description: "A compact formula sheet for the projective null cone, scalar and spinning CFT correlators, conformal generators, shadow language, and the AdS embedding used in holography."
sidebar:
  order: 3
---

The embedding-space formalism is a notation machine. Its job is not to add new physics, but to make conformal covariance manifest.

The central idea is simple: instead of letting the conformal group act nonlinearly on $x^\nu\in\mathbb R^d$, represent the same point by a null ray $P^A$ in a $(d+2)$-dimensional space. The conformal group then acts linearly as $SO(d+1,1)$ in Euclidean signature, or $SO(d,2)$ in Lorentzian signature.

This appendix collects the formulas used throughout the course. It is written as a working reference: conventions, scalar correlators, spinning correlators, projective measure, differential operators, and the AdS/CFT dictionary in embedding notation.

## Ambient space conventions

For Euclidean CFT$_d$, introduce an ambient space $\mathbb R^{d+1,1}$ with coordinates

$$
P^A=(P^+,P^-,P^\mu),
\qquad
\mu=1,\ldots,d.
$$

We use the inner product

$$
P\cdot Q
=
-\frac12(P^+Q^-+P^-Q^+)+P^\mu Q_\mu,
$$

where $P^\mu Q_\mu$ is contracted with the flat Euclidean metric $\delta_{\mu\nu}$. With this convention,

$$
P^2=-P^+P^-+P^\mu P_\mu.
$$

The physical conformal compactification of $\mathbb R^d$ is represented by the projective null cone

$$
P^2=0,
\qquad
P^A\sim \lambda P^A,
\qquad
\lambda\neq 0.
$$

The word **projective** is crucial. A boundary point is not a particular null vector $P^A$, but a ray $[P]$.

A convenient Poincare section is

$$
P(x)=(1,x^2,x^\mu).
$$

Then

$$
P(x)^2=-1\cdot x^2+x^2=0,
$$

and for two physical points $x_i,x_j$,

$$
P_i\cdot P_j=-\frac12 x_{ij}^2,
\qquad
x_{ij}^2=(x_i-x_j)^2.
$$

It is therefore standard to define

$$
P_{ij}\equiv -2P_i\cdot P_j.
$$

On the Poincare section,

$$
P_{ij}=x_{ij}^2.
$$

This one formula is the reason embedding notation is so efficient: all conformal distances are replaced by ambient inner products.

## The projective cone as conformal compactification

The projective null cone contains ordinary points $x^\mu$ as the patch $P^+\neq0$:

$$
x^\mu=\frac{P^\mu}{P^+}.
$$

The locus $P^+=0$ describes points at infinity in the compactification. Conformal transformations are simply ambient linear transformations

$$
P^A\mapsto \Lambda^A{}_B P^B,
\qquad
\Lambda\in SO(d+1,1),
$$

followed by returning to a chosen section, such as $P^+=1$. The nonlinear appearance of translations, inversions, dilatations, and special conformal transformations in physical space is just the price of gauge-fixing the projective scale.

For Lorentzian CFT, replace the ambient signature by $\mathbb R^{d,2}$. The same formulas hold with $x^2$ and $x_{ij}^2$ interpreted using the Lorentzian metric, together with the appropriate $i\epsilon$ prescription for correlators.

## Homogeneous scalar primaries

A scalar primary operator $\mathcal O(x)$ of scaling dimension $\Delta$ is represented by a homogeneous function $\mathcal O(P)$ on the null cone:

$$
\mathcal O(\lambda P)=\lambda^{-\Delta}\mathcal O(P).
$$

The physical operator is obtained by restricting to the Poincare section:

$$
\mathcal O(x)=\mathcal O(P(x)).
$$

The homogeneity condition is the embedding-space version of scaling dimension. Every valid correlator must have the correct projective weight at each insertion. For example, an $n$-point function of scalar primaries must obey

$$
\left\langle
\mathcal O_1(\lambda_1 P_1)\cdots \mathcal O_n(\lambda_n P_n)
\right\rangle
=
\prod_{i=1}^n\lambda_i^{-\Delta_i}
\left\langle
\mathcal O_1(P_1)\cdots \mathcal O_n(P_n)
\right\rangle.
$$

This is often the fastest way to derive conformally covariant structures.

## Scalar two- and three-point functions

For scalar primaries, the two-point function is

$$
\left\langle \mathcal O_i(P_1)\mathcal O_j(P_2)\right\rangle
=
\frac{C_{ij}\,\delta_{\Delta_i,\Delta_j}}{P_{12}^{\Delta_i}}.
$$

In an orthonormal basis of scalar primaries, one usually chooses $C_{ij}=\delta_{ij}$.

The scalar three-point function is

$$
\left\langle
\mathcal O_1(P_1)\mathcal O_2(P_2)\mathcal O_3(P_3)
\right\rangle
=
\frac{C_{123}}
{P_{12}^{\alpha_{12,3}}P_{13}^{\alpha_{13,2}}P_{23}^{\alpha_{23,1}}},
$$

where

$$
\alpha_{ij,k}
=
\frac{\Delta_i+\Delta_j-\Delta_k}{2}.
$$

This formula is fixed by projective homogeneity. For example, the total power of $P_1$ in the denominator is

$$
\alpha_{12,3}+\alpha_{13,2}=\Delta_1,
$$

as required.

The coefficient $C_{123}$ is dynamical CFT data. Symmetry fixes the position dependence, not the number multiplying it.

## Four-point functions and cross-ratios

For four scalar primaries, conformal symmetry leaves two independent invariants:

$$
u
=
\frac{P_{12}P_{34}}{P_{13}P_{24}},
\qquad
v
=
\frac{P_{14}P_{23}}{P_{13}P_{24}}.
$$

On the Poincare section these are the usual cross-ratios

$$
u
=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v
=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

A convenient scalar four-point parameterization is

$$
\left\langle
\mathcal O_1(P_1)\mathcal O_2(P_2)
\mathcal O_3(P_3)\mathcal O_4(P_4)
\right\rangle
=
\frac{1}{P_{12}^{(\Delta_1+\Delta_2)/2}P_{34}^{(\Delta_3+\Delta_4)/2}}
\left(\frac{P_{24}}{P_{14}}\right)^{\Delta_{12}/2}
\left(\frac{P_{14}}{P_{13}}\right)^{\Delta_{34}/2}
\mathcal G(u,v),
$$

where

$$
\Delta_{ij}=\Delta_i-\Delta_j.
$$

For identical scalars $\phi$ of dimension $\Delta$, this reduces to

$$
\left\langle
\phi(P_1)\phi(P_2)\phi(P_3)\phi(P_4)
\right\rangle
=
\frac{\mathcal G(u,v)}{P_{12}^{\Delta}P_{34}^{\Delta}}.
$$

The whole dynamical content of the four-point function is in $\mathcal G(u,v)$. The conformal block expansion, crossing symmetry, and the bootstrap all act on this function.

## Ambient conformal generators

The conformal group acts linearly on $P^A$. The ambient generators are

$$
J_{AB}
=
P_A\frac{\partial}{\partial P^B}
-
P_B\frac{\partial}{\partial P^A},
$$

up to the conventional factor of $-i$ used for Hermitian generators. They obey the $\mathfrak{so}(d+1,1)$ algebra

$$
[J_{AB},J_{CD}]
=
\eta_{BC}J_{AD}-\eta_{AC}J_{BD}
-\eta_{BD}J_{AC}+\eta_{AD}J_{BC},
$$

again up to factors of $i$ depending on convention.

For a scalar primary in physical coordinates, the corresponding differential operators can be taken as

$$
\mathcal P_\mu=\partial_\mu,
$$

$$
\mathcal M_{\mu\nu}=x_\mu\partial_\nu-x_\nu\partial_\mu,
$$

$$
\mathcal D=x\cdot\partial+\Delta,
$$

$$
\mathcal K_\mu
=x^2\partial_\mu-2x_\mu x\cdot\partial-2\Delta x_\mu.
$$

With different active/passive transformation conventions, all these generators may acquire an overall sign. The invariant statement is that a scalar correlator is annihilated by the sum of the generators acting on all insertions:

$$
\sum_{i=1}^n \mathcal G_i
\left\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\right\rangle=0
$$

for every generator $\mathcal G$ of the conformal algebra.

The quadratic conformal Casimir is

$$
\mathcal C_2
=\frac12 J_{AB}J^{AB}.
$$

On a primary of dimension $\Delta$ and spin $\ell$, its eigenvalue is

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

This is the number that appears in the Casimir equation for conformal blocks.

## Symmetric traceless tensors and polarizations

A spin-$\ell$ symmetric traceless tensor primary is encoded by a null polarization vector:

$$
\mathcal O(x,z)
=
\mathcal O_{\mu_1\cdots\mu_\ell}(x)
z^{\mu_1}\cdots z^{\mu_\ell},
\qquad
z^2=0.
$$

The condition $z^2=0$ removes traces. In embedding space, introduce a polarization vector $Z^A$ satisfying

$$
P^2=0,
\qquad
Z^2=0,
\qquad
P\cdot Z=0.
$$

The spinning primary is represented by a function $\mathcal O(P,Z)$ obeying

$$
\mathcal O(\lambda P,\alpha Z+\beta P)
=
\lambda^{-\Delta}\alpha^\ell \mathcal O(P,Z).
$$

There are two pieces in this formula.

The factor $\lambda^{-\Delta}$ encodes the scaling dimension. The factor $\alpha^\ell$ encodes spin. The shift $Z\to Z+\beta P$ is a gauge redundancy; physical tensor structures must be invariant under it.

The Poincare-section lift of the physical polarization is

$$
P(x)=(1,x^2,x^\mu),
\qquad
Z(x,z)=(0,2x\cdot z,z^\mu).
$$

Then

$$
P(x)\cdot Z(x,z)=0,
\qquad
Z(x,z)^2=z^2.
$$

Thus $z^2=0$ implies $Z^2=0$.

## Spinning two-point function

Define

$$
H_{ij}
=
P_{ij}\,Z_i\cdot Z_j
+2(Z_i\cdot P_j)(Z_j\cdot P_i).
$$

This object is gauge-invariant under $Z_i\to Z_i+\beta_iP_i$ and $Z_j\to Z_j+\beta_jP_j$.

A spin-$\ell$ two-point function is

$$
\left\langle
\mathcal O_1(P_1,Z_1)\mathcal O_2(P_2,Z_2)
\right\rangle
=
C_{12}\,\delta_{\Delta_1,\Delta_2}\delta_{\ell_1,\ell_2}
\frac{H_{12}^{\ell}}{P_{12}^{\Delta+\ell}}.
$$

Equivalently,

$$
\frac{H_{12}^{\ell}}{P_{12}^{\Delta+\ell}}
=
\frac{\mathcal H_{12}^{\ell}}{P_{12}^{\Delta}},
\qquad
\mathcal H_{12}=\frac{H_{12}}{P_{12}}.
$$

On the physical section,

$$
\mathcal H_{12}
=
z_1\cdot z_2
-2\frac{(z_1\cdot x_{12})(z_2\cdot x_{12})}{x_{12}^2}
=
z_1\cdot I(x_{12})\cdot z_2,
$$

where

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}
$$

is the inversion tensor. This is the standard physical-space form of the spinning two-point function.

## Spinning three-point building blocks

For three spinning insertions, define

$$
V_{i,jk}
=
\frac{P_{ik}(Z_i\cdot P_j)-P_{ij}(Z_i\cdot P_k)}{P_{jk}}.
$$

This is invariant under $Z_i\to Z_i+\beta_iP_i$ and is homogeneous of degree one in $P_i$ and degree one in $Z_i$.

The parity-even tensor structures are generated by $V_{i,jk}$ and $H_{ij}$. A convenient basis is

$$
\mathcal T_{n_{12},n_{13},n_{23}}
=
\frac{
V_{1,23}^{m_1}
V_{2,31}^{m_2}
V_{3,12}^{m_3}
H_{12}^{n_{12}}
H_{13}^{n_{13}}
H_{23}^{n_{23}}
}
{P_{12}^{(\tau_1+\tau_2-\tau_3)/2}
 P_{13}^{(\tau_1+\tau_3-\tau_2)/2}
 P_{23}^{(\tau_2+\tau_3-\tau_1)/2}},
$$

where

$$
\tau_i=\Delta_i+\ell_i,
$$

and

$$
m_1=\ell_1-n_{12}-n_{13},
$$

$$
m_2=\ell_2-n_{12}-n_{23},
$$

$$
m_3=\ell_3-n_{13}-n_{23}.
$$

The nonnegative integers $n_{12},n_{13},n_{23}$ must be chosen so that

$$
m_1,m_2,m_3\geq 0.
$$

A general parity-even three-point function is a linear combination

$$
\left\langle
\mathcal O_1(P_1,Z_1)
\mathcal O_2(P_2,Z_2)
\mathcal O_3(P_3,Z_3)
\right\rangle
=
\sum_{n_{12},n_{13},n_{23}}
\lambda_{n_{12},n_{13},n_{23}}
\mathcal T_{n_{12},n_{13},n_{23}}.
$$

The coefficients $\lambda_{n_{12},n_{13},n_{23}}$ are OPE data. Conservation equations and permutation symmetries may reduce the number of independent coefficients.

In special dimensions, parity-odd structures can also appear. They are built with the ambient epsilon tensor and are not captured by the purely $H,V$ parity-even basis.

## Thomas derivatives and extracting components

The null polarization trick hides traces by imposing $z^2=0$. To differentiate with respect to $z$ while preserving tracelessness, use the Thomas derivative

$$
D_z^\mu
=
\left(\frac d2-1+z\cdot\partial_z\right)\frac{\partial}{\partial z_\mu}
-
\frac12 z^\mu\partial_z^2.
$$

The embedding-space version is

$$
D_Z^A
=
\left(\frac d2-1+Z\cdot\partial_Z\right)
\frac{\partial}{\partial Z_A}
-
\frac12 Z^A\partial_Z^2.
$$

These derivatives are useful for extracting tensor components from generating functions. Normalization conventions vary, but schematically

$$
\mathcal O_{\mu_1\cdots\mu_\ell}(x)
\propto
D_{z,\mu_1}\cdots D_{z,\mu_\ell}\mathcal O(x,z)\bigg\vert_{z=0}.
$$

The proportionality constant depends only on $d$ and $\ell$, and cancels in many structural applications.

## Conservation constraints

A conserved spin-$\ell$ current has dimension

$$
\Delta=\ell+d-2,
\qquad
\ell\geq1.
$$

In physical polarization notation, conservation is

$$
\partial_x\cdot D_z\,\mathcal J(x,z)=0.
$$

For $\ell=1$, this is $\partial^\mu J_\mu=0$. For $\ell=2$, it is $\partial^\mu T_{\mu\nu}=0$ with $\Delta=d$.

In embedding notation, conservation can be implemented by an ambient divergence operator acting on $\mathcal J(P,Z)$, followed by projection to the cone. In practice, for correlators, it is often simplest to write the most general $H,V$ structure and then impose the physical divergence equations.

Conservation is a shortening condition. It reduces the number of independent tensor structures and relates OPE coefficients that would otherwise be independent.

## Projective integration measure

A projectively well-defined integral over the null cone is denoted

$$
\int D P\, f(P).
$$

The integrand must have homogeneity $-d$:

$$
f(\lambda P)=\lambda^{-d}f(P).
$$

In the Poincare section $P^+=1$, this reduces to an ordinary integral

$$
\int D P\, f(P)
=
\int d^d x\, f(P(x)),
$$

up to a convention-dependent normalization. This is the measure used in shadow transforms and conformal partial waves.

## Shadows

The scalar shadow of a primary of dimension $\Delta$ has dimension $d-\Delta$. In embedding notation, the scalar shadow transform is schematically

$$
\widetilde{\mathcal O}(P)
=
\int DQ\,
\frac{\mathcal O(Q)}{P_{PQ}^{d-\Delta}}.
$$

The exponent is fixed by homogeneity. Under $P\to\lambda P$,

$$
P_{PQ}^{-(d-\Delta)}\to \lambda^{-(d-\Delta)}P_{PQ}^{-(d-\Delta)},
$$

so $\widetilde{\mathcal O}$ has dimension $d-\Delta$.

Shadow language is especially useful for constructing conformal partial waves. Very roughly, a conformal partial wave is obtained by gluing two three-point functions with an integration over an intermediate projective point:

$$
\Psi_{\Delta,\ell}^{(s)}
\sim
\int D P_0\,
\left\langle \mathcal O_1\mathcal O_2\mathcal O_{\Delta,\ell}(P_0)\right\rangle
\left\langle \widetilde{\mathcal O}_{\Delta,\ell}(P_0)\mathcal O_3\mathcal O_4\right\rangle.
$$

The conformal block is obtained from the partial wave after separating the physical block from its shadow contribution.

## AdS in the same embedding space

Euclidean AdS$_{d+1}$ can be represented as the hyperboloid

$$
Y^2=-L^2
$$

inside the same ambient space $\mathbb R^{d+1,1}$. Setting $L=1$ for simplicity, Poincare coordinates $(z,x^\mu)$ are embedded as

$$
Y(z,x)=\left(\frac1z,\frac{z^2+x^2}{z},\frac{x^\mu}{z}\right).
$$

A quick check gives

$$
Y(z,x)^2=-1.
$$

The invariant between a bulk point $Y$ and a boundary point $P(x')$ is

$$
-2P(x')\cdot Y(z,x)
=
\frac{z^2+(x-x')^2}{z}.
$$

Therefore the scalar bulk-to-boundary propagator can be written as

$$
K_\Delta(Y,P)
=
\frac{\mathcal C_\Delta}{(-2P\cdot Y)^\Delta}.
$$

In Poincare coordinates this becomes

$$
K_\Delta(z,x;x')
=
\mathcal C_\Delta
\left(\frac{z}{z^2+(x-x')^2}\right)^\Delta.
$$

The mass-dimension relation for a scalar field in AdS$_{d+1}$ is

$$
m^2L^2=\Delta(\Delta-d).
$$

For spin, the same embedding language packages tensor indices and makes the boundary covariance of Witten diagrams transparent.

## Quick translation table

| Physical-space object | Embedding-space object |
|---|---|
| point $x^\mu$ | null ray $P^A\sim\lambda P^A$, $P^2=0$ |
| Poincare section | $P(x)=(1,x^2,x^\mu)$ |
| squared distance $x_{ij}^2$ | $P_{ij}=-2P_i\cdot P_j$ |
| scalar primary dimension $\Delta$ | homogeneity $\mathcal O(\lambda P)=\lambda^{-\Delta}\mathcal O(P)$ |
| spin-$\ell$ STT operator | polynomial $\mathcal O(P,Z)$ of degree $\ell$ in $Z$ |
| tracelessness | $Z^2=0$ |
| transversality/gauge redundancy | $Z\sim Z+\beta P$ |
| inversion tensor | $\mathcal H_{ij}=H_{ij}/P_{ij}$ |
| conformal group | linear $SO(d+1,1)$ or $SO(d,2)$ action |
| AdS bulk point | hyperboloid $Y^2=-L^2$ |
| bulk-boundary factor | $-2P\cdot Y$ |

## Common checks

Every embedding-space expression should pass four tests.

**Null-cone test.** It should be meaningful after imposing $P_i^2=0$.

**Projective-weight test.** Under $P_i\to\lambda_iP_i$, the expression must scale as $\lambda_i^{-\Delta_i}$ for each operator insertion.

**Gauge test for spin.** Under $Z_i\to Z_i+\beta_iP_i$, the expression must be invariant.

**Physical-section test.** After inserting $P(x)=(1,x^2,x)$ and $Z(x,z)=(0,2x\cdot z,z)$, the expression should reduce to the expected physical-space tensor structure.

These four checks catch most mistakes.

## AdS/CFT checkpoint

Embedding space is the natural notation for AdS/CFT because the CFT boundary and the AdS bulk live in the same ambient space:

$$
\text{boundary point: } P^2=0,
\qquad
\text{bulk point: } Y^2=-L^2.
$$

The first dictionary entries become nearly tautological:

$$
\mathcal O_\Delta(P)
\longleftrightarrow
\phi_\Delta(Y),
$$

$$
K_\Delta(Y,P)
\propto
(-2P\cdot Y)^{-\Delta},
$$

$$
m^2L^2=\Delta(\Delta-d).
$$

For correlators, the embedding formalism makes the symmetry constraints invisible in the best possible way: all expressions are built from $SO(d+1,1)$ invariants. Dynamics enters only through OPE coefficients, anomalous dimensions, and bulk couplings.

## Exercises

### Exercise 1

Show that the Poincare section

$$
P(x)=(1,x^2,x^\mu)
$$

satisfies $P(x)^2=0$ and $P_{ij}=x_{ij}^2$.

<details><summary><strong>Solution</strong></summary>

Using

$$
P\cdot Q=-\frac12(P^+Q^-+P^-Q^+)+P^\mu Q_\mu,
$$

we find

$$
P(x)^2=-P^+P^-+P^\mu P_\mu=-x^2+x^2=0.
$$

For two points,

$$
P_i\cdot P_j
=
-\frac12(x_i^2+x_j^2)+x_i\cdot x_j
=
-\frac12(x_i-x_j)^2.
$$

Therefore

$$
P_{ij}=-2P_i\cdot P_j=x_{ij}^2.
$$

</details>

### Exercise 2

Derive the scalar three-point function from projective homogeneity.

<details><summary><strong>Solution</strong></summary>

Assume

$$
\left\langle
\mathcal O_1(P_1)\mathcal O_2(P_2)\mathcal O_3(P_3)
\right\rangle
=
\frac{C_{123}}{P_{12}^{a}P_{13}^{b}P_{23}^{c}}.
$$

Under $P_1\to\lambda_1P_1$, the denominator scales as $\lambda_1^{a+b}$, so we need

$$
a+b=\Delta_1.
$$

Similarly,

$$
a+c=\Delta_2,
\qquad
b+c=\Delta_3.
$$

Solving gives

$$
a=\frac{\Delta_1+\Delta_2-\Delta_3}{2},
$$

$$
b=\frac{\Delta_1+\Delta_3-\Delta_2}{2},
$$

$$
c=\frac{\Delta_2+\Delta_3-\Delta_1}{2}.
$$

This is the stated three-point function.

</details>

### Exercise 3

Verify that

$$
\mathcal H_{12}=\frac{H_{12}}{P_{12}}
$$

reduces to $z_1\cdot I(x_{12})\cdot z_2$ on the Poincare section.

<details><summary><strong>Solution</strong></summary>

Use

$$
Z(x,z)=(0,2x\cdot z,z^\mu).
$$

Then

$$
Z_1\cdot Z_2=z_1\cdot z_2.
$$

Also,

$$
Z_1\cdot P_2= -z_1\cdot x_{12},
\qquad
Z_2\cdot P_1= z_2\cdot x_{12}.
$$

Therefore

$$
\frac{H_{12}}{P_{12}}
=
Z_1\cdot Z_2
+2\frac{(Z_1\cdot P_2)(Z_2\cdot P_1)}{P_{12}}
$$

becomes

$$
z_1\cdot z_2
-2\frac{(z_1\cdot x_{12})(z_2\cdot x_{12})}{x_{12}^2}.
$$

This is exactly

$$
z_1\cdot I(x_{12})\cdot z_2.
$$

</details>

### Exercise 4

Show that $V_{i,jk}$ is invariant under $Z_i\to Z_i+\beta P_i$.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta V_{i,jk}
=
\beta\frac{P_{ik}(P_i\cdot P_j)-P_{ij}(P_i\cdot P_k)}{P_{jk}}.
$$

Since

$$
P_i\cdot P_j=-\frac12P_{ij},
\qquad
P_i\cdot P_k=-\frac12P_{ik},
$$

we get

$$
\delta V_{i,jk}
=
\beta\frac{-\frac12P_{ik}P_{ij}+\frac12P_{ij}P_{ik}}{P_{jk}}=0.
$$

Thus $V_{i,jk}$ is gauge-invariant.

</details>

### Exercise 5

Using

$$
Y(z,x)=\left(\frac1z,\frac{z^2+x^2}{z},\frac{x^\mu}{z}\right),
$$

show that

$$
-2P(x')\cdot Y(z,x)=\frac{z^2+(x-x')^2}{z}.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
P(x')\cdot Y(z,x)
=
-\frac12\left(\frac{z^2+x^2}{z}+\frac{x'^2}{z}\right)
+\frac{x'\cdot x}{z}.
$$

Thus

$$
P(x')\cdot Y(z,x)
=
-\frac{z^2+x^2+x'^2-2x\cdot x'}{2z}
=
-\frac{z^2+(x-x')^2}{2z}.
$$

Multiplying by $-2$ gives

$$
-2P(x')\cdot Y(z,x)=\frac{z^2+(x-x')^2}{z}.
$$

Therefore

$$
(-2P(x')\cdot Y)^{-\Delta}
=
\left(\frac{z}{z^2+(x-x')^2}\right)^\Delta,
$$

which is the usual scalar bulk-to-boundary dependence.

</details>

## Further reading

For embedding-space notation in modern CFT and conformal bootstrap, see the standard papers and lecture notes on spinning correlators, conformal blocks, and shadow formalism. For holographic applications, compare these formulas with the embedding of Euclidean AdS as $Y^2=-L^2$ and the standard Witten-diagram building block $(-2P\cdot Y)^{-\Delta}$.
