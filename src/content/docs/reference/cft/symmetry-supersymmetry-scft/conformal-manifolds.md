---
title: "Exactly Marginal Deformations and Conformal Manifolds"
description: "Conformal manifolds, marginal operators, beta functions, Zamolodchikov metrics, and the AdS/CFT meaning of exactly marginal couplings."
sidebar:
  order: 4
---

## Goal

The previous pages introduced global symmetries, superconformal algebras, and BPS shortening. This page explains how a CFT can move continuously while remaining a CFT.

The central object is a **conformal manifold**: a family of CFTs connected by exactly marginal deformations. For AdS/CFT this is not a decorative topic. It is the boundary description of bulk moduli, massless scalar fields, S-duality identifications, and protected versus unprotected data as functions of coupling.

The practical slogan is:

$$
\boxed{
\text{exactly marginal scalar primary }\mathcal O_i\text{ with }\Delta_i=d
\quad\Longleftrightarrow\quad
\text{tangent direction on }\mathcal M_{\rm CFT}
}
$$

but the word “exactly” carries all the weight. A scalar operator of dimension $d$ is only **marginal at first order**. It is exactly marginal only if turning on its coupling does not generate a beta function.

## Marginal, relevant, irrelevant, exactly marginal

Let $\mathcal C$ be a Euclidean CFT in $d$ dimensions. Deform its action by scalar local operators:

$$
S \longrightarrow S_\lambda
= S + \sum_i \lambda^i \mu^{d-\Delta_i}\int d^d x\,\mathcal O_i(x).
$$

Here $\mu$ is a reference RG scale inserted so that $\lambda^i$ is dimensionless. At the undeformed CFT, the operator $\mathcal O_i$ has scaling dimension $\Delta_i$. The first-order classification is:

| Type of deformation | Condition at the CFT | First-order RG behavior |
|---|---:|---|
| Relevant | $\Delta_i<d$ | grows in the IR |
| Irrelevant | $\Delta_i>d$ | dies in the IR |
| Marginal | $\Delta_i=d$ | undecided at first order |
| Exactly marginal | $\Delta_i=d$ and $\beta^i=0$ along a finite-dimensional locus | stays conformal |

The dangerous case is the marginal one. A marginal operator can be marginally relevant, marginally irrelevant, or exactly marginal. The distinction is invisible from the engineering dimension alone.

Near a fixed point, the beta functions have the schematic form

$$
\beta^k(\lambda)
\equiv \frac{d\lambda^k}{d\log\mu}
= (d-\Delta_k)\lambda^k
-\frac{1}{2}S_{d-1}C_{ij}{}^k\lambda^i\lambda^j
+O(\lambda^3),
$$

where

$$
S_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}
$$

is the area of the unit $(d-1)$-sphere, and $C_{ij}{}^k$ appears in the OPE

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\frac{C_{ij}{}^k}{|x|^{\Delta_i+\Delta_j-\Delta_k}}\mathcal O_k(0)+\cdots.
$$

The precise sign and normalization of the quadratic term depend on conventions for the Euclidean action, operator normalization, and coupling normalization. The important invariant statement is that OPE singularities of marginal operators can produce logarithmic divergences in integrated correlation functions, and those logarithms become beta functions.

For marginal operators, $\Delta_i=d$. If $\mathcal O_i$ and $\mathcal O_j$ have an OPE term proportional to another marginal operator $\mathcal O_k$, the integral

$$
\int_{|x|<\epsilon} d^d x\,\frac{1}{|x|^d}
= S_{d-1}\log \epsilon + \text{finite}
$$

is logarithmically divergent. That logarithm is the first obstruction to exact marginality.

## Definition of a conformal manifold

A conformal manifold $\mathcal M_{\rm CFT}$ is a space whose points are CFTs, modulo equivalences such as field redefinitions and dualities. Locally, one may use coordinates $\lambda^i$, so that each nearby CFT has correlation functions

$$
\langle \mathcal O_{A_1}(x_1)\cdots \mathcal O_{A_n}(x_n)\rangle_\lambda.
$$

The defining condition is

$$
\beta^i(\lambda)=0
$$

