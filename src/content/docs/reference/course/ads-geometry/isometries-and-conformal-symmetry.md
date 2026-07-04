---
title: "Isometries and Conformal Symmetry"
description: "Why the isometry group of AdS is the conformal group of the boundary CFT, and how bulk Killing vectors become boundary translations, Lorentz transformations, dilatations, and special conformal transformations."
sidebar:
  order: 50
---

The first serious test of any proposed holographic dictionary is symmetry. Before we compute a correlator, before we discuss D-branes, and before we solve a bulk wave equation, the two sides must at least agree on their kinematics.

For AdS/CFT the match is beautiful:

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1}) \simeq SO(2,d),
$$

while the global conformal group of $d$-dimensional Lorentzian flat space is also $SO(2,d)$, up to standard global and discrete quotients.

This page explains why this is true and why it matters. The result is not merely a group-theory curiosity. It is the reason that a scalar mass in AdS can be related to a scaling dimension in the CFT, that global AdS time is related to the CFT Hamiltonian on the cylinder, and that the radial coordinate of AdS knows about scale transformations in the boundary theory.

<figure class="doc-figure" style="--figure-width: 56rem;">

![AdS isometries and boundary conformal symmetry](/figures/course/ads-isometries-conformal-symmetry.svg)

<figcaption>

The same group $SO(2,d)$ appears as the isometry group of $\mathrm{AdS}_{d+1}$ and as the global conformal group of the $d$-dimensional boundary theory. The bulk action on the AdS hyperboloid induces conformal transformations on the projective light cone that represents the boundary.

</figcaption>
</figure>

## Why this matters

AdS/CFT is often introduced by the slogan

$$
\text{gravity in the bulk}
\quad\longleftrightarrow\quad
\text{field theory on the boundary}.
$$

But the slogan hides a sharp constraint: the spacetime symmetries of the bulk must be realized as spacetime symmetries of the boundary theory.

In flat-space holography this would already be difficult. In AdS it is possible because the geometry has exactly the right symmetry group. The $d+1$ bulk dimensions of AdS do not lead to the Poincaré group in $d+1$ dimensions. Instead, the constant negative curvature and the timelike conformal boundary organize the isometries into $SO(2,d)$, precisely the group of conformal transformations of the $d$-dimensional boundary.

This symmetry match explains several later dictionary entries:

| Bulk statement | Boundary statement |
|---|---|
| AdS isometry group $SO(2,d)$ | global conformal group $SO(2,d)$ |
| global AdS time translation | Hamiltonian on $\mathbb R\times S^{d-1}$ |
| radial scaling in Poincaré AdS | boundary dilatation |
| bulk field representation | conformal multiplet of boundary operators |
| bulk energy of a normal mode | scaling dimension of a CFT state/operator |

Symmetry does not prove the full duality. Many theories can share the same symmetry group. But without this match, the duality would fail immediately.

## Setup: AdS as a hyperboloid

Use the embedding-space definition from [AdS as a Spacetime](/course/ads-geometry/ads-as-a-spacetime/). Let $\mathbb R^{2,d}$ have coordinates $X^A$, with

$$
A=-1,0,1,\ldots,d,
$$

and metric

$$
X\cdot X
=
-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2.
$$

Then $\mathrm{AdS}_{d+1}$ is the hyperboloid

$$
X\cdot X=-L^2.
$$

Any linear transformation preserving the ambient quadratic form maps this hyperboloid to itself. Thus the isometry group of the hyperboloid is essentially $O(2,d)$. Usually, when discussing the connected symmetry group relevant for local physics, one writes

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})_0 = SO_0(2,d),
$$

where the subscript means the identity component. In quantum theories with spinors, the actual group acting on states is often the double cover $\mathrm{Spin}(2,d)$. In most AdS/CFT formulas, however, writing $SO(2,d)$ is the harmless shorthand.

The infinitesimal generators are the ambient rotations and boosts

$$
M_{AB}
=
X_A\frac{\partial}{\partial X^B}
-
X_B\frac{\partial}{\partial X^A}.
$$

They preserve $X\cdot X$ because they are antisymmetric with respect to the ambient metric. They obey the Lie algebra

