---
title: "Differential Geometry Cheatsheet"
description: "A compact reference for curvature conventions, hypersurfaces, extrinsic curvature, Brown-York tensors, differential forms, and Fefferman-Graham geometry used in AdS/CFT."
sidebar:
  order: 20
---

This appendix collects the differential-geometry formulas used repeatedly in the course. It is a working reference, not a replacement for a general relativity textbook. The emphasis is on the conventions needed for AdS geometry, holographic renormalization, Brown–York stress tensors, and extremal surfaces.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A bulk region with a cutoff hypersurface, outward unit normal, induced metric, and extrinsic curvature.](/figures/course/differential-geometry-boundary-data.svg)

<figcaption>

Boundary data for a hypersurface $\Sigma$ embedded in a bulk spacetime $M$: unit normal $n^a$, induced metric $\gamma_{ab}=g_{ab}-\sigma n_an_b$, and extrinsic curvature $K_{ab}=\gamma_a{}^c\gamma_b{}^d\nabla_c n_d$.

</figcaption>
</figure>

## Metric and index basics

The metric $g_{ab}$ lowers indices and its inverse $g^{ab}$ raises them:

$$
V_a=g_{ab}V^b,
\qquad
V^a=g^{ab}V_b,
\qquad
g^{ac}g_{cb}=\delta^a{}_b.
$$

The invariant volume element is

$$
d^{D}x\sqrt{|g|},
\qquad
D=d+1.
$$

For Lorentzian metrics with mostly-plus signature, $g<0$, so $\sqrt{|g|}=\sqrt{-g}$. For Euclidean metrics, $g>0$, so $\sqrt{|g|}=\sqrt{g}$.

Useful variations are

$$
\delta\sqrt{|g|}
=\frac12\sqrt{|g|}\,g^{ab}\delta g_{ab}
=-\frac12\sqrt{|g|}\,g_{ab}\delta g^{ab},
$$

and

$$
\delta g^{ab}=-g^{ac}g^{bd}\delta g_{cd}.
$$

## Levi-Civita connection

The Levi-Civita connection is torsion-free and metric-compatible:

$$
\nabla_ag_{bc}=0,
\qquad
\Gamma^a{}_{bc}=\Gamma^a{}_{cb}.
$$

In coordinates,

$$
\Gamma^a{}_{bc}
=
\frac12g^{ad}
\left(
\partial_bg_{cd}
+\partial_cg_{bd}
-\partial_dg_{bc}
\right).
$$

For a scalar,

$$
\nabla_a\phi=\partial_a\phi.
$$

For a vector,

$$
\nabla_aV^b=\partial_aV^b+\Gamma^b{}_{ac}V^c.
$$

For a covector,

$$
\nabla_a\omega_b=\partial_a\omega_b-\Gamma^c{}_{ab}\omega_c.
$$

The scalar Laplacian is

$$
\nabla^2\phi
=
\frac{1}{\sqrt{|g|}}\partial_a
\left(
\sqrt{|g|}g^{ab}\partial_b\phi
\right).
$$

In Poincaré AdS$_{d+1}$,

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+\eta_{ij}dx^idx^j\right),
$$

this becomes

$$
\nabla^2\phi
=
\frac{z^2}{L^2}
\left(
\partial_z^2\phi
-\frac{d-1}{z}\partial_z\phi
+\Box_{\partial}\phi
\right),
$$

where $\Box_{\partial}=\eta^{ij}\partial_i\partial_j$ in Lorentzian signature.

## Curvature conventions

The course uses

$$
[\nabla_a,\nabla_b]V^c
=
R^c{}_{dab}V^d.
$$

In coordinates,

$$
R^a{}_{bcd}
=
\partial_c\Gamma^a{}_{db}
-\partial_d\Gamma^a{}_{cb}
+\Gamma^a{}_{ce}\Gamma^e{}_{db}
-\Gamma^a{}_{de}\Gamma^e{}_{cb}.
$$

The Ricci tensor and scalar are

