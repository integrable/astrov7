---
title: "Three-Point Functions"
description: "Defines and derives conformal three-point functions, explains their relation to OPE coefficients, and records the main scalar and spinning structures used in CFT."
sidebar:
  label: "Three-Point Functions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Osborn and Petkou 1994; Rychkov 2016; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - correlation functions
  - three-point functions
  - OPE coefficients
  - tensor structures
canonicalTopics:
  - cft-three-point-functions
  - conformal-kinematics
  - ope-coefficients
  - spinning-correlators
researchStatus:
  established:
    - "The coordinate dependence of scalar-primary three-point functions is fixed by global conformal symmetry up to constants once two-point normalizations are chosen."
    - "Three-point coefficients are part of the CFT data and appear as the structure constants of the local-operator algebra."
  active:
    - "For spinning operators, defects, supersymmetry, parity-odd structures, and Lorentzian observables, the classification and use of three-point tensor structures remains an active practical interface between representation theory and bootstrap computations."
---

## Summary

Three-point functions are the first correlation functions in a CFT that contain dynamical numbers. For scalar primary operators $\mathcal O_i$, conformal symmetry fixes the entire position dependence:

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{\lambda_{ijk}}
{x_{12}^{\Delta_i+\Delta_j-\Delta_k}
 x_{13}^{\Delta_i+\Delta_k-\Delta_j}
 x_{23}^{\Delta_j+\Delta_k-\Delta_i}},
$$

where $x_{ij}=|x_i-x_j|$ in Euclidean signature. The constant $\lambda_{ijk}$ is a three-point coefficient. After a convention for two-point functions is fixed, these constants are the OPE coefficients with one index lowered.

This is the first place where the phrase **CFT data** becomes concrete:

$$
\text{CFT data}
=
\{\text{operator spectrum},\ \text{two-point metric},\ \lambda_{ijk}\}.
$$

The two-point function tells us which operators are orthogonal and how they are normalized. The three-point function tells us how two local operators multiply into a third. Four-point functions then test whether this multiplication is associative.

:::note[One line to remember]
For scalar primaries, conformal symmetry fixes the *shape* of every three-point function; dynamics begins in the constants $\lambda_{ijk}$.
:::

## Prerequisites

You should know [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), and the basic form of [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/). The relation to multiplication of local operators is developed further in the [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) chapter.

For a first pass, it is enough to focus on scalar primaries in flat Euclidean space. Spinning tensor structures, conserved-current normalizations, and two-dimensional Virasoro refinements can be read after the basic scalar formula is familiar.

## Core idea

A three-point configuration has no continuous conformal invariant. Translations remove one point, rotations and dilatations simplify the relative separation, and special conformal transformations remove the last shape parameter. Equivalently, conformal symmetry is large enough to map any generic ordered triple of points to a standard triple.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A three-point configuration mapped to a conformal frame](/figures/cft-bootstrap/three-point-conformal-frame.svg)

<figcaption>

A generic three-point configuration has no conformal cross ratio. Conformal symmetry fixes the coordinate dependence; the remaining scalar-primary data are the constants $\lambda_{ijk}$.

</figcaption>
</figure>

This is why two- and three-point functions look so rigid, while four-point functions contain an arbitrary function of cross ratios. The sequence is:

| Correlator | Conformal freedom left |
|---|---|
| Two scalar primaries | Only a normalization and a selection rule. |
| Three scalar primaries | One number $\lambda_{ijk}$ for each allowed triple. |
| Four scalar primaries | A function of two cross ratios, constrained by OPE and crossing. |

The constant $\lambda_{ijk}$ is not decorative. It is a physical observable of the CFT, subject to normalization conventions. In a Lagrangian theory it can sometimes be computed perturbatively; in a non-Lagrangian theory it may be obtained from bootstrap, duality, localization, integrability, lattice input, or other nonperturbative methods.

## Setup and conventions

Unless stated otherwise, this page uses the CFT conventions of [Conventions and Notation](/cft-bootstrap/conventions/): flat Euclidean space, scalar primaries normalized by

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{G_{ij}}{|x|^{2\Delta_i}},
$$

with $G_{ij}$ the two-point metric on the space of operators of the same spin, dimension, and quantum numbers. In an orthonormal basis of real scalar primaries, $G_{ij}=\delta_{ij}$.

