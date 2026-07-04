---
title: "Compact Lie Groups"
description: "A QFT-oriented guide to compact Lie groups, Haar measure, unitary representations, maximal tori, roots, weights, Weyl groups, centers, and gauge-theory group data."
sidebar:
  label: "Compact Lie Groups"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard Lie group and QFT references, including Hall, Georgi, Fulton–Harris, Knapp, Bourbaki-style root theory, Weinberg, Srednicki, Coleman, Schwartz, and Zee."
topics:
  - compact Lie groups
  - Haar measure
  - unitary representations
  - maximal tori
  - roots and weights
  - Weyl group
  - centers and global forms
canonicalTopics:
  - compact-lie-groups
  - haar-measure
  - unitary-representations
  - maximal-torus
  - roots-and-weights
  - weyl-group
  - global-form-of-gauge-group
researchStatus:
  established:
    - "The structure and finite-dimensional representation theory of compact connected Lie groups are completely classified by maximal tori, root systems, weight lattices, Weyl groups, and global form data."
  active:
    - "Modern QFT uses the global form of compact groups, centers, representation lattices, and associated higher-form symmetries in increasingly refined ways, especially in gauge theory, defects, anomalies, and phases of matter."
---

## Summary

Compact Lie groups are the natural home of ordinary internal symmetries in unitary quantum theories. They include

$$
U(1),
\qquad
SU(N),
\qquad
SO(N),
\qquad
Spin(N),
\qquad
Sp(N),
$$

and products and quotients built from them. They control flavor multiplets, spin and isospin, gauge-group representations, color factors, characters, singlet constraints, and the global data behind Wilson lines and generalized symmetries.

A Lie group is compact if it is compact as a topological space. For matrix groups, this roughly means closed and bounded inside the relevant matrix space. Compactness has strong consequences:

- there is a normalized invariant Haar measure $dg$;
- every finite-dimensional representation can be made unitary;
- finite-dimensional representations are completely reducible;
- irreducible representations are classified by highest weights;
- characters obey orthogonality relations;
- averaging over the group projects onto invariant subspaces.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing the structure of compact Lie groups: Haar measure, unitary representations, maximal tori, Cartan subalgebras, roots, Weyl groups, weights, characters, singlet projection, centers, and QFT group data.](/figures/math-toolkit/compact-lie-group-structure.svg)

<figcaption>

Compactness turns representation theory into controlled unitary linear algebra. A connected compact Lie group is organized by a maximal torus $T$, its Cartan subalgebra $\mathfrak t$, roots of the adjoint action, weights of representations, the Weyl group $W=N(T)/T$, and global lattice data. In QFT these structures become multiplets, charge lattices, color factors, Casimirs, indices, centers, and singlet projections.

</figcaption>
</figure>

For QFT, compact Lie groups are not just a clean mathematical class. They are what make internal symmetry compatible with positive-definite Hilbert spaces and finite-multiplet particle states. Noncompact internal symmetry would generically force infinite-dimensional unitary multiplets or negative-norm trouble. Tiny caveat monster: spacetime symmetry is different. The Lorentz and Poincaré groups are noncompact, but they act on spacetime and momentum, not as ordinary finite internal multiplets.

## Prerequisites

You should know [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/) and [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/). You should also know [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/), since $SU(2)$ is the rank-one model for compact representation theory.

The contrast with spacetime symmetry is explained in [Poincaré Group](/math-toolkit/groups-representations/poincare-group/). Compact internal groups and noncompact spacetime groups play different roles in QFT.

We use physics conventions: compact-group generators are Hermitian in unitary representations, and commutators carry an explicit $i$:

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

The common fundamental-representation normalization for $SU(N)$ is

$$
\operatorname{tr}_F(T^aT^b)=\frac12\delta^{ab}.
$$

## Core idea

A compact connected Lie group is controlled by the largest commuting compact subgroup inside it: a maximal torus

$$
T\cong U(1)^r.
$$

The integer $r$ is the rank of the group. The Lie algebra of $T$ is the Cartan subalgebra

$$
\mathfrak t\subset\mathfrak g.
$$

Because the Cartan generators commute, they can be simultaneously diagonalized in any finite-dimensional unitary representation. Their eigenvalues are weights.

In the adjoint representation, the nonzero eigenvalues of the Cartan subalgebra are roots. Roots tell us how the nonabelian generators are arranged around the commuting Cartan directions. Weights tell us how a representation decomposes under the maximal torus.

