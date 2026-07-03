---
title: "Non-Abelian Gauge Transformations"
description: "Derives the finite and infinitesimal transformation laws for matter fields, Yang–Mills connections, covariant derivatives, and field strength in the volume convention."
sidebar:
  label: "Non-Abelian Gauge Transformations"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §69; Weinberg Vol. II §15.1; Schwartz §25.2; Coleman, Aspects of Symmetry, Secret Symmetry."
topics:
  - non-Abelian gauge transformations
  - Yang–Mills connection
  - covariant derivative
  - adjoint representation
  - gauge covariance
canonicalTopics:
  - non-abelian-gauge-transformations
  - yang-mills-connection
  - adjoint-transformation
  - gauge-covariant-field-strength
researchStatus:
  established:
    - "The local finite and infinitesimal transformation laws of Yang–Mills theory are textbook-standard once a convention for the covariant derivative is fixed."
  active:
    - "Large gauge transformations, boundary transformations, and global-form choices require additional global data beyond these local formulas."
---

## Summary

A non-Abelian gauge transformation is a spacetime-dependent change of internal frame valued in a Lie group $G$. In this volume we use

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators. A matter field in representation $R$ transforms as

$$
\psi(x)\mapsto U_R^{-1}(x)\psi(x),
\qquad
U_R(x)=\exp\{ig\alpha^a(x)T_R^a\}.
$$

Demanding that the covariant derivative transform like the field,

$$
D_\mu\psi\mapsto U_R^{-1}D_\mu\psi,
$$

fixes the gauge-field transformation law:

$$
\boxed{
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
}
$$

The field strength transforms without the inhomogeneous derivative term,

$$
\boxed{
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U,
}
$$

so it is gauge covariant rather than gauge invariant. This is the first major difference from QED: in a non-Abelian theory, even the curvature carries gauge charge.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A map of non-Abelian transformation laws: matter, covariant derivative, connection, and curvature.](/figures/gauge-theories-standard-model/non-abelian-transformation-map.svg)

<figcaption>

Non-Abelian gauge transformations in the convention $D_\mu=\partial_\mu+igA_\mu$. Matter fields and covariant derivatives transform with $U^{-1}$, the connection transforms with an extra derivative term, and the curvature transforms by conjugation only.

</figcaption>
</figure>

## Prerequisites

You should know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the sign convention for $D_\mu$ and $F_{\mu\nu}$. You should also know [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/), [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/), and [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/).

The needed group theory is the minimum package: generators $T^a$, commutators, structure constants $f^{abc}$, and the idea that a representation $R$ assigns a matrix $T_R^a$ to each generator.

## Core idea

In QED, the local gauge transformation is a phase. Phases commute, so the gauge field only shifts by a derivative and the field strength is invariant.

In Yang–Mills theory, the local gauge transformation is a matrix. Matrices at the same point need not commute, and matrices at different points can rotate internal frames differently. The gauge field has to do two jobs at once:

1. cancel the derivative of the local frame rotation;
2. rotate as a Lie-algebra-valued object under the local frame change.

That is why the connection transformation contains two pieces:

$$
A_\mu^U
=
\underbrace{U^{-1}A_\mu U}_{\text{homogeneous rotation}}
-
\underbrace{\frac{i}{g}U^{-1}\partial_\mu U}_{\text{inhomogeneous derivative correction}}.
$$

The curvature $F_{\mu\nu}$ is different. It measures the failure of covariant derivatives to commute, so the derivative pieces cancel. It transforms only by conjugation:

$$
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
$$

This is the compact statement behind the whole chapter. The Yang–Mills action works because traces are invariant under conjugation.

## Setup and conventions

Let $G$ be a compact Lie group with Hermitian generators $T^a$ in a representation $R$:

$$
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

For $SU(N)$ in the fundamental representation, we use

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

The gauge field is a Lie-algebra-valued one-form,

$$
A_\mu=A_\mu^aT^a,
$$

where $T^a$ should be read as the generator in whichever representation is acting on the field under discussion.

The covariant derivative on a matter field in representation $R$ is

$$
D_\mu\psi=(\partial_\mu+igA_\mu^aT_R^a)\psi.
$$

The local gauge transformation is written

$$
U_R(x)=\exp\{ig\alpha^a(x)T_R^a\},
\qquad
\psi(x)\mapsto \psi^U(x)=U_R^{-1}(x)\psi(x).
$$

The coupling $g$ is included in the exponent by convention. Some books instead write $U=\exp\{i\theta^aT^a\}$, with $\theta^a=g\alpha^a$. That change is harmless, but it moves factors of $g$ between the gauge parameter and the transformation law.

## Deriving the finite transformation of the connection

The defining requirement is covariance of the derivative:

$$
D_\mu^U\psi^U=U^{-1}D_\mu\psi.
$$

Write

$$
D_\mu^U=\partial_\mu+igA_\mu^U.
$$

Then

$$
(\partial_\mu+igA_\mu^U)(U^{-1}\psi)
=
(\partial_\mu U^{-1})\psi+U^{-1}\partial_\mu\psi+igA_\mu^UU^{-1}\psi.
$$

For this to equal

$$
U^{-1}(\partial_\mu+igA_\mu)\psi
=U^{-1}\partial_\mu\psi+igU^{-1}A_\mu\psi
$$

for every $\psi$, the non-$\partial_\mu\psi$ terms must satisfy

$$
(\partial_\mu U^{-1})+igA_\mu^UU^{-1}=igU^{-1}A_\mu.
$$

Multiplying on the right by $U$ and using

$$
(\partial_\mu U^{-1})U=-U^{-1}(\partial_\mu U),
$$

gives

$$
\boxed{
A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
}
$$

Equivalently, as an operator,

$$
D_\mu^U=U^{-1}D_\mu U.
$$

This operator equation is often the cleanest way to remember the result. The connection transformation is the coordinate expression of the statement that covariant differentiation is independent of the local internal frame.

## Infinitesimal transformations

For an infinitesimal transformation,

$$
U(x)=1+ig\alpha(x)+O(\alpha^2),
\qquad
\alpha(x)=\alpha^a(x)T^a.
$$

Using the finite formula gives

$$
A_\mu^U
=A_\mu+\partial_\mu\alpha+ig[A_\mu,\alpha]+O(\alpha^2).
$$

Thus

$$
\delta_\alpha A_\mu
=\partial_\mu\alpha+ig[A_\mu,\alpha].
$$

In components,

$$
\boxed{
\delta_\alpha A_\mu^a
=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
}
$$

The second term is the non-Abelian part. If $f^{abc}=0$, this reduces to the Abelian shift $A_\mu^a\mapsto A_\mu^a+\partial_\mu\alpha^a$.

It is useful to introduce the adjoint covariant derivative acting on an adjoint-valued quantity $X=X^aT^a$:

$$
D_\mu X=\partial_\mu X+ig[A_\mu,X],
$$

or

$$
(D_\mu X)^a=\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

Then the infinitesimal transformation of the connection is simply

$$
\delta_\alpha A_\mu=D_\mu\alpha.
$$

This formula is compact but slightly treacherous: $A_\mu$ itself is not an adjoint matter field because it has the extra inhomogeneous derivative term. Only its infinitesimal variation can be written using $D_\mu\alpha$.

## Curvature transforms covariantly

The field strength is defined by

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

Since

$$
D_\mu^U=U^{-1}D_\mu U,
$$

we get

$$
[D_\mu^U,D_\nu^U]
=U^{-1}[D_\mu,D_\nu]U.
$$

Therefore

$$
igF_{\mu\nu}^U=igU^{-1}F_{\mu\nu}U,
$$

and hence

$$
\boxed{
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
}
$$

Using the commutator definition with our convention gives

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
$$

or in components

$$
\boxed{
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
}
$$

For infinitesimal transformations,

$$
\delta_\alpha F_{\mu\nu}=ig[F_{\mu\nu},\alpha],
$$

so

$$
\boxed{
\delta_\alpha F_{\mu\nu}^a
=-gf^{abc}F_{\mu\nu}^b\alpha^c.
}
$$

There is no $\partial_\mu\alpha$ term. That is the crucial difference between a connection and its curvature.

## Why the Yang–Mills action is gauge invariant

The local Yang–Mills kinetic term is

$$
\mathcal L_{\mathrm{YM}}
=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

Under a gauge transformation,

$$
\operatorname{tr}(F_{\mu\nu}^UF^{U\mu\nu})
=
\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U)
=
\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U)
=
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}),
$$

where the last step uses cyclicity of the trace.

For generators normalized by $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$,

$$
\mathcal L_{\mathrm{YM}}
=-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

This is why $F_{\mu\nu}$ need not be gauge invariant as a matrix. Gauge invariance of the action only requires the trace of the quadratic combination.

## Matter bilinears and conjugate fields

A matter field transforms as $\psi\mapsto U^{-1}\psi$. Its Hermitian conjugate transforms as

$$
\psi^\dagger\mapsto \psi^\dagger U,
$$

and for Dirac fields, since $U$ acts only on internal indices,

$$
\bar\psi\mapsto \bar\psi U.
$$

Therefore the Dirac kinetic term is gauge invariant:

$$
\bar\psi i\gamma^\mu D_\mu\psi
\mapsto
\bar\psi U i\gamma^\mu U^{-1}D_\mu\psi
=
\bar\psi i\gamma^\mu D_\mu\psi.
$$

