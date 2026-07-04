---
title: "Lie Groups and Lie Algebras"
description: "A QFT-oriented introduction to Lie groups, Lie algebras, exponential maps, structure constants, adjoint representations, generator conventions, and global group data."
sidebar:
  label: "Lie Groups and Lie Algebras"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard Lie theory and QFT symmetry references, including Hall, Georgi, Fulton–Harris, Tung, Cornwell, Weinberg, Srednicki, Coleman, Schwartz, and Zee."
topics:
  - Lie groups
  - Lie algebras
  - exponential map
  - structure constants
  - adjoint representation
  - global group structure
canonicalTopics:
  - lie-group
  - lie-algebra
  - exponential-map
  - structure-constants
  - adjoint-representation
  - global-form-of-gauge-group
researchStatus:
  established:
    - "The local relationship between finite-dimensional Lie groups, their Lie algebras, representations, exponentials, and structure constants is mathematically standard and foundational for QFT symmetry."
  active:
    - "Global forms of gauge groups, disconnected symmetries, higher groups, categorical symmetries, and generalized global symmetries remain central in modern QFT beyond the finite-dimensional local theory developed here."
---

## Summary

A **Lie group** is a group that is also a smooth manifold, with smooth multiplication and inversion. A **Lie algebra** is the tangent space to the Lie group at the identity, equipped with a bracket that records infinitesimal noncommutativity.

For a Lie group $G$, its Lie algebra is written

$$
\mathfrak g=T_eG.
$$

For a matrix Lie group, elements near the identity can often be written as exponentials:

$$
g(t)=\exp(tX),
\qquad
X\in\mathfrak g.
$$

The slogan is

$$
\text{Lie algebra} = \text{infinitesimal local model of a Lie group}.
$$

This slogan is useful but incomplete. The Lie algebra captures the local structure near the identity. It does not by itself determine the global group. For example, $SU(2)$ and $SO(3)$ have the same Lie algebra but different representations as honest global groups.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a Lie group as a smooth manifold, its tangent Lie algebra at the identity, the exponential map, the bracket, local multiplication, differentiated representations, and the physicist generator convention.](/figures/math-toolkit/lie-algebra-exponential-map.svg)

<figcaption>

A Lie algebra is the tangent-space model of a Lie group at the identity. The exponential map sends infinitesimal data toward finite transformations, and representations differentiate to Lie-algebra representations. In compact-group physics conventions this local data is written $[T^a,T^b]=if^{abc}T^c$.

</figcaption>
</figure>

In QFT, Lie groups and Lie algebras appear in three closely related ways:

$$
\text{spacetime symmetries},
\qquad
\text{internal global symmetries},
\qquad
\text{gauge redundancies}.
$$

The same formulas occur in all three, but their physical interpretations differ. A Lorentz generator rotates fields and spacetime indices. A flavor generator rotates multiplets. A gauge generator removes redundant local variables. The algebraic technology is shared; the physics is not identical.

## Prerequisites

You should know [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/), especially group actions, representations, invariant tensors, dual representations, and the several meanings of “algebra” in QFT.

The compact-group generator and trace normalizations follow [Mathematical Conventions](/math-toolkit/conventions/). We use Hermitian generators for compact groups in physics formulas:

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

Classical generators act through Poisson brackets as explained in [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/). Gauge constraints and gauge generators are previewed in [Constraints Preview](/math-toolkit/calculus-of-variations-and-phase-space/constraints-preview/).

## Core idea

A continuous symmetry has finite transformations and infinitesimal transformations. Lie theory explains their relationship.

For a one-parameter family of transformations $g(t)$ with

$$
g(0)=e,
$$

the derivative at the identity gives an infinitesimal generator:

$$
X=\left.\frac{d}{dt}g(t)\right|_{t=0}\in T_eG.
$$

For matrix groups, this is literally a matrix. If $g(t)$ lies in a matrix group $G\subset GL(n,\mathbb C)$, then $X$ is an $n\times n$ matrix satisfying the infinitesimal version of the defining equations of $G$.

