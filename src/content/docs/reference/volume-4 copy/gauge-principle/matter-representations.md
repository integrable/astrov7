---
title: "Matter Representations"
description: "Explains how gauge-group representations determine matter-field transformations, covariant derivatives, charges, allowed invariant terms, and the first group-theory factors used in gauge theories."
sidebar:
  label: "Matter Representations"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–70 and 87–91; Weinberg Vol. II Ch. 15; Schwartz Chs. 25 and 29; Coleman, Aspects of Symmetry, unitary symmetry and secret symmetry."
topics:
  - matter representations
  - covariant derivatives
  - gauge charges
  - Standard Model representations
  - group-theory factors
canonicalTopics:
  - matter-representations
  - gauge-representations
  - covariant-derivative
  - standard-model-field-content
researchStatus:
  established:
    - "For a fixed gauge group and convention for the covariant derivative, the representation of each matter field determines its gauge transformation law, leading gauge coupling, invariant kinetic term, and group-theory factors."
  active:
    - "The global form of the gauge group, line-operator spectrum, anomaly constraints, and generalized-symmetry interpretation of representation data are treated in later chapters."
---

## Summary

A matter field in a gauge theory is not only a scalar, spinor, or tensor under spacetime symmetries. It also lives in a vector space on which the gauge group acts. That vector space is the field's **gauge representation**.

For a gauge group $G$, a representation $R$ assigns matrices $U_R$ to group elements and matrices $T_R^a$ to Lie-algebra generators. In the conventions of this volume,

$$
D_\mu\psi=(\partial_\mu+igA_\mu^aT_R^a)\psi,
\qquad
\psi\mapsto U_R^{-1}\psi.
$$

This small formula carries a lot of physics. It says which gauge bosons couple to the field, with what matrices, with what charge normalization, and which combinations of fields can appear in a gauge-invariant Lagrangian.

The slogan is:

$$
\text{gauge group tells what can rotate; representation tells how a field rotates.}
$$

<figure class="doc-figure" style="--figure-width: 45rem;">

![Representation data determine the matter transformation law, covariant derivative, gauge currents, invariant operators, and anomaly traces.](/figures/gauge-theories-standard-model/representation-data-map.svg)

<figcaption>

A representation $R$ is the bridge between an abstract gauge group $G$ and concrete matter fields. The matrices $T_R^a$ enter the covariant derivative, interaction vertices, invariant tensors, group-theory factors, and anomaly checks.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/), [Gauge Fields as Connections](/gauge-theories-standard-model/gauge-principle/gauge-fields-as-connections/), [Field Strength and Curvature](/gauge-theories-standard-model/gauge-principle/field-strength-and-curvature/), and [Minimal Coupling](/gauge-theories-standard-model/gauge-principle/minimal-coupling/).

The needed mathematics is basic representation theory: matrices acting on vector spaces, tensor products, complex conjugate representations, and traces of generators. The page states the group-theory facts it uses.

## Core idea

A gauge field $A_\mu=A_\mu^aT^a$ is Lie-algebra valued, but the symbol $T^a$ is not a universal matrix. It means “the generator in the representation of the field being acted on.”

For a scalar $\phi$ in a representation $R_\phi$,

$$
D_\mu\phi=(\partial_\mu+igA_\mu^aT_{R_\phi}^a)\phi.
$$

For a Dirac fermion $\psi$ in a possibly different representation $R_\psi$,

$$
D_\mu\psi=(\partial_\mu+igA_\mu^aT_{R_\psi}^a)\psi.
$$

The same gauge bosons appear, but the matrices can differ. A gluon couples to a quark with fundamental $SU(3)$ generators, to another gluon with adjoint generators, and not at all to a color-singlet lepton.

A representation determines four things immediately:

| Data | What it controls |
|---|---|
| Matrices $T_R^a$ | The covariant derivative and matter–gauge-boson vertex. |
| Tensor products involving $R$ | Which masses, potentials, and Yukawa terms are gauge invariant. |
| Trace factors such as $T(R)$ and $C_2(R)$ | Loop coefficients, beta functions, and color factors. |
| Reality type of $R$ | Whether invariant bilinears, Majorana-like masses, or pseudoreal structures may exist. |

