---
title: "Covariant Derivative in Representations"
description: "Explains how the Yang–Mills covariant derivative acts on matter fields in arbitrary representations, including fundamental, conjugate, adjoint, singlet, and tensor-product representations."
sidebar:
  label: "Covariant Derivative in Representations"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–70; Weinberg Vol. II §§15.1–15.2; Schwartz Ch. 25; Coleman, Aspects of Symmetry, Secret Symmetry."
topics:
  - covariant derivative
  - gauge representations
  - adjoint representation
  - matter fields
  - Yang–Mills theory
canonicalTopics:
  - covariant-derivative-in-representations
  - gauge-representations
  - adjoint-representation
  - conjugate-representation
  - matter-couplings-in-yang-mills
researchStatus:
  established:
    - "The representation-dependent form of the Yang–Mills covariant derivative is a standard local consequence of gauge covariance."
  active:
    - "Which representations are dynamically allowed or globally genuine can depend on the global form of the gauge group, line operators, anomalies, and boundary conditions."
---

## Summary

A Yang–Mills gauge field is one connection, but every matter field sees that connection through its own representation of the gauge group. If a field $\Psi$ takes values in a representation space $V_R$, then this volume uses

$$
D_\mu^{(R)}\Psi
=
\left(\partial_\mu+igA_\mu^aT_R^a\right)\Psi,
$$

where $T_R^a$ are the Hermitian generators of the Lie algebra in representation $R$:

$$
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

Under a local gauge transformation,

$$
\Psi(x)\mapsto U_R^{-1}(x)\Psi(x),
\qquad
U_R(x)=\exp\{ig\alpha^a(x)T_R^a\},
$$

the covariant derivative transforms the same way:

$$
D_\mu^{(R)}\Psi
\mapsto
U_R^{-1}D_\mu^{(R)}\Psi.
$$

The components $A_\mu^a$ are the same gauge field for the whole theory. What changes from field to field is the matrix $T_R^a$ multiplying them.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A Yang–Mills connection is sent through representation matrices to produce covariant derivatives in the fundamental, conjugate, adjoint, singlet, and tensor-product representations.](/figures/gauge-theories-standard-model/covariant-derivative-representations.svg)

<figcaption>

One gauge connection, many representation matrices. The local components $A_\mu^a$ are shared, but the operator $D_\mu^{(R)}=\partial_\mu+igA_\mu^aT_R^a$ depends on the representation carried by the field.

</figcaption>
</figure>

## Prerequisites

You should have read [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/) and [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/). The main convention to keep in view is

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
\Psi\mapsto U^{-1}\Psi.
$$

You should also be comfortable with matrices acting on internal indices and with the Lie-algebra relation

$$
[T^a,T^b]=if^{abc}T^c.
$$

No deep representation theory is needed here. The page uses only the idea that the same abstract generator can be represented by different matrices on different vector spaces.

## Core idea

The slogan is:

$$
\text{gauge field data} + \text{representation data}
\longrightarrow
\text{covariant derivative for a field}.
$$

The gauge field data are the spacetime one-forms $A_\mu^a(x)$ and the structure constants $f^{abc}$. The representation data are the matrices $T_R^a$ assigned to a particular matter multiplet. Once these are fixed, the covariant derivative is not a guess; it is forced by the demand that derivatives transform like fields.

This is one of the most useful pieces of Yang–Mills theory because it separates two questions that are often muddled:

1. What is the gauge group and connection of the theory?
2. In which representation does this particular field transform?

QCD quarks, QCD gluons, electroweak lepton doublets, Higgs doublets, and singlet right-handed charged leptons all use the same principle. They differ by the representation matrices inserted into $D_\mu$.

## Setup and conventions

Let $G$ be a compact Lie group with Lie algebra $\mathfrak g$. Locally choose Hermitian generators $T^a$ satisfying

$$
[T^a,T^b]=if^{abc}T^c.
$$

A representation $R$ assigns to each generator a matrix $T_R^a$ on a vector space $V_R$:

$$
T^a\longmapsto T_R^a,
\qquad
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

A field in this representation is a spacetime-dependent vector

$$
\Psi(x)\in V_R.
$$

The finite local gauge transformation is