For example, $U(N)$ consists of matrices satisfying

$$
U^\dagger U=\mathbf 1.
$$

Write

$$
U(t)=\mathbf 1+tX+O(t^2).
$$

Then

$$
U(t)^\dagger U(t)
=
\mathbf 1+t(X^\dagger+X)+O(t^2),
$$

so

$$
X^\dagger=-X.
$$

Thus the mathematical Lie algebra of $U(N)$ is anti-Hermitian matrices. Physicists often write

$$
X=iH,
\qquad
H^\dagger=H,
$$

and call the Hermitian matrices $H$ the generators. Both conventions describe the same infinitesimal transformations. The factor of $i$ is convention, but it must be carried consistently.

The bracket measures the first noncommutativity of infinitesimal transformations. If two generators $X$ and $Y$ are applied in a tiny commutator loop, the leading effect is controlled by

$$
[X,Y].
$$

For matrix groups this bracket is the matrix commutator. For abstract Lie groups, it is the commutator of left-invariant vector fields.

## Setup and conventions

A **Lie group** $G$ is a smooth manifold with a group structure such that multiplication

$$
m:G\times G\to G,
\qquad
m(g,h)=gh,
$$

and inversion

$$
i:G\to G,
\qquad
i(g)=g^{-1},
$$

are smooth maps.

Its **Lie algebra** is the tangent space at the identity,

$$
\mathfrak g=T_eG,
$$

together with a bracket

$$
[\cdot,\cdot]:\mathfrak g\times\mathfrak g\to\mathfrak g.
$$

The bracket is bilinear, antisymmetric, and satisfies the Jacobi identity:

$$
[X,Y]=-[Y,X],
$$

$$
[X,[Y,Z]]+[Y,[Z,X]]+[Z,[X,Y]]=0.
$$

For compact Lie groups in the physics convention used here, we use Hermitian representation matrices $T^a_R$ and write

$$
[T_R^a,T_R^b]=if^{ab}{}_{c}T_R^c.
$$

For compact simple groups, the trace normalization is

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
\qquad
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

For $SU(N)$ in the fundamental representation,

$$
\operatorname{tr}_F(T^aT^b)=\frac12\delta^{ab}.
$$

Mathematical sources often use anti-Hermitian generators $X^a=-iT^a$. In that convention,

$$
[X^a,X^b]=f^{ab}{}_{c}X^c.
$$

Neither convention is more correct. The mistake is mixing them inside one computation.

## Matrix Lie groups by examples

A **matrix Lie group** is a closed subgroup of $GL(n,\mathbb C)$ or $GL(n,\mathbb R)$, with matrix multiplication. Its Lie algebra can be found by differentiating the defining equations at the identity.

### The unitary group

The group

$$
U(N)=\{U\in GL(N,\mathbb C)\mid U^\dagger U=\mathbf 1\}
$$

has mathematical Lie algebra

$$
\mathfrak u(N)=\{X\in M_N(\mathbb C)\mid X^\dagger=-X\}.
$$

In physics, one writes $X=iH$ with $H=H^\dagger$, so Hermitian generators exponentiate as

$$
U(\alpha)=\exp(i\alpha_aT^a).
$$

### The special unitary group

The group

$$
SU(N)=\{U\in U(N)\mid \det U=1\}
$$

has Lie algebra

$$
\mathfrak{su}(N)=\{X\in\mathfrak u(N)\mid \operatorname{tr}X=0\}.
$$

In Hermitian physics convention, $X=iH$ and $H$ is traceless Hermitian. Thus $SU(N)$ has

$$
\dim SU(N)=N^2-1.
$$

This is why a Yang–Mills gauge field with gauge group $SU(N)$ has $N^2-1$ adjoint components:

$$
A_\mu=A_\mu^aT^a,
\qquad
a=1,\ldots,N^2-1.
$$

### The orthogonal group

The group

$$
SO(N)=\{R\in GL(N,\mathbb R)\mid R^TR=\mathbf 1,\;\det R=1\}
$$

