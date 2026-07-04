---
title: "Young Tableaux"
description: "A QFT-oriented guide to Young diagrams, Young symmetrizers, Schur functors, hook-length formulas, Littlewood–Richardson products, and SU(N) representation bookkeeping."
sidebar:
  label: "Young Tableaux"
  order: 9
level: Graduate
status: "Polished draft"
source: "Standard representation theory and QFT references, including Fulton–Harris, Fulton, Georgi, Hall, Humphreys, Cornwell, Tung, Weinberg, Srednicki, Coleman, and Schwartz."
topics:
  - Young diagrams
  - Young tableaux
  - Schur functors
  - tensor symmetries
  - Littlewood–Richardson rule
  - SU(N) representations
  - gauge theory group data
canonicalTopics:
  - young-tableaux
  - young-diagrams
  - young-symmetrizers
  - schur-functors
  - littlewood-richardson-rule
  - su-n-representations
  - tensor-product-decomposition
researchStatus:
  established:
    - "Young-diagram and Young-tableau methods give a standard finite-dimensional representation-theoretic calculus for GL(N), U(N), and SU(N), with precise restrictions and equivalences depending on N and on the global form of the group."
  active:
    - "In modern QFT the same combinatorics appears in large-N expansions, color decompositions, Hilbert-series counting, Schur–Weyl duality, symmetric-product theories, half-BPS sectors, and categorical refinements of representation theory."
---

## Summary

Young diagrams are a compact language for tensor symmetries. Young tableaux are Young diagrams filled with labels. Together they give one of the fastest practical ways to construct and decompose representations of $GL(N)$, $U(N)$, and $SU(N)$.

The basic idea is almost embarrassingly simple: draw boxes to remember which tensor indices are symmetrized and which are antisymmetrized. Rows mean symmetrization. Columns mean antisymmetrization. A diagram with $k$ boxes describes a symmetry type inside a $k$-fold tensor product,

$$
V^{\otimes k}.
$$

For a complex $N$-dimensional vector space $V$, a Young diagram $\lambda$ with at most $N$ rows defines an irreducible polynomial representation of $GL(V)$, called the Schur functor $S_\lambda(V)$. After restricting to $SU(N)$, diagrams that differ by full columns of height $N$ define the same representation, because the totally antisymmetric tensor $\epsilon_{i_1\cdots i_N}$ is an $SU(N)$ singlet.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a Young diagram, row symmetrization, column antisymmetrization, Schur functor construction, Littlewood–Richardson multiplication, and QFT uses.](/figures/math-toolkit/young-tableaux-workflow.svg)

<figcaption>

Young-diagram technology starts with tensor powers $V^{\otimes k}$. Rows symmetrize indices, columns antisymmetrize indices, and the resulting Young symmetrizer projects onto a definite $GL(N)$ or $SU(N)$ representation. Tensor products are decomposed by the Littlewood–Richardson rule, while QFT applications include color tensors, flavor multiplets, baryons, operator bases, and large-$N$ counting.

</figcaption>
</figure>

In QFT this is not decoration. Young diagrams organize quark flavor multiplets, color tensors, gauge-invariant operators, tensor-product decompositions, invariant couplings, large-$N$ baryons, and the representation content of local operators with many fields or derivatives. They turn “a tensor with many indices” into something one can actually compute with.

## Prerequisites

You should know [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/), [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/), [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/), and [Characters](/math-toolkit/groups-representations/characters/).

The most important prerequisite is the tensor product. Young diagrams do not replace tensor algebra; they are a notation for controlling it.

Throughout the page, $V\cong\mathbb C^N$ denotes the defining representation of $GL(N)$, $U(N)$, or $SU(N)$ unless stated otherwise. For $SU(N)$ we use physics language and call $V$ the fundamental representation, usually written $\mathbf N$.

## Core idea

Let $V$ be a vector space. The $k$-fold tensor product $V^{\otimes k}$ carries two commuting actions:

1. $GL(V)$ acts on each tensor factor.
2. The symmetric group $S_k$ permutes the tensor factors.

Explicitly,

$$
g\cdot(v_1\otimes\cdots\otimes v_k)
=(gv_1)\otimes\cdots\otimes(gv_k),
$$

while

