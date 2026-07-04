---
title: "Gauge Group Data"
description: "A QFT-oriented reference page for Lie-algebra, representation, Casimir, Dynkin-index, center, global-form, and anomaly data used in gauge theories."
sidebar:
  label: "Gauge Group Data"
  order: 10
level: Graduate
status: "Polished draft"
source: "Standard group-theory and QFT references, including Georgi, Slansky, Hall, Fulton–Harris, Weinberg, Srednicki, Schwartz, Coleman, Peskin–Schroeder, and anomaly references such as Bardeen and Fujikawa."
topics:
  - gauge groups
  - Lie algebra data
  - Casimir invariants
  - Dynkin index
  - center symmetry
  - global form of gauge group
  - anomaly coefficients
  - beta functions
canonicalTopics:
  - gauge-group-data
  - quadratic-casimir
  - dynkin-index
  - dual-coxeter-number
  - center-of-gauge-group
  - global-form-of-gauge-group
  - gauge-anomaly-coefficients
researchStatus:
  established:
    - "The Lie-algebra and finite-dimensional representation data listed here are standard, with convention-dependent normalizations made explicit."
  active:
    - "The global form of the gauge group, line-operator spectrum, higher-form symmetry, discrete theta angles, and anomaly constraints remain central in modern nonperturbative QFT and quantum phases of gauge theory."
---

## Summary

A gauge theory needs more than a name like “$SU(N)$.” It needs a set of group-theoretic data:

$$
G,
\qquad
\mathfrak g,
\qquad
R_i,
\qquad
\operatorname{tr}_{R_i}(T^aT^b),
\qquad
C_2(R_i),
\qquad
\text{global form and center charges}.
$$

These data determine the local vertices, color factors, perturbative beta functions, anomaly constraints, allowed Wilson lines, magnetic sectors, instanton sums, and sometimes the very meaning of the gauge theory.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Diagram showing how Lie algebra data, representation data, and global form feed into local dynamics, anomalies, singlets, bundles, monopoles, and one-form symmetries.](/figures/math-toolkit/gauge-group-data-flow.svg)

<figcaption>

Gauge group data split into local and global parts. The Lie algebra and representation invariants control perturbative formulas such as loop color factors and beta functions. The global form controls which representations are honest Wilson lines, which bundles are allowed, and which magnetic sectors and higher-form symmetries exist.

</figcaption>
</figure>

The most common local invariants are the **Dynkin index** $T(R)$ and the **quadratic Casimir** $C_2(R)$. With Hermitian generators in representation $R$,

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
$$

and

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

They are related by

$$
C_2(R)\dim R=T(R)\dim G.
$$

That one relation is the quickest way to check most normalization errors.

## Prerequisites

You should know [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/), [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/), [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/), [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/), [Characters](/math-toolkit/groups-representations/characters/), and [Young Tableaux](/math-toolkit/groups-representations/young-tableaux/).

This page is a reference note with explanations. It fixes the normalizations used by later QFT pages; it is not a full atlas of every representation of every group.

## Core idea

There are three layers of gauge group data.

The first layer is the **Lie algebra** $\mathfrak g$. It determines the local gauge bosons, structure constants, infinitesimal gauge transformations, and local perturbative vertices. For a basis $T^a$,

$$
[T^a,T^b]=if^{ab}{}_{c}T^c.
$$

The second layer is the **representation data** of matter and line operators. A field in representation $R$ couples through matrices $T_R^a$. Loop diagrams and anomaly diagrams do not merely ask “which group?” They ask for $T(R)$, $C_2(R)$, dimensions, reality type, and sometimes cubic or higher invariant tensors.

The third layer is the **global form** of the gauge group. The Lie algebras of $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$ are the same, but the two gauge theories can have different Wilson lines, magnetic line operators, bundles, one-form symmetries, and discrete theta parameters. Perturbation theory around trivial bundles may not notice the difference. The full QFT can.

So the practical rule is:

$$
\text{local formulas use }\mathfrak g\text{ and }R,
\qquad
\text{global sectors use }G\text{ itself}.
$$

## Setup and conventions

Generators are Hermitian in unitary representations:

$$
(T_R^a)^\dagger=T_R^a.
$$

The structure constants are defined by

