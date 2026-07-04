---
title: "Spinor Bilinears"
description: "Explains the scalar, pseudoscalar, vector, axial-vector, and tensor bilinears of four-dimensional Dirac spinors, including transformation laws, chirality, Hermiticity, and common QFT uses."
sidebar:
  label: "Spinor Bilinears"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard spinor and QFT references, including Weinberg, Srednicki, Schwartz, Zee, Coleman, and common two-component spinor conventions."
topics:
  - spinor bilinears
  - Dirac bilinears
  - Lorentz covariance
  - chiral currents
  - Majorana bilinears
  - tensor bilinears
canonicalTopics:
  - spinor-bilinears
  - dirac-bilinears
  - lorentz-covariant-bilinears
  - chiral-currents
  - majorana-bilinears
  - tensor-bilinears
researchStatus:
  established:
    - "The classification of four-dimensional Dirac bilinears into scalar, pseudoscalar, vector, axial-vector, and antisymmetric tensor covariants is standard once gamma-matrix and parity conventions are fixed."
  active:
    - "Bilinears remain a convention-sensitive interface in operator bases, effective field theory, lattice fermions, Majorana systems, anomalies, and automated amplitude calculations."
---

## Summary

Spinor bilinears are Lorentz-covariant expressions made from a spinor, its Dirac adjoint, and a gamma-matrix insertion. For two Dirac spinors $\theta$ and $\rho$, the basic form is

$$
\bar\theta\Gamma\rho,
$$

where $\Gamma$ is a $4\times4$ matrix built from gamma matrices. In four-dimensional Lorentzian QFT, the independent Dirac bilinears are conventionally organized as

$$
\bar\theta\rho,
\qquad
\bar\theta i\gamma^5\rho,
\qquad
\bar\theta\gamma^\mu\rho,
\qquad
\bar\theta\gamma^\mu\gamma^5\rho,
\qquad
\bar\theta\sigma^{\mu\nu}\rho.
$$

They transform as a scalar, pseudoscalar, vector, axial vector, and antisymmetric tensor. Here

$$
\sigma^{\mu\nu}\equiv \frac{i}{2}[\gamma^\mu,\gamma^\nu],
$$

using the mostly-minus convention from [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/).

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram from a Dirac adjoint, gamma insertion, and spinor to the five Lorentz-covariant bilinear families: scalar, pseudoscalar, vector, axial vector, and tensor, with representative QFT uses.](/figures/math-toolkit/spinor-bilinear-covariants.svg)

<figcaption>

A spinor bilinear is a Lorentz-covariant contraction $\bar\theta\Gamma\rho$. In four dimensions the $16$ independent gamma-matrix structures split into $1+1+4+4+6$ components: scalar, pseudoscalar, vector, axial vector, and antisymmetric tensor. This is the small table that secretly powers Dirac masses, currents, dipole operators, four-fermion bases, and spin sums.

</figcaption>
</figure>

The slogan is simple:

$$
\text{gamma-matrix basis}
\quad\Longrightarrow\quad
\text{Lorentz-covariant spinor operators}.
$$

The details are not cosmetic. The difference between $\bar\psi\gamma^\mu\psi$ and $\bar\psi\gamma^\mu\gamma^5\psi$ is the difference between vector and axial currents. The factor of $i$ in $\bar\psi i\gamma^5\psi$ is what makes the pseudoscalar bilinear Hermitian in the default conventions. The tensor $\bar\psi\sigma^{\mu\nu}\psi$ is what appears in magnetic dipole operators. And the completeness of these $16$ matrices is the algebra behind Fierz identities.

## Prerequisites

Read [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) and [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/) first. This page uses

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1,
$$

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2},
$$

and

$$
\bar\psi=\psi^\dagger\gamma^0.
$$

The next page, [Fierz Identities](/math-toolkit/clifford-spinors/fierz-identities/), uses the same bilinear basis to rearrange products of two bilinears.

## Core idea

A Dirac spinor transforms as

$$
\psi(x)\mapsto S(\Lambda)\psi(\Lambda^{-1}x),
$$

