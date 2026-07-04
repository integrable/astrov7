---
title: "Two-Point Functions"
description: "Derives the conformally fixed form of two-point functions, explains operator normalization and orthogonality, and records scalar and spinning two-point conventions."
sidebar:
  label: "Two-Point Functions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Osborn and Petkou 1994; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - two-point functions
  - conformal covariance
  - primary operators
  - operator normalization
  - reflection positivity
  - spinning correlators
  - conserved currents
canonicalTopics:
  - scalar-two-point-functions
  - spinning-two-point-functions
  - operator-normalization
  - cft-two-point-data
  - reflection-positivity
researchStatus:
  established:
    - 'At separated points, conformal symmetry fixes the two-point function of primary operators up to normalization and representation-theoretic selection rules.'
    - 'In a unitary theory, positive-norm Hermitian scalar primaries can be normalized so that $\langle\mathcal O_i(x)\mathcal O_j(0)\rangle=\delta_{ij}/|x|^{2\Delta_i}$.'
  active:
    - "Subtleties involving contact terms, defects, curved backgrounds, nonunitary theories, logarithmic CFTs, and Lorentzian distributions are treated in specialized later pages."
---

## Summary

A two-point function is the first nontrivial correlator of local operators. For scalar primary operators in flat Euclidean space, conformal symmetry fixes the separated-point answer to be

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{G_{ij}}{|x|^{2\Delta_i}},
\qquad \Delta_i=\Delta_j,
$$

and it vanishes when the two operators have incompatible scaling dimensions, spin, or internal charges. In an orthonormal real scalar basis, this becomes

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

This formula is simple, but it is load-bearing. It fixes what we mean by normalized operators, determines the identity contribution in the OPE, and makes later coefficients such as $\lambda_{ijk}$ meaningful numbers rather than basis-dependent decorations.

<figure class="doc-figure" style="--figure-width: 38rem;">

![Two scalar insertions in flat Euclidean space depend only on their separation after translations and rotations; scale and inversion covariance fix the power and require equal dimensions.](/figures/cft-bootstrap/two-point-separation.svg)

<figcaption>

For two scalar primaries in flat space, translations remove the center-of-mass point, rotations leave only $r=|x_{12}|$, dilatations fix the power of $r$, and inversion covariance requires the two dimensions to match.

</figcaption>
</figure>

Two-point functions are also the bridge between Euclidean correlators and Hilbert-space inner products in radial quantization. Reflection positivity says that the two-point matrix of physical operators must be positive. That positivity is the quiet engine behind the nonnegative coefficients that make the numerical conformal bootstrap possible.

## Prerequisites

You should know [Conventions and Notation](/cft-bootstrap/conventions/), [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/), and [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/).

This page uses flat Euclidean space $\mathbb R^d$ and separated insertions unless stated otherwise. Contact terms at coincident points are important for Ward identities and anomalies, but they are not part of the separated-point formulas derived here.

## Core idea

The two-point function of primary operators is fixed because there is almost no conformal invariant one can build from two separated points. Translations reduce the dependence to the difference

$$
x_{12}^\mu=x_1^\mu-x_2^\mu.
$$

Rotations reduce scalar dependence to $x_{12}^2$. Dilatations fix the power of $|x_{12}|$. Special conformal transformations, equivalently inversion plus translations plus inversion, impose the remaining selection rule: scalar primaries can have a nonzero two-point function only if their dimensions agree.

In radial quantization the same statement becomes linear algebra. A local operator at the origin creates a state,

$$
|\mathcal O_i\rangle=\mathcal O_i(0)|0\rangle,
$$

and the two-point function with the radially conjugate insertion computes an inner product. Operators with different $D$ eigenvalues are orthogonal, just as energy eigenstates with different energies are orthogonal in ordinary quantum mechanics.

The tiny formula

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{\delta_{ij}}{|x|^{2\Delta_i}}
$$

is therefore not only a correlator. It is a normalization convention, an orthogonality statement, and the first piece of the CFT data basis.

## Setup and conventions

We work in Euclidean flat space with metric $\delta_{\mu\nu}$. Differences and distances are

$$
x_{ij}^\mu=x_i^\mu-x_j^\mu,
\qquad
x_{ij}^2=\delta_{\mu\nu}x_{ij}^\mu x_{ij}^\nu,
\qquad
|x_{ij}|=(x_{ij}^2)^{1/2}.
$$

For a scalar primary of dimension $\Delta$, a finite conformal transformation $x\mapsto x'=f(x)$ with

$$
ds'^2=\Omega(x)^2 ds^2
$$

