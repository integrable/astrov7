---
title: "Hawking–Page transition"
description: "How the competition between thermal AdS and AdS black holes becomes a confinement/deconfinement transition in the dual large-N gauge theory."
sidebar:
  order: 20
---

## Why this matters

The planar black brane describes a thermal CFT on flat space. But a CFT can also be placed on a sphere:

$$
S^1_\beta \times S^{d-1}.
$$

In that case, the bulk has two natural Euclidean saddles with the same boundary:

$$
\text{thermal AdS}
\qquad
\text{and}
\qquad
\text{Euclidean AdS-Schwarzschild black hole}.
$$

The dominant saddle changes as the temperature is raised. This is the Hawking–Page transition. In holography, Witten's interpretation is that this gravitational transition is the large-$N$ confinement/deconfinement transition of the boundary gauge theory on $S^{d-1}$.

The transition teaches a lesson that appears everywhere in holography:

$$
\text{phase structure of the QFT}
\quad
\longleftrightarrow
\quad
\text{competition between bulk geometries}.
$$

The same boundary geometry can be filled in by more than one bulk spacetime. The leading large-$N$ thermodynamics is controlled by the saddle with the smallest Euclidean action.

## The boundary problem

The boundary thermal partition function is

$$
Z(\beta)=\mathrm{Tr}_{S^{d-1}} e^{-\beta H}.
$$

Equivalently, the Euclidean CFT lives on

$$
S^1_\beta \times S^{d-1}.
$$

The bulk path integral must sum over asymptotically AdS Euclidean geometries whose conformal boundary is this space:

$$
Z_{\mathrm{bulk}}[S^1_\beta\times S^{d-1}]
\approx
\sum_{\text{saddles }M}
\exp[-I_E[M]].
$$

At large $N$, this sum is dominated by the saddle with minimal renormalized Euclidean action.

The two basic saddles are:

1. **thermal AdS:** Euclidean global AdS with the time direction periodically identified;
2. **Euclidean AdS black hole:** a geometry where the thermal circle smoothly caps off at the horizon.

The two saddles have the same boundary but different topology.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Thermal AdS and AdS black hole saddles in the Hawking–Page transition](/figures/course/hawking-page-transition.svg)

<figcaption>

The Hawking–Page transition compares two bulk fillings of the same boundary $S^1_\beta\times S^{d-1}$. Thermal AdS dominates at low temperature; the large AdS black hole dominates above $T_{\rm HP}=(d-1)/(2\pi L)$. The thermal circle is noncontractible in thermal AdS but contractible in the black-hole saddle.

</figcaption>
</figure>

## Thermal AdS

Global Lorentzian AdS$_{d+1}$ has metric

$$
ds^2
=-\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+r^2d\Omega_{d-1}^2.
$$

The Euclidean thermal AdS saddle is obtained by $t=-i\tau$ and by identifying

$$
\tau\sim \tau+\beta.
$$

There is no horizon, so smoothness does not fix $\beta$. Any boundary temperature is allowed. The Euclidean topology is schematically

$$
S^1_\beta \times B^d,
$$

where $B^d$ is the spatial ball whose boundary is $S^{d-1}$.

The low-temperature CFT interpretation is a gas of color-singlet states on a compact space. At large $N$, the temperature-dependent part of the free energy is order $N^0$, not $N^2$.

## The global AdS-Schwarzschild black hole

The spherical AdS$_{d+1}$ black hole is

$$
ds^2
=-f(r)dt^2+\frac{dr^2}{f(r)}+r^2d\Omega_{d-1}^2,
$$

with

$$
f(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}}.
$$

The horizon radius $r_+$ is defined by $f(r_+)=0$, so

$$
\mu
=r_+^{d-2}\left(1+\frac{r_+^2}{L^2}\right).
$$

The Euclidean black-hole geometry has topology

$$
D^2\times S^{d-1},
$$

where the disk $D^2$ is formed by the Euclidean time circle and the radial direction. The time circle shrinks smoothly at the horizon.

## Temperature of the global black hole

After Wick rotation, smoothness at $r=r_+$ fixes the Euclidean period:

$$
T=\frac{f'(r_+)}{4\pi}.
$$

Using

$$
f(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}},
\qquad
\mu=r_+^{d-2}\left(1+\frac{r_+^2}{L^2}\right),
$$

we find

$$
f'(r_+)
=
\frac{d r_+}{L^2}+\frac{d-2}{r_+}.
$$

Therefore

$$
T(r_+)
=
\frac{1}{4\pi}
\left(
\frac{d r_+}{L^2}+\frac{d-2}{r_+}
\right)
=
\frac{d r_+^2+(d-2)L^2}{4\pi L^2 r_+}.
$$

