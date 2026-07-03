---
title: "Field Strength from the Commutator"
description: "Derives the non-Abelian field strength from the commutator of covariant derivatives using the volume convention D_mu = partial_mu + i g A_mu."
sidebar:
  label: "Field Strength from the Commutator"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–71; Schwartz Ch. 25; Weinberg Vol. II Yang–Mills material; Nakahara and Frankel on connections and curvature."
topics:
  - covariant derivative
  - field strength
  - Yang-Mills curvature
  - gauge covariance
  - Bianchi identity
  - sign conventions
canonicalTopics:
  - field-strength-from-commutator
  - non-abelian-field-strength
  - curvature-of-connection
  - bianchi-identity
researchStatus:
  established:
    - "The field strength is the curvature of the gauge connection and is equivalently defined by the commutator of covariant derivatives."
  active:
    - "Global bundle data, line operators, and nontrivial topology add structure beyond this local calculation; those topics are handled in the geometry and global-form pages."
---

## Summary

This page derives the standard local formula for the non-Abelian field strength from the commutator of two covariant derivatives. With the volume convention

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

we define $F_{\mu\nu}$ by

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

The result is

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
$$

or, in components,

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-g f^{abc}A_\mu^bA_\nu^c.
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![Field strength from the commutator of covariant derivatives](/figures/gauge-theories-standard-model/field-strength-commutator-flow.svg)

<figcaption>

The field strength is the part of $[D_\mu,D_\nu]$ that remains after factoring out $ig$. The non-Abelian term comes from the matrix commutator of the gauge potentials.

</figcaption>
</figure>

The calculation is short, but it is the seed of a lot of gauge theory: Yang–Mills dynamics, Wilson-loop holonomy, the Bianchi identity, gauge-boson self-interactions, and the geometric interpretation of $A_\mu$ as a connection.

## Setup

Let $\psi(x)$ be a matter field in a representation $R$ of a compact Lie algebra. The representation matrices $T_R^a$ are taken Hermitian and obey

$$
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

To keep notation light, we suppress the subscript $R$ and write

$$
A_\mu=A_\mu^aT^a.
$$

The covariant derivative acting on $\psi$ is

$$
D_\mu\psi=(\partial_\mu+igA_\mu)\psi.
$$

The ordinary derivative knows how the field changes from point to point. The gauge potential supplies the correction needed to compare internal vectors at nearby spacetime points. If $A_\mu$ is a connection, then $F_{\mu\nu}$ is its curvature: it measures the failure of two infinitesimal parallel transports to commute.

## Derivation

Act on a test field $\psi$. This avoids the slightly slippery habit of manipulating differential operators without specifying what their derivatives act on.

Start with

$$
[D_\mu,D_\nu]\psi
=
(\partial_\mu+igA_\mu)(\partial_\nu+igA_\nu)\psi
-(\mu\leftrightarrow\nu).
$$

Expand the first term:

$$
(\partial_\mu+igA_\mu)(\partial_\nu+igA_\nu)\psi
=
\partial_\mu\partial_\nu\psi
+ig(\partial_\mu A_\nu)\psi
+igA_\nu\partial_\mu\psi
+igA_\mu\partial_\nu\psi
-g^2A_\mu A_\nu\psi.
$$

The expression with $\mu$ and $\nu$ exchanged is

$$
(\partial_\nu+igA_\nu)(\partial_\mu+igA_\mu)\psi
=
\partial_\nu\partial_\mu\psi
+ig(\partial_\nu A_\mu)\psi
+igA_\mu\partial_\nu\psi
+igA_\nu\partial_\mu\psi
-g^2A_\nu A_\mu\psi.
$$

Subtract. The second-derivative terms cancel because ordinary partial derivatives commute. The terms with one derivative acting on $\psi$ also cancel. What remains is

$$
[D_\mu,D_\nu]\psi
=
\left[ig(\partial_\mu A_\nu-\partial_\nu A_\mu)-g^2(A_\mu A_\nu-A_\nu A_\mu)\right]\psi.
$$

Using $[A_\mu,A_\nu]=A_\mu A_\nu-A_\nu A_\mu$, this becomes

$$
[D_\mu,D_\nu]\psi
=
ig\left(\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu]\right)\psi.
$$

Therefore

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

That is the matrix-valued field strength.

## Components

Now insert $A_\mu=A_\mu^aT^a$. The derivative terms are immediate:

$$
\partial_\mu A_\nu-\partial_\nu A_\mu
=
(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)T^a.
$$

The commutator term is

$$
[A_\mu,A_\nu]
=
A_\mu^bA_\nu^c[T^b,T^c]
=
i f^{bca}A_\mu^bA_\nu^cT^a.
$$

For totally antisymmetric structure constants, $f^{bca}=f^{abc}$. Hence

