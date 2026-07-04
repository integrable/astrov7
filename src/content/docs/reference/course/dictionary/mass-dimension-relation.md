---
title: "The Mass-Dimension Relation"
description: "Derive the AdS/CFT relation between the mass of a scalar field in AdS and the scaling dimension of the dual CFT operator."
sidebar:
  order: 40
---

The previous page computed a scalar two-point function from a bulk on-shell action. In that calculation, one fact was used everywhere: the power with which a scalar field approaches the AdS boundary is fixed by its mass. That power becomes the scaling dimension of the dual CFT operator.

For a scalar field in $\mathrm{AdS}_{d+1}$ dual to a scalar primary operator $\mathcal O$ in a $d$-dimensional CFT, the relation is

$$
m^2L^2 = \Delta(\Delta-d).
$$

Equivalently,

$$
\Delta_\pm
=
\frac d2 \pm \nu,
\qquad
\nu
=
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

In standard quantization, the operator dimension is usually

$$
\Delta=\Delta_+=\frac d2+\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

The other root, $\Delta_-$, is not an error. It controls the source falloff in standard quantization and, in a special mass window, can itself become the operator dimension in alternate quantization. The next page is devoted to that subtlety.

<figure class="doc-figure" style="--figure-width: 58rem;">

![The scalar mass-dimension relation from the near-boundary indicial equation in AdS.](/figures/course/mass-dimension-relation.svg)

<figcaption>

A scalar field near the AdS boundary has two independent falloffs. The near-boundary wave equation gives $\alpha(\alpha-d)=m^2L^2$. In standard quantization, the slower falloff $z^{d-\Delta}\phi_{(0)}$ is the source and the faster falloff $z^\Delta A$ is the response, with $m^2L^2=\Delta(\Delta-d)$.

</figcaption>
</figure>

## Why this relation matters

A CFT has no particle masses. Its local operators are labeled by quantum numbers under the conformal group: spin, global charges, and scaling dimension. A gravitational theory in AdS, by contrast, has fields propagating on a curved spacetime. These fields have masses, spins, and interactions.

The mass-dimension relation is the bridge:

$$
\boxed{
\text{bulk scalar mass in AdS units}
\quad
\longleftrightarrow
\quad
\text{CFT scalar operator dimension}
}.
$$

The phrase “in AdS units” matters. The mass $m$ is dimensionful, but $mL$ is dimensionless. Since $\Delta$ is dimensionless, the scalar dictionary must involve $m^2L^2$.

This relation appears whenever we:

- identify supergravity modes with single-trace operators;
- decide whether a boundary deformation is relevant, marginal, or irrelevant;
- compute scalar two-point functions;
- diagnose possible instabilities of an AdS solution;
- impose boundary conditions in analytic or numerical holography;
- build bottom-up holographic models.

A negative $m^2$ does not automatically mean that the AdS background is unstable. The correct lower bound is the Breitenlohner–Freedman bound,

$$
m^2L^2\ge -\frac{d^2}{4},
$$

which follows already from requiring the square root in $\Delta_\pm$ to be real. We will return to this bound carefully on the next page.

## Setup

Use Poincare AdS in $d+1$ bulk dimensions:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+\eta_{ij}dx^i dx^j
\right),
\qquad
z>0.
$$

The conformal boundary is at $z=0$. In Euclidean signature, replace $\eta_{ij}$ by $\delta_{ij}$.

Consider a free scalar field with action

$$
S_\phi
=
\frac12
\int d^{d+1}x\,\sqrt{|g|}
\left(
g^{MN}\partial_M\phi\,\partial_N\phi
+
m^2\phi^2
\right).
$$

The equation of motion is

$$
(\Box_g-m^2)\phi=0.
$$

For the Poincare metric,

$$
\sqrt{|g|}
=
\left(\frac Lz\right)^{d+1},
\qquad
g^{zz}=\frac{z^2}{L^2},
\qquad
g^{ij}=\frac{z^2}{L^2}\eta^{ij}.
$$

Using

$$
\Box_g\phi
=
\frac1{\sqrt{|g|}}
\partial_M
\left(
\sqrt{|g|}g^{MN}\partial_N\phi
\right),
$$

we find

$$
z^2\partial_z^2\phi
-(d-1)z\partial_z\phi
+
z^2\partial_i\partial^i\phi
-
m^2L^2\phi
=
0.
$$

The near-boundary behavior is encoded in this equation.

## The indicial equation

Near $z=0$, the term $z^2\partial_i\partial^i\phi$ is subleading for smooth boundary dependence and finite boundary momentum. The leading radial equation is