$$
[M_{AB},M_{CD}]
=
\eta_{BC}M_{AD}
-
\eta_{AC}M_{BD}
-
\eta_{BD}M_{AC}
+
\eta_{AD}M_{BC},
$$

which is the Lie algebra $\mathfrak{so}(2,d)$.

The number of generators is

$$
\dim SO(2,d)
=
\frac{(d+2)(d+1)}{2}.
$$

This number will soon reappear from the boundary conformal group.

## The boundary as a projective light cone

The conformal boundary of AdS can be described elegantly using the same embedding space. Instead of the timelike hyperboloid

$$
X\cdot X=-L^2,
$$

consider the null cone

$$
P\cdot P=0.
$$

A point on the conformal boundary is not a particular null vector $P^A$, but a null ray:

$$
P^A \sim \lambda P^A,
\qquad
\lambda\neq 0.
$$

This quotient is called the projective null cone.

Why does this describe a conformal boundary rather than an ordinary boundary metric? Because rescaling the representative $P^A$ rescales the induced metric. The geometry is therefore not a single metric $g_{(0)}$, but a conformal class

$$
[g_{(0)}]
=
\{\Omega^2 g_{(0)}\}.
$$

This is exactly what we found geometrically in [The Conformal Boundary](/course/ads-geometry/conformal-boundary/).

Now the key point is immediate. The group $SO(2,d)$ preserves the ambient product $P\cdot P$, so it maps null vectors to null vectors. It also respects the identification $P\sim \lambda P$. Therefore it acts naturally on the projective null cone. Since the boundary metric is defined only up to Weyl rescaling, this action is conformal rather than ordinary isometric.

This gives the cleanest conceptual derivation:

$$
\boxed{
\text{bulk AdS isometries}
\quad\Longrightarrow\quad
\text{boundary conformal transformations}
}
$$

The same group acts linearly in embedding space, as isometries on the AdS hyperboloid, and as conformal transformations on the boundary.

## A useful boundary gauge

To make the preceding construction more concrete, introduce light-cone coordinates in embedding space,

$$
P^+,
\qquad
P^-,
\qquad
P^\mu,
$$

with ambient quadratic form

$$
P\cdot P=-P^+P^-+\eta_{\mu\nu}P^\mu P^\nu.
$$

On the projective cone, choose the representative

$$
P^+=1.
$$

Then the null condition gives

$$
P^-=x^2,
\qquad
P^\mu=x^\mu,
$$

where

$$
x^2=\eta_{\mu\nu}x^\mu x^\nu.
$$

Thus a boundary point can be represented as

$$
P^A(x)=(1,x^2,x^\mu).
$$

A general $SO(2,d)$ transformation sends $P^A(x)$ to another null vector. It may no longer satisfy $P^+=1$, so we rescale the vector to restore that gauge. This rescaling is precisely what produces the Weyl factor of a conformal transformation.

This construction explains why conformal transformations look nonlinear in ordinary coordinates even though they are just linear rotations in the embedding space.

## The boundary conformal group

A conformal transformation is a coordinate transformation that preserves the metric up to a local scale factor:

$$
f^*\eta_{\mu\nu}=\Omega(x)^2\eta_{\mu\nu}.
$$

Infinitesimally, write

$$
x^\mu\mapsto x^\mu+\xi^\mu(x).
$$

Then $\xi^\mu$ must obey the conformal Killing equation

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
\frac{2}{d}\,\eta_{\mu\nu}\,\partial_\rho\xi^\rho.
$$

For $d\geq 3$, the general solution on flat space is

$$
\xi^\mu(x)
=
a^\mu
+
\omega^\mu{}_{\nu}x^\nu
+
\lambda x^\mu
+
\left(2(b\cdot x)x^\mu-b^\mu x^2\right).
$$

The four terms are:

| Parameter | Transformation | Number of generators |
|---|---:|---:|
| $a^\mu$ | translations $P_\mu$ | $d$ |
| $\omega_{\mu\nu}=-\omega_{\nu\mu}$ | Lorentz transformations $M_{\mu\nu}$ | $d(d-1)/2$ |
| $\lambda$ | dilatation $D$ | $1$ |
| $b^\mu$ | special conformal transformations $K_\mu$ | $d$ |

Adding them gives

$$
d+\frac{d(d-1)}{2}+1+d
=
\frac{(d+1)(d+2)}{2},
$$

