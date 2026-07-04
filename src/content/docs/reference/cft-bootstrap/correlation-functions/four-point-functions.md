---
title: "Four-Point Functions"
description: "Explains conformal four-point functions, cross ratios, OPE channels, conformal-block decompositions, and the crossing equation that underlies the bootstrap."
sidebar:
  label: "Four-Point Functions"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Osborn and Petkou 1994; Rychkov 2016; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - four-point functions
  - cross ratios
  - operator product expansion
  - conformal blocks
  - crossing symmetry
canonicalTopics:
  - cft-four-point-functions
  - conformal-cross-ratios
  - conformal-block-decomposition
  - crossing-symmetry
researchStatus:
  established:
    - "Four-point functions are fixed by conformal symmetry up to functions of cross ratios; their OPE decompositions and crossing relations are the basic equations of the conformal bootstrap."
    - "For identical scalar operators in a unitary CFT, the Euclidean conformal-block decomposition has nonnegative squared OPE coefficients in an orthonormal basis."
  active:
    - "Modern bootstrap work extends these constraints to spinning operators, mixed correlators, defects, Lorentzian regimes, numerical semidefinite programs, and analytic large-spin expansions."
---

## Summary

Four-point functions are where CFT stops being kinematics and starts becoming a consistency problem. For identical scalar primaries $\phi$ of dimension $\Delta_\phi$, conformal symmetry fixes the four-point function to the form

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}},
$$

where $\mathcal G(u,v)$ is a function of the two conformal cross ratios

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The function $\mathcal G(u,v)$ is not arbitrary. The OPE expands it in conformal blocks,

$$
\mathcal G(u,v)
=
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2\,G_{\Delta,\ell}(u,v),
$$

and the same correlator must be obtained by applying the OPE in a different order. For identical scalars, this gives the crossing equation

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

This is the seed of the conformal bootstrap: the spectrum and OPE coefficients must be such that all OPE channel decompositions agree.

:::note[One line to remember]
Three-point functions give the multiplication constants; four-point functions demand that multiplication be associative.
:::

## Prerequisites

You should know [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), the idea of a [Conformal Frame](/cft-bootstrap/correlation-functions/conformal-frame/), and the operator–state/OPE intuition developed in [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) and [State-Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/).

For a first pass, read the scalar identical-operator formulas and the crossing equation. The later sections on spinning correlators, Lorentzian continuation, and numerical positivity are important, but they are not needed to understand the basic logic.

## Core idea

A two-point function has no shape. A three-point function has no shape. A four-point function has shape: after using conformal symmetry to fix three points, the fourth point still has two invariant coordinates.

Those two coordinates can be written as $u,v$ or as $z,\bar z$:

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![Four points, cross ratios, and OPE channels](/figures/cft-bootstrap/four-point-cross-ratios-channels.svg)

<figcaption>

Four points leave two real conformal invariants, packaged as $z,\bar z$ or $u=z\bar z$, $v=(1-z)(1-\bar z)$. Different OPE pairings give different channel expansions of the same function.

</figcaption>
</figure>

The four-point function is therefore the first scalar correlator with an undetermined function. The bootstrap idea is that this function has many equivalent OPE expansions, and they must all agree.

The rough structure is

$$
\text{four-point function}
\quad
\Longrightarrow
\quad
\text{OPE in one channel}
\quad
=
\quad
\text{OPE in another channel}.
$$

The equality is highly nontrivial because each channel expansion is organized by the spectrum of primary operators and their OPE coefficients.

## Setup and conventions

We work in flat Euclidean space unless stated otherwise. Write

$$
x_{ij}=|x_i-x_j|,
\qquad
x_{ij}^2=(x_i-x_j)^2.
$$

For scalar primaries $\mathcal O_i$ of dimensions $\Delta_i$, define

$$
\Delta_{ij}=\Delta_i-\Delta_j.
$$

The two standard cross ratios are

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

They are invariant under translations, rotations, dilatations, and special conformal transformations. In Euclidean kinematics, one often introduces $z,\bar z$ by

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

