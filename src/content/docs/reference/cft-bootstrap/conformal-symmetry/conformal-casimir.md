---
title: "Conformal Casimir"
description: "Defines the quadratic conformal Casimir, derives its eigenvalue on primary conformal multiplets, and explains its role in conformal blocks and bootstrap equations."
sidebar:
  label: "Conformal Casimir"
  order: 7
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Dolan–Osborn 2004; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - conformal Casimir
  - conformal multiplets
  - primary operators
  - conformal blocks
  - Casimir equation
  - bootstrap
canonicalTopics:
  - conformal-casimir
  - quadratic-casimir
  - conformal-block-casimir-equation
  - conformal-multiplet-labels
researchStatus:
  established:
    - 'The quadratic conformal Casimir has eigenvalue $\Delta(\Delta-d)+C_2(\rho)$ on a primary of dimension $\Delta$ and rotation representation $\rho$.'
    - 'For a symmetric traceless spin-$\ell$ primary, the eigenvalue is $\Delta(\Delta-d)+\ell(\ell+d-2)$.'
  active:
    - "Casimir equations are standard; active work uses more efficient block recursions, spinning blocks, supersymmetric blocks, defects, Lorentzian inversion, and numerical bootstrap implementations."
---

## Summary

The conformal Casimir is the invariant built from conformal generators. It commutes with every generator, so it acts as a constant on an irreducible conformal multiplet. With the radial-quantization conventions of this volume, the quadratic Casimir is

$$
\mathcal C_2
=
D^2+\frac{1}{2} M_{\mu\nu}M_{\mu\nu}
-\frac{1}{2}(P_\mu K_\mu+K_\mu P_\mu).
$$

On a primary operator of scaling dimension $\Delta$ and $SO(d)$ representation $\rho$, its eigenvalue is

$$
C_{\Delta,\rho}=\Delta(\Delta-d)+C_2(\rho).
$$

For a symmetric traceless spin-$\ell$ primary,

$$
C_{\Delta,\ell}=\Delta(\Delta-d)+\ell(\ell+d-2).
$$

This number labels the whole conformal multiplet, not just the primary. The reason is simple: $\mathcal C_2$ commutes with $P_\mu$, so descendants have the same Casimir eigenvalue as the primary.

The Casimir is also the engine behind conformal-block equations. In a four-point function, the contribution of an exchanged primary and all its descendants is an eigenfunction of a two-particle conformal Casimir differential operator. This is one of the cleanest bridges from representation theory to explicit bootstrap functions.

:::note[Why the Casimir matters]
The Casimir converts the slogan “sum over conformal multiplets” into an equation. A conformal block is the part of a correlator with a definite conformal-Casimir eigenvalue and definite OPE boundary behavior.
:::

## Prerequisites

You should know the generator conventions from [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/) and the algebra from [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/). You should also know the meaning of [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) and the idea that primaries and descendants form conformal multiplets.

This page uses Euclidean radial-quantization conventions. Lorentzian signature changes the rotation group and metric signs, but the representation-theoretic eigenvalue formula is analytically continued in the usual way.

## Core idea

For any Lie algebra, a Casimir operator is a combination of generators that commutes with all generators. In ordinary angular momentum theory, the familiar example is

$$
\mathbf J^2,
$$

which commutes with all $J_i$ and labels spin representations. In conformal field theory, the analogous object is built from

$$
P_\mu,
\qquad
M_{\mu\nu},
\qquad
D,
\qquad
K_\mu.
$$

The quadratic conformal Casimir labels conformal multiplets. A primary is specified by its scaling dimension and spin data. The Casimir packages those labels into one invariant number:

$$
\Delta,\rho
\quad\longmapsto\quad
C_{\Delta,\rho}=\Delta(\Delta-d)+C_2(\rho).
$$

For symmetric traceless spin $\ell$,

$$
C_2(\ell)=\ell(\ell+d-2).
$$

This formula appears constantly in conformal blocks, radial expansions, recursion relations, and analytic bootstrap arguments.

## Setup and conventions

We use the Euclidean conformal algebra in radial-quantization convention:

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
$$

$$
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}.
$$

The quadratic Casimir is defined as

$$
\mathcal C_2
=
D^2+\frac{1}{2} M_{\mu\nu}M_{\mu\nu}
-\frac{1}{2}(P_\mu K_\mu+K_\mu P_\mu).
$$

Repeated indices are summed. The rotation Casimir is normalized so that a symmetric traceless rank-$\ell$ representation has