which is exactly the dimension of $SO(2,d)$.

The finite transformations are generated by these vector fields. A special conformal transformation can be written as inversion, translation, inversion, giving

$$
x'^\mu
=
\frac{x^\mu-b^\mu x^2}{1-2b\cdot x+b^2x^2},
$$

with sign conventions depending on the definition of $b^\mu$ and $K_\mu$.

## Killing vectors in Poincaré AdS

Now let us see the same match directly in Poincaré coordinates. The metric is

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
\qquad
z>0.
$$

The following vector fields are Killing vectors of this metric:

$$
P_\mu=\partial_\mu,
$$

$$
M_{\mu\nu}=x_\mu\partial_\nu-x_\nu\partial_\mu,
$$

$$
D=x^\mu\partial_\mu+z\partial_z,
$$

and

$$
K_\mu
=
2x_\mu\left(x^\nu\partial_\nu+z\partial_z\right)
-
(x^2+z^2)\partial_\mu.
$$

The first two are unsurprising. Translations and Lorentz transformations act on the $x^\mu$ coordinates and leave $z$ unchanged. The dilatation is more interesting:

$$
x^\mu\to e^\alpha x^\mu,
\qquad
z\to e^\alpha z.
$$

Both numerator and denominator in the metric scale by the same factor:

$$
dz^2+dx^2\to e^{2\alpha}(dz^2+dx^2),
\qquad
z^2\to e^{2\alpha}z^2,
$$

so the metric is invariant.

This is the first precise version of the statement that the AdS radial direction is related to energy scale. Boundary dilatations do not act only on boundary coordinates; their bulk extension also rescales $z$.

At $z=0$, the bulk Killing vectors reduce to the familiar conformal generators on the boundary:

$$
P_\mu\to \partial_\mu,
$$

$$
M_{\mu\nu}\to x_\mu\partial_\nu-x_\nu\partial_\mu,
$$

$$
D\to x^\mu\partial_\mu,
$$

and

$$
K_\mu\to 2x_\mu x^\nu\partial_\nu-x^2\partial_\mu.
$$

The radial part of $D$ and $K_\mu$ is not a nuisance. It is exactly what makes these transformations true bulk isometries rather than merely boundary transformations.

## Radial position and scale

The dilatation vector field

$$
D=x^\mu\partial_\mu+z\partial_z
$$

has a simple interpretation. If a boundary length scale transforms as

$$
\ell\to e^\alpha\ell,
$$

then the radial coordinate transforms as

$$
z\to e^\alpha z.
$$

Thus small $z$ corresponds to short distances or high energies in the boundary theory, while larger $z$ corresponds roughly to longer distances or lower energies.

This statement should not be overinterpreted as a literal equality between $z$ and an RG scale in every situation. But the symmetry is exact: the transformation that rescales boundary distances must also rescale the AdS radial coordinate.

In terms of an energy scale $\mu$, the rough relation is

$$
\mu\sim \frac{1}{z}.
$$

This is the seed of the UV/IR relation: the near-boundary region of AdS corresponds to ultraviolet physics in the CFT, while the deep interior corresponds to infrared physics.

## Sources, operators, and conformal weights

Suppose a boundary scalar primary operator $\mathcal O$ has scaling dimension $\Delta$. Under a Weyl rescaling of the boundary metric,

$$
g_{(0)\mu\nu}\to \Omega^2 g_{(0)\mu\nu},
$$

a scalar primary transforms as

$$
\mathcal O\to \Omega^{-\Delta}\mathcal O.
$$

If $\phi_{(0)}$ is the source for $\mathcal O$, the source term is schematically

$$
\int d^d x\sqrt{|g_{(0)}|}\,\phi_{(0)}\mathcal O.
$$

For this term to be invariant under Weyl transformations, the source must transform with weight

$$
\phi_{(0)}\to \Omega^{\Delta-d}\phi_{(0)}.
$$

Equivalently, the source has engineering dimension

$$
[\phi_{(0)}]=d-\Delta.
$$

This is exactly what the bulk near-boundary expansion will later encode. For a scalar field in standard quantization,

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x).
$$

Under the bulk dilatation

$$
z\to e^\alpha z,
\qquad
x^\mu\to e^\alpha x^\mu,
$$

