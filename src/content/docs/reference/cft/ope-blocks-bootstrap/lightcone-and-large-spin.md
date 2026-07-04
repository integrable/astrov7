---
title: "Lightcone Bootstrap and Large Spin"
description: "Lightcone limits, double-twist families, large-spin perturbation theory, and the first CFT diagnostic of bulk locality."
sidebar:
  order: 4
---

## Goal

The previous page introduced crossing symmetry as associativity of the OPE. This page studies one of its sharpest consequences: the **lightcone bootstrap**.

The basic statement is simple:

$$
\boxed{
\text{identity in one OPE channel}
\quad +\quad
\text{crossing}
\quad\Longrightarrow\quad
\text{large-spin operators in the crossed channel}.
}
$$

For a scalar primary $\phi$, the large-spin operators have dimensions

$$
\Delta_{n,\ell}
=
2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0
\quad
(\ell\to\infty),
$$

so their twists approach

$$
\tau_{n,\ell}
\equiv
\Delta_{n,\ell}-\ell
\longrightarrow
2\Delta_\phi+2n.
$$

These operators are called **double-twist operators** and are denoted

$$
[\phi\phi]_{n,\ell}.
$$

For AdS/CFT, this is a major turning point. In a large-$N$ holographic CFT, double-trace operators $[\mathcal O\mathcal O]_{n,\ell}$ are the boundary description of two-particle states in global AdS. Their anomalous dimensions are binding energies. The large-spin expansion is therefore a CFT way to compute long-distance forces in AdS.

The discussion below is mainly for unitary CFTs in $d>2$ using global conformal symmetry. In $d=2$, Virasoro symmetry reorganizes the story, although the global lightcone logic remains useful.

## Four-point crossing revisited

Let $\phi$ be a real scalar primary of scaling dimension $\Delta_\phi$. Write its four-point function as

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\,\mathcal G(u,v),
$$

where

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

Here $z$ and $\bar z$ are conformal cross-ratio variables. In Euclidean signature they are complex conjugates. In Lorentzian signature they can be varied independently after analytic continuation.

The $12\to34$ OPE gives the conformal block expansion

$$
\mathcal G(u,v)
=
1+
\sum_{\mathcal O\in \phi\times\phi}
P_{\mathcal O}\,G_{\Delta,\ell}(u,v),
\qquad
P_{\mathcal O}=\lambda_{\phi\phi\mathcal O}^2\ge0,
$$

where the identity contribution has been written separately. For identical real scalars in a unitary CFT, positivity of two-point functions gives $P_{\mathcal O}\ge0$.

Exchanging $x_2\leftrightarrow x_4$ gives the crossing equation

$$
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u),
$$

or equivalently

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

In terms of $z,\bar z$,

$$
\mathcal G(z,\bar z)
=
\left(\frac{z\bar z}{(1-z)(1-\bar z)}\right)^{\Delta_\phi}
\mathcal G(1-z,1-\bar z).
$$

The lightcone bootstrap extracts consequences of this equation in singular Lorentzian limits.

## Twist is the lightcone quantum number

For a primary operator of dimension $\Delta$ and spin $\ell$, define its **twist** by

$$
\tau=\Delta-\ell.
$$

Twist controls the lightcone OPE. At small $z$, a scalar conformal block behaves schematically as

$$
G_{\Delta,\ell}(z,\bar z)
\underset{z\to0}{\sim}
 z^{\tau/2}\,k_{\Delta+\ell}(\bar z),
$$

where the collinear block is

$$
k_\beta(\bar z)
=
\bar z^{\beta/2}
{}_2F_1\!\left(\frac{\beta}{2},\frac{\beta}{2};\beta;\bar z\right).
$$

The exact normalization of $G_{\Delta,\ell}$ is conventional. The invariant statement is that the leading power of $z$ is $z^{\tau/2}$. Thus smaller twist means less suppression in the lightcone limit.

The identity operator has

$$
\Delta=0,
\qquad
\ell=0,
\qquad
\tau=0,
$$

so it dominates over all positive-twist operators.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Lightcone bootstrap and large-spin double-twist families](/figures/cft/lightcone-large-spin-bootstrap.svg)

<figcaption>

The lightcone bootstrap compares limits such as $z\to0$ and $1-\bar z\to0$ of the crossing equation. The crossed-channel identity produces a singularity that is reproduced in the direct channel by infinitely many large-spin operators. Their twists approach $2\Delta_\phi+2n$, with anomalous corrections $\gamma_{n,\ell}$ that vanish as $\ell\to\infty$.

