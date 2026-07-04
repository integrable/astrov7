---
title: "SL(2,C) and the Lorentz Group"
description: "A QFT-oriented guide to the double cover SL(2,C) of the proper orthochronous Lorentz group, Weyl spinors, Lorentz algebra, and finite-dimensional Lorentz representations."
sidebar:
  label: "SL(2,C) and Lorentz"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard Lorentz and spinor representation references, including Weinberg, Srednicki, Coleman, Schwartz, Zee, Tung, Cornwell, Hall, and representation-theory texts."
topics:
  - Lorentz group
  - SL(2,C)
  - Weyl spinors
  - Lorentz algebra
  - finite-dimensional representations
  - dotted and undotted indices
canonicalTopics:
  - lorentz-group
  - sl2c
  - weyl-spinors
  - lorentz-algebra
  - finite-dimensional-lorentz-representations
  - dotted-undotted-spinors
researchStatus:
  established:
    - "The relation between SL(2,C), the proper orthochronous Lorentz group, Weyl spinors, and finite-dimensional Lorentz representations is standard and foundational for relativistic QFT."
  active:
    - "Modern work extends this representation theory through spinor-helicity variables, conformal representations, celestial bases, higher-spin structures, and categorical or geometric treatments of spacetime symmetry."
---

## Summary

The connected Lorentz group in $3+1$ dimensions is not best understood directly through $4\times4$ matrices. For spinors, the natural object is its double cover:

$$
SL(2,\mathbb C).
$$

There is a two-to-one map

$$
SL(2,\mathbb C)\longrightarrow SO^+(1,3),
$$

where $SO^+(1,3)$ is the proper orthochronous Lorentz group: determinant $+1$ and preserving the time orientation. The kernel is

$$
\{+\mathbf 1,-\mathbf 1\}.
$$

The practical construction uses the fact that a Minkowski vector can be packaged as a $2\times2$ Hermitian matrix:

$$
X(x)=x^0\mathbf 1+\mathbf x\cdot\boldsymbol\sigma.
$$

Then

$$
\det X(x)=(x^0)^2-\mathbf x^2=x^2.
$$

For $A\in SL(2,\mathbb C)$,

$$
X(x)\mapsto X'(x)=AX(x)A^\dagger
$$

preserves the determinant and therefore preserves the Minkowski norm.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Concept diagram showing SL(2,C), Hermitian matrices representing Minkowski vectors, the map to the proper orthochronous Lorentz group, the kernel plus and minus identity, Weyl spinors, four-vectors, and the two commuting su(2) algebras after complexification.](/figures/math-toolkit/sl2c-lorentz-double-cover.svg)

<figcaption>

The double cover $SL(2,\mathbb C)\to SO^+(1,3)$ is built from the action $X\mapsto AXA^\dagger$ on Hermitian matrices. After complexifying the Lorentz algebra, the combinations $L_i=(J_i-iK_i)/2$ and $R_i=(J_i+iK_i)/2$ generate two commuting $\mathfrak{su}(2)$-type algebras, giving finite-dimensional labels $(j_L,j_R)$.

</figcaption>
</figure>

This page is the bridge from compact angular momentum to relativistic spin. $SU(2)$ tells us what spin-$j$ means. $SL(2,\mathbb C)$ tells us why relativistic fields carry labels such as

$$
(0,0),
\qquad
\left(\frac12,0\right),
\qquad
\left(0,\frac12\right),
\qquad
\left(\frac12,\frac12\right).
$$

Those labels are the grammar of scalar fields, Weyl spinors, Dirac spinors, vectors, field strengths, and eventually amplitudes.

## Prerequisites

You should know [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/), especially spin-$j$ representations, ladder operators, tensor products, and the distinction between $SU(2)$ and $SO(3)$.

You should also know [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/) for the relation between groups, Lie algebras, exponentials, global covers, and compact versus noncompact groups.

The metric convention follows [Mathematical Conventions](/math-toolkit/conventions/):

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

Thus

$$
x^2=(x^0)^2-\mathbf x^2.
$$

## Core idea

A Lorentz transformation is a linear transformation of Minkowski space preserving

$$
x^2=(x^0)^2-\mathbf x^2.
$$

Vectors see $4\times4$ Lorentz matrices. Spinors see $2\times2$ complex matrices.

