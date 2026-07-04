---
title: "Conserved Currents"
description: "How global symmetries appear in higher-dimensional CFT through conserved spin-one primary operators, Ward identities, charges, two-point normalizations, and current OPEs."
sidebar:
  label: "Conserved Currents"
  order: 3
level: Graduate
status: "Polished draft"
source: "Osborn and Petkou; Rychkov lectures; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019; conformal Ward identity literature."
topics:
  - conserved currents
  - global symmetries
  - Ward identities
  - higher-dimensional CFT
  - current normalization
canonicalTopics:
  - conserved-currents
  - global-symmetry-current
  - cft-ward-identities
researchStatus:
  established:
    - "In a unitary higher-dimensional CFT, an ordinary continuous global symmetry is represented by a conserved spin-one primary current of dimension d-1."
  active:
    - "Current correlators, anomalies, conformal collider constraints, generalized symmetries, defects, and numerical bootstrap systems with global symmetry remain active areas."
---

## Summary

A continuous ordinary global symmetry in a higher-dimensional CFT is represented by a conserved spin-one current

$$
J_\mu^a(x),
\qquad
\partial^\mu J_\mu^a=0,
$$

where $a$ is an adjoint index of the global symmetry algebra. In a unitary CFT, a conserved current is a primary operator with fixed scaling dimension

$$
\Delta_J=d-1.
$$

Its charge on a sphere surrounding an insertion is

$$
Q^a=\int_{S^{d-1}}dS^\mu\,J_\mu^a,
$$

and the Ward identity says that this charge acts on local operators by the corresponding symmetry generator.

The two-point function is fixed by conformal symmetry and conservation up to one positive normalization constant:

$$
\langle J_\mu^a(x)J_\nu^b(0)\rangle
=\frac{C_J\delta^{ab}I_{\mu\nu}(x)}{(x^2)^{d-1}},
\qquad
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The number $C_J$ is a higher-dimensional analogue of a current two-point normalization. It is not a central charge in the Virasoro sense, but it is physical after a convention for symmetry generators is fixed. It appears in bootstrap bounds, current correlators, conformal collider physics, and comparisons between CFTs.

## Prerequisites

Read [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) first. You should also know [Conformal Symmetry in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/conformal-symmetry-in-higher-dimensions/), [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/), and [Current OPE](/cft-bootstrap/operator-product-expansion/current-ope/) if those pages are available.

This page treats ordinary zero-form global symmetries. Higher-form symmetries have conserved higher-rank currents and extended charged operators; they are conceptually related but not the main subject here.

## Core idea

Noether's theorem says that a continuous global symmetry has a conserved current. In a CFT, the same current is not merely conserved: it is a conformal primary or a descendant equivalent to one, with spin one and dimension $d-1$.

The conservation equation

$$
\partial^\mu J_\mu^a=0
$$

is a shortening condition in conformal representation theory. It says that the divergence descendant is null and decouples. The charge

$$
Q^a=\int_\Sigma dS^\mu J_\mu^a
$$

is independent of smooth deformations of the closed surface $\Sigma$, as long as the surface does not cross charged operator insertions.

The basic picture is

$$
\text{global symmetry}
\quad\Longleftrightarrow\quad
\text{conserved spin-one primary}
\quad\Longleftrightarrow\quad
\text{Ward identities for charged operators}.
$$

In higher-dimensional CFT, conserved currents are among the most important protected operators, together with the stress tensor.

## Setup and conventions

Let $G$ be a continuous global symmetry group with Lie algebra generators $T^a$ satisfying

$$
[T^a,T^b]=i f^{ab}{}_c T^c.
$$

Local primary operators $\mathcal O_i$ transform in representations $R_i$ with matrices $T_i^a$:

$$
\delta^a\mathcal O_i=(T_i^a\mathcal O_i).
$$

The associated conserved current is

$$
J_\mu^a(x),
\qquad
\partial^\mu J_\mu^a(x)=0
$$

away from contact terms. We use Euclidean signature and normalize the area of the unit $(d-1)$-sphere as

$$
\omega_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

