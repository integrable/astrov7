---
title: "Symmetry Algebras"
description: "Explains how continuous symmetry groups become Lie algebras of conserved charges, how those charges act on states and operators, and why algebraic data are not the whole global symmetry."
sidebar:
  label: "Symmetry Algebras"
  order: 9
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I on symmetries and Lie groups; Coleman lectures on currents; Srednicki §§22–24; standard Lie-algebra and current-algebra conventions."
topics:
  - symmetry algebras
  - Lie algebras
  - conserved charges
  - representation theory
  - current algebra
  - central extensions
canonicalTopics:
  - symmetry-algebra
  - lie-algebra-of-charges
  - current-algebra
  - representation-generator
researchStatus:
  established:
    - "For exact continuous internal symmetries, conserved charges furnish a representation of the Lie algebra of the symmetry group on states and operators."
  active:
    - "Current algebras, central extensions, higher-form algebras, higher-group structures, and non-invertible symmetry categories refine the simple Lie-algebra picture in modern QFT."
---

## Summary

A continuous symmetry group $G$ has infinitesimal generators. In QFT those generators are conserved charges $Q_a$ acting on the Hilbert space.

With the convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

the charges of an exact internal symmetry obey

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c,
$$

where $f_{ab}{}^c$ are the structure constants of the Lie algebra $\mathfrak g=\operatorname{Lie}(G)$.

The same charges act on local operators. For a multiplet $\mathcal O_i$ one writes

$$
[Q_a,\mathcal O_i]=(\tau_a)_i{}^j\mathcal O_j,
$$

with a sign convention explained below. Abelian symmetry algebras have vanishing commutators. Nonabelian symmetry algebras do not: acting with two transformations in different orders can produce a third transformation.

The slogan is

$$
\text{continuous symmetry}
\quad\Longrightarrow\quad
\text{conserved charges closing under commutators}.
$$

But the algebra is not the whole symmetry. The same Lie algebra can exponentiate to different global groups, such as $SU(2)$ and $SO(3)$. Global form, allowed representations, line operators, discrete quotients, anomalies, and projective phases are extra data beyond the local commutator algebra.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A schematic map from a continuous symmetry group to charges, their commutator algebra, and their actions on states, local operators, and currents.](/figures/symmetry-anomalies-topology/symmetry-algebra-data-map.svg)

<figcaption>

A continuous symmetry gives charges $Q_a$. Their commutators define the Lie algebra, while their representations act on states, local operators, and currents. The Lie algebra controls infinitesimal symmetry; global questions require more data.

</figcaption>
</figure>

## Prerequisites

You should know [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/), and [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/).

Mathematically, the page assumes only the idea of a commutator and a Lie algebra. The purpose is not to replace a representation-theory course, but to identify exactly what part of Lie theory is used by QFT symmetry arguments.

## Core idea

A finite group element tells you how to transform an object. A Lie algebra tells you what happens infinitesimally.

Near the identity, write a symmetry as

$$
g(\alpha)=\exp(\alpha^aT_a).
$$

On the Hilbert space, the same transformation is implemented by a unitary operator

$$
U(\alpha)=e^{-i\alpha^aQ_a}.
$$

The charges $Q_a$ are the quantum generators. If $G$ is nonabelian, the order of two infinitesimal transformations matters. The commutator is another infinitesimal transformation:

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

This algebraic closure is why symmetry multiplets, Ward identities, current algebra, and nonabelian selection rules fit together. The charges do not merely label states; they form an algebra of transformations.

## Setup and conventions

For an internal continuous symmetry, choose Hermitian charges

$$
Q_a^\dagger=Q_a,
$$

and write

$$
U(\alpha)=e^{-i\alpha^aQ_a}.
$$

The action on operators is by pullback:

$$
\mathcal O\mapsto U(\alpha)^\dagger\mathcal O U(\alpha).
$$

Therefore

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

The charges close as

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

The structure constants are antisymmetric in $a,b$,

$$
f_{ab}{}^c=-f_{ba}{}^c,
$$

and obey the Jacobi identity