Later Standard Model pages are largely bookkeeping pages for this data. The bookkeeping is not optional. The fact that quarks are color triplets, weak doublets or singlets, and carry carefully chosen hypercharges is what makes the Standard Model a gauge theory rather than a list of particles.

## Setup and conventions

Let $G$ be a compact gauge group, and let $\mathfrak g$ be its Lie algebra. We choose Hermitian generators satisfying

$$
[T^a,T^b]=if^{abc}T^c.
$$

A representation $R$ assigns to each generator a matrix $T_R^a$ acting on a vector space $V_R$:

$$
T^a\longmapsto T_R^a\in \operatorname{End}(V_R),
\qquad
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

A field in $R$ has components

$$
\psi^i(x),\qquad i=1,\ldots,\dim R,
$$

and the gauge transformation is

$$
\psi(x)\mapsto U_R^{-1}(x)\psi(x),
\qquad
U_R(x)=\exp\{ig\alpha^a(x)T_R^a\}.
$$

With the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a,
$$

the covariant derivative transforms in the same representation:

$$
D_\mu\psi\mapsto U_R^{-1}D_\mu\psi.
$$

This covariance is the real content of the notation $D_\mu$. It is why the kinetic terms

$$
(D_\mu\phi)^\dagger D^\mu\phi
$$

and

$$
\bar\psi i\gamma^\mu D_\mu\psi
$$

are gauge invariant when the inner products on the representation spaces are invariant.

:::note[The representation is part of the field definition]
Writing “a scalar field” is incomplete in a gauge theory. One must say whether it is a singlet, fundamental, adjoint, doublet, triplet, or some other representation. Spacetime spin and gauge representation are independent labels.
:::

## Abelian representations are charges

For $G=U(1)$, every irreducible complex representation is one-dimensional. The representation is specified by a charge $q$:

$$
\psi\mapsto e^{-iq\alpha(x)}\psi,
\qquad
D_\mu\psi=(\partial_\mu+iqA_\mu)\psi.
$$

The generator is just the number $q/g$ if one writes the coupling separately, or simply the charge $q$ in the Abelian convention

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

A neutral field has $q=0$, so $D_\mu=\partial_\mu$. The complex conjugate field has the opposite charge:

$$
\psi^*\mapsto e^{+iq\alpha(x)}\psi^*.
$$

Thus $\psi^*$ belongs to the conjugate representation. In Abelian language, the conjugate representation is just charge $-q$.

This gives the first simple selection rule: a monomial is $U(1)$ gauge invariant only if the total charge is zero. For example,

$$
\psi_1\psi_2\psi_3
$$

can appear without additional charged fields only if

$$
q_1+q_2+q_3=0.
$$

For QED, a particle of electric charge $Qe$ has

$$
D_\mu=\partial_\mu+ieQA_\mu,
$$

where $e>0$ and $Q$ is measured in proton-charge units. The electron has $Q=-1$, so

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e.
$$

The statement “the electron has charge $-e$” is therefore representation theory for $U(1)$.

## Non-Abelian representations

For a non-Abelian group, the representation matrices do not all commute. The same Lie algebra can act on many different vector spaces.

The most common representations are:

| Representation | Meaning | Example |
|---|---|---|
| Singlet | $T_R^a=0$ for all $a$ | A field neutral under that gauge factor. |
| Fundamental | The defining representation | $SU(3)$ color triplet quark, $SU(2)$ weak doublet. |
| Antifundamental | Complex conjugate of the fundamental | $SU(3)$ antitriplet. |
| Adjoint | The Lie algebra acting on itself | Gauge bosons, ghosts, adjoint scalars. |
| Tensor representations | Built from products of fundamentals and antifundamentals | Symmetric, antisymmetric, and higher representations. |

In the fundamental representation of $SU(N)$, a field can be written as a column vector

$$
\psi^i,
\qquad i=1,\ldots,N.
$$

The generators are $N\times N$ traceless Hermitian matrices normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

For $SU(2)$ doublets,

$$
T^I=\frac{\tau^I}{2},
$$

where $\tau^I$ are the Pauli matrices. For $SU(3)$ color triplets,

$$
T^A=\frac{\lambda^A}{2},
$$

where $\lambda^A$ are the Gell-Mann matrices.

### Fundamental and antifundamental fields

If $\psi^i$ is in the fundamental of $SU(N)$, then

