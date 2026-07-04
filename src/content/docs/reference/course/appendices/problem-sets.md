---
title: "Problem Sets"
description: "A curated collection of AdS/CFT Foundations exercises with solution sketches, organized by course unit."
sidebar:
  order: 80
---

This appendix collects exercises for the whole course. The problems are designed to do three jobs at once:

1. make the main formulas reproducible;
2. expose the conceptual traps that usually stay hidden in polished lecture notes;
3. give research-oriented readers a path from basic calculations to modern holographic reasoning.

The solutions are written as compact solution sketches. They are detailed enough to check the logic, but they deliberately leave some algebra for the reader. A good way to use this page is to attempt each exercise before opening the solution box. If you only read the solutions, the formulas will look easier than they really are. Holography has a mischievous habit of hiding normalization and boundary-condition issues inside innocent-looking equations.

## Suggested routes

For a first pass through the course, do the starred exercises:

- **Core dictionary:** Exercises 1.1, 1.2, 2.1, 2.3, 3.1, 4.1, 4.2, 5.1, 5.2.
- **Black holes and real time:** Exercises 6.1, 6.2, 7.1, 7.2, 7.3.
- **Entanglement and quantum gravity:** Exercises 8.1, 8.2, 8.4, 10.1, 10.2.
- **Applications:** Exercises 9.1, 9.2, 9.4.

The optional challenge problems are marked **Challenge**. These are closer to small research-literature warmups than ordinary homework.

Throughout this appendix, the boundary dimension is $d$, the bulk dimension is $d+1$, and the AdS radius is $L$ unless explicitly set to $1$.

---

## Problem Set 1: Sources, CFT Data, and Large $N$

Relevant pages:

- [QFT Data and Generating Functionals](../cft-large-n/qft-data-and-generating-functionals/)
- [Conformal Symmetry Minimum](../cft-large-n/conformal-symmetry-minimum/)
- [Radial Quantization and the Cylinder](../cft-large-n/radial-quantization-and-the-cylinder/)
- [Large $N$ Gauge Theory](../cft-large-n/large-n-gauge-theory/)
- [Single-Trace Operators and Factorization](../cft-large-n/single-trace-and-factorization/)

### Exercise 1.1: Connected correlators from $W[J]$

Let

$$
Z[J]
=
\left\langle
\exp\!\left(\int d^d x\, J(x)\mathcal O(x)\right)
\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Show that

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}\bigg|_{J=0}
=
\langle \mathcal O(x)\mathcal O(y)\rangle
-
\langle \mathcal O(x)\rangle \langle \mathcal O(y)\rangle .
$$

Then explain why holography naturally computes $W[J]$, not only $Z[J]$.

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\frac{\delta W}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}
=
\langle \mathcal O(x)\rangle_J .
$$

Differentiating again gives

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\langle \mathcal O(x)\mathcal O(y)\rangle_J
-
\langle \mathcal O(x)\rangle_J\langle \mathcal O(y)\rangle_J .
$$

Setting $J=0$ gives the desired connected two-point function.

In the classical bulk approximation,

$$
Z_{\mathrm{CFT}}[J]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[J]\right),
$$

so