$$
\sigma\cdot(v_1\otimes\cdots\otimes v_k)
=v_{\sigma^{-1}(1)}\otimes\cdots\otimes v_{\sigma^{-1}(k)}.
$$

These two actions commute. Young diagrams label the simultaneous decomposition of $V^{\otimes k}$ under these two structures. This is the content of Schur–Weyl duality:

$$
V^{\otimes k}
\cong
\bigoplus_{\lambda\vdash k,\,\ell(\lambda)\le N}
S_\lambda(V)\otimes M_\lambda.
$$

Here $\lambda\vdash k$ means that $\lambda$ is a partition of $k$, $\ell(\lambda)$ is the number of nonzero rows, $S_\lambda(V)$ is an irreducible $GL(V)$ representation, and $M_\lambda$ is an irreducible $S_k$ representation.

The slogan is:

$$
\text{Young diagram}
=
\text{symmetry type of tensor indices}.
$$

For one row of $k$ boxes, all indices are symmetrized:

$$
S_{(k)}(V)=\operatorname{Sym}^k V.
$$

For one column of $k$ boxes, all indices are antisymmetrized:

$$
S_{(1^k)}(V)=\Lambda^k V.
$$

Every other Young diagram is a controlled mixture of row symmetrization and column antisymmetrization.

## Young diagrams as partitions

A Young diagram is specified by a partition

$$
\lambda=(\lambda_1,\lambda_2,\ldots,\lambda_r),
\qquad
\lambda_1\ge\lambda_2\ge\cdots\ge\lambda_r>0.
$$

The integer $\lambda_i$ is the number of boxes in row $i$. The total number of boxes is

$$
|\lambda|=\sum_i\lambda_i.
$$

The transpose or conjugate partition $\lambda'$ is obtained by reflecting the diagram across its main diagonal. Its parts $\lambda'_j$ are the column lengths.

For example,

$$
\lambda=(3,2)
$$

has three boxes in the first row and two boxes in the second row. Its transpose is

$$
\lambda'=(2,2,1).
$$

A diagram can be used for $GL(N)$ only if it has at most $N$ rows:

$$
\ell(\lambda)\le N.
$$

This is because any column of length $N+1$ would require antisymmetrizing $N+1$ indices in an $N$-dimensional vector space, which gives zero.

## Tableaux and fillings

A Young tableau is a Young diagram with entries placed in its boxes. Different types of tableaux are used for different tasks.

A **standard tableau** of size $k$ uses the labels

$$
1,2,\ldots,k
$$

exactly once, with entries increasing along rows and columns. Standard tableaux label bases for symmetric-group representations and concrete Young symmetrizers.

A **semistandard tableau** uses entries from

$$
1,2,\ldots,N,
$$

with entries weakly increasing along rows and strictly increasing down columns. Semistandard tableaux count weights of $GL(N)$ representations and give a combinatorial formula for characters.

A **physics tensor filling** often uses boxes as placeholders for tensor indices rather than numbers. For example, a two-index tensor $T^{ij}$ decomposes into

$$
T^{ij}=T^{(ij)}+T^{[ij]},
$$

corresponding to

$$
V\otimes V=\operatorname{Sym}^2V\oplus\Lambda^2V.
$$

The boxes are bookkeeping devices for these symmetries.

## Row symmetrization and column antisymmetrization

Take a Young diagram $\lambda$ with $k$ boxes and choose a standard filling $T$. Let $R_T\subset S_k$ be the subgroup that permutes labels within each row. Let $C_T\subset S_k$ be the subgroup that permutes labels within each column.

Define the row symmetrizer

$$
a_T=\sum_{r\in R_T}r
$$

and the column antisymmetrizer

$$
b_T=\sum_{c\in C_T}\operatorname{sgn}(c)c.
$$

A Young symmetrizer is, up to convention,

$$
c_T=a_Tb_T.
$$

Some books use $b_Ta_T$ instead. The two conventions produce equivalent irreducible representations but may differ by basis choices and normalization.

Applying $c_T$ to $V^{\otimes k}$ imposes the row and column symmetries encoded by $\lambda$. The image is an irreducible $GL(V)$ representation when $\ell(\lambda)\le N$.

The symmetrizer is not usually normalized as a projector. Instead it is quasi-idempotent:

$$
c_T^2=\kappa_T c_T
$$

for a nonzero scalar $\kappa_T$. A true projector is $c_T/\kappa_T$.

This matters in explicit tensor calculations. If you symmetrize and antisymmetrize indices but forget normalization, you may get the right representation but the wrong coefficient in a Lagrangian, amplitude, or two-point function.

## First decompositions

The first nontrivial tensor-product decomposition is

$$
V\otimes V
=\operatorname{Sym}^2V\oplus\Lambda^2V.
$$

In Young-diagram language this is

$$
(1)\otimes(1)=(2)\oplus(1,1).
$$

For $SU(N)$, this becomes

$$
\mathbf N\otimes\mathbf N
=\operatorname{Sym}^2\mathbf N\oplus\Lambda^2\mathbf N,
$$

where the two summands have dimensions

$$
\frac{N(N+1)}{2}
\qquad\text{and}\qquad
\frac{N(N-1)}{2}.
$$

For $SU(3)$,

$$
\mathbf 3\otimes\mathbf 3=\mathbf 6\oplus\overline{\mathbf 3}.
$$

The antisymmetric product is $\overline{\mathbf 3}$ because

$$
\Lambda^2\mathbf 3\cong\overline{\mathbf 3}
$$

using the invariant tensor $\epsilon_{ijk}$.

For $SU(2)$,

$$
\mathbf 2\otimes\mathbf 2=\mathbf 3\oplus\mathbf 1.
$$

The symmetric part is spin $1$, and the antisymmetric part is a singlet.

These examples are the baby version of much of particle spectroscopy and gauge-theory color algebra.

## Hook lengths and dimensions

Let $\lambda$ be a Young diagram. For a box $s=(i,j)$ in row $i$ and column $j$, define its hook length

$$
h(s)=\lambda_i-j+\lambda'_j-i+1.
$$

This counts the box itself, the boxes to its right, and the boxes below it.

The dimension of the corresponding $GL(N)$ representation is given by the hook-content formula:

$$
\dim S_\lambda(\mathbb C^N)
=\prod_{(i,j)\in\lambda}
\frac{N+j-i}{h(i,j)}.
$$

This formula is one of the main reasons Young diagrams are useful in QFT: dimensions of large tensor representations become products over boxes.

For one row of $k$ boxes,

$$
\dim\operatorname{Sym}^k\mathbb C^N
=\binom{N+k-1}{k}.
$$

For one column of $k$ boxes,

$$
\dim\Lambda^k\mathbb C^N
=\binom{N}{k}.
$$

For $\lambda=(2,1)$, the boxes have factors

$$
\frac{N}{3},\qquad N+1,
\qquad N-1,
$$

so

$$
\dim S_{(2,1)}(\mathbb C^N)
=\frac{N(N^2-1)}{3}.
$$

For $N=3$, this gives $8$, the adjoint representation of $SU(3)$.

## From Young diagrams to SU(N) Dynkin labels

For $SU(N)$, a Young diagram with row lengths

$$
\lambda=(\lambda_1,\lambda_2,\ldots,\lambda_{N-1},\lambda_N)
$$

determines Dynkin labels

$$
a_i=\lambda_i-\lambda_{i+1},
\qquad
 i=1,\ldots,N-1,
$$

where missing rows are treated as zero.

Conversely, the Dynkin labels determine row-length differences. Up to an overall full column of height $N$,

$$
\lambda_i=a_i+a_{i+1}+\cdots+a_{N-1}.
$$

The phrase “up to a full column” is important. For $SU(N)$, adding the same integer to all $N$ row lengths tensors the $U(N)$ representation by a power of $\det V$. Since

$$
\det g=1
$$

for $g\in SU(N)$, this operation does not change the $SU(N)$ representation.

Thus $SU(N)$ diagrams are really diagrams modulo full columns of height $N$.

For $SU(3)$, Dynkin labels $[p,q]$ correspond to row lengths

$$
\lambda=(p+q,q,0).
$$

The dimension is

$$
\dim[p,q]
=\frac12(p+1)(q+1)(p+q+2).
$$

Examples are

