---
title: "Operator Product Expansions in 2D"
description: "Explains the two-dimensional CFT operator product expansion, singular terms, chiral algebra, stress-tensor and current OPEs, and contour-mode extraction."
sidebar:
  label: "OPEs in 2D"
  order: 7
level: Graduate
status: "Polished draft"
source: "BPZ 1984; Di Francesco–Mathieu–Sénéchal 1997; Ginsparg 1988; Kac 1997"
topics:
  - two-dimensional CFT
  - operator product expansion
  - chiral algebra
  - Virasoro algebra
  - current algebra
canonicalTopics:
  - operator-product-expansions-in-two-dimensional-cft
  - chiral-operator-product-expansion
  - singular-terms-and-contour-algebra
  - virasoro-and-current-ope
researchStatus:
  established:
    - "In two-dimensional CFT, local OPEs decompose into holomorphic and antiholomorphic data; singular OPE terms encode Ward identities, mode algebras, and fusion constraints."
  active:
    - "Logarithmic CFTs, nonsemisimple chiral algebras, defects, boundaries, irrational spectra, and categorical formulations require refinements beyond the elementary primary-field OPE."
---

## Summary

The operator product expansion in two-dimensional CFT says that when two local operators approach one another, their product can be replaced inside correlators by a sum of local operators at one point:

$$
\mathcal O_i(z,\bar z)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k
y_{ij}^k(z,\bar z,\partial,\bar\partial)\mathcal O_k(0).
$$

For primary fields, the leading term has the characteristic two-dimensional form

$$
\phi_i(z,\bar z)\phi_j(0)
\sim
\sum_k
C_{ij}{}^k
z^{h_k-h_i-h_j}
\bar z^{\bar h_k-\bar h_i-\bar h_j}
\left(\phi_k(0)+\text{descendants}\right).
$$

The words “inside correlators” matter. The OPE is not ordinary multiplication of pointwise functions. It is a local expansion valid when all other insertions are farther away than the separation between the two operators.

Two-dimensional CFT is special because many important OPEs are holomorphic. Their singular parts determine contour integrals, and contour integrals determine symmetry algebras. For example,

$$
T(z)\phi(w,\bar w)
\sim
{h\phi(w,\bar w)\over (z-w)^2}
+{\partial\phi(w,\bar w)\over z-w}
$$

is the local form of the conformal Ward identity. Similarly,

$$
T(z)T(w)
\sim
{c/2\over (z-w)^4}
+{2T(w)\over (z-w)^2}
+{\partial T(w)\over z-w}
$$

is the OPE version of the Virasoro algebra.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/), [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), and [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/).

For the higher-dimensional perspective, see [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/), and [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/).

## Core idea

The OPE is the local multiplication law of operators. In a two-dimensional CFT it becomes unusually powerful because local conformal symmetry splits the short-distance expansion into holomorphic and antiholomorphic pieces.

<figure class="doc-figure" style="--figure-width: 48rem;">

![The 2D OPE replaces two nearby insertions by a local tower at one point.](/figures/cft-bootstrap/two-dimensional-ope-contours.svg)

<figcaption>

When two insertions lie inside a small contour that excludes all other insertions, their product can be replaced by a sum over local operators and descendants at one point. Singular holomorphic terms control contour integrals and therefore mode algebras.

</figcaption>
</figure>

The most useful slogan is

$$
\text{singular OPE terms}
\quad\Longleftrightarrow\quad
\text{contour algebra}.
$$

A pole in $z-w$ is not merely a divergence. It tells a contour integral what residue to pick up. That residue is the infinitesimal symmetry action, mode commutator, or Ward identity.

## Setup and conventions

We use Euclidean complex coordinates

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2,
\qquad
\partial={1\over 2}(\partial_1-i\partial_2),
\qquad
\bar\partial={1\over 2}(\partial_1+i\partial_2).
$$

A primary field has weights $(h,\bar h)$ and transforms locally as

