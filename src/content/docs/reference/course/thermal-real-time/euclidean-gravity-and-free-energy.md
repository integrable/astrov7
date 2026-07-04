---
title: "Euclidean Gravity and Free Energy"
description: "How the renormalized Euclidean gravitational action computes thermal partition functions, free energies, entropy, and phase dominance in holography."
sidebar:
  order: 30
---

## Why this matters

The previous pages used black holes and black branes as geometries that encode thermal CFT states. This page explains the quantitative rule behind that statement:

$$
Z_{\mathrm{CFT}}(\beta)
=
\mathrm{Tr}_{\mathcal H_\Sigma}\, e^{-\beta H}
\quad\longleftrightarrow\quad
Z_{\mathrm{bulk}}^{E}[S^1_\beta\times \Sigma]
\approx
\exp\!\left[-I_{E,\mathrm{ren}}\right].
$$

In the saddle approximation,

$$
I_{E,{\rm ren}} = \beta F,
$$

where $F$ is the Helmholtz free energy of the boundary theory in the ensemble specified by the Euclidean boundary conditions. This is the workhorse behind Hawking–Page transitions, black-brane thermodynamics, holographic pressure, and the comparison of competing saddles.

The conceptual point is simple but powerful: **equilibrium thermodynamics in the boundary theory is computed by comparing smooth Euclidean bulk fillings of the same boundary thermal manifold.**

## Boundary setup: thermal partition functions

For a QFT on a spatial manifold $\Sigma$, the canonical thermal partition function is

$$
Z(\beta)= {\rm Tr}_{\mathcal H_\Sigma} e^{-\beta H},
\qquad
\beta=\frac{1}{T}.
$$

The Euclidean path integral representation is a path integral on

$$
S^1_\beta\times \Sigma,
$$

with periodic boundary conditions for bosons and antiperiodic boundary conditions for fermions around $S^1_\beta$.

If one also turns on chemical potentials, sources, or background fields, the partition function becomes a functional. For example, a source $J$ for an operator $\mathcal O$ and a background metric $g_{(0)ij}$ give

$$
Z_{\rm CFT}[g_{(0)},J;\beta]
=
\int_{S^1_\beta\times \Sigma}\!\mathcal D\Phi\,
\exp\!\left(-S_E[\Phi;g_{(0)}]-\int J\mathcal O\right).
$$

In thermal holography, this boundary Euclidean manifold is not merely decorative. It is the asymptotic boundary condition for the Euclidean bulk saddle.

## Bulk setup: fill the thermal boundary

The Euclidean bulk path integral is formally

$$
Z_{\rm bulk}^{E}[g_{(0)},J]
=
\int_{\partial M\sim (g_{(0)},J)} \mathcal Dg\,\mathcal D\phi\, e^{-I_E[g,\phi]}.
$$

In the classical gravity limit this becomes a saddle-point expansion:

$$
Z_{\rm bulk}^{E}[g_{(0)},J]
\approx
\sum_{\text{smooth saddles }a}
\exp\!\left[-I_{E,{\rm ren}}^{(a)}[g_{(0)},J]\right].
$$

At leading order in large $N$, the dominant saddle is the one with the smallest renormalized Euclidean action. Thus

$$
F
=
- T\log Z
\approx
T\,I_{E,{\rm ren}}^{\rm dominant}.
$$

Equivalently,

$$
I_{E,{\rm ren}}^{\rm dominant}=\beta F.
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![Euclidean gravity and free energy workflow](/figures/course/euclidean-free-energy-workflow.svg)

<figcaption>

The Euclidean thermal CFT partition function is represented by a bulk filling whose conformal boundary contains the same thermal circle. In the saddle approximation, the renormalized Euclidean action gives $I_{E,{\rm ren}}=\beta F$; thermodynamic derivatives of $I_{E,{\rm ren}}$ give $E$, $S$, pressure, and charge densities.

</figcaption>
</figure>

## The Euclidean gravitational action

For pure Einstein gravity with negative cosmological constant, a common Euclidean convention is

$$
I_E
=
-\frac{1}{16\pi G_{d+1}}
\int_M d^{d+1}x\sqrt g\,(R-2\Lambda)
-\frac{1}{8\pi G_{d+1}}
\int_{\partial M} d^d x\sqrt\gamma\,K
+I_{\rm ct}.
$$

Here:

- $\gamma_{ij}$ is the induced metric on the cutoff boundary;
- $K$ is the trace of the extrinsic curvature;
- $I_{\rm ct}$ is a sum of local counterterms on the cutoff surface;
- $\Lambda=-d(d-1)/(2L^2)$ for AdS$_{d+1}$.

The counterterms are not optional. The raw on-shell action diverges because the AdS boundary has infinite volume. Holographic renormalization defines

$$
I_{E,{\rm ren}}
=
\lim_{\epsilon\to 0}
\left(
I_E^{z\ge \epsilon}\right),
$$

where $I_E^{z\ge \epsilon}$ includes the bulk action, the Gibbons–Hawking–York boundary term, and the counterterms on the cutoff surface $z=\epsilon$.

A useful warning: different sign conventions for the Euclidean action and extrinsic curvature exist in the literature. The invariant statement is the saddle relation

$$
Z_E \approx e^{-I_{E,{\rm ren}}}.
$$

## Thermodynamics from $I_E$

In the canonical ensemble,

$$
F = \frac{I_{E,{\rm ren}}}{\beta},
\qquad
E = \frac{\partial I_{E,{\rm ren}}}{\partial \beta},
\qquad
S = \beta E - I_{E,{\rm ren}}.
$$

Equivalently,

$$
S
=
\left(\beta\frac{\partial}{\partial \beta}-1\right) I_{E,{\rm ren}}.
$$

If the ensemble includes a chemical potential $\mu$ for a charge $Q$, then the Euclidean source is usually the boundary value of a bulk gauge field component, and the action computes the grand potential:

$$
I_{E,{\rm ren}}=\beta \Omega,
\qquad
\Omega = E-TS-\mu Q.
$$

Boundary conditions matter. Fixing the boundary value of $A_\tau$ computes a grand-canonical ensemble, while fixing electric flux computes a canonical ensemble. These two choices differ by a boundary Legendre transform.

## Example: planar black brane free energy

Consider the Euclidean planar AdS$_{d+1}$ black brane

$$
ds_E^2
=
\frac{L^2}{z^2}
\left[
f(z)d\tau^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

Smoothness at the Euclidean horizon requires

$$
\beta=\frac{4\pi z_h}{d},
\qquad
T=\frac{d}{4\pi z_h}.
$$

For this solution, holographic renormalization gives the renormalized Euclidean action density

$$
\frac{I_{E,{\rm ren}}}{\beta V_{d-1}}
=
-\frac{L^{d-1}}{16\pi G_{d+1}}\frac{1}{z_h^d}.
$$

Therefore the free energy density is

$$
f_{\rm therm}
\equiv
\frac{F}{V_{d-1}}
=
-\frac{L^{d-1}}{16\pi G_{d+1}}\frac{1}{z_h^d}.
$$

The pressure is

$$
p=-f_{\rm therm}
=
\frac{L^{d-1}}{16\pi G_{d+1}}\frac{1}{z_h^d},
$$

and conformal invariance gives

$$
\varepsilon=(d-1)p
=
\frac{(d-1)L^{d-1}}{16\pi G_{d+1}}\frac{1}{z_h^d}.
$$

The entropy density is either the thermodynamic derivative

$$
s=-\frac{\partial f_{\rm therm}}{\partial T},
$$

or the Bekenstein–Hawking area density

$$
s
=
\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}.
$$

Using $T=d/(4\pi z_h)$, these agree. The first law also works:

$$
d\varepsilon = T ds,
\qquad
\varepsilon + p = Ts.
$$

This is one of the cleanest demonstrations that the horizon is not merely a geometric feature. It carries the entropy of the thermal CFT state.

## A quick regulated-action check

It is useful to see where the free energy comes from. On shell,

$$
R=-\frac{d(d+1)}{L^2},
\qquad
R-2\Lambda=-\frac{2d}{L^2}.
$$

For the planar black brane,

$$
\sqrt g = \frac{L^{d+1}}{z^{d+1}}.
$$

Thus the regulated bulk action per $\beta V_{d-1}$ is

$$
\frac{I_{\rm bulk}}{\beta V_{d-1}}
=
\frac{dL^{d-1}}{8\pi G_{d+1}}
\int_\epsilon^{z_h}\frac{dz}{z^{d+1}}
=
\frac{L^{d-1}}{8\pi G_{d+1}}
\left(\frac{1}{\epsilon^d}-\frac{1}{z_h^d}\right).
$$

