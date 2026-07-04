---
title: "Coordinate Systems in AdS"
description: "A practical guide to global, Poincaré, Fefferman-Graham, Eddington-Finkelstein, Euclidean, and black-brane coordinates in Anti-de Sitter spacetime."
sidebar:
  order: 20
---

A coordinate system in AdS is never just notation. It usually encodes a choice of boundary conformal frame, radial gauge, causal patch, state, or numerical strategy. The same spacetime can look like a cylinder, a half-space, a thermal black brane, or a near-boundary expansion depending on what question we ask.

This page is a working reference. The goal is not to list every possible chart on $\mathrm{AdS}_{d+1}$, but to make the standard charts feel natural and to explain what each one is good for in holography.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A diagram of the main coordinate systems used in AdS/CFT: global coordinates, Poincaré coordinates, Fefferman-Graham coordinates, and ingoing Eddington-Finkelstein coordinates.](/figures/course/ads-coordinate-systems.svg)

<figcaption>

The main coordinate systems used in this course. Global coordinates naturally describe the CFT on the cylinder $\mathbb R_\tau\times S^{d-1}$; Poincaré coordinates describe a flat-space conformal patch; Fefferman–Graham coordinates expose sources, counterterms, and one-point functions; ingoing Eddington–Finkelstein coordinates are adapted to future horizons and retarded response.

</figcaption>
</figure>

## Why coordinates matter in AdS/CFT

The boundary theory is not sensitive to an arbitrary coordinate label in the bulk. It is sensitive to the conformal structure induced at the AdS boundary, the choice of state, and the boundary conditions imposed on bulk fields. Coordinate systems matter because they make different parts of this structure manifest.

For example:

| Bulk coordinates | Boundary viewpoint | Best use |
|---|---|---|
| global coordinates | CFT on $\mathbb R\times S^{d-1}$ | spectra, normal modes, Hilbert space, global black holes |
| Poincaré coordinates | CFT on $\mathbb R^{1,d-1}$ | local correlators, RG intuition, black branes |
| Fefferman–Graham coordinates | asymptotic expansion near the boundary | sources, counterterms, stress tensor, vevs |
| Euclidean Poincaré coordinates | CFT on $\mathbb R^d$ | Euclidean correlators, bulk-to-boundary propagators |
| Schwarzschild-like black-brane coordinates | thermal state with static time | thermodynamics, free energy, entropy |
| ingoing Eddington–Finkelstein coordinates | causal infalling frame | retarded correlators, quasinormal modes, time evolution |

The safest philosophy is this:

$$
\text{coordinate choice}
\quad\neq\quad
\text{new physics},
$$

but

$$
\text{coordinate choice}
\quad\Rightarrow\quad
\text{a convenient representation of the same physics}.
$$

This distinction prevents many early mistakes. The Poincaré patch is not a different AdS/CFT duality from global AdS. Fefferman–Graham gauge is not a complete global description of a black hole. Schwarzschild time is not the best coordinate for regularity at the future horizon. Each chart answers a different question well.

## The embedding-space starting point

It is useful to keep one coordinate-independent definition in the background. Lorentzian $\mathrm{AdS}_{d+1}$ is the hyperboloid

$$
-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2=-L^2
$$

inside $\mathbb R^{2,d}$ with metric

$$
ds_{\mathrm{emb}}^2
=
-dX_{-1}^2-dX_0^2+dX_1^2+\cdots+dX_d^2.
$$

The induced metric on this hyperboloid is the AdS metric. Different coordinate systems are different parametrizations of the same surface.

The isometry group is $SO(2,d)$, matching the conformal group of a $d$-dimensional Lorentzian CFT. That group-theoretic fact is often the cleanest way to remember why AdS geometry is the right bulk geometry for a CFT.

## Global coordinates

Global coordinates cover the entire AdS hyperboloid, up to the usual issue that the original hyperboloid contains closed timelike curves. In physics we normally pass to the universal cover and let the global time coordinate run over $\mathbb R$.

A standard parametrization is

$$
\begin{aligned}
X_{-1} &= L\cosh\rho\cos\tau,\\
X_0 &= L\cosh\rho\sin\tau,\\
X_i &= L\sinh\rho\, n_i,
\qquad i=1,\ldots,d,
\end{aligned}
$$

