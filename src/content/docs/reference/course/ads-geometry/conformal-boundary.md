---
title: "The Conformal Boundary of AdS"
description: "Why the AdS boundary is a conformal boundary, how boundary metrics arise from conformal compactification, and why holographic sources are defined only after choosing a conformal frame."
sidebar:
  order: 30
---

The boundary of AdS is not a wall sitting at finite proper distance. It is an asymptotic boundary reached only after a conformal compactification. This single sentence hides one of the most important technical points in AdS/CFT:

$$
\text{the boundary metric is not unique; only its conformal class is intrinsic.}
$$

That is exactly what one should expect for a CFT. A conformal field theory is naturally coupled not to a preferred metric $g_{(0)ij}$, but to a conformal structure $[g_{(0)}]$, where

$$
g_{(0)ij}\sim e^{2\sigma(x)}g_{(0)ij}.
$$

In computations, however, we usually choose one representative $g_{(0)ij}$. That choice is called a **conformal frame**. Poincaré AdS chooses a flat frame. Global AdS chooses the cylinder frame. Fefferman–Graham coordinates choose a near-boundary frame adapted to sources, counterterms, and one-point functions.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A schematic of conformal compactification in AdS: the physical metric has its boundary at infinite proper distance, while the compactified metric places the boundary at finite distance and determines only a conformal class of boundary metrics.](/figures/course/ads-conformal-boundary.svg)

<figcaption>

The physical AdS metric $g$ has the boundary at infinite proper distance. Multiplying by a defining function $\Omega^2$ gives a compactified metric $\bar g=\Omega^2 g$ that is finite at $\Omega=0$. Different choices of $\Omega$ rescale the induced boundary metric, so the intrinsic boundary datum is the conformal class $[g_{(0)}]$.

</figcaption>
</figure>

## Why this matters

The conformal boundary is where the boundary quantum field theory lives. More precisely, the CFT lives on a $d$-dimensional spacetime equipped with the conformal structure induced by the asymptotic bulk metric.

This affects almost every part of the dictionary:

| Bulk statement | Boundary interpretation |
|---|---|
| choose a conformal compactification | choose a conformal frame for the CFT |
| choose boundary metric representative $g_{(0)ij}$ | choose the source for $T^{ij}$ |
| change defining function $\Omega\to e^\omega\Omega$ | perform a boundary Weyl transformation |
| put a cutoff surface at $z=\epsilon$ | introduce a UV regulator in the CFT |
| remove the cutoff with counterterms | renormalize the CFT generating functional |

The point is not cosmetic. A calculation done on $\mathbb R^{1,d-1}$ and a calculation done on $\mathbb R\times S^{d-1}$ are related by conformal maps only when the theory, state, and insertions are transformed correctly. The conformal boundary tells us what the boundary spacetime is, what the sources are, and what it means to compare two coordinate systems.

## The Poincaré example

Start with the Poincaré metric on $\mathrm{AdS}_{d+1}$:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+\eta_{ij}dx^i dx^j
\right),
\qquad
z>0,
$$

where

$$
\eta_{ij}=\mathrm{diag}(-,+,\ldots,+).
$$

The boundary is usually said to be at $z=0$. But the proper radial distance from $z=z_0$ to $z=\epsilon$ is

$$
\ell(\epsilon,z_0)
=
\int_\epsilon^{z_0}\frac{L}{z}\,dz
=
L\log\frac{z_0}{\epsilon}.
$$

As $\epsilon\to 0$, this diverges. So the boundary is infinitely far away in the physical metric.

Nevertheless, the metric has a simple divergent conformal factor. Define

$$
\Omega=\frac{z}{L},
\qquad
\bar g=\Omega^2 g.
$$

Then

$$
d\bar s^2
=
\Omega^2 ds^2
=
 dz^2+\eta_{ij}dx^i dx^j.
$$

This compactified metric is perfectly finite at $z=0$. Its restriction to tangent vectors along $z=0$ gives

$$
ds^2_{\partial}=\eta_{ij}dx^i dx^j.
$$

Thus the Poincaré patch presents the CFT on flat Minkowski space $\mathbb R^{1,d-1}$.

