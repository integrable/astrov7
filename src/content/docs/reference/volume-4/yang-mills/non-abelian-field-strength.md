---
title: "Non-Abelian Field Strength"
description: "Derives the Yang–Mills field strength as curvature, explains its component signs, gauge covariance, infinitesimal holonomy, and Bianchi identity."
sidebar:
  label: "Non-Abelian Field Strength"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §69; Weinberg Vol. II §15.1; Schwartz §25.2; Zee Part IV.5; Polyakov, Gauge Fields and Strings, Ch. 1."
topics:
  - non-Abelian field strength
  - Yang–Mills curvature
  - Bianchi identity
  - infinitesimal holonomy
  - adjoint covariance
canonicalTopics:
  - non-abelian-field-strength
  - yang-mills-curvature
  - curvature-two-form
  - bianchi-identity
researchStatus:
  established:
    - "The local expression for the non-Abelian field strength and its covariant transformation law are standard consequences of treating the gauge field as a connection."
  active:
    - "Flat connections, global holonomies, line-operator spectra, and topological sectors require global data beyond the local curvature formula."
---

## Summary

The non-Abelian field strength is the curvature of a Yang–Mills connection. It is defined by the commutator of covariant derivatives,

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

where this volume uses

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

The result is

$$
\boxed{
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu]
}
$$

or, in components,

$$
\boxed{
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
}
$$

The commutator term is the whole story. It makes $F_{\mu\nu}$ transform covariantly,

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U,
$$

instead of with derivatives of the gauge parameter. It also makes pure Yang–Mills theory nonlinear, because $-\frac14F_{\mu\nu}^aF^{a\mu\nu}$ contains cubic and quartic gauge-boson interactions.

<figure class="doc-figure" style="--figure-width: 43rem;">

![The non-Abelian field strength is built from an Abelian curl plus a commutator term, and is checked by covariance, Bianchi identity, and small-loop holonomy.](/figures/gauge-theories-standard-model/non-abelian-field-strength-anatomy.svg)

<figcaption>

The non-Abelian field strength is not merely $\partial A-\partial A$. The commutator term $ig[A_\mu,A_\nu]$ is required by gauge covariance, controls infinitesimal holonomy, and gives the Bianchi identity $DF=0$ through the Jacobi identity.

</figcaption>
</figure>

## Prerequisites

You should know [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/) and [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/). The conceptual precursor is [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/), which introduced curvature for general gauge fields.

The convention load-bearing for this page is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
\psi\mapsto U^{-1}\psi.
$$

Many sources use $D_\mu=\partial_\mu-igA_\mu$. Do not import the component formula for $F_{\mu\nu}^a$ from such a source without translating signs.

## Core idea

The Abelian field strength is a curl:

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

That works because $U(1)$ phases commute. In a non-Abelian theory, the gauge potential is matrix-valued. Taking two infinitesimal gauge-covariant steps in different orders compares internal frames using different matrices, and the order matters. The curvature must therefore remember the commutator.

A good slogan is

$$
\text{non-Abelian curvature}
=
\text{ordinary curl}
+
\text{failure of internal rotations to commute}.
$$

More explicitly,

$$
F_{\mu\nu}
=
\underbrace{\partial_\mu A_\nu-\partial_\nu A_\mu}_{\text{curl part}}
+
\underbrace{ig[A_\mu,A_\nu]}_{\text{commutator part}}.
$$

The commutator part vanishes for Abelian gauge theory. For Yang–Mills theory it is mandatory, not optional. Without it, the object called “field strength” would not transform covariantly under local changes of internal frame.

## Setup and conventions

Let $G$ be a compact gauge group and let $T^a$ be Hermitian generators in a representation $R$:

$$
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

We usually suppress the representation label and write

$$
A_\mu=A_\mu^aT^a.
$$

