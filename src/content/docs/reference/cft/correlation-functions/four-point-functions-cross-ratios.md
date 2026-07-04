---
title: "Four-Point Functions and Cross-Ratios"
description: "The first dynamical CFT correlators, conformal cross-ratios, crossing channels, and the holographic meaning of four-point data."
sidebar:
  order: 3
---

Two- and three-point functions teach us the kinematics of conformal symmetry. Four-point functions are where conformal field theory becomes genuinely dynamical.

For scalar primaries, conformal symmetry fixes the two-point function up to normalizations and the three-point function up to OPE coefficients. But for four operators, conformal symmetry leaves a nontrivial function of two variables. That function is not a nuisance. It is the first place where the full interacting content of the CFT appears.

For AdS/CFT, this is a crucial transition:

$$
\boxed{
\text{two-point data} \leftrightarrow \text{bulk spectrum and kinetic terms},
\qquad
\text{three-point data} \leftrightarrow \text{bulk cubic couplings},
}
$$

while

$$
\boxed{
\text{four-point functions}
\leftrightarrow
\text{bulk exchange diagrams, contact interactions, loops, and locality constraints}.
}
$$

So this page is not merely about introducing $u$ and $v$. It is about learning the language in which crossing symmetry, OPE associativity, conformal blocks, Witten diagrams, and eventually bulk locality all speak to each other.

## The first nontrivial correlator

Let $\mathcal O_i(x_i)$ be scalar primary operators in a Euclidean CFT on $\mathbb R^d$. We write

$$
x_{ij}^2=(x_i-x_j)^2.
$$

The two-point and three-point functions are highly constrained:

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\rangle
=
\frac{C_{12}\delta_{\Delta_1,\Delta_2}}{(x_{12}^2)^{\Delta_1}},
$$

and

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)
\rangle
=
\frac{C_{123}}
{(x_{12}^2)^{\frac{\Delta_1+\Delta_2-\Delta_3}{2}}
 (x_{23}^2)^{\frac{\Delta_2+\Delta_3-\Delta_1}{2}}
 (x_{31}^2)^{\frac{\Delta_3+\Delta_1-\Delta_2}{2}}}.
$$

The constants $C_{12}$ and $C_{123}$ are CFT data after a choice of normalization. No arbitrary function appears.

For four points, the situation changes. There are conformally invariant combinations of the positions, so conformal symmetry cannot determine the full answer. Schematically,

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle
=
\text{fixed powers of }x_{ij}^2
\times
\text{an arbitrary function of cross-ratios}.
$$

That arbitrary function contains infinitely many pieces of CFT data. Its singular limits encode OPEs. Its consistency under permutations gives crossing equations. Its large-$N$ structure tells us whether the theory can look like weakly coupled gravity in AdS.

## Why only cross-ratios can remain

A conformal transformation is a composition of translations, rotations, dilatations, and special conformal transformations. Translation invariance says a correlator can depend only on differences $x_i-x_j$. Rotation invariance says scalar correlators can depend only on squared distances $x_{ij}^2$. Scale invariance then says only dimensionless ratios of these distances may survive after extracting the required powers.

Special conformal transformations are the final constraint. Under

$$
x^\mu
\mapsto
x^{\prime\mu}
=
\frac{x^\mu-b^\mu x^2}{1-2b\cdot x+b^2x^2},
$$

one finds

$$
\boxed{
{x_{ij}^{\prime}}^2
=
\frac{x_{ij}^2}{\sigma_i\sigma_j},
\qquad
\sigma_i=1-2b\cdot x_i+b^2x_i^2.
}
$$

Therefore the following two quantities are invariant:

$$
\boxed{
 u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
 v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
}
$$

The factors of $\sigma_i$ cancel between numerator and denominator. These are the standard conformal cross-ratios.

For four generic points in $d\geq 2$, there are two independent conformal invariants. In two dimensions, it is often more natural to use one complex cross-ratio $z$ and its antiholomorphic partner $\bar z$. In higher-dimensional Euclidean CFTs, one can also introduce $z,\bar z$ by

