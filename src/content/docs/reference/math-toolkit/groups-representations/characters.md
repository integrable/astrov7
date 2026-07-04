---
title: "Characters"
description: "A QFT-oriented guide to group characters, weight-sum formulas, Weyl invariance, character orthogonality, Weyl integration, tensor-product decompositions, and singlet projection."
sidebar:
  label: "Characters"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard compact-group representation theory and QFT references, including Hall, Georgi, Fulton–Harris, Knapp, Weyl character theory, Weinberg, Srednicki, Coleman, Schwartz, and Zee."
topics:
  - characters
  - compact Lie groups
  - Weyl character formula
  - Weyl integration formula
  - character orthogonality
  - tensor products
  - singlet projection
canonicalTopics:
  - characters
  - character-orthogonality
  - weyl-character-formula
  - weyl-integration-formula
  - tensor-product-decomposition
  - singlet-projection
researchStatus:
  established:
    - "Character theory of compact Lie groups is a standard, rigorous, and complete tool for finite-dimensional unitary representation theory, tensor-product decompositions, and invariant counting."
  active:
    - "Modern QFT generalizes character-like traces to indices, partition functions, line-defect traces, equivariant characters, supersymmetric localization formulas, modular characters, and categorical character theory."
---

## Summary

A character is the trace of a representation:

$$
\chi_R(g)=\operatorname{tr}_{V_R}\rho_R(g).
$$

That small trace carries a huge amount of information. For compact groups, characters determine irreducible representations, obey orthogonality relations, decompose tensor products, count invariant tensors, and turn many group-theory questions into integrals.

Characters are useful because they forget basis choices but remember representation content. Since trace is invariant under conjugation,

$$
\chi_R(hgh^{-1})=\chi_R(g),
$$

so a character is a class function. For compact connected Lie groups, every element is conjugate to an element of a maximal torus $T$, so the character can be studied as a Weyl-invariant function on $T$.

If the representation $R$ has weights $\lambda$ with multiplicities $m_\lambda$, then on the torus

$$
\chi_R(e^{i\theta\cdot H})
=\sum_{\lambda}m_\lambda e^{i\lambda(\theta)}.
$$

That is the character as a weight-generating function.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram showing how a representation gives weight spaces, then a character, then class-function technology such as orthogonality, tensor-product decomposition, singlet projection, and Weyl integration.](/figures/math-toolkit/character-technology-flow.svg)

<figcaption>

Character technology for compact groups. A representation decomposes into weight spaces on a maximal torus. The character sums the weights with multiplicity, becomes a Weyl-invariant class function, and can then be used for orthogonality, tensor-product decomposition, singlet projection, and Weyl integration.

</figcaption>
</figure>

For QFT, characters appear whenever symmetry is used as a computational filter: projecting onto singlets, counting gauge-invariant operators, decomposing products of fields, evaluating group averages, writing partition functions with chemical potentials, and organizing Hilbert spaces by charge.

## Prerequisites

You should know [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/), [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/), and [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/). The character is easiest to understand once weights are already familiar.

You should also know the $SU(2)$ ladder picture from [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/), since $SU(2)$ provides the cleanest first example of a character formula.

Throughout this page, $G$ is usually a compact Lie group and $R,S,T$ denote finite-dimensional complex representations. The Haar measure is normalized by

$$
\int_G dg=1.
$$

## Core idea

A representation is a matrix-valued function of the group:

$$
\rho_R:G\to GL(V_R).
$$

A character is its trace:

$$
\chi_R(g)=\operatorname{tr}_{V_R}\rho_R(g).
$$

At first glance, taking a trace sounds like throwing away information. But for compact groups, the trace keeps exactly the information needed to identify irreducible representations and compute their multiplicities in direct sums.

If

$$
V=\bigoplus_i n_i V_i
$$

is a direct sum of irreducible representations, then

$$
\chi_V(g)=\sum_i n_i\chi_i(g).
$$

So characters linearize direct sums.

If $V_R\otimes V_S$ is a tensor product, then

