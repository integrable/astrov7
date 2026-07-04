---
title: "Black Branes and Thermal CFTs"
description: "How planar AdS black branes encode finite-temperature states of holographic CFTs, including temperature, entropy, energy, pressure, and horizons."
sidebar:
  order: 10
---

## Why this matters

The first miracle of finite-temperature AdS/CFT is that a thermal state of a nongravitational quantum field theory is represented by a spacetime with a horizon.

For a holographic CFT on flat space,

$$
\text{thermal CFT on } \mathbb R_t \times \mathbb R^{d-1}
\quad
\longleftrightarrow
\quad
\text{planar AdS}_{d+1}\text{ black brane}.
$$

This is not just a poetic statement. The Hawking temperature of the horizon is the temperature of the boundary state, the horizon area is the thermal entropy, and the asymptotic metric coefficients determine the CFT stress tensor. The black-brane geometry is the workhorse behind holographic thermodynamics, real-time Green's functions, quasinormal modes, hydrodynamics, viscosity, conductivity, and much of AdS/CMT.

The important conceptual shift is this:

$$
\text{finite temperature in the CFT}
\quad
\longleftrightarrow
\quad
\text{a black object in the bulk}.
$$

A horizon is therefore not an exotic extra assumption. It is the bulk representation of an ordinary mixed state in the boundary theory.

## Boundary setup: a thermal CFT state

Take a $d$-dimensional CFT on flat spacetime. The thermal density matrix is

$$
\rho_\beta
=
\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\mathrm{Tr}\, e^{-\beta H},
\qquad
\beta = \frac{1}{T}.
$$

In Euclidean signature, the same partition function is computed by a path integral on

$$
S^1_\beta \times \mathbb R^{d-1},
$$

where bosons are periodic and fermions are antiperiodic around the thermal circle.

For a homogeneous and isotropic thermal CFT state, the one-point function of the stress tensor has the perfect-fluid form

$$
\langle T^i{}_j \rangle
=
\mathrm{diag}(-\varepsilon,p,p,\ldots,p),
$$

where conformal invariance implies

$$
\langle T^i{}_i \rangle = -\varepsilon + (d-1)p =0,
\qquad
\varepsilon = (d-1)p.
$$

Dimensional analysis then requires

$$
p \propto T^d,
\qquad
\varepsilon \propto T^d,
\qquad
s \propto T^{d-1},
$$

but the proportionality constants are strongly coupled dynamical data. Holography computes those constants from a classical black-brane geometry.

## The planar AdS black brane

The neutral planar AdS$_{d+1}$ black brane is

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dt^2
+d\vec x^{\,2}
+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d .
$$

Here:

- the AdS boundary is at $z=0$;
- the horizon is at $z=z_h$;
- the boundary spatial directions are $\vec x\in \mathbb R^{d-1}$;
- $L$ is the AdS radius.

Near the boundary, $f(z)\to 1$, so the induced boundary metric is conformal to flat Minkowski space:

$$
ds^2_{\partial}
=
-dt^2+d\vec x^{\,2}.
$$

Thus the black brane is not changing the CFT Lagrangian by turning on a curved boundary metric. It is changing the state. The temperature, energy density, pressure, and entropy density are state data.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Planar AdS black brane and the dual thermal CFT](/figures/course/black-branes-thermal-cfts.svg)

<figcaption>

A planar AdS black brane is dual to a homogeneous thermal CFT state. The boundary at $z=0$ carries the QFT on $\mathbb R_t\times\mathbb R^{d-1}$, while the horizon at $z=z_h$ sets $T=d/(4\pi z_h)$ and contributes entropy density $s=\mathrm{Area}/(4G_{d+1}V)$.

</figcaption>
</figure>

## Deriving the temperature

The temperature is fixed by smoothness of the Euclidean geometry. Wick rotate $t=-i\tau$:

$$
ds_E^2
=
\frac{L^2}{z^2}
\left[
f(z)d\tau^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right].
$$

Near the horizon, write $z=z_h-y$ with $y\ll z_h$. Then

$$
f(z)
=
1-\left(1-\frac{y}{z_h}\right)^d
\approx
\frac{d y}{z_h}.
$$

The $(\tau,z)$ part of the metric becomes

$$
ds_E^2\big|_{\tau,z}
\approx
\frac{L^2}{z_h^2}
\left[
\frac{d y}{z_h}d\tau^2
+
\frac{z_h}{d y}dy^2
\right].
$$

Define a radial coordinate $R$ by

$$
y=\frac{d z_h}{4L^2}R^2.
$$

Then

$$
ds_E^2\big|_{\tau,z}
\approx
dR^2+
\left(\frac{d}{2z_h}R\right)^2 d\tau^2.
$$

This is smooth polar space only if the angular variable

