---
title: "Pfaffians"
description: "A QFT-oriented introduction to Pfaffians, antisymmetric quadratic forms, real Grassmann Gaussian integrals, Majorana fermions, zero modes, and Pfaffian signs."
sidebar:
  label: "Pfaffians"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki, fermionic path integrals and functional determinants; Coleman, functional integration and instanton lectures; Zee, Grassmann integrals; Nakahara, Grassmann calculus; Zinn-Justin, functional methods."
topics:
  - Pfaffians
  - antisymmetric matrices
  - Majorana fermions
  - fermionic Gaussian integrals
  - zero modes
canonicalTopics:
  - pfaffians
  - majorana-gaussians
  - antisymmetric-bilinear-forms
  - fermionic-determinants
researchStatus:
  established:
    - "Finite-dimensional Pfaffians and their Grassmann Gaussian integral representation are exact algebraic identities."
  active:
    - "In continuum QFT, Pfaffian signs and phases can encode global anomalies, spectral flow, eta invariants, and sign problems; the correct treatment depends on regulator, reality structure, and spacetime dimension."
---

## Summary

A Pfaffian is the determinant-like invariant of an antisymmetric matrix. If $A$ is a $2n\times 2n$ antisymmetric matrix,

$$
A^T=-A,
$$

then its Pfaffian, written $\operatorname{Pf}(A)$, satisfies

$$
\operatorname{Pf}(A)^2=\det A.
$$

This equation is useful but slightly dangerous. The Pfaffian is not “the positive square root” of the determinant. It carries orientation and sign data. That sign data is exactly why Pfaffians are unavoidable for real fermions, Majorana fields, fermion zero modes, and global anomaly questions.

The finite-dimensional Grassmann Gaussian identity is

$$
\int d\chi_{2n}\cdots d\chi_1\,
\exp\left(\frac12\chi_i A_{ij}\chi_j\right)
=\operatorname{Pf}(A),
$$

with the convention

$$
\int d\chi_{2n}\cdots d\chi_1\,\chi_1\chi_2\cdots\chi_{2n}=1.
$$

So the dictionary is:

$$
\text{complex fermion Gaussian}\Rightarrow \det A,
\qquad
\text{real fermion Gaussian}\Rightarrow \operatorname{Pf}(A).
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![The Pfaffian of a four-by-four antisymmetric matrix as a signed sum over pairings.](/figures/math-toolkit/pfaffian-pairings.svg)

<figcaption>

For four real Grassmann variables, the Pfaffian is the signed sum over perfect pairings: $\operatorname{Pf}(A)=A_{12}A_{34}-A_{13}A_{24}+A_{14}A_{23}$. The signs are not decoration; they are the orientation signs of the top Grassmann monomial.

</figcaption>
</figure>

The slogan is:

$$
\operatorname{Pfaffian}
=\text{fermionic Gaussian pairing with no independent conjugate variables}.
$$

## Prerequisites

You should know [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/) and [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/). We use their conventions for Grassmann generators, ordered measures, coefficient extraction, and fermionic signs.

It is also helpful to know the determinant and Gaussian identities in [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/). The next page, [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), explains what happens when these finite-dimensional determinants and Pfaffians become regulated spectral objects.

## Core idea

For complex Grassmann variables, the quadratic form is usually written with independent variables $\psi_i$ and $\bar\psi_i$:

$$
\bar\psi_i A_{ij}\psi_j.
$$

Berezin integration over all $\bar\psi_i$ and $\psi_i$ gives $\det A$. This is the algebra behind the Dirac fermion path integral.

For real Grassmann variables, there is no independent $\bar\psi$. A quadratic expression must instead have the form

$$
\frac12\chi_i A_{ij}\chi_j.
$$

Only the antisymmetric part of $A$ contributes, because

$$
\chi_i A_{ij}\chi_j
=\frac12\chi_i(A_{ij}-A_{ji})\chi_j.
$$

The symmetric part vanishes after anticommuting the Grassmann variables. Thus the natural quadratic data for real fermions is an antisymmetric bilinear form, and the natural Gaussian answer is a Pfaffian.

For two variables,

$$
A=\begin{pmatrix}0&a\\-a&0\end{pmatrix},
$$

so

$$
\frac12\chi_iA_{ij}\chi_j=a\chi_1\chi_2.
$$

The integral is