has Lie algebra

$$
\mathfrak{so}(N)=\{X\in M_N(\mathbb R)\mid X^T=-X\}.
$$

For $SO(3)$, one can choose angular momentum generators satisfying

$$
[J_i,J_j]=i\epsilon_{ijk}J_k.
$$

These are Hermitian quantum generators. The corresponding real antisymmetric infinitesimal rotation matrices are anti-Hermitian after complexification.

### The Lorentz group

With mostly-minus metric,

$$
\eta=\operatorname{diag}(+1,-1,-1,-1),
$$

the Lorentz group is

$$
O(1,3)=\{\Lambda\in GL(4,\mathbb R)\mid \Lambda^T\eta\Lambda=\eta\}.
$$

The connected proper orthochronous component is denoted $SO^+(1,3)$. Its Lie algebra consists of matrices $\omega$ satisfying

$$
\omega^T\eta+\eta\omega=0.
$$

The Lorentz group is noncompact. This is why finite-dimensional Lorentz spinor and tensor representations used for fields are not unitary representations on the particle Hilbert space. Particle states are instead classified by unitary irreducible representations of the Poincaré group.

## Exponential map

For a matrix Lie group, the exponential map is the matrix exponential:

$$
\exp X=\sum_{n=0}^\infty \frac{X^n}{n!}.
$$

It sends Lie algebra elements to group elements near the identity:

$$
X\in\mathfrak g
\quad\longmapsto\quad
\exp X\in G.
$$

In physics Hermitian-generator convention, finite compact-group transformations are usually written

$$
g(\theta)=\exp(i\theta_aT^a).
$$

The exponential map is locally reliable near the identity. Globally, it can fail to be one-to-one, and for some Lie groups it is not onto the whole group.

For $U(1)$,

$$
\alpha\mapsto e^{i\alpha}
$$

is periodic:

$$
e^{i(\alpha+2\pi)}=e^{i\alpha}.
$$

Thus the Lie algebra is $\mathbb R$, but the group is a circle. The local infinitesimal generator does not remember the global identification $\alpha\sim\alpha+2\pi$.

For $SU(2)$, every group element is an exponential, but the map is not one-to-one. For many noncompact groups, exponential coordinates cover only part of the group. In QFT, local perturbative computations often depend only on the Lie algebra, while nonperturbative observables can depend on the global group.

## Baker–Campbell–Hausdorff formula

The Baker–Campbell–Hausdorff formula says that, for $X$ and $Y$ sufficiently small,

$$
\exp X\exp Y=\exp Z,
$$

where

$$
Z=X+Y+\frac12[X,Y]
+\frac1{12}[X,[X,Y]]
+\frac1{12}[Y,[Y,X]]+\cdots.
$$

The first correction to simply adding generators is the commutator. This is the local origin of nonabelian composition.

If

$$
[X,Y]=0,
$$

then

$$
\exp X\exp Y=\exp(X+Y).
$$

For nonabelian groups, this fails. This failure is exactly why ordering matters for Wilson lines, time-ordered exponentials, path-ordered exponentials, and nonabelian gauge theory.

A related commutator loop is

$$
\exp(\epsilon X)\exp(\epsilon Y)\exp(-\epsilon X)\exp(-\epsilon Y)
=
\exp(\epsilon^2[X,Y]+O(\epsilon^3)).
$$

This formula gives a geometric interpretation of the Lie bracket: it measures the infinitesimal failure of two flows to commute.

## Structure constants and basis dependence

Choose a basis $T^a$ of a Lie algebra representation. In the compact Hermitian convention,

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

The numbers $f^{ab}{}_{c}$ are **structure constants**. They are not a tensor under arbitrary changes of basis unless the basis change is tracked. They encode the bracket in that chosen basis.

Antisymmetry of the bracket implies

$$
f^{ab}{}_{c}=-f^{ba}{}_{c}.
$$

The Jacobi identity implies

$$
f^{ab}{}_{d}f^{dc}{}_{e}
+f^{bc}{}_{d}f^{da}{}_{e}
+f^{ca}{}_{d}f^{db}{}_{e}=0.
$$