$$
\psi\mapsto U^{-1}\psi.
$$

Its Hermitian conjugate transforms as

$$
\psi^\dagger\mapsto \psi^\dagger U.
$$

A field in the antifundamental representation can be written with a lower or barred index, depending on notation. The important point is that it transforms with the complex conjugate representation. For $SU(N)$ with $N\geq 3$, the fundamental and antifundamental are inequivalent complex representations.

This distinction matters. In color $SU(3)$, a quark is a $\mathbf 3$, an antiquark is a $\bar{\mathbf 3}$, and a color-singlet meson uses the invariant contraction

$$
\bar q_i q^i.
$$

### The adjoint representation

The adjoint representation is the representation in which the Lie algebra acts on itself. Its vector space has dimension

$$
\dim G.
$$

Using components $X=X^aT^a$, the adjoint action is

$$
X\mapsto U^{-1}XU.
$$

The adjoint generators can be represented by matrices

$$
(T_{\mathrm{adj}}^a)_{bc}=-if^{abc}
$$

up to equivalent index conventions. Gauge fields transform inhomogeneously as connections, not simply as adjoint matter fields, but the field strength transforms covariantly in the adjoint:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

That is why traces such as

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

are gauge invariant.

## Representation invariants and allowed terms

Gauge-invariant terms are singlets. More precisely, a product of fields can appear in the Lagrangian only if the tensor product of their representations contains the trivial representation.

This rule explains many familiar terms.

For a complex scalar $\phi$ in a unitary representation $R$,

$$
\phi^\dagger\phi
$$

is a singlet because $R^*\otimes R$ contains the trivial representation. Therefore the mass term

$$
-m^2\phi^\dagger\phi
$$

is gauge invariant.

For a Dirac fermion whose left- and right-handed components transform in the same representation, the Dirac mass term

$$
-m\bar\psi\psi
$$

is gauge invariant. In a chiral gauge theory, the left- and right-handed fields can transform differently. Then a bare Dirac mass may be forbidden by gauge symmetry.

This is exactly what happens in the electroweak theory before symmetry breaking. The electron mass term is not simply present from the start. It is generated by a Yukawa coupling involving the Higgs doublet.

### Tensor-product test

Suppose fields $\psi_1,\psi_2,\ldots,\psi_n$ transform in representations $R_1,R_2,\ldots,R_n$. A local product can be made gauge invariant only if

$$
R_1\otimes R_2\otimes\cdots\otimes R_n
$$

contains a singlet, possibly after using conjugate fields and invariant tensors such as $\delta^i{}_j$, $\epsilon_{ij}$, or $\epsilon_{ijk}$.

Examples:

$$
\mathbf N^*\otimes\mathbf N\supset \mathbf 1
\qquad\text{for }SU(N),
$$

so $\phi^\dagger\phi$ is invariant for a fundamental scalar.

For $SU(2)$,

$$
\mathbf 2\otimes\mathbf 2=\mathbf 1\oplus\mathbf 3,
$$

so two doublets can form a singlet using the antisymmetric tensor $\epsilon_{ij}$.

For $SU(3)$,

$$
\mathbf 3\otimes\mathbf 3\otimes\mathbf 3\supset\mathbf 1,
$$

with singlet contraction $\epsilon_{ijk}q^iq^jq^k$. This is the color structure behind baryon operators.

## Group-theory factors

Loop calculations and beta functions depend on a few representation invariants. The most common are the Dynkin index $T(R)$ and quadratic Casimir $C_2(R)$, defined by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
$$

and

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

Taking the trace of the second equation gives

$$
C_2(R)d_R=T(R)d_G,
$$

where

$$
d_R=\dim R,
\qquad
d_G=\dim G.
$$

For $SU(N)$ with the fundamental normalization $\operatorname{tr}(T^aT^b)=\delta^{ab}/2$,

| Representation | Dimension | $T(R)$ | $C_2(R)$ |
|---|---:|---:|---:|
| Fundamental $\mathbf N$ | $N$ | $1/2$ | $(N^2-1)/(2N)$ |
| Antifundamental $\bar{\mathbf N}$ | $N$ | $1/2$ | $(N^2-1)/(2N)$ |
| Adjoint | $N^2-1$ | $N$ | $N$ |

For QCD, these become