The Weyl group is a finite reflection group

$$
W=N(T)/T,
$$

where $N(T)$ is the normalizer of $T$ in $G$. The Weyl group identifies different points in the Cartan subalgebra that are related by the original nonabelian group. It is the remnant of nonabelian symmetry after reducing to the maximal torus.

For connected compact semisimple groups, irreducible representations are classified by dominant integral highest weights. This is the high-level slogan:

$$
\text{irreducible representations}
\longleftrightarrow
\text{dominant integral weights compatible with the global form of }G.
$$

The phrase "compatible with the global form" matters. The Lie algebra $\mathfrak{su}(2)$ can integrate to both

$$
SU(2)
$$

and

$$
SO(3)\cong SU(2)/\mathbb Z_2.
$$

The local algebra is the same, but the allowed representations differ. Half-integer spins are representations of $SU(2)$, not honest representations of $SO(3)$.

## Setup and conventions

Let $G$ be a compact Lie group with Lie algebra $\mathfrak g$. A representation is a homomorphism

$$
\rho:G\to GL(V),
$$

where $V$ is a complex vector space. If $G$ is compact, then any finite-dimensional representation can be made unitary. Concretely, start with any positive-definite Hermitian inner product $(\cdot,\cdot)_0$ on $V$ and average it over the group:

$$
(v,w)=\int_G dg\, (\rho(g)v,\rho(g)w)_0.
$$

The Haar measure is normalized so that

$$
\int_G dg=1.
$$

The averaged inner product is $G$-invariant:

$$
(\rho(h)v,\rho(h)w)=(v,w).
$$

Therefore $\rho(g)$ is unitary with respect to this inner product.

Differentiating the representation gives a Lie algebra representation

$$
d\rho:\mathfrak g\to \operatorname{End}(V).
$$

In physics notation, one often writes the Hermitian generators as $T^a_R$ in a representation $R$, with finite group elements

$$
\rho_R(e^{i\theta_aT^a})=e^{i\theta_aT_R^a}.
$$

Some mathematics references use anti-Hermitian generators instead. Then the explicit $i$ disappears from commutators. The two conventions are equivalent, but mixing them is a reliable way to anger every sign in the room.

## Compactness and unitary representations

Compactness makes representation theory behave like finite-dimensional quantum mechanics.

First, compactness gives a Haar measure $dg$ invariant under left and right multiplication:

$$
\int_G dg\,f(g)=\int_G dg\,f(hg)=\int_G dg\,f(gh).
$$

Second, Haar averaging makes finite-dimensional representations unitary. This is why finite multiplets of compact internal symmetries can live in a positive-definite Hilbert space.

Third, unitary representations are completely reducible. If $W\subset V$ is an invariant subspace, then its orthogonal complement $W^\perp$ is also invariant. Therefore

$$
V=W\oplus W^\perp.
$$

Repeating this decomposition splits $V$ into irreducible pieces.

Fourth, Schur's lemma becomes a powerful computational tool. If $A:V_R\to V_S$ intertwines two irreducible representations, then

$$
A\rho_R(g)=\rho_S(g)A
$$

for all $g\in G$ implies

$$
A=0
$$

unless $R\cong S$, and if $R=S$ then $A$ is a scalar multiple of the identity.

This is the linear algebra behind selection rules, character orthogonality, Casimir eigenvalues, and invariant tensor counting.

## Maximal tori, rank, and Cartan subalgebras

A torus is a compact connected abelian Lie group:

$$
T\cong U(1)^r.
$$

A maximal torus of a compact connected Lie group $G$ is a torus not contained in any larger torus. All maximal tori in $G$ are conjugate. The dimension of a maximal torus is the rank:

$$
\operatorname{rank}G=\dim T.
$$

Examples:

| group | rank | dimension | common role |
|---|---:|---:|---|
| $U(1)$ | $1$ | $1$ | abelian charge |
| $SU(N)$ | $N-1$ | $N^2-1$ | special unitary flavor or color |
| $SO(N)$ | $\lfloor N/2\rfloor$ | $N(N-1)/2$ | real vector symmetry |
| $Sp(N)$ | $N$ | $N(2N+1)$ | pseudoreal symplectic symmetry |

Here $Sp(N)$ means the compact symplectic group often written $USp(2N)$ in particle physics.

