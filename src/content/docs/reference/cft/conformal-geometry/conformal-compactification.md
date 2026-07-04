---
title: "Conformal Compactification and the Cylinder"
description: "How flat space becomes a patch of the Einstein cylinder, why dilatations become cylinder time translations, and why global AdS has a cylindrical boundary."
sidebar:
  order: 3
---

Conformal field theory is not naturally tied to one particular metric. It is naturally tied to a **conformal class** of metrics,

$$
[g]=\{e^{2\sigma(x)}g\},
$$

at least when we discuss local separated correlators and ignore anomaly subtleties for the moment. This is why CFT can move so efficiently between flat space, spheres, cylinders, and compactified spacetimes.

This page explains one of the most important geometric moves in the subject:

$$
\text{flat space}
\quad \longrightarrow \quad
\text{compactified space}
\quad \longrightarrow \quad
\text{cylinder}.
$$

For AdS/CFT, this is not optional decoration. The conformal boundary of global $\mathrm{AdS}_{d+1}$ is the cylinder

$$
\mathbb R_T\times S^{d-1}.
$$

So a CFT that is first introduced on $\mathbb R^{1,d-1}$ must also know how to live on $\mathbb R\times S^{d-1}$. The map between these two descriptions is the geometric origin of the state-operator correspondence and of the statement that scaling dimensions become energies on the cylinder.

## What conformal compactification means

A compactification usually adds points at infinity. A **conformal compactification** does this while preserving the causal and angular structure. More precisely, one embeds a noncompact spacetime with metric $g$ into a larger spacetime with metric $\hat g$ such that

$$
g=\Omega^{-2}\hat g
$$

on the original region, with $\Omega=0$ at the added boundary. Since multiplying the metric by a nonzero function does not change null directions, a conformal compactification keeps light cones intact.

For a general QFT, this would be a violent operation. For a CFT, it is natural, because Weyl rescalings are part of the geometric language of the theory. This is why CFT correlation functions can often be transported from flat space to a sphere or cylinder by simple Weyl factors.

The important warning is that the compactified space is not simply “the same metric with infinity drawn closer.” It is a different representative of the same conformal structure. The CFT is allowed to compare them because it is conformal.

## Euclidean warm-up: $\mathbb R^d$ and $S^d$

Euclidean flat space has a simple one-point conformal compactification:

$$
\mathbb R^d\cup\{\infty\}\simeq S^d.
$$

This is the stereographic projection. Let $X^A$, $A=1,\ldots,d+1$, be coordinates on a unit sphere embedded in $\mathbb R^{d+1}$,

$$
\sum_{A=1}^{d+1}(X^A)^2=1.
$$

Stereographic coordinates $x^\mu\in\mathbb R^d$ may be chosen as

$$
X^\mu=\frac{2x^\mu}{1+x^2},
\qquad
X^{d+1}=\frac{1-x^2}{1+x^2},
$$

where

$$
x^2=\sum_{\mu=1}^d (x^\mu)^2.
$$

The round sphere metric becomes

$$
ds_{S^d}^2
=
\frac{4\,dx^\mu dx_\mu}{(1+x^2)^2}.
$$

Thus

$$
ds_{S^d}^2=e^{2\sigma(x)}ds_{\mathbb R^d}^2,
\qquad
 e^{\sigma(x)}=\frac{2}{1+x^2}.
$$

A scalar primary of dimension $\Delta$ transforms under a Weyl rescaling as

$$
\mathcal O_{e^{2\sigma}g}(x)
=
e^{-\Delta\sigma(x)}\mathcal O_g(x),
$$

up to the standard caveat that anomalies can affect the generating functional and contact terms in even dimensions. Therefore separated scalar correlators on the sphere are related to flat-space correlators by

$$
\left\langle \prod_i \mathcal O_i(x_i)\right\rangle_{S^d}
=
\prod_i e^{-\Delta_i\sigma(x_i)}
\left\langle \prod_i \mathcal O_i(x_i)\right\rangle_{\mathbb R^d}.
$$

For example, if

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle_{\mathbb R^d}
=
\frac{C_{\mathcal O}}{|x_1-x_2|^{2\Delta}},
$$

