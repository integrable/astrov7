---
title: "Stress-Tensor Correlators"
description: "Explains the stress-tensor two-point normalization, Ward-identity constraints, three- and four-point structures, and the role of stress-tensor data in CFT and bootstrap."
sidebar:
  label: "Stress-Tensor Correlators"
  order: 7
level: Graduate
status: "Polished draft"
source: "Osborn and Petkou 1994; Di Francesco–Mathieu–Sénéchal 1997; Hofman and Maldacena 2008; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - stress tensor
  - correlation functions
  - Ward identities
  - central charge
  - conformal bootstrap
canonicalTopics:
  - cft-stress-tensor-correlators
  - stress-tensor-two-point-normalization
  - stress-tensor-ward-identities
  - stress-tensor-bootstrap-data
researchStatus:
  established:
    - "In a local CFT with a stress tensor, the stress tensor is a conserved symmetric traceless spin-two primary of dimension d, and its two-point function defines the convention-dependent positive coefficient C_T in unitary theories."
    - "Stress-tensor Ward identities fix universal couplings of the stress tensor to local operators and constrain stress-tensor three-point functions beyond separated-point conformal covariance."
  active:
    - "Stress-tensor four-point functions, conformal collider bounds, ANEC constraints, spinning numerical bootstrap, and holographic stress-tensor data remain active research areas."
---

## Summary

The stress tensor $T_{\mu\nu}$ is the universal local operator that generates spacetime symmetries. In a flat-space CFT at separated points it is symmetric, traceless, conserved, and has scaling dimension $d$:

$$
T_{\mu\nu}=T_{\nu\mu},
\qquad
T^\mu_{\ \mu}=0,
\qquad
\partial^\mu T_{\mu\nu}=0,
\qquad
\Delta_T=d.
$$

Its two-point function defines the higher-dimensional stress-tensor normalization $C_T$:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=
\frac{C_T}{x^{2d}}\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where

$$
\mathcal I_{\mu\nu,\rho\sigma}(x)
=
\frac12\left(I_{\mu\rho}I_{\nu\sigma}+I_{\mu\sigma}I_{\nu\rho}\right)
-
\frac1d\delta_{\mu\nu}\delta_{\rho\sigma},
\qquad
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The number $C_T$ is not just another OPE coefficient. It is the normalization of the operator that couples to the background metric and generates conformal transformations. Once $T_{\mu\nu}$ is normalized by its Ward identity, $C_T$ is theory-dependent data. If one instead uses the unit-normalized operator $\widehat T_{\mu\nu}=T_{\mu\nu}/\sqrt{C_T}$ in a conformal-block expansion, then stress-tensor OPE coefficients acquire factors of $1/\sqrt{C_T}$.

:::caution[Convention check]
The symbol $C_T$ is not universal across papers. Always compare the full two-point tensor structure, not just the name of the coefficient.
:::

## Prerequisites

You should know [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/), [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/), [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/), and [Stress-Tensor Multiplet Preview](/cft-bootstrap/operators-states-radial-quantization/stress-tensor-multiplet-preview/). The site-wide stress-tensor conventions are summarized in [Conventions and Notation](/cft-bootstrap/conventions/).

For a first pass, focus on the two-point normalization, the scalar-scalar-stress Ward identity, and the distinction between physical $T_{\mu\nu}$ and unit-normalized $\widehat T_{\mu\nu}$.

## Core idea

The stress tensor appears in CFT in three related but different roles:

| Role | What it controls |
|---|---|
| conserved current for spacetime symmetry | translations, rotations, dilatations, and special conformal transformations |
| local operator in the spectrum | a spin-two primary with $\Delta=d$ |
| response to background geometry | metric variations, trace anomalies, contact terms |

These roles are tied together by Ward identities. That is why stress-tensor correlators are more constrained than generic spin-two correlators.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Hierarchy of CFT data involving the stress tensor](/figures/cft-bootstrap/stress-tensor-correlator-hierarchy.svg)

<figcaption>

Stress-tensor data are organized by Ward identities. The physical normalization of $T_{\mu\nu}$ is fixed by charges; $C_T$ is then measured by $\langle TT\rangle$, while $\langle \phi\phi T\rangle$, $\langle TTT\rangle$, and $\langle TTTT\rangle$ encode increasingly detailed dynamical information.

