---
title: "Heavy Operators and Geodesics"
description: "How large-dimension boundary operators become massive bulk particles and why their two-point functions are controlled by regularized geodesic lengths."
sidebar:
  order: 40
---

## Why this matters

A scalar field in AdS is dual to a scalar primary operator. When the operator dimension is large,

$$
\Delta\gg 1,
$$

the dual bulk particle is heavy in AdS units. A heavy particle follows a saddle-point worldline, so its propagator is controlled by the length of a geodesic. This gives one of the most geometric approximations in AdS/CFT:

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
\sim
\exp\left[-\frac{\Delta}{L}\,\ell_{\rm ren}(x_1,x_2)\right].
$$

Here $\ell_{\rm ren}$ is the regularized length of a bulk geodesic connecting the boundary insertion points. This formula makes the slogan “correlators probe geometry” very concrete.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Heavy operators and geodesic approximation in AdS](/figures/course/heavy-operators-geodesics.svg)

<figcaption>

For $1\ll \Delta\ll C_T$, a heavy scalar operator creates a massive probe particle. The Euclidean two-point function is dominated by a boundary-anchored geodesic. If $\Delta$ becomes comparable to the central charge, the particle backreacts and the probe approximation fails.

</figcaption>
</figure>

The geodesic approximation is useful because it turns some field-theory questions into geometric questions. It is also dangerous when used too casually. The approximation has a controlled regime, requires regularization near the boundary, and becomes subtle in Lorentzian signature and in black-hole backgrounds.

This page explains the clean version first.

## Heavy does not always mean the same thing

There are several different meanings of “heavy operator” in holography. It is important not to mix them.

For this page, a heavy scalar operator means

$$
1\ll \Delta \ll C_T,
$$

where $C_T$ is the coefficient of the stress-tensor two-point function. In holographic theories,

$$
C_T\sim \frac{L^{d-1}}{G_N}\sim N^2
$$

for the standard matrix-like examples. The condition $1\ll\Delta$ makes the WKB/geodesic approximation reliable. The condition $\Delta\ll C_T$ means that the object is still a probe: its gravitational backreaction is small.

There are other important regimes:

| Operator size | Bulk interpretation |
|---|---|
| $\Delta=O(1)$ | light bulk field; use wave equation, not geodesic WKB |
| $1\ll\Delta\ll C_T$ | heavy probe particle; geodesic approximation |
| $\Delta\sim C_T$ | backreacting object; conical defect, star, brane, or black hole depending on details |
| $\Delta$ string-scale | stringy state; particle approximation may fail |
| large spin $\ell\gg1$ | spinning or extended trajectory; null/spacelike limits matter |

This page focuses on the probe-particle regime.

## From mass to dimension

For a scalar field in AdS$_{d+1}$,

$$
m^2L^2=\Delta(\Delta-d).
$$

Solving for $\Delta$ in standard quantization gives

$$
\Delta
=
\frac d2+
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

When $mL\gg1$,

$$
\Delta
=
mL+\frac d2+O\!\left(\frac{1}{mL}\right).
$$

Thus a large scaling dimension corresponds to a large particle mass in AdS units. At leading WKB order one often identifies $mL$ and $\Delta$. The difference by $d/2$ affects subleading prefactors and normalization, but not the leading exponential in the large-$\Delta$ approximation.

## Worldline representation

A massive scalar propagator has a worldline representation of the schematic form

$$
G(X_1,X_2)
\sim
\int_{X(0)=X_1}^{X(1)=X_2}
\mathcal D X\,\exp[-m\,\ell[X]],
$$

where $\ell[X]$ is the proper length of the path $X(\lambda)$:

$$
\ell[X]
=
\int d\lambda\,
\sqrt{
g_{MN}(X)
\frac{dX^M}{d\lambda}
\frac{dX^N}{d\lambda}
}.
$$

For $mL\gg1$, the path integral is dominated by stationary paths. Varying $\ell[X]$ gives the geodesic equation. Therefore