$$
f_{ab}{}^d f_{dc}{}^e
+f_{bc}{}^d f_{da}{}^e
+f_{ca}{}^d f_{db}{}^e=0.
$$

The Jacobi identity is not an extra decoration. It is the consistency condition saying that nested commutators of generators associate correctly.

:::note[Convention-sensitive source note]
This page uses Hermitian quantum charges $Q_a$ and $U(\alpha)=e^{-i\alpha^aQ_a}$. Mathematicians often use anti-Hermitian generators for the Lie algebra, while many physics sources use Hermitian matrices $t_a$ with $[t_a,t_b]=if_{ab}{}^ct_c$. Translation between these choices is mechanical but sign-sensitive.
:::

## From group multiplication to commutators

The Lie algebra records the leading failure of infinitesimal transformations to commute.

For two small parameters $\alpha$ and $\beta$,

$$
U(\alpha)U(\beta)U(\alpha)^{-1}U(\beta)^{-1}
=
1-\alpha^a\beta^b[Q_a,Q_b]+O(\alpha^2\beta,\alpha\beta^2).
$$

If

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c,
$$

then this group commutator is itself an infinitesimal symmetry generated by $f_{ab}{}^cQ_c$.

This is invisible for abelian groups. For $U(1)^n$,

$$
[Q_a,Q_b]=0.
$$

But for a nonabelian group, the algebra is part of the physics. It fixes how multiplet components mix, which currents rotate into one another, and which tensor structures can appear in invariant interactions and correlation functions.

## Representations on states

If states transform in a representation $R$ of $G$, the charges are represented by matrices $t_a^{(R)}$ on the multiplet indices.

For a state multiplet $|\psi,i\rangle$,

$$
Q_a|\psi,i\rangle=(t_a^{(R)})_i{}^j|\psi,j\rangle,
$$

where the matrices satisfy

$$
[t_a^{(R)},t_b^{(R)}]=if_{ab}{}^c t_c^{(R)}.
$$

The finite transformation is

$$
U(\alpha)|\psi,i\rangle
=\left(e^{-i\alpha^at_a^{(R)}}\right)_i{}^j|\psi,j\rangle.
$$

If the Hamiltonian commutes with all $Q_a$,

$$
[H,Q_a]=0,
$$

then states in the same irreducible symmetry multiplet have the same energy, unless additional effects such as spontaneous symmetry breaking or explicit symmetry breaking intervene.

For a compact group, the Hilbert space decomposes schematically as

$$
\mathcal H\simeq\bigoplus_{R\in\widehat G}\mathcal K_R\otimes V_R,
$$

where $V_R$ carries the irreducible representation and $\mathcal K_R$ is a multiplicity space of other labels.

## Representations on operators

Operators also transform in representations. Suppose $\mathcal O_i$ is an operator multiplet and define matrices $\tau_a$ by

$$
[Q_a,\mathcal O_i]=(\tau_a)_i{}^j\mathcal O_j.
$$

Then

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=\left(e^{i\alpha^a\tau_a}\right)_i{}^j\mathcal O_j.
$$

Because this is a pullback action on operators with lower multiplet indices, the matrices $\tau_a$ satisfy

$$
[\tau_a,\tau_b]=-if_{ab}{}^c\tau_c.
$$

If one instead writes operator multiplets with upper indices or uses the active transformation $U\mathcal O U^{-1}$, the sign is reversed. Many sources simply call the corresponding matrices $t_a$ and absorb this distinction into index placement.

For abelian symmetries there is no sign issue from commutators, and the formula reduces to

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

:::tip[How to avoid sign pain]
When in doubt, specify the finite transformation first. For example,

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)=R(\alpha)_i{}^j\mathcal O_j.
$$

Then derive the commutator by differentiating at $\alpha=0$. The finite transformation is less ambiguous than the sign of the infinitesimal generator.
:::

## Examples

### The abelian case

For $G=U(1)$, there is one charge $Q$ and

$$
[Q,Q]=0.
$$

An operator of charge $q$ obeys

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

The algebra is too simple to mix components, but it still gives powerful selection rules: charges add.

For $G=U(1)^n$, there are commuting charges $Q_A$, $A=1,\dots,n$, and a charged operator has a charge vector $q_A$:

$$
[Q_A,\mathcal O_{\mathbf q}]=q_A\mathcal O_{\mathbf q}.
$$

Selection rules require vector charge balance.

### The SU(2) case

For $SU(2)$, write generators $Q_i$ with

$$
[Q_i,Q_j]=i\epsilon_{ij}{}^kQ_k.
$$

It is often useful to define

$$
Q_\pm=Q_1\pm iQ_2.
$$

Then

$$
[Q_3,Q_\pm]=\pm Q_\pm,
\qquad
[Q_+,Q_-]=2Q_3.
$$

In a spin-$j$ multiplet, states can be labeled by

$$
|j,m\rangle,
\qquad
m=-j,-j+1,\dots,j.
$$

The raising and lowering operators move within the same irreducible representation:

$$
Q_\pm|j,m\rangle\propto |j,m\pm1\rangle.
$$

The quadratic Casimir

$$
Q^2=Q_1^2+Q_2^2+Q_3^2
$$

commutes with all $Q_i$ and labels irreducible representations:

$$
Q^2|j,m\rangle=j(j+1)|j,m\rangle.
$$

### The SU(N) case

For $SU(N)$, one often chooses Hermitian generators $t_a$ in the fundamental representation normalized by

$$
\operatorname{tr}(t_at_b)=\frac12\delta_{ab}.
$$

Then

$$
[t_a,t_b]=if_{ab}{}^ct_c.
$$

In QFT, the corresponding charges satisfy the same algebra,

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

Matter fields in the fundamental representation, antifundamental representation, adjoint representation, or higher tensor representations carry the corresponding matrices. Invariant interactions are built by contracting representation indices into singlets.

## Current algebra

For a continuous internal symmetry with currents $j_a^\mu$, the charges are spatial integrals:

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

The integrated algebra

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c
$$

comes from a local current algebra of the schematic form

$$
[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)]
=
if_{ab}{}^c j_c^0(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y)
+\text{contact terms}.
$$

The phrase “contact terms” is doing real work. Local products of currents are distributions, and their commutators can contain derivative delta functions or central terms. In many ordinary internal-symmetry applications, these terms integrate to zero under good boundary conditions. In two-dimensional CFT and in anomalous theories, they can be physically central.

A current can also transform in the adjoint representation:

$$
[Q_a,j_b^\mu]=if_{ab}{}^c j_c^\mu,
$$

up to convention-dependent signs and contact terms. This expresses the fact that the currents themselves form a multiplet under the symmetry.

## Algebra versus global group

The Lie algebra is local near the identity. It does not always determine the full global symmetry group.

The classic example is

$$
\mathfrak{su}(2)\simeq\mathfrak{so}(3).
$$

The groups $SU(2)$ and $SO(3)=SU(2)/\mathbb Z_2$ have the same Lie algebra but different allowed representations. Half-integer spin representations are honest representations of $SU(2)$, but not of $SO(3)$.

This distinction matters in QFT. The global form of a symmetry group can determine:

- which local operators are allowed,
- which background bundles can be turned on,
- which line operators are genuine,
- which finite quotients exist,
- which anomalies are possible,
- which gauging operations are allowed.

So a statement such as “the symmetry algebra is $\mathfrak{su}(2)$” is incomplete. It fixes infinitesimal transformations, but not the full global symmetry structure.

## Central extensions and projective representations

Sometimes the charges close only up to central terms:

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c+i\kappa_{ab}\mathbf 1.
$$

If $\kappa_{ab}$ cannot be removed by redefining the charges, the Hilbert space carries a projective representation or a centrally extended algebra.

In ordinary compact internal symmetries of relativistic QFT, central extensions are often absent for the finite-dimensional Lie algebra of global charges. But central terms are essential in nearby contexts:

- quantum mechanics can realize projective representations of symmetry groups,
- two-dimensional current algebras have levels,
- the Virasoro algebra has a central charge,
- supersymmetry algebras can have central charges tied to extended objects,
- anomalous current algebras can contain Schwinger terms.

The planned projective-representation page will return to this point. The anomaly and CFT chapters develop the current-algebra examples in detail.