The Lie algebra of a maximal torus is a Cartan subalgebra:

$$
\mathfrak t=\operatorname{Lie}(T).
$$

For compact groups, it is often convenient to choose Hermitian Cartan generators

$$
H_i,
\qquad
[H_i,H_j]=0,
\qquad
 i,j=1,\ldots,r.
$$

In a representation $R$, one can diagonalize all $H_i$ simultaneously:

$$
H_i|\lambda\rangle=\lambda_i|\lambda\rangle.
$$

The vector

$$
\lambda=(\lambda_1,\ldots,\lambda_r)
$$

is a weight of the representation.

For $SU(2)$, the maximal torus is generated by $J_3$, and the weights are the familiar angular-momentum eigenvalues

$$
m=-j,-j+1,\ldots,j.
$$

Everything in compact representation theory is a sophisticated generalization of that ladder.

## Roots, weights, and the Weyl group

After complexifying the Lie algebra,

$$
\mathfrak g_\mathbb C=\mathfrak g\otimes_\mathbb R\mathbb C,
$$

the Cartan subalgebra acts diagonally on the adjoint representation. The decomposition is

$$
\mathfrak g_\mathbb C
=\mathfrak t_\mathbb C\oplus\bigoplus_{\alpha\in\Delta}\mathfrak g_\alpha,
$$

where $\Delta$ is the root system. For $E_\alpha\in\mathfrak g_\alpha$,

$$
[H_i,E_\alpha]=\alpha_iE_\alpha.
$$

The vector

$$
\alpha=(\alpha_1,\ldots,\alpha_r)
$$

is a root. Roots are the nonzero weights of the adjoint representation.

Weights of a general representation $R$ are eigenvalues of the Cartan generators on $V_R$:

$$
V_R=\bigoplus_{\lambda}V_{R,\lambda}.
$$

The root generators shift weights:

$$
E_\alpha:V_{R,\lambda}\to V_{R,\lambda+\alpha}.
$$

This is the general version of the $SU(2)$ ladder operators $J_+$ and $J_-$.

The Weyl group acts on $\mathfrak t^*$ by reflections. For each root $\alpha$, the reflection is

$$
s_\alpha(\lambda)=\lambda-2\frac{(\lambda,\alpha)}{(\alpha,\alpha)}\alpha.
$$

The Weyl group identifies weights related by the nonabelian symmetry. Characters, tensor products, and integration formulas often become manageable after reducing to the maximal torus and quotienting by the Weyl group.

A choice of positive roots splits the root system into

$$
\Delta=\Delta_+\cup\Delta_-.
$$

A set of simple roots

$$
\alpha_1,\ldots,\alpha_r
$$

forms a basis such that every positive root is a nonnegative integer combination of simple roots.

The Cartan matrix is

$$
A_{ij}=2\frac{(\alpha_i,\alpha_j)}{(\alpha_j,\alpha_j)}.
$$

It encodes the Dynkin diagram of the semisimple Lie algebra.

## Highest weights and irreducible representations

For a compact connected simply connected semisimple Lie group, finite-dimensional irreducible representations are classified by dominant integral highest weights.

The fundamental weights $\omega_i$ are defined by

$$
2\frac{(\omega_i,\alpha_j)}{(\alpha_j,\alpha_j)}=\delta_{ij}.
$$

A dominant integral weight is

$$
\lambda=\sum_{i=1}^r n_i\omega_i,
\qquad
n_i\in\mathbb Z_{\ge0}.
$$

The nonnegative integers $n_i$ are the Dynkin labels of the representation.

The highest-weight construction says:

1. choose a dominant integral weight $\lambda$;
2. introduce a highest-weight state $|\lambda\rangle$ annihilated by all raising operators $E_\alpha$ for $\alpha\in\Delta_+$;
3. act with lowering operators to generate the representation;
4. quotient out null or redundant descendants according to the Lie algebra relations.

For $SU(2)$, there is one simple root and one Dynkin label. The spin-$j$ representation has highest weight

$$
\lambda=2j\,\omega,
$$

so the Dynkin label is

$$
n=2j.
$$

Thus $n=0,1,2,3,\ldots$ corresponds to

$$
j=0,\frac12,1,\frac32,\ldots.
$$

For $SU(3)$, there are two fundamental weights. Irreducible representations are labeled by two nonnegative integers

$$
(p,q).
$$