$$
ig[A_\mu,A_\nu]
=
-g f^{abc}A_\mu^bA_\nu^cT^a.
$$

Thus

$$
F_{\mu\nu}=F_{\mu\nu}^aT^a,
$$

with

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-g f^{abc}A_\mu^bA_\nu^c.
$$

The minus sign in the last term is not a typo. It follows from using $D_\mu=\partial_\mu+igA_\mu$ together with Hermitian generators. If instead you use $D_\mu=\partial_\mu-igA_\mu$, the non-Abelian term changes sign.

## Abelian check

For $U(1)$, the generator is just a number in any irreducible representation, so

$$
[A_\mu,A_\nu]=0.
$$

The formula reduces to

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

This is the Maxwell field strength. The Abelian check is the quickest way to confirm the normalization of the derivative terms, but it cannot check the sign of the non-Abelian commutator term because that term vanishes.

## Gauge-covariance check

Let a local gauge transformation act on matter by

$$
\psi'(x)=U(x)\psi(x).
$$

Covariance of the derivative means

$$
D_\mu'\psi'=U D_\mu\psi,
$$

or as an operator statement,

$$
D_\mu'=U D_\mu U^{-1}.
$$

Taking a commutator gives

$$
[D_\mu',D_\nu']
=
U[D_\mu,D_\nu]U^{-1}.
$$

Using $[D_\mu,D_\nu]=igF_{\mu\nu}$ on both sides, we get

$$
F_{\mu\nu}'=UF_{\mu\nu}U^{-1}.
$$

This is exactly what we want. The field strength is not gauge-invariant as a matrix in a non-Abelian theory; it is gauge-covariant. Gauge-invariant local expressions are traces such as

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

or, in components with the usual normalization of generators, $F_{\mu\nu}^aF^{a\mu\nu}$.

## Differential-form version

Write the connection one-form as

$$
A=A_\mu dx^\mu,
$$

and define

$$
D=d+igA.
$$

Then the same calculation is summarized by

$$
D^2=igF,
\qquad
F=dA+igA\wedge A.
$$

The wedge product includes matrix multiplication. In components,

$$
F=
\frac12F_{\mu\nu}dx^\mu\wedge dx^\nu.
$$

This notation is compact because it knows about antisymmetry automatically. It is also the cleanest bridge to the geometric statement: field strength is curvature.

## Bianchi identity from the Jacobi identity

The commutator definition makes the Bianchi identity almost free. The Jacobi identity for operators says

$$
[D_\mu,[D_\nu,D_\rho]]
+[D_\nu,[D_\rho,D_\mu]]
+[D_\rho,[D_\mu,D_\nu]]=0.
$$

Using $[D_\mu,D_\nu]=igF_{\mu\nu}$ gives

$$
[D_\mu,F_{\nu\rho}]
+[D_\nu,F_{\rho\mu}]
+[D_\rho,F_{\mu\nu}]=0.
$$

When $F_{\nu\rho}$ acts by multiplication in the same representation, this is

$$
\mathcal D_\mu F_{\nu\rho}
+\mathcal D_\nu F_{\rho\mu}
+\mathcal D_\rho F_{\mu\nu}=0,
$$

where the adjoint covariant derivative is

$$
\mathcal D_\mu X=\partial_\mu X+ig[A_\mu,X].
$$

Equivalently,

$$
\mathcal D_{[\mu}F_{\nu\rho]}=0.
$$

In differential-form notation this is

$$
DF=0.
$$

In the Abelian limit it reduces to the familiar identity $\partial_{[\mu}F_{\nu\rho]}=0$, which contains the homogeneous Maxwell equations.

## Why this calculation matters

The field strength is the local object that can appear in the Yang–Mills action:

$$
\mathcal L_{\mathrm{YM}}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=-\frac14 F_{\mu\nu}^aF^{a\mu\nu}
$$

when $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$.

The commutator term is the origin of gauge-boson self-interactions. In an Abelian theory, $F_{\mu\nu}$ is linear in $A_\mu$, so the pure gauge kinetic term is quadratic. In a non-Abelian theory, $F_{\mu\nu}$ contains $A_\mu A_\nu$, so $F^2$ contains cubic and quartic powers of the gauge field. Gluons interact with gluons because color is non-Abelian.

The same field strength controls Wilson-loop holonomy, topological densities such as $F\widetilde F$, anomaly formulas, background-field gauge, and the curvature language used in geometric treatments of gauge theory.

## Common mistakes

**Forgetting what the derivative acts on.** The cancellation of the $A_\mu\partial_\nu\psi$ terms is visible only if you act on a test field. Operator shorthand is fine after the calculation, not before.

**Losing the sign in the commutator term.** With $D_\mu=\partial_\mu+igA_\mu$ and $[T^a,T^b]=if^{abc}T^c$, the component formula contains $-g f^{abc}A_\mu^bA_\nu^c$.

