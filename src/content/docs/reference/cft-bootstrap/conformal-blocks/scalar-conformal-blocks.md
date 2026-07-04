---
title: "Scalar Conformal Blocks"
description: "Defines scalar conformal blocks, fixes their normalization, and explains their OPE limits, radial expansion, special cases, and bootstrap role."
sidebar:
  label: "Scalar Conformal Blocks"
  order: 2
level: Graduate
status: "Polished draft"
source: "Ferrara–Gatto–Grillo 1973; Dolan–Osborn 2001; Pappadopulo–Rychkov–Espin–Rattazzi 2012; Hogervorst–Rychkov 2013; Poland–Rychkov–Vichi 2019"
topics:
  - scalar conformal blocks
  - conformal partial waves
  - radial expansion
  - OPE channels
  - bootstrap equations
canonicalTopics:
  - scalar-conformal-blocks
  - conformal-block-normalization
  - radial-coordinates
  - cft-data
  - bootstrap-kinematics
researchStatus:
  established:
    - "For scalar external primaries, each exchanged symmetric-traceless conformal multiplet contributes a universal scalar conformal block multiplied by OPE coefficients."
    - "Closed forms are known in important special dimensions, while rapidly convergent radial expansions and recursion relations are the standard general-purpose tools."
  active:
    - "Efficient block generation, rational approximations, spinning generalizations, supersymmetric blocks, and Lorentzian analytic continuations remain important technical infrastructure for modern bootstrap work."
---

## Summary

A **scalar conformal block** is the universal contribution of one exchanged conformal multiplet to a four-point function of scalar primary operators. The word “scalar” refers to the **external operators**, not necessarily to the exchanged operator. The exchanged primary may have spin $\ell$.

For scalar primaries $\mathcal O_i$ of dimensions $\Delta_i$, the $12\to34$ channel expansion of the reduced four-point function is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v).
$$

The CFT chooses the spectrum $\Delta,\ell$ and the OPE coefficients $\lambda_{12\mathcal O}$ and $\lambda_{34\mathcal O}$. Conformal symmetry chooses the function $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)$.

This separation is the reason conformal blocks are useful. Once the block functions have been computed, the dynamical question becomes a problem about which spectra and OPE coefficients can be combined consistently with crossing symmetry, unitarity, and any global-symmetry selection rules.

## Prerequisites

You should know [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/), [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), and [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/).

The page uses Euclidean scalar four-point functions in $d$ dimensions. Spinning external operators, Virasoro blocks, supersymmetric blocks, and Lorentzian inversion are separate topics.

## Core idea

A scalar four-point function has no free Lorentz indices. Once the external dimensions are fixed, all nontrivial coordinate dependence is captured by cross-ratios. Therefore the exchange of a primary with dimension $\Delta$ and spin $\ell$ is described by a single function of two variables.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A scalar conformal block packages the exchanged primary and all descendants into one universal cross-ratio function.](/figures/cft-bootstrap/scalar-conformal-block-data.svg)

<figcaption>

For scalar external primaries, the pair of three-point couplings and the exchanged conformal multiplet determine one scalar conformal block $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)$. The block is kinematic; the OPE coefficients are dynamical CFT data.

</figcaption>
</figure>

The block is not just the primary exchange. Descendants are fixed by conformal symmetry and appear with precise relative coefficients. The block is the sum over the whole multiplet.

A useful mental model is

$$
\text{scalar block}
=
\text{primary of }(\Delta,\ell)
+
\text{all descendants, with conformal-algebra weights}.
$$

## Setup and conventions

Let

$$
\Delta_{ij}\equiv \Delta_i-\Delta_j,
\qquad
x_{ij}=x_i-x_j.
$$

The cross-ratios are

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

It is often useful to introduce complex variables $z,\bar z$ by

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

For Euclidean configurations, $z$ and $\bar z$ are complex conjugates. In a conformal frame where the four points lie in a plane, they can be treated as the two coordinates of that plane. In Lorentzian kinematics, $z$ and $\bar z$ are analytically continued and need not be conjugates.

We write the scalar four-point function as

$$
\begin{aligned}
&\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle
\\
&\quad =
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}{
(x_{12}^2)^{(\Delta_1+\Delta_2)/2}
(x_{34}^2)^{(\Delta_3+\Delta_4)/2}
}
\mathcal G(u,v).
\end{aligned}
$$

