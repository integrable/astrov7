---
title: "BTZ Black Holes"
description: "The geometry, horizons, thermodynamics, and CFT interpretation of the Banados-Teitelboim-Zanelli black hole in AdS3."
sidebar:
  order: 30
---

The BTZ black hole is the place where AdS$_3$/CFT$_2$ stops being a beautiful symmetry story and becomes a black-hole story. It is a black hole in $2+1$ bulk dimensions, discovered by Bañados, Teitelboim, and Zanelli, and it has mass, angular momentum, horizons, temperature, entropy, and a first law.

The surprise is that pure Einstein gravity in three dimensions has no local gravitons. Locally, every vacuum solution with negative cosmological constant is just AdS$_3$. The BTZ black hole is therefore not a black hole because curvature becomes singular in the usual four-dimensional Schwarzschild sense. It is a black hole because a global identification of AdS$_3$ changes the causal structure and creates horizons.

That is exactly why BTZ is so useful in holography. It is simple enough to solve almost completely, but rich enough to teach us about thermal CFT states, black-hole entropy, modular invariance, and the microscopic meaning of horizons.

## Setup

We work with three-dimensional Einstein gravity with negative cosmological constant,

$$
I
=
\frac{1}{16\pi G_3}
\int d^3x\sqrt{-g}\left(R+\frac{2}{L^2}\right)
+
\text{boundary terms}.
$$

The equations of motion are

$$
R_{\mu\nu}=-\frac{2}{L^2}g_{\mu\nu}.
$$

In three dimensions, the Riemann tensor is algebraically determined by the Ricci tensor. Thus any vacuum solution of these equations has

$$
R_{\mu\nu\rho\sigma}
=
-\frac{1}{L^2}
\left(
 g_{\mu\rho}g_{\nu\sigma}
 -
 g_{\mu\sigma}g_{\nu\rho}
\right),
\qquad
R=-\frac{6}{L^2}.
$$

So locally the BTZ spacetime is AdS$_3$. All the black-hole physics is global.

<figure class="doc-figure" style="--figure-width: 50rem;">

![BTZ black holes as locally AdS3 quotients with inner and outer horizons.](/figures/course/btz-black-holes.svg)

<figcaption>

The nonextremal rotating BTZ black hole is locally AdS$_3$, but the angular identification creates a spacetime with outer and inner horizons at $r_+$ and $r_-$. The horizon “area” in three bulk dimensions is a circumference, $2\pi r_+$.

</figcaption>
</figure>

## The rotating BTZ metric

The rotating BTZ metric can be written as

$$
ds^2
=
-N^2(r)dt^2
+
\frac{dr^2}{N^2(r)}
+
r^2\left(d\phi+N^\phi(r)dt\right)^2,
\qquad
\phi\sim\phi+2\pi,
$$

where

$$
N^2(r)
=
-8G_3M+\frac{r^2}{L^2}+\frac{16G_3^2J^2}{r^2},
\qquad
N^\phi(r)
=
-\frac{4G_3J}{r^2}.
$$

Here $M$ and $J$ are the conserved mass and angular momentum measured at infinity. With these conventions, global AdS$_3$ has

$$
M=-\frac{1}{8G_3},
\qquad
J=0,
$$

while the massless BTZ geometry has $M=J=0$.

For black holes, it is usually cleaner to parametrize the solution by the outer and inner horizon radii $r_+$ and $r_-$. Then

$$
N^2(r)
=
\frac{(r^2-r_+^2)(r^2-r_-^2)}{L^2r^2},
\qquad
N^\phi(r)
=
-\frac{r_+r_-}{Lr^2},
$$

and

$$
M
=
\frac{r_+^2+r_-^2}{8G_3L^2},
\qquad
J
=
\frac{r_+r_-}{4G_3L}.
$$

The two parametrizations agree because

$$
16G_3^2J^2
=
\frac{r_+^2r_-^2}{L^2},
\qquad
8G_3M
=
\frac{r_+^2+r_-^2}{L^2}.
$$

The condition for a nonextremal rotating black hole is

$$
r_+>r_-\geq 0.
$$

The extremal limit is $r_+=r_-$, where the temperature vanishes. The nonrotating BTZ black hole has $r_-=0$.

## Horizons and angular velocity

The horizons are the zeroes of $N^2(r)$. The outer horizon is at $r=r_+$, and the inner horizon is at $r=r_-$. The Killing vector that generates the outer horizon is

$$
\chi
=
\partial_t+\Omega_H\partial_\phi,
$$

where the horizon angular velocity is

$$
\Omega_H
=
- N^\phi(r_+)
=
\frac{r_-}{Lr_+}.
$$

This is the angular velocity of the black hole as seen from the nonrotating frame at infinity.

The surface gravity gives the Hawking temperature,

$$
T_H
=
\frac{r_+^2-r_-^2}{2\pi L^2r_+}.
$$

For $r_-=0$, this reduces to

$$
T_H
=
\frac{r_+}{2\pi L^2}.
$$

The temperature grows linearly with $r_+$ for the nonrotating BTZ black hole. This is different from asymptotically flat Schwarzschild in four dimensions, where larger black holes are colder. In AdS, large black holes are thermodynamically stable.

