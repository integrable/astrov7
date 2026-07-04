---
title: "D3-Branes: Two Descriptions"
description: "How a stack of D3-branes gives both four-dimensional N=4 super-Yang–Mills theory and a ten-dimensional gravitational D3-brane geometry, setting up the derivation of AdS5/CFT4."
sidebar:
  order: 30
---

The previous page explained why D-branes have a double life. They support open-string degrees of freedom on their worldvolume, and they source closed-string fields in spacetime. The canonical AdS$_5$/CFT$_4$ example begins when we apply this double life to a stack of $N$ coincident D3-branes in type IIB string theory.

There are two natural ways to describe the same stack.

First, look at the light open strings ending on the branes. Their low-energy dynamics is a four-dimensional gauge theory on the D3-brane worldvolume. For $N$ coincident branes, the Chan–Paton labels become $N\times N$ matrix degrees of freedom, giving a $U(N)$ gauge theory. After separating the free center-of-mass $U(1)$ multiplet, the interacting sector is $\mathcal N=4$ $SU(N)$ super-Yang–Mills theory.

Second, look at the same D3-branes as massive charged objects in type IIB string theory. They curve the surrounding ten-dimensional spacetime and source Ramond–Ramond five-form flux. At large $N$, the backreaction is strong enough that the branes are better described by a smooth classical supergravity solution: the extremal D3-brane geometry.

The key point is not that these are analogous systems. They are two descriptions of one system.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Two descriptions of a stack of D3-branes](/figures/course/d3-branes-two-descriptions.svg)

<figcaption>

A stack of $N$ coincident D3-branes has an open-string description and a closed-string description. The low-energy open-string sector gives four-dimensional $\mathcal N=4$ $U(N)$ super-Yang–Mills theory, with a decoupled center-of-mass $U(1)$. The closed-string description is the extremal D3-brane geometry, whose near-horizon region becomes $\mathrm{AdS}_5\times S^5$. The low-energy decoupling argument removes the same free flat-space closed-string sector on both sides and compares the remaining nontrivial sectors.

</figcaption>
</figure>

## Why this matters

This page is the hinge of the whole canonical construction. The AdS/CFT dictionary does not begin with a mysterious declaration that a gauge theory equals gravity. It begins with a familiar string-theory phenomenon: the same branes can be studied using open strings or closed strings.

The open-string description naturally contains gauge theory because open-string endpoints carry Chan–Paton labels. The closed-string description naturally contains gravity because closed strings contain the graviton, and D-branes carry tension and Ramond–Ramond charge. D3-branes are special because their worldvolume is four-dimensional and their low-energy gauge coupling is dimensionless. This is exactly the dimension in which a conformal Yang–Mills theory can appear.

The conceptual path is therefore:

$$
\text{D3-branes}
\quad \Longrightarrow \quad
\begin{cases}
\text{open strings on the branes} & \Rightarrow \mathcal N=4\text{ SYM},\\
\text{closed strings sourced by the branes} & \Rightarrow \text{D3-brane geometry}.
\end{cases}
$$

The next pages will take a low-energy near-horizon limit and turn this two-description statement into the standard form of the duality,

$$
\mathcal N=4\;SU(N)\;\text{SYM}
\quad \longleftrightarrow \quad
\text{type IIB string theory on } \mathrm{AdS}_5\times S^5 .
$$

## The setup

Work in ten-dimensional type IIB string theory with coordinates

$$
X^M,
\qquad M=0,1,\ldots,9.
$$

A D3-brane fills time and three spatial directions. We write the worldvolume coordinates as

$$
x^\mu,
\qquad \mu=0,1,2,3,
$$

and the six transverse coordinates as

$$
y^i,
\qquad i=1,\ldots,6.
$$

The transverse radius is

$$
r^2 = y^i y^i .
$$

The branes are taken to be flat, parallel, and coincident at $r=0$. Coincident means that the transverse positions of all $N$ branes are the same. This is important: when the branes are separated, strings stretching between different branes have nonzero length and become massive. When the branes coincide, those stretched strings become massless, and the gauge symmetry is enhanced.