The distributional identity

$$
\partial^\mu\left(\frac{x_\mu}{\omega_{d-1}|x|^d}\right)=\delta^{(d)}(x)
$$

is useful for fixing Ward-identity coefficients. Different signs appear in the literature depending on whether charges act on operators by commutator, infinitesimal variation, or anti-Hermitian generators. This page prioritizes consistency over a universal sign convention.

## Dimension from unitarity

A spin-one primary in a unitary CFT obeys the unitarity bound

$$
\Delta\ge d-1.
$$

At the bound, the divergence descendant has zero norm:

$$
\partial^\mu J_\mu=0.
$$

Thus a conserved current has

$$
\Delta_J=d-1.
$$

Conversely, if a spin-one primary saturates this bound in a unitary CFT, it is conserved and generates a global symmetry, up to subtleties involving decoupled sectors or improvements.

This is the higher-dimensional analogue of a short representation. In two-dimensional CFT, chiral currents have holomorphic OPEs and Kac–Moody algebras. In $d>2$, the finite conformal algebra still forces the current dimension, but there is no generic infinite-dimensional current algebra.

## Charges and surface independence

Given a closed codimension-one surface $\Sigma$, define

$$
Q^a_\Sigma=\int_\Sigma dS^\mu J_\mu^a.
$$

If $\Sigma$ is smoothly deformed without crossing operator insertions, conservation gives

