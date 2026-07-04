---
title: "Conventions and Units"
description: "A reference page fixing the dimensions, signatures, coordinates, curvature conventions, source normalizations, and Fourier conventions used in AdS/CFT Foundations."
sidebar:
  order: 40
---

Conventions are not decoration in AdS/CFT. They decide signs in one-point functions, powers of the radial coordinate in near-boundary expansions, factors of $i$ in real-time correlators, and factors of $L$, $2\pi$, $G_N$, and $N$ in the dictionary. A reader can understand the main ideas while ignoring some of these details, but a researcher cannot compute reliably without them.

This page fixes the default conventions used throughout **AdS/CFT Foundations**. Later pages will sometimes introduce a temporary convention if it makes a derivation cleaner, but when that happens the change will be stated explicitly.

The most important default choices are:

| Convention | Choice in this course |
|---|---|
| boundary dimension | $d$ |
| bulk dimension | $D=d+1$ |
| Lorentzian signature | mostly plus, $(-,+,\ldots,+)$ |
| AdS radius | $L$ |
| Poincaré radial coordinate | $z$, with boundary at $z=0$ |
| alternative radial coordinate | $r=L^2/z$, with boundary at $r=\infty$ |
| natural units | $\hbar=c=k_B=1$ |
| Euclidean partition function | $Z_E \approx e^{-S_{E,\text{ren,on-shell}}}$ |
| Lorentzian partition function | $Z_L \approx e^{iS_{L,\text{ren,on-shell}}}$ |

The course keeps factors of $L$ visible in foundational pages. In longer computations we may set $L=1$ temporarily, but the final dictionary statements will usually restore it.

## Dimensions and indices

The boundary quantum field theory lives in $d$ spacetime dimensions. The gravitational theory lives in $d+1$ spacetime dimensions. I will often write

$$
D=d+1
$$

for the bulk dimension.

Index conventions are:

| Indices | Meaning | Range |
|---|---|---|
| $M,N,P,Q$ | bulk spacetime indices | $0,1,\ldots,d$ |
| $\mu,\nu,\rho,\sigma$ | boundary spacetime indices | $0,1,\ldots,d-1$ |
| $i,j,k,\ell$ | boundary spatial indices | $1,\ldots,d-1$ |
| $a,b,c$ | coordinates intrinsic to a cutoff surface | usually $0,1,\ldots,d-1$ |

Thus a bulk point in Poincaré coordinates is

$$
X^M=(z,x^\mu)=(z,t,\vec x),
$$

while a boundary point is

$$
x^\mu=(t,\vec x).
$$

The coordinate $z$ is a bulk coordinate. It is not a coordinate of the boundary theory.

The bulk metric is usually denoted $g_{MN}$. The induced metric on a cutoff surface is denoted $\gamma_{\mu\nu}$. The boundary metric, after the appropriate conformal rescaling and cutoff removal, is denoted $g_{(0)\mu\nu}$.

## Units and mass dimensions

We use natural units

$$
\hbar=c=k_B=1.
$$

Lengths, inverse energies, and inverse temperatures have the same dimension. In boundary field theory notation,

$$
[x^\mu]=-1,
\qquad
[\partial_\mu]=1.
$$

If a local scalar operator $\mathcal O$ has scaling dimension $\Delta$, then

$$
[\mathcal O]=\Delta.
$$

A source $J$ coupled through

$$
\int d^d x\sqrt{|g_{(0)}|}\,J\mathcal O
$$

has dimension

$$
[J]=d-\Delta.
$$

This simple relation is one of the first checks on the holographic dictionary. If a bulk scalar has near-boundary behavior

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x),
$$

then $\phi_{(0)}$ has precisely the dimension expected of a source for an operator of dimension $\Delta$, once powers of $L$ and the chosen normalization of $\phi$ are accounted for.

In the bulk,

$$
[G_D]=\text{length}^{D-2}=\text{length}^{d-1}.
$$

The dimensionless measure of gravitational strength in AdS units is therefore

$$
\frac{G_{d+1}}{L^{d-1}}.
$$

In holographic CFTs, its inverse is proportional to the number of degrees of freedom. In the canonical AdS$_5$/CFT$_4$ example,

