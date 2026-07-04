---
title: "Conformal Symmetry: The Minimum Needed"
description: "The essential conformal field theory needed for AdS/CFT: conformal transformations, primary operators, scaling dimensions, fixed two- and three-point functions, OPE data, Ward identities, and the match to AdS isometries."
sidebar:
  order: 20
---

AdS/CFT is a duality between a gravitational theory in asymptotically Anti-de Sitter spacetime and a conformal field theory on the boundary. To start using the duality, we do not need the whole technology of conformal field theory. We need a precise minimum:

1. what conformal transformations are;
2. how local operators transform;
3. how symmetry constrains correlation functions;
4. what data remain dynamical;
5. why the conformal group matches the AdS isometry group.

This page develops that minimum. The goal is not to replace a full CFT course. The goal is to make the holographic dictionary legible.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Conformal symmetry organizes CFT data and matches AdS isometries](/figures/course/conformal-symmetry-map.svg)

<figcaption>

The same group that acts as conformal transformations on the boundary also acts as isometries of $\mathrm{AdS}_{d+1}$. Conformal symmetry fixes kinematics; the spectrum of primary operators and their OPE coefficients contain the dynamical data that holography repackages as bulk fields and interactions.

</figcaption>
</figure>

## Why this matters for holography

The word “conformal” in AdS/CFT is not decorative. It is the reason the boundary theory can live naturally on the conformal boundary of AdS, and it is the reason the two sides have the same spacetime symmetry.

In $d$-dimensional Lorentzian flat space, the conformal group is locally $SO(2,d)$. The isometry group of $\mathrm{AdS}_{d+1}$ is also $SO(2,d)$. Thus the basic symmetry match is

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})
=
SO(2,d)
=
\mathrm{Conf}(\mathbb R^{1,d-1}).
$$

This match is the first hard clue that a CFT can be dual to a theory in AdS. Translations, rotations, boosts, dilations, and special conformal transformations of the boundary are realized as ordinary spacetime isometries of the bulk.

But symmetry alone does not determine the theory. A CFT has dynamical data: operator dimensions, spins, OPE coefficients, central charges, and global-symmetry data. In holography, these data become bulk masses, spins, couplings, gauge fields, Newton's constant, and higher-derivative corrections.

A useful first slogan is

$$
\text{CFT kinematics}
\quad
\longleftrightarrow
\quad
\text{AdS geometry},
$$

while

$$
\text{CFT dynamics}
\quad
\longleftrightarrow
\quad
\text{bulk spectrum and interactions}.
$$

This page explains the field-theory side of those statements.

## Conformal transformations

A conformal transformation is a coordinate transformation that preserves angles but may change local lengths. In flat space, write

$$
x^\mu \mapsto x'^\mu(x).
$$

The transformation is conformal if the metric changes only by a position-dependent scale factor:

$$
\eta_{\rho\sigma}
\frac{\partial x'^\rho}{\partial x^\mu}
\frac{\partial x'^\sigma}{\partial x^\nu}
=
\Omega(x)^2\eta_{\mu\nu}.
$$

Equivalently,

$$
ds'^2 = \Omega(x)^2 ds^2.
$$

In Euclidean signature, replace $\eta_{\mu\nu}$ by $\delta_{\mu\nu}$. In Lorentzian signature, conformal transformations preserve the light-cone structure because multiplying the metric by a nonzero scalar does not change which tangent vectors are null.

The most familiar conformal transformations are:

| transformation | action on coordinates |
|---|---|
| translations | $x^\mu \to x^\mu+a^\mu$ |
| rotations or Lorentz transformations | $x^\mu \to \Lambda^\mu{}_\nu x^\nu$ |
| dilations | $x^\mu \to \lambda x^\mu$ |
| special conformal transformations | $x^\mu \to \dfrac{x^\mu-b^\mu x^2}{1-2b\cdot x+b^2x^2}$ |

The special conformal transformation looks mysterious at first sight, but it has a simple origin: it is an inversion, followed by a translation, followed by another inversion. If

$$
I: x^\mu \mapsto \frac{x^\mu}{x^2},
$$

then a special conformal transformation is schematically

$$
K_b = I\,T_{-b}\,I.
$$

This is why the special conformal generators are as fundamental as translations in a conformal theory. They are not optional extra symmetries; together with translations, rotations, and dilations, they complete the finite-dimensional conformal group in $d>2$.

## Infinitesimal conformal transformations

Let

$$
x'^\mu = x^\mu + \xi^\mu(x)
$$

be an infinitesimal transformation. To first order in $\xi$, the metric changes by

$$
\delta g_{\mu\nu}
=
\partial_\mu \xi_\nu+
\partial_\nu \xi_\mu.
$$

The transformation is conformal if this change is proportional to the metric. Thus $\xi^\mu$ obeys the conformal Killing equation

$$
\partial_\mu \xi_\nu+
\partial_\nu \xi_\mu
=
\frac{2}{d}(\partial\cdot \xi)\eta_{\mu\nu}.
$$

For $d>2$, the general solution in flat space is

$$
\xi^\mu(x)
=
a^\mu
+
\omega^\mu{}_{\nu}x^\nu
+
\lambda x^\mu
+
2(b\cdot x)x^\mu
-
b^\mu x^2.
$$

The four terms are, respectively:

| parameter | generator | meaning |
|---|---|---|
| $a^\mu$ | $P_\mu$ | translations |
| $\omega_{\mu\nu}=-\omega_{\nu\mu}$ | $M_{\mu\nu}$ | rotations or Lorentz transformations |
| $\lambda$ | $D$ | dilation |
| $b^\mu$ | $K_\mu$ | special conformal transformations |

Counting generators gives

$$
d + \frac{d(d-1)}{2} + 1 + d
=
\frac{(d+1)(d+2)}{2},
$$

which is the dimension of $SO(d+1,1)$ in Euclidean signature or $SO(2,d)$ in Lorentzian signature.

A few useful commutators are

$$
[D,P_\mu] = P_\mu,
\qquad
[D,K_\mu] = -K_\mu,
\qquad
[K_\mu,P_\nu] = 2\eta_{\mu\nu}D-2M_{\mu\nu},
$$

up to conventional factors of $i$ and sign choices in Lorentzian quantum-mechanical conventions. The first two equations say that translations raise scale and special conformal transformations lower scale, in the representation-theoretic sense used in radial quantization.

:::note
In $d=2$, the local conformal algebra is infinite-dimensional. The global conformal group is still finite-dimensional, but two-dimensional CFT has the much stronger Virasoro symmetry. This course first treats the $d>2$ logic, then returns to the special power of $\mathrm{AdS}_3/\mathrm{CFT}_2$ later.
:::

## Scale invariance versus conformal invariance

Scale invariance means invariance under

$$
x^\mu \to \lambda x^\mu.
$$

Conformal invariance includes scale invariance but also special conformal transformations. In many unitary relativistic QFTs with a good stress tensor, scale invariance plus additional assumptions implies conformal invariance, but this is a subtle theorem-like subject rather than a definition.

For this course, a CFT means a quantum field theory with conformal symmetry. Equivalently, on flat space it has an improved stress tensor whose trace vanishes at separated points:

$$
T^\mu{}_{\mu}=0.
$$

On curved backgrounds, even-dimensional CFTs can have a Weyl anomaly. That anomaly is not a contradiction. It means that the quantum generating functional is not invariant under local Weyl rescalings of the background metric. Holographically, the Weyl anomaly arises from logarithmic terms in the near-boundary expansion and from logarithmic counterterms.

## Local operators and scaling dimensions

A local operator $\mathcal O(x)$ is an observable inserted at a spacetime point. Under the coordinate map $x'=\lambda x$, a scalar operator of scaling dimension $\Delta$ transforms as

$$
\mathcal O'(x')=\lambda^{-\Delta}\mathcal O(x).
$$

The number $\Delta$ is the scaling dimension of the operator.

In an interacting CFT, $\Delta$ is generally not the classical engineering dimension. It includes anomalous dimensions. One of the main dynamical problems in CFT is to determine the allowed operator dimensions and OPE coefficients.

In holography, $\Delta$ is also the first quantum number that tells us what kind of bulk field we are looking at. For a scalar field in $\mathrm{AdS}_{d+1}$, the mass-dimension relation will be

$$
m^2L^2 = \Delta(\Delta-d).
$$

This formula will be derived later. For now, the important point is that the CFT scaling dimension becomes a bulk mass in AdS units.

## Primary operators

The most important local operators in a CFT are primary operators. Roughly, a primary is an operator that transforms simply under conformal transformations and is not obtained by differentiating another local operator.

For a scalar primary $\mathcal O(x)$ of dimension $\Delta$, a finite conformal transformation with local scale factor $\Omega(x)$ gives

$$
\mathcal O'(x') = \Omega(x)^{-\Delta}\mathcal O(x).
$$