$$
\chi_{R\otimes S}(g)
=\operatorname{tr}_{V_R\otimes V_S}\bigl(\rho_R(g)\otimes\rho_S(g)\bigr)
=\chi_R(g)\chi_S(g).
$$

So characters turn tensor products into ordinary multiplication.

If

$$
R\otimes S=\bigoplus_T N_{RS}^{\ T}T,
$$

then

$$
\chi_R\chi_S=\sum_T N_{RS}^{\ T}\chi_T.
$$

Thus tensor-product decomposition becomes character multiplication followed by expansion in the irreducible character basis. It is representation theory with the annoying matrices hidden behind one elegant trace. Very civilized.

## Setup and conventions

A class function is a function $f:G\to\mathbb C$ satisfying

$$
f(hgh^{-1})=f(g)
$$

for all $g,h\in G$. Every character is a class function because

$$
\operatorname{tr}(ABA^{-1})=\operatorname{tr}(B).
$$

For compact $G$, define an inner product on class functions by

$$
\langle f_1,f_2\rangle
=\int_G dg\, f_1(g)^* f_2(g).
$$

With normalized Haar measure, irreducible characters obey

$$
\langle\chi_R,\chi_S\rangle=\delta_{RS}.
$$

This orthogonality is the character version of Schur's lemma.

A representation $V$ decomposes into irreducibles as

$$
V=\bigoplus_R n_R V_R.
$$

The multiplicity is extracted by projection:

$$
n_R=\langle\chi_R,\chi_V\rangle
=\int_G dg\,\chi_R(g)^*\chi_V(g).
$$

In particular, the multiplicity of the singlet representation is

$$
\dim V^G=\int_G dg\,\chi_V(g),
$$

because the trivial character is

$$
\chi_{\mathbf 1}(g)=1.
$$

This is the group-theoretic backbone behind gauge singlet counting, invariant tensor counting, and group averaging.

## Characters on a maximal torus

Let $G$ be compact and connected, and let $T$ be a maximal torus. Every element of $G$ is conjugate to an element of $T$. Since characters are class functions, it is enough to know $\chi_R$ on $T$.

Let $H_i$ be a Cartan basis and write

$$
t=e^{i\theta^iH_i}\in T.
$$

If $V_R$ decomposes into weight spaces

$$
V_R=\bigoplus_\lambda V_\lambda,
$$

then $t$ acts on $V_\lambda$ by multiplication by $e^{i\lambda(\theta)}$. Therefore

$$
\chi_R(t)=\sum_\lambda m_\lambda e^{i\lambda(\theta)},
\qquad
m_\lambda=\dim V_\lambda.
$$

The Weyl group acts on $T$ by conjugation inside $G$. Since characters are class functions,

$$
\chi_R(wt)=\chi_R(t)
\qquad
w\in W.
$$

Equivalently, the weight-sum expression is Weyl invariant as a whole, even if individual weights are moved around.

This is the first important lesson:

$$
\text{character} = \text{Weyl-invariant weighted sum over weights}.
$$

## The SU(2) characters

For $SU(2)$, a maximal torus can be parametrized by

$$
t(\theta)=\begin{pmatrix}
e^{i\theta/2}&0\\
0&e^{-i\theta/2}
\end{pmatrix}.
$$

The spin-$j$ representation has weights

$$
m=-j,-j+1,\ldots,j.
$$

Therefore its character is

$$
\chi_j(\theta)=\sum_{m=-j}^{j}e^{im\theta}.
$$

This finite geometric sum gives

$$
\chi_j(\theta)
=\frac{\sin\left((2j+1)\theta/2\right)}{\sin(\theta/2)}.
$$

Examples:

$$
\chi_0(\theta)=1,
$$

$$
\chi_{1/2}(\theta)=e^{i\theta/2}+e^{-i\theta/2}=2\cos(\theta/2),
$$

$$
\chi_1(\theta)=e^{i\theta}+1+e^{-i\theta}=1+2\cos\theta.
$$

