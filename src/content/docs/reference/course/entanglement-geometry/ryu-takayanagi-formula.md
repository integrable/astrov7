---
title: "Ryu–Takayanagi formula"
description: "The geometric formula for holographic entanglement entropy, including minimal surfaces, homology, AdS3 intervals, strips, UV divergences, and the replica argument."
sidebar:
  order: 20
---

The Ryu–Takayanagi formula is one of the most important entries in the AdS/CFT dictionary. It says that, in a classical static holographic bulk, the entanglement entropy of a boundary region is computed by the area of a minimal surface in the bulk.

For a boundary spatial region $A$, the formula is

$$
S_A
=
\frac{\operatorname{Area}(\gamma_A)}{4G_N},
$$

where $\gamma_A$ is a codimension-two bulk surface satisfying

$$
\partial \gamma_A = \partial A
$$

and a homology condition explained below.

This formula is astonishing because the left-hand side is a quantum-information quantity in a non-gravitational QFT, while the right-hand side is a geometric area in a higher-dimensional gravitational spacetime.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A boundary region A is anchored to a bulk minimal surface gamma_A. The entanglement entropy is area(gamma_A)/(4G_N).](/figures/course/ryu-takayanagi-formula.svg)

<figcaption>

The RT surface $\gamma_A$ is anchored on $\partial A$ and homologous to $A$. In a static classical bulk, $S_A=\operatorname{Area}(\gamma_A)/(4G_N)$.

</figcaption>
</figure>

## The statement

Assume the bulk geometry is static and asymptotically AdS. Choose a constant-time slice of the boundary and a spatial region $A$ on that slice. The RT surface $\gamma_A$ is the minimal-area bulk codimension-two surface such that

$$
\partial\gamma_A = \partial A .
$$

More precisely, $\gamma_A$ must also be homologous to $A$: there must exist a bulk spatial region $r_A$ such that

$$
\partial r_A = A \cup \gamma_A
$$

with orientations understood. Then the leading large-$N$ entanglement entropy is

$$
S_A
=
\frac{\operatorname{Area}(\gamma_A)}{4G_N} .
$$

The formula is valid at the leading classical-gravity order. Quantum corrections will modify it to include bulk entanglement across the surface; time-dependent states require the covariant HRT generalization.

A compact summary is:

$$
\boxed{
\text{boundary entanglement}
\quad\longleftrightarrow\quad
\text{bulk extremal area}
}
$$

for holographic theories in the correct large-$N$, large-gap regime.

## Why the surface has codimension two

In a $d$-dimensional boundary QFT, the region $A$ is spatial, so it has dimension $d-1$. Its boundary $\partial A$ has dimension $d-2$.

The bulk spacetime has dimension $d+1$. A constant-time bulk slice has dimension $d$. The RT surface lies inside that bulk spatial slice and is anchored on $\partial A$, so it has dimension $d-1$? Careful: the RT surface is codimension two in spacetime, hence dimension

$$
(d+1)-2=d-1.
$$

On a constant-time slice, it is codimension one. This is why in AdS$_3$/CFT$_2$ the RT surface is a geodesic: the bulk spacetime is three-dimensional, and a codimension-two surface is one-dimensional.

The dimension matches the Bekenstein–Hawking area law. A black-hole horizon is also a codimension-two surface, and its entropy is

$$
S_{\mathrm{BH}} = \frac{\operatorname{Area}(\mathcal H)}{4G_N} .
$$

The RT formula generalizes this area-entropy relation from horizons to entangling surfaces.

## Why the homology condition matters

The condition $\partial\gamma_A=\partial A$ is not enough. The RT surface must be homologous to $A$. That is, $A$ and $\gamma_A$ should together bound a bulk region $r_A$.

This condition has several important consequences.

First, for a pure state on the whole boundary, it ensures

$$
S_A = S_{A^c} .
$$

The same bulk surface can be viewed as homologous to $A$ or to $A^c$.

Second, in black-hole geometries, the homology condition can force the RT surface for a large region to include or avoid horizon pieces in a precise way. This is how ordinary thermal entropy enters entanglement entropy.

Third, the homology region $r_A$ is the first appearance of what later becomes the entanglement wedge. In classical static situations, the entanglement wedge is the domain of dependence of $r_A$.

## The simplest example: an interval in AdS$_3$/CFT$_2$