$$
[1,0]=\mathbf 3,
\qquad
[0,1]=\overline{\mathbf 3},
\qquad
[2,0]=\mathbf 6,
\qquad
[1,1]=\mathbf 8.
$$

For $SU(2)$, a Young diagram modulo columns of height $2$ leaves only a single row. A row of $2j$ boxes is spin $j$ and has dimension

$$
2j+1.
$$

So ordinary angular momentum addition is the rank-one shadow of the Young-diagram calculus.

## Center charge and N-ality

The center of $SU(N)$ is

$$
Z(SU(N))\cong\mathbb Z_N.
$$

A central element

$$
z=e^{2\pi i/N}\mathbf 1
$$

acts on the fundamental representation by multiplication by $z$. Therefore it acts on a tensor with $k$ fundamental indices by $z^k$.

For an $SU(N)$ representation described by a Young diagram $\lambda$, the center charge is determined by the number of boxes:

$$
z\mapsto z^{|\lambda|}.
$$

The number

$$
|\lambda|\,\bmod N
$$

is called the $N$-ality of the representation.

This is not just representation-theory trivia. In gauge theory, $N$-ality controls screening by adjoint matter, the center charge of Wilson lines, and whether a representation descends to a quotient group such as

$$
PSU(N)=SU(N)/\mathbb Z_N.
$$

A representation of $SU(N)$ descends to a representation of $PSU(N)$ exactly when its $N$-ality is zero.

For $SU(3)$, triality is

$$
|\lambda|\,\bmod 3.
$$

In Dynkin labels $[p,q]$, this is

$$
p+2q\,\bmod 3.
$$

Thus $\mathbf 3$ has triality $1$, $\overline{\mathbf 3}$ has triality $2$, and $\mathbf 8$ has triality $0$.

## Conjugate representations

For $SU(N)$, the conjugate of the fundamental representation is represented by a column of height $N-1$:

$$
\overline{\mathbf N}\cong\Lambda^{N-1}\mathbf N.
$$

The isomorphism uses the invariant epsilon tensor,

$$
\epsilon_{i_1\cdots i_N}.
$$

For general diagrams, conjugation can be described by complementing the diagram inside a suitable rectangle and then removing full columns. In Dynkin labels, it is easier:

$$
[a_1,a_2,\ldots,a_{N-1}]^*
=[a_{N-1},\ldots,a_2,a_1].
$$

For $SU(3)$,

$$
[p,q]^*=[q,p].
$$

Thus

$$
\mathbf 3=[1,0],
\qquad
\overline{\mathbf 3}=[0,1],
\qquad
\mathbf 8=[1,1]^*=\mathbf 8.
$$

A representation is real or pseudoreal only if it is equivalent to its conjugate. Young diagrams make conjugation visually accessible, but the invariant bilinear form requires additional information.

For example, the $SU(2)$ fundamental is pseudoreal, not real. Its diagram is one box, but the reason is the invariant antisymmetric tensor $\epsilon_{ij}$.

## Littlewood–Richardson products

The tensor product of two $GL(N)$ representations decomposes as

$$
S_\lambda(V)\otimes S_\mu(V)
=\bigoplus_\nu c_{\lambda\mu}^{\ \ \nu}S_\nu(V),
$$

where the nonnegative integers $c_{\lambda\mu}^{\ \ \nu}$ are Littlewood–Richardson coefficients.

The Littlewood–Richardson rule gives a combinatorial method for computing them. One version is:

1. Add the boxes of $\mu$ to $\lambda$ to form $\nu$, never violating the Young-diagram shape.
2. Label the added boxes according to the rows of $\mu$.
3. Require the filling to be semistandard and satisfy the lattice-word condition.
4. Count the valid fillings.

The full rule is more precise than this slogan, but the practical moral is clear: tensor-product decomposition is box addition with strict constraints.

The simplest products are

$$
(1)\otimes(1)=(2)\oplus(1,1),
$$

and

$$
(2)\otimes(1)=(3)\oplus(2,1).
$$

For $SU(N)$ these translate into decompositions such as

$$
\operatorname{Sym}^2\mathbf N\otimes\mathbf N
=\operatorname{Sym}^3\mathbf N\oplus S_{(2,1)}\mathbf N.
$$

For $SU(3)$,