For a compact simple Lie algebra, one often chooses an orthonormal basis with respect to an invariant inner product so that indices can be moved without visible metrics. In practical physics formulas, this is often hidden inside the normalization

$$
\operatorname{tr}_F(T^aT^b)=\frac12\delta^{ab}
$$

for $SU(N)$ fundamentals.

When comparing sources, always check whether their generators are Hermitian or anti-Hermitian and how their trace is normalized. A change

$$
T^a\mapsto cT^a
$$

rescales both the structure constants and trace normalizations. Couplings and fields may then be rescaled to compensate.

## Representations and their differentials

A smooth representation of a Lie group is a smooth homomorphism

$$
\rho:G\to GL(V).
$$

Differentiating at the identity gives a Lie-algebra representation

$$
d\rho:\mathfrak g\to \operatorname{End}(V).
$$

For a curve $g(t)=\exp(tX)$,

$$
d\rho(X)=\left.\frac{d}{dt}\rho(\exp(tX))\right|_{t=0}.
$$

The representation property implies

$$
d\rho([X,Y])=[d\rho(X),d\rho(Y)].
$$

In physics compact-group notation, one often writes

$$
\rho(e^{i\theta_aT^a})=e^{i\theta_aT_R^a},
$$

where $T_R^a$ are matrices in representation $R$ satisfying

$$
[T_R^a,T_R^b]=if^{ab}{}_{c}T_R^c.
$$

The same abstract Lie algebra can have many representations. For $SU(2)$, the spin-$j$ representation has dimension

$$
2j+1,
$$

with

$$
j=0,\frac12,1,\frac32,\ldots
$$

as representations of $SU(2)$. Only integer $j$ descend to honest representations of $SO(3)$.

This distinction is not decorative. It is the mathematical reason spinors change sign under a $2\pi$ rotation while vectors do not.

## Adjoint action and adjoint representation

A Lie group acts on itself by conjugation:

$$
C_g(h)=ghg^{-1}.
$$

Differentiating this action at the identity gives the **adjoint representation** of the group on its Lie algebra:

$$
\operatorname{Ad}_g:
\mathfrak g\to\mathfrak g.
$$

For a matrix group,

$$
\operatorname{Ad}_g(X)=gXg^{-1}.
$$

Differentiating again gives the adjoint representation of the Lie algebra:

$$
\operatorname{ad}_X(Y)=[X,Y].
$$

In a basis with Hermitian compact generators,

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

The adjoint-representation matrices can be written as

$$
(T_A^a)^b{}_{c}=-if^{ab}{}_{c}
$$

with a consistent placement of row and column indices. These matrices satisfy

$$
[T_A^a,T_A^b]=if^{ab}{}_{c}T_A^c.
$$

Gauge fields in Yang–Mills theory transform in the adjoint representation locally, while matter fields may transform in other representations. The field strength is Lie-algebra-valued:

$$
F_{\mu\nu}=F_{\mu\nu}^aT^a.
$$

The adjoint representation is also where the quadratic Casimir $C_A$ appears:

$$
f^{acd}f^{bcd}=C_A\delta^{ab}
$$

in the standard compact normalization.

## Invariant bilinear forms and traces

A bilinear form $B$ on a Lie algebra is **invariant** if

$$
B([X,Y],Z)+B(Y,[X,Z])=0.
$$

Equivalently, $\operatorname{ad}_X$ is antisymmetric with respect to $B$.

For a representation $R$, the trace form

$$
B_R(X,Y)=\operatorname{tr}_R(T_R(X)T_R(Y))
$$

is invariant. For a compact simple Lie algebra, invariant symmetric bilinear forms are unique up to an overall scale. This is why one can define indices such as

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

The **Killing form** is

$$
K(X,Y)=\operatorname{tr}(\operatorname{ad}_X\operatorname{ad}_Y).
$$