where $n_i n_i=1$ parametrizes $S^{d-1}$. The induced metric is

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2+d\rho^2+\sinh^2\rho\,d\Omega_{d-1}^2
\right).
$$

Here $\tau$ is dimensionless. The physical global time is $t=L\tau$. If we define

$$
r=L\sinh\rho,
$$

then the same metric becomes

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+r^2 d\Omega_{d-1}^2.
$$

The boundary lies at $r\to\infty$, or equivalently $\rho\to\infty$. Near the boundary,

$$
ds^2
\sim
\frac{r^2}{L^2}
\left(-dt^2+L^2 d\Omega_{d-1}^2\right)
+
\frac{L^2}{r^2}dr^2.
$$

After stripping off the divergent conformal factor $r^2/L^2$, the boundary metric is

$$
ds_{\partial}^2=-dt^2+L^2d\Omega_{d-1}^2.
$$

Equivalently, in dimensionless time,

$$
ds_{\partial}^2
\sim
-d\tau^2+d\Omega_{d-1}^2.
$$

Thus global AdS is naturally dual to the CFT on the cylinder

$$
\mathbb R_\tau\times S^{d-1}.
$$

### When to use global coordinates

Global coordinates are the right language for questions involving the full CFT Hilbert space. They are especially useful for:

- the state-operator correspondence;
- normal modes and spectra;
- global AdS black holes;
- finite-volume thermal physics on $S^{d-1}$;
- causal questions involving the full boundary cylinder.

The energy conjugate to global time is the CFT Hamiltonian on the cylinder. For a primary operator of scaling dimension $\Delta$, the corresponding cylinder energy is essentially $\Delta/L$. This is why global AdS is the natural home of the statement

$$
\text{operator dimensions}
\quad\longleftrightarrow\quad
\text{bulk energies}.
$$

## Poincaré coordinates

Poincaré coordinates are the workhorse of AdS/CFT. They describe a patch of AdS whose boundary is flat Minkowski space.

The metric is

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+\eta_{\mu\nu}dx^\mu dx^\nu
\right),
\qquad
z>0,
$$

where

$$
\eta_{\mu\nu}=\mathrm{diag}(-,+,\ldots,+),
\qquad
\mu,\nu=0,\ldots,d-1.
$$

The boundary is at $z=0$. The deep interior of the Poincaré patch is $z\to\infty$.

The embedding-space map is conveniently written as

$$
\begin{aligned}
X_{-1}+X_d &= \frac{L^2}{z},\\
X^\mu &= \frac{Lx^\mu}{z},\\
X_{-1}-X_d &= \frac{z^2+\eta_{\mu\nu}x^\mu x^\nu}{z}.
\end{aligned}
$$

This covers the region

$$
X_{-1}+X_d>0.
$$

So the Poincaré chart is not the entire global AdS spacetime. It is a wedge. This matters when discussing global causality, finite-volume spectra, and states that do not fit inside the Poincaré patch.

### Scale transformations are manifest

The metric is invariant under

$$
z\to \lambda z,
\qquad
x^\mu\to\lambda x^\mu.
$$

On the boundary, this becomes the ordinary scale transformation of the CFT. This is the cleanest first glimpse of the UV/IR relation:

$$
\text{small }z
\quad\leftrightarrow\quad
\text{UV physics},
$$

and

$$
\text{large }z
\quad\leftrightarrow\quad
\text{IR physics}.
$$

A cutoff surface $z=\epsilon$ is therefore interpreted as a UV regulator in the boundary theory, with a scale of order

$$
\Lambda_{\mathrm{UV}}\sim\frac{1}{\epsilon}.
$$

The precise proportionality depends on conventions, Weyl frame, and how the cutoff is implemented. The robust statement is the inverse relation between radial depth and boundary energy scale.

### When to use Poincaré coordinates

Poincaré coordinates are ideal for:

- CFT correlators on flat $\mathbb R^{1,d-1}$;
- the GKP/Witten prescription in its simplest form;
- bulk-to-boundary propagators;
- planar black branes;
- translationally invariant states;
- momentum-space calculations.

