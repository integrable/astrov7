---
title: "Roots, Weights, and Dynkin Diagrams"
description: "A QFT-oriented guide to Cartan subalgebras, roots, weights, coroots, Weyl chambers, highest weights, Dynkin labels, and Dynkin diagrams."
sidebar:
  label: "Roots, Weights, and Dynkin Diagrams"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard Lie theory and QFT references, including Hall, Georgi, Fulton–Harris, Humphreys, Knapp, Cornwell, Tung, Weinberg, Srednicki, Coleman, Schwartz, and Zee."
topics:
  - roots
  - weights
  - Dynkin diagrams
  - Cartan subalgebras
  - Weyl groups
  - highest weights
  - representation theory
canonicalTopics:
  - roots-and-weights
  - dynkin-diagrams
  - cartan-subalgebra
  - weyl-group
  - highest-weight-representations
  - lie-algebra-representation-theory
researchStatus:
  established:
    - "The root, weight, Weyl-group, and Dynkin-diagram classification of finite-dimensional representations of compact connected semisimple Lie groups is a standard complete theory, modulo global-form restrictions on which weights exponentiate to honest group representations."
  active:
    - "In modern QFT, the same lattice data enters line-operator spectra, centers, higher-form symmetries, monopole charges, Coulomb branches, localization formulas, anomaly constraints, and global choices of gauge group."
---

## Summary

Roots and weights are the coordinate system in which nonabelian symmetry becomes computable.

A compact connected Lie group can look intimidating as a curved noncommutative manifold, but near any maximal torus it is governed by ordinary linear algebra. Choose commuting Cartan generators. Then every finite-dimensional representation decomposes into simultaneous eigenspaces. The eigenvalues are **weights**. In the adjoint representation, the nonzero weights are **roots**. Roots describe the charged non-Cartan generators of the Lie algebra; weights describe the charges of states or fields in a chosen representation.

The entire classification of finite-dimensional irreducible representations of a compact connected semisimple Lie algebra is organized by a simple statement:

$$
\text{irreducible representations}
\longleftrightarrow
\text{dominant integral highest weights}.
$$

Dynkin diagrams are a compact graphical encoding of the simple roots. They classify the complex simple Lie algebras and give a practical language for representations through Dynkin labels.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing roots, weights, simple roots, Cartan matrices, Dynkin labels, and their QFT uses.](/figures/math-toolkit/roots-weights-dynkin-map.svg)

<figcaption>

Roots and weights are dual pieces of Cartan data. Roots come from the adjoint action $[H,E_\alpha]=\alpha(H)E_\alpha$, weights come from $H|\mu\rangle=\mu(H)|\mu\rangle$, simple roots define the Cartan matrix $A_{ij}=\langle\alpha_i^\vee,\alpha_j\rangle$, and dominant highest weights are recorded by Dynkin labels $n_i=\langle\alpha_i^\vee,\lambda\rangle$. In QFT this becomes the language of charges, gauge bosons, matter multiplets, Weyl identifications, centers, Wilson lines, and monopoles.

</figcaption>
</figure>

In QFT, this language appears everywhere: isospin multiplets, color representations, gauge boson charges, Wilson lines, monopoles, centers, anomaly coefficients, localization matrix models, and spontaneous breaking to Cartan subgroups. It is the difference between saying “the field is in some representation” and actually computing what that representation does.

## Prerequisites

You should know [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/), [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/), [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/), and [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/).

The rank-one model is $SU(2)$. If the words “Cartan generator,” “raising operator,” “lowering operator,” and “highest-weight state” feel fuzzy, first review angular momentum. The whole general theory is a many-dimensional version of the $J_3,J_+,J_-$ story.

We use physics conventions for compact groups: generators in unitary representations are Hermitian and commutators include an explicit $i$,

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

For abstract root theory, it is often convenient to complexify the Lie algebra and work with root vectors $E_\alpha$. The invariant inner product on the weight space is conventionally normalized so that long roots have length squared $2$ unless stated otherwise. This is a mathematical normalization of the root system; it need not be identical to every trace normalization used in perturbative gauge theory.

## Core idea

A compact connected Lie group $G$ has maximal commuting compact subgroups called maximal tori,

$$
T\cong U(1)^r.
$$

The integer $r$ is the rank. The Lie algebra of $T$ is a Cartan subalgebra, written here as $\mathfrak h$ after complexification. Since the Cartan generators commute, they can be diagonalized simultaneously in any finite-dimensional representation.

