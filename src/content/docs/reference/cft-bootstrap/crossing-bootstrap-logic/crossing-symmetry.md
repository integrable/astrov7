---
title: "Crossing Symmetry"
description: "How equality of different OPE expansions of one four-point function becomes the basic consistency condition of the conformal bootstrap."
sidebar:
  label: "Crossing Symmetry"
  order: 1
level: Graduate
status: "Polished draft"
source: "Polyakov 1974; Belavin–Polyakov–Zamolodchikov 1984; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - crossing symmetry
  - OPE associativity
  - four-point functions
  - conformal blocks
  - conformal bootstrap
canonicalTopics:
  - crossing-symmetry
  - ope-associativity
  - four-point-bootstrap
  - conformal-bootstrap
researchStatus:
  established:
    - "Crossing symmetry is the statement that different OPE expansions of the same correlator agree on their common domain of analytic continuation."
    - "For four-point functions, crossing converts the associativity of the local operator algebra into functional equations for CFT data."
  active:
    - "The precise analytic continuation, Lorentzian singularity structure, and optimal use of crossing in higher-dimensional, spinning, defect, and nonunitary settings remain active research directions."
---

## Summary

Crossing symmetry is the demand that a correlation function should not remember which pair of operators we chose to fuse first. In a four-point function, the OPE can be applied in the $12\to34$ channel, the $14\to23$ channel, or the $13\to24$ channel. These are different expansions of one object, so they must agree after analytic continuation to a common region.

For an identical scalar primary $\phi$ of dimension $\Delta_\phi$, write

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\,\mathcal G(U,V),
$$

where

$$
U=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
V=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The exchange $x_1\leftrightarrow x_3$ gives

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U).
$$

That simple-looking equation is the entrance to the conformal bootstrap. Once $\mathcal G$ is expanded in conformal blocks, crossing becomes a constraint on operator dimensions, spins, and OPE coefficients.

## Prerequisites

You should know [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/), and [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/).

It also helps to have read [Euclidean and Lorentzian CFT](/cft-bootstrap/what-is-a-cft/euclidean-and-lorentzian-cft/). Crossing is easiest to state in Euclidean signature, but many of its deepest consequences come from Lorentzian continuations.

## Core idea

A local QFT assigns correlation functions to ordered collections of local operator insertions. The OPE says that when two insertions approach each other, their product can be replaced inside correlators by a sum over local operators. For four points, there is more than one useful way to perform this replacement:

$$
(\mathcal O_1\mathcal O_2)(\mathcal O_3\mathcal O_4),
\qquad
(\mathcal O_1\mathcal O_4)(\mathcal O_2\mathcal O_3),
\qquad
(\mathcal O_1\mathcal O_3)(\mathcal O_2\mathcal O_4).
$$

Crossing symmetry says that these are not independent choices. They are different coordinate expansions of the same correlator.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Crossing channels for a four-point function](/figures/cft-bootstrap/crossing-four-point-channels.svg)

<figcaption>

Two OPE channel decompositions of the same four-point function. The $12\to34$ and $14\to23$ expansions use different intermediate primary multiplets, but crossing demands that they reconstruct one correlator.

</figcaption>
</figure>

This is why crossing is often called OPE associativity. The slogan is accurate, but one should not read it too algebraically. The OPE is an expansion with a domain of convergence, and crossing compares expansions after analytic continuation. The algebraic image is useful because it remembers the physics: local products must be associative inside correlation functions.

## Setup and conventions

We work in Euclidean flat space unless stated otherwise. For scalar four-point functions, use

$$
x_{ij}=x_i-x_j,
\qquad
x_{ij}^2=(x_i-x_j)^2.
$$

For four points in $d\ge2$, conformal symmetry leaves two independent cross-ratios. We use

$$
U=z\bar z,
\qquad
V=(1-z)(1-\bar z),
$$

with $z$ and $\bar z$ complex conjugates in Euclidean configurations. In Lorentzian signature, $z$ and $\bar z$ are better treated as independent variables with prescribed branch choices.

For identical scalar primaries, the reduced correlator is

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V),
$$

where $\phi_i$ means $\phi(x_i)$. The identity operator in the $\phi\times\phi$ OPE contributes $1$ to $\mathcal G(U,V)$ in the normalization $\langle \phi(x)\phi(0)\rangle=1/(x^2)^{\Delta_\phi}$.

## Channels and permutations

Permuting identical external operators changes the prefactor and transforms the cross-ratios. For the exchange $1\leftrightarrow3$,