$$
\theta = \frac{d}{2z_h}\tau
$$

has period $2\pi$. Therefore

$$
\beta = \frac{4\pi z_h}{d},
\qquad
T = \frac{d}{4\pi z_h}.
$$

This derivation is worth remembering. In holography, the boundary temperature is often nothing more mysterious than the condition that the Euclidean horizon is not a cone.

## Entropy density from horizon area

The Bekenstein–Hawking entropy is

$$
S = \frac{\mathrm{Area}(\mathcal H)}{4G_{d+1}}.
$$

For the planar brane, the horizon metric in the spatial boundary directions is

$$
ds^2_{\mathcal H}
=
\frac{L^2}{z_h^2}d\vec x^{\,2}.
$$

If $V_{d-1}=\int d^{d-1}x$ is the coordinate spatial volume, then

$$
\mathrm{Area}(\mathcal H)
=
V_{d-1}\left(\frac{L}{z_h}\right)^{d-1}.
$$

Hence the entropy density is

$$
s
=
\frac{S}{V_{d-1}}
=
\frac{1}{4G_{d+1}}
\left(\frac{L}{z_h}\right)^{d-1}.
$$

Using $z_h=d/(4\pi T)$,

$$
s
=
\frac{L^{d-1}}{4G_{d+1}}
\left(\frac{4\pi T}{d}\right)^{d-1}.
$$

This already displays the essential holographic scaling:

$$
s \sim \frac{L^{d-1}}{G_{d+1}}T^{d-1}.
$$

Since $L^{d-1}/G_{d+1}\sim N^2$ in adjoint large-$N$ examples, the entropy density is of order $N^2$, as expected for a deconfined plasma of matrix degrees of freedom.

## Pressure, energy density, and free energy

The free energy density is

$$
\mathcal F = -p.
$$

For a homogeneous system,

$$
s = -\frac{\partial \mathcal F}{\partial T}
= \frac{\partial p}{\partial T}.
$$

Integrating the entropy density and choosing the zero-temperature pressure to vanish gives

$$
p
=
\frac{L^{d-1}}{16\pi G_{d+1}}
\frac{1}{z_h^d}
=
\frac{L^{d-1}}{16\pi G_{d+1}}
\left(\frac{4\pi T}{d}\right)^d.
$$

Conformal invariance then gives

$$
\varepsilon=(d-1)p
=
\frac{(d-1)L^{d-1}}{16\pi G_{d+1}}
\frac{1}{z_h^d}.
$$

The stress tensor is therefore

$$
\langle T^i{}_j\rangle
=
\frac{L^{d-1}}{16\pi G_{d+1}z_h^d}
\mathrm{diag}(-(d-1),1,1,\ldots,1).
$$

The trace vanishes:

$$
\langle T^i{}_i\rangle
=-(d-1)p+(d-1)p=0.
$$

This is one of the cleanest checks that the planar black brane is dual to a thermal state of a CFT on flat space.

## The AdS$_5$/CFT$_4$ result

For the canonical duality, $d=4$ and

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi}.
$$

The temperature is

$$
T=\frac{1}{\pi z_h}.
$$

The entropy density becomes

$$
s
=
\frac{L^3}{4G_5z_h^3}
=
\frac{\pi^2}{2}N^2T^3.
$$

The pressure and energy density are

$$
p=\frac{\pi^2}{8}N^2T^4,
\qquad
\varepsilon=\frac{3\pi^2}{8}N^2T^4,
$$

so the free energy density is

$$
\mathcal F=-\frac{\pi^2}{8}N^2T^4.
$$

At zero 't Hooft coupling, the free thermal gas of $\mathcal N=4$ SYM degrees of freedom gives a larger entropy density. The strong-coupling result is famously smaller by a factor $3/4$ at leading large $N$:

$$
\frac{s_{\lambda=\infty}}{s_{\lambda=0}}
=
\frac{3}{4}.
$$

This ratio should not be oversold. It is a comparison between two endpoints of the coupling, not a derivation that the strongly coupled plasma is “almost free.” But it is historically important because it made clear that black-brane thermodynamics can produce quantitative statements about strongly coupled gauge theory.

## Why it is a brane, not a spherical black hole

The boundary spatial geometry is $\mathbb R^{d-1}$, so the horizon is also planar. This is why the solution is called a black brane rather than a black hole.

The distinction matters:

$$
\text{CFT on } \mathbb R^{d-1}
\quad
\longleftrightarrow
\quad
\text{planar black brane},
$$

whereas

$$
\text{CFT on } S^{d-1}
\quad
\longleftrightarrow
\quad
\text{global AdS black hole or thermal AdS}.
$$