</figcaption>
</figure>

A generic spin-two primary can have arbitrary two- and three-point normalization. The stress tensor cannot. Its normalization is fixed by demanding that its integrated flux generate the correct action of conformal transformations on every local operator.

## Setup and conventions

We work in flat Euclidean space $\mathbb R^d$ at separated points unless contact terms are explicitly discussed. The physical stress tensor is normalized by the Ward identity for conformal charges. For a conformal Killing vector $\xi^\mu(x)$, the corresponding charge is schematically

$$
Q_\xi(\Sigma)=\int_\Sigma dS_\mu\,\xi_\nu T^{\mu\nu},
$$

where $\Sigma$ surrounds an operator insertion. Inserting $Q_\xi$ into a correlator implements the infinitesimal conformal transformation generated by $\xi$.

The surface area of the unit $(d-1)$-sphere is

$$
S_d=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

This $S_d$ appears in Ward-identity normalizations. If another page rescales the stress tensor, every formula involving $C_T$ and $\lambda_{\phi\phi T}$ must be rescaled accordingly.

## Two-point function and positivity

Conformal symmetry, conservation, symmetry, and tracelessness fix the separated-point two-point function to

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=
\frac{C_T}{x^{2d}}\mathcal I_{\mu\nu,\rho\sigma}(x).
$$

Here $C_T$ is positive in a unitary theory because the stress-tensor state has positive norm in radial quantization:

$$
|T_{\mu\nu}\rangle=T_{\mu\nu}(0)|0\rangle.
$$

The coefficient $C_T$ often plays the role of a higher-dimensional analog of a central charge, but that phrase is only an analogy. In two dimensions, the Virasoro central charge $c$ appears in the $T(z)T(0)$ OPE. In $d>2$, $C_T$ is a two-point normalization; trace-anomaly coefficients, sphere free energies, and conformal collider parameters are related but distinct data.

## Scalar-scalar-stress correlator

The three-point function $\langle \phi\phi T\rangle$ is a useful calibration point. For a scalar primary $\phi$ of dimension $\Delta_\phi$, conformal symmetry allows one separated-point tensor structure. The Ward identity fixes its coefficient.

In the physical stress-tensor normalization used here,

$$
\lambda_{\phi\phi T}^{\mathrm{phys}}
=
-\frac{d\Delta_\phi}{(d-1)S_d},
$$

in the common tensor-structure convention where the stress-tensor insertion is encoded using a polarization vector $z$ and the unique structure is proportional to

$$
\left[(Z_{123}\cdot z)^2-\frac1d z^2 Z_{123}^2\right].
$$

The sign depends on the convention for $T_{\mu\nu}$ and the conformal generators, but the point does not: the coefficient is fixed by $\Delta_\phi$ once the physical stress tensor is normalized by Ward identities.

In bootstrap calculations one often wants unit two-point normalization. Define

$$
\widehat T_{\mu\nu}=\frac{T_{\mu\nu}}{\sqrt{C_T}}.
$$

Then the corresponding block coefficient is

$$
\lambda_{\phi\phi\widehat T}
=
-\frac{d\Delta_\phi}{(d-1)S_d\sqrt{C_T}}.
$$

Thus the stress-tensor contribution to the scalar four-point function knows about $C_T$. This is why scalar bootstrap bounds can constrain $C_T$.

## Three stress tensors

The correlator $\langle TTT\rangle$ contains more information than $C_T$. In $d\geq4$, parity-even conformal invariance and conservation allow three standard tensor structures, often parameterized by the structures realized by a free scalar, a free fermion, and a free vector. The Ward identity fixes one linear combination in terms of $C_T$, leaving two independent dimensionless ratios.

In $d=3$, the parity-even space is smaller, and parity-odd structures can appear in parity-violating theories. In $d=2$, the local conformal algebra is enhanced to Virasoro symmetry, and the holomorphic stress-tensor OPE is fixed by the central charge:

$$
T(z)T(0)
\sim
\frac{c}{2z^4}
+
\frac{2T(0)}{z^2}
+
\frac{\partial T(0)}{z}.
$$