Consider the vacuum of a two-dimensional holographic CFT on the line. The dual bulk is Poincaré AdS$_3$:

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2-dt^2+dx^2\right),
\qquad z>0 .
$$

Take a boundary interval

$$
A = \left[-\frac{\ell}{2},\frac{\ell}{2}\right]
$$

at $t=0$. The RT surface is a spacelike geodesic in the $t=0$ hyperbolic plane,

$$
ds^2_{t=0}
=
\frac{L^2}{z^2}(dz^2+dx^2) .
$$

By symmetry, the geodesic is a semicircle:

$$
x^2+z^2=\left(\frac{\ell}{2}\right)^2 .
$$

Regulate the boundary by cutting off the geometry at $z=\epsilon$. Parametrize the semicircle by

$$
x=\frac{\ell}{2}\cos\theta,
\qquad
z=\frac{\ell}{2}\sin\theta .
$$

Then

$$
ds
=
\frac{L}{\sin\theta}d\theta .
$$

The cutoff corresponds to $\sin\theta_\epsilon=2\epsilon/\ell$. The geodesic length is

$$
\operatorname{Length}(\gamma_A)
=
2L\int_{\theta_\epsilon}^{\pi/2}\frac{d\theta}{\sin\theta}
=
2L\log\frac{\ell}{\epsilon}+O(\epsilon^2) .
$$

Therefore

$$
S_A
=
\frac{\operatorname{Length}(\gamma_A)}{4G_3}
=
\frac{L}{2G_3}\log\frac{\ell}{\epsilon}+\cdots .
$$

Using the Brown–Henneaux central charge

$$
c=\frac{3L}{2G_3},
$$

we obtain

$$
S_A
=
\frac{c}{3}\log\frac{\ell}{\epsilon}+\cdots,
$$

which is exactly the CFT$_2$ vacuum interval result.

This example is the canonical first check of the RT formula.

## UV divergences from near-boundary area

The RT surface approaches the AdS boundary near $\partial A$. This automatically produces a divergent area.

Near the boundary, the bulk metric locally looks like

$$
ds^2
=\frac{L^2}{z^2}\left(dz^2+ds^2_{\partial}\right) .
$$

For a smooth entangling surface, the RT surface is approximately a vertical extension of $\partial A$ close to $z=0$. Its area therefore contains

$$
\operatorname{Area}(\gamma_A)
\sim
L^{d-1}\operatorname{Area}(\partial A)
\int_\epsilon \frac{dz}{z^{d-1}} .
$$

For $d>2$,

$$
\operatorname{Area}(\gamma_A)
\sim
\frac{L^{d-1}}{d-2}\frac{\operatorname{Area}(\partial A)}{\epsilon^{d-2}}+\cdots .
$$

Thus

$$
S_A
\sim
\frac{L^{d-1}}{4G_N(d-2)}
\frac{\operatorname{Area}(\partial A)}{\epsilon^{d-2}}
+
\cdots .
$$

This is exactly the QFT area law. The coefficient is cutoff dependent, just as on the boundary.

The near-boundary divergence is not an embarrassment. It is the holographic image of short-distance entanglement.

## Strip regions in higher dimensions

A useful higher-dimensional example is an infinite strip in the vacuum of a $d$-dimensional CFT:

$$
A=\left\{ -\frac{\ell}{2}\leq x\leq \frac{\ell}{2},\quad \mathbf y\in \mathbb R^{d-2}\right\} .
$$

Work in Euclidean-signature or constant-time Poincaré AdS:

$$
ds^2
=\frac{L^2}{z^2}\left(dz^2+dx^2+d\mathbf y^2\right) .
$$

Let the RT surface be described by $z=z(x)$ and extend along the transverse $\mathbf y$ directions. If $V_{d-2}$ is the regulated transverse volume, the area functional is