$$
\phi'(z',\bar z')
=
\left({\partial z'\over \partial z}\right)^{-h}
\left({\partial \bar z'\over \partial \bar z}\right)^{-\bar h}
\phi(z,\bar z).
$$

Equivalently, when expressing the same field in new coordinates, one often writes the inverse Jacobian form. The important invariant statement is that $h$ and $\bar h$ control holomorphic and antiholomorphic short-distance powers.

We write $A(z)B(w)\sim\cdots$ for equality of singular terms and leading local terms inside correlators as $z\to w$. Regular terms may be omitted when only contour residues are needed.

When both holomorphic and antiholomorphic dependence matters, write

$$
z_{ij}=z_i-z_j,
\qquad
\bar z_{ij}=\bar z_i-\bar z_j.
$$

## Primary-field OPE

Let $\phi_i$, $\phi_j$, and $\phi_k$ be primary fields with weights $(h_i,\bar h_i)$, $(h_j,\bar h_j)$, and $(h_k,\bar h_k)$. The leading primary contribution to the OPE has the form

$$
\phi_i(z,\bar z)\phi_j(0)
\sim
\sum_k C_{ij}{}^k
z^{h_k-h_i-h_j}
\bar z^{\bar h_k-\bar h_i-\bar h_j}
\phi_k(0)+\cdots.
$$

The dots include descendants of $\phi_k$ and contributions of other conformal families. Global conformal symmetry fixes descendant coefficients once the primary coefficient is chosen. For example, in a purely holomorphic chiral sector, the first descendant appears as

$$
\phi_i(z)\phi_j(0)
\supset
C_{ij}{}^k z^{h_k-h_i-h_j}
\left(
\phi_k(0)
+{h_k+h_i-h_j\over 2h_k}z\partial\phi_k(0)+\cdots
\right),
$$

when $h_k\ne0$ and $\phi_k$ is an ordinary global primary. Similar formulas hold in the antiholomorphic sector.

In a full 2D CFT, a local operator has both sectors. The OPE coefficient $C_{ij}{}^k$ is part of the CFT data, while the descendant terms are kinematics once the symmetry algebra and normalization conventions are fixed.

## Identity channel

The identity operator has weights

$$
h_\mathbf 1=\bar h_\mathbf 1=0.
$$

If two scalar primaries are normalized by

$$
\langle \phi_i(z,\bar z)\phi_j(0)\rangle
={g_{ij}\over z^{2h_i}\bar z^{2\bar h_i}},
$$

then the identity contribution to the OPE is

$$
\phi_i(z,\bar z)\phi_j(0)
\supset
{g_{ij}\mathbf 1\over z^{2h_i}\bar z^{2\bar h_i}}
$$

when the two-point function is allowed by spin and internal symmetries.

For a unit-normalized scalar primary,

$$
\phi(z,\bar z)\phi(0)
\sim
{\mathbf 1\over |z|^{2\Delta}}+\text{less singular terms}.
$$

The identity channel is the vacuum channel in radial quantization. It dominates the short-distance limit whenever it is allowed.

## Holomorphic OPEs and singular parts

A holomorphic field $A(z)$ has OPEs involving only powers of $z-w$ in the singular part:

$$
A(z)B(w)\sim
\sum_{n\ge1}{C_n(w)\over (z-w)^n}.
$$

The singular part is enough to compute contour integrals. If

$$
A_m={1\over 2\pi i}\oint dz\,z^{m+h_A-1}A(z),
$$

then the commutators of modes are obtained by moving contours past insertions and collecting residues. This is why chiral OPEs are often treated as algebraic multiplication tables.

Do not mistake this for saying that regular terms are unimportant. Regular terms matter for full correlation functions, normal-ordered products, and non-singular operator definitions. But pole terms are the part seen by local contour symmetries.

## Stress tensor OPEs

The defining OPE of the stress tensor with a primary field is

$$
T(z)\phi(w,\bar w)
\sim
{h\phi(w,\bar w)\over (z-w)^2}
+{\partial\phi(w,\bar w)\over z-w}.
$$

The antiholomorphic stress tensor obeys

$$
\bar T(\bar z)\phi(w,\bar w)
\sim
{\bar h\phi(w,\bar w)\over (\bar z-\bar w)^2}
+{\bar\partial\phi(w,\bar w)\over \bar z-\bar w}.
$$

These OPEs encode the fact that $\phi$ has weights $(h,\bar h)$. Integrating $T(z)$ against a vector field $\epsilon(z)$ gives the infinitesimal conformal transformation

$$
\delta_\epsilon\phi(w,\bar w)
=
\epsilon(w)\partial\phi(w,\bar w)+h\partial\epsilon(w)\phi(w,\bar w).
$$

The stress tensor OPE with itself is

$$
T(z)T(w)
\sim
{c/2\over (z-w)^4}
+{2T(w)\over (z-w)^2}
+{\partial T(w)\over z-w}.
$$

The fourth-order pole is the central term. Without it, $T$ would behave like a primary of weight $2$. With it, $T$ is quasi-primary under global conformal maps and anomalous under general local conformal maps.

Using

$$
L_n={1\over 2\pi i}\oint dz\,z^{n+1}T(z),
$$

the $TT$ OPE gives the Virasoro algebra

$$
[L_m,L_n]=(m-n)L_{m+n}+{c\over 12}m(m^2-1)\delta_{m+n,0}.
$$

The barred modes obey the same formula with $\bar c$, and the two sectors commute in an ordinary local CFT:

$$
[L_m,\bar L_n]=0.
$$

## Current OPEs

For a holomorphic conserved current $J^a(z)$ associated with an affine symmetry, the OPE with a field in representation $R$ is

$$
J^a(z)\phi_i(w,\bar w)
\sim
{(t_R^a)_i{}^j\phi_j(w,\bar w)\over z-w}.
$$

The contour integral

$$
Q^a={1\over 2\pi i}\oint dz\,J^a(z)
$$

acts as the symmetry generator on local fields.

For a nonabelian current algebra, the current-current OPE is

$$
J^a(z)J^b(w)
\sim
{k\delta^{ab}\over (z-w)^2}
+{if^{ab}{}_cJ^c(w)\over z-w}.
$$

The coefficient $k$ is the level. In modes,

$$
J^a_n={1\over 2\pi i}\oint dz\,z^nJ^a(z),
$$

the OPE gives

$$
[J^a_m,J^b_n]
=if^{ab}{}_cJ^c_{m+n}+km\delta^{ab}\delta_{m+n,0}.
$$

This is the affine Kac–Moody algebra. The same logic applies to antiholomorphic currents $\bar J^a(\bar z)$.

## Free-field examples

For a chiral free fermion normalized by

$$
\langle \psi(z)\psi(w)\rangle={1\over z-w},
$$

the basic OPE is

$$
\psi(z)\psi(w)\sim {1\over z-w}.
$$

The stress tensor is

$$
T(z)=-{1\over 2}:\psi\partial\psi:(z),
$$

and one finds

$$
T(z)\psi(w)
\sim
{\frac{1}{2}\psi(w)\over (z-w)^2}+{\partial\psi(w)\over z-w}.
$$

Thus $\psi$ has holomorphic weight $h=1/2$.

For a chiral free boson with

$$
X(z)X(w)\sim -\log(z-w),
$$

one has

$$
\partial X(z)\partial X(w)
\sim -{1\over (z-w)^2}.
$$

It is often convenient to define

$$
J(z)=i\partial X(z),
$$

so that

$$
J(z)J(w)\sim {1\over (z-w)^2}.
$$

For vertex operators

$$
V_\alpha(z)=:e^{i\alpha X(z)}:,
$$

the leading OPE is

$$
V_\alpha(z)V_\beta(w)
\sim
(z-w)^{\alpha\beta}V_{\alpha+\beta}(w)+\cdots,
$$

in this normalization. In a compact boson, allowed charges and mutual locality impose additional lattice conditions.

## Normal ordering and regular parts

Normal ordering removes singular self-contractions. If two holomorphic fields have OPE

$$
A(z)B(w)=\text{singular terms}+\text{regular terms},
$$

then the normal-ordered product is the finite local operator obtained from the regular part:

$$
:A B:(w)=\lim_{z\to w}\left(A(z)B(w)-\text{singular terms}\right).
$$

For example, the free-boson stress tensor can be written as

$$
T(z)=-{1\over 2}:\partial X\partial X:(z),
$$

or, using $J=i\partial X$,

$$
T(z)={1\over 2}:JJ:(z).
$$

Normal ordering is not merely a notation for “put annihilation operators on the right.” In CFT it is a local subtraction prescription tied to the OPE.

## Contour extraction

The simplest residue identity is

$$
{1\over 2\pi i}\oint_w dz\,{1\over z-w}=1.
$$

If

$$
A(z)B(w)\sim {C(w)\over z-w},
$$

then

$$
\oint_w {dz\over 2\pi i} A(z)B(w)=C(w).
$$

For higher poles,

$$
{1\over 2\pi i}\oint_w dz\,{f(z)\over (z-w)^{n+1}}
={1\over n!}\partial_w^n f(w).
$$

This identity turns the stress-tensor OPE into conformal transformations. For example,

$$
\delta_\epsilon\phi(w)
=
\oint_w {dz\over 2\pi i}\epsilon(z)T(z)\phi(w)
$$

with

$$
T(z)\phi(w)
\sim
{h\phi(w)\over (z-w)^2}+{\partial\phi(w)\over z-w}
$$

gives

$$
\delta_\epsilon\phi(w)=h\partial\epsilon(w)\phi(w)+\epsilon(w)\partial\phi(w).
$$

That is the infinitesimal primary transformation law.

## OPE, fusion, and conformal blocks

The OPE tells us which conformal families can appear in the product of two operators. Schematically,

$$
\mathcal V_i\times\mathcal V_j
=\sum_k N_{ij}{}^k\mathcal V_k,
$$

where $\mathcal V_i$ denotes a conformal family or chiral module. The nonnegative integers $N_{ij}{}^k$ are fusion multiplicities in rational settings, but in a general CFT the spectrum and multiplicities can be continuous, infinite, or nonsemisimple.

For a four-point function, applying the OPE in the $12$ channel produces a conformal-block decomposition:

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\sum_k C_{12k}C_{34k}\mathcal F_k(z)\bar{\mathcal F}_k(\bar z),
$$

with the precise index contractions depending on normalization and degeneracies.

In rational CFT, the sum over chiral blocks is finite for fixed external fields. In irrational CFT, such as Liouville theory, the decomposition may involve integrals over continuous spectra. The local OPE idea is the same, but the bookkeeping is different.

## Locality and monodromy

Two-dimensional OPEs may involve fractional powers:

$$
z^{h_k-h_i-h_j}\bar z^{\bar h_k-\bar h_i-\bar h_j}.
$$

Moving one operator around another sends

$$
z\to e^{2\pi i}z,
\qquad
\bar z\to e^{-2\pi i}\bar z.
$$

The phase is controlled by spin differences. A full local correlator must have acceptable monodromy. Chiral blocks alone can be multivalued; physical correlators are assembled so that locality, spin-statistics, and any extended-algebra constraints are satisfied.

This is one reason holomorphic factorization must be handled carefully. A chiral algebra may provide building blocks, but the full local CFT is the consistent pairing of left and right sectors.

## OPE associativity in 2D

Associativity says that expanding a product of three or more operators in different orders gives the same local correlator. In a four-point function, this becomes equality of different channel decompositions:

$$
\sum_p C_{12p}C_{p34}\mathcal F_p^{(s)}(z)\bar{\mathcal F}_p^{(s)}(\bar z)
=
\sum_q C_{14q}C_{q23}\mathcal F_q^{(t)}(z)\bar{\mathcal F}_q^{(t)}(\bar z).
$$

This is the two-dimensional conformal bootstrap equation in its broadest local form. In minimal models and rational CFTs, the equations become finite algebraic and analytic consistency conditions. In general 2D CFTs, the same principle remains true but may involve infinite sums, continuous spectra, or nontrivial analytic continuation.

## Common pitfalls

**Treating the OPE as ordinary pointwise multiplication.** The OPE is an asymptotic or convergent local expansion inside correlators, with a specified radial-ordering domain.

**Keeping only the leading primary and forgetting descendants.** The leading power identifies the conformal family, but descendants are essential for full correlators and conformal blocks.

**Assuming chiral factorization means one product.** Full local correlators are usually sums of products of holomorphic and antiholomorphic blocks.

**Ignoring branch cuts.** Fractional powers are common. A local CFT must have consistent monodromy after left and right sectors are combined.

**Confusing OPE coefficients with two-point-normalization-independent numbers.** If operators are rescaled, OPE coefficients change. Invariant statements involve consistent two-point metrics and products such as normalized squared OPE coefficients.

**Calling all regular terms irrelevant.** Regular terms do not affect simple residues, but they define normal-ordered products and matter in composite-operator calculations.

**Using the stress-tensor OPE for non-primary fields without modification.** Descendants, logarithmic partners, currents, and fields with anomalous transformation laws have extra structure.

## Relations to other pages

[Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) derives the Ward identity behind the $T\phi$ OPE. [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/) explains why OPEs are Hilbert-space spectral decompositions.

[OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) gives the general CFT OPE viewpoint. This page specializes it to 2D, where pole terms and contour residues become a working algebra.

[Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) derives the Virasoro commutators from the $TT$ OPE. [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) develops the $JJ$ OPE and affine symmetry in detail.

[Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/) explains how the choice of symmetry algebra changes the conformal blocks generated by the OPE.

[Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) uses null states and OPE closure to solve a class of rational theories.

## Research status

The elementary two-dimensional OPE technology is established and foundational. It underlies the Virasoro algebra, affine current algebras, minimal models, WZW models, rational CFT, and the two-dimensional conformal bootstrap.

Active and advanced directions refine the same idea. Logarithmic CFTs allow non-diagonal action of $L_0$ and logarithmic OPE terms. Nonsemisimple tensor categories describe logarithmic and nonunitary models. Defects and boundaries introduce bulk-boundary and defect OPEs. Irrational CFTs such as Liouville theory require continuous spectra. Modern chiral-algebra and vertex-operator-algebra language gives a theorem-level formulation of many holomorphic OPE statements.

The safe graduate-level rule is: master the pole terms, residues, and primary OPE first. Then treat rationality, logarithms, defects, and categorical language as refinements of the same local principle.

## Exercises

### Extract the primary transformation law

Use

$$
T(z)\phi(w)\sim {h\phi(w)\over (z-w)^2}+{\partial\phi(w)\over z-w}
$$

and

$$
\delta_\epsilon\phi(w)=\oint_w {dz\over 2\pi i}\epsilon(z)T(z)\phi(w)
$$

to derive

$$
\delta_\epsilon\phi(w)=\epsilon(w)\partial\phi(w)+h\partial\epsilon(w)\phi(w).
$$

<details><summary><strong>Solution</strong></summary>

Insert the OPE into the contour integral:

$$
\delta_\epsilon\phi(w)
=
\oint_w {dz\over 2\pi i}\epsilon(z)
\left({h\phi(w)\over (z-w)^2}+{\partial\phi(w)\over z-w}\right).
$$

The simple pole gives

$$
\epsilon(w)\partial\phi(w).
$$

The double pole gives a derivative of $\epsilon$:

$$
\oint_w {dz\over 2\pi i}{\epsilon(z)\over (z-w)^2}=\partial\epsilon(w).
$$

Thus

$$
\delta_\epsilon\phi(w)=\epsilon(w)\partial\phi(w)+h\partial\epsilon(w)\phi(w).
$$

</details>

### Derive the central term in the Virasoro algebra

Assume

$$
T(z)T(w)\sim {c/2\over (z-w)^4}+{2T(w)\over (z-w)^2}+{\partial T(w)\over z-w}
$$

and

$$
L_n={1\over 2\pi i}\oint dz\,z^{n+1}T(z).
$$

Show that the central term in $[L_m,L_n]$ is

$$
{c\over 12}m(m^2-1)\delta_{m+n,0}.
$$

<details><summary><strong>Solution</strong></summary>

The fourth-order pole contributes

$$
{c\over 2}\oint_0 {dw\over 2\pi i}w^{n+1}
\oint_w {dz\over 2\pi i}{z^{m+1}\over (z-w)^4}.
$$

Using

$$
\oint_w {dz\over 2\pi i}{z^{m+1}\over (z-w)^4}
={1\over 3!}\partial_w^3 w^{m+1}
={m(m^2-1)\over 6}w^{m-2},
$$

we get

$$
{c\over 2}{m(m^2-1)\over 6}
\oint_0 {dw\over 2\pi i}w^{m+n-1}
={c\over 12}m(m^2-1)\delta_{m+n,0}.
$$

The second- and first-order poles give $(m-n)L_{m+n}$.

</details>

### Current charge action

Suppose

$$
J^a(z)\phi_i(w)\sim {(t^a)_i{}^j\phi_j(w)\over z-w}.
$$

Show that

$$
Q^a\phi_i(w)=(t^a)_i{}^j\phi_j(w),
\qquad
Q^a={1\over 2\pi i}\oint_w dz\,J^a(z).
$$

<details><summary><strong>Solution</strong></summary>

Insert the OPE:

$$
Q^a\phi_i(w)
=
\oint_w {dz\over 2\pi i}{(t^a)_i{}^j\phi_j(w)\over z-w}.
$$

The contour integral of $(z-w)^{-1}$ is $1$, so

$$
Q^a\phi_i(w)=(t^a)_i{}^j\phi_j(w).
$$

</details>

### Free fermion weight

Let

$$
\psi(z)\psi(w)\sim {1\over z-w},
\qquad
T(z)=-{1\over 2}:\psi\partial\psi:(z).
$$

Using Wick contractions, verify that

$$
T(z)\psi(w)\sim {\frac{1}{2}\psi(w)\over (z-w)^2}+{\partial\psi(w)\over z-w}.
$$

<details><summary><strong>Solution</strong></summary>

Contract one of the fermions in $T(z)$ with $\psi(w)$. The contraction

$$
\psi(z)\psi(w)\sim {1\over z-w}
$$

and its derivative

$$
\partial\psi(z)\psi(w)\sim -{1\over (z-w)^2}
$$

produce the singular terms. Carefully accounting for fermion signs and expanding the uncontracted field around $w$ gives

$$
T(z)\psi(w)\sim {\frac{1}{2}\psi(w)\over (z-w)^2}+{\partial\psi(w)\over z-w}.
$$

Thus $\psi$ is a primary field of holomorphic weight $h=1/2$.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” for the foundational local conformal bootstrap and OPE framework.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the chapters on conformal invariance in two dimensions, the operator formalism, OPEs, minimal models, and current algebras.
- P. Ginsparg, *Applied Conformal Field Theory*, for a compact derivation of the stress-tensor OPE, Virasoro modes, and free-field examples.
- V. Kac, *Vertex Algebras for Beginners*, for the algebraic formulation of chiral OPEs and modes.
- P. Goddard and D. Olive, “Kac–Moody and Virasoro algebras in relation to quantum physics,” for a classic review of current algebras and Virasoro symmetry.

## Version history

- 2026-06-28: First polished draft. Introduces the 2D OPE, primary OPE powers, identity channel, stress-tensor and current OPEs, contour extraction, free-field examples, fusion, monodromy, and bootstrap associativity.