acts on separated-point correlators by the covariance rule

$$
\langle \mathcal O_1(x_1')\cdots \mathcal O_n(x_n')\rangle
=\prod_{a=1}^n \Omega(x_a)^{-\Delta_a}
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle,
$$

for scalar primaries. Spinning primaries also carry rotation matrices acting on their indices.

For inversion,

$$
x'^\mu=\frac{x^\mu}{x^2},
\qquad
\Omega(x)=\frac1{x^2},
$$

and distances transform as

$$
|x_1'-x_2'|
=\frac{|x_1-x_2|}{|x_1||x_2|}.
$$

These two facts are enough to finish the scalar two-point derivation.

## Scalar primary two-point functions

Let

$$
F_{12}(x_1,x_2)
=\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\rangle
$$

for scalar primaries of dimensions $\Delta_1$ and $\Delta_2$.

Translation invariance gives

$$
F_{12}(x_1,x_2)=F_{12}(x_{12}).
$$

Rotation invariance gives

$$
F_{12}(x_{12})=f(x_{12}^2).
$$

Dilatation covariance under $x\mapsto \lambda x$ gives

$$
F_{12}(\lambda x_{12})
=\lambda^{-\Delta_1-\Delta_2}F_{12}(x_{12}),
$$

so away from $x_{12}=0$,

$$
F_{12}(x_1,x_2)
=\frac{C_{12}}{|x_{12}|^{\Delta_1+\Delta_2}}.
$$

Now apply inversion. Conformal covariance gives

$$
F_{12}(x_1,x_2)
=|x_1|^{-2\Delta_1}|x_2|^{-2\Delta_2}
F_{12}(x_1',x_2').
$$

Using the distance transformation,

$$
F_{12}(x_1',x_2')
=\frac{C_{12}}{|x_1'-x_2'|^{\Delta_1+\Delta_2}}
=\frac{C_{12}|x_1|^{\Delta_1+\Delta_2}|x_2|^{\Delta_1+\Delta_2}}
{|x_{12}|^{\Delta_1+\Delta_2}}.
$$

Therefore

$$
F_{12}(x_1,x_2)
=\frac{C_{12}|x_1|^{-\Delta_1+\Delta_2}|x_2|^{\Delta_1-\Delta_2}}
{|x_{12}|^{\Delta_1+\Delta_2}}.
$$

For this to equal the dilatation answer for arbitrary $x_1,x_2$, either $C_{12}=0$ or

$$
\Delta_1=\Delta_2.
$$

Thus the nonzero scalar two-point function is

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\rangle
=\frac{C_{12}}{|x_{12}|^{2\Delta}},
\qquad
\Delta_1=\Delta_2=\Delta.
$$

This is the first example of a powerful CFT theme: symmetry often determines the coordinate dependence completely, while leaving a finite-dimensional space of constants.

## Operator bases and normalization

Suppose several scalar primaries have the same scaling dimension and the same internal quantum numbers. Then conformal symmetry allows a matrix of two-point coefficients,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{G_{ij}}{|x|^{2\Delta}}.
$$

In a unitary theory, reflection positivity implies that $G_{ij}$ is positive definite for non-null Hermitian operators. We may choose a basis that diagonalizes and normalizes it:

$$
G_{ij}=\delta_{ij}.
$$

This choice is not merely aesthetic. If we rescale

$$
\mathcal O_i\mapsto a_i\mathcal O_i,
$$

then

$$
G_{ij}\mapsto a_i a_j G_{ij},
$$

and three-point coefficients also rescale. Therefore the number $\lambda_{ijk}$ has no invariant meaning until the two-point normalization has been fixed.

For complex operators, or operators charged under an internal symmetry, the natural two-point function pairs an operator with its conjugate:

$$
\langle \mathcal O_i(x)\mathcal O_j^\dagger(0)\rangle
=\frac{\delta_{ij}}{|x|^{2\Delta_i}}
$$

in an orthonormal basis. A correlator such as $\langle \mathcal O(x)\mathcal O(0)\rangle$ can vanish by charge conservation even when $\langle \mathcal O(x)\mathcal O^\dagger(0)\rangle$ is nonzero.

## Internal symmetry selection rules

Conformal symmetry is not the only symmetry acting on two-point functions. If the theory has an internal symmetry group $G$, local operators transform in representations of $G$. The vacuum is usually invariant, so a two-point function can be nonzero only when the tensor product of the two representations contains the singlet.

For example, if $\mathcal O_a$ transforms in a real irreducible representation $R$ with invariant metric $\delta_{ab}$, then