$$
\boxed{
 u=z\bar z,
\qquad
 v=(1-z)(1-\bar z).
}
$$

For Euclidean configurations, $z$ and $\bar z$ are complex conjugates when the four points lie in a real two-plane. After Lorentzian continuation, they should be treated as independent variables living on different analytic sheets.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![Four-point cross-ratios and OPE channels](/figures/cft/four-point-cross-ratios-channels.svg)

<figcaption>

Four scalar insertions have two independent conformal cross-ratios, $u$ and $v$. Different OPE limits organize the same four-point function into different channels: $(12)(34)$, $(14)(23)$, and $(13)(24)$. Crossing symmetry says that these decompositions describe the same correlator.

</figcaption>
</figure>

## The general scalar four-point function

Let

$$
\Delta_{ij}=\Delta_i-\Delta_j.
$$

A convenient conformally covariant form for four scalar primaries is

$$
\boxed{
\begin{aligned}
&\left\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\mathcal O_3(x_3)\mathcal O_4(x_4)
\right\rangle
\\[4pt]
&\quad =
\frac{1}
{(x_{12}^2)^{\frac{\Delta_1+\Delta_2}{2}}
 (x_{34}^2)^{\frac{\Delta_3+\Delta_4}{2}}}
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\frac{\Delta_{12}}{2}}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\frac{\Delta_{34}}{2}}
\mathcal G(u,v).
\end{aligned}
}
$$

The prefactor is conventional. It is chosen so that all nontrivial dependence is packaged into a dimensionless function $\mathcal G(u,v)$. Other prefactors are equally valid, but they move simple powers of $u$ and $v$ between the prefactor and the reduced correlator.

For identical scalar primaries $\phi$ of dimension $\Delta$, the formula simplifies to

$$
\boxed{
\left\langle
\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)
\right\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2x_{34}^2)^\Delta}.
}
$$

This is the most important normalization for first contact with the conformal bootstrap.

The identity operator contribution in the $12\to 34$ channel is then simply

$$
\mathcal G(u,v)=1+\cdots,
\qquad
u\to 0,
\quad
v\to 1.
$$

Here the dots are contributions from nontrivial operators in the $\phi\times\phi$ OPE.

## Conformal frames

Cross-ratios become more transparent in a conformal frame. The conformal group can move four generic points into a two-dimensional plane and then fix three of them. A standard choice is

$$
x_1\to 0,
\qquad
x_3\to 1,
\qquad
x_4\to \infty,
\qquad
x_2\to z.
$$

Then the two cross-ratios become

$$
\boxed{
 u=z\bar z,
\qquad
 v=(1-z)(1-\bar z).
}
$$

This frame is extremely useful, but it hides some symmetry. The four original points are all on equal footing. Choosing a conformal frame is like fixing a gauge: it is convenient, but the final answer must be expressible in terms of invariant data.

The main OPE limits are:

$$
\begin{array}{ccl}
\text{$s$ channel: } x_1\to x_2 &\Longleftrightarrow& u\to 0,\quad v\to 1,\quad z,\bar z\to 0,\\[4pt]
\text{$t$ channel: } x_2\to x_3 &\Longleftrightarrow& v\to 0,\quad u\to 1,\quad z,\bar z\to 1,\\[4pt]
\text{$u$ channel: } x_1\to x_3 &\Longleftrightarrow& z,\bar z\to \infty\quad \text{after a suitable frame choice.}
\end{array}
$$

The names $s,t,u$ are borrowed from scattering theory. In a CFT, the channels are not scattering channels in flat spacetime, but the analogy is powerful: each channel corresponds to grouping the four operators into two OPE pairs.

## Crossing symmetry

For identical scalar operators, the four-point function must be invariant under permutations of the insertions. This gives functional equations for $\mathcal G(u,v)$.

Using

$$
\left\langle
\phi_1\phi_2\phi_3\phi_4
\right\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2x_{34}^2)^\Delta},
$$

exchange $x_1\leftrightarrow x_3$. The cross-ratios transform as

$$
(u,v)\mapsto (v,u).
$$

