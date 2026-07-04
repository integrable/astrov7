---
title: "Conformal Blocks"
description: "Conformal families, Casimir equations, OPE channels, and the kinematical functions used in the bootstrap."
sidebar:
  order: 2
---

The OPE says that a product of local operators can be expanded as a sum over conformal families. A **conformal block** is the contribution of one such family to a four-point function.

That sentence is short, but it is the gateway to the modern bootstrap and to the holographic interpretation of CFT data. The OPE coefficients are dynamical numbers. The conformal blocks are universal functions fixed by symmetry. Once we know the spectrum and OPE coefficients, four-point functions are assembled as

$$
\boxed{
\text{four-point function}
=
\sum_{\text{primary }\mathcal O}
\text{OPE coefficient}\times\text{OPE coefficient}\times\text{conformal block}.
}
$$

The block is therefore the natural unit of CFT perturbation theory. In AdS/CFT language, it is also the natural boundary object associated with the exchange of an irreducible representation of the AdS isometry group.

## The four-point function setup

Let $\mathcal O_i$ be scalar primary operators of dimensions $\Delta_i$. Conformal symmetry fixes their four-point function up to a function of two cross-ratios:

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle
=
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}
{(x_{12}^2)^{(\Delta_1+\Delta_2)/2}(x_{34}^2)^{(\Delta_3+\Delta_4)/2}}
\mathcal G(u,v),
$$

where

$$
\Delta_{ij}=\Delta_i-\Delta_j,
$$

and

$$
u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

Here $x_{ij}^2=(x_i-x_j)^2$ in Euclidean signature. For identical scalars $\phi$ of dimension $\Delta_\phi$, the same convention reduces to

$$
\langle
\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)
\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}
\mathcal G(u,v).
$$

The function $\mathcal G(u,v)$ contains the dynamical information not fixed by global conformal symmetry. The conformal block expansion is a way of computing $\mathcal G(u,v)$ by repeatedly using the OPE.

## The $12\to34$ OPE channel

Now apply the OPE to $\mathcal O_1(x_1)\mathcal O_2(x_2)$ and separately to $\mathcal O_3(x_3)\mathcal O_4(x_4)$. In the $12\to34$ channel, the reduced correlator decomposes as

$$
\boxed{
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{12,34}(u,v).
}
$$

The sum runs over primary operators $\mathcal O$ that appear in both OPEs

$$
\mathcal O_1\times\mathcal O_2,
\qquad
\mathcal O_3\times\mathcal O_4.
$$

For scalar external operators, the exchanged primary is usually taken to be a symmetric traceless tensor

$$
\mathcal O_{\mu_1\cdots\mu_\ell},
$$

with spin $\ell$ and scaling dimension $\Delta$. The block

$$
G_{\Delta,\ell}^{12,34}(u,v)
$$

is the total contribution of this primary and all of its descendants:

$$
[\mathcal O]
=
\left\{
\mathcal O,
P_\mu\mathcal O,
P_{\mu_1}P_{\mu_2}\mathcal O,
\ldots
\right\}.
$$

Only the two OPE coefficients $\lambda_{12\mathcal O}$ and $\lambda_{34\mathcal O}$ are dynamical. The relative weights of the descendants inside $G_{\Delta,\ell}^{12,34}$ are fixed by the conformal algebra.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 55rem;">

![Conformal block as a projector onto one conformal family.](/figures/cft/conformal-block-family-projector.svg)

<figcaption>

A conformal block in the $12\to34$ channel is the contribution of one conformal family $[\mathcal O_{\Delta,\ell}]$ to the four-point function. The OPE coefficients $\lambda_{12\mathcal O}$ and $\lambda_{34\mathcal O}$ are dynamical CFT data, while the function $G_{\Delta,\ell}^{12,34}(u,v)$ is fixed by conformal representation theory.

</figcaption>
</figure>

This is the first point where one should resist a tempting but misleading analogy: a conformal block is not exactly a Feynman diagram. It is a representation-theoretic object. In holographic CFTs, it is related to exchange processes in AdS, but a full Witten exchange diagram generally contains more than the single conformal block of the exchanged single-trace operator.

## Projectors onto conformal families

The cleanest definition of a conformal block uses radial quantization. Think of the pair $\mathcal O_1\mathcal O_2$ as creating a state and the pair $\mathcal O_3\mathcal O_4$ as annihilating a state. Insert a projector onto the conformal family of a primary $\mathcal O$:

$$
\Pi_{\mathcal O}
=
\sum_{a,b\in[\mathcal O]}
|a\rangle (G^{-1})^{ab}\langle b|.
$$

Here $|a\rangle$ and $|b\rangle$ run over descendants in the conformal family $[\mathcal O]$, and

$$
G_{ab}=\langle a|b\rangle
$$

is the Gram matrix of descendant inner products. Then the contribution of this family to the four-point function is schematically

$$
\langle
\mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4
\rangle_{[\mathcal O]}
=
\langle
\mathcal O_1\mathcal O_2\,\Pi_{\mathcal O}\,\mathcal O_3\mathcal O_4
\rangle.
$$

After factoring out the universal position-dependent prefactor, this projected contribution is exactly the conformal block.

This formula is conceptually important for three reasons. First, it shows that a block is the contribution of an entire representation, not just the primary state. Second, it explains why descendant coefficients are fixed: they are determined by the conformal algebra and by the inner products of descendant states. Third, it makes unitarity visible. In a unitary CFT, the Gram matrix is positive definite after null states are removed, so the conformal block decomposition has positivity properties.

## OPE limit and block normalization

In the $12\to34$ channel, the OPE limit is

$$
x_1\to x_2,
\qquad
x_3\to x_4.
$$

In terms of cross-ratios this is

$$
u\to0,
\qquad
v\to1.
$$

The leading behavior of a block is determined by the exchanged primary. For scalar exchange, a common normalization is

$$
\boxed{
G_{\Delta,0}^{12,34}(u,v)
\sim
u^{\Delta/2}
\qquad
(u\to0).
}
$$

For spin $\ell$, the primary carries angular dependence. A useful way to state the leading behavior is to use radial variables. In Euclidean kinematics one may write

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

Then introduce

$$
z=\frac{4\rho}{(1+\rho)^2},
\qquad
\bar z=\frac{4\bar\rho}{(1+\bar\rho)^2},
\qquad
\rho=r e^{i\theta},
\qquad
\eta=\cos\theta.
$$

The small-$r$ expansion is the radial OPE expansion. For $d>2$, with

$$
\nu_d=\frac d2-1,
$$

a standard block normalization is

$$
G_{\Delta,\ell}(r,\eta)
=
r^\Delta
\frac{C_\ell^{(\nu_d)}(\eta)}{C_\ell^{(\nu_d)}(1)}
+O(r^{\Delta+1}),
$$

where $C_\ell^{(\nu_d)}(\eta)$ is a Gegenbauer polynomial. The power $r^\Delta$ comes from the dimension of the exchanged primary. The Gegenbauer polynomial is the angular wavefunction for spin $\ell$ on $S^{d-1}$.

The descendants then generate the higher powers

$$
r^{\Delta+1},
\quad
r^{\Delta+2},
\quad
r^{\Delta+3},
\quad
\ldots.
$$

This is one reason radial coordinates are so useful numerically: inside the Euclidean OPE convergence domain, the block is a controlled expansion in $r$.

## Casimir equation

The projector definition is conceptually clean, but it is not always the fastest way to compute blocks. A more practical characterization uses the quadratic conformal Casimir.

Let $J_i^{AB}$ be the $SO(d,2)$ generators acting on the point $x_i$ and on the tensor indices of $\mathcal O_i$. The total generator acting on the pair $(1,2)$ is

$$
J_{12}^{AB}=J_1^{AB}+J_2^{AB}.
$$

The exchanged conformal family has a fixed quadratic Casimir eigenvalue:

$$
C_2(\Delta,\ell)
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

Therefore the conformal block satisfies a differential equation of the form

$$
\boxed{
\mathcal C_{12}\,G_{\Delta,\ell}^{12,34}(u,v)
=
C_2(\Delta,\ell)G_{\Delta,\ell}^{12,34}(u,v),
}
$$

where

$$
\mathcal C_{12}
=
\frac12 J_{12}^{AB}J_{12,AB}
$$

is represented as a second-order differential operator acting on the cross-ratios. The OPE boundary condition fixes the desired solution. Without the boundary condition, the Casimir equation also admits the shadow solution associated with dimension $d-\Delta$.

This is the representation-theoretic reason blocks are universal. They are eigenfunctions of the same symmetry operator that classifies conformal multiplets.

## Blocks, shadows, and partial waves

The terms **conformal block** and **conformal partial wave** are often used loosely, but it is useful to keep them distinct.