$$
\mathbf 6\otimes\mathbf 3=\mathbf{10}\oplus\mathbf 8.
$$

This is precisely the kind of decomposition used in flavor $SU(3)$ and color algebra.

## SU(3) flavor examples

Historically, Young tableaux became beloved in particle physics because $SU(3)$ flavor multiplets are visually simple.

The fundamental quark flavor multiplet is

$$
\mathbf 3=(u,d,s).
$$

Two quarks decompose as

$$
\mathbf 3\otimes\mathbf 3
=\mathbf 6\oplus\overline{\mathbf 3}.
$$

The symmetric representation $\mathbf 6$ has Dynkin labels $[2,0]$, while the antisymmetric representation $\overline{\mathbf 3}$ has labels $[0,1]$.

Three quarks decompose as

$$
\mathbf 3\otimes\mathbf 3\otimes\mathbf 3
=\mathbf{10}\oplus\mathbf 8\oplus\mathbf 8\oplus\mathbf 1.
$$

In Young-diagram language,

$$
(1)\otimes(1)\otimes(1)
=(3)\oplus2(2,1)\oplus(1,1,1),
$$

and for $SU(3)$ these become

$$
\mathbf{10},\qquad \mathbf 8,\qquad \mathbf 1.
$$

The totally antisymmetric three-box column is an $SU(3)$ singlet because it is built from $\epsilon_{ijk}$.

This same logic appears in QCD color: a color-singlet baryon uses

$$
\epsilon_{ijk}q^iq^jq^k.
$$

The fact that the color part is antisymmetric constrains the allowed spin-flavor-spatial symmetry of the full wavefunction. Representation theory quietly enforces Fermi statistics. Tiny boxes, big consequences.

## SU(N) adjoint representation

The adjoint representation of $SU(N)$ has Dynkin labels

$$
[1,0,\ldots,0,1].
$$

As a tensor statement,

$$
\mathbf N\otimes\overline{\mathbf N}
=\mathbf 1\oplus\operatorname{Adj}.
$$

Equivalently, an adjoint-valued object can be represented as a traceless tensor

$$
X^i{}_{j},
\qquad
X^i{}_{i}=0.
$$

The dimension is

$$
N^2-1.
$$

The corresponding Young diagram can be represented by row lengths

$$
(2,1,1,\ldots,1,0),
$$

with $N-1$ nonzero rows. For $SU(3)$ this is $(2,1)$, whose dimension is $8$. For $SU(2)$ this reduces, after removing columns of height $2$, to a row of two boxes, the spin-$1$ representation.

This is a good example of why $SU(N)$ diagrams must be read modulo full columns.

## Trace removal and irreducibility

Young symmetrization alone is not always the whole story when invariant tensors are available.

For $GL(N)$, the Schur functors $S_\lambda(V)$ are irreducible polynomial representations. For $SU(N)$, restriction is controlled by removing determinant columns. But for orthogonal and symplectic groups, the defining representation has invariant tensors

$$
\delta_{ij}
\qquad\text{or}\qquad
\Omega_{ij},
$$

so tensors can have traces that must be removed to get irreducible representations.

For example, a symmetric two-tensor of $SO(N)$ decomposes into a traceless symmetric tensor plus a singlet:

$$
\operatorname{Sym}^2\mathbf N
=\operatorname{Sym}^2_0\mathbf N\oplus\mathbf 1.
$$

The Young diagram with two boxes in a row tells you the symmetry type, but not yet the trace constraint.

This is one of the most common traps. Young diagrams are most straightforward for $GL(N)$, $U(N)$, and $SU(N)$. They can be adapted to $SO(N)$ and $USp(2N)$, but extra trace and equivalence rules enter.

Spinor representations of $SO(N)$ are not ordinary tensor Young diagrams of the vector representation. They require Clifford algebra and spin weights.

## Schur polynomials and characters

For $U(N)$, the character of $S_\lambda(\mathbb C^N)$ is the Schur polynomial

$$
s_\lambda(x_1,\ldots,x_N),
$$

where $x_i$ are torus eigenvalues. The character can be written as

$$
s_\lambda(x)
=\frac{\det\left(x_i^{\lambda_j+N-j}\right)_{1\le i,j\le N}}
{\det\left(x_i^{N-j}\right)_{1\le i,j\le N}}.
$$

