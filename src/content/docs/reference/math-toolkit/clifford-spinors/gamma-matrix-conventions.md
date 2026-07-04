---
title: "Gamma Matrix Conventions"
description: "Fixes the gamma-matrix, chirality, trace, Dirac-adjoint, Lorentz-generator, and Euclidean-continuation conventions used for four-dimensional spinor calculations."
sidebar:
  label: "Gamma Matrices"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard spinor and QFT references, including Weinberg, Srednicki, Schwartz, Zee, Coleman, Nakahara, Frankel, and common two-component spinor conventions."
topics:
  - gamma matrices
  - Clifford algebra
  - chirality
  - Dirac adjoint
  - trace identities
  - Lorentz generators
canonicalTopics:
  - gamma-matrix-conventions
  - clifford-algebra-representations
  - chirality
  - dirac-adjoint
  - gamma-trace-identities
  - lorentz-spinor-generators
researchStatus:
  established:
    - "Gamma matrices are representation matrices of the Clifford algebra; the identities on this page are convention-dependent but standard once the metric, epsilon tensor, and gamma-five choice are fixed."
  active:
    - "Careful gamma-matrix conventions remain important in automated amplitude calculations, chiral theories, anomalies, dimensional regularization, Euclidean continuation, and fermions on curved or topologically nontrivial spaces."
---

## Summary

Gamma matrices are matrices that represent the Clifford algebra of spacetime. In the default mostly-minus convention,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

they satisfy

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1.
$$

This single relation fixes most of the algebra used in Dirac equations, spin sums, fermion propagators, chiral projectors, trace manipulations, and Lorentz transformations of spinors. It implies, for example,

$$
(p\!\!\!/)^2=p^2\mathbf 1,
$$

where

$$
p\!\!\!/\equiv \gamma^\mu p_\mu.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram from the mostly-minus metric and orientation to the Clifford relation, slash notation, Dirac operator, Dirac adjoint, chirality, Lorentz generators, trace identities, charge conjugation, and Euclidean continuation.](/figures/math-toolkit/gamma-matrix-convention-map.svg)

<figcaption>

Once the metric convention and orientation are fixed, the gamma-matrix package determines slash notation, the Dirac adjoint, chirality, Lorentz generators, charge conjugation identities, traces, and the safest way to state Euclidean continuation caveats. One sign choice, many consequences.

</figcaption>
</figure>

The most common source of spinor mistakes is not a hard theorem. It is a convention mismatch: mostly-minus versus mostly-plus metric, $\epsilon^{0123}$ versus $\epsilon_{0123}$, $\gamma^5$ sign, or a factor of $i$ in $\sigma^{\mu\nu}$. This page fixes a coherent set of conventions and gives translation warnings where the literature splits.

## Prerequisites

Read [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/) and [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/) first. This page assumes the Clifford relation and the double-cover relation

$$
\operatorname{Spin}^+(1,3)\simeq SL(2,\mathbb C)
$$

for the proper orthochronous Lorentz group. It also uses the default [Mathematical Conventions](/math-toolkit/conventions/), especially $c=\hbar=1$, mostly-minus metric, and $e^{-ip\cdot x}$ plane waves.

The next page, [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/), uses these conventions to compare the common spinor types.

## Core idea

Gamma matrices are not additional physical fields. They are a representation of a metric algebra.

The Clifford relation says that the symmetric part of a gamma-matrix product is the metric:

$$
\gamma^\mu\gamma^\nu
=
\eta^{\mu\nu}\mathbf 1
+
\frac12[\gamma^\mu,\gamma^\nu].
$$

The symmetric part produces scalar contractions such as $p^2$. The antisymmetric part carries spin information and produces Lorentz generators, field-strength couplings, and chirality-sensitive traces.

The matrix basis is not unique. If $M$ is invertible, then

$$
\gamma'^\mu=M\gamma^\mu M^{-1}
$$

satisfies the same Clifford relation. The Dirac basis, chiral basis, and Majorana-friendly bases are different coordinate systems on the same algebraic object. A formula that depends on a special basis should say so. A formula that uses only the Clifford relation is representation-independent.

## Setup and conventions

We work in four-dimensional Lorentzian spacetime unless stated otherwise. The metric is

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

and gamma matrices satisfy

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1.
$$

Thus

$$
(\gamma^0)^2=+\mathbf 1,
\qquad
(\gamma^i)^2=-\mathbf 1.
$$

