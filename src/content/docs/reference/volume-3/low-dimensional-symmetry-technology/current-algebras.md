---
title: "Current Algebras"
description: "Explains current algebras as local algebraic structures of conserved currents, with emphasis on two-dimensional OPEs, Schwinger terms, Ward identities, and symmetry constraints."
sidebar:
  label: "Current Algebras"
  order: 6
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry, Soft Pions and Dilatations; Coleman QFT Lectures chs. 5–6; Srednicki §§22–24, 67–68; Ginsparg, Applied CFT; Di Francesco–Mathieu–Sénéchal."
topics:
  - current algebra
  - Ward identities
  - Schwinger terms
  - two-dimensional CFT
  - chiral currents
  - operator product expansion
canonicalTopics:
  - current-algebra
  - chiral-current
  - schwinger-term
  - current-ope
  - ward-identity
researchStatus:
  established:
    - "Current algebras are standard tools for encoding the local algebra of symmetry currents, especially in two-dimensional CFT, current algebra methods, and soft-pion physics."
    - "In two dimensions, holomorphic current OPEs and their mode algebras give the bridge from ordinary Noether currents to affine Kac–Moody symmetry."
  active:
    - "Modern uses emphasize current algebras with defects, boundaries, anomalies, non-semisimple symmetry, logarithmic theories, and generalized symmetry structures."
---

## Summary

A **current algebra** is the local algebra obeyed by conserved currents. It is the sharpened version of saying “charges generate a symmetry.” Instead of studying only the global charges

$$
Q^a=\int d^{d-1}\mathbf x\,j^{0a}(t,\mathbf x),
$$

one studies the local commutators or operator products of the current densities themselves.

The basic logic is:

$$
\text{symmetry}
\quad\Rightarrow\quad
\text{current}
\quad\Rightarrow\quad
\text{current algebra}
\quad\Rightarrow\quad
\text{Ward identities and selection rules}.
$$

In two-dimensional QFT and CFT, current algebras become especially powerful because a conserved chiral current can be holomorphic:

$$
\bar\partial J^a(z)=0.
$$

Then the current algebra is encoded in an operator product expansion,

$$
J^a(z)J^b(w)
\sim
\frac{k\,\kappa^{ab}}{(z-w)^2}
+
\frac{i f^{ab}{}_{c}J^c(w)}{z-w}
+\text{regular}.
$$

The coefficient $k$ is the **level**. The double pole is the two-dimensional descendant of the Schwinger term or central extension. Expanding the current in modes gives the affine algebra of the next page.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A diagram showing conserved currents, current-current OPEs, mode algebras, and Ward identities as connected descriptions of current algebra.](/figures/symmetry-anomalies-topology/current-algebra-ope-modes.svg)

<figcaption>

A current algebra can be read in several equivalent languages: equal-time commutators, current-current OPEs, contour Ward identities, and mode algebras. In two dimensions these descriptions become unusually concrete because holomorphic currents turn local symmetry into complex analysis.

</figcaption>
</figure>

This page explains current algebra as low-dimensional symmetry technology. The next page explains the affine Kac–Moody algebra obtained by expanding holomorphic currents into Laurent modes.

## Prerequisites

You should know [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/), [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/), [Bosonization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/bosonization/), and the basic idea of an operator product expansion.

For two-dimensional formulas, we use complex coordinates

$$
z=x^1+ix^2,\qquad \bar z=x^1-ix^2
$$

in Euclidean signature unless a page says otherwise. Normalizations of currents and levels vary across the literature. This page fixes the algebraic structure and states the normalization whenever a formula is convention-sensitive.

## Core idea

For an ordinary continuous internal symmetry, the global charges obey

$$
[Q^a,Q^b]=if^{ab}{}_{c}Q^c.
$$

A current algebra asks for the local version:

$$
[j^{0a}(t,\mathbf x),j^{0b}(t,\mathbf y)].
$$

Naively one expects