The important word is **presents**. The bulk metric did not come with a uniquely normalized boundary metric. We got $\eta_{ij}$ because we chose the defining function $\Omega=z/L$.

## Defining functions and conformal compactification

Let $M$ be the physical bulk spacetime and let $\bar M$ be a manifold with boundary such that

$$
M=\mathrm{int}(\bar M),
\qquad
\partial \bar M\neq\varnothing.
$$

A smooth function $\Omega$ on $\bar M$ is called a **defining function** for the boundary if

$$
\Omega>0\quad\text{inside }M,
\qquad
\Omega=0\quad\text{on }\partial\bar M,
\qquad
d\Omega\neq 0\quad\text{on }\partial\bar M.
$$

A metric $g$ is **conformally compact** if

$$
\bar g=\Omega^2 g
$$

extends smoothly enough to $\partial\bar M$ and is nondegenerate there, except for the expected Lorentzian signature structure.

The induced metric on the boundary is obtained by restricting $\bar g$ to vectors tangent to $\partial\bar M$:

$$
g_{(0)}=\bar g\big|_{T\partial\bar M}.
$$

But $\Omega$ is not unique. If $\omega$ is smooth near the boundary, then

$$
\Omega'=e^{\omega}\Omega
$$

is also a defining function. The corresponding compactified metric is

$$
\bar g'=(\Omega')^2g=e^{2\omega}\bar g.
$$

Restricting to the boundary gives

$$
g'_{(0)ij}=e^{2\omega_{(0)}(x)}g_{(0)ij},
\qquad
\omega_{(0)}(x)=\omega\big|_{\partial\bar M}.
$$

Therefore the intrinsic datum at the boundary is not $g_{(0)ij}$ itself. It is the equivalence class

$$
[g_{(0)}]
=
\left\{e^{2\sigma(x)}g_{(0)}\right\}.
$$

This is the precise sense in which AdS has a **conformal boundary**.

## Exact AdS in global compactified coordinates

The global AdS metric can be written as

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2
+d\rho^2
+\sinh^2\rho\,d\Omega_{d-1}^2
\right).
$$

The boundary is at $\rho\to\infty$. To make the conformal boundary visible, introduce

$$
r=L\sinh\rho,
\qquad
r=L\tan\chi,
\qquad
0\le \chi<\frac{\pi}{2}.
$$

Then the metric becomes

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

The boundary is now at

$$
\chi=\frac{\pi}{2}.
$$

Choosing

$$
\Omega=\cos\chi
$$

gives the compactified metric