</figcaption>
</figure>

## The crossed-channel identity forces large spin

Use crossing in the form

$$
\mathcal G(z,\bar z)
=
\left(\frac{z\bar z}{(1-z)(1-\bar z)}\right)^{\Delta_\phi}
\mathcal G(1-z,1-\bar z).
$$

In the crossed channel, the identity operator contributes

$$
\mathcal G(1-z,1-\bar z)\supset1.
$$

Therefore crossing implies a direct-channel contribution

$$
\mathcal G(z,\bar z)
\supset
\left(\frac{z\bar z}{(1-z)(1-\bar z)}\right)^{\Delta_\phi}.
$$

In the lightcone regime $z\to0$ and $\bar z\to1$, this behaves as

$$
\mathcal G(z,\bar z)
\sim
z^{\Delta_\phi}\,
\frac{\bar z^{\Delta_\phi}}{(1-\bar z)^{\Delta_\phi}}.
$$

This has two consequences.

First, the direct-channel OPE must contain operators whose twists approach

$$
\tau=2\Delta_\phi.
$$

Indeed, a direct-channel block contributes as $z^{\tau/2}$, so matching $z^{\Delta_\phi}$ requires $\tau/2=\Delta_\phi$.

Second, the factor

$$
(1-\bar z)^{-\Delta_\phi}
$$

is a power-law singularity. A finite number of fixed-spin conformal blocks cannot reproduce it. For fixed $\beta$, the collinear block $k_\beta(\bar z)$ has at most a logarithmic singularity as $\bar z\to1$. The power-law singularity arises from summing infinitely many blocks with unbounded spin.

So the crossed-channel identity forces an infinite large-spin tower in the direct channel.

## Double-twist operators

The required operators are called double-twist operators. In weakly coupled or generalized-free language they look like

$$
[\phi\phi]_{n,\ell}
\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
-\text{traces},
\qquad
n=0,1,2,\ldots.
$$

Their generalized-free dimensions are

$$
\Delta^{(0)}_{n,\ell}
=2\Delta_\phi+2n+\ell,
$$

and their generalized-free twists are

$$
\tau^{(0)}_{n,\ell}
=2\Delta_\phi+2n.
$$

In a generic interacting CFT, $[\phi\phi]_{n,\ell}$ is notation for an asymptotic family of primary operators. The operators need not literally be normal-ordered products. The theorem-level statement is

$$
\boxed{
\Delta_{n,\ell}
=2\Delta_\phi+2n+
\ell+
\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0
\quad
(\ell\to\infty).
}
$$

This is one of the deepest universal facts about CFTs in $d>2$: even a strongly coupled CFT has a generalized-free-like high-spin tail in the OPE of two scalar operators.

## Generalized free field as the zeroth-order answer

A generalized free scalar has Wick-like correlators but does not need to come from a local free-field Lagrangian. Its four-point function is

$$
\mathcal G_{\operatorname{GFF}}(u,v)
=
1+u^{\Delta_\phi}
+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

The three terms are the three pairings of four identical operators. This expression is crossing-symmetric and its $\phi\times\phi$ OPE contains double-twist operators with exact dimensions

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+
\ell.
$$

Large-$N$ holographic CFTs start from this structure because single-trace correlators factorize at leading order. But the existence of double-twist families is not a large-$N$ assumption. Large $N$ only makes the generalized-free approximation accurate over a much wider range of the spectrum.

## Minimal twist controls the leading correction

The identity gives the leading double-twist towers. The next correction comes from the lowest-twist non-identity operator exchanged in the crossed channel.

Let $\mathcal O_m$ be the lowest-twist non-identity operator relevant to the channel, with

$$
\tau_m=\Delta_m-\ell_m.
$$

At fixed $n$ and large spin,

$$
\gamma_{n,\ell}
\sim
\frac{1}{J^{\tau_m}},
$$

where $J$ is the conformal spin of the double-twist operator. A useful definition is

$$
J^2
=
\left(\ell+\frac{\tau}{2}\right)
\left(\ell+\frac{\tau}{2}-1\right),
\qquad
J\sim\ell
\quad
(\ell\gg1).
$$

More carefully,