where $S(\Lambda)$ is the spinor representation of a Lorentz transformation. The Dirac adjoint transforms oppositely,

$$
\bar\psi(x)\mapsto \bar\psi(\Lambda^{-1}x)S(\Lambda)^{-1}.
$$

Therefore a bilinear transforms according to how the gamma-matrix insertion transforms:

$$
\bar\psi\Gamma\psi
\mapsto
\bar\psi S(\Lambda)^{-1}\Gamma S(\Lambda)\psi.
$$

If $S^{-1}\Gamma S=\Gamma$, the bilinear is a scalar. If $S^{-1}\Gamma^\mu S=\Lambda^\mu{}_{\nu}\Gamma^\nu$, the bilinear is a vector. If the insertion carries two antisymmetric Lorentz indices, it transforms as an antisymmetric tensor.

This is the whole organizing principle. The gamma-matrix insertion is a small representation-theory device placed between $\bar\psi$ and $\psi$.

For example, using

$$
S(\Lambda)^{-1}\gamma^\mu S(\Lambda)
=\Lambda^\mu{}_{\nu}\gamma^\nu,
$$

the current

$$
V^\mu=\bar\psi\gamma^\mu\psi
$$

transforms as

$$
V^\mu\mapsto \Lambda^\mu{}_{\nu}V^\nu.
$$

The spinor indices disappear; the remaining object is a Lorentz vector.

## The sixteen-dimensional gamma basis

The complex vector space of $4\times4$ matrices has dimension $16$. In four dimensions, a convenient basis is

$$
\mathbf 1,
\qquad
\gamma^5,
\qquad
\gamma^\mu,
\qquad
\gamma^\mu\gamma^5,
\qquad
\sigma^{\mu\nu}.
$$

The counting is

$$
1+1+4+4+6=16,
$$

because $\sigma^{\mu\nu}$ is antisymmetric in $\mu,\nu$.

This basis is adapted to the Lorentz group. It is not just a random matrix basis. Each block transforms irreducibly, or nearly irreducibly, under Lorentz transformations:

| Insertion | Bilinear | Lorentz type | Components |
|---|---|---|---:|
| $\mathbf 1$ | $\bar\theta\rho$ | scalar | 1 |
| $i\gamma^5$ | $\bar\theta i\gamma^5\rho$ | pseudoscalar | 1 |
| $\gamma^\mu$ | $\bar\theta\gamma^\mu\rho$ | vector | 4 |
| $\gamma^\mu\gamma^5$ | $\bar\theta\gamma^\mu\gamma^5\rho$ | axial vector | 4 |
| $\sigma^{\mu\nu}$ | $\bar\theta\sigma^{\mu\nu}\rho$ | antisymmetric tensor | 6 |

The word “pseudoscalar” means that the object is Lorentz invariant under proper orthochronous Lorentz transformations but changes sign under parity. Similarly, an axial vector transforms like a vector under proper Lorentz transformations but has the opposite parity behavior from an ordinary vector.

There is a compact way to remember the classification:

$$
\bar\theta\rho
\quad\text{has no Lorentz index},
$$

$$
\bar\theta\gamma^\mu\rho
\quad\text{has one Lorentz index},
$$

$$
\bar\theta\sigma^{\mu\nu}\rho
\quad\text{has two antisymmetric Lorentz indices},
$$

and $\gamma^5$ makes the corresponding object parity-odd or dualized.

## Hermiticity and the factor of i

For an operator bilinear $\bar\psi\Gamma\psi$, the relevant adjoint operation is not simply $\Gamma^\dagger$. It is

$$
\bar\Gamma\equiv\gamma^0\Gamma^\dagger\gamma^0.
$$

If

$$
\bar\Gamma=\Gamma,
$$

then $\bar\psi\Gamma\psi$ is Hermitian for a single Dirac field, up to the usual care with products of fermion operators at the same point.

Using the default gamma-matrix conventions,