$$
\frac{L^3}{G_5}\sim N^2.
$$

The symbol $\sim$ means “up to a numerical factor depending on convention or compactification.” When an exact coefficient matters, the relevant page will state the normalization being used.

## Lorentzian and Euclidean signatures

The default Lorentzian signature is mostly plus:

$$
\eta_{\mu\nu}=\mathrm{diag}(-1,+1,\ldots,+1).
$$

For a boundary momentum $k^\mu=(\omega,\vec k)$,

$$
k_\mu x^\mu=-\omega t+\vec k\cdot\vec x,
$$

and

$$
k^2=\eta^{\mu\nu}k_\mu k_\nu=-\omega^2+\vec k^{\,2}.
$$

Euclidean signature is obtained by Wick rotation. We write Euclidean time as $\tau$ and Euclidean coordinates as

$$
x_E^\mu=(\tau,\vec x),
\qquad
\delta_{\mu\nu}=\mathrm{diag}(+1,+1,\ldots,+1).
$$

A common Wick rotation is

$$
t=-i\tau,
\qquad
\omega=i\omega_E.
$$

This is a convention, not a theorem. In real-time holography, analytic continuation must be supplemented by a choice of contour and by physical boundary conditions at horizons. The retarded correlator, for example, is selected by incoming-wave boundary conditions at a black-hole horizon, not merely by replacing $\omega_E$ with $-i(\omega+i0^+)$ in a random Euclidean expression.

## AdS metrics

The default Poincaré patch metric for Lorentzian AdS$_{d+1}$ is

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2-dt^2+d\vec x^{\,2}
\right),
\qquad
z>0.
$$

The conformal boundary is at

$$
z\to 0.
$$

The deep Poincaré interior is at

$$
z\to \infty.
$$

The same metric is often written using

$$
r=\frac{L^2}{z}.
$$

Then

$$
ds^2
=
\frac{r^2}{L^2}
\left(
-dt^2+d\vec x^{\,2}
\right)
+
\frac{L^2}{r^2}dr^2,
\qquad
r>0,
$$

and the boundary is at

$$
r\to\infty.
$$

Both $z$ and $r$ are common. This course prefers $z$ for near-boundary expansions and field/operator dictionary derivations, because powers of $z$ make the ultraviolet limit visually obvious. It uses $r$ when discussing some black brane and D-brane geometries, because those literatures often use $r$.

The Euclidean Poincaré metric is

$$
ds_E^2
=
\frac{L^2}{z^2}
\left(
 dz^2+d\tau^2+d\vec x^{\,2}
\right).
$$

Global Lorentzian AdS$_{d+1}$ is written as

$$
ds^2
=
L^2
\left[
-(1+\rho^2)d\tau^2
+
\frac{d\rho^2}{1+\rho^2}
+
\rho^2 d\Omega_{d-1}^2
\right],
\qquad
\rho\ge 0.
$$

Its boundary is the conformal class of

$$
ds_{\partial}^2=-d\tau^2+d\Omega_{d-1}^2,
$$

so global AdS is naturally dual to the CFT on the cylinder

$$
\mathbb R_\tau\times S^{d-1}.
$$

## Fefferman–Graham form

Near the boundary, asymptotically locally AdS metrics can often be written in Fefferman–Graham gauge:

$$
ds^2
=
\frac{L^2}{z^2}
\left[
 dz^2+g_{\mu\nu}(z,x)dx^\mu dx^\nu
\right].
$$

The near-boundary expansion has the schematic form

$$
g_{\mu\nu}(z,x)
=
 g_{(0)\mu\nu}(x)
+z^2 g_{(2)\mu\nu}(x)
+\cdots
+z^d g_{(d)\mu\nu}(x)
+\cdots.
$$

For even boundary dimension $d$, logarithmic terms can appear:

$$
g_{\mu\nu}(z,x)
=
\cdots
+z^d\log z^2\,h_{(d)\mu\nu}(x)
+\cdots.
$$

Those logarithms are not technical annoyances. They are the bulk avatar of conformal anomalies in the boundary theory.

The boundary metric is not literally $g_{\mu\nu}(z=0,x)$ as an ordinary induced metric at a finite surface. Instead, the physical statement is conformal:

$$
g_{MN}^{\mathrm{bulk}}
\sim
\frac{L^2}{z^2}
\left(dz^2+g_{(0)\mu\nu}dx^\mu dx^\nu\right),
\qquad
z\to0.
$$

Only the conformal class of $g_{(0)\mu\nu}$ is fixed by the asymptotic AdS structure unless a representative is chosen.

## Curvature conventions

We define the Riemann tensor by

$$
[\nabla_M,\nabla_N]V^P
=
R^P{}_{QMN}V^Q.
$$

The Ricci tensor and scalar are

$$
R_{MN}=R^P{}_{MPN},
\qquad
R=g^{MN}R_{MN}.
$$

With these conventions, pure AdS$_{d+1}$ has

$$
R_{MNPQ}
=
-\frac{1}{L^2}
\left(
 g_{MP}g_{NQ}-g_{MQ}g_{NP}
\right),
$$

$$
R_{MN}
=
-\frac{d}{L^2}g_{MN},
\qquad
R
=
-\frac{d(d+1)}{L^2}.
$$

The cosmological constant in Einstein gravity is

$$
\Lambda
=
-\frac{d(d-1)}{2L^2}.
$$

For the Lorentzian Einstein-Hilbert action,

$$
S_{\mathrm{grav}}
=
\frac{1}{16\pi G_{d+1}}
\int_{\mathcal M} d^{d+1}x\sqrt{-g}\,(R-2\Lambda)
+\frac{1}{8\pi G_{d+1}}
\int_{\partial\mathcal M} d^d x\sqrt{|\gamma|}\,K
+S_{\mathrm{ct}},
$$

the equations of motion are

$$
R_{MN}-\frac12 Rg_{MN}+\Lambda g_{MN}=8\pi G_{d+1}T_{MN}.
$$

In vacuum, $T_{MN}=0$, pure AdS solves these equations.

### Boundary terms and outward normals

For a cutoff region

$$
\mathcal M_\epsilon=\{z\ge\epsilon\},
$$

the outward-pointing unit normal points toward smaller $z$, namely toward the conformal boundary. In pure Poincaré AdS,

$$
n_M dx^M=-\frac{L}{z}dz.
$$

We define the extrinsic curvature of the cutoff surface by

$$
K_{\mu\nu}
=
\gamma_\mu{}^M\gamma_\nu{}^N\nabla_M n_N,
\qquad
K=\gamma^{\mu\nu}K_{\mu\nu}.
$$

This sign convention is important for Brown–York stress tensors and holographic renormalization. If you compare with another reference and every Brown–York sign seems reversed, the first thing to check is the orientation of the normal vector.

## Euclidean actions and thermodynamics

The Euclidean path integral is written schematically as

$$
Z_E
=
\int \mathcal D\Phi\,e^{-S_E[\Phi]}.
$$

In the saddle-point approximation,

$$
Z_E\approx e^{-S_{E,\text{on-shell}}}.
$$

After holographic renormalization,

$$
Z_E\approx e^{-S_{E,\text{ren,on-shell}}}.
$$

For a thermal ensemble with inverse temperature

$$
\beta=\frac{1}{T},
$$

the Euclidean time circle has period $\beta$ for bosonic fields. The free energy is

$$
F=-T\log Z_E.
$$

At leading saddle level this gives

$$
F=T\,S_{E,\text{ren,on-shell}}
=\frac{1}{\beta}S_{E,\text{ren,on-shell}}.
$$

This formula is simple, but it hides a common pitfall: one must compare Euclidean actions with the same boundary data. When computing phase transitions such as Hawking–Page transitions, the thermal circles of the competing saddle geometries must be matched at the cutoff surface before the cutoff is removed.

## Sources, generating functionals, and signs

This course uses the connected generating functional

$$
W[J]=\log Z[J].
$$

For a Euclidean QFT, we write the source convention as

$$
Z_E[J]
=
\left\langle
\exp\!\left(
\int d^d x\sqrt{g_{(0)}}\,J(x)\mathcal O(x)
\right)
\right\rangle_E.
$$

Then

$$
\langle \mathcal O(x)\rangle_J
=
\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta W[J]}{\delta J(x)}.
$$