The price is that global features are hidden. The surface $z\to\infty$ is called the Poincaré horizon in pure AdS. It is not a curvature singularity and not a black-hole horizon. It is a horizon of the coordinate patch.

## Global boundary versus Poincaré boundary

The boundary of global AdS is the cylinder $\mathbb R\times S^{d-1}$. The boundary of the Poincaré patch is Minkowski space $\mathbb R^{1,d-1}$, plus subtleties at the Poincaré horizon and points at infinity.

These are related by a conformal map. Let the cylinder metric be

$$
ds_{\mathrm{cyl}}^2
=
-d\tau^2+d\theta^2+\sin^2\theta\,d\Omega_{d-2}^2.
$$

Let $R$ be the radial coordinate on Minkowski space, so that

$$
ds_{\mathrm{Mink}}^2=-dt^2+dR^2+R^2d\Omega_{d-2}^2.
$$

A standard map is

$$
\frac{t}{L}
=
\frac{\sin\tau}{\cos\tau+\cos\theta},
\qquad
\frac{R}{L}
=
\frac{\sin\theta}{\cos\tau+\cos\theta}.
$$

Then

$$
ds_{\mathrm{Mink}}^2
=
\frac{L^2}{(\cos\tau+\cos\theta)^2}
\left(
-d\tau^2+d\theta^2+\sin^2\theta\,d\Omega_{d-2}^2
\right).
$$

Thus Minkowski space is conformal to a patch of the cylinder. This is the boundary reason why global AdS and the Poincaré patch describe different conformal frames and different regions of the same underlying conformal compactification.

## Euclidean AdS

The Euclidean continuation of Poincaré AdS is

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+d\vec x^{\,2}
\right),
\qquad
z>0.
$$

This space is hyperbolic space $H_{d+1}$. It is the standard arena for Euclidean CFT correlators. The boundary is $\mathbb R^d$ at $z=0$, together with the usual point at infinity after conformal compactification.

Euclidean AdS is especially useful because elliptic boundary-value problems are cleaner than Lorentzian initial-boundary-value problems. For example, the scalar bulk-to-boundary propagator in Euclidean Poincaré AdS takes the schematic form

$$
K_\Delta(z,x;x')
\propto
\left(
\frac{z}{z^2+|x-x'|^2}
\right)^\Delta.
$$

This formula is one of the first workhorses for deriving CFT two-point functions holographically.

## Fefferman–Graham coordinates

Fefferman–Graham coordinates are not just another chart. They are the near-boundary gauge in which the holographic dictionary becomes systematic.

For an asymptotically locally AdS spacetime, the metric can be written near the boundary as

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+g_{\mu\nu}(z,x)dx^\mu dx^\nu
\right).
$$

The boundary lies at $z=0$. The leading term in the expansion of $g_{\mu\nu}(z,x)$ defines the boundary metric representative:

$$
g_{\mu\nu}(z,x)
=
g_{(0)\mu\nu}(x)+z^2g_{(2)\mu\nu}(x)+\cdots.
$$

More generally, for an even boundary dimension $d$, logarithmic terms can appear:

$$
g_{\mu\nu}(z,x)
=
g_{(0)\mu\nu}
+z^2g_{(2)\mu\nu}
+\cdots
+z^d g_{(d)\mu\nu}
+z^d\log z^2\,h_{(d)\mu\nu}
+\cdots.
$$

The coefficient $g_{(0)\mu\nu}$ is the source for the CFT stress tensor. Roughly speaking, $g_{(d)\mu\nu}$ contains the state-dependent information from which $\langle T_{\mu\nu}\rangle$ is extracted, after adding the appropriate counterterms and local anomaly terms.

This is why Fefferman–Graham gauge is central in holographic renormalization:

$$
\text{near-boundary expansion}
\quad\longrightarrow\quad
\text{sources, counterterms, one-point functions}.
$$

### What Fefferman–Graham coordinates do not do

Fefferman–Graham coordinates are adapted to the boundary, not necessarily to the whole spacetime. They can break down at horizons, caustics, or other places where the family of geodesics normal to the cutoff surface becomes singular.

This is a common practical point. Use Fefferman–Graham coordinates to read off boundary data. Use other coordinates to solve a problem globally if they are better adapted to horizons or time evolution.

## Planar black-brane coordinates

The finite-temperature state of a CFT on flat space is dual, in the simplest Einstein-gravity setting, to a planar AdS black brane. In Schwarzschild-like coordinates,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right),
$$

