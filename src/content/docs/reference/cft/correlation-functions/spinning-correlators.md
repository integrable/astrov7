---
title: "Spinning Correlators"
description: "Tensor structures, polarization-vector notation, conserved-current and stress-tensor correlators, and the AdS/CFT meaning of spin."
sidebar:
  order: 2
---

Scalar correlators are the cleanest place to learn conformal kinematics, but they hide an important part of the story. In any serious CFT, many of the most important operators carry spin:

$$
J_\mu,
\qquad
T_{\mu\nu},
\qquad
\mathcal O_{\mu_1\cdots \mu_\ell},
\qquad
\psi_\alpha.
$$

For AdS/CFT, spinning operators are unavoidable. A conserved current is dual to a bulk gauge field. The stress tensor is dual to the graviton. A spin-$\ell$ single-trace primary is dual, when the CFT has a weakly coupled bulk description, to a bulk field of spin $\ell$. The spin of the boundary operator is the spin seen by the AdS isometry group.

The central lesson is:

$$
\boxed{
\text{conformal symmetry fixes not only powers of distances, but also tensor structures.}
}
$$

The coefficients multiplying those structures are dynamical CFT data. In holography, they encode bulk kinetic terms and interaction vertices.

## Spinning primaries

We work in flat Euclidean space $\mathbb R^d$. A symmetric traceless spin-$\ell$ primary is an operator

$$
\mathcal O_{\mu_1\cdots \mu_\ell}(x)
$$

that is symmetric in its indices and traceless on every pair:

$$
\mathcal O_{\mu_1\cdots \mu_i\cdots \mu_j\cdots \mu_\ell}
=
\mathcal O_{\mu_1\cdots \mu_j\cdots \mu_i\cdots \mu_\ell},
$$

$$
\delta^{\mu_i\mu_j}
\mathcal O_{\mu_1\cdots \mu_i\cdots \mu_j\cdots \mu_\ell}=0.
$$

The word **spin** means representation of the rotation group $SO(d)$. In this page we focus on bosonic symmetric traceless tensors, because they are the operators most directly used for currents, stress tensors, higher-spin currents, and many bootstrap applications. Spinors and mixed-symmetry tensors obey the same general logic but require extra representation theory.

A spin-$\ell$ primary is labeled by

$$
\boxed{
\mathcal O_{\mu_1\cdots \mu_\ell}
\quad\Longleftrightarrow\quad
(\Delta,\ell,\mathcal R),
}
$$

where $\Delta$ is the scaling dimension, $\ell$ is the spacetime spin, and $\mathcal R$ is any internal global-symmetry representation.

At the origin, a primary is annihilated by special conformal transformations:

$$
[K_\mu,\mathcal O_{\mu_1\cdots \mu_\ell}(0)]=0.
$$

Descendants are obtained by acting with translations:

$$
P_{\nu_1}\cdots P_{\nu_n}
\mathcal O_{\mu_1\cdots \mu_\ell}(0)
\quad\Longleftrightarrow\quad
\partial_{\nu_1}\cdots\partial_{\nu_n}
\mathcal O_{\mu_1\cdots \mu_\ell}(0).
$$

Thus spin is not decoration. It is part of the conformal representation.

## Polarization-vector notation

Writing all tensor indices explicitly quickly becomes painful. The standard trick is to contract the operator with an auxiliary polarization vector $\zeta^\mu$:

$$
\boxed{
\mathcal O(x,\zeta)
=
\mathcal O_{\mu_1\cdots \mu_\ell}(x)
\zeta^{\mu_1}\cdots\zeta^{\mu_\ell}.
}
$$

The operator is homogeneous of degree $\ell$ in $\zeta$:

$$
\left(\zeta\cdot\partial_\zeta-\ell\right)\mathcal O(x,\zeta)=0.
$$

To impose tracelessness efficiently, take the auxiliary vector to be null:

$$
\boxed{
\zeta^2=0.
}
$$

Any trace term in the tensor would produce a factor of $\zeta^2$, and therefore vanish on the null cone. The null-polarization formalism stores exactly the symmetric traceless part.

For example,