The same component field $A_\mu^a$ can act through different matrices $T_R^a$ depending on the field it acts on. The field strength components $F_{\mu\nu}^a$ are representation-independent Lie-algebra components, while the matrix $F_{\mu\nu}=F_{\mu\nu}^aT_R^a$ depends on the representation used to act on matter.

The finite gauge transformation is

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

The covariant derivative transforms as an operator:

$$
D_\mu^U=U^{-1}D_\mu U.
$$

This operator equation is the shortest route to the curvature transformation law.

## Three equivalent definitions

There are three equivalent local ways to recognize the same object.

| Viewpoint | Formula | Meaning |
|---|---|---|
| Commutator of covariant derivatives | $[D_\mu,D_\nu]=igF_{\mu\nu}$ | Curvature is the failure of covariant derivatives to commute. |
| Differential forms | $F=dA+igA\wedge A$ | Curvature two-form of the connection $A$. |
| Small loop holonomy | $U_{\partial\Sigma}=1-igF_{\mu\nu}\Delta x^\mu\Delta x^\nu+O(\Delta x^3)$ | Curvature is detected by parallel transport around an infinitesimal loop. |

The first definition is best for deriving components. The second is best for geometry. The third is best for remembering why Wilson loops know about gauge fields.

## Commutator derivation

Act on a matter field $\psi$:

$$
D_\mu D_\nu\psi
=(\partial_\mu+igA_\mu)(\partial_\nu+igA_\nu)\psi.
$$

Expanding,

$$
\begin{aligned}
D_\mu D_\nu\psi
={}&\partial_\mu\partial_\nu\psi
+ig(\partial_\mu A_\nu)\psi
+igA_\nu\partial_\mu\psi\\
&+igA_\mu\partial_\nu\psi
-g^2A_\mu A_\nu\psi.
\end{aligned}
$$

Subtract the expression with $\mu$ and $\nu$ interchanged. The second derivatives cancel, and the terms with $A_\mu\partial_\nu\psi$ cancel. What remains is

$$
[D_\mu,D_\nu]\psi
=
ig(\partial_\mu A_\nu-\partial_\nu A_\mu)\psi
-g^2(A_\mu A_\nu-A_\nu A_\mu)\psi.
$$

Since

$$
-g^2(A_\mu A_\nu-A_\nu A_\mu)
=ig\,ig[A_\mu,A_\nu],
$$

we get

$$
[D_\mu,D_\nu]\psi
=
ig(\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu])\psi.
$$

Thus

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

This derivation is also a useful check on factors of $i$. The final expression must be Hermitian if $A_\mu$ and $T^a$ are Hermitian. Since $[A_\mu,A_\nu]$ is anti-Hermitian, the factor $i$ makes $ig[A_\mu,A_\nu]$ Hermitian after including real $g$.

## Component formula and the sign of the nonlinear term

Insert

$$
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

The commutator term is

$$
ig[A_\mu,A_\nu]
=igA_\mu^bA_\nu^c[T^b,T^c]
=igA_\mu^bA_\nu^c if^{bca}T^a.
$$

Therefore

$$
ig[A_\mu,A_\nu]
=-g f^{bca}A_\mu^bA_\nu^cT^a.
$$

Using cyclic antisymmetry of the structure constants, this is

$$
-g f^{abc}A_\mu^bA_\nu^cT^a.
$$

Hence

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

If your memory says the sign should be plus, your memory is probably using the other covariant derivative convention. The invariant definition $[D_\mu,D_\nu]=igF_{\mu\nu}$ is safer than memorizing the component sign.

## Gauge covariance

Because

$$
D_\mu^U=U^{-1}D_\mu U,
$$

we have

$$
[D_\mu^U,D_\nu^U]
=U^{-1}[D_\mu,D_\nu]U.
$$

Using the definition of $F_{\mu\nu}$,

$$
igF_{\mu\nu}^U
=igU^{-1}F_{\mu\nu}U,
$$

so

$$
\boxed{
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
}
$$