## Symmetry algebras and Ward identities

Ward identities know the algebra.

For an infinitesimal symmetry,

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

Applying two variations and commuting them gives another variation:

$$
[\delta_a,\delta_b]\mathcal O=-f_{ab}{}^c\delta_c\mathcal O
$$

with the pullback convention used here. This sign is the same convention issue discussed above: the physical statement is that the transformations close.

In path-integral language, local Ward identities involve current insertions. Requiring that two Ward transformations be compatible with the algebra leads to consistency conditions. In anomaly theory, the analogous requirement is the Wess–Zumino consistency condition: even anomalous variations must respect the algebra of symmetry transformations.

## Common pitfalls

**Confusing the algebra with the group.** $SU(2)$ and $SO(3)$ have the same Lie algebra but different representations and global data.

**Assuming all charges commute.** Only abelian charges can be simultaneously diagonalized. Nonabelian charges organize multiplets.

**Ignoring sign conventions for operator multiplets.** Decide whether you are using $U^\dagger\mathcal O U$ or $U\mathcal O U^{-1}$, and whether multiplet indices are in a representation or dual representation.

**Forgetting contact terms in current algebra.** Local current commutators are distributional. Integrated charges may be simple even when local current algebra is subtle.

**Calling a gauge algebra a physical global symmetry algebra.** Gauge generators are constraints or redundancies. Physical global symmetries act faithfully on gauge-invariant observables or on boundary data.

**Assuming Lie-algebra data fixes anomalies.** Many anomalies depend on global topology, finite subgroups, background bundles, and global form, not just the infinitesimal algebra.

## Relations to other pages

[Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/) explains how charges act on states and define charge sectors. [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) uses the algebra and representations to derive vanishing rules.

[Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/) gives the finite-group and representation-theoretic background. [Projective Representations Preview](/symmetry-anomalies-topology/ordinary-global-symmetries/projective-representations-preview/) will explain central extensions and phase ambiguities.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter develops current algebra, contact terms, and Ward identities. [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) explains why global form matters when coupling symmetries to background gauge fields. [Anomalies](/symmetry-anomalies-topology/anomalies/) explains how quantum effects can obstruct the naive symmetry algebra or its gauging.

## Research status

The Lie-algebra action of ordinary continuous symmetries is established textbook material.

The active frontier lies in refinements. Current algebras can have central extensions. Higher-form symmetries have higher-degree charges and topological operators. Higher-group symmetries mix ordinary and higher-form transformations. Non-invertible symmetries replace a group algebra by a fusion category or more general defect algebra. Symmetry TFT packages these algebraic and topological data into a higher-dimensional topological theory.

The lesson for ordinary symmetries remains durable: algebra controls infinitesimal structure, while topology and representation theory control global structure.

## Exercises

### Exercise 1: Jacobi identity for structure constants

Assume $[Q_a,Q_b]=if_{ab}{}^cQ_c$. Use the operator Jacobi identity to derive the Jacobi identity for $f_{ab}{}^c$.

<details><summary><strong>Solution</strong></summary>

The operator Jacobi identity is

$$
[Q_a,[Q_b,Q_c]]+[Q_b,[Q_c,Q_a]]+[Q_c,[Q_a,Q_b]]=0.
$$

Using $[Q_b,Q_c]=if_{bc}{}^dQ_d$ gives

$$
[Q_a,[Q_b,Q_c]]=if_{bc}{}^d[Q_a,Q_d]
=if_{bc}{}^d(if_{ad}{}^eQ_e)
=-f_{bc}{}^d f_{ad}{}^eQ_e.
$$

Adding cyclic permutations and using linear independence of the generators gives

$$
f_{bc}{}^d f_{ad}{}^e
+f_{ca}{}^d f_{bd}{}^e
+f_{ab}{}^d f_{cd}{}^e=0,
$$

which is the Jacobi identity, up to equivalent relabelings of dummy indices.

</details>

### Exercise 2: SU(2) raising and lowering algebra

Given $[Q_i,Q_j]=i\epsilon_{ij}{}^kQ_k$ and $Q_\pm=Q_1\pm iQ_2$, show that