The planar black brane is appropriate for infinite-volume thermal physics. The global black hole is appropriate for a CFT on a sphere and has a richer phase structure, including the Hawking–Page transition discussed on the next page.

A large global AdS black hole with horizon radius much larger than $L$ looks locally like a planar black brane near any small patch of the horizon. This is the geometric reason that the black-brane formulas capture the high-temperature, large-volume limit of the CFT on a sphere.

## Horizon regularity and real-time coordinates

The Schwarzschild-like coordinate system above is singular at $z=z_h$, even though the horizon itself is smooth. For real-time calculations, it is often better to use ingoing Eddington–Finkelstein time

$$
v=t-z_*,
\qquad
\frac{dz_*}{dz}=-\frac{1}{f(z)}.
$$

Then the metric becomes

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dv^2
-2dvdz
+d\vec x^{\,2}
\right].
$$

This coordinate system is regular at the future horizon. It is the natural language for retarded Green's functions: imposing infalling behavior at the horizon corresponds to causal response in the boundary theory.

For equilibrium thermodynamics, Euclidean smoothness is enough. For real-time correlators, horizon boundary conditions become part of the dictionary.

## The state is mixed, but the bulk is classical

A thermal density matrix is mixed. A classical black-brane geometry, however, looks like a single saddle. There is no contradiction.

In the large-$N$ limit, the bulk path integral is dominated by a saddle geometry. That saddle computes the leading contribution to the thermal generating functional:

$$
Z_{\mathrm{CFT}}[\beta]
\approx
\exp\left(-I_{E,\text{on-shell}}[\text{black brane}]\right).
$$

The fact that the saddle is classical does not mean the boundary state is pure. It means that the density matrix has a semiclassical dual description.

The entropy is not a small quantum correction. It is of order $1/G_{d+1}\sim N^2$ and appears already at the classical level through the horizon area.

## What the horizon means for the boundary theory

The horizon is associated with several boundary phenomena:

- nonzero entropy density;
- dissipation and absorption;
- relaxation to equilibrium;
- poles of retarded Green's functions at quasinormal-mode frequencies;
- hydrodynamic behavior at long wavelengths.

A horizon gives the bulk a place where classical waves can fall in. From the boundary viewpoint, this corresponds to loss of phase coherence in a thermal medium, not to violation of unitarity. At finite $N$, the exact CFT time evolution is unitary. The classical black brane captures the leading large-$N$, long-time-before-recurrence approximation.

## Validity of the black-brane description

The two-derivative Einstein black brane is reliable when:

$$
N\gg 1,
\qquad
\lambda\gg 1,
$$

or, more generally, when the CFT has a large central charge and a large gap to higher-spin single-trace operators.

Corrections come in two broad types:

$$
\frac{G_{d+1}}{L^{d-1}}
\sim
\frac{1}{N^2}
\qquad
\text{bulk loop corrections},
$$

and