$$
d\bar s^2
=
L^2\left(
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

Restricting to $\chi=\pi/2$ gives

$$
d\bar s^2\big|_{\partial}
=
L^2\left(-d\tau^2+d\Omega_{d-1}^2\right).
$$

Up to the overall factor $L^2$, the boundary is the cylinder

$$
\mathbb R_\tau\times S^{d-1}.
$$

This is why global AdS is naturally dual to the CFT quantized on the cylinder.

The factor $L^2$ in the boundary metric is not sacred. We may absorb it by a constant Weyl rescaling, or use physical time $t=L\tau$ to write

$$
ds^2_{\partial}=-dt^2+L^2d\Omega_{d-1}^2.
$$

Both descriptions represent the same boundary conformal structure, but they use different normalizations of time and energy.

## Poincaré frame versus cylinder frame

The Poincaré patch gives the boundary metric

$$
ds^2_{\partial}=\eta_{ij}dx^i dx^j,
$$

while global AdS gives

$$
ds^2_{\partial}=-d\tau^2+d\Omega_{d-1}^2.
$$

These are not unrelated. The Lorentzian cylinder is the natural conformal compactification of Minkowski space. In radial quantization, a flat-space CFT on $\mathbb R^d$ is mapped to the cylinder by writing, in Euclidean signature,

$$
r=e^\tau,
\qquad
\delta_{ij}dx^i dx^j=dr^2+r^2d\Omega_{d-1}^2
=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

The flat metric and the cylinder metric differ by a Weyl factor. For an ordinary massive QFT, this would change the theory in an essential way. For a CFT, it is a change of conformal frame, up to possible anomalies and global subtleties.

This is the boundary counterpart of the statement that Poincaré and global coordinates are different ways of presenting AdS. They make different conformal frames manifest.

## Cutoff surfaces and the UV/IR relation

Holographic computations are usually regulated by cutting off the bulk near the boundary. In Poincaré coordinates, put the cutoff surface at

$$
z=\epsilon.
$$

The induced metric on this surface is

$$
h_{ij}(\epsilon)
=
\frac{L^2}{\epsilon^2}\eta_{ij}.
$$

This diverges as $\epsilon\to 0$. The finite boundary metric is recovered by rescaling:

$$
\gamma_{ij}(\epsilon)
=
\frac{\epsilon^2}{L^2}h_{ij}(\epsilon)
=\eta_{ij}.
$$

In a more general asymptotically AdS metric, the same idea becomes

$$
g_{(0)ij}
=
\lim_{\epsilon\to 0}\frac{\epsilon^2}{L^2}h_{ij}(\epsilon).
$$

The surface $z=\epsilon$ is not just a geometric regulator. In the boundary theory it corresponds to a UV regulator. Roughly,

$$
\text{small }z
\quad\longleftrightarrow\quad
\text{high energy / short distance}.
$$

The infinite AdS volume near $z=0$ is therefore the bulk avatar of boundary UV divergences. Holographic renormalization is the systematic procedure of adding local counterterms on the cutoff surface and then taking $\epsilon\to 0$.

## Fefferman–Graham form

Near the conformal boundary, many asymptotically AdS metrics can be written in Fefferman–Graham gauge:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+g_{ij}(z,x)dx^i dx^j
\right).
$$

The boundary is at $z=0$, and the boundary metric representative is

$$
g_{(0)ij}(x)=g_{ij}(0,x).
$$

For solutions of Einstein's equations with negative cosmological constant, the near-boundary expansion has the schematic form

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)
+z^2g_{(2)ij}(x)
+\cdots
+z^d g_{(d)ij}(x)
+\cdots.
$$

When the boundary dimension $d$ is even, logarithmic terms may appear:

$$
g_{ij}(z,x)
=
\cdots
+z^d\log z^2\,h_{(d)ij}(x)
+z^d g_{(d)ij}(x)
+\cdots.
$$

The coefficients below order $z^d$ are locally determined by the source metric $g_{(0)ij}$ through the bulk equations of motion. The coefficient $g_{(d)ij}$ contains state-dependent information and is related, after renormalization, to the CFT stress tensor expectation value:

$$
g_{(d)ij}
\quad\leadsto\quad
\langle T_{ij}\rangle.
$$

This is the gravitational version of a general QFT principle: sources determine allowed local counterterms and Ward identities, but expectation values contain additional dynamical information about the state.

## The boundary metric is a source

In QFT, the stress tensor is defined by varying the generating functional with respect to the background metric. Schematically,

$$
\delta W[g_{(0)}]
=
\frac{1}{2}\int d^dx\sqrt{|g_{(0)}|}\,
\langle T^{ij}\rangle\,\delta g_{(0)ij}.
$$

Thus $g_{(0)ij}$ is the source for $T^{ij}$.

In AdS/CFT, $g_{(0)ij}$ is extracted from the leading asymptotic behavior of the bulk metric. Therefore,

$$
\text{leading boundary behavior of }g_{\mu\nu}
\quad\longleftrightarrow\quad
\text{source for }T^{ij}.
$$

The expectation value $\langle T^{ij}\rangle$ is not obtained just by reading off the leading divergence. It requires the renormalized Brown–York stress tensor, including local counterterms. That will be developed later in the holographic renormalization unit.

For now, the main point is simple: choosing a boundary conformal frame is choosing the background geometry on which the CFT generating functional is evaluated.

## Weyl transformations and source weights

Suppose a scalar primary operator $\mathcal O$ has scaling dimension $\Delta$, and the CFT action is deformed by

$$
\int d^dx\sqrt{|g_{(0)}|}\,J\mathcal O.
$$

Under a Weyl transformation