the factor $z^{d-\Delta}$ carries the correct scaling for a source of dimension $d-\Delta$. This is not an accident. The mass-dimension relation and the source/vev dictionary are organized by the same $SO(2,d)$ representation theory.

## Global AdS and the cylinder

In global coordinates, the conformal boundary of AdS is the cylinder

$$
\mathbb R_t\times S^{d-1}.
$$

The global AdS time translation is a rotation in the two timelike embedding directions, often described as an $SO(2)$ subgroup of $SO(2,d)$. On the boundary, it becomes time translation on the cylinder.

This is why global AdS is naturally related to radial quantization in the CFT. The flat-space dilatation generator becomes the Hamiltonian on the cylinder:

$$
D_{\mathbb R^d}
\quad\longleftrightarrow\quad
H_{\mathbb R\times S^{d-1}}.
$$

A primary operator at the origin creates a state on the sphere, and its scaling dimension becomes the cylinder energy:

$$
H_{\mathrm{cyl}}|\mathcal O\rangle
=
\Delta |\mathcal O\rangle.
$$

On the bulk side, normal modes in global AdS have quantized frequencies. For a scalar field, the spectrum takes the form

$$
\omega_{n,\ell}=\Delta+2n+\ell,
\qquad
n=0,1,2,\ldots,
$$

where $\ell$ is the angular momentum on $S^{d-1}$. The ground mode corresponds to the primary operator, while higher modes correspond to descendants.

This is a preview of the mass-dimension relation. The match between bulk energies and CFT dimensions is a representation-theoretic statement before it is a computational one.

## Lorentzian and Euclidean versions

The discussion above used Lorentzian boundary signature. In that case the global conformal group of $d$-dimensional Minkowski space is

$$
SO(2,d).
$$

In Euclidean signature, the conformal group of $\mathbb R^d$ is instead

$$
SO(1,d+1),
$$

which is also the isometry group of Euclidean AdS, or hyperbolic space $H_{d+1}$.

This difference is only a signature difference, but it is worth keeping straight:

| Boundary signature | Bulk space | Symmetry group |
|---|---|---|
| Lorentzian $\mathbb R^{1,d-1}$ | Lorentzian $\mathrm{AdS}_{d+1}$ | $SO(2,d)$ |
| Euclidean $\mathbb R^d$ | Euclidean AdS $H_{d+1}$ | $SO(1,d+1)$ |

Many Euclidean computations are analytic continuations of Lorentzian statements, but not every real-time question can be answered by simply changing signs. This will matter when we discuss retarded Green's functions and black-hole horizons.

## The special case of two dimensions

For $d=2$, the global conformal group is

$$
SO(2,2)
\simeq
\frac{SL(2,\mathbb R)\times SL(2,\mathbb R)}{\mathbb Z_2}
$$

in Lorentzian signature. But two-dimensional CFTs often have an infinite-dimensional local conformal symmetry generated by two Virasoro algebras.

This does not contradict the statement

$$
\mathrm{Isom}(\mathrm{AdS}_3)=SO(2,2).
$$

The exact isometries of pure $\mathrm{AdS}_3$ give the global conformal subgroup. The larger Virasoro symmetry appears as an asymptotic symmetry of gravity with appropriate boundary conditions, not as an ordinary finite-dimensional isometry of the AdS metric. This distinction is the starting point of the Brown–Henneaux analysis, which appears later in the AdS$_3$/CFT$_2$ unit.

## What symmetry does and does not prove

The symmetry match is necessary, but not sufficient.

It tells us that the following identifications are natural:

$$
\text{bulk fields in }SO(2,d)\text{ representations}
\quad\leftrightarrow\quad
\text{CFT operators in conformal multiplets}.
$$

It also tells us that the CFT stress tensor should be dual to the bulk metric, because both are tied to spacetime symmetries. Similarly, a conserved global current in the CFT should be dual to a gauge field in the bulk.

But the symmetry alone does not determine the full dynamics. It does not determine the spectrum of operator dimensions, the OPE coefficients, the bulk interaction vertices, or whether the bulk theory is local at scales below the AdS radius. Those are dynamical questions.

The full power of AdS/CFT is that it combines this symmetry structure with a dynamical equality of partition functions and correlation functions.