A mass term $m\bar\psi\psi$ is invariant if the left- and right-handed fields transform in compatible representations. This caveat becomes important for chiral gauge theories and the Standard Model: not every fermion mass term allowed by Lorentz symmetry is allowed by gauge symmetry.

For a scalar field in representation $R$,

$$
(D_\mu\phi)^\dagger D^\mu\phi
$$

is invariant for the same reason. The potential must be built from invariant contractions, such as $\phi^\dagger\phi$ for a fundamental scalar, or more complicated singlet contractions for tensor representations.

## Abelian limit and representation independence

There are two useful checks on the formulas.

First, if $G=U(1)$, all matrices commute. The homogeneous conjugation is trivial and the finite transformation reduces to

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

matching the Abelian convention after identifying the charge carried by the matter field.

Second, the gauge-field components $A_\mu^a$ do not depend on which matter representation we use to derive the transformation law. The matrices $T_R^a$ change with $R$, but the structure constants $f^{abc}$ are the same Lie-algebra data. The component formula

$$
\delta_\alpha A_\mu^a
=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c
$$

is therefore representation-independent.

This is essential. A single gluon field $G_\mu^A$ must couple consistently to quarks in the fundamental representation, antiquarks in the antifundamental representation, and gluons in the adjoint representation.

## Transformation table

| Object | Transformation law | Comment |
|---|---|---|
| Matter field | $\psi\mapsto U^{-1}\psi$ | Convention paired with $D_\mu=\partial_\mu+igA_\mu$. |
| Conjugate matter field | $\bar\psi\mapsto \bar\psi U$ | Internal matrices commute with $\gamma^\mu$. |
| Covariant derivative | $D_\mu\mapsto U^{-1}D_\mu U$ | Operator statement. |
| Connection | $A_\mu\mapsto U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U$ | Has an inhomogeneous derivative term. |
| Curvature | $F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U$ | Gauge covariant, not gauge invariant. |
| Adjoint field | $X\mapsto U^{-1}XU$ | Includes $F_{\mu\nu}$, ghosts, and adjoint matter. |
| Infinitesimal connection | $\delta A_\mu^a=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c$ | Reduces to Abelian shift when $f^{abc}=0$. |
| Infinitesimal curvature | $\delta F_{\mu\nu}^a=-gf^{abc}F_{\mu\nu}^b\alpha^c$ | No derivative of the gauge parameter. |

## Common pitfalls

**Using the wrong sign convention from memory.** Many texts use $D_\mu=\partial_\mu-igA_\mu$. This page uses $D_\mu=\partial_\mu+igA_\mu$. Translate all transformation laws before borrowing formulas.

**Forgetting that $F_{\mu\nu}$ is not invariant.** In Yang–Mills theory, $F_{\mu\nu}$ transforms by conjugation. The trace $\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})$ is invariant; the matrix $F_{\mu\nu}$ is not.

**Treating $A_\mu$ as an adjoint matter field.** The connection has an inhomogeneous derivative term. Only differences of connections, or curvature-like objects, transform homogeneously.

**Confusing global color rotations with gauge transformations.** A constant $U$ is contained among gauge transformations, but in a gauge theory the meaning of global remnants depends on boundary conditions and which transformations are counted as redundancies. Do not infer physical global color charges from the local formulas alone.

**Suppressing representation labels too aggressively.** The object $A_\mu=A_\mu^aT^a$ acts using $T_R^a$ on a field in representation $R$. The component gauge field $A_\mu^a$ is shared, but the matrix acting on the field changes with the representation.

**Forgetting path ordering in finite transport.** For non-Abelian $G$, matrices along a path do not commute. Wilson lines require $\mathcal P$, and open Wilson lines transform at their endpoints.

## Relations to other pages

- [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/) fixes the sign convention used here.
- [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/) gives the geometric interpretation of $A_\mu$ and Wilson lines.
- [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) derives $F_{\mu\nu}$ from the commutator of covariant derivatives.
- [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/) explains why traces, singlet contractions, and Wilson loops are the natural observables.
- Yang–Mills Action uses the transformation law of $F_{\mu\nu}$ to build the classical action.

## Research status

The local transformation laws on this page are settled textbook material. The convention-dependent signs are not physical; the invariant content is the covariance of $D_\mu$, the conjugation law for $F_{\mu\nu}$, and the gauge invariance of trace observables.

The global story is richer. Large gauge transformations, boundary conditions, global forms such as $SU(N)$ versus $SU(N)/\mathbb Z_N$, center one-form symmetries, and line-operator spectra are not determined by the local Lie algebra alone. Those issues are treated later because they affect confinement diagnostics, theta sectors, and the precise meaning of the Standard Model gauge group.

