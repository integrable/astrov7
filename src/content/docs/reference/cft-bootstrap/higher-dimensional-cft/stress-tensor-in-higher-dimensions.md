---
title: "Stress Tensor in Higher Dimensions"
description: "The universal conserved spin-two primary of a higher-dimensional CFT, including Ward identities, two-point normalization, trace improvements, and the role of C_T."
sidebar:
  label: "Stress Tensor"
  order: 4
level: Graduate
status: "Polished draft"
source: "Osborn and Petkou; Rychkov lectures; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019; conformal Ward identity literature."
topics:
  - stress tensor
  - higher-dimensional CFT
  - Ward identities
  - central charge analogues
  - conformal collider
canonicalTopics:
  - stress-tensor-in-higher-dimensions
  - cft-stress-tensor
  - c-t-normalization
researchStatus:
  established:
    - "In a local unitary CFT in dimensions greater than two, the stress tensor is a conserved symmetric traceless spin-two primary of dimension d."
  active:
    - "Stress-tensor three-point structures, conformal collider bounds, causality constraints, anomalies, defects, and higher-spin or nonlocal exceptions remain active research areas."
---

## Summary

The **stress tensor** is the local operator that generates spacetime translations, rotations, dilatations, and special conformal transformations. In a flat-space CFT in $d>2$, the improved stress tensor is symmetric, conserved, and traceless:

$$
T_{\mu\nu}=T_{\nu\mu},
\qquad
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

It is a spin-two primary with protected scaling dimension

$$
\Delta_T=d.
$$

Its two-point function is fixed by conformal symmetry up to one positive coefficient $C_T$:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=\frac{C_T}{(x^2)^d}\,\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where

$$
\mathcal I_{\mu\nu,\rho\sigma}(x)
=\frac12\left(I_{\mu\rho}I_{\nu\sigma}+I_{\mu\sigma}I_{\nu\rho}\right)-\frac1d\delta_{\mu\nu}\delta_{\rho\sigma},
$$

and

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The number $C_T$ is one of the main higher-dimensional analogues of the two-dimensional central charge. It is not the coefficient of a Virasoro algebra, because there is no generic Virasoro algebra in $d>2$. Instead, $C_T$ measures the normalization of stress-tensor fluctuations and enters Ward identities, conformal collider bounds, thermal physics, entanglement, and bootstrap constraints.

## Prerequisites

Read [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) and [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/) first. You should also know [Conformal Symmetry in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/conformal-symmetry-in-higher-dimensions/) and the state-operator map from radial quantization.

The stress tensor is a conserved spin-two current, but it deserves its own page because it is tied to spacetime symmetry rather than an internal global symmetry. Its Ward identities are universal in every local CFT.

## Core idea

An ordinary global symmetry current generates transformations on charged operators. The stress tensor does the same for spacetime transformations. Integrating $T_{\mu\nu}$ against a conformal Killing vector $\epsilon^\nu(x)$ gives the conserved charge

$$
Q_\epsilon=\int_\Sigma dS^\mu\,T_{\mu\nu}\epsilon^\nu.
$$

For translations, rotations, dilatations, and special conformal transformations, $Q_\epsilon$ gives the conformal generators

$$
P_\mu,\quad M_{\mu\nu},\quad D,\quad K_\mu.
$$

The local conservation equation

$$
\partial^\mu T_{\mu\nu}=0
$$

is therefore the local form of spacetime symmetry. The tracelessness condition

$$
T^\mu{}_{\mu}=0
$$

is the local form of scale and conformal invariance in flat space, after choosing an appropriate improved stress tensor when an improvement exists.

The slogan is

$$
\text{stress tensor}
\quad=\quad
\text{local current for spacetime conformal symmetry}.
$$

Because the stress tensor is universal, any consistent local CFT must explain where it is in the spectrum and how it appears in OPEs.

## Setup and conventions

We use Euclidean signature unless stated otherwise. Coordinates are $x^\mu$, with metric $\delta_{\mu\nu}$. The stress tensor is normalized by its Ward identities: it generates translations through the surface charge

$$
P_\nu=\int_{S^{d-1}}dS^\mu\,T_{\mu\nu}.
$$

The area of the unit sphere is

$$
\omega_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

The inversion tensor is

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The spin-two projector appearing in the two-point function is