Operators with spin also rotate by a local Lorentz transformation. For example, a vector primary has both a scale factor and a matrix acting on its index.

Descendant operators are obtained by derivatives of primaries:

$$
\partial_\mu \mathcal O,
\qquad
\partial_\mu\partial_\nu \mathcal O,
\qquad
\ldots
$$

In radial quantization, which we discuss on the next page, primaries are highest-weight states of the conformal algebra, and descendants are created by acting with translations $P_\mu$. This is the CFT analogue of organizing a Hilbert space into irreducible representations.

For holography, primary operators are the natural boundary objects dual to elementary bulk fields. Descendants correspond to derivatives and excitations of the same bulk field rather than new independent particles.

## What conformal symmetry fixes

Symmetry strongly restricts correlation functions. This is the first major reason CFTs are tractable.

Translation invariance implies that correlators depend only on coordinate differences. Rotation or Lorentz invariance constrains the tensor structure. Scale invariance fixes the overall degree of homogeneity. Special conformal invariance imposes further restrictions, often enough to determine the entire coordinate dependence of two- and three-point functions.

### One-point functions

On flat space, the vacuum one-point function of a non-identity scalar primary vanishes:

$$
\langle \mathcal O(x)\rangle = 0,
\qquad
\mathcal O \neq \mathbf 1.
$$

This follows from translation invariance and scale invariance. Translation invariance says the answer is constant. Scale invariance then forces that constant to vanish unless the operator has $\Delta=0$. In a unitary CFT, the scalar primary with $\Delta=0$ is the identity.

On curved spaces, in thermal states, or in states with sources turned on, one-point functions can be nonzero. Holographic one-point functions are precisely a controlled way to compute such responses.

### Two-point functions

For scalar primaries, conformal symmetry fixes the two-point function up to normalization. In a basis of scalar primaries with diagonal two-point functions,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

More generally, before choosing an orthonormal basis,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{C_{ij}}{|x|^{2\Delta_i}},
\qquad
\Delta_i=\Delta_j,
$$

and the correlator vanishes for scalar primaries of different dimensions, assuming no degeneracy mixing has been left unresolved.

This formula is the boundary target of the first holographic two-point function calculation. A free scalar field in AdS, evaluated on shell with prescribed boundary value, reproduces this power law.

### Three-point functions

For three scalar primaries, conformal symmetry fixes the coordinate dependence up to a constant $C_{123}$:

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)
\rangle
=
\frac{C_{123}}
{|x_{12}|^{\Delta_1+\Delta_2-\Delta_3}
 |x_{23}|^{\Delta_2+\Delta_3-\Delta_1}
 |x_{13}|^{\Delta_1+\Delta_3-\Delta_2}},
$$

where

$$
x_{ij}=x_i-x_j.
$$

The number $C_{123}$ is dynamical. In a holographic CFT, it is computed from a cubic interaction in the bulk. This is the simplest example of the rule

$$
\text{bulk coupling}
\quad
\longleftrightarrow
\quad
\text{CFT OPE coefficient}.
$$

### Four-point functions

Four-point functions are much less constrained. For identical scalar primaries of dimension $\Delta$,

$$
\langle
\mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)
\rangle
=
\frac{1}{|x_{12}|^{2\Delta}|x_{34}|^{2\Delta}}
\mathcal G(u,v),
$$

where the conformally invariant cross ratios are

$$
u =
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v =
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The function $\mathcal G(u,v)$ contains nontrivial dynamical information. Its structure encodes the operator product expansion, crossing symmetry, and, in holographic theories, aspects of bulk locality.