For semisimple Lie algebras, the Killing form is nondegenerate. In compact conventions it is negative definite if anti-Hermitian generators are used; with Hermitian generators and inserted factors of $i$, signs shift. This is a common source of convention mismatch.

For most QFT pages, the important lesson is not the abstract Killing form itself. It is that contractions of adjoint indices require a chosen invariant metric, and the normalization of that metric controls $f^{abc}$, $C_A$, $T(R)$, $C_2(R)$, beta-function coefficients, anomaly coefficients, and color factors.

## Real forms and complexification

Many Lie algebras used in QFT have real forms and complexifications.

A real Lie algebra $\mathfrak g$ can be complexified:

$$
\mathfrak g_\mathbb C=\mathfrak g\otimes_\mathbb R\mathbb C.
$$

For example,

$$
\mathfrak{su}(2)_\mathbb C\simeq \mathfrak{sl}(2,\mathbb C).
$$

But $SU(2)$ and $SL(2,\mathbb C)$ are very different Lie groups. One is compact; the other is noncompact and is the double cover of the proper orthochronous Lorentz group in four dimensions.

A **real form** of a complex Lie algebra is a real Lie algebra whose complexification gives the complex algebra. Different real forms can have very different representation theory. For example,

$$
\mathfrak{su}(2),
\qquad
\mathfrak{sl}(2,\mathbb R),
$$

are different real forms of $\mathfrak{sl}(2,\mathbb C)$.

Physics often complexifies Lie algebras to simplify representation theory, then imposes a reality condition appropriate to a chosen spacetime signature or compact group. This is harmless if the reality condition is restored before making claims about unitarity, Hermiticity, or global group representations.

## Compact versus noncompact groups

Compact Lie groups behave especially nicely. Finite-dimensional unitary representations are abundant, and many representations decompose into irreducibles. For compact groups, one can average over the group using Haar measure to build invariant inner products.

This is why compact internal symmetry groups are technically friendly. Gauge groups in ordinary Yang–Mills theory are usually compact. Their finite-dimensional matter representations can be taken unitary, and Hermitian generators are natural in physics notation.

Noncompact groups are subtler. The Lorentz group is noncompact. It has finite-dimensional representations useful for fields, such as vectors and Weyl spinors, but these are not unitary in the Hilbert-space sense. Its unitary representations are infinite-dimensional, except for trivial cases.

This leads to a central QFT distinction:

$$
\text{fields transform in finite-dimensional Lorentz representations},
$$

while

$$
\text{physical particles transform in unitary Poincaré representations}.
$$

Mixing these two statements is one of the classic ways to get confused about spinors, polarizations, gauge fields, and negative-norm states.

## Lie algebra versus global group

The Lie algebra does not determine the global group uniquely.

The simplest example is

$$
\mathfrak{su}(2)\simeq\mathfrak{so}(3).
$$

The groups are related by

$$
SU(2)/\mathbb Z_2\simeq SO(3).
$$

They have the same local commutation relations, but their global representations differ. Half-integer spin representations are representations of $SU(2)$, not of $SO(3)$.

Another example is the distinction between $\mathbb R$ and $U(1)$. They have the same Lie algebra, but $U(1)$ is compact and has periodic global structure. That periodicity quantizes charges for honest representations:

$$
\rho_q(e^{i\alpha})=e^{iq\alpha}
$$

is single-valued on $U(1)$ only when $q\in\mathbb Z$ in the chosen normalization.

In gauge theory, the global form of the gauge group affects line operators, magnetic charges, instanton sectors, theta angles, one-form symmetries, and the classification of bundles. The Lie algebra alone gives the perturbative gauge bosons and local vertices, but not the full nonperturbative theory.

This is the practical rule:

$$
\text{perturbative local formulas often see }\mathfrak g;
\qquad
\text{global observables can see }G.
$$

## Lie-algebra-valued fields and covariant derivatives

Gauge theory uses Lie-algebra-valued fields. In the compact Hermitian convention,

$$
A_\mu=A_\mu^aT^a,
$$

and the covariant derivative on matter in representation $R$ is

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a.
$$