for all couplings tangent to $\mathcal M_{\rm CFT}$. The tangent space at a point $p$ is represented by integrated insertions of exactly marginal scalar primaries:

$$
T_p\mathcal M_{\rm CFT}
\simeq
\left\{
\mathcal O_i\,\middle|\,
\Delta_i=d,\quad \ell_i=0,\quad \mathcal O_i\text{ not redundant},\quad \beta^i=0
\right\}.
$$

The phrase “not redundant” is important. Some deformations correspond to changes of variables or to total derivatives. A deformation by a redundant operator can move us through different descriptions of the same CFT rather than to a genuinely new CFT.

The CFT data vary over the conformal manifold:

$$
\mathcal C_\lambda:
\qquad
\left\{
\Delta_A(\lambda),\ \ell_A,\ C_{ABC}(\lambda),\ \text{global symmetry data}
\right\}.
$$

Protected data may remain constant; unprotected data usually vary. In $\mathcal N=4$ SYM, for example, dimensions of half-BPS operators are protected, while dimensions of long single-trace operators generally depend on the 't Hooft coupling.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 55rem;">

![Conformal manifolds and AdS moduli](/figures/cft/conformal-manifold-moduli.svg)

<figcaption>

A conformal manifold $\mathcal M_{\rm CFT}$ is a locus of vanishing beta functions. Tangent directions are exactly marginal scalar operators $\mathcal O_i$ with $\Delta_i=d$; normal directions generally have nonzero beta functions. In AdS/CFT, these tangent directions correspond to massless bulk scalars whose boundary values are CFT couplings.

</figcaption>
</figure>

## Conformal perturbation theory

The most direct way to understand conformal manifolds is to perturb correlation functions. Let

$$
S_\lambda = S + \lambda^i\int d^d x\,\mathcal O_i(x).
$$

Then, formally,

$$
\partial_i
\langle \mathcal X\rangle_\lambda
=
-\int d^d x\,
\langle \mathcal O_i(x)\mathcal X\rangle_\lambda
+\text{contact counterterms},
$$

where $\mathcal X$ is a product of separated local operators. The integral is usually UV divergent near the insertion points of $\mathcal X$ and near coincident insertions in higher derivatives. Renormalization removes these divergences, but the finite answer can depend on contact-term conventions.

At second order,

$$
\frac{1}{2}\lambda^i\lambda^j
\int d^d x\,d^d y\,
\langle \mathcal O_i(x)\mathcal O_j(y)\mathcal X\rangle
$$

contains the dangerous region $x\to y$. If the OPE has a marginal term

$$
\mathcal O_i(x)\mathcal O_j(y)
\supset
\frac{C_{ij}{}^k}{|x-y|^d}\mathcal O_k(y),
$$

then the integral contains

$$
\frac{1}{2}\lambda^i\lambda^j C_{ij}{}^k
\int d^d y\,\mathcal O_k(y)
\int_{|x-y|<\epsilon}\frac{d^d x}{|x-y|^d}.
$$

The inner integral is logarithmic. Absorbing it into a redefinition of $\lambda^k$ produces a beta function. Thus, a clean first test for exact marginality is:

$$
\boxed{
\text{marginal operators must not generate marginal beta functions under their OPEs.}
}
$$

This condition is not the full story. Higher orders can still obstruct exact marginality. Supersymmetry often makes the higher-order problem tractable.

## The Zamolodchikov metric

The conformal manifold has a natural metric, defined by two-point functions of exactly marginal operators. For scalar marginal operators in $d$ dimensions,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle_\lambda
=\frac{G_{ij}(\lambda)}{|x|^{2d}}.
$$

The coefficient $G_{ij}(\lambda)$ is the **Zamolodchikov metric**. In a unitary Euclidean CFT it is positive definite on non-redundant exactly marginal directions:

$$
G_{ij}v^iv^j>0
$$

for any nonzero tangent vector $v^i$.

The metric is physical, but its local expression depends on the choice of coordinates $\lambda^i$. Under a change of exactly marginal coordinates,

$$
\lambda^i\longrightarrow \lambda^{\prime a}(\lambda),
$$

it transforms as an ordinary tensor:

$$
G'_{ab}(\lambda')
=\frac{\partial\lambda^i}{\partial\lambda^{\prime a}}
\frac{\partial\lambda^j}{\partial\lambda^{\prime b}}
G_{ij}(\lambda).
$$

There can also be global identifications. A conformal manifold is often not simply a smooth patch of $\mathbb R^n$ or $\mathbb C^n$; it may be a quotient by a duality group and may have singular loci where extra operators become conserved or extra degrees of freedom become light.

## What is held fixed along a conformal manifold?

Moving along $\mathcal M_{\rm CFT}$ preserves conformal symmetry, but it does not preserve every piece of CFT data.

The following structures are typically stable under a smooth exactly marginal deformation:

| Quantity | Behavior along $\mathcal M_{\rm CFT}$ |
|---|---|
| Spacetime dimension $d$ | fixed |
| Conformal algebra $\mathfrak{so}(d,2)$ | fixed |
| Stress tensor multiplet | persists |
| Exactly marginal operators | span tangent directions, may mix |
| Global symmetry | may be preserved, reduced, enhanced, or realized differently at special loci |
| Operator dimensions $\Delta_A$ | generally vary unless protected |
| OPE coefficients $C_{ABC}$ | generally vary |
| Central charges/anomaly coefficients | often constrained; in many supersymmetric cases protected |

This is a subtle point for AdS/CFT. Moving along a conformal manifold is not the same as flowing under RG. It is not that the CFT changes scale by scale. Rather, the entire theory is changed while remaining scale invariant at every point.

A useful distinction is:

$$
\begin{array}{ccl}
\text{RG flow} &:& \beta^i\neq0,\quad \mu\frac{d\lambda^i}{d\mu}\neq0,\\[4pt]
\text{conformal manifold} &:& \beta^i=0,\quad \lambda^i\text{ labels different fixed points.}
\end{array}
$$

## Examples

### The compact boson in two dimensions

The simplest exactly marginal family is the compact free boson CFT. Let

$$
X\sim X+2\pi R.
$$

Changing the radius $R$ changes the spectrum of momentum and winding operators, but the theory remains conformal. The exactly marginal operator is schematically

$$
\mathcal O_R(z,\bar z)=\partial X\bar\partial X,
$$

with conformal weights

$$
(h,\bar h)=(1,1),
\qquad
\Delta=2.
$$

Thus $\partial X\bar\partial X$ is marginal in $d=2$. In fact it is exactly marginal, and the conformal manifold is the radius line with the T-duality identification