$$
g_{(0)ij}\to e^{2\sigma}g_{(0)ij},
$$

a primary transforms as

$$
\mathcal O\to e^{-\Delta\sigma}\mathcal O.
$$

Since

$$
\sqrt{|g_{(0)}|}\to e^{d\sigma}\sqrt{|g_{(0)}|},
$$

the source must transform as

$$
J\to e^{-(d-\Delta)\sigma}J
$$

for the source term to be Weyl invariant.

This explains why the leading coefficient of a bulk scalar field is not just a scalar under changes of conformal frame. If

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)+z^\Delta A(x)+\cdots,
$$

then $\phi_{(0)}$ is a source of Weyl weight $d-\Delta$. Changing the defining function changes the way the same bulk solution is decomposed into source and response.

This is one reason holographic computations must keep track of the chosen conformal frame.

## Weyl anomaly

Classically, a CFT is invariant under local Weyl transformations. Quantum mechanically, the generating functional can fail to be Weyl invariant when the boundary dimension $d$ is even. Then one has a conformal anomaly:

$$
W[e^{2\sigma}g_{(0)}]
=
W[g_{(0)}]
+\mathcal A_\sigma[g_{(0)}].
$$

In holography, this anomaly appears through logarithmic terms in the near-boundary expansion and logarithmic divergences in the regulated on-shell action. This is not a bug in the dictionary. It is one of its strongest checks: the bulk computation reproduces the CFT Weyl anomaly.

For odd boundary dimension $d$, there is no local Weyl anomaly of this type, although finite quantities can still depend on global choices and on the renormalization scheme.

## Asymptotically AdS versus exactly AdS

Exact AdS is maximally symmetric. Its boundary conformal class is conformally flat. But holography is not limited to exact AdS.

A spacetime is often called **asymptotically locally AdS**, or AlAdS, if near the boundary it approaches AdS in the conformal compactification sense. In Fefferman–Graham form this means, roughly,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+g_{(0)ij}(x)dx^i dx^j+O(z^2)
\right).
$$

The boundary metric $g_{(0)ij}(x)$ need not be flat. It can be a curved Lorentzian metric. On the CFT side, this means the theory is placed on a curved background spacetime.

This generalization is essential for:

- computing the stress tensor by varying the boundary metric;
- studying CFTs on curved spaces such as $S^{d-1}\times\mathbb R$;
- deriving Ward identities and conformal anomalies;
- treating black holes whose boundary geometry is not simply flat Minkowski space;
- defining holographic renormalization covariantly.

Terminology varies slightly across the literature. Some authors distinguish “asymptotically AdS” from “asymptotically locally AdS” depending on the allowed boundary conformal structure and falloff conditions. In this course, the important operational idea is the conformal compactification: the bulk metric has a controlled asymptotic form, and the boundary data define a CFT source geometry.

## The boundary is timelike

In Lorentzian AdS, the conformal boundary is timelike. This is very different from asymptotically flat spacetime, where future and past null infinity play a central role.

Because the AdS boundary is timelike, signals can reach it and return in finite global time after imposing reflecting boundary conditions. For example, a radial null ray in global AdS satisfies

$$
0=-d\tau^2+d\chi^2,
$$

in compactified coordinates, so it reaches the boundary $\chi=\pi/2$ from the center $\chi=0$ in

$$
\Delta\tau=\frac{\pi}{2}.
$$

This is why boundary conditions in AdS are part of the physical definition of the problem. In the holographic dictionary, those boundary conditions become sources and choices of state in the boundary theory.

## What about $z\to\infty$?

In Poincaré coordinates, students often see two special places:

$$
z=0,
\qquad
z\to\infty.
$$

Only $z=0$ is the conformal boundary of the Poincaré patch. The region $z\to\infty$ is the deep interior of the Poincaré patch. In Lorentzian signature, it is associated with a Poincaré horizon, not another copy of the CFT spacetime.

In Euclidean signature, hyperbolic space $H^{d+1}$ can be represented as the upper half-space with boundary $z=0$, but the full conformal boundary is $S^d$. The point at infinity in the upper half-space completes $\mathbb R^d$ to $S^d$.

So the safe statement is:

$$
\text{the conformal boundary is defined by compactification, not by guessing from coordinate limits.}
$$

A coordinate limit can be a boundary, a horizon, a coordinate artifact, or a singularity. The conformal compactification tells us which one it is.

## Boundary diffeomorphisms and Weyl transformations

Bulk diffeomorphism invariance is not lost at the boundary. Diffeomorphisms that act nontrivially on the boundary become transformations of the CFT sources.

Near the boundary, bulk diffeomorphisms preserving Fefferman–Graham gauge include transformations that act as

$$
g_{(0)ij}\to e^{2\sigma(x)}g_{(0)ij}
$$

on the boundary representative. These are often called Penrose–Brown–Henneaux transformations in the AdS context.

The conceptual message is:

$$
\text{bulk gauge redundancy near infinity}
\quad\longleftrightarrow\quad
\text{boundary diffeomorphism and Weyl structure}.
$$

This is the geometric origin of the CFT Ward identities. Boundary diffeomorphism invariance gives stress-tensor conservation, while Weyl transformations give the trace Ward identity, including possible anomalies.

## Dictionary checkpoint

After this page, the following entries should feel precise:

| Boundary concept | Bulk concept |
|---|---|
| boundary spacetime | conformal boundary $\partial\bar M$ |
| boundary metric representative $g_{(0)ij}$ | induced metric of $\bar g=\Omega^2g$ at $\Omega=0$ |
| boundary conformal class $[g_{(0)}]$ | freedom to choose defining function $\Omega$ |
| Weyl transformation | change of conformal representative $g_{(0)}\to e^{2\sigma}g_{(0)}$ |
| stress-tensor source | leading asymptotic metric coefficient $g_{(0)ij}$ |
| CFT UV cutoff | radial cutoff surface $z=\epsilon$ |
| Weyl anomaly | logarithmic divergence/log term in holographic renormalization |

The boundary is not a finite material wall. It is the place where the conformally rescaled bulk metric has a finite induced conformal structure. That conformal structure is the geometric background of the CFT.

## Common confusions

### “The CFT lives at $z=0$ in the physical metric.”

The phrase is useful but imprecise. In the physical metric, $z=0$ is infinitely far away and the metric diverges. The CFT lives on the conformal boundary obtained after rescaling the metric by a defining function.

### “The boundary metric is $\eta_{ij}$.”

Only in the Poincaré conformal frame. Global AdS gives a cylinder frame, and more general asymptotically AdS solutions can have curved boundary metric representatives. The intrinsic data are conformal.

### “Changing the conformal frame is just a harmless convention.”

Often it is, but not always. Operators and sources transform with Weyl weights, states may transform nontrivially, and even-dimensional CFTs can have Weyl anomalies. A formula correct in the flat frame may need factors of the Weyl scale in another frame.

### “The radial cutoff is an IR cutoff because it cuts off the bulk.”

Near the AdS boundary, the radial cutoff is a UV cutoff in the boundary theory. Small $z$ corresponds to high energy. The phrase “UV/IR relation” means that the same radial direction can look infrared or ultraviolet depending on which side of the duality one is emphasizing.

### “$z\to\infty$ is another boundary.”

In Lorentzian Poincaré AdS, $z\to\infty$ is the deep interior of the Poincaré patch and is related to a horizon, not an independent CFT boundary. The conformal boundary is identified by the conformal compactification.

## Exercises

### Exercise 1: Infinite distance to the Poincaré boundary

For the Poincaré metric

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+\eta_{ij}dx^i dx^j\right),
$$

compute the proper radial distance from $z=z_0$ to $z=\epsilon$. What happens as $\epsilon\to 0$?

<details>
<summary><strong>Solution</strong></summary>

Along a radial curve with fixed $x^i$,

$$
ds=\frac{L}{z}dz.
$$

Thus

$$
\ell(\epsilon,z_0)
=
\int_\epsilon^{z_0}\frac{L}{z}\,dz
=
L\log\frac{z_0}{\epsilon}.
$$

As $\epsilon\to 0$, this diverges. The Poincaré boundary is therefore at infinite proper distance in the physical AdS metric.