$$
W_{\mathrm{CFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

The on-shell action is therefore the generator of connected correlators at leading large $N$.

</details>

### Exercise 1.2: Scaling dimension of a source

Suppose a scalar primary operator has dimension $\Delta$ in a $d$-dimensional CFT. The source deformation is

$$
\delta S = \int d^d x\, J(x)\mathcal O(x).
$$

Find the engineering dimension of $J$. Classify the deformation as relevant, marginal, or irrelevant when $J$ is constant.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless. Since $d^d x$ has dimension $-d$ and $\mathcal O$ has dimension $\Delta$, the source must have dimension

$$
[J]=d-\Delta.
$$

For a constant source:

- $\Delta<d$: $J$ has positive dimension, so the deformation is relevant.
- $\Delta=d$: $J$ is dimensionless, so the deformation is marginal.
- $\Delta>d$: $J$ has negative dimension, so the deformation is irrelevant.

In holography, this classification becomes a statement about the leading falloff of the dual bulk field near the AdS boundary.

</details>

### Exercise 1.3: Radial quantization and cylinder energy

Use the flat metric on $\mathbb R^d$ in polar coordinates,

$$
ds_{\mathbb R^d}^2 = dr^2 + r^2 d\Omega_{d-1}^2,
$$

and define $r=e^\tau$. Show that $\mathbb R^d\setminus\{0\}$ is Weyl equivalent to $\mathbb R_\tau\times S^{d-1}$. Explain why a primary operator of dimension $\Delta$ creates a cylinder state of energy $\Delta$.

<details>
<summary><strong>Solution</strong></summary>

With $r=e^\tau$, $dr=e^\tau d\tau$, so

$$
ds_{\mathbb R^d}^2
=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

Thus $\mathbb R^d\setminus\{0\}$ is conformal to the cylinder $\mathbb R_\tau\times S^{d-1}$.

The generator of translations in $\tau$ is the dilatation operator $D$. If $\mathcal O(0)$ is a primary with

$$
D\mathcal O(0)|0\rangle=\Delta\mathcal O(0)|0\rangle,
$$

then the corresponding cylinder state

$$
|\mathcal O\rangle = \mathcal O(0)|0\rangle
$$

has cylinder energy $E_{\mathrm{cyl}}=\Delta$.

</details>

### Exercise 1.4: Genus counting

In a large-$N$ gauge theory with adjoint fields, a connected vacuum diagram drawn in double-line notation has genus $g$. Show that its $N$-scaling is

$$
\mathcal A_g \sim N^{2-2g}
$$

when the 't Hooft coupling $\lambda=g_{\mathrm{YM}}^2N$ is held fixed.

<details>
<summary><strong>Solution</strong></summary>

A double-line diagram defines a two-dimensional surface. Let $F$ be the number of index loops, $E$ the number of propagators, and $V$ the number of vertices. Index loops give powers of $N$, while the powers of $g_{\mathrm{YM}}$ can be reorganized into powers of $\lambda$ and $N$. At fixed $\lambda$, the net power of $N$ is

$$
N^{F-E+V}.
$$

The Euler characteristic of a closed orientable surface is

$$
\chi=F-E+V=2-2g.
$$

Therefore

$$
\mathcal A_g\sim N^{2-2g}.
$$

This is the field-theory origin of the string genus expansion, with $1/N$ behaving like a string coupling.

</details>

### Exercise 1.5: Factorization and generalized free fields

Let normalized single-trace operators obey

$$
\langle \mathcal O_i(x)\mathcal O_j(y)\rangle_c \sim N^0,
\qquad
\langle \mathcal O_1\cdots \mathcal O_n\rangle_c \sim N^{2-n}.
$$

Show that the connected four-point function is suppressed by $1/N^2$ relative to disconnected Wick-like pairings. What does this imply for the leading large-$N$ behavior of $\mathcal O$?

<details>
<summary><strong>Solution</strong></summary>

For $n=4$,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_c\sim N^{-2}.
$$

The full four-point function contains disconnected products of two-point functions, each of order $N^0$:

$$
\langle \mathcal O_1\mathcal O_2\rangle
\langle \mathcal O_3\mathcal O_4\rangle
+\text{permutations}.
$$

Thus the leading large-$N$ theory behaves like a generalized free field: correlators factorize into two-point functions, but the spectrum and two-point function need not be those of an ordinary free scalar field.

In the bulk, this is the statement that single-particle fields become free at $N=\infty$.

</details>

---

## Problem Set 2: AdS Geometry

Relevant pages:

- [AdS as a Spacetime](../ads-geometry/ads-as-a-spacetime/)
- [Coordinate Systems](../ads-geometry/coordinate-systems/)
- [The Conformal Boundary](../ads-geometry/conformal-boundary/)
- [Global AdS and the Cylinder](../ads-geometry/global-ads-and-the-cylinder/)
- [Fields in AdS](../ads-geometry/fields-in-ads/)
- [Black Holes and Black Branes](../ads-geometry/black-holes-and-black-branes/)

### Exercise 2.1: Global AdS from the embedding

AdS$_{d+1}$ is the hyperboloid

$$
-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2=-L^2
$$

inside $\mathbb R^{2,d}$. Use the parametrization

$$
X_{-1}=L\cosh\rho\cos t,
\qquad
X_0=L\cosh\rho\sin t,
\qquad
X_i=L\sinh\rho\, n_i,
$$

with $\sum_i n_i^2=1$, to derive the global AdS metric.

<details>
<summary><strong>Solution</strong></summary>

The ambient metric is

$$
ds^2=-dX_{-1}^2-dX_0^2+\sum_{i=1}^d dX_i^2.
$$

Substituting the parametrization and using $\sum_i n_i dn_i=0$ gives

$$
ds^2
=L^2\left(-\cosh^2\rho\,dt^2+d\rho^2+\sinh^2\rho\,d\Omega_{d-1}^2\right).
$$

Strictly, $t$ is periodic on the embedded hyperboloid. The physical AdS spacetime used in holography is usually the universal cover, where $t\in\mathbb R$.

</details>

### Exercise 2.2: The conformal boundary of global AdS

Starting from

$$
ds^2
=L^2\left(-\cosh^2\rho\,dt^2+d\rho^2+\sinh^2\rho\,d\Omega_{d-1}^2\right),
$$

show that the conformal boundary is $\mathbb R_t\times S^{d-1}$.

<details>
<summary><strong>Solution</strong></summary>

At large $\rho$,

$$
\cosh\rho\sim \sinh\rho\sim \frac{e^\rho}{2}.
$$

Thus the metric asymptotes to

$$
ds^2\sim L^2\left[d\rho^2+\frac{e^{2\rho}}{4}\left(-dt^2+d\Omega_{d-1}^2\right)\right].
$$

Multiplying by the conformal factor $4e^{-2\rho}/L^2$ and taking $\rho\to\infty$ removes the divergent scale and leaves

$$
ds_{\partial}^2=-dt^2+d\Omega_{d-1}^2.
$$

Therefore the boundary conformal class contains the cylinder metric on $\mathbb R_t\times S^{d-1}$.

</details>

### Exercise 2.3: Scalar falloffs in Poincare AdS

For Euclidean Poincare AdS,

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+d\mathbf x^2\right),
$$

consider a scalar satisfying

$$
(\nabla^2-m^2)\phi=0.
$$

Assume a near-boundary power law $\phi\sim z^\alpha$. Show that

$$
\alpha(\alpha-d)=m^2L^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Near the boundary, derivatives along $\mathbf x$ are subleading for the indicial equation. The scalar Laplacian gives

$$
\nabla^2\phi
=\frac{z^2}{L^2}\left(\partial_z^2\phi-\frac{d-1}{z}\partial_z\phi+\cdots\right).
$$

For $\phi=z^\alpha$,

$$
\partial_z^2\phi-\frac{d-1}{z}\partial_z\phi
=\alpha(\alpha-d)z^{\alpha-2}.
$$

Therefore

$$
(\nabla^2-m^2)\phi=0
\quad\Longrightarrow\quad
\alpha(\alpha-d)=m^2L^2.
$$

The two roots are

$$
\alpha=\Delta_-=d-\Delta,
\qquad
\alpha=\Delta,
$$

where $m^2L^2=\Delta(\Delta-d)$.

</details>

### Exercise 2.4: Black-brane temperature

The planar AdS$_{d+1}$ black brane can be written as

$$
ds^2=\frac{L^2}{z^2}\left[-f(z)dt^2+d\mathbf x^2+\frac{dz^2}{f(z)}\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

Derive its Hawking temperature.

<details>
<summary><strong>Solution</strong></summary>

Near the horizon, set $z=z_h-u$ with $u\ll z_h$. Then

$$
f(z)\approx \frac{d}{z_h}u.
$$

The Euclidean $(t_E,z)$ part of the metric is

$$
ds_E^2\approx \frac{L^2}{z_h^2}\left[\frac{d u}{z_h}dt_E^2+\frac{z_h}{d u}du^2\right].
$$

Define a radial coordinate $\rho$ by

$$
u=\frac{d z_h}{4}\rho^2.
$$

Then

$$
ds_E^2\approx \frac{L^2}{z_h^2}\left[d\rho^2+\left(\frac{d}{2z_h}\right)^2\rho^2 dt_E^2\right].
$$

Smoothness at $\rho=0$ requires

$$
t_E\sim t_E+\frac{4\pi z_h}{d}.
$$

Thus

$$
T=\frac{1}{\beta}=\frac{d}{4\pi z_h}.
$$

</details>

---

## Problem Set 3: String Origin of AdS/CFT

Relevant pages:

- [Open and Closed Strings](../string-origin/open-and-closed-strings/)
- [D-Branes for Field Theorists](../string-origin/d-branes-for-field-theorists/)
- [D3-Branes: Two Descriptions](../string-origin/d3-branes-two-descriptions/)
- [Near-Horizon Geometry](../string-origin/near-horizon-geometry/)
- [The Decoupling Limit](../string-origin/decoupling-limit/)
- [The Parameter Map](../string-origin/parameter-map/)
- [Why Classical Gravity Emerges](../string-origin/why-classical-gravity-emerges/)

### Exercise 3.1: The near-horizon D3-brane metric

The extremal D3-brane metric is

$$
ds^2=H(r)^{-1/2}dx_{1,3}^2+H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
\qquad
H(r)=1+\frac{L^4}{r^4}.
$$

Show that for $r\ll L$ this becomes $\mathrm{AdS}_5\times S^5$.

<details>
<summary><strong>Solution</strong></summary>

In the near-horizon region $r\ll L$,

$$
H(r)\approx \frac{L^4}{r^4}.
$$

Therefore

$$
H^{-1/2}\approx \frac{r^2}{L^2},
\qquad
H^{1/2}\approx \frac{L^2}{r^2}.
$$

The metric becomes

$$
ds^2
=\frac{r^2}{L^2}dx_{1,3}^2
+\frac{L^2}{r^2}dr^2
+L^2d\Omega_5^2.
$$

With $z=L^2/r$, this is

$$
ds^2
=\frac{L^2}{z^2}\left(dz^2+dx_{1,3}^2\right)+L^2d\Omega_5^2.
$$

The first factor is Poincare AdS$_5$, and the second is a round $S^5$ of the same radius $L$.

</details>

### Exercise 3.2: Parameter map and classical gravity

Use

$$
L^4=4\pi g_s N\alpha'^2,
\qquad
\lambda=g_{\mathrm{YM}}^2N,
\qquad
g_{\mathrm{YM}}^2=4\pi g_s.
$$

Show that

$$
\frac{L^4}{\alpha'^2}=\lambda,
\qquad
g_s=\frac{\lambda}{4\pi N}.
$$

Then identify the conditions for suppressing stringy and quantum corrections.

<details>
<summary><strong>Solution</strong></summary>

Substituting $g_{\mathrm{YM}}^2=4\pi g_s$ into $\lambda=g_{\mathrm{YM}}^2N$ gives

$$
\lambda=4\pi g_sN.
$$

Thus

$$
L^4=\lambda\alpha'^2,
\qquad
\frac{L^4}{\alpha'^2}=\lambda,
\qquad
g_s=\frac{\lambda}{4\pi N}.
$$

Stringy curvature corrections are suppressed when

$$
\frac{\alpha'}{L^2}\sim \lambda^{-1/2}\ll1,
$$

so one needs $\lambda\gg1$. Bulk quantum loops are suppressed by powers of $G_N/L^{d-1}\sim1/N^2$, so one needs $N\gg1$. Classical supergravity is reliable when both conditions hold, with the additional requirement that the relevant string coupling regime is weak.

</details>

### Exercise 3.3: Why the low-energy limit is subtle

In the D3-brane decoupling limit, one sends $\alpha'\to0$ while keeping

$$
U=\frac{r}{\alpha'}
$$

fixed. Explain why this can keep near-horizon excitations finite even though massive string modes in the asymptotically flat region decouple.

<details>
<summary><strong>Solution</strong></summary>

In the open-string description, massive string states have masses of order

$$
M_s\sim \frac{1}{\sqrt{\alpha'}},
$$

so they decouple as $\alpha'\to0$ at fixed gauge-theory energy.

In the closed-string geometry, however, the D3-brane throat has a large redshift. Energies measured at infinity are redshifted relative to local energies near $r=0$. Keeping

$$
U=\frac{r}{\alpha'}
$$

fixed isolates excitations whose asymptotic energy remains finite because the redshift compensates the shrinking string length. The decoupling limit therefore retains the near-horizon AdS throat while removing interactions with asymptotically flat bulk modes.

</details>

### Exercise 3.4: Symmetry matching

List the bosonic symmetries of $\mathrm{AdS}_5\times S^5$ and match them to the bosonic symmetries of $\mathcal N=4$ SYM.

<details>
<summary><strong>Solution</strong></summary>

The isometry group of $\mathrm{AdS}_5$ is

$$
SO(2,4),
$$

which is the conformal group of four-dimensional Minkowski space. The isometry group of $S^5$ is

$$
SO(6)\simeq SU(4),
$$

which matches the $R$-symmetry of $\mathcal N=4$ SYM.

Thus

$$
SO(2,4)\times SO(6)
$$

matches the bosonic part of the superconformal symmetry of the boundary theory.

</details>

---

## Problem Set 4: The Basic Dictionary

Relevant pages:

- [Statement of the Correspondence](../dictionary/statement-of-the-correspondence/)
- [The GKPW Prescription](../dictionary/gkpw-prescription/)
- [Scalar Two-Point Functions](../dictionary/scalar-two-point-functions/)
- [Mass-Dimension Relation](../dictionary/mass-dimension-relation/)
- [Alternate Quantization and the BF Bound](../dictionary/alternate-quantization-and-bf-bound/)
- [One-Point Functions and VEVs](../dictionary/one-point-functions-and-vevs/)
- [Spin, Symmetry, and Conserved Currents](../dictionary/spin-symmetry-and-conserved-currents/)
- [The Stress Tensor and the Metric](../dictionary/stress-tensor-and-the-metric/)

### Exercise 4.1: The GKPW differentiations

Assume

$$
W_{\mathrm{CFT}}[\phi_{(0)}]
= -S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

Show that

$$
\langle \mathcal O(x)\rangle
= -\frac{1}{\sqrt{g_{(0)}}}\frac{\delta S_{\text{ren,on-shell}}}{\delta \phi_{(0)}(x)}
$$

with this Euclidean sign convention. Explain why different references may differ by signs.

<details>
<summary><strong>Solution</strong></summary>

The CFT one-point function is defined by

$$
\langle \mathcal O(x)\rangle
=
\frac{1}{\sqrt{g_{(0)}}}\frac{\delta W_{\mathrm{CFT}}}{\delta \phi_{(0)}(x)}.
$$

Using $W_{\mathrm{CFT}}=-S_{\text{ren,on-shell}}$ gives

$$
\langle \mathcal O(x)\rangle
= -\frac{1}{\sqrt{g_{(0)}}}\frac{\delta S_{\text{ren,on-shell}}}{\delta \phi_{(0)}(x)}.
$$

Sign differences arise from choices such as $Z=e^{-S_E}$ versus $Z=e^{iS_L}$, whether the source deformation is $+\int J\mathcal O$ or $-\int J\mathcal O$, and whether canonical momenta are defined with inward or outward normal vectors.

</details>

### Exercise 4.2: Mass-dimension relation and the BF bound

Let

$$
\Delta_\pm=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

Find the condition for $\Delta_\pm$ to be real. Interpret it physically.

<details>
<summary><strong>Solution</strong></summary>

Reality requires

$$
\frac{d^2}{4}+m^2L^2\ge0.
$$

Thus

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

This is the Breitenlohner–Freedman bound. In AdS, a scalar can have negative mass squared without being unstable, because the gravitational potential and boundary conditions can stabilize it. Below the BF bound, the scaling dimensions become complex, signaling an instability.

</details>

### Exercise 4.3: Alternate quantization window

For a scalar in AdS$_{d+1}$, alternate quantization is possible when both near-boundary modes are normalizable. The window is

$$
-\frac{d^2}{4}<m^2L^2<-\frac{d^2}{4}+1.
$$

Show that in this window $\Delta_- > \frac{d-2}{2}$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
\nu=\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

The window says

$$
0<\nu<1.
$$

Then

$$
\Delta_- = \frac d2-\nu > \frac d2-1 = \frac{d-2}{2}.
$$

This is precisely the scalar unitarity bound in a $d$-dimensional CFT. Alternate quantization is allowed when the lower-dimension operator still respects unitarity.

</details>

### Exercise 4.4: Gauge fields and currents

A bulk Maxwell field has near-boundary expansion in AdS$_{d+1}$, schematically,

$$
A_i(z,x)=a_i(x)+z^{d-2}b_i(x)+\cdots.
$$

Identify the source and response. What boundary operator is dual to $A_i$? What Ward identity follows from bulk gauge invariance?

<details>
<summary><strong>Solution</strong></summary>

The leading coefficient $a_i(x)$ is the source. It is a background gauge field coupled to a conserved current:

$$
\int d^d x\, a_i J^i.
$$

The response coefficient $b_i(x)$ is related, after normalization and counterterms, to $\langle J^i\rangle$.

Bulk gauge invariance implies invariance of the renormalized generating functional under

$$
a_i\to a_i+\partial_i\lambda.
$$

This gives the Ward identity

$$
\nabla_i\langle J^i\rangle=0,
$$

up to possible anomaly terms in anomalous theories.

</details>

### Exercise 4.5: Stress tensor from metric variation

The CFT stress tensor is defined by

$$
\langle T^{ij}\rangle
=\frac{2}{\sqrt{g_{(0)}}}\frac{\delta W}{\delta g_{(0)ij}}.
$$

Using $W=-S_{\mathrm{ren}}$, write the corresponding holographic expression. Explain why the metric is special among sources.

<details>
<summary><strong>Solution</strong></summary>

With $W=-S_{\mathrm{ren}}$,

$$
\langle T^{ij}\rangle
=-\frac{2}{\sqrt{g_{(0)}}}\frac{\delta S_{\mathrm{ren}}}{\delta g_{(0)ij}}.
$$

The metric is special because it sources the stress tensor and also determines the geometry on which all other sources and operators are defined. Its bulk dual is the full dynamical metric, not a probe field. Therefore its variation requires the Gibbons–Hawking–York term, gravitational counterterms, and careful treatment of diffeomorphism and Weyl Ward identities.

</details>

---

## Problem Set 5: Holographic Renormalization

Relevant pages:

- [Why Renormalization Is Needed](../holographic-renormalization/why-renormalization-is-needed/)
- [Near-Boundary Expansion](../holographic-renormalization/near-boundary-expansion/)
- [Counterterms and the Renormalized Action](../holographic-renormalization/counterterms-and-renormalized-action/)
- [One-Point Functions from Variation](../holographic-renormalization/one-point-functions-from-variation/)
- [Ward Identities and Anomalies](../holographic-renormalization/ward-identities-and-anomalies/)
- [Radial Hamiltonian Viewpoint](../holographic-renormalization/radial-hamiltonian-viewpoint/)
- [A Practical Recipe](../holographic-renormalization/practical-recipe/)

### Exercise 5.1: Divergence of a scalar on-shell action

For a scalar in Euclidean AdS$_{d+1}$, the regulated on-shell action contains a boundary term

$$
S_{\mathrm{reg}}
=\frac12\int_{z=\epsilon} d^d x\sqrt{\gamma}\,\phi n^z\partial_z\phi.
$$

Using

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+\cdots,
$$

show that the leading divergence scales as $\epsilon^{d-2\Delta}$.

<details>
<summary><strong>Solution</strong></summary>

For Poincare AdS,

$$
\sqrt{\gamma}\sim \left(\frac{L}{\epsilon}\right)^d,
\qquad
n^z\partial_z\sim -\frac{\epsilon}{L}\partial_z.
$$

The leading scalar behavior gives

$$
\phi\partial_z\phi
\sim
z^{d-\Delta}\phi_{(0)}\,(d-\Delta)z^{d-\Delta-1}\phi_{(0)}
\sim z^{2d-2\Delta-1}.
$$

Multiplying by $\sqrt{\gamma}n^z\sim \epsilon^{-d+1}$ gives

$$
S_{\mathrm{reg}}^{\mathrm{leading}}
\sim
\epsilon^{-d+1}\epsilon^{2d-2\Delta-1}
=
\epsilon^{d-2\Delta}.
$$

This divergence is local in the source and is removed by a local boundary counterterm.

</details>

### Exercise 5.2: A scalar counterterm

For a scalar with standard quantization, the leading counterterm often has the form

$$
S_{\mathrm{ct}}
=\frac{d-\Delta}{2L}\int_{z=\epsilon} d^d x\sqrt{\gamma}\,\phi^2.
$$

Explain why this counterterm is local and why locality is essential.

<details>
<summary><strong>Solution</strong></summary>

The counterterm is built from fields induced on the cutoff surface $z=\epsilon$: $\gamma_{ij}$ and $\phi$. It contains no inverse nonlocal operators such as $1/\Box$. Therefore it is local.

Locality is essential because UV divergences of a local QFT are canceled by local counterterms. In holography, near-boundary divergences are dual to boundary UV divergences. A nonlocal counterterm would change finite long-distance physics rather than merely choosing a renormalization scheme.

</details>

### Exercise 5.3: Ward identity from source variation

Suppose

$$
W[g_{(0)},J]
$$

is invariant under infinitesimal boundary diffeomorphisms generated by $\xi^i$. The sources transform as

$$
\delta g_{(0)ij}=\nabla_i\xi_j+\nabla_j\xi_i,
\qquad
\delta J=\xi^i\nabla_i J.
$$

Show that

$$
\nabla_i\langle T^{ij}\rangle+\langle\mathcal O\rangle\nabla^j J=0.
$$

<details>
<summary><strong>Solution</strong></summary>

The variation of $W$ is

$$
\delta W
=\int d^d x\sqrt{g_{(0)}}\left(
\frac12\langle T^{ij}\rangle\delta g_{(0)ij}
+\langle\mathcal O\rangle\delta J
\right).
$$

Substituting the diffeomorphism variations gives

$$
\delta W
=\int \sqrt{g_{(0)}}\left(
\langle T^{ij}\rangle\nabla_i\xi_j
+\langle\mathcal O\rangle\xi^i\nabla_iJ
\right).
$$

Integrating the first term by parts,

$$
\delta W
=-\int \sqrt{g_{(0)}}\,\xi_j
\left(\nabla_i\langle T^{ij}\rangle+\langle\mathcal O\rangle\nabla^jJ\right).
$$

Since $\xi_j$ is arbitrary and $\delta W=0$, the Ward identity follows.

</details>

### Exercise 5.4: Weyl anomaly from a logarithmic term

Suppose the renormalized action contains a logarithmic counterterm contribution of the form

$$
S_{\log}=\log \epsilon\int d^d x\sqrt{g_{(0)}}\,\mathcal A[g_{(0)},J].
$$

Explain why the trace Ward identity may contain an anomaly.

<details>
<summary><strong>Solution</strong></summary>

A boundary Weyl transformation is related to a rescaling of the cutoff. If the regulated action contains a $\log\epsilon$ term, changing the cutoff changes the finite part by a local functional. After renormalization, this local functional remains as an anomalous Weyl variation.

Schematically,

$$
\langle T^i{}_i\rangle
+\sum_a (d-\Delta_a)J_a\langle\mathcal O_a\rangle
=\mathcal A.
$$

The anomaly $\mathcal A$ is local in the sources and background metric. It is not removable by counterterms that preserve all desired symmetries.

</details>

### Exercise 5.5: Radial Hamiltonian intuition

Explain why the radial Hamilton–Jacobi equation can be interpreted as a holographic renormalization group equation.

<details>
<summary><strong>Solution</strong></summary>

The radial coordinate controls the cutoff scale of the boundary theory. Moving the cutoff surface from $z=\epsilon$ to a nearby value changes the induced fields and the regulated on-shell action. The Hamilton–Jacobi equation describes precisely this radial evolution:

$$
\partial_r S_{\text{on-shell}}+H\left[\Phi,\frac{\delta S}{\delta\Phi}\right]=0.
$$

Near the boundary, solving this equation locally determines divergent counterterms. The finite radial evolution of renormalized data corresponds to RG flow of sources, couplings, and expectation values.

</details>

---

## Problem Set 6: Correlators and Probes

Relevant pages:

- [Witten Diagrams](../correlators-probes/witten-diagrams/)
- [Three-Point Functions and Bulk Couplings](../correlators-probes/three-point-functions-and-bulk-couplings/)
- [Four-Point Functions and Bulk Locality](../correlators-probes/four-point-functions-and-bulk-locality/)
- [Heavy Operators and Geodesics](../correlators-probes/heavy-operators-and-geodesics/)
- [Wilson Loops](../correlators-probes/wilson-loops/)
- [Probe Branes and Flavor](../correlators-probes/probe-branes-and-flavor/)
- [Bulk Causality and Boundary Consistency](../correlators-probes/bulk-causality-and-boundary-consistency/)

### Exercise 6.1: Contact Witten diagram scaling

Consider a cubic bulk interaction

$$
S_{\mathrm{int}}=\frac{g_{123}}{3!}\int d^{d+1}x\sqrt{g}\,\phi_1\phi_2\phi_3.
$$

Write the tree-level contribution to

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle.
$$

What CFT data does $g_{123}$ control?

<details>
<summary><strong>Solution</strong></summary>

The tree-level contact Witten diagram is

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
\sim
-g_{123}\int_{\mathrm{AdS}} d^{d+1}X\sqrt{g}\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2)K_{\Delta_3}(X;x_3),
$$

up to normalization conventions. Conformal symmetry fixes the position dependence:

$$
\frac{C_{123}}{|x_{12}|^{\Delta_1+\Delta_2-\Delta_3}
|x_{23}|^{\Delta_2+\Delta_3-\Delta_1}
|x_{31}|^{\Delta_3+\Delta_1-\Delta_2}}.
$$

The bulk coupling $g_{123}$ controls the OPE coefficient $C_{123}$ after dividing by the chosen two-point normalizations.

</details>

### Exercise 6.2: Generalized free four-point functions

Let $\mathcal O$ be a normalized large-$N$ single-trace scalar. At leading order,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
$$

factorizes into pairings. Explain why this implies the presence of double-trace operators in the $\mathcal O\times\mathcal O$ OPE.

<details>
<summary><strong>Solution</strong></summary>

The disconnected four-point function contains products of two-point functions. In a conformal block decomposition, these disconnected pieces are not empty; they are reproduced by an infinite tower of double-trace primary operators schematically of the form

$$
[\mathcal O\mathcal O]_{n,\ell}
\sim
\mathcal O\,\partial^{2n}\partial_{\{\mu_1}\cdots\partial_{\mu_\ell\}}\mathcal O.
$$

At leading large $N$ their dimensions are approximately

$$
\Delta_{n,\ell}=2\Delta+2n+\ell.
$$

Bulk interactions at order $1/N^2$ shift these dimensions and OPE coefficients, encoding binding energies and scattering data in AdS.

</details>

### Exercise 6.3: Geodesic approximation to a two-point function

For a heavy scalar with $\Delta\gg1$, the bulk propagator is approximated by

$$
G(X,Y)\sim e^{-m\ell(X,Y)}.
$$

In Euclidean Poincare AdS$_{d+1}$, the geodesic anchored at two boundary points separated by $\ell_{\partial}$ has regularized length

$$
\ell_{\mathrm{reg}}=2L\log\frac{\ell_{\partial}}{\epsilon}+\text{constant}.
$$

Show that this reproduces the expected CFT two-point scaling.

<details>
<summary><strong>Solution</strong></summary>

Using the geodesic approximation,

$$
\langle\mathcal O(x)\mathcal O(y)\rangle
\sim e^{-m\ell_{\mathrm{reg}}}
\sim
\left(\frac{\epsilon}{|x-y|}\right)^{2mL}.
$$

The cutoff-dependent factor is removed by boundary wavefunction renormalization. For a heavy scalar,

$$
\Delta\approx mL.
$$

Therefore

$$
\langle\mathcal O(x)\mathcal O(y)\rangle
\sim \frac{1}{|x-y|^{2\Delta}},
$$

as required by conformal symmetry.

</details>

### Exercise 6.4: Wilson loop saddle

Explain why the expectation value of a large-$N$, large-$\lambda$ Wilson loop is approximated by

$$
\langle W(C)\rangle\sim e^{-S_{\mathrm{NG}}^{\mathrm{ren}}[\Sigma_C]},
$$

where $\Sigma_C$ is a string worldsheet ending on $C$ at the AdS boundary.

<details>
<summary><strong>Solution</strong></summary>

A Wilson loop in the fundamental representation inserts an external fundamental charge. In the string description, fundamental charges are endpoints of fundamental strings. Therefore a boundary loop $C$ is filled by a string worldsheet $\Sigma_C$ whose boundary is $C$.

At large $\lambda$,

$$
\frac{L^2}{\alpha'}\sim \sqrt\lambda\gg1,
$$

so the string path integral is dominated by a classical worldsheet saddle. The action is the Nambu–Goto area,

$$
S_{\mathrm{NG}}=\frac{1}{2\pi\alpha'}\int d^2\sigma\sqrt{\det h}.
$$

The area diverges near the boundary due to the infinite mass of the external quark; subtracting this divergence gives $S_{\mathrm{NG}}^{\mathrm{ren}}$.

</details>

### Exercise 6.5: Causality in pure AdS

A bulk null curve in pure AdS connects two boundary points. Explain why it cannot arrive earlier than a boundary null curve connecting the same endpoints.

<details>
<summary><strong>Solution</strong></summary>

Pure AdS has a conformal structure in which bulk null curves projected to the boundary cannot beat the boundary light cone. In global AdS, a radial null ray from boundary to center and back takes boundary time $\Delta t=\pi$, the same as a boundary null ray crossing the sphere from one antipodal point to the other. More general bulk curves are no faster.

This no-shortcut property is crucial for boundary causality. In deformed geometries or higher-derivative theories, apparent bulk shortcuts can signal inconsistency unless additional physics restores causality.

</details>

---

## Problem Set 7: Thermal and Real-Time Holography

Relevant pages:

- [Black Branes and Thermal CFTs](../thermal-real-time/black-branes-and-thermal-cfts/)
- [Hawking–Page transition](../thermal-real-time/hawking-page-transition/)
- [Euclidean Gravity and Free Energy](../thermal-real-time/euclidean-gravity-and-free-energy/)
- [Real-Time Prescription](../thermal-real-time/real-time-prescription/)
- [Retarded Green Functions](../thermal-real-time/retarded-green-functions/)
- [Quasinormal Modes](../thermal-real-time/quasinormal-modes/)
- [Hydrodynamics from Gravity](../thermal-real-time/hydrodynamics-from-gravity/)
- [Shear Viscosity](../thermal-real-time/shear-viscosity/)

### Exercise 7.1: Planar black-brane thermodynamics

For the planar AdS$_{d+1}$ black brane,

$$
ds^2=\frac{L^2}{z^2}\left[-f(z)dt^2+d\mathbf x^2+\frac{dz^2}{f(z)}\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

show that the entropy density is

$$
s=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}.
$$

Then write it in terms of $T$.

<details>
<summary><strong>Solution</strong></summary>

The horizon is at $z=z_h$. The spatial metric along the horizon is

$$
ds_{\mathrm{hor}}^2=\frac{L^2}{z_h^2}d\mathbf x^2.
$$

The area per unit boundary spatial volume is

$$
\frac{A}{V}=\left(\frac{L}{z_h}\right)^{d-1}.
$$

The Bekenstein–Hawking entropy density is therefore

$$
s=\frac{A}{4G_{d+1}V}
=\frac{1}{4G_{d+1}}\left(\frac{L}{z_h}\right)^{d-1}.
$$

Using

$$
T=\frac{d}{4\pi z_h},
$$

we get

$$
s=\frac{L^{d-1}}{4G_{d+1}}\left(\frac{4\pi T}{d}\right)^{d-1}.
$$

</details>

### Exercise 7.2: Hawking–Page temperature

For a global AdS$_{d+1}$ Schwarzschild black hole,

$$
f(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}}.
$$

The free energy changes sign at $r_h=L$. Show that the transition temperature is

$$
T_{\mathrm{HP}}=\frac{d-1}{2\pi L}.
$$

<details>
<summary><strong>Solution</strong></summary>

The temperature of a global AdS-Schwarzschild black hole is

$$
T=\frac{1}{4\pi}\left(\frac{d r_h}{L^2}+\frac{d-2}{r_h}\right).
$$

At the Hawking–Page transition, $r_h=L$. Therefore

$$
T_{\mathrm{HP}}
=\frac{1}{4\pi}\left(\frac{d}{L}+\frac{d-2}{L}\right)
=\frac{d-1}{2\pi L}.
$$

In the boundary theory on $S^{d-1}$, this corresponds to a large-$N$ confinement/deconfinement transition.

</details>

### Exercise 7.3: Infalling boundary condition

Near a nonextremal horizon, a scalar mode behaves as

$$
\phi\sim (r-r_h)^{\pm i\omega/(4\pi T)}e^{-i\omega t}.
$$

Identify the infalling solution.

<details>
<summary><strong>Solution</strong></summary>

Introduce the tortoise coordinate $r_*$, with $r_*\to -\infty$ at the horizon. Near the horizon,

$$
r_*\sim \frac{1}{4\pi T}\log(r-r_h).
$$

Modes behave as

$$
e^{-i\omega t}e^{\pm i\omega r_*}.
$$

The infalling Eddington–Finkelstein coordinate is

$$
v=t+r_*.
$$

The infalling mode is regular as a function of $v$:

$$
e^{-i\omega v}=e^{-i\omega t}e^{-i\omega r_*}
\sim e^{-i\omega t}(r-r_h)^{-i\omega/(4\pi T)}.
$$

Thus the minus exponent is infalling.

</details>

### Exercise 7.4: Quasinormal modes as poles

Suppose a bulk fluctuation has near-boundary expansion

$$
\phi(z)=z^{d-\Delta}A(\omega,k)+z^\Delta B(\omega,k)+\cdots.
$$

The retarded Green function is schematically

$$
G_R(\omega,k)\sim \frac{B(\omega,k)}{A(\omega,k)}.
$$

Explain why quasinormal modes are poles of $G_R$.

<details>
<summary><strong>Solution</strong></summary>

Quasinormal modes satisfy two conditions:

1. infalling behavior at the horizon;
2. no source at the boundary.

The no-source condition is

$$
A(\omega,k)=0.
$$

For a nontrivial solution with $B\ne0$, this makes

$$
G_R\sim \frac{B}{A}
$$

singular. Therefore quasinormal frequencies are poles of the retarded Green function. Hydrodynamic modes are the quasinormal modes whose frequencies vanish as $k\to0$.

</details>

### Exercise 7.5: Shear diffusion and $\eta/s$

Hydrodynamics predicts a shear pole

$$
\omega=-iD_\eta k^2+\cdots,
\qquad
D_\eta=\frac{\eta}{\epsilon+p}.
$$

For a conformal plasma with zero chemical potential, show that if $\eta/s=1/(4\pi)$, then

$$
D_\eta=\frac{1}{4\pi T}.
$$

<details>
<summary><strong>Solution</strong></summary>

At zero chemical potential, thermodynamics gives

$$
\epsilon+p=sT.
$$

Therefore

$$
D_\eta=\frac{\eta}{sT}.
$$

Using

$$
\frac{\eta}{s}=\frac{1}{4\pi},
$$

we get

$$
D_\eta=\frac{1}{4\pi T}.
$$

This is the shear diffusion constant of two-derivative Einstein gravity duals.

</details>

---

## Problem Set 8: Entanglement and Geometry

Relevant pages:

- [Entanglement Entropy in QFT](../entanglement-geometry/entanglement-entropy-in-qft/)
- [Ryu–Takayanagi formula](../entanglement-geometry/ryu-takayanagi-formula/)
- [The Covariant HRT formula](../entanglement-geometry/covariant-hrt-formula/)
- [Entanglement Wedges](../entanglement-geometry/entanglement-wedges/)
- [Relative Entropy and Linearized Gravity](../entanglement-geometry/relative-entropy-and-linearized-gravity/)
- [Quantum Extremal Surfaces](../entanglement-geometry/quantum-extremal-surfaces/)
- [Islands and Information](../entanglement-geometry/islands-and-information/)

### Exercise 8.1: Entanglement first law

Relative entropy is

$$
S(\rho\|\sigma)=\mathrm{Tr}(\rho\log\rho)-\mathrm{Tr}(\rho\log\sigma).
$$

Let $\rho=\sigma+\delta\rho$ with $\mathrm{Tr}\delta\rho=0$. Show that to first order,

$$
\delta S = \delta\langle K_\sigma\rangle,
\qquad
K_\sigma=-\log\sigma.
$$

<details>
<summary><strong>Solution</strong></summary>

The von Neumann entropy is

$$
S(\rho)=-\mathrm{Tr}(\rho\log\rho).
$$

The first-order variation is

$$
\delta S=-\mathrm{Tr}(\delta\rho\log\sigma)-\mathrm{Tr}(\sigma\sigma^{-1}\delta\rho).
$$

The second term is $-\mathrm{Tr}\delta\rho=0$. Thus

$$
\delta S=\mathrm{Tr}(\delta\rho K_\sigma)=\delta\langle K_\sigma\rangle.
$$

This is the entanglement first law.

</details>

### Exercise 8.2: RT interval in AdS$_3$

In Poincare AdS$_3$,

$$
ds^2=\frac{L^2}{z^2}(dz^2+dx^2-dt^2),
$$

consider a boundary interval of length $\ell$ at fixed $t$. The geodesic is a semicircle. Its regularized length is

$$
\mathrm{Length}_{\mathrm{reg}}=2L\log\frac{\ell}{\epsilon}.
$$

Use RT and Brown–Henneaux to reproduce the CFT$_2$ vacuum interval entropy.

<details>
<summary><strong>Solution</strong></summary>

The RT formula gives

$$
S_A=\frac{\mathrm{Length}_{\mathrm{reg}}}{4G_3}
=\frac{L}{2G_3}\log\frac{\ell}{\epsilon}.
$$

Brown–Henneaux gives

$$
c=\frac{3L}{2G_3}.
$$

Therefore

$$
\frac{L}{2G_3}=\frac{c}{3},
$$

and

$$
S_A=\frac{c}{3}\log\frac{\ell}{\epsilon}.
$$

This is the standard vacuum entanglement entropy of an interval in a two-dimensional CFT.

</details>

### Exercise 8.3: Homology condition

Why is the homology condition necessary in the RT formula? Give an example where minimizing area alone would give the wrong answer.

<details>
<summary><strong>Solution</strong></summary>

The homology condition requires that the boundary region $A$ and the bulk surface $\gamma_A$ together bound a bulk region. It chooses the correct surface among possible extremal surfaces and encodes the density matrix whose entropy is being computed.

For a thermal state dual to a black hole, the entropy of the entire boundary should equal the thermal entropy, not zero. If one allowed the empty surface for $A=$ the whole boundary, area minimization alone would give $S=0$. The homology condition instead allows the horizon as the relevant surface, giving

$$
S=\frac{\mathrm{Area}_{\mathrm{horizon}}}{4G_N}.
$$

</details>

### Exercise 8.4: Quantum extremal surface condition

The generalized entropy is

$$
S_{\mathrm{gen}}(X)=\frac{\mathrm{Area}(X)}{4G_N}+S_{\mathrm{bulk}}(\Sigma_X).
$$

What equation determines a quantum extremal surface?

<details>
<summary><strong>Solution</strong></summary>

A quantum extremal surface is stationary under local deformations of $X$:

$$
\delta_X S_{\mathrm{gen}}=0.
$$

Equivalently,

$$
\frac{1}{4G_N}\delta_X\mathrm{Area}(X)+\delta_X S_{\mathrm{bulk}}(\Sigma_X)=0.
$$

The first term is classical geometry. The second term is the response of the bulk entanglement entropy to moving the surface. At leading classical order, $S_{\mathrm{bulk}}$ is subleading and the condition reduces to extremality of the area.

</details>

### Exercise 8.5: Islands and the Page curve

In the island formula, the radiation entropy is computed by

$$
S(R)=\min_{I}\;\mathrm{ext}_{I}\left[\frac{\mathrm{Area}(\partial I)}{4G_N}+S_{\mathrm{bulk}}(R\cup I)\right].
$$

Explain why an island saddle can make the entropy decrease after the Page time.

<details>
<summary><strong>Solution</strong></summary>

Without an island, $S_{\mathrm{bulk}}(R)$ grows as Hawking radiation accumulates. This reproduces the semiclassical monotonic growth.

With an island, the entropy is instead computed using $R\cup I$. After the Page time, the island includes degrees of freedom in the black-hole interior that purify part of the radiation. The bulk entropy term becomes smaller, while the area cost is roughly the remaining black-hole entropy. Minimizing over saddles causes the island saddle to dominate when it gives a smaller generalized entropy. This produces a Page curve compatible with unitarity.

</details>

---

## Problem Set 9: AdS$_3$/CFT$_2$

Relevant pages:

- [Why AdS$_3$ Is Special](../ads3-cft2/why-ads3-is-special/)
- [Brown–Henneaux central charge](../ads3-cft2/brown-henneaux-central-charge/)
- [BTZ Black Holes](../ads3-cft2/btz-black-holes/)
- [Cardy Formula and Black-Hole Entropy](../ads3-cft2/cardy-formula-and-black-hole-entropy/)
- [Virasoro Symmetry and Boundary Gravitons](../ads3-cft2/virasoro-symmetry-and-boundary-gravitons/)
- [Lessons for Higher-Dimensional Holography](../ads3-cft2/lessons-for-higher-dimensional-holography/)

### Exercise 9.1: No local gravitons in three dimensions

Use the fact that in three dimensions the Riemann tensor is algebraically determined by the Ricci tensor to explain why pure Einstein gravity in AdS$_3$ has no local propagating gravitons.

<details>
<summary><strong>Solution</strong></summary>

In $3$ dimensions, the Weyl tensor vanishes identically. The Riemann tensor can be written entirely in terms of $R_{\mu\nu}$ and $R$. In vacuum Einstein gravity with cosmological constant,

$$
R_{\mu\nu}=-\frac{2}{L^2}g_{\mu\nu}.
$$

Therefore the full Riemann tensor is locally fixed to that of AdS$_3$. There are no local metric perturbations carrying independent degrees of freedom. The nontrivial physics comes from global identifications, black holes, and boundary gravitons associated with asymptotic symmetries.

</details>

### Exercise 9.2: Brown–Henneaux central charge

Use

$$
c=\frac{3L}{2G_3}
$$

and the BTZ entropy

$$
S_{\mathrm{BTZ}}=\frac{2\pi r_+}{4G_3}
$$

to anticipate why the Cardy formula should reproduce black-hole entropy.

<details>
<summary><strong>Solution</strong></summary>

The BTZ mass and angular momentum map to CFT left and right energies. The Cardy formula gives, schematically,

$$
S_{\mathrm{Cardy}}
=2\pi\sqrt{\frac{c}{6}\left(L_0-\frac c{24}\right)}
+2\pi\sqrt{\frac{c}{6}\left(\bar L_0-\frac c{24}\right)}.
$$

Since $c\sim L/G_3$ and the CFT energies scale with combinations of $r_+\pm r_-$, the square roots combine into a result proportional to $r_+/G_3$. The exact normalization gives

$$
S_{\mathrm{Cardy}}=\frac{2\pi r_+}{4G_3}=S_{\mathrm{BTZ}}.
$$

The match is powerful because it uses asymptotic symmetry data, not detailed microscopic string states.

</details>

### Exercise 9.3: BTZ temperatures

For a rotating BTZ black hole, the left and right temperatures are

$$
T_L=\frac{r_+-r_-}{2\pi L},
\qquad
T_R=\frac{r_++r_-}{2\pi L}.
$$

Show that for $r_-=0$, they are equal. What is the physical interpretation?

<details>
<summary><strong>Solution</strong></summary>

Setting $r_-=0$ gives

$$
T_L=T_R=\frac{r_+}{2\pi L}.
$$

A nonrotating BTZ black hole has no left-right asymmetry in the dual CFT. Rotation corresponds to unequal excitation of left- and right-moving sectors; when angular momentum vanishes, the two sectors have equal temperatures.

</details>

### Exercise 9.4: Boundary gravitons and descendants

Explain why AdS$_3$ boundary gravitons are dual to Virasoro descendants of the vacuum rather than new primary operators.

<details>
<summary><strong>Solution</strong></summary>

Boundary gravitons are generated by Brown–Henneaux asymptotic diffeomorphisms. They are not local bulk propagating modes; they are large diffeomorphism excitations carrying nonzero surface charges.

In the CFT, the corresponding excitations are obtained by acting on the vacuum with Virasoro generators:

$$
L_{-n_1}\cdots L_{-n_k}|0\rangle.
$$

These are descendants in the vacuum module. They are physical because the associated diffeomorphisms are not pure gauge at the boundary.

</details>

---

## Problem Set 10: Applications and Beyond

Relevant pages:

- [What Counts as a Holographic CFT?](../applications-beyond/what-counts-as-a-holographic-cft/)
- [Other AdS Backgrounds](../applications-beyond/other-ads-backgrounds/)
- [RG Flows and Domain Walls](../applications-beyond/rg-flows-and-domain-walls/)
- [Confinement and Hard-Wall Models](../applications-beyond/confinement-and-hard-wall-models/)
- [Finite Density and Bulk Gauge Fields](../applications-beyond/finite-density-and-bulk-gauge-fields/)
- [Reissner–Nordstrom AdS](../applications-beyond/reissner-nordstrom-ads/)
- [AdS$_2$ Throats and IR Criticality](../applications-beyond/ads2-throats-and-ir-criticality/)
- [Holographic Conductivity](../applications-beyond/holographic-conductivity/)
- [Holographic Superconductors](../applications-beyond/holographic-superconductors/)
- [Fermions and Spectral Functions](../applications-beyond/fermions-and-spectral-functions/)
- [Bottom-Up Models](../applications-beyond/bottom-up-models/)
- [Limits of the Dictionary](../applications-beyond/limits-of-the-dictionary/)

### Exercise 10.1: Large gap and local bulk EFT

Explain why large $N$ alone is not enough to guarantee a local Einstein gravity dual. What additional condition is usually needed?

<details>
<summary><strong>Solution</strong></summary>

Large $N$ gives factorization and weak bulk interactions. It suggests a semiclassical bulk expansion, but it does not guarantee that the bulk is local or that only low-spin fields are light.

A local Einstein-like bulk EFT also needs a sparse low-dimension single-trace spectrum, or equivalently a large gap $\Delta_{\mathrm{gap}}$ to higher-spin and stringy single-trace operators. This gap suppresses higher-derivative and stringy corrections, allowing a small number of light bulk fields to interact locally in AdS.

</details>

### Exercise 10.2: Holographic $c$-theorem intuition

Consider a domain-wall metric

$$
ds^2=dr^2+e^{2A(r)}\eta_{ij}dx^i dx^j.
$$

Explain why a monotonicity theorem for $A'(r)$ can be interpreted as a holographic $c$-theorem.

<details>
<summary><strong>Solution</strong></summary>

In a holographic RG flow, the radial direction corresponds to energy scale. Fixed points are AdS regions with constant $A'(r)=1/L_{\mathrm{eff}}$. The number of degrees of freedom is measured by a quantity proportional to

$$
\frac{1}{G_N[A'(r)]^{d-1}}.
$$

Einstein's equations plus the null energy condition imply monotonicity of an appropriate function of $A'(r)$. This matches the expectation that degrees of freedom decrease along RG flow from UV to IR.

</details>

### Exercise 10.3: Hard-wall mass gap

A hard-wall model cuts off AdS at $z=z_m$. Explain why this produces a discrete spectrum for normal modes.

<details>
<summary><strong>Solution</strong></summary>

In pure Poincare AdS, the radial direction extends to $z=\infty$, allowing a continuum of normalizable modes in many cases. A hard wall imposes an IR boundary condition at finite $z=z_m$, turning the radial wave equation into a Sturm–Liouville problem on a finite interval:

$$
0<z<z_m.
$$

With boundary conditions at both $z=0$ and $z=z_m$, only discrete eigenvalues are allowed. These eigenvalues are interpreted as masses of bound states in the boundary theory.

</details>

### Exercise 10.4: Charge density as electric flux

For a bulk Maxwell field with action

$$
S=-\frac{1}{4g_F^2}\int d^{d+1}x\sqrt{-g}\,F_{MN}F^{MN},
$$

show that the canonical radial momentum conjugate to $A_t$ is proportional to charge density.

<details>
<summary><strong>Solution</strong></summary>

The radial canonical momentum is

$$
\Pi^t
=\frac{\delta S}{\delta(\partial_r A_t)}
=-\frac{1}{g_F^2}\sqrt{-g}\,F^{rt},
$$

up to sign conventions depending on the radial coordinate and normal orientation.

The holographic dictionary identifies the variation of the renormalized action with the current expectation value:

$$
\langle J^t\rangle=\rho\sim \Pi^t_{\mathrm{ren}}.
$$

Thus boundary charge density is radial electric flux.

</details>

### Exercise 10.5: AdS$_2$ scaling

In an extremal RN-AdS background, the near-horizon region is often

$$
\mathrm{AdS}_2\times\mathbb R^{d-1}.
$$

Why does this lead to frequency scaling but not ordinary momentum scaling in the IR?

<details>
<summary><strong>Solution</strong></summary>

AdS$_2$ has an $SL(2,\mathbb R)$ scaling symmetry acting on time and the AdS$_2$ radial coordinate. The spatial $\mathbb R^{d-1}$ directions are spectators in the near-horizon geometry. Therefore the IR critical behavior scales frequency but treats momentum as a parameter labeling different AdS$_2$ fields.

This produces semi-local criticality: nontrivial scaling in time, but not in space.

</details>

### Exercise 10.6: Superconductor instability

In a charged black-brane background, a charged scalar has an effective mass in the near-horizon region. Explain how a near-horizon BF-bound violation can trigger a holographic superconducting instability.

<details>
<summary><strong>Solution</strong></summary>

The charged scalar couples to the background gauge field through

$$
D_M=\nabla_M-iqA_M.
$$

This modifies the effective mass in the near-horizon region. In an extremal or near-extremal charged black brane, the near-horizon geometry may contain an AdS$_2$ factor. If the effective mass violates the AdS$_2$ BF bound, the normal phase becomes unstable to developing scalar hair.

In the boundary theory, a charged operator condenses:

$$
\langle\mathcal O\rangle\ne0,
$$

breaking the global $U(1)$ symmetry. Strictly, unless the boundary $U(1)$ is dynamical, the phase is a superfluid rather than an ordinary electromagnetic superconductor.

</details>

---

## Problem Set 11: Bulk Quantum Gravity from CFT

Relevant pages:

- [Bulk Effective Field Theory](../bulk-quantum-gravity/bulk-effective-field-theory/)
- [Large $N$ Factorization and Fock Space](../bulk-quantum-gravity/large-n-factorization-and-fock-space/)
- [Bulk Reconstruction](../bulk-quantum-gravity/bulk-reconstruction/)
- [Quantum Error Correction](../bulk-quantum-gravity/quantum-error-correction/)
- [Black-Hole Information in AdS/CFT](../bulk-quantum-gravity/black-hole-information-in-ads-cft/)
- [Stringy and Quantum Corrections](../bulk-quantum-gravity/stringy-and-quantum-corrections/)
- [Open Problems and Research Map](../bulk-quantum-gravity/open-problems-and-research-map/)

### Exercise 11.1: Bulk loop counting

Explain why connected bulk loop corrections are expected to be suppressed by $G_N/L^{d-1}\sim1/N^2$.

<details>
<summary><strong>Solution</strong></summary>

The classical gravitational action scales as

$$
S_{\mathrm{grav}}\sim \frac{L^{d-1}}{G_N}.
$$

In AdS/CFT this coefficient is proportional to the number of CFT degrees of freedom, often $N^2$ for adjoint gauge theories. Therefore

$$
\frac{L^{d-1}}{G_N}\sim N^2.
$$

The saddle-point expansion of the bulk path integral is an expansion in the inverse of this coefficient:

$$
\frac{G_N}{L^{d-1}}\sim \frac{1}{N^2}.
$$

Thus bulk loops correspond to $1/N^2$ corrections in the CFT.

</details>

### Exercise 11.2: Multi-trace states and bulk Fock space

Why are double-trace operators interpreted as two-particle states in the bulk at leading large $N$?

<details>
<summary><strong>Solution</strong></summary>

At leading large $N$, normalized single-trace operators behave as generalized free fields. Products of two single-trace operators therefore create approximately independent excitations. A double-trace primary has schematic form

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}.
$$

Its leading dimension is approximately

$$
\Delta_1+\Delta_2+2n+\ell,
$$

which is the energy of two particles in global AdS, with radial excitation number $n$ and angular momentum $\ell$. Interactions shift this dimension at order $1/N^2$.

</details>

### Exercise 11.3: HKLL reconstruction at leading order

The leading reconstruction of a free bulk scalar is schematically

$$
\phi(z,x)=\int d^d x'\,K(z,x|x')\mathcal O(x').
$$

What properties must the smearing kernel $K$ satisfy?

<details>
<summary><strong>Solution</strong></summary>

The kernel must ensure that $\phi(z,x)$:

1. solves the free bulk wave equation;
2. has the correct near-boundary limit corresponding to $\mathcal O$;
3. obeys the chosen bulk boundary conditions and state-dependent regularity conditions;
4. has the correct bulk commutators within the code subspace.

In interacting theories, this expression receives multi-trace corrections. In gravitational theories, one must also specify a gravitational dressing because local bulk operators are not gauge-invariant by themselves.

</details>

### Exercise 11.4: Error correction and redundant reconstruction

Explain how the same bulk operator can be reconstructible on two different boundary regions without contradicting ordinary quantum mechanics.

<details>
<summary><strong>Solution</strong></summary>

In holography, bulk operators are logical operators acting on a code subspace of the full boundary Hilbert space. Quantum error-correcting codes allow the same logical operator to have different physical representations on different sets of boundary degrees of freedom.

These representations agree inside the code subspace, even though they are different microscopic operators on the full Hilbert space. There is no contradiction because they are not independent copies of the operator; they are different reconstructions of the same logical action.

</details>

### Exercise 11.5: Boundary unitarity and black-hole information

Why does AdS/CFT strongly suggest that black-hole evaporation in AdS is unitary, even though semiclassical gravity seems to produce information loss?

<details>
<summary><strong>Solution</strong></summary>

The boundary CFT is an ordinary quantum theory with unitary time evolution. If AdS/CFT is an exact equivalence, then any bulk process, including black-hole formation and evaporation in AdS with appropriate boundary conditions, must be encoded in unitary CFT evolution.

The semiclassical Hawking calculation is not wrong in its regime; rather, it misses nonperturbative or quantum-gravitational effects that become important for questions about the fine-grained entropy. Islands and replica wormholes provide one modern way to see how semiclassical gravitational calculations of entropy can be modified to produce a Page curve.

</details>

### Exercise 11.6: Stringy versus quantum corrections

Classify the following corrections as stringy, quantum, or both:

1. a higher-derivative term $\alpha'^3 R^4$;
2. a one-loop determinant of a bulk field;
3. exchange of a massive string mode;
4. a genus-one string worldsheet correction.

<details>
<summary><strong>Solution</strong></summary>

1. $\alpha'^3 R^4$ is a stringy finite-coupling correction. In AdS$_5$/CFT$_4$ it is suppressed by powers of $1/\lambda$.
2. A one-loop determinant of a bulk field is a quantum bulk correction, usually suppressed by $1/N^2$.
3. Exchange of a massive string mode is stringy; its effects are suppressed at energies below the string scale or by a large gap.
4. A genus-one worldsheet correction is quantum in string perturbation theory, controlled by powers of $g_s$, and therefore related to $1/N$ effects. Depending on the observable, it may also involve stringy scale dependence.

</details>

---

## Challenge Problems

These problems are more open-ended. They are meant for readers who want to convert the course into research preparation.

### Challenge 1: Derive a scalar two-point function with all normalization factors

Starting from the Euclidean AdS scalar action,

$$
S=\frac12\int d^{d+1}x\sqrt g\left[(\partial\phi)^2+m^2\phi^2\right],
$$

solve the momentum-space equation using Bessel functions, impose regularity in the interior, evaluate the regulated on-shell action, subtract local divergences, and derive the nonlocal part of

$$
\langle\mathcal O(k)\mathcal O(-k)\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

The solution is

$$
\phi(z,k)=\phi_{(0)}(k)\,\mathcal N\,z^{d/2}K_\nu(kz),
\qquad
\nu=\Delta-\frac d2,
$$

with $\mathcal N$ chosen so that the leading near-boundary coefficient is $\phi_{(0)}$. Expanding $K_\nu(kz)$ near $z=0$ separates analytic terms in $k^2$ from the nonanalytic term $k^{2\nu}$. The analytic terms correspond to contact terms and are removed or shifted by local counterterms. The nonlocal term gives

$$
\langle\mathcal O(k)\mathcal O(-k)\rangle
\propto
k^{2\nu},
$$

for noninteger $\nu$. Fourier transforming gives

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
\propto
\frac{1}{|x|^{2\Delta}}.
$$

The exact coefficient depends on the normalization of the bulk action and the operator.

</details>

### Challenge 2: From entanglement first law to linearized Einstein equations

For a ball-shaped boundary region in the vacuum CFT, use the known local modular Hamiltonian and the RT formula to explain why

$$
\delta S_A=\delta\langle K_A\rangle
$$

for all balls implies the linearized Einstein equations in the bulk.

<details>
<summary><strong>Solution</strong></summary>

The CFT modular Hamiltonian for a ball is an integral of the stress tensor with a conformal Killing weight. The holographic stress tensor maps its variation to the asymptotic metric perturbation. The RT entropy variation maps to the variation of the extremal-surface area.

Using the Iyer–Wald formalism, the difference

$$
\delta\langle K_A\rangle-\delta S_A
$$

can be written as a bulk integral over a region bounded by the ball and its RT surface, with integrand proportional to the linearized Einstein equations contracted with a Killing vector associated with the ball. If the entanglement first law holds for all balls, this integral vanishes for all such regions, implying the local linearized Einstein equations.

</details>

### Challenge 3: A controlled bottom-up model checklist

Choose a bottom-up holographic model from the literature. Analyze it using the following checklist:

1. What are the sources and operators?
2. What symmetries are exact?
3. What is the UV completion, if known?
4. Which parameters are fitted rather than derived?
5. Which predictions are robust under changing higher-derivative terms or potentials?
6. Does the model obey basic causality, stability, and thermodynamic consistency checks?

<details>
<summary><strong>Solution</strong></summary>

There is no single answer. A good analysis distinguishes dictionary-level statements from phenomenological assumptions. For example, in an Einstein–Maxwell–dilaton model, the metric sources $T^{ij}$, the Maxwell field sources a current $J^i$, and the scalar sources some operator $\mathcal O$. But unless the scalar potential and gauge coupling function are derived from a known compactification, they are phenomenological inputs.

A strong answer should identify which observables are protected by symmetry or horizon universality and which are model-dependent. It should also check thermodynamic stability, positivity of spectral functions, absence of superluminal boundary propagation, and the reliability of the two-derivative truncation.

</details>

### Challenge 4: Design a research-level problem from the course

Pick one equation from the course and turn it into a research question. The question should include:

- a precise setup;
- a limit or approximation scheme;
- an observable;
- a known result to reproduce;
- one new direction or deformation.

<details>
<summary><strong>Solution</strong></summary>

A good example:

**Setup:** Einstein–Maxwell–scalar theory in AdS$_4$.

**Limit:** probe limit first, then include backreaction perturbatively.

**Observable:** optical conductivity $\sigma(\omega)$ across the superconducting transition.

**Known result:** reproduce the gap-like feature and delta function in the imaginary part associated with superfluid density.

**New direction:** add a controlled higher-derivative interaction such as $C_{MNRS}F^{MN}F^{RS}$ and study which features of the conductivity remain robust while checking causality constraints.

The key is to avoid vague goals such as “study holographic superconductors.” A research problem becomes tractable only after the observable, approximation, and consistency checks are specified.

</details>

## Final advice

Do not treat these exercises as isolated computations. The same pattern repeats across the course:

$$
\text{source}
\quad\longrightarrow\quad
\text{bulk boundary condition}
\quad\longrightarrow\quad
\text{regularity or state condition}
\quad\longrightarrow\quad
S_{\mathrm{ren}}
\quad\longrightarrow\quad
\text{CFT observable}.
$$

Once this chain becomes familiar, AdS/CFT stops looking like a bag of miracles and starts looking like a rigorous computational language.