$$
C_F=\frac43,
\qquad
C_A=3,
\qquad
T_F=\frac12.
$$

These numbers appear everywhere in perturbative gauge theory. They are not mysterious coefficients produced by Feynman diagrams; they are traces of representation matrices.

## Product gauge groups

Many important gauge groups are products. If

$$
G=G_1\times G_2\times\cdots\times G_k,
$$

then a matter representation is a tuple

$$
R=(R_1,R_2,\ldots,R_k).
$$

The covariant derivative is a sum of contributions from each factor:

$$
D_\mu
=
\partial_\mu
+i\sum_{r=1}^k g_r A_{r\mu}^{a_r}T_{R_r}^{a_r}.
$$

If a field is a singlet under one factor, the corresponding generator is zero on that field.

For the Standard Model gauge algebra, using the local product notation,

$$
SU(3)_c\times SU(2)_L\times U(1)_Y,
$$

a field is usually labelled by

$$
(R_3,R_2)_Y.
$$

The covariant derivative is

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_{R_3}^A
+igW_\mu^IT_{R_2}^I
+ig'YB_\mu.
$$

The electric charge convention in this volume is

$$
Q=T^3+Y.
$$

One generation of minimal Standard Model matter can be summarized as follows, using right-handed fermion fields rather than left-handed conjugates:

| Field | Representation | Electric charges of components |
|---|---|---|
| $Q_L=(u_L,d_L)$ | $(\mathbf 3,\mathbf 2)_{1/6}$ | $+2/3$, $-1/3$ |
| $u_R$ | $(\mathbf 3,\mathbf 1)_{2/3}$ | $+2/3$ |
| $d_R$ | $(\mathbf 3,\mathbf 1)_{-1/3}$ | $-1/3$ |
| $L_L=(\nu_L,e_L)$ | $(\mathbf 1,\mathbf 2)_{-1/2}$ | $0$, $-1$ |
| $e_R$ | $(\mathbf 1,\mathbf 1)_{-1}$ | $-1$ |
| $H=(H^+,H^0)$ | $(\mathbf 1,\mathbf 2)_{1/2}$ | $+1$, $0$ |

This table is not merely taxonomy. It determines the allowed kinetic terms, Yukawa couplings, gauge vertices, anomaly sums, and the pattern of electroweak symmetry breaking.

:::caution[Right-handed fields versus left-handed conjugates]
Some Standard Model tables list only left-handed Weyl fields. Then $u_R$ is replaced by the left-handed conjugate $u^c$, which transforms as $(\bar{\mathbf 3},\mathbf 1)_{-2/3}$. Both notations describe the same particles, but the representation labels differ because conjugation changes gauge charges.
:::

## Gauge currents from representations

The matter current coupled to a gauge field contains the representation matrix. For a Dirac fermion in representation $R$,

$$
\mathcal L_\psi=\bar\psi(i\gamma^\mu D_\mu-m)\psi
$$

expands as

$$
\mathcal L_\psi
=
\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-gA_\mu^a\bar\psi\gamma^\mu T_R^a\psi.
$$

Thus the current is

$$
j^{a\mu}=\bar\psi\gamma^\mu T_R^a\psi
$$

with the interaction term $-gA_\mu^aj^{a\mu}$ in these conventions.

For a scalar, the current has the same representation matrices but also contains derivative terms. Schematically,

$$
j^{a\mu}_\phi
\sim
 i\phi^\dagger T_R^a\overleftrightarrow{D^\mu}\phi,
$$

with the precise placement of $D_\mu$ chosen so that the expression is Hermitian and gauge covariant.

The important point is representation-theoretic: the gauge boson sees the matrix $T_R^a$ carried by the matter field. Different representations produce different charge factors even when the spacetime spin is the same.

## Real, complex, and pseudoreal representations

Representations can be classified by their relation to their complex conjugates.

A representation is **real** if it is equivalent to its conjugate by a symmetric invariant structure. The adjoint representation of a compact Lie group is real.

A representation is **pseudoreal** if it is equivalent to its conjugate by an antisymmetric invariant structure. The fundamental doublet of $SU(2)$ is pseudoreal.

A representation is **complex** if it is not equivalent to its conjugate. The fundamental $\mathbf 3$ of $SU(3)$ is complex.