$$
\gamma^0(\gamma^5)^\dagger\gamma^0
=\gamma^0\gamma^5\gamma^0
=-\gamma^5.
$$

Therefore $\bar\psi\gamma^5\psi$ is anti-Hermitian, while

$$
\bar\psi i\gamma^5\psi
$$

is Hermitian. This is why the pseudoscalar bilinear is usually written with an explicit $i$.

By contrast,

$$
\gamma^0(\gamma^\mu)^\dagger\gamma^0=\gamma^\mu,
$$

so the vector current

$$
\bar\psi\gamma^\mu\psi
$$

is Hermitian. One also finds

$$
\gamma^0(\gamma^\mu\gamma^5)^\dagger\gamma^0=\gamma^\mu\gamma^5,
$$

and

$$
\gamma^0(\sigma^{\mu\nu})^\dagger\gamma^0=\sigma^{\mu\nu}.
$$

So the standard Hermitian set is

$$
\bar\psi\psi,
\qquad
\bar\psi i\gamma^5\psi,
\qquad
\bar\psi\gamma^\mu\psi,
\qquad
\bar\psi\gamma^\mu\gamma^5\psi,
\qquad
\bar\psi\sigma^{\mu\nu}\psi.
$$

Tiny convention note, because this is where gremlins breed: the algebraic Fierz basis often uses $\gamma^5$ rather than $i\gamma^5$ because trace orthogonality is slightly cleaner. The physical Hermitian pseudoscalar operator uses $i\gamma^5$ in these conventions.

## Scalar and pseudoscalar bilinears

The scalar bilinear is

$$
S\equiv\bar\psi\psi.
$$

For a free Dirac fermion, the mass term is

$$
\mathcal L_m=-m\bar\psi\psi.
$$

The scalar bilinear couples left and right chirality. Since

$$
P_L\gamma^0=\gamma^0P_R,
$$

one has

$$
\bar\psi\psi
=\bar\psi_L\psi_R+\bar\psi_R\psi_L,
$$

where $\psi_{L,R}=P_{L,R}\psi$ and $\bar\psi_{L,R}=\bar\psi P_{R,L}$. The bar flips the projector. This little fact is a frequent source of wrong chiral signs.

The pseudoscalar bilinear is

$$
P\equiv\bar\psi i\gamma^5\psi.
$$

It is parity-odd. A fermion mass term of the form

$$
-m\bar\psi\psi-im_5\bar\psi\gamma^5\psi
$$

can be viewed as a complex chiral mass. In simple single-fermion models, a chiral rotation can move the phase between scalar and pseudoscalar mass terms. In gauge theories with anomalies, this movement can shift a topological theta term. So the humble pseudoscalar bilinear is already standing next to anomaly physics, trying to look innocent.

In chiral components,

$$
\bar\psi i\gamma^5\psi
=i\left(-\bar\psi_L\psi_R+\bar\psi_R\psi_L\right).
$$

Together, $\bar\psi\psi$ and $\bar\psi i\gamma^5\psi$ measure the real and imaginary parts of a chirality-flipping fermion bilinear.

## Vector and axial-vector bilinears

The vector current is

$$
V^\mu\equiv\bar\psi\gamma^\mu\psi.
$$

For a Dirac fermion with a global phase symmetry

$$
\psi\mapsto e^{i\alpha}\psi,
$$

the Noether current is precisely

$$
j^\mu=\bar\psi\gamma^\mu\psi.
$$

Classically, for the free Dirac equation,

$$
(i\gamma^\mu\partial_\mu-m)\psi=0,
$$

one obtains

$$
\partial_\mu(\bar\psi\gamma^\mu\psi)=0.
$$

The axial current is

$$
A^\mu\equiv\bar\psi\gamma^\mu\gamma^5\psi.
$$

It measures the difference between right- and left-chiral currents. In chiral components,

$$
V^\mu
=\bar\psi_L\gamma^\mu\psi_L+\bar\psi_R\gamma^\mu\psi_R,
$$

while

$$
A^\mu
=-\bar\psi_L\gamma^\mu\psi_L+\bar\psi_R\gamma^\mu\psi_R.
$$