This is covariance, not invariance. In components, an infinitesimal transformation with

$$
U=1+ig\alpha+O(\alpha^2),
\qquad
\alpha=\alpha^aT^a,
$$

gives

$$
\delta_\alpha F_{\mu\nu}=ig[F_{\mu\nu},\alpha],
$$

or

$$
\boxed{
\delta_\alpha F_{\mu\nu}^a
=-gf^{abc}F_{\mu\nu}^b\alpha^c.
}
$$

A quick derivation uses $\delta A_\mu=D_\mu\alpha$:

$$
\delta F_{\mu\nu}
=D_\mu\delta A_\nu-D_\nu\delta A_\mu
=D_\mu D_\nu\alpha-D_\nu D_\mu\alpha
=[D_\mu,D_\nu]\alpha
=ig[F_{\mu\nu},\alpha].
$$

No derivative of $\alpha$ appears in the final answer. That cancellation is one of the best tests that the commutator term in $F_{\mu\nu}$ has the right coefficient.

## Differential forms and the Bianchi identity

Write the connection one-form as

$$
A=A_\mu dx^\mu.
$$

The curvature two-form is

$$
F=dA+igA\wedge A
=\frac12F_{\mu\nu}dx^\mu\wedge dx^\nu.
$$

The wedge product includes matrix multiplication. This matters: $A\wedge A$ does not vanish for a matrix-valued one-form, because the matrices need not commute.

The Bianchi identity is

$$
DF=0,
$$

or in components,

$$
\boxed{
D_\lambda F_{\mu\nu}+D_\mu F_{\nu\lambda}+D_\nu F_{\lambda\mu}=0.
}
$$

One way to see it is to use the Jacobi identity for covariant derivatives:

$$
[D_\lambda,[D_\mu,D_\nu]]
+[D_\mu,[D_\nu,D_\lambda]]
+[D_\nu,[D_\lambda,D_\mu]]=0.
$$

Substitute $[D_\mu,D_\nu]=igF_{\mu\nu}$. The result is precisely the component Bianchi identity.

In Abelian theory this reduces to

$$
\partial_\lambda F_{\mu\nu}+\partial_\mu F_{\nu\lambda}+\partial_\nu F_{\lambda\mu}=0,
$$

which is the familiar homogeneous Maxwell equation.

## Infinitesimal holonomy

With the Wilson-line convention used in this volume,

$$
U_C(y,x)=\mathcal P\exp\left(-ig\int_C A_\mu dz^\mu\right),
$$

parallel transport around a small rectangle in the $\mu\nu$ plane gives

$$
U_{\partial\Sigma}
=
1-igF_{\mu\nu}(x)\Delta x^\mu\Delta x^\nu
+O(\Delta x^3),
$$

for the orientation used in the figure. Reversing the loop orientation flips the sign.

This equation explains why curvature is operationally meaningful. A connection tells you how to transport a vector. Curvature tells you whether the result depends on the path. In a non-Abelian theory the result is a matrix, so the order along the path matters and the path-ordering symbol $\mathcal P$ is not negotiable.

For a closed loop, the trace

$$
\operatorname{tr}U_C
$$

is gauge invariant. This is the seed of Wilson-loop physics, confinement diagnostics, and the lattice formulation of gauge theory.

## Flat connections are locally pure gauge, not always globally trivial

If $F_{\mu\nu}=0$ on a simply connected patch, the connection is locally pure gauge. Equivalently, one can choose a gauge in which $A_\mu=0$ on that patch. In this sense curvature measures the local obstruction to removing the gauge field.

The word “locally” is essential. A connection can be flat and still have nontrivial global holonomy around a noncontractible loop. Such global information is invisible to the local formula for $F_{\mu\nu}$ but visible to Wilson loops. This distinction later becomes important for finite temperature, compact spaces, theta sectors, center symmetry, and global forms of gauge groups.