## Exercises

### Exercise 1: Derive the connection transformation law

Starting from

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
\psi^U=U^{-1}\psi,
$$

impose

$$
D_\mu^U\psi^U=U^{-1}D_\mu\psi.
$$

Derive

$$
A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

<details>
<summary><strong>Solution</strong></summary>

Write $D_\mu^U=\partial_\mu+igA_\mu^U$. Then

$$
D_\mu^U(U^{-1}\psi)
=(\partial_\mu U^{-1})\psi+U^{-1}\partial_\mu\psi+igA_\mu^UU^{-1}\psi.
$$

This must equal

$$
U^{-1}\partial_\mu\psi+igU^{-1}A_\mu\psi.
$$

Cancel the common $U^{-1}\partial_\mu\psi$ term and multiply on the right by $U$:

$$
(\partial_\mu U^{-1})U+igA_\mu^U=igU^{-1}A_\mu U.
$$

Using $(\partial_\mu U^{-1})U=-U^{-1}\partial_\mu U$ gives

$$
igA_\mu^U=igU^{-1}A_\mu U+U^{-1}\partial_\mu U.
$$

Dividing by $ig$ yields

$$
A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

</details>

### Exercise 2: Infinitesimal transformation of the gauge field

Let

$$
U=1+ig\alpha+O(\alpha^2),
\qquad
\alpha=\alpha^aT^a.
$$

Use the finite transformation law to show that

$$
\delta A_\mu^a=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

<details>
<summary><strong>Solution</strong></summary>

To first order,

$$
U^{-1}=1-ig\alpha+O(\alpha^2),
\qquad
U^{-1}\partial_\mu U=ig\partial_\mu\alpha+O(\alpha^2).
$$

Also

$$
U^{-1}A_\mu U
=(1-ig\alpha)A_\mu(1+ig\alpha)
=A_\mu+ig[A_\mu,\alpha]+O(\alpha^2).
$$

Therefore

$$
A_\mu^U=A_\mu+\partial_\mu\alpha+ig[A_\mu,\alpha]+O(\alpha^2).
$$

Using

$$
[A_\mu,\alpha]=A_\mu^b\alpha^c[T^b,T^c]
=iA_\mu^b\alpha^cf^{bca}T^a,
$$

we get

$$
\delta A_\mu^a=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

</details>

### Exercise 3: Curvature covariance from the commutator

Assume $D_\mu^U=U^{-1}D_\mu U$ and $[D_\mu,D_\nu]=igF_{\mu\nu}$. Show that

$$
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute the transformed commutator as an operator:

$$
[D_\mu^U,D_\nu^U]
=[U^{-1}D_\mu U,U^{-1}D_\nu U]
=U^{-1}[D_\mu,D_\nu]U.
$$

Using $[D_\mu,D_\nu]=igF_{\mu\nu}$ and $[D_\mu^U,D_\nu^U]=igF_{\mu\nu}^U$ gives

$$
igF_{\mu\nu}^U=igU^{-1}F_{\mu\nu}U.
$$

Cancel $ig$ to obtain

$$
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
$$

</details>

### Exercise 4: Gauge invariance of the trace kinetic term

Use $F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U$ and cyclicity of the trace to prove that

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

Under a gauge transformation,

$$
\operatorname{tr}(F_{\mu\nu}^UF^{U\mu\nu})
=
\operatorname{tr}(U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U).
$$

Since $UU^{-1}=1$,

$$
\operatorname{tr}(F_{\mu\nu}^UF^{U\mu\nu})
=
\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U).
$$

By cyclicity,

$$
\operatorname{tr}(U^{-1}F_{\mu\nu}F^{\mu\nu}U)
=
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}UU^{-1})
=
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §69, for the construction of non-Abelian gauge theory from localizing a global $SU(N)$ symmetry.
- Schwartz, *Quantum Field Theory and the Standard Model*, §25.2, for the Wilson-line and covariant-derivative viewpoint on Abelian and non-Abelian gauge invariance.
- Zee, *Quantum Field Theory in a Nutshell*, non-Abelian gauge theory chapters, for physical intuition and a fast comparison with QED.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, §15.1, for a systematic treatment of gauge transformations, field strength, and Yang–Mills Lagrangians.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic conceptual discussion of gauge fields and gauge invariance.
- Polyakov, *Gauge Fields and Strings*, Ch. 1, for local symmetry as the entry point to gauge systems, Wilson loops, and nonperturbative gauge theory.

## Version history

- **2026-06-17:** Initial polished draft. Fixed the finite and infinitesimal transformation laws to the volume convention $D_\mu=\partial_\mu+igA_\mu$ and added the transformation-law map figure.
