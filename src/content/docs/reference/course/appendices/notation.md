---
title: "Notation"
description: "Course-wide notation for AdS/CFT Foundations: dimensions, indices, signatures, sources, correlators, large N, thermodynamics, entanglement, and geometry."
sidebar:
  order: 10
---

This appendix fixes the notation used throughout **AdS/CFT Foundations**. It is not meant to declare the only good convention in the literature. It is a translation layer: when you compare these notes with papers, this page tells you what symbols mean here and where sign or normalization choices can differ.

The most important convention is the dimension convention:

$$
\text{boundary dimension}=d,
\qquad
\text{bulk dimension}=d+1.
$$

Thus $\mathrm{AdS}_{d+1}$ is dual to a $d$-dimensional CFT. In the canonical example,

$$
\mathrm{AdS}_5 \times S^5
\quad \longleftrightarrow \quad
\mathcal N=4\; SU(N)\; \text{SYM in }d=4.
$$

## Index conventions

Bulk indices are usually uppercase Latin letters,

$$
M,N,P,Q=0,1,\ldots,d,
$$

or lowercase Latin letters from the beginning of the alphabet,

$$
a,b,c,d=0,1,\ldots,d.
$$

Boundary indices are lowercase Latin letters from the middle of the alphabet,

$$
i,j,k,l=0,1,\ldots,d-1.
$$

Spatial boundary indices are often Greek or lowercase Latin with arrows suppressed,

$$
\vec x=(x^1,\ldots,x^{d-1}),
\qquad
\mathbf k=(k_1,\ldots,k_{d-1}).
$$

When no confusion is possible, the course uses $x$ for all boundary coordinates and $z$ or $r$ for the AdS radial coordinate.

| Object | Course notation | Comment |
|---|---:|---|
| bulk metric | $g_{MN}$ | dynamical gravitational field |
| induced cutoff metric | $\gamma_{ij}$ | metric on $z=\epsilon$ or $r=r_c$ |
| boundary source metric | $g_{(0)ij}$ | CFT background metric |
| boundary flat metric | $\eta_{ij}$ | Lorentzian, mostly plus |
| Euclidean flat metric | $\delta_{ij}$ | positive definite |
| AdS radius | $L$ | sometimes set to $1$ only locally |
| bulk Newton constant | $G_{d+1}$ | after reduction on compact spaces |
| string length squared | $\alpha'$ | $\ell_s^2=\alpha'$ |
| string coupling | $g_s$ | controls string loops |
| 't Hooft coupling | $\lambda$ | $\lambda=g_{\mathrm{YM}}^2N$ |

## Signature conventions

Lorentzian boundary signature is mostly plus:

$$
\eta_{ij}dx^i dx^j=-dt^2+d\vec x^{\,2}.
$$

A common Lorentzian Poincaré-AdS metric is

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2 - dt^2 + d\vec x^{\,2}
\right),
\qquad
z>0.
$$

The Euclidean version is

$$
ds_E^2
=
\frac{L^2}{z^2}
\left(
 dz^2 + d\tau^2 + d\vec x^{\,2}
\right).
$$

The boundary is at $z=0$. The deep Poincaré interior is $z\to\infty$. Some pages use a radial coordinate $r=L^2/z$, in which the boundary is at $r\to\infty$.

## Curvature conventions

The course uses

$$
[\nabla_M,\nabla_N]V^P
=
R^P{}_{QMN}V^Q,
$$

with Ricci tensor and scalar curvature

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
R_{MN}=-\frac{d}{L^2}g_{MN},
\qquad
R=-\frac{d(d+1)}{L^2}.
$$

The cosmological constant in Einstein gravity is

$$
\Lambda=-\frac{d(d-1)}{2L^2},
$$

so that the vacuum Einstein equation reads

$$
R_{MN}-\frac12 Rg_{MN}+\Lambda g_{MN}=0.
$$

## AdS coordinate systems

The Poincaré metric is

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\eta_{ij}dx^i dx^j\right).
$$

The global AdS metric is

$$
ds^2
=
-L^2\cosh^2\rho\,dt^2
+L^2d\rho^2
+L^2\sinh^2\rho\,d\Omega_{d-1}^2.
$$

A frequently used equivalent form is

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+\frac{dr^2}{1+r^2/L^2}
+r^2d\Omega_{d-1}^2.
$$