$$
[T_R^a,T_R^b]=if^{ab}{}_{c}T_R^c.
$$

For simple compact Lie algebras, we choose the common physics normalization in which the fundamental representation of $SU(N)$ obeys

$$
\operatorname{tr}_{\mathbf N}(T^aT^b)=\frac12\delta^{ab}.
$$

With this convention,

$$
T(\mathbf N)=\frac12,
\qquad
C_2(\mathbf N)=\frac{N^2-1}{2N},
\qquad
C_2(\operatorname{Adj})=N
$$

for $SU(N)$.

For other groups, the phrase “standard representation” means:

- for $SO(N)$ or $Spin(N)$, the $N$-dimensional vector representation;
- for $Sp(N)$, the $2N$-dimensional defining representation of the compact symplectic group, also often called $USp(2N)$.

Different books use different normalizations for $SO(N)$ and $Sp(N)$. This page states the normalization each time. Translation is straightforward: if all generators are rescaled by $T^a\mapsto \alpha T^a$, then $T(R)$ and $C_2(R)$ both rescale by $\alpha^2$.

## The Dynkin index and quadratic Casimir

For an irreducible representation $R$, the Dynkin index $T(R)$ is defined by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

The quadratic Casimir $C_2(R)$ is defined by

$$
\sum_a T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

Take the trace of the Casimir equation over $R$:

$$
\operatorname{tr}_R(T_R^aT_R^a)=C_2(R)\dim R.
$$

Summing the index definition over $a=b$ gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=T(R)\dim G.
$$

Hence

$$
C_2(R)\dim R=T(R)\dim G.
$$

For the adjoint representation, one writes

$$
C_A=C_2(\operatorname{Adj}).
$$

With the long-root-length convention $(\alpha,\alpha)=2$ for long roots,

$$
C_A=h^\vee,
$$

where $h^\vee$ is the dual Coxeter number. In the $SU(N)$ normalization above,

$$
C_A=N.
$$

## Completeness for SU(N)

In the fundamental representation of $SU(N)$ with

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

the generators satisfy the completeness identity

$$
(T^a)^i{}_{j}(T^a)^k{}_{\ell}
=rac12\left(\delta^i{}_{\ell}\delta^k{}_{j}
-\frac1N\delta^i{}_{j}\delta^k{}_{\ell}\right).
$$

This identity is just the statement that the $SU(N)$ generators form an orthonormal basis of traceless Hermitian matrices. It is the color-algebra workhorse behind many QCD calculations.

A useful corollary is

$$
T^aT^a=C_F\mathbf 1,
\qquad
C_F=\frac{N^2-1}{2N}.
$$

For $SU(3)$,

$$
C_F=\frac43,
\qquad
C_A=3,
\qquad
T_F=\frac12.
$$

Those three numbers appear so often in QCD that they deserve their own tiny shrine.

## Classical group data

The following table uses the normalizations described above. For $SO(N)$ and $Sp(N)$, note that some particle-physics texts rescale generators differently, so compare trace conventions before importing formulas.

| Lie algebra family | Rank | Dimension | $h^\vee=C_A$ | Standard representation | $T(\text{std})$ | $C_2(\text{std})$ |
|---|---:|---:|---:|---:|---:|---:|
| $\mathfrak{su}_N$ | $N-1$ | $N^2-1$ | $N$ | $\mathbf N$ | $1/2$ | $(N^2-1)/(2N)$ |
| $\mathfrak{so}_N$ | $\lfloor N/2\rfloor$ | $N(N-1)/2$ | $N-2$ | vector $\mathbf N$ | $1$ | $(N-1)/2$ |
| $\mathfrak{sp}_N$ | $N$ | $N(2N+1)$ | $N+1$ | fundamental $\mathbf{2N}$ | $1/2$ | $(2N+1)/4$ |

Here $\mathfrak{sp}_N$ means the Lie algebra of the compact group often written $Sp(N)$ or $USp(2N)$. The latter notation makes the fundamental dimension $2N$ explicit.

For $SU(N)$, common representation data are:

| Representation of $SU(N)$ | Dimension | $T(R)$ | $C_2(R)$ |
|---|---:|---:|---:|
| fundamental $\mathbf N$ | $N$ | $1/2$ | $(N^2-1)/(2N)$ |
| adjoint | $N^2-1$ | $N$ | $N$ |
| two-index symmetric | $N(N+1)/2$ | $(N+2)/2$ | $(N-1)(N+2)/N$ |
| two-index antisymmetric | $N(N-1)/2$ | $(N-2)/2$ | $(N+1)(N-2)/N$ |
| $k$-index antisymmetric | $\binom Nk$ | $\frac12\binom{N-2}{k-1}$ | $k(N-k)(N+1)/(2N)$ |

These entries assume the $SU(N)$ fundamental normalization $T(\mathbf N)=1/2$.

## Exceptional group data

For many QFT applications, only the rank, dimension, center, and dual Coxeter number of exceptional groups are needed.

| Simply connected compact group | Rank | Dimension | Center | $h^\vee$ |
|---|---:|---:|---:|---:|
| $G_2$ | 2 | 14 | trivial | 4 |
| $F_4$ | 4 | 52 | trivial | 9 |
| $E_6$ | 6 | 78 | $\mathbb Z_3$ | 12 |
| $E_7$ | 7 | 133 | $\mathbb Z_2$ | 18 |
| $E_8$ | 8 | 248 | trivial | 30 |

Exceptional groups appear less often in first-pass QFT than $SU(N)$, $SO(N)$, and $Sp(N)$, but they are not decorative. They matter in grand unification, string compactifications, conformal field theory, exceptional global symmetries, and certain supersymmetric or strongly coupled systems.

## SU(N) Casimir from a Young diagram

Let an $SU(N)$ representation be described by a Young diagram with row lengths

$$
\lambda_1\ge\lambda_2\ge\cdots\ge\lambda_N\ge0,
$$

and let

$$
k=\sum_i\lambda_i
$$

be the number of boxes. With $T(\mathbf N)=1/2$, the quadratic Casimir is

$$
C_2(\lambda)
=\frac12\left[
Nk+
\sum_i\lambda_i(\lambda_i+1-2i)
-\frac{k^2}{N}
\right].
$$

For the fundamental, $\lambda=(1,0,\ldots,0)$ and $k=1$, so

$$
C_2(\mathbf N)
=\frac12\left(N-\frac1N\right)
=\frac{N^2-1}{2N}.
$$

For the two-index antisymmetric representation, $\lambda=(1,1,0,\ldots)$ and $k=2$, giving

$$
C_2(A_2)=\frac{(N+1)(N-2)}N.
$$

For the two-index symmetric representation, $\lambda=(2,0,\ldots)$ and $k=2$, giving

$$
C_2(S_2)=\frac{(N-1)(N+2)}N.
$$

The Dynkin index then follows from

$$
T(R)=\frac{C_2(R)\dim R}{\dim G}.
$$

This is often faster than evaluating traces directly.

## Center charge and N-ality

The center of $SU(N)$ is

$$
Z(SU(N))\cong\mathbb Z_N.
$$

A central element

$$
z=e^{2\pi i m/N}\mathbf 1
$$

acts on a tensor with $k$ fundamental indices by multiplication by

$$
z^k=e^{2\pi i mk/N}.
$$

For an $SU(N)$ representation described by a Young diagram $\lambda$, the center charge is determined by

$$
k=|\lambda|\,\bmod N.
$$

This residue is called $N$-ality.

Representations with zero $N$-ality descend to representations of

$$
PSU(N)=SU(N)/\mathbb Z_N.
$$

Representations with nonzero $N$-ality do not. Thus the adjoint representation descends to $PSU(N)$, but the fundamental representation does not.

This matters in QFT because Wilson lines are labeled by representations of the gauge group, not merely by representations of the Lie algebra. A pure Yang–Mills theory with local algebra $\mathfrak{su}_N$ can have different global forms, such as $SU(N)$ or $PSU(N)$, and these choices differ in their line operators and magnetic sectors even though their perturbative gluon vertices are locally the same.

## Global forms of common groups

The Lie algebra does not determine the global group. A compact connected Lie group with Lie algebra $\mathfrak g$ is obtained from the simply connected group $\widetilde G$ by quotienting by a subgroup of its center:

$$
G=\widetilde G/\Gamma,
\qquad
\Gamma\subset Z(\widetilde G).
$$

Examples:

$$
SU(N)/\mathbb Z_N=PSU(N),
$$

