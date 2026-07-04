---
title: "Wilson Loops"
description: "How holography computes nonlocal Wilson-loop observables using fundamental strings whose worldsheets end on boundary loops."
sidebar:
  order: 50
---

## Why this matters

Most of the dictionary so far has involved local operators. A scalar operator $\mathcal O(x)$ is dual to a bulk scalar field, a current $J^i(x)$ is dual to a bulk gauge field, and the stress tensor $T^{ij}(x)$ is dual to the metric. Wilson loops are different. They are nonlocal operators: instead of asking what happens at one point, they ask how the gauge field transports color around a curve.

In gauge theory, Wilson loops are among the cleanest probes of confinement, screening, external heavy quarks, and the geometry of strongly coupled gauge dynamics. In holography they are also among the most vivid examples of the stringy origin of the correspondence. The dual of a Wilson loop is not a supergravity field. It is a string worldsheet.

The schematic dictionary is

$$
\boxed{
\langle W[C]\rangle
\simeq
\exp\left[-S_{\rm string,ren}(\Sigma_C)\right]
}
$$

where $\Sigma_C$ is a string worldsheet in the bulk whose boundary is the curve $C$ at the conformal boundary of AdS:

$$
\partial \Sigma_C = C .
$$

At large $N$ and large 't Hooft coupling $\lambda$, the dominant worldsheet is a classical minimal surface. This is the first place in the course where the literal string in string theory becomes unavoidable.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Wilson loops from string worldsheets in AdS](/figures/course/wilson-loops-string-worldsheet.svg)

<figcaption>

A Wilson loop $W[C]$ is a nonlocal boundary observable. In the classical string limit its expectation value is controlled by a bulk fundamental-string worldsheet $\Sigma_C$ ending on the boundary curve $C$. For a rectangular loop, the connected U-shaped surface computes the heavy quark–antiquark potential.

</figcaption>
</figure>

This page explains the basic prescription, derives the strong-coupling Coulomb potential in the canonical AdS$_5$/CFT$_4$ example, and clarifies what Wilson loops are and are not measuring.

## Wilson loops in gauge theory

For an ordinary gauge field $A_\mu=A_\mu^a T^a$, the Wilson loop in representation $R$ along a closed curve $C$ is

$$
W_R[C]
=
\frac{1}{\dim R}
\operatorname{Tr}_R\,
\mathcal P\exp\left(i\oint_C A_\mu dx^\mu\right),
$$

where $\mathcal P$ denotes path ordering. Under a gauge transformation, the holonomy around a closed loop transforms by conjugation, so its trace is gauge invariant.

For a rectangular loop with temporal extent $T$ and spatial separation $\ell$, the large-$T$ behavior defines a static quark–antiquark potential:

$$
\langle W(\ell,T)\rangle
\sim
\exp[-T V(\ell)]
\qquad
T\to\infty
$$

in Euclidean signature. In a confining theory one expects

$$
V(\ell)\sim \sigma \, \ell
\qquad
\text{at large }\ell,
$$

with string tension $\sigma$. In a conformal theory, dimensional analysis instead requires

$$
V(\ell)\propto \frac{1}{\ell}
$$

up to a dimensionless function of couplings.

The Wilson loop is therefore a clean diagnostic of whether color sources are confined, screened, or Coulombic. Holography turns this diagnostic into a problem about a string worldsheet.

## The Maldacena–Wilson loop in $\mathcal N=4$ SYM

The canonical supersymmetric loop in $\mathcal N=4$ SYM is not only the holonomy of $A_\mu$. The theory also has six adjoint scalar fields $\Phi_I$, with $I=1,\ldots,6$. A locally supersymmetric Wilson loop couples to both the gauge field and the scalars:

$$
W[C,n]
=
\frac{1}{N}
\operatorname{Tr}\,
\mathcal P
\exp\left[
\oint_C ds\left(
  i A_\mu(x)\dot x^\mu
  + |\dot x|\, n^I(s)\Phi_I(x)
\right)
\right],
$$

where $n^I(s)$ is a unit vector on $S^5$:

$$
n^I n^I = 1.
$$