with

$$
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The boundary is at $z=0$. The future event horizon is at

$$
z=z_h.
$$

The Hawking temperature is

$$
T=\frac{d}{4\pi z_h}.
$$

The entropy density is the horizon area density divided by $4G_{d+1}$:

$$
s
=
\frac{1}{4G_{d+1}}
\left(\frac{L}{z_h}\right)^{d-1}.
$$

These formulas are the geometric beginning of thermal holography:

$$
\text{CFT temperature}
\quad\longleftrightarrow\quad
\text{Hawking temperature},
$$

and

$$
\text{CFT entropy density}
\quad\longleftrightarrow\quad
\text{horizon area density}.
$$

The Schwarzschild-like coordinate $t$ is excellent for thermodynamics, but the metric component $g_{zz}=L^2/(z^2f)$ diverges at the horizon. This is a coordinate singularity, not a curvature singularity. For real-time response, we usually switch to horizon-regular coordinates.

## Ingoing Eddington–Finkelstein coordinates

For the black brane, define the tortoise coordinate $z_*$ by

$$
\frac{dz_*}{dz}=\frac{1}{f(z)}.
$$

An ingoing time coordinate is

$$
v=t-z_*.
$$

Then

$$
dt=dv+\frac{dz}{f(z)}.
$$

Substituting into the black-brane metric gives

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dv^2-2\,dv\,dz+d\vec x^{\,2}
\right).
$$

This metric is regular at the future horizon $z=z_h$ in the coordinates relevant for infalling observers. The coordinate $v$ labels ingoing null slices.

In pure Poincaré AdS, where $f(z)=1$, the same transformation is simply

$$
v=t-z,
$$

and the metric becomes

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-dv^2-2\,dv\,dz+d\vec x^{\,2}
\right).
$$

### Why this chart matters for retarded correlators

The retarded Green's function asks how the system responds after a source is applied. In the bulk, the causal prescription is that perturbations should be infalling at the future horizon. Ingoing Eddington–Finkelstein coordinates make this condition smooth rather than singular.

That is why many real-time and numerical calculations are performed in EF-like coordinates. They are also the natural coordinates for characteristic evolution in gravitational collapse, Vaidya geometries, and time-dependent black brane backgrounds.

## Global AdS black holes

For a CFT on $S^{d-1}$ at finite temperature, the relevant static bulk geometries are not planar black branes but global AdS black holes. A common form is

$$
ds^2
=
-F(r)dt^2+\frac{dr^2}{F(r)}+r^2d\Omega_{d-1}^2,
$$

where, for the uncharged Einstein-gravity black hole,

$$
F(r)=1+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}}.
$$

The horizon radius $r_h$ is determined by

$$
F(r_h)=0.
$$

Planar black branes and global black holes are locally similar near sufficiently large horizons, but they represent different boundary systems:

$$
\begin{array}{ccl}
\text{planar black brane} &\longleftrightarrow& \text{thermal CFT on } \mathbb R^{d-1},\\
\text{global AdS black hole} &\longleftrightarrow& \text{thermal CFT on } S^{d-1}.
\end{array}
$$

This distinction becomes important in the Hawking–Page transition and in discussions of confinement/deconfinement analogies.

## A coordinate user's guide

Here is a quick decision tree.

### Use global coordinates when...

You care about the entire boundary cylinder, normal modes, global causal structure, or states created by local operators in radial quantization.

Typical question:

$$
\text{What bulk mode corresponds to a CFT operator of dimension }\Delta?
$$

### Use Poincaré coordinates when...

You care about flat-space correlators, translationally invariant states, or simple scale transformations.

Typical question:

$$
\text{What is }\langle\mathcal O(x)\mathcal O(0)\rangle\text{ on }\mathbb R^d?
$$

### Use Fefferman–Graham coordinates when...

You need to identify sources, expectation values, conformal anomalies, or the boundary stress tensor.

Typical question:

$$
\text{Given an asymptotic metric, what is }\langle T_{\mu\nu}\rangle?
$$

### Use black-brane coordinates when...

You want temperature, entropy, free energy, static thermodynamics, or equilibrium transport.

Typical question:

$$
\text{What is the entropy density of the thermal CFT?}
$$

### Use ingoing Eddington–Finkelstein coordinates when...

You want retarded Green's functions, infalling boundary conditions, quasinormal modes, time-dependent backgrounds, or numerical evolution across a future horizon.

Typical question:

$$
\text{Which bulk perturbations are smooth at the future horizon?}
$$

## Dictionary checkpoint

Coordinate systems translate into boundary language as follows.

| Bulk statement | Boundary interpretation |
|---|---|
| global boundary is $\mathbb R\times S^{d-1}$ | CFT quantized on the cylinder |
| Poincaré boundary is $\mathbb R^{1,d-1}$ | CFT in flat-space conformal frame |
| $z\to0$ | ultraviolet boundary scale |
| $z$ large | infrared radial depth |
| Fefferman–Graham leading metric $g_{(0)\mu\nu}$ | source for $T_{\mu\nu}$ |
| black-brane horizon at $z_h$ | thermal state with $T=d/(4\pi z_h)$ |
| horizon area density | entropy density |
| ingoing EF regularity | retarded/infalling prescription |

The deepest lesson is that the CFT does not live at a particular radial coordinate. It lives at the conformal boundary. The radial coordinate organizes how bulk fields approach that boundary and how energy scales are represented geometrically.

## Common confusions

### “The Poincaré patch is all of AdS.”

It is not. Poincaré coordinates cover only the region $X_{-1}+X_d>0$ of the full AdS hyperboloid. They are perfect for many local CFT questions on flat space, but global questions may require global coordinates.

### “The Poincaré horizon is a black-hole horizon.”

In pure AdS, $z\to\infty$ is a coordinate horizon of the Poincaré patch. It is not associated with thermal entropy. A black-brane horizon at $z=z_h$ is physically different: it corresponds to a thermal state and has a nonzero horizon area density.

### “Fefferman–Graham coordinates are always the best coordinates.”

They are best near the boundary. They are not necessarily good at horizons. Holographic renormalization likes Fefferman–Graham gauge; real-time horizon physics often likes Eddington–Finkelstein gauge.

### “Changing the boundary metric representative changes the theory.”

A CFT is naturally defined on a conformal class of metrics, though Weyl anomalies and sources can make the details important. Global-cylinder and flat-space descriptions are related by conformal transformations, but the state and operator insertions must be transformed carefully.

### “The sign of the EF cross term is universal.”

The sign depends on whether the radial coordinate increases inward or outward and on whether one uses ingoing or outgoing null coordinates. In this course, with $z$ increasing inward, ingoing EF coordinates for the black brane give

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-fdv^2-2\,dv\,dz+d\vec x^{\,2}
\right).
$$

Other papers may use $r=L^2/z$, in which case the corresponding cross term often has the opposite sign.

## Exercises

### Exercise 1: Derive the global AdS metric

Starting from

$$
\begin{aligned}
X_{-1} &= L\cosh\rho\cos\tau,\\
X_0 &= L\cosh\rho\sin\tau,\\
X_i &= L\sinh\rho\,n_i,
\end{aligned}
$$

with $n_in_i=1$, derive

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2+d\rho^2+\sinh^2\rho\,d\Omega_{d-1}^2
\right).
$$

<details>
<summary><strong>Solution</strong></summary>

Compute the embedding metric

$$
ds_{\mathrm{emb}}^2
=
-dX_{-1}^2-dX_0^2+\sum_{i=1}^d dX_i^2.
$$

The first two coordinates give

$$
-dX_{-1}^2-dX_0^2
=
-L^2\sinh^2\rho\,d\rho^2
-L^2\cosh^2\rho\,d\tau^2.
$$

For $X_i=L\sinh\rho\,n_i$, using $n_idn_i=0$ and $dn_idn_i=d\Omega_{d-1}^2$, one obtains

$$
\sum_i dX_i^2
=
L^2\cosh^2\rho\,d\rho^2
+L^2\sinh^2\rho\,d\Omega_{d-1}^2.
$$