We write

$$
x_{ij}=|x_i-x_j|,
\qquad
x_{ij}^2=(x_i-x_j)^2.
$$

The scalar formula below uses powers of $x_{ij}$, not powers of $x_{ij}^2$. Equivalently, it may be written with powers of $x_{ij}^2$ divided by two:

$$
x_{ij}^{\alpha}=(x_{ij}^2)^{\alpha/2}.
$$

For complex operators, charged operators, and multiplets, do not silently identify raised and lowered operator indices. The coefficient $\lambda_{ijk}$ with all indices lowered is related to an OPE coefficient $\lambda_{ij}{}^k$ by the two-point metric:

$$
\lambda_{ijk}=\lambda_{ij}{}^\ell G_{\ell k}.
$$

In an orthonormal real basis this distinction disappears. In a general basis it is exactly where many wrong factors hide.

## Scalar primaries

Let $\mathcal O_i$, $\mathcal O_j$, and $\mathcal O_k$ be scalar primary operators of dimensions $\Delta_i$, $\Delta_j$, and $\Delta_k$. Translation and rotation invariance imply that the three-point function depends only on distances:

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=F(x_{12},x_{13},x_{23}).
$$

A homogeneous ansatz is

$$
F=\frac{C}{x_{12}^{a}x_{13}^{b}x_{23}^{c}}.
$$

Dilatation invariance requires

$$
a+b+c=\Delta_i+\Delta_j+\Delta_k.
$$

This single equation is not enough. The special conformal constraint is most efficiently imposed using inversion. Under inversion,

$$
x^\mu\mapsto x'^\mu=\frac{x^\mu}{x^2},
\qquad
x'_{mn}=\frac{x_{mn}}{|x_m||x_n|}.
$$

A scalar primary transforms with the appropriate Weyl weight, so covariance of the correlator forces

$$
a+b=2\Delta_i,
\qquad
 a+c=2\Delta_j,
\qquad
 b+c=2\Delta_k.
$$

Solving gives

$$
a=\Delta_i+\Delta_j-\Delta_k,
\qquad
b=\Delta_i+\Delta_k-\Delta_j,
\qquad
c=\Delta_j+\Delta_k-\Delta_i.
$$

Therefore

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{\lambda_{ijk}}
{x_{12}^{\Delta_i+\Delta_j-\Delta_k}
 x_{13}^{\Delta_i+\Delta_k-\Delta_j}
 x_{23}^{\Delta_j+\Delta_k-\Delta_i}}
$$

for scalar primaries.

The exponents need not be positive. If, for example, $\Delta_k>\Delta_i+\Delta_j$, the factor $x_{12}^{\Delta_i+\Delta_j-\Delta_k}$ moves to the numerator. That is not a problem; it says how the correlator behaves when $x_1$ approaches $x_2$ if such an operator appears in the OPE.

:::caution[Do not over-read the exponent signs]
Conformal kinematics allows any dimensions satisfying the representation-theoretic constraints of the theory. The signs of the exponents in the three-point formula are not by themselves unitarity constraints.
:::

## Relation to the OPE

The operator product expansion of two scalar primaries has the schematic form

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k \lambda_{ij}{}^k\,|x|^{\Delta_k-\Delta_i-\Delta_j}
\bigl(\mathcal O_k(0)+\text{descendants}\bigr).
$$

The descendant terms are not optional; they are fixed by conformal symmetry once the primary contribution is present. However, the single coefficient multiplying the whole conformal family is $\lambda_{ij}{}^k$.

To see the connection with the three-point function, insert the OPE into a correlator with $\mathcal O_\ell(y)$:

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal O_\ell(y)\rangle
\sim
\sum_k \lambda_{ij}{}^k |x|^{\Delta_k-\Delta_i-\Delta_j}
\langle \mathcal O_k(0)\mathcal O_\ell(y)\rangle+\text{descendant terms}.
$$

Using the two-point function gives

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal O_\ell(y)\rangle
\sim
\sum_k \lambda_{ij}{}^k G_{k\ell}
\frac{|x|^{\Delta_k-\Delta_i-\Delta_j}}{|y|^{2\Delta_k}}
+\text{controlled corrections}.
$$

Thus

$$
\lambda_{ij\ell}=\lambda_{ij}{}^kG_{k\ell}.
$$