$$
\Psi(x)\mapsto U_R^{-1}(x)\Psi(x),
\qquad
U_R(x)=\exp\{ig\alpha^a(x)T_R^a\}.
$$

The same spacetime functions $\alpha^a(x)$ appear for every representation. What changes is the matrix representation of the abstract generator.

The gauge connection in representation $R$ is

$$
A_\mu^{(R)}(x)=A_\mu^a(x)T_R^a,
$$

and the covariant derivative is

$$
\boxed{
D_\mu^{(R)}
=
\partial_\mu+igA_\mu^aT_R^a.
}
$$

The field strength in representation $R$ is likewise

$$
F_{\mu\nu}^{(R)}=F_{\mu\nu}^aT_R^a,
\qquad
[D_\mu^{(R)},D_\nu^{(R)}]=igF_{\mu\nu}^{(R)}.
$$

This formula is a good sign-checking device. If your $D_\mu$ and $F_{\mu\nu}$ do not satisfy this relation in every representation, one of the signs has escaped the zoo.

## Why the ordinary derivative fails

Start with a matter field transforming as

$$
\Psi\mapsto U_R^{-1}\Psi.
$$

The ordinary derivative transforms as

$$
\partial_\mu\Psi
\mapsto
\partial_\mu(U_R^{-1}\Psi)
=
U_R^{-1}\partial_\mu\Psi
+(\partial_\mu U_R^{-1})\Psi.
$$

The second term is the problem. It is present only because the internal frame depends on $x$. The gauge field is introduced precisely to cancel that term. With

$$
D_\mu^{(R)}=\partial_\mu+igA_\mu^{(R)},
$$

and

$$
A_\mu^{(R)}\mapsto
U_R^{-1}A_\mu^{(R)}U_R
-\frac{i}{g}U_R^{-1}\partial_\mu U_R,
$$

one finds

$$
(D_\mu^{(R)}\Psi)'
=
U_R^{-1}D_\mu^{(R)}\Psi.
$$

So $D_\mu\Psi$ is a field of the same representation type as $\Psi$. That is what the word “covariant” means here.

## Fundamental representation

For $SU(N)$, the fundamental representation $F$ acts on $N$-component columns. The generators are often written

$$
t^a\equiv T_F^a,
\qquad
\operatorname{tr}(t^at^b)=\frac12\delta^{ab}.
$$

A fundamental field $q^i$ may be viewed as a column vector $q$. In this volume's convention,

$$
q\mapsto U_F^{-1}q,
\qquad
D_\mu q=(\partial_\mu+igA_\mu^at^a)q.
$$

For QCD, quarks transform in the fundamental representation of $SU(3)_c$. A quark field carries a color index,

$$
q^i(x),\qquad i=1,2,3,
$$

and the gluon field appears as the matrix

$$
(A_\mu)^i{}_{j}=A_\mu^a(t^a)^i{}_{j}.
$$

The covariant derivative is

$$
(D_\mu q)^i
=
\partial_\mu q^i+igA_\mu^a(t^a)^i{}_{j}q^j.
$$

This formula is the local seed of every quark–gluon vertex.

## Conjugate and dual representations

The conjugate representation is not obtained by putting a minus sign on the coupling by hand. It is obtained by using the conjugate representation matrices.

If $R$ has generators $T_R^a$, then a column transforming in the conjugate representation $\bar R$ uses

$$
T_{\bar R}^a=-(T_R^a)^*,
$$

so that

$$
U_{\bar R}=U_R^*.
$$

For the antifundamental of $SU(N)$,

$$
T_{\bar F}^a=-(t^a)^*.
$$

Thus an antifundamental column $\widetilde q$ has

$$
D_\mu\widetilde q
=
\left(\partial_\mu+igA_\mu^aT_{\bar F}^a\right)\widetilde q
=
\left(\partial_\mu-igA_\mu^a(t^a)^*\right)\widetilde q.
$$

This resembles changing $g\to -g$, but that is not the conceptual rule. The rule is: use the generator appropriate to the representation.

A dual row vector transforms oppositely. If $q\mapsto U_F^{-1}q$, then

$$
q^\dagger\mapsto q^\dagger U_F,
$$

and its covariant derivative is naturally

$$
D_\mu q^\dagger
=
\partial_\mu q^\dagger-igq^\dagger A_\mu^at^a.
$$

