---
title: "Stress Tensor OPE"
description: "Derives the stress-tensor contribution to the operator product expansion, explains its Ward-identity normalization, and connects stress-tensor exchange to the central charge data used in bootstrap."
sidebar:
  label: "Stress Tensor OPE"
  order: 7
level: Graduate
status: "Polished draft"
source: "Osborn and Petkou 1994; Di Francesco et al. 1997; Rychkov 2016; Simmons-Duffin 2017; Poland et al. 2019"
topics:
  - conformal field theory
  - operator product expansion
  - stress tensor
  - Ward identities
  - central charge
  - bootstrap
canonicalTopics:
  - stress-tensor-ope
  - conformal-ward-identities
  - central-charge-data
  - stress-tensor-exchange
researchStatus:
  established:
    - "The stress tensor is a conserved spin-two primary of dimension d in an ordinary local CFT, and its leading singular OPE with local operators is fixed by conformal Ward identities."
    - "The coefficient of stress-tensor exchange in a scalar four-point function is fixed by the external scaling dimension and by the stress-tensor two-point normalization C_T, up to tensor-structure conventions."
  active:
    - "Stress-tensor correlators, energy-flux positivity, Lorentzian inversion, chaos bounds, and stress-tensor bootstrap systems remain major tools in current CFT research."
---

## Summary

The stress tensor $T_{\mu\nu}$ is the universal local operator that generates spacetime symmetries. In a $d$-dimensional CFT it is a conserved, symmetric, traceless spin-two primary,

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu_{\ \mu}=0,
\qquad
\Delta_T=d.
$$

There are two closely related OPE statements called “the stress-tensor OPE.”

First, the OPE of $T_{\mu\nu}$ with a local operator records how conformal charges act on that operator. For a scalar primary $\mathcal O$ of dimension $\Delta$, the leading singular term is

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
\frac{d\,\Delta}{(d-1)S_d}
\frac{x_\mu x_\nu-\frac1d\delta_{\mu\nu}x^2}{|x|^{d+2}}\,
\mathcal O(0)
+\cdots,
$$

where

$$
S_d=\frac{2\pi^{d/2}}{\Gamma(d/2)}
$$

is the area of the unit $(d-1)$-sphere. The sign convention here is that the charge

$$
Q_\xi=\int_{S^{d-1}}dS_\mu\,\xi_\nu T^{\mu\nu}
$$

acts on an operator enclosed by the small sphere as $+\delta_\xi\mathcal O$. Reversing the orientation of the sphere reverses the sign.

Second, the OPE of two ordinary operators often contains $T_{\mu\nu}$ as a universal exchanged primary. For a unit-normalized scalar $\phi$,

$$
\phi(x)\phi(0)
=
\frac{1}{|x|^{2\Delta_\phi}}\mathbf 1
+\text{coefficient fixed by Ward identities}\times T_{\mu\nu}(0)
+\cdots.
$$

The identity term is fixed by the two-point function. The stress-tensor term is fixed by $\Delta_\phi$ and the stress-tensor normalization $C_T$. This is why stress-tensor exchange is one of the first universal nontrivial entries in conformal-block decompositions.

<figure class="doc-figure" style="--figure-width: 39rem;">

![A stress-tensor flux sphere around a local operator implements a conformal Ward identity.](/figures/cft-bootstrap/stress-tensor-ope-charge-sphere.svg)

<figcaption>

The singular part of the $T_{\mu\nu}(x)\mathcal O(0)$ OPE is fixed by the requirement that the stress-tensor flux through a small sphere acts as the conformal charge on the enclosed operator.

</figcaption>
</figure>

## Prerequisites

You should know [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/), [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/), [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/), [Identity Operator in the OPE](/cft-bootstrap/operator-product-expansion/identity-operator-in-the-ope/), and [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/).

The page uses Euclidean flat-space CFT notation. Lorentzian signs and factors of $i$ depend on the continuation convention; the invariant content is the Ward identity.

## Core idea

The stress tensor is not just another spin-two operator. It is the Noether operator for translations, rotations, dilatations, and special conformal transformations. Therefore its singular OPEs are fixed by symmetry.

The guiding principle is

$$
\int_{S^{d-1}}dS_\mu\,\xi_\nu T^{\mu\nu}(x)\,\mathcal O(0)
=
\delta_\xi\mathcal O(0),
$$