This distinction affects what invariant bilinears exist. It also affects chiral gauge theories. Fermions in complex representations can produce gauge anomalies unless the full set of chiral matter fields cancels them. Pseudoreal representations have their own global anomaly subtleties, most famously the $SU(2)$ global anomaly.

These topics belong to the Standard Model anomaly chapter, but the warning starts here: in a chiral gauge theory, representation data is constrained by quantum consistency.

## The center and the global form warning

The local Lie algebra does not always determine the full gauge group. For example, the Lie algebra $\mathfrak{su}(N)$ is shared by $SU(N)$ and $SU(N)/\mathbb Z_N$. Which group is meant can affect allowed line operators and bundles.

Matter representations are part of this choice. If all dynamical fields transform in the adjoint representation, then the center of $SU(N)$ acts trivially on all local fields. In such a theory, the effective global form of the gauge group may be closer to $SU(N)/\mathbb Z_N$ than to $SU(N)$, depending on the line operators and bundles allowed.

This page mostly uses local representation theory. Later pages on global form, center symmetry, Wilson loops, and confinement explain why this warning is not a footnote in nonperturbative gauge theory.

## Common pitfalls

**Confusing gauge group with representation.** Saying “the field is $SU(3)$” is sloppy. The field is in a representation of $SU(3)$, such as $\mathbf 3$, $\bar{\mathbf 3}$, $\mathbf 8$, or $\mathbf 1$.

**Forgetting that $T^a$ depends on the field.** In $D_\mu=\partial_\mu+igA_\mu^aT^a$, the matrices $T^a$ are in the representation of the field being differentiated. A quark, gluon, Higgs, and lepton do not all see the same matrix.

**Treating charge normalization as convention-free.** For one $U(1)$ factor, rescaling the generator and inverse-rescaling the coupling can leave physics unchanged. Once multiple fields, embeddings, unification conventions, or anomaly coefficients are discussed, the normalization must be stated.

**Ignoring conjugate representations.** For $SU(N\geq 3)$, $\mathbf N$ and $\bar{\mathbf N}$ are inequivalent. This matters for arrows in color flow, Yukawa terms, baryon operators, and anomaly calculations.

**Assuming every allowed term is present.** Gauge invariance says what is allowed, not what must appear. Additional global symmetries, discrete symmetries, EFT power counting, or model assumptions may forbid terms that gauge symmetry would allow.

**Assuming local Lie-algebra data fixes all physics.** The representation matrices determine local couplings. The global form of the gauge group and the spectrum of line operators require more information.

## Relations to other pages

[Minimal Coupling](/gauge-theories-standard-model/gauge-principle/minimal-coupling/) explains why the covariant derivative is the leading interaction with a gauge field. This page explains what matrix appears in that derivative.

The QED chapter specializes this page to $U(1)$ charge. The Yang–Mills chapter develops the non-Abelian representations and their gauge-boson self-interactions. The Standard Model field-content page will use the notation $(R_3,R_2)_Y$ throughout.

The anomaly chapter uses representation traces to decide whether a chiral gauge theory is quantum mechanically consistent. The Wilson-loop and center-symmetry pages use representation data to classify line operators and confinement diagnostics.

## Research status

The local representation theory used on this page is established textbook material. The open-ended parts are not the matrices themselves but how representation data interacts with global structure, generalized symmetries, anomaly constraints, nonperturbative sectors, and dual descriptions.

In modern language, representations label not only fields but also possible charged operators. Which charged operators are genuine, which require attached topological surfaces, and which are screened by dynamical matter are global questions. They become central in the chapters on Wilson loops, confinement, generalized symmetries, and Standard Model consistency.

## Exercises

### Exercise 1: Covariance of the covariant derivative

Let

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
\psi\mapsto U^{-1}\psi,
$$

and

$$
A_\mu\mapsto A_\mu^U=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

Show that

$$
D_\mu^U\psi^U=U^{-1}D_\mu\psi.
$$

<details><summary><strong>Solution</strong></summary>

Start with

$$
D_\mu^U\psi^U
=
(\partial_\mu+igA_\mu^U)(U^{-1}\psi).
$$

The derivative term gives

$$
\partial_\mu(U^{-1}\psi)=(\partial_\mu U^{-1})\psi+U^{-1}\partial_\mu\psi.
$$

The gauge-field term gives

