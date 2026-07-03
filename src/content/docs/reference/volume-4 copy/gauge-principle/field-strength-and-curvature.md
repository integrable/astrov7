---
title: "Field Strength and Curvature"
description: "Derives the gauge field strength as curvature, the commutator of covariant derivatives, infinitesimal Wilson-loop holonomy, and the Bianchi identity."
sidebar:
  label: "Field Strength and Curvature"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II §15.1; Srednicki §69; Schwartz Ch. 25; Zee Part IV.5; Polyakov Ch. 1."
topics:
  - field strength
  - curvature
  - commutator of covariant derivatives
  - Bianchi identity
canonicalTopics:
  - gauge-field-strength
  - curvature-two-form
  - bianchi-identity
researchStatus:
  established:
    - "The field strength as the curvature of a gauge connection is a standard local formulation of Abelian and non-Abelian gauge theory."
  active:
    - "Global issues such as flat but topologically nontrivial connections, allowed line operators, and generalized symmetries add physical data beyond the local curvature form."
---

## Summary

A gauge field $A_\mu$ is a connection: it tells us how to compare internal vectors at nearby spacetime points. Its field strength $F_{\mu\nu}$ is the corresponding **curvature**: it measures the failure of parallel transport around a tiny closed loop to return an internal vector to itself.

In this volume's convention,

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators $T^a$. The field strength is defined by

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

Equivalently,

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
$$

or in components,

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

For an Abelian gauge group the commutator term vanishes, and this reduces to the familiar electromagnetic expression. For a non-Abelian gauge group the extra term is not decoration. It is exactly what makes the curvature transform covariantly,

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U,
$$

and it is the seed of gauge-boson self-interactions in Yang–Mills theory.

## Prerequisites

You should know [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/) and [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/). The only algebra needed is matrix multiplication, the Lie-algebra commutator, and the fact that covariant derivatives should transform like the fields they act on.

The conventions are those of [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/): mostly-minus metric, Hermitian generators, and

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

## Core idea

Ordinary derivatives commute on a smooth scalar function:

$$
[\partial_\mu,\partial_\nu]f=0.
$$

Covariant derivatives need not commute, because each covariant derivative contains a comparison rule in internal space. Taking two covariant steps in opposite orders can produce a mismatch. That mismatch is the curvature.

The whole local theory is compressed into the equation

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

The left-hand side says “compare by going first in the $\mu$ direction and then in the $\nu$ direction, and subtract the reverse comparison.” The right-hand side says the result is multiplication by a Lie-algebra-valued tensor $F_{\mu\nu}$.

<figure class="doc-figure" style="--figure-width: 43rem;">

![The field strength measures the mismatch between two infinitesimal covariant transports around a small plaquette.](/figures/gauge-theories-standard-model/field-strength-plaquette.svg)

<figcaption>

The field strength is the curvature of the gauge connection. It is detected either by the commutator $[D_\mu,D_\nu]$ or by the leading nontrivial term in the holonomy around a small loop.

</figcaption>
</figure>

This page derives the formula, its gauge transformation law, the Bianchi identity, and the Yang–Mills kinetic term.

## Setup and conventions

The gauge field is a matrix-valued one-form

$$
A=A_\mu dx^\mu,
\qquad
A_\mu=A_\mu^aT^a.
$$

The covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu,
$$

and a matter field in the chosen representation transforms as

$$
\psi\mapsto U^{-1}\psi.
$$

The gauge field transforms as a connection:

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

It is useful to distinguish two ways of writing curvature. In component language we write

$$
[D_\mu,D_\nu]=igF_{\mu\nu}.
$$

In differential-form language,

$$
D=d+igA,
$$

and the curvature two-form is

$$
F=dA+igA\wedge A.
$$

The wedge product includes matrix multiplication. Written in components,

$$
F=\frac12F_{\mu\nu}dx^\mu\wedge dx^\nu.
$$

The factor $1/2$ is only the usual convention for an antisymmetric two-form; it does not change the component formula.

## The commutator derivation

Let $D_\mu$ act on a matter field $\psi$:

$$
D_\mu\psi=(\partial_\mu+igA_\mu)\psi.
$$

Then