$$
R_{ab}=R^c{}_{acb},
\qquad
R=g^{ab}R_{ab}.
$$

The Einstein tensor is

$$
G_{ab}=R_{ab}-\frac12Rg_{ab}.
$$

The vacuum Einstein equation with cosmological constant is

$$
G_{ab}+\Lambda g_{ab}=0.
$$

For AdS$_{d+1}$,

$$
R_{abcd}
=
-\frac{1}{L^2}
\left(g_{ac}g_{bd}-g_{ad}g_{bc}\right),
$$

so

$$
R_{ab}=-\frac{d}{L^2}g_{ab},
\qquad
R=-\frac{d(d+1)}{L^2},
\qquad
\Lambda=-\frac{d(d-1)}{2L^2}.
$$

## Maximally symmetric spaces

A $D$-dimensional maximally symmetric space has curvature

$$
R_{abcd}
=\frac{R}{D(D-1)}
\left(g_{ac}g_{bd}-g_{ad}g_{bc}\right).
$$

For a sphere of radius $L$,

$$
R_{ab}=\frac{D-1}{L^2}g_{ab},
\qquad
R=\frac{D(D-1)}{L^2}.
$$

For AdS$_D$,

$$
R_{ab}=-\frac{D-1}{L^2}g_{ab},
\qquad
R=-\frac{D(D-1)}{L^2}.
$$

This sign is one of the easiest ways to catch curvature-convention mistakes.

## Hypersurfaces and induced metric

Let $\Sigma$ be a hypersurface with unit normal $n^a$. Define

$$
\sigma=n^an_a,
$$

so $\sigma=+1$ for a spacelike normal and $\sigma=-1$ for a timelike normal.

The induced metric is

$$
\gamma_{ab}=g_{ab}-\sigma n_an_b.
$$

It obeys

$$
\gamma_{ab}n^b=0.
$$

The corresponding projector is

$$
\gamma^a{}_b=\delta^a{}_b-\sigma n^a n_b.
$$

For tensors intrinsic to $\Sigma$, the induced covariant derivative is