Adding the two contributions gives

$$
ds^2
=
L^2d\rho^2
-L^2\cosh^2\rho\,d\tau^2
+L^2\sinh^2\rho\,d\Omega_{d-1}^2,
$$

which is the desired metric.

</details>

### Exercise 2: Check the Poincaré scaling isometry

Show that

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right)
$$

is invariant under

$$
z\to\lambda z,
\qquad
x^\mu\to\lambda x^\mu.
$$

<details>
<summary><strong>Solution</strong></summary>

Under the transformation,

$$
dz\to\lambda dz,
\qquad
dx^\mu\to\lambda dx^\mu.
$$

Therefore the numerator transforms as

$$
dz^2+\eta_{\mu\nu}dx^\mu dx^\nu
\to
\lambda^2
\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
$$

while the denominator transforms as

$$
z^2\to\lambda^2z^2.
$$

The factors cancel, so the metric is invariant. On the boundary this is the ordinary scale transformation of the CFT.

</details>

### Exercise 3: Derive the planar black-brane temperature

For

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dt^2+\frac{dz^2}{f(z)}+d\vec x^{\,2}
\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

show that

$$
T=\frac{d}{4\pi z_h}.
$$

<details>
<summary><strong>Solution</strong></summary>

Go to Euclidean time $t=-i\tau_E$. Near the horizon, set

$$
z=z_h-\epsilon,
\qquad
\epsilon\ll z_h.
$$

Define

$$
a=|f'(z_h)|=\frac{d}{z_h}.
$$

Then

$$
f(z)\approx a\epsilon.
$$

Near the horizon, the Euclidean $(\tau_E,\epsilon)$ part of the metric is

$$
ds_E^2
\approx
\frac{L^2}{z_h^2}
\left(
a\epsilon\,d\tau_E^2
+\frac{d\epsilon^2}{a\epsilon}
\right).
$$

Define a radial coordinate $\varrho$ by

$$
\epsilon=\frac{a}{4}\varrho^2.
$$

Then

$$
\frac{d\epsilon^2}{a\epsilon}=d\varrho^2,
\qquad
a\epsilon\,d\tau_E^2=\frac{a^2}{4}\varrho^2d\tau_E^2.
$$

The near-horizon metric becomes

$$
ds_E^2
\approx
\frac{L^2}{z_h^2}
\left(
d\varrho^2
+\frac{a^2}{4}\varrho^2d\tau_E^2
\right).
$$

Smoothness at the origin requires the angular coordinate

$$
\frac{a}{2}\tau_E
$$

to have period $2\pi$. Therefore

$$
\beta=\frac{4\pi z_h}{d},
\qquad
T=\frac{1}{\beta}=\frac{d}{4\pi z_h}.
$$

</details>

### Exercise 4: Convert Schwarzschild time to ingoing EF time

Starting from the black-brane metric and defining

$$
v=t-z_* ,
\qquad
\frac{dz_*}{dz}=\frac{1}{f(z)},
$$

show that the metric becomes

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dv^2-2\,dv\,dz+d\vec x^{\,2}
\right).
$$

<details>
<summary><strong>Solution</strong></summary>

From

$$
v=t-z_* ,
$$

we get

$$
dv=dt-\frac{dz}{f(z)},
\qquad
 dt=dv+\frac{dz}{f(z)}.
$$

Substitute into

$$
-fdt^2+\frac{dz^2}{f}.
$$

This gives

$$
-f\left(dv+\frac{dz}{f}\right)^2+\frac{dz^2}{f}
=
-fdv^2-2\,dv\,dz-\frac{dz^2}{f}+\frac{dz^2}{f}.
$$

The last two terms cancel, leaving

$$
-fdv^2-2\,dv\,dz.
$$

Therefore

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-fdv^2-2\,dv\,dz+d\vec x^{\,2}
\right).
$$

</details>

## Further reading

- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- G. W. Gibbons, [Anti-de-Sitter Spacetime and Its Uses](https://arxiv.org/abs/1110.1206).
- C. A. Ballon Bayona and N. R. F. Braga, [Anti-de Sitter Boundary in Poincaré Coordinates](https://arxiv.org/abs/hep-th/0512182).
