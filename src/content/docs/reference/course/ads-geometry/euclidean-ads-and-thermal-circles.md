---
title: "Euclidean AdS and Thermal Circles"
description: "How Wick rotation, Euclidean thermal circles, and smoothness at horizons encode temperature, entropy, and black-hole thermodynamics in AdS/CFT."
sidebar:
  order: 80
---

The previous page introduced AdS black holes and black branes as Lorentzian geometries dual to thermal states of the boundary theory. This page explains why the same physics can often be read from a Euclidean geometry in which time is periodic.

The short version is this:

$$
Z_{\rm CFT}(\beta)
=
{\rm Tr}\, e^{-\beta H}
\quad
\longleftrightarrow
\quad
Z_{\rm grav}[S^1_\beta \times \Sigma]
\approx
\sum_{\text{bulk saddles}}
\exp\!\left[-I_E^{\rm ren}\right].
$$

The boundary field theory sees a thermal circle $S^1_\beta$. The bulk must fill this boundary circle in some smooth way. If the bulk saddle has a horizon in Lorentzian signature, then in Euclidean signature the horizon is not a boundary. It is the place where the thermal circle smoothly contracts to zero size. Requiring this contraction to be smooth fixes the temperature.

That one sentence is the geometric origin of Hawking temperature.

## Why this matters

Euclidean methods are not just a computational convenience. They explain several features of thermal holography at once:

- the relation between horizon regularity and temperature;
- the interpretation of black holes as thermal states;
- the gravitational calculation of the free energy;
- the competition between different bulk saddles with the same boundary data;
- the Hawking–Page transition;
- the origin of black-hole entropy from the Euclidean action.

The key shift is conceptual. In Lorentzian signature, a black-hole horizon is a causal surface. In Euclidean signature, the same horizon becomes a smooth origin of polar coordinates. The thermal circle is the angular coordinate around that origin.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Two Euclidean AdS fillings of the same boundary thermal circle](/figures/course/euclidean-ads-thermal-circles.svg)

<figcaption>

The same boundary thermal data $S^1_\beta\times \Sigma$ can be filled by different Euclidean bulk saddles. In a black-hole or black-brane saddle, the Euclidean time circle smoothly contracts at the horizon, fixing $\beta$ by regularity.

</figcaption>
</figure>

## Thermal states from Euclidean time

For an ordinary quantum system with Hamiltonian $H$, the thermal partition function is

$$
Z(\beta) = {\rm Tr}\, e^{-\beta H},
\qquad
\beta = \frac{1}{T}.
$$

In Euclidean quantum field theory, this trace is represented by a path integral on a Euclidean time circle:

$$
\tau \sim \tau + \beta.
$$

Bosonic fields are periodic around this circle, while fermionic fields are antiperiodic in the thermal ensemble:

$$
\Phi(\tau+\beta,\vec x) = \Phi(\tau,\vec x),
\qquad
\Psi(\tau+\beta,\vec x) = -\Psi(\tau,\vec x).
$$

This is why finite temperature breaks supersymmetry in most thermal applications: supersymmetry would want bosons and fermions to be treated symmetrically, while the thermal trace gives them different spin structures around $S^1_\beta$.

In AdS/CFT, the boundary thermal path integral becomes a boundary condition for the bulk gravitational path integral. Schematically,

$$
Z_{\rm CFT}[S^1_\beta\times \Sigma]
=
Z_{\rm bulk}[\partial \mathcal M = S^1_\beta\times \Sigma].
$$

At large $N$, the bulk path integral is approximated by saddle points:

$$
Z_{\rm bulk}[\partial \mathcal M]
\approx
\sum_i \exp\!\left[-I_E^{\rm ren}[\mathcal M_i]\right],
$$

where each $\mathcal M_i$ is a smooth Euclidean bulk geometry whose conformal boundary is the prescribed thermal boundary geometry. The dominant saddle is the one with the smallest renormalized Euclidean action.