The fundamental triplet is $(1,0)$, the anti-fundamental is $(0,1)$, and the adjoint is $(1,1)$.

## Centers, global forms, and representation lattices

The Lie algebra does not determine the global group uniquely. Different compact Lie groups may have the same Lie algebra.

The cleanest example is

$$
SU(2)\to SO(3)\cong SU(2)/\mathbb Z_2.
$$

Both have Lie algebra $\mathfrak{su}(2)$, but their representations differ. The irreducible representations of $SU(2)$ have

$$
j=0,\frac12,1,\frac32,\ldots,
$$

while the honest representations of $SO(3)$ have only

$$
j=0,1,2,\ldots.
$$

The center of $SU(N)$ is

$$
Z(SU(N))\cong\mathbb Z_N,
$$

generated by

$$
e^{2\pi i/N}\mathbf 1_N.
$$

The quotient

$$
PSU(N)=SU(N)/\mathbb Z_N
$$

has the same Lie algebra $\mathfrak{su}(N)$ but a different set of allowed representations.

In gauge theory, this difference is not philosophical glitter. It changes the spectrum of genuine Wilson lines, the one-form global symmetry, the allowed bundles, the topological sectors, and sometimes the discrete theta angles. Perturbative Feynman rules only see the Lie algebra, but nonperturbative and global questions can see the global form of the gauge group.

Representation lattices organize this distinction. For a simply connected compact semisimple group, all dominant integral weights occur. For a quotient by a subgroup of the center, only weights on which the quotient kernel acts trivially define honest representations.

The slogan is:

$$
\text{Lie algebra} \Rightarrow \text{local interactions},
$$

but

$$
\text{global group form} \Rightarrow \text{allowed charges and line operators}.
$$

## Invariant tensors, Casimirs, and indices

QFT calculations rarely need the entire representation theory of a compact group. They often need a smaller list of group data:

- dimensions of representations;
- quadratic Casimirs;
- Dynkin indices;
- invariant tensors;
- branching rules under subgroups;
- tensor-product decompositions;
- center charges.

Let $T_R^a$ be Hermitian generators in a representation $R$ of a compact simple Lie algebra. Define the Dynkin index $T(R)$ by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

Define the quadratic Casimir $C_2(R)$ by

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

Taking the trace of the Casimir equation gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=C_2(R)\dim R.
$$

Using the Dynkin-index definition and summing over $a=1,\ldots,\dim G$ gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=T(R)\dim G.
$$

Therefore

$$
C_2(R)\dim R=T(R)\dim G.
$$

For $SU(N)$ with

$$
\operatorname{tr}_F(T^aT^b)=\frac12\delta^{ab},
$$

the fundamental representation has

$$
T(F)=\frac12,
$$

and

$$
C_2(F)=\frac{N^2-1}{2N}.
$$

The adjoint representation has

$$
T(\operatorname{adj})=C_2(\operatorname{adj})=N.
$$

These constants appear in one-loop beta functions, anomaly coefficients, color factors, current two-point functions, and large-$N$ counting.

Invariant tensors are group-invariant elements in tensor products. For example, an invariant bilinear form on $R$ corresponds to a singlet inside

$$
R\otimes R
$$

or

$$
R\otimes R^*.
$$

Invariant tensors are the representation-theoretic reason certain interaction terms are allowed in a Lagrangian.

## Haar measure, characters, and singlet projection

The character of a representation $R$ is

$$
\chi_R(g)=\operatorname{tr}_R\rho_R(g).
$$

Characters are class functions:

$$
\chi_R(hgh^{-1})=\chi_R(g).
$$

For compact groups, irreducible characters obey orthogonality:

$$
\int_G dg\,\chi_R(g)^*\chi_S(g)=\delta_{RS}.
$$

This is the group-theory analogue of Fourier orthogonality. In fact, for compact abelian groups, it reduces to ordinary Fourier series on a torus.

Averaging over the group projects onto invariants. If $V$ is a representation, define

$$
\Pi_{\operatorname{inv}}=\int_G dg\,\rho(g).
$$

Then

$$
\rho(h)\Pi_{\operatorname{inv}}
=\int_G dg\,\rho(hg)
=\int_G dg\,\rho(g)
=\Pi_{\operatorname{inv}},
$$

so the image of $\Pi_{\operatorname{inv}}$ lies in the invariant subspace. Also