Tensor products can now be read by multiplication. For example,

$$
\chi_{1/2}(\theta)^2
=(e^{i\theta/2}+e^{-i\theta/2})^2
=e^{i\theta}+2+e^{-i\theta}.
$$

But

$$
\chi_1(\theta)=e^{i\theta}+1+e^{-i\theta},
\qquad
\chi_0(\theta)=1.
$$

Therefore

$$
\chi_{1/2}^2=\chi_1+\chi_0,
$$

which is the character proof of

$$
\frac12\otimes\frac12=1\oplus0.
$$

The general Clebsch–Gordan rule becomes

$$
\chi_j\chi_k
=\sum_{\ell=|j-k|}^{j+k}\chi_\ell,
$$

where $\ell$ increases in integer steps.

## Orthogonality and multiplicities

For compact groups, irreducible characters form an orthonormal basis for square-integrable class functions. The basic formula is

$$
\int_G dg\,\chi_R(g)^*\chi_S(g)=\delta_{RS}.
$$

This gives the multiplicity of $T$ inside $R\otimes S$:

$$
N_{RS}^{\ T}
=\int_G dg\,\chi_T(g)^*\chi_R(g)\chi_S(g).
$$

More generally, the number of singlets in a tensor product

$$
V_{R_1}\otimes\cdots\otimes V_{R_n}
$$

is

$$
\dim\left(V_{R_1}\otimes\cdots\otimes V_{R_n}\right)^G
=\int_G dg\,\chi_{R_1}(g)\cdots\chi_{R_n}(g).
$$

This formula is a workhorse. It counts invariant tensors. In QFT language, it counts how many independent symmetry-invariant contractions can be built from fields in the specified representations, before spacetime indices, equations of motion, integration by parts, or other relations are imposed.

For a representation $R$, the space

$$
R\otimes R^*
$$

always contains one singlet if $R$ is irreducible:

$$
\int_G dg\,\chi_R(g)\chi_R(g)^*=1.
$$

That singlet is the identity map $R\to R$, or equivalently the invariant pairing between $R$ and $R^*$.

## Weyl integration formula

Because characters are class functions, it is inefficient to integrate them over the whole group. The Weyl integration formula reduces a group integral over $G$ to an integral over a maximal torus $T$.

For a class function $f$ on compact connected $G$,

$$
\int_G dg\,f(g)
=\frac1{|W|}\int_T dt\, |\Delta(t)|^2 f(t),
$$

where $W$ is the Weyl group and

$$
\Delta(e^{i\theta})
=\prod_{\alpha>0}\left(e^{i\alpha(\theta)/2}-e^{-i\alpha(\theta)/2}\right)
$$

is the Weyl denominator.

The factor $|\Delta(t)|^2$ is the Jacobian from diagonalizing group elements. For unitary matrices, it is the familiar Vandermonde determinant squared. This is why matrix model measures contain eigenvalue repulsion.

For $SU(2)$, the Weyl group has order $2$ and

$$
\Delta(\theta)=e^{i\theta/2}-e^{-i\theta/2}=2i\sin(\theta/2).
$$

With $\theta\in[0,2\pi)$ and normalized torus measure $d\theta/(2\pi)$,

$$
\int_{SU(2)}dg\,f(g)
=\frac1\pi\int_0^{2\pi}d\theta\,\sin^2(\theta/2)f(\theta)
$$

for class functions $f$.

This formula makes the orthogonality of $SU(2)$ characters concrete:

$$
\frac1\pi\int_0^{2\pi}d\theta\,
\sin^2(\theta/2)\chi_j(\theta)^*\chi_k(\theta)
=\delta_{jk}.
$$

## Weyl character formula

Let $\Lambda$ be a dominant integral highest weight. Let

$$
\rho=\frac12\sum_{\alpha>0}\alpha
$$

be the Weyl vector. Equivalently,

$$
\rho=\sum_{i=1}^r\omega_i
$$

for a semisimple Lie algebra, where $\omega_i$ are the fundamental weights.

The Weyl character formula says