## The operator product expansion

The operator product expansion, or OPE, says that when two local operators approach each other, their product can be expanded in local operators at one point:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k\,
\frac{\mathcal O_k(0)}{|x|^{\Delta_i+\Delta_j-\Delta_k}}
+
\text{descendants}.
$$

This expression is schematic: spinning operators require tensor structures, and descendants come with fixed differential operators. But the message is correct. Once the spectrum of primaries and the OPE coefficients are known, local correlation functions are highly constrained.

A compact way to describe a CFT is therefore:

$$
\text{CFT data}
=
\left\{
\Delta_i,
\ell_i,
C_{ijk},
\text{global-symmetry representations},
\ldots
\right\}.
$$

Here $\ell_i$ denotes spin. In two dimensions, one often organizes the data using left and right conformal weights $(h,\bar h)$ instead of $\Delta$ and $\ell$.

In AdS/CFT, these data are not abstract bookkeeping. They are the boundary encoding of the bulk theory:

| CFT datum | Bulk interpretation |
|---|---|
| primary operator $\mathcal O_i$ | single-particle bulk field $\phi_i$ in the large-$N$ limit |
| scaling dimension $\Delta_i$ | mass or energy of the bulk field in AdS units |
| spin $\ell_i$ | spin of the bulk field |
| OPE coefficient $C_{ijk}$ | cubic bulk coupling, after normalization |
| central charge or stress-tensor normalization | inverse Newton coupling in AdS units |
| large gap in high-spin single-trace operators | local bulk effective field theory regime |

The table is a guide, not a replacement for the dictionary. Each entry has normalization subtleties that will matter in computations.

## Conserved currents and the stress tensor

Continuous global symmetries in a CFT have conserved currents:

$$
\partial_\mu J^\mu = 0.
$$

A conserved current in $d$ dimensions has protected scaling dimension

$$
\Delta_J = d-1.
$$

In holography, such a current is dual to a bulk gauge field $A_M$. The boundary value of $A_\mu$ is a source for $J^\mu$, and the normalizable response gives the expectation value of the current.

The stress tensor is conserved and traceless in flat-space CFT:

$$
\partial_\mu T^{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

It has dimension

$$
\Delta_T=d.
$$

In holography, the stress tensor is dual to the bulk metric $g_{MN}$. This is one of the deepest entries in the dictionary:

$$
T_{\mu\nu}
\quad
\longleftrightarrow
\quad
g_{MN}.
$$

The source for the stress tensor is the boundary metric $g_{(0)\mu\nu}$. Varying the renormalized generating functional with respect to this metric gives

$$
\langle T^{\mu\nu}\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W}{\delta g_{(0)\mu\nu}}.
$$

On the bulk side, this same quantity is computed by the renormalized Brown–York stress tensor.

## Unitarity bounds

In a unitary CFT, scaling dimensions cannot be arbitrary. For $d\ge 3$, scalar primaries obey

$$
\Delta \ge \frac{d-2}{2},
$$

while symmetric traceless spin-$\ell$ primaries with $\ell\ge 1$ obey

$$
\Delta \ge \ell+d-2.
$$

Saturation has physical meaning. A spin-one primary with

$$
\Delta=d-1
$$

is a conserved current. A spin-two primary with

$$
\Delta=d
$$

is a conserved stress tensor.

These bounds foreshadow bulk stability bounds. For example, the scalar unitarity bound is related, through the AdS mass-dimension relation, to the range of allowed scalar masses in AdS. The precise bulk statement is the Breitenlohner–Freedman bound, which we will discuss when studying fields in AdS.

## Sources and dimensions

The previous page introduced sources and generating functionals. In a CFT, scaling dimensions immediately determine the dimension of a source.

If a scalar operator $\mathcal O$ has dimension $\Delta$, the source coupling is

$$
\int d^d x\, J(x)\mathcal O(x).
$$

For the exponent in the path integral to be dimensionless, the source must have mass dimension

$$
[J]=d-\Delta.
$$

This simple relation is essential in holography. The leading near-boundary coefficient of a bulk field has exactly the scaling expected for a source of dimension $d-\Delta$.

It also classifies deformations:

| operator dimension | deformation by $\int J\mathcal O$ |
|---|---|
| $\Delta<d$ | relevant |
| $\Delta=d$ | marginal |
| $\Delta>d$ | irrelevant |

Relevant deformations grow in the infrared. Irrelevant deformations become more important in the ultraviolet and are usually harder to define nonperturbatively. In the bulk, relevant deformations often correspond to changing boundary conditions for fields whose backreaction drives the geometry away from AdS in the interior.

## CFT on the cylinder

Flat Euclidean space minus the origin is conformally equivalent to a cylinder:

$$
\mathbb R^d\setminus\{0\}
\simeq
\mathbb R_\tau\times S^{d-1},
\qquad
r=e^\tau.
$$

Indeed,

$$
ds^2 = dr^2+r^2d\Omega_{d-1}^2
= e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

A CFT is insensitive to the overall Weyl factor, up to possible anomalies and operator rescalings. Therefore radial evolution in flat space becomes time evolution on the cylinder.

This is the origin of the state-operator map. A local operator inserted at the origin creates a state on $S^{d-1}$, and the scaling dimension becomes the cylinder energy:

$$
E_{\mathrm{cyl}} = \frac{\Delta}{L_{S^{d-1}}}.
$$

This relation is central in global AdS/CFT: global AdS has boundary $\mathbb R\times S^{d-1}$, so CFT states on the cylinder are naturally compared with bulk states in global AdS.

The next page develops this idea in more detail.

## What conformal symmetry does not fix

Conformal symmetry is powerful, but it is not omnipotent.

It fixes the coordinate dependence of scalar two- and three-point functions. It constrains tensor structures. It organizes operators into representations. It relates Ward identities to conserved currents and the stress tensor.

But it does not, by itself, determine:

- the list of primary operators;
- their scaling dimensions;
- the OPE coefficients;
- the value of the central charge;
- the full functions of cross ratios in four-point and higher-point correlators;
- whether the CFT has a weakly curved gravitational dual.

The last point is especially important. A CFT is not automatically holographic in the sense of having a simple Einstein-gravity dual. A weakly curved local bulk dual requires extra dynamical structure, including large $N$ factorization and a sparse spectrum of low-dimension single-trace operators with a large gap to higher-spin single-trace operators.

That is why the next parts of the course combine conformal symmetry with large-$N$ gauge theory.

## Dictionary checkpoint

The minimum CFT dictionary from this page is:

| Boundary concept | Bulk interpretation |
|---|---|
| conformal group $SO(2,d)$ | isometry group of $\mathrm{AdS}_{d+1}$ |
| primary operator $\mathcal O_{\Delta,\ell}$ | bulk field with spin $\ell$ |
| scaling dimension $\Delta$ | bulk mass or energy in AdS units |
| OPE coefficient $C_{ijk}$ | bulk interaction strength |
| conserved current $J^\mu$ | bulk gauge field $A_M$ |
| stress tensor $T^{\mu\nu}$ | bulk metric $g_{MN}$ |
| source for $\mathcal O$ | boundary value of the dual bulk field |
| source for $T^{\mu\nu}$ | boundary metric |

The key lesson is that conformal symmetry fixes the stage. The CFT data tell us what theory is playing on that stage.

## Common confusions

### “Conformal symmetry fixes the whole CFT.”

No. It fixes much of the kinematics, but not the spectrum and OPE coefficients. Two CFTs can have the same conformal group and very different dynamics.

### “Scale invariance and conformal invariance are the same thing.”

Conformal invariance includes scale invariance, but the converse is subtle. In this course, we assume conformal invariance when we say CFT.

### “A primary is just an operator with no derivatives.”

Not quite. Being primary is a representation-theoretic condition under the conformal group. In simple examples, descendants are often derivatives of primaries, but composite operators with derivatives can sometimes be arranged into primary combinations after subtracting descendants.

### “The AdS radial direction is generated by the CFT dilation operator in every coordinate system.”

This is too quick. In Poincaré AdS, a boundary dilation can be extended into the bulk as a scaling of both boundary coordinates and the radial coordinate. But the precise relation between radial position and energy scale is coordinate- and state-dependent. The robust statement is that asymptotic radial behavior encodes UV scaling data.