$$
\Pi_{\operatorname{inv}}^2=\Pi_{\operatorname{inv}}.
$$

Thus it is a projection operator.

For a tensor product

$$
V=V_{R_1}\otimes\cdots\otimes V_{R_n},
$$

the number of singlets is

$$
\dim V^G
=\int_G dg\,\chi_{R_1}(g)\cdots\chi_{R_n}(g),
$$

with complex conjugation inserted if a dual representation is explicitly present. This formula is a compact way to count invariant couplings and gauge singlets.

For $U(1)$, the same formula says that charges must sum to zero. If

$$
\chi_q(e^{i\theta})=e^{iq\theta},
$$

then

$$
\int_0^{2\pi}\frac{d\theta}{2\pi}e^{i(q_1+\cdots+q_n)\theta}
=\delta_{q_1+\cdots+q_n,0}.
$$

That is the simplest singlet-projection rule.

## Compact groups in QFT

Compact Lie groups enter QFT in several distinct ways.

First, they describe global internal symmetries. States and operators are organized into multiplets, and selection rules follow from representation theory.

Second, they describe gauge groups. In Yang–Mills theory, the local gauge field takes values in the Lie algebra:

$$
A_\mu=A_\mu^aT^a.
$$

The perturbative vertices use the structure constants

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

But the nonperturbative theory may depend on the global form of the group, not just the Lie algebra.

Third, compact groups classify matter representations. A scalar, fermion, or line operator may transform in a representation $R$. Whether $R$ is real, complex, or pseudoreal affects possible mass terms, symmetry breaking patterns, anomalies, and flavor symmetries.

Fourth, compact groups appear through maximal tori and characters in finite-temperature partition functions, matrix models, lattice gauge theory, localization, and group-integral formulas.

Fifth, centers of compact groups lead to higher-form symmetries. Pure $SU(N)$ Yang–Mills has a center one-form symmetry $\mathbb Z_N$ acting on Wilson lines, while adding matter in representations charged under the center can break that symmetry.

Sixth, compact groups organize topological terms and bundles. The instanton number, monopole charges, characteristic classes, and global anomalies all know about the group and its global form.

This is why a QFT page that says only "take gauge group $G$ with Lie algebra $\mathfrak g$" may be leaving out important information. For perturbation theory near the identity, $\mathfrak g$ may be enough. For line operators, bundles, defects, and anomalies, $G$ matters.

## Common pitfalls

**Confusing compactness with finite size of matrices.** A group can be represented by finite matrices and still be noncompact. For example, $SL(2,\mathbb C)$ is a finite-dimensional matrix group but is not compact.

**Thinking the Lie algebra determines all physics.** The Lie algebra determines local infinitesimal transformations. The global group determines allowed representations, center charges, bundles, and line operators.

**Forgetting the quotient.** $SU(2)$ and $SO(3)$ have the same Lie algebra but different representations. Saying "the gauge algebra is $\mathfrak{su}(2)$" does not specify the full gauge group.

**Mixing Hermitian and anti-Hermitian conventions.** Physics generators are often Hermitian and obey $[T^a,T^b]=if^{ab}{}_{c}T^c$. Mathematics generators are often anti-Hermitian and obey brackets without an explicit $i$.

**Calling every commuting set a Cartan subalgebra.** In compact connected Lie groups, a Cartan subalgebra is the Lie algebra of a maximal torus. It is maximal abelian in the relevant compact sense.

**Assuming every representation of the Lie algebra integrates to every group with that algebra.** A representation of $\mathfrak{su}(2)$ with $j=\frac12$ integrates to $SU(2)$ but not to $SO(3)$.

**Ignoring the center.** The center may act trivially on local adjoint fields but nontrivially on Wilson lines or matter representations. In modern QFT, that is often the whole plot.

## Relations to other pages

[SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/) is the rank-one model for compact representation theory, including weights, ladders, tensor products, and characters.

[Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/) explains local versus global group structure, exponentiation, and the difference between a Lie algebra and a Lie group.

[Poincaré Group](/math-toolkit/groups-representations/poincare-group/) is the main contrast case: spacetime symmetry is noncompact, and its unitary irreducible representations are infinite-dimensional momentum-orbit representations.

[SL(2,C) and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/) shows why Lorentz spinor representations are finite-dimensional but nonunitary, unlike finite-dimensional representations of compact internal groups.