A conformal block is the OPE contribution with a definite short-distance behavior:

$$
G_{\Delta,\ell}\sim u^{\Delta/2}
\qquad
\text{in the }12\text{ OPE limit}.
$$

The shadow block has leading behavior

$$
G_{d-\Delta,\ell}\sim u^{(d-\Delta)/2}.
$$

A conformal partial wave is usually a particular single-valued combination of the block and its shadow. The shadow formalism is extremely useful for deriving integral representations and harmonic analysis on the conformal group. The OPE, however, selects the block with the physical dimension $\Delta$.

For bootstrap equations, the objects appearing in the OPE expansion are conformal blocks, not arbitrary block-shadow combinations.

## Identity, currents, and stress-tensor blocks

The simplest exchanged operator is the identity $\mathbf 1$. For identical unit-normalized scalar operators,

$$
\phi\times\phi\supset \mathbf 1,
$$

and the identity block is

$$
G_{0,0}(u,v)=1.
$$

This reproduces the disconnected two-point contraction

$$
\langle\phi(x_1)\phi(x_2)\rangle
\langle\phi(x_3)\phi(x_4)\rangle.
$$

If the CFT has a continuous global symmetry, the conserved current $J_\mu^a$ can appear in appropriate OPE channels. It has

$$
\Delta_J=d-1,
\qquad
\ell=1.
$$

If the theory has a local stress tensor, then $T_{\mu\nu}$ has

$$
\Delta_T=d,
\qquad
\ell=2.
$$

These conserved operators sit at unitarity bounds, so their conformal families are shortened: some descendants are null because of conservation,

$$
\partial^\mu J_\mu^a=0,
\qquad
\partial^\mu T_{\mu\nu}=0.
$$

Accordingly, current and stress-tensor blocks are special cases of spinning blocks with shortening conditions imposed. Their OPE coefficients are constrained by Ward identities. For example, the coefficient of the stress-tensor block in $\langle\phi\phi\phi\phi\rangle$ is not an arbitrary independent number once the normalization of $T_{\mu\nu}$ is chosen; it is tied to $\Delta_\phi$ and to the stress-tensor two-point normalization.

## Positivity in unitary CFTs

For identical real scalar primaries in a unitary CFT, the block expansion takes the form

$$
\mathcal G(u,v)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v).
$$

After choosing positive two-point normalization, the coefficients obey

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

For identical bosonic scalars, only even-spin symmetric traceless operators appear in the singlet OPE channel unless internal symmetry structures allow an antisymmetric tensor. Thus schematically

$$
\phi\times\phi
=
\mathbf 1
+\sum_{\substack{\mathcal O\\ \ell\;\text{even}}}
\lambda_{\phi\phi\mathcal O}[\mathcal O].
$$

This positivity is the engine of the numerical conformal bootstrap. The blocks are known functions. The unknowns are nonnegative coefficients and allowed dimensions. Crossing symmetry then becomes a sharply constrained problem.

## Two dimensions: global blocks versus Virasoro blocks

In $d=2$, there is an important distinction. The finite-dimensional global conformal group is

$$
SL(2,\mathbb C),
$$

or equivalently the complexified version of the global left-right conformal group. Global conformal families are generated by the global lowering modes

$$
L_{-1},
\qquad
\bar L_{-1}.
$$

A global conformal block sums only these global descendants. But a two-dimensional CFT has local conformal symmetry, whose quantum algebra is Virasoro:

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac c{12}m(m^2-1)\delta_{m+n,0}.
$$

A Virasoro family contains all descendants created by

$$
L_{-n},\quad \bar L_{-n},
\qquad n\ge1.
$$

Therefore a Virasoro block resums much more than a global block. In AdS$_3$/CFT$_2$, this distinction is not cosmetic: Virasoro blocks include the effects of boundary gravitons. Global blocks are appropriate when one is organizing states under the finite subgroup; Virasoro blocks are appropriate when exploiting the full local conformal symmetry.

This course will return to Virasoro blocks in the two-dimensional CFT modules. For now, when we say “conformal block” in general $d$, we mean the global $SO(d,2)$ block.

## Holographic interpretation

Conformal blocks are the representation-theoretic bridge between CFT correlators and bulk physics.

