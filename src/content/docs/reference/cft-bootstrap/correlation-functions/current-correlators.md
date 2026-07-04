---
title: "Current Correlators"
description: "Explains correlation functions involving conserved spin-one currents, their Ward identities, normalization conventions, current central charges, and bootstrap role."
sidebar:
  label: "Current Correlators"
  order: 8
level: Graduate
status: "Polished draft"
source: "Osborn and Petkou 1994; Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - conserved currents
  - global symmetry
  - Ward identities
  - current correlators
  - conformal bootstrap
canonicalTopics:
  - current-correlators
  - conserved-spin-one-currents
  - current-ward-identities
  - current-two-point-normalization
  - global-symmetry-bootstrap
researchStatus:
  established:
    - "An ordinary continuous global symmetry in a local CFT is represented by a conserved spin-one current of dimension d minus one, and its correlators obey Ward identities that fix the symmetry action on charged local operators."
    - "Once the physical current is normalized so that its flux generates the symmetry algebra, the two-point coefficient C_J is theory-dependent CFT data."
  active:
    - "Current correlators enter mixed-correlator bootstrap systems, conformal collider bounds, current four-point functions, flavor central charges, and anomaly-sensitive background-field Ward identities."
---

## Summary

A conserved current $J^a_\mu$ is the local operator associated with an ordinary continuous global symmetry. The adjoint index $a$ labels a generator of the symmetry algebra. Conservation means

$$
\partial^\mu J^a_\mu=0
$$

away from other operator insertions. In a unitary CFT, a conserved spin-one primary saturates the spin-one unitarity bound, so its scaling dimension is protected:

$$
\Delta_J=d-1.
$$

Conformal symmetry and conservation fix the separated-point two-point function to

$$
\langle J^a_\mu(x)J^b_\nu(0)\rangle
=
\frac{C_J\,\delta^{ab}}{(x^2)^{d-1}}I_{\mu\nu}(x),
\qquad
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The coefficient $C_J$ is often called a current central charge or flavor central charge. That name is useful, but it is not self-contained: $C_J$ depends on the normalization of the current and on the normalization of the symmetry generators. The invariant object is the two-point formula together with the Ward identity that says what charge the current generates.

The current's defining property is its flux. If $\Sigma$ is a sphere surrounding a charged insertion, then

$$
Q^a(\Sigma)=\int_\Sigma dS^\mu\,J^a_\mu
$$

acts on the insertion by the representation matrix $t^a$. In a convention where $[Q^a,\mathcal O_i]=(t^a)_i{}^j\mathcal O_j$, the leading current OPE is

$$
J^a_\mu(x)\mathcal O_i(0)
\sim
\frac{x_\mu}{S_d(x^2)^{d/2}}(t^a)_i{}^j\mathcal O_j(0)+\cdots,
\qquad
S_d=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![Flux of a current through a sphere surrounding a charged operator](/figures/cft-bootstrap/current-ward-flux-sphere.svg)

<figcaption>

The flux of a conserved current through a small sphere surrounding $\mathcal O_i$ gives the symmetry action on that operator. Deforming the sphere through a correlator gives the current Ward identity and charge-selection rules.

</figcaption>
</figure>

:::note[One line to remember]
Conformal symmetry fixes the shape of current correlators; the Ward identity fixes the meaning and normalization of the current.
:::

## Prerequisites

You should know [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/), [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/), and [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/).

This page treats ordinary zero-form global symmetries: the charged objects are local operators. Higher-form symmetries act on extended operators and have their own higher-degree currents or topological charge operators. The analogy is powerful, but the formulas on this page should not be copied blindly to line and surface operators.

## Core idea

Current correlators combine three facts.

| Ingredient | Meaning |
|---|---|
| Spin-one conformal covariance | $J^a_\mu$ has the tensor structures of a vector primary. |
| Conservation | $\partial^\mu J^a_\mu=0$ at separated points and $\Delta_J=d-1$. |
| Charge action | Contact terms at insertions say how the symmetry acts on local operators. |

The subtle point is normalization. There are two common languages.

In the **physical normalization**, $Q^a=\int dS^\mu J^a_\mu$ acts with the chosen representation matrices $t^a$. Then the current–operator OPE is fixed, and $C_J$ is dynamical CFT data.

