---
title: "Conformal Generators"
description: "Explains the conformal generators as vector fields, conserved charges, and operators acting on primary fields and descendants."
sidebar:
  label: "Conformal Generators"
  order: 6
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Coleman 1985"
topics:
  - conformal generators
  - primary operators
  - descendant operators
  - radial quantization
  - stress tensor charges
  - conformal Ward identities
canonicalTopics:
  - conformal-generators
  - primary-descendant-structure
  - radial-quantization
  - stress-tensor-charges
researchStatus:
  established:
    - 'The global conformal generators $P_\mu$, $M_{\mu\nu}$, $D$, and $K_\mu$ generate translations, rotations or Lorentz transformations, dilatations, and special conformal transformations.'
    - 'In radial quantization, $D$ grades states by scaling dimension, $P_\mu$ raises the grade by one, and $K_\mu$ lowers it by one.'
  active:
    - "The generator algebra is standard; active uses include spinning correlators, conformal defects, Lorentzian inversion formulas, celestial CFT, and automated conformal-block generation."
---

## Summary

The conformal generators are the infinitesimal operators behind conformal symmetry. In flat $d$-dimensional CFT the global generators are

$$
P_\mu,
\qquad
M_{\mu\nu}=-M_{\nu\mu},
\qquad
D,
\qquad
K_\mu.
$$

They generate translations, rotations or Lorentz transformations, dilatations, and special conformal transformations. The commutators most responsible for CFT representation theory are

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}
$$

in the Euclidean radial-quantization conventions used in this volume.

The same symbols have three closely related meanings. Geometrically, they are vector fields on spacetime. Dynamically, they are conserved charges built from the stress tensor. Spectrally, they act on states created by local operators. The third interpretation is the one used most heavily in the conformal bootstrap:

$$
K_\mu|\mathcal O\rangle=0,
\qquad
D|\mathcal O\rangle=\Delta |\mathcal O\rangle,
\qquad
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
\quad\text{are descendants.}
$$

:::note[The ladder picture]
A conformal multiplet is a ladder. The primary state sits at the bottom, $P_\mu$ climbs upward by increasing the scaling dimension, and $K_\mu$ climbs downward. The commutator $[K,P]$ measures where you are on the ladder.
:::

<figure class="doc-figure" style="--figure-width: 34rem;">

![Conformal generator ladder](/figures/cft-bootstrap/conformal-generator-ladder.svg)

<figcaption>

In radial quantization, $D$ grades the Hilbert space, $P_\mu$ raises the scaling dimension, $K_\mu$ lowers it, and $M_{\mu\nu}$ rotates states inside each level. A primary sits at the bottom of the multiplet because it is annihilated by all $K_\mu$.

</figcaption>
</figure>

## Prerequisites

You should know the [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/), the finite maps in [Finite Conformal Transformations](/cft-bootstrap/conformal-symmetry/finite-conformal-transformations/), and the infinitesimal origin of the algebra from the [Conformal Killing Equation](/cft-bootstrap/conformal-symmetry/conformal-killing-equation/). It is also helpful to know the role of local operators from [Local Operators as Observables](/cft-bootstrap/what-is-a-cft/local-operators-as-observables/).

This page uses Euclidean notation unless stated otherwise. Lorentzian formulas are obtained by replacing $\delta_{\mu\nu}$ with $\eta_{\mu\nu}$ and rotations with Lorentz transformations. Factors of $i$ depend on whether generators are represented as Hermitian quantum charges or as real differential operators. We keep the bootstrap/radial-quantization convention used in [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/).

## Core idea

The generator dictionary is

| Generator | Geometric transformation | Effect in radial quantization |
|---|---|---|
| $P_\mu$ | translation | raises dimension by $1$ |
| $M_{\mu\nu}$ | rotation or Lorentz transformation | changes spin indices inside a level |
| $D$ | scale transformation | measures scaling dimension |
| $K_\mu$ | special conformal transformation | lowers dimension by $1$ |

The geometric part comes from the conformal Killing vector

$$
\xi^\mu(x)=a^\mu+\omega^\mu{}_{\nu}x^\nu+\lambda x^\mu+2(b\cdot x)x^\mu-b^\mu x^2.
$$