Equivalently,

$$
\bar\psi\gamma^\mu P_L\psi
=\frac12(V^\mu-A^\mu),
\qquad
\bar\psi\gamma^\mu P_R\psi
=\frac12(V^\mu+A^\mu).
$$

For a massive free Dirac fermion, the classical axial-current divergence is

$$
\partial_\mu A^\mu
=2im\bar\psi\gamma^5\psi
=2m\bar\psi i\gamma^5\psi.
$$

Thus the axial current is classically conserved when $m=0$. In a gauge theory, a quantum anomaly may add another term. The axial current is the first place many students see that a classical symmetry of a Lagrangian need not survive the quantum definition of the theory.

## Tensor bilinears

The tensor bilinear is

$$
T^{\mu\nu}\equiv\bar\psi\sigma^{\mu\nu}\psi,
\qquad
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

It is antisymmetric:

$$
T^{\mu\nu}=-T^{\nu\mu}.
$$

This gives $6$ independent components, like an electromagnetic field strength. That is not a coincidence: tensor bilinears naturally couple to antisymmetric two-tensors.

The most common physical examples are magnetic and electric dipole operators. In an effective Lagrangian one encounters terms such as

$$
\bar\psi\sigma^{\mu\nu}\psi F_{\mu\nu},
$$

and

$$
\bar\psi\sigma^{\mu\nu}\gamma^5\psi F_{\mu\nu}.
$$

The first is a magnetic-dipole-type coupling; the second is electric-dipole-type and is sensitive to discrete symmetries.

The dual tensor relation in the conventions of this page is

$$
\sigma^{\mu\nu}\gamma^5
=\frac{i}{2}\epsilon^{\mu\nu\rho\sigma}\sigma_{\rho\sigma},
\qquad
\epsilon^{0123}=+1.
$$

This identity is useful whenever tensor bilinears are split into self-dual and anti-self-dual parts, or when one rewrites electric and magnetic dipole operators.

Chirality also matters. Since

$$
[\sigma^{\mu\nu},\gamma^5]=0,
$$

the tensor preserves chirality as a matrix:

$$
\sigma^{\mu\nu}P_L=P_L\sigma^{\mu\nu},
\qquad
\sigma^{\mu\nu}P_R=P_R\sigma^{\mu\nu}.
$$

But because the Dirac adjoint flips chiral projectors, tensor bilinears such as $\bar\psi\sigma^{\mu\nu}\psi$ connect opposite barred and unbarred chiral labels in the same way mass terms do. In effective operator bases, this is one reason dipole operators often carry chirality flips and are proportional to a mass or a Yukawa insertion when a chiral symmetry is present.

## Parity and charge conjugation

Under parity, take

$$
\psi(t,\mathbf x)\mapsto \gamma^0\psi(t,-\mathbf x).
$$

Then the bilinears behave as follows:

| Bilinear | Parity behavior | Common interpretation |
|---|---|---|
| $\bar\psi\psi$ | even | scalar mass or scalar density |
| $\bar\psi i\gamma^5\psi$ | odd | pseudoscalar density |
| $V^0=\bar\psi\gamma^0\psi$ | even | charge density |
| $V^i=\bar\psi\gamma^i\psi$ | odd | spatial current |
| $A^0=\bar\psi\gamma^0\gamma^5\psi$ | odd | axial charge density |
| $A^i=\bar\psi\gamma^i\gamma^5\psi$ | even | spin-like axial current |
| $T^{0i}=\bar\psi\sigma^{0i}\psi$ | odd | electric-type tensor component |
| $T^{ij}=\bar\psi\sigma^{ij}\psi$ | even | magnetic-type tensor component |

Under charge conjugation for a single neutral Dirac bilinear, the standard signs are

| Bilinear | Charge-conjugation sign |
|---|---:|
| $\bar\psi\psi$ | $+$ |
| $\bar\psi i\gamma^5\psi$ | $+$ |
| $\bar\psi\gamma^\mu\psi$ | $-$ |
| $\bar\psi\gamma^\mu\gamma^5\psi$ | $+$ |
| $\bar\psi\sigma^{\mu\nu}\psi$ | $-$ |