This function has a minimum for $d>2$. Setting $dT/dr_+=0$ gives

$$
r_+^2=\frac{d-2}{d}L^2,
$$

and hence

$$
T_{\min}
=
\frac{\sqrt{d(d-2)}}{2\pi L}.
$$

For $T<T_{\min}$, there is no smooth spherical AdS black hole with boundary circle size $\beta=1/T$. For $T>T_{\min}$, there are two branches: a small black hole and a large black hole.

## Mass, entropy, and free energy

The mass of the AdS-Schwarzschild black hole is

$$
M
=
\frac{(d-1)\Omega_{d-1}}{16\pi G_{d+1}}\mu,
$$

where $\Omega_{d-1}$ is the volume of the unit $S^{d-1}$. The entropy is

$$
S
=
\frac{\Omega_{d-1}r_+^{d-1}}{4G_{d+1}}.
$$

The canonical free energy is

$$
F=M-TS.
$$

Substituting the expressions above gives the remarkably simple result

$$
F_{\mathrm{BH}}
=
\frac{\Omega_{d-1}r_+^{d-2}}{16\pi G_{d+1}}
\left(1-\frac{r_+^2}{L^2}\right),
$$

relative to thermal AdS with the same boundary circle.

Thus:

$$
F_{\mathrm{BH}}>0
\quad
\text{for}
\quad
r_+<L,
$$

and

$$
F_{\mathrm{BH}}<0
\quad
\text{for}
\quad
r_+>L.
$$

The Hawking–Page transition occurs at

$$
r_+=L.
$$

At this point the temperature is

$$
T_{\mathrm{HP}}
=
T(r_+=L)
=
\frac{d-1}{2\pi L}.
$$

For temperatures above $T_{\mathrm{HP}}$, the large black hole has lower free energy than thermal AdS and dominates the canonical ensemble.

## Small and large AdS black holes

The black-hole temperature curve has two branches above $T_{\min}$:

- the **small black hole**, with $r_+^2<(d-2)L^2/d$;
- the **large black hole**, with $r_+^2>(d-2)L^2/d$.

The sign of the specific heat follows from the sign of $dT/dr_+$. Since entropy increases with $r_+$,

$$
C
=T\frac{dS}{dT}
$$

has the same sign as $dr_+/dT$. Therefore:

$$
C<0
\quad
\text{for small AdS black holes},
$$

and

$$
C>0
\quad
\text{for large AdS black holes}.
$$

The small branch is thermodynamically unstable in the canonical ensemble. The large branch is stable once it exists, but it only dominates over thermal AdS when $T>T_{\mathrm{HP}}$.

The sequence is:

$$
T<T_{\min}:
\quad
\text{only thermal AdS},
$$

$$
T_{\min}<T<T_{\mathrm{HP}}:
\quad
\text{thermal AdS dominates},
$$

$$
T>T_{\mathrm{HP}}:
\quad
\text{large black hole dominates}.
$$

## Example: AdS$_5$/CFT$_4$

For AdS$_5$, the boundary dimension is $d=4$, and the CFT lives on

$$
S^1_\beta\times S^3.
$$

The temperature of the spherical black hole is

$$
T(r_+)
=
\frac{2r_+^2+L^2}{2\pi L^2 r_+}.
$$

The minimum temperature is

$$
T_{\min}
=
\frac{\sqrt{2}}{\pi L},
$$

and the Hawking–Page temperature is

$$
T_{\mathrm{HP}}
=
\frac{3}{2\pi L}.
$$

The transition temperature is of order the inverse sphere radius. That is natural: on a compact sphere, the theory has a finite-size scale.

## Gauge theory interpretation

The boundary theory is a large-$N$ gauge theory on a compact space. The low-temperature phase has only order-one thermal free energy:

$$
F_{\mathrm{low}} \sim N^0.
$$

The high-temperature phase has order-$N^2$ free energy:

$$
F_{\mathrm{high}} \sim -N^2 T^d.
$$

This is the large-$N$ distinction between a color-singlet confined phase and a deconfined adjoint plasma.

In the bulk:

$$
\text{thermal AdS}
\quad
\longleftrightarrow
\quad
\text{confined or singlet-dominated phase},
$$

while

$$
\text{large AdS black hole}
\quad
\longleftrightarrow
\quad
\text{deconfined plasma phase}.
$$

The free-energy scaling is the simplest evidence. Thermal AdS has no horizon, hence no classical horizon entropy. The large black hole has entropy

$$
S\sim \frac{L^{d-1}}{G_{d+1}}\sim N^2.
$$