$$
\gamma_{n,\ell}
=
-\frac{a_n(\mathcal O_m)}{J^{\tau_m}}
+\cdots,
$$

in the common identical-scalar setup for positive-norm even-spin exchange, with $a_n(\mathcal O_m)$ determined by the OPE coefficient $\lambda_{\phi\phi\mathcal O_m}$ and by kinematics. The coefficient depends on conventions. The universal part is the power $J^{-\tau_m}$.

The OPE coefficients also receive large-spin corrections:

$$
P_{n,\ell}
=
P^{\operatorname{GFF}}_{n,\ell}
\left(1+\delta P_{n,\ell}\right),
\qquad
\delta P_{n,\ell}\sim J^{-\tau_m},
$$

with possible logarithms when anomalous dimensions are inserted into powers like $z^{\tau/2}$.

This is **large-spin perturbation theory**. It is perturbation theory in $1/J$, not necessarily in a Lagrangian coupling.

## Stress-tensor exchange and gravity

Every local CFT has a stress tensor. In a unitary CFT in $d>2$,

$$
\Delta_T=d,
\qquad
\ell_T=2,
\qquad
\tau_T=d-2.
$$

If stress-tensor exchange is the leading non-identity correction, then

$$
\gamma_{n,\ell}^{(T)}
\sim
-\frac{\kappa_{n,\phi,d}}{C_T}\frac{1}{J^{d-2}},
\qquad
\kappa_{n,\phi,d}>0,
$$

up to normalization conventions for $C_T$ and $T_{\mu\nu}$.

In AdS/CFT, this is the CFT signature of graviton exchange. The negative sign is the boundary avatar of gravitational attraction: the two-particle energy is lowered by a long-range attractive force.

The power is also meaningful. Stress tensor exchange has twist $d-2$, so the correction falls as $J^{-(d-2)}$. This is the CFT version of the long-distance falloff associated with a massless spin-two field in $AdS_{d+1}$.

## Currents, scalars, and other long-range forces

If the CFT has a conserved global current $J_\mu$, then

$$
\Delta_J=d-1,
\qquad
\ell_J=1,
\qquad
\tau_J=d-2.
$$

Current exchange therefore gives the same large-spin power as stress-tensor exchange:

$$
\gamma_{n,\ell}^{(J)}\sim J^{-(d-2)}.
$$

In AdS/CFT, this is the exchange of a bulk gauge field. The sign depends on the charges of the two particles.

If the theory contains a light scalar $\mathcal O$ with

$$
\Delta_{\mathcal O}<d-2,
$$

then scalar exchange dominates over stress-tensor exchange:

$$
\gamma_{n,\ell}^{(\mathcal O)}
\sim
-\frac{a_n(\mathcal O)}{J^{\Delta_{\mathcal O}}}.
$$

Thus the hierarchy of twists in the CFT is the hierarchy of long-range forces in the AdS dual.

## Why large spin means large distance in AdS

In radial quantization, a primary operator creates a state on $S^{d-1}$ with cylinder energy

$$
E_{\rm cyl}=\Delta.
$$

A double-trace operator $[\mathcal O\mathcal O]_{n,\ell}$ creates a two-particle state. At leading large $N$,

$$
\Delta^{(0)}_{n,\ell}
=2\Delta_\mathcal O+2n+
\ell.
$$

The spin $\ell$ is the orbital angular momentum of the two particles. Large angular momentum keeps the particles far apart, so long-distance interactions are weak. The anomalous dimension

$$
\gamma_{n,\ell}
=
\Delta_{n,\ell}-\Delta^{(0)}_{n,\ell}
$$

is the interaction energy. The larger the spin, the larger the separation, and the smaller the binding energy.

This is why

$$
\gamma_{n,\ell}\sim J^{-\tau_m}
$$

is naturally interpreted as a long-distance potential. The lightest exchanged bulk field gives the longest-range force. The CFT phrase for “lightest long-range exchange” is “lowest twist.”

## Large spin is not the same as large $N$

The large-spin theorem is general. It follows from crossing, unitarity, and the identity operator. It does not require large $N$, supersymmetry, a Lagrangian, or a weakly coupled bulk dual.

Large $N$ adds a different expansion. In a large-$N$ CFT, connected correlators of single-trace operators are suppressed:

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}
\sim
\frac{1}{N^2}.
$$

Then double-trace anomalous dimensions are typically small:

$$
\gamma_{n,\ell}=O(1/N^2),
$$

and at large spin they also decay as a power of $1/J$:

$$
\gamma_{n,\ell}
\sim
-\frac{1}{N^2}\frac{a_n}{J^{\tau_m}}
+\cdots.
$$

For holography, the two limits have different meanings:

| CFT limit | Bulk meaning |
|---|---|
| large $N$ | weak bulk coupling, $G_N\ll1$ |
| large gap | local bulk EFT below the string scale |
| large spin | large impact parameter, long-distance forces |

Large spin exists in every unitary CFT. Large $N$ and a large gap are what make it look like weakly coupled local gravity.

## Lorentzian inversion viewpoint

The modern way to make the lightcone bootstrap systematic is the Lorentzian inversion formula. Schematically, it expresses a function of OPE data as an integral over the double discontinuity of a four-point function:

$$
c(\Delta,\ell)
\sim
\int dz\,d\bar z\;\mu(z,\bar z)
G_{\Delta,\ell}(z,\bar z)
\operatorname{dDisc}\mathcal G(z,\bar z).
$$

This formula is schematic: the exact integration region, kernel, and normalization depend on conventions. Its conceptual meaning is robust. Lorentzian singularities determine analytic functions of spin. Poles in $\Delta$ give operator dimensions, and residues give OPE coefficients.

For AdS/CFT this connects three ideas:

$$
\text{crossing symmetry}
\quad\Longleftrightarrow\quad
\text{Lorentzian analyticity}
\quad\Longleftrightarrow\quad
\text{bulk causality and locality}.
$$

We will not need the full inversion formula immediately, but the idea will return when we discuss holographic causality and bulk locality.

## What the lightcone bootstrap does not say

The lightcone bootstrap controls asymptotic large-spin families. It does not determine the full finite-spin spectrum. A large-spin formula should not be blindly extrapolated to $\ell=0$ or $\ell=2$.

It also does not imply that a CFT is holographic. The 3D Ising CFT has large-spin double-twist families, but it is not a weakly coupled theory of gravity in AdS. Holography requires extra structure: large-$N$ factorization, a sparse low-twist spectrum, and a large gap to higher-spin single-trace operators.

Finally, one must account for mixing. In large-$N$ CFTs, many double-trace operators can have the same quantum numbers. The physical anomalous dimensions are eigenvalues of a mixing matrix, not necessarily the shift of one chosen schematic product.

## AdS/CFT checkpoint

The key dictionary is

$$
[\mathcal O\mathcal O]_{n,\ell}
\quad\longleftrightarrow\quad
\text{two-particle state in global AdS},
$$

and

$$
\gamma_{n,\ell}
\quad\longleftrightarrow\quad
\text{binding energy or phase shift}.
$$

The lightcone bootstrap gives the asymptotic form of $\gamma_{n,\ell}$ from crossing symmetry alone. Stress-tensor exchange is graviton exchange. Current exchange is gauge-boson exchange. Light scalar exchange is scalar-force exchange.

This is the first place in the course where CFT crossing symmetry visibly manufactures bulk physics.

## Summary

The chain of ideas is

$$
\text{crossing}
\quad\Rightarrow\quad
\text{identity singularity in crossed channel}
\quad\Rightarrow\quad
\text{large-spin towers}
\quad\Rightarrow\quad
\tau_{n,\ell}\to2\Delta_\phi+2n.
$$

The leading correction is controlled by the lowest non-identity twist:

$$
\mathcal O_m\text{ of twist }\tau_m
\quad\Rightarrow\quad
\gamma_{n,\ell}\sim J^{-\tau_m}.
$$

In holographic CFTs, this becomes the boundary derivation of long-distance bulk interactions.

## Exercises

### Exercise 1. Crossing for identical scalars

Starting from

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v),
$$

show that invariance under $x_2\leftrightarrow x_4$ gives

$$
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u).
$$

<details><summary><strong>Solution</strong></summary>

Under $x_2\leftrightarrow x_4$, the same four-point function can be written as

$$
\frac{1}{x_{14}^{2\Delta_\phi}x_{23}^{2\Delta_\phi}}\mathcal G(v,u),
$$

because the two cross-ratios exchange:

$$
u\leftrightarrow v.
$$

Equating the two representations gives

$$
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v)
=
\frac{1}{x_{14}^{2\Delta_\phi}x_{23}^{2\Delta_\phi}}\mathcal G(v,u).
$$