This table explains, for instance, why a Majorana fermion cannot carry an ordinary conserved $U(1)$ vector charge. A Majorana field is its own charge conjugate, so a $C$-odd diagonal vector current vanishes identically for one Majorana species.

Do not overuse the table without context. In gauge theories, flavor indices, complex representations, and operator ordering can change the practical statement. The table is the spinor part of the story, not the whole model.

## Majorana bilinears

A Majorana spinor satisfies

$$
\psi^c=\psi,
$$

where

$$
\psi^c=C\bar\psi^T.
$$

For a single Majorana field in four-dimensional Lorentzian signature, the vector and tensor bilinears vanish:

$$
\bar\psi\gamma^\mu\psi=0,
\qquad
\bar\psi\sigma^{\mu\nu}\psi=0.
$$

The scalar, pseudoscalar, and axial-vector bilinears can be nonzero:

$$
\bar\psi\psi,
\qquad
\bar\psi i\gamma^5\psi,
\qquad
\bar\psi\gamma^\mu\gamma^5\psi.
$$

This is why Majorana fermions have no ordinary number current but can have axial couplings. It is also why Majorana mass terms are possible even though Majorana fermions do not carry a conserved particle-number symmetry.

For two different Majorana fields $\psi_a$ and $\psi_b$, the mixed bilinears obey symmetry or antisymmetry relations under $a\leftrightarrow b$. In operator bases, those signs matter. The safe practice is to keep the field labels until the end and only then specialize to identical Majorana fields.

## Weyl notation and chiral currents

In the chiral basis, write a Dirac spinor as

$$
\Psi=
\begin{pmatrix}
\psi_L\\
\psi_R
\end{pmatrix}.
$$

Using

$$
\gamma^\mu=
\begin{pmatrix}
0&\sigma^\mu\\
\bar\sigma^\mu&0
\end{pmatrix},
\qquad
\gamma^5=
\begin{pmatrix}
-\mathbf 1&0\\
0&\mathbf 1
\end{pmatrix},
$$

with

$$
\sigma^\mu=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^i),
$$

one finds

$$
\bar\Psi\gamma^\mu\Psi
=\psi_R^\dagger\sigma^\mu\psi_R
+\psi_L^\dagger\bar\sigma^\mu\psi_L,
$$

and

$$
\bar\Psi\gamma^\mu\gamma^5\Psi
=\psi_R^\dagger\sigma^\mu\psi_R
-\psi_L^\dagger\bar\sigma^\mu\psi_L.
$$

Thus vector and axial currents are just the sum and difference of right- and left-chiral currents.

The scalar bilinear mixes chiralities:

$$
\bar\Psi\Psi
=\psi_R^\dagger\psi_L+\psi_L^\dagger\psi_R,
$$

and the pseudoscalar bilinear is

$$
\bar\Psi i\gamma^5\Psi
=i\left(-\psi_R^\dagger\psi_L+\psi_L^\dagger\psi_R\right).
$$

This chiral decomposition is often the cleanest way to read Standard Model operators. Gauge interactions preserve chirality before electroweak symmetry breaking. Mass terms and dipole operators flip chirality. Four-fermion currents may be left-left, right-right, or left-right. The gamma-matrix notation hides this structure; the Weyl notation exposes it.

## Completeness and why Fierz identities are coming

Every $4\times4$ matrix $M$ can be expanded in the gamma basis. A common expansion is

$$
M
=\frac14\operatorname{tr}(M)\mathbf 1
+\frac14\operatorname{tr}(\gamma^5M)\gamma^5
+\frac14\operatorname{tr}(\gamma_\mu M)\gamma^\mu
-\frac14\operatorname{tr}(\gamma_\mu\gamma^5M)\gamma^\mu\gamma^5
+\frac18\operatorname{tr}(\sigma_{\mu\nu}M)\sigma^{\mu\nu}.
$$