$$
ig\left(U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U\right)U^{-1}\psi
=
igU^{-1}A_\mu\psi+U^{-1}(\partial_\mu U)U^{-1}\psi.
$$

Use

$$
\partial_\mu U^{-1}=-U^{-1}(\partial_\mu U)U^{-1}
$$

to cancel the two terms involving $\partial_\mu U$. The result is

$$
D_\mu^U\psi^U
=
U^{-1}\partial_\mu\psi+igU^{-1}A_\mu\psi
=
U^{-1}D_\mu\psi.
$$

</details>

### Exercise 2: The Casimir-index identity

Using

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
\qquad
T_R^aT_R^a=C_2(R)\mathbf 1_R,
$$

show that

$$
C_2(R)d_R=T(R)d_G.
$$

<details><summary><strong>Solution</strong></summary>

Take the trace of the second equation over the representation space $V_R$:

$$
\operatorname{tr}_R(T_R^aT_R^a)=C_2(R)\operatorname{tr}_R\mathbf 1_R=C_2(R)d_R.
$$

Now use the first equation and sum over $a$:

$$
\operatorname{tr}_R(T_R^aT_R^a)=T(R)\delta^{aa}=T(R)d_G.
$$

Equating the two expressions gives

$$
C_2(R)d_R=T(R)d_G.
$$

</details>

### Exercise 3: Standard Model electric charges

Using $Q=T^3+Y$, check the electric charges of the components of

$$
Q_L=(u_L,d_L)\sim(\mathbf 3,\mathbf 2)_{1/6},
\qquad
L_L=(\nu_L,e_L)\sim(\mathbf 1,\mathbf 2)_{-1/2},
\qquad
H=(H^+,H^0)\sim(\mathbf 1,\mathbf 2)_{1/2}.
$$

<details><summary><strong>Solution</strong></summary>

For an $SU(2)$ doublet, the upper component has $T^3=+1/2$ and the lower component has $T^3=-1/2$.

For $Q_L$ with $Y=1/6$,

$$
Q(u_L)=\frac12+\frac16=\frac23,
\qquad
Q(d_L)=-\frac12+\frac16=-\frac13.
$$

For $L_L$ with $Y=-1/2$,

$$
Q(\nu_L)=\frac12-\frac12=0,
\qquad
Q(e_L)=-\frac12-\frac12=-1.
$$

For $H$ with $Y=1/2$,

$$
Q(H^+)=\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

</details>

### Exercise 4: Hypercharge in Yukawa terms

Using the right-handed-field notation in the table, check that the Standard Model Yukawa structures

$$
\bar Q_L H d_R,
\qquad
\bar Q_L\widetilde H u_R,
\qquad
\bar L_L H e_R,
$$

are neutral under $U(1)_Y$, where

$$
\widetilde H=i\tau^2H^*
$$

has hypercharge $-1/2$.

<details><summary><strong>Solution</strong></summary>

The conjugate $\bar Q_L$ carries hypercharge $-1/6$. Therefore

$$
Y(\bar Q_L H d_R)
=-\frac16+\frac12-\frac13=0.
$$

For the up-type term, $\widetilde H$ has $Y=-1/2$, so

$$
Y(\bar Q_L\widetilde H u_R)
=-\frac16-\frac12+\frac23=0.
$$

For the charged-lepton term, $\bar L_L$ carries $Y=+1/2$, so

$$
Y(\bar L_L H e_R)
=\frac12+\frac12-1=0.
$$

The non-Abelian singlet contractions also work: color is contracted between $\bar Q_L$ and the quark singlet, and weak $SU(2)$ indices are contracted between the doublets.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§69–70, for non-Abelian gauge theory and group representations in a perturbative QFT setting.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for gauge invariance, Lie-algebra structure, and representation-dependent couplings.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25 and 29, for Yang–Mills theory and the Standard Model representation assignments.
- Coleman, *Aspects of Symmetry*, “An Introduction to Unitary Symmetry” and “Secret Symmetry,” for classic representation-theory and gauge-theory perspective.
- Georgi, *Lie Algebras in Particle Physics*, for a dedicated treatment of representation theory used in particle physics.

## Version history

- **2026-06-17:** Initial polished draft, aligned with the volume convention $D_\mu=\partial_\mu+igA_\mu^aT_R^a$ and $Q=T^3+Y$.