Lowered gamma matrices are defined by the metric:

$$
\gamma_\mu=\eta_{\mu\nu}\gamma^\nu,
$$

so

$$
\gamma_0=\gamma^0,
\qquad
\gamma_i=-\gamma^i.
$$

For a four-vector $p^\mu=(p^0,\mathbf p)$,

$$
p_\mu=(p^0,-\mathbf p),
$$

and

$$
p\!\!\!/
=\gamma^\mu p_\mu
=\gamma^0p^0-\gamma^i p^i.
$$

This is the notation to use in site pages. Do not use the usual slashed-$p$ macro here; write $p\!\!\!/$ explicitly so the expression renders reliably in KaTeX.

The Hermiticity convention is

$$
(\gamma^\mu)^\dagger=\gamma^0\gamma^\mu\gamma^0.
$$

Equivalently,

$$
(\gamma^0)^\dagger=\gamma^0,
\qquad
(\gamma^i)^\dagger=-\gamma^i.
$$

The Dirac adjoint is

$$
\bar\psi\equiv\psi^\dagger\gamma^0.
$$

With this definition, $\bar\psi\psi$ is a Lorentz scalar and $\bar\psi\gamma^\mu\psi$ is a Lorentz vector.

## The Dirac algebra in practice

The Clifford relation immediately gives

$$
(p\!\!\!/)^2
=p_\mu p_\nu\gamma^\mu\gamma^\nu
=p_\mu p_\nu\eta^{\mu\nu}\mathbf 1
=p^2\mathbf 1.
$$

The commutator part drops out because $p_\mu p_\nu$ is symmetric while $[\gamma^\mu,\gamma^\nu]$ is antisymmetric.

Therefore

$$
(p\!\!\!/-m)(p\!\!\!/+m)
=(p^2-m^2)\mathbf 1.
$$

This is the algebra behind the free Dirac equation

$$
(i\gamma^\mu\partial_\mu-m)\psi=0
$$

and the momentum-space Feynman propagator

$$
S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

The numerator $p\!\!\!/+m$ is not a decoration. It is the inverse of the first-order Dirac operator, up to the scalar Klein–Gordon denominator.

A useful companion identity is

$$
\gamma^\mu\gamma_\mu=4\mathbf 1.
$$

More generally, in $d$ dimensions with the same Clifford logic,

$$
\gamma^\mu\gamma_\mu=d\mathbf 1.
$$

Be careful: identities involving $\gamma^5$ do not continue naively to non-integer $d$. That is one reason chiral theories and dimensional regularization require extra care.

## Chirality and gamma five

We choose

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3.
$$

With the mostly-minus Clifford relation, this gives

$$
(\gamma^5)^2=\mathbf 1,
\qquad
\{\gamma^5,\gamma^\mu\}=0,
\qquad
(\gamma^5)^\dagger=\gamma^5.
$$

The chiral projectors are

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

Thus a left-chiral spinor has $\gamma^5$ eigenvalue $-1$, and a right-chiral spinor has $\gamma^5$ eigenvalue $+1$:

$$
\gamma^5\psi_L=-\psi_L,
\qquad
\gamma^5\psi_R=+\psi_R.
$$

Because $\gamma^5$ anticommutes with every $\gamma^\mu$,

$$
\gamma^\mu P_L=P_R\gamma^\mu,
\qquad
\gamma^\mu P_R=P_L\gamma^\mu.
$$

This is why the Dirac kinetic term pairs left and right chiral projectors in the operator but still preserves chirality for massless fields. The mass term is different: it directly couples left and right chiral components.

The orientation convention used for trace identities is

$$
\epsilon^{0123}=+1.
$$

Since the metric has determinant $-1$, this implies

$$
\epsilon_{0123}=-1.
$$

With these choices,

$$
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=-4i\epsilon^{\mu\nu\rho\sigma}.
$$

If you change the sign of $\gamma^5$ or the orientation convention, this trace changes sign. Tiny choice, giant consequences. This is exactly where anomaly calculations become convention minefields.

## Lorentz generators on Dirac spinors

Define

$$
\Sigma^{\mu\nu}
=\frac{i}{4}[\gamma^\mu,\gamma^\nu].
$$

These matrices generate the spinor representation of the Lorentz algebra. They satisfy the Lorentz commutation relations