The free energy is then

$$
F = -T \log Z
\approx
T I_E^{\rm ren},
$$

or equivalently

$$
I_E^{\rm ren} = \beta F
$$

for the dominant saddle.

## Wick rotation and the Euclidean metric

For a static Lorentzian metric, one often writes

$$
t = -i\tau.
$$

A simple example is pure Poincare AdS. In Lorentzian signature,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-dt^2 + d\vec x^{\,2} + dz^2
\right).
$$

After Wick rotation,

$$
ds_E^2
=
\frac{L^2}{z^2}
\left(
d\tau^2 + d\vec x^{\,2} + dz^2
\right).
$$

If we impose

$$
\tau \sim \tau + \beta,
$$

then the boundary geometry is $S^1_\beta\times \mathbb R^{d-1}$. Locally this is still Euclidean AdS, but globally it has a thermal circle.

For global AdS, the Lorentzian metric can be written as

$$
ds^2
=
L^2
\left(
-\cosh^2\rho\, dt^2
+d\rho^2
+\sinh^2\rho\, d\Omega_{d-1}^2
\right).
$$

The Euclidean continuation is

$$
ds_E^2
=
L^2
\left(
\cosh^2\rho\, d\tau^2
+d\rho^2
+\sinh^2\rho\, d\Omega_{d-1}^2
\right).
$$

At large $\rho$, the metric is conformal to

$$
d\tau^2 + d\Omega_{d-1}^2.
$$

If $\tau$ has period $\beta$, the boundary is

$$
S^1_\beta \times S^{d-1}.
$$

This geometry is usually called thermal AdS. It is locally the same as Euclidean AdS, but with Euclidean time periodically identified.

## The horizon as a smooth Euclidean origin

Now consider a static black hole metric of the form

$$
ds^2
=
-f(r)dt^2
+\frac{dr^2}{f(r)}
+r^2 d\Sigma_{d-1}^2,
$$

where the horizon is at

$$
f(r_h)=0.
$$

Assume the horizon is nonextremal, so

$$
f'(r_h)>0.
$$

After Wick rotation $t=-i\tau$,

$$
ds_E^2
=
f(r)d\tau^2
+\frac{dr^2}{f(r)}
+r^2 d\Sigma_{d-1}^2.
$$

Near the horizon,

$$
f(r) = f'(r_h)(r-r_h)+\cdots.
$$

Define a new radial coordinate $\rho$ by