The spectral part follows from the commutators with $D$:

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu.
$$

If $|\text{state}\rangle$ has $D$-eigenvalue $\Delta$, then $P_\mu|\text{state}\rangle$ has eigenvalue $\Delta+1$, while $K_\mu|\text{state}\rangle$ has eigenvalue $\Delta-1$, unless the relevant state vanishes.

## Setup and conventions

We work in flat Euclidean space with coordinates $x^\mu$ and metric $\delta_{\mu\nu}$. The global conformal algebra is generated by

$$
P_\mu,
\qquad
M_{\mu\nu},
\qquad
D,
\qquad
K_\mu.
$$

The convention is

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}.
$$

This convention is useful because it directly says that $P_\mu$ raises and $K_\mu$ lowers scaling dimension.

There is a parallel coordinate-vector-field convention, often written

$$
\begin{aligned}
p_\mu &= \partial_\mu,\\
m_{\mu\nu} &= x_\mu\partial_\nu-x_\nu\partial_\mu,\\
d &= x\cdot\partial,\\
k_\mu &= 2x_\mu x\cdot\partial-x^2\partial_\mu.
\end{aligned}
$$

These are geometric vector fields. The action of charges on local operators differs by the usual active-versus-passive sign and by terms that act on scaling dimension and spin. Whenever a sign looks mysterious, first ask whether the formula is a coordinate vector field, an operator variation, or a Hilbert-space charge. This saves a heroic amount of avoidable pain.

## Generators as vector fields

The infinitesimal coordinate transformation

$$
x^\mu\mapsto x'^\mu=x^\mu+\xi^\mu(x)
$$

is conformal when $\xi^\mu$ solves the conformal Killing equation

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
\frac{2}{d}(\partial\cdot \xi)\delta_{\mu\nu}.
$$

For $d>2$, the flat-space solutions are exactly

$$
\xi^\mu(x)=a^\mu+\omega^\mu{}_{\nu}x^\nu+\lambda x^\mu+2(b\cdot x)x^\mu-b^\mu x^2.
$$

The corresponding vector fields are:

| Parameter | Vector field | Name |
|---|---|---|
| $a^\mu$ | $a^\mu\partial_\mu$ | translation |
| $\omega_{\mu\nu}$ | $\omega^\mu{}_{\nu}x^\nu\partial_\mu$ | rotation |
| $\lambda$ | $\lambda x^\mu\partial_\mu$ | dilatation |
| $b^\mu$ | $(2(b\cdot x)x^\mu-b^\mu x^2)\partial_\mu$ | special conformal transformation |

The special conformal vector field vanishes at the origin:

$$
\xi_K^\mu(0)=0.
$$

This observation becomes important in the operator formalism: at the origin, special conformal transformations do not move a primary insertion point. Instead, they test whether the operator is primary or descendant.

## Generators as stress-tensor charges

In a local QFT, continuous spacetime symmetries are generated by charges built from the stress tensor. For a conformal Killing vector $\xi^\mu$, define the current

$$
j_\xi^\mu=T^{\mu}{}_{\nu}\xi^\nu.
$$

Its divergence is

$$
\partial_\mu j_\xi^\mu
=
(\partial_\mu T^{\mu}{}_{\nu})\xi^\nu+T^{\mu\nu}\partial_\mu\xi_\nu.
$$

If the stress tensor is conserved and symmetric, and if the theory has an improved traceless stress tensor,

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
T^{\mu\nu}=T^{\nu\mu},
\qquad
T^\mu{}_{\mu}=0,
$$

then the conformal Killing equation implies

$$
\partial_\mu j_\xi^\mu=0.
$$

Thus translations, rotations, dilatations, and special conformal transformations all have conserved charges. In Lorentzian signature, on a constant-time slice, these charges are schematically

$$
Q_\xi=\int d^{d-1}\mathbf x\,T^{0}{}_{\nu}\xi^\nu.
$$

The four standard charge families are therefore moments of the stress tensor:

$$
\begin{aligned}
P_\nu &\sim \int d^{d-1}\mathbf x\,T^{0}{}_{\nu},\\
M_{\mu\nu} &\sim \int d^{d-1}\mathbf x\,(x_\mu T^{0}{}_{\nu}-x_\nu T^{0}{}_{\mu}),\\
D &\sim \int d^{d-1}\mathbf x\,x^\nu T^{0}{}_{\nu},\\
K_\mu &\sim \int d^{d-1}\mathbf x\,(2x_\mu x^\nu-x^2\delta_\mu{}^\nu)T^{0}{}_{\nu}.
\end{aligned}
$$

The symbol $\sim$ hides signature, orientation, and equal-time commutator conventions. The important point is structural: conformal charges are stress-tensor moments. This is why the stress tensor is the operator that knows about spacetime symmetry.

:::caution[Traceless stress tensor is not optional]
For translations and rotations, conservation of $T_{\mu\nu}$ is enough. For dilatations and special conformal transformations, the trace matters. If $T^\mu{}_{\mu}$ cannot be improved to zero, the conformal charges are not conserved.
:::

## Acting on scalar primary operators

Let $\mathcal O(x)$ be a scalar primary of dimension $\Delta$. A conformal transformation generated by $\xi^\mu$ acts infinitesimally as

$$
\delta_\xi \mathcal O(x)
=
-\xi^\mu(x)\partial_\mu\mathcal O(x)-\Delta\sigma(x)\mathcal O(x),
$$

where

$$
\sigma(x)=\frac{1}{d}\partial_\mu\xi^\mu(x).
$$

For the elementary transformations this becomes

$$
\begin{aligned}
\delta_P\mathcal O(x)&=-a^\mu\partial_\mu\mathcal O(x),\\
\delta_M\mathcal O(x)&=-\omega^\mu{}_{\nu}x^\nu\partial_\mu\mathcal O(x),\\
\delta_D\mathcal O(x)&=-\lambda(x\cdot\partial+\Delta)\mathcal O(x),\\
\delta_K\mathcal O(x)&=-\left(2(b\cdot x)x^\mu-b^\mu x^2\right)\partial_\mu\mathcal O(x)-2\Delta(b\cdot x)\mathcal O(x).
\end{aligned}
$$

Thus, as differential operators on scalar-primary insertions, one may write

$$
\begin{aligned}
\mathcal P_\mu&=-\partial_\mu,\\
\mathcal M_{\mu\nu}&=x_\mu\partial_\nu-x_\nu\partial_\mu,\\
\mathcal D&=-(x\cdot\partial+\Delta),\\
\mathcal K_\mu&=-\left(2x_\mu x\cdot\partial-x^2\partial_\mu+2\Delta x_\mu\right).
\end{aligned}
$$

This representation is often the fastest way to derive the form of two- and three-point functions. Translation and rotation invariance say that a scalar two-point function depends only on $x_{12}^2$. Dilatation covariance then fixes its power. Special conformal covariance removes the remaining freedom unless the dimensions match.

## Acting on spinning primary operators

A spinning primary has indices transforming in a representation of $SO(d)$ in Euclidean signature or $SO(d-1,1)$ in Lorentzian signature. Let $\Sigma_{\mu\nu}$ denote the spin matrices acting on those indices. Then the rotation generator contains an orbital and an intrinsic part:

$$
\mathcal M_{\mu\nu}
=
x_\mu\partial_\nu-x_\nu\partial_\mu+\Sigma_{\mu\nu}.
$$

The special conformal generator also has a spin term:

$$
\mathcal K_\mu
=
-\left(2x_\mu x\cdot\partial-x^2\partial_\mu+2\Delta x_\mu+2x^\nu\Sigma_{\mu\nu}\right).
$$

For a vector primary $V_\rho(x)$, the spin matrices act by

$$
(\Sigma_{\mu\nu}V)_\rho
=
\delta_{\nu\rho}V_\mu-\delta_{\mu\rho}V_\nu.
$$

For symmetric traceless tensors, spin matrices act on each index and then project back to the symmetric traceless representation. In practice, spinning correlator calculations are often simplified with index-free polarization vectors, embedding-space notation, or differential operators. The generator principle is the same: orbital motion plus intrinsic spin.