where $\xi^\mu(x)$ is a conformal Killing vector and the small sphere encloses the operator at the origin. This one equation contains the translation, rotation, scale, and special-conformal Ward identities.

In two dimensions this becomes the familiar holomorphic OPE

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\,\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}.
$$

In higher dimensions the same idea is true, but the tensor structure is less compact.

## Setup and conventions

We define the stress-tensor two-point coefficient by

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=
\frac{C_T}{|x|^{2d}}\,
\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where

$$
\mathcal I_{\mu\nu,\rho\sigma}(x)
=
\frac12\left(I_{\mu\rho}(x)I_{\nu\sigma}(x)+I_{\mu\sigma}(x)I_{\nu\rho}(x)\right)
-\frac1d\delta_{\mu\nu}\delta_{\rho\sigma},
$$

and

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The coefficient $C_T$ is convention-dependent because it scales quadratically if $T_{\mu\nu}$ is rescaled. In a physical CFT, however, the stress tensor is normalized by its Ward identities, so $C_T$ is a genuine theory-dependent number. In $d=2$ it is proportional to the Virasoro central charge $c$; in higher dimensions $C_T$ is the standard stress-tensor two-point normalization used in bootstrap and energy-flux discussions.

A scalar primary obeys

$$
\mathcal O(x)\mapsto \Omega(x)^{-\Delta}\mathcal O(x')
$$

under a conformal map whose local scale factor is $\Omega(x)$, ignoring possible rotation matrices for spinning operators.

## Stress tensor with a scalar primary

Let $\mathcal O$ be a scalar primary of dimension $\Delta$. The most singular traceless symmetric tensor structure consistent with rotations is

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
A_\mathcal O
\frac{x_\mu x_\nu-\frac1d\delta_{\mu\nu}x^2}{|x|^{d+2}}\,
\mathcal O(0)+\cdots.
$$

The coefficient is fixed by the dilatation Ward identity. Use $\xi^\nu=x^\nu$ and integrate over a sphere of radius $r$:

$$
Q_D\mathcal O(0)
=
\int_{S_r^{d-1}}dS_\mu\,x_\nu T^{\mu\nu}(x)\mathcal O(0).
$$

Since $dS_\mu=r^{d-1}n_\mu d\Omega$ and $x_\mu=rn_\mu$,

$$
\int dS_\mu\,x_\nu
\frac{x^\mu x^\nu-\frac1d\delta^{\mu\nu}x^2}{|x|^{d+2}}
=
S_d\,\frac{d-1}{d}.
$$

Requiring $Q_D\mathcal O(0)=\Delta\mathcal O(0)$ gives

$$
A_\mathcal O=\frac{d\,\Delta}{(d-1)S_d}.
$$

Therefore

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
\frac{d\,\Delta}{(d-1)S_d}
\frac{x_\mu x_\nu-\frac1d\delta_{\mu\nu}x^2}{|x|^{d+2}}\,
\mathcal O(0)
+\cdots.
$$

The omitted terms are not optional decoration. They include derivative and spin-dependent terms required for translations, rotations, and special conformal transformations. The compact way to remember the full singular OPE is the charge-integral statement, not just the displayed leading term.

:::caution[Orientation and sign conventions]
Some references define the small sphere with the opposite orientation or put the stress tensor on the other side of the Ward identity. Then the displayed coefficient appears with the opposite sign. The invariant statement is that the flux of $T_{\mu\nu}$ generates the conformal transformation of the enclosed operator.
:::

## Translation, rotation, and spin terms

For a constant translation vector $\xi^\mu=a^\mu$, the Ward identity demands

$$
Q_a\mathcal O(0)=a^\rho\partial_\rho\mathcal O(0).
$$

The leading dilatation term above does not produce this derivative term. The derivative appears in the subleading singular terms of the $T_{\mu\nu}\mathcal O$ OPE.

For a spinning primary $\mathcal O_A$, where $A$ labels a representation of $SO(d)$, the local conformal variation contains a spin rotation:

$$
\delta_\xi \mathcal O_A
=
-\xi^\rho\partial_\rho\mathcal O_A
-\Delta\,\sigma_\xi\,\mathcal O_A
-\frac12\omega_{\xi}^{\rho\sigma}(\Sigma_{\rho\sigma})_A^{\ B}\mathcal O_B,
$$

up to the sign convention chosen for active versus passive transformations. Here $\sigma_\xi$ is the local scale factor and $\omega_\xi^{\rho\sigma}$ is the local rotation. The $T_{\mu\nu}\mathcal O_A$ OPE must reproduce all of these terms after integration against $\xi_\nu$.

This is why the stress-tensor OPE is easiest to state as a Ward identity. Pointwise formulas are useful, but the charge-integral form is what fixes the physics.

## Stress tensor inside a scalar-scalar OPE

Now take a unit-normalized scalar primary $\phi$:

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{|x|^{2\Delta_\phi}}.
$$

The singlet OPE begins as

$$
\phi(x)\phi(0)
=
\frac{1}{|x|^{2\Delta_\phi}}\mathbf 1
+
\mathcal A_{\phi\phi T}\,
\frac{x^\mu x^\nu}{|x|^{2\Delta_\phi-d+2}}\,
T_{\mu\nu}(0)
+\cdots.
$$

The coefficient $\mathcal A_{\phi\phi T}$ is fixed by the same Ward identity that fixes $\langle T\phi\phi\rangle$. With the $C_T$ normalization above and the charge convention used on this page,

$$
\mathcal A_{\phi\phi T}
=
\frac{d\,\Delta_\phi}{(d-1)S_d\,C_T},
$$

for the displayed tensor structure. If one instead uses a unit-normalized stress tensor

$$
\widehat T_{\mu\nu}=\frac{T_{\mu\nu}}{\sqrt{C_T}},
$$

then the corresponding OPE coefficient scales as

$$
\lambda_{\phi\phi\widehat T}
\propto
\frac{\Delta_\phi}{\sqrt{C_T}}.
$$

The proportionality constant depends on the precise conformal-block and three-point tensor-structure normalization. The physical message does not: **stress-tensor exchange is not an arbitrary scalar OPE coefficient.** Once $\Delta_\phi$ and $C_T$ are fixed, the Ward identity fixes it.

This is one of the reasons $C_T$ is visible in the numerical bootstrap. Bounding or extracting stress-tensor exchange is equivalent to bounding or extracting a central-charge-like datum.

## The three-point function with two scalars

The Ward-fixed OPE is the short-distance form of the Ward-fixed three-point function

$$
\langle T_{\mu\nu}(x_1)\phi(x_2)\phi(x_3)\rangle.
$$

Conformal symmetry fixes the tensor structure up to one coefficient, and stress-tensor conservation fixes that coefficient in terms of $\Delta_\phi$ and the normalization of $\langle \phi\phi\rangle$. Schematically,

$$
\langle T\phi\phi\rangle
=
\Delta_\phi\times
\text{universal conformal tensor structure}.
$$

The word “schematically” matters here. In actual calculations, the tensor structure contains the standard conformally covariant vector built from the three points. The important lesson for this page is not the decorative form of the structure; it is the fact that the coefficient is fixed by Ward identities rather than by new dynamical input.

## Universal singlet operators in the scalar OPE

For a neutral scalar $\phi$, the singlet OPE often starts as

$$
\phi\times\phi
=
\mathbf 1
+
(\text{lowest scalar singlets})
+
T_{\mu\nu}
+
(\text{higher-spin and higher-dimension operators}).
$$

The identity is fixed by the two-point function. The stress tensor is fixed by $\Delta_\phi$ and $C_T$. The scalar singlets are usually dynamical and theory-specific.

For example, in the three-dimensional Ising CFT,

$$
\sigma\times\sigma
=
\mathbf 1+\epsilon+T+\cdots.
$$

Here the existence and dimensions of $\epsilon$ and later operators are nontrivial CFT data. The existence of $T$ is universal, and its dimension and spin are fixed, but $C_T$ is theory-dependent.

## Two-dimensional version

In a two-dimensional CFT, write complex coordinates $z,\bar z$. The holomorphic stress tensor has the OPE with a primary field $\phi$ of weights $(h,\bar h)$

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\,\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}.
$$