$$
[\Sigma^{\mu\nu},\Sigma^{\rho\sigma}]
=i(\eta^{\nu\rho}\Sigma^{\mu\sigma}
-\eta^{\mu\rho}\Sigma^{\nu\sigma}
-\eta^{\nu\sigma}\Sigma^{\mu\rho}
+\eta^{\mu\sigma}\Sigma^{\nu\rho}).
$$

They also act correctly on gamma matrices:

$$
[\Sigma^{\rho\sigma},\gamma^\mu]
=i(\eta^{\mu\sigma}\gamma^\rho-\eta^{\mu\rho}\gamma^\sigma).
$$

For an infinitesimal Lorentz transformation

$$
\Lambda^\mu{}_\nu=\delta^\mu{}_\nu+\omega^\mu{}_\nu,
\qquad
\omega_{\mu\nu}=-\omega_{\nu\mu},
$$

one may choose

$$
S(\Lambda)=\exp\left(-\frac{i}{2}\omega_{\mu\nu}\Sigma^{\mu\nu}\right),
$$

so that

$$
S(\Lambda)^{-1}\gamma^\mu S(\Lambda)
=\Lambda^\mu{}_\nu\gamma^\nu.
$$

This identity is the operational definition worth remembering. If a source uses the opposite active/passive convention, the exponential may appear with the opposite sign while the covariance statement is adjusted accordingly.

Some books define

$$
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

Then

$$
\Sigma^{\mu\nu}=\frac12\sigma^{\mu\nu}.
$$

Both notations are common. Always check whether a formula uses $\Sigma^{\mu\nu}$ or $\sigma^{\mu\nu}$ before importing a factor of two.

## Chiral basis and sigma matrices

The chiral, or Weyl, basis is especially useful for separating left- and right-handed spinors. Define

$$
\sigma^\mu=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^i),
$$

where $\sigma^i$ are the Pauli matrices. Then one can take

$$
\gamma^\mu=
\begin{pmatrix}
0 & \sigma^\mu \\
\bar\sigma^\mu & 0
\end{pmatrix}.
$$

This gives

$$
\gamma^5=
\begin{pmatrix}
-\mathbf 1 & 0 \\
0 & \mathbf 1
\end{pmatrix}.
$$

So in this basis a Dirac spinor decomposes as

$$
\psi=
\begin{pmatrix}
\psi_L \\
\psi_R
\end{pmatrix},
\qquad
P_L\psi=
\begin{pmatrix}
\psi_L \\
0
\end{pmatrix},
\qquad
P_R\psi=
\begin{pmatrix}
0 \\
\psi_R
\end{pmatrix}.
$$

The two-component sigma matrices obey

$$
\sigma^\mu\bar\sigma^\nu+\sigma^\nu\bar\sigma^\mu=2\eta^{\mu\nu}\mathbf 1,
$$

and

$$
\bar\sigma^\mu\sigma^\nu+\bar\sigma^\nu\sigma^\mu=2\eta^{\mu\nu}\mathbf 1.
$$

These are the two-component versions of the Clifford relation.

## Trace identities

For four-component gamma matrices,

$$
\operatorname{tr}\mathbf 1=4,
$$

and traces of an odd number of gamma matrices vanish:

$$
\operatorname{tr}(\gamma^{\mu_1}\cdots\gamma^{\mu_{2k+1}})=0.
$$

The basic two- and four-gamma traces are

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu)=4\eta^{\mu\nu},
$$

and

$$
\operatorname{tr}(\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=4(\eta^{\mu\nu}\eta^{\rho\sigma}
-\eta^{\mu\rho}\eta^{\nu\sigma}
+\eta^{\mu\sigma}\eta^{\nu\rho}).
$$

With $\gamma^5$,

$$
\operatorname{tr}(\gamma^5)=0,
\qquad
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu)=0,
$$

and

$$
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=-4i\epsilon^{\mu\nu\rho\sigma}.
$$

These formulas are usually enough for tree-level spin sums and many one-loop numerator reductions. Longer traces can be reduced by repeatedly anticommuting adjacent gamma matrices and using cyclicity of the trace.

When traces involve $\gamma^5$ inside dimensional regularization, do not blindly use four-dimensional trace identities. The object $\gamma^5$ is intrinsically four-dimensional in this definition. Different schemes preserve different desirable properties, and chiral anomalies are precisely where this bookkeeping matters.

## Dirac bilinears