$$
\mathcal I_{\mu\nu,\rho\sigma}(x)
=\frac12\left(I_{\mu\rho}(x)I_{\nu\sigma}(x)+I_{\mu\sigma}(x)I_{\nu\rho}(x)\right)-\frac1d\delta_{\mu\nu}\delta_{\rho\sigma}.
$$

This object is symmetric in $\mu\nu$, symmetric in $\rho\sigma$, and traceless in each pair.

Normalization conventions for $C_T$ differ across the literature. The formula above defines the convention used on this page. When comparing numerical values, always check the normalization of $T_{\mu\nu}$ and of the two-point tensor structure.

## Stress tensor as a conformal primary

In a unitary CFT, a symmetric traceless spin-$\ell$ primary satisfies the unitarity bound

$$
\Delta\ge \ell+d-2
\qquad
\ell\ge1.
$$

For a spin-two operator, this gives

$$
\Delta\ge d.
$$

The stress tensor saturates the bound:

$$
\Delta_T=d.
$$

At saturation, the divergence descendant is null:

$$
\partial^\mu T_{\mu\nu}=0.
$$

Thus conservation is a shortening condition. The stress tensor is not just a random operator with dimension $d$; it is the short spin-two multiplet whose charge generates spacetime translations and the rest of the conformal algebra.

If a unitary CFT has more than one conserved spin-two operator, the theory typically decomposes into decoupled sectors, each with its own stress tensor. A single interacting CFT is usually assumed to have a unique stress tensor. This uniqueness assumption is often important in bootstrap work.

## Ward identity for translations

The stress tensor Ward identity for translations is the distributional statement