$$
\begin{aligned}
D_\mu D_\nu\psi
&=(\partial_\mu+igA_\mu)(\partial_\nu+igA_\nu)\psi\\
&=\partial_\mu\partial_\nu\psi
+ig(\partial_\mu A_\nu)\psi
+igA_\nu\partial_\mu\psi
+igA_\mu\partial_\nu\psi
-g^2A_\mu A_\nu\psi.
\end{aligned}
$$

Interchanging $\mu$ and $\nu$ and subtracting, the ordinary second derivatives and the terms with one $A$ multiplying one derivative cancel in pairs. What remains is

$$
[D_\mu,D_\nu]\psi
=
ig(\partial_\mu A_\nu-\partial_\nu A_\mu)\psi
-g^2(A_\mu A_\nu-A_\nu A_\mu)\psi.
$$

Therefore

$$
[D_\mu,D_\nu]\psi
=
ig\left(\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu]\right)\psi.
$$

Since this holds for any matter field in the representation,

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

Now insert

$$
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

The commutator contribution is

$$
ig[A_\mu,A_\nu]
=igA_\mu^bA_\nu^c[T^b,T^c]
=-gA_\mu^bA_\nu^c f^{bca}T^a.
$$

Using cyclic antisymmetry of the structure constants, this gives

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

This is the formula tied to the convention $D_\mu=\partial_\mu+igA_\mu$. If you read a source with $D_\mu=\partial_\mu-igA_\mu$, the sign of the non-Abelian term is usually reversed.

## Gauge transformation of curvature

The cleanest derivation uses the covariant derivative itself. Under a gauge transformation,

$$
D_\mu\mapsto D_\mu^U=U^{-1}D_\mu U
$$

as an operator. Therefore

$$
[D_\mu^U,D_\nu^U]
=
[U^{-1}D_\mu U,U^{-1}D_\nu U]
=
U^{-1}[D_\mu,D_\nu]U.
$$

Using $[D_\mu,D_\nu]=igF_{\mu\nu}$, we get

$$
igF_{\mu\nu}^U=igU^{-1}F_{\mu\nu}U,
$$

hence

$$
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
$$

This is a crucial distinction between Abelian and non-Abelian theory. In QED, $F_{\mu\nu}$ is gauge invariant. In a non-Abelian theory, $F_{\mu\nu}$ is not invariant as a matrix; it transforms covariantly by conjugation. Gauge-invariant local quantities are built by contracting all gauge indices, for example

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

For an infinitesimal transformation

$$
U=1+ig\theta+O(\theta^2),
\qquad
\theta=\theta^aT^a,
$$

the curvature changes by

$$
\delta F_{\mu\nu}=ig[F_{\mu\nu},\theta].
$$

In components,

$$
\delta F_{\mu\nu}^a=-gf^{abc}F_{\mu\nu}^b\theta^c.
$$

No derivative of $\theta$ appears. The inhomogeneous derivative term in the transformation of $A_\mu$ has disappeared. That is what it means for $F_{\mu\nu}$ to be tensorial, or covariant, rather than a connection.

## Curvature as infinitesimal holonomy

The connection page introduced finite parallel transport along a path $C$:

$$
U_C(y,x)
=
\mathcal P\exp\left(-ig\int_C A_\mu dz^\mu\right).
$$

Around a tiny rectangle spanned by $\Delta x^\mu$ and $\Delta x^\nu$, the closed-loop holonomy is

$$
U_{\partial\Sigma}
=
1-igF_{\mu\nu}(x)\Delta x^\mu\Delta x^\nu
+O(\Delta x^3),
$$

with the sign corresponding to the orientation shown in the figure. This is the finite-transport version of the commutator formula.

This expression is often the most physical definition of curvature. If $F_{\mu\nu}=0$ on a small patch, parallel transport around sufficiently small contractible loops is trivial up to higher-order corrections. If $F_{\mu\nu}\neq 0$, the connection has local curvature: internal vectors remember the route by which they were transported.

The Abelian version is familiar from electromagnetism. The phase acquired by a charge $q$ around a small loop is

$$
\exp\left(-iq\oint A\right)
=
1-iq\int_\Sigma F+\cdots.
$$