The standard independent four-dimensional Dirac bilinears are

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

They transform respectively as scalar, pseudoscalar, vector, axial vector, and antisymmetric tensor. Here

$$
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

The factor of $i$ in the pseudoscalar $\bar\psi i\gamma^5\psi$ is conventional but useful: with the Hermiticity choices above, it makes the bilinear Hermitian for ordinary anticommuting quantum fields.

These bilinears form a basis for $4\times4$ complex matrices:

$$
\mathbf 1,
\quad
\gamma^5,
\quad
\gamma^\mu,
\quad
\gamma^\mu\gamma^5,
\quad
\sigma^{\mu\nu}.
$$

Counting gives

$$
1+1+4+4+6=16,
$$

which is the dimension of the full matrix algebra. This basis is the starting point for Fierz identities.

## Charge conjugation

A charge-conjugation matrix $C$ is a matrix satisfying

$$
C^{-1}\gamma^\mu C=-(\gamma^\mu)^T.
$$

Given $C$, the charge conjugate of a Dirac spinor is

$$
\psi^c=C\bar\psi^T.
$$

The precise matrix $C$ depends on the gamma-matrix basis and phase conventions. The defining relation above is the basis-independent content.

A Majorana spinor is a spinor satisfying a reality condition of the form

$$
\psi^c=\psi.
$$

This condition is natural in four-dimensional Lorentzian signature, but it does not transfer unchanged to Euclidean signature. Euclidean fermion path integrals often treat $\psi$ and $\bar\psi$ as independent Grassmann variables even when their Lorentzian interpretation suggests a reality condition.

## Euclidean continuation

One convenient Euclidean gamma-matrix convention is

$$
\gamma_E^k=i\gamma^k,
\qquad k=1,2,3,
$$

and

$$
\gamma_E^4=\gamma^0.
$$

Then

$$
\{\gamma_E^a,\gamma_E^b\}=2\delta^{ab}\mathbf 1,
\qquad a,b=1,2,3,4,
$$

and the Euclidean gamma matrices are Hermitian. With this choice,

$$
\gamma_E^5\equiv\gamma_E^1\gamma_E^2\gamma_E^3\gamma_E^4=\gamma^5.
$$

This is a convention, not a theorem of nature. Some authors put factors of $i$ elsewhere, or define Euclidean time with the opposite sign. When comparing Euclidean formulas, track simultaneously the Wick rotation, gamma matrices, $\gamma^5$, epsilon tensors, and the definition of the Euclidean action.

## Common pitfalls

**Treating gamma matrices as vectors.** The object $\gamma^\mu$ carries a Lorentz index, but it is a fixed set of matrices, not a vector field. Lorentz covariance is expressed by the similarity transformation $S^{-1}\gamma^\mu S=\Lambda^\mu{}_\nu\gamma^\nu$.

**Forgetting that $p\!\!\!/$ uses $p_\mu$.** In mostly-minus convention,

$$
p\!\!\!/ = \gamma^\mu p_\mu = \gamma^0p^0-\gamma^i p^i.
$$

Writing $\gamma^\mu p^\mu$ is not the same expression unless you also lower the gamma matrix or change the summation convention.

**Importing a $\gamma^5$ trace from another convention.** The sign of

$$
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
$$

is tied to the definition of $\gamma^5$ and $\epsilon^{0123}$. Do not memorize it apart from those choices.

**Confusing $\sigma^{\mu\nu}$ with the spinor generator.** If $\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu]$, then the Lorentz generator is $\Sigma^{\mu\nu}=\frac12\sigma^{\mu\nu}$. Some authors call the generator itself $\sigma^{\mu\nu}/2$; some hide the factor in the exponential.

**Using four-dimensional $\gamma^5$ identities in $d$ dimensions.** This is the classic chiral-regularization trap. In anomaly calculations, careless anticommutation of $\gamma^5$ can erase the effect one is trying to compute.

## Relations to other pages

This page is the convention anchor for [Weyl, Dirac, and Majorana Spinors](/math-toolkit/clifford-spinors/weyl-dirac-majorana-spinors/), spinor bilinears, Fierz identities, spinor-helicity methods, and later pages on Dirac fields and fermion propagators.

The algebraic origin is explained in [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/). The group-theoretic origin is explained in [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/) and [SL(2,C) and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/). Pauli-matrix identities used in the chiral basis are collected in [Pauli Matrices](/math-toolkit/clifford-spinors/pauli-matrices/).