Similarly,

$$
\bar T(\bar z)\phi(w,\bar w)
\sim
\frac{\bar h\,\phi(w,\bar w)}{(\bar z-\bar w)^2}
+
\frac{\partial_{\bar w}\phi(w,\bar w)}{\bar z-\bar w}.
$$

The stress tensor also has an OPE with itself:

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

This formula is the two-dimensional origin of many statements about central charge. In higher dimensions, there is no infinite-dimensional Virasoro algebra, but $C_T$ still plays the role of the stress-tensor two-point normalization.

## Bootstrap role

In a scalar four-point function, stress-tensor exchange contributes a conformal block with

$$
\Delta=d,\qquad \ell=2.
$$

For identical unit-normalized scalars, the contribution has the schematic form

$$
\lambda_{\phi\phi T}^2G_{d,2}(u,v),
\qquad
\lambda_{\phi\phi T}^2\propto \frac{\Delta_\phi^2}{C_T}.
$$

Thus a lower bound on $C_T$ is related to an upper bound on the amount of stress-tensor exchange, and vice versa. This relationship is one of the classic ways the bootstrap turns a local Ward identity into a quantitative constraint on the CFT.

In mixed-correlator systems, stress tensors and currents also impose shared Ward-identity constraints among several four-point functions. This is one reason mixed systems are powerful: the same universal operator must appear consistently across many OPE channels.