$$
z^2\partial_z^2\phi
-(d-1)z\partial_z\phi
-
m^2L^2\phi
\simeq
0.
$$

Try a power-law solution

$$
\phi(z,x)\sim z^\alpha f(x).
$$

Then

$$
z\partial_z\phi=\alpha\phi,
\qquad
z^2\partial_z^2\phi=\alpha(\alpha-1)\phi.
$$

Substituting gives

$$
\alpha(\alpha-1)-(d-1)\alpha-m^2L^2=0.
$$

Therefore

$$
\alpha(\alpha-d)=m^2L^2.
$$

The two roots are

$$
\alpha=\Delta_\pm
=
\frac d2
\pm
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

Thus a scalar field behaves near the boundary as

$$
\phi(z,x)
\sim
z^{\Delta_-}\alpha(x)
+
z^{\Delta_+}\beta(x),
$$

where $\alpha(x)$ and $\beta(x)$ are the two independent asymptotic coefficients.

Since

$$
\Delta_-+\Delta_+=d,
$$

we can write the standard-quantization expansion as

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x),
\qquad
\Delta=\Delta_+.
$$

This gives the central result:

$$
\boxed{
m^2L^2=\Delta(\Delta-d).
}
$$

## Why the exponent is a CFT dimension

The derivation above gives two radial powers. Why should one of them be a CFT scaling dimension?

The reason is that AdS isometries act as conformal transformations at the boundary. In Poincare coordinates, the bulk transformation

$$
x^i\to\Lambda x^i,
\qquad
z\to\Lambda z
$$

leaves the metric invariant. This is the boundary dilatation.

In standard quantization,

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x).
$$

Because $z^{d-\Delta}$ scales as $\Lambda^{d-\Delta}$, the coefficient $\phi_{(0)}$ transforms as a source of dimension

$$
[\phi_{(0)}]=d-\Delta.
$$

The CFT source coupling is

$$
\int d^d x\,\phi_{(0)}(x)\mathcal O(x).
$$

For this term to be dimensionless, $\mathcal O$ must have dimension

$$
[\mathcal O]=\Delta.
$$

Thus the radial falloff has become the CFT scaling law.

The lesson is

$$
\boxed{
\text{radial falloff in AdS}
\quad
\longrightarrow
\quad
\text{scale transformation on the boundary}
\quad
\longrightarrow
\quad
\text{operator dimension}.
}
$$

## Source and response in standard quantization

For most scalar calculations in this course, we use standard quantization:

$$
\Delta=\Delta_+,
\qquad
\Delta_-=d-\Delta.
$$

Then

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}(x)+\cdots
\right)
+
z^\Delta
\left(
A(x)+\cdots
\right).
$$

The dictionary is

$$
\boxed{
\phi_{(0)}(x)
=
\text{source for }\mathcal O(x),
\qquad
A(x)
=
\text{response data}.
}
$$

More precisely, after holographic renormalization,

$$
\langle\mathcal O(x)\rangle
=
\text{constant}\times A(x)
+
\text{local terms in }\phi_{(0)}.
$$

The local terms depend on counterterm choices and are responsible for contact terms in correlators. The nonlocal part of the response is fixed by the bulk solution.

## Momentum-space solution

The same exponents appear in the exact Euclidean momentum-space solution. Fourier transform along the boundary:

$$
\phi(z,x)
=
\int\frac{d^d k}{(2\pi)^d}
e^{ik\cdot x}
\phi_k(z).
$$

The radial equation becomes

$$
z^2\phi_k''
-
(d-1)z\phi_k'
-
(k^2z^2+m^2L^2)\phi_k
=
0.
$$

The solution regular in the Euclidean interior is

$$
\phi_k(z)
=
z^{d/2}K_\nu(kz),
\qquad
\nu
=
\sqrt{\frac{d^2}{4}+m^2L^2},
$$

up to normalization. Near $z=0$,

$$
z^{d/2}K_\nu(kz)
\sim
c_-(k)z^{d/2-\nu}
+
c_+(k)z^{d/2+\nu}
+
\cdots.
$$

Thus the full regular solution contains the same two powers,

$$
\Delta_-=\frac d2-\nu,
\qquad
\Delta_+=\frac d2+\nu.
$$

When the regular solution is inserted into the renormalized on-shell action, the nonlocal momentum-space two-point function scales as

$$
\langle\mathcal O(k)\mathcal O(-k)\rangle
\propto
k^{2\nu}.
$$

Fourier transformation gives

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
\propto
\frac{1}{|x|^{d+2\nu}}
=
\frac{1}{|x|^{2\Delta_+}}.
$$