## Entropy and the first law

In three dimensions, the horizon “area” is the length of the horizon circle:

$$
A_H=2\pi r_+.
$$

The Bekenstein–Hawking entropy is therefore

$$
S_{\rm BH}
=
\frac{A_H}{4G_3}
=
\frac{2\pi r_+}{4G_3}
=
\frac{\pi r_+}{2G_3}.
$$

The first law is

$$
dM
=
T_H dS_{\rm BH}
+
\Omega_H dJ.
$$

Let us check it explicitly. From

$$
M=\frac{r_+^2+r_-^2}{8G_3L^2},
\qquad
J=\frac{r_+r_-}{4G_3L},
\qquad
S=\frac{\pi r_+}{2G_3},
$$

we get

$$
dM
=
\frac{r_+dr_+ + r_-dr_-}{4G_3L^2},
$$

while

$$
T_HdS
=
\frac{r_+^2-r_-^2}{2\pi L^2r_+}
\frac{\pi dr_+}{2G_3}
=
\frac{r_+^2-r_-^2}{4G_3L^2r_+}dr_+,
$$

and

$$
\Omega_H dJ
=
\frac{r_-}{Lr_+}
\frac{r_-dr_+ + r_+dr_-}{4G_3L}
=
\frac{r_-^2}{4G_3L^2r_+}dr_+
+
\frac{r_-}{4G_3L^2}dr_-.
$$

Adding these two terms gives $dM$.

## Locally AdS, globally a black hole

Because the BTZ metric is locally AdS$_3$, there is no curvature singularity at $r=0$. The scalar curvature is constant everywhere away from quotient fixed points or causal pathologies:

$$
R=-\frac{6}{L^2}.
$$

This sounds paradoxical only if one expects a black hole to require large local curvature. BTZ teaches a sharper lesson: horizons are global causal structures. They do not require local curvature blowup.

A useful slogan is

$$
\text{BTZ black hole}
=
\mathrm{AdS}_3 / \Gamma,
$$

where $\Gamma$ is a discrete subgroup of the AdS$_3$ isometry group. The quotient identification makes the angular direction periodic in a way that creates a horizon. In the Euclidean geometry, the black hole is a solid torus; which cycle contracts smoothly in the bulk determines the thermal saddle.

This quotient viewpoint is one reason BTZ is a privileged laboratory for quantum gravity. The local dynamics is almost trivial, but the global and boundary dynamics are not.

## Boundary interpretation

The asymptotic boundary of global AdS$_3$ is a cylinder,

$$
\mathbb R_t\times S^1_\phi.
$$

A rotating BTZ black hole is dual to a thermal state of the CFT$_2$ on this cylinder, generally with nonzero angular potential. Equivalently, the state has different effective temperatures for left- and right-moving sectors.

It is useful to define

$$
T_L
=
\frac{r_+ - r_-}{2\pi L^2},
\qquad
T_R
=
\frac{r_+ + r_-}{2\pi L^2}.
$$

Then

$$
T_H
=
\frac{2T_LT_R}{T_L+T_R},
$$

and the angular velocity is encoded in the imbalance between $T_L$ and $T_R$. The nonrotating black hole has $T_L=T_R$.

The left/right split is not an artificial trick. A two-dimensional CFT naturally factorizes the global conformal algebra into left-moving and right-moving copies. In the next page, this split is what makes the Cardy formula reproduce the BTZ entropy.

## Energy scales and the AdS$_3$ vacuum

With the conventions above, global AdS$_3$ has negative mass,

$$
M_{\rm AdS}=-\frac{1}{8G_3}.
$$

This is not a mistake. It reflects the Casimir energy of the dual CFT on the cylinder. The massless BTZ geometry, $M=0$, is not global AdS$_3$; it is a quotient sometimes called the zero-mass black hole.

For

$$
-\frac{1}{8G_3}<M<0,
$$

one finds conical defect geometries rather than black holes. They are also locally AdS$_3$, but they do not have BTZ horizons.

This family of locally AdS$_3$ geometries is holographically important: it previews the idea that different CFT states can produce different global quotients or defects even when the local bulk curvature is unchanged.

## Euclidean BTZ and the boundary torus

After Wick rotation and suitable continuation of angular momentum, Euclidean BTZ has a boundary torus. The two cycles are the angular circle and the Euclidean thermal circle. Smoothness requires the contractible cycle in the bulk to have the correct period.

This is the three-dimensional version of the horizon-smoothness argument used earlier for Euclidean black holes. Near the outer horizon, the Euclidean geometry locally looks like polar coordinates,

$$
ds_E^2\sim d\rho^2+\rho^2 d\theta^2+\cdots,
$$

and absence of a conical singularity fixes the temperature.

In AdS$_3$/CFT$_2$, this Euclidean torus viewpoint is especially powerful because the CFT partition function on a torus is constrained by modular invariance. The Hawking–Page transition and BTZ dominance can be rephrased as competition between different solid-torus fillings of the same boundary torus.

## Dictionary checkpoint