$$
\operatorname{Area}
=L^{d-1}V_{d-2}
\int_{-\ell/2}^{\ell/2} dx\,
\frac{\sqrt{1+(z')^2}}{z^{d-1}} .
$$

Since the integrand does not depend explicitly on $x$, there is a conserved quantity. At the turning point $z=z_*$ where $z'=0$, one obtains

$$
\frac{1}{z^{d-1}\sqrt{1+(z')^2}}
=
\frac{1}{z_*^{d-1}} .
$$

This gives

$$
\frac{\ell}{2}
=
z_*\int_0^1 du\,
\frac{u^{d-1}}{\sqrt{1-u^{2d-2}}} .
$$

The area has the structure

$$
\operatorname{Area}
=
\frac{2L^{d-1}V_{d-2}}{d-2}\frac{1}{\epsilon^{d-2}}
-
\kappa_d L^{d-1}\frac{V_{d-2}}{\ell^{d-2}}
+
\cdots,
$$

where $\kappa_d$ is a positive dimension-dependent constant. The first term is the area-law divergence. The second term is finite and controlled by conformal invariance.

## Ball-shaped regions

For a ball of radius $R$ in the vacuum of a CFT, the RT surface in Poincaré AdS is a hemisphere:

$$
r^2+z^2=R^2 .
$$

This example is special because the boundary reduced density matrix is conformally related to a thermal state on hyperbolic space. In the bulk, the same geometry can be described as a hyperbolic black hole whose horizon area computes the entropy.

This relation is the cleanest geometric bridge between three ideas:

$$
\text{sphere entanglement}
\quad\longleftrightarrow\quad
\text{thermal entropy on }\mathbb R\times\mathbb H^{d-1}
\quad\longleftrightarrow\quad
\text{horizon area} .
$$

It also plays a central role in derivations of the RT formula and in later arguments connecting entanglement to Einstein's equations.

## The replica argument in one page

The RT formula was originally proposed as a conjecture and later understood through the gravitational replica method.

On the boundary, the Rényi entropies are computed from

$$
\operatorname{Tr}\rho_A^n
=
\frac{Z_n}{(Z_1)^n},
$$

where $Z_n$ is the path integral on an $n$-fold branched cover. In holography, at large $N$,

$$
Z_n \approx e^{-I_n^{\text{on-shell}}},
$$

where $I_n$ is the Euclidean action of a bulk saddle whose boundary is the replicated geometry.

The entanglement entropy is

$$
S_A
=
\left.\partial_n\left(I_n-nI_1\right)\right|_{n=1}
$$

up to the conventional sign inherited from $Z=e^{-I}$. In the $n\to1$ limit, the replicated geometry has a codimension-two fixed locus. Regularity of the bulk saddle enforces extremality of this locus, and differentiating the action with respect to the replica opening angle produces

$$
S_A=\frac{\operatorname{Area}}{4G_N} .
$$

This is the same mechanism that gives black-hole entropy from a conical defect. The RT surface is a generalized entropy surface, not an arbitrary geometric ornament.

## Minimal versus extremal

In a static spacetime with a time-reflection-symmetric slice, the RT surface is a minimal-area surface within that slice.

In time-dependent Lorentzian spacetimes, there may be no preferred static slice. The correct generalization is the Hubeny–Rangamani–Takayanagi prescription: use a codimension-two extremal surface in the full Lorentzian spacetime, again anchored on $\partial A$ and satisfying a homology condition.

This course treats RT first because it is easier to visualize and compute. The covariant HRT formula appears later.

## RT and black holes

In a thermal state dual to a black brane, the RT surface for a small boundary region stays near the boundary. It mostly measures vacuum-like UV entanglement.

For a large region, the surface dips deep into the bulk and can run close to the horizon. In that limit, part of the area becomes approximately

$$
\operatorname{Area}\approx \operatorname{Vol}(A)\,\frac{L^{d-1}}{z_h^{d-1}},
$$

so

$$
S_A \approx s_{\mathrm{thermal}}\operatorname{Vol}(A)+\text{boundary-law terms} .
$$

This reproduces the expected extensive thermal entropy.

For global AdS black holes, competing surfaces can lead to entanglement plateaus and phase transitions. These are geometric versions of large-$N$ changes in the dominant saddle for entanglement entropy.

## Strong subadditivity from geometry

The RT formula gives a beautiful geometric proof of strong subadditivity. The idea is that minimal surfaces for unions of regions can be cut and re-glued into candidate surfaces for other unions. Since the actual RT surface is minimal among candidates, one obtains inequalities such as

$$
S_{A\cup B} + S_{B\cup C}
\geq
S_B + S_{A\cup B\cup C} .
$$

This is not merely a consistency check. It shows that the area prescription knows about a fundamental theorem of quantum information.

Holographic entropy actually satisfies additional inequalities beyond those obeyed by arbitrary quantum states. These extra constraints reflect the special large-$N$ geometric structure of holographic states.

## What RT does not say

The RT formula is powerful, but it is not the whole story.

It does not by itself compute the full finite-$N$ entanglement entropy. The leading correction is bulk entanglement across the RT surface. Schematically,

$$
S_A
=
\frac{\operatorname{Area}(X_A)}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_A)
+
\cdots,
$$

where $X_A$ becomes a quantum extremal surface in the quantum-corrected formula.

It does not apply directly to arbitrary time-dependent situations; one must use HRT.

It does not say that all QFT entanglement entropy is geometric. The geometric prescription is a feature of holographic theories in a regime with a classical bulk dual.

It does not remove the need for renormalization. The RT area is divergent and must be regulated in a way matched to the boundary cutoff.

## Dictionary checkpoint

The RT formula adds a new kind of entry to the dictionary:

| Boundary quantity | Bulk quantity |
|---|---|
| region $A$ on a spatial slice | boundary anchor for a bulk surface |
| entangling surface $\partial A$ | boundary $\partial\gamma_A$ of the RT surface |
| entanglement entropy $S_A$ | $\operatorname{Area}(\gamma_A)/(4G_N)$ |
| short-distance area-law divergence | near-boundary area divergence |
| pure-state equality $S_A=S_{A^c}$ | homology and complementary regions |
| thermal entropy contribution | horizon area contribution |
| strong subadditivity | minimal-surface cut-and-paste inequality |
| reduced density matrix of $A$ | later: entanglement wedge of $A$ |

This is the first place in the course where geometry computes an intrinsically nonlocal QFT quantity.

## Common confusions

### “The RT surface is any surface ending on $\partial A$."

No. It must be the minimal-area surface among surfaces anchored on $\partial A$ and homologous to $A$, in the static classical case.

### “The RT formula is the same as the black-hole entropy formula.”

It uses the same area-over-$4G_N$ structure, but the surface need not be a horizon. Black-hole entropy is a special case or close cousin. RT applies to boundary subregion entanglement.

### “The homology condition is a technical detail.”

It is essential. Without it, the formula gives wrong answers in spacetimes with horizons or nontrivial topology and can fail basic entropy properties.

### “RT is finite because minimal surfaces avoid the boundary.”

They do not avoid the boundary. They are anchored at $\partial A$, so their area diverges near $z=0$. This divergence matches the UV divergence of QFT entanglement entropy.

### “The surface should always be connected.”

Not necessarily. For multiple boundary regions, the minimal homologous surface can be connected or disconnected. Transitions between these choices produce sharp large-$N$ changes in mutual information.

### “RT proves that spacetime is literally made of entanglement entropy.”

RT shows that entanglement and geometry are deeply linked in holographic theories. Turning that into a precise statement about the emergence of all spacetime data requires additional ideas: entanglement wedges, relative entropy, modular flow, bulk reconstruction, and quantum corrections.

## Exercises

### Exercise 1: The AdS$_3$ geodesic length

For the semicircle

$$
x=\frac{\ell}{2}\cos\theta,
\qquad
z=\frac{\ell}{2}\sin\theta,
$$

in the metric

$$
ds^2=\frac{L^2}{z^2}(dz^2+dx^2),
$$

show that the regularized length is

$$
\operatorname{Length}=2L\log\frac{\ell}{\epsilon}+\cdots .
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
dx=-\frac{\ell}{2}\sin\theta\,d\theta,
\qquad
 dz=\frac{\ell}{2}\cos\theta\,d\theta .
$$

Therefore

$$
dx^2+dz^2=\left(\frac{\ell}{2}\right)^2d\theta^2 .
$$

Since $z=(\ell/2)\sin\theta$,

$$
ds
=\frac{L}{z}\sqrt{dx^2+dz^2}
=\frac{L}{\sin\theta}d\theta .
$$

The cutoff $z=\epsilon$ gives $\sin\theta_\epsilon=2\epsilon/\ell$. Thus

$$
\operatorname{Length}
=2L\int_{\theta_\epsilon}^{\pi/2}\frac{d\theta}{\sin\theta}
=2L\left[\log\tan\frac{\theta}{2}\right]_{\theta_\epsilon}^{\pi/2} .
$$

For small $\theta_\epsilon$,

$$
\tan\frac{\theta_\epsilon}{2}\sim \frac{\epsilon}{\ell} .
$$

Hence

$$
\operatorname{Length}
=2L\log\frac{\ell}{\epsilon}+\cdots .
$$

</details>

### Exercise 2: Recover the CFT$_2$ coefficient

Use

$$
S_A=\frac{\operatorname{Length}}{4G_3},
\qquad
c=\frac{3L}{2G_3},
$$

to show that the interval entropy is

$$
S_A=\frac{c}{3}\log\frac{\ell}{\epsilon}+\cdots .
$$

<details>
<summary><strong>Solution</strong></summary>

Using the previous result,

$$
S_A
=\frac{1}{4G_3}\left(2L\log\frac{\ell}{\epsilon}\right)
=\frac{L}{2G_3}\log\frac{\ell}{\epsilon} .
$$

The Brown–Henneaux relation gives

$$
\frac{L}{2G_3}=\frac{c}{3} .
$$

Therefore

$$
S_A=\frac{c}{3}\log\frac{\ell}{\epsilon}+\cdots .
$$

</details>

### Exercise 3: Width of the strip

Starting from the strip area functional

$$
\operatorname{Area}
=L^{d-1}V_{d-2}\int dx\,
\frac{\sqrt{1+(z')^2}}{z^{d-1}},
$$

show that

$$
\frac{\ell}{2}
=
z_*\int_0^1du\,
\frac{u^{d-1}}{\sqrt{1-u^{2d-2}}} .
$$

<details>
<summary><strong>Solution</strong></summary>

The Lagrangian is

$$
\mathcal L=\frac{\sqrt{1+(z')^2}}{z^{d-1}} .
$$

Since it has no explicit $x$ dependence, the Hamiltonian-like quantity

$$
\mathcal L-z'\frac{\partial\mathcal L}{\partial z'}
$$

is conserved. Compute

$$
\frac{\partial\mathcal L}{\partial z'}
=\frac{z'}{z^{d-1}\sqrt{1+(z')^2}},
$$

so

$$
\mathcal L-z'\frac{\partial\mathcal L}{\partial z'}
=\frac{1}{z^{d-1}\sqrt{1+(z')^2}} .
$$

At the turning point $z=z_*$, $z'=0$, so the conserved value is $1/z_*^{d-1}$. Hence

$$
\sqrt{1+(z')^2}=\left(\frac{z_*}{z}\right)^{d-1} .
$$

Solving for $dx/dz$ gives

$$
\frac{dx}{dz}
=\frac{z^{d-1}}{\sqrt{z_*^{2d-2}-z^{2d-2}}} .
$$

Then

$$
\frac{\ell}{2}
=\int_0^{z_*}dz\,
\frac{z^{d-1}}{\sqrt{z_*^{2d-2}-z^{2d-2}}} .
$$

With $u=z/z_*$, this becomes

$$
\frac{\ell}{2}
=
z_*\int_0^1du\,
\frac{u^{d-1}}{\sqrt{1-u^{2d-2}}} .
$$

</details>

### Exercise 4: Why large regions see horizons

Explain qualitatively why the RT surface for a large region in a black-brane geometry gives an extensive thermal entropy term.

<details>
<summary><strong>Solution</strong></summary>

For a large boundary region, the minimal surface can lower its area by dipping deep into the bulk. In a black-brane geometry, the deepest accessible region is near the horizon. The surface then contains a long segment running close to the horizon, with area approximately proportional to the boundary volume of $A$ times the horizon area density. Dividing by $4G_N$ gives

$$
S_A \supset s_{\mathrm{thermal}}\operatorname{Vol}(A),
$$

which is the ordinary thermal entropy contained in the region. The remaining parts of the surface connect this near-horizon segment to the boundary and produce boundary-law contributions.

</details>

## Further reading

- S. Ryu and T. Takayanagi, [Holographic Derivation of Entanglement Entropy from AdS/CFT](https://arxiv.org/abs/hep-th/0603001).
- S. Ryu and T. Takayanagi, [Aspects of Holographic Entanglement Entropy](https://arxiv.org/abs/hep-th/0605073).
- V. E. Hubeny, M. Rangamani, and T. Takayanagi, [A Covariant Holographic Entanglement Entropy Proposal](https://arxiv.org/abs/0705.0016).
- A. Lewkowycz and J. Maldacena, [Generalized Gravitational Entropy](https://arxiv.org/abs/1304.4926).
- H. Casini, M. Huerta, and R. C. Myers, [Towards a Derivation of Holographic Entanglement Entropy](https://arxiv.org/abs/1102.0440).
- M. Headrick and T. Takayanagi, [A Holographic Proof of the Strong Subadditivity of Entanglement Entropy](https://arxiv.org/abs/0704.3719).