and

$$
Spin(N)/\mathbb Z_2=SO(N)
$$

for the quotient by the element acting trivially on vectors.

The center of $Spin(N)$ depends on $N$:

| Simply connected group | Center |
|---|---:|
| $Spin(2n+1)$ | $\mathbb Z_2$ |
| $Spin(4n)$ | $\mathbb Z_2\times\mathbb Z_2$ |
| $Spin(4n+2)$ | $\mathbb Z_4$ |

These distinctions control which spinor and vector representations are honest representations of the chosen group. They also control possible one-form symmetries and line-operator lattices.

## Cubic anomalies and reality type

In four-dimensional chiral gauge theories, local gauge anomalies are controlled by cubic traces of generators. For complex representations, define the anomaly coefficient by

$$
\operatorname{tr}_R\bigl(T^a\{T^b,T^c\}\bigr)
=A(R)\operatorname{tr}_{F}\bigl(T^a\{T^b,T^c\}\bigr)
$$

for $SU(N)$, with $F$ the fundamental. This convention gives

$$
A(F)=1,
\qquad
A(\overline R)=-A(R).
$$

Real and pseudoreal representations have vanishing perturbative cubic anomaly:

$$
A(R)=0.
$$

For $SU(N)$, the two-index antisymmetric representation has

$$
A(A_2)=N-4
$$

in the normalization $A(F)=1$. Thus the $SU(5)$ representation $\mathbf{10}$ has anomaly coefficient $1$, and $\overline{\mathbf 5}$ has anomaly coefficient $-1$, so

$$
\mathbf{10}\oplus\overline{\mathbf 5}
$$

is locally anomaly-free as an $SU(5)$ chiral multiplet.

For $SU(2)$, the perturbative cubic anomaly vanishes because there is no nonzero symmetric invariant $d^{abc}$. This does not remove every possible anomaly: $SU(2)$ has a famous global anomaly for an odd number of Weyl doublets. Local anomaly cancellation and global anomaly cancellation are different tests.

## How group data enters beta functions

For a four-dimensional non-Abelian gauge theory, the one-loop beta function has the schematic form

$$
\beta(g)=-\frac{g^3}{16\pi^2}b_0+O(g^5).
$$

For Dirac fermions and complex scalars in representations $R_f$ and $R_s$,

$$
b_0
=\frac{11}{3}C_2(G)
-\frac{4}{3}\sum_{\text{Dirac }f}T(R_f)
-\frac{1}{3}\sum_{\text{complex }s}T(R_s).
$$

Equivalently, each Weyl fermion contributes $-(2/3)T(R)$, and each real scalar contributes $-(1/6)T(R)$.

For QCD with gauge group $SU(3)$ and $n_f$ Dirac quarks in the fundamental representation,

$$
C_2(G)=3,
\qquad
T(F)=\frac12,
$$

so

$$
b_0=11-\frac{2}{3}n_f.
$$

The physics of asymptotic freedom is dynamical, but the coefficient knows the group theory.

## Standard Model local data

The Standard Model is locally based on

$$
\mathfrak{su}_3\oplus\mathfrak{su}_2\oplus\mathfrak u_1.
$$

The most-used nonabelian group factors are:

| Factor | $C_A$ | Fundamental $T_F$ | Fundamental $C_F$ | Center |
|---|---:|---:|---:|---:|
| $SU(3)_c$ | 3 | $1/2$ | $4/3$ | $\mathbb Z_3$ |
| $SU(2)_L$ | 2 | $1/2$ | $3/4$ | $\mathbb Z_2$ |

The abelian factor requires a separate normalization choice. Hypercharge $Y$ can be normalized in the Standard Model convention, or in grand-unified convention with

$$
g_1^2=\frac53 g_Y^2.
$$

Because $U(1)$ generators can be rescaled together with the coupling, abelian “Dynkin indices” are charge-squared sums only after a normalization has been fixed.

The global form of the Standard Model gauge group is subtler than the local algebra. Common possibilities are quotients of

$$
SU(3)\times SU(2)\times U(1)
$$

by a subgroup of its center, with the famous $\mathbb Z_6$ quotient playing an important role in many discussions. These choices do not alter the local perturbative Feynman rules, but they affect line operators, allowed bundles, monopole charges, and global symmetries.