$$
G(X_1,X_2)
\approx
\mathcal A(X_1,X_2)\,
e^{-m\ell_{\rm geo}(X_1,X_2)},
$$

where $\mathcal A$ is a fluctuation determinant. At leading exponential order, only the geodesic length matters.

To obtain a boundary correlator, take $X_1$ and $X_2$ to the AdS boundary with the usual holographic rescaling. Since geodesics reaching the boundary have infinite length, the length must be regulated and renormalized.

## Example: Euclidean Poincaré AdS

Work in Euclidean Poincaré AdS$_{d+1}$,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+d x^i d x^i
\right),
\qquad
z>0.
$$

Consider two boundary points separated by

$$
R=|x_1-x_2|.
$$

By translation and rotation, put them at

$$
x_1=-\frac R2,
\qquad
x_2=\frac R2,
$$

along one boundary direction. The geodesic in the $(x,z)$ plane is the semicircle

$$
x^2+z^2=\left(\frac R2\right)^2.
$$

Regulate the endpoints by stopping the geodesic at $z=\epsilon$. Parametrize the semicircle as

$$
x=\frac R2\cos\theta,
\qquad
z=\frac R2\sin\theta.
$$

The endpoints are at

$$
\sin\theta_\epsilon=\frac{2\epsilon}{R}.
$$

Along the curve,

$$
dx^2+dz^2
=
\left(\frac R2\right)^2d\theta^2,
$$

so the proper length is

$$
\ell_\epsilon
=
L
\int_{\theta_\epsilon}^{\pi-\theta_\epsilon}
\frac{d\theta}{\sin\theta}.
$$

Using

$$
\int \frac{d\theta}{\sin\theta}
=
\log\tan\frac{\theta}{2},
$$

one finds

$$
\ell_\epsilon
=
2L\log\frac{R}{\epsilon}
+
O(\epsilon^2).
$$

The divergence $2L\log(1/\epsilon)$ is universal. Define the renormalized length by subtracting the endpoint divergence:

$$
\ell_{\rm ren}
=
\lim_{\epsilon\to0}
\left[
\ell_\epsilon-2L\log\frac{1}{\epsilon}
\right]
=
2L\log R
+\text{constant}.
$$

The constant depends on the precise subtraction convention and becomes an operator-normalization choice.

Then

$$
e^{-m\ell_{\rm ren}}
\propto
R^{-2mL}.
$$

Using $mL\simeq\Delta$ at leading order gives

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
\propto
\frac{1}{|x_1-x_2|^{2\Delta}},
$$

which is the CFT two-point function. The geodesic approximation has reproduced the correct conformal scaling.

## Relation to the exact propagator

The exact Euclidean boundary two-point function of a scalar primary is

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
=
\frac{C_\Delta}{|x_1-x_2|^{2\Delta}}.
$$

The geodesic approximation captures the leading exponential dependence at large $\Delta$. It does not determine the full normalization $C_\Delta$ unless one also computes the fluctuation determinant and keeps careful track of holographic normalization.

This distinction matters. The geodesic formula should be read as

$$
\log\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
=
-\frac{\Delta}{L}\ell_{\rm ren}(x_1,x_2)
+
O(\Delta^0),
$$

not as an exact equality including prefactors.

## Why the boundary length must be renormalized

A geodesic ending at the AdS boundary always has infinite proper length. Near $z=0$,

$$
ds
\sim
L\frac{dz}{z},
$$

so

$$
\int_\epsilon \frac{dz}{z}
\sim
\log\frac{1}{\epsilon}.
$$

This divergence is not a problem. It is the geometric form of the standard UV divergence associated with inserting local operators. In the geodesic approximation, renormalizing the length is the worldline version of holographic renormalization.

One can think of each boundary endpoint as contributing a wavefunction renormalization factor,

$$
Z_\epsilon^{1/2}
\sim
\epsilon^{-\Delta}.
$$