$$
U\longleftrightarrow V.
$$

The same four-point function can be written as

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V)
$$

or, after exchanging $1$ and $3$,

$$
\langle \phi_3\phi_2\phi_1\phi_4\rangle
=
\frac{1}{(x_{23}^2x_{14}^2)^{\Delta_\phi}}\mathcal G(V,U).
$$

Because the operators are identical bosonic scalars, the two correlators are equal. Multiply by the common denominator and use

$$
\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}=\frac{U}{V}.
$$

This gives

$$
\mathcal G(U,V)
=
\left(\frac{U}{V}\right)^{\Delta_\phi}\mathcal G(V,U),
$$

or equivalently

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U).
$$

This is the most common form of identical-scalar crossing.

:::note[Names for the channels]
In analogy with scattering theory, the $12\to34$ channel is often called the $s$-channel, the $14\to23$ channel the $t$-channel, and the $13\to24$ channel the $u$-channel. These names are useful shorthand, but the object here is a CFT correlation function, not an ordinary scattering amplitude.
:::

## OPE channel expansion

Apply the OPE to the pair $\phi(x_1)\phi(x_2)$ and similarly to $\phi(x_3)\phi(x_4)$. The reduced four-point function has the conformal block expansion

$$
\mathcal G(U,V)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(U,V).
$$

Here $G_{\Delta,\ell}$ is the scalar conformal block for the conformal multiplet of a primary $\mathcal O$ of dimension $\Delta$ and spin $\ell$. The square appears because the same OPE coefficient occurs on the left and right side of the four-point function.

Crossing then becomes

$$
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
\left[
V^{\Delta_\phi}G_{\Delta,\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,\ell}(V,U)
\right]=0.
$$

Defining

$$
F_{\Delta,\ell}(U,V)
=
V^{\Delta_\phi}G_{\Delta,
\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,
\ell}(V,U),
$$

we get the schematic bootstrap equation

$$
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0.
$$

This equation is a compact way of saying infinitely many equations. It must hold as a function of two variables, not just at one point.

## Identity exchange and the first consistency check

The identity operator appears in $\phi\times\phi$ whenever $\phi$ has a nonzero two-point function with itself. In the standard normalization,

$$
G_{0,0}(U,V)=1,
\qquad
\lambda_{\phi\phi\mathbf 1}=1.
$$

The identity contribution to crossing is

$$
F_{\mathbf 1}(U,V)=V^{\Delta_\phi}-U^{\Delta_\phi}.
$$

Therefore the nontrivial operators must satisfy

$$
F_{\mathbf 1}(U,V)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0.
$$

This is the cleanest way to see why a CFT cannot have arbitrary operator data. The identity term is fixed by normalization. The rest of the spectrum must conspire to cancel it as a function of $U,V$.

At small $U$ with $V$ held away from zero, the $12$ OPE expansion begins with the identity. The crossed expansion must reproduce the same singular behavior using infinitely many operators in the crossed channel. Many deep bootstrap facts are sharpened versions of this elementary tension.

## Nonidentical external operators

For nonidentical scalars, the four-point function has more prefactors and crossing relates different reduced functions. For example,

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
$$

in the $12\to34$ channel involves operators in $\phi_1\times\phi_2$ and $\phi_3\times\phi_4$, while the crossed channel may involve operators in $\phi_1\times\phi_4$ and $\phi_2\times\phi_3$.

The resulting equation has the same logical form,

$$
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G^{12,34}_{\mathcal O}(U,V)
=
\sum_{\mathcal O}
\lambda_{14\mathcal O}\lambda_{23\mathcal O}
G^{14,23}_{\mathcal O}(V,U),
$$

but the coefficients need not be simple squares. Positivity becomes more subtle and usually appears only after one organizes all correlators in a reflection-positive matrix form.

This is why identical-scalar crossing is pedagogically perfect but not representative of the full bootstrap ecosystem. Realistic bootstrap systems often use several operators, several correlators, and several global-symmetry sectors.

## Crossing with global symmetry

Suppose $\phi_i$ transforms in a representation of a global symmetry group. The four-point function

$$
\langle \phi_i\phi_j\phi_k\phi_l\rangle
$$

has tensor structures in the internal indices. The OPE $\phi_i\times\phi_j$ decomposes into irreducible symmetry channels $R$:

$$
\phi_i\times\phi_j
\sim
\sum_R \sum_{\mathcal O\in R}
\lambda_{\phi\phi\mathcal O}
\mathcal O.
$$