The lesson is that $\langle TTT\rangle$ is not “just fixed by symmetry” in higher dimensions. Symmetry constrains it to a finite-dimensional space; dynamics chooses a point in that space.

## Four stress tensors

The four-point function $\langle TTTT\rangle$ is a spinning four-point function with many tensor structures and many functions of cross-ratios. It is the natural stress-tensor analog of the scalar four-point function

$$
\langle \phi\phi\phi\phi\rangle
=
\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}},
$$

but with a vector of functions rather than a single $\mathcal G(u,v)$.

The $TT$ OPE contains the identity, the stress tensor itself, and all primary operators allowed by spin, parity, and internal symmetries:

$$
T\times T
\sim
\mathbf 1+T+\sum_{\mathcal O}\lambda_{TT\mathcal O}^{(a)}\mathcal O+\text{descendants}.
$$

The coefficients $\lambda_{TT\mathcal O}^{(a)}$ are labeled by tensor structures. Crossing symmetry of $\langle TTTT\rangle$ is therefore a coupled spinning bootstrap problem. It is extremely rich, but it is not the first place to learn bootstrap; scalar and mixed-scalar correlators are the on-ramp.

## Metric response and contact terms

The stress tensor is also the response of the theory to a background metric. Schematically,

$$
T_{\mu\nu}(x)
=
-\frac{2}{\sqrt g}\frac{\delta W[g]}{\delta g^{\mu\nu}(x)},
$$

up to Euclidean sign conventions. Repeated metric variations generate stress-tensor correlators.

This viewpoint explains why stress-tensor correlators are full of contact-term subtleties. At separated points, conformal symmetry fixes tensor structures. At coincident points, additional local terms encode Ward identities, anomalies, improvement choices, and scheme-dependent curvature counterterms.

A separated-point formula for $\langle TT\rangle$ is not by itself a complete definition of the stress tensor on curved backgrounds.

## Bootstrap role

Stress-tensor correlators enter bootstrap in several ways.

| Data | Bootstrap meaning |
|---|---|
| $C_T$ | Measures the norm of $T_{\mu\nu}$ and controls stress-tensor exchange in unit-normalized bases. |
| $\lambda_{\phi\phi T}$ | Fixed by $\Delta_\phi$ and $C_T$ after normalizing $T$. |
| $\langle TTT\rangle$ | Encodes conformal collider data and constraints from energy positivity. |
| $\langle JJT\rangle$ | Controls energy flux from charged states and current bootstrap constraints. |
| $\langle TTTT\rangle$ | Gives a fully stress-tensor bootstrap problem, important in holographic and causality applications. |

In holographic CFTs, $C_T$ is related to the effective Newton constant in AdS, while the independent $\langle TTT\rangle$ structures encode higher-derivative gravitational couplings. That dictionary is useful, but it relies on extra large-$N$ and sparse-spectrum assumptions; it is not true of an arbitrary CFT.

## Common pitfalls

**Treating $T_{\mu\nu}$ as a generic spin-two primary.** A generic spin-two primary has no reason to generate translations or dilatations. The stress tensor is distinguished by Ward identities and by its role as the metric response.

**Comparing $C_T$ values without checking normalization.** Some papers normalize free scalars to one; others use different $S_d$ factors or two-point tensor structures. Compare the equation defining $\langle TT\rangle$, not the symbol $C_T$ alone.

**Forgetting the difference between $T$ and $\widehat T$.** The physical stress tensor is fixed by charges. The unit-normalized stress tensor is convenient for conformal blocks. OPE coefficients differ by powers of $\sqrt{C_T}$.

**Ignoring contact terms.** Conservation equations and Ward identities contain contact terms at coincident points. Separated-point correlators are necessary, but not sufficient, for anomalies and background-metric response.

**Calling every central quantity a central charge.** In two dimensions, $c$ is the Virasoro central charge. In higher dimensions, $C_T$, anomaly coefficients, and sphere free energies are distinct, though related in special settings.

## Relations to other pages