The miracle is that every vector $x^\mu$ can be encoded by a Hermitian matrix

$$
X(x)=x^0\mathbf 1+x^i\sigma_i.
$$

The determinant is the Minkowski norm:

$$
\det X(x)=x^2.
$$

If $A\in SL(2,\mathbb C)$, then

$$
X\mapsto AXA^\dagger
$$

maps Hermitian matrices to Hermitian matrices and preserves the determinant:

$$
\det(AXA^\dagger)=\det A\det X\det A^\dagger=\det X.
$$

Therefore this transformation induces a Lorentz transformation on $x^\mu$.

The same $A$ and $-A$ produce the same Lorentz transformation, so $SL(2,\mathbb C)$ is a double cover of $SO^+(1,3)$.

The second core idea is algebraic. The Lorentz algebra has rotation generators $J_i$ and boost generators $K_i$ satisfying

$$
[J_i,J_j]=i\epsilon_{ijk}J_k,
$$

$$
[J_i,K_j]=i\epsilon_{ijk}K_k,
$$

$$
[K_i,K_j]=-i\epsilon_{ijk}J_k.
$$

After complexifying the algebra, define

$$
L_i=\frac12(J_i-iK_i),
\qquad
R_i=\frac12(J_i+iK_i).
$$

Then

$$
[L_i,L_j]=i\epsilon_{ijk}L_k,
\qquad
[R_i,R_j]=i\epsilon_{ijk}R_k,
\qquad
[L_i,R_j]=0.
$$

So finite-dimensional complex Lorentz representations are built from two copies of $SU(2)$ representation theory. Their labels are

$$
(j_L,j_R).
$$

## Setup and conventions

Greek indices run over spacetime components:

$$
\mu,\nu=0,1,2,3.
$$

Spatial indices run over

$$
i,j,k=1,2,3.
$$

The Pauli matrices are

$$
\sigma_1=\begin{pmatrix}0&1\\1&0\end{pmatrix},
\qquad
\sigma_2=\begin{pmatrix}0&-i\\i&0\end{pmatrix},
\qquad
\sigma_3=\begin{pmatrix}1&0\\0&-1\end{pmatrix}.
$$

We use

$$
\sigma^\mu=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^i).
$$

They satisfy

$$
\sigma^\mu\bar\sigma^\nu+\sigma^\nu\bar\sigma^\mu=2\eta^{\mu\nu}\mathbf 1,
$$

and similarly with $\sigma$ and $\bar\sigma$ exchanged.

To make the determinant construction explicit, this page writes

$$
X(x)=x^0\mathbf 1+x^i\sigma_i.
$$

Equivalently, with $x_\mu=(x^0,-\mathbf x)$,

$$
X(x)=x_\mu\bar\sigma^\mu.
$$

The determinant is

$$
\det\left(x^0\mathbf 1+\mathbf x\cdot\boldsymbol\sigma\right)
=(x^0)^2-\mathbf x^2.
$$

A Lorentz transformation is represented on vectors by a real matrix $\Lambda^\mu{}_{\nu}$ satisfying

$$
\eta_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}=\eta_{\mu\nu}.
$$

The proper orthochronous subgroup is

$$
SO^+(1,3)=\{\Lambda\in O(1,3):\det\Lambda=1,\ \Lambda^0{}_0\ge1\}.
$$

The plus sign means connected to the identity. This page focuses on this connected component. Parity and time reversal are important in QFT, but they are discrete transformations outside $SO^+(1,3)$.

## From Hermitian matrices to Lorentz transformations

Every Hermitian $2\times2$ matrix can be written uniquely as

$$
X=x^0\mathbf 1+x^i\sigma_i
$$

with real $x^\mu$.

For

$$
A\in SL(2,\mathbb C),
\qquad
\det A=1,
$$

define

$$
X'=AXA^\dagger.
$$

Since $X^\dagger=X$,