$$
\int d\chi_2d\chi_1\,e^{a\chi_1\chi_2}
=\int d\chi_2d\chi_1\,(1+a\chi_1\chi_2)
=a.
$$

Therefore

$$
\operatorname{Pf}\begin{pmatrix}0&a\\-a&0\end{pmatrix}=a.
$$

This example contains the whole idea: the Pfaffian is the coefficient of the top Grassmann monomial produced by the exponential of an antisymmetric quadratic form.

## Setup and conventions

Let $A$ be a $2n\times 2n$ antisymmetric matrix over $\mathbb C$ or $\mathbb R$. Its Pfaffian is

$$
\operatorname{Pf}(A)
=\frac{1}{2^n n!}
\sum_{\sigma\in S_{2n}}
\operatorname{sgn}(\sigma)
A_{\sigma(1)\sigma(2)}
A_{\sigma(3)\sigma(4)}
\cdots
A_{\sigma(2n-1)\sigma(2n)}.
$$

Equivalently, $\operatorname{Pf}(A)$ is the signed sum over perfect pairings of the set $\{1,2,\ldots,2n\}$. If a pairing is written as

$$
(i_1,j_1)(i_2,j_2)\cdots(i_n,j_n),
\qquad i_k<j_k,
\qquad i_1<i_2<\cdots<i_n,
$$

then its sign is the sign of the permutation

$$
(1,2,\ldots,2n)\mapsto(i_1,j_1,i_2,j_2,\ldots,i_n,j_n).
$$

For four variables,

$$
\operatorname{Pf}(A)
=A_{12}A_{34}-A_{13}A_{24}+A_{14}A_{23}.
$$

The corresponding determinant is

$$
\det A
=\left(A_{12}A_{34}-A_{13}A_{24}+A_{14}A_{23}\right)^2.
$$

Odd-dimensional antisymmetric matrices always have zero determinant. A nonzero Pfaffian exists only for even-dimensional antisymmetric matrices.

Throughout this page, the real Grassmann measure is ordered as

$$
d^{2n}\chi=d\chi_{2n}\cdots d\chi_1,
$$

with

$$
\int d^{2n}\chi\,\chi_1\cdots\chi_{2n}=1.
$$

With this convention,

$$
\int d^{2n}\chi\,
\exp\left(\frac12\chi^T A\chi\right)
=\operatorname{Pf}(A).
$$

If an action is written as $S=\frac12\chi^T B\chi$ and the path-integral weight is $e^{-S}$, then this formula is applied with $A=-B$. Different books often hide this sign by choosing a different exponent convention. Do not compare Pfaffian signs across conventions without checking the order of the measure and the sign in the exponent. Tiny signs here are tiny mousetraps.

## The square-root identity

The identity

$$
\operatorname{Pf}(A)^2=\det A
$$

is easiest to understand from canonical form. A complex antisymmetric matrix can be brought by a change of basis to a block form built from $2\times2$ antisymmetric blocks. In the real case, a real antisymmetric matrix can be brought by an orthogonal transformation to

$$
Q^T A Q=\operatorname{diag}\bigl(J(\lambda_1),J(\lambda_2),\ldots,J(\lambda_n)\bigr),
\qquad
J(\lambda)=\begin{pmatrix}0&\lambda\\-\lambda&0\end{pmatrix}.
$$

For this block-diagonal matrix,

$$
\operatorname{Pf}(Q^T A Q)=\lambda_1\lambda_2\cdots\lambda_n,
$$

while

$$
\det(Q^T A Q)=\lambda_1^2\lambda_2^2\cdots\lambda_n^2.
$$

Thus the square of the Pfaffian is the determinant.

But the Pfaffian changes under an ordinary change of basis in a way that remembers orientation. If $S$ is invertible, then

$$
\operatorname{Pf}(S^T A S)=\det(S)\operatorname{Pf}(A).
$$

The determinant of $S$ is why the Pfaffian has sign information. An orientation-reversing change of basis flips the sign of the Pfaffian even though the determinant of $A$ is unchanged.

This is the conceptual point behind many physical appearances of Pfaffian signs: the determinant sees eigenvalues squared, while the Pfaffian sees an oriented square root.

## Exterior-form interpretation

There is a compact geometric way to define the same object. Let $e^1,\ldots,e^{2n}$ be a basis of a $2n$-dimensional vector space, and define the two-form

$$
\omega=\frac12 A_{ij}e^i\wedge e^j.
$$

Then