Crossing becomes a vector equation in the space of internal tensor structures:

$$
\sum_R\sum_{\mathcal O\in R}
\lambda_{\phi\phi\mathcal O}^2
\vec F^{\,R}_{\Delta,\ell}(U,V)=0.
$$

The arrows matter. Different irreducible representations contribute different crossing vectors. In models with $O(N)$ symmetry, for instance, the singlet, symmetric-traceless, and antisymmetric sectors obey different spin selection rules and carry different blocks in the crossing equation.

## Crossing and analyticity

In Euclidean signature, OPE expansions converge in radial-ordered domains. The $12\to34$ and $14\to23$ expansions need not converge in exactly the same geometric region. Crossing is therefore not the naive equality of two power series term by term in one disk. It is the equality of analytic continuations of the same correlator.

This point prevents several mistakes:

- One channel may be efficient where another channel is inefficient.
- A truncated OPE in one channel should not be expected to reproduce all singularities of another channel.
- Lorentzian continuation can pass around branch points, producing commutators, double discontinuities, and lightcone singularities.

The practical bootstrap often evaluates derivatives at the crossing-symmetric point

$$
z=\bar z=\frac12,
\qquad
U=V=\frac14,
$$

because this point treats the two crossed channels symmetrically and lies in a good Euclidean region.

## Why crossing is powerful

Crossing is powerful because it combines three ingredients that are individually simple:

| Ingredient | Role |
|---|---|
| Conformal symmetry | Fixes the shape of each multiplet contribution. |
| OPE | Reduces correlators to sums over local operator data. |
| Locality and associativity | Requires different reductions of the same correlator to agree. |

The result is a set of nonlinear constraints on the spectrum and OPE coefficients. The equations are nonlinear because the spectrum itself is unknown, even though each block enters linearly once the spectrum is proposed.

For unitary identical-scalar problems, the squared OPE coefficients obey

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This positivity lets one ask whether the identity crossing vector can be cancelled by a positive combination of allowed non-identity vectors. That question is the bridge from crossing symmetry to numerical bootstrap bounds.

## Checks and examples

### Mean-field theory

A generalized free scalar of dimension $\Delta_\phi$ has

$$
\mathcal G(U,V)=1+U^{\Delta_\phi}+\left(\frac{U}{V}\right)^{\Delta_\phi}.
$$

Then

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U),
$$

so crossing is satisfied. The nontrivial exchanged operators are the double-twist operators schematically $\phi\partial^\ell\partial^{2n}\phi$.

### Two-dimensional minimal models

In rational two-dimensional CFTs, crossing reduces to finite-dimensional consistency conditions among conformal blocks for selected correlators. The classic minimal-model bootstrap is much more rigid than a generic higher-dimensional bootstrap problem because Virasoro symmetry packages infinitely many global descendants into each Virasoro block.

### Interacting higher-dimensional CFTs

For the 3D Ising CFT, crossing equations for correlators of $\sigma$ and $\epsilon$, combined with unitarity, $\mathbb Z_2$ symmetry, and spectral assumptions, lead to small allowed islands for the low-lying CFT data. This is not because crossing knows the word “Ising.” It is because the Ising CFT appears to be highly isolated among unitary CFT data satisfying the chosen assumptions.

## Common pitfalls

| Pitfall | Repair |
|---|---|
| Treating crossing as optional. | Crossing is part of locality and associativity of the operator algebra. Without it, the proposed CFT data do not define consistent correlators. |
| Equating crossing with permutation symmetry only. | Permutation symmetry gives the visible equation; the deeper statement is equality of different OPE channel expansions. |
| Forgetting the prefactor. | The reduced function $\mathcal G(U,V)$ is not itself invariant under all permutations; powers of $U,V$ appear. |
| Thinking each operator in one channel matches one operator in another. | Crossing equates full sums. One operator in one channel is generally reproduced by infinitely many operators in another. |
| Ignoring convergence domains. | OPE expansions are channel expansions with domains. Crossing compares their analytic continuation. |
| Assuming positivity for every crossing equation. | Positivity depends on unitarity, reflection positivity, identical or matrix-organized external data, and normalization choices. |
| Confusing global blocks with Virasoro blocks in two dimensions. | Global crossing and Virasoro crossing are both valid organizations, but they sum descendants differently. |

## Relations to other pages