$$
\frac{1}{2} M_{\mu\nu}M_{\mu\nu}
\quad\leadsto\quad
\ell(\ell+d-2).
$$

Different books move signs between $M_{\mu\nu}$, factors of $i$, and the definition of the Casimir. The invariant statement is the eigenvalue formula. When comparing references, compare the eigenvalue, not just the displayed operator.

## Why it commutes with the algebra

The conformal algebra is isomorphic to

$$
\mathfrak{so}(d+1,1)
$$

in Euclidean signature and to

$$
\mathfrak{so}(d,2)
$$

in Lorentzian signature. If $J_{AB}$ are generators of this higher-dimensional rotation algebra, the quadratic invariant is

$$
\frac{1}{2}J_{AB}J^{AB}.
$$

Rewriting $J_{AB}$ in terms of $P_\mu$, $K_\mu$, $D$, and $M_{\mu\nu}$ gives the expression for $\mathcal C_2$ above. Since $J_{AB}J^{AB}$ is invariant under the adjoint action of the algebra, it commutes with every generator.

Equivalently, one can verify directly that

$$
[\mathcal C_2,P_\mu]=[\mathcal C_2,K_\mu]=[\mathcal C_2,D]=[\mathcal C_2,M_{\mu\nu}]=0
$$

using the commutation relations. The direct verification is a good algebra exercise, but conceptually the higher-dimensional rotation-algebra origin is cleaner.

## Eigenvalue on a primary

Let $|\mathcal O\rangle$ be a primary state with

$$
K_\mu|\mathcal O\rangle=0,
\qquad
D|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

Assume it transforms in an $SO(d)$ representation $\rho$, so

$$
\frac{1}{2}M_{\mu\nu}M_{\mu\nu}|\mathcal O\rangle
=
C_2(\rho)|\mathcal O\rangle.
$$

Now act with $\mathcal C_2$ on the primary. The term $P_\mu K_\mu$ vanishes because $K_\mu$ annihilates the primary:

$$
P_\mu K_\mu|\mathcal O\rangle=0.
$$

The other mixed term is

$$
K_\mu P_\mu|\mathcal O\rangle
=
[K_\mu,P_\mu]|\mathcal O\rangle,
$$

where the sum over $\mu$ is understood. Using

$$
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu},
$$

and tracing over $\mu=\nu$, the antisymmetry $M_{\mu\mu}=0$ gives

$$
[K_\mu,P_\mu]=2dD.
$$

Therefore

$$
K_\mu P_\mu|\mathcal O\rangle=2d\Delta|\mathcal O\rangle.
$$

Putting the pieces together,

$$
\begin{aligned}
\mathcal C_2|\mathcal O\rangle
&=
\left(D^2+\frac{1}{2}M_{\mu\nu}M_{\mu\nu}-\frac{1}{2}K_\mu P_\mu\right)|\mathcal O\rangle\\
&=
\left(\Delta^2+C_2(\rho)-d\Delta\right)|\mathcal O\rangle.
\end{aligned}
$$

Thus

$$
C_{\Delta,\rho}=\Delta(\Delta-d)+C_2(\rho).
$$

For a symmetric traceless tensor of spin $\ell$,

$$
C_2(\rho)=\ell(\ell+d-2),
$$

so

$$
C_{\Delta,\ell}=\Delta(\Delta-d)+\ell(\ell+d-2).
$$

This is the eigenvalue used in scalar conformal blocks in $d$ dimensions.

## Descendants have the same Casimir

Since $\mathcal C_2$ commutes with $P_\mu$,

$$
\mathcal C_2 P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
=
P_{\mu_1}\cdots P_{\mu_n}\mathcal C_2|\mathcal O\rangle.
$$

Therefore

$$
\mathcal C_2 P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
=
C_{\Delta,\rho}P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle.
$$

All descendants in the same multiplet share the same Casimir eigenvalue. This is the algebraic reason a conformal block collects a primary and all of its descendants into one object.

## Spin examples

For scalar primaries,

$$
\ell=0,
\qquad
C_{\Delta,0}=\Delta(\Delta-d).
$$

For vector primaries,

$$
\ell=1,
\qquad
C_{\Delta,1}=\Delta(\Delta-d)+d-1.
$$

For spin-two symmetric traceless primaries,

$$
\ell=2,
\qquad
C_{\Delta,2}=\Delta(\Delta-d)+2d.
$$

A conserved current in $d$ dimensions has