The BTZ black hole gives the following entries in the AdS$_3$/CFT$_2$ dictionary:

| Bulk quantity | Boundary interpretation |
|---|---|
| $M$ | energy above the AdS$_3$ vacuum, including cylinder Casimir conventions |
| $J$ | angular momentum on the boundary circle |
| $r_+$ | entropy through the horizon circumference |
| $r_-$ | left/right thermal imbalance, or rotation |
| $T_H$ | physical Hawking temperature of the CFT thermal state |
| $T_L,T_R$ | chiral temperatures of left- and right-moving CFT sectors |
| Euclidean BTZ | solid-torus saddle for the CFT torus partition function |

The conceptual lesson is simple but deep:

$$
\text{global identifications in locally AdS}_3
\quad
\longleftrightarrow
\quad
\text{thermal and spinning states of the CFT}_2.
$$

## Common confusions

### “If BTZ is locally AdS$_3$, it is not a real black hole.”

It is a real black hole. Horizons are global causal structures, not local curvature invariants. BTZ has an event horizon, Hawking temperature, entropy, and a first law.

### “The BTZ singularity is a curvature singularity.”

Not in pure Einstein gravity. The curvature is locally that of AdS$_3$. The singular behavior is tied to the quotient and causal structure, not a divergent curvature scalar.

### “The entropy is strange because there are no gravitons.”

That is precisely why BTZ is profound. The entropy is not counting local graviton waves in the bulk. In AdS$_3$/CFT$_2$, it is accounted for by the asymptotic symmetry degrees of freedom of the boundary CFT.

### “$M=0$ is global AdS$_3$.”

No. In the standard BTZ convention, global AdS$_3$ has $M=-1/(8G_3)$. The $M=0$ geometry is the massless BTZ solution.

### “The inner horizon is irrelevant.”

For nonrotating BTZ, $r_-=0$. But in the rotating case $r_-$ controls angular momentum and left/right imbalance. It is essential for matching to chiral CFT data.

## Exercises

### Exercise 1: Nonrotating BTZ thermodynamics

Set $r_-=0$. Express $M$, $T_H$, and $S$ in terms of $r_+$, and verify the first law $dM=T_HdS$.

<details>
<summary><strong>Solution</strong></summary>

For $r_-=0$,

$$
M=\frac{r_+^2}{8G_3L^2},
\qquad
T_H=\frac{r_+}{2\pi L^2},
\qquad
S=\frac{\pi r_+}{2G_3}.
$$

Then

$$
dM=\frac{r_+}{4G_3L^2}dr_+,
$$

and

$$
T_HdS
=
\frac{r_+}{2\pi L^2}\frac{\pi}{2G_3}dr_+
=
\frac{r_+}{4G_3L^2}dr_+.
$$

Thus $dM=T_HdS$.

</details>

### Exercise 2: Extremal limit

Show that the Hawking temperature vanishes when $r_+=r_-$. What happens to $M$ and $J$ in this limit?

<details>
<summary><strong>Solution</strong></summary>

The temperature is

$$
T_H=\frac{r_+^2-r_-^2}{2\pi L^2r_+}.
$$

When $r_+=r_-$, the numerator vanishes, so $T_H=0$.

The conserved charges become

$$
M=\frac{2r_+^2}{8G_3L^2}=\frac{r_+^2}{4G_3L^2},
\qquad
J=\frac{r_+^2}{4G_3L}.
$$

Thus

$$
J=ML.
$$

The extremal BTZ black hole saturates the bound $|J|\leq ML$.

</details>

### Exercise 3: Left/right temperatures

Using

$$
T_L=\frac{r_+ - r_-}{2\pi L^2},
\qquad
T_R=\frac{r_+ + r_-}{2\pi L^2},
$$

verify that

$$
T_H=\frac{2T_LT_R}{T_L+T_R}.
$$

<details>
<summary><strong>Solution</strong></summary>

First compute

$$
T_LT_R
=
\frac{r_+^2-r_-^2}{4\pi^2L^4},
$$

and

$$
T_L+T_R
=
\frac{2r_+}{2\pi L^2}
=
\frac{r_+}{\pi L^2}.
$$

Therefore

$$
\frac{2T_LT_R}{T_L+T_R}
=
\frac{2(r_+^2-r_-^2)}{4\pi^2L^4}
\frac{\pi L^2}{r_+}
=
\frac{r_+^2-r_-^2}{2\pi L^2r_+}
=
T_H.
$$

</details>

## Further reading

- M. Bañados, C. Teitelboim, and J. Zanelli, [The Black Hole in Three Dimensional Space Time](https://arxiv.org/abs/hep-th/9204099).
- S. Carlip, [Conformal Field Theory, $(2+1)$-Dimensional Gravity, and the BTZ Black Hole](https://arxiv.org/abs/gr-qc/0503022).
- P. Kraus, [Lectures on Black Holes and the AdS$_3$/CFT$_2$ Correspondence](https://arxiv.org/abs/hep-th/0609074).
- D. Birmingham, [Exact Results for the BTZ Black Hole](https://arxiv.org/abs/hep-th/0102155).