This is exactly the conformal two-point function for a scalar primary of dimension $\Delta_+$.

## Global AdS interpretation

There is another useful way to see the formula. In global AdS, the boundary is the cylinder

$$
\mathbb R_t\times S^{d-1}.
$$

The CFT Hamiltonian on this cylinder is the dilatation operator. A primary operator of dimension $\Delta$ creates a cylinder state of energy

$$
EL=\Delta.
$$

A scalar field in global AdS has normal-mode frequencies

$$
\omega_{n,\ell}L
=
\Delta+2n+\ell,
\qquad
n=0,1,2,\ldots,
\qquad
\ell=0,1,2,\ldots.
$$

The lowest normal mode has

$$
\omega_0L=\Delta.
$$

So the mass-dimension relation can also be read as

$$
\boxed{
\text{lowest global AdS energy}
=
\text{CFT scaling dimension of the primary}.
}
$$

Boundary derivatives acting on the primary create descendants. In the bulk, these correspond to higher global normal modes with extra energy $2n+\ell$.

## Examples

### Massless scalar

If $m^2=0$, then

$$
\Delta(\Delta-d)=0.
$$

The roots are

$$
\Delta_+=d,
\qquad
\Delta_-=0.
$$

In standard quantization, a massless scalar is dual to a marginal scalar operator of dimension $d$. In the canonical $\mathrm{AdS}_5/\mathrm{CFT}_4$ example, the dilaton couples to the Yang–Mills Lagrangian density, an operator of dimension $4$.

### Scalar in $\mathrm{AdS}_5$

For $d=4$,

$$
m^2L^2=\Delta(\Delta-4).
$$

If

$$
m^2L^2=-4,
$$

then

$$
\Delta=2.
$$

This saturates the BF bound in $\mathrm{AdS}_5$.

If

$$
m^2L^2=-3,
$$

then

$$
\Delta_+=3,
\qquad
\Delta_-=1.
$$

The $\Delta_-=1$ root sits at the scalar unitarity bound in four dimensions, so it is an endpoint case requiring care.

### Scalar in $\mathrm{AdS}_4$

For $d=3$,

$$
m^2L^2=\Delta(\Delta-3).
$$

If

$$
m^2L^2=-2,
$$

then

$$
\Delta_+=2,
\qquad
\Delta_-=1.
$$

Both choices are allowed in the alternate-quantization window. This example appears frequently in $\mathrm{AdS}_4/\mathrm{CFT}_3$ and in holographic condensed-matter models.

## Relevant, marginal, and irrelevant operators

In a $d$-dimensional CFT, a scalar deformation by $\mathcal O$ is

$$
\delta S
=
\int d^d x\,J\mathcal O.
$$

The classification is

$$
\begin{array}{ccl}
\Delta<d &:& \text{relevant},\\
\Delta=d &:& \text{marginal},\\
\Delta>d &:& \text{irrelevant}.
\end{array}
$$

Using standard quantization,

$$
m^2L^2=\Delta(\Delta-d).
$$

Therefore:

- marginal scalar operators with $\Delta=d$ correspond to $m^2=0$;
- relevant scalar operators with $d/2<\Delta<d$ correspond to negative $m^2$ above the BF bound;
- irrelevant scalar operators with $\Delta>d$ correspond to positive $m^2$.

This is an excellent sanity check when building holographic models. Choosing a scalar mass is choosing the UV dimension of the dual operator.

## The BF bound preview

The square root

$$
\nu=\sqrt{\frac{d^2}{4}+m^2L^2}
$$

is real only if

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

This is the Breitenlohner–Freedman bound. At the bound,

$$
\nu=0,
\qquad
\Delta_+=\Delta_-=\frac d2.
$$

Below the bound,

$$
\Delta=\frac d2\pm i\gamma,
\qquad
\gamma>0,
$$

so the CFT dimensions would be complex. On the bulk side, the AdS background is unstable to this scalar mode. The next page explains the BF bound and alternate quantization more carefully.

## What about spin?

The scalar relation is the simplest because the Klein–Gordon equation is second order and has two visible radial falloffs. Other fields obey analogous but different relations.

A massless bulk gauge field is dual to a conserved current,

$$
\Delta(J^\mu)=d-1.
$$

The bulk metric is dual to the stress tensor,

$$
\Delta(T_{\mu\nu})=d.
$$

A spinor in AdS obeys a first-order equation and has a relation of the rough form

$$
\Delta=\frac d2+|m|L,
$$

with its own boundary-condition subtleties. The scalar case is the correct first laboratory because it displays sources, responses, the BF bound, and alternate quantization in their cleanest form.