The field strength is defined by

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT_R^a.
$$

With the conventions used in the Mathematical Toolkit conventions page,

$$
F^a_{\mu\nu}
=
\partial_\mu A^a_\nu-
\partial_\nu A^a_\mu
-gf^{abc}A^b_\mu A^c_\nu.
$$

The nonabelian term comes directly from the Lie bracket. If the group is abelian, $f^{abc}=0$, and the field strength reduces to the familiar curl-like expression.

Gauge transformations can be written locally as

$$
U(x)=\exp(i\alpha^a(x)T^a).
$$

The covariant derivative is designed to transform covariantly:

$$
D_\mu\phi\mapsto U(D_\mu\phi)
$$

when

$$
\phi\mapsto U\phi.
$$

This is the representation-theoretic content of minimal coupling.

## Charges as Lie algebra generators

For a continuous global symmetry, Noether charges $Q^a$ represent the Lie algebra on the Hilbert space. In the compact Hermitian convention,

$$
[Q^a,Q^b]=if^{ab}{}_{c}Q^c.
$$

A local operator transforming in representation $R$ obeys

$$
[Q^a,\mathcal O_i]=-(T_R^a)_i{}^j\mathcal O_j
$$

or the same formula with the opposite sign, depending on whether the finite operator action is written as $U\mathcal O U^{-1}$ or $U^{-1}\mathcal O U$. The sign convention must be fixed at the start of a page involving Ward identities.

Classically, the analogous statement is

$$
\{Q^a,Q^b\}=f^{ab}{}_{c}Q^c
$$

up to the same convention choices. Quantization roughly turns Poisson brackets into commutators by

$$
\{\cdot,\cdot\}\quad\leadsto\quad \frac1i[\cdot,\cdot],
$$

with $\hbar=1$.

Central extensions can modify these algebras. For example, current algebras and Virasoro algebras contain central terms. Those extensions are not visible in the finite-dimensional Lie algebra of an ordinary compact symmetry group alone; they arise in representations, quantum anomalies, boundary terms, or infinite-dimensional symmetry algebras.

## Common pitfalls

**Forgetting that the Lie algebra is local.** The Lie algebra describes infinitesimal transformations near the identity. It does not determine centers, quotients, fundamental groups, allowed line operators, or charge lattices.

**Mixing Hermitian and anti-Hermitian generators.** Physicists often write $U=e^{i\theta_aT^a}$ with $T^a$ Hermitian. Mathematicians often put the $i$ into the Lie algebra element. Translate all commutators, covariant derivatives, and curvature signs together.

**Assuming the exponential map is globally one-to-one.** It usually is not. Even $U(1)$ has $\alpha\sim\alpha+2\pi$.

**Assuming the exponential map covers the whole group.** For many noncompact groups it does not. Local perturbation theory may not care; global questions can.

**Calling Lorentz field representations unitary.** Finite-dimensional nontrivial Lorentz representations are not unitary because the Lorentz group is noncompact. Physical Hilbert-space representations of the Poincaré group are unitary and typically infinite-dimensional before momentum labels are fixed.

**Using structure constants without specifying normalization.** Rescaling generators changes the numerical values of $f^{ab}{}_{c}$ and trace normalizations. Gauge couplings and Casimirs must be translated consistently.

**Treating all representations of the Lie algebra as representations of the group.** A Lie-algebra representation may fail to integrate to a representation of a chosen global group. Half-integer spin integrates to $SU(2)$ but not to $SO(3)$.

**Confusing the adjoint representation with the fundamental representation.** For $SU(N)$, the fundamental has dimension $N$, while the adjoint has dimension $N^2-1$. Gauge bosons transform in the adjoint; quarks in QCD transform in the fundamental.

## Relations to other pages

This page follows [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/) and supplies the local continuous-symmetry technology needed for the rest of the chapter.

The next planned pages specialize the general machinery to $SU(2)$ and angular momentum, then to the Lorentz group and spinorial representations. Gauge-theory pages later use the compact-group trace conventions, adjoint representation, Casimirs, and global group distinctions introduced here.