This ensures that the singlet contraction obeys the ordinary product rule:

$$
D_\mu(q^\dagger q)
=
\partial_\mu(q^\dagger q).
$$

Gauge indices have manners. Upper, lower, row, column, fundamental, and antifundamental labels are not decoration; they tell $D_\mu$ how to act.

## Adjoint representation

A field in the adjoint representation can be written as a Lie-algebra-valued matrix

$$
X=X^aT^a.
$$

It transforms by conjugation:

$$
X\mapsto U^{-1}XU.
$$

The covariant derivative is then

$$
D_\mu X
=
\partial_\mu X+ig[A_\mu,X].
$$

In components, using $[T^a,T^b]=if^{abc}T^c$, this is

$$
\boxed{
(D_\mu X)^a
=
\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
}
$$

The minus sign in the second term is a direct consequence of this volume's convention $D_\mu=\partial_\mu+igA_\mu$ and $F_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c$.

The gauge field itself is not a tensorial adjoint matter field because $A_\mu$ transforms with an inhomogeneous derivative term. But its curvature is adjoint-valued:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U,
$$

and the covariant derivative of the curvature is

$$
(D_\rho F_{\mu\nu})^a
=
\partial_\rho F_{\mu\nu}^a-gf^{abc}A_\rho^bF_{\mu\nu}^c.
$$

This is why the Yang–Mills equation is written with a covariant derivative rather than an ordinary divergence.

## Singlets

A gauge singlet is a field on which all generators vanish:

$$
T_{\mathbf 1}^a=0.
$$

Therefore

$$
D_\mu^{(\mathbf 1)}=\partial_\mu.
$$

Singlet does not mean “unimportant.” It means the field is neutral under this gauge factor. In the Standard Model, a field can be a singlet under $SU(3)_c$ but not under $SU(2)_L\times U(1)_Y$, or vice versa. For a product gauge group, one must specify the representation under every factor.

## Tensor products and composite fields

If $\Phi\in V_R$ and $\Xi\in V_S$, then a tensor-product field $\Phi\otimes\Xi$ transforms in $R\otimes S$. The generator is

$$
T_{R\otimes S}^a
=
T_R^a\otimes \mathbf 1_S+\mathbf 1_R\otimes T_S^a.
$$

Thus

$$
D_\mu(\Phi\otimes\Xi)
=
(D_\mu\Phi)\otimes\Xi+\Phi\otimes(D_\mu\Xi).
$$

This is just the Leibniz rule, but with internal matrices included. It is how covariant derivatives act on composite operators, Yukawa terms, baryon operators, and tensor representations.

A useful special case is a gauge-invariant contraction. If $I:V_R\otimes V_S\to\mathbb C$ is an invariant tensor, then

$$
I(T_R^a\Phi,\Xi)+I(\Phi,T_S^a\Xi)=0.
$$

Consequently,

$$
D_\mu I(\Phi,\Xi)
=
\partial_\mu I(\Phi,\Xi).
$$

Gauge-invariant operators do not need a gauge connection to compare their internal frames; the invariant tensor has already canceled the gauge transformation.

## Scalars, spinors, and spacetime indices

Gauge representations are independent of Lorentz representations. A scalar multiplet $\phi^i$, a Dirac multiplet $\psi^i$, and a vector multiplet $B_\nu^i$ may all transform in the same internal representation $R$.

In flat spacetime the gauge-covariant derivative acts on the internal index, while ordinary derivatives act on the spacetime dependence:

$$
(D_\mu\phi)^i
=
\partial_\mu\phi^i+igA_\mu^a(T_R^a)^i{}_{j}\phi^j,
$$

$$
(D_\mu\psi)^i
=
\partial_\mu\psi^i+igA_\mu^a(T_R^a)^i{}_{j}\psi^j.
$$

The Dirac index is untouched by $T_R^a$. The gauge generator acts on the internal multiplet index; the gamma matrices act on spinor indices. For a Dirac field,

$$
\mathcal L_\psi
=
\bar\psi(i\gamma^\mu D_\mu^{(R)}-m)\psi,
$$

and the gauge interaction is

$$
\mathcal L_{\bar\psi\psi A}
=
-gA_\mu^a\bar\psi\gamma^\mu T_R^a\psi.
$$