</details>

### Exercise 2: Compactifying Poincaré AdS

Take

$$
\Omega=\frac{z}{L}.
$$

Show that $\bar g=\Omega^2g$ extends smoothly to $z=0$, and find the induced boundary metric.

<details>
<summary><strong>Solution</strong></summary>

Multiplying by $\Omega^2=z^2/L^2$ gives

$$
d\bar s^2
=
\frac{z^2}{L^2}\frac{L^2}{z^2}
\left(dz^2+\eta_{ij}dx^i dx^j\right)
=
dz^2+\eta_{ij}dx^i dx^j.
$$

This is finite at $z=0$. Restricting to tangent vectors along the boundary means setting $dz=0$, so

$$
ds^2_{\partial}=\eta_{ij}dx^i dx^j.
$$

Thus this defining function chooses the flat Minkowski representative of the boundary conformal class.

</details>

### Exercise 3: Global AdS boundary cylinder

Starting from

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+\frac{dr^2}{1+r^2/L^2}
+r^2d\Omega_{d-1}^2,
$$

set $t=L\tau$ and $r=L\tan\chi$. Show that the conformal boundary is $\mathbb R\times S^{d-1}$.

<details>
<summary><strong>Solution</strong></summary>

With $r=L\tan\chi$,

$$
1+\frac{r^2}{L^2}=1+\tan^2\chi=\sec^2\chi,
$$

and

$$
dr=L\sec^2\chi\,d\chi.
$$

Therefore

$$
\frac{dr^2}{1+r^2/L^2}
=
\frac{L^2\sec^4\chi\,d\chi^2}{\sec^2\chi}
=
L^2\sec^2\chi\,d\chi^2.
$$

Also,

$$
r^2d\Omega_{d-1}^2
=L^2\tan^2\chi\,d\Omega_{d-1}^2
=L^2\sec^2\chi\,\sin^2\chi\,d\Omega_{d-1}^2.
$$

Since $t=L\tau$,

$$
-\left(1+\frac{r^2}{L^2}\right)dt^2
=-L^2\sec^2\chi\,d\tau^2.
$$

Thus

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

Multiplying by $\Omega^2=\cos^2\chi$ and restricting to $\chi=\pi/2$ gives

$$
d\bar s^2\big|_{\partial}
=L^2\left(-d\tau^2+d\Omega_{d-1}^2\right).
$$

Therefore the boundary conformal structure is that of the cylinder $\mathbb R\times S^{d-1}$.

</details>

### Exercise 4: Non-uniqueness of the boundary metric

Let $\Omega'=e^\omega\Omega$ be another defining function. Show that the boundary metric changes by a Weyl transformation.

<details>
<summary><strong>Solution</strong></summary>

The compactified metrics are related by

$$
\bar g'=(\Omega')^2g=e^{2\omega}\Omega^2g=e^{2\omega}\bar g.
$$

Restricting to the boundary gives

$$
g'_{(0)ij}=e^{2\omega_{(0)}}g_{(0)ij},
\qquad
\omega_{(0)}=\omega|_{\partial\bar M}.
$$

Thus different defining functions choose different representatives of the same boundary conformal class.

</details>

### Exercise 5: Weyl weight of a scalar source

A scalar primary $\mathcal O$ has dimension $\Delta$, and the source term is

$$
\int d^dx\sqrt{|g|}\,J\mathcal O.
$$

If $g_{ij}\to e^{2\sigma}g_{ij}$ and $\mathcal O\to e^{-\Delta\sigma}\mathcal O$, how must $J$ transform for the source term to be Weyl invariant?

<details>
<summary><strong>Solution</strong></summary>

The volume form transforms as

$$
\sqrt{|g|}\to e^{d\sigma}\sqrt{|g|}.
$$

The operator transforms as

$$
\mathcal O\to e^{-\Delta\sigma}\mathcal O.
$$

For the product $\sqrt{|g|}J\mathcal O$ to be invariant, $J$ must transform as

$$
J\to e^{-(d-\Delta)\sigma}J.
$$

Thus the source has Weyl weight $d-\Delta$.

</details>

## Further reading

- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