Using

$$
\frac{x_{12}^2x_{34}^2}{x_{14}^2x_{23}^2}
=
\frac{u}{v},
$$

we obtain

$$
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}\mathcal G(v,u).
$$

</details>

### Exercise 2. Why the crossed identity implies twist $2\Delta_\phi$

Use the crossed-channel identity contribution to show that the direct-channel OPE must contain operators whose twists approach $2\Delta_\phi$.

<details><summary><strong>Solution</strong></summary>

Crossing gives

$$
\mathcal G(z,\bar z)
=
\left(\frac{z\bar z}{(1-z)(1-\bar z)}\right)^{\Delta_\phi}
\mathcal G(1-z,1-\bar z).
$$

The crossed-channel identity gives

$$
\mathcal G(1-z,1-\bar z)\supset1.
$$

Thus

$$
\mathcal G(z,\bar z)
\supset
\left(\frac{z\bar z}{(1-z)(1-\bar z)}\right)^{\Delta_\phi}.
$$

At small $z$ with $\bar z$ fixed, this behaves as

$$
\mathcal G(z,\bar z)\sim z^{\Delta_\phi}F(\bar z).
$$

A direct-channel conformal block behaves as

$$
G_{\Delta,\ell}(z,\bar z)
\sim z^{\tau/2}k_{\Delta+\ell}(\bar z).
$$

Matching powers gives

$$
\frac{\tau}{2}=\Delta_\phi,
\qquad
\tau=2\Delta_\phi.
$$

The singular dependence on $1-\bar z$ then requires infinitely many large-spin operators with this limiting twist.

</details>

### Exercise 3. Double-twist dimensions

Assume generalized-free counting for

$$
[\phi\phi]_{n,\ell}
\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
-\text{traces}.
$$

Compute its dimension and twist.

<details><summary><strong>Solution</strong></summary>

The two scalar fields contribute $2\Delta_\phi$. The $\ell$ symmetric traceless derivatives contribute dimension $\ell$ and spin $\ell$. The $n$ factors of $\partial^2$ contribute dimension $2n$ and no spin. Thus

$$
\Delta^{(0)}_{n,\ell}=2\Delta_\phi+\ell+2n.
$$

The twist is

$$
\tau^{(0)}_{n,\ell}
=
\Delta^{(0)}_{n,\ell}-\ell
=2\Delta_\phi+2n.
$$

</details>

### Exercise 4. Stress-tensor power law

Assume the lowest non-identity crossed-channel operator is the stress tensor in a $d$-dimensional CFT. What is the large-spin power of its contribution to $\gamma_{n,\ell}$?

<details><summary><strong>Solution</strong></summary>

The stress tensor has

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

Therefore

$$
\tau_T=\Delta_T-\ell_T=d-2.
$$

An exchanged operator of twist $\tau_m$ gives a large-spin correction of order

$$
\gamma_{n,\ell}\sim J^{-\tau_m}.
$$

For stress-tensor exchange,

$$
\gamma_{n,\ell}^{(T)}
\sim
-\frac{\kappa_{n,\phi,d}}{C_T}J^{-(d-2)},
$$

up to normalization conventions. For example, in $d=4$ this gives $\gamma_{n,\ell}^{(T)}\sim -J^{-2}$.

</details>

### Exercise 5. Large conformal spin

For a leading double-twist operator with $\tau_{0,\ell}\to2\Delta_\phi$, show that

$$
J^2
\sim
(\ell+\Delta_\phi)(\ell+\Delta_\phi-1).
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
J^2
=
\left(\ell+\frac{\tau}{2}\right)
\left(\ell+\frac{\tau}{2}-1\right).
$$

For the leading double-twist family,

$$
\tau\to2\Delta_\phi.
$$

Substitution gives

$$
J^2
\sim
(\ell+\Delta_\phi)(\ell+\Delta_\phi-1).
$$

At large spin $J\sim\ell$, but $J$ is often the cleaner variable for asymptotic expansions.

</details>

## Further reading

For the original modern lightcone-bootstrap perspective, read Komargodski and Zhiboedov, and Fitzpatrick, Kaplan, Poland, and Simmons-Duffin. For the Lorentzian inversion formula, read Caron-Huot. For holographic applications, compare these ideas with large-$N$ double-trace perturbation theory and tree-level Witten diagrams.