Fefferman–Graham gauge is usually written as

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+g_{ij}(z,x)dx^i dx^j
\right),
$$

with near-boundary expansion

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)+z^2g_{(2)ij}(x)+\cdots+z^dg_{(d)ij}(x)+\cdots .
$$

The coefficient $g_{(0)ij}$ is the source metric for the CFT stress tensor. The coefficient $g_{(d)ij}$ contains state-dependent data related to $\langle T_{ij}\rangle$, after local terms and anomalies are included.

## Cutoff surfaces and outward normals

A radial cutoff surface is denoted

$$
\Sigma_\epsilon: z=\epsilon.
$$

The induced metric on $\Sigma_\epsilon$ is

$$
\gamma_{ij}(\epsilon,x)
=
\frac{L^2}{\epsilon^2}g_{ij}(\epsilon,x).
$$

For the region $z\ge \epsilon$, the outward-pointing unit normal points toward smaller $z$:

$$
n^M\partial_M=-\frac{z}{L}\partial_z.
$$

The extrinsic curvature convention used in this course is

$$
K_{ij}
=
\gamma_i{}^M\gamma_j{}^N\nabla_M n_N
=
\frac12\mathcal L_n\gamma_{ij}.
$$

For pure AdS in Poincaré coordinates this gives

$$
K_{ij}=\frac1L\gamma_{ij}.
$$

Some references choose the opposite normal or define $K_{ij}$ with an extra minus sign. When comparing Brown–York tensors or Gibbons–Hawking–York terms, this is the first sign to check.

## Actions and path integrals

The Lorentzian bulk gravitational action is written schematically as

$$
S_L
=
\frac{1}{16\pi G_{d+1}}
\int_M d^{d+1}x\sqrt{-g}\,(R-2\Lambda)
+
\frac{1}{8\pi G_{d+1}}
\int_{\partial M}d^dx\sqrt{|\gamma|}\,K
+S_{\mathrm{matter}}+S_{\mathrm{ct}}.
$$

The Euclidean saddle approximation is

$$
Z_E[J]\approx e^{-S_{E,\mathrm{ren}}[J]}.
$$

Therefore

$$
W_E[J]\equiv \log Z_E[J]
\approx
-S_{E,\mathrm{ren}}[J].
$$

Whenever signs matter, the page should specify whether it is using Euclidean or Lorentzian conventions. A safe rule is:

$$
\langle \mathcal O\rangle_E
=
\frac{1}{\sqrt{g_{(0)}}}\frac{\delta W_E}{\delta J}
=
-\frac{1}{\sqrt{g_{(0)}}}\frac{\delta S_{E,\mathrm{ren}}}{\delta J},
$$

while in Lorentzian signature, with $Z_L\sim e^{iS_L}$,

$$
\langle \mathcal O\rangle_L
=
\frac{1}{\sqrt{-g_{(0)}}}\frac{\delta S_{L,\mathrm{ren}}}{\delta J}.
$$

Many holography papers absorb these sign choices into the definition of the renormalized canonical momentum. Do not compare one-point functions across references without checking the path-integral convention.

## Sources and operators

A source $J$ for a scalar operator $\mathcal O$ deforms the boundary action as

$$
S_{\mathrm{CFT}}
\longrightarrow
S_{\mathrm{CFT}}
+
\int d^dx\sqrt{|g_{(0)}|}\,J\mathcal O.
$$

If $\mathcal O$ has scaling dimension $\Delta$, then the source has dimension

$$
[J]=d-\Delta.
$$

For a bulk scalar of mass $m$,

$$
m^2L^2=\Delta(\Delta-d),
$$

and near the boundary

$$
\phi(z,x)
=
z^{d-\Delta}\left(\phi_{(0)}(x)+\cdots\right)
+
z^\Delta\left(\phi_{(2\Delta-d)}(x)+\cdots\right).
$$

In standard quantization, $\phi_{(0)}$ is the source and $\phi_{(2\Delta-d)}$ is related to the vev. In alternate quantization, when allowed, the roles are exchanged after the appropriate Legendre transform.

The most common field/operator pairs are:

| Bulk object | Boundary object | Source |
|---|---|---|
| scalar $\phi$ | scalar operator $\mathcal O$ | leading scalar boundary value |
| gauge field $A_M$ | conserved current $J^i$ | boundary gauge field $A_{(0)i}$ |
| metric $g_{MN}$ | stress tensor $T^{ij}$ | boundary metric $g_{(0)ij}$ |
| spinor $\psi$ | fermionic operator $\mathcal O_\psi$ | leading spinor component |
| string worldsheet | Wilson loop $W[C]$ | boundary contour $C$ |
| extremal surface | entanglement entropy | boundary region $A$ |