The generator and trace conventions are anchored in [Mathematical Conventions](/math-toolkit/conventions/). Hamiltonian charges and their brackets connect back to [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/), while local gauge redundancy connects to [Constraints Preview](/math-toolkit/calculus-of-variations-and-phase-space/constraints-preview/) and [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/).

## Research status

The finite-dimensional local theory of Lie groups and Lie algebras is settled mathematical infrastructure. The most common QFT mistakes are not open problems; they are convention mistakes, global-form mistakes, or mismatches between field representations and Hilbert-space representations.

The active QFT frontier uses this infrastructure in more elaborate settings: global forms of gauge groups, higher-form symmetries, higher groups, non-invertible symmetries, categorical symmetries, boundary symmetry algebras, current algebras, vertex operator algebras, and infinite-dimensional symmetry structures. Those topics require this page, but they are not exhausted by it.

## Exercises

### Exercise 1

Find the Lie algebra of $SU(N)$ by differentiating the defining conditions

$$
U^\dagger U=\mathbf 1,
\qquad
\det U=1.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
U(t)=\mathbf 1+tX+O(t^2).
$$

The unitary condition gives

$$
U(t)^\dagger U(t)
=\mathbf 1+t(X^\dagger+X)+O(t^2).
$$

Thus

$$
X^\dagger=-X.
$$

For the determinant condition, use

$$
\det(\mathbf 1+tX)=1+t\operatorname{tr}X+O(t^2).
$$

Since $\det U(t)=1$, we get

$$
\operatorname{tr}X=0.
$$

Therefore

$$
\mathfrak{su}(N)=\{X\mid X^\dagger=-X,\; \operatorname{tr}X=0\}.
$$

In physics notation one writes $X=iH$, where $H$ is traceless Hermitian.

</details>

### Exercise 2

Using the Baker–Campbell–Hausdorff formula, show that if $[X,Y]=0$, then

$$
\exp X\exp Y=\exp(X+Y).
$$

<details><summary><strong>Solution</strong></summary>

The Baker–Campbell–Hausdorff formula gives

$$
\exp X\exp Y=\exp\left(X+Y+\frac12[X,Y]+\frac1{12}[X,[X,Y]]+\frac1{12}[Y,[Y,X]]+\cdots\right).
$$

If $[X,Y]=0$, then every nested commutator involving $X$ and $Y$ also vanishes. The exponent reduces to

$$
X+Y.
$$

Therefore

$$
\exp X\exp Y=\exp(X+Y).
$$

This is why abelian exponentials behave like ordinary exponentials, while nonabelian ones require ordering.

</details>

### Exercise 3

Let $[T^a,T^b]=if^{ab}{}_{c}T^c$. Show that the Jacobi identity implies

$$
f^{ab}{}_{d}f^{dc}{}_{e}
+f^{bc}{}_{d}f^{da}{}_{e}
+f^{ca}{}_{d}f^{db}{}_{e}=0.
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
[T^a,[T^b,T^c]]+[T^b,[T^c,T^a]]+[T^c,[T^a,T^b]]=0.
$$

The first term is

$$
[T^a,if^{bc}{}_{d}T^d]
=if^{bc}{}_{d}[T^a,T^d]
=if^{bc}{}_{d}if^{ad}{}_{e}T^e
=-f^{bc}{}_{d}f^{ad}{}_{e}T^e.
$$

Using antisymmetry $f^{ad}{}_{e}=-f^{da}{}_{e}$, this is

$$
f^{bc}{}_{d}f^{da}{}_{e}T^e.
$$

The other cyclic terms give

$$
f^{ca}{}_{d}f^{db}{}_{e}T^e,
\qquad
f^{ab}{}_{d}f^{dc}{}_{e}T^e.
$$

Since the basis elements $T^e$ are independent, the coefficient of each $T^e$ must vanish, giving the stated identity.

</details>

### Exercise 4

For $U(1)$, explain why the Lie algebra alone permits arbitrary real charges, while the compact group $U(1)$ quantizes charges in integer units after choosing the minimal charge normalization.