$$
[Q_3,Q_\pm]=\pm Q_\pm.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
[Q_3,Q_+]=[Q_3,Q_1]+i[Q_3,Q_2].
$$

Using the $SU(2)$ algebra,

$$
[Q_3,Q_1]=iQ_2,
\qquad
[Q_3,Q_2]=-iQ_1.
$$

Therefore

$$
[Q_3,Q_+]=iQ_2+i(-iQ_1)=Q_1+iQ_2=Q_+.
$$

Similarly,

$$
[Q_3,Q_-]=-Q_-.
$$

</details>

### Exercise 3: Operator representation sign

Suppose $[Q_a,\mathcal O_i]=(\tau_a)_i{}^j\mathcal O_j$ and $[Q_a,Q_b]=if_{ab}{}^cQ_c$. Use the Jacobi identity to show that $[\tau_a,\tau_b]=-if_{ab}{}^c\tau_c$ with the pullback convention of this page.

<details><summary><strong>Solution</strong></summary>

Start from

$$
[Q_a,[Q_b,\mathcal O_i]]-[Q_b,[Q_a,\mathcal O_i]]=[[Q_a,Q_b],\mathcal O_i].
$$

The left side is

$$
(\tau_b\tau_a-\tau_a\tau_b)_i{}^j\mathcal O_j
=-[\tau_a,\tau_b]_i{}^j\mathcal O_j.
$$

The right side is

$$
[if_{ab}{}^cQ_c,\mathcal O_i]
=if_{ab}{}^c(\tau_c)_i{}^j\mathcal O_j.
$$

Thus

$$
-[\tau_a,\tau_b]=if_{ab}{}^c\tau_c,
$$

or

$$
[\tau_a,\tau_b]=-if_{ab}{}^c\tau_c.
$$

The minus sign reflects the convention $\mathcal O\mapsto U^\dagger\mathcal O U$ with lower multiplet indices.

</details>

### Exercise 4: Same algebra, different group

Explain why a theory whose local operators all have integer $SU(2)$ spin could have global symmetry $SO(3)$ rather than $SU(2)$.

<details><summary><strong>Solution</strong></summary>

The groups $SU(2)$ and $SO(3)=SU(2)/\mathbb Z_2$ have the same Lie algebra. Their difference is global. Half-integer spin representations are representations of $SU(2)$ but not honest representations of $SO(3)$.

If all genuine local operators have integer spin under this algebra, the central element $-1\in SU(2)$ acts trivially on all local operators. Then the faithful global action on local operators may be the quotient group $SO(3)$.

One must still check extended operators, backgrounds, and possible anomalies before declaring the full global symmetry, but the example shows why the Lie algebra alone is insufficient.

</details>

### Exercise 5: Abelian subalgebras

For $SU(2)$, can $Q_1$, $Q_2$, and $Q_3$ be simultaneously diagonalized? What about $Q^2$ and $Q_3$?

<details><summary><strong>Solution</strong></summary>

The three generators cannot be simultaneously diagonalized because they do not commute:

$$
[Q_i,Q_j]=i\epsilon_{ij}{}^kQ_k.
$$

However, the Casimir

$$
Q^2=Q_1^2+Q_2^2+Q_3^2
$$

commutes with all $Q_i$, so in particular

$$
[Q^2,Q_3]=0.
$$

Therefore one can choose states $|j,m\rangle$ that are simultaneous eigenstates of $Q^2$ and $Q_3$, but not of all three $Q_i$.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially the discussion of symmetries, Lie groups, projective representations, and superselection.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on spacetime and internal symmetries.
- Sidney Coleman, *Aspects of Symmetry*, especially “An Introduction to Unitary Symmetry,” “Soft Pions,” and “Dilatations.”
- Mark Srednicki, *Quantum Field Theory*, sections 22–24 on continuous, discrete, and nonabelian symmetries.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on Lorentz symmetry, gauge invariance, Ward identities, and Standard Model group theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry, group theory, and symmetry breaking.

## Version history

- **2026-06-17:** First polished draft for the Ordinary Global Symmetries chapter.