$$
\langle \mathcal O_a(x)\mathcal O_b(0)\rangle
=\frac{\delta_{ab}}{|x|^{2\Delta}}
$$

after normalization. If $\mathcal O_a$ and $\widetilde{\mathcal O}_\alpha$ transform in inequivalent irreducible representations, then

$$
\langle \mathcal O_a(x)\widetilde{\mathcal O}_\alpha(0)\rangle=0.
$$

For charged complex operators, the invariant pairing is between conjugate representations. This is why one often writes charged two-point functions as $\langle \mathcal O(x)\mathcal O^\dagger(0)\rangle$ rather than $\langle \mathcal O(x)\mathcal O(0)\rangle$.

## Spinning two-point functions

For spinning primaries, conformal symmetry fixes not only the power of $|x|$ but also the tensor structure. The essential object is the inversion tensor

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

It obeys

$$
I_{\mu\rho}(x)I_{\rho\nu}(x)=\delta_{\mu\nu},
$$

and it describes how vectors rotate under inversion. For a spin-one primary $V_\mu$ of dimension $\Delta$,

$$
\langle V_\mu(x)V_\nu(0)\rangle
=\frac{C_V}{|x|^{2\Delta}}I_{\mu\nu}(x).
$$

For a symmetric traceless spin-$\ell$ primary, introduce a null polarization vector $z^\mu$ with $z^2=0$ and write

$$
\mathcal O(x,z)=\mathcal O_{\mu_1\cdots\mu_\ell}(x)z^{\mu_1}\cdots z^{\mu_\ell}.
$$

A compact two-point convention is

$$
\langle \mathcal O(x,z_1)\mathcal O(0,z_2)\rangle
=\frac{C_{\mathcal O}\left(z_1\cdot I(x)\cdot z_2\right)^\ell}{|x|^{2\Delta}}.
$$

The null-polarization trick hides traces, which is exactly the point: symmetric traceless tensors are represented by homogeneous polynomials modulo terms proportional to $z^2$.

For general Lorentz or rotation representations, the same principle holds. Two-point functions are diagonal between inequivalent irreducible representations, and the allowed tensor structures are fixed by conformal covariance up to normalization. The detailed taxonomy is deferred to [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/).

## Conserved currents and the stress tensor

A conserved spin-one current $J_\mu$ in a unitary CFT has

$$
\Delta_J=d-1,
\qquad
\partial^\mu J_\mu=0.
$$

Its separated-point two-point function is

$$
\langle J_\mu(x)J_\nu(0)\rangle
=\frac{C_J}{|x|^{2(d-1)}}I_{\mu\nu}(x),
$$

up to the convention used to normalize the associated charge. The conservation law is not an independent extra tensor structure; it is compatible with conformal covariance precisely at the conserved-current dimension.

The stress tensor is a conserved spin-two primary with

$$
\Delta_T=d,
\qquad
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0,
$$

again away from contact terms. The higher-dimensional convention used in this volume is

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=\frac{C_T}{|x|^{2d}}\mathcal I_{\mu\nu,\rho\sigma}(x),
$$

where

$$
\mathcal I_{\mu\nu,\rho\sigma}(x)
=\frac12\left(I_{\mu\rho}I_{\nu\sigma}+I_{\mu\sigma}I_{\nu\rho}\right)
-\frac1d\delta_{\mu\nu}\delta_{\rho\sigma}.
$$

The coefficient $C_T$ is positive in unitary theories with a nonzero stress tensor. Its numerical value is convention-dependent, so comparing $C_T$ across papers requires checking the tensor structure and the free-field normalization.

## Identity term in the OPE

The two-point function fixes the identity contribution in the OPE. In an orthonormal scalar basis,

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{\delta_{ij}}{|x|^{2\Delta_i}}\mathbf 1.
$$

Taking the vacuum expectation value and using

$$
\langle \mathbf 1\rangle=1
$$

reproduces the two-point function. This is the simplest consistency check between two-point normalization and OPE conventions.

For a non-orthonormal basis,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{G_{ij}}{|x|^{2\Delta}},
$$

the identity coefficient is $G_{ij}$ rather than $\delta_{ij}$. Many factor-of-$G$ mistakes in bootstrap calculations are just failures to distinguish a general operator basis from an orthonormal one. Tiny linear algebra gremlin, huge downstream chaos.

## Reflection positivity and Hilbert-space meaning

In radial quantization, define

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

The conjugate bra is represented by a radially reflected insertion at infinity, or equivalently by inversion. For a scalar primary, the conjugate insertion is schematically