$$
\frac{\alpha'}{L^2}
\sim
\frac{1}{\sqrt{\lambda}}
\qquad
\text{stringy corrections}.
$$

These corrections modify the equation of state, transport coefficients, and entropy-area relation. The classical black brane is the leading approximation, not the full finite-temperature duality.

## Dictionary checkpoint

| Boundary thermal CFT | Planar AdS black brane |
|---|---|
| temperature $T$ | Hawking temperature $d/(4\pi z_h)$ |
| entropy density $s$ | horizon area density divided by $4G_{d+1}$ |
| energy density $\varepsilon$ | normalizable metric coefficient / ADM density |
| pressure $p$ | spatial stress tensor component |
| free energy density $\mathcal F$ | Euclidean on-shell action density times $T$ |
| thermal equilibrium | stationary black-brane saddle |
| dissipation | absorption by the future horizon |
| retarded response | infalling horizon condition |
| deconfined adjoint plasma | entropy and free energy of order $N^2$ |

The slogan is useful but should be read precisely:

$$
\text{thermal CFT state}
\quad
\leftrightarrow
\quad
\text{asymptotically AdS black geometry}.
$$

The boundary theory remains an ordinary quantum system. The horizon is how its large-$N$ thermal physics is geometrized.

## Common confusions

### “The temperature is put in by hand at the horizon.”

The horizon position $z_h$ is a parameter of the solution, but once $z_h$ is chosen the temperature is fixed by Euclidean smoothness:

$$
T=\frac{d}{4\pi z_h}.
$$

One cannot independently choose both $z_h$ and $T$ for the same smooth saddle.

### “The black brane changes the boundary metric.”

Near $z=0$, the metric approaches pure AdS with flat boundary metric. The black brane changes the normalizable part of the bulk metric, which is interpreted as a state-dependent stress tensor.

### “A black brane is dual to confinement.”

No. A planar AdS black brane has free energy and entropy of order $N^2$, characteristic of a deconfined plasma. Hawking–Page-type transitions, not the planar black brane by itself, are the standard holographic avatar of confinement/deconfinement transitions.

### “The horizon entropy is entanglement entropy of a boundary region.”

Not in this context. The horizon entropy is thermal entropy of the full boundary system. Holographic entanglement entropy is computed by extremal surfaces anchored on boundary subregions, not by the black-brane horizon in general. The two ideas are related but not identical.

### “Flat-space black branes and AdS black branes behave the same thermodynamically.”

They do not. The AdS boundary conditions act like a gravitational box. Large AdS black holes and black branes can be thermodynamically stable in the canonical ensemble, unlike asymptotically flat Schwarzschild black holes.

## Exercises

### Exercise 1: Derive the black-brane temperature

Starting from

$$
ds_E^2
=
\frac{L^2}{z^2}
\left[
f(z)d\tau^2+
\frac{dz^2}{f(z)}+d\vec x^{\,2}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

show that smoothness at $z=z_h$ requires

$$
T=\frac{d}{4\pi z_h}.
$$

<details>
<summary><strong>Solution</strong></summary>

Near the horizon, set $z=z_h-y$ with $y\ll z_h$. Then

$$
f(z)\approx \frac{d y}{z_h}.
$$

The $(\tau,z)$ part of the metric is

$$
ds_E^2\big|_{\tau,z}
\approx
\frac{L^2}{z_h^2}
\left[
\frac{d y}{z_h}d\tau^2
+
\frac{z_h}{d y}dy^2
\right].
$$

With

$$
y=\frac{d z_h}{4L^2}R^2,
$$

this becomes

$$
ds_E^2\big|_{\tau,z}
\approx
 dR^2+
\left(\frac{d}{2z_h}R\right)^2d\tau^2.
$$

Smoothness of polar coordinates requires $\frac{d}{2z_h}\tau$ to have period $2\pi$, so

$$
\beta=\frac{4\pi z_h}{d},
\qquad
T=\frac{1}{\beta}=\frac{d}{4\pi z_h}.
$$

</details>

### Exercise 2: Check conformal thermodynamics

Use

$$
p=\frac{L^{d-1}}{16\pi G_{d+1}z_h^d},
\qquad
T=\frac{d}{4\pi z_h},
$$

to show that

$$
s=\frac{\partial p}{\partial T}
=
\frac{L^{d-1}}{4G_{d+1}z_h^{d-1}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Write

$$
p(T)=\frac{L^{d-1}}{16\pi G_{d+1}}
\left(\frac{4\pi T}{d}\right)^d.
$$

Then

$$
\frac{\partial p}{\partial T}
=
\frac{dL^{d-1}}{16\pi G_{d+1}}
\left(\frac{4\pi}{d}\right)^d T^{d-1}.
$$

Using $T=d/(4\pi z_h)$ gives

$$
\frac{\partial p}{\partial T}
=
\frac{L^{d-1}}{4G_{d+1}}
\frac{1}{z_h^{d-1}},
$$

which equals the Bekenstein–Hawking entropy density.

</details>

### Exercise 3: The AdS$_5$/CFT$_4$ entropy density

Using

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi},
\qquad
T=\frac{1}{\pi z_h},
$$

show that

$$
s=\frac{\pi^2}{2}N^2T^3.
$$

<details>
<summary><strong>Solution</strong></summary>

For $d=4$,

$$
s=\frac{L^3}{4G_5z_h^3}.
$$

Since $z_h^{-1}=\pi T$,

$$
s=\frac{L^3}{4G_5}\pi^3T^3.
$$

Using $L^3/G_5=2N^2/\pi$ gives

$$
s=\frac{1}{4}\frac{2N^2}{\pi}\pi^3T^3
=\frac{\pi^2}{2}N^2T^3.
$$

</details>

### Exercise 4: Why does the stress tensor have zero trace?

Given

$$
\langle T^i{}_j\rangle
=
\mathrm{diag}(-\varepsilon,p,\ldots,p),
\qquad
\varepsilon=(d-1)p,
$$

show that $\langle T^i{}_i\rangle=0$.

<details>
<summary><strong>Solution</strong></summary>

The trace is

$$
\langle T^i{}_i\rangle
=-\varepsilon+(d-1)p.
$$

Substituting $\varepsilon=(d-1)p$ gives

$$
\langle T^i{}_i\rangle=0.
$$

This is the expected result for a CFT on flat space, where there is no Weyl anomaly contribution in the homogeneous thermal background.

</details>

## Further reading

- S. S. Gubser, I. R. Klebanov, and A. W. Peet, [Entropy and Temperature of Black 3-Branes](https://arxiv.org/abs/hep-th/9602135).
- E. Witten, [Anti de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