This is the gravitational origin of the large number of deconfined degrees of freedom.

## The Polyakov loop and contractible thermal circles

A sharper diagnostic involves the Polyakov loop, a Wilson loop wrapping the Euclidean thermal circle. Holographically, a fundamental Wilson loop is computed by a string worldsheet ending on the corresponding boundary loop.

In thermal AdS, the Euclidean time circle is noncontractible in the bulk. There is no disk-shaped worldsheet ending on the thermal circle at leading classical order, so the Polyakov loop vanishes in the large-$N$ saddle:

$$
\langle P\rangle =0.
$$

In the Euclidean black-hole geometry, the thermal circle caps off at the horizon. A disk-shaped string worldsheet can end on the boundary thermal circle and fill into the bulk. Thus

$$
\langle P\rangle \neq 0
$$

in the black-hole phase.

This is the geometric version of center-symmetry behavior in the deconfinement transition. The phrase “center symmetry” should be used with some care in theories with matter content or boundary conditions that explicitly break it, but in the canonical large-$N$ discussion the thermal-circle topology gives the right intuition.

## Relation to the planar black brane

The previous page studied the planar black brane, dual to a CFT on flat space. The Hawking–Page transition is instead about a CFT on a sphere.

The two are related by a large-volume limit. At high temperature on $S^{d-1}$,

$$
T L \gg 1,
$$

the dominant black hole has

$$
r_+\gg L.
$$

Near a small patch of its horizon, the sphere looks flat, and the large black hole locally approaches the planar black brane. The free energy becomes extensive in the spatial volume of the sphere, and the thermodynamics approaches the black-brane equation of state.

As $L\to \infty$ with $T$ fixed,

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}\to 0.
$$

Thus on flat space, the deconfined black-brane phase dominates at any nonzero temperature in the classical holographic CFT. There is no finite-temperature Hawking–Page transition for the neutral planar black brane on $\mathbb R^{d-1}$.

## Topology is part of the physics

A useful way to remember the transition is:

$$
\text{thermal AdS: } S^1_\beta\times B^d,
$$

$$
\text{black hole: } D^2\times S^{d-1}.
$$

Both have boundary

$$
S^1_\beta\times S^{d-1},
$$

but they fill it in differently. The bulk topology tells the boundary theory whether the thermal circle is contractible, which controls the leading behavior of the Polyakov loop.

This is a recurring theme in holography. Boundary observables are sensitive not only to the local metric but also to global bulk topology.

## What is actually first order?

At infinite $N$, the Hawking–Page transition is sharp. The leading free energy jumps from order $N^0$ thermal behavior to order $N^2$ black-hole behavior, and the entropy jumps by order $N^2$.

At finite $N$, the exact CFT on a compact space has a finite-dimensional regulated Hilbert space below any energy cutoff and no truly singular thermodynamic transition. The sharp transition is a large-$N$ phenomenon.

This is analogous to many large-$N$ matrix models: a phase transition appears in the $N\to\infty$ limit even at finite spatial volume.

## Beyond the canonical case

The phrase “Hawking–Page transition” is often used more broadly for a transition between a horizonless geometry and a black-hole geometry. But one should keep the details straight.

For example:

- on $S^{d-1}$, thermal AdS competes with spherical AdS black holes;
- with a compact spatial circle, the AdS soliton can compete with a black brane;
- in bottom-up models, different black-hole branches or horizonless geometries can model different phases.

These are related ideas, but not identical calculations. The clean canonical calculation is the comparison between thermal global AdS and the global AdS-Schwarzschild black hole.

## Dictionary checkpoint

| Boundary gauge theory on $S^{d-1}$ | Bulk saddle |
|---|---|
| thermal partition function $Z(\beta)$ | Euclidean gravity path integral |
| low-temperature singlet phase | thermal AdS |
| high-temperature deconfined phase | large AdS black hole |
| order-$N^0$ thermal free energy | horizonless saddle |
| order-$N^2$ entropy and free energy | black-hole horizon |
| Polyakov loop zero at leading order | noncontractible thermal circle |
| Polyakov loop nonzero | contractible thermal circle |
| deconfinement transition | Hawking–Page transition |

The transition is therefore not merely a black-hole curiosity. It is the gravitational computation of a large-$N$ phase transition in the boundary theory.

## Common confusions

### “The Hawking–Page transition happens for every black brane.”

No. The standard Hawking–Page transition compares thermal global AdS with a spherical AdS black hole for boundary $S^1_\beta\times S^{d-1}$. The neutral planar black brane on flat space does not have a finite-temperature Hawking–Page transition of this type.

### “Thermal AdS has zero free energy.”