$$
\chi_\Lambda
=\frac{\sum_{w\in W}\epsilon(w)e^{w(\Lambda+\rho)}}
{\sum_{w\in W}\epsilon(w)e^{w(\rho)}}.
$$

Here $e^\lambda$ denotes the formal exponential associated with a weight, and $\epsilon(w)=\det(w)=\pm1$ is the sign of the Weyl-group element.

The denominator is the Weyl denominator:

$$
\sum_{w\in W}\epsilon(w)e^{w(\rho)}
=e^\rho\prod_{\alpha>0}(1-e^{-\alpha}).
$$

The Weyl character formula is not usually the fastest way to do everyday low-rank decompositions by hand, but it is conceptually central. It packages the highest-weight representation into a Weyl-antisymmetrized numerator divided by a universal denominator.

### SU(2) from Weyl

For $SU(2)$, the Weyl group has two elements: identity and reflection. Let the highest weight be

$$
\Lambda=n\omega,
$$

with

$$
\rho=\omega.
$$

Then

$$
\chi_n
=\frac{e^{(n+1)\omega}-e^{-(n+1)\omega}}
{e^{\omega}-e^{-\omega}}.
$$

Setting $e^\omega=e^{i\theta/2}$ gives

$$
\chi_n(\theta)
=\frac{\sin((n+1)\theta/2)}{\sin(\theta/2)}.
$$

Since $n=2j$, this is the spin-$j$ character formula above.

## Dimensions from characters

The dimension of a representation is the value of its character at the identity:

$$
\dim R=\chi_R(e).
$$

Using the Weyl character formula and carefully taking the identity limit gives the Weyl dimension formula:

$$
\dim V_\Lambda
=\prod_{\alpha>0}
\frac{(\Lambda+\rho,\alpha)}{(\rho,\alpha)}.
$$

Equivalently, using coroots,

$$
\dim V_\Lambda
=\prod_{\alpha>0}
\frac{\langle\alpha^\vee,\Lambda+\rho\rangle}{\langle\alpha^\vee,\rho\rangle}.
$$

For $SU(2)$ with $\Lambda=n\omega$, this gives

$$
\dim V_{n\omega}=n+1.
$$

For $SU(3)$ with Dynkin labels $[p,q]$, the dimension formula becomes

$$
\dim[p,q]=\frac12(p+1)(q+1)(p+q+2).
$$

Checks:

$$
\dim[1,0]=3,
\qquad
\dim[0,1]=3,
\qquad
\dim[1,1]=8.
$$

These are the fundamental, antifundamental, and adjoint representations of $SU(3)$.

## The SU(3) examples

Let

$$
t=\operatorname{diag}(z_1,z_2,z_3)\in SU(3),
\qquad
z_1z_2z_3=1.
$$

The fundamental character is

$$
\chi_{\mathbf 3}(t)=z_1+z_2+z_3.
$$

The antifundamental character is

$$
\chi_{\overline{\mathbf 3}}(t)
=z_1^{-1}+z_2^{-1}+z_3^{-1}.
$$

The product is

$$
\chi_{\mathbf 3}\chi_{\overline{\mathbf 3}}
=\sum_{i,j}z_i z_j^{-1}.
$$

This includes the three diagonal terms $z_i z_i^{-1}=1$. One linear combination is the singlet, and the remaining traceless part is the adjoint. Therefore

$$
\mathbf 3\otimes\overline{\mathbf 3}
=\mathbf 1\oplus\mathbf 8,
$$

or in characters,

$$
\chi_{\mathbf 8}
=\chi_{\mathbf 3}\chi_{\overline{\mathbf 3}}-1.
$$

Similarly,

$$
\mathbf 3\otimes\mathbf 3
=\mathbf 6\oplus\overline{\mathbf 3}.
$$

The character statement is

$$
(z_1+z_2+z_3)^2
=\chi_{\mathbf 6}+\chi_{\overline{\mathbf 3}}.
$$