where $\bar z$ is the complex conjugate of $z$ for real Euclidean configurations. In Lorentzian kinematics, analytic continuation makes $z$ and $\bar z$ independent variables.

For four nonidentical scalar primaries, a convenient convention is

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\mathcal O_4(x_4)\rangle
=
\frac{
\left(\frac{x_{24}}{x_{14}}\right)^{\Delta_{12}}
\left(\frac{x_{14}}{x_{13}}\right)^{\Delta_{34}}
}
{x_{12}^{\Delta_1+\Delta_2}x_{34}^{\Delta_3+\Delta_4}}
\mathcal G_{1234}(u,v).
$$

The prefactor is conventional. Different books distribute powers of $x_{ij}$ differently, but all choices leave the same invariant content in a function of $u$ and $v$.

For identical scalars this simplifies to

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}.
$$

This is the normalization used for the main crossing equations below.

## Cross ratios and conformal frames

A conformal frame is a convenient representative of a conformal equivalence class of point configurations. For four points in Euclidean signature and $d\ge 2$, a standard frame is

$$
x_1=0,
\qquad
x_3=e_1,
\qquad
x_4=\infty,
\qquad
x_2=(\sigma,\tau,0,\ldots,0).
$$

Then

$$
z=\sigma+i\tau,
\qquad
\bar z=\sigma-i\tau,
$$

and the cross ratios become

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The notation $x_4=\infty$ means the usual primary limit

$$
\mathcal O(\infty)=\lim_{|x|\to\infty}|x|^{2\Delta}\mathcal O(x).
$$

In this frame, the reduced four-point function can be viewed as a matrix element on the cylinder or in radial quantization. That is the bridge to conformal blocks: insert a complete set of states between pairs of operators, and organize the result by conformal multiplets.

## OPE limits and channels

A four-point function has several natural short-distance limits. Each limit corresponds to an OPE channel.

| Channel | OPE pairing | Typical limit | What is expanded |
|---|---|---|---|
| s-channel | $(12)(34)$ | $x_1\to x_2$, $x_3\to x_4$ | $\mathcal O_1\times\mathcal O_2$ and $\mathcal O_3\times\mathcal O_4$ |
| t-channel | $(14)(23)$ | $x_1\to x_4$, $x_2\to x_3$ | $\mathcal O_1\times\mathcal O_4$ and $\mathcal O_2\times\mathcal O_3$ |
| u-channel | $(13)(24)$ | $x_1\to x_3$, $x_2\to x_4$ | $\mathcal O_1\times\mathcal O_3$ and $\mathcal O_2\times\mathcal O_4$ |

The labels $s,t,u$ are borrowed from scattering theory. They are only names for pairings; no scattering interpretation is required.

In the identical scalar convention,

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}},
$$

the $s$-channel OPE limit $x_1\to x_2$ corresponds to

$$
u\to0,
\qquad
v\to1.
$$

The leading identity contribution gives

$$
\mathcal G(u,v)=1+\cdots
\qquad
(u\to0,\ v\to1).
$$

Non-identity primaries contribute powers controlled by their dimensions, plus angular dependence controlled by their spin.

## Conformal block decomposition

Apply the OPE to $\mathcal O_1(x_1)\mathcal O_2(x_2)$ and to $\mathcal O_3(x_3)\mathcal O_4(x_4)$. Each primary operator $\mathcal O$ and all of its descendants contribute a fixed function of cross ratios: a conformal block.

For scalar external operators,

$$
\mathcal G_{1234}(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}\,
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v),
$$

where $\mathcal O$ has dimension $\Delta$ and spin $\ell$. The block $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}$ is fixed by conformal symmetry. The dynamical input is only the spectrum and the OPE coefficients.

For identical scalars with unit two-point normalization,

$$
\mathcal G(u,v)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v).
$$

In a unitary CFT, the coefficients $\lambda_{\phi\phi\mathcal O}^2$ are nonnegative in this expansion. This positivity is the engine behind many numerical bootstrap bounds.