A single-trace primary $\mathcal O_{\Delta,\ell}$ corresponds, at large $N$, to a single-particle field in AdS with mass and spin determined by $\Delta$ and $\ell$. The conformal family $[\mathcal O_{\Delta,\ell}]$ is the full boundary representation of that bulk particle. In this sense, the block $G_{\Delta,\ell}$ is the CFT contribution of one exchanged AdS representation.

However, one must be careful:

$$
\boxed{
\text{single conformal block}
\neq
\text{full exchange Witten diagram in general}.
}
$$

A Witten exchange diagram usually decomposes into the conformal block of the exchanged single-trace operator plus an infinite set of double-trace blocks. Those double-trace contributions are required by the boundary OPE and by the locality of the bulk interaction.

A more precise statement is that special objects such as geodesic Witten diagrams compute individual conformal blocks, while ordinary exchange Witten diagrams compute full crossing-compatible contributions to correlators. This distinction becomes crucial when reconstructing bulk locality from CFT data.

The holographic moral is:

$$
\text{blocks classify possible exchanged states,}
\qquad
\text{OPE coefficients determine how strongly they couple.}
$$

## Common pitfalls

A conformal block is not an OPE coefficient. The OPE coefficient is a number, or a tensor-structure coefficient. The block is a function of cross-ratios.

A conformal block is not the contribution of a single operator alone. It is the contribution of the primary and all descendants in the conformal family.

A conformal block is not usually a full physical amplitude. A full four-point function must be crossing-symmetric. A single block in one channel is generally not crossing-symmetric by itself.

A global block is not a Virasoro block. In two-dimensional CFT, Virasoro symmetry reorganizes infinitely many global descendants into larger families.

These distinctions sound pedantic until one studies AdS/CFT. Then they become survival equipment.

## What to remember

The conformal block expansion of a scalar four-point function is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{12,34}(u,v).
$$

The block $G_{\Delta,\ell}^{12,34}$ is fixed by conformal symmetry. It is the contribution of the conformal family $[\mathcal O_{\Delta,\ell}]$. It may be defined by a projector in radial quantization or as the solution of a quadratic Casimir equation with OPE boundary conditions.

For bootstrap, blocks turn crossing symmetry into equations for the spectrum and OPE coefficients. For AdS/CFT, blocks organize boundary correlators into exchanged AdS representations.

## Exercises

### Exercise 1: Identity block

Let $\phi$ be a unit-normalized scalar primary of dimension $\Delta_\phi$, and write

$$
\langle
\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)
\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(u,v).
$$

Show that the identity contribution in the $12\to34$ channel gives

$$
G_{0,0}(u,v)=1.
$$

<details>
<summary><strong>Solution</strong></summary>

The identity contribution in the OPE is

$$
\phi(x_1)\phi(x_2)
\supset
\frac{\mathbf 1}{(x_{12}^2)^{\Delta_\phi}}.
$$

Similarly,

$$
\phi(x_3)\phi(x_4)
\supset
\frac{\mathbf 1}{(x_{34}^2)^{\Delta_\phi}}.
$$

Multiplying the two identity contributions gives

$$
\langle
\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)
\rangle_{\mathbf 1}
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}.
$$

Comparing with the definition of $\mathcal G(u,v)$, the identity contributes

$$
\mathcal G_{\mathbf 1}(u,v)=1.
$$

Thus, in this normalization,

$$
\boxed{G_{0,0}(u,v)=1.}
$$

</details>

### Exercise 2: Why the coefficient is a product of OPE coefficients

Explain why the $12\to34$ channel contribution of a primary $\mathcal O$ to a scalar four-point function is proportional to

$$
\lambda_{12\mathcal O}\lambda_{34\mathcal O},
$$

not to a new independent four-point coefficient.

<details>
<summary><strong>Solution</strong></summary>

Use the OPE in the pair $12$:

$$
\mathcal O_1\times\mathcal O_2
\supset
\lambda_{12\mathcal O}[\mathcal O].
$$

Use the OPE again in the pair $34$:

$$
\mathcal O_3\times\mathcal O_4
\supset
\lambda_{34\mathcal O}[\mathcal O].
$$

The four-point contribution in which the same conformal family propagates between the two pairs is obtained by projecting onto $[\mathcal O]$:

$$
\langle
\mathcal O_1\mathcal O_2\Pi_{\mathcal O}\mathcal O_3\mathcal O_4
\rangle.
$$

The overlap of the pair $12$ with the family is proportional to $\lambda_{12\mathcal O}$, and the overlap of the pair $34$ with the same family is proportional to $\lambda_{34\mathcal O}$. The remaining descendant sum is fixed by conformal symmetry and is the block $G_{\Delta,\ell}^{12,34}$.