## Primary states in radial quantization

Radial quantization turns radius into Euclidean time. A local operator at the origin creates a state on a sphere:

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

A primary state is annihilated by all special conformal generators:

$$
K_\mu|\mathcal O\rangle=0.
$$

It has definite scaling dimension and spin:

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
$$

and

$$
M_{\mu\nu}|\mathcal O\rangle
\quad\text{acts in the spin representation of }\mathcal O.
$$

Descendant states are obtained by applying translations:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle.
$$

Because $[D,P_\mu]=P_\mu$, an $n$th-level descendant has scaling dimension

$$
\Delta+n.
$$

Not every descendant is independent. Conservation equations, equations of motion in special theories, and null-state conditions can remove descendants. For example, if $J_\mu$ is a conserved current, then

$$
\partial^\mu J_\mu=0
$$

means that one level-one descendant vanishes. This shortening is visible algebraically as a null descendant.

## Why primary means lowest weight

The conformal algebra has a triangular structure in radial quantization:

$$
K_\mu \quad\text{lowers},
\qquad
D,M_{\mu\nu}\quad\text{measure and rotate},
\qquad
P_\mu \quad\text{raise}.
$$

A unitary theory cannot contain states of arbitrarily low dimension inside a normalizable conformal multiplet. Therefore a multiplet must begin with a state killed by the lowering operators:

$$
K_\mu|\mathcal O\rangle=0.
$$

This is the CFT analogue of a lowest-weight representation. It is the reason the bootstrap can organize every local operator into primary data plus descendants. Instead of summing over all local operators independently, one sums over primary conformal multiplets.

## Generator algebra and descendant norms

The mixed commutator lets us compute descendant norms without knowing any Lagrangian. In radial quantization the adjoint relation is

$$
P_\mu^\dagger=K_\mu,
$$

up to standard convention choices. For a scalar primary normalized by $\langle \mathcal O|\mathcal O\rangle=1$,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
\langle \mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Since $K_\mu|\mathcal O\rangle=0$,

$$
K_\mu P_\nu|\mathcal O\rangle
=
[K_\mu,P_\nu]|\mathcal O\rangle
=
2\delta_{\mu\nu}\Delta|\mathcal O\rangle
$$

for a scalar. Therefore

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}.
$$

Reflection positivity requires this matrix to be positive semidefinite, so a nontrivial scalar primary must have $\Delta\geq 0$. Higher-level and spinning descendants give stronger bounds. This is the algebraic beginning of the unitarity bounds used throughout CFT and bootstrap.

## Ward identity form

The generator action on a correlator is a Ward identity. If

$$
G_n=\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle,
$$

then global conformal invariance says

$$
\sum_{i=1}^n \mathcal G_i\,G_n=0
$$

for every global generator $\mathcal G$. For scalar primaries, the four equations are

$$
\sum_i \partial_{x_i^\mu}G_n=0,
$$

$$
\sum_i
\left(x_{i\mu}\partial_{x_i^\nu}-x_{i\nu}\partial_{x_i^\mu}\right)G_n=0,
$$

$$
\sum_i
\left(x_i\cdot\partial_{x_i}+\Delta_i\right)G_n=0,
$$

and

$$
\sum_i
\left(2x_{i\mu}x_i\cdot\partial_{x_i}-x_i^2\partial_{x_i^\mu}+2\Delta_i x_{i\mu}\right)G_n=0.
$$

For spinning operators, add the spin matrices to the rotation and special-conformal equations. These identities are the workhorses behind conformal kinematics: they fix two- and three-point functions up to constants and reduce four-point functions to functions of cross-ratios.

## Two dimensions as a special case

In two Euclidean dimensions, the local conformal algebra is infinite-dimensional. In complex coordinates, local conformal transformations are generated by holomorphic and antiholomorphic vector fields,

$$
\epsilon(z)\partial_z,
\qquad
\bar\epsilon(\bar z)\partial_{\bar z}.
$$

The global subalgebra corresponds to