The identity operator is part of the sum:

$$
\mathbf 1\in \phi\times\phi,
\qquad
\Delta_{\mathbf 1}=0,
\qquad
\ell_{\mathbf 1}=0,
\qquad
G_{0,0}(u,v)=1.
$$

Thus the identity contribution is the constant $1$ in the $s$-channel reduced correlator.

:::note[Blocks are kinematics]
A conformal block is not a new dynamical object. It is the fixed contribution of one conformal multiplet to a four-point function. Dynamics chooses which blocks appear and with what coefficients.
:::

## Crossing symmetry

The same four local operators can be multiplied in different orders. Associativity of the OPE requires the channel decompositions to agree. For identical scalars, exchanging $x_1$ and $x_3$ maps

$$
u\leftrightarrow v.
$$

Starting from

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}},
$$

permutation symmetry gives

$$
\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
=
\frac{\mathcal G(v,u)}{x_{23}^{2\Delta_\phi}x_{14}^{2\Delta_\phi}}.
$$

Using

$$
\frac{x_{12}^2x_{34}^2}{x_{14}^2x_{23}^2}=\frac{u}{v},
$$

we obtain

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u),
$$

or equivalently

$$
 v^{\Delta_\phi}\mathcal G(u,v)
 =u^{\Delta_\phi}\mathcal G(v,u)
$$

Substituting the block expansion gives

$$
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
\left[
 v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
 -u^{\Delta_\phi}G_{\Delta,\ell}(v,u)
\right]=0.
$$

Define

$$
F_{\Delta,\ell}(u,v)
=
 v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
 -u^{\Delta_\phi}G_{\Delta,\ell}(v,u).
$$

Then the crossing equation is simply

$$
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(u,v)=0.
$$

This is an infinite-dimensional vector equation: every point, derivative, or expansion coefficient in cross-ratio space gives a constraint.

## Why positivity matters

In an orthonormal basis of exchanged primaries in a unitary Euclidean CFT,

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

The crossing equation is therefore not merely an equation with unknown signs. It is a sum of known functions with nonnegative coefficients, subject to assumptions about the spectrum.

This permits the logic of linear functionals. If a proposed spectrum were consistent, then no linear functional $\alpha$ could satisfy

$$
\alpha(F_{\mathbf 1})>0,
\qquad
\alpha(F_{\Delta,\ell})\ge0
\quad\text{for every allowed non-identity }(\Delta,\ell).
$$

If such a functional exists, the proposed spectrum is excluded. This is the basic mechanism behind rigorous numerical bootstrap bounds.

The positivity statement depends on all of the following:

- Euclidean reflection positivity or Lorentzian unitarity with a good Wick rotation.
- A basis where two-point functions are positive and diagonal.
- Identical external scalar operators, or a suitable positive matrix generalization for mixed correlators.
- Correct treatment of tensor structures and global-symmetry sectors.

When any of these assumptions changes, the positivity statement must be rewritten rather than assumed.

## Examples

### Generalized free scalar

Let $\phi$ be a generalized free scalar with unit two-point function

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{x^{2\Delta_\phi}}.
$$

Wick contraction gives

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
+\frac{1}{x_{13}^{2\Delta_\phi}x_{24}^{2\Delta_\phi}}
+\frac{1}{x_{14}^{2\Delta_\phi}x_{23}^{2\Delta_\phi}}.
$$

In the identical-scalar convention, the reduced correlator is

$$
\mathcal G_{\mathrm{GFF}}(u,v)
=1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

This obeys crossing:

$$
v^{\Delta_\phi}\mathcal G_{\mathrm{GFF}}(u,v)
=u^{\Delta_\phi}\mathcal G_{\mathrm{GFF}}(v,u).
$$

The OPE contains the identity and an infinite tower of double-trace operators schematically written

$$
[\phi\phi]_{n,\ell}\sim \phi\,\partial^{2n}\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}\phi-\text{traces},
$$

with approximate dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell
$$

in the generalized free theory.

### Ising-type four-point functions