$$
\Delta=d-1,
\qquad
\ell=1,
$$

so

$$
C_J=(d-1)(-1)+d-1=0.
$$

A stress tensor has

$$
\Delta=d,
\qquad
\ell=2,
$$

so

$$
C_T=0+2d=2d.
$$

The current example is a useful reminder: a zero quadratic Casimir does not mean the operator is the identity. It means the particular combination of dimension and spin gives zero in this convention.

## Two-dimensional translation

In two dimensions, a primary is often labeled by holomorphic weights

$$
(h,\bar h),
$$

with

$$
\Delta=h+\bar h,
\qquad
\ell=h-\bar h.
$$

The global conformal algebra is

$$
\mathfrak{sl}(2,\mathbb C)
\simeq
\mathfrak{sl}(2)\oplus\mathfrak{sl}(2)
$$

in Euclidean complex notation. The $d=2$ global Casimir eigenvalue becomes

$$
C_{\Delta,\ell}
=
\Delta(\Delta-2)+\ell^2
=
2h(h-1)+2\bar h(\bar h-1).
$$

The full Virasoro algebra has additional structure, and Virasoro conformal blocks are not determined merely by this global quadratic Casimir. Still, the global Casimir remains the right object for global blocks and for understanding the finite conformal subgroup.

## Shadow symmetry

The scalar part of the eigenvalue obeys

$$
\Delta(\Delta-d)=(d-\Delta)((d-\Delta)-d).
$$

Therefore

$$
C_{\Delta,\ell}=C_{d-\Delta,\ell}.
$$

The representation with dimension $d-\Delta$ is called the shadow representation. This degeneracy is important in conformal-block technology: the Casimir differential equation alone cannot distinguish a block from its shadow solution. The physical block is selected by the OPE limit.

For scalar exchange, the physical block behaves schematically as

$$
g_{\Delta,\ell}(u,v)\sim u^{\Delta/2}
$$

in the $12\to 0$ OPE limit, while the shadow solution behaves like

$$
u^{(d-\Delta)/2}.
$$

More precisely, angular dependence and spin determine the leading Gegenbauer polynomial, but the power of $u$ is the quickest way to see how the physical branch is selected.

## Casimir equation for conformal blocks

Consider a scalar four-point function. After factoring out the fixed position dependence, the dynamical part depends on cross-ratios

$$
u=x\bar x,
\qquad
v=(1-x)(1-\bar x).
$$

In an OPE channel, one expands the reduced correlator as

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
\,g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v),
$$

where

$$
\Delta_{12}=\Delta_1-\Delta_2,
\qquad
\Delta_{34}=\Delta_3-\Delta_4.
$$

The conformal block $g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)$ is the contribution of one primary of dimension $\Delta$ and spin $\ell$, together with all of its descendants.

Let $\mathcal C_{12}$ be the quadratic Casimir differential operator built from the sum of generators acting on points $1$ and $2$:

$$
\mathcal C_{12}
=
\left(\mathcal G_1+\mathcal G_2\right)^2.
$$

This notation means: form the quadratic conformal Casimir using the total generator acting on the pair $(x_1,x_2)$. Then the block satisfies

$$
\mathcal C_{12}\,g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)
=
C_{\Delta,\ell}\,g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v).
$$

This is the Casimir equation. It is a second-order differential equation in the cross-ratios. The OPE boundary condition selects the physical solution.

:::tip[Blocks are representation theory in disguise]
A conformal block is not an arbitrary special function. It is the eigenfunction of a representation-theoretic operator, normalized by an OPE limit. This is why the same block appears in every CFT with the same spacetime dimension and external dimensions.
:::

## Why the pairwise Casimir appears

In the $12$ OPE channel, operators $\mathcal O_1(x_1)$ and $\mathcal O_2(x_2)$ are fused into an exchanged primary multiplet:

$$
\mathcal O_1\times\mathcal O_2
\sim
\sum_{\mathcal O} \lambda_{12\mathcal O}\,\mathcal O+\text{descendants}.
$$

The total conformal generator acting on the product is the sum of the generators acting on the two insertions:

$$
\mathcal G_{12}=\mathcal G_1+\mathcal G_2.
$$

When the OPE projects onto the multiplet of $\mathcal O$, the total generator $\mathcal G_{12}$ acts as the generator on that exchanged multiplet. Therefore its Casimir must take the exchanged eigenvalue

$$
C_{\Delta,\ell}.
$$

This argument is completely general. The explicit differential operator depends on coordinates and external spins, but the eigenvalue is fixed by the exchanged primary.