This is divergent. The Gibbons–Hawking–York term and counterterms cancel the $\epsilon^{-d}$ divergence and adjust the finite term. The final renormalized answer is

$$
\frac{I_{E,{\rm ren}}}{\beta V_{d-1}}
=
-\frac{L^{d-1}}{16\pi G_{d+1}z_h^d}.
$$

The lesson is not the numerical factor alone. The lesson is that finite thermodynamics comes from the **renormalized** on-shell action, not from the bulk volume integral by itself.

## Example: global AdS black holes

For a CFT on $S^{d-1}$, the relevant Euclidean boundary is

$$
S^1_\beta\times S^{d-1}.
$$

Two important smooth bulk fillings are:

$$
\text{thermal global AdS},
\qquad
\text{Euclidean AdS-Schwarzschild black hole}.
$$

The global AdS-Schwarzschild metric has

$$
ds_E^2
=
f(r)d\tau^2+\frac{dr^2}{f(r)}+r^2 d\Omega_{d-1}^2,
$$

with

$$
f(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}},
\qquad
\mu=r_h^{d-2}\left(1+\frac{r_h^2}{L^2}\right).
$$

The temperature is

$$
T
=
\frac{d r_h^2+(d-2)L^2}{4\pi L^2 r_h}.
$$

The free energy is

$$
F
=
\frac{\Omega_{d-1} r_h^{d-2}}{16\pi G_{d+1}L^2}
\left(L^2-r_h^2\right).
$$

So large black holes with $r_h>L$ have $F<0$ and dominate over thermal AdS, while small black holes with $r_h<L$ have $F>0$ and do not dominate the canonical ensemble. The transition occurs at

$$
r_h=L,
\qquad
T_{\rm HP}=\frac{d-1}{2\pi L}.
$$

This is the Hawking–Page transition. On the boundary, it is interpreted as a large-$N$ thermal phase transition on compact space.

## Entropy from the Euclidean action

The formula

$$
S=\left(\beta\frac{\partial}{\partial\beta}-1\right)I_E
$$

reproduces the Bekenstein–Hawking entropy. One intuitive derivation uses a conical defect.

Near a Euclidean horizon, the metric locally looks like

$$
ds^2 \approx dR^2 + R^2 d\theta^2 + ds_{\mathcal H}^2.
$$

Smoothness requires $\theta\sim \theta+2\pi$. If instead the angular period is $2\pi\alpha$, the origin has a conical defect with localized curvature. Evaluating the derivative of the action with respect to $\alpha$ at $\alpha=1$ gives

$$
S=\frac{\mathrm{Area}(\mathcal H)}{4G_{d+1}}.
$$

In higher-derivative gravity, this result is replaced by Wald entropy or its appropriate generalization. In two-derivative Einstein gravity, it is the area law.

## Which saddle wins?

At leading large $N$, the saddle with smallest $I_E$ dominates:

$$
Z\approx e^{-I_{E}^{\rm min}}.
$$

If two saddles exchange dominance as $\beta$ changes, the boundary theory has a large-$N$ phase transition. The Hawking–Page transition is the canonical example:

$$
\Delta I_E(\beta)=I_E^{\rm black\ hole}-I_E^{\rm thermal\ AdS}.
$$

Then

$$
\Delta I_E<0
\quad\Rightarrow\quad
\text{black hole dominates},
$$

while

$$
\Delta I_E>0
\quad\Rightarrow\quad
\text{thermal AdS dominates}.
$$

At finite $N$, the transition is rounded or corrected by subleading saddles and quantum fluctuations. In the strict classical gravity limit, the saddle competition becomes sharp.

## Dictionary checkpoint

| Boundary quantity | Euclidean bulk quantity |
|---|---|
| thermal circle $S^1_\beta$ | asymptotic Euclidean time circle |
| partition function $Z(\beta)$ | bulk Euclidean path integral |
| free energy $F$ | $I_{E,{\rm ren}}/\beta$ |
| entropy $S$ | $\beta\partial_\beta I_E-I_E$ or horizon area |
| pressure $p$ | $-F/V$ for homogeneous states |
| chemical potential $\mu$ | boundary value of Euclidean gauge field |
| phase transition | exchange of dominant Euclidean saddle |

The Euclidean action computes equilibrium thermodynamics. It does not, by itself, compute real-time response. For that we need the Lorentzian prescription.

## Common confusions