The correlator

$$
\langle \sigma\sigma\sigma\sigma\rangle
$$

is the canonical entry point into the scalar bootstrap. The $\sigma\times\sigma$ OPE contains $\mathbb Z_2$-even operators:

$$
\sigma\times\sigma\sim \mathbf 1+\lambda_{\sigma\sigma\varepsilon}\varepsilon+\lambda_{\sigma\sigma\varepsilon'}\varepsilon'+\lambda_{\sigma\sigma T}T+\cdots.
$$

Crossing of the four-$\sigma$ correlator constrains the dimensions and OPE coefficients of all such exchanged operators. The celebrated three-dimensional Ising bootstrap starts from this idea, then uses more correlators, assumptions, and numerical precision to isolate a small allowed region for the CFT data.

### Free scalar caveat

A free scalar in $d>2$ has infinitely many conserved higher-spin currents. These appear in the $\phi\times\phi$ OPE and make the four-point function much more special than a generic interacting CFT. The generalized-free formula is useful, but a genuinely local free scalar also has an equation of motion and null descendants. Keep those two ideas distinct.

## Global symmetry and mixed correlators

If operators transform under a global symmetry, four-point functions decompose into representation channels. For example, if $\phi_i$ is a vector of $O(N)$, then

$$
\phi_i\times\phi_j
$$

contains singlet, traceless-symmetric, and antisymmetric sectors. The four-point function is a sum of tensor structures in $i,j,k,l$, each multiplying a function of $u,v$.

Crossing becomes a vector or matrix equation relating these sectors. In mixed-correlator bootstrap problems, one studies several four-point functions at once, such as

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\varepsilon\varepsilon\rangle,
\qquad
\langle \varepsilon\varepsilon\varepsilon\varepsilon\rangle.
$$

The unknown OPE coefficients assemble into positive semidefinite matrices rather than single nonnegative numbers. This is why semidefinite programming enters the numerical bootstrap.

## Spinning four-point functions

Four-point functions involving spin have more tensor structures and more crossing equations. A schematic form is

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_a \mathcal T_a(x_i,z_i)\,\mathcal G_a(u,v),
$$

where $\mathcal T_a$ are independent conformally covariant tensor structures and the functions $\mathcal G_a$ are dynamical. The OPE expansion then involves spinning conformal blocks and multiple three-point tensor structures.

Important examples include

- four currents $\langle JJJJ\rangle$,
- four stress tensors $\langle TTTT\rangle$,
- mixed scalar-current correlators,
- mixed scalar-stress-tensor correlators,
- fermionic correlators,
- correlators in parity-violating three-dimensional CFTs.

The conceptual picture is the same as for scalars, but the bookkeeping is heavier: tensor structures, Ward identities, conservation equations, parity, and permutation symmetries all have to be implemented consistently.

## Two-dimensional form

In two-dimensional CFT, a four-point function depends on $z$ and $\bar z$. For scalar primaries with weights $(h_i,\bar h_i)$, the global conformal group fixes a prefactor and leaves a function of $z,\bar z$.

The OPE decomposition can be written in terms of global conformal blocks or, more powerfully, Virasoro conformal blocks. A typical diagonal schematic form is

$$
\mathcal G(z,\bar z)
=\sum_p C_{12p}C_{34p}\,
\mathcal F_p(z)\overline{\mathcal F_p(z)}.
$$

Here $\mathcal F_p(z)$ is a chiral conformal block. In rational CFTs, the number of allowed primaries can be finite, and crossing becomes a finite-dimensional consistency problem involving fusion and braiding data. In generic irrational CFTs, the sum may be infinite or include integrals over continuous spectra.

The key point survives unchanged: four-point functions are where OPE associativity becomes visible.

## Euclidean and Lorentzian regimes

In Euclidean signature, $z$ and $\bar z$ are complex conjugates. The OPE is often absolutely convergent in appropriate radial variables, and crossing can be treated as an equality of Euclidean functions.

Lorentzian continuation is subtler. The variables $z$ and $\bar z$ become independent, and branch cuts encode causal orderings, commutators, Regge limits, lightcone limits, and chaos-type constraints. Lorentzian methods such as the lightcone bootstrap and inversion formulas extract CFT data from controlled singular limits of four-point functions.

The Euclidean bootstrap and Lorentzian bootstrap are not separate theories. They are different analytic regimes of the same correlators.

## Common pitfalls

### Forgetting that the prefactor is conventional

The reduced function $\mathcal G(u,v)$ depends on how powers of $x_{ij}$ are factored out. Crossing formulas must match the chosen convention.

### Confusing $u$ with a channel label

The cross ratio $u$ is not the same thing as the u-channel. Unfortunately the notation is traditional. The u-channel is a pairing of operators; the cross ratio $u$ is an invariant number.

### Dropping the identity operator

The identity block is essential. In the $s$-channel identical-scalar convention, it gives the leading $1$ in $\mathcal G(u,v)$ as $u\to0$, $v\to1$.

### Assuming positivity without checking the setup

The simple coefficient positivity $\lambda^2\ge0$ applies in a unitary identical-scalar setup with orthonormal exchanged operators. Mixed correlators, spinning external operators, nonunitary CFTs, and non-diagonal two-point metrics require modified statements.

### Treating crossing as a single number equation

Crossing is a functional equation. Numerical bootstrap methods turn it into finitely many derivative constraints only after choosing a truncation or functional space.

### Thinking conformal blocks are optional notation

Blocks are what make the OPE compatible with conformal symmetry. They package every descendant contribution fixed by a primary. Without blocks, the four-point OPE expansion is not organized in a symmetry-adapted way.

## Relations to other pages

- [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/) explains the coefficients that appear squared or paired in four-point block decompositions.
- [Cross Ratios](/cft-bootstrap/correlation-functions/cross-ratios/) gives a focused treatment of $u,v$ and $z,\bar z$.
- [Conformal Frame](/cft-bootstrap/correlation-functions/conformal-frame/) explains the gauge-fixing viewpoint on point configurations.
- [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) develops the short-distance expansion used in each channel.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) studies the functions $G_{\Delta,\ell}(u,v)$.
- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) turns the equality of channel decompositions into bootstrap equations.
- [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) explains how positivity and linear functionals become practical bounds.