This is why two-point normalization matters. If you rescale an operator by

$$
\mathcal O_i\mapsto a_i\mathcal O_i,
$$

then

$$
G_{ij}\mapsto a_ia_jG_{ij},
\qquad
\lambda_{ijk}\mapsto a_ia_ja_k\lambda_{ijk}.
$$

The invariant content is not the raw symbol $\lambda_{ijk}$ by itself, but the CFT data together with a declared normalization convention.

## Selection rules

A three-point coefficient can vanish for many reasons. Some are dynamical; others are forced by symmetry.

### Scaling dimensions

The two-point function imposes the strong rule that scalar primaries with different dimensions have zero two-point function. Three-point functions have no analogous equality-of-dimensions rule. Operators of three different dimensions can have a nonzero three-point coefficient.

### Internal symmetries

If the theory has an internal global symmetry, $\lambda_{ijk}$ must be an invariant tensor in the product of the three representations. For an Abelian symmetry with charges $q_i$, $q_j$, and $q_k$, a necessary condition is

$$
q_i+q_j+q_k=0.
$$

For a $\mathbb Z_2$ symmetry, the product of parities must be even. In the Ising CFT, for example, the schematic selection rule is

$$
\sigma\times \sigma\times \varepsilon: \text{allowed},
\qquad
\sigma\times\sigma\times\sigma: \text{forbidden},
$$

because $\sigma$ is odd and $\varepsilon$ is even.

### Spin and parity

For spinning operators, rotation invariance and parity further restrict allowed tensor structures. In a parity-invariant theory, parity-odd tensor structures have zero coefficients unless the operator content or background allows parity violation.

### Identical operators

If two or three operators are identical bosonic scalars, permutation symmetry imposes corresponding symmetry of the coefficient and can eliminate some spin structures. For example, in the OPE of two identical scalar bosons, only even-spin symmetric traceless primaries appear in the parity-even scalar channel.

## Spinning operators

Scalar three-point functions have one coordinate structure. Spinning three-point functions can have several independent tensor structures.

A symmetric traceless spin-$\ell$ primary may be packaged with a null polarization vector $z^\mu$ satisfying $z^2=0$:

$$
\mathcal O_{\Delta,\ell}(x,z)
=\mathcal O_{\mu_1\cdots\mu_\ell}(x)z^{\mu_1}\cdots z^{\mu_\ell}.
$$

For two scalars and one symmetric traceless spin-$\ell$ primary, conformal symmetry fixes the structure up to one coefficient:

$$
\langle \phi_i(x_1)\phi_j(x_2)\mathcal O_{\Delta,\ell}(x_3,z)\rangle
=
\frac{\lambda_{ij\mathcal O}\,\bigl(z\cdot V_{3,12}\bigr)^\ell}
{x_{12}^{\Delta_i+\Delta_j-\Delta+\ell}
 x_{13}^{\Delta_i+\Delta-\Delta_j-\ell}
 x_{23}^{\Delta_j+\Delta-\Delta_i-\ell}},
$$

where

$$
V_{3,12}^\mu
=\frac{x_{31}^\mu}{x_{31}^2}-\frac{x_{32}^\mu}{x_{32}^2}.
$$

The null-vector condition $z^2=0$ automatically removes traces. In index notation the numerator means the symmetric traceless projection of $V_{3,12}^{\mu_1}\cdots V_{3,12}^{\mu_\ell}$.

With more spinning operators, the number of structures increases. A generic spinning three-point function has the form

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\sum_{a}\lambda^{(a)}_{123}\,\mathcal T_a(x_i,z_i),
$$

where $\mathcal T_a$ are independent conformally invariant tensor structures. The coefficients $\lambda^{(a)}_{123}$ are part of the CFT data.

:::note[Spinning data]
For spinning operators, “the OPE coefficient” often really means a vector of coefficients, one for each allowed tensor structure.
:::

## Conserved currents and stress tensors

Conserved operators are special because Ward identities fix some of their three-point coefficients.

For a global symmetry current $J_\mu^a$, the Ward identity has the schematic form