$$
\epsilon(z)=a+bz+cz^2,
\qquad
\bar\epsilon(\bar z)=\bar a+\bar b\bar z+\bar c\bar z^2.
$$

Equivalently, it is generated by

$$
L_{-1},L_0,L_1,
\qquad
\bar L_{-1},\bar L_0,\bar L_1.
$$

The relation to higher-dimensional notation is schematic but useful:

$$
P \leftrightarrow L_{-1},\bar L_{-1},
\qquad
D,M \leftrightarrow L_0,\bar L_0,
\qquad
K \leftrightarrow L_1,\bar L_1.
$$

The full Virasoro algebra is a central extension of the local conformal transformations. This is why the global-generator story is only the opening move in two-dimensional CFT.

## Checks and uses

A good generator convention should pass four checks.

First, $P_\mu$ should translate insertions:

$$
[P_\mu,\mathcal O(x)]\propto \partial_\mu\mathcal O(x).
$$

Second, $D$ should measure the scaling dimension at the origin:

$$
[D,\mathcal O(0)]|0\rangle=\Delta\mathcal O(0)|0\rangle.
$$

Third, $K_\mu$ should annihilate a primary inserted at the origin:

$$
[K_\mu,\mathcal O(0)]|0\rangle=0.
$$

Fourth, the descendant norm computed from $P_\mu^\dagger=K_\mu$ should be positive in a unitary theory.

These checks are more than bookkeeping. They are the bridge from symmetry to spectral constraints, and from spectral constraints to bootstrap inequalities.

## Common pitfalls

**Mixing vector fields with charges.** The coordinate vector field $d=x\cdot\partial$ and the charge $D$ acting on states are related, but they are not literally the same operator. Signs and factors of $i$ depend on active/passive and Hermitian/anti-Hermitian conventions.

**Forgetting the scaling term.** A scalar primary does not transform only by moving its argument. It also gets the factor involving $\Delta\sigma(x)$. This term is what makes two-point functions have fixed powers.

**Treating all local operators as primaries.** Most local operators are descendants. The bootstrap sum is over primary multiplets, not over every derivative operator separately.

**Ignoring spin terms.** For spinning primaries, the generators include intrinsic spin matrices. Dropping them gives wrong Ward identities for vectors, tensors, currents, and the stress tensor.

**Assuming tracelessness of the stress tensor without checking improvement.** A scale-invariant theory may have a conserved dilatation current, but conformal generators require a suitable traceless stress tensor under the assumptions discussed in [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/).

## Relations to other pages

- [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/) states the full algebra and its identification with $\mathfrak{so}(d+1,1)$ or $\mathfrak{so}(d,2)$.
- [Conformal Casimir](/cft-bootstrap/conformal-symmetry/conformal-casimir/) packages the generators into an invariant operator whose eigenvalues label conformal multiplets.
- [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) develops the representation theory in a dedicated operators-and-states chapter.
- [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) explains why $P_\mu^\dagger=K_\mu$ and why scaling dimension becomes cylinder energy.
- [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/) derives the local and integrated Ward identities in more detail.
- [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) derives the full bounds from descendant positivity.

## Research status

The global generator algebra is settled mathematical infrastructure. Its standard uses in CFT include classifying local operators, deriving correlator kinematics, proving unitarity bounds, constructing conformal blocks, and formulating crossing equations.

Research-level complications arise when the same generators are used in less textbook settings: Lorentzian causal configurations, light-ray operators, defects and boundaries, spinning correlators, nonlocal operators, celestial bases, supersymmetric extensions, and automated conformal-block algorithms. In those settings the algebra is unchanged, but its representation on the relevant operator space can be subtle.

## Exercises

### Exercise 1: Check the dilatation commutator

Using the coordinate vector fields

$$
d=x^\rho\partial_\rho,
\qquad
p_\mu=\partial_\mu,
$$

compute $[d,p_\mu]$.

<details><summary><strong>Solution</strong></summary>

Act on a test function $f(x)$:

$$
[d,p_\mu]f
=
x^\rho\partial_\rho\partial_\mu f
-
\partial_\mu(x^\rho\partial_\rho f).
$$

The second term is