## Research status

The conformal form of scalar four-point functions, the cross ratios, the OPE block expansion, and the basic crossing equation are established textbook material.

Active work lies in scale and refinement: high-precision mixed-correlator bootstrap, spinning correlators, supersymmetric multiplets, defect and boundary four-point functions, Lorentzian inversion formulas, Regge and lightcone limits, modular and thermal analogues, rigorous error control for numerical computations, and analytic control of large-spin expansions.

For readers entering research, the most important habit is to specify the full setup: external operators, two-point normalization, global-symmetry channel, tensor-structure basis, OPE channel, cross-ratio convention, and Euclidean or Lorentzian regime.

## Exercises

### Exercise 1: cross ratios in the conformal frame

Use the conformal frame

$$
x_1=0,
\qquad
x_3=e_1,
\qquad
x_4=\infty,
\qquad
x_2=(\sigma,\tau,0,\ldots,0),
$$

and define $z=\sigma+i\tau$. Show that

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

<details><summary><strong>Solution</strong></summary>

Before sending $x_4$ to infinity, the cross ratios are

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

When $x_4\to\infty$, the ratios $x_{34}^2/x_{24}^2$ and $x_{14}^2/x_{24}^2$ tend to $1$. Since $x_1=0$ and $x_3=e_1$,

$$
x_{12}^2=\sigma^2+\tau^2=z\bar z,
\qquad
x_{13}^2=1.
$$

Thus $u=z\bar z$. Also

$$
x_{23}^2=(\sigma-1)^2+\tau^2=(1-z)(1-\bar z),
$$

so $v=(1-z)(1-\bar z)$.

</details>

### Exercise 2: crossing of generalized free theory

For