The prefactor changes, and equality of the correlator gives

$$
\boxed{
\mathcal G(u,v)
=
\left(\frac{u}{v}\right)^\Delta
\mathcal G(v,u).
}
$$

Another useful permutation is $x_1\leftrightarrow x_2$, under which

$$
(u,v)
\mapsto
\left(\frac{u}{v},\frac1v\right),
$$

and for a bosonic identical scalar one obtains

$$
\boxed{
\mathcal G(u,v)=\mathcal G\left(\frac{u}{v},\frac1v\right).
}
$$

These equations are simple to write and hard to solve. Their meaning is deep: the OPE must be associative.

In the $s$ channel one expands the product $\phi(x_1)\phi(x_2)$ and separately $\phi(x_3)\phi(x_4)$. In the $t$ channel one instead expands $\phi(x_2)\phi(x_3)$ and $\phi(x_1)\phi(x_4)$. Both procedures compute the same function. Crossing symmetry is the equality of these two expansions.

This is the conceptual heart of the conformal bootstrap.

## OPE interpretation

The OPE of two identical scalars has the schematic form

$$
\phi(x_1)\phi(x_2)
\sim
\sum_{\mathcal O}
\lambda_{\phi\phi\mathcal O}
C_{\mathcal O}(x_{12},\partial_{x_2})
\mathcal O(x_2),
$$

where the sum runs over primary operators and their descendants. Plugging this OPE into the four-point function gives an expansion of $\mathcal G(u,v)$.

For identical scalars in a unitary CFT, the schematic conformal block expansion is

$$
\boxed{
\mathcal G(u,v)
=
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta_{\mathcal O},\ell_{\mathcal O}}(u,v).
}
$$

The functions $G_{\Delta,\ell}(u,v)$ are conformal blocks. They are fixed by symmetry and encode the contribution of one primary operator together with all of its descendants. The coefficients $\lambda_{\phi\phi\mathcal O}^2$ are nonnegative in a reflection-positive Euclidean CFT when $\phi$ is real and the operators are normalized appropriately.

The identity operator contributes

$$
G_{0,0}(u,v)=1.
$$

A scalar primary of dimension $\Delta_{\mathcal O}$ begins at small $u$ roughly as

$$
G_{\Delta_{\mathcal O},0}(u,v)
\sim
u^{\Delta_{\mathcal O}/2}
\times
\text{a function of }v,
\qquad
u\to 0,
$$

while a spin-$\ell$ primary carries angular dependence controlled by $SO(d)$ representation theory.

We will study conformal blocks systematically later. For now, the point is this:

$$
\boxed{
\text{the four-point function is a generating function for the spectrum and OPE coefficients.}
}
$$

The crossing equation becomes a nontrivial constraint on those data:

$$
\sum_{\mathcal O\in s\text{-channel}}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v)
=
\left(\frac{u}{v}\right)^\Delta
\sum_{\mathcal O\in t\text{-channel}}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(v,u).
$$

For identical scalars, the set of exchanged operators is the same on both sides, but the functions are evaluated in different channels.

## Generalized free fields

A very important benchmark is a generalized free field. Let $\phi$ be a scalar operator with unit-normalized two-point function

$$
\langle \phi(x)\phi(0)\rangle=\frac1{(x^2)^\Delta}.
$$

A generalized free field has Wick-like factorization of higher-point functions, even though it need not come from a free local Lagrangian. Its four-point function is

$$
\langle
\phi_1\phi_2\phi_3\phi_4
\rangle_{\mathrm{GFF}}
=
\frac1{(x_{12}^2x_{34}^2)^\Delta}
+
\frac1{(x_{13}^2x_{24}^2)^\Delta}
+
\frac1{(x_{14}^2x_{23}^2)^\Delta}.
$$

Therefore, in our reduced normalization,

$$
\boxed{
\mathcal G_{\mathrm{GFF}}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
}
$$

This formula is one of the fastest ways to see why generalized free fields are central to holography. In a large-$N$ CFT, single-trace operators often behave at leading order like generalized free fields:

$$
\mathcal G(u,v)
=
\mathcal G_{\mathrm{GFF}}(u,v)
+
\frac1{N^p}\mathcal G_{\mathrm{conn}}(u,v)
+
\cdots.
$$

The disconnected terms describe free propagation of noninteracting bulk particles. The connected term is where bulk interactions begin. In a semiclassical AdS dual, $\mathcal G_{\mathrm{conn}}$ is computed by tree-level Witten diagrams: exchange diagrams plus contact diagrams.

## Large-$N$ interpretation

Suppose $\mathcal O$ is a single-trace scalar primary in a large-$N$ CFT, normalized so that

$$
\langle \mathcal O(x)\mathcal O(0)\rangle\sim N^0.
$$

Large-$N$ factorization says

$$
\langle
\mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4
\rangle
=
\langle\mathcal O_1\mathcal O_2\rangle
\langle\mathcal O_3\mathcal O_4\rangle
+
\langle\mathcal O_1\mathcal O_3\rangle
\langle\mathcal O_2\mathcal O_4\rangle
+
\langle\mathcal O_1\mathcal O_4\rangle
\langle\mathcal O_2\mathcal O_3\rangle
+
\langle\mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_{\mathrm{conn}}.
$$

Usually

$$
\langle\mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\mathrm{conn}}
\ll
\langle\mathcal O\mathcal O\rangle\langle\mathcal O\mathcal O\rangle
$$

at large $N$. The leading disconnected answer is generalized free. The first correction encodes anomalous dimensions and OPE coefficients of double-trace operators

$$
[\mathcal O\mathcal O]_{n,\ell}
\sim
\mathcal O\,\partial^{2n}\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}\mathcal O
-
\text{traces},
$$

with approximate dimensions

$$
\Delta_{n,\ell}^{(0)}=2\Delta+2n+\ell.
$$

Interactions shift these dimensions:

$$
\Delta_{n,\ell}
=
2\Delta+2n+\ell+\frac1{N^p}\gamma_{n,\ell}+\cdots.
$$

In AdS, these double-trace operators are two-particle states. Their anomalous dimensions are boundary measurements of bulk interactions.

## Singular limits and physics

The most important information in a four-point function often appears in its singular limits.

### OPE limit

The $s$-channel OPE limit is

$$
x_1\to x_2,
\qquad
u\to 0,
\qquad
v\to 1.
$$

This limit reveals which operators appear in $\phi\times\phi$. Operators of smaller dimension dominate. For example, the identity contribution gives $1$, while a scalar primary $\mathcal O$ of dimension $\Delta_{\mathcal O}$ contributes at order $u^{\Delta_{\mathcal O}/2}$.

### Lightcone limit

In Lorentzian signature, one can take one cross-ratio small while keeping the other fixed or small in a different way. A basic lightcone limit is

$$
u\to 0,
\qquad
u \ll 1-v \ll 1.
$$

Such limits are the entry point to the lightcone bootstrap. They imply the existence of large-spin double-twist operators and are closely related to the emergence of locality in AdS.

### Regge and chaos limits

After analytic continuation around branch points in $z,\bar z$, one obtains Lorentzian Regge limits. These limits probe high-energy bulk scattering in AdS and are constrained by causality and chaos bounds. The same Euclidean function $\mathcal G(u,v)$ therefore contains much more than Euclidean geometry: its analytic continuation knows about Lorentzian dynamics.

## AdS/CFT checkpoint

Four-point functions are the natural meeting point of CFT bootstrap and AdS dynamics.

A tree-level AdS four-point function has two broad types of contributions:

$$
\boxed{
\text{contact Witten diagram}
\quad\Longleftrightarrow\quad
\text{local bulk quartic interaction},
}
$$

and

$$
\boxed{
\text{exchange Witten diagram}
\quad\Longleftrightarrow\quad
\text{bulk field exchanged between two pairs of boundary insertions}.
}
$$

On the CFT side, the same answer must admit an OPE expansion in every channel. Thus a single AdS diagram is not merely a Feynman-like object; it must be compatible with conformal block decompositions and crossing symmetry.