Therefore

$$
\langle1234\rangle_{[\mathcal O]}
\propto
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{12,34}(u,v).
$$

There is no independent four-point coefficient because the OPE reduces the four-point function to products of three-point data.

</details>

### Exercise 3: Casimir eigenvalue for a scalar exchange

For a scalar primary $\mathcal O$ of dimension $\Delta$, the spin is $\ell=0$. Use the general Casimir eigenvalue

$$
C_2(\Delta,\ell)=\Delta(\Delta-d)+\ell(\ell+d-2)
$$

to find the scalar eigenvalue. What happens under the shadow replacement $\Delta\to d-\Delta$?

<details>
<summary><strong>Solution</strong></summary>

For scalar exchange, set $\ell=0$. Then

$$
C_2(\Delta,0)=\Delta(\Delta-d).
$$

Under the shadow replacement,

$$
\Delta\to d-\Delta,
$$

we get

$$
C_2(d-\Delta,0)
=(d-\Delta)((d-\Delta)-d)
=(d-\Delta)(-\Delta)
=\Delta(\Delta-d).
$$

Thus the primary of dimension $\Delta$ and its shadow of dimension $d-\Delta$ have the same quadratic Casimir eigenvalue. This is why the Casimir differential equation alone does not distinguish the physical block from the shadow block; the OPE boundary condition does.

</details>

### Exercise 4: Leading OPE behavior

In the $12\to34$ OPE channel, explain why a scalar exchanged primary of dimension $\Delta$ gives a leading block behavior

$$
G_{\Delta,0}(u,v)\sim u^{\Delta/2}
$$

as $u\to0$.

<details>
<summary><strong>Solution</strong></summary>

The OPE of two scalar primaries contains the exchanged scalar primary as

$$
\mathcal O_1(x_1)\mathcal O_2(x_2)
\supset
\lambda_{12\mathcal O}
|x_{12}|^{\Delta-\Delta_1-\Delta_2}
\mathcal O(x_2)+\cdots.
$$

Similarly, the pair $34$ has an OPE coefficient $\lambda_{34\mathcal O}$. The leading contribution of the primary, before descendants are included, carries a factor controlled by the separation of the two OPE pairs:

$$
|x_{12}|^\Delta |x_{34}|^\Delta
$$

after the standard external prefactor is stripped off. The cross-ratio

$$
u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}
$$

is proportional to the square of the OPE separation, so this contribution appears as

$$
u^{\Delta/2}.
$$

Descendants add higher powers in the OPE expansion. Thus

$$
\boxed{
G_{\Delta,0}(u,v)\sim u^{\Delta/2}.
}
$$

</details>

### Exercise 5: Block versus exchange Witten diagram

In a large-$N$ holographic CFT, why is it imprecise to identify a single conformal block with a full exchange Witten diagram?

<details>
<summary><strong>Solution</strong></summary>

A single conformal block is the contribution of one conformal family $[\mathcal O]$. If $\mathcal O$ is a single-trace primary, this block represents the exchange of one irreducible AdS representation.

A full exchange Witten diagram is a complete position-space contribution to a four-point function. When expanded in CFT conformal blocks, it generally contains

$$
\text{one single-trace block}
$$

associated with the exchanged bulk field, plus

$$
\text{infinitely many double-trace blocks}
$$

associated with two-particle boundary operators. These double-trace blocks are required by the OPE structure of the boundary theory and by the locality of the bulk interaction.

Thus the better statement is:

$$
\text{a conformal block isolates one representation,}
\qquad
\text{a Witten diagram gives a full correlator contribution.}
$$

Special constructions such as geodesic Witten diagrams can compute individual blocks, but ordinary exchange Witten diagrams are not single blocks.

</details>

## Further reading

For the original two-dimensional operator-algebra viewpoint, see the discussion of conformal families, operator algebra, conformal blocks, and crossing symmetry in Di Francesco, Mathieu, and Sénéchal. For modern higher-dimensional conformal blocks and bootstrap conventions, see Rychkov’s *EPFL Lectures on Conformal Field Theory in $D\ge3$* and Simmons-Duffin’s *TASI Lectures on the Conformal Bootstrap*. For the AdS/CFT interpretation, compare conformal block decompositions with Witten diagrams, geodesic Witten diagrams, and large-$N$ double-trace expansions.