$$
\partial^\mu\langle J_\mu^a(x)\mathcal O_i(x_1)\mathcal O_j(x_2)\rangle
=
-\delta^{(d)}(x-x_1)(T^a)_i{}^k\langle \mathcal O_k(x_1)\mathcal O_j(x_2)\rangle
-\delta^{(d)}(x-x_2)(T^a)_j{}^k\langle \mathcal O_i(x_1)\mathcal O_k(x_2)\rangle,
$$

up to sign conventions for the symmetry generators. This means that the $J\mathcal O\mathcal O$ coefficient is not an arbitrary dynamical number once the charge representation and current normalization are fixed.

Similarly, the stress tensor satisfies translation, rotation, and scale Ward identities. The $T\mathcal O\mathcal O$ three-point coefficient is fixed by the scaling dimension and spin representation of $\mathcal O$, once the stress-tensor normalization is fixed. In practice, the stress-tensor two-point coefficient $C_T$ and the normalization of $T_{\mu\nu}$ determine how this coefficient is written.

This is the first hint of a general theme:

$$
\text{ordinary conserved current}
\Longleftrightarrow
\text{protected three-point coupling}.
$$

The current and stress-tensor cases are revisited in [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/), [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/), and [Stress-Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/).

## Two-dimensional form

In two-dimensional CFT, write complex coordinates as

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2.
$$

A primary has weights $(h_i,\bar h_i)$ and dimension and spin

$$
\Delta_i=h_i+\bar h_i,
\qquad
s_i=h_i-\bar h_i.
$$

The three-point function of primary fields takes the holomorphically factorized form

$$
\langle \phi_1(z_1,\bar z_1)\phi_2(z_2,\bar z_2)\phi_3(z_3,\bar z_3)\rangle
=
\frac{C_{123}}
{z_{12}^{h_1+h_2-h_3}z_{13}^{h_1+h_3-h_2}z_{23}^{h_2+h_3-h_1}}
\frac{1}
{\bar z_{12}^{\bar h_1+\bar h_2-\bar h_3}
 \bar z_{13}^{\bar h_1+\bar h_3-\bar h_2}
 \bar z_{23}^{\bar h_2+\bar h_3-\bar h_1}}.
$$

Global conformal invariance fixes this form. Virasoro symmetry does not introduce a new coordinate dependence for primary three-point functions on the plane, but it strongly constrains which operators exist, which fusion rules are allowed, and which constants are compatible with crossing and modular consistency.

## Examples

### Generalized free scalar

Let $\phi$ be a generalized free scalar with

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{x^{2\Delta_\phi}}.
$$

The three-point function $\langle \phi\phi\phi\rangle$ vanishes in a Gaussian theory with $\phi\mapsto-\phi$ symmetry. But the composite scalar $\phi^2$ appears in the $\phi\times\phi$ OPE. Define the normalized operator

$$
\mathcal O_{\phi^2}=\frac{1}{\sqrt{2}}:\!\phi^2\!:.
$$

Then Wick contraction gives

$$
\langle \phi(x_1)\phi(x_2)\mathcal O_{\phi^2}(x_3)\rangle
=
\frac{\sqrt{2}}{x_{13}^{2\Delta_\phi}x_{23}^{2\Delta_\phi}}.
$$

This matches the scalar three-point formula with

$$
\Delta_{\mathcal O_{\phi^2}}=2\Delta_\phi,
\qquad
\lambda_{\phi\phi\mathcal O_{\phi^2}}=\sqrt{2}.
$$

This example is a useful normalization check: the coefficient is not guessed from symmetry; it comes from the chosen normalization of the composite operator.

### Free scalar in more than two dimensions

For a free scalar in $d>2$,

$$
\Delta_\phi=\frac{d-2}{2}.
$$

The equation of motion $\partial^2\phi=0$ makes a descendant null. This affects the conformal multiplet and the OPE, but it does not change the scalar three-point kinematic formula. It changes which operators and coefficients the theory actually has.

### Ising-type notation

A common symbolic part of the Ising CFT data is

$$
\sigma\times\sigma\sim \mathbf 1+\lambda_{\sigma\sigma\varepsilon}\varepsilon+\cdots.
$$

The number $\lambda_{\sigma\sigma\varepsilon}$ is the same dynamical datum that appears in

$$
\langle \sigma(x_1)\sigma(x_2)\varepsilon(x_3)\rangle
=\frac{\lambda_{\sigma\sigma\varepsilon}}
{x_{12}^{2\Delta_\sigma-\Delta_\varepsilon}
 x_{13}^{\Delta_\varepsilon}
 x_{23}^{\Delta_\varepsilon}},