## Relation to crossing

Crossing symmetry compares different OPE channels. For four identical scalar primaries $\phi$, one can write schematically

$$
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
\,g_{\Delta,\ell}(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
\,g_{\Delta,\ell}(v,u).
$$

The Casimir does not by itself impose crossing. It supplies the channel functions $g_{\Delta,\ell}$. Crossing then says that different sums of these Casimir eigenfunctions must define the same correlator.

This separation is conceptually useful:

$$
\text{Casimir equation}
\quad\Rightarrow\quad
\text{basis of conformal blocks},
$$

$$
\text{crossing equation}
\quad\Rightarrow\quad
\text{constraints on CFT data}.
$$

The numerical bootstrap begins after both steps: write crossing in a conformal-block basis, then impose unitarity and positivity on the coefficients.

## Casimir versus Hamiltonian

In radial quantization, $D$ is the Hamiltonian on the cylinder:

$$
H_{\text{cyl}}=D.
$$

It is tempting to think the Casimir is just another name for energy. It is not. The dilatation operator $D$ distinguishes levels inside a multiplet:

$$
\Delta,
\quad
\Delta+1,
\quad
\Delta+2,
\quad
\ldots
$$

The Casimir is constant on the whole multiplet:

$$
C_{\Delta,\rho},
\quad
C_{\Delta,\rho},
\quad
C_{\Delta,\rho},
\quad
\ldots
$$

So $D$ grades states, while $\mathcal C_2$ labels the irreducible representation. Both are essential, but they answer different questions.

## Beyond the quadratic Casimir

The conformal algebra also has higher Casimir invariants. For many scalar-block applications, the quadratic Casimir is enough to characterize the differential equation for a block, supplemented by spin and boundary conditions. For general representations, especially in higher rank and with spinning operators, higher Casimirs can help distinguish representations with the same quadratic eigenvalue.

For the main bootstrap spine, the quadratic Casimir is the workhorse because it gives a second-order differential equation and the universal eigenvalue

$$
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

Higher Casimirs are best viewed as refinements rather than replacements.

## Common pitfalls

**Comparing Casimir formulas without comparing conventions.** Some references use Hermitian generators with factors of $i$, some use anti-Hermitian generators, and some use differential operators. The safest invariant is the primary eigenvalue.

**Thinking the Casimir labels a single state.** It labels the entire conformal multiplet. Descendants have different $D$-eigenvalues but the same Casimir eigenvalue.

**Forgetting the spin contribution.** The scalar formula $\Delta(\Delta-d)$ is incomplete for spinning exchange. A symmetric traceless spin-$\ell$ primary contributes $\ell(\ell+d-2)$.

**Assuming the Casimir equation uniquely defines the physical block.** It does not. Shadow solutions have the same Casimir eigenvalue. The OPE boundary condition selects the physical block.

**Confusing global and Virasoro blocks in two dimensions.** The global quadratic Casimir governs global $SL(2)$ blocks. Virasoro blocks incorporate infinitely many additional descendants generated by the full Virasoro algebra.

## Relations to other pages

- [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/) explains the generators entering $\mathcal C_2$.
- [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/) states the commutators and the relation to $\mathfrak{so}(d+1,1)$ or $\mathfrak{so}(d,2)$.
- [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) explains why conformal multiplets begin with primaries.
- [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) develops the representation theory organized by $\Delta$, spin, null states, and shortening.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) uses the Casimir equation to construct block functions.
- [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) gives the detailed cross-ratio differential equation.
- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) explains how conformal blocks enter bootstrap equations.

## Research status

The quadratic Casimir eigenvalue and its role in conformal blocks are standard. The modern frontier is not the existence of the Casimir equation, but the efficient and accurate use of conformal blocks in complicated settings: spinning external operators, mixed correlators, defects, boundaries, supersymmetry, noninteger dimension, Lorentzian inversion, and large-scale numerical bootstrap.

In numerical work, Casimir equations are one route to blocks, but not always the computationally preferred route. Recursion relations, radial coordinates, rational approximations, and specialized software are often more efficient. Conceptually, however, the Casimir remains the cleanest way to remember why conformal blocks are universal representation-theoretic objects.

## Exercises

### Exercise 1: Scalar Casimir eigenvalue

Let $|\mathcal O\rangle$ be a scalar primary with

$$
K_\mu|\mathcal O\rangle=0,
\qquad
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
\qquad
M_{\mu\nu}|\mathcal O\rangle=0.
$$