$$
\partial^\mu\langle T_{\mu\nu}(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=-\sum_i\delta^{(d)}(x-x_i)\partial_{x_i^\nu}
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle,
$$

for scalar operators. For spinning operators, the right-hand side also includes the appropriate action on their spin indices when rotations are generated.

Integrating this equation over a region whose boundary is a sphere around one insertion gives the statement that the translation charge moves that operator:

$$
[P_\nu,\mathcal O(x_i)]=\partial_{x_i^\nu}\mathcal O(x_i),
$$

up to the Euclidean-signature and Hermitian-generator convention.

This identity fixes the leading singularity in the $T\mathcal O$ OPE. It is the stress-tensor analogue of the current Ward identity for internal symmetries.

## Ward identities for conformal transformations

Let $\epsilon^\nu(x)$ be a conformal Killing vector:

$$
\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu
=\frac{2}{d}(\partial\cdot\epsilon)\delta_{\mu\nu}.
$$

Using conservation and tracelessness,

$$
\partial^\mu(T_{\mu\nu}\epsilon^\nu)
=(\partial^\mu T_{\mu\nu})\epsilon^\nu+\frac12 T^{\mu\nu}(\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu)
=0
$$

away from operator insertions. Therefore

$$
Q_\epsilon=\int_\Sigma dS^\mu T_{\mu\nu}\epsilon^\nu
$$

is conserved under deformations of $\Sigma$ that do not cross insertions.

Choosing $\epsilon^\nu$ gives the conformal generators:

| Transformation | Conformal Killing vector | Charge |
|---|---|---|
| Translation | $\epsilon^\nu=a^\nu$ | $a^\nu P_\nu$ |
| Rotation | $\epsilon^\nu=\omega^\nu{}_{\rho}x^\rho$ | $\frac12\omega^{\mu\nu}M_{\mu\nu}$ |
| Dilatation | $\epsilon^\nu=\lambda x^\nu$ | $\lambda D$ |
| Special conformal | $\epsilon^\nu=b^\nu x^2-2x^\nu b\cdot x$ | $b^\nu K_\nu$ |

This is the cleanest way to remember why $T_{\mu\nu}$ is the current for the full conformal group, not merely translations.

## Trace, scale invariance, and improvement

In a classical field theory, the canonical stress tensor need not be symmetric or traceless. One can often improve it by adding total-derivative terms that do not change the conserved translation charges.

A typical improvement has the schematic form

$$
T_{\mu\nu}\longrightarrow T_{\mu\nu}+\left(\partial_\mu\partial_\nu-\delta_{\mu\nu}\partial^2\right)L,
$$

where $L$ is a scalar operator of dimension $d-2$. This changes the trace by a total derivative:

$$
T^\mu{}_{\mu}\longrightarrow T^\mu{}_{\mu}-(d-1)\partial^2L.
$$

A theory can be scale invariant with a trace of the form

$$
T^\mu{}_{\mu}=\partial^2 L.
$$

If an appropriate local $L$ exists, the improved stress tensor can be made traceless, and the theory is conformal in flat space.

The distinction matters because scale invariance and conformal invariance are not identical as formal assumptions. In most unitary relativistic fixed points of interest, the improved traceless stress tensor exists. But when discussing theorems, virial currents, nonunitary theories, or nonlocal models, this point must be stated carefully.

## Two-point function and C_T

The stress-tensor two-point function is fixed by conformal symmetry, symmetry, tracelessness, and conservation:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=\frac{C_T}{(x^2)^d}\mathcal I_{\mu\nu,\rho\sigma}(x).
$$

The coefficient $C_T$ is positive in a unitary CFT with a nonzero stress tensor:

$$
C_T>0.
$$

Physically, $C_T$ measures the size of stress-tensor fluctuations. It also controls the normalization of the stress-tensor conformal block in OPE decompositions.

In $d=2$, the analogous information is often packaged by the Virasoro central charge $c$. With standard 2D conventions,

$$
\langle T(z)T(0)\rangle=\frac{c/2}{z^4}.
$$

In $d>2$, there is no universal Virasoro algebra, so $C_T$ is the more appropriate stress-tensor two-point normalization. Some references normalize $C_T$ so that a free scalar has a convenient value; others use the tensor convention written above. Always compare definitions before comparing numbers.

## Stress tensor in scalar OPEs

For a scalar primary $\phi$, the OPE $\phi\times\phi$ contains the stress tensor if $\phi$ is not in a completely decoupled sector from it:

$$
\phi(x)\phi(0)\sim \cdots+\lambda_{\phi\phi T}\,x^\mu x^\nu T_{\mu\nu}(0)+\cdots .
$$

The coefficient is not arbitrary. Ward identities relate $\lambda_{\phi\phi T}$ to the scaling dimension $\Delta_\phi$ and to the stress-tensor normalization $C_T$.

The exact numerical formula depends on the normalization of scalar two-point functions and on the convention for the tensor structure of $\langle \phi\phi T\rangle$. The invariant lesson is:

$$
\lambda_{\phi\phi T}\text{ is fixed by }\Delta_\phi\text{ and }C_T.
$$

This is unlike a generic three-point coefficient, which is independent CFT data. The stress tensor is special because it generates conformal transformations.

In bootstrap equations, the stress tensor appears as a spin-two operator at fixed dimension $d$. Its OPE coefficient is tied to $C_T$, so bounding $C_T$ is often equivalent to bounding the strength of stress-tensor exchange.

## Three-point functions of T

The three-point function

$$
\langle T_{\mu\nu}(x_1)T_{\rho\sigma}(x_2)T_{\alpha\beta}(x_3)\rangle
$$

is constrained by conformal symmetry and conservation but is not fixed by $C_T$ alone in $d>2$. There can be several independent tensor structures.

For parity-even CFTs in $d\ge4$, the $TTT$ correlator has a finite number of independent coefficients. In $d=3$, parity-odd structures can also appear if parity is not assumed. Ward identities relate the overall normalization to $C_T$, but additional shape parameters remain.

These extra parameters are important in conformal collider physics. Energy-flux positivity imposes inequalities on stress-tensor three-point data. In holographic CFTs, the same data are related to causality constraints on higher-derivative gravity couplings.

Thus the stress tensor has two layers of data:

| Data | Meaning |
|---|---|
| $C_T$ | Two-point normalization of stress-tensor fluctuations. |
| $TTT$ structures | Three-point data controlling energy flux, collider bounds, and gravitational couplings in holography. |

The two-point normalization is universal and single-number. The three-point function contains more refined dynamical information.

## Weyl anomaly preview

In even dimensions, putting a CFT on a curved background can produce a Weyl anomaly:

$$
\langle T^\mu{}_{\mu}\rangle\ne0
$$

on curved space, even though the flat-space stress tensor is traceless as an operator away from contact terms.

In $d=2$, the Weyl anomaly is controlled by the central charge $c$:

$$
\langle T^\mu{}_{\mu}\rangle=-\frac{c}{12}R
$$

up to convention choices. In $d=4$, the anomaly contains coefficients often called $a$ and $c$:

$$
\langle T^\mu{}_{\mu}\rangle
\sim
c\,W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}-a\,E_4+\text{scheme-dependent terms}.
$$