$$
D_aT^{b\cdots}{}_{c\cdots}
=
\gamma_a{}^{a'}\gamma^b{}_{b'}\cdots\gamma_c{}^{c'}\cdots
\nabla_{a'}T^{b'\cdots}{}_{c'\cdots}.
$$

## Extrinsic curvature

The extrinsic curvature is

$$
K_{ab}
=
\gamma_a{}^c\gamma_b{}^d\nabla_c n_d.
$$

For hypersurface-orthogonal $n^a$,

$$
K_{ab}=\frac12\mathcal L_n\gamma_{ab}.
$$

The trace is

$$
K=\gamma^{ab}K_{ab}.
$$

For a radial foliation with vanishing shift,

$$
ds^2=N(r,x)^2dr^2+\gamma_{ij}(r,x)dx^idx^j,
$$

and normal along increasing $r$,

$$
K_{ij}=\frac{1}{2N}\partial_r\gamma_{ij}.
$$

If the outward normal points toward decreasing $r$, the sign flips.

### Poincaré-AdS cutoff surface

For

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+g_{ij}(z,x)dx^idx^j\right),
$$

the induced metric on $z=\epsilon$ is

$$
\gamma_{ij}=\frac{L^2}{\epsilon^2}g_{ij}(\epsilon,x).
$$

For the regulated region $z\ge \epsilon$, the outward unit normal is

$$
n=-\frac{z}{L}\partial_z.
$$

Therefore

$$
K_{ij}
=-\frac{z}{2L}\partial_z\gamma_{ij}.
$$

For pure AdS, $g_{ij}=\eta_{ij}$ and hence

$$
K_{ij}=\frac1L\gamma_{ij},
\qquad
K=\frac dL.
$$

## Gauss–Codazzi equations

Intrinsic curvature on $\Sigma$ is related to bulk curvature by the Gauss equation:

$$
\mathcal R_{abcd}
=
\gamma_a{}^e\gamma_b{}^f\gamma_c{}^g\gamma_d{}^hR_{efgh}
+
\sigma\left(K_{ac}K_{bd}-K_{ad}K_{bc}\right).
$$

The Codazzi equation is

$$
D_aK^a{}_b-D_bK
=
\gamma_b{}^cR_{cd}n^d.
$$

These equations are the geometric origin of many radial constraint equations in holography. In particular, the momentum constraint becomes the boundary stress-tensor conservation Ward identity.

## Gibbons–Hawking–York term

The Einstein–Hilbert action contains second derivatives of the metric. With Dirichlet boundary conditions for the induced metric, the correct variational principle requires the Gibbons–Hawking–York term:

$$
S_{\mathrm{GHY}}
=
\frac{1}{8\pi G}\int_{\partial M}d^dx\sqrt{|\gamma|}\,K,
$$

for the sign conventions used in this course. If a reference uses the opposite normal or opposite definition of $K_{ij}$, the displayed sign changes accordingly.

The regulated gravitational action is schematically

$$
S_{\mathrm{reg}}
=
\frac{1}{16\pi G}\int_{M_\epsilon}d^{d+1}x\sqrt{|g|}\,(R-2\Lambda)
+
\frac{1}{8\pi G}\int_{\Sigma_\epsilon}d^dx\sqrt{|\gamma|}\,K.
$$

Holographic renormalization adds local counterterms:

$$
S_{\mathrm{ren}}
=
\lim_{\epsilon\to0}
\left(S_{\mathrm{reg}}+S_{\mathrm{ct}}\right).
$$

## Brown–York tensor

The unrenormalized Brown–York tensor is the response to the induced metric:

$$
T^{ij}_{\mathrm{BY}}
=
\frac{2}{\sqrt{|\gamma|}}\frac{\delta S_{\mathrm{reg}}}{\delta\gamma_{ij}}.
$$

With the conventions above, its gravitational part is

$$
T^{ij}_{\mathrm{BY}}
=
\frac{1}{8\pi G}\left(K^{ij}-K\gamma^{ij}\right),
$$

before counterterms. The renormalized holographic stress tensor is obtained from

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{|g_{(0)}|}}\frac{\delta S_{\mathrm{ren}}}{\delta g_{(0)ij}},
$$

with Euclidean/Lorentzian signs handled as in the notation appendix.

For asymptotically AdS spacetimes, the raw Brown–York tensor diverges as the cutoff is removed. Counterterms are not optional; they are required to obtain finite CFT observables.

## Fefferman–Graham expansion

Fefferman–Graham gauge writes the metric as

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+g_{ij}(z,x)dx^idx^j\right).
$$

The near-boundary expansion has the structure

$$
g_{ij}(z,x)
=
g_{(0)ij}
+z^2g_{(2)ij}
+\cdots
+z^d\left(g_{(d)ij}+h_{(d)ij}\log z^2\right)
+\cdots .
$$

The logarithmic term appears in even boundary dimension $d$ and is tied to the Weyl anomaly.

For pure Einstein gravity, the lower coefficients are locally determined by $g_{(0)ij}$. For example, when $d>2$,

$$
g_{(2)ij}
=-\frac{L^2}{d-2}
\left(
R_{ij}[g_{(0)}]
-\frac{1}{2(d-1)}R[g_{(0)}]g_{(0)ij}
\right),
$$

up to the convention in which $L$ is absorbed into the definition of $z$. The coefficient $g_{(d)ij}$ contains nonlocal state data and determines $\langle T_{ij}\rangle$ after local terms are included.

## Scalar near-boundary equation

For a scalar field,

$$
(\nabla^2-m^2)\phi=0.
$$

Near the boundary, take $\phi\sim z^\alpha$. Using the AdS Laplacian gives

$$
\alpha(\alpha-d)=m^2L^2.
$$

Thus

$$
\alpha=\Delta
\quad\text{or}\quad
\alpha=d-\Delta,
$$