In the classical Euclidean gravity approximation,

$$
W[J]
=
-S_{E,\text{ren,on-shell}}[J].
$$

Therefore, with this convention,

$$
\langle \mathcal O(x)\rangle_J
=
-\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta S_{E,\text{ren,on-shell}}}{\delta J(x)}.
$$

Some references put the source term into the Euclidean action as $S_E+\int J\mathcal O$ and define $W=-\log Z$. Those choices move minus signs around. The invariant prescription is not the isolated sign in a memorized formula; it is the complete relation among the source convention, the definition of $W$, and the bulk on-shell action.

For Lorentzian signature, the corresponding schematic relation is

$$
Z_L[J]
=
\left\langle
\exp\!\left(
i\int d^d x\sqrt{|g_{(0)}|}\,J\mathcal O
\right)
\right\rangle
\approx
\exp\!\left(iS_{L,\text{ren,on-shell}}[J]\right).
$$

Real-time correlators require more than this schematic equation. To compute retarded functions, one must impose the correct causal prescription, especially at horizons.

## Fourier transforms

For Lorentzian real-time problems, our default Fourier convention is

$$
f(t,\vec x)
=
\int\frac{d\omega\,d^{d-1}k}{(2\pi)^d}
\,e^{-i\omega t+i\vec k\cdot\vec x}
\,f(\omega,\vec k).
$$

Thus

$$
\partial_t\to -i\omega,
\qquad
\partial_i\to ik_i.
$$

The inverse convention is

$$
f(\omega,\vec k)
=
\int dt\,d^{d-1}x\,
e^{i\omega t-i\vec k\cdot\vec x}
f(t,\vec x).
$$

For Euclidean problems,

$$
f(x_E)
=
\int\frac{d^d k_E}{(2\pi)^d}
\,e^{ik_E\cdot x_E}f(k_E),
$$

where

$$
k_E\cdot x_E=\omega_E\tau+\vec k\cdot\vec x.
$$

At finite temperature, bosonic Euclidean frequencies are

$$
\omega_n=2\pi nT,
\qquad
n\in\mathbb Z,
$$

while fermionic Euclidean frequencies are

$$
\omega_n=(2n+1)\pi T.
$$

The retarded Green's function convention used later is

$$
G_R(t,\vec x)
=
-i\theta(t)\left\langle
[\mathcal O(t,\vec x),\mathcal O(0,\vec 0)]
\right\rangle.
$$

With our Fourier convention, poles of $G_R(\omega,\vec k)$ in a stable thermal state lie in the lower half of the complex $\omega$ plane.

## Scalar fields and operator dimensions

For a bulk scalar field, the Lorentzian action convention is

$$
S_\phi
=
-\frac12
\int d^{d+1}x\sqrt{-g}
\left(
 g^{MN}\partial_M\phi\partial_N\phi
 +m^2\phi^2
\right).
$$

The equation of motion is

$$
(\nabla^2-m^2)\phi=0.
$$

Near the boundary of AdS$_{d+1}$, solutions behave as

$$
\phi(z,x)
\sim
z^{\Delta_-}\phi_{(0)}(x)
+
z^{\Delta_+}A(x),
$$

where

$$
\Delta_\pm
=
\frac d2\pm\nu,
\qquad
\nu=\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

In standard quantization,

$$
\Delta=\Delta_+,
\qquad
\Delta_-=d-\Delta.
$$

Equivalently,

$$
m^2L^2=\Delta(\Delta-d).
$$

The Breitenlohner–Freedman bound is

$$
m^2L^2\ge -\frac{d^2}{4}.
$$

When the mass lies in the window that permits alternate quantization, the identification of source and expectation value can change. That case is treated later; until then, “standard quantization” is the default.

## Gauge fields and currents

For a bulk Abelian gauge field, the default Lorentzian normalization is

$$
S_A
=
-\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\sqrt{-g}\,F_{MN}F^{MN},
\qquad
F_{MN}=\partial_M A_N-\partial_N A_M.
$$

The leading boundary value $A_{(0)\mu}$ sources a conserved current $J^\mu$:

$$
\int d^d x\sqrt{|g_{(0)}|}\,A_{(0)\mu}J^\mu.
$$