## Contact terms and improvements

The stress tensor is defined up to improvement terms when the theory admits suitable lower-dimension operators. A typical improvement has the schematic form

$$
T_{\mu\nu}\to T_{\mu\nu}
+
(\partial_\mu\partial_\nu-\delta_{\mu\nu}\partial^2)L,
$$

where $L$ is a scalar operator of dimension $d-2$. Improvements can change contact terms and local expressions for $T_{\mu\nu}$, but they do not change the integrated conformal charges or the physical Ward identities.

This matters when comparing Lagrangian calculations to CFT-normalized correlators. A stress tensor that is conserved but not traceless may need improvement at a conformal fixed point. Conversely, in a theory that is scale invariant but not conformal, an appropriate improvement may not exist.

## Common pitfalls

**Forgetting that $T_{\mu\nu}$ is physically normalized.** Unlike a generic primary, the stress tensor cannot be freely rescaled once it is required to generate translations and conformal transformations. Rescaling $T$ would rescale the charges.

**Confusing $C_T$ with a free OPE coefficient.** $C_T$ is theory-dependent, but the coefficient of $\langle T\phi\phi\rangle$ is Ward-fixed once $C_T$ and $\Delta_\phi$ are specified.

**Keeping only the leading term in the $T\mathcal O$ OPE.** The leading scalar term fixes the dimension. Subleading singular terms are needed for translations, rotations, and special conformal transformations.

**Using two-dimensional formulas in higher dimensions.** The elegant $T(z)\phi(w)$ OPE relies on holomorphic factorization and the Virasoro structure. Higher-dimensional CFTs have stress-tensor Ward identities, not a local holomorphic stress-tensor algebra.

**Ignoring contact terms.** Ward identities are distributional statements. Coincident-point terms matter when deriving conservation laws, charges, anomalies, and metric variations.

## Relations to other pages

- [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/) gives the symmetry derivation behind this page.
- [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) develops $C_T$, $\langle TTT\rangle$, and metric-response definitions.
- [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/) explains why conservation is multiplet shortening.
- [Identity Operator in the OPE](/cft-bootstrap/operator-product-expansion/identity-operator-in-the-ope/) treats the universal operator that appears before $T_{\mu\nu}$ in neutral OPEs.
- [Conformal Blocks](/cft-bootstrap/conformal-blocks/) later turns stress-tensor exchange into the $\Delta=d$, $\ell=2$ block.
- [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) later explains how stress-tensor exchange participates in positive conformal-block sums.

## Research status

The Ward-identity normalization of the stress-tensor OPE is settled and is part of the standard definition of local CFT. The stress-tensor two-point normalization $C_T$ is a central observable in higher-dimensional CFT, much as $c$ is central in two-dimensional CFT.

Active research uses stress-tensor OPE data in several directions: numerical bounds on $C_T$, mixed-correlator bootstrap systems involving $T_{\mu\nu}$, collider bounds and average null energy conditions, Lorentzian inversion formulas, holographic causality constraints, and the structure of stress-tensor correlators in supersymmetric and nonsupersymmetric theories.

## Exercises

### Exercise 1: Fix the leading coefficient from dilatations

Assume

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
A
\frac{x_\mu x_\nu-\frac1d\delta_{\mu\nu}x^2}{|x|^{d+2}}\mathcal O(0).
$$

Use $Q_D=\int dS_\mu\,x_\nu T^{\mu\nu}$ to determine $A$ if $Q_D\mathcal O=\Delta\mathcal O$.

<details><summary><strong>Solution</strong></summary>

On a sphere of radius $r$, set $x^\mu=rn^\mu$ and $dS_\mu=r^{d-1}n_\mu d\Omega$. Then