$$
R\sim \frac{\alpha'}{R}
$$

up to conventions for $\alpha'$.

This example is pedagogically useful because it shows that moving on a conformal manifold can change the spectrum without breaking conformal invariance.

### Four-dimensional $\mathcal N=4$ SYM

The canonical AdS/CFT example has an exactly marginal complex coupling

$$
\tau=\frac{\theta}{2\pi}+\frac{4\pi i}{g_{\rm YM}^2}.
$$

The local conformal manifold is the upper half-plane parameterized by $\tau$. Globally, one must quotient by S-duality:

$$
\tau\sim \frac{a\tau+b}{c\tau+d},
\qquad
\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in SL(2,\mathbb Z).
$$

In the AdS dual, $\tau$ is identified with the boundary value of the type IIB axio-dilaton. The exactly marginal deformation is in the same supermultiplet as protected operators. The theory remains conformal for all values of $\tau$, but the anomalous dimensions of unprotected operators vary with $\lambda=g_{\rm YM}^2N$.

### Four-dimensional $\mathcal N=1$ SCFTs

In $4d$ $\mathcal N=1$ theories, exactly marginal deformations can arise from gauge couplings and superpotential terms. A superpotential deformation

$$
\delta W = h^a\mathcal O_a
$$

is classically marginal if the chiral operator $\mathcal O_a$ has R-charge $2$, equivalently dimension $3$ in a superconformal theory:

$$
\Delta(\mathcal O_a)=\frac{3}{2}R(\mathcal O_a)=3.
$$

Not every such coupling is exactly marginal. Global symmetries impose moment-map-like constraints, and couplings related by complexified global symmetry transformations can describe equivalent theories. A useful schematic statement is

$$
\mathcal M_{\rm CFT}
\sim
\frac{\{\text{marginal supersymmetric couplings satisfying }\beta=0\}}{G_{\mathbb C}}.
$$

This quotient structure is one reason conformal manifolds in supersymmetric theories are geometrically rich.

### Non-examples

A coupling can be classically marginal and still fail to define a conformal manifold. For example, suppose near $g=0$,

$$
\beta_g=b g^2+O(g^3).
$$

Then $g=0$ is a fixed point, but $g\neq0$ runs unless $b=0$ and the higher terms cooperate. The direction is marginally relevant or marginally irrelevant depending on the sign of $b$ and on the RG direction.

This is why “dimension $d$” is a necessary condition for exact marginality, not a sufficient one.

## Supersymmetry and protection

Supersymmetry is the main mechanism that makes conformal manifolds controllable in interacting CFTs. The logic is simple but powerful:

1. BPS shortening protects certain operator dimensions.
2. Marginal supersymmetric deformations are often descendants of protected primaries.
3. Holomorphy and R-symmetry constrain beta functions.
4. Multiplet recombination tells us when a candidate marginal operator becomes marginally irrelevant.

For example, in a superconformal theory, an exactly marginal deformation must preserve the superconformal algebra under discussion. This usually means the deformation is not an arbitrary scalar primary of dimension $d$, but a supersymmetric descendant whose integrated insertion is compatible with the preserved supercharges.

A useful diagnostic is recombination. A candidate marginal operator may fail to be exactly marginal because it pairs with a conserved current multiplet when a global symmetry is broken. The corresponding current is no longer conserved, and the would-be marginal deformation becomes part of a long multiplet. In this case the apparent marginal direction is lifted.

This explains why global symmetries are not merely decorative: they can remove naive marginal directions from the true conformal manifold.

## Conformal manifold versus moduli space of vacua

These two ideas are often confused, especially in supersymmetric theories.

A **conformal manifold** is a space of theories:

$$
\lambda^i\in\mathcal M_{\rm CFT}
\quad\Rightarrow\quad
\mathcal C_{\lambda^i}\text{ is a CFT.}
$$

A **moduli space of vacua** is a space of states within one theory:

$$
\langle \mathcal O\rangle \neq0
$$

for some scalar operator. In a CFT, a nonzero vacuum expectation value of an operator with positive dimension usually introduces a scale and therefore spontaneously breaks conformal invariance.

Thus:

$$
\boxed{
\text{conformal manifold: change the CFT couplings;}
\qquad
\text{moduli space of vacua: change the vacuum.}
}
$$

Both can appear in the same supersymmetric model, but they are conceptually different.

## AdS/CFT checkpoint

For a scalar operator in a $d$-dimensional CFT, the standard AdS/CFT mass-dimension relation is

$$
 m^2R^2=\Delta(\Delta-d).
$$

If $\mathcal O_i$ is exactly marginal, then

$$
\Delta_i=d,
$$

so

$$
 m_i^2R^2=d(d-d)=0.
$$

Therefore:

$$
\boxed{
\text{exactly marginal CFT operator}
\quad\Longleftrightarrow\quad
\text{massless scalar modulus in }\mathrm{AdS}_{d+1}.
}
$$

The source for $\mathcal O_i$ is the boundary value of the bulk scalar:

$$
\phi^i_{\partial}=\lambda^i.
$$

Moving along the conformal manifold means changing the asymptotic value of a massless scalar while preserving the existence of an AdS vacuum. This is different from exciting a normalizable mode of the scalar, which would correspond to changing the state rather than the theory.

The Zamolodchikov metric is also visible in the bulk. If the low-energy bulk action contains

$$
S_{\rm bulk}\supset
-\frac{1}{2\kappa^2}
\int d^{d+1}x\sqrt{g}\,
G^{\rm bulk}_{ij}(\phi)\,
\partial_M\phi^i\partial^M\phi^j,
$$

then the boundary two-point function of the marginal operators determines the metric on the scalar moduli space, up to the usual AdS/CFT normalization factors. Schematically,

$$
G^{\rm Zam}_{ij}(\lambda)
\longleftrightarrow
G^{\rm bulk}_{ij}(\phi_{\partial}=\lambda).
$$

This is why conformal manifolds are not just CFT bookkeeping. They are the boundary avatar of bulk moduli spaces of AdS vacua.

## Dualities and global structure

A conformal manifold is rarely just the naive coupling space. Two values of the apparent coupling may define the same CFT:

$$
\lambda\sim \gamma\cdot \lambda,
\qquad \gamma\in\Gamma_{\rm duality}.
$$

Thus the true conformal manifold is often a quotient:

$$
\mathcal M_{\rm CFT}
=\mathcal M_{\rm local}/\Gamma_{\rm duality}.
$$

Examples include T-duality for compact bosons and S-duality for $\mathcal N=4$ SYM. At fixed points of the duality group, the CFT may have enhanced discrete or continuous symmetry. At singular loci, new light degrees of freedom or enhanced conserved currents can appear.

From the CFT side, these phenomena show up as special behavior of CFT data:

$$
\Delta_A(\lambda),\quad C_{ABC}(\lambda),\quad G_{ij}(\lambda).
$$

From the AdS side, they show up as special loci in the moduli space of AdS vacua.

## Common mistakes

The first common mistake is to say “$\Delta=d$, therefore exactly marginal.” The correct statement is:

$$
\Delta=d
\quad\Rightarrow\quad
\text{marginal at first order only.}
$$

Exact marginality requires vanishing beta functions to all orders.

The second common mistake is to identify a coupling with a vev. In AdS/CFT, the distinction is source versus response:

$$
\phi(z,x)\sim z^{d-\Delta}\lambda(x)+z^\Delta\langle\mathcal O(x)\rangle+\cdots.
$$

For $\Delta=d$, the source is the leading $z^0$ mode, up to possible logarithmic subtleties. Changing the source changes the CFT; changing the normalizable mode changes the state.

The third common mistake is to ignore quotienting. The same local Lagrangian parameters can describe physically identical CFTs because of duality or because of global symmetry transformations acting on couplings.

## Minimal dictionary

| CFT concept | AdS concept |
|---|---|
| Exactly marginal operator $\mathcal O_i$ with $\Delta_i=d$ | Massless scalar field $\phi^i$ |
| Coupling $\lambda^i$ | Boundary value $\phi^i_\partial$ |
| Conformal manifold $\mathcal M_{\rm CFT}$ | Moduli space of AdS vacua |
| Zamolodchikov metric $G_{ij}$ | Bulk scalar kinetic metric |
| Duality quotient | Large gauge/string duality identification |
| Protected operator data | Short multiplet / KK protected data |
| Varying anomalous dimensions | Interaction-dependent bulk masses/energies |

## Exercises

### Exercise 1 — Integrated insertions

Let

$$
S_\lambda=S+\lambda\int d^d x\,\mathcal O(x).
$$

Show formally that

$$
\frac{\partial}{\partial\lambda}\langle \mathcal X\rangle_\lambda
=-\int d^d x\,
\langle \mathcal O(x)\mathcal X\rangle_\lambda
+\langle \mathcal X\rangle_\lambda\int d^d x\,\langle \mathcal O(x)\rangle_\lambda,
$$

where $\mathcal X$ is a product of local operators. Explain why the second term usually vanishes in a CFT on flat space when $\mathcal O$ has nonzero dimension and no source.

<details><summary><strong>Solution</strong></summary>

Write

$$
\langle\mathcal X\rangle_\lambda
=\frac{1}{Z_\lambda}
\int[D\Phi]\,\mathcal X\,e^{-S_\lambda}.
$$

Differentiating gives two terms: one from the numerator and one from $Z_\lambda$:

$$
\partial_\lambda\langle\mathcal X\rangle_\lambda
=
-\left\langle \mathcal X\int d^d x\,\mathcal O(x)\right\rangle_\lambda
+\langle\mathcal X\rangle_\lambda
\left\langle\int d^d x\,\mathcal O(x)\right\rangle_\lambda.
$$

This is the desired formula. In a flat-space CFT without sources, one-point functions of non-identity scalar primaries vanish by translation and scale invariance, so $\langle\mathcal O(x)\rangle=0$ unless $\mathcal O$ is the identity or there are contact/anomaly subtleties.

</details>

### Exercise 2 — The logarithm behind the beta function

Suppose $\mathcal O_i$ and $\mathcal O_j$ are marginal scalar operators in $d$ dimensions and their OPE contains

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{C_{ij}{}^k}{|x|^d}\mathcal O_k(0),
$$

where $\mathcal O_k$ is also marginal. Show that the second-order perturbation produces a logarithmic UV divergence proportional to $C_{ij}{}^k\int d^d y\,\mathcal O_k(y)$.

<details><summary><strong>Solution</strong></summary>

The relevant second-order term is

$$
\frac{1}{2}\lambda^i\lambda^j
\int d^d x\,d^d y\,\mathcal O_i(x)\mathcal O_j(y).
$$

In the region $x\to y$, use the OPE:

$$
\mathcal O_i(x)\mathcal O_j(y)
\supset
\frac{C_{ij}{}^k}{|x-y|^d}\mathcal O_k(y).
$$

Then the divergent part is

$$
\frac{1}{2}\lambda^i\lambda^j C_{ij}{}^k
\int d^d y\,\mathcal O_k(y)
\int_{a<|r|<\epsilon}\frac{d^d r}{|r|^d}.
$$

Using spherical coordinates,

$$
\int_{a<|r|<\epsilon}\frac{d^d r}{|r|^d}
=S_{d-1}\int_a^\epsilon\frac{dr}{r}
=S_{d-1}\log\frac{\epsilon}{a}.
$$

The logarithmic dependence on the UV cutoff $a$ is the signal of coupling renormalization and hence of a beta function for $\lambda^k$.

</details>

### Exercise 3 — Exactly marginal means massless in AdS

Use

$$
 m^2R^2=\Delta(\Delta-d)
$$

to show that an exactly marginal operator is dual to a massless scalar in $\mathrm{AdS}_{d+1}$. Why do we use $\Delta=d$ rather than $\Delta=0$?

<details><summary><strong>Solution</strong></summary>

For an exactly marginal operator, $\Delta=d$. Therefore

$$
 m^2R^2=d(d-d)=0.
$$

The quadratic equation $m^2R^2=\Delta(\Delta-d)$ also has the root $\Delta=0$ when $m^2=0$. That root corresponds to the identity-like or alternate behavior, not to a nontrivial local marginal scalar operator in the standard quantization. A deformation of the CFT action by a local scalar operator requires an operator of dimension $d$ so that

$$
\int d^d x\,\lambda\mathcal O(x)
$$

is dimensionless with dimensionless $\lambda$.

</details>

### Exercise 4 — Compact boson radius deformation

For a free compact boson in two dimensions, take $X=X_L(z)+X_R(\bar z)$. Show that

$$
\mathcal O_R=\partial X\bar\partial X
$$

has conformal weights $(1,1)$. Explain why this is the correct dimension for a marginal deformation in $d=2$.

<details><summary><strong>Solution</strong></summary>

In the free boson CFT, $\partial X$ is holomorphic with weights $(1,0)$, while $\bar\partial X$ is antiholomorphic with weights $(0,1)$. Therefore their product has

$$
(h,\bar h)=(1,0)+(0,1)=(1,1).
$$

The scaling dimension is

$$
\Delta=h+\bar h=2.
$$

Since the spacetime dimension of the CFT is $d=2$, the integrated deformation

$$
\delta S=\lambda\int d^2x\,\partial X\bar\partial X
$$

has dimensionless coupling. This is the first-order criterion for marginality. In the compact boson, the deformation is exactly marginal and changes the radius $R$.

</details>

## Takeaway

A conformal manifold is the space of continuous CFTs obtained by exactly marginal deformations. Its tangent vectors are scalar primaries of dimension $d$ whose integrated insertions do not generate beta functions. Its metric is read from two-point functions of these marginal operators. In holography, the same structure is seen as a moduli space of AdS vacua parameterized by boundary values of massless bulk scalars.