Here $\mathbf 6$ is the symmetric two-index representation, while $\overline{\mathbf 3}$ is the antisymmetric two-index representation:

$$
\wedge^2\mathbf 3\cong\overline{\mathbf 3}.
$$

Characters make this decomposition visible without choosing explicit Clebsch–Gordan coefficients.

## Real, complex, and pseudoreal representations

Characters can detect conjugation properties.

The character of the conjugate representation is

$$
\chi_{R^*}(g)=\chi_R(g)^*.
$$

A representation is complex if $R\not\cong R^*$. Then its character is not generally real. For $SU(3)$,

$$
\mathbf 3\not\cong\overline{\mathbf 3}.
$$

A representation is real or pseudoreal if $R\cong R^*$. In both cases the character is real-valued, but the invariant bilinear form differs: symmetric for real representations and antisymmetric for pseudoreal representations.

For $SU(2)$, the spin-$j$ representations are self-conjugate. Integer-spin representations are real, while half-integer-spin representations are pseudoreal. Characters alone see self-conjugacy, but they do not by themselves distinguish symmetric from antisymmetric invariant bilinear forms. For that, one uses the Frobenius–Schur indicator or direct invariant tensor analysis.

In QFT this distinction matters for Majorana conditions, reality constraints, global anomalies, and whether a mass term can be written using a symmetric or antisymmetric invariant pairing.

## Characters and Hilbert-space traces

In quantum theory, characters are closely related to symmetry-twined traces. If a Hilbert space decomposes into representations of $G$, then

$$
Z(g)=\operatorname{Tr}_{\mathcal H}\left(g e^{-\beta H}\right)
$$

is a character-valued partition function, assuming $H$ commutes with $G$.

If

$$
\mathcal H=\bigoplus_R \mathcal M_R\otimes V_R,
$$

where $\mathcal M_R$ is the multiplicity space, then

$$
Z(g)=\sum_R Z_R\chi_R(g),
$$

with

$$
Z_R=\operatorname{Tr}_{\mathcal M_R}(e^{-\beta H}).
$$

Turning on chemical potentials for Cartan charges is exactly the torus version of this idea:

$$
Z(\theta)=\operatorname{Tr}_{\mathcal H}\left(e^{i\theta^i Q_i}e^{-\beta H}\right).
$$

Expanding $Z(\theta)$ in characters organizes the Hilbert space into irreducible multiplets. This is the finite-dimensional ancestor of many index and partition-function technologies used in modern QFT.

## Gauge singlet projection

In gauge theory, physical states or gauge-invariant local operators must be singlets under the gauge group, modulo gauge-fixing and constraint subtleties. Character integrals implement the finite-dimensional part of that projection.

Suppose fields transform in a representation $R$, and we want to count singlets in a tensor construction whose character is $\chi_V(g)$. The singlet count is

$$
\dim V^G=\int_G dg\,\chi_V(g).
$$

For symmetric products, one often packages the counting using generating functions. The character of symmetric powers is encoded by

$$
\sum_{n=0}^{\infty} t^n\chi_{\operatorname{Sym}^n R}(g)
=\exp\left(\sum_{k=1}^{\infty}\frac{t^k}{k}\chi_R(g^k)\right).
$$

The character of exterior powers is encoded by

$$
\sum_{n=0}^{\infty} t^n\chi_{\wedge^n R}(g)
=\exp\left(\sum_{k=1}^{\infty}\frac{(-1)^{k+1}t^k}{k}\chi_R(g^k)\right).
$$

These plethystic formulas are widely used in operator counting. They count representation-theoretic structures before subtracting derivative relations, equations of motion, gauge identities, or other physical equivalences.

## Common pitfalls

**A character is not just a dimension.** The dimension is the character at the identity, $\chi_R(e)$. The full character remembers the weights and can distinguish many representations with the same dimension.

**Characters are class functions, not arbitrary functions on the group.** They are constant on conjugacy classes. For connected compact groups, they can be studied on the maximal torus, but only after imposing Weyl invariance.

**Multiplying dimensions is not decomposing tensor products.** Dimensions satisfy