The radial electric flux is related to the expectation value of the current. The precise coefficient depends on the Maxwell normalization, counterterms, and the chosen radial coordinate. We will therefore keep $g_{d+1}^2$ explicit in current correlator computations.

At finite density, the chemical potential is not merely the value of $A_t$ at one point; it is a gauge-invariant potential difference. In a common black-brane gauge,

$$
\mu=A_t(z=0)-A_t(z_h),
$$

with regularity often imposing $A_t(z_h)=0$ at the horizon.

## Metric sources and stress tensors

The boundary metric $g_{(0)\mu\nu}$ sources the stress tensor:

$$
\delta W
=
\frac12
\int d^d x\sqrt{|g_{(0)}|}\,
\langle T^{\mu\nu}\rangle\delta g_{(0)\mu\nu}
+\cdots.
$$

Equivalently,

$$
\langle T^{\mu\nu}\rangle
=
\frac{2}{\sqrt{|g_{(0)}|}}
\frac{\delta W}{\delta g_{(0)\mu\nu}}.
$$

Because $W=-S_{E,\mathrm{ren}}$ in our Euclidean convention, the Euclidean stress tensor extracted from the on-shell action has the corresponding minus sign. In Lorentzian signature the relation is obtained from the Lorentzian generating functional. Later, when we compute the holographic stress tensor, we will derive the working formula rather than relying on memory.

## Normalizations and what $\sim$ means

AdS/CFT has two kinds of statements:

1. exact statements with fixed normalizations;
2. scaling statements that display dependence on $N$, $\lambda$, $L$, or $G_N$ while suppressing numerical constants.

This course uses $\sim$ for the second kind. For example,

$$
\frac{L^{d-1}}{G_{d+1}}\sim C_T
$$

means that the bulk Newton constant in AdS units controls the stress-tensor two-point coefficient of the boundary CFT. The exact coefficient depends on the dimension and on the normalization convention for $T_{\mu\nu}$.

Similarly,