For a non-Abelian group, the same statement remains true but with matrix-valued path-ordered holonomy.

## Abelian field strength

For $U(1)$,

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

The commutator is

$$
[D_\mu,D_\nu]=iq(\partial_\mu A_\nu-\partial_\nu A_\mu),
$$

so

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

Under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$,

$$
F_{\mu\nu}\mapsto
F_{\mu\nu}
+\partial_\mu\partial_\nu\alpha
-\partial_\nu\partial_\mu\alpha
=
F_{\mu\nu}.
$$

Thus the electromagnetic field strength is gauge invariant.

With the mostly-minus metric and the common electromagnetic convention used in this volume,

$$
F_{\mu\nu}F^{\mu\nu}=2(\mathbf B^2-\mathbf E^2),
$$

and the Maxwell kinetic term is

$$
\mathcal L_{\mathrm{Maxwell}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
=
\frac12(\mathbf E^2-\mathbf B^2).
$$

The equation $F=dA$ also implies the Abelian Bianchi identity

$$
\partial_{[\lambda}F_{\mu\nu]}=0,
$$

which contains the homogeneous Maxwell equations.

## Non-Abelian Bianchi identity

For a non-Abelian connection, the Bianchi identity is not $dF=0$. The correct statement is covariant:

$$
DF=0.
$$

In components,

$$
D_\lambda F_{\mu\nu}
+D_\mu F_{\nu\lambda}
+D_\nu F_{\lambda\mu}=0,
$$

where the adjoint covariant derivative is

$$
D_\lambda F_{\mu\nu}
=
\partial_\lambda F_{\mu\nu}+ig[A_\lambda,F_{\mu\nu}].
$$

In components,

$$
(D_\lambda F_{\mu\nu})^a
=
\partial_\lambda F_{\mu\nu}^a
-gf^{abc}A_\lambda^bF_{\mu\nu}^c.
$$

The shortest proof is the Jacobi identity for covariant derivatives:

$$
[D_\lambda,[D_\mu,D_\nu]]
+[D_\mu,[D_\nu,D_\lambda]]
+[D_\nu,[D_\lambda,D_\mu]]
=0.
$$

Using $[D_\mu,D_\nu]=igF_{\mu\nu}$, the Jacobi identity becomes precisely

$$
D_\lambda F_{\mu\nu}
+D_\mu F_{\nu\lambda}
+D_\nu F_{\lambda\mu}
=0.
$$

Do not confuse this with the equation of motion. The Bianchi identity is a geometric identity obeyed by any connection. The equation of motion follows from an action and can be changed by matter sources or higher-derivative terms.

## Yang–Mills kinetic term

Because $F_{\mu\nu}$ transforms by conjugation,

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U,
$$

the trace

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant. The standard Yang–Mills Lagrangian is

$$
\mathcal L_{\mathrm{YM}}
=
-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

With fundamental $SU(N)$ normalization

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

this is

$$
\mathcal L_{\mathrm{YM}}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

Expanding the non-Abelian field strength shows why Yang–Mills gauge bosons self-interact. Let

$$
f_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a.
$$

Then

$$
F_{\mu\nu}^a=f_{\mu\nu}^a-gf^{abc}A_\mu^bA_\nu^c.
$$

Therefore

$$
\begin{aligned}
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
&=
-\frac14 f_{\mu\nu}^af^{a\mu\nu}
+\frac{g}{2}f^{abc}f_{\mu\nu}^aA^{b\mu}A^{c\nu}\\
&\quad
-\frac{g^2}{4}f^{abc}f^{ade}
A_\mu^bA_\nu^cA^{d\mu}A^{e\nu}.
\end{aligned}
$$

The first term is the free kinetic term. The second and third terms are cubic and quartic gauge-boson interactions. They are not optional add-ons; they are forced by gauge covariance of the curvature.

For an Abelian group all structure constants vanish, so these self-interactions are absent in the Maxwell kinetic term.

## Pure gauge and flat connections

A connection obtained by gauge-transforming the zero connection is called pure gauge. In this convention it has the form

$$
A=-\frac{i}{g}G^{-1}dG.
$$

Its curvature vanishes:

$$
F=dA+igA\wedge A=0.
$$

This can be checked directly using the Maurer–Cartan identity, or more conceptually by noting that $F=0$ for $A=0$ and curvature transforms covariantly.

Locally, on a simply connected patch, $F=0$ means the connection is pure gauge. Globally, the story is subtler. On a space with noncontractible loops or excluded regions, a flat connection can have nontrivial holonomy. The Aharonov–Bohm effect is the Abelian warning sign; non-Abelian flat connections are central in finite-volume gauge theory, thermal gauge theory, and topological sectors.

So $F_{\mu\nu}$ is the local curvature, not the complete global gauge-field data.

## Common pitfalls

**Mixing sign conventions.** With $D_\mu=\partial_\mu+igA_\mu$, the non-Abelian component formula has $-gf^{abc}A_\mu^bA_\nu^c$. Do not import the opposite sign from a $D_\mu=\partial_\mu-igA_\mu$ source without translating.

**Calling non-Abelian $F_{\mu\nu}$ gauge invariant.** It is covariant, not invariant: $F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U$. Traces and fully contracted expressions are gauge invariant.

**Forgetting the commutator term.** Several copies of Maxwell theory would have $F^a=dA^a$. Yang–Mills theory has the extra $ig[A_\mu,A_\nu]$ term, and that term is why the gauge bosons carry non-Abelian charge.

**Confusing the Bianchi identity with dynamics.** $DF=0$ is geometric. The Yang–Mills equation $D_\mu F^{\mu\nu}=\text{source}$ comes from varying an action.

**Assuming flat means zero.** Flat means $F=0$. It does not always mean $A_\mu=0$ globally, because holonomies around noncontractible loops can remain.

**Forgetting the representation in a commutator calculation.** The matrix $F_{\mu\nu}=F_{\mu\nu}^aT_R^a$ acts in whatever representation $R$ the covariant derivative acts on. The components $F_{\mu\nu}^a$ are common, but the matrices $T_R^a$ depend on the field.

## Relations to other pages

- [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/) gives the parallel-transport viewpoint that makes curvature natural.
- [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/) derives the connection transformation law from local covariance of matter derivatives.
- [Minimal Coupling](/gauge-theories-standard-model/gauge-principle/minimal-coupling/) uses $D_\mu$ and $F_{\mu\nu}$ to build gauge-invariant matter and gauge-field Lagrangians.
- Later pages on Yang–Mills theory use the cubic and quartic interactions hidden inside $-\frac14F_{\mu\nu}^aF^{a\mu\nu}$.

## Research status

The local formula for field strength as curvature is settled textbook material. It is the basis of Maxwell theory, Yang–Mills theory, QCD, electroweak theory, lattice plaquettes, instanton number, and anomaly formulas.

The subtleties begin when local curvature is not the whole story. Flat connections with nontrivial holonomy, nontrivial bundles, global form of the gauge group, boundary conditions, line-operator spectra, and generalized symmetries all require information beyond the local expression for $F_{\mu\nu}$.

## Exercises

### Exercise 1: Compute the commutator

Starting from

$$
D_\mu=\partial_\mu+igA_\mu,
$$

compute $[D_\mu,D_\nu]\psi$ and show that

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

<details>
<summary><strong>Solution</strong></summary>

Expand both orders:

$$
\begin{aligned}
D_\mu D_\nu\psi
&=
\partial_\mu\partial_\nu\psi
+ig(\partial_\mu A_\nu)\psi
+igA_\nu\partial_\mu\psi
+igA_\mu\partial_\nu\psi
-g^2A_\mu A_\nu\psi,\\
D_\nu D_\mu\psi
&=
\partial_\nu\partial_\mu\psi
+ig(\partial_\nu A_\mu)\psi
+igA_\mu\partial_\nu\psi
+igA_\nu\partial_\mu\psi
-g^2A_\nu A_\mu\psi.
\end{aligned}
$$

Subtracting cancels the ordinary second derivatives and the single-derivative terms, leaving

$$
[D_\mu,D_\nu]\psi
=
ig(\partial_\mu A_\nu-\partial_\nu A_\mu)\psi
-g^2[A_\mu,A_\nu]\psi.
$$

Since $-g^2[A_\mu,A_\nu]=ig\,ig[A_\mu,A_\nu]$, this is

$$
[D_\mu,D_\nu]\psi
=
ig\left(\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu]\right)\psi.
$$