where

$$
\Delta(\Delta-d)=m^2L^2.
$$

This is the geometric core of the scalar mass-dimension relation.

## Differential forms

A $p$-form is

$$
\omega=\frac1{p!}\omega_{a_1\cdots a_p}dx^{a_1}\wedge\cdots\wedge dx^{a_p}.
$$

The exterior derivative is

$$
d\omega
=
\frac1{p!}\partial_b\omega_{a_1\cdots a_p}
 dx^b\wedge dx^{a_1}\wedge\cdots\wedge dx^{a_p}.
$$

For a gauge field,

$$
F=dA,
\qquad
F_{ab}=\partial_aA_b-\partial_bA_a.
$$

The Maxwell action can be written as

$$
S_{\mathrm{Maxwell}}
=-\frac{1}{4g_F^2}\int d^{d+1}x\sqrt{-g}\,F_{ab}F^{ab}
=-\frac{1}{2g_F^2}\int F\wedge *F.
$$

The Maxwell equation is

$$
\nabla_aF^{ab}=0
$$

or, in form language,

$$
d*F=0.
$$

The Bianchi identity is

$$
dF=0.
$$

## Extremal surfaces

For a codimension-two surface $X$ with induced metric $h_{\alpha\beta}$, the area functional is

$$
\mathrm{Area}(X)
=
\int_X d^{d-1}\sigma\sqrt{h}.
$$

A minimal surface extremizes this functional on a static time slice. A covariant HRT surface extremizes the spacetime area functional and has vanishing trace of the extrinsic curvature vector:

$$
K^a=0.
$$

For quantum extremal surfaces, the extremized functional is the generalized entropy,

$$
S_{\mathrm{gen}}[X]
=
\frac{\mathrm{Area}(X)}{4G_N}+S_{\mathrm{bulk}}(\Sigma_X).
$$

## Useful variational identities

The connection variation is

$$
\delta\Gamma^a{}_{bc}
=
\frac12g^{ad}
\left(
\nabla_b\delta g_{cd}
+\nabla_c\delta g_{bd}
-\nabla_d\delta g_{bc}
\right).
$$

The Ricci variation is

$$
\delta R_{ab}
=
\nabla_c\delta\Gamma^c{}_{ab}
-\nabla_b\delta\Gamma^c{}_{ac}.
$$

The Einstein–Hilbert variation has the schematic form

$$
\delta\left(\sqrt{|g|}R\right)
=
\sqrt{|g|}\,G_{ab}\delta g^{ab}
+\text{boundary term}.
$$

The Gibbons–Hawking–York term cancels the part of the boundary term involving normal derivatives of $\delta\gamma_{ij}$.

## Common traps

### Trap 1: changing the normal changes $K_{ij}$

If $n^a\to -n^a$, then

$$
K_{ij}\to -K_{ij}.
$$

This changes the displayed sign of the Brown–York tensor and the Gibbons–Hawking–York term. Physical answers agree only after all conventions are changed consistently.

### Trap 2: $\gamma_{ij}$ is not $g_{(0)ij}$

The cutoff induced metric diverges as

$$
\gamma_{ij}\sim \frac{L^2}{\epsilon^2}g_{(0)ij}.
$$

The CFT source metric is the finite conformal representative $g_{(0)ij}$, not the raw induced metric $\gamma_{ij}$.

### Trap 3: intrinsic and extrinsic curvature are different

The intrinsic curvature $\mathcal R_{ijkl}[\gamma]$ is built from the induced metric on the hypersurface. The extrinsic curvature $K_{ij}$ measures how the hypersurface is embedded in the bulk. Holographic counterterms use intrinsic curvature of $\gamma_{ij}$, while Brown–York momenta use extrinsic curvature.

### Trap 4: Euclidean and Lorentzian signs are not cosmetic

The Euclidean action computes $e^{-I_E}$; the Lorentzian action computes $e^{iS_L}$. One-point functions and canonical momenta can differ by signs or factors of $i$ if translated carelessly.