Using

$$
\mathcal C_2
=
D^2+\frac{1}{2}M_{\mu\nu}M_{\mu\nu}-\frac{1}{2}(P_\mu K_\mu+K_\mu P_\mu),
$$

show that

$$
\mathcal C_2|\mathcal O\rangle=\Delta(\Delta-d)|\mathcal O\rangle.
$$

<details><summary><strong>Solution</strong></summary>

The rotation term vanishes on a scalar primary, and $P_\mu K_\mu|\mathcal O\rangle=0$. Therefore

$$
\mathcal C_2|\mathcal O\rangle
=
\left(D^2-\frac{1}{2}K_\mu P_\mu\right)|\mathcal O\rangle.
$$

Since $K_\mu|\mathcal O\rangle=0$,

$$
K_\mu P_\mu|\mathcal O\rangle=[K_\mu,P_\mu]|\mathcal O\rangle.
$$

Tracing the commutator gives

$$
[K_\mu,P_\mu]=2dD.
$$

Thus

$$
K_\mu P_\mu|\mathcal O\rangle=2d\Delta|\mathcal O\rangle.
$$

Finally,

$$
\mathcal C_2|\mathcal O\rangle
=
(\Delta^2-d\Delta)|\mathcal O\rangle
=
\Delta(\Delta-d)|\mathcal O\rangle.
$$

</details>

### Exercise 2: Descendants have the same eigenvalue

Suppose $[\mathcal C_2,P_\mu]=0$ and

$$
\mathcal C_2|\mathcal O\rangle=C|\mathcal O\rangle.
$$

Show that $P_\nu|\mathcal O\rangle$ has the same Casimir eigenvalue if it is nonzero.

<details><summary><strong>Solution</strong></summary>

Use the commutator:

$$
\mathcal C_2P_\nu|\mathcal O\rangle
=
P_\nu\mathcal C_2|\mathcal O\rangle
=
CP_\nu|\mathcal O\rangle.
$$

Thus $P_\nu|\mathcal O\rangle$ has the same Casimir eigenvalue $C$.

</details>

### Exercise 3: Shadow degeneracy

Show that

$$
C_{\Delta,\ell}=C_{d-\Delta,\ell}
$$

for symmetric traceless spin $\ell$.

<details><summary><strong>Solution</strong></summary>

Compute the dimension-dependent part:

$$
(d-\Delta)((d-\Delta)-d)
=
(d-\Delta)(-\Delta)
=
\Delta(\Delta-d).
$$

The spin term is unchanged, so

$$
C_{d-\Delta,\ell}=C_{\Delta,\ell}.
$$

This is the Casimir reason that conformal blocks and shadow blocks solve the same differential equation.

</details>

### Exercise 4: Two-dimensional form

In $d=2$, use

$$
\Delta=h+\bar h,
\qquad
\ell=h-\bar h
$$

to show that

$$
\Delta(\Delta-2)+\ell^2=2h(h-1)+2\bar h(\bar h-1).
$$

<details><summary><strong>Solution</strong></summary>

Substitute:

$$
\Delta(\Delta-2)+\ell^2
=
(h+\bar h)(h+\bar h-2)+(h-\bar h)^2.
$$

Expand both terms:

$$
(h+\bar h)(h+\bar h-2)
=
h^2+2h\bar h+\bar h^2-2h-2\bar h,
$$

and

$$
(h-\bar h)^2=h^2-2h\bar h+\bar h^2.
$$

Adding gives

$$
2h^2+2\bar h^2-2h-2\bar h
=
2h(h-1)+2\bar h(\bar h-1).
$$

</details>

## References

- Philippe Di Francesco, Pierre Mathieu, and David Sénéchal, *Conformal Field Theory*, especially the operator formalism, global conformal algebra, and conformal families.
- F. A. Dolan and H. Osborn, “Conformal Partial Waves and the Operator Product Expansion,” for the Casimir-equation approach to higher-dimensional conformal blocks.
- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for modern higher-dimensional CFT representation theory and conformal blocks.
- David Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for radial quantization, Casimirs, OPE, conformal blocks, and bootstrap equations.
- David Poland, Slava Rychkov, and Alessandro Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” for the role of Casimir equations and blocks in numerical bootstrap.

## Version history

- 2026-06-27: First polished draft. Defines the quadratic conformal Casimir, derives its primary eigenvalue, explains descendant invariance, shadow degeneracy, and the Casimir equation for conformal blocks.