$$
\dim(R\otimes S)=\dim R\,\dim S,
$$

but the decomposition into irreducibles requires character multiplication or another representation-theoretic method.

**The Weyl integration measure is not flat in eigenvalues.** Diagonalizing a group element introduces $|\Delta|^2$. Forgetting this factor breaks character orthogonality.

**A real-valued character does not automatically mean a representation is real rather than pseudoreal.** Real and pseudoreal representations are both self-conjugate. The difference lies in the symmetry of the invariant bilinear form.

**Lie-algebra characters and group characters are not always the same global object.** A formal weight sum may describe a Lie-algebra representation that does not integrate to the chosen global form of the group.

**Infinite-dimensional traces require care.** Finite-dimensional compact-group characters are perfectly well-defined. Hilbert-space traces in QFT need regulators, convergence conditions, grading, or index protection.

## Relations to other pages

Characters turn the weights from [Roots, Weights, and Dynkin Diagrams](/math-toolkit/groups-representations/roots-weights-and-dynkin-diagrams/) into functions that can be multiplied and integrated.

The $SU(2)$ examples rely on [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/). Character multiplication gives a compact derivation of Clebsch–Gordan decompositions.

The Haar measure and compactness assumptions come from [Compact Lie Groups](/math-toolkit/groups-representations/compact-lie-groups/). Without compactness, finite-dimensional character orthogonality generally does not hold in this simple form.

The next computational layer is Young tableaux and gauge-group data. Those pages will use characters as one route to tensor-product decompositions, dimensions, indices, and invariant tensors.

## Research status

The finite-dimensional character theory of compact Lie groups is established. The Weyl character formula, Weyl integration formula, Peter–Weyl theorem, and character orthogonality are standard.

In QFT, character-like objects remain active because the basic idea generalizes. Supersymmetric indices are graded characters protected under deformations. Conformal characters organize descendant towers. Affine and Virasoro characters transform under modular transformations. Equivariant characters appear in localization. Defect and categorical settings lead to newer notions of trace and character beyond ordinary compact groups.

## Exercises

### Exercise 1

Use $SU(2)$ characters to show

$$
\frac12\otimes1=\frac32\oplus\frac12.
$$

<details><summary><strong>Solution</strong></summary>

The characters are

$$
\chi_{1/2}=e^{i\theta/2}+e^{-i\theta/2},
$$

and

$$
\chi_1=e^{i\theta}+1+e^{-i\theta}.
$$

Their product is

$$
\chi_{1/2}\chi_1
=e^{3i\theta/2}+2e^{i\theta/2}+2e^{-i\theta/2}+e^{-3i\theta/2}.
$$

The spin-$3/2$ character is

$$
\chi_{3/2}
=e^{3i\theta/2}+e^{i\theta/2}+e^{-i\theta/2}+e^{-3i\theta/2}.
$$

Subtracting gives

$$
\chi_{1/2}\chi_1-\chi_{3/2}
=e^{i\theta/2}+e^{-i\theta/2}
=\chi_{1/2}.
$$

Therefore

$$
\chi_{1/2}\chi_1=\chi_{3/2}+\chi_{1/2},
$$

so

$$
\frac12\otimes1=\frac32\oplus\frac12.
$$

</details>

### Exercise 2

Show that the number of singlets in $R\otimes R^*$ is $1$ when $R$ is irreducible.

<details><summary><strong>Solution</strong></summary>

The character of $R\otimes R^*$ is

$$
\chi_R(g)\chi_{R^*}(g).
$$

Since

$$
\chi_{R^*}(g)=\chi_R(g)^*,
$$

we get

$$
\chi_{R\otimes R^*}(g)=|\chi_R(g)|^2.
$$

The number of singlets is

$$
\int_G dg\,|\chi_R(g)|^2.
$$

By character orthogonality for irreducible $R$,

$$
\int_G dg\,\chi_R(g)^*\chi_R(g)=1.
$$

Therefore $R\otimes R^*$ contains one singlet.