The minus sign in the axial term and the factor of $1/8$ in the tensor term are not typos. They come from the trace inner products of the gamma basis.

This expansion is the matrix version of saying that the five bilinear families form a complete list. Once you insert this completeness relation into a product such as

$$
(\bar\psi_1\psi_2)(\bar\psi_3\psi_4),
$$

you get Fierz identities, which rewrite the pairing $(12)(34)$ into $(14)(32)$. That is the topic of the next page.

## Common pitfalls

**Forgetting that the Dirac adjoint flips chirality.** Since $\bar\psi_L=\bar\psi P_R$ and $\bar\psi_R=\bar\psi P_L$, a scalar mass term couples left and right chirality even though it looks like $\bar\psi\psi$.

**Dropping the factor of i in the pseudoscalar.** With the conventions here, $\bar\psi\gamma^5\psi$ is anti-Hermitian, while $\bar\psi i\gamma^5\psi$ is Hermitian.

**Treating an axial vector as an ordinary vector under parity.** $\bar\psi\gamma^\mu\gamma^5\psi$ has one Lorentz index, but its parity behavior is opposite to $\bar\psi\gamma^\mu\psi$.

**Assuming a Majorana fermion has a vector number current.** A single Majorana field has no conserved $U(1)$ particle-number current; the diagonal vector bilinear vanishes.

**Importing tensor-duality signs from another convention.** The identity

$$
\sigma^{\mu\nu}\gamma^5
=\frac{i}{2}\epsilon^{\mu\nu\rho\sigma}\sigma_{\rho\sigma}
$$

uses $\epsilon^{0123}=+1$, mostly-minus metric, and $\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3$.

## Exercises

### Exercise 1: Vector transformation law

Assume

$$
S^{-1}\gamma^\mu S=\Lambda^\mu{}_{\nu}\gamma^\nu,
$$

and

$$
\psi\mapsto S\psi,
\qquad
\bar\psi\mapsto\bar\psi S^{-1}.
$$

Show that $V^\mu=\bar\psi\gamma^\mu\psi$ transforms as a Lorentz vector.

<details><summary><strong>Solution</strong></summary>

Under the transformation,

$$
V^\mu\mapsto
\bar\psi S^{-1}\gamma^\mu S\psi.
$$

Using the defining gamma-matrix transformation law,

$$
\bar\psi S^{-1}\gamma^\mu S\psi
=\Lambda^\mu{}_{\nu}\bar\psi\gamma^\nu\psi
=\Lambda^\mu{}_{\nu}V^\nu.
$$

That is exactly the vector transformation law.

</details>

### Exercise 2: Hermiticity of the pseudoscalar

Using

$$
\gamma^0(\gamma^5)^\dagger\gamma^0=-\gamma^5,
$$

show that $\bar\psi i\gamma^5\psi$ is Hermitian.

<details><summary><strong>Solution</strong></summary>

For a bilinear $\bar\psi\Gamma\psi$, the gamma-matrix part of Hermitian conjugation is controlled by

$$
\bar\Gamma=\gamma^0\Gamma^\dagger\gamma^0.
$$

Take $\Gamma=i\gamma^5$. Since $(i\gamma^5)^\dagger=-i\gamma^5$,

$$
\gamma^0(i\gamma^5)^\dagger\gamma^0
=-i\gamma^0\gamma^5\gamma^0
=-i(-\gamma^5)
=i\gamma^5.
$$

Thus $\bar\Gamma=\Gamma$, so $\bar\psi i\gamma^5\psi$ is Hermitian.

</details>

### Exercise 3: Axial divergence for a free massive Dirac field

Using the equations of motion

$$
(i\gamma^\mu\partial_\mu-m)\psi=0,
\qquad
(\partial_\mu\bar\psi)i\gamma^\mu+m\bar\psi=0,
$$

show that