Tiny local loop: curvature. Big or topologically nontrivial loop: holonomy. Different beasts, same connection.

## Gauge-invariant local densities

Because $F_{\mu\nu}$ transforms by conjugation, traces of products of $F$ are gauge invariant. The most important local density is

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=\frac12F_{\mu\nu}^aF^{a\mu\nu}
$$

for $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. This gives the Yang–Mills kinetic term.

In four dimensions there is also the CP-odd density

$$
\operatorname{tr}(F_{\mu\nu}\widetilde F^{\mu\nu})
=\frac12F_{\mu\nu}^a\widetilde F^{a\mu\nu}.
$$

This is locally a total derivative but can detect global topological sectors. It belongs to the theta-angle story rather than the minimal kinetic action.

## Common pitfalls

**Pitfall 1: omitting the commutator term.** The curl part alone does not transform covariantly in a non-Abelian theory. The commutator term cancels derivative terms from the local gauge rotation.

**Pitfall 2: memorizing the sign without the convention.** With $D_\mu=\partial_\mu+igA_\mu$, the component nonlinear term is $-gf^{abc}A_\mu^bA_\nu^c$. With the opposite convention, the sign changes.

**Pitfall 3: calling $F_{\mu\nu}$ gauge invariant.** It is gauge covariant. Traces and singlet contractions are gauge invariant.

**Pitfall 4: forgetting that $A\wedge A$ can be nonzero.** For ordinary scalar-valued one-forms, $A\wedge A=0$. For matrix-valued one-forms, the matrix product makes $A\wedge A$ encode the commutator.

**Pitfall 5: identifying $F=0$ with $A=0$ globally.** A flat connection can have nontrivial holonomy on a space with noncontractible cycles. Local curvature does not exhaust global gauge-field data.

**Pitfall 6: suppressing representation labels too much.** The components $F_{\mu\nu}^a$ are Lie-algebra components. The matrix $F_{\mu\nu}=F_{\mu\nu}^aT_R^a$ depends on the representation $R$ used to act on matter.

## Relations to other pages

- [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/) gives the broader curvature viewpoint and Abelian/non-Abelian comparison.
- [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/) derives the finite transformation law for $A_\mu$ and $F_{\mu\nu}$.
- [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/) uses $\operatorname{tr}(F^2)$ to build the classical action and equations of motion.
- Covariant Derivative in Representations explains how $F_{\mu\nu}$ acts on different representation spaces.
- Gauge-Boson Self-Interactions expands the commutator term into three- and four-gauge-boson vertices.
- Wilson Loops, Phases, and Confinement studies finite holonomy as a nonperturbative observable.

## Research status

The local field-strength formula, Bianchi identity, and gauge-covariance law are settled. They are part of the classical definition of Yang–Mills theory.

The global and quantum implications are still rich. Flat connections, bundles on nontrivial manifolds, instantons, theta vacua, line operators, center symmetry, confinement, and the mass gap all depend on information not visible in a single local formula. This page gives the local curvature; later pages explain what the curvature does not see.

## Exercises

### Exercise 1: Derive the component sign

Starting from

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
\qquad
A_\mu=A_\mu^aT^a,
$$

and $[T^a,T^b]=if^{abc}T^c$, derive

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

<details>
<summary><strong>Solution</strong></summary>

The derivative terms give

$$
(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)T^a.
$$

The commutator term is

$$
ig[A_\mu,A_\nu]
=igA_\mu^bA_\nu^c[T^b,T^c]
=igA_\mu^bA_\nu^c if^{bca}T^a.
$$

Since $i^2=-1$,

$$
ig[A_\mu,A_\nu]
=-g f^{bca}A_\mu^bA_\nu^cT^a.
$$

Relabeling the cyclic structure-constant indices gives

$$
-g f^{abc}A_\mu^bA_\nu^cT^a.
$$

Therefore

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

</details>

