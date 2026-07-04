---
title: "Black Holes and Black Branes"
description: "How AdS black holes and planar black branes encode thermal states of the boundary CFT, including horizons, temperature, entropy, and the first thermodynamic dictionary."
sidebar:
  order: 70
---

Black holes are not a decorative complication in AdS/CFT. They are the way thermal many-body physics appears geometrically.

In ordinary quantum field theory, a thermal state is described by a density matrix

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\mathrm{Tr}\,e^{-\beta H},
\qquad
\beta=\frac{1}{T}.
$$

In holography, the same thermal state is often described by a bulk saddle with a horizon. The horizon temperature is the field-theory temperature, and the horizon area is the field-theory entropy:

$$
T_{\mathrm{CFT}}=T_{\mathrm{Hawking}},
\qquad
S_{\mathrm{CFT}}=\frac{\mathrm{Area}_{\mathrm{horizon}}}{4G_N}.
$$

This is one of the first places where the duality stops sounding like a slogan. A strongly coupled thermal plasma, with many interacting quantum degrees of freedom, becomes a classical spacetime with a horizon.

This page introduces two geometries that appear constantly in AdS/CFT:

- **global AdS black holes**, dual to thermal states of a CFT on $\mathbb R_t\times S^{d-1}$;
- **planar AdS black branes**, dual to homogeneous thermal states of a CFT on $\mathbb R_t\times\mathbb R^{d-1}$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Global AdS black holes and planar AdS black branes](/figures/course/ads-black-holes-black-branes.svg)

<figcaption>

Global AdS black holes and planar AdS black branes are thermal bulk saddles with different boundary frames. Spherical horizons describe thermal CFTs on $\mathbb R_t\times S^{d-1}$, while planar horizons describe thermal plasmas on $\mathbb R_t\times\mathbb R^{d-1}$. Horizon data become boundary thermodynamic data.

</figcaption>
</figure>

## Why horizons are natural in holography

A finite-temperature CFT state has entropy. In a large-$N$ holographic theory, the thermal entropy is typically of order $N^2$ for adjoint gauge theories:

$$
S_{\mathrm{thermal}}\sim N^2.
$$

On the gravity side, the quantity of order $N^2$ is the inverse Newton constant in AdS units:

$$
\frac{L^{d-1}}{G_{d+1}}\sim N^2.
$$

Therefore a classical area law

$$
S=\frac{A}{4G_{d+1}}
$$

has precisely the right large-$N$ scaling to describe a deconfined plasma of many boundary degrees of freedom.

This is not merely dimensional analysis. A black brane has a regular horizon, a Hawking temperature, a free energy, and hydrodynamic perturbations. These map to the temperature, thermodynamic potential, and transport behavior of the boundary theory. Later, quasinormal modes of the horizon will become poles of retarded Green's functions.

For now, keep the following translation in mind:

$$
\text{thermal state of the boundary theory}
\quad\longleftrightarrow\quad
\text{black object in the AdS bulk}.
$$

## Einstein gravity with negative cosmological constant

In this unit we work in classical Einstein gravity with negative cosmological constant. The bulk action is schematically

$$
S=\frac{1}{16\pi G_{d+1}}\int d^{d+1}x\sqrt{-g}
\left(R+\frac{d(d-1)}{L^2}\right)+S_{\mathrm{boundary}}.
$$

The vacuum Einstein equation is

$$
R_{MN}=-\frac{d}{L^2}g_{MN}.
$$

Pure AdS is one solution. Black holes and black branes are other solutions with the same asymptotic AdS boundary behavior. They differ in the interior: instead of a smooth center or a zero-temperature Poincaré horizon, they contain an event horizon at finite radial position.

A useful family of static black solutions is

$$
ds^2=-f_k(r)dt^2+\frac{dr^2}{f_k(r)}+r^2 d\Sigma_{k,d-1}^2,
$$

where

$$
f_k(r)=k+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}}.
$$

Here $d\Sigma_{k,d-1}^2$ is the metric on a $(d-1)$-dimensional space of constant curvature $k$:

$$
k=+1 \quad \text{spherical horizon},
$$

$$
k=0 \quad \text{planar horizon},
$$

$$
k=-1 \quad \text{hyperbolic horizon}.
$$

The spherical and planar cases are the essential ones for this foundations course. The horizon radius $r_h$ is the largest positive root of

$$
f_k(r_h)=0.
$$

Equivalently,

$$
\mu=r_h^{d-2}\left(k+\frac{r_h^2}{L^2}\right).
$$

## Temperature from the horizon

Near a nonextremal horizon, the metric looks like Rindler space. This gives a universal formula for the Hawking temperature.