In the **unit-normalized bootstrap normalization**, one defines

$$
\widehat J^a_\mu=\frac{J^a_\mu}{\sqrt{C_J}},
$$

so that $\langle \widehat J\widehat J\rangle$ has coefficient one. Then the OPE coefficient of $\widehat J$ with charged operators contains a factor $1/\sqrt{C_J}$. Both languages are useful. Most mistakes come from silently switching between them.

## Setup and conventions

We work in flat Euclidean $\mathbb R^d$ at separated points unless contact terms are explicitly displayed. Lie-algebra generators are denoted $t^a$. The current is physically normalized by

$$
[Q^a,\mathcal O_i]=(t^a)_i{}^j\mathcal O_j.
$$

Some Lorentzian references instead write $\delta^a\mathcal O_i=i\alpha^a[Q^a,\mathcal O_i]$ with Hermitian generators. Some mathematical references use anti-Hermitian generators. These choices move signs and factors of $i$ between $Q^a$, $J^a_\mu$, and $t^a$; they do not change the physics.

The volume of the unit $(d-1)$-sphere is

$$
S_d=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

The distribution identity behind the current OPE is

$$
\partial_\mu\left(\frac{x^\mu}{S_d(x^2)^{d/2}}\right)=\delta^{(d)}(x).
$$

This is Gauss's law in Euclidean notation. It is why the leading singular coefficient in $J_\mu\mathcal O$ is fixed once the current has physical charge normalization.

## Two-point function and the coefficient C_J

For a vector primary $V_\mu$ of dimension $\Delta$, conformal covariance fixes

$$
\langle V_\mu(x)V_\nu(0)\rangle
=
\frac{C_V}{(x^2)^\Delta}I_{\mu\nu}(x).
$$

Taking the divergence at separated points gives

$$
\partial^\mu\left[\frac{I_{\mu\nu}(x)}{(x^2)^\Delta}\right]
=
2(\Delta-d+1)\frac{x_\nu}{(x^2)^{\Delta+1}}.
$$

Thus a conserved vector primary has $\Delta=d-1$. For a current in the adjoint of a simple symmetry group,

$$
\langle J^a_\mu(x)J^b_\nu(0)\rangle
=
\frac{C_J\delta^{ab}}{(x^2)^{d-1}}I_{\mu\nu}(x).
$$

For a product symmetry group, each simple factor and each independent Abelian factor can have its own current two-point coefficient. In a unitary CFT, $C_J>0$ for a nonzero current. Radial quantization sees this as positivity of the current state $J^a_\mu(0)|0\rangle$.

:::caution[Do not compare bare numbers called C_J]
If $t^a$ is rescaled, the physically normalized current and $C_J$ rescale. A quoted number called $C_J$ is meaningful only after the generator convention and current two-point tensor structure have been stated.
:::

## Ward identity and current OPE

The local Ward identity is

$$
\partial_\mu\langle J^{a\mu}(x)\mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle
=
\sum_{i=1}^n
\delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots (t_i^a\mathcal O_i)(x_i)\cdots \mathcal O_n\rangle,
$$

with the sign convention fixed by the definition of $Q^a$ above. At separated points, the divergence vanishes. The symmetry action lives in the contact terms.

The OPE version is obtained by shrinking a small sphere around $x_i$:

$$
J^a_\mu(x)\mathcal O_i(0)
\sim
\frac{x_\mu}{S_d(x^2)^{d/2}}(t^a)_i{}^j\mathcal O_j(0)+\text{less singular terms}.
$$

Integrating over a small sphere gives

$$
\int_{S_r^{d-1}}dS^\mu\,J^a_\mu(x)\mathcal O_i(0)
=
(t^a)_i{}^j\mathcal O_j(0),
$$

which is the charge action. For a $U(1)$ current and an operator of charge $q$,

$$
J_\mu(x)\mathcal O(0)
\sim
q\frac{x_\mu}{S_d(x^2)^{d/2}}\mathcal O(0)+\cdots.
$$

## Charge selection rules

Global symmetry invariance says that the total charge acting on a correlator vanishes:

$$
\sum_{i=1}^n t_i^a\,
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle=0.
$$

For $U(1)$ primary operators of definite charges $q_i$, this gives

$$
\left(\sum_{i=1}^n q_i\right)
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle=0.
$$

Thus a nonzero $U(1)$ correlator must have total charge zero. For non-Abelian symmetry, the correlator must be an invariant tensor in the product of the external representations.

For example,

$$
\langle \mathcal O_q(x_1)\mathcal O_q(x_2)\rangle=0
\qquad(q\neq0),
$$

while

$$
\langle \mathcal O_q(x_1)\mathcal O_{-q}(x_2)\rangle
$$

may be nonzero.

## Scalar-scalar-current correlators

The three-point function of two charged scalar primaries and a current is almost fixed before dynamics enters. Let $\mathcal O_i$ and $\mathcal O_j^\dagger$ have common scaling dimension $\Delta$ and two-point coefficient $C_\mathcal O$:

$$
\langle \mathcal O_i(x)\mathcal O_j^\dagger(0)\rangle
=
\frac{C_\mathcal O\delta_{ij}}{(x^2)^\Delta}.
$$

Conformal symmetry permits one parity-even vector structure:

$$
Z_\mu(x_3;x_1,x_2)=
\frac{(x_3-x_1)_\mu}{(x_3-x_1)^2}
-
\frac{(x_3-x_2)_\mu}{(x_3-x_2)^2}.
$$

With the current inserted at $x_3$, a convenient separated-point form is

$$
\langle \mathcal O_i(x_1)\mathcal O_j^\dagger(x_2)J^a_\mu(x_3)\rangle
=
\lambda_{\mathcal O\mathcal OJ}(t^a)_i{}^j
\frac{Z_\mu(x_3;x_1,x_2)}
{(x_{12}^2)^{\Delta-(d-2)/2}(x_{13}^2)^{(d-2)/2}(x_{23}^2)^{(d-2)/2}}.
$$

The Ward identity fixes

$$
\lambda_{\mathcal O\mathcal OJ}=\frac{C_\mathcal O}{S_d}
$$

in the physical current normalization used here. If the current is unit-normalized, then

$$
\lambda_{\mathcal O\mathcal O\widehat J}
=
\frac{C_\mathcal O}{S_d\sqrt{C_J}}.
$$

This is the main quantitative bridge between current correlators and bootstrap bounds. When the current appears as a unit-normalized exchanged operator, its OPE coefficient knows about $C_J$.

## Three-current correlators

The three-current correlator has the schematic form

$$
\langle J^a_\mu(x_1)J^b_\nu(x_2)J^c_\rho(x_3)\rangle.
$$

Internal symmetry restricts the adjoint-index structures. For a simple non-Abelian symmetry, antisymmetric tensors $f^{abc}$ are tied to the current algebra and Ward identities. If the group admits symmetric invariant tensors, structures involving $d^{abc}$ may also appear. In odd spacetime dimensions, parity-odd structures can occur when allowed by symmetry and regularization.

At separated points, conformal covariance fixes the position dependence up to finitely many tensor structures. Current conservation removes some combinations. At coincident points, the divergence has contact terms governed by the Lie algebra. Schematically,

$$
\partial^\mu\langle J^a_\mu(x)J^b_\nu(y)J^c_\rho(z)\rangle
=
f^{abd}\delta^{(d)}(x-y)\langle J^d_\nu(y)J^c_\rho(z)\rangle
+f^{acd}\delta^{(d)}(x-z)\langle J^b_\nu(y)J^d_\rho(z)\rangle
+\text{possible anomaly terms}.
$$

The anomaly phrase matters. An 't Hooft anomaly does not mean the global symmetry is absent. It means the symmetry cannot be consistently gauged, or equivalently that background-field Ward identities have controlled anomalous terms.

## Four-current correlators and bootstrap data

The four-current correlator is not fixed by symmetry. It decomposes into tensor structures multiplied by functions of cross-ratios:

$$
\langle J^a_\mu(x_1)J^b_\nu(x_2)J^c_\rho(x_3)J^d_\sigma(x_4)\rangle
=
\sum_A \mathcal T_A^{abcd}{}_{\mu\nu\rho\sigma}(x_i)\,G_A(u,v).
$$