The dictionary is:

$$
\begin{array}{ccl}
\text{single-trace exchange} &\leftrightarrow& \text{single-particle bulk field},\\[3pt]
\text{double-trace tower} &\leftrightarrow& \text{two-particle bulk states},\\[3pt]
\text{anomalous dimensions }\gamma_{n,\ell} &\leftrightarrow& \text{bulk interactions},\\[3pt]
\text{crossing symmetry} &\leftrightarrow& \text{consistent factorization of the same bulk process},\\[3pt]
\text{large-spin behavior} &\leftrightarrow& \text{bulk locality and long-distance propagation}.
\end{array}
$$

This is why four-point functions are a central object in modern holography. A CFT with a sparse large-$N$ spectrum and appropriately behaved four-point functions can look like a local gravitational theory in AdS. A CFT whose four-point functions violate the expected analyticity, positivity, or large-spin constraints cannot.

## Common conventions

There are several common notational choices. They are all equivalent, but mixing them carelessly causes many wrong factors.

One convention uses $x_{ij}=|x_i-x_j|$ and writes powers of $x_{ij}$ directly. This page uses $x_{ij}^2$ and therefore many exponents include factors of $1/2$.

Another convention defines

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^\Delta}
\mathcal G(u,v),
$$

while another defines a symmetrized object $\mathcal F(u,v)$ by extracting additional powers of $u$ and $v$. The crossing equation changes form under this redefinition, but the physical content is unchanged.

In two-dimensional CFT, one often writes

$$
\langle
\phi_1(z_1,\bar z_1)\cdots\phi_4(z_4,\bar z_4)
\rangle
=
\text{fixed powers}
\times
\mathcal F(z,\bar z),
$$

where

$$
z=\frac{z_{12}z_{34}}{z_{13}z_{24}},
\qquad
\bar z=\frac{\bar z_{12}\bar z_{34}}{\bar z_{13}\bar z_{24}}.
$$

For a 2D CFT, $z$ and $\bar z$ are especially powerful because the global conformal group factorizes into holomorphic and antiholomorphic pieces, and the local conformal symmetry enhances this further to Virasoro symmetry.

## Summary

The four-point function is the first CFT correlator with an undetermined function:

$$
\boxed{
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\text{kinematic prefactor}\times \mathcal G(u,v).
}
$$

The two cross-ratios are

$$
\boxed{
 u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
 v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
}
$$

The OPE decomposes $\mathcal G(u,v)$ into conformal blocks. Crossing symmetry equates different decompositions. In large-$N$ holographic CFTs, the disconnected part is generalized free, while the connected part encodes bulk interactions.

So the real lesson is:

$$
\boxed{
\text{Four-point functions are where CFT data becomes dynamical geometry.}
}
$$

## Exercises

### Exercise 1. Invariance of $u$ and $v$

Use

$$
{x_{ij}^{\prime}}^2
=
\frac{x_{ij}^2}{\sigma_i\sigma_j}
$$

under a special conformal transformation to show that

$$
 u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
 v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}
$$

are invariant.

<details><summary><strong>Solution</strong></summary>

Under the transformation,

$$
{x_{12}^{\prime}}^2{x_{34}^{\prime}}^2
=
\frac{x_{12}^2x_{34}^2}{\sigma_1\sigma_2\sigma_3\sigma_4},
$$

and

$$
{x_{13}^{\prime}}^2{x_{24}^{\prime}}^2
=
\frac{x_{13}^2x_{24}^2}{\sigma_1\sigma_3\sigma_2\sigma_4}.
$$

The same product $\sigma_1\sigma_2\sigma_3\sigma_4$ appears in numerator and denominator, so it cancels:

$$
u'
=
\frac{{x_{12}^{\prime}}^2{x_{34}^{\prime}}^2}{{x_{13}^{\prime}}^2{x_{24}^{\prime}}^2}
=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}
=u.
$$

The same calculation gives