- [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/) gives the tensor-structure language used here.
- [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/) explains how stress-tensor flux generates conformal transformations.
- [Stress-Tensor Multiplet Preview](/cft-bootstrap/operators-states-radial-quantization/stress-tensor-multiplet-preview/) explains why the stress tensor is a universal conserved spin-two primary.
- [Stress-Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/) develops the local OPE form of the same Ward-identity content.
- [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) specializes to the holomorphic stress tensor, Virasoro symmetry, and the central charge $c$.
- [Holographic CFT](/cft-bootstrap/holographic-cft/) uses stress-tensor data in the AdS/CFT dictionary.

## Research status

The separated-point two- and three-point kinematics of stress tensors are standard. The subtle parts are convention dependence, contact terms, and the interpretation of positivity or causality constraints. Modern work uses stress-tensor correlators in conformal collider physics, Lorentzian inversion, holographic causality, numerical bootstrap with spin, and constraints from averaged energy conditions.

## Exercises

### Exercise 1: Unit-normalized stress tensor

Assume the physical stress tensor satisfies

$$
\langle TT\rangle=C_T\,\mathcal K_T,
$$

where $\mathcal K_T$ denotes the fixed tensor structure. Define $\widehat T=T/\sqrt{C_T}$. Show that $\langle \widehat T\widehat T\rangle=\mathcal K_T$ and that every three-point coefficient with one stress tensor is divided by $\sqrt{C_T}$.

<details>
<summary><strong>Solution</strong></summary>

By linearity,

$$
\langle \widehat T\widehat T\rangle
=
\frac1{C_T}\langle TT\rangle
=
\mathcal K_T.
$$

Similarly, for any two operators $\mathcal O_1,\mathcal O_2$,

$$
\langle \mathcal O_1\mathcal O_2\widehat T\rangle
=
\frac1{\sqrt{C_T}}
\langle \mathcal O_1\mathcal O_2 T\rangle.
$$

Thus coefficients involving one unit-normalized stress tensor carry one factor of $1/\sqrt{C_T}$.

</details>

### Exercise 2: Why stress-tensor exchange knows about dimension

Use the Ward-identity result

$$
\lambda_{\phi\phi\widehat T}
=
-\frac{d\Delta_\phi}{(d-1)S_d\sqrt{C_T}}
$$

to explain why the stress-tensor conformal block in $\langle \phi\phi\phi\phi\rangle$ has a coefficient proportional to $\Delta_\phi^2/C_T$.

<details>
<summary><strong>Solution</strong></summary>

In an identical-scalar four-point function with unit-normalized exchanged primaries, the block coefficient is the square of the OPE coefficient. Therefore the stress-tensor contribution is proportional to

$$
\lambda_{\phi\phi\widehat T}^2
=
\frac{d^2\Delta_\phi^2}{(d-1)^2S_d^2C_T}.
$$

Up to the tensor and block normalization convention, the important dependence is $\Delta_\phi^2/C_T$.

</details>

### Exercise 3: Conservation as shortening

Explain why the stress tensor saturates the symmetric-traceless spin-$\ell$ unitarity bound in $d>2$.

<details>
<summary><strong>Solution</strong></summary>

For a symmetric traceless primary of spin $\ell\geq1$, the unitarity bound is

$$
\Delta\geq \ell+d-2.
$$

For the stress tensor, $\ell=2$ and $\Delta_T=d$, so

$$
\Delta_T=d=2+d-2.
$$

The bound is saturated. The corresponding null descendant is the divergence $\partial^\mu T_{\mu\nu}$, which is set to zero by conservation.

</details>

## References

### Standard first pass

- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, for Ward identities, stress-tensor normalization, and bootstrap use of $C_T$.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” for stress-tensor data in higher-dimensional bootstrap.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for the two-dimensional stress tensor, Virasoro algebra, and central charge.

### Deeper references

- H. Osborn and A. C. Petkou, “Implications of Conformal Invariance in Field Theories for General Dimensions,” for higher-dimensional current and stress-tensor correlators.
- D. M. Hofman and J. Maldacena, “Conformal Collider Physics: Energy and Charge Correlations,” for energy-flux constraints on stress-tensor three-point data.
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Correlators,” for embedding-space treatment of spinning and stress-tensor correlators.

## Version history

- **2026-06-27:** Initial polished draft on $C_T$, stress-tensor Ward identities, scalar-scalar-stress tensor structure, $TTT$ data, contact-term caveats, two-dimensional specialization, conformal collider overview, and exercises.