After a conventional subtraction, its temperature-dependent free energy is order $N^0$. But the CFT on a sphere can also have a Casimir energy of order $N^2$. The Hawking–Page comparison concerns the properly renormalized action difference between saddles with the same boundary.

### “The small black hole is the confined phase.”

No. The small black hole is a black-hole saddle with negative specific heat. It is not the dominant low-temperature canonical saddle. The low-temperature phase is thermal AdS.

### “The transition means the CFT becomes gravitational.”

The CFT is always nongravitational. The transition means that the dominant bulk saddle changes. The same boundary quantum system has different semiclassical bulk descriptions in different thermal regimes.

### “The Polyakov-loop argument is just a local horizon argument.”

It is topological. The key distinction is whether the Euclidean thermal circle is contractible in the bulk. A contractible circle permits a disk worldsheet ending on the boundary loop; a noncontractible circle does not.

## Exercises

### Exercise 1: Derive the global black-hole temperature

For

$$
f(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}},
\qquad
f(r_+)=0,
$$

show that

$$
T(r_+)=\frac{d r_+^2+(d-2)L^2}{4\pi L^2 r_+}.
$$

<details>
<summary><strong>Solution</strong></summary>

The horizon condition gives

$$
\mu=r_+^{d-2}\left(1+\frac{r_+^2}{L^2}\right).
$$

The temperature is

$$
T=\frac{f'(r_+)}{4\pi}.
$$

Since

$$
f'(r)=\frac{2r}{L^2}+\frac{(d-2)\mu}{r^{d-1}},
$$

we find

$$
f'(r_+)
=\frac{2r_+}{L^2}
+\frac{d-2}{r_+}
\left(1+\frac{r_+^2}{L^2}\right)
=\frac{d r_+}{L^2}+\frac{d-2}{r_+}.
$$

Therefore

$$
T(r_+)=\frac{1}{4\pi}
\left(\frac{d r_+}{L^2}+\frac{d-2}{r_+}\right)
=\frac{d r_+^2+(d-2)L^2}{4\pi L^2r_+}.
$$

</details>

### Exercise 2: Locate the minimum temperature

Show that $T(r_+)$ has a minimum at

$$
r_+^2=\frac{d-2}{d}L^2,
$$

and find $T_{\min}$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
T(r_+)=\frac{1}{4\pi}
\left(\frac{d r_+}{L^2}+\frac{d-2}{r_+}\right).
$$

Then

$$
\frac{dT}{dr_+}
=\frac{1}{4\pi}
\left(\frac{d}{L^2}-\frac{d-2}{r_+^2}\right).
$$

Setting this to zero gives

$$
r_+^2=\frac{d-2}{d}L^2.
$$

Substituting back into $T(r_+)$ gives

$$
T_{\min}
=\frac{\sqrt{d(d-2)}}{2\pi L}.
$$

</details>

### Exercise 3: Find the Hawking–Page temperature

Given

$$
F_{\mathrm{BH}}
=
\frac{\Omega_{d-1}r_+^{d-2}}{16\pi G_{d+1}}
\left(1-\frac{r_+^2}{L^2}\right),
$$

show that the Hawking–Page transition occurs at

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}.
$$

<details>
<summary><strong>Solution</strong></summary>

The transition occurs when the black-hole free energy equals the thermal AdS free energy, which in this normalization means

$$
F_{\mathrm{BH}}=0.
$$

The nonzero solution is

$$
r_+=L.
$$

Using

$$
T(r_+)=\frac{d r_+^2+(d-2)L^2}{4\pi L^2r_+},
$$

we get

$$
T_{\mathrm{HP}}
=\frac{dL^2+(d-2)L^2}{4\pi L^3}
=\frac{2d-2}{4\pi L}
=\frac{d-1}{2\pi L}.
$$

</details>

### Exercise 4: Explain the planar limit

Use

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}
$$

to explain why there is no finite Hawking–Page temperature for the neutral planar black brane on $\mathbb R^{d-1}$.

<details>
<summary><strong>Solution</strong></summary>

The planar limit corresponds to making the boundary sphere very large, $L\to\infty$, while zooming in on a small local patch. Then

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}\to 0.
$$

Therefore any fixed nonzero temperature lies above the transition temperature in the infinite-volume limit. The dominant saddle becomes the planar black brane. This is why the neutral black brane on flat space does not exhibit a finite-temperature Hawking–Page transition.

</details>

## Further reading

- S. W. Hawking and D. N. Page, [Thermodynamics of Black Holes in Anti-de Sitter Space](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-87/issue-4/Thermodynamics-of-black-holes-in-anti-de-Sitter-space/cmp/1103922135.full).
- E. Witten, [Anti de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