**Calling $F_{\mu\nu}^a$ gauge-invariant.** The components mix under a gauge transformation. Gauge-invariant local quantities are traces or complete contractions built from covariant objects.

**Confusing the representation of matter with the adjoint representation of $F$.** The commutator is computed using whatever matrices act on $\psi$, but $F_{\mu\nu}=F_{\mu\nu}^aT_R^a$ always transforms by conjugation in that representation. The coefficients $F_{\mu\nu}^a$ are adjoint-valued.

**Using a different convention silently.** If a source uses anti-Hermitian generators or $D=\partial-igA$, translate before comparing signs.

## Exercises

### Abelian limit

Set $G=U(1)$ and let a field have charge $q$. Write $D_\mu=\partial_\mu+iqA_\mu$. Show that

$$
[D_\mu,D_\nu]=iq(\partial_\mu A_\nu-\partial_\nu A_\mu).
$$

<details><summary><strong>Solution</strong></summary>

Because $A_\mu$ is an ordinary function in the Abelian case, $[A_\mu,A_\nu]=0$. Acting on a test field $\psi$ gives

$$
[D_\mu,D_\nu]\psi
=iq(\partial_\mu A_\nu-\partial_\nu A_\mu)\psi.
$$

Thus

$$
[D_\mu,D_\nu]=iqF_{\mu\nu},
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

</details>

### Sign translation

Suppose another author uses

$$
\widehat D_\mu=\partial_\mu-ig\widehat A_\mu,
\qquad
[\widehat D_\mu,\widehat D_\nu]=-ig\widehat F_{\mu\nu}.
$$

Assuming the same Hermitian generators, derive the component formula for $\widehat F_{\mu\nu}^a$.

<details><summary><strong>Solution</strong></summary>

Repeat the calculation with $-ig\widehat A_\mu$. One finds

$$
[\widehat D_\mu,\widehat D_\nu]
=-ig\left(\partial_\mu\widehat A_\nu-\partial_\nu\widehat A_\mu-ig[\widehat A_\mu,\widehat A_\nu]\right).
$$

Therefore

$$
\widehat F_{\mu\nu}
=
\partial_\mu\widehat A_\nu-\partial_\nu\widehat A_\mu-ig[\widehat A_\mu,\widehat A_\nu].
$$

Using $[T^b,T^c]=if^{bca}T^a$ gives

$$
\widehat F_{\mu\nu}^a
=
\partial_\mu\widehat A_\nu^a-\partial_\nu\widehat A_\mu^a
+g f^{abc}\widehat A_\mu^b\widehat A_\nu^c.
$$

So the non-Abelian term has the opposite sign from the convention used on this page.

</details>

### Bianchi identity

Use the Jacobi identity for $D_\mu,D_\nu,D_\rho$ to derive

$$
\mathcal D_{[\mu}F_{\nu\rho]}=0.
$$

<details><summary><strong>Solution</strong></summary>

The Jacobi identity is

$$
[D_\mu,[D_\nu,D_\rho]]
+[D_\nu,[D_\rho,D_\mu]]
+[D_\rho,[D_\mu,D_\nu]]=0.
$$

Substitute $[D_\alpha,D_\beta]=igF_{\alpha\beta}$:

$$
ig\left([D_\mu,F_{\nu\rho}]+[D_\nu,F_{\rho\mu}]+[D_\rho,F_{\mu\nu}]\right)=0.
$$

For an adjoint-valued multiplication operator $X$,

$$
[D_\mu,X]=\partial_\mu X+ig[A_\mu,X]\equiv \mathcal D_\mu X.
$$

Hence

$$
\mathcal D_\mu F_{\nu\rho}
+\mathcal D_\nu F_{\rho\mu}
+\mathcal D_\rho F_{\mu\nu}=0,
$$

which is the Bianchi identity.

</details>

## Related pages

- [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/) explains the geometric meaning of the gauge potential.
- [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) explains the same object conceptually.
- [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/) studies the Yang–Mills version in more detail.
- [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/) uses $F_{\mu\nu}^aF^{a\mu\nu}$ to build the gauge-field dynamics.
- [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/) expands $F^2$ into cubic and quartic interactions.

## References

- Srednicki, *Quantum Field Theory*, especially the non-Abelian gauge theory and path-integral chapters.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the Yang–Mills theory chapter.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for gauge-theory conventions and non-Abelian dynamics.
- Nakahara, *Geometry, Topology and Physics*, and Frankel, *The Geometry of Physics*, for the connection and curvature viewpoint.

## Version history

- **2026-06-19:** Initial worked calculation deriving $F_{\mu\nu}$ from $[D_\mu,D_\nu]$, with Abelian, gauge-covariance, and Bianchi-identity checks.