The four-dimensional coefficient named $c$ is related to the stress-tensor two-point normalization $C_T$ but should not be confused with the two-dimensional Virasoro central charge. The coefficient $a$ is tied to the Euler density and appears in the $a$-theorem.

This page focuses on flat-space CFT. Curved-space anomalies require a separate treatment because contact terms, improvement terms, and scheme dependence become central.

## Examples

### Free scalar

A free real scalar in $d$ dimensions has action

$$
S=\frac12\int d^dx\,\partial_\mu\phi\partial^\mu\phi.
$$

The canonical stress tensor is not traceless. The improved stress tensor is

$$
T_{\mu\nu}=\partial_\mu\phi\partial_\nu\phi-rac12\delta_{\mu\nu}(\partial\phi)^2
+\xi\left(\delta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)\phi^2,
$$

with

$$
\xi=\frac{d-2}{4(d-1)}.
$$

Using the free equation of motion $\partial^2\phi=0$, this stress tensor is conserved and traceless.

### Free fermion

A free massless fermion has a stress tensor built from the symmetric bilinear in $\psi$ and its derivative. It is conserved and traceless using the Dirac equation. The explicit formula depends on gamma-matrix and Euclidean-continuation conventions, so this page records only the structural fact: the stress tensor is a spin-two primary with $\Delta=d$ and a calculable $C_T$.

### Interacting fixed point

In an interacting CFT such as the three-dimensional Ising CFT, the stress tensor is not a simple bilinear in free fields. Nevertheless, it is still present, conserved, and normalized by $C_T$. This is one of the major virtues of the CFT-data viewpoint: the stress tensor is defined by symmetry and Ward identities, not by a particular Lagrangian formula.

## Common pitfalls

**Do not confuse $C_T$ with the two-dimensional central charge without a convention map.** In $d>2$, $C_T$ is the stress-tensor two-point coefficient. It is not a Virasoro central charge.

**Do not assume the canonical stress tensor is the CFT stress tensor.** Improvements may be needed to make $T^\mu{}_{\mu}=0$ at a conformal fixed point.

**Do not forget contact terms in Ward identities.** Conservation and tracelessness are distributional statements inside correlators. Contact terms encode the action of symmetry generators on insertions.

**Do not treat $\lambda_{\phi\phi T}$ as generic OPE data.** It is fixed by Ward identities once $\Delta_\phi$ and the normalizations are chosen.

**Do not ignore uniqueness assumptions.** Multiple conserved spin-two operators usually indicate decoupled sectors. Bootstrap studies often assume a unique stress tensor.

**Do not import the 2D Virasoro story into higher dimensions.** The higher-dimensional stress tensor does not generate an infinite tower of local conformal transformations.

**Do not assume flat-space tracelessness removes curved-space anomalies.** Even-dimensional CFTs can have Weyl anomalies on curved backgrounds.

## Relations to other pages

This page follows [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) and [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/). It prepares [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/) by showing the spin-two shortening at $\Delta=d$.

It also connects to [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/), [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/), [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/), and [Holographic CFT](/cft-bootstrap/holographic-cft/).

For the two-dimensional contrast, see [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Stress-Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/), and [Conformal Anomaly in 2D](/cft-bootstrap/virasoro-central-charge/conformal-anomaly-in-2d/).

## Research status

The stress tensor, its conservation, tracelessness, Ward identities, and two-point form in higher-dimensional CFT are established. The role of $C_T$ as a central normalization of stress-tensor fluctuations is standard.

Active research focuses on sharper constraints from stress-tensor three-point functions, conformal collider physics, Lorentzian causality, average energy conditions, defects and boundaries, anomalies, nonunitary theories, higher-spin symmetry, and numerical bootstrap determinations of $C_T$ in strongly coupled models.

## Exercises

### Exercise 1

Show that the stress tensor dimension follows from conservation and the spin-two unitarity bound.