The scalar block convention used here is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v),
$$

where $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}$ has unit leading radial behavior as explained below. Many references use $g$ rather than $G$, and some include spin-dependent constants inside the block. The physics is unchanged if the OPE coefficients are rescaled consistently.

## What the labels mean

The label

$$
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)
$$

contains four kinds of data.

| Label | Meaning | Kinematic or dynamical? |
|---|---|---|
| $\Delta$ | Dimension of the exchanged primary | Dynamical spectrum label |
| $\ell$ | Spin of the exchanged symmetric-traceless primary | Dynamical spectrum label |
| $\Delta_{12}$ | Difference of the first pair of external dimensions | External kinematic input |
| $\Delta_{34}$ | Difference of the second pair of external dimensions | External kinematic input |
| $u,v$ | Cross-ratios of the insertion points | Kinematic variables |

The block depends on $\Delta$ and $\ell$, but it is not a new CFT datum. It is the same function in every CFT with the same spacetime dimension and the same external dimension differences.

For identical scalars $\phi$ of dimension $\Delta_\phi$,

$$
\Delta_{12}=\Delta_{34}=0,
$$

and the block is usually written simply as

$$
G_{\Delta,\ell}(u,v).
$$

If $\phi$ is a real identical scalar, Bose symmetry implies that only even-spin primaries appear in the $\phi\times\phi$ OPE.

## OPE limit and normalization

The $12\to34$ OPE limit is

$$
x_1\to x_2,
\qquad
x_3\to x_4.
$$

In cross-ratio language this is roughly $u\to0$ with the angular variable held fixed. The leading term of the block must look like the exchange of a primary with dimension $\Delta$ and spin $\ell$.

A clean way to state the normalization uses radial variables. Define

$$
\rho=\frac{z}{(1+\sqrt{1-z})^2},
\qquad
z=\frac{4\rho}{(1+\rho)^2},
$$

and write

$$
\rho=re^{i\theta},
\qquad
\eta=\cos\theta.
$$

Let

$$
\nu=\frac d2-1,
\qquad
\widehat C_\ell^{(\nu)}(\eta)\equiv
\frac{C_\ell^{(\nu)}(\eta)}{C_\ell^{(\nu)}(1)}
$$

be the Gegenbauer polynomial normalized to $\widehat C_\ell^{(\nu)}(1)=1$. The site convention for scalar blocks is

$$
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(r,\eta)
=
(4r)^\Delta \widehat C_\ell^{(\nu)}(\eta)
+O(r^{\Delta+1}).
$$

This condition fixes the overall scale of the block. If another source uses

$$
G_{\Delta,\ell}^{\text{source}}
=A_{\ell,d}
G_{\Delta,\ell}^{\text{site}},
$$

then the corresponding OPE coefficients must be converted by

$$
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
\longrightarrow
\frac{\lambda_{12\mathcal O}\lambda_{34\mathcal O}}{A_{\ell,d}}.
$$

Only the product of coefficient and block is convention-independent.

## Radial expansion

Radial quantization gives the most transparent expansion. In the symmetric radial frame, two operators create an incoming state on a sphere of radius $r<1$, and the other two operators create an outgoing state on the unit sphere. The exchanged conformal multiplet is graded by the dilatation operator.

The block has an expansion of the form

$$
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(r,\eta)
=
(4r)^\Delta
\sum_{m=0}^{\infty}r^m
\sum_j
B_{m,j}\widehat C_j^{(\nu)}(\eta).
$$

The integer $m$ is the descendant level. At level $m$, the possible spins $j$ come from tensoring the original spin $\ell$ with $m$ derivatives, then removing traces and null descendants if necessary. The leading coefficient is

$$
B_{0,j}=\delta_{j\ell}.
$$

In a unitary theory, radial quantization also explains why the expansion behaves well inside the Euclidean OPE domain: it is a spectral expansion in states ordered by scaling dimension. In numerical bootstrap work, the radial variable $\rho$ is preferred over $z$ because the expansion converges rapidly near the crossing-symmetric point.

## Special cases and closed forms

Closed forms are known in several important cases, but it is better to understand them as gifts, not as the definition of a block.

Define the one-variable function

$$
k_\beta^{a,b}(x)\equiv
x^{\beta/2}
{}_2F_1\left(\frac{\beta-a}{2},\frac{\beta+b}{2};\beta;x\right),
$$