$$
\mathcal G(u,v)=1+u^\Delta+\left(\frac{u}{v}\right)^\Delta,
$$

verify the identical-scalar crossing equation

$$
v^\Delta\mathcal G(u,v)=u^\Delta\mathcal G(v,u).
$$

<details><summary><strong>Solution</strong></summary>

Compute the left-hand side:

$$
v^\Delta\mathcal G(u,v)
=v^\Delta+(uv)^\Delta+u^\Delta.
$$

Now exchange $u$ and $v$ in $\mathcal G$:

$$
\mathcal G(v,u)=1+v^\Delta+\left(\frac{v}{u}\right)^\Delta.
$$

Multiplying by $u^\Delta$ gives

$$
u^\Delta\mathcal G(v,u)
=u^\Delta+(uv)^\Delta+v^\Delta.
$$

The two expressions agree.

</details>

### Exercise 3: the identity block in the OPE limit

For identical unit-normalized scalars, explain why the $s$-channel identity contribution gives $\mathcal G(u,v)\to1$ as $x_1\to x_2$ and $x_3\to x_4$.

<details><summary><strong>Solution</strong></summary>

The identity term in the OPE is

$$
\phi(x_1)\phi(x_2)\sim \frac{1}{x_{12}^{2\Delta_\phi}}\mathbf 1+\cdots.
$$

Similarly,

$$
\phi(x_3)\phi(x_4)\sim \frac{1}{x_{34}^{2\Delta_\phi}}\mathbf 1+\cdots.
$$

Thus the leading contribution to the four-point function is

$$
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}.
$$

Comparing with

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=\frac{\mathcal G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}},
$$

gives $\mathcal G(u,v)\to1$.

</details>

### Exercise 4: why squared OPE coefficients are nonnegative

In the identical-scalar expansion

$$
\mathcal G(u,v)=\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v),
$$

why are the coefficients nonnegative in a unitary CFT?

<details><summary><strong>Solution</strong></summary>

Choose an orthonormal basis of exchanged primary states in radial quantization, so that the two-point metric is positive and diagonal. The same real coefficient $\lambda_{\phi\phi\mathcal O}$ appears at the two three-point vertices of the identical-scalar four-point function. The contribution of the primary family is therefore proportional to

$$
\lambda_{\phi\phi\mathcal O}\lambda_{\phi\phi\mathcal O}=\lambda_{\phi\phi\mathcal O}^2.
$$

For real coefficients in a reflection-positive setup, this square is nonnegative. In mixed-correlator problems, the analogous statement is positivity of a matrix of OPE coefficients, not necessarily positivity of a single number in every component.

</details>

### Exercise 5: identify the OPE channel

In the limit $z\to0$ with $\bar z\to0$ in the conformal frame, which OPE channel is being probed?

<details><summary><strong>Solution</strong></summary>

In the conformal frame, $u=z\bar z$. Thus $z,\bar z\to0$ means $u\to0$. This corresponds to $x_1\to x_2$ in the standard frame, so it probes the $s$-channel OPE $\mathcal O_1\times\mathcal O_2$, together with the corresponding pairing $\mathcal O_3\times\mathcal O_4$.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. See the operator formalism, conformal families, conformal blocks, crossing, and minimal-model chapters.
- H. Osborn and A. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals Phys.* 231 (1994) 311–362.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D Greater Than or Equal to 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI 2015 lectures, arXiv:1602.07982.
- F. A. Dolan and H. Osborn, “Conformal Four Point Functions and the Operator Product Expansion,” *Nucl. Phys. B* 599 (2001) 459–496, arXiv:hep-th/0011040.
- M. Hogervorst and S. Rychkov, “Radial Coordinates for Conformal Blocks,” *Phys. Rev. D* 87 (2013) 106004, arXiv:1303.1111.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Rev. Mod. Phys.* 91 (2019) 015002, arXiv:1805.04405.

## Version history

- 2026-06-27: Added a polished page on scalar four-point kinematics, cross-ratios, conformal frames, OPE channels, crossing equations, and bootstrap positivity.