The denominator is the Vandermonde determinant,

$$
\prod_{i<j}(x_i-x_j).
$$

This is the type-$A$ Weyl character formula in concrete form.

The product of Schur polynomials expands as

$$
s_\lambda(x)s_\mu(x)
=\sum_\nu c_{\lambda\mu}^{\ \ \nu}s_\nu(x),
$$

with the same Littlewood–Richardson coefficients that decompose tensor products.

This is why the same diagrams appear in character theory, invariant counting, and Hilbert series. The representation ring is being written in a basis of Schur functions.

## Invariant tensors

Invariant tensors are the pieces of tensor products that contain the singlet representation.

For $SU(N)$, the basic invariant tensors are

$$
\delta^i{}_j
$$

and

$$
\epsilon_{i_1\cdots i_N},
\qquad
\epsilon^{i_1\cdots i_N}.
$$

The Kronecker tensor pairs a fundamental with an antifundamental. The epsilon tensor converts $N-1$ fundamentals into an antifundamental, or $N$ fundamentals into a singlet.

Young diagrams help decide whether a singlet can appear. For example,

$$
\mathbf N^{\otimes k}
$$

contains an $SU(N)$ singlet only if $k$ is a multiple of $N$, because the center charge must vanish:

$$
k\equiv0\,\bmod N.
$$

This condition is necessary but not always sufficient for a particular symmetrized component. The actual multiplicity is determined by the full decomposition.

In gauge theory, invariant tensors determine allowed interactions and gauge-invariant operators. A Yukawa coupling, quartic scalar term, baryon operator, or color-ordered amplitude exists only if the tensor product of the participating representations contains a singlet.

## Large-N intuition

Young diagrams are especially useful in large-$N$ gauge theory.

A representation built from a fixed number of boxes as $N\to\infty$ behaves like a finite tensor representation of the fundamental. Its dimension grows as a power of $N$ equal to the number of boxes:

$$
\dim S_\lambda(\mathbb C^N)
\sim
\frac{N^{|\lambda|}}{\prod_{s\in\lambda}h(s)}
\qquad
(N\to\infty,\ |\lambda|\text{ fixed}).
$$

This scaling is useful for large-$N$ counting of operators and color contractions.

Representations with $O(N)$ boxes are a different story. Their dimensions can grow exponentially with $N$, and the shape of the Young diagram becomes a macroscopic object. Such diagrams appear in large-$N$ matrix models, half-BPS sectors, giant gravitons, and related holographic settings.

The finite-box and large-shape regimes should not be casually mixed. Same boxes, very different asymptotics.

## QFT uses

Young tableaux appear in QFT in several recurring ways.

**Flavor multiplets.** Hadron multiplets under approximate flavor symmetries are classified by tensor products of fundamental quark representations.

**Color tensors.** QCD amplitudes and gauge-invariant operators require decomposition of products of fundamental, antifundamental, and adjoint representations.

**Operator bases.** Local operators with many fields and derivatives must be decomposed under Lorentz, flavor, gauge, and permutation symmetries. Young diagrams separate symmetric, antisymmetric, and mixed-symmetry structures.

**Baryons.** The epsilon tensor in $SU(N)$ produces baryon-like color singlets from $N$ fundamentals.

**Higher-spin and mixed-symmetry fields.** Tensor fields with many spacetime indices are classified by Young symmetries, though gauge constraints and trace constraints must be handled separately.

**Large-$N$ counting.** The number of boxes and the shape of diagrams control dimensions, Casimirs, and asymptotic behavior.

**Schur operators.** In supersymmetric gauge theories and matrix models, Schur polynomial operators diagonalize two-point functions in protected sectors.

Young tableaux are not a replacement for physical reasoning, but they are a splendid anti-chaos device.

## Common pitfalls

**Rows and columns are not interchangeable.** Rows symmetrize; columns antisymmetrize. Transposing a diagram usually gives a different representation.

**A diagram that works for $GL(N)$ may vanish for small $N$.** A column with more than $N$ boxes is zero for an $N$-dimensional defining representation.

**For SU(N), full columns of height N are trivial.** Adding or removing such columns changes a $U(N)$ representation by a determinant factor but leaves the $SU(N)$ representation unchanged.