</details>

### Exercise 3

For $SU(3)$, use characters to explain why

$$
\mathbf 3\otimes\overline{\mathbf 3}=\mathbf 1\oplus\mathbf 8.
$$

<details><summary><strong>Solution</strong></summary>

Let

$$
t=\operatorname{diag}(z_1,z_2,z_3),
\qquad
z_1z_2z_3=1.
$$

Then

$$
\chi_{\mathbf 3}=z_1+z_2+z_3,
$$

and

$$
\chi_{\overline{\mathbf 3}}=z_1^{-1}+z_2^{-1}+z_3^{-1}.
$$

The product is

$$
\chi_{\mathbf 3}\chi_{\overline{\mathbf 3}}
=\sum_{i,j}z_i z_j^{-1}.
$$

This is the character of the space of all linear maps $\mathbb C^3\to\mathbb C^3$, i.e. $3\times3$ matrices. It decomposes into trace and traceless parts:

$$
\operatorname{End}(\mathbb C^3)
=\mathbb C\mathbf 1\oplus \mathfrak{sl}_3.
$$

The trace part is the singlet $\mathbf 1$, and the traceless part is the adjoint $\mathbf 8$. Hence

$$
\mathbf 3\otimes\overline{\mathbf 3}=\mathbf 1\oplus\mathbf 8.
$$

</details>

### Exercise 4

Use the Weyl integration formula for $SU(2)$ to check that the trivial and spin-$1$ characters are orthogonal.

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
\chi_0(\theta)=1,
\qquad
\chi_1(\theta)=1+2\cos\theta.
$$

The Weyl integration formula gives

$$
\langle\chi_0,\chi_1\rangle
=\frac1\pi\int_0^{2\pi}d\theta\,
\sin^2(\theta/2)(1+2\cos\theta).
$$

Use

$$
\sin^2(\theta/2)=\frac{1-\cos\theta}{2}.
$$

Then the integrand is

$$
\frac{1-\cos\theta}{2}(1+2\cos\theta)
=\frac12+\frac12\cos\theta-\cos^2\theta.
$$

Integrating from $0$ to $2\pi$ gives

$$
\frac12(2\pi)+0-\pi=0.
$$

Thus

$$
\langle\chi_0,\chi_1\rangle=0.
$$

</details>

### Exercise 5

Use the Weyl dimension formula to compute the dimension of the $SU(3)$ representation with Dynkin labels $[2,0]$.

<details><summary><strong>Solution</strong></summary>

For $SU(3)$, the dimension of the representation $[p,q]$ is

$$
\dim[p,q]=\frac12(p+1)(q+1)(p+q+2).
$$

For $[2,0]$, this gives

$$
\dim[2,0]
=\frac12(3)(1)(4)=6.
$$

So $[2,0]$ is the six-dimensional symmetric square of the fundamental:

$$
\operatorname{Sym}^2\mathbf 3=\mathbf 6.
$$

</details>

## References

- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for compact groups, maximal tori, Weyl integration, and character theory.
- H. Georgi, *Lie Algebras in Particle Physics*, for characters, weights, tensor products, and physics applications.
- W. Fulton and J. Harris, *Representation Theory*, for highest-weight representations, Weyl character formula, and classical group examples.
- A. W. Knapp, *Lie Groups Beyond an Introduction*, for Weyl character theory and compact group representation theory.
- J. E. Humphreys, *Introduction to Lie Algebras and Representation Theory*, for root systems, weights, and character-related representation theory.
- W.-K. Tung, *Group Theory in Physics*, and J. F. Cornwell, *Group Theory in Physics*, for character tables and physical representation theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for symmetry representations, group averages, gauge theory, and particle-physics uses of group theory.
- M. Srednicki, *Quantum Field Theory*, for non-Abelian symmetries, group representations, and gauge-theory group factors.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for practical Standard Model group theory and representation decompositions.
- S. Coleman, *Aspects of Symmetry*, for compact symmetry, current algebra, and representation-theoretic physics.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