then the sphere two-point function is

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle_{S^d}
=
C_{\mathcal O}
\left[
\frac{(1+x_1^2)(1+x_2^2)}{4|x_1-x_2|^2}
\right]^\Delta.
$$

The bracket is the inverse square chordal distance on the sphere. So the flat-space power law is not lost; it is rewritten in a compact geometry.

## Radial quantization and the Euclidean cylinder

There is another Euclidean map that is even more important for operator theory. Write a point in $\mathbb R^d$ as

$$
x^\mu=r n^\mu,
\qquad
n^\mu n_\mu=1,
\qquad
r>0.
$$

Introduce logarithmic radius

$$
\tau=\log r.
$$

Then the flat metric becomes

$$
ds_{\mathbb R^d}^2
=dr^2+r^2d\Omega_{d-1}^2
=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

After the Weyl rescaling by $e^{-2\tau}$, flat space minus the origin becomes the Euclidean cylinder

$$
\mathbb R^d\setminus\{0\}
\quad\sim_{\text{Weyl}}\quad
\mathbb R_\tau\times S^{d-1}.
$$

This is the geometric basis of **radial quantization**. Equal-radius spheres in flat space become equal-time slices on the cylinder. The dilatation generator

$$
D=x^\mu\partial_\mu=r\partial_r
$$

becomes

$$
D=\partial_\tau.
$$

So dilatations in flat space become time translations on the Euclidean cylinder. After analytic continuation to Lorentzian cylinder time, this is the statement

$$
H_{\mathrm{cyl}}=D
$$

for a unit-radius sphere. If the sphere has radius $R$, then

$$
H_{\mathrm{cyl}}=\frac{D}{R}.
$$

A primary operator of scaling dimension $\Delta$ therefore creates a cylinder state with energy

$$
E_{\mathcal O}=\frac{\Delta}{R}.
$$

Descendants created by derivatives have energies

$$
E=\frac{\Delta+n}{R},
\qquad n=0,1,2,\ldots.
$$

This is why the discrete spectrum of a CFT on $S^{d-1}$ is the same information as the list of operator dimensions in flat space.

## Lorentzian compactification of Minkowski space

Now consider Lorentzian flat space $\mathbb R^{1,d-1}$ with spherical spatial coordinates,

$$
ds^2=-dt^2+dr^2+r^2d\Omega_{d-2}^2,
\qquad r\geq 0.
$$

Introduce null coordinates

$$
u=t-r,
\qquad
v=t+r.
$$

Then

$$
ds^2=-du\,dv+\frac{(v-u)^2}{4}d\Omega_{d-2}^2.
$$

To bring infinity to a finite coordinate location, define

$$
u=\tan U,
\qquad
v=\tan V,
$$

with

$$
-\frac{\pi}{2}<U<\frac{\pi}{2},
\qquad
-\frac{\pi}{2}<V<\frac{\pi}{2}.
$$

Finally set

$$
T=U+V,
\qquad
\chi=V-U.
$$

A short computation gives

$$
ds^2
=
\frac{1}{4\cos^2U\cos^2V}
\left(
-dT^2+d\chi^2+\sin^2\chi\,d\Omega_{d-2}^2
\right).
$$

The metric in parentheses is the metric on the Einstein static universe,

$$
ds_{\mathrm{Ein}}^2=-dT^2+d\Omega_{d-1}^2,
$$

where

$$
d\Omega_{d-1}^2=d\chi^2+\sin^2\chi\,d\Omega_{d-2}^2.
$$

Thus Minkowski space is conformal to a finite region of the cylinder

$$
\mathbb R_T\times S^{d-1}.
$$

The region is determined by

$$
0\leq \chi<\pi,
\qquad
|T|+\chi<\pi.
$$

Its boundary consists of future timelike infinity $i^+$, past timelike infinity $i^-$, spatial infinity $i^0$, and future and past null infinity $\mathcal I^+$ and $\mathcal I^-$.

<figure class="doc-figure" style="--figure-width: 28rem; --caption-width: 52rem;">