For a static metric of the form

$$
ds^2=-f(r)dt^2+\frac{dr^2}{f(r)}+\cdots,
$$

with a simple zero at $r=r_h$, the temperature is

$$
T=\frac{f'(r_h)}{4\pi}.
$$

For the family above,

$$
f_k'(r)=\frac{2r}{L^2}+(d-2)\frac{\mu}{r^{d-1}}.
$$

Using

$$
\mu=r_h^{d-2}\left(k+\frac{r_h^2}{L^2}\right),
$$

we obtain

$$
T=\frac{1}{4\pi}\left(\frac{d r_h}{L^2}+\frac{(d-2)k}{r_h}\right).
$$

This single formula teaches a lot. For planar horizons, $k=0$, so

$$
T_{\mathrm{planar}}=\frac{d r_h}{4\pi L^2}.
$$

For spherical horizons, $k=1$, so

$$
T_{\mathrm{spherical}}=\frac{1}{4\pi}\left(\frac{d r_h}{L^2}+\frac{d-2}{r_h}\right).
$$

Small spherical black holes behave roughly like asymptotically flat Schwarzschild black holes, with $T\sim 1/r_h$. Large AdS black holes behave differently, with $T\sim r_h/L^2$. This difference is one reason large AdS black holes can be thermodynamically stable.

## Entropy from area

The Bekenstein–Hawking entropy is

$$
S=\frac{A_h}{4G_{d+1}}.
$$

For

$$
ds^2=-f_k(r)dt^2+\frac{dr^2}{f_k(r)}+r^2 d\Sigma_{k,d-1}^2,
$$

the horizon area is

$$
A_h=r_h^{d-1}V_{k,d-1},
$$

where

$$
V_{k,d-1}=\int d^{d-1}x\sqrt{\det\Sigma_k}.
$$

Thus

$$
S=\frac{V_{k,d-1}r_h^{d-1}}{4G_{d+1}}.
$$

For a planar horizon, $V_{0,d-1}$ is infinite, so the useful quantity is entropy density. In the common $z$ coordinate convention below, it is

$$
s=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}.
$$

Because $z_h\sim 1/T$, this gives

$$
s\propto T^{d-1},
$$

as required by conformal invariance in $d$ boundary spacetime dimensions.

## The planar black brane in Poincaré coordinates

For many holographic computations, the most convenient thermal geometry is the planar black brane:

$$
ds^2=\frac{L^2}{z^2}\left(-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}\right),
$$

with

$$
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The boundary is at $z=0$. The horizon is at

$$
z=z_h.
$$

The Hawking temperature is

$$
T=\frac{d}{4\pi z_h}.
$$

The entropy density is

$$
s=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}
=\frac{1}{4G_{d+1}}\left(\frac{4\pi L T}{d}\right)^{d-1}.
$$

This is the workhorse geometry for strongly coupled thermal plasmas. It is homogeneous and isotropic along the boundary spatial directions $\vec x$, so it is dual to a translation-invariant thermal state of a CFT on flat space.

Near the boundary,

$$
ds^2\sim \frac{L^2}{z^2}\left(-dt^2+d\vec x^{\,2}+dz^2\right),
\qquad z\to 0,
$$

so the boundary conformal frame is flat Minkowski space:

$$
\mathbb R_t\times \mathbb R^{d-1}.
$$

The blackening factor $f(z)$ only becomes important in the interior. This is exactly what one expects from the UV/IR relation: the near-boundary ultraviolet region knows about the spacetime where the CFT lives, while the deeper bulk knows about the state.

## Thermodynamics of the planar brane

A CFT on flat space has no intrinsic scale. At temperature $T$, dimensional analysis gives

$$
p\propto T^d,
\qquad
\epsilon\propto T^d,
\qquad
s\propto T^{d-1}.
$$

Conformal invariance also implies a traceless stress tensor:

$$
T^\mu_{\ \mu}=0.
$$

For a homogeneous thermal state,

$$
\langle T^\mu_{\ \nu}\rangle=\mathrm{diag}(-\epsilon,p,p,\ldots,p),
$$

so tracelessness gives

$$
-\epsilon+(d-1)p=0.
$$

Therefore

$$
\epsilon=(d-1)p.
$$

The planar black brane reproduces this structure. In the standard Einstein-gravity normalization, holographic renormalization gives

$$
p=\frac{L^{d-1}}{16\pi G_{d+1}z_h^d},
\qquad
\epsilon=\frac{(d-1)L^{d-1}}{16\pi G_{d+1}z_h^d}.
$$

The entropy density follows from thermodynamics:

$$
s=\frac{\partial p}{\partial T}.
$$

Using

$$
z_h=\frac{d}{4\pi T},
$$

one recovers

$$
s=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}.
$$

So the same quantity is computed in two ways:

$$
\text{field-theory thermodynamics}
\quad\longleftrightarrow\quad
\text{horizon area}.
$$

This is the first concrete black-hole lesson of AdS/CFT.

## The AdS$_5$ black brane and strongly coupled $\mathcal N=4$ SYM

For the canonical AdS$_5$/CFT$_4$ example, the planar black brane is a five-dimensional geometry:

$$
ds^2=\frac{L^2}{z^2}\left(-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^4.
$$

The temperature is

$$
T=\frac{1}{\pi z_h}.
$$

Using the AdS$_5\times S^5$ parameter map,

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi},
$$

so the entropy density of strongly coupled large-$N$ $\mathcal N=4$ SYM is

$$
s=\frac{\pi^2}{2}N^2T^3.
$$

The $N^2$ counts adjoint degrees of freedom. The $T^3$ follows from conformal invariance in four spacetime dimensions. The numerical coefficient is genuine strong-coupling information.

## Global AdS black holes

The global Schwarzschild-AdS metric is

$$
ds^2=-f(r)dt^2+\frac{dr^2}{f(r)}+r^2d\Omega_{d-1}^2,
$$

with

$$
f(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}}.
$$

Its conformal boundary is

$$
\mathbb R_t\times S^{d-1}.
$$

Thus global AdS black holes are dual to thermal CFT states on a spatial sphere. This is different from the planar brane, which is dual to the CFT on flat space.

The horizon radius is determined by

$$
f(r_h)=0,
$$

so

$$
\mu=r_h^{d-2}\left(1+\frac{r_h^2}{L^2}\right).
$$

The temperature is

$$
T=\frac{1}{4\pi}\left(\frac{d r_h}{L^2}+\frac{d-2}{r_h}\right).
$$

This function has a minimum. Differentiating gives

$$
\frac{dT}{dr_h}=\frac{1}{4\pi}\left(\frac{d}{L^2}-\frac{d-2}{r_h^2}\right).
$$

The minimum occurs at

$$
r_h^2=\frac{d-2}{d}L^2,
$$

with

$$
T_{\min}=\frac{\sqrt{d(d-2)}}{2\pi L}.
$$

For $T>T_{\min}$, there are two black-hole branches:

- a small black hole with $r_h^2<\frac{d-2}{d}L^2$;
- a large black hole with $r_h^2>\frac{d-2}{d}L^2$.

The small branch has negative specific heat. The large branch has positive specific heat. The positive specific heat of large AdS black holes is one of the qualitative differences between AdS and asymptotically flat space.

## Why large AdS black holes can be stable

In asymptotically flat spacetime, a Schwarzschild black hole has

$$
T\sim \frac{1}{r_h}.
$$

As it loses energy, it gets hotter, so its heat capacity is negative. This makes equilibrium with a heat bath unstable.

In AdS, large black holes instead have

$$
T\sim \frac{r_h}{L^2}.
$$

As the black hole gains energy and grows, it gets hotter. This positive heat capacity makes large AdS black holes stable in the canonical ensemble.

A useful intuition is that AdS behaves like a gravitational box. The conformal boundary reflects excitations back into the bulk, and large black holes can equilibrate with their surroundings. This “box” picture is not a substitute for boundary conditions, but it is a good first guide.

## Hawking–Page transition: the first phase transition

Global AdS has another saddle with the same boundary topology: thermal AdS. It is simply Euclidean global AdS with periodically identified Euclidean time. It has no horizon.

At low temperature, the dominant saddle is thermal AdS. At sufficiently high temperature, the dominant saddle is a large AdS black hole. The transition between them is the Hawking–Page transition.

For the spherical Schwarzschild-AdS black hole, the free energy is proportional to

$$
F\propto r_h^{d-2}\left(1-\frac{r_h^2}{L^2}\right).
$$

Thus the free energy changes sign at

$$
r_h=L.
$$

The transition temperature is therefore

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}.
$$

In AdS/CFT, this becomes a phase transition of the boundary theory on $S^{d-1}$. In large-$N$ gauge theories, it is often interpreted as a confinement/deconfinement-type transition:

$$
\text{thermal AdS}\quad\longleftrightarrow\quad\text{low-entropy phase},
$$

$$
\text{large AdS black hole}\quad\longleftrightarrow\quad\text{high-entropy deconfined phase}.
$$

The phrase “confinement/deconfinement” should be used with care for a conformal theory on a compact sphere. The more robust statement is about the scaling of the free energy with $N$:

$$
F_{\mathrm{thermal\ AdS}}\sim O(N^0),
\qquad
F_{\mathrm{black\ hole}}\sim O(N^2).
$$

The black-hole phase has order $N^2$ entropy, exactly as expected for a deconfined adjoint plasma.

## Planar branes as the large black-hole limit

The planar black brane can be obtained as a local large-radius limit of a large spherical AdS black hole. For a large global black hole,

$$
r_h\gg L.
$$

A small patch of the horizon looks approximately flat. In that patch, the sphere $S^{d-1}$ is approximated by $\mathbb R^{d-1}$, and the spherical black hole becomes a planar black brane.

This is why the two metrics have similar high-temperature thermodynamics. For a large global black hole,

$$
T\sim \frac{d r_h}{4\pi L^2},
\qquad
S\sim \frac{r_h^{d-1}\mathrm{Vol}(S^{d-1})}{4G_{d+1}}.
$$

For the planar brane,

$$
T\sim \frac{r_h}{L^2},
\qquad
s\sim \frac{r_h^{d-1}}{4G_{d+1}}.
$$

The planar brane is therefore the natural description of the thermodynamic limit of the boundary CFT.

## Horizon versus boundary

A common beginner confusion is to imagine that the CFT “lives on the horizon.” It does not.

The CFT lives on the conformal boundary. In the planar black brane metric,

$$
z=0
$$

is the boundary, while

$$
z=z_h
$$

is the horizon.

The horizon is part of the bulk interior. Its area computes the entropy of the boundary state, but the boundary degrees of freedom are not literally located on the horizon in the same geometric sense that a field lives on a spacetime manifold.

A better statement is

$$
\text{the CFT state is encoded in the bulk geometry, including its horizon}.
$$

This distinction matters later. Boundary observables are defined by asymptotic behavior near the conformal boundary, while real-time dissipative physics is controlled by conditions at the horizon.

## Euclidean preview

The next page will discuss Euclidean AdS and thermal circles more systematically, but the essential idea is already visible.

Near a nonextremal horizon, the Euclidean metric takes the approximate form

$$
ds_E^2\approx d\rho^2+\kappa^2\rho^2d\tau^2+\cdots,
$$

where $\kappa$ is the surface gravity. This is polar-coordinate flat space if and only if

$$
\tau\sim \tau+\frac{2\pi}{\kappa}.
$$

Therefore the inverse temperature is

$$
\beta=\frac{1}{T}=\frac{2\pi}{\kappa}.
$$

For metrics of the form

$$
ds^2=-f(r)dt^2+\frac{dr^2}{f(r)}+\cdots,
$$

the surface gravity is