$$
Q^a_\Sigma=Q^a_{\Sigma'}.
$$

Indeed, the difference between the two charges is an integral over the region $M$ between the surfaces:

$$
Q^a_\Sigma-Q^a_{\Sigma'}
=\int_M d^dx\,\partial^\mu J_\mu^a=0,
$$

provided there are no contact terms inside $M$.

If the surface crosses a charged local operator, the charge changes by the action of the symmetry generator. This is the geometric form of a Ward identity.

In radial quantization, taking $\Sigma=S^{d-1}$ around the origin gives a charge operator acting on the Hilbert space on the sphere. Charged states are created by charged local operators through the state-operator correspondence.

## Ward identity for local operators

The current Ward identity in a correlation function is

$$
\partial^\mu\langle J_\mu^a(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=-\sum_{i=1}^n\delta^{(d)}(x-x_i)
\langle \mathcal O_1(x_1)\cdots (T_i^a\mathcal O_i)(x_i)\cdots\mathcal O_n(x_n)\rangle,
$$

up to the overall sign convention for $T_i^a$. Integrating over a region containing all insertions gives the global Ward identity

$$
\sum_{i=1}^n
\langle \mathcal O_1\cdots (T_i^a\mathcal O_i)\cdots\mathcal O_n\rangle=0.
$$

This says that a nonzero correlator must be invariant under the global symmetry.

For an abelian $U(1)$ symmetry, if $\mathcal O_i$ has charge $q_i$, the Ward identity implies the selection rule

$$
\sum_i q_i=0
$$

for a nonzero correlator on the sphere.

For nonabelian $G$, the correlator must be an invariant tensor in

$$
R_1\otimes R_2\otimes\cdots\otimes R_n.
$$

## Current OPE with charged operators

The Ward identity implies the leading current OPE with a charged local operator. With the convention above,

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
-\frac{x_\mu}{\omega_{d-1}|x|^d}(T_i^a\mathcal O_i)(0)+\cdots .
$$

The coefficient is fixed by integrating over a small sphere around the origin:

$$
\int_{S^{d-1}_\epsilon}dS^\mu\frac{x_\mu}{\omega_{d-1}|x|^d}=1.
$$

Thus the charge contour or surface integral acts as the generator $T_i^a$ on $\mathcal O_i$.

The ellipsis includes less singular terms and contributions from other operators allowed by symmetry. The leading singularity is universal because it is fixed by the Ward identity. It does not depend on the microscopic Lagrangian or on a weak-coupling description.

This is the higher-dimensional analogue of the current-primary OPE in two dimensions, but with a power-law singularity rather than a holomorphic simple pole.

## Two-point normalization

Conformal symmetry fixes the current two-point function to be

$$
\langle J_\mu^a(x)J_\nu^b(0)\rangle
=\frac{C_J\delta^{ab}I_{\mu\nu}(x)}{(x^2)^{d-1}},
$$

where

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The conservation equation holds for $x\ne0$:

$$
\partial^\mu\left[\frac{I_{\mu\nu}(x)}{(x^2)^{d-1}}\right]=0.
$$

The coefficient $C_J$ depends on the normalization of the symmetry generators. If one rescales

$$
T^a\mapsto \alpha T^a,
$$

then the current and $C_J$ rescale. Therefore $C_J$ is meaningful only after the generator normalization is fixed.

In a unitary CFT, $C_J$ is positive for a nontrivial conserved current. It is a physical observable in a chosen convention and can be compared across theories with the same global symmetry normalization.

## Three-point functions and current algebra data

Current three-point functions are constrained by conformal symmetry, global symmetry, and conservation. For a nonabelian symmetry, the correlator

$$
\langle J_\mu^a(x_1)J_\nu^b(x_2)J_\rho^c(x_3)\rangle
$$

has group-theory tensors such as

$$
f^{abc}
$$

and, when allowed by the group and representation content,

$$
d^{abc}.
$$

The precise number of independent conformal tensor structures depends on $d$, parity, and the symmetry group. Ward identities relate some coefficients to the current two-point normalization and to anomaly coefficients when anomalies exist.

The phrase “current algebra” can mean different things in different dimensions. In two dimensions, holomorphic currents obey a local Kac–Moody OPE with a level. In $d>2$, there is no generic holomorphic current algebra. The algebra of charges is still the finite Lie algebra:

$$
[Q^a,Q^b]=i f^{ab}{}_c Q^c,
$$

but local current OPEs are higher-dimensional OPEs with many possible operators, not a two-term Kac–Moody OPE.

## Currents in the OPE

If two operators transform under $G$, their OPE is constrained by global symmetry. For charged scalars $\phi_i$ and $\phi_j$, the OPE can contain the current if the tensor product of their representations contains the adjoint:

$$
R_i\otimes R_j\supset \operatorname{Adj}(G).
$$

For example, in an $O(N)$ model with fundamental scalars $\phi_i$, the OPE decomposes into singlet, symmetric traceless, and antisymmetric sectors:

$$
\phi_i\times\phi_j
\sim
\delta_{ij}(\text{singlets})
+\left(\text{symmetric traceless}\right)_{ij}
+\left(\text{antisymmetric}\right)_{ij}.
$$

The $O(N)$ conserved current belongs to the antisymmetric representation. Its dimension is fixed:

$$
\Delta_J=d-1,
$$

and its OPE coefficient with $\phi_i\phi_j$ is related by Ward identities to the charge normalization and to $C_J$.

In numerical bootstrap, imposing a conserved current in a particular global-symmetry sector is a powerful spectral assumption.

## Flavor central charges and bootstrap normalizations

Bootstrap papers often define a **flavor central charge** or current central charge, commonly denoted $C_J$, sometimes normalized so that a free real scalar or free fermion has a specified value.

There is no universal convention across all papers. Common choices differ by factors involving

$$
\omega_{d-1},
\qquad
2\pi,
\qquad
\operatorname{Tr}(T^aT^b),
\qquad
\text{and representation indices}.
$$

The invariant procedure is:

1. Fix the generator normalization, for example $\operatorname{Tr}_R(T^aT^b)=I_R\delta^{ab}$.
2. Define the current by the Ward identity.
3. Read $C_J$ from the two-point function.
4. Use the same convention when comparing OPE coefficients or collider bounds.

This is analogous to level normalization in current-algebra CFT, but in $d>2$ there is no generic Kac–Moody level. The current two-point coefficient is the key normalization.

## Anomalies and background fields

A global current can be coupled to a nondynamical background gauge field $A_\mu^a$:

$$
\delta S=\int d^dx\,A_\mu^aJ^{a\mu}.
$$

This is a diagnostic tool. It lets one define current correlators, Ward identities, contact terms, and possible 't Hooft anomalies.

An ordinary global symmetry has an 't Hooft anomaly if the generating functional cannot be made invariant under background gauge transformations while preserving locality and other required symmetries. An anomaly does not mean the global symmetry is absent. It means the symmetry cannot be gauged without adding extra degrees of freedom or anomaly inflow.

In even spacetime dimensions, anomalies can appear in current correlation functions. In odd dimensions, parity-odd contact terms and Chern–Simons-like background terms can play an analogous role in classifying contact-term ambiguities.

This page does not develop anomaly theory in detail. The main point is that conserved currents are the local operators through which ordinary global symmetries couple to backgrounds.

## Higher-form symmetry preview

Ordinary global symmetries act on local operators and have conserved one-form currents $J_\mu$. Modern QFT also uses higher-form symmetries. A $q$-form global symmetry acts on $q$-dimensional extended operators and is associated with a conserved $(q+1)$-form current.

For example, in $d$ dimensions a one-form symmetry has a conserved two-form current

$$
J_{\mu\nu},
\qquad
\partial^\mu J_{\mu\nu}=0,
$$

and charged objects are line operators rather than local operators.

This is not the same as the spin-one current studied in most of this page. The similarity is structural: conserved currents define topological charge operators by integration over closed surfaces. The difference is the dimension of the charged objects and the degree of the current.

Higher-form symmetries are important in gauge theories, line operators, confinement, and modern generalized-symmetry language.

## Examples

### Free complex scalar

A free complex scalar has a $U(1)$ current

$$
J_\mu=i\left(\phi^\dagger\partial_\mu\phi-(\partial_\mu\phi^\dagger)\phi\right).
$$

At the free fixed point in $d$ dimensions, the scalar has dimension

$$
\Delta_\phi=\frac{d-2}{2},
$$

and the current has dimension

$$
\Delta_J=2\Delta_\phi+1=d-1.
$$

The equation of motion implies conservation. In an interacting CFT with the same global symmetry, the current dimension remains $d-1$ because conservation protects it.

### O(N) models

In an $O(N)$ CFT with fundamental fields or order parameters $\phi_i$, the conserved currents are antisymmetric:

$$
J_\mu^{ij}=-J_\mu^{ji}.
$$

They generate rotations in the $ij$ plane. In the $\phi_i\times\phi_j$ OPE, they appear in the antisymmetric sector with spin one and dimension $d-1$.

In bootstrap studies of $O(N)$ models, the existence of this current is one of the basic exact pieces of spectral data.

## Common pitfalls

**Do not confuse global symmetries with gauge redundancies.** A global symmetry has gauge-invariant charged operators and a conserved current. A gauge redundancy is not itself a physical global symmetry.

**Do not call $C_J$ a Virasoro central charge.** In $d>2$, $C_J$ is a current two-point normalization. It is analogous in importance, but not the same object as the two-dimensional central charge $c$.

**Do not forget generator normalization.** Rescaling the symmetry generators rescales the current and $C_J$. Comparisons require a fixed convention.

**Do not assume every vector primary is conserved.** Conservation occurs only at the unitarity bound $\Delta=d-1$.

**Do not import Kac–Moody OPEs into $d>2$.** Higher-dimensional current OPEs are not holomorphic current algebras. The finite charges obey the Lie algebra, but the local OPE contains the usual higher-dimensional tower of operators.

**Do not ignore contact terms.** Ward identities for currents are distributional equations. Contact terms are essential, especially when coupling to background fields or discussing anomalies.

**Do not confuse ordinary and higher-form symmetries.** Ordinary currents act on local operators. Higher-form currents act on extended operators.

## Relations to other pages

This page follows [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) and prepares [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), where the conserved spin-two operator is treated separately.

It connects to [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/) through shortening at $\Delta=d-1$, to [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) through $C_J$, and to [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) through global-symmetry representations.

For two-dimensional current algebras, see [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/). For generalized symmetries, see the later symmetry and gauge-theory chapters.

## Research status

The relation between ordinary continuous global symmetries, conserved spin-one currents, charges, Ward identities, and current two-point functions is established in higher-dimensional CFT.

Active work concerns sharper constraints and broader contexts: current and stress-tensor mixed correlators, conformal collider bounds, anomalies and contact terms, global symmetries in gauge theories, generalized symmetries, defect-localized currents, non-invertible symmetry, and numerical bootstrap bounds on $C_J$ and charged spectra.

## Exercises

### Exercise 1

Use the distributional identity

$$
\partial^\mu\left(\frac{x_\mu}{\omega_{d-1}|x|^d}\right)=\delta^{(d)}(x)
$$

to check the leading current OPE coefficient for a charged operator.

<details><summary><strong>Solution</strong></summary>

Suppose

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
-\frac{x_\mu}{\omega_{d-1}|x|^d}(T_i^a\mathcal O_i)(0).
$$

Taking the divergence gives

$$
\partial^\mu J_\mu^a(x)\mathcal O_i(0)
\sim
-\delta^{(d)}(x)(T_i^a\mathcal O_i)(0).
$$

This is precisely the contact term in the Ward identity with the sign convention used on this page.

</details>

### Exercise 2

Show that the current two-point function has the correct scaling dimension.

<details><summary><strong>Solution</strong></summary>

A conserved current in $d$ dimensions has dimension

$$
\Delta_J=d-1.
$$

A two-point function of two operators of dimension $\Delta_J$ must scale as

$$
|x|^{-2\Delta_J}=|x|^{-2(d-1)}.
$$

The formula

$$
\langle J_\mu^a(x)J_\nu^b(0)\rangle
=\frac{C_J\delta^{ab}I_{\mu\nu}(x)}{(x^2)^{d-1}}
$$

has denominator

$$
(x^2)^{d-1}=|x|^{2(d-1)},
$$

and $I_{\mu\nu}(x)$ is dimensionless. Therefore the scaling is correct.

</details>

### Exercise 3

For a $U(1)$ symmetry, derive the charge-neutrality condition for a nonzero sphere correlator.

<details><summary><strong>Solution</strong></summary>

If $\mathcal O_i$ has charge $q_i$, the global Ward identity is

$$
\sum_i q_i\langle \mathcal O_1\cdots\mathcal O_n\rangle=0.
$$

If the correlator is nonzero, the prefactor must vanish:

$$
\sum_i q_i=0.
$$

Thus a nonzero sphere correlator must have total $U(1)$ charge zero.

</details>

### Exercise 4

Explain why an $O(N)$ current appears in the antisymmetric sector of $\phi_i\times\phi_j$.

<details><summary><strong>Solution</strong></summary>

The generators of $O(N)$ are antisymmetric matrices. Therefore the conserved current carries two antisymmetric fundamental indices:

$$
J_\mu^{ij}=-J_\mu^{ji}.
$$

The tensor product of two fundamentals decomposes into singlet, symmetric traceless, and antisymmetric sectors:

$$
\mathbf N\otimes\mathbf N=\mathbf 1\oplus\mathbf{S}\oplus\mathbf{A}.
$$

Since $J_\mu^{ij}$ is antisymmetric in $i,j$, it belongs to the antisymmetric sector $\mathbf A$ of the $\phi_i\times\phi_j$ OPE.

</details>

## References

- H. Osborn and A. Petkou, "Implications of conformal invariance in field theories for general dimensions," *Annals of Physics* **231** (1994).
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, "TASI Lectures on the Conformal Bootstrap," 2016.
- D. Poland, S. Rychkov, and A. Vichi, "The Conformal Bootstrap: Theory, Numerical Techniques, and Applications," *Reviews of Modern Physics* **91** (2019).
- D. M. Hofman and J. Maldacena, "Conformal collider physics: Energy and charge correlations," *Journal of High Energy Physics* **2008**.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, "Generalized Global Symmetries," *Journal of High Energy Physics* **2015**.

## Version history

- 2026-06-30: First polished draft. Added conserved-current definition, Ward identities, current OPE, charge surface interpretation, two-point normalization, anomaly and higher-form previews, examples, pitfalls, exercises, and references.