![Radial Penrose diagram of conformally compactified Minkowski space](/figures/cft/conformal-compactification-penrose.svg)

<figcaption>

A radial Penrose diagram for $d$-dimensional Minkowski space. The coordinates $u=t-r$ and $v=t+r$ are compactified by $u=\tan U$ and $v=\tan V$, then $T=U+V$ and $\chi=V-U$. The physical Minkowski region is $0\leq\chi<\pi$ and $|T|+\chi<\pi$, a finite part of the Einstein cylinder $\mathbb R_T\times S^{d-1}$.

</figcaption>
</figure>

The essential feature is that null lines remain at $45^\circ$ in the $(T,\chi)$ diagram. This is exactly what conformal transformations are supposed to preserve: not lengths, but light cones.

## The compactified space and the universal cover

The global conformal group acts most naturally on the compactified spacetime, not on the affine patch $\mathbb R^{1,d-1}$ alone. This matters because inversions and special conformal transformations can send finite points to infinity.

A very clean way to describe the compactification is to use the projective null cone in $\mathbb R^{d,2}$:

$$
X^2=0,
\qquad
X^A\sim \lambda X^A,
\qquad \lambda\neq 0.
$$

This is the geometric construction behind the embedding-space formalism of the next page. Topologically, the compactified Lorentzian space is

$$
\frac{S^{d-1}\times S^1}{\mathbb Z_2}.
$$

For physics, one often passes to the universal cover

$$
S^{d-1}\times \mathbb R.
$$

This avoids periodic time. The same move appears for global AdS: the hyperboloid in $\mathbb R^{d,2}$ has closed timelike curves if one keeps the original periodic time, so the physical spacetime used in AdS/CFT is usually the universal covering space. Its boundary is also

$$
S^{d-1}\times \mathbb R.
$$

This is one reason the cylinder is not merely a calculational trick. It is the natural global home of the boundary theory dual to global AdS.

## Cylinder correlators from flat-space correlators

The radial map gives a useful formula for correlators on the cylinder. Let

$$
x_i=e^{\tau_i}n_i,
\qquad n_i\in S^{d-1}.
$$

A scalar primary transforms as

$$
\mathcal O_{\mathrm{cyl}}(\tau,n)
=e^{\Delta\tau}\mathcal O_{\mathbb R^d}(x).
$$

For a normalized scalar primary with flat-space two-point function

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
=\frac{1}{|x_1-x_2|^{2\Delta}},
$$

the Euclidean cylinder two-point function is

$$
\langle \mathcal O_{\mathrm{cyl}}(\tau_1,n_1)
\mathcal O_{\mathrm{cyl}}(\tau_2,n_2)\rangle
=
\frac{1}{\left[2\left(\cosh(\tau_{12})-n_1\cdot n_2\right)\right]^\Delta},
$$

where

$$
\tau_{12}=\tau_1-\tau_2.
$$

To see this, use

$$
|x_1-x_2|^2
=e^{\tau_1+\tau_2}
\left[2\left(\cosh\tau_{12}-n_1\cdot n_2\right)\right].
$$

The Weyl factors $e^{\Delta\tau_i}$ precisely cancel the overall $e^{\tau_1+\tau_2}$ dependence. This cancellation is why cylinder correlators depend only on cylinder time differences and angular separations.

For large Euclidean time separation $\tau_{12}\to +\infty$, the correlator behaves as

$$
\langle \mathcal O_{\mathrm{cyl}}(\tau_1,n_1)
\mathcal O_{\mathrm{cyl}}(\tau_2,n_2)\rangle
\sim e^{-\Delta\tau_{12}}.
$$

This is exactly the spectral behavior of a state of cylinder energy $\Delta$.

## From flat-space vacuum to cylinder quantization

Radial quantization foliates Euclidean flat space by spheres. The sphere at radius $r$ becomes a time slice at $\tau=\log r$. The origin $r=0$ becomes the far past of the cylinder, and infinity becomes the far future:

$$
r=0\quad \leftrightarrow\quad \tau=-\infty,
$$

$$
r=\infty\quad \leftrightarrow\quad \tau=+\infty.
$$

Inserting a local operator at the origin prepares a state on a surrounding sphere:

$$
\mathcal O(0)|0\rangle
\quad \longleftrightarrow \quad
|\mathcal O\rangle_{S^{d-1}}.
$$

This is the state-operator correspondence. We will develop it fully later, but its geometry is already clear here. A local insertion at $r=0$ becomes an initial condition in the infinite cylinder past.

The vacuum on flat space maps to a distinguished cylinder state. In even dimensions there can be a Weyl-anomaly-induced Casimir energy on the cylinder. This does not spoil the state-operator map; it only means that one must be clear about the zero of the cylinder Hamiltonian. In many CFT conventions, the energy of a primary state relative to the vacuum is still $\Delta/R$.

## Why this is the boundary of global AdS

Global $\mathrm{AdS}_{d+1}$ may be written as

$$
ds_{\mathrm{AdS}}^2
=\frac{R^2}{\cos^2\rho}
\left(
-dT^2+d\rho^2+\sin^2\rho\,d\Omega_{d-1}^2
\right),
$$

with

$$
0\leq \rho<\frac{\pi}{2}.
$$

The conformal boundary lies at

$$
\rho\to \frac{\pi}{2}.
$$

Multiplying the bulk metric by $\cos^2\rho/R^2$ and taking the boundary limit gives the boundary conformal metric

$$
ds_{\partial\mathrm{AdS}}^2
=-dT^2+d\Omega_{d-1}^2.
$$

Therefore the natural spacetime of the boundary CFT in global AdS/CFT is

$$
\mathbb R_T\times S^{d-1}.
$$

This is exactly the cylinder obtained by conformally compactifying Minkowski space. In the Poincare patch, the boundary looks like $\mathbb R^{1,d-1}$. In global AdS, the boundary is the full cylinder. These are not different CFTs; they are different conformal frames and different global patches.

This gives a useful dictionary entry:

| CFT geometry | Bulk interpretation |
|---|---|
| $\mathbb R^{1,d-1}$ | Poincare boundary patch |
| $\mathbb R\times S^{d-1}$ | global AdS boundary |
| dilatation $D$ | cylinder Hamiltonian $H_{\mathrm{cyl}}$ |
| scaling dimension $\Delta$ | global AdS energy $ER$ |
| radial quantization | bulk global-state language |

So when we say that a CFT operator of dimension $\Delta$ is dual to a bulk particle state of energy $E=\Delta/R$, the cylinder is doing the geometry behind the sentence.

## Causal diamonds and domains of dependence

The compactified picture is also useful because it makes causal domains finite. A ball-shaped spatial region in a CFT has a causal development that is a diamond. Conformal transformations can map this diamond to hyperbolic space times time,

$$
D(B)\sim \mathbb R\times H^{d-1},
$$

up to a Weyl factor. This observation is central in the study of modular Hamiltonians, thermal density matrices, and holographic entanglement entropy. We will return to it in the module on thermal CFT and entanglement.

For now, the point is simple: conformal compactification is not just about drawing infinity. It is a way of making causal structure, operator evolution, and AdS boundary conditions simultaneously visible.

## What changes under a Weyl transformation?

A CFT is invariant under Weyl transformations in the sense relevant to local physics, but a few careful statements prevent confusion.

First, primary operators transform covariantly:

$$
\mathcal O_i\mapsto e^{-\Delta_i\sigma}\mathcal O_i
$$

for scalar primaries, with spin-dependent vielbein factors for spinning primaries.

Second, separated correlators are transported by these local factors:

$$
\left\langle\prod_i\mathcal O_i(x_i)\right\rangle_{e^{2\sigma}g}
=
\prod_i e^{-\Delta_i\sigma(x_i)}
\left\langle\prod_i\mathcal O_i(x_i)\right\rangle_g,
$$

again up to anomaly and contact-term subtleties.

Third, the partition function need not be invariant. In even dimensions, the Weyl anomaly implies schematically

$$
\delta_\sigma \log Z[g]
=\int d^dx\sqrt g\,\sigma(x)\langle T^\mu{}_{\mu}\rangle.
$$