$$
\partial_\mu(x^\rho\partial_\rho f)
=
\delta_\mu{}^\rho\partial_\rho f+x^\rho\partial_\mu\partial_\rho f
=
\partial_\mu f+x^\rho\partial_\rho\partial_\mu f.
$$

Therefore

$$
[d,p_\mu]f=-\partial_\mu f,
$$

so

$$
[d,p_\mu]=-p_\mu.
$$

This is the vector-field convention. The radial-quantization charge convention used for states has $[D,P_\mu]=P_\mu$. The sign difference is the active-versus-passive convention.

</details>

### Exercise 2: Show that $P$ raises dimension

Suppose

$$
D|\psi\rangle=\Delta|\psi\rangle,
\qquad
[D,P_\mu]=P_\mu.
$$

Show that $P_\mu|\psi\rangle$ has dimension $\Delta+1$ if it is nonzero.

<details><summary><strong>Solution</strong></summary>

Compute

$$
D(P_\mu|\psi\rangle)
=
P_\mu D|\psi\rangle+[D,P_\mu]|\psi\rangle.
$$

Using the assumptions,

$$
D(P_\mu|\psi\rangle)
=
\Delta P_\mu|\psi\rangle+P_\mu|\psi\rangle
=
(\Delta+1)P_\mu|\psi\rangle.
$$

Thus $P_\mu|\psi\rangle$ has dimension $\Delta+1$, unless it vanishes.

</details>

### Exercise 3: Scalar level-one norm

Let $|\mathcal O\rangle$ be a scalar primary with

$$
K_\mu|\mathcal O\rangle=0,
\qquad
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
\qquad
\langle\mathcal O|\mathcal O\rangle=1.
$$

Using $P_\mu^\dagger=K_\mu$, show that

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle=2\Delta\delta_{\mu\nu}.
$$

<details><summary><strong>Solution</strong></summary>

By radial conjugation,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Since $K_\mu|\mathcal O\rangle=0$,

$$
K_\mu P_\nu|\mathcal O\rangle
=
[K_\mu,P_\nu]|\mathcal O\rangle.
$$

For a scalar primary, $M_{\mu\nu}|\mathcal O\rangle=0$, so

$$
[K_\mu,P_\nu]|\mathcal O\rangle
=
(2\delta_{\mu\nu}D-2M_{\mu\nu})|\mathcal O\rangle
=
2\Delta\delta_{\mu\nu}|\mathcal O\rangle.
$$

Taking the inner product with $\langle\mathcal O|$ gives the result.

</details>

### Exercise 4: Special conformal transformations at the origin

For the special conformal vector field

$$
\xi^\mu(x)=2(b\cdot x)x^\mu-b^\mu x^2,
$$

show that $\xi^\mu(0)=0$ and $\sigma(0)=0$, where $\sigma=(\partial\cdot\xi)/d$.

<details><summary><strong>Solution</strong></summary>

The vector field is quadratic in $x$, so immediately

$$
\xi^\mu(0)=0.
$$

Its divergence is

$$
\partial_\mu\xi^\mu=2d(b\cdot x),
$$

so

$$
\sigma(x)=2b\cdot x.
$$

Therefore $\sigma(0)=0$. This explains why the special conformal generator annihilates a primary insertion at the origin: it neither moves the insertion nor rescales it there. Descendant operators are different because derivatives at the origin transform nontrivially.

</details>

## References

- Philippe Di Francesco, Pierre Mathieu, and David Sénéchal, *Conformal Field Theory*, especially the chapters on global conformal invariance, two-dimensional conformal invariance, and the operator formalism.
- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for a modern bootstrap-oriented introduction to conformal generators, primaries, descendants, and unitarity.
- David Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for radial quantization, reflection positivity, conformal multiplets, and bootstrap conventions.
- David Poland, Slava Rychkov, and Alessandro Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” for the role of conformal generators in higher-dimensional bootstrap.
- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on dilatations, currents, Ward identities, and the relation between scale and conformal symmetry.

## Version history

- 2026-06-27: First polished draft. Sets generator conventions for the CFT and Bootstrap volume and connects vector fields, stress-tensor charges, primary states, descendants, and Ward identities.