$$
[j^{0a}(t,\mathbf x),j^{0b}(t,\mathbf y)]
=
if^{ab}{}_{c}j^{0c}(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

In quantum field theory, however, local products are singular. Extra derivative-of-delta-function terms can appear. These are **Schwinger terms**:

$$
[j^{0a}(t,x),j^{0b}(t,y)]
=
if^{ab}{}_{c}j^{0c}(t,x)\delta(x-y)
+
\text{central terms}.
$$

Those central terms are not cosmetic. They encode anomalies, levels, and representation data. In two dimensions they become the central extension of affine current algebra.

## Equal-time current algebra

Let $j^{\mu a}$ be a conserved current for a Lie algebra $\mathfrak g$. The charge is

$$
Q^a=\int dx\, j^{0a}(t,x)
$$

in $1+1$ dimensions. The charge should generate the symmetry action on local operators:

$$
[Q^a,\mathcal O_i]=-(T^a)_i{}^j\mathcal O_j
$$

up to the sign convention used for active transformations.

A local current algebra is stronger. It specifies commutators of densities. A common schematic form is

$$
[j^{0a}(t,x),j^{0b}(t,y)]
=
if^{ab}{}_{c}j^{0c}(t,x)\delta(x-y)
+
C^{ab}\partial_x\delta(x-y).
$$

The first term is the Lie algebra localized at a point. The second term is a Schwinger term. It is central because it is proportional to the identity rather than to an operator-valued current.

For compact simple $\mathfrak g$, $C^{ab}$ is usually proportional to the invariant bilinear form $\kappa^{ab}$. In a two-dimensional chiral theory it becomes proportional to the level $k$.

:::note[Source note: current commutators]
The current-algebra tradition in QFT often starts from equal-time commutators and derives soft theorems, pion amplitudes, or Ward identities. Modern CFT usually packages the same local algebra in OPE language. The translation is cleanest in two dimensions.
:::

## Two-dimensional chiral currents

In two Euclidean dimensions, write the current components as

$$
J(z)=j_z(z,\bar z),\qquad \bar J(\bar z)=j_{\bar z}(z,\bar z).
$$

A conserved current obeys

$$
\bar\partial J+\partial\bar J=0.
$$

If the current is chiral, then

$$
\bar J=0,\qquad \bar\partial J=0.
$$

Thus $J(z)$ is holomorphic away from operator insertions. This turns Ward identities into contour-integral statements.

For a holomorphic current $J^a(z)$, the charge acting on an operator at $w$ can be written as

$$
Q^a_{\mathcal C}=\frac{1}{2\pi i}\oint_{\mathcal C}dz\,J^a(z).
$$

If the contour $\mathcal C$ encloses a local operator $\mathcal O_i(w)$, then the singular part of the OPE determines the action:

$$
J^a(z)\mathcal O_i(w)
\sim
\frac{-(T^a)_i{}^j\mathcal O_j(w)}{z-w}.
$$

The minus sign here follows the active convention inherited from the ordinary-symmetry pages. If a different convention for $Q^a$ is chosen, this sign flips.

## Current-current OPE

For a nonabelian chiral current algebra, the defining OPE is

$$
J^a(z)J^b(w)
\sim
\frac{k\,\kappa^{ab}}{(z-w)^2}
+
\frac{i f^{ab}{}_{c}J^c(w)}{z-w}.
$$

Here:

| Symbol | Meaning |
|---|---|
| $\mathfrak g$ | Lie algebra of the chiral symmetry. |
| $f^{ab}{}_{c}$ | Structure constants. |
| $\kappa^{ab}$ | Invariant bilinear form used to normalize generators. |
| $k$ | Level of the current algebra. |
| $J^a(z)$ | Holomorphic current. |

The simple pole encodes the Lie bracket. The double pole is the central extension. If $k=0$, the OPE still has the classical Lie bracket term, but many unitary CFT applications require positive level for nontrivial compact current algebras.

For an abelian $U(1)$ current, the structure constants vanish and the OPE reduces to

$$
J(z)J(w)\sim \frac{k}{(z-w)^2}.
$$

This is the current algebra of a compact free boson or chiral fermion, up to normalization.

:::note[Normalization warning]
Some CFT references absorb $i$ into the structure constants or use anti-Hermitian generators. Some normalize $\kappa^{ab}$ so that long roots have length squared $2$, while particle-physics references often normalize fundamental generators by $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. The value called “$k$” depends on that choice.
:::

## Contours and Ward identities

The holomorphic current Ward identity is a contour-deformation statement.

Insert $J^a(z)$ into a correlator:

$$
\left\langle J^a(z)\mathcal O_1(w_1)\cdots\mathcal O_n(w_n)\right\rangle.
$$

If the current has OPE

$$
J^a(z)\mathcal O_i(w_i)
\sim
\frac{-(T_i^a)\mathcal O_i(w_i)}{z-w_i},
$$

then integrating $J^a(z)$ around all insertions gives

$$
\sum_{i=1}^n
\left\langle
\mathcal O_1(w_1)\cdots (T_i^a\mathcal O_i)(w_i)\cdots \mathcal O_n(w_n)
\right\rangle
=0
$$

for a correlator on the sphere with no extra current insertion at infinity.

This is the chiral current version of the global Ward identity. The advantage is that the same contour technology also captures current insertions, descendants, Knizhnik–Zamolodchikov equations, and affine representation theory.

## From OPE to modes

A holomorphic current has Laurent expansion

$$
J^a(z)=\sum_{n\in\mathbb Z}J_n^a z^{-n-1}.
$$

The modes are contour integrals,

$$
J_n^a=\frac{1}{2\pi i}\oint dz\, z^n J^a(z).
$$

Using the current-current OPE and contour manipulations gives

$$
[J_m^a,J_n^b]
=
if^{ab}{}_{c}J_{m+n}^c
+
k\,m\,\kappa^{ab}\delta_{m+n,0}.
$$

This is the affine Kac–Moody algebra. The zero modes obey the original finite-dimensional Lie algebra:

$$
[J_0^a,J_0^b]=if^{ab}{}_{c}J_0^c.
$$

Thus the affine algebra is not a replacement for the symmetry algebra. It is a loop-enhanced, centrally extended local version of it.

## Examples

### Free compact boson

For a free boson $\varphi$, a chiral $U(1)$ current is

$$
J(z)=i\sqrt{k}\,\partial\varphi(z),
$$

with normalization chosen so that

$$
J(z)J(w)\sim\frac{k}{(z-w)^2}.
$$

Vertex operators

$$
V_q(w)=e^{iq\varphi(w)}
$$

carry $U(1)$ charge because

$$
J(z)V_q(w)\sim \frac{q\,V_q(w)}{z-w}.
$$

This is the current-algebra core of abelian bosonization.

### Free chiral fermions

For chiral fermions $\psi_i$ in a representation of a group $G$, the bilinear

$$
J^a(z)=:\psi^\dagger_i(T^a)^i{}_{j}\psi^j:(z)
$$

is a holomorphic current in the free theory. Wick contraction gives the current-current OPE with a level determined by the representation and normalization of $T^a$.

This example is the simplest way to see where the double pole comes from: it is a short-distance singularity of a product of two composite currents.

### Wess–Zumino–Witten models

The Wess–Zumino–Witten model on a compact Lie group $G$ has chiral left and right current algebras. Schematically,

$$
G_L(z)\times G_R(\bar z)
$$

becomes two commuting affine algebras, one holomorphic and one antiholomorphic. The integer level $k$ is tied to quantization of the Wess–Zumino term.

WZW models are the canonical interacting examples where current algebra is not just a perturbative trick but a full organizing principle of the CFT.

## Schwinger terms and anomalies

Schwinger terms are central extensions of current algebras. They are closely related to anomalies.

A local current algebra without central extension may be the classical expectation. Quantum regularization can force a central term. In two-dimensional chiral fermion theories, the same coefficient that appears in the current OPE controls anomalous variation under background gauge transformations.

This is not an accident. A current algebra records how symmetry acts locally at short distances. An anomaly is precisely the obstruction to making that symmetry compatible with background gauging. Current algebra is often where the obstruction becomes visible.

:::caution[Do not erase the central term]
A derivative-of-delta-function term or double pole can look like a technical nuisance. It is usually the main physical content: the level, the anomaly coefficient, the central extension, or the obstruction data.
:::

## Current algebra versus ordinary global symmetry

An ordinary global symmetry only requires charges obeying a group law. A current algebra asks for the local singular structure of the currents.

| Structure | Ordinary symmetry | Current algebra |
|---|---|---|
| Basic object | Global charge $Q^a$ | Local current $j^{\mu a}$ or $J^a(z)$ |
| Algebra | $[Q^a,Q^b]=if^{ab}{}_{c}Q^c$ | Current-current commutators or OPEs |
| Extra data | Representation of operators | Schwinger terms, level, local singularities |
| Natural in | Any dimension | Especially powerful in two dimensions |
| Main output | Selection rules | Ward identities, affine symmetry, exact constraints |

This distinction is why current algebra was historically powerful even before modern CFT language: it extracted robust consequences from symmetry and locality without solving the full dynamics.

## Common pitfalls

**Confusing current algebra with the global Lie algebra.** The zero modes reproduce the finite-dimensional Lie algebra, but the full current algebra contains infinitely many modes and central terms.

**Dropping Schwinger terms.** Central extensions often encode anomaly data. Removing them by hand usually changes the theory.

**Forgetting normalization of $k$.** The level depends on how the invariant bilinear form is normalized. Always state the convention.

**Assuming every conserved current is holomorphic.** Conservation alone gives $\bar\partial J+\partial\bar J=0$. Holomorphic factorization needs additional conditions such as chirality and conformal invariance.

**Treating current products as ordinary products.** Composite currents are singular at coincident points. OPEs and normal ordering are not optional cosmetics.

**Forgetting global and boundary subtleties.** Contour arguments can fail or acquire extra terms on manifolds with boundary, punctures, nontrivial cycles, or anomalous background fields.

## Relations to other pages

[Affine Symmetries Preview](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/affine-symmetries-preview/) turns the current-current OPE into the affine Kac–Moody mode algebra.

[Bosonization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/bosonization/) uses abelian current algebra as its basic dictionary. [Fermionization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/fermionization/) explains the spin-structure and fermion-parity caveats behind free-fermion current algebras.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter gives the general current formalism. The [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter explains why central terms and anomalous current conservation are often two views of the same quantum obstruction.

## Research status

Ordinary current algebra, chiral current OPEs, and affine Kac–Moody algebras are established tools in QFT and CFT.

Active directions include current algebra in logarithmic and nonunitary CFTs, supergroup current algebras, boundary and defect current algebra, anomalous current algebra in generalized symmetry settings, and current-like structures for non-invertible symmetry where “current” may be replaced by topological defect networks.

## Exercises

### Exercise 1: U(1) charge from an OPE

Suppose

$$
J(z)\mathcal O_q(w)\sim\frac{q\,\mathcal O_q(w)}{z-w}.
$$

Show that the contour charge

$$
Q=\frac{1}{2\pi i}\oint_w dz\,J(z)
$$

acts on $\mathcal O_q$ with eigenvalue $q$.

<details><summary><strong>Solution</strong></summary>

Insert the OPE into the contour integral:

$$
Q\,\mathcal O_q(w)
=
\frac{1}{2\pi i}\oint_w dz\,
\frac{q\,\mathcal O_q(w)}{z-w}
=
q\,\mathcal O_q(w).
$$

Only the simple pole contributes. This is the contour version of charge action.

</details>

### Exercise 2: Current modes

Let

$$
J(z)=\sum_{n\in\mathbb Z}J_n z^{-n-1},
\qquad
J(z)J(w)\sim\frac{k}{(z-w)^2}.
$$

Show that

$$
[J_m,J_n]=k\,m\,\delta_{m+n,0}.
$$

<details><summary><strong>Solution</strong></summary>

Use the contour definition

$$
J_m=\frac{1}{2\pi i}\oint dz\,z^mJ(z).
$$

The commutator is obtained by the double contour integral around the singular part of the OPE:

$$
[J_m,J_n]
=
\frac{1}{(2\pi i)^2}
\oint_0 dw\,w^n
\oint_w dz\,z^m\frac{k}{(z-w)^2}.
$$

The inner contour gives

$$
\oint_w dz\,\frac{z^m}{(z-w)^2}=2\pi i\,m\,w^{m-1}.
$$

Thus

$$
[J_m,J_n]
=
\frac{k m}{2\pi i}\oint_0 dw\,w^{m+n-1}
=
k m\,\delta_{m+n,0}.
$$

</details>

### Exercise 3: Why the double pole is central

In the OPE

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+
\frac{i f^{ab}{}_{c}J^c(w)}{z-w},
$$

explain why the double pole becomes a central term in the mode algebra.

<details><summary><strong>Solution</strong></summary>

The double pole is proportional to the identity operator, not to another current. When converted into modes, it produces

$$
k\,m\,\kappa^{ab}\delta_{m+n,0}.
$$

This term commutes with all operators because it is a number times the identity. It is therefore central.

</details>

### Exercise 4: Ward identity from contour deformation

Let $J^a(z)$ be holomorphic away from insertions. Explain why moving a large contour past several operator insertions gives a global symmetry Ward identity.

<details><summary><strong>Solution</strong></summary>

Because $J^a(z)$ is holomorphic away from insertions, the contour integral of $J^a$ is invariant under deformations that do not cross singularities. If a large contour enclosing all insertions can be shrunk away or moved to infinity with no contribution, then the sum of residues at all insertions must vanish. Each residue is the symmetry action on that insertion, so one obtains

$$
\sum_i
\langle\mathcal O_1\cdots (T_i^a\mathcal O_i)\cdots \mathcal O_n\rangle=0.
$$

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “Dilatations,” for the current-algebra tradition in QFT.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 5–6, for symmetry, conservation laws, and internal currents.
- Mark Srednicki, *Quantum Field Theory*, §§22–24 and §§67–68, for continuous symmetries, nonabelian symmetries, and Ward identities.
- Paul Ginsparg, “Applied Conformal Field Theory,” especially the sections on free fields and affine Kac–Moody algebras.
- Philippe Di Francesco, Pierre Mathieu, and David Sénéchal, *Conformal Field Theory*, for current OPEs, affine algebras, WZW models, and rational CFT.
- Peter Goddard and David Olive, “Kac–Moody and Virasoro Algebras in Relation to Quantum Physics,” for the classic physics review perspective.

## Version history

- 2026-06-23: Initial polished draft. Added equal-time current algebra, Schwinger terms, holomorphic current OPEs, contour Ward identities, examples, anomaly caveats, and exercises.