## Dictionary checkpoint

For a scalar field in $\mathrm{AdS}_{d+1}$,

$$
(\Box-m^2)\phi=0
$$

implies

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}(x)+\cdots
\right)
+
z^\Delta
\left(
A(x)+\cdots
\right),
$$

where

$$
\boxed{
m^2L^2=\Delta(\Delta-d).
}
$$

In standard quantization,

$$
\boxed{
\Delta=\Delta_+,
\qquad
\phi_{(0)}(x)=\text{source for }\mathcal O(x),
\qquad
A(x)\sim\text{vev data}.
}
$$

The exact vev is obtained by varying the renormalized on-shell action, not by reading off $A$ blindly.

## Common confusions

### “Negative $m^2$ means the bulk is unstable.”

Not in AdS. A scalar is stable if it obeys

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

Negative mass squared often corresponds to a relevant scalar operator.

### “The two roots are two different particles.”

No. They are two asymptotic behaviors of the same bulk field. In standard quantization, one is the source falloff and the other is the response falloff. In a special window, one may choose alternate quantization.

### “The faster-falling coefficient is automatically the vev.”

It is related to the vev, but holographic renormalization is needed. Local counterterms can contribute contact terms and scheme-dependent pieces.

### “The relation depends on Poincare coordinates.”

No. Poincare coordinates make the derivation short. Global AdS gives the same $\Delta$ as the lowest normal-mode energy.

### “A massless scalar is dual to the identity operator.”

No. In standard quantization, a massless scalar has $\Delta=d$. The $\Delta_-=0$ root is the source falloff, not the identity operator.

## Exercises

### Exercise 1: Derive the indicial equation

Starting from

$$
z^2\partial_z^2\phi
-
(d-1)z\partial_z\phi
-
m^2L^2\phi
=
0,
$$

insert $\phi=z^\alpha$ and derive the indicial equation.

<details>
<summary><strong>Solution</strong></summary>

For $\phi=z^\alpha$,

$$
\partial_z\phi=\alpha z^{\alpha-1},
\qquad
\partial_z^2\phi=\alpha(\alpha-1)z^{\alpha-2}.
$$

Thus

$$
z^2\partial_z^2\phi
-
(d-1)z\partial_z\phi
-
m^2L^2\phi
=
\left[
\alpha(\alpha-1)
-
(d-1)\alpha
-
m^2L^2
\right]z^\alpha.
$$

The coefficient must vanish, so

$$
\alpha(\alpha-d)=m^2L^2.
$$

</details>

### Exercise 2: A scalar in $\mathrm{AdS}_5$

For a scalar in $\mathrm{AdS}_5$ with $m^2L^2=-3$, find the two possible exponents.

<details>
<summary><strong>Solution</strong></summary>

For $\mathrm{AdS}_5$, the boundary dimension is $d=4$. The equation is

$$
\Delta(\Delta-4)=-3.
$$

Thus

$$
\Delta^2-4\Delta+3=0,
$$

so

$$
(\Delta-1)(\Delta-3)=0.
$$

The roots are

$$
\Delta_-=1,
\qquad
\Delta_+=3.
$$

</details>

### Exercise 3: Relevant operators and negative mass squared

Show that for $d/2<\Delta<d$, standard quantization gives a negative bulk $m^2$ that still obeys the BF bound.

<details>
<summary><strong>Solution</strong></summary>

The mass is

$$
m^2L^2=\Delta(\Delta-d).
$$

If $d/2<\Delta<d$, then $\Delta>0$ and $\Delta-d<0$, so $m^2<0$.

Rewrite the relation as

$$
m^2L^2
=
\left(
\Delta-\frac d2
\right)^2
-
\frac{d^2}{4}.
$$

The square is nonnegative, so

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

</details>

### Exercise 4: Source dimension

Show that the source coupled to an operator of dimension $\Delta$ through

$$
\int d^d x\,J(x)\mathcal O(x)
$$

has dimension $d-\Delta$.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless. The measure $d^d x$ has mass dimension $-d$, and $\mathcal O$ has dimension $\Delta$. Therefore

$$
[J]+\Delta-d=0,
$$

so

$$
[J]=d-\Delta.
$$

This matches the standard bulk expansion, where the source multiplies $z^{d-\Delta}$.

</details>

## Further reading

- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT$_d$/AdS$_{d+1}$ Correspondence](https://arxiv.org/abs/hep-th/9804058).
- I. R. Klebanov and E. Witten, [AdS/CFT Correspondence and Symmetry Breaking](https://arxiv.org/abs/hep-th/9905104).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