<details><summary><strong>Solution</strong></summary>

For a symmetric traceless spin-$\ell$ primary in a unitary CFT with $\ell\ge1$, the unitarity bound is

$$
\Delta\ge \ell+d-2.
$$

For $\ell=2$, this gives

$$
\Delta\ge d.
$$

A conserved spin-two current satisfies

$$
\partial^\mu T_{\mu\nu}=0.
$$

Conservation is the shortening condition that occurs at saturation of the bound, so

$$
\Delta_T=d.
$$

</details>

### Exercise 2

Verify that the improvement term

$$
\Delta T_{\mu\nu}=\left(\partial_\mu\partial_\nu-\delta_{\mu\nu}\partial^2\right)L
$$

is conserved identically.

<details><summary><strong>Solution</strong></summary>

Take the divergence:

$$
\partial^\mu\Delta T_{\mu\nu}
=\partial^\mu\partial_\mu\partial_\nu L-\partial_\nu\partial^2L.
$$

Since derivatives commute in flat space,

$$
\partial^\mu\partial_\mu\partial_\nu L=\partial_\nu\partial^2L.
$$

Therefore

$$
\partial^\mu\Delta T_{\mu\nu}=0.
$$

Thus this improvement does not change the translation charge.

</details>

### Exercise 3

Show that the conformal charge $Q_\epsilon$ is conserved when $\epsilon^\mu$ is a conformal Killing vector and $T_{\mu\nu}$ is conserved and traceless.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial^\mu(T_{\mu\nu}\epsilon^\nu)
=(\partial^\mu T_{\mu\nu})\epsilon^\nu+T_{\mu\nu}\partial^\mu\epsilon^\nu.
$$

The first term vanishes by stress-tensor conservation. Since $T_{\mu\nu}$ is symmetric,

$$
T_{\mu\nu}\partial^\mu\epsilon^\nu
=\frac12T_{\mu\nu}(\partial^\mu\epsilon^\nu+\partial^\nu\epsilon^\mu).
$$

Using the conformal Killing equation,

$$
\partial_\mu\epsilon_\nu+\partial_\nu\epsilon_\mu
=\frac{2}{d}(\partial\cdot\epsilon)\delta_{\mu\nu},
$$

this becomes

$$
\frac1d(\partial\cdot\epsilon)T^\mu{}_{\mu}=0
$$

because the stress tensor is traceless. Hence

$$
\partial^\mu(T_{\mu\nu}\epsilon^\nu)=0.
$$

</details>

### Exercise 4

Why is the stress-tensor OPE coefficient in $\phi\times\phi$ not independent CFT data?

<details><summary><strong>Solution</strong></summary>

The stress tensor generates conformal transformations. Therefore its coupling to any primary operator is fixed by the Ward identity for translations, rotations, and dilatations. Once the scalar two-point function is normalized and the stress-tensor two-point coefficient $C_T$ is chosen, the coefficient of the $\langle \phi\phi T\rangle$ tensor structure is fixed by the dimension $\Delta_\phi$.

A generic spin-two primary would have an independent OPE coefficient. The stress tensor is special because it is the conserved current for spacetime symmetry.

</details>

## References

- H. Osborn and A. Petkou, "Implications of conformal invariance in field theories for general dimensions," *Annals of Physics* **231** (1994).
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, "TASI Lectures on the Conformal Bootstrap," 2016.
- D. Poland, S. Rychkov, and A. Vichi, "The Conformal Bootstrap: Theory, Numerical Techniques, and Applications," *Reviews of Modern Physics* **91** (2019).
- D. M. Hofman and J. Maldacena, "Conformal collider physics: Energy and charge correlations," *Journal of High Energy Physics* **2008**.
- A. B. Zamolodchikov, "Irreversibility of the flux of the renormalization group in a 2D field theory," *JETP Letters* **43** (1986).
- Z. Komargodski and A. Schwimmer, "On renormalization group flows in four dimensions," *Journal of High Energy Physics* **2011**.

## Version history

- 2026-06-30: First polished draft. Added stress-tensor Ward identities, two-point normalization, $C_T$, improvement terms, scalar OPE relation, $TTT$ data preview, Weyl anomaly preview, examples, pitfalls, exercises, and references.