For one D3-brane, the massless open-string sector gives a $U(1)$ gauge theory. For $N$ coincident D3-branes, open strings can begin and end on any pair of branes, so a field carries two brane labels:

$$
\Phi^a{}_b(x),
\qquad a,b=1,\ldots,N.
$$

Thus the worldvolume fields are $N\times N$ matrices. This is the origin of the $U(N)$ gauge symmetry.

## Description I: open strings and the worldvolume gauge theory

The open-string mass spectrum has a tower of massive string states with masses of order

$$
M^2 \sim \frac{1}{\alpha'} .
$$

At energies

$$
E\sqrt{\alpha'} \ll 1,
$$

the massive string excitations are not produced. The remaining light open-string modes on a D3-brane stack are precisely the fields of four-dimensional $\mathcal N=4$ super-Yang–Mills theory:

| Open-string mode | Four-dimensional field | Interpretation |
|---|---|---|
| vector polarizations along the brane | gauge field $A_\mu$ | gauge connection on the stack |
| scalar polarizations transverse to the brane | six scalars $\Phi^I$, $I=1,\ldots,6$ | brane positions in $\mathbb R^6$ |
| fermionic modes | four Weyl fermions | superpartners required by $\mathcal N=4$ supersymmetry |

All these fields transform in the adjoint representation of $U(N)$ because they are matrix-valued open-string modes.

A compact way to remember the field content is that $\mathcal N=4$ SYM in four dimensions is the dimensional reduction of ten-dimensional $\mathcal N=1$ super-Yang–Mills theory. The ten-dimensional gauge field has components

$$
A_M,
\qquad M=0,1,\ldots,9.
$$

After reducing to four dimensions, the components split as

$$
A_M
\quad \longrightarrow \quad
A_\mu \;\text{for}\; \mu=0,1,2,3,
\qquad
\Phi^I \equiv A_{3+I} \;\text{for}\; I=1,\ldots,6.
$$

The four-dimensional gauge field lives along the D3-brane. The six scalars describe motion in the six transverse directions.

## The $U(1)$ and the interacting $SU(N)$ sector

For $N$ coincident D3-branes, the worldvolume theory is naturally $U(N)$ rather than $SU(N)$. But the overall $U(1)$ is special. It describes the center-of-mass motion of the stack and a free abelian gauge multiplet. The interacting nonabelian dynamics is carried by the $SU(N)$ part.

Schematically,

$$
U(N) \simeq \frac{SU(N)\times U(1)}{\mathbb Z_N}.
$$

At low energies, the center-of-mass $U(1)$ decouples from the interacting $SU(N)$ sector. The canonical AdS/CFT example is usually stated as a duality involving the interacting $SU(N)$ theory:

$$
\mathcal N=4\;SU(N)\;\text{SYM}
\quad \longleftrightarrow \quad
\text{type IIB strings on }\mathrm{AdS}_5\times S^5.
$$

The $U(1)$ is not a deep contradiction. It is a decoupled free sector, not part of the strongly interacting large-$N$ dynamics that gives the AdS throat.

## Couplings on the open-string side

The D3-brane Yang–Mills coupling is related to the string coupling. With the convention used throughout this course,

$$
g_{\mathrm{YM}}^2 = 4\pi g_s,
$$

so the 't Hooft coupling is

$$
\lambda = g_{\mathrm{YM}}^2N = 4\pi g_s N.
$$

Different trace normalizations can move factors of $2$ or $2\pi$ between $g_{\mathrm{YM}}^2$ and $g_s$. The invariant lesson is that the open-string loop-counting parameter and the gauge coupling are tied to each other, while the collective backreaction of $N$ branes is controlled by $g_sN$, equivalently by $\lambda$ up to convention.

The open-string perturbative description is most direct when

$$
g_sN \ll 1,
\qquad \text{or equivalently} \qquad
\lambda \ll 1.
$$

In this regime the D3-branes are weakly backreacting, and weakly coupled Yang–Mills language is natural. The classical gravity description will be natural in the opposite regime, $g_sN\gg 1$, together with small $g_s$ so that bulk loops are suppressed. This is the first glimpse of the strong/weak character of AdS/CFT.

## Description II: closed strings and the D3-brane geometry

A D3-brane is not only a place where open strings end. It is also a dynamical object with tension and Ramond–Ramond charge. Therefore it sources closed-string fields. For $N$ coincident D3-branes, the corresponding type IIB supergravity solution is the extremal D3-brane geometry.

In string frame, the metric can be written as

$$
ds^2
=
H(r)^{-1/2}\eta_{\mu\nu}dx^\mu dx^\nu
+
H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
$$

where

$$
H(r)=1+\frac{L^4}{r^4}.
$$

The dilaton is constant,

$$
e^\Phi = g_s,
$$

and the solution carries self-dual Ramond–Ramond five-form flux $F_5$. The flux through the $S^5$ surrounding the branes is quantized and proportional to $N$:

$$
\int_{S^5} F_5 \propto N.
$$

With the convention used in this course, the length scale $L$ is related to the microscopic string parameters by

$$
L^4 = 4\pi g_sN\alpha'^2.
$$

Equivalently,

$$
\frac{L^4}{\alpha'^2}=4\pi g_sN=\lambda.
$$

This equation is already the seed of the AdS/CFT parameter map. It says that the curvature radius of the gravitational solution, measured in string units, is controlled by the 't Hooft coupling of the gauge theory.

## Why the harmonic function is $1+L^4/r^4$

The D3-brane has six transverse spatial directions. Far from the brane, the gravitational and RR fields solve a Laplace equation in the transverse space $\mathbb R^6$. For a point source in $n$ spatial dimensions, the harmonic function behaves as

$$
H(r) = 1+\frac{\text{constant}}{r^{n-2}}
\qquad (n>2).
$$

Here $n=6$, so

$$
H(r)=1+\frac{L^4}{r^4}.
$$

The constant term $1$ is important. It tells us that the geometry is asymptotically flat as $r\to\infty$:

$$
H(r)\to 1,
\qquad
r\to\infty.
$$

The second term dominates near the branes:

$$
H(r)\approx \frac{L^4}{r^4},
\qquad
r\ll L.
$$

That near-brane region is the throat that becomes $\mathrm{AdS}_5\times S^5$.

## The throat and the redshift

The D3-brane geometry has a useful physical interpretation. It contains an asymptotically flat region at large $r$ and a long throat near $r=0$. A local excitation deep in the throat is gravitationally redshifted relative to an observer at infinity.

For a static excitation, the energy measured at infinity is roughly

$$
E_\infty
\sim
H(r)^{-1/4}E_{\mathrm{local}}.
$$

Near the branes,

$$
H(r)^{-1/4}
\approx
\frac{r}{L},
$$

so

$$
E_\infty
\sim
\frac{r}{L}E_{\mathrm{local}}.
$$

Modes localized deep in the throat can have very small energy as seen from infinity. This is the closed-string-side reason that the low-energy limit keeps throat physics. It is not merely that the branes are heavy. The geometry itself creates a low-energy sector.

## Two low-energy decompositions

Now compare the low-energy decompositions on the two sides.

On the open-string side, before taking the final decoupling limit, the full system contains:

$$
\text{open strings on the D3-branes}
\quad + \quad
\text{closed strings in ten-dimensional flat space}.
$$

At low energy, this becomes

$$
\mathcal N=4\;U(N)\;\text{SYM}
\quad + \quad
\text{free ten-dimensional closed strings}.
$$

The free closed strings decouple because the ten-dimensional Newton coupling scales as

$$
G_{10}\sim g_s^2\alpha'^4,
$$

and the low-energy limit sends the gravitational interactions with the asymptotically flat bulk to zero.

On the closed-string side, the same branes are described by closed strings moving in the D3-brane background. Low-energy excitations split into two classes:

$$
\text{closed strings in the asymptotically flat region}
\quad + \quad
\text{closed strings in the near-horizon throat}.
$$

Again the asymptotically flat closed strings form a free decoupled sector. The nontrivial low-energy sector is the throat.

Thus the two descriptions have the same structure:

$$
\begin{array}{ccc}
\text{open-string description} && \text{closed-string description} \\
\mathcal N=4\;U(N)\;\text{SYM} + \text{free bulk strings}
&&
\text{throat strings} + \text{free bulk strings}.
\end{array}
$$

Discard the same free flat-space bulk sector on both sides. What remains is the core equivalence:

$$
\mathcal N=4\;SU(N)\;\text{SYM}
\quad \longleftrightarrow \quad
\text{type IIB string theory in the D3-brane throat}.
$$

The next page will show explicitly that the throat geometry is $\mathrm{AdS}_5\times S^5$.

## Why D3-branes are special

Many D$p$-branes support gauge theories, so why do D3-branes give the canonical conformal example?

The answer is dimensional. The Yang–Mills coupling on a D$p$-brane has dimension

$$
[g_{\mathrm{YM}}^2] = 3-p.
$$

For $p=3$, the coupling is dimensionless:

$$
[g_{\mathrm{YM}}^2]=0.
$$

A dimensionless coupling is compatible with conformal invariance. Indeed, the maximally supersymmetric D3-brane worldvolume theory is the four-dimensional CFT $\mathcal N=4$ SYM.

For $p\neq 3$, the worldvolume gauge theory has a dimensionful coupling. Those branes still lead to important gauge/gravity dualities, but the dual field theories are not conformal in the same simple way. The D3-brane is special because both sides naturally produce a scale-invariant near-horizon system.

## Symmetry preview

The open-string side has the symmetries of $\mathcal N=4$ SYM:

$$
SO(1,3) \times SO(6)_R
$$

plus supersymmetry. The $SO(1,3)$ is the Lorentz symmetry along the branes. The $SO(6)_R$ rotates the six transverse scalar fields, equivalently the six directions normal to the D3-branes.

The closed-string D3-brane solution has the same manifest bosonic symmetries before the near-horizon limit:

$$
SO(1,3) \times SO(6).
$$

The $SO(6)$ rotates the transverse sphere $S^5$. In the near-horizon limit, the spacetime becomes $\mathrm{AdS}_5\times S^5$, whose bosonic isometry group is

$$
SO(2,4)\times SO(6).
$$

This matches the conformal group and R-symmetry group of the four-dimensional CFT:

$$
SO(2,4)\times SO(6)_R.
$$

This symmetry enhancement is not cosmetic. It is one of the strongest clues that the near-horizon D3-brane system is exactly the same system as the conformal gauge theory.

## The validity of the two descriptions

The two descriptions are not equally useful in the same regime.

The weakly coupled open-string/gauge-theory description is most direct when

$$
\lambda = g_{\mathrm{YM}}^2N \ll 1.
$$

The weakly curved classical gravity description is most direct when

$$
\frac{L^2}{\alpha'} \gg 1,
$$

or equivalently

$$
\lambda \gg 1.
$$

Bulk quantum loops are suppressed when the effective string coupling is small, which in the AdS$_5$/CFT$_4$ large-$N$ limit means taking

$$
N\gg 1
$$

with appropriate control of $g_s\sim \lambda/N$.

Thus the classical gravity limit is roughly

$$
N\gg 1,
\qquad
\lambda\gg 1.
$$

This is the famous inversion: the gravitational description is simple when the gauge theory is strongly coupled. The D3-brane argument explains why this inversion is possible. Open strings and closed strings are different perturbative expansions of one underlying theory.

## A useful comparison table

| Same D3-brane system | Open-string description | Closed-string description |
|---|---|---|
| fundamental objects | open strings ending on branes | closed strings in spacetime |
| low-energy sector | $\mathcal N=4$ $U(N)$ SYM | extremal D3-brane supergravity background |
| interacting sector | $\mathcal N=4$ $SU(N)$ SYM | near-horizon throat strings |
| coupling parameter | $\lambda=g_{\mathrm{YM}}^2N$ | $L^4/\alpha'^2$ |
| degrees of freedom | adjoint matrices, order $N^2$ | five-form flux $N$, $L^8/G_{10}\sim N^2$ |
| simple regime | $\lambda\ll 1$ perturbative gauge theory | $N\gg1$, $\lambda\gg1$ classical supergravity |

The table is deliberately schematic. The full duality is not just a comparison of two classical limits. The exact statement relates the full quantum gauge theory to full type IIB string theory in the corresponding background.

## Dictionary checkpoint

From this page, keep the following translations.

$$
N\;\text{D3-branes}
\quad \longleftrightarrow \quad
U(N)\;\text{Chan–Paton gauge symmetry}.
$$

$$
\text{center-of-mass }U(1)
\quad \longleftrightarrow \quad
\text{decoupled free brane motion}.
$$

$$
\text{interacting open-string sector}
\quad \longleftrightarrow \quad
\mathcal N=4\;SU(N)\;\text{SYM}.
$$

$$
\text{D3-brane charge }N
\quad \longleftrightarrow \quad
\int_{S^5}F_5 \propto N.
$$

$$
\lambda=g_{\mathrm{YM}}^2N
\quad \longleftrightarrow \quad
\frac{L^4}{\alpha'^2}.
$$

The last relation is the first quantitative bridge between gauge dynamics and spacetime geometry.

## Common confusions

### “The gauge theory lives inside the AdS throat.”

Not quite. Before the decoupling limit, the open strings live on the D3-brane worldvolume in ten-dimensional asymptotically flat spacetime. After the near-horizon decoupling limit, the nontrivial open-string sector is reinterpreted as the boundary CFT dual to strings in the throat. The boundary of AdS is not literally the original brane sitting at $r=0$ in the same coordinates.

### “The D3-brane geometry is already pure AdS.”

No. The full extremal D3-brane solution has

$$
H(r)=1+\frac{L^4}{r^4}.
$$

It is asymptotically flat at large $r$. Only the near-horizon region $r\ll L$ becomes $\mathrm{AdS}_5\times S^5$.

### “The $U(1)$ means the duality should be about $U(N)$, not $SU(N)$.”

The natural brane worldvolume theory is $U(N)$, but the overall $U(1)$ is a free center-of-mass multiplet. The strongly interacting sector is $SU(N)$. Most AdS/CFT statements focus on this interacting sector. The difference between $U(N)$ and $SU(N)$ is usually invisible in leading large-$N$ local single-trace dynamics, but it matters in precise global questions.

### “The open-string and closed-string descriptions are both weakly coupled at the same time.”

Usually they are not. Weakly coupled gauge theory corresponds to $\lambda\ll1$. Weakly curved classical gravity corresponds to $\lambda\gg1$. The duality is powerful because it relates a difficult regime of one description to an easier regime of the other.

### “The five-form flux is just decoration.”

No. The $F_5$ flux carries the D3-brane charge. The integer $N$ appears geometrically through flux quantization and controls the number of degrees of freedom in the dual gauge theory.

## Exercises

### Exercise 1: Why does the D3 harmonic function fall as $1/r^4$?

The D3-brane has six transverse spatial directions. Use the Green's function of the Laplacian in $n$ spatial dimensions to explain why the extremal D3-brane harmonic function has the form

$$
H(r)=1+\frac{L^4}{r^4}.
$$

<details>
<summary><strong>Solution</strong></summary>

For a radially symmetric function in $n$ Euclidean dimensions, the Laplacian away from the origin is

$$
\nabla^2 H
=
\frac{1}{r^{n-1}}\frac{d}{dr}\left(r^{n-1}\frac{dH}{dr}\right).
$$

A harmonic function away from the source satisfies $\nabla^2H=0$, so

$$
r^{n-1}\frac{dH}{dr}=\text{constant}.
$$

Thus

$$
\frac{dH}{dr}\propto r^{1-n},
$$

and for $n>2$,

$$
H(r)=1+\frac{\text{constant}}{r^{n-2}}.
$$

For a D3-brane in ten dimensions, there are $9-3=6$ transverse spatial directions. Therefore $n=6$, and

$$
H(r)=1+\frac{L^4}{r^4}.
$$

</details>

### Exercise 2: Why is the D3-brane Yang–Mills coupling dimensionless?

In $(p+1)$ spacetime dimensions, the Yang–Mills coupling has engineering dimension

$$
[g_{\mathrm{YM}}^2]=3-p.
$$

What happens for $p=3$, and why is this important for the canonical AdS$_5$/CFT$_4$ example?

<details>
<summary><strong>Solution</strong></summary>

For $p=3$,

$$
[g_{\mathrm{YM}}^2]=3-3=0.
$$

So the gauge coupling is dimensionless. A dimensionless coupling is compatible with scale invariance and conformal invariance. The maximally supersymmetric D3-brane worldvolume theory is exactly conformal: it is four-dimensional $\mathcal N=4$ super-Yang–Mills theory. This is why D3-branes lead naturally to an AdS dual with a conformal boundary theory.

</details>

### Exercise 3: Extract the near-horizon metric

Start with the D3-brane metric

$$
ds^2
=
H(r)^{-1/2}\eta_{\mu\nu}dx^\mu dx^\nu
+
H(r)^{1/2}\left(dr^2+r^2d\Omega_5^2\right),
$$

with

$$
H(r)=1+\frac{L^4}{r^4}.
$$

Show that for $r\ll L$ the metric becomes

$$
ds^2
=
\frac{r^2}{L^2}\eta_{\mu\nu}dx^\mu dx^\nu
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2.
$$

<details>
<summary><strong>Solution</strong></summary>

In the near-horizon region $r\ll L$, the second term in $H(r)$ dominates:

$$
H(r)\approx \frac{L^4}{r^4}.
$$

Therefore

$$
H(r)^{-1/2}\approx \left(\frac{L^4}{r^4}\right)^{-1/2}=\frac{r^2}{L^2},
$$

and

$$
H(r)^{1/2}\approx \left(\frac{L^4}{r^4}\right)^{1/2}=\frac{L^2}{r^2}.
$$

Substituting into the metric gives

$$
ds^2
=
\frac{r^2}{L^2}\eta_{\mu\nu}dx^\mu dx^\nu
+
\frac{L^2}{r^2}\left(dr^2+r^2d\Omega_5^2\right).
$$

The sphere term simplifies:

$$
\frac{L^2}{r^2}r^2d\Omega_5^2=L^2d\Omega_5^2.
$$

Hence

$$
ds^2
=
\frac{r^2}{L^2}\eta_{\mu\nu}dx^\mu dx^\nu
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2.
$$

The first two terms are the Poincaré form of $\mathrm{AdS}_5$, after the coordinate change $z=L^2/r$. The next page develops this in detail.

</details>

### Exercise 4: Identify the strong/weak inversion

Using

$$
\lambda=g_{\mathrm{YM}}^2N=4\pi g_sN,
\qquad
\frac{L^4}{\alpha'^2}=\lambda,
$$

explain why weakly curved classical gravity corresponds to strong 't Hooft coupling in the gauge theory.

<details>
<summary><strong>Solution</strong></summary>

Weakly curved string backgrounds require the curvature radius to be large compared with the string length:

$$
L^2\gg \alpha'.
$$

Equivalently,

$$
\frac{L^4}{\alpha'^2}\gg1.
$$

But the D3-brane parameter map gives

$$
\frac{L^4}{\alpha'^2}=\lambda.
$$

Therefore weakly curved classical geometry requires

$$
\lambda\gg1.
$$

This is strong 't Hooft coupling in the gauge theory. Thus the simple classical gravity regime is not dual to perturbative gauge theory. It is dual to a strongly coupled large-$N$ gauge theory.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- J. Polchinski, S. Chaudhuri, and C. V. Johnson, [Notes on D-Branes](https://arxiv.org/abs/hep-th/9602052).
- J. Polchinski, [Introduction to Gauge/Gravity Duality](https://arxiv.org/abs/1010.6134).

The next page will take the near-horizon limit explicitly and show how the D3-brane throat becomes $\mathrm{AdS}_5\times S^5$.