This is why a CFT can have a nonzero Casimir energy on the cylinder even though flat-space $T^\mu{}_{\mu}$ vanishes away from anomalies.

Fourth, the Hilbert space interpretation can change. Quantizing on flat time slices and quantizing on cylinder time slices are related, but the Hamiltonians are different conformal generators. The cylinder Hamiltonian is the one adapted to radial quantization and global AdS.

## AdS/CFT checkpoint

The main lesson is the chain

$$
\mathbb R^{1,d-1}
\quad\sim_{\text{conformal}}\quad
\text{patch of }\mathbb R_T\times S^{d-1}
\quad=
\partial(\text{global AdS}_{d+1}).
$$

This has several immediate consequences.

Scaling dimensions become cylinder energies:

$$
\Delta=ER.
$$

Flat-space local operators become states on $S^{d-1}$:

$$
\mathcal O(0)|0\rangle\leftrightarrow |\mathcal O\rangle.
$$

The CFT spectrum is the global AdS energy spectrum. Large-$N$ single-trace primaries will later become one-particle bulk states; multi-trace primaries will become multi-particle states; and the stress tensor state will encode the graviton sector.

The compactification also explains why global questions in AdS/CFT are sharper on the cylinder than on $\mathbb R^{1,d-1}$. Black holes, thermal states, finite-volume spectra, and normal modes are naturally global-AdS/cylinder concepts.

## Common pitfalls

A conformal compactification is not an isometry. Distances and volumes change. Null directions and angles are what survive.

The point at infinity in Euclidean $\mathbb R^d$ is simple, but Lorentzian infinity is richer. One must distinguish $i^+$, $i^-$, $i^0$, $\mathcal I^+$, and $\mathcal I^-$.

The cylinder time Hamiltonian is not the ordinary Minkowski time-translation generator $P_0$. It is related to dilatations in radial quantization. On the Lorentzian compactification, different choices of time correspond to different conformal generators.

The compactified Lorentzian space has global identifications. In quantum physics and in AdS/CFT, one usually works with the universal cover $S^{d-1}\times\mathbb R$.

## Exercises

### Exercise 1: Derive the cylinder metric from radial coordinates

Starting from Euclidean flat space

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2,
$$

set $r=e^\tau$. Show that the metric is Weyl-equivalent to the cylinder metric.

<details><summary><strong>Solution</strong></summary>

Since

$$
dr=e^\tau d\tau,
$$

we have

$$
dr^2=e^{2\tau}d\tau^2,
\qquad
r^2d\Omega_{d-1}^2=e^{2\tau}d\Omega_{d-1}^2.
$$

Therefore

$$
ds^2=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

Multiplying by the Weyl factor $e^{-2\tau}$ gives

$$
ds_{\mathrm{cyl}}^2=d\tau^2+d\Omega_{d-1}^2.
$$

Thus $\mathbb R^d\setminus\{0\}$ is conformal to $\mathbb R_\tau\times S^{d-1}$.

</details>

### Exercise 2: Show that $D=\partial_\tau$

Using $x^\mu=e^\tau n^\mu$, show that the flat-space dilatation vector field $D=x^\mu\partial_\mu$ becomes $\partial_\tau$.

<details><summary><strong>Solution</strong></summary>

The radial coordinate is

$$
r=e^\tau.
$$

The radial derivative relation is

$$
\partial_\tau=r\partial_r.
$$

Since

$$
x^\mu\partial_\mu=r\partial_r,
$$

we get

$$
D=x^\mu\partial_\mu=\partial_\tau.
$$

This is why dilatations in flat space are translations in cylinder time.

</details>

### Exercise 3: Derive the Lorentzian compactified metric

Starting from

$$
ds^2=-du\,dv+\frac{(v-u)^2}{4}d\Omega_{d-2}^2,
$$

use

$$
u=\tan U,
\qquad
v=\tan V,
\qquad
T=U+V,
\qquad
\chi=V-U
$$

to show that

$$
ds^2
=\frac{1}{4\cos^2U\cos^2V}
\left(-dT^2+d\chi^2+\sin^2\chi\,d\Omega_{d-2}^2\right).
$$

<details><summary><strong>Solution</strong></summary>

First,