<details><summary><strong>Solution</strong></summary>

The Lie algebra of $U(1)$ is locally $\mathbb R$. A Lie-algebra representation on a one-dimensional complex vector space may assign the generator any real number $q$ in physics Hermitian normalization:

$$
\delta\phi=iq\alpha\phi.
$$

But the group $U(1)$ identifies

$$
\alpha\sim\alpha+2\pi.
$$

A group representation must be single-valued:

$$
e^{iq(\alpha+2\pi)}=e^{iq\alpha}.
$$

Thus

$$
e^{i2\pi q}=1,
$$

which requires

$$
q\in\mathbb Z
$$

in the normalization where the smallest charge is $1$. The Lie algebra saw only infinitesimal $\alpha$; the group sees the periodic circle.

</details>

### Exercise 5

Let $G$ be a matrix Lie group. Show that the adjoint action

$$
\operatorname{Ad}_g(X)=gXg^{-1}
$$

preserves brackets:

$$
\operatorname{Ad}_g([X,Y])=[\operatorname{Ad}_gX,\operatorname{Ad}_gY].
$$

<details><summary><strong>Solution</strong></summary>

Compute the right-hand side:

$$
[\operatorname{Ad}_gX,\operatorname{Ad}_gY]
=[gXg^{-1},gYg^{-1}].
$$

Using matrix multiplication,

$$
[gXg^{-1},gYg^{-1}]
=gXg^{-1}gYg^{-1}-gYg^{-1}gXg^{-1}.
$$

Since $g^{-1}g=\mathbf 1$, this becomes

$$
gXYg^{-1}-gYXg^{-1}=g[X,Y]g^{-1}.
$$

Therefore

$$
[\operatorname{Ad}_gX,\operatorname{Ad}_gY]
=\operatorname{Ad}_g([X,Y]).
$$

</details>

### Exercise 6

In $SU(N)$ Yang–Mills theory, the gauge field is written $A_\mu=A_\mu^aT^a$. Explain why the number of gauge boson components labeled by $a$ is $N^2-1$.

<details><summary><strong>Solution</strong></summary>

The index $a$ labels a basis of the Lie algebra $\mathfrak{su}(N)$. In physics notation, the generators are traceless Hermitian $N\times N$ matrices.

The real vector space of Hermitian $N\times N$ matrices has dimension $N^2$: there are $N$ real diagonal entries and $N(N-1)/2$ complex off-diagonal entries, giving

$$
N+2\frac{N(N-1)}2=N^2.
$$

The traceless condition removes one real dimension. Therefore

$$
\dim \mathfrak{su}(N)=N^2-1.
$$

Thus

$$
a=1,\ldots,N^2-1.
$$

For QCD, $N=3$, so there are $3^2-1=8$ gluon color components.

</details>

## References

- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for a precise and readable development of Lie groups, Lie algebras, exponentials, representations, and compact groups.
- H. Georgi, *Lie Algebras in Particle Physics*, for compact Lie algebras, structure constants, roots, weights, and particle-physics normalization conventions.
- W. Fulton and J. Harris, *Representation Theory*, for finite-dimensional representation theory and the relation between Lie algebras and representations.
- W.-K. Tung, *Group Theory in Physics*, and J. F. Cornwell, *Group Theory in Physics*, for extensive physics applications of Lie groups and Lie algebras.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for Wigner’s theorem, Poincaré symmetry, projective representations, and field representations; Vol. II for nonabelian gauge-theory Lie algebra conventions.
- M. Srednicki, *Quantum Field Theory*, for Lorentz representations, spinor representations, nonabelian symmetries, and gauge-theory group data.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for the use of Lie groups and Lie algebras in Lorentz symmetry, Yang–Mills theory, and the Standard Model.
- S. Coleman, *Aspects of Symmetry* and *Lectures of Sidney Coleman on Quantum Field Theory*, for physical uses of symmetry generators, current algebra, gauge theory, and spontaneous symmetry breaking.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