$$
J(x,\zeta)=J_\mu(x)\zeta^\mu,
$$

$$
T(x,\zeta)=T_{\mu\nu}(x)\zeta^\mu\zeta^\nu,
\qquad
\zeta^2=0.
$$

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Index-free notation for spinning operators using auxiliary null polarizations](/figures/cft/spinning-correlators-polarization.svg)

<figcaption>

A symmetric traceless tensor can be encoded by the polynomial $\mathcal O_\ell(x,\zeta)$ with $\zeta^2=0$. The basic two-point tensor structure is built from the inversion tensor $I_{\mu\nu}(x)$ through $H_{12}=\zeta_1^\mu I_{\mu\nu}(x_{12})\zeta_2^\nu$.

</figcaption>
</figure>

When needed, explicit components can be recovered by differentiating with respect to $\zeta$ and projecting to the symmetric traceless part. In practice, most conformal correlators are clearer in polarization notation.

## Tensor primaries under conformal maps

Let $x\mapsto x'$ be a conformal transformation,

$$
\frac{\partial x'^\rho}{\partial x^\mu}
\frac{\partial x'^\sigma}{\partial x^\nu}
\delta_{\rho\sigma}
=
\Omega(x)^2\delta_{\mu\nu}.
$$

The Jacobian decomposes into a scale factor and a local rotation:

$$
\frac{\partial x'^\rho}{\partial x^\mu}
=
\Omega(x)R^\rho{}_{\mu}(x),
\qquad
R^\rho{}_{\mu}R^\sigma{}_{\nu}\delta_{\rho\sigma}=\delta_{\mu\nu}.
$$

A spin-$\ell$ primary transforms as

$$
\boxed{
\mathcal O'_{\mu_1\cdots \mu_\ell}(x')
=
\Omega(x)^{-\Delta}
R_{\mu_1}{}^{\nu_1}(x)\cdots
R_{\mu_\ell}{}^{\nu_\ell}(x)
\mathcal O_{\nu_1\cdots \nu_\ell}(x).
}
$$

For a scalar, the local rotations are absent. For tensors, conformal covariance has two jobs: it fixes scaling powers and rotates indices.

The most useful example is inversion,

$$
x'^\mu=\frac{x^\mu}{x^2}.
$$

Its Jacobian is

$$
\frac{\partial x'^\mu}{\partial x^\nu}
=
\frac1{x^2}
\left(
\delta^\mu{}_{\nu}
-
2\frac{x^\mu x_\nu}{x^2}
\right).
$$

The local rotation is the **inversion tensor**

$$
\boxed{
I_{\mu\nu}(x)
=
\delta_{\mu\nu}
-
2\frac{x_\mu x_\nu}{x^2}.
}
$$

It obeys

$$
I_{\mu\rho}(x)I_{\rho\nu}(x)=\delta_{\mu\nu},
\qquad
I_{\mu\nu}(x)=I_{\nu\mu}(x),
\qquad
I_{\mu\nu}(-x)=I_{\mu\nu}(x).
$$

The inversion tensor is the basic building block of spinning two-point functions.

## Two-point functions of spinning primaries

A two-point function of spinning primaries is fixed by translation, rotation, scale invariance, and inversion. For symmetric traceless spin-$\ell$ primaries, the answer is simplest in polarization notation:

$$
\boxed{
\left\langle
\mathcal O_i(x,\zeta_1)\mathcal O_j(0,\zeta_2)
\right\rangle
=
\frac{C_{ij}\left(\zeta_1\cdot I(x)\cdot\zeta_2\right)^\ell}{(x^2)^\Delta}.
}
$$

This is nonzero only when the two operators have the same dimension, the same spin, and conjugate global-symmetry quantum numbers. Otherwise the two-point function vanishes, apart from possible mixing inside degenerate subspaces.

Here

$$
\zeta_1\cdot I(x)\cdot\zeta_2
=
\zeta_1\cdot\zeta_2
-
2\frac{(\zeta_1\cdot x)(\zeta_2\cdot x)}{x^2}.
$$

For $\ell=0$, this reduces to the scalar two-point function:

$$
\left\langle\mathcal O_i(x)\mathcal O_j(0)\right\rangle
=
\frac{C_{ij}}{(x^2)^\Delta}.
$$

For $\ell=1$,

$$
\left\langle
\mathcal O_\mu(x)\mathcal O_\nu(0)
\right\rangle
=
\frac{C_{\mathcal O} I_{\mu\nu}(x)}{(x^2)^\Delta}.
$$

For $\ell=2$,

$$
\left\langle
\mathcal O_{\mu\nu}(x)\mathcal O_{\rho\sigma}(0)
\right\rangle
=
\frac{C_{\mathcal O}}{(x^2)^\Delta}
\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where

$$
\boxed{
\mathcal I_{\mu\nu,\rho\sigma}(x)
=
\frac12
\left(
I_{\mu\rho}(x)I_{\nu\sigma}(x)
+
I_{\mu\sigma}(x)I_{\nu\rho}(x)
\right)
-
\frac1d\delta_{\mu\nu}\delta_{\rho\sigma}.
}
$$

This tensor is symmetric in $\mu\leftrightarrow\nu$, symmetric in $\rho\leftrightarrow\sigma$, symmetric under exchanging the two index pairs, and traceless on either pair.

## Conserved currents

A conserved spin-$1$ current satisfies

$$
\partial^\mu J_\mu^a=0.
$$

In a unitary CFT, a conserved current is a shortened conformal multiplet. Its scaling dimension is fixed:

$$
\boxed{
\Delta_J=d-1.
}
$$

The two-point function is therefore

$$
\boxed{
\left\langle
J_\mu^a(x)J_\nu^b(0)
\right\rangle
=
\frac{C_J\delta^{ab}I_{\mu\nu}(x)}{(x^2)^{d-1}}.
}
$$

The constant $C_J$ is a genuine observable after one fixes the normalization of the symmetry generators. It is often called a **flavor central charge**. In AdS/CFT, $C_J$ is controlled by the kinetic term of the dual bulk gauge field.

At separated points, current conservation follows directly from the two-point function. With other operators inserted, the full Ward identity contains contact terms:

$$
\partial^\mu
\left\langle
J_\mu^a(x)\prod_i\mathcal O_i(x_i)
\right\rangle
=
-
\sum_i\delta^{(d)}(x-x_i)
\left\langle
\mathcal O_1(x_1)\cdots
(T_i^a\mathcal O_i)(x_i)\cdots
\right\rangle.
$$

Equivalently, near a charged operator,

$$
\boxed{
J_\mu^a(x)\mathcal O_i(0)
\sim
\frac1{S_{d-1}}\frac{x_\mu}{|x|^d}
(T^a)_i{}^j\mathcal O_j(0)
+\cdots,
}
$$

where

$$
S_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}
$$

is the area of the unit sphere $S^{d-1}$. The sign convention depends on whether the symmetry generators are taken Hermitian or anti-Hermitian. The invariant content is the flux of $J_\mu^a$ through a small sphere around the operator insertion.

## The stress tensor

The stress tensor is the conserved current for translations. In a CFT, after possible improvement terms, it is symmetric, conserved, and traceless:

$$
T_{\mu\nu}=T_{\nu\mu},
\qquad
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

As a conformal primary, it has

$$
\boxed{
\Delta_T=d,
\qquad
\ell_T=2.
}
$$

Its two-point function is fixed to be

$$
\boxed{
\left\langle
T_{\mu\nu}(x)T_{\rho\sigma}(0)
\right\rangle
=
\frac{C_T}{(x^2)^d}
\mathcal I_{\mu\nu,\rho\sigma}(x).
}
$$

The coefficient $C_T$ is the higher-dimensional analogue of a stress-tensor central charge. In a holographic CFT with an Einstein-gravity dual, it scales schematically as

$$
\boxed{
C_T\sim \frac{L^{d-1}}{G_N},
}
$$

up to convention-dependent numerical factors. Large $C_T$ is the boundary signal of a weakly coupled semiclassical gravitational sector.

The stress tensor Ward identity is

$$
\partial^\mu
\left\langle
T_{\mu\nu}(x)\prod_i\mathcal O_i(x_i)
\right\rangle
=
-
\sum_i\delta^{(d)}(x-x_i)
\frac{\partial}{\partial x_i^\nu}
\left\langle
\prod_i\mathcal O_i(x_i)
\right\rangle
+
\text{spin terms}.
$$

For scalar operators, there are no spin terms. For spinning operators, the spin terms implement the local rotation generated by the stress tensor.

The trace Ward identity in flat space is, at separated points,

$$
\left\langle
T^\mu{}_{\mu}(x)\prod_i\mathcal O_i(x_i)
\right\rangle=0.
$$

At coincident points there are contact terms implementing scale transformations of the inserted operators. On curved backgrounds there may also be Weyl-anomaly terms.

## Three-point functions with one spinning operator

The simplest spinning three-point function has two scalar operators and one symmetric traceless spin-$\ell$ operator. Define

$$
Y_3^\mu
=
\frac{x_{31}^\mu}{x_{31}^2}
-
\frac{x_{32}^\mu}{x_{32}^2}.
$$

Then conformal symmetry fixes

$$
\boxed{
\left\langle
\mathcal O_1(x_1)
\mathcal O_2(x_2)
\mathcal O_{\Delta,\ell}(x_3,\zeta)
\right\rangle
=
\frac{
\lambda_{12\mathcal O}
\left(\zeta\cdot Y_3\right)^\ell
}
{|x_{12}|^{\Delta_1+\Delta_2-\Delta+\ell}
 |x_{23}|^{\Delta_2+\Delta-\Delta_1-\ell}
 |x_{31}|^{\Delta+\Delta_1-\Delta_2-\ell}}
}
$$

at separated points. When $\ell=0$, this reduces to the scalar three-point function from the previous page.

Several useful facts follow immediately. First, there is only one parity-even tensor structure for two scalars and one symmetric traceless spin-$\ell$ operator. Second, if $\mathcal O_1=\mathcal O_2$ are identical bosonic scalars, exchanging $x_1\leftrightarrow x_2$ sends

$$
Y_3^\mu\mapsto -Y_3^\mu.
$$

The denominator is unchanged. Therefore

$$
\boxed{
\lambda_{\mathcal O\mathcal O\mathcal X_\ell}=0
\quad\text{for odd }\ell
}
$$

when $\mathcal O$ is a real identical scalar and $\mathcal X_\ell$ is a symmetric traceless operator with no additional antisymmetric internal tensor.

## General parity-even three-point structures

For three spinning symmetric traceless primaries, conformal symmetry allows finitely many tensor structures. Polarization notation makes the classification manageable.

For three points, define cyclically

$$
V_i
=
\zeta_i\cdot
\left(
\frac{x_{ij}}{x_{ij}^2}
-
\frac{x_{ik}}{x_{ik}^2}
\right),
\qquad
(i,j,k)=(1,2,3),(2,3,1),(3,1,2),
$$

and

$$
H_{ij}
=
\frac{\zeta_i\cdot\zeta_j}{x_{ij}^2}
-
2\frac{(\zeta_i\cdot x_{ij})(\zeta_j\cdot x_{ij})}{(x_{ij}^2)^2}.
$$

The object $V_i$ carries one polarization $\zeta_i$; the object $H_{ij}$ carries one $\zeta_i$ and one $\zeta_j$. These are the basic parity-even conformal building blocks.


Let the three spins be $\ell_1,\ell_2,\ell_3$, and define the twists

$$
\tau_i=\Delta_i-\ell_i.
$$

For nonnegative integers $n_{12},n_{13},n_{23}$, define

$$
m_1=\ell_1-n_{12}-n_{13},
$$

$$
m_2=\ell_2-n_{12}-n_{23},
$$

$$
m_3=\ell_3-n_{13}-n_{23}.
$$

Whenever all $m_i\geq0$, there is a parity-even tensor structure of the schematic form

$$
\boxed{
\mathcal T_{n_{12},n_{13},n_{23}}
=
\frac{
V_1^{m_1}V_2^{m_2}V_3^{m_3}
H_{12}^{n_{12}}H_{13}^{n_{13}}H_{23}^{n_{23}}
}
{|x_{12}|^{\tau_1+\tau_2-\tau_3}
 |x_{23}|^{\tau_2+\tau_3-\tau_1}
 |x_{31}|^{\tau_3+\tau_1-\tau_2}}
}
$$

up to convention-dependent signs and normalizations. A general three-point function is a sum over such structures:

$$
\left\langle
\mathcal O_1(x_1,\zeta_1)
\mathcal O_2(x_2,\zeta_2)
\mathcal O_3(x_3,\zeta_3)
\right\rangle
=
\sum_{n_{12},n_{13},n_{23}}
\lambda_{n_{12},n_{13},n_{23}}
\mathcal T_{n_{12},n_{13},n_{23}}.
$$

This expression says something important: **for spinning operators, a three-point coefficient is usually not a single number. It is a vector of coefficients, one for each independent tensor structure.**

In low dimensions, some structures become linearly dependent because of dimension-specific identities. In $d=3$, parity-odd structures built from $\epsilon_{\mu\nu\rho}$ can also appear. Conservation equations further reduce the number of independent coefficients.

## Ward identities fix special three-point coefficients

The coefficient in a generic spinning three-point function is dynamical. But when the spinning operator is a conserved current associated with an exact symmetry, the Ward identity can fix some coefficients.

For example, suppose $\mathcal O_i$ transforms under a global symmetry generated by $T^a$. The correlator

$$
\left\langle
J_\mu^a(x_1)
\mathcal O_i(x_2)
\mathcal O_j(x_3)
\right\rangle
$$

has the conformal form of a vector-scalar-scalar correlator. Its overall coefficient is fixed by the charge of $\mathcal O_i$ and the normalization of the scalar two-point function. This is the three-point version of the current OPE

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
\frac1{S_{d-1}}\frac{x_\mu}{|x|^d}
(T^a)_i{}^j\mathcal O_j(0)+\cdots.
$$

Similarly, the scalar-scalar-stress-tensor three-point function has one parity-even tensor structure:

$$
\left\langle
T_{\mu\nu}(x_1)
\mathcal O(x_2)\mathcal O(x_3)
\right\rangle
=
\frac{\lambda_{\mathcal O\mathcal O T}}
{|x_{12}|^{d-2} |x_{13}|^{d-2} |x_{23}|^{2\Delta-d+2}}
\left(
Y_\mu Y_\nu-\frac1d\delta_{\mu\nu}Y^2
\right),
$$

where

$$
Y_\mu
=
\frac{x_{12,\mu}}{x_{12}^2}
-
\frac{x_{13,\mu}}{x_{13}^2}.
$$

The Ward identity fixes $\lambda_{\mathcal O\mathcal O T}$ in terms of $\Delta$ and the normalization of $\langle\mathcal O\mathcal O\rangle$. A common convention gives

$$
\boxed{
\lambda_{\mathcal O\mathcal O T}
=
-
\frac{d\Delta}{(d-1)S_{d-1}}
C_{\mathcal O},
}
$$

where

$$
\left\langle\mathcal O(x)\mathcal O(0)\right\rangle
=
\frac{C_{\mathcal O}}{(x^2)^\Delta}.
$$

The sign depends on the convention for defining $T_{\mu\nu}$ and the Ward identity, but the proportionality to $\Delta C_{\mathcal O}$ is invariant. In holography, this is the boundary statement that every bulk field couples universally to the graviton.

## Unitarity bounds and shortening

Spinning operators are constrained by unitarity. For symmetric traceless tensors with $\ell\geq1$,

$$
\boxed{
\Delta\geq \ell+d-2.
}
$$

When the bound is saturated, the multiplet shortens:

$$
\Delta=\ell+d-2
\quad\Longrightarrow\quad
\partial^{\mu_1}\mathcal O_{\mu_1\mu_2\cdots \mu_\ell}=0.
$$

For $\ell=1$, this gives a conserved current:

$$
\Delta=d-1.
$$

For $\ell=2$, it gives the stress tensor:

$$
\Delta=d.
$$

For $\ell>2$, an exactly conserved higher-spin current is extremely restrictive. In an interacting CFT with a unique stress tensor, the presence of exactly conserved higher-spin currents usually signals a free or higher-spin-symmetric theory. This is why large-$N$ holographic CFTs with local Einstein-like bulk duals do not have light exactly massless higher-spin fields beyond the graviton and gauge fields; their higher-spin single-trace operators acquire anomalous dimensions.

## Spinning four-point functions

For four-point functions, spinning tensor structures multiply functions of cross-ratios. Schematically,

$$
\left\langle
\mathcal O_1(x_1,\zeta_1)
\mathcal O_2(x_2,\zeta_2)
\mathcal O_3(x_3,\zeta_3)
\mathcal O_4(x_4,\zeta_4)
\right\rangle
=
\sum_A
\mathcal T_A(x_i,\zeta_i)
\mathcal G_A(u,v),
$$

where

$$
u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The index $A$ labels independent tensor structures. Crossing symmetry mixes the functions $\mathcal G_A(u,v)$. This is why spinning bootstrap problems are more complicated than scalar bootstrap problems: crossing becomes a matrix equation among tensor structures.

In AdS/CFT, these tensor structures are the boundary shadows of bulk cubic and quartic vertices involving spin. For example, $\langle JJJJ\rangle$ knows about bulk gauge interactions, while $\langle TTTT\rangle$ knows about graviton interactions and higher-derivative corrections to the bulk gravitational action.

## AdS/CFT checkpoint

The most important spinning operators for holography are

$$
\boxed{
J_\mu^a
\longleftrightarrow
A_M^a
}
$$

for global symmetries and bulk gauge fields,

$$
\boxed{
T_{\mu\nu}
\longleftrightarrow
g_{MN}
}
$$

for the stress tensor and the bulk metric, and

$$
\boxed{
\mathcal O_{\mu_1\cdots\mu_\ell}
\longleftrightarrow
\Phi_{M_1\cdots M_\ell}
}
$$

for more general spin-$\ell$ bulk fields.

The two-point coefficients determine bulk kinetic terms schematically as

$$
C_J\sim \frac{L^{d-3}}{g_{d+1}^2},
\qquad
C_T\sim \frac{L^{d-1}}{G_N}.
$$

Three-point tensor structures determine possible cubic couplings. Conservation of $J_\mu$ becomes bulk gauge invariance. Conservation of $T_{\mu\nu}$ becomes bulk diffeomorphism invariance. Violating these conservation laws would mean that the corresponding bulk gauge symmetry is absent or broken.

This is one of the deepest lessons of AdS/CFT:

$$
\boxed{
\text{bulk gauge redundancy is encoded as boundary current conservation.}
}
$$

## Common pitfalls

A spinning correlator is not fixed by dimensional analysis alone. The tensor structures matter as much as the powers of $|x_{ij}|$.

Another common mistake is to treat $C_J$ and $C_T$ as completely analogous to scalar two-point normalizations. A scalar operator can be rescaled freely:

$$
\mathcal O\mapsto \lambda\mathcal O.
$$

But $J_\mu$ and $T_{\mu\nu}$ have canonical normalizations once their Ward identities are fixed. You cannot freely rescale the stress tensor without changing the definition of translations, and you cannot freely rescale a current without changing the normalization of the charge.

A third common mistake is to ignore contact terms. Conservation equations are true at separated points, but Ward identities include delta functions at operator insertions. These contact terms encode charges, dimensions, spin, and translations.

Finally, parity matters. In $d=3$, parity-odd structures may appear in current and stress-tensor correlators. These structures are especially important in Chern-Simons-matter theories and in holographic models with parity-violating bulk interactions.

## Exercises

### Exercise 1. Properties of the inversion tensor

Show that

$$
I_{\mu\rho}(x)I_{\rho\nu}(x)=\delta_{\mu\nu}.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2n_\mu n_\nu,
\qquad
n_\mu=\frac{x_\mu}{|x|}.
$$

Then $n^2=1$, and

$$
I_{\mu\rho}I_{\rho\nu}
=
(\delta_{\mu\rho}-2n_\mu n_\rho)
(\delta_{\rho\nu}-2n_\rho n_\nu).
$$

Expanding gives

$$
I_{\mu\rho}I_{\rho\nu}
=
\delta_{\mu\nu}
-2n_\mu n_\nu
-2n_\mu n_\nu
+4n_\mu(n_\rho n_\rho)n_\nu.
$$

Since $n_\rho n_\rho=1$, the last three terms cancel. Therefore

$$
I_{\mu\rho}I_{\rho\nu}=\delta_{\mu\nu}.
$$

</details>

### Exercise 2. Current conservation fixes the vector two-point exponent

Consider

$$
G_{\mu\nu}(x)=\frac{I_{\mu\nu}(x)}{(x^2)^\alpha}.
$$

Show that $\partial^\mu G_{\mu\nu}=0$ at separated points if and only if $\alpha=d-1$.

<details><summary><strong>Solution</strong></summary>

First compute

$$
\partial^\mu I_{\mu\nu}(x)
=
-2(d-1)\frac{x_\nu}{x^2}.
$$

Also,

$$
\partial^\mu (x^2)^{-\alpha}
=
-2\alpha x^\mu (x^2)^{-\alpha-1}.
$$

Using

$$
x^\mu I_{\mu\nu}(x)=-x_\nu,
$$

we find

$$
\partial^\mu
\left[
\frac{I_{\mu\nu}(x)}{(x^2)^\alpha}
\right]
=
\frac{-2(d-1)x_\nu}{(x^2)^{\alpha+1}}
+
\frac{2\alpha x_\nu}{(x^2)^{\alpha+1}}.
$$

Thus

$$
\partial^\mu G_{\mu\nu}(x)
=
2(\alpha-d+1)\frac{x_\nu}{(x^2)^{\alpha+1}}.
$$

This vanishes at separated points precisely when

$$
\alpha=d-1.
$$

Therefore a conserved vector two-point function has denominator $(x^2)^{d-1}$, meaning $\Delta_J=d-1$.

</details>

### Exercise 3. Odd spins in the OPE of identical scalars

Let $\phi$ be a real scalar primary. Use the formula for

$$
\left\langle
\phi(x_1)\phi(x_2)\mathcal O_{\Delta,\ell}(x_3,\zeta)
\right\rangle
$$

to show that a parity-even symmetric traceless operator of odd spin cannot appear in the $\phi\times\phi$ OPE.

<details><summary><strong>Solution</strong></summary>

For two identical scalars, the three-point function is proportional to

$$
(\zeta\cdot Y_3)^\ell,
$$

where

$$
Y_3^\mu
=
\frac{x_{31}^\mu}{x_{31}^2}
-
\frac{x_{32}^\mu}{x_{32}^2}.
$$

Under exchanging the two identical scalar insertions, $x_1\leftrightarrow x_2$, we get

$$
Y_3^\mu\mapsto -Y_3^\mu.
$$

The denominator is unchanged because $\Delta_1=\Delta_2$. Therefore the correlator transforms as

$$
(\zeta\cdot Y_3)^\ell\mapsto (-1)^\ell(\zeta\cdot Y_3)^\ell.
$$

But the correlator of identical bosonic scalars must be symmetric under $x_1\leftrightarrow x_2$. Thus for odd $\ell$ the coefficient must vanish:

$$
\lambda_{\phi\phi\mathcal O_\ell}=0,
\qquad
\ell\text{ odd}.
$$

</details>

### Exercise 4. The stress-tensor two-point tensor is traceless

Show that

$$
\delta^{\mu\nu}\mathcal I_{\mu\nu,\rho\sigma}(x)=0.
$$

<details><summary><strong>Solution</strong></summary>

Recall

$$
\mathcal I_{\mu\nu,\rho\sigma}(x)
=
\frac12
\left(
I_{\mu\rho}I_{\nu\sigma}
+
I_{\mu\sigma}I_{\nu\rho}
\right)
-
\frac1d\delta_{\mu\nu}\delta_{\rho\sigma}.
$$

Contract with $\delta^{\mu\nu}$:

$$
\delta^{\mu\nu}\mathcal I_{\mu\nu,\rho\sigma}
=
\frac12
\left(
I^\nu{}_{\rho}I_{\nu\sigma}
+
I^\nu{}_{\sigma}I_{\nu\rho}
\right)
-
\frac1d\delta^{\mu\nu}\delta_{\mu\nu}\delta_{\rho\sigma}.
$$

Using

$$
I^\nu{}_{\rho}I_{\nu\sigma}=\delta_{\rho\sigma},
$$

and similarly for the second term, we obtain

$$
\delta^{\mu\nu}\mathcal I_{\mu\nu,\rho\sigma}
=
\frac12(\delta_{\rho\sigma}+\delta_{\rho\sigma})
-
\delta_{\rho\sigma}=0.
$$

Thus the stress-tensor two-point function is traceless on either index pair.

</details>

### Exercise 5. Flux of a current around a charged operator

Assume the OPE

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
\frac1{S_{d-1}}\frac{x_\mu}{|x|^d}
(T^a)_i{}^j\mathcal O_j(0).
$$

Show that integrating $J_\mu^a$ over a small sphere around the origin gives the charge action on $\mathcal O_i$.

<details><summary><strong>Solution</strong></summary>

Let $S^{d-1}_\epsilon$ be a sphere of radius $\epsilon$ around the origin. The outward surface element is

$$
dS^\mu=n^\mu\epsilon^{d-1}d\Omega,
\qquad
x^\mu=\epsilon n^\mu,
\qquad
n^2=1.
$$

Using the OPE,

$$
\int_{S^{d-1}_\epsilon} dS^\mu J_\mu^a(x)\mathcal O_i(0)
\sim
\frac1{S_{d-1}}
\int d\Omega\,
\epsilon^{d-1}n^\mu
\frac{\epsilon n_\mu}{\epsilon^d}
(T^a)_i{}^j\mathcal O_j(0).
$$

Since $n^\mu n_\mu=1$,

$$
\int_{S^{d-1}_\epsilon} dS^\mu J_\mu^a(x)\mathcal O_i(0)
\sim
\frac1{S_{d-1}}
\int d\Omega\,(T^a)_i{}^j\mathcal O_j(0).
$$

The area of the unit sphere $S^{d-1}$ is $S_{d-1}$, so

$$
\int_{S^{d-1}_\epsilon} dS^\mu J_\mu^a(x)\mathcal O_i(0)
\sim
(T^a)_i{}^j\mathcal O_j(0).
$$

Thus the charge

$$
Q^a=\int_{S^{d-1}}dS^\mu J_\mu^a
$$

acts on the local operator as the symmetry generator $T^a$.

</details>

## Takeaway

Spinning correlators are fixed by two ingredients:

$$
\boxed{
\text{conformal covariance}
+
\text{tensor representation theory}.
}
$$

For two-point functions,

$$
\left\langle
\mathcal O(x,\zeta_1)\mathcal O(0,\zeta_2)
\right\rangle
=
\frac{C_{\mathcal O}(\zeta_1\cdot I(x)\cdot\zeta_2)^\ell}{(x^2)^\Delta}.
$$

For conserved currents and the stress tensor,

$$
\Delta_J=d-1,
\qquad
\Delta_T=d,
$$

and

$$
C_J\leftrightarrow \text{bulk gauge kinetic term},
\qquad
C_T\leftrightarrow \text{bulk Newton constant}.
$$

Three-point functions of spinning operators contain finitely many tensor structures, each with its own coefficient. These coefficients are CFT data. In AdS/CFT, they are the boundary encoding of bulk cubic interactions involving gauge fields, gravitons, and higher-spin fields.

## Further reading

For the classic two-dimensional treatment of tensor fields, Ward identities, and the stress tensor, see Di Francesco, Mathieu, and Sénéchal, Chapters 4--6. For modern higher-dimensional spinning correlator technology, see Costa, Penedones, Poland, and Rychkov on spinning conformal correlators, and Simmons-Duffin's TASI lectures. For holographic applications, compare the current and stress-tensor two-point normalizations with the quadratic action for bulk gauge fields and gravitons.