## Research status

The gamma-matrix algebra itself is settled. What remains delicate is not the algebra but its deployment in contexts where several structures collide: chiral gauge theories, anomalies, dimensional regularization, curved backgrounds, Majorana or Weyl reality conditions, nonorientable manifolds, lattice fermions, and automated symbolic calculations.

A reliable calculation states its gamma-matrix convention before the first nontrivial sign can matter. That is not pedantry. It is version control for spin.

## Exercises

### Exercise 1: Squaring the Dirac operator

Using only

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1,
$$

show that

$$
(p\!\!\!/-m)(p\!\!\!/+m)=p^2-m^2.
$$

<details><summary><strong>Solution</strong></summary>

Expand:

$$
(p\!\!\!/-m)(p\!\!\!/+m)
=(p\!\!\!/)^2-m^2.
$$

Now

$$
(p\!\!\!/)^2=p_\mu p_\nu\gamma^\mu\gamma^\nu.
$$

Since $p_\mu p_\nu$ is symmetric, only the symmetric part of $\gamma^\mu\gamma^\nu$ contributes:

$$
p_\mu p_\nu\gamma^\mu\gamma^\nu
=\frac12p_\mu p_\nu\{\gamma^\mu,\gamma^\nu\}
=p_\mu p_\nu\eta^{\mu\nu}\mathbf 1
=p^2\mathbf 1.
$$

Therefore

$$
(p\!\!\!/-m)(p\!\!\!/+m)=(p^2-m^2)\mathbf 1.
$$

</details>

### Exercise 2: Chiral projectors flip through gamma matrices

Show that

$$
\gamma^\mu P_L=P_R\gamma^\mu.
$$

<details><summary><strong>Solution</strong></summary>

Using $P_L=(1-\gamma^5)/2$ and $\{\gamma^5,\gamma^\mu\}=0$,

$$
\gamma^\mu P_L
=\frac12\gamma^\mu(1-\gamma^5)
=\frac12(\gamma^\mu-\gamma^\mu\gamma^5).
$$

Anticommutation gives

$$
-\gamma^\mu\gamma^5=\gamma^5\gamma^\mu,
$$

so

$$
\gamma^\mu P_L
=\frac12(1+\gamma^5)\gamma^\mu
=P_R\gamma^\mu.
$$

The proof for $\gamma^\mu P_R=P_L\gamma^\mu$ is identical.

</details>

### Exercise 3: The sign of the gamma-five trace

Assuming $\epsilon^{0123}=+1$ and $\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3$, compute

$$
\operatorname{tr}(\gamma^5\gamma^0\gamma^1\gamma^2\gamma^3).
$$

<details><summary><strong>Solution</strong></summary>

Let

$$
I=\gamma^0\gamma^1\gamma^2\gamma^3.
$$

In mostly-minus signature,

$$
I^2=-\mathbf 1.
$$

Therefore

$$
\gamma^5\gamma^0\gamma^1\gamma^2\gamma^3
=iI^2
=-i\mathbf 1.
$$

Taking the trace in a four-dimensional Dirac representation gives

$$
\operatorname{tr}(\gamma^5\gamma^0\gamma^1\gamma^2\gamma^3)=-4i.
$$

Since $\epsilon^{0123}=+1$, this matches

$$
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=-4i\epsilon^{\mu\nu\rho\sigma}
$$

for $(\mu,\nu,\rho,\sigma)=(0,1,2,3)$.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. See the discussion of Lorentz representations and Dirac fields.
- M. Srednicki, *Quantum Field Theory*. See the chapters on Lorentz representations, spinor fields, spinor indices, and gamma-matrix technology.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the chapters on spinors, Dirac matrices, spinor solutions, and QED trace technology.
- A. Zee, *Quantum Field Theory in a Nutshell*. See the spinor and Dirac-equation discussions.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* and *Aspects of Symmetry*. Useful for symmetry, currents, and spinor-adjacent QFT conventions.
- M. Nakahara, *Geometry, Topology and Physics*, and T. Frankel, *The Geometry of Physics*. Useful for spin geometry, Clifford-algebra background, and Dirac operators.

## Version history

- **2026-06-24:** Initial polished draft. Fixed mostly-minus gamma-matrix conventions, $\gamma^5$, trace identities, Lorentz generators, chiral basis, charge conjugation, and Euclidean continuation.