$$
r-r_h = \frac{f'(r_h)}{4}\rho^2.
$$

Then the $(r,\tau)$ part of the metric becomes

$$
ds_{E,2}^2
\simeq
d\rho^2
+
\left(\frac{f'(r_h)}{2}\right)^2
\rho^2 d\tau^2.
$$

This is just the flat plane in polar coordinates if the angular coordinate

$$
\theta = \frac{f'(r_h)}{2}\tau
$$

has period $2\pi$. Therefore $\tau$ must have period

$$
\beta
=
\frac{4\pi}{f'(r_h)}.
$$

The Hawking temperature is

$$
T = \frac{1}{\beta}
= \frac{f'(r_h)}{4\pi}.
$$

This is the smoothness derivation of the Hawking temperature. No quantum field theory in curved spacetime was needed at this stage. The temperature is forced by the requirement that the Euclidean geometry be regular at the place where the Lorentzian horizon used to be.

More generally, if the near-horizon Lorentzian metric is

$$
ds^2
\simeq
-\kappa^2\rho^2 dt^2
+d\rho^2
+ds_{\rm horizon}^2,
$$

then the Euclidean metric is

$$
ds_E^2
\simeq
d\rho^2
+\kappa^2\rho^2 d\tau^2
+ds_{\rm horizon}^2.
$$

Smoothness requires

$$
\beta = \frac{2\pi}{\kappa},
\qquad
T = \frac{\kappa}{2\pi},
$$

where $\kappa$ is the surface gravity.

## Planar AdS black brane

The planar AdS$_{d+1}$ black brane is

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dt^2
+d\vec x^{\,2}
+
\frac{dz^2}{f(z)}
\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The boundary is at $z=0$, and the horizon is at $z=z_h$.

After Wick rotation,

$$
ds_E^2
=
\frac{L^2}{z^2}
\left(
f(z)d\tau^2
+d\vec x^{\,2}
+
\frac{dz^2}{f(z)}
\right).
$$

Near the horizon,

$$
f(z)
\simeq
\frac{d}{z_h}(z_h-z).
$$

The same smoothness analysis gives

$$
\beta = \frac{4\pi z_h}{d},
\qquad
T = \frac{d}{4\pi z_h}.
$$

This formula is one of the most frequently used results in finite-temperature holography. It relates the location of the black-brane horizon to the boundary temperature.

For AdS$_5$, where $d=4$,

$$
T = \frac{1}{\pi z_h}.
$$

The horizon is deeper in the bulk at lower temperature and closer to the boundary at higher temperature.

## Global AdS-Schwarzschild black holes

For a spherical horizon, the global AdS-Schwarzschild metric is

$$
ds^2
=
-f(r)dt^2
+\frac{dr^2}{f(r)}
+r^2 d\Omega_{d-1}^2,
$$

with

$$
f(r)
=
1+\frac{r^2}{L^2}
-\frac{\mu}{r^{d-2}}.
$$

The horizon radius $r_h$ satisfies

$$
f(r_h)=0,
$$

so

$$
\mu
=
r_h^{d-2}
\left(1+\frac{r_h^2}{L^2}\right).
$$

The temperature is

$$
T
=
\frac{f'(r_h)}{4\pi}
=
\frac{1}{4\pi}
\left(
\frac{d r_h}{L^2}
+
\frac{d-2}{r_h}
\right).
$$

This function has a minimum. Small AdS black holes behave thermodynamically like asymptotically flat black holes and have negative specific heat. Large AdS black holes have positive specific heat and can dominate the canonical ensemble.

This is already a major difference between AdS and flat space. The AdS boundary acts like a gravitational box. Large black holes can be in stable thermal equilibrium with their own radiation.

## Thermal AdS versus Euclidean black holes

For boundary topology

$$
S^1_\beta \times S^{d-1},
$$

there are at least two important Euclidean fillings.

The first is thermal AdS. Its topology is roughly

$$
S^1_\beta \times B^d.
$$

The thermal circle is noncontractible. The spatial $S^{d-1}$ shrinks smoothly in the interior.

The second is the Euclidean AdS black hole. Its topology is roughly

$$
B^2 \times S^{d-1}.
$$

Here the Euclidean time circle is contractible. It shrinks smoothly at the horizon.

The boundary data are the same, but the bulk fillings are topologically different. Therefore the gravitational path integral should sum over both:

$$
Z_{\rm grav}[S^1_\beta\times S^{d-1}]
\approx
\exp\!\left[-I_E^{\rm thermal\ AdS}\right]
+
\exp\!\left[-I_E^{\rm black\ hole}\right]
+\cdots.
$$

At low temperature, thermal AdS dominates. At high temperature, the large AdS black hole dominates. This exchange of dominance is the Hawking–Page transition.

On the boundary, for a large-$N$ gauge theory on $S^{d-1}$, this transition is interpreted as a confinement/deconfinement-type transition. The details depend on the theory and ensemble, but the rough scaling is simple:

$$
F_{\rm thermal\ AdS} \sim N^0,
\qquad
F_{\rm black\ hole} \sim N^2.
$$

The black hole carries the entropy of order $N^2$ degrees of freedom.

## The Euclidean gravitational action

The Euclidean gravitational path integral has the schematic form

$$
Z_{\rm grav}
=
\int \mathcal D g\,\mathcal D\phi\; e^{-I_E[g,\phi]}.
$$

In the saddle-point approximation,

$$
\log Z_{\rm grav}
\approx
-I_E^{\rm ren}[g_{\rm saddle},\phi_{\rm saddle}].
$$

For Einstein gravity, the renormalized Euclidean action has the schematic structure

$$
I_E^{\rm ren}
=
-\frac{1}{16\pi G_{d+1}}
\int_{\mathcal M} d^{d+1}x\sqrt g\,(R-2\Lambda)
-\frac{1}{8\pi G_{d+1}}
\int_{\partial\mathcal M} d^d x\sqrt h\,K
+I_{\rm ct}.
$$

The precise sign of the Gibbons–Hawking–York term depends on the convention for the outward normal and for $K$. What matters physically is that the boundary term is needed for a well-posed Dirichlet variational problem, and the counterterms are needed to make the AdS on-shell action finite.

Once $I_E^{\rm ren}$ is known, the thermodynamic quantities follow from

$$
F = \frac{I_E^{\rm ren}}{\beta},
$$

$$
E = \frac{\partial I_E^{\rm ren}}{\partial \beta},
$$

and

$$
S
=
\beta E - I_E^{\rm ren}.
$$

Equivalently,

$$
S
=
\left(\beta \frac{\partial}{\partial \beta}-1\right)
I_E^{\rm ren}.
$$

For an AdS black hole or black brane, this entropy agrees with the Bekenstein–Hawking area law:

$$
S
=
\frac{A_{\rm horizon}}{4G_{d+1}}.
$$

The Euclidean derivation is especially elegant because the entropy comes from the geometry of the smooth cap. If one changes the period $\beta$ away from the smooth value while holding the horizon area fixed, the Euclidean geometry develops a conical defect. The response of the gravitational action to this conical defect gives precisely $A/(4G)$ in two-derivative Einstein gravity.

## Smoothness versus arbitrary temperature

A common question is: if the boundary circle has arbitrary length $\beta$, why can a black hole only have a special value of $\beta$?

The answer is that the boundary condition specifies the length of the thermal circle at infinity, but a smooth black-hole filling exists only when that boundary period matches the horizon regularity condition. For a family of black holes labeled by $r_h$, the regularity condition determines $\beta$ as a function of $r_h$.

For example, the planar black brane satisfies

$$
\beta = \frac{4\pi z_h}{d}.
$$

Thus for any boundary temperature $T=1/\beta$, there is a corresponding horizon location

$$
z_h = \frac{d}{4\pi T}.
$$

For global AdS-Schwarzschild black holes, the relation $T(r_h)$ is not one-to-one. Above a minimum temperature, there are usually two black holes: a small unstable one and a large stable one. The large one is the relevant saddle at sufficiently high temperature.

If one insists on the wrong period for a given horizon radius, the Euclidean geometry is not smooth. It has a conical singularity at the horizon. Such geometries are useful in entropy derivations, but they are not ordinary smooth saddles of the vacuum Einstein equations.

## Euclidean preparation of states

The full thermal circle computes a trace:

$$
Z(\beta)={\rm Tr}\, e^{-\beta H}.
$$

A Euclidean path integral over half of the thermal circle prepares a state. In an ordinary QFT, cutting the circle open at two times prepares the thermofield-double state

$$
|{\rm TFD}\rangle
=
\frac{1}{\sqrt{Z(\beta)}}
\sum_n e^{-\beta E_n/2}
|n\rangle_L |n\rangle_R.
$$

In holography, the Lorentzian continuation of the corresponding Euclidean black-hole saddle gives the eternal two-sided AdS black hole. This is a first glimpse of a powerful idea: Euclidean geometry can prepare Lorentzian states.

This course will return to this point when discussing real-time holography, entanglement wedges, and black-hole information.

## Charged and rotating previews

Although this page focuses on neutral static black holes, the Euclidean method generalizes.

For a conserved charge, the grand canonical partition function is

$$
Z(\beta,\mu)
=
{\rm Tr}\, e^{-\beta(H-\mu Q)}.
$$

In the bulk, the chemical potential is encoded in the boundary value of a Euclidean gauge field. A useful regularity condition is that the one-form $A=A_\tau d\tau$ should be smooth at the place where the $\tau$ circle contracts. In a convenient gauge this means

$$
A_\tau(r_h)=0,
$$

so the chemical potential is the gauge-invariant difference between the boundary and the horizon:

$$
\mu = A_\tau(\infty)-A_\tau(r_h).
$$

For rotating black holes, the Euclidean identification mixes time with angular variables. The boundary ensemble then includes angular potentials. These refinements are conceptually straightforward but technically richer, so they are deferred to later applications.

## Dictionary checkpoint

The main translations from this page are:

| Boundary thermal field theory | Euclidean AdS gravity |
|---|---|
| thermal partition function $Z(\beta)$ | bulk path integral with boundary $S^1_\beta\times \Sigma$ |
| inverse temperature $\beta$ | circumference of Euclidean boundary time circle |
| thermal state | smooth Euclidean filling of the thermal boundary |
| black-hole temperature | smoothness condition at Euclidean horizon |
| free energy $F$ | $I_E^{\rm ren}/\beta$ |
| entropy $S$ | $\beta E-I_E^{\rm ren}$, equal to $A/(4G)$ for Einstein gravity |
| phase transition | exchange of dominance between Euclidean saddles |
| horizon in Lorentzian signature | smooth cap of the thermal circle in Euclidean signature |

The essential lesson is that temperature is boundary data, but a black-hole saddle can fill that boundary data only when the thermal circle closes smoothly in the interior.

## Common confusions

### “The Euclidean horizon is another boundary.”

No. For a smooth nonextremal Euclidean black hole, the horizon is the origin of polar coordinates in the $(\rho,\tau)$ plane. The thermal circle shrinks there. One should not impose independent boundary data at the Euclidean horizon.

### “The thermal circle period can be chosen independently of the black hole.”

Not for a fixed smooth black-hole geometry. The period is fixed by regularity at the horizon. Equivalently, the black-hole size determines the temperature. In some families, such as planar black branes, this relation is one-to-one. In global AdS, it can be many-to-one or have a minimum temperature.

### “Thermal AdS and the AdS black hole have different boundary theories.”

No. They are different bulk saddles with the same boundary thermal geometry. They contribute to the same boundary partition function. Their competition is precisely what makes the Hawking–Page transition possible.

### “Euclidean methods automatically give real-time correlators.”

Euclidean correlators determine many equilibrium quantities, but real-time retarded correlators require additional analytic continuation and horizon boundary conditions. In holography, infalling boundary conditions at Lorentzian horizons are essential for retarded response.

### “Extremal black holes are obtained by the same smoothness argument with $T=0$.”

Extremal horizons are subtle. The near-horizon Euclidean geometry is not a smooth disk in the same way as a nonextremal horizon. The Euclidean time circle does not simply cap off with a finite opening angle. Many zero-temperature limits must be taken with care.

## Exercises

### Exercise 1: Euclidean Rindler smoothness

Consider the two-dimensional Euclidean metric

$$
ds^2 = d\rho^2 + \kappa^2\rho^2 d\tau^2.
$$

Show that the geometry is smooth at $\rho=0$ only if $\tau$ has period $2\pi/\kappa$.

<details>
<summary><strong>Solution</strong></summary>

Flat polar coordinates are

$$
ds^2=d\rho^2+\rho^2 d\theta^2,
$$

where $\theta$ has period $2\pi$. In the given metric,

$$
\theta = \kappa \tau.
$$

Therefore $\theta\sim \theta+2\pi$ implies

$$
\tau \sim \tau + \frac{2\pi}{\kappa}.
$$

If the period is different, the origin has a conical excess or deficit. Thus a smooth Euclidean horizon fixes

$$
\beta = \frac{2\pi}{\kappa},
\qquad
T = \frac{\kappa}{2\pi}.
$$

</details>

### Exercise 2: Temperature of the planar black brane

For

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

derive the temperature

$$
T=\frac{d}{4\pi z_h}.
$$

<details>
<summary><strong>Solution</strong></summary>

After Wick rotation,

$$
ds_E^2
=
\frac{L^2}{z^2}
\left(
f(z)d\tau^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right).
$$

Near the horizon, write

$$
y=z_h-z.
$$

Then

$$
f(z)=1-\left(1-\frac{y}{z_h}\right)^d
\simeq
\frac{d y}{z_h}.
$$

The two-dimensional $(y,\tau)$ part is

$$
ds_{E,2}^2
\simeq
\frac{L^2}{z_h^2}
\left(
\frac{d y}{z_h}d\tau^2
+
\frac{z_h}{d y}dy^2
\right).
$$

Define

$$
y=\frac{d z_h}{4L^2}\rho^2.
$$

Then

$$
ds_{E,2}^2
\simeq
d\rho^2
+
\frac{d^2}{4z_h^2}\rho^2 d\tau^2.
$$

Smoothness requires

$$
\frac{d}{2z_h}\tau
$$

to have period $2\pi$. Therefore

$$
\beta = \frac{4\pi z_h}{d},
\qquad
T=\frac{1}{\beta}=\frac{d}{4\pi z_h}.
$$

</details>

### Exercise 3: Minimum temperature of global AdS-Schwarzschild

For the global AdS-Schwarzschild black hole,

$$
T(r_h)
=
\frac{1}{4\pi}
\left(
\frac{d r_h}{L^2}
+
\frac{d-2}{r_h}
\right).
$$

Find the horizon radius at which the temperature is minimized and compute $T_{\min}$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dT}{dr_h}
=
\frac{1}{4\pi}
\left(
\frac{d}{L^2}
-
\frac{d-2}{r_h^2}
\right).
$$

Setting this to zero gives

$$
r_h^2 = L^2\frac{d-2}{d},
$$

so

$$
r_h = L\sqrt{\frac{d-2}{d}}.
$$

At this radius,

$$
\frac{d r_h}{L^2}
=
\frac{\sqrt{d(d-2)}}{L},
\qquad
\frac{d-2}{r_h}
=
\frac{\sqrt{d(d-2)}}{L}.
$$

Therefore

$$
T_{\min}
=
\frac{1}{4\pi}
\frac{2\sqrt{d(d-2)}}{L}
=
\frac{\sqrt{d(d-2)}}{2\pi L}.
$$

</details>

### Exercise 4: Thermodynamics from the Euclidean action

Suppose a saddle has renormalized Euclidean action $I_E(\beta)$ and partition function

$$
Z(\beta)\approx e^{-I_E(\beta)}.
$$

Show that

$$
E=\frac{\partial I_E}{\partial \beta},
\qquad
S=\beta\frac{\partial I_E}{\partial \beta}-I_E.
$$

<details>
<summary><strong>Solution</strong></summary>

The thermal energy is

$$
E=-\frac{\partial}{\partial \beta}\log Z.
$$

Since

$$
\log Z \approx -I_E,
$$

we get

$$
E=\frac{\partial I_E}{\partial \beta}.
$$

The free energy is

$$
F=-\frac{1}{\beta}\log Z=\frac{I_E}{\beta}.
$$

Using

$$
F=E-TS=E-\frac{1}{\beta}S,
$$

we find

$$
S=\beta(E-F)
=\beta\frac{\partial I_E}{\partial \beta}-I_E.
$$

</details>

## Further reading

- G. W. Gibbons and S. W. Hawking, [Action Integrals and Partition Functions in Quantum Gravity](https://doi.org/10.1103/PhysRevD.15.2752).
- S. W. Hawking and D. N. Page, [Thermodynamics of Black Holes in Anti-de Sitter Space](https://doi.org/10.1007/BF01208266).
- E. Witten, [Anti de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