$$
\frac{1}{n!}\omega^n
=\operatorname{Pf}(A)\,e^1\wedge e^2\wedge\cdots\wedge e^{2n}.
$$

This formula makes the orientation dependence obvious. The Pfaffian is the coefficient of the top exterior form. Berezin integration is doing the same operation in the Grassmann algebra:

$$
\int d\chi_{2n}\cdots d\chi_1\,
\exp\left(\frac12\chi_iA_{ij}\chi_j\right)
$$

extracts the coefficient of $\chi_1\cdots\chi_{2n}$, just as the exterior-form formula extracts the coefficient of $e^1\wedge\cdots\wedge e^{2n}$.

This is a good way to remember why Pfaffians appear in symplectic geometry, fermionic integration, and orientation-line problems: all three involve top exterior powers of antisymmetric forms.

## Relation to ordinary determinants

Complex fermions can be rewritten as real fermions by doubling variables. This gives a bridge between determinants and Pfaffians.

Let $A$ be an $n\times n$ matrix and form the $2n\times2n$ antisymmetric matrix

$$
\mathcal A=
\begin{pmatrix}
0&A\\
-A^T&0
\end{pmatrix}.
$$

Then

$$
\operatorname{Pf}(\mathcal A)
=(-1)^{n(n-1)/2}\det A.
$$

The sign depends on the ordering of the doubled variables. If instead the variables are ordered as pairs, for example $(\psi_1,\bar\psi_1,\psi_2,\bar\psi_2,\ldots)$, the same determinant may appear with a different overall convention sign.

This is not a contradiction. A Pfaffian is attached not only to an antisymmetric form but also to an orientation of the underlying variable space. A determinant formula for complex fermions secretly chooses a complex orientation.

In QFT language:

- a Dirac fermion path integral gives a determinant of a Dirac operator;
- a Majorana fermion path integral gives a Pfaffian of an antisymmetric operator built from the Dirac operator and charge conjugation;
- two equivalent-looking formulas can differ by a sign convention if they use different orderings of real Grassmann variables.

## Source formula and Wick pairings

Let $A$ be invertible and antisymmetric. Introduce odd sources $\eta_i$ and use the source convention $\eta^T\chi=\eta_i\chi_i$. Then

$$
Z_A[\eta]
=\int d^{2n}\chi\,
\exp\left(\frac12\chi^T A\chi+\eta^T\chi\right)
=\operatorname{Pf}(A)
\exp\left(\frac12\eta^T A^{-1}\eta\right).
$$

This is the Pfaffian version of the Gaussian generating functional. It says that every even moment is a signed sum over pairings. With the source and measure convention above,

$$
\langle \chi_i\chi_j\rangle
=-(A^{-1})_{ij}.
$$

For four variables,

$$
\langle \chi_i\chi_j\chi_k\chi_l\rangle
=\langle \chi_i\chi_j\rangle\langle \chi_k\chi_l\rangle
-\langle \chi_i\chi_k\rangle\langle \chi_j\chi_l\rangle
+\langle \chi_i\chi_l\rangle\langle \chi_j\chi_k\rangle.
$$

This has exactly the same pairing pattern as the four-by-four Pfaffian. Indeed, for any even number of variables,

$$
\langle \chi_{i_1}\chi_{i_2}\cdots\chi_{i_{2r}}\rangle
=
\operatorname{Pf}\left(\langle \chi_{i_a}\chi_{i_b}\rangle\right)_{1\le a,b\le 2r}.
$$

Odd moments vanish unless zero modes and insertions change the saturation rule.

## Majorana fermions

A Majorana field is the field-theoretic version of a real fermionic variable. The precise meaning depends on spacetime signature and dimension, but the path-integral algebra follows the same finite-dimensional pattern.

A typical quadratic Majorana action has the schematic form

$$
S_E=\frac12\int d^d x\,\psi^T B\psi,
$$

where $B$ is antisymmetric after including spinor, spacetime, and internal indices. Often $B$ is built from a charge-conjugation matrix and a Dirac operator, schematically

$$
B=C\mathcal D.
$$

The corresponding formal path integral is

$$
\int D\psi\,e^{-S_E}\sim \operatorname{Pf}(-B).
$$

Since

$$
\operatorname{Pf}(B)^2=\det B,
$$