$$
\langle \mathcal O|
=\lim_{x\to\infty}|x|^{2\Delta}\langle 0|\mathcal O(x).
$$

Then the two-point coefficient is the norm of the state:

$$
\langle \mathcal O_i|\mathcal O_j\rangle=G_{ij}.
$$

Reflection positivity says

$$
\sum_{i,j}c_i^*G_{ij}c_j\geq0
$$

for physical operators. If $G$ has a zero eigenvalue, the corresponding state is null and must be quotiented out in a unitary theory. If $G$ has a negative eigenvalue, the theory is not unitary in the usual Hilbert-space sense.

This positivity is why the identical-scalar OPE coefficients enter many bootstrap equations as squares,

$$
\lambda_{\phi\phi\mathcal O}^2\geq0,
$$

after the exchanged operators are normalized by their two-point functions.

## Two-dimensional language

In two dimensions, it is common to use complex coordinates

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2.
$$

A primary is labeled by holomorphic and antiholomorphic weights $(h,\bar h)$, with

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The two-point function of scalar primaries with $h=\bar h$ is the same formula in disguise. More generally, for primaries with weights $(h_i,\bar h_i)$,

$$
\langle \mathcal O_i(z,\bar z)\mathcal O_j(0,0)\rangle
=\frac{C_{ij}}{z^{2h_i}\bar z^{2\bar h_i}}
$$

when the weights match appropriately; otherwise it vanishes. Chiral fields have $\bar h=0$, antiholomorphic fields have $h=0$, and spin appears as the difference $h-\bar h$.

The two-dimensional formula has extra richness because the local conformal algebra enhances to the Virasoro algebra. That enhancement is not assumed in this higher-dimensional chapter; it is developed in [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/).

## Contact terms and separated points

The formulas above are separated-point formulas. They can be modified by distributions supported at coincident points, such as derivatives of delta functions. These terms do not change ordinary separated-point correlators, but they can be physically meaningful.

Contact terms appear in:

| Context | Why contact terms matter |
|---|---|
| Ward identities | Conserved charges act on operator insertions at coincident points. |
| Stress-tensor correlators | Curved-background variations generate contact terms. |
| Anomalies | Weyl and chiral anomalies are often visible through local terms. |
| Scheme dependence | Some contact terms can be shifted by local counterterms. |
| Fourier-space correlators | Polynomial momentum terms correspond to contact terms in position space. |

The bootstrap usually begins with separated-point four-point functions, where these subtleties are absent or controlled. Ward identity and anomaly pages bring them back carefully.

## Common pitfalls

**Comparing OPE coefficients before fixing two-point normalization.** If $\mathcal O\mapsto a\mathcal O$, then its two-point coefficient and its three-point coefficients change. Normalize first; compare second.

**Forgetting degeneracies.** If two operators have the same $\Delta$, spin, and internal quantum numbers, conformal symmetry allows mixing. You must diagonalize the two-point matrix before using a Kronecker delta.

**Pairing charged operators incorrectly.** A charged operator usually has a nonzero two-point function with its conjugate, not with itself.

**Treating contact terms as either always irrelevant or always physical.** At separated points they are invisible. In Ward identities and anomalies they can be the whole story. The context decides.

**Using $C_T$ without a convention.** The stress-tensor two-point coefficient depends on the tensor-structure normalization. A quoted number for $C_T$ needs its convention attached, preferably with the free-scalar or free-fermion normalization.

## Relations to other pages

[Conventions and Notation](/cft-bootstrap/conventions/) fixes the default two-point normalization used throughout the volume. [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) explains why spectra and OPE coefficients define the theory. [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) gives the geometric origin of the inner product used here.

The next pages, [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/) and [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), explain how normalized operators lead to meaningful three-point coefficients and reduced four-point functions. The OPE chapter then uses the two-point identity term and the three-point coefficients to build operator products.

For spin-one currents and stress tensors, see [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/) and [Stress-Tensor Multiplet Preview](/cft-bootstrap/operators-states-radial-quantization/stress-tensor-multiplet-preview/). Full current and stress-tensor correlator technology appears later in this chapter.

## Research status

The separated-point two-point functions of primary operators are settled conformal kinematics. The scalar formula, spinning inversion tensor, current two-point function, and stress-tensor two-point function are standard.

The active issues are not about whether the basic formula is true. They concern extensions and precision bookkeeping: tensor-structure bases for spinning and mixed correlators, contact terms in curved backgrounds, Lorentzian distributional correlators, defect and boundary two-point functions, logarithmic CFTs with non-diagonal dilatation action, and numerical conventions for current and stress-tensor normalization.