## U(1) data

For $U(1)$, every irreducible representation is one-dimensional and labeled by a charge $q$:

$$
\psi\mapsto e^{iq\alpha}\psi.
$$

There is no nontrivial adjoint self-interaction:

$$
f^{abc}=0.
$$

The analog of $T(R)$ is charge squared, but only after choosing a normalization for the generator. If a Weyl fermion has charge $q$, then its contributions to abelian anomaly sums involve powers such as

$$
q,
\qquad
q^3,
\qquad
q\,T(R_{\text{nonabelian}}),
$$

depending on whether the anomaly is gravitational–$U(1)$, $U(1)^3$, or mixed nonabelian–nonabelian–$U(1)$.

This is why hypercharge normalization is not a harmless cosmetic detail when comparing beta functions, anomalies, and grand-unified embeddings.

## A compact checklist

When specifying a gauge theory, record the following.

1. The local algebra $\mathfrak g$.
2. The global group $G=\widetilde G/\Gamma$.
3. The generator normalization.
4. The matter representations $R_i$.
5. $\dim R_i$, $T(R_i)$, $C_2(R_i)$, and reality type.
6. Center charges and which Wilson lines are allowed.
7. Perturbative gauge anomaly coefficients for chiral matter.
8. Global anomaly constraints, if relevant.
9. Abelian charge normalization and quotient identifications.
10. Any discrete theta angles or topological terms, if the global form permits them.

Skipping item 2 is fine for a quick one-loop calculation. It is not fine for a nonperturbative definition of the theory.

## Common pitfalls

The Lie algebra is not the full gauge group. $SU(N)$ and $PSU(N)$ have the same local gauge bosons but different line operators and bundle sectors.

The symbols $T(R)$ and $C_2(R)$ are convention-dependent. A formula is meaningless unless the generator normalization is stated.

The adjoint index and adjoint Casimir are equal in the usual simple-group normalization because $\dim R=\dim G$ for the adjoint. That equality should not be blindly extended to other representations.

The $U(1)$ case is not obtained by setting $C_A=0$ and forgetting normalization. Abelian charges can be rescaled with the coupling, and anomaly sums depend on the chosen normalization.

Perturbative local anomalies and global anomalies are different. $SU(2)$ has no local cubic anomaly but can have a global anomaly.

Young diagrams describe $SU(N)$ tensor representations efficiently, but center charge and global form decide whether a representation is allowed for a quotient group.

## Relations to other pages

[Young Tableaux](/math-toolkit/groups-representations/young-tableaux/) gives the tensor-index technology behind many $SU(N)$ representation dimensions and Casimirs.

[Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/) explains highest weights, Dynkin labels, roots, coroots, and Weyl chambers. This page turns that data into QFT-ready lookup formulas.

[Characters](/math-toolkit/groups-representations/characters/) explains how representation decompositions, singlet projections, and group averages can be computed from traces.

Later pages on gauge theory, anomalies, renormalization, lattice gauge theory, line operators, generalized symmetries, and the Standard Model should link back here whenever a formula uses $C_A$, $C_F$, $T_F$, center charge, or anomaly coefficients without derivation.

## Research status

The local data in this page are established representation theory. Dimensions, Dynkin indices, Casimirs, centers, dual Coxeter numbers, and anomaly coefficients are standard once conventions are fixed.

The active frontier lies in global and generalized data: global form of the gauge group, line-operator spectra, one-form symmetries, discrete theta angles, generalized anomalies, noninvertible defects, and global constraints on quantum gravity or condensed-matter phases. Modern QFT treats these as part of the specification of the theory, not optional decoration.

## Exercises

### Exercise 1

Derive the relation

$$
C_2(R)\dim R=T(R)\dim G.
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

Taking the trace over $R$ gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=C_2(R)\dim R.
$$

Now use

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

Setting $a=b$ and summing over $a$ gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=T(R)\delta^{aa}=T(R)\dim G.
$$

Equating the two expressions gives

$$
C_2(R)\dim R=T(R)\dim G.
$$

</details>

### Exercise 2

Use the $SU(N)$ Young-diagram Casimir formula to compute $C_2$ of the fundamental representation.

<details><summary><strong>Solution</strong></summary>

For the fundamental representation, the row lengths are