one often says that a Majorana fermion contributes “half a Dirac determinant.” This is a useful mnemonic for magnitudes and local perturbation theory, but it can erase sign and phase information. The Pfaffian is not merely a square root. It is a choice of square root that can vary over background fields.

This matters in several places:

- **Majorana mass terms.** Real fermions naturally produce antisymmetric quadratic forms.
- **Instantons and zero modes.** Fermion zero modes make the Pfaffian vanish unless insertions saturate them.
- **Global anomalies.** A determinant may be positive after squaring, while the Pfaffian can change sign around a loop in field space.
- **Lattice simulations.** A fluctuating Pfaffian sign or phase can become a sign problem.

The finite-dimensional Pfaffian is therefore not optional decoration. It is the local algebraic shadow of a global geometric object: the fermion determinant line, or more precisely for real fermions, a Pfaffian line.

## Zero modes and saturation

If $A$ has a zero vector, then $\det A=0$, hence

$$
\operatorname{Pf}(A)=0.
$$

In the Grassmann integral this has a direct explanation. Suppose $\chi_0$ is a zero-mode variable that does not appear in the quadratic form. Then the exponential cannot supply a factor of $\chi_0$. Since Berezin integration extracts the top coefficient, the integral vanishes unless an insertion supplies the missing variable.

For example,

$$
\int d\chi_2d\chi_1\,1=0,
\qquad
\int d\chi_2d\chi_1\,\chi_1\chi_2=1.
$$

A zero mode must be saturated.

In QFT this becomes a selection rule. Fermion zero modes in an instanton background, for example, imply that correlation functions without enough fermionic insertions vanish. Correlation functions with the right insertions can be nonzero and carry the information that would otherwise have been hidden inside a zero determinant.

For bosonic zero modes, the Gaussian integral diverges and one introduces collective coordinates. For fermionic zero modes, the Gaussian integral vanishes and one needs Grassmann insertions. This contrast is one of the cleanest ways to remember the difference between commuting and anticommuting integration.

## Pfaffian signs and spectral flow

For a real finite-dimensional antisymmetric matrix, the nonzero eigenvalues are imaginary pairs,

$$
\pm i\lambda_k,
\qquad \lambda_k\in\mathbb R.
$$

The determinant only knows $\lambda_k^2$. The Pfaffian knows the oriented product $\lambda_1\cdots\lambda_n$, up to the orientation convention. When a parameter is varied continuously, the Pfaffian can change sign only by passing through zero. In spectral language, this happens when an eigenvalue pair crosses zero.

This gives a useful mental model for global signs in QFT. As background gauge fields or metrics vary, the fermion operator varies. If the family of operators has spectral flow through zero, a Pfaffian can return with the opposite sign after a closed loop in background-field space. Such sign changes are the finite-dimensional prototype of global anomalies.

The determinant squared may look harmless because it returns to the same positive value. The Pfaffian remembers the trip.

## Common pitfalls

**“The Pfaffian is just the square root of the determinant.”** It is an oriented square root. The sign or phase is part of the data, and it can be physically meaningful.

**“Any quadratic fermion form gives a Pfaffian.”** A quadratic form in a single set of Grassmann variables only sees its antisymmetric part. If you have independent $\bar\psi$ and $\psi$ variables, the natural answer is a determinant; if you have one real set of variables, the natural answer is a Pfaffian.

**“The sign of the Pfaffian is absolute.”** The sign depends on the orientation of the Grassmann measure. What is physical is whether a consistent sign choice exists globally over the relevant parameter space, and how signs compare between configurations.

**“Zero modes are small corrections.”** They are not corrections to the determinant. They make the Pfaffian vanish. One must separate zero modes and saturate the corresponding Grassmann variables with insertions.

**“A Majorana determinant is always the square root of a Dirac determinant.”** Perturbatively and locally this may be a good mnemonic. Globally, the Pfaffian line can be nontrivial, and sign or phase data can matter.

**“The finite-dimensional formula automatically defines the continuum path integral.”** It defines the regulated algebra. In continuum QFT, the operator, domain, regulator, boundary conditions, and reality structure must still be specified.

## Relations to other pages

This page sits between [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/) and [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/). Berezin integration explains why Grassmann Gaussian integrals produce determinant-like objects. This page explains the real-fermion case. Functional determinants explain how these objects become regulated products over infinitely many modes.

The finite-dimensional algebra also connects backward to [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/), because the Pfaffian is a top exterior coefficient. It connects forward to heat kernels, zeta regularization, stationary phase, and anomalies, where Pfaffian phases and signs become part of the one-loop answer.