$$
v'
=
\frac{{x_{14}^{\prime}}^2{x_{23}^{\prime}}^2}{{x_{13}^{\prime}}^2{x_{24}^{\prime}}^2}
=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}
=v.
$$

Thus $u$ and $v$ are conformal invariants.

</details>

### Exercise 2. Crossing under $x_1\leftrightarrow x_3$

For an identical scalar $\phi$ of dimension $\Delta$, define

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2x_{34}^2)^\Delta}.
$$

Show that exchanging $x_1$ and $x_3$ gives

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^\Delta\mathcal G(v,u).
$$

<details><summary><strong>Solution</strong></summary>

Under $x_1\leftrightarrow x_3$, the cross-ratios exchange:

$$
(u,v)\mapsto (v,u).
$$

The correlator can therefore also be written as

$$
\langle\phi_3\phi_2\phi_1\phi_4\rangle
=
\frac{\mathcal G(v,u)}{(x_{32}^2x_{14}^2)^\Delta}
=
\frac{\mathcal G(v,u)}{(x_{23}^2x_{14}^2)^\Delta}.
$$

Since the fields are identical bosonic scalars, the correlator is unchanged by the permutation. Therefore

$$
\frac{\mathcal G(u,v)}{(x_{12}^2x_{34}^2)^\Delta}
=
\frac{\mathcal G(v,u)}{(x_{23}^2x_{14}^2)^\Delta}.
$$

Multiplying by $(x_{12}^2x_{34}^2)^\Delta$ gives

$$
\mathcal G(u,v)
=
\left(
\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}
\right)^\Delta
\mathcal G(v,u).
$$

But

$$
\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}
=
\frac{u}{v}.
$$

Hence

$$
\mathcal G(u,v)=\left(\frac{u}{v}\right)^\Delta\mathcal G(v,u).
$$

</details>

### Exercise 3. Generalized free four-point function

Assume

$$
\langle\phi(x)\phi(0)\rangle=\frac1{(x^2)^\Delta}
$$

and Wick-like factorization. Show that

$$
\mathcal G_{\mathrm{GFF}}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

<details><summary><strong>Solution</strong></summary>

Wick-like factorization gives three pairings:

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=
\frac1{(x_{12}^2)^\Delta(x_{34}^2)^\Delta}
+
\frac1{(x_{13}^2)^\Delta(x_{24}^2)^\Delta}
+
\frac1{(x_{14}^2)^\Delta(x_{23}^2)^\Delta}.
$$

Factor out $(x_{12}^2x_{34}^2)^{-\Delta}$:

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=
\frac1{(x_{12}^2x_{34}^2)^\Delta}
\left[
1+
\left(\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}\right)^\Delta
+
\left(\frac{x_{12}^2x_{34}^2}{x_{14}^2x_{23}^2}\right)^\Delta
\right].
$$

The second term is $u^\Delta$. For the third term,

$$
\frac{x_{12}^2x_{34}^2}{x_{14}^2x_{23}^2}
=
\frac{u}{v}.
$$

Thus

$$
\mathcal G_{\mathrm{GFF}}(u,v)
=
1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

</details>

### Exercise 4. Cross-ratios in the conformal frame

In the conformal frame

$$
x_1=0,
\qquad
x_2=z,
\qquad
x_3=1,
\qquad
x_4=\infty,
$$

show that

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

<details><summary><strong>Solution</strong></summary>

Treat the point at infinity by taking $x_4=R$ and sending $R\to\infty$. In complex notation,

$$
x_{12}^2=|z|^2=z\bar z,
\qquad
x_{13}^2=1,
$$

and for large $R$,

$$
x_{34}^2\sim R^2,
\qquad
x_{24}^2\sim R^2.
$$

Therefore

$$
u
=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}
\to
z\bar z.
$$

Similarly,

$$
x_{23}^2=|z-1|^2=(1-z)(1-\bar z),
\qquad
x_{14}^2\sim R^2,
$$

while

$$
x_{13}^2=1,
\qquad
x_{24}^2\sim R^2.
$$

Thus

$$
v
=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}
\to
(1-z)(1-\bar z).
$$

</details>