$$
dS_\mu x_\nu
\frac{x^\mu x^\nu-\frac1d\delta^{\mu\nu}x^2}{|x|^{d+2}}
=
d\Omega\,
n_\mu n_\nu
\left(n^\mu n^\nu-\frac1d\delta^{\mu\nu}\right).
$$

The angular expression is

$$
1-\frac1d=\frac{d-1}{d}.
$$

Therefore

$$
Q_D\mathcal O
=
A S_d\frac{d-1}{d}\mathcal O.
$$

Setting this equal to $\Delta\mathcal O$ gives

$$
A=\frac{d\,\Delta}{(d-1)S_d}.
$$

</details>

### Exercise 2: The two-dimensional primary OPE

In a two-dimensional CFT, suppose

$$
T(z)\phi(w,\bar w)
\sim
\frac{a\,\phi(w,\bar w)}{(z-w)^2}
+
\frac{b\,\partial_w\phi(w,\bar w)}{z-w}.
$$

Use the contour charges $L_0$ and $L_{-1}$ to identify $a$ and $b$ for a primary of weight $h$.

<details><summary><strong>Solution</strong></summary>

The holomorphic conformal charges are

$$
L_n=\frac{1}{2\pi i}\oint_w dz\,(z-w)^{n+1}T(z).
$$

For $n=0$, the contour picks the coefficient of $(z-w)^{-2}$ and gives

$$
L_0\phi=h\phi,
$$

so $a=h$. For $n=-1$, the contour picks the coefficient of $(z-w)^{-1}$ and gives translations:

$$
L_{-1}\phi=\partial_w\phi,
$$

so $b=1$. Therefore

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\,\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}.
$$

</details>

### Exercise 3: Why stress-tensor exchange depends on central charge

Let $\widehat T_{\mu\nu}=T_{\mu\nu}/\sqrt{C_T}$ be unit-normalized. Explain why the OPE coefficient $\lambda_{\phi\phi\widehat T}$ scales like $\Delta_\phi/\sqrt{C_T}$.

<details><summary><strong>Solution</strong></summary>

The physical stress tensor $T_{\mu\nu}$ is normalized by the Ward identity. The coefficient of the physical $T_{\mu\nu}$ in $\phi\times\phi$ is therefore proportional to $\Delta_\phi/C_T$ when the two-point function is written as $\langle TT\rangle=C_T(\text{fixed tensor structure})$.

Replacing $T_{\mu\nu}$ by the unit-normalized operator $\widehat T_{\mu\nu}=T_{\mu\nu}/\sqrt{C_T}$ multiplies the OPE coefficient by $\sqrt{C_T}$. Hence

$$
\lambda_{\phi\phi\widehat T}
\propto
\frac{\Delta_\phi}{C_T}\sqrt{C_T}
=
\frac{\Delta_\phi}{\sqrt{C_T}}.
$$

The proportionality constant depends on the detailed tensor-structure convention, but the scaling with $\Delta_\phi$ and $C_T$ is fixed.

</details>

### Exercise 4: Improvement and charges

Show that the improvement

$$
\Delta T_{\mu\nu}
=
(\partial_\mu\partial_\nu-\delta_{\mu\nu}\partial^2)L
$$

does not change translation charges if surface terms vanish.

<details><summary><strong>Solution</strong></summary>

The translation charge shift is

$$
\Delta P_\nu
=
\int_\Sigma dS_\mu\,\Delta T^{\mu}_{\ \nu}.
$$

For a constant-time or radial surface with suitable boundary behavior, this is a total derivative on the surface plus a boundary term at infinity or at the edge of the surface. If the surface has no boundary and the fields fall off appropriately, the integral vanishes. Therefore the improvement can change local expressions and contact terms but not the conserved translation charge.

</details>

## References

- H. Osborn and A. C. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals of Physics* **231** (1994), arXiv:hep-th/9307010.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982.
- D. Poland, S. Rychkov, and A. Vichi, “The conformal bootstrap: theory, numerical techniques, and applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405.
- J. L. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996.
- A. B. Zamolodchikov, “Irreversibility of the flux of the renormalization group in a 2D field theory,” *JETP Letters* **43** (1986).

## Version history

- 2026-06-27: First polished draft. Derived the leading $T_{\mu\nu}\mathcal O$ singularity from the dilatation Ward identity, recorded the scalar-scalar stress-tensor OPE, explained $C_T$ dependence, and connected stress-tensor exchange to bootstrap.