$$
\partial_\mu(\bar\psi\gamma^\mu\gamma^5\psi)
=2m\bar\psi i\gamma^5\psi.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu(\bar\psi\gamma^\mu\gamma^5\psi)
=(\partial_\mu\bar\psi)\gamma^\mu\gamma^5\psi
+\bar\psi\gamma^\mu\gamma^5\partial_\mu\psi.
$$

From the adjoint equation,

$$
(\partial_\mu\bar\psi)i\gamma^\mu=-m\bar\psi,
$$

so

$$
(\partial_\mu\bar\psi)\gamma^\mu=im\bar\psi.
$$

Therefore the first term is

$$
(\partial_\mu\bar\psi)\gamma^\mu\gamma^5\psi
=im\bar\psi\gamma^5\psi.
$$

For the second term, use $\gamma^\mu\gamma^5=-\gamma^5\gamma^\mu$:

$$
\bar\psi\gamma^\mu\gamma^5\partial_\mu\psi
=-\bar\psi\gamma^5\gamma^\mu\partial_\mu\psi.
$$

The Dirac equation gives

$$
i\gamma^\mu\partial_\mu\psi=m\psi,
\qquad
\gamma^\mu\partial_\mu\psi=-im\psi.
$$

Hence

$$
-\bar\psi\gamma^5\gamma^\mu\partial_\mu\psi
=im\bar\psi\gamma^5\psi.
$$

Adding both terms gives

$$
\partial_\mu(\bar\psi\gamma^\mu\gamma^5\psi)
=2im\bar\psi\gamma^5\psi
=2m\bar\psi i\gamma^5\psi.
$$

</details>

### Exercise 4: Count the tensor components

Why does $\bar\psi\sigma^{\mu\nu}\psi$ contain six independent Lorentz components in four dimensions?

<details><summary><strong>Solution</strong></summary>

The tensor $\sigma^{\mu\nu}$ is antisymmetric:

$$
\sigma^{\mu\nu}=-\sigma^{\nu\mu}.
$$

An antisymmetric two-index object in $4$ dimensions has

$$
\binom{4}{2}=6
$$

independent components. These may be grouped as three $0i$ components and three spatial $ij$ components, analogous to the electric-type and magnetic-type components of an antisymmetric field strength.

</details>

### Exercise 5: Chiral currents from vector and axial currents

Show that

$$
\bar\psi\gamma^\mu P_L\psi
=\frac12(V^\mu-A^\mu),
\qquad
\bar\psi\gamma^\mu P_R\psi
=\frac12(V^\mu+A^\mu).
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

Then

$$
\bar\psi\gamma^\mu P_L\psi
=\frac12\bar\psi\gamma^\mu(1-\gamma^5)\psi
=\frac12\left(\bar\psi\gamma^\mu\psi-\bar\psi\gamma^\mu\gamma^5\psi\right)
=\frac12(V^\mu-A^\mu).
$$

The right-chiral identity follows similarly:

$$
\bar\psi\gamma^\mu P_R\psi
=\frac12\bar\psi\gamma^\mu(1+\gamma^5)\psi
=\frac12(V^\mu+A^\mu).
$$

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. See the discussion of Lorentz representations, discrete symmetries, and spinor fields.
- M. Srednicki, *Quantum Field Theory*. See the chapters on left- and right-handed spinor fields, manipulating spinor indices, spinor technology, and gamma-matrix technology.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the chapters on spinors, Dirac matrices, spinor solutions, and QED trace technology.
- A. Zee, *Quantum Field Theory in a Nutshell*. See the spinor, Dirac-equation, and current-algebra discussions.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* and *Aspects of Symmetry*. Useful for currents, symmetry transformations, and bilinear operators in physical arguments.
- H. K. Dreiner, H. E. Haber, and S. P. Martin, “Two-component spinor techniques and Feynman rules for quantum field theory and supersymmetry.” Useful for two-component spinor conventions and chiral bilinears.

## Version history

- **2026-06-24:** Initial polished draft. Classified the five four-dimensional Dirac bilinear families, fixed Hermiticity conventions, parity and charge-conjugation signs, Majorana bilinear caveats, chiral decompositions, and introductory exercises.