where

$$
a=\Delta_{12},
\qquad
b=\Delta_{34}.
$$

In two dimensions, **global** conformal blocks factorize into holomorphic and antiholomorphic hypergeometric pieces. Schematically,

$$
G_{\Delta,\ell}^{a,b}(z,\bar z)
\propto
k_{\Delta+\ell}^{a,b}(z)
k_{\Delta-\ell}^{a,b}(\bar z)
+
(z\leftrightarrow \bar z),
$$

with a spin- and convention-dependent normalization. These are global $SL(2,\mathbb C)$ blocks, not Virasoro blocks.

In four dimensions, scalar global blocks also have compact Dolan–Osborn expressions in terms of the same $k_\beta$ functions. In odd dimensions such as $d=3$, no comparably simple general closed form is known, and radial or recursion methods are the practical standard.

The lesson is not “blocks are hypergeometric functions.” The lesson is subtler: conformal symmetry turns the sum over descendants into a special function, and the form of that special function depends on dimension, spin, and normalization.

## Identity, scalar, and spin blocks

The identity block is special. With the four-point prefactor chosen above, the identity contribution to an identical-scalar four-point function is

$$
G_{\mathbf 1}(u,v)=1.
$$

It is present only when the two-point contractions allowed by quantum numbers permit it. For a real identical scalar,

$$
\phi\times\phi=\mathbf 1+\varepsilon+T+\cdots,
$$

so the identity block supplies the leading disconnected term in the $12\to34$ channel.

A scalar exchanged primary has $\ell=0$. Its leading angular structure is constant:

$$
G_{\Delta,0}(r,\eta)=(4r)^\Delta+O(r^{\Delta+1}).
$$

A spin-one exchange has a leading angular dependence proportional to $\eta$, and a spin-two exchange has the leading quadrupole angular dependence. For identical scalars, odd-spin blocks do not appear in the $\phi\times\phi$ channel, but they do appear in non-identical scalar OPEs.

## Blocks versus coefficients

The block knows how a multiplet propagates through a four-point function. The OPE coefficient knows how strongly the external operators couple to that multiplet. Confusing these two roles creates many wrong bootstrap equations.

For identical real scalars with unit-normalized two-point functions, the expansion is usually written

$$
\mathcal G(u,v)
=
1+\sum_{\mathcal O\neq\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v).
$$

Reflection positivity implies

$$
\lambda_{\phi\phi\mathcal O}^2\ge0
$$

for operators appearing in the $\phi\times\phi$ OPE of a unitary Euclidean CFT. This positivity is not a statement about the block by itself. It is a statement about the squared OPE coefficient in a positive-norm Hilbert space.

## Crossing in block language

For identical scalars,

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}
\mathcal G(u,v).
$$

Exchanging $x_1\leftrightarrow x_3$ gives crossing:

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

Substituting the block expansion gives

$$
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2
\left[
 v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
-u^{\Delta_\phi}G_{\Delta,\ell}(v,u)
\right]
=0.
$$

This is the prototype of a bootstrap equation. All the theory dependence is in the allowed list of $(\Delta,\ell)$ and the nonnegative coefficients $\lambda_{\phi\phi\mathcal O}^2$. The functions multiplying those coefficients are known once the scalar blocks are known.

## Common pitfalls

**Calling every block scalar.** A scalar conformal block means scalar external operators. The exchanged primary can have spin. Spinning correlators require spinning blocks or differential-operator reductions to scalar seed blocks.

**Forgetting the normalization convention.** A block can be rescaled by a constant. The OPE coefficient must be rescaled inversely. Numerical bootstrap bounds depend on consistent conventions, not on a sacred normalization of $G$.

**Confusing global and Virasoro blocks in two dimensions.** The global block sums descendants under the finite-dimensional global conformal algebra. A Virasoro block sums descendants under the full Virasoro algebra and depends on the central charge $c$.

**Thinking the block is dynamical.** The spectrum and OPE coefficients are dynamical. The block is the symmetry-fixed kernel that tells a given multiplet how to appear in the correlator.

**Ignoring selection rules.** Internal symmetry, parity, permutation symmetry, and conservation laws determine which blocks can appear. The scalar block function does not know these rules unless you impose them in the sum.

## Relations to other pages

[Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/) explains the projector picture behind blocks. [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) derives the differential equation that scalar blocks satisfy. [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) develops the $\rho$ expansion more systematically. [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) turns scalar block decompositions into bootstrap equations.

For two-dimensional theories, [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/) explains why 2D CFT has two different notions of a block. For spinning correlators, see [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/) and the later page [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/).

## Research status

The scalar-block story is conceptually settled. The main definitions, Casimir equation, OPE boundary conditions, shadow subtlety, and radial expansions are standard.

The active part is computational and structural. Large mixed-correlator systems need fast, stable block evaluation. Modern numerical bootstrap work often uses rational approximations to derivatives of blocks at the crossing-symmetric point. Analytic bootstrap work studies block limits: lightcone, Regge, large spin, large dimension, Mellin, and Lorentzian continuations.

A useful slogan is: scalar blocks are no longer mysterious, but they are still infrastructure. Like a good linear algebra routine, they become most important when they disappear into reliable computations.

## Exercises

### Exercise 1: Identity block for identical scalars

For identical scalar primaries $\phi$ with

$$
\langle \phi(x_1)\phi(x_2)\rangle
=
\frac{1}{(x_{12}^2)^{\Delta_\phi}},
$$

show that the identity contribution to

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}
$$

is $\mathcal G_{\mathbf 1}(u,v)=1$.

<details><summary><strong>Solution</strong></summary>

The identity contribution in the $12\to34$ channel comes from contracting $x_1$ with $x_2$ and $x_3$ with $x_4$:

$$
\langle \phi(x_1)\phi(x_2)\rangle
\langle \phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}.
$$

Comparing with the four-point form, the corresponding reduced function is

$$
\mathcal G_{\mathbf 1}(u,v)=1.
$$

Thus, with the usual identical-scalar prefactor, the identity block is the constant block.

</details>

### Exercise 2: Even spins for identical scalars

Explain why only even-spin symmetric-traceless primaries appear in the OPE of two identical real scalar primaries.

<details><summary><strong>Solution</strong></summary>

The OPE $\phi(x_1)\phi(x_2)$ must be symmetric under $x_1\leftrightarrow x_2$. The leading tensor structure for a spin-$\ell$ exchanged primary contains a factor like

$$
(x_{12}^{\mu_1}\cdots x_{12}^{\mu_\ell}-\text{traces})\mathcal O_{\mu_1\cdots\mu_\ell}(x_2).
$$

Under $x_{12}\to -x_{12}$ this factor picks up $(-1)^\ell$. Symmetry of the identical-scalar product therefore requires $(-1)^\ell=1$, so $\ell$ must be even.

</details>

### Exercise 3: Leading radial behavior

Using the normalized radial convention

$$
G_{\Delta,\ell}(r,\eta)
=
(4r)^\Delta \widehat C_\ell^{(d/2-1)}(\eta)+O(r^{\Delta+1}),
$$

write the leading behavior for a scalar exchange and for a spin-one exchange.

<details><summary><strong>Solution</strong></summary>

For $\ell=0$,

$$
\widehat C_0^{(\nu)}(\eta)=1,
$$

so

$$
G_{\Delta,0}(r,\eta)=(4r)^\Delta+O(r^{\Delta+1}).
$$

For $\ell=1$,

$$
C_1^{(\nu)}(\eta)=2\nu\eta,
\qquad
C_1^{(\nu)}(1)=2\nu,
$$

so $\widehat C_1^{(\nu)}(\eta)=\eta$. Therefore

$$
G_{\Delta,1}(r,\eta)=(4r)^\Delta \eta+O(r^{\Delta+1}).
$$

</details>

## References

- Ferrara, Gatto, and Grillo, “Conformal Algebra in Space-Time and Operator Product Expansion,” 1973.
- Dolan and Osborn, “Conformal Four Point Functions and the Operator Product Expansion,” 2001.
- Pappadopulo, Rychkov, Espin, and Rattazzi, “OPE Convergence in Conformal Field Theory,” 2012.
- Hogervorst and Rychkov, “Radial Coordinates for Conformal Blocks,” 2013.
- Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- Poland, Rychkov, and Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” 2019.

## Version history

- **2026-06-27:** First polished draft. Introduced scalar block conventions, leading radial normalization, special cases, crossing role, and common normalization pitfalls.