$$
du=\sec^2U\,dU,
\qquad
 dv=\sec^2V\,dV.
$$

Also

$$
U=\frac{T-\chi}{2},
\qquad
V=\frac{T+\chi}{2},
$$

so

$$
dU\,dV=\frac{1}{4}(dT^2-d\chi^2).
$$

Therefore

$$
-du\,dv
=\frac{1}{4\cos^2U\cos^2V}(-dT^2+d\chi^2).
$$

For the angular term,

$$
v-u=\tan V-\tan U
=\frac{\sin(V-U)}{\cos U\cos V}
=\frac{\sin\chi}{\cos U\cos V}.
$$

Thus

$$
\frac{(v-u)^2}{4}d\Omega_{d-2}^2
=\frac{1}{4\cos^2U\cos^2V}
\sin^2\chi\,d\Omega_{d-2}^2.
$$

Combining both pieces gives the desired result.

</details>

### Exercise 4: Cylinder two-point function

Let

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle_{\mathbb R^d}
=\frac{1}{|x_1-x_2|^{2\Delta}}.
$$

Using $x_i=e^{\tau_i}n_i$ and

$$
\mathcal O_{\mathrm{cyl}}(\tau_i,n_i)=e^{\Delta\tau_i}\mathcal O(x_i),
$$

show that

$$
\langle \mathcal O_{\mathrm{cyl}}(\tau_1,n_1)\mathcal O_{\mathrm{cyl}}(\tau_2,n_2)\rangle
=
\frac{1}{\left[2(\cosh\tau_{12}-n_1\cdot n_2)\right]^\Delta}.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
|x_1-x_2|^2
=e^{2\tau_1}+e^{2\tau_2}-2e^{\tau_1+\tau_2}n_1\cdot n_2.
$$

Factor out $e^{\tau_1+\tau_2}$:

$$
|x_1-x_2|^2
=e^{\tau_1+\tau_2}
\left(e^{\tau_{12}}+e^{-\tau_{12}}-2n_1\cdot n_2\right).
$$

Since

$$
e^{\tau_{12}}+e^{-\tau_{12}}=2\cosh\tau_{12},
$$

we get

$$
|x_1-x_2|^2
=e^{\tau_1+\tau_2}
2(\cosh\tau_{12}-n_1\cdot n_2).
$$

Therefore

$$
\frac{e^{\Delta\tau_1}e^{\Delta\tau_2}}{|x_1-x_2|^{2\Delta}}
=
\frac{1}{\left[2(\cosh\tau_{12}-n_1\cdot n_2)\right]^\Delta}.
$$

</details>

### Exercise 5: Boundary metric of global AdS

Starting from

$$
ds_{\mathrm{AdS}}^2
=\frac{R^2}{\cos^2\rho}
\left(
-dT^2+d\rho^2+\sin^2\rho\,d\Omega_{d-1}^2
\right),
$$

show that the conformal boundary metric is the cylinder metric.

<details><summary><strong>Solution</strong></summary>

The boundary is at

$$
\rho\to\frac{\pi}{2}.
$$

The AdS metric diverges there by the conformal factor $R^2/\cos^2\rho$. Remove this divergent factor by defining the rescaled metric

$$
d\hat s^2=\frac{\cos^2\rho}{R^2}ds_{\mathrm{AdS}}^2.
$$

Then

$$
d\hat s^2=-dT^2+d\rho^2+\sin^2\rho\,d\Omega_{d-1}^2.
$$

Restricting to the boundary means dropping the normal direction $d\rho^2$ and setting $\sin\rho\to 1$. Hence

$$
ds_{\partial\mathrm{AdS}}^2=-dT^2+d\Omega_{d-1}^2.
$$

This is the Lorentzian cylinder $\mathbb R_T\times S^{d-1}$.

</details>

## Further reading

For the two-dimensional version of these ideas, the classic route is through the plane-to-cylinder map $z=e^w$, radial quantization, and finite-size scaling. For higher-dimensional CFT and AdS/CFT, the key references are modern CFT lecture notes on radial quantization and the standard AdS/CFT introductions that describe global AdS and its conformal boundary.