### “The free energy is just the bulk action without boundary terms.”

No. The Gibbons–Hawking–York term and counterterms are essential. Without them, the variational problem is not correct and the action is divergent.

### “A Euclidean black hole has a Lorentzian horizon.”

The Euclidean geometry has a smooth origin where the thermal circle caps off. The Lorentzian horizon is recovered after analytic continuation. The Euclidean cap is why the temperature is fixed.

### “All saddles with the same boundary are equally important.”

They all contribute in principle, but in the classical large-$N$ limit the smallest renormalized action dominates. Subdominant saddles are exponentially suppressed by factors of order $e^{-N^2}$ in standard large-$N$ examples.

### “The Euclidean action always computes Helmholtz free energy.”

Only if the boundary conditions define a canonical ensemble. If sources such as chemical potentials are fixed, the action computes an appropriate thermodynamic potential, usually a grand potential.

### “Euclidean correlators are enough for transport.”

Euclidean correlators determine Matsubara data. Transport coefficients require real-time retarded correlators and a prescription for horizon boundary conditions. This is the subject of the next page.

## Exercises

### Exercise 1: Planar black-brane equation of state

Starting from

$$
f_{\rm therm}
=
-\frac{L^{d-1}}{16\pi G_{d+1}z_h^d},
\qquad
T=\frac{d}{4\pi z_h},
$$

show that $\varepsilon=(d-1)p$ and $\varepsilon+p=Ts$.

<details>
<summary><strong>Solution</strong></summary>

The pressure is

$$
p=-f_{\rm therm}
=
\frac{L^{d-1}}{16\pi G_{d+1}z_h^d}.
$$

Conformal invariance gives $T^i{}_i=0$, so for a homogeneous thermal state

$$
-\varepsilon+(d-1)p=0,
$$

hence

$$
\varepsilon=(d-1)p.
$$

The entropy density from the horizon area is

$$
s=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}.
$$

Then

$$
Ts
=
\frac{d}{4\pi z_h}\frac{L^{d-1}}{4G_{d+1}z_h^{d-1}}
=
\frac{dL^{d-1}}{16\pi G_{d+1}z_h^d}
=dp.
$$

Since $\varepsilon+p=(d-1)p+p=dp$, we get

$$
\varepsilon+p=Ts.
$$

</details>

### Exercise 2: Hawking–Page free energy sign

For a global AdS$_{d+1}$ black hole,

$$
F
=
\frac{\Omega_{d-1} r_h^{d-2}}{16\pi G_{d+1}L^2}
\left(L^2-r_h^2\right).
$$

For which values of $r_h$ does the black hole dominate over thermal AdS?

<details>
<summary><strong>Solution</strong></summary>

With the usual normalization in which thermal AdS has $F=0$, the black hole dominates when $F<0$. Since the prefactor

$$
\frac{\Omega_{d-1} r_h^{d-2}}{16\pi G_{d+1}L^2}
$$

is positive, the sign is determined by $L^2-r_h^2$. Therefore

$$
F<0
\quad\Longleftrightarrow\quad
r_h>L.
$$

The transition occurs at $r_h=L$, corresponding to

$$
T_{\rm HP}=\frac{d-1}{2\pi L}.
$$

</details>

### Exercise 3: Entropy from the action

Suppose a saddle has

$$
I_E(\beta)=\beta M-S_0,
$$

where $M$ and $S_0$ are independent of $\beta$ along the family considered. Use

$$
S=\left(\beta\partial_\beta-1\right)I_E
$$

to find the entropy.

<details>
<summary><strong>Solution</strong></summary>

First compute

$$
\partial_\beta I_E = M.
$$

Then

$$
\left(\beta\partial_\beta-1\right)I_E
=
\beta M-(\beta M-S_0)
=S_0.
$$

For an Einstein black hole, $S_0$ is the Bekenstein–Hawking entropy

$$
S_0=\frac{\mathrm{Area}(\mathcal H)}{4G}.
$$

</details>

## Further reading

- G. W. Gibbons and S. W. Hawking, [Action Integrals and Partition Functions in Quantum Gravity](https://doi.org/10.1103/PhysRevD.15.2752).
- S. W. Hawking and D. N. Page, [Thermodynamics of Black Holes in Anti-de Sitter Space](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-87/issue-4/Thermodynamics-of-black-holes-in-anti-de-Sitter-space/cmp/1103922135.full).
- E. Witten, [Anti de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