$$
\kappa=\frac{f'(r_h)}{2},
$$

so

$$
T=\frac{f'(r_h)}{4\pi}.
$$

This is the geometric origin of the temperature formulas used above.

## Dictionary checkpoint

The black-hole dictionary introduced on this page is:

| Boundary quantity | Bulk quantity |
|---|---|
| thermal density matrix $\rho_\beta$ | black-hole or black-brane saddle |
| temperature $T$ | Hawking temperature of the horizon |
| entropy $S$ or entropy density $s$ | horizon area divided by $4G_N$ |
| CFT on $\mathbb R_t\times S^{d-1}$ | global AdS black hole |
| CFT on $\mathbb R_t\times\mathbb R^{d-1}$ | planar AdS black brane |
| high-temperature deconfined phase on $S^{d-1}$ | large AdS black hole |
| thermal response and dissipation | horizon boundary conditions |

The important conceptual shift is that **state data** in the boundary theory become **interior geometry** in the bulk.

## Common confusions

### “A black brane is just a black hole with a funny name.”

A black brane has a horizon extended along noncompact spatial directions. Its horizon topology is planar, usually $\mathbb R^{d-1}$. A global AdS black hole has a compact spherical horizon, $S^{d-1}$. The difference matters because the boundary theories live in different conformal frames: flat space versus the cylinder.

### “The CFT lives on the horizon.”

No. The CFT lives on the conformal boundary. The horizon is a bulk feature that encodes thermal entropy and dissipative dynamics of the boundary state.

### “All AdS black holes are thermodynamically stable.”

No. Small spherical AdS black holes have negative specific heat. Large spherical AdS black holes and planar black branes are thermodynamically stable in the standard canonical setting.

### “The planar black brane has a Hawking–Page transition.”

Not in the same way as the global spherical black hole. The Hawking–Page transition relies on comparing thermal AdS and a spherical black hole with boundary $S^{d-1}$. For the planar boundary $\mathbb R^{d-1}$, conformal invariance and infinite volume lead to a different thermodynamic structure.

### “The horizon is visible in the UV of the CFT.”

The horizon is deep in the bulk, so it is more naturally tied to infrared and thermal physics. Boundary UV data are controlled by the near-boundary expansion. This separation is not absolute, but it is a good first guide.

## Exercises

### Exercise 1: Temperature of the planar black brane

Consider

$$
ds^2=\frac{L^2}{z^2}\left(-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

Show that the temperature is

$$
T=\frac{d}{4\pi z_h}.
$$

<details>
<summary><strong>Solution</strong></summary>

For a metric of the form

$$
ds^2=\Omega(z)^2\left(-f(z)dt^2+\frac{dz^2}{f(z)}+\cdots\right),
$$

with a simple zero of $f(z)$ at $z=z_h$, Euclidean smoothness gives

$$
T=\frac{|f'(z_h)|}{4\pi}.
$$

Here

$$
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

so

$$
f'(z)=-\frac{d z^{d-1}}{z_h^d}.
$$

At the horizon,

$$
|f'(z_h)|=\frac{d}{z_h}.
$$

Therefore

$$
T=\frac{d}{4\pi z_h}.
$$

</details>

### Exercise 2: Conformal scaling of entropy density

Using

$$
T=\frac{d}{4\pi z_h}
$$

and

$$
s=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1},
$$

show that the entropy density scales as $T^{d-1}$.

<details>
<summary><strong>Solution</strong></summary>

From the temperature relation,

$$
z_h=\frac{d}{4\pi T}.
$$

Substitution gives

$$
s=\frac{1}{4G_{d+1}}\left(\frac{4\pi L T}{d}\right)^{d-1}.
$$

Thus

$$
s\propto T^{d-1}.
$$

This is exactly what dimensional analysis predicts for a conformal field theory in $d$ spacetime dimensions.

</details>

### Exercise 3: Minimum temperature of a spherical AdS black hole

For a global Schwarzschild-AdS black hole,

$$
T(r_h)=\frac{1}{4\pi}\left(\frac{d r_h}{L^2}+\frac{d-2}{r_h}\right).
$$

Find the radius where $T(r_h)$ is minimized.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dT}{dr_h}=\frac{1}{4\pi}\left(\frac{d}{L^2}-\frac{d-2}{r_h^2}\right).
$$

Setting this to zero gives

$$
\frac{d}{L^2}=\frac{d-2}{r_h^2}.
$$

Therefore

$$
r_h^2=\frac{d-2}{d}L^2.
$$

The minimum temperature is

$$
T_{\min}=\frac{\sqrt{d(d-2)}}{2\pi L}.
$$

</details>

### Exercise 4: Hawking–Page temperature

Assume the free energy of a spherical AdS black hole is proportional to

$$
F\propto r_h^{d-2}\left(1-\frac{r_h^2}{L^2}\right).
$$

Use the temperature formula to show that the free energy changes sign at

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}.
$$

<details>
<summary><strong>Solution</strong></summary>

The free energy changes sign when

$$
1-\frac{r_h^2}{L^2}=0.
$$

Thus $r_h=L$. Substituting into

$$
T(r_h)=\frac{1}{4\pi}\left(\frac{d r_h}{L^2}+\frac{d-2}{r_h}\right)
$$

gives

$$
T_{\mathrm{HP}}=\frac{1}{4\pi}\left(\frac{d}{L}+\frac{d-2}{L}\right)=\frac{d-1}{2\pi L}.
$$

</details>

### Exercise 5: Traceless stress tensor and equation of state

A homogeneous thermal CFT has

$$
\langle T^\mu_{\ \nu}\rangle=\mathrm{diag}(-\epsilon,p,p,\ldots,p).
$$

Use tracelessness to show that

$$
\epsilon=(d-1)p.
$$

<details>
<summary><strong>Solution</strong></summary>

For a CFT in flat space with no anomaly,

$$
\langle T^\mu_{\ \mu}\rangle=0.
$$

Taking the trace gives

$$
-\epsilon+(d-1)p=0.
$$

Therefore

$$
\epsilon=(d-1)p.
$$

This is the conformal equation of state. The planar black brane reproduces it holographically.

</details>

## Further reading

- S. W. Hawking and D. N. Page, [Thermodynamics of Black Holes in Anti-de Sitter Space](https://doi.org/10.1007/BF01208266).
- E. Witten, [Anti de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- S. A. Hartnoll, A. Lucas, and S. Sachdev, [Holographic Quantum Matter](https://arxiv.org/abs/1612.07324), especially the thermal black-brane setup.