## Dictionary checkpoint

The central translation from this page is:

$$
\boxed{
\mathrm{Isom}(\mathrm{AdS}_{d+1})
=
SO(2,d)
=
\text{global conformal group of the Lorentzian boundary CFT}
}
$$

More explicitly:

| Bulk generator | Boundary interpretation |
|---|---|
| $P_\mu$ | translations |
| $M_{\mu\nu}$ | Lorentz transformations |
| $D=x^\mu\partial_\mu+z\partial_z$ | dilatations and radial scaling |
| $K_\mu$ | special conformal transformations |
| global AdS time | cylinder Hamiltonian |
| bulk representation | conformal multiplet |

The AdS radial coordinate transforms under boundary scale transformations. This is the symmetry origin of the UV/IR relation and the first clue that radial evolution in the bulk is related to renormalization-group structure in the boundary theory.

## Common confusions

### “AdS has one more dimension, so should its symmetry be the Poincaré group in one higher dimension?”

No. The Poincaré group is the isometry group of flat Minkowski space. AdS is curved and has constant negative curvature. Its isometry group is $SO(2,d)$, not the $(d+1)$-dimensional Poincaré group.

### “The boundary conformal group is just Poincaré transformations plus scale transformations.”

Not for $d\geq 2$. Special conformal transformations are also part of the finite-dimensional global conformal group. Together, translations, Lorentz transformations, dilatations, and special conformal transformations close into $SO(2,d)$.

### “The radial coordinate is itself the RG scale.”

This is a useful slogan but not a literal identity. The exact statement is that boundary scale transformations are extended into the bulk by transformations that also rescale $z$. In many situations this motivates $\mu\sim 1/z$, but a precise holographic RG scheme requires choices of cutoff surface, counterterms, and radial gauge.

### “Bulk isometries are gauge redundancies, so they cannot act on CFT states.”

Small diffeomorphisms that vanish suitably at the boundary are gauge redundancies. Isometries and asymptotic symmetries that act nontrivially at the boundary correspond to genuine global symmetries of the boundary theory. Their charges act on CFT states.

### “The Poincaré patch shows all AdS symmetries manifestly.”

No. The Poincaré patch makes translations, Lorentz transformations, and dilatations transparent, but it covers only part of global AdS. Some global aspects of $SO(2,d)$ are hidden in Poincaré coordinates.

### “In AdS$_3$, the conformal group is only $SO(2,2)$.”

The global conformal subgroup is $SO(2,2)$. The infinite-dimensional Virasoro symmetry of two-dimensional CFT appears on the gravity side as an asymptotic symmetry of AdS$_3$, not as an ordinary isometry of the exact AdS$_3$ metric.

## Exercises

### Exercise 1: Count the conformal generators

Show that the number of generators in $d$-dimensional conformal symmetry agrees with $\dim SO(2,d)$.

<details>
<summary><strong>Solution</strong></summary>

For $d$-dimensional Lorentzian flat space, the finite-dimensional global conformal generators are:

$$
\begin{array}{c|c}
\text{generator type} & \text{number} \\
\hline
P_\mu & d \\
M_{\mu\nu} & d(d-1)/2 \\
D & 1 \\
K_\mu & d
\end{array}
$$

Therefore the total number is

$$
d+\frac{d(d-1)}2+1+d
=
\frac{d^2-d+4d+2}{2}
=
\frac{d^2+3d+2}{2}
=
\frac{(d+1)(d+2)}2.
$$

The group $SO(2,d)$ acts on a vector space of dimension $d+2$, so its number of generators is

$$
\frac{(d+2)(d+1)}2,
$$

which agrees.

</details>

### Exercise 2: Check the conformal Killing equation for a dilatation

Let

$$
\xi^\mu=\lambda x^\mu.
$$

Show that it solves

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=
\frac{2}{d}\eta_{\mu\nu}\partial_\rho\xi^\rho.
$$

<details>
<summary><strong>Solution</strong></summary>

Lowering the index gives

$$
\xi_\nu=\lambda x_\nu.
$$

Thus

$$
\partial_\mu\xi_\nu=\lambda\eta_{\mu\nu},
\qquad
\partial_\nu\xi_\mu=\lambda\eta_{\nu\mu}.
$$