### Exercise 2: Infinitesimal covariance

Use $\delta A_\mu=D_\mu\alpha$ and $\delta F_{\mu\nu}=D_\mu\delta A_\nu-D_\nu\delta A_\mu$ to show that

$$
\delta F_{\mu\nu}=ig[F_{\mu\nu},\alpha].
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute $\delta A_\mu=D_\mu\alpha$:

$$
\delta F_{\mu\nu}
=D_\mu D_\nu\alpha-D_\nu D_\mu\alpha
=[D_\mu,D_\nu]\alpha.
$$

Using $[D_\mu,D_\nu]=igF_{\mu\nu}$ as an operator acting by commutator on adjoint-valued objects,

$$
[D_\mu,D_\nu]\alpha=ig[F_{\mu\nu},\alpha].
$$

Thus

$$
\delta F_{\mu\nu}=ig[F_{\mu\nu},\alpha].
$$

</details>

### Exercise 3: Bianchi identity from Jacobi

Use the Jacobi identity

$$
[D_\lambda,[D_\mu,D_\nu]]+
[D_\mu,[D_\nu,D_\lambda]]+
[D_\nu,[D_\lambda,D_\mu]]=0
$$

and $[D_\mu,D_\nu]=igF_{\mu\nu}$ to derive

$$
D_\lambda F_{\mu\nu}+D_\mu F_{\nu\lambda}+D_\nu F_{\lambda\mu}=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert $[D_\mu,D_\nu]=igF_{\mu\nu}$ into the first nested commutator:

$$
[D_\lambda,[D_\mu,D_\nu]]=[D_\lambda,igF_{\mu\nu}].
$$

As an operator on matter fields, this is multiplication by

$$
igD_\lambda F_{\mu\nu}.
$$

The other two cyclic terms similarly give $igD_\mu F_{\nu\lambda}$ and $igD_\nu F_{\lambda\mu}$. The Jacobi identity therefore becomes

$$
ig(D_\lambda F_{\mu\nu}+D_\mu F_{\nu\lambda}+D_\nu F_{\lambda\mu})=0.
$$

Cancel $ig$ to obtain the Bianchi identity.

</details>

### Exercise 4: Abelian limit

Set $f^{abc}=0$. Show that the non-Abelian formulas reduce to

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
\delta F_{\mu\nu}=0,
\qquad
\partial_{[\lambda}F_{\mu\nu]}=0.
$$

<details>
<summary><strong>Solution</strong></summary>

If $f^{abc}=0$, all generators commute. Therefore $[A_\mu,A_\nu]=0$, and the field strength becomes the ordinary curl:

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The infinitesimal transformation is $\delta A_\mu=\partial_\mu\alpha$, so

$$
\delta F_{\mu\nu}
=\partial_\mu\partial_\nu\alpha-\partial_\nu\partial_\mu\alpha=0.
$$

The Bianchi identity becomes the statement that antisymmetrizing three ordinary derivatives of $A_\mu$ gives zero:

$$
\partial_{[\lambda}F_{\mu\nu]}=0.
$$

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §69, for the construction of non-Abelian gauge theory and the field-strength convention used in a particle-physics normalization.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for gauge invariance, Wilson lines, and the Yang–Mills field strength.
- Zee, *Quantum Field Theory in a Nutshell*, Part IV.5, for a compact physical introduction to non-Abelian gauge theory.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, §15.1, for a systematic derivation of non-Abelian gauge transformations and field strength.
- Polyakov, *Gauge Fields and Strings*, Ch. 1, for the local-symmetry and gauge-field viewpoint that leads naturally to Wilson loops and nonperturbative gauge theory.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic explanation of gauge fields, curvature, and the Higgs phenomenon.

## Version history

- **2026-06-17:** Initial polished draft. Added commutator derivation, component sign check, gauge covariance, Bianchi identity, infinitesimal holonomy, flat-connection caveat, and exercises.