### “Every CFT has an Einstein gravity dual.”

No. A generic CFT does not have a weakly curved classical bulk description. Einstein gravity requires special large-$N$ and large-gap properties.

## Exercises

### Exercise 1: Solve the scale dependence of a two-point function

Let $\mathcal O$ be a scalar primary of dimension $\Delta$ in a translation- and rotation-invariant Euclidean CFT. Show that scale invariance implies

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C}{|x|^{2\Delta}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Translation and rotation invariance imply that the two-point function depends only on $r=|x|$:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle = f(r).
$$

Under a dilation $x\to \lambda x$, each scalar primary contributes a factor $\lambda^{-\Delta}$. Therefore

$$
f(\lambda r)=\lambda^{-2\Delta}f(r).
$$

The solution is

$$
f(r)=\frac{C}{r^{2\Delta}}.
$$

Special conformal invariance further implies that two scalar primaries have a nonzero two-point function only when their dimensions match, after choosing a basis that diagonalizes the two-point matrix.

</details>

### Exercise 2: Count the conformal generators

For $d>2$, count the number of generators associated with translations, rotations, dilations, and special conformal transformations. Show that the result agrees with the dimension of $SO(2,d)$.

<details>
<summary><strong>Solution</strong></summary>

There are $d$ translations $P_\mu$, $d$ special conformal transformations $K_\mu$, one dilation $D$, and

$$
\frac{d(d-1)}{2}
$$

rotations or Lorentz transformations $M_{\mu\nu}$. Thus the total is

$$
d+d+1+\frac{d(d-1)}{2}
=
2d+1+\frac{d^2-d}{2}
=
\frac{d^2+3d+2}{2}
=
\frac{(d+1)(d+2)}{2}.
$$

The group $SO(2,d)$ acts on a vector space of dimension $d+2$, so its Lie algebra has

$$
\frac{(d+2)(d+1)}{2}
$$

generators, in agreement with the count above.

</details>

### Exercise 3: Determine the dimension of a source

Suppose a scalar operator $\mathcal O$ has scaling dimension $\Delta$ in $d$ spacetime dimensions. The theory is deformed by

$$
\delta S = -\int d^d x\,J(x)\mathcal O(x).
$$

What is the mass dimension of $J$?

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless in units with $\hbar=1$. The measure has dimension

$$
[d^d x]=-d,
$$

and the operator has dimension

$$
[\mathcal O]=\Delta.
$$

Therefore

$$
[J]+\Delta-d=0,
$$

so

$$
[J]=d-\Delta.
$$

This is why the source for a relevant operator has positive mass dimension, the source for a marginal operator is dimensionless, and the source for an irrelevant operator has negative mass dimension.

</details>

### Exercise 4: Relate conserved currents to protected dimensions

A conserved current obeys $\partial_\mu J^\mu=0$. Use the unitarity-bound statement for spin-$\ell$ primaries,

$$
\Delta \ge \ell+d-2,
$$

to identify the dimensions of a conserved current and the stress tensor.

<details>
<summary><strong>Solution</strong></summary>

For a spin-one current, set $\ell=1$. Saturating the bound gives

$$
\Delta_J = 1+d-2=d-1.
$$

The conservation equation removes a descendant from the representation, which is why the bound is saturated.

For the stress tensor, $\ell=2$, so saturation gives

$$
\Delta_T = 2+d-2=d.
$$

Thus a conserved current has dimension $d-1$, and the conserved stress tensor has dimension $d$.

</details>

## Further reading

- S. Rychkov, [EPFL Lectures on Conformal Field Theory in $D\ge 3$ Dimensions](https://arxiv.org/abs/1601.05000).
- D. Simmons-Duffin, [TASI Lectures on the Conformal Bootstrap](https://arxiv.org/abs/1602.07982).
- P. Di Francesco, P. Mathieu, and D. Sénéchal, [Conformal Field Theory](https://link.springer.com/book/10.1007/978-1-4612-2256-9).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).

For this course, the next essential step is not more CFT technology. It is radial quantization and the cylinder, because that is where scaling dimensions become energies and the boundary of global AdS becomes the natural home of the CFT Hilbert space.