Therefore

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu
=2\lambda\eta_{\mu\nu}.
$$

On the other hand,

$$
\partial_\rho\xi^\rho
=\partial_\rho(\lambda x^\rho)
=\lambda d.
$$

Hence

$$
\frac{2}{d}\eta_{\mu\nu}\partial_\rho\xi^\rho
=\frac{2}{d}\eta_{\mu\nu}(\lambda d)
=2\lambda\eta_{\mu\nu},
$$

which matches the left-hand side.

</details>

### Exercise 3: Show that the AdS dilatation is a Killing vector

Consider Poincaré AdS,

$$
ds^2=\frac{L^2}{z^2}(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu).
$$

Show that the finite transformation

$$
z\to e^\alpha z,
\qquad
x^\mu\to e^\alpha x^\mu
$$

leaves the metric invariant.

<details>
<summary><strong>Solution</strong></summary>

Under the transformation,

$$
dz\to e^\alpha dz,
\qquad
 dx^\mu\to e^\alpha dx^\mu.
$$

Thus

$$
dz^2+\eta_{\mu\nu}dx^\mu dx^\nu
\to
 e^{2\alpha}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right).
$$

The denominator transforms as

$$
z^2\to e^{2\alpha}z^2.
$$

Therefore

$$
\frac{L^2}{z^2}(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu)
\to
\frac{L^2}{e^{2\alpha}z^2}
 e^{2\alpha}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right)
=ds^2.
$$

So the vector field

$$
D=x^\mu\partial_\mu+z\partial_z
$$

generates an AdS isometry.

</details>

### Exercise 4: Boundary limit of the special conformal Killing vector

The bulk special conformal Killing vector in Poincaré AdS can be written as

$$
K_\mu
=
2x_\mu\left(x^\nu\partial_\nu+z\partial_z\right)
-
(x^2+z^2)\partial_\mu.
$$

Take the limit $z\to 0$. What boundary vector field remains?

<details>
<summary><strong>Solution</strong></summary>

At $z=0$, the $z\partial_z$ term vanishes as a vector tangent to the boundary, and the $z^2\partial_\mu$ term also vanishes. The remaining boundary vector field is

$$
K_\mu^{\partial}
=
2x_\mu x^\nu\partial_\nu-x^2\partial_\mu.
$$

This is the standard special conformal generator, up to sign conventions. The radial terms are nevertheless essential in the bulk: without them, the vector field would not be a Killing vector of the full AdS metric.

</details>

### Exercise 5: Source dimension from Weyl invariance

Suppose a scalar primary has dimension $\Delta$. The source term is

$$
\int d^d x\sqrt{|g_{(0)}|}\,\phi_{(0)}\mathcal O.
$$

Under

$$
g_{(0)\mu\nu}\to \Omega^2 g_{(0)\mu\nu},
\qquad
\mathcal O\to \Omega^{-\Delta}\mathcal O,
$$

find the Weyl transformation of $\phi_{(0)}$ that keeps the source term invariant.

<details>
<summary><strong>Solution</strong></summary>

The measure transforms as

$$
\sqrt{|g_{(0)}|}\to \Omega^d\sqrt{|g_{(0)}|}.
$$

The operator transforms as

$$
\mathcal O\to \Omega^{-\Delta}\mathcal O.
$$

For the product to be invariant, the source must transform as

$$
\phi_{(0)}\to \Omega^{\Delta-d}\phi_{(0)}.
$$

Therefore the source has Weyl weight $\Delta-d$, or equivalently engineering dimension

$$
[\phi_{(0)}]=d-\Delta.
$$

This is the same scaling that appears in the leading AdS falloff $z^{d-\Delta}\phi_{(0)}$.

</details>

## Further reading

The symmetry match between AdS isometries and CFT conformal transformations is already central in the original AdS/CFT proposal and its early formulations:

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- D. Simmons-Duffin, [TASI Lectures on the Conformal Bootstrap](https://arxiv.org/abs/1602.07982), especially the discussion of conformal symmetry and embedding-space notation.
- S. Rychkov, [EPFL Lectures on Conformal Field Theory in $D\geq 3$ Dimensions](https://arxiv.org/abs/1601.05000), for a pedagogical CFT-side treatment of conformal generators and primaries.