- [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) defines the local expansion whose consistency crossing tests.
- [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/) gives the operator-algebra viewpoint on the same idea.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) explains the functions appearing in the channel expansion.
- [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/) turns the crossing statement into a standard equation for CFT data.
- [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) explains why unitary crossing equations can be attacked by positive functionals.
- [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/) studies crossing in Lorentzian and lightcone limits.

## Research status

The Euclidean four-point crossing equation for local primaries is established textbook material. Its use in two-dimensional CFT, higher-dimensional conformal bootstrap, statistical critical phenomena, supersymmetric CFT, and holography is central and mature.

Active questions concern how much crossing plus general principles can prove in broad classes of theories. Examples include rigorous isolation of specific higher-dimensional CFTs, optimal treatment of spinning and mixed correlators, Lorentzian inversion and dispersion methods, nonunitary CFTs, defects, boundaries, finite temperature, and modular analogues.

A good rule of thumb: crossing symmetry is settled; extracting all its consequences is very much not settled. Tiny equation, very large bite.

## Exercises

### Exercise 1: Derive identical scalar crossing

Starting from

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V),
$$

derive

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U)
$$

from the exchange $1\leftrightarrow3$.

<details><summary><strong>Solution</strong></summary>

After exchanging $1$ and $3$, the cross-ratios are interchanged:

$$
U\leftrightarrow V.
$$

The same correlator is also

$$
\frac{1}{(x_{23}^2x_{14}^2)^{\Delta_\phi}}\mathcal G(V,U).
$$

For identical bosonic scalars, the two expressions are equal. Thus

$$
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V)
=
\frac{1}{(x_{23}^2x_{14}^2)^{\Delta_\phi}}\mathcal G(V,U).
$$

Multiplying by $(x_{12}^2x_{34}^2)^{\Delta_\phi}$ gives

$$
\mathcal G(U,V)
=
\left(\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}\right)^{\Delta_\phi}\mathcal G(V,U).
$$

Since

$$
\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}=\frac{U}{V},
$$

we obtain

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U).
$$

</details>

### Exercise 2: Check generalized free crossing

Show that

$$
\mathcal G(U,V)=1+U^{\Delta_\phi}+\left(\frac{U}{V}\right)^{\Delta_\phi}
$$

satisfies identical-scalar crossing.

<details><summary><strong>Solution</strong></summary>

Compute the left side:

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
V^{\Delta_\phi}+U^{\Delta_\phi}V^{\Delta_\phi}+U^{\Delta_\phi}.
$$

Compute the right side:

$$
U^{\Delta_\phi}\mathcal G(V,U)
=
U^{\Delta_\phi}+U^{\Delta_\phi}V^{\Delta_\phi}+V^{\Delta_\phi}.
$$

The two expressions are equal term by term.

</details>

### Exercise 3: Why no one-to-one channel matching?

Explain why an exchanged primary in the $12\to34$ channel does not generally correspond to a single exchanged primary in the $14\to23$ channel.

<details><summary><strong>Solution</strong></summary>

A conformal block is the contribution of one conformal multiplet in a particular OPE channel. Crossing equates full correlators, not individual blocks. A single block in one channel has a singularity and analytic structure adapted to that channel. Re-expanding it in another channel typically requires an infinite sum of blocks. Therefore crossing relates sums over spectra and OPE coefficients, not operator-by-operator pairings.

</details>

### Exercise 4: Identity cancellation

In identical-scalar crossing, write the equation with the identity contribution separated. What must the non-identity operators do?

<details><summary><strong>Solution</strong></summary>

With $G_{0,0}=1$ and $\lambda_{\phi\phi\mathbf 1}=1$,

$$
F_{\mathbf 1}(U,V)=V^{\Delta_\phi}-U^{\Delta_\phi}.
$$

The crossing equation becomes

$$
F_{\mathbf 1}(U,V)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0.
$$

Thus the non-identity spectrum and OPE coefficients must cancel the fixed identity crossing vector as a function of $U,V$. This is the first visible bootstrap constraint.

</details>

## References

- A. M. Polyakov, “Non-Hamiltonian approach to conformal quantum field theory,” 1974.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” 1984.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters on correlation functions, OPE, conformal blocks, and crossing.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, lectures on four-point functions, OPE, conformal blocks, and bootstrap.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, sections on crossing, reflection positivity, and conformal blocks.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” sections on CFT techniques and crossing relations.

## Version history

- 2026-06-28: First polished draft. Added identical-scalar crossing derivation, channel interpretation, OPE/block expansion, identity contribution, symmetry-sector comments, pitfalls, exercises, and a crossing-channel figure.