For a scalar multiplet,

$$
\mathcal L_\phi=(D_\mu\phi)^\dagger D^\mu\phi-m^2\phi^\dagger\phi,
$$

and expanding the two covariant derivatives gives one-gauge-boson and two-gauge-boson scalar vertices. The group-theory part of every such vertex is fixed by $T_R^a$ or by products of $T_R^a$.

## Product gauge groups

For a product gauge group

$$
G=G_1\times G_2\times\cdots,
$$

a field carries a representation under each factor. The covariant derivative is the sum of the corresponding connections:

$$
D_\mu
=
\partial_\mu
+i\sum_i g_i A_{\mu,i}^{a_i}T_{R_i}^{a_i}.
$$

For the Standard Model gauge algebra,

$$
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y,
$$

a field may be a color triplet, weak doublet, and hypercharge $Y$ representation all at once. The corresponding covariant derivative contains three terms:

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_c^A
+igW_\mu^aT_L^a
+ig'B_\mu Y.
$$

Here $Y$ is a number on an irreducible hypercharge representation, while $T_c^A$ and $T_L^a$ may be nontrivial matrices. In this volume the electric charge convention is

$$
Q=T_L^3+Y.
$$

## Representation data in interactions

Representation matrices enter perturbation theory in a brutally concrete way. A gauge boson attached to a matter line inserts a generator $T_R^a$ on that matter line.

For a Dirac multiplet in representation $R$, the vertex factor is

$$
\bar\psi\psi A_\mu^a:
\qquad
-ig\gamma^\mu T_R^a.
$$

For a complex scalar multiplet, the one-gauge-boson vertex contains $T_R^a$ and the two-gauge-boson vertex contains products of generators. Loop corrections therefore produce group-theory factors such as

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R,
\qquad
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

These quantities will reappear in QCD, gauge renormalization, anomaly cancellation, and Standard Model field tables.

## Common pitfalls

**Using fundamental generators for every field.** The notation $T^a$ is often overloaded. A quark, an antiquark, a gluon, and a singlet do not all use the same matrices.

**Changing the sign of $g$ instead of changing the representation.** Conjugate representations have conjugate generators. The coupling $g$ belongs to the gauge factor; the sign and matrix structure seen by a field are encoded in $T_R^a$.

**Confusing adjoint matter with the gauge field.** An adjoint scalar transforms homogeneously, $X\mapsto U^{-1}XU$. The connection transforms inhomogeneously. The curvature transforms homogeneously.

**Forgetting tensor-product generators.** If a field carries two indices, the generator acts on both. Invariant tensors cancel these actions only after the correct Leibniz rule has been used.

**Mixing internal and Lorentz indices.** Gauge generators act on internal multiplet indices. Gamma matrices, polarization vectors, and spin connections live in spacetime or spinor structure. The product is simple only when the indices are kept honest.

**Ignoring global form.** Local representation matrices are Lie-algebra data. Whether a representation is allowed as a genuine representation of the global gauge group can depend on quotienting by the center, as in $SU(N)$ versus $SU(N)/\mathbb Z_N$.

## Relations to other pages

This page completes the local matter-coupling part of the Yang–Mills setup. It relies on [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/) for the transformation law and on [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/) for the curvature convention.

The next page, [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/), explains what happens even when no matter representation is present: the Yang–Mills field strength itself contains products of gauge fields.

Later pages use this material repeatedly. QCD uses the fundamental and adjoint representations of $SU(3)_c$. Electroweak theory uses doublets and singlets of $SU(2)_L$ together with hypercharge. Standard Model anomaly cancellation depends delicately on the representation and chirality of every Weyl fermion.

## Research status

The local formulas on this page are established. They are fixed once the gauge algebra, representation, generator normalization, and covariant-derivative sign convention are fixed.

The subtleties begin when local Lie-algebra data are not enough. Global forms of gauge groups, higher-form symmetries, line operators, boundary conditions, anomaly constraints, and nonperturbative sectors can distinguish theories with identical local covariant derivatives. Those issues are not corrections to the formulas above; they are additional data required to define the full quantum theory.

## Exercises

### Exercise 1: Check covariance of the covariant derivative