</details>

### Exercise 2: Component sign check

Use $[T^a,T^b]=if^{abc}T^c$ to derive the component formula

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert $A_\mu=A_\mu^aT^a$ into

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu].
$$

The derivative terms give

$$
(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)T^a.
$$

The commutator term gives

$$
igA_\mu^bA_\nu^c[T^b,T^c]
=igA_\mu^bA_\nu^cif^{bca}T^a
=-g f^{abc}A_\mu^bA_\nu^cT^a,
$$

where cyclic antisymmetry was used in the last step. Reading off the coefficient of $T^a$ gives the result.

</details>

### Exercise 3: Curvature transforms covariantly

Assume

$$
D_\mu^U=U^{-1}D_\mu U.
$$

Show that $F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U$.

<details>
<summary><strong>Solution</strong></summary>

Compute the transformed commutator:

$$
[D_\mu^U,D_\nu^U]
=
[U^{-1}D_\mu U,U^{-1}D_\nu U]
=
U^{-1}[D_\mu,D_\nu]U.
$$

Since

$$
[D_\mu^U,D_\nu^U]=igF_{\mu\nu}^U
$$

and

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

we obtain

$$
igF_{\mu\nu}^U=igU^{-1}F_{\mu\nu}U.
$$

Cancel $ig$ to get