## Exercises

### Exercise 1: Derive the scalar power law

Use translations, rotations, and dilatations to show that a scalar two-point function must have the form

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\rangle
=\frac{C_{12}}{|x_{12}|^{\Delta_1+\Delta_2}}
$$

before imposing special conformal transformations.

<details><summary><strong>Solution</strong></summary>

Translation invariance implies dependence only on $x_{12}=x_1-x_2$. Rotation invariance implies dependence only on $r=|x_{12}|$. Under $x\mapsto \lambda x$, scalar primaries give

$$
F(\lambda r)=\lambda^{-\Delta_1-\Delta_2}F(r).
$$

The separated-point solution is therefore

$$
F(r)=\frac{C_{12}}{r^{\Delta_1+\Delta_2}}.
$$

This does not yet require $\Delta_1=\Delta_2$; that comes from inversion.

</details>

### Exercise 2: Use inversion to force equal dimensions

Starting from the answer in Exercise 1 and using

$$
|x_1'-x_2'|=\frac{|x_1-x_2|}{|x_1||x_2|},
\qquad
x'^\mu=\frac{x^\mu}{x^2},
$$

show that a nonzero scalar two-point function requires $\Delta_1=\Delta_2$.

<details><summary><strong>Solution</strong></summary>

Inversion covariance gives

$$
F(x_1,x_2)=|x_1|^{-2\Delta_1}|x_2|^{-2\Delta_2}F(x_1',x_2').
$$

The scale-invariant ansatz gives

$$
F(x_1',x_2')
=\frac{C_{12}|x_1|^{\Delta_1+\Delta_2}|x_2|^{\Delta_1+\Delta_2}}
{|x_{12}|^{\Delta_1+\Delta_2}}.
$$

Thus

$$
F(x_1,x_2)
=\frac{C_{12}|x_1|^{-\Delta_1+\Delta_2}|x_2|^{\Delta_1-\Delta_2}}
{|x_{12}|^{\Delta_1+\Delta_2}}.
$$

For this to equal the original expression for arbitrary $x_1,x_2$, the powers of $|x_1|$ and $|x_2|$ must vanish. Hence $\Delta_1=\Delta_2$, unless $C_{12}=0$.

</details>

### Exercise 3: Check current conservation

Show that

$$
\partial^\mu\left(\frac{I_{\mu\nu}(x)}{|x|^{2\Delta}}\right)=0
$$

only when $\Delta=d-1$.

<details><summary><strong>Solution</strong></summary>

Using

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2},
$$

one finds

$$
\partial^\mu\left(\frac{I_{\mu\nu}(x)}{|x|^{2\Delta}}\right)
=2(\Delta-d+1)\frac{x_\nu}{|x|^{2\Delta+2}}.
$$

Therefore the divergence vanishes at separated points precisely when

$$
\Delta=d-1.
$$

This is the spin-one conserved-current dimension.

</details>

### Exercise 4: Rescale an exchanged operator

Suppose $\mathcal O$ has two-point coefficient $G_{\mathcal O}$ and appears in the OPE $\phi\times\phi$ with coefficient $\lambda_{\phi\phi\mathcal O}$. If $\mathcal O\mapsto a\mathcal O$, how do $G_{\mathcal O}$ and $\lambda_{\phi\phi\mathcal O}$ change?

<details><summary><strong>Solution</strong></summary>

The two-point coefficient scales as

$$
G_{\mathcal O}\mapsto a^2G_{\mathcal O}.
$$

With the convention

$$
\phi(x)\phi(0)\supset \lambda_{\phi\phi\mathcal O}|x|^{\Delta_{\mathcal O}-2\Delta_\phi}\mathcal O(0),
$$

the same operator product is kept fixed only if

$$
\lambda_{\phi\phi\mathcal O}\mapsto a^{-1}\lambda_{\phi\phi\mathcal O}.
$$

This is why bootstrap coefficients are usually quoted after choosing $G_{\mathcal O}=1$.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters on global conformal invariance, two-dimensional conformal invariance, and the operator formalism.
- H. Osborn and A. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals of Physics* **231** (1994), for current and stress-tensor two- and three-point structures in general dimension.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for a concise modern derivation of scalar correlators and unitarity conventions.
- D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for radial quantization, reflection positivity, and bootstrap normalization.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), for the connection between two-point normalization, OPE coefficients, conformal blocks, and numerical bootstrap.

## Version history

- 2026-06-27: First polished draft. Derived scalar two-point functions, recorded scalar and spinning conventions, and connected two-point normalization to OPE and bootstrap positivity.