$$
(X')^\dagger=(AXA^\dagger)^\dagger=AXA^\dagger=X'.
$$

So $X'$ is again Hermitian, and hence corresponds to a unique vector $x'^\mu$:

$$
X'=x'^0\mathbf 1+x'^i\sigma_i.
$$

The determinant is preserved:

$$
\det X'
=\det A\det X\det A^\dagger
=\det X.
$$

Since $\det X=x^2$, this gives

$$
x'^2=x^2.
$$

Thus $x'^\mu=\Lambda(A)^\mu{}_{\nu}x^\nu$ for some Lorentz transformation $\Lambda(A)$.

The map

$$
A\mapsto \Lambda(A)
$$

is a group homomorphism:

$$
\Lambda(A_1A_2)=\Lambda(A_1)\Lambda(A_2).
$$

Indeed,

$$
X\mapsto A_2XA_2^\dagger
\mapsto A_1A_2X A_2^\dagger A_1^\dagger
=(A_1A_2)X(A_1A_2)^\dagger.
$$

The image is $SO^+(1,3)$, and the kernel is

$$
\ker\Lambda=\{\mathbf 1,-\mathbf 1\}.
$$

Therefore

$$
SO^+(1,3)\cong SL(2,\mathbb C)/\mathbb Z_2.
$$

This is the Lorentzian analogue of

$$
SO(3)\cong SU(2)/\mathbb Z_2.
$$

The difference is that $SL(2,\mathbb C)$ is noncompact, because boosts are noncompact.

## Rotations and boosts inside SL(2,C)

The compact subgroup $SU(2)\subset SL(2,\mathbb C)$ corresponds to spatial rotations.

Take

$$
A=\exp\left(-\frac{i}{2}\theta_i\sigma_i\right)\in SU(2).
$$

Then

$$
X\mapsto AXA^\dagger=AXA^{-1}
$$

rotates the spatial vector $\mathbf x$ while leaving $x^0$ unchanged.

Boosts are represented by Hermitian, nonunitary matrices. For a boost of rapidity $\varphi$ in the $3$-direction, take

$$
A=\exp\left(\frac{\varphi}{2}\sigma_3\right).
$$

Then

$$
A=\begin{pmatrix}e^{\varphi/2}&0\\0&e^{-\varphi/2}\end{pmatrix}.
$$

Applying $X\mapsto AXA^\dagger$ gives

$$
x'^0=x^0\cosh\varphi+x^3\sinh\varphi,
$$

$$
x'^3=x^3\cosh\varphi+x^0\sinh\varphi,
$$

with $x^1$ and $x^2$ unchanged. The hyperbolic functions are the tell: boosts are not compact rotations with imaginary angles in a unitary finite-dimensional representation. They are noncompact transformations.

## The Lorentz algebra

The Lorentz algebra is generated by rotations $J_i$ and boosts $K_i$. With Hermitian generators in physics convention,

$$
[J_i,J_j]=i\epsilon_{ijk}J_k,
$$

$$
[J_i,K_j]=i\epsilon_{ijk}K_k,
$$

$$
[K_i,K_j]=-i\epsilon_{ijk}J_k.
$$

The minus sign in the last commutator is the algebraic shadow of the Lorentzian metric. Boosts do not form another compact rotation algebra by themselves.

One way to remember the algebra is to write the antisymmetric Lorentz generators $M_{\mu\nu}=-M_{\nu\mu}$ and define

$$
J_i=\frac12\epsilon_{ijk}M_{jk},
\qquad
K_i=M_{0i}.
$$

The Lorentz algebra in covariant notation is

$$
[M_{\mu\nu},M_{\rho\sigma}]
=i\left(
\eta_{\nu\rho}M_{\mu\sigma}
-\eta_{\mu\rho}M_{\nu\sigma}
-\eta_{\nu\sigma}M_{\mu\rho}
+\eta_{\mu\sigma}M_{\nu\rho}
\right),
$$

with the mostly-minus metric. Different sign conventions for $M_{\mu\nu}$ or for the exponential of finite transformations can move signs around. The $J,K$ algebra above fixes the convention used on this page.

## Two commuting SU(2)-type algebras

The finite-dimensional complex representation theory becomes transparent after complexifying the Lorentz algebra. Define

$$
L_i=\frac12(J_i-iK_i),
\qquad
R_i=\frac12(J_i+iK_i).
$$

A direct computation gives

$$
[L_i,L_j]=i\epsilon_{ijk}L_k,
$$

$$
[R_i,R_j]=i\epsilon_{ijk}R_k,
$$

$$
[L_i,R_j]=0.
$$

Thus the complexified Lorentz algebra decomposes as

$$
\mathfrak{so}(1,3)_\mathbb C
\cong
\mathfrak{sl}(2,\mathbb C)\oplus\mathfrak{sl}(2,\mathbb C),
$$

or, in compact-rotation notation,

$$
\mathfrak{so}(1,3)_\mathbb C
\cong
\mathfrak{su}(2)_\mathbb C\oplus\mathfrak{su}(2)_\mathbb C.
$$

The notation can be mildly treacherous: $SL(2,\mathbb C)$ as a real Lie group is the double cover of $SO^+(1,3)$, while $\mathfrak{sl}(2,\mathbb C)$ also appears as a complex Lie algebra. Context decides which meaning is intended.

Because $L_i$ and $R_i$ commute, an irreducible finite-dimensional complex representation is labeled by a pair of spins:

$$
(j_L,j_R),
\qquad
j_L,j_R\in\frac12\mathbb Z_{\ge0}.
$$

Its dimension is

$$
\dim(j_L,j_R)=(2j_L+1)(2j_R+1).
$$

The rotation generators are

$$
J_i=L_i+R_i,
$$

and the boost generators are

$$
K_i=i(L_i-R_i).
$$

Under the rotation subgroup, the representation $(j_L,j_R)$ decomposes like the tensor product of $SU(2)$ representations:

$$
(j_L,j_R)\big|_{SU(2)_{\text{rot}}}
\cong
\bigoplus_{j=|j_L-j_R|}^{j_L+j_R}V_j.
$$

This formula tells you which ordinary rotation spins appear inside a Lorentz field representation.

## Basic finite-dimensional Lorentz representations

The standard representations are:

| Lorentz representation | dimension | common object | rotation content |
|---|---:|---|---|
| $(0,0)$ | $1$ | scalar | spin $0$ |
| $(\frac12,0)$ | $2$ | left-handed Weyl spinor | spin $\frac12$ |
| $(0,\frac12)$ | $2$ | right-handed Weyl spinor | spin $\frac12$ |
| $(\frac12,\frac12)$ | $4$ | Lorentz vector | spin $0\oplus1$ under rotations |
| $(1,0)$ | $3$ | self-dual two-form part | spin $1$ |
| $(0,1)$ | $3$ | anti-self-dual two-form part | spin $1$ |
| $(\frac12,0)\oplus(0,\frac12)$ | $4$ | Dirac spinor | two Weyl spinors |

The vector representation has rotation content

$$
\frac12\otimes\frac12=0\oplus1.
$$

This matches the familiar split of a four-vector into a time component and a spatial vector under spatial rotations:

$$
V^\mu=(V^0,\mathbf V).
$$

The antisymmetric tensor representation decomposes as

$$
\left(\frac12,\frac12\right)\wedge
\left(\frac12,\frac12\right)
\cong
(1,0)\oplus(0,1).
$$

In electromagnetism, this corresponds to the split of $F_{\mu\nu}$ into self-dual and anti-self-dual pieces after complexification.

## Weyl spinors

An undotted Weyl spinor transforms as

$$
\psi_\alpha\mapsto A_\alpha{}^\beta\psi_\beta,
\qquad
A\in SL(2,\mathbb C).
$$

It is in the representation

$$
\left(\frac12,0\right).
$$

A dotted Weyl spinor transforms in the complex conjugate representation:

$$
\bar\chi_{\dot\alpha}\mapsto A^*_{\dot\alpha}{}^{\dot\beta}\bar\chi_{\dot\beta},
$$

which is labeled

$$
\left(0,\frac12\right).
$$

The dot is not decoration. It tells you which of the two $SU(2)$-type factors the spinor belongs to.

There are invariant antisymmetric tensors

$$
\epsilon_{\alpha\beta},
\qquad
\epsilon_{\dot\alpha\dot\beta},
$$

with

$$
\epsilon_{12}=1.
$$

They raise and lower spinor indices. For example, one common convention is

$$
\psi^\alpha=\epsilon^{\alpha\beta}\psi_\beta,
\qquad
\psi_\alpha=\epsilon_{\alpha\beta}\psi^\beta.
$$

The determinant-one condition implies

$$
A^T\epsilon A=\epsilon,
$$

so the contraction

$$
\psi^\alpha\chi_\alpha
$$

is Lorentz invariant for two undotted spinors. Similarly,

$$
\bar\psi_{\dot\alpha}\bar\chi^{\dot\alpha}
$$

is invariant for dotted spinors.

A mixed object with one undotted and one dotted index transforms as a vector:

$$
X_{\alpha\dot\alpha}\sim x_\mu\bar\sigma^\mu_{\alpha\dot\alpha}.
$$

This is the index version of the Hermitian matrix construction.

## Sigma matrices as the spinor-vector dictionary

The matrices $\sigma^\mu$ and $\bar\sigma^\mu$ translate between vector and spinor notation. They satisfy

$$
\sigma^\mu_{\alpha\dot\alpha}\bar\sigma^{\nu\dot\alpha\beta}
+
\sigma^\nu_{\alpha\dot\alpha}\bar\sigma^{\mu\dot\alpha\beta}
=2\eta^{\mu\nu}\delta_\alpha{}^\beta.
$$

Similarly,

$$
\bar\sigma^{\mu\dot\alpha\alpha}\sigma^\nu_{\alpha\dot\beta}
+
\bar\sigma^{\nu\dot\alpha\alpha}\sigma^\mu_{\alpha\dot\beta}
=2\eta^{\mu\nu}\delta^{\dot\alpha}{}_{\dot\beta}.
$$

These identities are the two-component-spinor version of the Clifford algebra. Later, the Dirac gamma matrices package them into $4\times4$ matrices.

A vector can be written as a bispinor:

$$
V_{\alpha\dot\alpha}=V_\mu\sigma^\mu_{\alpha\dot\alpha}
$$

or with the barred convention depending on index placement. The inverse relation uses

$$
V^\mu=\frac12\bar\sigma^{\mu\dot\alpha\alpha}V_{\alpha\dot\alpha}.
$$

The precise placement of bars and raised/lowered indices varies across sources. The invariant content is stable: a Lorentz vector is the tensor product of one undotted and one dotted spinor.

## Dirac spinors from Weyl spinors

A Dirac spinor is not irreducible as a representation of the connected Lorentz group. It is the direct sum

$$
\left(\frac12,0\right)\oplus\left(0,\frac12\right).
$$

In a chiral basis, one writes schematically

$$
\Psi=\begin{pmatrix}\psi_\alpha\\ \bar\chi^{\dot\alpha}\end{pmatrix}.
$$

The upper component is left-handed; the lower component is right-handed. A Lorentz-invariant mass term couples the two chiralities. That is why a massive Dirac fermion needs both Weyl representations.

For a massless Weyl fermion, one chirality can exist by itself in a complex representation of the internal gauge group. Whether such a theory is consistent then depends on gauge anomaly cancellation, a physics question beyond the representation theory on this page.

Majorana reality conditions relate a spinor to its complex conjugate. In $3+1$ Lorentzian signature, a Majorana spinor can be written using both Weyl components with a reality condition. The detailed gamma-matrix conventions belong in the spinor chapter, but the representation-theory statement is already here: complex conjugation swaps

$$
\left(\frac12,0\right)
\longleftrightarrow
\left(0,\frac12\right).
$$

## Finite-dimensional Lorentz representations are not Hilbert-space representations

The Lorentz group is noncompact. Consequently, nontrivial finite-dimensional Lorentz representations are not unitary with respect to a positive-definite inner product.

This statement is crucial. Local fields transform in finite-dimensional Lorentz representations, but one-particle Hilbert-space states transform in unitary irreducible representations of the Poincaré group.

For example, a four-vector field $A_\mu(x)$ transforms in $(\frac12,\frac12)$. A massive spin-$1$ particle has three physical spin states. A massless photon has two physical helicity states. The field representation is a covariant way to write local equations and interactions; it is not the physical state space by itself.

This is one of the most important conceptual separations in relativistic QFT:

$$
\text{finite-dimensional Lorentz reps for fields}
\neq
\text{unitary Poincaré reps for particles}.
$$

Both are needed. Mixing them is a reliable source of fog.

## Parity and complex conjugation

The connected Lorentz group $SO^+(1,3)$ does not include parity. Parity exchanges the two Weyl representations:

$$
\left(\frac12,0\right)
\leftrightarrow
\left(0,\frac12\right).
$$

More generally,

$$
(j_L,j_R)\longleftrightarrow (j_R,j_L)\quad\text{under parity}.
$$

Therefore a representation with $j_L\neq j_R$ is chiral. It is not invariant under parity by itself. A parity-invariant theory usually pairs it with its parity conjugate.

Complex conjugation also swaps the two factors:

$$
(j_L,j_R)^*=(j_R,j_L).
$$

This is why the complex conjugate of a left-handed Weyl spinor is right-handed.

The vector representation is self-conjugate:

$$
\left(\frac12,\frac12\right)^*
=
\left(\frac12,\frac12\right).
$$

A scalar is also self-conjugate as a Lorentz representation, although an internal symmetry representation can still make a scalar field complex.

## A compact dictionary

| Object | Lorentz representation | Meaning |
|---|---|---|
| scalar $\phi$ | $(0,0)$ | no spinor or vector index |
| left Weyl spinor $\psi_\alpha$ | $(\frac12,0)$ | undotted spinor |
| right Weyl spinor $\bar\chi_{\dot\alpha}$ | $(0,\frac12)$ | dotted spinor |
| Dirac spinor $\Psi$ | $(\frac12,0)\oplus(0,\frac12)$ | two Weyl spinors packaged together |
| vector $V_\mu$ | $(\frac12,\frac12)$ | one undotted and one dotted index |
| self-dual two-form | $(1,0)$ | symmetric undotted pair |
| anti-self-dual two-form | $(0,1)$ | symmetric dotted pair |
| rotation generator $J_i$ | algebra generator | compact subgroup action |
| boost generator $K_i$ | algebra generator | noncompact transformation |
| parity | not in $SO^+(1,3)$ | swaps left and right |

## Common pitfalls

**Treating $SO(1,3)$ as if it were the whole Lorentz story.** Spinors require a double cover. The connected spin group in $3+1$ dimensions is $SL(2,\mathbb C)$, not $SO^+(1,3)$ itself.

**Forgetting the two-to-one map.** The matrices $A$ and $-A$ in $SL(2,\mathbb C)$ induce the same Lorentz transformation on vectors. Spinors can distinguish them; vectors cannot.

**Thinking finite-dimensional Lorentz representations are unitary Hilbert-space representations.** They are generally not. Fields transform covariantly in finite-dimensional representations. Physical states transform unitarily under the Poincaré group.

**Confusing left-handed and right-handed spinors with helicity too early.** Chirality is a Lorentz representation label. Helicity is a spin projection along momentum for a state. For massless particles they are closely related; for massive particles they are not the same concept.

**Dropping bars on sigma matrices.** With mostly-minus signature, $\sigma^\mu=(1,\sigma^i)$ and $\bar\sigma^\mu=(1,-\sigma^i)$ appear together. Losing a bar often means losing a metric sign.

**Forgetting that parity is outside the connected Lorentz group.** The labels $(j_L,j_R)$ are representations of the connected group. Parity maps $(j_L,j_R)$ to $(j_R,j_L)$.

**Using spinor index positions casually.** The tensors $\epsilon_{\alpha\beta}$ and $\epsilon_{\dot\alpha\dot\beta}$ raise and lower indices. Different books choose different sign conventions. The page-level convention must be fixed before comparing component formulas.

## Relations to other pages

[SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/) supplies the spin-$j$ representation theory used in the labels $(j_L,j_R)$.

[Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/) explains double covers, Lie algebras, complexification, exponentials, and the difference between local and global group data.

[Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/) explains representations, tensor products, invariant tensors, and dual representations in general language.

The later Poincaré group page should explain Wigner's classification of one-particle states, including mass, spin, helicity, and little groups. The later Clifford algebras and spinors chapter should explain how Weyl spinors, Dirac spinors, gamma matrices, bilinears, and Fierz identities are organized in four-component notation.

## Research status

The relationship between $SL(2,\mathbb C)$ and $SO^+(1,3)$, the Lorentz algebra, Weyl spinors, and finite-dimensional Lorentz representations is standard and settled.

Active research uses this representation theory in more advanced ways. Spinor-helicity variables turn Lorentz spinors into efficient scattering-amplitude variables. Celestial amplitudes reorganize four-dimensional scattering using Lorentz transformations as conformal transformations on the celestial sphere. Higher-spin theories explore representations beyond ordinary low-spin fields. Conformal field theory extends Lorentz representations into representations of the conformal group. None of those developments changes the basic $SL(2,\mathbb C)$ backbone; they build on it.

## Exercises

### Exercise 1

Show that

$$
\det\left(x^0\mathbf 1+x^i\sigma_i\right)=(x^0)^2-\mathbf x^2.
$$

<details><summary><strong>Solution</strong></summary>

Using the Pauli matrices,

$$
x^0\mathbf 1+x^i\sigma_i
=\begin{pmatrix}
x^0+x^3&x^1-ix^2\\
x^1+ix^2&x^0-x^3
\end{pmatrix}.
$$

The determinant is

$$
(x^0+x^3)(x^0-x^3)-(x^1-ix^2)(x^1+ix^2).
$$

This equals

$$
(x^0)^2-(x^3)^2-(x^1)^2-(x^2)^2.
$$

Therefore

$$
\det\left(x^0\mathbf 1+x^i\sigma_i\right)
=(x^0)^2-\mathbf x^2=x^2.
$$

</details>

### Exercise 2

Prove that $X\mapsto AXA^\dagger$ preserves the Minkowski norm when $A\in SL(2,\mathbb C)$.

<details><summary><strong>Solution</strong></summary>

The Minkowski norm is encoded by

$$
x^2=\det X.
$$

Under the transformation,

$$
X'=AXA^\dagger.
$$

The determinant is multiplicative:

$$
\det X'=\det A\det X\det A^\dagger.
$$

Since $A\in SL(2,\mathbb C)$,

$$
\det A=1.
$$

Also

$$
\det A^\dagger=(\det A)^*=1.
$$

Thus

$$
\det X'=\det X.
$$

Therefore

$$
x'^2=x^2.
$$

The induced transformation on $x^\mu$ is Lorentz.

</details>

### Exercise 3

Show that the kernel of the map

$$
SL(2,\mathbb C)\to SO^+(1,3)
$$

is $\{+\mathbf 1,-\mathbf 1\}$.

<details><summary><strong>Solution</strong></summary>

An element $A$ is in the kernel if

$$
AXA^\dagger=X
$$

for every Hermitian $X$.

Taking $X=\mathbf 1$ gives

$$
AA^\dagger=\mathbf 1,
$$

so $A$ is unitary and $A^\dagger=A^{-1}$. Then the kernel condition becomes

$$
AXA^{-1}=X
$$

for every Hermitian $X$.

Hermitian matrices span all complex $2\times2$ matrices over $\mathbb C$, so $A$ commutes with every $2\times2$ matrix. Therefore $A$ is a scalar matrix:

$$
A=\lambda\mathbf 1.
$$

The condition $A\in SL(2,\mathbb C)$ gives

$$
\det A=\lambda^2=1.
$$

Hence

$$
\lambda=\pm1.
$$

Therefore

$$
\ker\Lambda=\{+\mathbf 1,-\mathbf 1\}.
$$

</details>

### Exercise 4

Using the Lorentz algebra

$$
[J_i,J_j]=i\epsilon_{ijk}J_k,
\qquad
[J_i,K_j]=i\epsilon_{ijk}K_k,
\qquad
[K_i,K_j]=-i\epsilon_{ijk}J_k,
$$

prove that

$$
L_i=\frac12(J_i-iK_i),
\qquad
R_i=\frac12(J_i+iK_i)
$$

satisfy

$$
[L_i,L_j]=i\epsilon_{ijk}L_k,
\qquad
[R_i,R_j]=i\epsilon_{ijk}R_k,
\qquad
[L_i,R_j]=0.
$$

<details><summary><strong>Solution</strong></summary>

First compute

$$
[L_i,L_j]
=\frac14[J_i-iK_i,J_j-iK_j].
$$

Expanding,

$$
[L_i,L_j]
=\frac14\left([J_i,J_j]-i[J_i,K_j]-i[K_i,J_j]-[K_i,K_j]\right).
$$

Use

$$
[J_i,J_j]=i\epsilon_{ijk}J_k,
$$

$$
[J_i,K_j]=i\epsilon_{ijk}K_k,
$$

$$
[K_i,J_j]=i\epsilon_{ijk}K_k,
$$

and

$$
[K_i,K_j]=-i\epsilon_{ijk}J_k.
$$

Then

$$
[L_i,L_j]
=\frac14\left(i\epsilon_{ijk}J_k+\epsilon_{ijk}K_k+\epsilon_{ijk}K_k+i\epsilon_{ijk}J_k\right).
$$

So

$$
[L_i,L_j]
=\frac12\left(i\epsilon_{ijk}J_k+\epsilon_{ijk}K_k\right).
$$

But

$$
i\epsilon_{ijk}L_k
=i\epsilon_{ijk}\frac12(J_k-iK_k)
=\frac12\left(i\epsilon_{ijk}J_k+\epsilon_{ijk}K_k\right).
$$

Therefore

$$
[L_i,L_j]=i\epsilon_{ijk}L_k.
$$

The computation for $R_i$ is the same algebra with the opposite sign choice and gives

$$
[R_i,R_j]=i\epsilon_{ijk}R_k.
$$

For the mixed commutator,

$$
[L_i,R_j]
=\frac14[J_i-iK_i,J_j+iK_j].
$$

Expanding and substituting the same algebra gives equal and opposite terms, so

$$
[L_i,R_j]=0.
$$

</details>

### Exercise 5

What is the dimension of the Lorentz representation $(j_L,j_R)$? What rotation spins appear in it?

<details><summary><strong>Solution</strong></summary>

The two labels $j_L$ and $j_R$ are ordinary $SU(2)$ spin labels for two commuting $SU(2)$-type algebras after complexification.

The spin-$j_L$ representation has dimension

$$
2j_L+1,
$$

and the spin-$j_R$ representation has dimension

$$
2j_R+1.
$$

Since the full representation is a tensor product, its dimension is

$$
\dim(j_L,j_R)=(2j_L+1)(2j_R+1).
$$

Under the diagonal rotation subgroup, the representation decomposes as angular-momentum addition:

$$
(j_L,j_R)\big|_{SU(2)_{\text{rot}}}
\cong
\bigoplus_{j=|j_L-j_R|}^{j_L+j_R}V_j.
$$

The spin $j$ increases in integer steps.

For example,

$$
\left(\frac12,\frac12\right)
$$

has dimension $4$ and decomposes under rotations as

$$
0\oplus1.
$$

</details>

### Exercise 6

Explain why a nontrivial finite-dimensional Lorentz representation cannot be unitary with respect to a positive-definite inner product.

<details><summary><strong>Solution</strong></summary>

Here is a compact Lie-algebra proof.

In a finite-dimensional unitary representation, the derived representation sends each real Lie-algebra generator to an anti-Hermitian matrix. Therefore the bilinear form

$$
B_\rho(X,Y)=-\operatorname{tr}(d\rho(X)d\rho(Y))
$$

is positive semidefinite:

$$
B_\rho(X,X)\ge0.
$$

It is also invariant under the Lie algebra:

$$
B_\rho([Z,X],Y)+B_\rho(X,[Z,Y])=0,
$$

because the trace is cyclic.

For a simple real Lie algebra, every invariant symmetric bilinear form is proportional to the Killing form. The Lorentz algebra $\mathfrak{so}(1,3)$ is simple as a real Lie algebra, and its Killing form is indefinite: rotations and boosts have opposite signs.

A positive semidefinite invariant form cannot be a nonzero multiple of an indefinite form. Hence

$$
B_\rho=0.
$$

This implies

$$
d\rho(X)=0
$$

for every Lorentz-algebra generator $X$. The representation is therefore trivial on the connected Lorentz group.

So nontrivial finite-dimensional Lorentz representations are not unitary Hilbert-space representations. They are covariant field representations. Physical particle states instead transform in unitary representations of the Poincaré group.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for Lorentz invariance, Poincaré representations, one-particle states, and the relation between fields and particles.
- M. Srednicki, *Quantum Field Theory*, for Lorentz representations, left- and right-handed spinor fields, spinor indices, and gamma-matrix technology.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for Lorentz representations, spinors, helicity, and practical Standard Model conventions.
- A. Zee, *Quantum Field Theory in a Nutshell*, for a fast physical introduction to spinors, Lorentz symmetry, and the role of two-component spinors.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for Lorentz representations, Weyl spinors, Dirac fields, and the representation-theoretic logic of relativistic fields.
- W.-K. Tung, *Group Theory in Physics*, and J. F. Cornwell, *Group Theory in Physics*, for detailed group-theoretic treatment of the Lorentz group and spinor representations.
- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for the mathematical background on Lie groups, Lie algebras, complexification, and representations.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