If $R$ is a representation on $V_R$, then

$$
V_R=\bigoplus_{\mu} V_\mu,
$$

where

$$
V_\mu=\{v\in V_R: H v=\mu(H)v\text{ for every }H\in\mathfrak h\}.
$$

The linear functional $\mu\in\mathfrak h^*$ is a weight. Its multiplicity is

$$
m_\mu=\dim V_\mu.
$$

Now apply the same idea to the adjoint representation of the Lie algebra on itself. One has

$$
\mathfrak g_\mathbb C
=\mathfrak h\oplus\bigoplus_{\alpha\in\Phi}\mathfrak g_\alpha,
$$

where

$$
\mathfrak g_\alpha
=\{X\in\mathfrak g_\mathbb C:[H,X]=\alpha(H)X\text{ for every }H\in\mathfrak h\}.
$$

The nonzero functionals $\alpha$ are roots. For a complex semisimple Lie algebra, each root space is one-dimensional.

So weights are the Cartan charges of a representation; roots are the Cartan charges of the Lie algebra itself.

That single distinction is worth tattooing on the chalkboard:

$$
\text{weights classify states in a representation},
\qquad
\text{roots classify non-Cartan generators}.
$$

## Setup and conventions

Let $\mathfrak g$ be the complexification of the Lie algebra of a compact connected semisimple Lie group. Choose a Cartan subalgebra $\mathfrak h\subset\mathfrak g$. The dual vector space $\mathfrak h^*$ contains roots and weights.

The invariant inner product on $\mathfrak g$ restricts to $\mathfrak h$ and induces an inner product on $\mathfrak h^*$. We write it as

$$
(\lambda,\mu)
$$

for weights and roots. For each root $\alpha$, define the coroot

$$
\alpha^\vee=\frac{2\alpha}{(\alpha,\alpha)},
$$

where the inner product is being used to identify $\mathfrak h^*$ with $\mathfrak h$. The canonical pairing is

$$
\langle \alpha^\vee,\lambda\rangle
=\frac{2(\alpha,\lambda)}{(\alpha,\alpha)}.
$$

This pairing is the integral object. Many formulas are cleaner when written using coroots rather than roots.

A weight $\lambda$ is integral if

$$
\langle\alpha^\vee,\lambda\rangle\in\mathbb Z
$$

for every root $\alpha$. A weight is dominant if

$$
\langle\alpha_i^\vee,\lambda\rangle\in\mathbb Z_{\ge0}
$$

for every simple root $\alpha_i$.

The simple roots are a basis of roots chosen after declaring a notion of positivity. If the rank is $r$, there are $r$ simple roots,

$$
\alpha_1,\ldots,\alpha_r.
$$

The fundamental weights $\omega_i$ are the dual basis to the simple coroots:

$$
\langle\alpha_i^\vee,\omega_j\rangle=\delta_{ij}.
$$

Therefore every dominant integral highest weight can be written uniquely as

$$
\lambda=\sum_{i=1}^r n_i\omega_i,
\qquad
n_i\in\mathbb Z_{\ge0}.
$$

The integers $n_i$ are the Dynkin labels of the representation.

## Cartan subalgebras and simultaneous charges

The Cartan subalgebra is the maximal commuting part of the Lie algebra. In a compact group, it is the infinitesimal version of a maximal torus.

For $SU(N)$, a standard Cartan subalgebra consists of traceless diagonal matrices. A diagonal matrix has $N$ entries, but the tracelessness condition removes one, so

$$
\operatorname{rank} SU(N)=N-1.
$$

A representation of $SU(N)$ can be decomposed by the eigenvalues of these $N-1$ commuting Cartan generators. Those eigenvalues are weights.

This is exactly what happens for $SU(2)$ angular momentum. The Cartan subalgebra has one generator, usually $J_3$. The spin-$j$ representation has weights

$$
m=-j,-j+1,\ldots,j.
$$

For higher-rank groups, a weight is not one number but a vector of charges under the Cartan generators.

Physically, the Cartan subalgebra is what remains manifest when a nonabelian symmetry is reduced to its maximal commuting set. In gauge theory, for example, moving onto a generic Coulomb branch breaks

$$
G\to U(1)^r
$$

up to global subtleties. Matter fields then have abelian charges given by their weights, while off-diagonal gauge bosons have charges given by roots.

## Roots from the adjoint representation

The adjoint representation is the action of the Lie algebra on itself:

$$
\operatorname{ad}_X(Y)=[X,Y].
$$

For $H\in\mathfrak h$, the adjoint action can be diagonalized. The Cartan generators themselves have zero weight because

$$
[H,H']=0
$$

for $H,H'\in\mathfrak h$. The remaining generators come in root spaces. For each root $\alpha$, choose a root vector $E_\alpha$ satisfying

$$
[H,E_\alpha]=\alpha(H)E_\alpha.
$$

The root vector $E_\alpha$ is a raising or lowering operator for weights. If $v$ has weight $\mu$, then

$$
H(E_\alpha v)=([H,E_\alpha]+E_\alpha H)v
=(\alpha(H)+\mu(H))E_\alpha v.
$$

So either $E_\alpha v=0$, or $E_\alpha v$ has weight

$$
\mu+\alpha.
$$

Roots are therefore the allowed steps between weights inside a representation.

This is the higher-rank version of

$$
[J_3,J_\pm]=\pm J_\pm.
$$

The roots of $\mathfrak{su}(2)$ are $+\alpha$ and $-\alpha$, and $J_\pm$ move weights by those roots.

## Positive roots and simple roots

The set of roots $\Phi$ is symmetric:

$$
\alpha\in\Phi
\quad\Longrightarrow\quad
-\alpha\in\Phi.
$$

To speak about highest weights, we choose which roots are positive. This is not extra physics; it is a convention equivalent to choosing a Weyl chamber.

A positive root is simple if it cannot be written as a sum of two positive roots. The simple roots

$$
\alpha_1,\ldots,\alpha_r
$$

form a basis for the root lattice. Every root can be written either as a nonnegative or a nonpositive integer combination of simple roots.

For $SU(3)$, the root system is type $A_2$. There are two simple roots,

$$
\alpha_1,
\qquad
\alpha_2,
$$

and the positive roots are

$$
\alpha_1,
\qquad
\alpha_2,
\qquad
\alpha_1+\alpha_2.
$$

The root vectors associated with positive roots act as raising operators relative to the chosen positive system. A highest-weight vector $v_\lambda$ is a vector annihilated by all positive-root generators:

$$
E_{\alpha_i}v_\lambda=0
\qquad
\text{for all simple }\alpha_i.
$$

The representation is then generated by applying lowering operators $E_{-\alpha_i}$.

## Coroots and integrality

The coroot attached to a root is

$$
\alpha^\vee=\frac{2\alpha}{(\alpha,\alpha)}.
$$

Why not just use roots? Because representation-theoretic integrality is controlled by the pairing with coroots:

$$
\langle\alpha^\vee,\lambda\rangle\in\mathbb Z.
$$

This condition reduces to familiar angular-momentum integrality in each $SU(2)$ subalgebra generated by a root. Every root $\alpha$ defines an $\mathfrak{su}(2)$-type subalgebra spanned by

$$
E_\alpha,
\qquad
E_{-\alpha},
\qquad
H_\alpha.
$$

In that subalgebra, the number

$$
\langle\alpha^\vee,\lambda\rangle
$$

is the highest weight measured in $SU(2)$ units. The reason it must be an integer is the same reason finite angular-momentum multiplets have integral spacing.

This is also why long and short roots matter. If all roots have the same length, the algebra is simply laced. If not, roots and coroots differ nontrivially. In gauge theory, electric charges live naturally in a weight lattice, while magnetic charges live naturally in a coweight or coroot lattice. Langlands duality exchanges these structures.

## Cartan matrix

The Cartan matrix is the integer matrix

$$
A_{ij}=\langle\alpha_i^\vee,\alpha_j\rangle
=\frac{2(\alpha_i,\alpha_j)}{(\alpha_i,\alpha_i)}.
$$

It satisfies

$$
A_{ii}=2,
$$

and for $i\ne j$,

$$
A_{ij}\in\{0,-1,-2,-3\}.
$$

The product

$$
A_{ij}A_{ji}=4\cos^2\theta_{ij}
$$

encodes the angle between simple roots. The ratio

$$
\frac{A_{ij}}{A_{ji}}=\frac{(\alpha_j,\alpha_j)}{(\alpha_i,\alpha_i)}
$$

encodes relative root lengths.

For $A_2$, the simple roots have equal length and angle $120^\circ$, so

$$
A=
\begin{pmatrix}
2&-1\\
-1&2
\end{pmatrix}.
$$

For rank one, $A_1$, the Cartan matrix is just

$$
A=(2).
$$

The Cartan matrix is not the Killing metric and not the trace normalization of generators. It is an integer incidence structure built from simple roots and coroots.

## Dynkin diagrams

A Dynkin diagram encodes the Cartan matrix graphically.

The rules are:

- one node for each simple root;
- no line if $A_{ij}A_{ji}=0$;
- one line if $A_{ij}A_{ji}=1$;
- two lines if $A_{ij}A_{ji}=2$;
- three lines if $A_{ij}A_{ji}=3$;
- arrows point toward the shorter root.

The simply laced diagrams have only single lines. They are

$$
A_n,
\qquad
D_n,
\qquad
E_6,E_7,E_8.
$$

The non-simply-laced diagrams have roots of different lengths:

$$
B_n,
\qquad
C_n,
\qquad
F_4,
\qquad
G_2.
$$

The connected Dynkin diagrams classify complex simple Lie algebras. Compact connected simple Lie groups with the same Lie algebra can still differ by global form, but the Dynkin diagram fixes the local algebra.

For example,

$$
\mathfrak{su}(2)\cong\mathfrak{so}(3)
$$

has Dynkin diagram $A_1$. The groups $SU(2)$ and $SO(3)$ have the same roots and Dynkin diagram but different allowed representations.

## Fundamental weights and Dynkin labels

The fundamental weights are defined by

$$
\langle\alpha_i^\vee,\omega_j\rangle=\delta_{ij}.
$$

They are dual to the simple coroots, not generally to the simple roots under the naive Euclidean dot product. This distinction matters in non-simply-laced algebras.

Every dominant highest weight is

$$
\lambda=\sum_{i=1}^r n_i\omega_i,
$$

with

$$
n_i\in\mathbb Z_{\ge0}.
$$

The tuple

$$
(n_1,\ldots,n_r)
$$

is the Dynkin-label description of the irreducible representation.

For $SU(2)$, there is one fundamental weight $\omega$, and the highest weight is

$$
\lambda=n\omega.
$$

This corresponds to spin

$$
j=\frac n2,
$$

so the representation has dimension

$$
2j+1=n+1.
$$

For $SU(3)$, irreducible representations are labeled by two nonnegative integers,

$$
(p,q).
$$

The fundamental representation $\mathbf 3$ has highest weight

$$
\omega_1,
$$

so its Dynkin labels are

$$
(1,0).
$$

The antifundamental $\overline{\mathbf 3}$ has highest weight

$$
\omega_2,
$$

so its labels are

$$
(0,1).
$$

The adjoint $\mathbf 8$ has highest weight

$$
\omega_1+\omega_2,
$$

so its labels are

$$
(1,1).
$$

## Weight systems of representations

The highest-weight theorem says that, once the highest weight is known, the representation is fixed. The rest of the weights are obtained by descending with negative simple roots, subject to the finite-dimensional representation rules.

The set of weights in a representation forms a finite pattern in $\mathfrak h^*$. It is invariant under the Weyl group when multiplicities are included.

For $SU(2)$, the spin-$j$ representation has weights

$$
j,j-1,\ldots,-j.
$$

Each weight has multiplicity one.

For $SU(3)$, weight diagrams are two-dimensional. The fundamental $\mathbf 3$ has three weights forming a triangle. The adjoint $\mathbf 8$ has six nonzero weights equal to the roots, plus the zero weight with multiplicity two, corresponding to the two Cartan generators.

In a gauge theory, this distinction is very physical. For an $SU(3)$ gauge field, the gluons in the adjoint representation decompose under the Cartan as:

- two neutral Cartan gluons, with weight zero;
- six charged off-diagonal gluons, with charges equal to the six roots.

Matter fields in the fundamental representation instead carry the three fundamental weights.

## Weyl group and Weyl chambers

The Weyl group is generated by reflections in the hyperplanes perpendicular to roots. For a root $\alpha$, the reflection acts on a weight $\lambda$ by

$$
s_\alpha(\lambda)
=\lambda-\langle\alpha^\vee,\lambda\rangle\alpha.
$$

The Weyl group is finite. It is the leftover nonabelian identification after reducing to the Cartan. For $SU(N)$, the Weyl group is the symmetric group

$$
W(SU(N))\cong S_N,
$$

acting by permuting diagonal entries.

A Weyl chamber is a connected component of the complement of the reflection hyperplanes. The dominant chamber is defined by

$$
\langle\alpha_i^\vee,\lambda\rangle\ge0
$$

for all simple roots $\alpha_i$.

Every Weyl orbit meets the closure of the dominant chamber exactly once. This is why highest weights can be chosen dominant.

In gauge theory, the Weyl group is often a residual gauge redundancy. If a scalar field in the adjoint representation takes a value in the Cartan, then different points related by Weyl transformations describe the same physical vacuum. Thus a classical Coulomb branch is often locally

$$
\mathfrak h/W,
$$

possibly with additional quantum corrections and global identifications.

## Root and weight lattices

The root lattice is the integer span of the roots:

$$
Q=\operatorname{span}_{\mathbb Z}\{\alpha\in\Phi\}.
$$

The weight lattice is the lattice of integral weights:

$$
P=\{\lambda\in\mathfrak h^*: \langle\alpha^\vee,\lambda\rangle\in\mathbb Z\text{ for all roots }\alpha\}.
$$

The root lattice sits inside the weight lattice:

$$
Q\subseteq P.
$$

For a simply connected compact simple group, all dominant integral weights correspond to honest finite-dimensional representations. For a quotient group, only a sublattice of weights exponentiates.

For example, the Lie algebra $\mathfrak{su}(2)$ has weight lattice generated by $\omega$ and root lattice generated by

$$
\alpha=2\omega.
$$

The simply connected group $SU(2)$ allows all dominant weights

$$
n\omega,
\qquad
n\in\mathbb Z_{\ge0}.
$$

These are spin $j=n/2$ representations. The quotient group

$$
SO(3)\cong SU(2)/\mathbb Z_2
$$

allows only integer-spin representations, corresponding to even $n$.

This global-form subtlety is not optional in modern QFT. The same Lie algebra can define different gauge theories depending on which line operators are allowed and how the center acts.

## Centers and global form

For a simply connected compact simple group $\widetilde G$, the center is related to the quotient

$$
P/Q.
$$

More precisely, the center of $\widetilde G$ is naturally dual to $P/Q$. This quotient measures the difference between all possible integral weights and the root lattice.

For $SU(N)$,

$$
Z(SU(N))\cong\mathbb Z_N.
$$

Representations of $SU(N)$ can be assigned an $N$-ality, which records how the center acts. The adjoint representation has trivial $N$-ality, while the fundamental has nontrivial $N$-ality.

The quotient group

$$
PSU(N)=SU(N)/\mathbb Z_N
$$

allows only representations on which the center acts trivially. This changes the spectrum of genuine Wilson lines and modifies the higher-form symmetry structure of the gauge theory.

Roots, weights, and centers therefore control a piece of physics that is invisible if one specifies only the Lie algebra.

## Classical families

Here is a compact reference table for the simple classical Lie algebras. The notation is standard but slightly treacherous, because the same local algebra can integrate to multiple global groups.

| Type | Lie algebra | Common simply connected compact group | Rank | Weyl group |
|---|---:|---:|---:|---:|
| $A_{n-1}$ | $\mathfrak{sl}_n(\mathbb C)$ compact form $\mathfrak{su}(n)$ | $SU(n)$ | $n-1$ | $S_n$ |
| $B_n$ | $\mathfrak{so}_{2n+1}(\mathbb C)$ compact form $\mathfrak{so}(2n+1)$ | $Spin(2n+1)$ | $n$ | signed permutations |
| $C_n$ | $\mathfrak{sp}_{2n}(\mathbb C)$ compact form $\mathfrak{sp}(n)$ | $Sp(n)$ | $n$ | signed permutations |
| $D_n$ | $\mathfrak{so}_{2n}(\mathbb C)$ compact form $\mathfrak{so}(2n)$ | $Spin(2n)$ | $n$ | even signed permutations |

The exceptional types are

$$
G_2,
\qquad
F_4,
\qquad
E_6,
\qquad
E_7,
\qquad
E_8.
$$

They are not rare in theoretical physics. $E_6$, $E_7$, and $E_8$ appear in grand unification, string compactifications, exceptional global symmetries, and supersymmetric field theory. $G_2$ and $F_4$ appear in exceptional holonomy, octonionic constructions, and special gauge-theory examples.

## The SU(N) root system

For $SU(N)$, it is useful to introduce vectors $e_i$ in $\mathbb R^N$ with the constraint that the trace direction is removed. The roots are

$$
\alpha_{ij}=e_i-e_j,
\qquad
 i\ne j.
$$

A standard choice of simple roots is

$$
\alpha_i=e_i-e_{i+1},
\qquad
 i=1,\ldots,N-1.
$$

The Weyl group $S_N$ permutes the $e_i$.

The fundamental representation $\mathbf N$ has weights that can be represented by $e_i$ after projecting out the trace direction. The adjoint representation has weights

$$
e_i-e_j
\qquad
(i\ne j)
$$

plus the zero weight with multiplicity $N-1$.

The Cartan matrix of $A_{N-1}$ is

$$
A_{ij}=2\delta_{ij}-\delta_{i,j+1}-\delta_{i+1,j}.
$$

Its Dynkin diagram is a chain of $N-1$ nodes.

The representation with Dynkin labels

$$
(n_1,n_2,\ldots,n_{N-1})
$$

has highest weight

$$
\lambda=\sum_{i=1}^{N-1} n_i\omega_i.
$$

Young tableaux provide a particularly efficient additional language for $SU(N)$ representations; they will be introduced separately.

## QFT dictionary

The root–weight dictionary is one of the most useful translation tables in field theory.

| Mathematical object | QFT interpretation |
|---|---|
| Cartan subalgebra $\mathfrak h$ | maximal commuting charges or abelian gauge fields |
| Rank $r$ | number of independent Cartan generators |
| Weight $\mu$ of representation $R$ | Cartan charge of a state or field component in $R$ |
| Root $\alpha$ | Cartan charge of an off-diagonal adjoint generator or gauge boson |
| Simple roots $\alpha_i$ | chosen raising/lowering basis and Dynkin diagram data |
| Fundamental weights $\omega_i$ | basis for highest-weight labels |
| Dynkin labels $n_i$ | integer label of an irreducible representation |
| Weyl group $W$ | residual nonabelian identification on Cartan data |
| Root lattice $Q$ | adjoint charge lattice |
| Weight lattice $P$ | electric charge lattice for simply connected group representations |
| Coroot lattice | natural magnetic charge lattice in many gauge theories |
| Center | quotient data controlling representation classes and line operators |

Two common examples make the dictionary concrete.

First, in Yang–Mills theory with gauge group $G$, the gauge bosons transform in the adjoint representation. Relative to the Cartan, the neutral gauge bosons sit in $\mathfrak h$, while the charged gauge bosons carry root charges.

Second, a matter field in representation $R$ decomposes into components labeled by weights $\mu$. Coupling to a background Cartan gauge field $A$ produces phases and covariant derivatives controlled by $\mu(A)$.

## Example: roots as W-boson charges

Suppose an adjoint scalar field has a vacuum expectation value in the Cartan,

$$
\phi=a\in\mathfrak h.
$$

This generically breaks the gauge group to the maximal torus. The commutator with a root generator is

$$
[a,E_\alpha]=\alpha(a)E_\alpha.
$$

The off-diagonal gauge boson associated with $E_\alpha$ becomes massive with a mass proportional to

$$
|\alpha(a)|.
$$

Thus roots are the electric charges of the massive $W$-bosons under the unbroken abelian gauge group.

This statement is one of the reasons root systems are not decorative representation theory. They literally give the charge spectrum after nonabelian symmetry is broken to Cartan.

## Example: weights as matter charges

Let $\psi$ be a matter field in representation $R$. In a Cartan basis, decompose it as

$$
\psi=\sum_\mu \psi_\mu,
$$

where $\psi_\mu$ has weight $\mu$.

For a Cartan-valued gauge field

$$
A=A^iH_i,
$$

the covariant derivative acts as

$$
D\psi_\mu=(d+i\mu(A))\psi_\mu
$$

up to the representation and sign conventions for the gauge coupling. The weight is the abelian charge vector.

This is how nonabelian representation theory becomes ordinary charge bookkeeping after restriction to the maximal torus.

## Highest-weight classification

For compact connected semisimple groups, every finite-dimensional irreducible representation has a highest weight. The highest weight is dominant and integral. Conversely, every dominant integral weight defines an irreducible representation of the simply connected group.

The proof is not needed for most QFT computations, but the mechanism is worth knowing.

Choose positive roots. A highest-weight vector $v_\lambda$ satisfies

$$
E_\alpha v_\lambda=0
\qquad
\text{for all }\alpha>0,
$$

and

$$
H v_\lambda=\lambda(H)v_\lambda.
$$

The rest of the representation is generated by lowering operators:

$$
E_{-\alpha_i}.
$$

Finite dimensionality forces the strings in each simple-root direction to terminate. This gives the integrality conditions

$$
\langle\alpha_i^\vee,\lambda\rangle\in\mathbb Z_{\ge0}.
$$

The Dynkin labels are exactly these termination lengths:

$$
n_i=\langle\alpha_i^\vee,\lambda\rangle.
$$

So a Dynkin label is not a mysterious name. It is the number of lowering steps available from the highest weight in the $i$th simple-root direction.

## Common pitfalls

**Pitfall 1: confusing roots and weights.** Roots are weights of the adjoint representation. General representations have weights that need not themselves be roots.

**Pitfall 2: treating Dynkin diagrams as group diagrams.** Dynkin diagrams classify complex simple Lie algebras, not global forms of compact groups. $SU(2)$ and $SO(3)$ share the same $A_1$ diagram but have different representation spectra.

**Pitfall 3: forgetting coroots.** Integrality is measured by $\langle\alpha^\vee,\lambda\rangle$, not by a raw dot product with $\alpha$. This matters whenever roots have different lengths.

**Pitfall 4: reading Dynkin labels as individual weight charges.** Dynkin labels describe the highest weight of an entire irreducible representation. They are not the list of all weights in that representation.

**Pitfall 5: thinking the Weyl group is an extra physical symmetry.** Often it is a residual gauge identification on Cartan variables. In such cases, Weyl-related Cartan data are the same physical configuration, not distinct configurations related by a global symmetry.

**Pitfall 6: using only the Lie algebra when line operators matter.** The Lie algebra fixes roots and local gauge bosons. The global form of the group fixes which weights are honest representations and which Wilson lines are allowed.

## Relations to other pages

[Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/) explains why compactness gives unitary finite-dimensional representation theory, Haar measure, and complete reducibility.

[SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/) is the rank-one prototype: weights are $J_3$ eigenvalues, roots are the steps generated by $J_\pm$, and finite-dimensionality gives highest weights.

[Characters](/math-toolkit/groups-representations/characters/) packages weights and multiplicities into class functions. It is the next natural page after this one.

The later pages Young Tableaux and Gauge Group Data will turn this structure into practical tables for tensor products, dimensions, Casimirs, Dynkin indices, centers, and anomaly coefficients.

## Research status

The classification of complex semisimple Lie algebras by Dynkin diagrams, and the classification of finite-dimensional irreducible representations by highest weights, are established mathematics.

What remains active is not the classification itself but its use in QFT. Modern work often depends on the global form of the gauge group, the lattice of allowed line operators, generalized global symmetries, magnetic charge lattices, dual groups, and defects. These questions use the same root and weight data, but ask more refined physical questions than old-fashioned multiplet counting.

## Exercises

### Exercise 1

For $\mathfrak{su}(2)$, let the simple root be $\alpha$ and the fundamental weight be $\omega$. Show that

$$
\alpha=2\omega.
$$

Explain why the highest weight $n\omega$ corresponds to spin $j=n/2$.

<details><summary><strong>Solution</strong></summary>

For $\mathfrak{su}(2)$, there is one simple root and one simple coroot. The fundamental weight is defined by

$$
\langle\alpha^\vee,\omega\rangle=1.
$$

But

$$
\langle\alpha^\vee,\alpha\rangle=2
$$

by definition of the coroot. Therefore $\alpha$ pairs with $\alpha^\vee$ twice as strongly as $\omega$ does, so

$$
\alpha=2\omega
$$

in the one-dimensional weight space.

A highest weight $\lambda=n\omega$ has

$$
\langle\alpha^\vee,\lambda\rangle=n.
$$

For $SU(2)$, the highest weight equals $2j$ in angular-momentum units, so

$$
n=2j,
\qquad
j=\frac n2.
$$

The representation has dimension

$$
2j+1=n+1.
$$

</details>

### Exercise 2

The $A_2$ simple roots have equal length and angle $120^\circ$. Compute the Cartan matrix.

<details><summary><strong>Solution</strong></summary>

Since the roots have equal length,

$$
(\alpha_1,\alpha_1)=(\alpha_2,\alpha_2).
$$

The diagonal entries are always

$$
A_{11}=A_{22}=2.
$$

For the off-diagonal entries,

$$
A_{12}=\frac{2(\alpha_1,\alpha_2)}{(\alpha_1,\alpha_1)}.
$$

The angle is $120^\circ$, so

$$
(\alpha_1,\alpha_2)=|\alpha_1||\alpha_2|\cos 120^\circ
=-\frac12|\alpha_1|^2.
$$

Therefore

$$
A_{12}=2\left(-\frac12\right)=-1.
$$

Similarly,

$$
A_{21}=-1.
$$

Thus

$$
A=
\begin{pmatrix}
2&-1\\
-1&2
\end{pmatrix}.
$$

</details>

### Exercise 3

For $SU(3)$, the fundamental representation has Dynkin labels $(1,0)$ and the antifundamental has labels $(0,1)$. What is the highest weight of the adjoint representation in Dynkin-label notation?

<details><summary><strong>Solution</strong></summary>

For $SU(3)$, the adjoint representation has highest root

$$
\theta=\alpha_1+\alpha_2.
$$

In the $A_2$ root system, the highest root is also

$$
\theta=\omega_1+\omega_2.
$$

Therefore its Dynkin labels are

$$
(1,1).
$$

This is the $\mathbf 8$ representation.

</details>

### Exercise 4

Let $v$ be a weight vector of weight $\mu$, and let $E_\alpha$ be a root vector. Show that if $E_\alpha v\ne0$, then $E_\alpha v$ has weight $\mu+\alpha$.

<details><summary><strong>Solution</strong></summary>

For every $H\in\mathfrak h$,

$$
Hv=\mu(H)v,
$$

and

$$
[H,E_\alpha]=\alpha(H)E_\alpha.
$$

Then

$$
H(E_\alpha v)=([H,E_\alpha]+E_\alpha H)v.
$$

Substituting the two eigenvalue equations gives

$$
H(E_\alpha v)=\alpha(H)E_\alpha v+\mu(H)E_\alpha v.
$$

Thus

$$
H(E_\alpha v)=(\mu+\alpha)(H)E_\alpha v.
$$

If $E_\alpha v\ne0$, it is a weight vector of weight $\mu+\alpha$.

</details>

### Exercise 5

Show that the Weyl reflection

$$
s_\alpha(\lambda)=\lambda-\langle\alpha^\vee,\lambda\rangle\alpha
$$

sends $\alpha$ to $-\alpha$.

<details><summary><strong>Solution</strong></summary>

Set $\lambda=\alpha$. Then

$$
s_\alpha(\alpha)=\alpha-\langle\alpha^\vee,\alpha\rangle\alpha.
$$

By definition of the coroot,

$$
\langle\alpha^\vee,\alpha\rangle=2.
$$

Therefore

$$
s_\alpha(\alpha)=\alpha-2\alpha=-\alpha.
$$

So $s_\alpha$ is indeed reflection through the hyperplane perpendicular to $\alpha$.

</details>

### Exercise 6

Explain why the spin-$\frac12$ representation is allowed for $SU(2)$ but not for $SO(3)$.

<details><summary><strong>Solution</strong></summary>

The groups are related by

$$
SO(3)\cong SU(2)/\mathbb Z_2.
$$

A representation of $SU(2)$ descends to a representation of $SO(3)$ only if the central element

$$
-\mathbf 1\in SU(2)
$$

acts trivially.

In the spin-$j$ representation, this element acts as

$$
(-1)^{2j}\mathbf 1.
$$

For $j=\frac12$,

$$
(-1)^{2j}=(-1)^1=-1.
$$

Thus the central element acts nontrivially, and the representation does not descend to $SO(3)$.

Equivalently, the $SU(2)$ highest weight is $\omega$, while $SO(3)$ only allows even multiples of $\omega$, corresponding to integer spin.

</details>

## References

- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for a friendly mathematical development of roots, weights, Weyl groups, and highest weights.
- J. E. Humphreys, *Introduction to Lie Algebras and Representation Theory*, for the classical root-system and highest-weight theory.
- H. Georgi, *Lie Algebras in Particle Physics*, for Dynkin diagrams, roots, weights, and representation theory in particle-physics normalization conventions.
- W. Fulton and J. Harris, *Representation Theory*, for highest weights, classical groups, and examples.
- A. W. Knapp, *Lie Groups Beyond an Introduction*, for compact Lie groups, root systems, Weyl groups, and characters.
- W.-K. Tung, *Group Theory in Physics*, and J. F. Cornwell, *Group Theory in Physics*, for physics-oriented group theory and representation calculations.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for representation theory in relativistic particles, internal symmetries, and gauge theory.
- M. Srednicki, *Quantum Field Theory*, for group representations and gauge-theory group factors.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for Yang–Mills representations and Standard Model group theory.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for modern uses of centers, line operators, and higher-form symmetries.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