**Young diagrams are not enough for SO(N) and USp(2N).** Orthogonal and symplectic groups have invariant bilinear forms, so trace constraints and additional equivalences appear.

**Spinor representations are not vector-index Young diagrams.** Spinors of $SO(N)$ require Clifford algebra and highest-weight data, not just boxes made from the vector representation.

**Symmetrizers need normalization.** The raw Young symmetrizer is usually not an idempotent projector. Correlator normalizations and kinetic terms can care about this.

**Tensor products are not obtained by arbitrary box addition.** The Littlewood–Richardson rule has constraints. Randomly appending boxes gives wrong multiplicities.

**Dimension formulas depend on N.** The same diagram has different dimensions for different $N$, and diagrams can become equivalent after removing full $SU(N)$ columns.

**N-ality is box number mod N, not dimension mod N.** The center charge of an $SU(N)$ representation is controlled by $|\lambda|\,\bmod N$.

## Relations to other pages

[Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/) explains the highest-weight language behind Young diagrams. For $SU(N)$, Dynkin labels and row-length differences are two ways of saying the same thing.

[Characters](/math-toolkit/groups-representations/characters/) explains how Schur polynomials and character multiplication encode the same tensor-product decompositions.

[Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/) uses Young diagrams for center charge, representation dimensions, invariant tensors, and common $SU(N)$ decompositions.

[Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/) explains why global form, center, and maximal tori matter before one starts drawing boxes.

The Clifford Algebras and Spinors chapter will handle spinor representations, gamma matrices, and Fierz identities. Do not force spinors into ordinary Young diagrams unless you are explicitly using spinor highest weights or spinorial Young-tableau technology.

## Research status

The finite-dimensional Young-diagram calculus for $GL(N)$, $U(N)$, and $SU(N)$ is standard and complete. Hook formulas, Schur functions, and Littlewood–Richardson coefficients are exact mathematical tools.

What remains active is not the basic calculus, but its use in more sophisticated QFT structures: large-$N$ asymptotics, protected operator sectors, symmetric-product theories, representation stability, Hilbert-series algorithms, tensor categories, and combinatorial bases for amplitudes and correlators.

When these tools appear in frontier topics, the same warning applies: the boxes are exact, but their physical interpretation depends on the Hilbert space, gauge group global form, operator mixing, and dynamics.

## Exercises

### Exercise 1

Use Young diagrams to decompose $\mathbf N\otimes\mathbf N$ for $SU(N)$. What are the dimensions of the two summands?

<details><summary><strong>Solution</strong></summary>

Two fundamentals have two possible Young symmetries:

$$
(1)\otimes(1)=(2)\oplus(1,1).
$$

Thus

$$
\mathbf N\otimes\mathbf N
=\operatorname{Sym}^2\mathbf N\oplus\Lambda^2\mathbf N.
$$

The dimensions are

$$
\dim\operatorname{Sym}^2\mathbf N=\frac{N(N+1)}2,
$$

and

$$
\dim\Lambda^2\mathbf N=\frac{N(N-1)}2.
$$

Their sum is

$$
\frac{N(N+1)}2+\frac{N(N-1)}2=N^2,
$$

as required.

</details>

### Exercise 2

Show that the $SU(3)$ representation with Young diagram $\lambda=(2,1)$ has dimension $8$.

<details><summary><strong>Solution</strong></summary>

Use the hook-content formula

$$
\dim S_\lambda(\mathbb C^N)
=\prod_{(i,j)\in\lambda}\frac{N+j-i}{h(i,j)}.
$$

For $\lambda=(2,1)$, the hook lengths are

$$
h(1,1)=3,
\qquad
h(1,2)=1,
\qquad
h(2,1)=1.
$$

The numerator factors are

$$
N,
\qquad
N+1,
\qquad
N-1.
$$

So

$$
\dim S_{(2,1)}(\mathbb C^N)
=\frac{N(N+1)(N-1)}3.
$$

For $N=3$,

$$
\dim S_{(2,1)}(\mathbb C^3)
=\frac{3\cdot4\cdot2}{3}=8.
$$

This is the adjoint representation of $SU(3)$.

</details>

### Exercise 3

For $SU(3)$, convert Dynkin labels $[p,q]$ into Young row lengths and derive the dimension formula