$$
F_{\mu\nu}^U=U^{-1}F_{\mu\nu}U.
$$

</details>

### Exercise 4: Bianchi identity from Jacobi

Use the Jacobi identity for $D_\lambda,D_\mu,D_\nu$ to show that

$$
D_\lambda F_{\mu\nu}
+D_\mu F_{\nu\lambda}
+D_\nu F_{\lambda\mu}=0.
$$

<details>
<summary><strong>Solution</strong></summary>

The Jacobi identity says

$$
[D_\lambda,[D_\mu,D_\nu]]
+[D_\mu,[D_\nu,D_\lambda]]
+[D_\nu,[D_\lambda,D_\mu]]=0.
$$

Using

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

this becomes

$$
ig[D_\lambda,F_{\mu\nu}]
+ig[D_\mu,F_{\nu\lambda}]
+ig[D_\nu,F_{\lambda\mu}]=0.
$$

When $F_{\mu\nu}$ acts by multiplication in the adjoint representation,

$$
[D_\lambda,F_{\mu\nu}]=D_\lambda F_{\mu\nu}.
$$

Dividing by $ig$ gives

$$
D_\lambda F_{\mu\nu}
+D_\mu F_{\nu\lambda}
+D_\nu F_{\lambda\mu}=0.
$$

</details>

### Exercise 5: Gauge invariance of the Yang–Mills kinetic term

Show that

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

is gauge invariant if $F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U$.

<details>
<summary><strong>Solution</strong></summary>

Under a gauge transformation,

$$
F_{\mu\nu}F^{\mu\nu}
\mapsto
U^{-1}F_{\mu\nu}UU^{-1}F^{\mu\nu}U
=
U^{-1}F_{\mu\nu}F^{\mu\nu}U.
$$

Taking the trace and using cyclicity,

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

- M. Srednicki, *Quantum Field Theory*, §69, for the non-Abelian field strength from the covariant derivative commutator.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Yang–Mills theory, Wilson lines, and gauge-invariant kinetic terms.
- A. Zee, *Quantum Field Theory in a Nutshell*, Part IV.5, for an intuitive route from gauge fields to non-Abelian curvature.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §15.1, for the systematic construction of non-Abelian gauge invariance and curvature.
- A. M. Polyakov, *Gauge Fields and Strings*, Ch. 1, for the gauge-system viewpoint leading toward Wilson loops, lattice gauge theory, and nonperturbative phases.
- M. Nakahara, *Geometry, Topology and Physics*, for the mathematical language of connections, curvature, Bianchi identities, and characteristic classes.

## Version history

- **2026-06-17:** Initial polished draft for the Gauge Principle and Classical Gauge Theory chapter.