## Generating functionals and correlators

The Euclidean generating functional is

$$
Z[J]
=
\left\langle
\exp\left(
\int d^dx\sqrt{g_{(0)}}\,J(x)\mathcal O(x)
\right)
\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Connected correlators are obtained from $W[J]$:

$$
\langle \mathcal O(x_1)\cdots\mathcal O(x_n)\rangle_c
=
\frac{1}{\sqrt{g_{(0)}(x_1)}\cdots\sqrt{g_{(0)}(x_n)}}
\frac{\delta^n W}{\delta J(x_1)\cdots\delta J(x_n)}\bigg|_{J=0}.
$$

For Lorentzian response,

$$
G_R(t,\vec x)
=
-i\theta(t)\langle[\mathcal O(t,\vec x),\mathcal O(0)]\rangle.
$$

The spectral density convention is

$$
\rho(\omega,\mathbf k)
=
-2\,\mathrm{Im}\,G_R(\omega,\mathbf k).
$$

For a conserved current, conductivity is usually written as

$$
\sigma(\omega)
=
\frac{1}{i\omega}G^R_{J_xJ_x}(\omega,\mathbf k=0),
$$

up to diamagnetic/contact terms depending on the theory.

## Fourier transform convention

The default convention is

$$
f(x)
=
\int\frac{d^dk}{(2\pi)^d}\,e^{ik\cdot x}f(k),
\qquad
f(k)=\int d^dx\,e^{-ik\cdot x}f(x).
$$

In Lorentzian signature,

$$
k\cdot x=-\omega t+\mathbf k\cdot\mathbf x.
$$

Thus

$$
e^{ik\cdot x}=e^{-i\omega t+i\mathbf k\cdot\mathbf x}.
$$

Thermal Euclidean frequencies are

$$
\omega_n=2\pi nT
\quad\text{for bosons},
\qquad
\omega_n=(2n+1)\pi T
\quad\text{for fermions}.
$$

Retarded correlators are obtained by analytic continuation with the correct causal prescription, not merely by replacing $\omega_n$ with $-i\omega$ in an arbitrary expression.

## Large $N$ and coupling conventions

For gauge group $SU(N)$,

$$
\lambda=g_{\mathrm{YM}}^2N.
$$

In the canonical AdS$_5$/CFT$_4$ example,

$$
\frac{L^4}{\alpha'^2}=\lambda,
\qquad
4\pi g_s=g_{\mathrm{YM}}^2,
\qquad
g_s=\frac{\lambda}{4\pi N}.
$$

The useful hierarchy is:

| Boundary limit | Bulk meaning |
|---|---|
| $N\to\infty$ | suppresses bulk loops |
| $\lambda\to\infty$ | suppresses string-scale corrections |
| finite $N$ | quantum gravity corrections |
| finite $\lambda$ | stringy/$\alpha'$ corrections |
| large gap $\Delta_{\mathrm{gap}}$ | local bulk EFT below the gap |

Normalized single-trace operators are usually chosen so that

$$
\langle \mathcal O\mathcal O\rangle\sim N^0,
\qquad
\langle \mathcal O\mathcal O\mathcal O\rangle_c\sim \frac1N,
\qquad
\langle \mathcal O^n\rangle_c\sim N^{2-n}.
$$

Unnormalized single-trace operators have different powers of $N$. When reading papers, always check which normalization is being used.

## Thermodynamic notation

The thermal density matrix is

$$
\rho=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
\beta=\frac1T.
$$

With chemical potential,

$$
Z(\beta,\mu)
=
\mathrm{Tr}\,e^{-\beta(H-\mu Q)}.
$$

The Euclidean free energy is

$$
F=-T\log Z,
\qquad
I_E=\beta F
$$

at a dominant saddle. For an AdS black hole or brane,

$$
S=\frac{\mathrm{Area}_{\mathrm{horizon}}}{4G_{d+1}}.
$$

The planar black-brane horizon is usually at $z=z_h$, and the temperature is

$$
T=\frac{d}{4\pi z_h}
$$

for the standard neutral AdS$_{d+1}$ black brane.

## Entanglement notation

For a boundary spatial region $A$, the reduced density matrix is

$$
\rho_A=\mathrm{Tr}_{\bar A}\rho.
$$

The von Neumann entropy is

$$
S_A=-\mathrm{Tr}\,\rho_A\log\rho_A.
$$

The classical Ryu–Takayanagi/HRT formula is written as

$$
S_A=\frac{\mathrm{Area}(X_A)}{4G_N},
$$

where $X_A$ is a codimension-two minimal or extremal bulk surface homologous to $A$.

The quantum-extremal-surface formula is

$$
S_A
=
\underset{X_A}{\mathrm{ext}}\left[
\frac{\mathrm{Area}(X_A)}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_A)
\right].
$$