$$

assuming unit-normalized two-point functions. Numerical bootstrap studies often quote such coefficients alongside scaling dimensions.

## Why three-point data are enough locally

Given the spectrum of primary operators and all three-point coefficients, the OPE recursively reduces products of local operators to sums over conformal families. In this sense, local correlators on flat space are generated from the data

$$
\{\Delta_i,\ \ell_i,\ G_{ij},\ \lambda_{ijk}^{(a)}\}.
$$

Four-point functions are not additional independent local input. They are the consistency test. If the OPE is applied in two different orders, the answers must agree. That agreement is crossing symmetry.

The punchline is:

$$
\text{three-point functions define multiplication},
\qquad
\text{four-point functions test associativity}.
$$

This is the conceptual core of the conformal bootstrap.

## Common pitfalls

### Confusing a kinematic structure with a dynamical coefficient

Conformal symmetry fixes the powers of $x_{ij}$. It does not usually fix $\lambda_{ijk}$. A page full of correct powers can still contain no dynamical information until the coefficients are specified.

### Forgetting the two-point metric

If $G_{ij}\ne\delta_{ij}$, then $\lambda_{ijk}$ and $\lambda_{ij}{}^k$ are not the same object. Raising or lowering an operator index uses the two-point metric.

### Assuming all allowed coefficients are nonzero

Symmetry can say a coefficient is allowed. It cannot say it is nonzero. A coefficient may vanish accidentally, because of dynamics, duality, an enhanced symmetry, a free-field equation of motion, or a special point on a conformal manifold.

### Assuming three-point coefficients are positive

In a unitary CFT, the coefficients squared in certain identical-scalar four-point block decompositions are nonnegative. Individual three-point coefficients can be positive, negative, real, complex, or basis-dependent depending on operator conventions. Positivity is a statement about norms and squared OPE coefficients in a specified reflection-positive setup, not a universal sign rule for every $\lambda_{ijk}$.

### Treating spinning correlators as scalar correlators with indices attached

Spinning correlators have independent tensor structures. Conservation, parity, permutation symmetry, and Ward identities can relate or eliminate structures. The scalar formula is the starting point, not the whole story.

## Relations to other pages

- [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/) fixes the normalization conventions needed to interpret $\lambda_{ijk}$.
- [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) explains how products of three-point coefficients enter conformal-block decompositions.
- [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) develops the same constants from the operator product viewpoint.
- [Conformal Blocks](/cft-bootstrap/conformal-blocks/) packages the contribution of a primary and all of its descendants to four-point functions.
- [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) and [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) explain the special Ward-identity constraints on conserved spinning operators.

## Research status

The scalar-primary formula is settled textbook material. The relation between three-point coefficients and OPE coefficients is also part of the standard formulation of CFT.

Active work enters through increasingly sophisticated settings: spinning correlators in general dimension, defects and boundaries, parity-odd structures, supersymmetric shortening, Lorentzian inversion, light-ray operators, numerical bootstrap implementations with many tensor structures, and normalization conventions that allow clean comparisons across analytic, numerical, and holographic calculations.

The practical moral is conservative: every time a page quotes a three-point coefficient, it should also make clear the two-point normalization, operator basis, tensor structure, and symmetry channel.

## Exercises

### Exercise 1: derive the scalar exponents

Assume

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=\frac{C}{x_{12}^{a}x_{13}^{b}x_{23}^{c}}.
$$

Use inversion covariance to derive $a$, $b$, and $c$.

<details><summary><strong>Solution</strong></summary>

Under inversion,

$$
x_{ij}\mapsto \frac{x_{ij}}{|x_i||x_j|}.
$$

Therefore the denominator transforms with factors

$$
|x_1|^{a+b}|x_2|^{a+c}|x_3|^{b+c}.
$$

A scalar primary of dimension $\Delta_i$ contributes the covariance factor $|x_i|^{2\Delta_i}$. Hence

$$
a+b=2\Delta_1,
\qquad
a+c=2\Delta_2,
\qquad
b+c=2\Delta_3.
$$

Solving gives