Later pages in this chapter develop roots, weights, Dynkin diagrams, characters, Young tableaux, and gauge-group data more explicitly.

## Research status

The classification of compact connected Lie groups and their finite-dimensional irreducible representations is established mathematics. The Cartan–Weyl classification, Dynkin diagrams, highest weights, character formulas, and Haar integration are mature tools.

The active QFT frontier lies in how global form data are used. Centers, quotient groups, representation lattices, higher-form symmetries, line-operator spectra, discrete theta angles, non-invertible defects, anomalies, and global structures of gauge theory remain central in modern research. The underlying compact Lie group theory is settled; its physical deployment is very much alive.

## Exercises

### Exercise 1

Let $\rho:G\to GL(V)$ be a finite-dimensional representation of a compact Lie group. Starting from an arbitrary positive-definite Hermitian inner product $(\cdot,\cdot)_0$, define

$$
(v,w)=\int_G dg\,(\rho(g)v,\rho(g)w)_0.
$$

Show that this averaged inner product is $G$-invariant.

<details><summary><strong>Solution</strong></summary>

We need to show

$$
(\rho(h)v,\rho(h)w)=(v,w)
$$

for all $h\in G$. By definition,

$$
(\rho(h)v,\rho(h)w)
=\int_G dg\,(\rho(g)\rho(h)v,\rho(g)\rho(h)w)_0.
$$

Using $\rho(g)\rho(h)=\rho(gh)$,

$$
(\rho(h)v,\rho(h)w)
=\int_G dg\,(\rho(gh)v,\rho(gh)w)_0.
$$

The Haar measure is right-invariant, so the change of variables

$$
g'=gh
$$

leaves $dg$ unchanged. Therefore

$$
(\rho(h)v,\rho(h)w)
=\int_G dg'\,(\rho(g')v,\rho(g')w)_0
=(v,w).
$$

Thus the representation is unitary with respect to the averaged inner product.

</details>

### Exercise 2

Show that

$$
\Pi=\int_G dg\,\rho(g)
$$

is a projection onto the invariant subspace $V^G$.

<details><summary><strong>Solution</strong></summary>

First, show that the image is invariant. For any $h\in G$,

$$
\rho(h)\Pi
=\int_G dg\,\rho(hg).
$$

By left-invariance of Haar measure, the change of variables $g'=hg$ gives

$$
\rho(h)\Pi
=\int_G dg'\,\rho(g')
=\Pi.
$$

Thus $\rho(h)(\Pi v)=\Pi v$, so $\Pi v\in V^G$.

Second,

$$
\Pi^2
=\int_G dg\int_G dh\,\rho(g)\rho(h)
=\int_G dg\int_G dh\,\rho(gh).
$$

For fixed $g$, use $k=gh$. Haar measure gives $dh=dk$, so

$$
\Pi^2
=\int_G dg\int_G dk\,\rho(k)
=\left(\int_G dg\right)\Pi.
$$

With normalized Haar measure,

$$
\int_G dg=1,
$$

so

$$
\Pi^2=\Pi.
$$

Finally, if $v\in V^G$, then $\rho(g)v=v$ for all $g$, so

$$
\Pi v=\int_G dg\,v=v.
$$

Therefore $\Pi$ projects onto $V^G$.

</details>

### Exercise 3

For $SU(2)$, explain why the spin-$j$ representation has weights

$$
m=-j,-j+1,\ldots,j.
$$

Identify the highest weight and the Dynkin label.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$, choose the Cartan generator

$$
H=J_3.
$$

A spin-$j$ representation has basis states $|j,m\rangle$ satisfying

$$
J_3|j,m\rangle=m|j,m\rangle.
$$

The ladder operators

$$
J_+=J_1+iJ_2,
\qquad
J_-=J_1-iJ_2
$$

shift $m$ by $+1$ and $-1$. Finite-dimensionality forces a highest value and a lowest value. In the spin-$j$ representation, these are

$$
m=j
$$

and

$$
m=-j.
$$

Thus the weights are

$$
-j,-j+1,\ldots,j.
$$

The highest weight is $j$ in angular-momentum normalization. In Dynkin-label normalization, the fundamental weight corresponds to spin $\frac12$, so the Dynkin label is

$$
n=2j.
$$

Thus spin $j=\frac12$ has Dynkin label $1$, spin $j=1$ has Dynkin label $2$, and so on.

</details>

### Exercise 4