In physics pages, Pfaffians appear in Majorana fermion path integrals, instanton zero-mode counting, Faddeev–Popov-like fermionic determinants, supersymmetric localization, lattice fermions, and global anomalies.

## Research status

The finite-dimensional theory is complete: Pfaffians, their transformation laws, and their Grassmann Gaussian integral representation are exact algebraic facts.

The continuum use of Pfaffians is subtler. Perturbative local calculations often only require $\operatorname{Pf}(B)^2=\det B$. Nonperturbative questions can depend on the Pfaffian sign or phase, the topology of determinant/Pfaffian lines, spectral flow, eta invariants, boundary conditions, and regulator choices. These are not fringe issues. They are central in global anomaly theory, Majorana lattice fermions, topological superconductors, and supersymmetric path integrals.

## Exercises

### Exercise 1: Two-variable Pfaffian

Let

$$
A=\begin{pmatrix}0&a\\-a&0\end{pmatrix}.
$$

Compute $\operatorname{Pf}(A)$ from the Grassmann integral

$$
\int d\chi_2d\chi_1\,
\exp\left(\frac12\chi_iA_{ij}\chi_j\right).
$$

<details><summary><strong>Solution</strong></summary>

The quadratic form is

$$
\frac12\chi_iA_{ij}\chi_j
=\frac12(a\chi_1\chi_2-a\chi_2\chi_1)
=a\chi_1\chi_2.
$$

Since $(\chi_1\chi_2)^2=0$,

$$
e^{a\chi_1\chi_2}=1+a\chi_1\chi_2.
$$

Therefore

$$
\int d\chi_2d\chi_1\,e^{a\chi_1\chi_2}
=a.
$$

So

$$
\operatorname{Pf}(A)=a.
$$

</details>

### Exercise 2: The four-variable formula

Let $A$ be a $4\times4$ antisymmetric matrix. Show that

$$
\operatorname{Pf}(A)=A_{12}A_{34}-A_{13}A_{24}+A_{14}A_{23}.
$$

<details><summary><strong>Solution</strong></summary>

Only terms in

$$
\exp\left(\frac12\chi_iA_{ij}\chi_j\right)
$$

that contain all four variables survive the Berezin integral. Since

$$
\frac12\chi_iA_{ij}\chi_j
=\sum_{i<j}A_{ij}\chi_i\chi_j,
$$

the top-degree terms come from pairings of $\{1,2,3,4\}$:

$$
(A_{12}\chi_1\chi_2)(A_{34}\chi_3\chi_4),
$$

$$
(A_{13}\chi_1\chi_3)(A_{24}\chi_2\chi_4),
$$

and

$$
(A_{14}\chi_1\chi_4)(A_{23}\chi_2\chi_3).
$$

The second monomial is

$$
\chi_1\chi_3\chi_2\chi_4=-\chi_1\chi_2\chi_3\chi_4,
$$

and the third is

$$
\chi_1\chi_4\chi_2\chi_3=+\chi_1\chi_2\chi_3\chi_4.
$$

Thus the coefficient of $\chi_1\chi_2\chi_3\chi_4$ is

$$
A_{12}A_{34}-A_{13}A_{24}+A_{14}A_{23},
$$

which is the Pfaffian.

</details>

### Exercise 3: Change of variables

Use the Grassmann Gaussian integral to show that

$$
\operatorname{Pf}(S^TAS)=\det(S)\operatorname{Pf}(A)
$$

for an invertible ordinary matrix $S$.

<details><summary><strong>Solution</strong></summary>

Make the Grassmann change of variables

$$
\chi=S\chi'.
$$

The quadratic form becomes

$$
\chi^T A\chi=\chi'^T S^TAS\chi'.
$$

The Berezin measure transforms inversely to an ordinary bosonic measure:

$$
d^{2n}\chi=\det(S)^{-1}d^{2n}\chi'.
$$

Therefore

$$
\operatorname{Pf}(A)
=\int d^{2n}\chi\,e^{\frac12\chi^TA\chi}
=\det(S)^{-1}\int d^{2n}\chi'\,e^{\frac12\chi'^T S^TAS\chi'}.
$$

The last integral is $\operatorname{Pf}(S^TAS)$, so

$$
\operatorname{Pf}(A)=\det(S)^{-1}\operatorname{Pf}(S^TAS).
$$