The entanglement wedge of $A$ is denoted $\mathcal W_E[A]$.

## Common normalization landmines

### $U(N)$ versus $SU(N)$

The D3-brane open-string theory naturally gives $U(N)$, but the center-of-mass $U(1)$ decouples in the infrared. The interacting CFT is usually described as $SU(N)$ $\mathcal N=4$ SYM.

### $4\pi$ factors

Some references use

$$
g_{\mathrm{YM}}^2=4\pi g_s,
$$

while others absorb $4\pi$ into the gauge-coupling convention. The parametric statement $L^4/\alpha'^2\sim \lambda$ is robust, but exact numerical factors require a fixed convention.

### Euclidean signs

Because $Z_E\sim e^{-S_E}$, Euclidean one-point functions often carry a minus sign relative to direct variations of $S_E$. Lorentzian expressions are cleaner for response functions, but require causal boundary conditions.

### Stress-tensor normalization

The stress tensor is defined by variation with respect to the boundary metric. Depending on whether one varies $g_{ij}$ or $g^{ij}$, one writes

$$
\delta W
=
\frac12\int d^dx\sqrt{|g|}\,\langle T^{ij}\rangle\delta g_{ij}
$$

or

$$
\delta W
=-\frac12\int d^dx\sqrt{|g|}\,\langle T_{ij}\rangle\delta g^{ij}.
$$

These are the same definition expressed with inverse variables.

## Minimal symbol dictionary

| Symbol | Meaning |
|---|---|
| $d$ | boundary spacetime dimension |
| $L$ | AdS radius |
| $z$ | Poincaré radial coordinate, boundary at $z=0$ |
| $r$ | alternative radial coordinate, often boundary at $r\to\infty$ |
| $G_{d+1}$ | Newton constant in the noncompact AdS spacetime |
| $g_{(0)ij}$ | boundary metric source |
| $\gamma_{ij}$ | induced metric on a finite cutoff surface |
| $K_{ij}$ | extrinsic curvature of a cutoff/boundary hypersurface |
| $\Delta$ | scaling dimension of a boundary operator |
| $m$ | mass of the dual bulk field |
| $\phi_{(0)}$ | leading scalar source in standard quantization |
| $\langle\mathcal O\rangle$ | renormalized one-point function |
| $W[J]$ | connected generating functional |
| $G_R$ | retarded Green function |
| $\lambda$ | 't Hooft coupling $g_{\mathrm{YM}}^2N$ |
| $\alpha'$ | string length squared |
| $g_s$ | string coupling |
| $X_A$ | RT/HRT/QES surface anchored to $\partial A$ |

## Quick consistency checks

### Check 1: dimensions of a source

If $\mathcal O$ has dimension $\Delta$, then $J$ has dimension $d-\Delta$ because the deformation

$$
\int d^dx\,J\mathcal O
$$

must be dimensionless.

### Check 2: the scalar falloff

If

$$
\phi\sim z^\alpha,
$$

then the leading near-boundary scalar equation in Poincaré AdS gives

$$
\alpha(\alpha-d)=m^2L^2.
$$

Thus

$$
\alpha=d-\Delta
\quad\text{or}\quad
\alpha=\Delta.
$$

### Check 3: the AdS curvature scale

All curvature invariants in pure AdS are set by $L$. For example,

$$
R=-\frac{d(d+1)}{L^2}.
$$

Therefore higher-derivative corrections are suppressed only when the string length is small compared with $L$.

## Further reading

- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- M. Henningson and K. Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).
- S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- J. D. Brown and J. W. York, [Quasilocal Energy and Conserved Charges Derived from the Gravitational Action](https://arxiv.org/abs/gr-qc/9209012).