The OPE in the $J^a\times J^b$ channel contains operators in representations appearing in

$$
\operatorname{Adj}\otimes\operatorname{Adj}.
$$

The identity appears in the singlet channel. The current itself appears in the adjoint channel because of the current algebra. The stress tensor appears because every local CFT with a stress tensor couples universally to energy and momentum. With unit-normalized exchanged operators, the protected current and stress-tensor OPE coefficients are tied to $C_J$ and $C_T$.

This is why current bootstrap systems are powerful. They combine conformal kinematics, spin, global-symmetry representation theory, positivity, and Ward-normalized protected exchanges.

## Two-dimensional current algebra

In two-dimensional CFT, conserved currents often split into holomorphic and antiholomorphic pieces:

$$
J^a_z(z),
\qquad
\bar J^a_{\bar z}(\bar z).
$$

A holomorphic affine current obeys an OPE of the form

$$
J^a(z)J^b(0)
\sim
\frac{k\delta^{ab}}{z^2}
+
\frac{i f^{abc}J^c(0)}{z}
+\cdots.
$$

The level $k$ is a two-dimensional current-normalization datum, but the structure is much stronger than the higher-dimensional $C_J$ story: the current modes generate an affine Kac–Moody algebra. This belongs later in [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) and [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/). The bridge to remember is

$$
C_J \text{ in higher dimensions}
\quad\longleftrightarrow\quad
k \text{ for chiral currents in two dimensions},
$$

with different conventions and additional two-dimensional algebraic structure.

## Current correlators and background fields

A clean way to organize current correlators is to couple the CFT to a nondynamical background gauge field $A^a_\mu$:

$$
\delta S=\int d^dx\,A^a_\mu J^{a\mu}.
$$

Current correlators are functional derivatives of the generating functional $W[A]$:

$$
\langle J^a_\mu(x)J^b_\nu(y)\rangle
=
\left.\frac{\delta^2W[A]}{\delta A^{a\mu}(x)\delta A^{b\nu}(y)}\right|_{A=0}
+
\text{contact convention terms}.
$$

Background gauge invariance of $W[A]$ is the compact source of the current Ward identities. If background gauge invariance cannot be preserved, the obstruction is an anomaly.

This viewpoint prevents a common category error: a global symmetry is not a gauge redundancy of the CFT. The background field is a source, not a dynamical field, unless one explicitly gauges the symmetry.

## Common pitfalls

**Confusing a vector primary with a current.** A vector primary of dimension $\Delta>d-1$ is not conserved and does not generate a global symmetry. A current has $\Delta=d-1$ and a Ward identity with contact terms.

**Forgetting contact terms.** The equation $\partial^\mu J^a_\mu=0$ is a separated-point statement. Ward identities for charged operators require delta functions at insertion points.

**Comparing $C_J$ without comparing generator normalization.** The number $C_J$ changes if $t^a$ is rescaled. Always state the Lie-algebra convention.

**Unit-normalizing $J$ and still using physical-charge OPE coefficients.** If $\widehat J=J/\sqrt{C_J}$, then OPE coefficients involving $\widehat J$ contain factors of $1/\sqrt{C_J}$.

**Treating anomalies as symmetry breaking.** An 't Hooft anomaly is not the absence of a global symmetry. It is an obstruction to gauging the symmetry, visible in background-field Ward identities.

**Importing two-dimensional current algebra into higher dimensions.** The affine OPE $J^a(z)J^b(0)\sim k\delta^{ab}/z^2+\cdots$ is special to chiral two-dimensional currents. Higher-dimensional currents have related Ward identities but not the same holomorphic algebra.

## Relations to other pages

[Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/) gives the tensor-structure technology used for current correlators. [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) is the spacetime-symmetry analog, with $T_{\mu\nu}$ replacing $J^a_\mu$. [Conformal Ward Identities for Correlators](/cft-bootstrap/correlation-functions/conformal-ward-identities-for-correlators/) explains how integrated Ward identities constrain correlator kinematics. [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) turns current correlators into current OPEs. [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) uses current exchanges and global-symmetry channels in bootstrap equations.