This scalar coupling is not a decorative detail. It tells the bulk string where to sit on the $S^5$. A choice of $n^I$ selects a point, or more generally a path, in the internal sphere.

For a straight supersymmetric line or a circular half-BPS loop, the scalar coupling is essential. The loop without scalar coupling is also an interesting gauge-theory observable, but the simplest fundamental-string prescription in AdS$_5\times S^5$ naturally computes the Maldacena–Wilson loop.

## The bulk prescription

A Wilson loop in the fundamental representation is dual to a fundamental string ending on the boundary contour $C$. In Euclidean signature the classical worldsheet action is the Nambu–Goto action

$$
S_{\rm NG}
=
\frac{1}{2\pi\alpha'}
\int_{\Sigma_C} d^2\sigma\,
\sqrt{\det h_{ab}},
$$

where $h_{ab}$ is the induced metric on the worldsheet:

$$
h_{ab}
=
G_{MN}(X)\,
\partial_a X^M\partial_b X^N.
$$

The leading saddle approximation gives

$$
\langle W[C]\rangle
\approx
\exp[-S_{\rm NG,ren}(C)] .
$$

In AdS$_5\times S^5$,

$$
\frac{L^2}{\alpha'} = \sqrt\lambda,
$$

so the action of a surface with AdS-scale area is of order $\sqrt\lambda$. This explains a famous nonperturbative feature: at strong coupling, Wilson-loop exponents often scale as $\sqrt\lambda$, not as $\lambda$.

The word “renormalized” is important. A string that reaches the AdS boundary has infinite area. Physically, this divergence is the infinite rest mass of an external quark. One must regulate near $z=0$ and subtract local boundary counterterms, or equivalently subtract the areas of reference straight strings when computing an energy difference.

The prescription is therefore more precisely

$$
S_{\rm string,ren}
=
\lim_{\epsilon\to0}
\left(
S_{\rm NG}^{z\ge \epsilon}
+
S_{\rm bdy}^{z=\epsilon}
\right).
$$

The boundary term depends on the precise loop and on the choice of variables, but its role is universal: remove the local divergence attached to the boundary contour.

## Warm-up: the straight string

Consider Euclidean Poincaré AdS$_5$:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+d\tau^2+d\vec x^2\right).
$$

A straight Wilson line along Euclidean time is represented by a vertical string at fixed spatial position:

$$
\tau = \sigma^0,
\qquad
z=\sigma^1,
\qquad
\vec x=\text{constant}.
$$

The induced metric is

$$
h_{ab}d\sigma^a d\sigma^b
=
\frac{L^2}{z^2}(d\tau^2+dz^2),
$$

so the regulated action over time interval $T$ is

$$
S_{\rm straight}
=
\frac{1}{2\pi\alpha'}
\int_0^T d\tau\int_\epsilon^{z_{\rm IR}} dz\,\frac{L^2}{z^2}
=
\frac{\sqrt\lambda}{2\pi}
T\left(\frac{1}{\epsilon}-\frac{1}{z_{\rm IR}}\right).
$$

The $1/\epsilon$ divergence is the heavy-quark mass divergence. It is local on the boundary line and is removed by the Wilson-line renormalization. For a supersymmetric straight line in the vacuum, the renormalized expectation value is conventionally normalized to one:

$$
\langle W_{\rm line}\rangle = 1.
$$

This is a useful calibration. The connected quark–antiquark worldsheet will be compared with two disconnected straight strings.

## The rectangular loop and the heavy-quark potential

Now compute the potential between an external quark and antiquark separated by distance $\ell$ in strongly coupled $\mathcal N=4$ SYM. Take a rectangular loop with long Euclidean time extent $T$ and spatial endpoints at

$$
x=\pm \frac{\ell}{2}.
$$

Use static gauge

$$
\tau = t,
\qquad
\sigma=x,
\qquad
z=z(x).
$$

The Nambu–Goto action becomes

$$
S_{\rm NG}
=
\frac{T L^2}{2\pi\alpha'}
\int_{-\ell/2}^{\ell/2} dx\,
\frac{\sqrt{1+z'(x)^2}}{z(x)^2}
=
\frac{T\sqrt\lambda}{2\pi}
\int_{-\ell/2}^{\ell/2} dx\,
\frac{\sqrt{1+z'^2}}{z^2}.
$$

The surface hangs into the bulk, reaches a maximum depth $z_*$ at $x=0$, and returns to the boundary. Since the Lagrangian does not depend explicitly on $x$, there is a conserved quantity:

$$
\frac{1}{z^2\sqrt{1+z'^2}}
=
\frac{1}{z_*^2}.
$$

Solving for $z'$ gives

$$
z'^2
=
\frac{z_*^4}{z^4}-1.
$$

The separation is therefore

$$
\frac{\ell}{2}
=
\int_0^{z_*} dz\,\frac{z^2}{\sqrt{z_*^4-z^4}}
=
z_*\int_0^1 dy\,\frac{y^2}{\sqrt{1-y^4}}.
$$

The integral evaluates to

$$
\int_0^1 dy\,\frac{y^2}{\sqrt{1-y^4}}
=
\sqrt\pi\,\frac{\Gamma(3/4)}{\Gamma(1/4)}.
$$

Thus

$$
\ell
=
2 z_*\sqrt\pi\,\frac{\Gamma(3/4)}{\Gamma(1/4)}.
$$

After subtracting the two straight-string masses, the renormalized energy is

$$
V(\ell)
=
-\frac{4\pi^2}{\Gamma(1/4)^4}\,
\frac{\sqrt\lambda}{\ell}.
$$

This result is worth staring at. The theory is conformal, so $V(\ell)$ must scale as $1/\ell$. Holography computes the coefficient at strong coupling and large $N$. The dependence on $\sqrt\lambda$ is nonanalytic from the viewpoint of weak-coupling perturbation theory.

## What the hanging string is telling you

The U-shaped string gives an especially concrete version of the UV/IR relation. Boundary separation $\ell$ is related to the maximum radial depth $z_*$:

$$
z_* \sim \ell.
$$

Short-distance probes remain near the boundary. Long-distance probes fall deeper into the bulk. This is the same intuition used in holographic RG, now encoded in a minimal surface.

In the vacuum of a conformal theory, the string can hang arbitrarily deep, producing a Coulombic potential at all distances. In a geometry with an IR wall, cap, or horizon, the large-distance behavior can change. For example:

| Bulk behavior | Wilson-loop behavior |
|---|---|
| pure AdS throat | Coulombic $V(\ell)\sim -1/\ell$ |
| confining cap or hard wall | area law at large $\ell$ |
| black-brane horizon | screening at finite temperature |
| string breaking allowed by dynamical flavors | connected string may cease to dominate |

This is one reason Wilson loops are so useful: they translate qualitative geometry into qualitative force laws.

## Circular Wilson loops

The circular half-BPS Wilson loop is another landmark example. For a circle of radius $R$ on the boundary of Euclidean AdS, the minimal surface is a hemisphere:

$$
z^2+r^2=R^2.
$$

The renormalized classical string action is

$$
S_{\rm ren}=-\sqrt\lambda,
$$

so the leading strong-coupling behavior is

$$
\langle W_{\rm circle}\rangle
\sim
\exp(\sqrt\lambda).
$$

This sign may look odd at first: Euclidean actions are usually positive. The point is that the divergent area subtraction includes a boundary contribution, and the finite renormalized result can be negative. The circular BPS loop became an important precision test because supersymmetric localization computes it exactly in the gauge theory, including finite-$N$ and finite-$\lambda$ information. In this foundations course, the main lesson is simpler: the same minimal-surface prescription that gives the quark–antiquark potential also computes smooth loop expectation values.

## Wilson loops at finite temperature

At finite temperature, the dual geometry contains a black brane:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 f(z)d\tau^2+d\vec x^2+\frac{dz^2}{f(z)}
\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The Euclidean time circle has circumference

$$
\beta = \frac{1}{T}.
$$

A temporal Wilson loop wrapping the Euclidean thermal circle is the Polyakov loop. In a deconfined plasma, a single string can end on the boundary loop and fall into the horizon. Its renormalized action computes the free energy of an external heavy quark:

$$
\langle P\rangle
\sim e^{-\beta F_Q}.
$$

A rectangular Wilson loop at finite temperature is represented by a connected worldsheet only up to a maximum separation. At large enough separation the dominant configuration becomes two disconnected strings ending on the horizon. This is the holographic picture of color screening in a plasma.

The detailed finite-temperature analysis belongs later in the course, but the qualitative message is already visible: horizons screen external color sources.

## Higher representations and other loop operators

The fundamental Wilson loop is dual to a fundamental string. Other nonlocal operators have related but distinct bulk descriptions:

| Boundary operator | Typical bulk object |
|---|---|
| fundamental Wilson loop | fundamental string F1 |
| Wilson loop in large symmetric representation | D3-brane with electric flux |
| Wilson loop in large antisymmetric representation | D5-brane with electric flux |
| 't Hooft loop | D1-string or magnetic dual object |
| dyonic loop | $(p,q)$ string |

This table should be read as orientation, not as a universal theorem. The precise object depends on the theory, the representation, supersymmetry, and the background. The key point is that nonlocal line operators often require extended stringy objects, not just supergravity fields.

## Common confusions

### “A Wilson loop is dual to a bulk gauge field.”

A conserved current $J^\mu$ is dual to a bulk gauge field $A_M$. A Wilson loop in the fundamental representation is instead dual to a fundamental string worldsheet ending on the boundary loop. The bulk gauge field computes current correlators; the string computes the phase/holonomy observable associated with an external color source.

### “The string endpoint is a dynamical quark in the boundary theory.”

In the basic Wilson-loop calculation, the endpoint represents an infinitely heavy external probe, not a dynamical quark field in the original $\mathcal N=4$ SYM spectrum. Dynamical fundamental matter requires adding flavor branes, which is the subject of the next page.

### “The minimal area is finite because the loop is finite.”

No. Any string worldsheet ending at the AdS boundary has a near-boundary area divergence. This is the holographic version of the UV divergence associated with an external heavy source. One must renormalize the worldsheet action.

### “The Wilson loop proves confinement in $\mathcal N=4$ SYM.”

It does not. The strong-coupling result in the vacuum is Coulombic:

$$
V(\ell)\propto -\frac{\sqrt\lambda}{\ell}.
$$

This is exactly what conformal invariance requires. Confinement requires an IR scale and a different bulk geometry, such as a cap-off or hard wall.

### “Large $N$ alone justifies the classical string worldsheet.”

Large $N$ suppresses string loops. The classical worldsheet approximation also needs large $\lambda$, because the string tension in AdS units is

$$
T_{\rm string}L^2=\frac{\sqrt\lambda}{2\pi}.
$$

For small $\lambda$, the worldsheet is strongly quantum even if $N$ is large.

## Dictionary checkpoint

| Boundary statement | Bulk statement |
|---|---|
| fundamental Wilson loop $W[C]$ | fundamental string ending on $C$ |
| $\langle W[C]\rangle$ at large $N$, large $\lambda$ | $e^{-S_{\rm string,ren}}$ |
| rectangular loop | heavy quark–antiquark potential |
| scalar coupling $n^I\Phi_I$ in $\mathcal N=4$ SYM | endpoint position/path on $S^5$ |
| perimeter divergence | infinite area of string near boundary |
| screening at finite temperature | disconnected strings ending on a horizon |
| confinement criterion | large loop dominated by area-law worldsheet |

The important conceptual addition is that the holographic dictionary is not limited to local fields. Nonlocal gauge-invariant observables can be dual to extended bulk objects.

## Exercises

### Exercise 1: Dimensional analysis of the quark–antiquark potential

Use conformal invariance to determine the functional form of the static potential $V(\ell)$ in four-dimensional $\mathcal N=4$ SYM. What can and cannot be fixed by symmetry?

<details>
<summary><strong>Solution</strong></summary>

The potential has dimensions of energy, so in a conformal theory it must scale as inverse length:

$$
V(\ell)=\frac{c(\lambda,N)}{\ell}.
$$

Conformal symmetry fixes the $1/\ell$ dependence but not the dimensionless coefficient $c(\lambda,N)$. Holography at large $N$ and large $\lambda$ gives

$$
c(\lambda,N)
=
-\frac{4\pi^2}{\Gamma(1/4)^4}\sqrt\lambda
+\cdots,
$$

where the ellipsis denotes $1/\sqrt\lambda$ and $1/N$ corrections.

</details>

### Exercise 2: Derive the first integral for the hanging string

For the Lagrangian

$$
\mathcal L(z,z')=\frac{\sqrt{1+z'^2}}{z^2},
$$

show that

$$
\frac{1}{z^2\sqrt{1+z'^2}}
=
\frac{1}{z_*^2},
$$

where $z_*$ is the maximum radial depth of the string.

<details>
<summary><strong>Solution</strong></summary>

Since $\mathcal L$ has no explicit $x$ dependence, the Hamiltonian-like quantity

$$
z'\frac{\partial\mathcal L}{\partial z'}-\mathcal L
$$

is conserved. We compute

$$
\frac{\partial\mathcal L}{\partial z'}
=
\frac{z'}{z^2\sqrt{1+z'^2}},
$$

so

$$
z'\frac{\partial\mathcal L}{\partial z'}-\mathcal L
=
\frac{z'^2}{z^2\sqrt{1+z'^2}}
-
\frac{\sqrt{1+z'^2}}{z^2}
=
-\frac{1}{z^2\sqrt{1+z'^2}}.
$$

At the midpoint of the string, $z=z_*$ and $z'=0$, so the conserved quantity equals $-1/z_*^2$. Hence

$$
\frac{1}{z^2\sqrt{1+z'^2}}
=
\frac{1}{z_*^2}.
$$

</details>

### Exercise 3: Why does the action scale as $\sqrt\lambda$?

Explain why the classical string action in AdS$_5\times S^5$ has an overall factor $\sqrt\lambda$.

<details>
<summary><strong>Solution</strong></summary>

The Nambu–Goto action is

$$
S_{\rm NG}=\frac{1}{2\pi\alpha'}\int d^2\sigma\sqrt{\det h}.
$$

For a worldsheet whose geometry is set by the AdS radius $L$, the induced area contains a factor $L^2$. Therefore

$$
S_{\rm NG}\sim \frac{L^2}{\alpha'}.
$$

In the AdS$_5$/CFT$_4$ parameter map,

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

Thus the classical worldsheet action is of order $\sqrt\lambda$. This is why many strong-coupling Wilson-loop results have the form $\exp[-O(\sqrt\lambda)]$ or $\exp[+O(\sqrt\lambda)]$ after renormalization.

</details>

### Exercise 4: Boundary divergence of a straight string

Using the straight string result

$$
S_{\rm straight}
=
\frac{\sqrt\lambda}{2\pi}
T\left(\frac{1}{\epsilon}-\frac{1}{z_{\rm IR}}\right),
$$

identify the divergent contribution to the heavy-quark energy.

<details>
<summary><strong>Solution</strong></summary>

The Euclidean action of a static object over time $T$ is $S=T E$. Therefore the divergent contribution to the heavy-quark energy is

$$
E_{\rm div}
=
\frac{\sqrt\lambda}{2\pi}\frac{1}{\epsilon}.
$$

This is interpreted as the infinite bare mass of an external quark. A renormalized Wilson loop subtracts this local divergence.

</details>

## Further reading

- J. Maldacena, [Wilson Loops in Large $N$ Field Theories](https://arxiv.org/abs/hep-th/9803002).
- S.-J. Rey and J.-T. Yee, [Macroscopic Strings as Heavy Quarks: Large-$N$ Gauge Theory and Anti-de Sitter Supergravity](https://arxiv.org/abs/hep-th/9803001).
- N. Drukker, D. J. Gross, and H. Ooguri, [Wilson Loops and Minimal Surfaces](https://arxiv.org/abs/hep-th/9904191).
- N. Drukker and D. J. Gross, [An Exact Prediction of $\mathcal N=4$ SUSYM Theory for String Theory](https://arxiv.org/abs/hep-th/0010274).