$$
\lambda=(1,0,\ldots,0),
$$

so $k=1$. The Casimir formula gives

$$
C_2(\lambda)
=\frac12\left[
Nk+
\sum_i\lambda_i(\lambda_i+1-2i)
-\frac{k^2}{N}
\right].
$$

Only $i=1$ contributes to the sum:

$$
\lambda_1(\lambda_1+1-2)=1(1+1-2)=0.
$$

Thus

$$
C_2(F)=\frac12\left(N-\frac1N\right)
=\frac{N^2-1}{2N}.
$$

</details>

### Exercise 3

Compute the one-loop coefficient $b_0$ for $SU(3)$ gauge theory with $n_f$ Dirac fermions in the fundamental representation.

<details><summary><strong>Solution</strong></summary>

For $SU(3)$,

$$
C_2(G)=C_A=3,
\qquad
T(F)=\frac12.
$$

With $n_f$ Dirac fermions and no scalars,

$$
b_0=\frac{11}{3}C_A-\frac{4}{3}n_f T(F).
$$

Therefore

$$
b_0=\frac{11}{3}(3)-\frac{4}{3}n_f\left(\frac12\right)
=11-\frac23 n_f.
$$

</details>

### Exercise 4

For $SU(N)$, find the $N$-ality of the fundamental representation, the adjoint representation, and the two-index antisymmetric representation.

<details><summary><strong>Solution</strong></summary>

$N$-ality is the number of boxes in the Young diagram modulo $N$.

The fundamental has one box, so

$$
\text{$N$-ality}(F)=1\,\bmod N.
$$

The adjoint has Dynkin labels $[1,0,\ldots,0,1]$ and can be represented by the Young diagram with row lengths

$$
(2,1,1,\ldots,1)
$$

with $N$ boxes total. Hence

$$
\text{$N$-ality}(\operatorname{Adj})=0\,\bmod N.
$$

The two-index antisymmetric representation has two boxes, so

$$
\text{$N$-ality}(A_2)=2\,\bmod N.
$$

Thus the adjoint descends to $PSU(N)$, while the fundamental does not. The two-index antisymmetric descends only when $2=0\,\bmod N$, which for $N\ge2$ happens for $N=2$, where the representation is a singlet.

</details>

### Exercise 5

Use the anomaly coefficients

$$
A(F)=1,
\qquad
A(\overline R)=-A(R),
\qquad
A(A_2)=N-4
$$

for $SU(N)$ to check that $\mathbf{10}\oplus\overline{\mathbf 5}$ is locally anomaly-free for $SU(5)$.

<details><summary><strong>Solution</strong></summary>

For $SU(5)$, the $\mathbf{10}$ is the two-index antisymmetric representation $A_2$. Its anomaly coefficient is

$$
A(A_2)=N-4=5-4=1.
$$

The $\overline{\mathbf 5}$ is the antifundamental, so

$$
A(\overline{\mathbf 5})=-A(\mathbf 5)=-1.
$$

Therefore the total local cubic anomaly is

$$
A(\mathbf{10})+A(\overline{\mathbf 5})=1-1=0.
$$

So $\mathbf{10}\oplus\overline{\mathbf 5}$ is locally anomaly-free as an $SU(5)$ chiral matter representation.

</details>

## References

- H. Georgi, *Lie Algebras in Particle Physics*, for Casimirs, Dynkin indices, Young tableaux, and particle-physics group theory.
- R. Slansky, “Group Theory for Unified Model Building,” for extensive representation tables and anomaly coefficients.
- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for compact groups, roots, weights, centers, and representation theory.
- W. Fulton and J. Harris, *Representation Theory*, for highest weights, dimensions, and classical group representations.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for gauge theory, representations, anomalies, and renormalization.
- M. Srednicki, *Quantum Field Theory*, for non-Abelian gauge theory, group factors, beta functions, and anomalies.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for practical Standard Model group theory and loop factors.
- S. Coleman, *Aspects of Symmetry*, for $SU(2)$, $SU(3)$, representations, symmetry, and anomaly-related physics.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, for QCD group factors and perturbative applications.
- L. S. Brown, *Quantum Field Theory*, and J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for group factors in renormalization and gauge theories.

## Version history

- **2026-06-24:** Initial polished draft for the Mathematical Toolkit volume.