## Exercises

### Exercise 1: extrinsic curvature of the Poincaré cutoff

For pure Euclidean AdS,

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+\delta_{ij}dx^idx^j\right),
$$

show that the cutoff surface $z=\epsilon$ has

$$
K_{ij}=\frac1L\gamma_{ij}
$$

when the regulated region is $z\ge\epsilon$.

<details>
<summary><strong>Solution</strong></summary>

The induced metric is

$$
\gamma_{ij}=\frac{L^2}{z^2}\delta_{ij}.
$$

For the region $z\ge\epsilon$, the outward normal points toward smaller $z$:

$$
n=-\frac{z}{L}\partial_z.
$$

Using

$$
K_{ij}=\frac12\mathcal L_n\gamma_{ij},
$$

we get

$$
K_{ij}
=\frac12\left(-\frac{z}{L}\right)\partial_z
\left(\frac{L^2}{z^2}\delta_{ij}\right)
=\frac12\left(-\frac{z}{L}\right)
\left(-\frac{2L^2}{z^3}\delta_{ij}\right)
=\frac{L}{z^2}\delta_{ij}.
$$

Since

$$
\gamma_{ij}=\frac{L^2}{z^2}\delta_{ij},
$$

this is

$$
K_{ij}=\frac1L\gamma_{ij}.
$$

</details>

### Exercise 2: scalar indicial equation

Starting from

$$
\nabla^2\phi
=
\frac{z^2}{L^2}
\left(
\partial_z^2\phi
-\frac{d-1}{z}\partial_z\phi
+\Box_{\partial}\phi
\right),
$$

ignore boundary derivatives near $z=0$ and set $\phi=z^\alpha$. Derive

$$
\alpha(\alpha-d)=m^2L^2.
$$

<details>
<summary><strong>Solution</strong></summary>

For $\phi=z^\alpha$,

$$
\partial_z\phi=\alpha z^{\alpha-1},
\qquad
\partial_z^2\phi=\alpha(\alpha-1)z^{\alpha-2}.
$$

Dropping boundary derivatives,

$$
\nabla^2\phi
=
\frac{z^2}{L^2}
\left[
\alpha(\alpha-1)z^{\alpha-2}
-(d-1)\alpha z^{\alpha-2}
\right]
=
\frac{\alpha(\alpha-d)}{L^2}z^\alpha.
$$

The equation $(\nabla^2-m^2)\phi=0$ gives

$$
\frac{\alpha(\alpha-d)}{L^2}=m^2,
$$

or

$$
\alpha(\alpha-d)=m^2L^2.
$$

</details>

### Exercise 3: AdS solves Einstein's equation

Using

$$
R_{ab}=-\frac{d}{L^2}g_{ab},
\qquad
R=-\frac{d(d+1)}{L^2},
$$

show that AdS$_{d+1}$ solves

$$
R_{ab}-\frac12Rg_{ab}+\Lambda g_{ab}=0
$$

with

$$
\Lambda=-\frac{d(d-1)}{2L^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the curvature data:

$$
R_{ab}-\frac12Rg_{ab}
=
-\frac{d}{L^2}g_{ab}
+\frac12\frac{d(d+1)}{L^2}g_{ab}.
$$

Thus

$$
R_{ab}-\frac12Rg_{ab}
=
\frac{d(d-1)}{2L^2}g_{ab}.
$$

The Einstein equation is satisfied if

$$
\frac{d(d-1)}{2L^2}g_{ab}+\Lambda g_{ab}=0,
$$

so

$$
\Lambda=-\frac{d(d-1)}{2L^2}.
$$

</details>

## Further reading

- R. M. Wald, *General Relativity*, for a clean modern treatment of curvature, variational principles, and causal structure.
- J. D. Brown and J. W. York, [Quasilocal Energy and Conserved Charges Derived from the Gravitational Action](https://arxiv.org/abs/gr-qc/9209012).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