$$
\dim[p,q]=\frac12(p+1)(q+1)(p+q+2).
$$

<details><summary><strong>Solution</strong></summary>

For $SU(3)$,

$$
\lambda=(\lambda_1,\lambda_2,\lambda_3),
\qquad
p=\lambda_1-\lambda_2,
\qquad
q=\lambda_2-\lambda_3.
$$

After removing full columns, set $\lambda_3=0$. Then

$$
\lambda_2=q,
\qquad
\lambda_1=p+q.
$$

So

$$
\lambda=(p+q,q,0).
$$

The Weyl dimension formula for $SU(3)$ gives

$$
\dim[p,q]
=\prod_{1\le i<j\le3}\frac{\lambda_i-\lambda_j+j-i}{j-i}.
$$

The three factors are

$$
\frac{\lambda_1-\lambda_2+1}{1}=p+1,
$$

$$
\frac{\lambda_2-\lambda_3+1}{1}=q+1,
$$

and

$$
\frac{\lambda_1-\lambda_3+2}{2}=\frac{p+q+2}{2}.
$$

Therefore

$$
\dim[p,q]=\frac12(p+1)(q+1)(p+q+2).
$$

</details>

### Exercise 4

Compute the center charge of the $SU(5)$ representation with Young row lengths $\lambda=(2,1,1,0,0)$. Does it descend to a representation of $PSU(5)$?

<details><summary><strong>Solution</strong></summary>

The number of boxes is

$$
|\lambda|=2+1+1=4.
$$

The center charge is box number mod $5$:

$$
4\mod5.
$$

Since this is nonzero, the representation does not descend to a representation of

$$
PSU(5)=SU(5)/\mathbb Z_5.
$$

Only representations with zero $5$-ality descend to $PSU(5)$.

</details>

### Exercise 5

Use Young diagrams to decompose $\mathbf 3\otimes\mathbf 3\otimes\mathbf 3$ for $SU(3)$.

<details><summary><strong>Solution</strong></summary>

First,

$$
\mathbf 3\otimes\mathbf 3=\mathbf 6\oplus\overline{\mathbf 3}.
$$

Now tensor with another $\mathbf 3$.

The symmetric two-box representation gives

$$
(2)\otimes(1)=(3)\oplus(2,1),
$$

which corresponds to

$$
\mathbf 6\otimes\mathbf 3=\mathbf{10}\oplus\mathbf 8.
$$

The antisymmetric two-box column gives

$$
(1,1)\otimes(1)=(2,1)\oplus(1,1,1),
$$

which corresponds to

$$
\overline{\mathbf 3}\otimes\mathbf 3=\mathbf 8\oplus\mathbf 1.
$$

Therefore

$$
\mathbf 3\otimes\mathbf 3\otimes\mathbf 3
=\mathbf{10}\oplus\mathbf 8\oplus\mathbf 8\oplus\mathbf 1.
$$

The dimensions add correctly:

$$
10+8+8+1=27=3^3.
$$

</details>

## References

- W. Fulton and J. Harris, *Representation Theory*, for Schur functors, Young diagrams, highest weights, and classical group representation theory.
- W. Fulton, *Young Tableaux*, for a detailed mathematical account of tableaux, Schur functions, and Littlewood–Richardson coefficients.
- H. Georgi, *Lie Algebras in Particle Physics*, for Young-tableau methods in particle physics and $SU(N)$ representation theory.
- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for compact groups, highest weights, and representation theory.
- J. E. Humphreys, *Introduction to Lie Algebras and Representation Theory*, for roots, weights, and highest-weight representations.
- W.-K. Tung, *Group Theory in Physics*, and J. F. Cornwell, *Group Theory in Physics*, for physics applications of Young diagrams and tensor methods.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for symmetry representations and gauge-theory representation data.
- M. Srednicki, *Quantum Field Theory*, especially the sections on group representations and non-Abelian gauge theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for Standard Model group theory, color algebra, and practical representation decompositions.
- S. Coleman, *Aspects of Symmetry*, for symmetry multiplets and representation-theoretic reasoning in particle physics.

## Version history

- **2026-06-24:** Initial polished draft for the Mathematical Toolkit volume.