$$
\frac{L^4}{\alpha'^2}\sim\lambda
$$

captures the fact that large 't Hooft coupling makes the AdS radius large in string units. In the canonical AdS$_5\times S^5$ example, a more precise relation is

$$
L^4=4\pi g_sN\alpha'^2,
$$

with a corresponding convention-dependent relation between $g_{\mathrm{YM}}^2$ and $g_s$.

Whenever an exact numerical coefficient matters physically, the relevant page will state it explicitly.

## Dictionary checkpoint

The conventions above support the following default translations:

| Boundary statement | Bulk statement |
|---|---|
| QFT lives in $d$ dimensions | bulk has dimension $d+1$ |
| UV limit of the QFT | near-boundary limit $z\to0$ |
| IR direction of the QFT | motion inward toward larger $z$ |
| boundary metric $g_{(0)\mu\nu}$ | conformal representative of the AdS boundary metric |
| source $J$ for $\mathcal O$ | leading boundary coefficient of bulk field $\phi$ |
| $W[J]=\log Z[J]$ | $-S_{E,\text{ren,on-shell}}[J]$ in Euclidean classical gravity |
| large number of degrees of freedom | large $L^{d-1}/G_{d+1}$ |
| thermal circle of length $\beta$ | smooth Euclidean black-hole or thermal-AdS saddle |

These are not new physical claims. They are the bookkeeping rules that allow the physical claims to be made unambiguously.

## Common confusions

### “The AdS boundary is at $z=0$, so the metric is singular there.”

The Poincaré metric has an infinite conformal factor near $z=0$:

$$
ds^2\sim \frac{L^2}{z^2}(dz^2+g_{(0)\mu\nu}dx^\mu dx^\nu).
$$

The boundary metric is obtained after stripping off this divergent conformal factor. The singularity is not a curvature singularity of AdS; it reflects that the boundary is at infinite proper distance.

### “The signs in one-point functions should be universal.”

They are not universal in isolation. A sign in

$$
\langle\mathcal O\rangle\propto \frac{\delta S_{\mathrm{ren}}}{\delta J}
$$

depends on whether one defines $W=\log Z$ or $W=-\log Z$, and whether the source appears as $+\int J\mathcal O$ in the exponent or $+\int J\mathcal O$ in the Euclidean action. The safe method is to start from the generating functional and derive the variation.

### “Setting $L=1$ means $L$ has disappeared physically.”

No. Setting $L=1$ is a choice of units. Dimensionless quantities such as $m^2L^2$, $TL$, and $G_{d+1}/L^{d-1}$ still remember the physical ratios.

### “The radial coordinate $r$ and the radial coordinate $z$ have the same UV direction.”

They do not. In Poincaré coordinates,

$$
z\to0
$$

is the boundary, while in the $r=L^2/z$ coordinate,

$$
r\to\infty
$$

is the boundary. Mixing these conventions is a reliable way to invert UV and IR statements by accident.

### “Euclidean correlators determine all Lorentzian correlators automatically.”

Euclidean correlators contain important analytic information, but Lorentzian real-time physics requires a causal prescription. In black-hole backgrounds, imposing incoming-wave boundary conditions at the horizon is essential for retarded correlators.

## Exercises

### Exercise 1: Boundary direction in $z$ and $r$

The Poincaré radial coordinates are related by

$$
r=\frac{L^2}{z}.
$$

If the AdS boundary is at $z\to0$, where is it in $r$ coordinates? What is the deep Poincaré interior in $r$ coordinates?

<details>
<summary><strong>Solution</strong></summary>

As $z\to0$,

$$
r=\frac{L^2}{z}\to\infty.
$$

Thus the AdS boundary is at $r\to\infty$. The deep Poincaré interior is $z\to\infty$, which corresponds to

$$
r\to0.
$$

This is why it is dangerous to say simply “large radius” without specifying the radial coordinate.

</details>

### Exercise 2: Dimension of a source

Let $\mathcal O$ be a scalar operator of dimension $\Delta$ in a $d$-dimensional CFT. The source coupling is

$$
\int d^d x\,J(x)\mathcal O(x).
$$

Using $[x]=-1$, find the mass dimension of $J$.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless. Since

$$
[d^d x]=-d,
\qquad
[\mathcal O]=\Delta,
$$

we require

$$
[J]+\Delta-d=0.
$$

Therefore

$$
[J]=d-\Delta.
$$

This matches the standard near-boundary scalar behavior, where the source coefficient multiplies $z^{d-\Delta}$.

</details>

### Exercise 3: Curvature of AdS

Using the convention stated above, pure AdS$_{d+1}$ satisfies

$$
R_{MN}=-\frac{d}{L^2}g_{MN}.
$$

Compute the Ricci scalar $R$.

<details>
<summary><strong>Solution</strong></summary>

Contract with $g^{MN}$:

$$
R=g^{MN}R_{MN}
=-\frac{d}{L^2}g^{MN}g_{MN}.
$$

In $d+1$ bulk dimensions,

$$
g^{MN}g_{MN}=d+1.
$$

Therefore

$$
R=-\frac{d(d+1)}{L^2}.
$$

</details>

### Exercise 4: Euclidean source sign

Suppose

$$
Z_E[J]
=
\left\langle
\exp\!\left(\int J\mathcal O\right)
\right\rangle_E,
\qquad
W[J]=\log Z_E[J].
$$

In classical Euclidean holography,

$$
W[J]=-S_{E,\mathrm{ren}}[J].
$$

What is $\langle\mathcal O\rangle_J$ in terms of $S_{E,\mathrm{ren}}$?

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\langle\mathcal O(x)\rangle_J
=
\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta W[J]}{\delta J(x)}.
$$

Since $W[J]=-S_{E,\mathrm{ren}}[J]$,

$$
\langle\mathcal O(x)\rangle_J
=
-\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta S_{E,\mathrm{ren}}}{\delta J(x)}.
$$

The minus sign is not a universal truth about holography; it follows from the source and $W$ conventions chosen in the question.

</details>

## Further reading

For the original correlation-function dictionary, see Gubser, Klebanov, and Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109), and Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150). For a broad review of conventions and parameter regimes in the original AdS/CFT correspondence, see Aharony, Gubser, Maldacena, Ooguri, and Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111). For the systematic treatment of cutoff surfaces, near-boundary expansions, counterterms, and renormalized one-point functions, see Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