Compute the rank, dimension, and center of $SU(N)$.

<details><summary><strong>Solution</strong></summary>

An element of $SU(N)$ is an $N\times N$ unitary matrix with determinant $1$.

A maximal torus consists of diagonal matrices

$$
\operatorname{diag}(e^{i\theta_1},\ldots,e^{i\theta_N})
$$

with determinant one:

$$
\sum_{i=1}^N\theta_i=0
\quad \text{mod }2\pi.
$$

There are $N-1$ independent angles, so

$$
\operatorname{rank}SU(N)=N-1.
$$

The Lie algebra $\mathfrak{su}(N)$ consists of traceless Hermitian generators in physics convention. Hermitian $N\times N$ matrices have real dimension $N^2$. The traceless condition removes one dimension, so

$$
\dim SU(N)=N^2-1.
$$

The center consists of matrices proportional to the identity that also have determinant one:

$$
z=e^{i\theta}\mathbf 1_N,
\qquad
z^N=e^{iN\theta}=1.
$$

Therefore

$$
e^{i\theta}=e^{2\pi ik/N},
\qquad
k=0,1,\ldots,N-1,
$$

and

$$
Z(SU(N))\cong\mathbb Z_N.
$$

</details>

### Exercise 5

Using

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}
$$

and

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R,
$$

show that

$$
C_2(R)\dim R=T(R)\dim G.
$$

<details><summary><strong>Solution</strong></summary>

Take the trace of the Casimir equation:

$$
\operatorname{tr}_R(T_R^aT_R^a)
=\operatorname{tr}_R(C_2(R)\mathbf 1_R)
=C_2(R)\dim R.
$$

On the other hand, using the Dynkin-index definition and summing over $a$,

$$
\operatorname{tr}_R(T_R^aT_R^a)
=T(R)\delta^{aa}.
$$

The index $a$ runs over a basis of the Lie algebra, so

$$
\delta^{aa}=\dim G.
$$

Therefore

$$
\operatorname{tr}_R(T_R^aT_R^a)=T(R)\dim G.
$$

Equating the two expressions gives

$$
C_2(R)\dim R=T(R)\dim G.
$$

</details>

### Exercise 6

Explain why the spin-$\frac12$ representation of $\mathfrak{su}(2)$ integrates to a representation of $SU(2)$ but not to a representation of $SO(3)$.

<details><summary><strong>Solution</strong></summary>

The groups are related by

$$
SO(3)\cong SU(2)/\mathbb Z_2,
$$

where the kernel of the covering map is

$$
\{+\mathbf 1,-\mathbf 1\}\subset SU(2).
$$

A representation of $SU(2)$ descends to $SO(3)$ only if the kernel acts trivially.

In the spin-$j$ representation, the central element $-\mathbf 1$ acts as

$$
(-1)^{2j}\mathbf 1.
$$

For $j=\frac12$,

$$
(-1)^{2j}=(-1)^1=-1.
$$

Thus $-\mathbf 1$ acts nontrivially. The spin-$\frac12$ representation is an honest representation of $SU(2)$, but not of $SO(3)$.

For integer $j$, $(-1)^{2j}=+1$, so those representations do descend to $SO(3)$.

</details>

## References

- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for compact Lie groups, maximal tori, weights, roots, and representation theory with a friendly mathematical style.
- H. Georgi, *Lie Algebras in Particle Physics*, for roots, weights, Dynkin diagrams, tensor products, and particle-physics normalization conventions.
- W. Fulton and J. Harris, *Representation Theory*, for highest-weight representations and classical groups.
- A. W. Knapp, *Lie Groups Beyond an Introduction*, for compact Lie groups, Weyl groups, characters, and structure theory.
- W.-K. Tung, *Group Theory in Physics*, and J. F. Cornwell, *Group Theory in Physics*, for physics-oriented compact-group representation theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for internal symmetries, representations, gauge groups, and Lie-algebra conventions in QFT.
- M. Srednicki, *Quantum Field Theory*, for nonabelian symmetries, group representations, gauge theory, and group factors in perturbation theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for Lie groups in Yang–Mills theory, Standard Model representations, and practical group factors.
- S. Coleman, *Aspects of Symmetry*, for physical uses of compact groups, unitary symmetry, current algebra, and spontaneous symmetry breaking.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, "Generalized Global Symmetries," for modern QFT uses of centers and higher-form symmetries.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