Let $\Psi\mapsto U_R^{-1}\Psi$ and

$$
A_\mu^{(R)}\mapsto
U_R^{-1}A_\mu^{(R)}U_R-\frac{i}{g}U_R^{-1}\partial_\mu U_R.
$$

Show that $D_\mu^{(R)}\Psi\mapsto U_R^{-1}D_\mu^{(R)}\Psi$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
D_\mu'\Psi'
=
\left(\partial_\mu+igA_\mu'\right)U_R^{-1}\Psi.
$$

Using

$$
A_\mu'=U_R^{-1}A_\mu U_R-\frac{i}{g}U_R^{-1}\partial_\mu U_R,
$$

we get

$$
D_\mu'\Psi'
=(\partial_\mu U_R^{-1})\Psi+U_R^{-1}\partial_\mu\Psi
+igU_R^{-1}A_\mu\Psi
+U_R^{-1}(\partial_\mu U_R)U_R^{-1}\Psi.
$$

Differentiate $U_RU_R^{-1}=1$ to obtain

$$
(\partial_\mu U_R^{-1})=-U_R^{-1}(\partial_\mu U_R)U_R^{-1}.
$$

The two derivative-of-$U_R$ terms cancel, leaving

$$
D_\mu'\Psi'
=U_R^{-1}(\partial_\mu+igA_\mu)\Psi
=U_R^{-1}D_\mu\Psi.
$$

</details>

### Exercise 2: Derive the adjoint component sign

Let $X=X^aT^a$ transform by conjugation. Starting from

$$
D_\mu X=\partial_\mu X+ig[A_\mu,X],
$$

show that

$$
(D_\mu X)^a=\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
[A_\mu,X]
=A_\mu^bX^c[T^b,T^c]
=iA_\mu^bX^cf^{bca}T^a.
$$

Then

$$
ig[A_\mu,X]
=ig\,iA_\mu^bX^cf^{bca}T^a
=-gA_\mu^bX^cf^{bca}T^a.
$$

Since $f^{bca}=f^{abc}$ by cyclicity of the totally antisymmetric structure constants,

$$
D_\mu X
=\left(\partial_\mu X^a-gf^{abc}A_\mu^bX^c\right)T^a.
$$

</details>

### Exercise 3: Gauge invariance of a baryon-like contraction

For $SU(3)$, let $q^i$, $r^j$, and $s^k$ be three fundamental fields. Show that

$$
B=\epsilon_{ijk}q^ir^js^k
$$

is gauge invariant under the local $SU(3)$ transformation, and explain why $D_\mu B=\partial_\mu B$.

<details><summary><strong>Solution</strong></summary>

Under a finite transformation,

$$
q^i\mapsto (U^{-1})^i{}_{i'}q^{i'},
$$

and similarly for $r$ and $s$. Therefore

$$
B\mapsto
\epsilon_{ijk}(U^{-1})^i{}_{i'}(U^{-1})^j{}_{j'}(U^{-1})^k{}_{k'}q^{i'}r^{j'}s^{k'}.
$$

The epsilon tensor transforms with the determinant:

$$
\epsilon_{ijk}(U^{-1})^i{}_{i'}(U^{-1})^j{}_{j'}(U^{-1})^k{}_{k'}
=(\det U^{-1})\epsilon_{i'j'k'}.
$$

For $U\in SU(3)$, $\det U=1$, so $B$ is invariant. Since the invariant tensor $\epsilon_{ijk}$ cancels the three generator actions, the connection terms in the Leibniz rule cancel, and the covariant derivative of the singlet contraction is just the ordinary derivative:

$$
D_\mu B=\partial_\mu B.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§69–70, for non-Abelian gauge theory and group representations in a compact QFT sequence.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.1–15.2, for non-Abelian gauge invariance, covariant derivatives, field strengths, and gauge-theory Lagrangians.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Yang–Mills theory, gauge invariance, Wilson lines, and representation language.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic conceptual discussion of gauge fields and representations in symmetry breaking.
- Zee, *Quantum Field Theory in a Nutshell*, Part IV.5 and the grand-unification chapters, for physical intuition about non-Abelian groups and matter multiplets.

## Version history

- **2026-06-17:** Initial polished draft for the improved Gauge Theories and the Standard Model volume.