For higher-form symmetries, line operators, surface operators, and generalized charges, see the symmetry/anomalies/topology material rather than treating them as ordinary current correlators.

## Research status

The separated-point form of two- and three-point current correlators, current Ward identities, and current normalization logic are standard CFT technology. Current four-point functions and mixed-correlator systems are active in numerical bootstrap, especially in theories with non-Abelian global symmetry, supersymmetry, or conserved flavor currents.

Current correlators also sit at the boundary between CFT and anomaly theory. The modern generalized-symmetry viewpoint makes clear that ordinary currents are only one member of a larger family of topological charge operators and Ward identities. This page uses only the ordinary zero-form case.

## Exercises

### Exercise 1: Conservation of the current two-point function

Show that

$$
\partial^\mu\left[\frac{I_{\mu\nu}(x)}{(x^2)^{d-1}}\right]=0
$$

for $x\ne0$.

<details><summary><strong>Solution</strong></summary>

Write

$$
\frac{I_{\mu\nu}(x)}{(x^2)^{d-1}}
=
\frac{\delta_{\mu\nu}}{(x^2)^{d-1}}
-2\frac{x_\mu x_\nu}{(x^2)^d}.
$$

The divergence of the first term is

$$
\partial^\mu\frac{\delta_{\mu\nu}}{(x^2)^{d-1}}
=-2(d-1)\frac{x_\nu}{(x^2)^d}.
$$

For the second term, use

$$
\partial^\mu(x_\mu x_\nu)=(d+1)x_\nu,
\qquad
\partial^\mu(x^2)^{-d}=-2d x^\mu(x^2)^{-d-1}.
$$

Thus

$$
\partial^\mu\left(\frac{x_\mu x_\nu}{(x^2)^d}\right)
=(d+1)\frac{x_\nu}{(x^2)^d}
-2d\frac{x^2x_\nu}{(x^2)^{d+1}}
=-(d-1)\frac{x_\nu}{(x^2)^d}.
$$

Multiplying by $-2$ gives $+2(d-1)x_\nu/(x^2)^d$, which cancels the first term.

</details>

### Exercise 2: Abelian selection rule

Let $\mathcal O_i$ have $U(1)$ charges $q_i$. Use the integrated Ward identity to show that

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle=0
$$

unless $\sum_i q_i=0$.

<details><summary><strong>Solution</strong></summary>

For a $U(1)$ current, $t_i$ is multiplication by $q_i$. Integrating the Ward identity over all space gives

$$
0=\sum_i q_i\langle \mathcal O_1\cdots\mathcal O_n\rangle,
$$

assuming no boundary contribution at infinity and a symmetry-invariant vacuum. Therefore either the correlator vanishes or $\sum_iq_i=0$.

</details>

### Exercise 3: Flux normalization of the current OPE

Use

$$
\partial_\mu\left(\frac{x^\mu}{(x^2)^{d/2}}\right)=S_d\delta^{(d)}(x)
$$

to check that the coefficient $1/S_d$ in the current–operator OPE reproduces the charge contact term.

<details><summary><strong>Solution</strong></summary>

Integrate the OPE

$$
J_\mu(x)\mathcal O(0)
\sim
q\frac{x_\mu}{S_d(x^2)^{d/2}}\mathcal O(0)
$$

over a small sphere. Since $dS^\mu=x^\mu r^{d-2}d\Omega$ in the radial direction, the integral of $x_\mu/(x^2)^{d/2}$ over the sphere gives $S_d$. The coefficient $1/S_d$ leaves precisely $q\mathcal O(0)$, which is the charge action.

</details>

## References

- H. Osborn and A. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals of Physics* **231** (1994), for current and stress-tensor correlators in general dimension.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the chapters on Ward identities, currents, and affine current algebras in two dimensions.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for conserved currents, conformal multiplets, and CFT data conventions.
- D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for current normalization, Ward identities, reflection positivity, and bootstrap conventions.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), for global symmetry, currents, and numerical bootstrap applications.

## Version history

- **2026-06-27:** Added a polished first version explaining current Ward identities, current two-point normalization, scalar-current-scalar correlators, and bootstrap use of $C_J$.
