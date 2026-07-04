---
title: "Near-Horizon Geometry"
description: "Derive how the extremal D3-brane supergravity solution develops an AdS5 x S5 throat, and learn how the radial coordinate becomes the first geometric version of energy scale in AdS/CFT."
sidebar:
  order: 40
---

The previous page explained that a stack of $N$ coincident D3-branes has two complementary descriptions. The open-string description gives four-dimensional $\mathcal N=4$ super-Yang–Mills theory. The closed-string description gives the extremal D3-brane supergravity solution.

This page performs the central geometric step: it shows explicitly that the near-horizon region of the D3-brane solution is

$$
\mathrm{AdS}_5 \times S^5 .
$$

This is the moment when the brane argument turns into the canonical AdS$_5$/CFT$_4$ geometry.

The result is simple enough to remember, but subtle enough to deserve a careful derivation. The near-horizon limit is not merely the statement that $r$ is small. It is a controlled zoom into the throat of the D3-brane geometry, in which the asymptotically flat region decouples and the throat becomes a complete spacetime with its own conformal boundary.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Near-horizon geometry of a stack of D3-branes](/figures/course/d3-near-horizon-geometry.svg)

<figcaption>

The extremal D3-brane geometry has an asymptotically flat region at $r\gg L$, a transition region near $r\sim L$, and a near-horizon throat at $r\ll L$. In the throat, $H(r)=1+L^4/r^4$ is approximated by $L^4/r^4$, and the geometry becomes $\mathrm{AdS}_5\times S^5$. The coordinate $z=L^2/r$ puts the AdS$_5$ factor in Poincaré form; $r=0$ becomes the Poincaré horizon $z=\infty$, while the mouth of the throat becomes the AdS boundary $z=0$ after the decoupling limit.

</figcaption>
</figure>

## Why this matters

The full D3-brane geometry is not pure AdS. It is a ten-dimensional spacetime that is asymptotically flat far from the branes and strongly warped near them. The AdS/CFT correspondence uses a special low-energy sector of this spacetime: the near-horizon throat.

The geometry teaches three foundational lessons.

First, AdS$_5$ is not inserted by hand. It emerges from the gravitational field of D3-branes.

Second, the radius of curvature is controlled by the same parameter that controls the strength of the gauge theory:

$$
\frac{L^4}{\alpha'^2}=\lambda .
$$

Thus weakly curved geometry corresponds to large 't Hooft coupling.

Third, the D3-brane charge becomes five-form flux through the $S^5$:

$$
\int_{S^5} F_5 \propto N .
$$

The integer $N$ does not disappear when the branes are replaced by geometry. It becomes flux, and it controls the number of degrees of freedom in the dual gauge theory.

## The extremal D3-brane solution

Work in type IIB string theory with ten-dimensional coordinates split as

$$
X^M=(x^\mu,y^i),
$$

where

$$
\mu=0,1,2,3,
\qquad
 i=1,\ldots,6.
$$

The D3-branes fill the $x^\mu$ directions and sit at the origin of the six transverse coordinates $y^i$. Define the transverse radial coordinate

$$
r^2=y^i y^i .
$$

In string frame, the extremal D3-brane metric is

$$
ds^2
=
H(r)^{-1/2}\,\eta_{\mu\nu}dx^\mu dx^\nu
+
H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
$$

where

$$
H(r)=1+\frac{L^4}{r^4}.
$$

The Minkowski metric along the branes is

$$
\eta_{\mu\nu}dx^\mu dx^\nu
=
-dt^2+d\vec x^{\,2}.
$$

The dilaton is constant,

$$
e^\Phi=g_s,
$$

and the solution carries self-dual Ramond–Ramond five-form flux $F_5$. Flux quantization relates the length scale $L$ to the D3-brane charge $N$:

$$
L^4=4\pi g_sN\alpha'^2.
$$

With the convention used in this course,

$$
g_{\mathrm{YM}}^2=4\pi g_s,
\qquad
\lambda=g_{\mathrm{YM}}^2N,
$$

so

$$
\frac{L^4}{\alpha'^2}=\lambda .
$$

Different trace conventions can move factors of $2$ and $\pi$ between $g_{\mathrm{YM}}^2$ and $g_s$. The invariant physical statement is that $L^4/\alpha'^2$ is proportional to $g_sN$, equivalently to the 't Hooft coupling up to convention.

## The two terms in $H(r)$

The harmonic function

$$
H(r)=1+\frac{L^4}{r^4}
$$

has two pieces with different geometric meanings.

At large radius,

$$
r\gg L,
$$

the constant term dominates:

$$
H(r)\approx 1.
$$

The metric becomes approximately flat ten-dimensional Minkowski spacetime:

$$
ds^2\approx \eta_{\mu\nu}dx^\mu dx^\nu+dr^2+r^2d\Omega_5^2.
$$

This is the asymptotically flat region.

Near the branes,

$$
r\ll L,
$$

the second term dominates:

$$
H(r)\approx \frac{L^4}{r^4}.
$$

This is the near-horizon region. It is also called the throat because the radial proper distance grows logarithmically as one moves toward $r=0$.

To see the throat behavior, look only at the radial part of the near-horizon metric. Since

$$
H(r)^{1/2}\approx \frac{L^2}{r^2},
$$

the radial line element is

$$
ds_{\mathrm{radial}}=\frac{L}{r}\,dr.
$$

The proper radial distance between $r_1$ and $r_2$ is therefore

$$
\ell
=
\int_{r_1}^{r_2}\frac{L}{r}\,dr
=
L\log\frac{r_2}{r_1}.
$$

As $r_1\to 0$, this distance diverges. The horizon at $r=0$ lies infinitely far down the throat in the extremal geometry.

## Deriving $\mathrm{AdS}_5\times S^5$

Now take the near-horizon approximation

$$
H(r)\approx \frac{L^4}{r^4}.
$$

Then

$$
H(r)^{-1/2}\approx \frac{r^2}{L^2},
\qquad
H(r)^{1/2}\approx \frac{L^2}{r^2}.
$$

Substitute these into the D3-brane metric:

$$
ds^2
=
\frac{r^2}{L^2}\eta_{\mu\nu}dx^\mu dx^\nu
+
\frac{L^2}{r^2}\left(dr^2+r^2d\Omega_5^2\right).
$$

The sphere term simplifies:

$$
\frac{L^2}{r^2}r^2d\Omega_5^2
=
L^2d\Omega_5^2.
$$

Thus

$$
ds^2
=
\frac{r^2}{L^2}\eta_{\mu\nu}dx^\mu dx^\nu
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2.
$$

The last term is a round five-sphere of radius $L$.

To recognize the first two terms as AdS$_5$, introduce the Poincaré radial coordinate

$$
z=\frac{L^2}{r}.
$$

Then

$$
r=\frac{L^2}{z},
\qquad
 dr=-\frac{L^2}{z^2}dz.
$$

The brane-parallel warp factor becomes

$$
\frac{r^2}{L^2}=\frac{L^2}{z^2},
$$

and the radial term becomes

$$
\frac{L^2}{r^2}dr^2
=
\frac{L^2}{z^2}dz^2.
$$

Therefore

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right)
+
L^2d\Omega_5^2.
$$

This is precisely

$$
\mathrm{AdS}_5\times S^5
$$

in Poincaré coordinates, with both factors having radius $L$.

## What happened to the branes?

A common first reaction is: if the branes were at $r=0$, and $r=0$ has become the Poincaré horizon $z=\infty$, where did the D3-branes go?

The answer is that the localized brane source has been replaced, in the near-horizon supergravity description, by flux and geometry. The D3-brane charge is measured by the five-form flux through the $S^5$:

$$
\frac{1}{(2\pi)^4\alpha'^2}\int_{S^5}F_5=N,
$$

up to the conventional normalization of $F_5$. The integer $N$ survives as topological flux data of the geometry.

This is familiar from other gravitational solutions. Outside a charged object, one can measure its charge by flux through a surrounding sphere even if the microscopic source is hidden behind a horizon or replaced by a smooth region in an effective description. In the D3-brane case, the near-horizon throat keeps the flux but discards the asymptotically flat region.

The geometric slogan is:

$$
\text{D3-branes at } r=0
\quad\leadsto\quad
\text{five-form flux through } S^5.
$$

The field-theory slogan is:

$$
N\;\text{colors}
\quad\leadsto\quad
N\;\text{units of }F_5\text{ flux}.
$$

## The near-horizon limit is a zoom

It is tempting to say simply: take $r\ll L$, drop the $1$ in $H(r)$, and obtain AdS. That is correct as a local geometric statement, but the AdS/CFT limit is more precise.

The near-horizon limit is a zoom into the throat while keeping finite the energy scale seen by the D3-brane theory. A useful variable is

$$
U=\frac{r}{\alpha'}.
$$

In the decoupling limit one sends

$$
\alpha'\to 0
$$

while keeping $U$, $g_{\mathrm{YM}}^2$, and $N$ fixed. Since

$$
L^4=\lambda\alpha'^2,
$$

the ratio

$$
\frac{L^4}{r^4}
=
\frac{\lambda\alpha'^2}{\alpha'^4U^4}
=
\frac{\lambda}{\alpha'^2U^4}
$$

becomes parametrically large in the throat scaling. Thus the $1$ in $H(r)$ disappears from the metric measured in string units. The asymptotically flat region is removed, and the throat is blown up into a complete AdS spacetime.

One often writes the near-horizon metric in the form

$$
\frac{ds^2}{\alpha'}
=
\frac{U^2}{\sqrt\lambda}\eta_{\mu\nu}dx^\mu dx^\nu
+
\sqrt\lambda\frac{dU^2}{U^2}
+
\sqrt\lambda\,d\Omega_5^2,
$$

with the same convention $L^4/\alpha'^2=\lambda$. This makes the gauge-theory coupling dependence visible: the curvature radius in string units is

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

The next page will focus on the decoupling limit in more detail. For now, the important point is that the AdS boundary of the near-horizon geometry is not the original asymptotically flat infinity. It is the upper end of the throat after the zoom.

## The redshift interpretation

The D3-brane throat also explains why near-horizon excitations are naturally low-energy excitations as seen from far away.

For a static excitation at radius $r$, the relation between local proper energy and energy measured at infinity is controlled by the time-time component of the metric:

$$
E_\infty
=
\sqrt{-g_{tt}(r)}\,E_{\mathrm{local}}.
$$

For the D3-brane solution,

$$
g_{tt}=-H(r)^{-1/2},
$$

so

$$
E_\infty=H(r)^{-1/4}E_{\mathrm{local}}.
$$

In the near-horizon region,

$$
H(r)^{-1/4}\approx \frac{r}{L},
$$

hence

$$
E_\infty\approx \frac{r}{L}E_{\mathrm{local}}.
$$

As $r\to0$, finite local energies are redshifted to arbitrarily small energies as seen from infinity. This is the closed-string-side reason that the low-energy limit keeps throat physics.

In the $z$ coordinate, this becomes

$$
E_\infty\approx \frac{L}{z}E_{\mathrm{local}}.
$$

Large $z$ means deep interior and low boundary energy. Small $z$ means near the AdS boundary and high boundary energy. This is the first geometric hint of the UV/IR relation:

$$
z\;\text{small}
\quad\leftrightarrow\quad
\text{UV},
\qquad
z\;\text{large}
\quad\leftrightarrow\quad
\text{IR}.
$$

This statement will become sharper when we study holographic renormalization.

## The sphere and the R-symmetry

The five-sphere is not an optional decoration. It remembers the six transverse directions to the D3-branes.

The original flat transverse space is

$$
\mathbb R^6.
$$

Writing it in polar coordinates gives

$$
dy^i dy^i=dr^2+r^2d\Omega_5^2.
$$

The rotations of the transverse space form

$$
SO(6).
$$

On the D3-brane worldvolume, the six transverse positions become six scalar fields of $\mathcal N=4$ SYM. Rotating these scalars gives the $SO(6)_R$ R-symmetry:

$$
SO(6)_R\simeq SU(4)_R.
$$

On the gravity side, the same symmetry is the isometry group of $S^5$:

$$
\mathrm{Isom}(S^5)=SO(6).
$$

Thus

$$
SO(6)_R\;\text{of the CFT}
\quad\longleftrightarrow\quad
SO(6)\;\text{isometry of }S^5.
$$

The size of the sphere is also fixed by the flux. More flux means a larger radius in string units:

$$
\frac{L^4}{\alpha'^2}=4\pi g_sN.
$$

In other words, a large number of colors makes the compact space large enough for classical geometry to be reliable, provided the 't Hooft coupling is large.

## The symmetry enhancement

Before taking the near-horizon limit, the D3-brane solution is invariant under the four-dimensional Poincaré group along the branes and rotations of the transverse space:

$$
ISO(1,3)\times SO(6).
$$

After taking the near-horizon limit, the AdS$_5$ factor has isometry group

$$
SO(2,4),
$$

and the sphere has isometry group

$$
SO(6).
$$

Thus the near-horizon bosonic symmetry is

$$
SO(2,4)\times SO(6).
$$

This is exactly the bosonic symmetry expected of four-dimensional $\mathcal N=4$ superconformal Yang–Mills theory:

$$
\text{conformal symmetry }SO(2,4)
\quad\times\quad
\text{R-symmetry }SO(6)_R.
$$

The enhancement from $ISO(1,3)$ to $SO(2,4)$ is a geometric reflection of conformal invariance. The D3-brane throat does not merely preserve scale invariance approximately; its metric is exactly AdS in the near-horizon limit, so it realizes the full conformal group geometrically.

## The Poincaré horizon and the AdS boundary

The coordinate change

$$
z=\frac{L^2}{r}
$$

maps the D3-brane throat as follows:

$$
r\to 0
\quad\Longleftrightarrow\quad
z\to\infty,
$$

and

$$
r\to\infty
\quad\Longleftrightarrow\quad
z\to0.
$$

This can be confusing because the near-horizon approximation was derived for $r\ll L$, while the AdS boundary seems to be at $r=\infty$.

The resolution is that the decoupling limit zooms into the throat and removes the asymptotically flat region. In the original D3-brane solution, the near-horizon approximation is valid only below the transition scale $r\sim L$. In the limiting throat geometry, the upper end of the throat is stretched into the AdS boundary. The $z=0$ boundary is therefore not the original ten-dimensional flat-space infinity. It is the boundary of the isolated near-horizon spacetime.

Similarly, the point $r=0$ is not an ordinary curvature singularity of the near-horizon geometry. It is the Poincaré horizon of AdS$_5$. The Poincaré patch covers only part of global AdS$_5$, and $z=\infty$ is a horizon of this coordinate patch.

This distinction matters later when we discuss boundary conditions. The CFT lives on the conformal boundary of the isolated AdS throat, not at the original location of the branes in the unreduced asymptotically flat geometry.

## Curvature and the supergravity limit

Both the AdS$_5$ and $S^5$ factors have radius $L$. Curvature invariants scale as powers of $1/L^2$. For example, the AdS$_5$ part has schematic curvature

$$
R_{\mathrm{AdS}_5}\sim -\frac{1}{L^2},
$$

while the $S^5$ part has positive curvature of the same magnitude:

$$
R_{S^5}\sim +\frac{1}{L^2}.
$$

Stringy corrections are controlled by the curvature in string units:

$$
\frac{\alpha'}{L^2}
=
\frac{1}{\sqrt\lambda}.
$$

Therefore the classical supergravity approximation requires

$$
\lambda\gg1.
$$

Bulk string loops are controlled by the string coupling. With the convention above,

$$
g_s=\frac{\lambda}{4\pi N}.
$$

So one also wants

$$
g_s\ll1,
$$

which is achieved in the standard large-$N$ limit by taking

$$
N\gg\lambda
$$

if one insists on weakly coupled ten-dimensional string perturbation theory, or more generally by taking $N$ large enough that gravitational loop corrections are suppressed. The common classical supergravity regime is summarized by

$$
N\gg1,
\qquad
\lambda\gg1,
\qquad
\frac{\lambda}{N}\ll1.
$$

The first condition suppresses quantum gravity corrections, the second suppresses stringy curvature corrections, and the third keeps the ten-dimensional string coupling small.

## Flux, radius, and degrees of freedom

The D3-brane solution ties together three quantities:

$$
N,
\qquad
L,
\qquad
G_{10}.
$$

Dimensional reduction on the $S^5$ gives a five-dimensional Newton constant of order

$$
G_5\sim \frac{G_{10}}{\mathrm{Vol}(S^5)}
\sim \frac{G_{10}}{L^5}.
$$

Since

$$
G_{10}\sim g_s^2\alpha'^4,
$$

and

$$
L^4\sim g_sN\alpha'^2,
$$

one finds the important scaling

$$
\frac{L^3}{G_5}\sim \frac{L^8}{G_{10}}\sim N^2.
$$

This is the gravitational version of the fact that an adjoint $SU(N)$ gauge theory has order $N^2$ degrees of freedom. In later pages, this scaling will appear in the central charges of $\mathcal N=4$ SYM, the entropy density of black branes, and the normalization of stress-tensor correlators.

## A compact derivation

It is useful to compress the entire derivation into one chain:

$$
\begin{aligned}
 ds^2
&=
H^{-1/2}dx_{1,3}^2
+
H^{1/2}(dr^2+r^2d\Omega_5^2),
\\[4pt]
H(r)&=1+\frac{L^4}{r^4},
\\[4pt]
r\ll L
&\quad\Rightarrow\quad
H(r)\approx \frac{L^4}{r^4},
\\[4pt]
ds^2
&\approx
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2,
\\[4pt]
z&=\frac{L^2}{r},
\\[4pt]
ds^2
&=
\frac{L^2}{z^2}(dz^2+dx_{1,3}^2)
+
L^2d\Omega_5^2.
\end{aligned}
$$

Here $dx_{1,3}^2=\eta_{\mu\nu}dx^\mu dx^\nu$. In Lorentzian signature,

$$
dx_{1,3}^2=-dt^2+d\vec x^{\,2}.
$$

The first factor is AdS$_5$ in Poincaré coordinates. The second factor is the round five-sphere. The two radii are equal because the geometry is supported by self-dual five-form flux in type IIB supergravity.

## Dictionary checkpoint

The near-horizon D3-brane geometry gives the following translations.

$$
\text{D3-brane harmonic function }H(r)=1+\frac{L^4}{r^4}
\quad\longrightarrow\quad
\text{asymptotically flat region plus throat}.
$$

$$
r\ll L
\quad\longrightarrow\quad
\mathrm{AdS}_5\times S^5\;\text{near-horizon geometry}.
$$

$$
z=\frac{L^2}{r}
\quad\longrightarrow\quad
\text{Poincaré AdS radial coordinate}.
$$

$$
r=0
\quad\longrightarrow\quad
z=\infty\;\text{Poincaré horizon}.
$$

$$
\int_{S^5}F_5=N
\quad\longrightarrow\quad
N\;\text{colors in the boundary theory}.
$$

$$
\frac{L^4}{\alpha'^2}=\lambda
\quad\longrightarrow\quad
\text{curvature radius controlled by the 't Hooft coupling}.
$$

$$
SO(2,4)\times SO(6)
\quad\longrightarrow\quad
\text{4d conformal symmetry }\times\text{ R-symmetry}.
$$

## Common confusions

### “Near horizon” means “set $r=0$.”

No. The near-horizon region is the scaling region $r\ll L$, not the single point $r=0$. After the coordinate change $z=L^2/r$, this entire region becomes the Poincaré patch of AdS$_5$.

### “The AdS boundary is the original flat-space infinity.”

No. The original D3-brane solution is asymptotically flat at $r\to\infty$. The AdS boundary is the upper end of the isolated throat after the near-horizon decoupling limit. It is not the same as the original asymptotically flat boundary.

### “The $S^5$ shrinks near the horizon because $r\to0$.”

No. In the near-horizon metric, the sphere term is

$$
H(r)^{1/2}r^2d\Omega_5^2
\approx
\frac{L^2}{r^2}r^2d\Omega_5^2
=
L^2d\Omega_5^2.
$$

The $S^5$ has fixed radius $L$ in the throat.

### “The branes vanish, so $N$ vanishes.”

No. The localized brane source is replaced by five-form flux. The integer $N$ remains as

$$
\int_{S^5}F_5\propto N.
$$

This flux controls both the geometry and the number of degrees of freedom of the dual gauge theory.

### “Large $N$ alone makes the geometry weakly curved.”

Not quite. The curvature radius in string units is controlled by

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

Large $N$ suppresses bulk quantum loops, but large $\lambda$ is needed to suppress stringy curvature corrections. Classical Einstein gravity requires both kinds of control.

### “The radial coordinate is literally the field-theory energy.”

The radial coordinate is geometrically tied to energy scale, but it is not literally equal to a renormalization scale in all circumstances. In the D3-brane throat, $U=r/\alpha'$ is a useful energy-like variable, and in Poincaré AdS small $z$ corresponds to the UV while large $z$ corresponds to the IR. Precise statements require specifying observables, cutoffs, and renormalization schemes.

## Exercises

### Exercise 1: Derive the near-horizon metric

Start from

$$
ds^2
=
H(r)^{-1/2}dx_{1,3}^2
+
H(r)^{1/2}(dr^2+r^2d\Omega_5^2),
$$

with

$$
H(r)=1+\frac{L^4}{r^4}.
$$

Show that for $r\ll L$,

$$
ds^2
=
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2.
$$

<details>
<summary><strong>Solution</strong></summary>

For $r\ll L$,

$$
H(r)\approx \frac{L^4}{r^4}.
$$

Therefore

$$
H(r)^{-1/2}
\approx
\left(\frac{L^4}{r^4}\right)^{-1/2}
=
\frac{r^2}{L^2},
$$

and

$$
H(r)^{1/2}
\approx
\left(\frac{L^4}{r^4}\right)^{1/2}
=
\frac{L^2}{r^2}.
$$

Substituting gives

$$
ds^2
=
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}(dr^2+r^2d\Omega_5^2).
$$

The sphere term becomes

$$
\frac{L^2}{r^2}r^2d\Omega_5^2=L^2d\Omega_5^2.
$$

So

$$
ds^2
=
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2.
$$

</details>

### Exercise 2: Put the throat in Poincaré coordinates

Using

$$
z=\frac{L^2}{r},
$$

show that

$$
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}dr^2
=
\frac{L^2}{z^2}(dz^2+dx_{1,3}^2).
$$

<details>
<summary><strong>Solution</strong></summary>

From $z=L^2/r$,

$$
r=\frac{L^2}{z},
\qquad
 dr=-\frac{L^2}{z^2}dz.
$$

Then

$$
\frac{r^2}{L^2}
=
\frac{L^2}{z^2}.
$$

For the radial term,

$$
\frac{L^2}{r^2}dr^2
=
\frac{L^2}{L^4/z^2}\left(\frac{L^4}{z^4}dz^2\right)
=
\frac{z^2}{L^2}\frac{L^4}{z^4}dz^2
=
\frac{L^2}{z^2}dz^2.
$$

Thus

$$
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}dr^2
=
\frac{L^2}{z^2}(dx_{1,3}^2+dz^2),
$$

which is AdS$_5$ in Poincaré form.

</details>

### Exercise 3: Infinite throat distance

Use the near-horizon radial line element

$$
ds_{\mathrm{radial}}=\frac{L}{r}dr
$$

to compute the proper distance from $r=\epsilon$ to $r=r_0$. What happens as $\epsilon\to0$?

<details>
<summary><strong>Solution</strong></summary>

The proper distance is

$$
\ell(\epsilon,r_0)
=
\int_\epsilon^{r_0}\frac{L}{r}dr
=
L\log\frac{r_0}{\epsilon}.
$$

As $\epsilon\to0$,

$$
\ell(\epsilon,r_0)\to\infty.
$$

Thus the extremal D3-brane throat has infinite proper length. The horizon at $r=0$ lies infinitely far down the throat in this radial metric.

</details>

### Exercise 4: Redshift in the throat

In the near-horizon region,

$$
g_{tt}=-\frac{r^2}{L^2}.
$$

Show that a local excitation of energy $E_{\mathrm{local}}$ at radius $r$ has energy

$$
E_\infty=\frac{r}{L}E_{\mathrm{local}}
$$

as measured relative to the asymptotic time coordinate.

<details>
<summary><strong>Solution</strong></summary>

For a static metric, the redshift relation is

$$
E_\infty=\sqrt{-g_{tt}(r)}\,E_{\mathrm{local}}.
$$

In the near-horizon D3-brane geometry,

$$
g_{tt}=-\frac{r^2}{L^2}.
$$

Therefore

$$
\sqrt{-g_{tt}(r)}=\frac{r}{L},
$$

and hence

$$
E_\infty=\frac{r}{L}E_{\mathrm{local}}.
$$

As $r\to0$, fixed local energies are redshifted to very small asymptotic energies. This is why throat excitations survive the low-energy limit.

</details>

### Exercise 5: Curvature in string units

Using

$$
\frac{L^4}{\alpha'^2}=\lambda,
$$

show that the condition $L^2\gg\alpha'$ is equivalent to $\lambda\gg1$.

<details>
<summary><strong>Solution</strong></summary>

Taking the square root of

$$
\frac{L^4}{\alpha'^2}=\lambda
$$

gives

$$
\frac{L^2}{\alpha'}=\sqrt\lambda.
$$

The condition that the curvature radius be large compared with the string length is

$$
L^2\gg\alpha',
$$

or

$$
\frac{L^2}{\alpha'}\gg1.
$$

Using the parameter map, this is

$$
\sqrt\lambda\gg1,
$$

which is equivalent to

$$
\lambda\gg1.
$$

Thus weak curvature in string units corresponds to strong 't Hooft coupling in the gauge theory.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- J. Polchinski, S. Chaudhuri, and C. V. Johnson, [Notes on D-Branes](https://arxiv.org/abs/hep-th/9602052).
- J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).
- J. Polchinski, [Introduction to Gauge/Gravity Duality](https://arxiv.org/abs/1010.6134).

The next page will use this geometry to formulate the decoupling limit more precisely: which sectors remain, which sectors become free, and why the equality is between $\mathcal N=4$ SYM and type IIB string theory on the isolated $\mathrm{AdS}_5\times S^5$ throat.