Equivalently,

$$
\operatorname{Pf}(S^TAS)=\det(S)\operatorname{Pf}(A).
$$

</details>

### Exercise 4: Determinant as a Pfaffian

Let $A$ be an $n\times n$ matrix and define

$$
\mathcal A=
\begin{pmatrix}
0&A\\
-A^T&0
\end{pmatrix}.
$$

Check the formula

$$
\operatorname{Pf}(\mathcal A)=(-1)^{n(n-1)/2}\det A
$$

for $n=1$ and $n=2$.

<details><summary><strong>Solution</strong></summary>

For $n=1$,

$$
\mathcal A=\begin{pmatrix}0&a\\-a&0\end{pmatrix},
$$

so

$$
\operatorname{Pf}(\mathcal A)=a=\det A.
$$

The sign factor is $(-1)^0=1$.

For $n=2$, write

$$
A=\begin{pmatrix}a&b\\c&d\end{pmatrix}.
$$

Then

$$
\mathcal A=\begin{pmatrix}
0&0&a&b\\
0&0&c&d\\
-a&-c&0&0\\
-b&-d&0&0
\end{pmatrix}.
$$

Using the four-variable formula,

$$
\operatorname{Pf}(\mathcal A)
=\mathcal A_{12}\mathcal A_{34}-\mathcal A_{13}\mathcal A_{24}+\mathcal A_{14}\mathcal A_{23}
=0-ad+bc.
$$

Thus

$$
\operatorname{Pf}(\mathcal A)=-(ad-bc)=-\det A.
$$

The sign factor is $(-1)^1=-1$, as required.

</details>

### Exercise 5: Zero-mode saturation

Let $\chi_1,\chi_2,\chi_3,\chi_4$ be Grassmann variables and take

$$
A_{12}=a,
\qquad
A_{21}=-a,
$$

with all other entries involving $\chi_3$ and $\chi_4$ equal to zero. Compute

$$
\int d\chi_4d\chi_3d\chi_2d\chi_1\,
\exp(a\chi_1\chi_2)
$$

and

$$
\int d\chi_4d\chi_3d\chi_2d\chi_1\,
\chi_3\chi_4\exp(a\chi_1\chi_2).
$$

<details><summary><strong>Solution</strong></summary>

The exponential is

$$
e^{a\chi_1\chi_2}=1+a\chi_1\chi_2.
$$

The first integral has no term containing the top monomial $\chi_1\chi_2\chi_3\chi_4$, so it vanishes:

$$
\int d\chi_4d\chi_3d\chi_2d\chi_1\,
\exp(a\chi_1\chi_2)=0.
$$

The second integral contains

$$
\chi_3\chi_4(a\chi_1\chi_2)
=a\chi_3\chi_4\chi_1\chi_2.
$$

Moving $\chi_1\chi_2$ past $\chi_3\chi_4$ requires four odd swaps, so there is no minus sign:

$$
\chi_3\chi_4\chi_1\chi_2=\chi_1\chi_2\chi_3\chi_4.
$$

Therefore

$$
\int d\chi_4d\chi_3d\chi_2d\chi_1\,
\chi_3\chi_4e^{a\chi_1\chi_2}=a.
$$

The variables $\chi_3$ and $\chi_4$ were zero modes. The insertion $\chi_3\chi_4$ saturated them.

</details>

## References

- M. Srednicki, *Quantum Field Theory*. Fermionic path integrals, formal Grassmann Gaussian identities, Majorana fields, and functional determinants.
- A. Zee, *Quantum Field Theory in a Nutshell*. Grassmann integration, fermions, anomalies, and determinant intuition.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Functional integration for Fermi fields and ghost fields.
- S. Coleman, *Aspects of Symmetry*. Functional integration, instanton zero modes, determinants, and false-vacuum methods.
- M. Nakahara, *Geometry, Topology and Physics*. Grassmann calculus and fermionic oscillator path integrals.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, fermionic Gaussian integration, and determinant/Pfaffian regularization issues.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Fermions, Majorana fields, functional determinants, and gauge-theory quantization.

## Version history

- 2026-06-24: First polished draft. Defined Pfaffians as signed sums over pairings, derived the Grassmann Gaussian identity, explained the square-root identity, change-of-basis law, determinant relation, Majorana interpretation, zero-mode saturation, Pfaffian signs, and continuum QFT caveats.