Multiplying the regulated bulk propagator by the appropriate boundary factors removes the divergence and leaves the finite CFT correlator.

## Global AdS and the cylinder

In global Euclidean AdS, the boundary is conformal to

$$
\mathbb R_\tau\times S^{d-1}.
$$

For two insertions on the cylinder separated by Euclidean time $\tau$ and angle $\theta$, conformal symmetry fixes the two-point function to be

$$
\langle
\mathcal O(\tau,\Omega)
\mathcal O(0,\Omega')
\rangle
\propto
\frac{1}{
\left[
2(\cosh\tau-\cos\theta)
\right]^\Delta
},
$$

where $\cos\theta=\Omega\cdot\Omega'$. A boundary-anchored geodesic in global AdS reproduces the leading large-$\Delta$ exponential of this expression.

The cylinder viewpoint is conceptually useful. At large $\Delta$, the operator creates a high-energy bulk particle state. The propagation of that particle between boundary insertions is dominated by the classical path through global AdS.

## Thermal states and black holes

In a finite-temperature holographic state, the bulk geometry is often an AdS black hole or black brane. The geodesic approximation then gives

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle_\beta
\sim
e^{-\Delta \ell_{\rm ren}^{\rm black\ hole}(x_1,x_2)/L}.
$$

This makes heavy-operator correlators useful probes of black-hole geometry. Equal-time spatial correlators can probe how geodesics dip toward the horizon. Time-dependent correlators can reveal singularities, horizons, and analytic structure, though this is much more subtle than the Euclidean vacuum example.

For example, in a planar black brane,

$$
ds^2
=
\frac{L^2}{z^2}
\left[
f(z)d\tau^2
+d\vec x^2
+
\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

a spatial geodesic connecting boundary points separated by $\ell$ reaches a turning point $z_\ast$. As $\ell$ becomes large, $z_\ast$ approaches the horizon $z_h$. Thus long-distance thermal correlators are controlled by near-horizon geometry.

This is a good example of the general principle:

$$
\text{large boundary separations}
\quad
\longleftrightarrow
\quad
\text{deep bulk probes}.
$$

## Lorentzian caveats

The Euclidean geodesic approximation is clean. Lorentzian correlators require more care.

First, different correlators require different prescriptions: time-ordered, retarded, Wightman, and in-in correlators are not the same. Second, real Lorentzian geodesics may not connect the desired boundary points, or multiple geodesics may contribute. Third, complex geodesics can be required. Fourth, Stokes phenomena can change which saddle dominates as one varies the insertion points.

A safe way to say the rule is:

$$
\text{large-}\Delta\text{ correlators}
\quad
\text{are controlled by worldline saddles},
$$

but those saddles are not always simple real spacelike geodesics.

This caveat is especially important in black-hole backgrounds. Statements like “the correlator probes behind the horizon” can be meaningful in special setups, but they depend on the analytic continuation and the correlator being computed.

## Heavy-light and backreaction

So far the heavy operator has been a probe. If the dimension becomes comparable to $C_T$, the operator creates a state with order-one gravitational backreaction:

$$
\Delta\sim C_T
\quad
\Rightarrow
\quad
G_N E_{\rm bulk}\sim L^{d-2}.
$$

In AdS$_3$/CFT$_2$, such heavy operators may create conical defects or BTZ black holes, depending on their dimension. In higher dimensions, sufficiently heavy insertions can create stars, branes, or black-hole-like geometries.

This leads to an important distinction:

- **probe heavy operators**: use geodesics in a fixed background;
- **backreacting heavy operators**: first determine the geometry sourced by the operator, then compute probes or observables in that geometry.

Many modern applications use heavy-light correlators: heavy operators create a background state, while light operators probe it. That is related to the present page but is conceptually one step beyond it.

## Relation to Wilson lines and minimal surfaces

The geodesic approximation is the particle version of a broader semiclassical idea. A heavy point particle is dominated by a worldline length,

$$
S_{\rm particle}=m\ell.
$$

A string worldsheet is dominated by an area,

$$
S_{\rm string}=\frac{1}{2\pi\alpha'}\mathrm{Area}.
$$

A brane is dominated by a worldvolume action. Thus many holographic probes have the general form

$$
\langle \text{probe observable}\rangle
\sim
e^{-S_{\rm classical\ probe}}.
$$

The Wilson-loop page will use the same idea with strings instead of particles.

## Dictionary checkpoint

The heavy-operator/geodesic dictionary is:

| Boundary quantity | Bulk geometric quantity |
|---|---|
| scalar primary with $\Delta\gg1$ | massive bulk particle with $mL\simeq\Delta$ |
| two-point function | particle propagator |
| leading large-$\Delta$ exponent | regularized geodesic length |
| endpoint UV divergence | near-boundary length divergence |
| large separation | geodesic probes deeper radial region |
| $\Delta\ll C_T$ | probe limit |
| $\Delta\sim C_T$ | backreacting object |

The most important formula is

$$
\log
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
=
-\frac{\Delta}{L}\ell_{\rm ren}(x_1,x_2)
+
O(\Delta^0).
$$

## Common confusions

### “A geodesic computes the exact two-point function.”

Usually no. The geodesic length gives the leading exponential in the large-$\Delta$ limit. Exact correlators require solving the wave equation or computing the full bulk propagator, including prefactors and normalization.

### “Heavy means backreacting.”

Not necessarily. In this page, heavy means $\Delta\gg1$, but the probe approximation also requires $\Delta\ll C_T$. Backreaction becomes important when $\Delta$ is comparable to the number of degrees of freedom.

### “Every boundary pair is connected by one real geodesic.”

In Euclidean AdS, the basic vacuum example is simple. In Lorentzian geometries or black-hole backgrounds, there may be no real spacelike geodesic, multiple geodesics, complex geodesics, or saddles whose dominance changes.

### “The radial depth is always exactly the energy scale.”

The radial direction is related to scale, but the relationship depends on coordinates, state, observable, and renormalization scheme. Geodesics give a vivid geometric picture, not a universal one-line formula.

### “The $d/2$ difference between $mL$ and $\Delta$ never matters.”

It does not matter for the leading large-$\Delta$ exponential, but it can matter for subleading terms and normalization. When precision is needed, use the exact relation

$$
\Delta
=
\frac d2+
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

## Exercises

### Exercise 1: Derive the semicircle geodesic length

In Euclidean Poincaré AdS,

$$
ds^2=\frac{L^2}{z^2}(dz^2+dx^2),
$$

consider the semicircle

$$
x=\frac R2\cos\theta,
\qquad
z=\frac R2\sin\theta.
$$

Show that the regulated length between $z=\epsilon$ endpoints is

$$
\ell_\epsilon
=
2L\log\frac{R}{\epsilon}
+
O(\epsilon^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Along the semicircle,

$$
dx^2+dz^2
=
\left(\frac R2\right)^2d\theta^2,
\qquad
z=\frac R2\sin\theta.
$$

Therefore

$$
ds
=
L\frac{d\theta}{\sin\theta}.
$$

The cutoff $z=\epsilon$ means

$$
\sin\theta_\epsilon=\frac{2\epsilon}{R}.
$$

The length is

$$
\ell_\epsilon
=
L\int_{\theta_\epsilon}^{\pi-\theta_\epsilon}
\frac{d\theta}{\sin\theta}
=
L\left[
\log\tan\frac{\theta}{2}
\right]_{\theta_\epsilon}^{\pi-\theta_\epsilon}.
$$

Using

$$
\tan\frac{\pi-\theta_\epsilon}{2}
=
\cot\frac{\theta_\epsilon}{2},
$$

we get

$$
\ell_\epsilon
=
L\log
\left[
\frac{\cot(\theta_\epsilon/2)}
{\tan(\theta_\epsilon/2)}
\right]
=
2L\log\cot\frac{\theta_\epsilon}{2}.
$$

For small $\epsilon$,

$$
\theta_\epsilon\simeq \frac{2\epsilon}{R},
\qquad
\cot\frac{\theta_\epsilon}{2}
\simeq
\frac{R}{\epsilon}.
$$

Hence

$$
\ell_\epsilon
=
2L\log\frac{R}{\epsilon}
+
O(\epsilon^2).
$$

</details>

### Exercise 2: Recover the CFT power law

Using

$$
\ell_{\rm ren}=2L\log R+\text{constant},
$$

show that the geodesic approximation gives

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
\propto
R^{-2\Delta}.
$$

<details>
<summary><strong>Solution</strong></summary>

The geodesic formula is

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\rangle
\sim
\exp\left[-\frac{\Delta}{L}\ell_{\rm ren}\right].
$$

Substitute

$$
\ell_{\rm ren}=2L\log R+\text{constant}.
$$

Then

$$
\exp\left[-\frac{\Delta}{L}\ell_{\rm ren}\right]
=
\exp[-2\Delta\log R]\times \text{constant}
=
R^{-2\Delta}\times \text{constant}.
$$

The constant depends on the subtraction convention and operator normalization.

</details>

### Exercise 3: Probe versus backreacting heavy operator

In a holographic CFT with $C_T\sim N^2$, explain why the condition

$$
1\ll \Delta\ll N^2
$$

is the natural regime for a heavy probe particle.

<details>
<summary><strong>Solution</strong></summary>

The first inequality,

$$
1\ll \Delta,
$$

means that the dual particle mass satisfies $mL\gg1$. This makes the worldline path integral semiclassical, so a geodesic saddle dominates.

The second inequality,

$$
\Delta\ll N^2,
$$

means the particle energy is small compared with the scale controlling gravitational backreaction. Since

$$
\frac{L^{d-1}}{G_N}\sim C_T\sim N^2,
$$

an object with energy of order $N^2/L$ can substantially modify the geometry. For $\Delta\ll N^2$, the geometry can be treated as fixed and the particle as a probe.

</details>

### Exercise 4: Large mass expansion

Starting from

$$
\Delta
=
\frac d2+
\sqrt{\frac{d^2}{4}+m^2L^2},
$$

show that

$$
\Delta=mL+\frac d2+O\!\left(\frac{1}{mL}\right)
$$

for $mL\gg1$.

<details>
<summary><strong>Solution</strong></summary>

Factor out $mL$ from the square root:

$$
\sqrt{\frac{d^2}{4}+m^2L^2}
=
mL
\sqrt{1+\frac{d^2}{4m^2L^2}}.
$$

For $mL\gg1$, use

$$
\sqrt{1+x}=1+\frac{x}{2}+O(x^2).
$$

Then

$$
\sqrt{\frac{d^2}{4}+m^2L^2}
=
mL
\left[
1+\frac{d^2}{8m^2L^2}
+O\!\left(\frac{1}{m^4L^4}\right)
\right],
$$

so

$$
\Delta
=
mL+\frac d2
+
O\!\left(\frac{1}{mL}\right).
$$

</details>

## Further reading

- V. Balasubramanian, P. Kraus, A. Lawrence, and S. Trivedi, [Holographic Probes of Anti-de Sitter Spacetimes](https://arxiv.org/abs/hep-th/9808017).
- V. Balasubramanian and S. F. Ross, [Holographic Particle Detection](https://arxiv.org/abs/hep-th/9906226).
- J. Louko, D. Marolf, and S. F. Ross, [On Geodesic Propagators and Black Hole Holography](https://arxiv.org/abs/hep-th/0002111).
- J. M. Maldacena, [Eternal Black Holes in Anti-de Sitter](https://arxiv.org/abs/hep-th/0106112).
- J. Penedones, [TASI Lectures on AdS/CFT](https://arxiv.org/abs/1608.04948).