$$
a=\Delta_1+\Delta_2-\Delta_3,
\qquad
b=\Delta_1+\Delta_3-\Delta_2,
\qquad
c=\Delta_2+\Delta_3-\Delta_1.
$$

</details>

### Exercise 2: selection rules in an Ising-like theory

Suppose a CFT has a $\mathbb Z_2$ symmetry with $\sigma$ odd and $\varepsilon$ even. Which of the following scalar three-point coefficients are symmetry-forbidden?

$$
\lambda_{\sigma\sigma\sigma},
\qquad
\lambda_{\sigma\sigma\varepsilon},
\qquad
\lambda_{\varepsilon\varepsilon\varepsilon},
\qquad
\lambda_{\sigma\varepsilon\varepsilon}.
$$

<details><summary><strong>Solution</strong></summary>

A correlator is allowed only if the product of parities is even. Thus

$$
\sigma\sigma\sigma: (-)(-)(-)=-
$$

is forbidden, while

$$
\sigma\sigma\varepsilon: (-)(-)(+)=+,
\qquad
\varepsilon\varepsilon\varepsilon:(+)(+)(+)=+,
$$

are allowed by $\mathbb Z_2$. Finally,

$$
\sigma\varepsilon\varepsilon:(+)(+)(-)=-
$$

is forbidden. Symmetry allows $\lambda_{\sigma\sigma\varepsilon}$ and $\lambda_{\varepsilon\varepsilon\varepsilon}$; dynamics decides whether the allowed coefficients are nonzero.

</details>

### Exercise 3: normalized composite in generalized free theory

Let $\langle \phi(x)\phi(0)\rangle=x^{-2\Delta}$ and define

$$
\mathcal O=\frac{1}{\sqrt{2}}:\!\phi^2\!:.
$$

Show that $\langle \mathcal O(x)\mathcal O(0)\rangle=x^{-4\Delta}$ and compute $\lambda_{\phi\phi\mathcal O}$.

<details><summary><strong>Solution</strong></summary>

Wick contraction gives

$$
\langle :\!\phi^2\!:(x):\!\phi^2\!:(0)\rangle
=2\langle \phi(x)\phi(0)\rangle^2
=\frac{2}{x^{4\Delta}}.
$$

Therefore $\mathcal O=:\!\phi^2\!:/\sqrt2$ has unit two-point normalization.

Similarly,

$$
\langle \phi(x_1)\phi(x_2):\!\phi^2\!:(x_3)\rangle
=\frac{2}{x_{13}^{2\Delta}x_{23}^{2\Delta}}.
$$

Dividing by $\sqrt2$ gives

$$
\langle \phi(x_1)\phi(x_2)\mathcal O(x_3)\rangle
=\frac{\sqrt2}{x_{13}^{2\Delta}x_{23}^{2\Delta}}.
$$

This is the scalar three-point form with $\Delta_{\mathcal O}=2\Delta$ and

$$
\lambda_{\phi\phi\mathcal O}=\sqrt2.
$$

</details>

### Exercise 4: why there is no three-point cross ratio

Explain why a scalar-primary three-point function cannot contain an arbitrary function analogous to the four-point function $\mathcal G(u,v)$.

<details><summary><strong>Solution</strong></summary>

A conformally invariant function of insertion points must be built from conformal cross ratios. For three distinct points in flat space with $d>1$, conformal transformations can move the triple to a fixed standard configuration. There is no continuous invariant left. Therefore the correlator can only be a fixed covariant prefactor times a constant. Four points are different: after fixing three of them, one point still has two invariant coordinates, conventionally packaged as $z$ and $\bar z$, or equivalently $u$ and $v$.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. See the global conformal constraints, operator formalism, OPE, conformal families, and minimal-model chapters.
- H. Osborn and A. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals Phys.* 231 (1994) 311–362.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D Greater Than or Equal to 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI 2015 lectures, arXiv:1602.07982.
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Correlators,” *JHEP* 11 (2011) 071, arXiv:1107.3554.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Rev. Mod. Phys.* 91 (2019) 015002, arXiv:1805.04405.

## Version history

- 2026-06-27: First polished draft. Defines scalar-primary three-point functions, derives the coordinate dependence, relates $\lambda_{ijk}$ to OPE coefficients, records selection rules, spinning structures, Ward-identity constraints, examples, and exercises.
